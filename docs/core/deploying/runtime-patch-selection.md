---
title: 獨立式部署執行階段向前復原
description: 了解獨立式部署的 dotnet publish 變更。
author: jralexander
ms.author: kdollard
ms.date: 05/31/2018
ms.openlocfilehash: 40d28e81e2ac1b27e7fd89e16d2d906a080fd18b
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697206"
---
# <a name="self-contained-deployment-runtime-roll-forward"></a><span data-ttu-id="86ce7-103">獨立式部署執行階段向前復原</span><span class="sxs-lookup"><span data-stu-id="86ce7-103">Self-contained deployment runtime roll forward</span></span>

<span data-ttu-id="86ce7-104">.NET Core [獨立式應用程式部署](index.md)包含 .NET Core l 程式庫和 .NET Core 執行階段。</span><span class="sxs-lookup"><span data-stu-id="86ce7-104">.NET Core [self-contained application deployments](index.md) include both the .NET Core libraries and the .NET Core runtime.</span></span> <span data-ttu-id="86ce7-105">從 .NET Core SDK 2.1.300 (.NET Core 2.1) 開始，獨立式應用程式部署[現在會發佈電腦上的最高修補程式執行階段](https://github.com/dotnet/designs/pull/36)。</span><span class="sxs-lookup"><span data-stu-id="86ce7-105">Starting in .NET Core SDK 2.1.300 (.NET Core 2.1), a self-contained application deployment [now publishes the highest patch runtime on your machine](https://github.com/dotnet/designs/pull/36).</span></span> <span data-ttu-id="86ce7-106">根據預設，用於獨立式部署的 [`dotnet publish`](../tools/dotnet-publish.md) 會選取發佈電腦上已安裝為 SDK 一部分的最新版本。</span><span class="sxs-lookup"><span data-stu-id="86ce7-106">By default,[`dotnet publish`](../tools/dotnet-publish.md) for a self-contained deployment selects the latest version installed as part of the SDK on the publishing machine.</span></span> <span data-ttu-id="86ce7-107">這可讓您部署的應用程式使用 `publish` 期間所提供的安全性修正 (和其他修正) 來執行。</span><span class="sxs-lookup"><span data-stu-id="86ce7-107">This enables your deployed application to run with security fixes (and other fixes) available during `publish`.</span></span> <span data-ttu-id="86ce7-108">應用程式必須重新發佈，才能取得新的修補程式。</span><span class="sxs-lookup"><span data-stu-id="86ce7-108">The application must be re-published to obtain a new patch.</span></span> <span data-ttu-id="86ce7-109">藉由在 `dotnet publish` 命令上指定 `-r <RID>`，或者在專案檔 (csproj / vbproj) 中或命令列上指定[執行階段識別碼 (RID)](../rid-catalog.md)，即可建立獨立式應用程式。</span><span class="sxs-lookup"><span data-stu-id="86ce7-109">Self-contained applications are created by specifying `-r <RID>` on `dotnet publish` command or by specifying the [runtime identifier (RID)](../rid-catalog.md) in the project file (csproj / vbproj) or on the command line.</span></span>

## <a name="patch-version-roll-forward-overview"></a><span data-ttu-id="86ce7-110">修補程式版本向前復原概觀</span><span class="sxs-lookup"><span data-stu-id="86ce7-110">Patch version roll forward overview</span></span>

<span data-ttu-id="86ce7-111">[`restore`](../tools/dotnet-restore.md)、[`build`](../tools/dotnet-build.md) 和 [`publish`](../tools/dotnet-publish.md) 是可以分別執行的 `dotnet` 命令。</span><span class="sxs-lookup"><span data-stu-id="86ce7-111">[`restore`](../tools/dotnet-restore.md), [`build`](../tools/dotnet-build.md) and [`publish`](../tools/dotnet-publish.md) are `dotnet` commands that can run separately.</span></span> <span data-ttu-id="86ce7-112">執行階段選擇屬於 `restore` 作業的一部分，而不是 `publish` 或 `build`。</span><span class="sxs-lookup"><span data-stu-id="86ce7-112">The runtime choice is part of the `restore` operation, not `publish` or `build`.</span></span> <span data-ttu-id="86ce7-113">如果您呼叫 `publish`，將會選擇最新的修補程式版本。</span><span class="sxs-lookup"><span data-stu-id="86ce7-113">If you call `publish`, the latest patch version will be chosen.</span></span> <span data-ttu-id="86ce7-114">如果您呼叫 `publish` 搭配 `--no-restore` 引數，則可能無法取得所需的修補程式版本，因為之前的 `restore` 可能尚未使用新的獨立式應用程式發佈原則來執行。</span><span class="sxs-lookup"><span data-stu-id="86ce7-114">If you call `publish` with the `--no-restore` argument, then you may not get the desired patch version because a prior `restore` may not have been executed with the new self-contained application publishing policy.</span></span> <span data-ttu-id="86ce7-115">在此情況下，會產生文字類似於下列內容的建置錯誤：</span><span class="sxs-lookup"><span data-stu-id="86ce7-115">In this case, a build error is generated with text similar to the following:</span></span>

  <span data-ttu-id="86ce7-116">「此專案已使用 Microsoft.NETCore.App 2.0.0　版進行還原，但以目前的設定，將改用 2.0.6 版。</span><span class="sxs-lookup"><span data-stu-id="86ce7-116">"The project was restored using Microsoft.NETCore.App version 2.0.0, but with current settings, version 2.0.6 would be used instead.</span></span> <span data-ttu-id="86ce7-117">若要解決此問題，請確定會針對還原和後續作業 (例如建置或發佈) 使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="86ce7-117">To resolve this issue, make sure the same settings are used for restore and for subsequent operations such as build or publish.</span></span> <span data-ttu-id="86ce7-118">一般來說，如果在建置或發佈期間 (而不是在還原期間) 設定了 RuntimeIdentifier 屬性，就會發生此問題。」</span><span class="sxs-lookup"><span data-stu-id="86ce7-118">Typically this issue can occur if the RuntimeIdentifier property is set during build or publish but not during restore."</span></span>

> [!NOTE]
> <span data-ttu-id="86ce7-119">`restore` 和 `build` 可以當作另一個命令 (如 `publish`) 的一部分隱含執行。</span><span class="sxs-lookup"><span data-stu-id="86ce7-119">`restore` and `build` can be run implicitly as part of another command, like `publish`.</span></span> <span data-ttu-id="86ce7-120">作為另一個命令的一部分以隱含方式執行時，會提供其他內容給它們，以便產生正確的成品。</span><span class="sxs-lookup"><span data-stu-id="86ce7-120">When run implicitly as part of another command, they are provided with additional context so that the right artifacts are produced.</span></span> <span data-ttu-id="86ce7-121">當您搭配執行階段進行 `publish` (例如，`dotnet publish -r linux-x64`)，隱含的 `restore` 會還原 linux-x64 執行階段的套件。</span><span class="sxs-lookup"><span data-stu-id="86ce7-121">When you `publish` with a runtime (for example, `dotnet publish -r linux-x64`), the implicit `restore` restores packages for the linux-x64 runtime.</span></span> <span data-ttu-id="86ce7-122">如果您明確地呼叫 `restore`，預設不會還原執行階段套件，因為它並沒有該內容。</span><span class="sxs-lookup"><span data-stu-id="86ce7-122">If you call `restore` explicitly, it does not restore runtime packages by default, because it doesn't have that context.</span></span>

## <a name="how-to-avoid-restore-during-publish"></a><span data-ttu-id="86ce7-123">如何避免在發佈期間進行還原</span><span class="sxs-lookup"><span data-stu-id="86ce7-123">How to avoid restore during publish</span></span>

<span data-ttu-id="86ce7-124">執行 `restore` 作為 `publish` 作業的一部分有時候可能不適用於您的情況。</span><span class="sxs-lookup"><span data-stu-id="86ce7-124">Running `restore` as part of the `publish` operation may be undesirable for your scenario.</span></span> <span data-ttu-id="86ce7-125">若要在建立獨立式應用程式時避免在 `publish` 期間進行 `restore`，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="86ce7-125">To avoid `restore` during `publish` while creating self-contained applications, do the following:</span></span>

* <span data-ttu-id="86ce7-126">將 `RuntimeIdentifiers` 屬性設定為要發佈之所有 [RID](../rid-catalog.md) 的分號分隔清單</span><span class="sxs-lookup"><span data-stu-id="86ce7-126">Set the `RuntimeIdentifiers` property to a semicolon-separated list of all the [RIDs](../rid-catalog.md) to be published</span></span>
* <span data-ttu-id="86ce7-127">將 `TargetLatestRuntimePatch` 屬性設定為 `true`</span><span class="sxs-lookup"><span data-stu-id="86ce7-127">Set the `TargetLatestRuntimePatch` property to `true`</span></span>

## <a name="no-restore-argument-with-dotnet-publish-options"></a><span data-ttu-id="86ce7-128">No-restore 引數搭配 dotnet publish 選項</span><span class="sxs-lookup"><span data-stu-id="86ce7-128">No-restore argument with dotnet publish options</span></span>

<span data-ttu-id="86ce7-129">如果您想要使用相同的專案檔同時建立獨立式應用程式和[與架構相依的應用程式](index.md)，而且想要使用 `--no-restore` 引數搭配 `dotnet publish`，則選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="86ce7-129">If you want to create both self-contained applications and [framework-dependent applications](index.md) with the same project file, and you want to use the `--no-restore` argument with `dotnet publish`, then choose one of the following:</span></span>

1. <span data-ttu-id="86ce7-130">偏好與架構相依的行為。</span><span class="sxs-lookup"><span data-stu-id="86ce7-130">Prefer the framework-dependent behavior.</span></span> <span data-ttu-id="86ce7-131">如果應用程式是與架構相依的應用程式，這是預設行為。</span><span class="sxs-lookup"><span data-stu-id="86ce7-131">If the application is framework-dependent, this is the default behavior.</span></span> <span data-ttu-id="86ce7-132">如果應用程式是獨立式應用程式，且可以使用未修補的 2.1.0 本機執行階段，請在專案檔 (csproj / vbproj) 中將 `TargetLatestRuntimePatch` 設定為 `false`。</span><span class="sxs-lookup"><span data-stu-id="86ce7-132">If the application is self-contained, and can use an unpatched 2.1.0 local runtime, set the `TargetLatestRuntimePatch` to `false` in the project file (csproj / vbproj).</span></span>

2. <span data-ttu-id="86ce7-133">偏好獨立式行為。</span><span class="sxs-lookup"><span data-stu-id="86ce7-133">Prefer the self-contained behavior.</span></span> <span data-ttu-id="86ce7-134">如果應用程式是獨立式應用程式，這是預設行為。</span><span class="sxs-lookup"><span data-stu-id="86ce7-134">If the application is self-contained, this is the default behavior.</span></span> <span data-ttu-id="86ce7-135">如果應用程式是與架構相依的應用程式，且需要安裝最新的修補程式，請在專案檔 (csproj / vbproj) 中將 `TargetLatestRuntimePatch` 設定為 `true`。</span><span class="sxs-lookup"><span data-stu-id="86ce7-135">If the application is framework-dependent, and requires the latest patch installed, set `TargetLatestRuntimePatch` to `true` in the project file (csproj / vbproj).</span></span>

3. <span data-ttu-id="86ce7-136">在專案檔 (csproj / vbproj) 中將 `RuntimeFrameworkVersion` 設定為特定的修補程式版本，藉以取得執行階段架構版本的明確控制權。</span><span class="sxs-lookup"><span data-stu-id="86ce7-136">Take explicit control of the runtime framework version by setting `RuntimeFrameworkVersion` to the specific patch version in the project file (csproj / vbproj).</span></span>