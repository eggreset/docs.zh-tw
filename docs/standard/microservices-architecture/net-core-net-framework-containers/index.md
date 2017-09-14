---
title: "針對 Docker 容器在 .NET Core 和 .NET Framework 之間進行選擇"
description: "容器化 .NET 應用程式的 .NET 微服務架構 | 針對 Docker 容器在 .NET Core 和 .NET Framework 之間進行選擇"
keywords: "Docker, 微服務, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 5650fed27546efc1485a4617559198f03823f2de
ms.contentlocale: zh-tw
ms.lasthandoff: 09/05/2017

---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="f8ba5-104">針對 Docker 容器在 .NET Core 和 .NET Framework 之間進行選擇</span><span class="sxs-lookup"><span data-stu-id="f8ba5-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="f8ba5-105">有兩個支援的實作，可使用 .NET 來建置伺服器端容器化 Docker 應用程式：[.NET Framework](https://www.microsoft.com/net/download/framework) 及 [.NET Core](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="f8ba5-106">這兩者共用許多 .NET Standard 元件，而您可以在這兩者間共用程式碼。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="f8ba5-107">不過，兩者間有一些基本差異，而您使用的實作取決於您想要完成的目標。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="f8ba5-108">本節提供每個實作選擇時機的指引。</span><span class="sxs-lookup"><span data-stu-id="f8ba5-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f8ba5-109">[上一個] (../container-docker-introduction/docker-containers-images-registries.md) [下一個] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="f8ba5-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
