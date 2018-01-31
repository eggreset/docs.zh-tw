---
title: "Microsoft WCF Web Service Reference Provider 工具"
description: "新增 .NET Core 和 ASP.NET Core 專案功能的 Microsoft WCF Web Service Reference Provider 工具概觀，與 .NET Framework 專案的「新增服務參考」類似。"
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: e445361f9f4a858f4b34ca1008670fadc62b8b3c
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2018
---
# <a name="microsoft-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="1db3a-103">Microsoft WCF Web Service Reference Provider 工具</span><span class="sxs-lookup"><span data-stu-id="1db3a-103">Microsoft WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="1db3a-104">多年來，許多 Visual Studio 開發人員都享受[**新增服務參考**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)工具在其 .NET Framework 專案需要存取 Web 服務時所提供的生產力。</span><span class="sxs-lookup"><span data-stu-id="1db3a-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="1db3a-105">**WCF Web Service Reference** 工具是 Visual Studio 連線服務延伸模組，以針對 .NET Core 和 ASP.NET Core 專案提供「新增服務參考」功能這類體驗。</span><span class="sxs-lookup"><span data-stu-id="1db3a-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="1db3a-106">此工具可從目前方案中的 Web 服務、網路位置或 WSDL 檔案擷取中繼資料，且能產生與 .NET Core 相容的來源檔案，其中包含的 Windows Communication Foundation (WCF) 用戶端 Proxy 程式碼可讓您用於存取 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="1db3a-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1db3a-107">您只應該參考來自信任來源的服務。</span><span class="sxs-lookup"><span data-stu-id="1db3a-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="1db3a-108">新增不信任來源的參考可能會危及安全性。</span><span class="sxs-lookup"><span data-stu-id="1db3a-108">Adding references from an untrusted source may compromise security.</span></span> 

## <a name="how-to-use-the-extension"></a><span data-ttu-id="1db3a-109">如何使用延伸模組</span><span class="sxs-lookup"><span data-stu-id="1db3a-109">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="1db3a-110">**WCF Web Service Reference** 選項適用於使用下列專案範本建立的專案：</span><span class="sxs-lookup"><span data-stu-id="1db3a-110">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
> * <span data-ttu-id="1db3a-111">**Visual C#** > **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="1db3a-111">**Visual C#** > **.NET Core**</span></span>
> * <span data-ttu-id="1db3a-112">**Visual C#** > **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="1db3a-112">**Visual C#** > **.NET Standard**</span></span>
> * <span data-ttu-id="1db3a-113">**Visual C#** > **Web** > **ASP.NET Core Web 應用程式**</span><span class="sxs-lookup"><span data-stu-id="1db3a-113">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="1db3a-114">使用 **ASP.NET Core Web 應用程式** 專案範本作為範例，本文會引導您完成將 WCF 服務參考新增至專案：</span><span class="sxs-lookup"><span data-stu-id="1db3a-114">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="1db3a-115">在方案總管中，按兩下專案的 [已連線的服務] 節點 (針對 .NET Core 或 .NET Standard 專案，在方案總管中，以滑鼠右鍵按一下專案的 [相依性] 節點時，可以使用此選項)。</span><span class="sxs-lookup"><span data-stu-id="1db3a-115">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

<span data-ttu-id="1db3a-116">[已連線的服務] 頁面隨即顯示 (如下圖所示)：</span><span class="sxs-lookup"><span data-stu-id="1db3a-116">The **Connected Services** page appears as shown in the following image:</span></span>

![已連線的服務索引標籤](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="1db3a-118">在 [已連線的服務] 頁面上，按一下 [Microsoft WCF Web Service Reference Provider]。</span><span class="sxs-lookup"><span data-stu-id="1db3a-118">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="1db3a-119">這會啟動 [設定 WCF Web 服務參考精靈]：</span><span class="sxs-lookup"><span data-stu-id="1db3a-119">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

![服務端點索引標籤](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="1db3a-121">選取服務。</span><span class="sxs-lookup"><span data-stu-id="1db3a-121">Select a service.</span></span>

    <span data-ttu-id="1db3a-122">3a.</span><span class="sxs-lookup"><span data-stu-id="1db3a-122">3a.</span></span> <span data-ttu-id="1db3a-123">[設定 WCF Web 服務參考精靈] 內有數個服務搜尋選項可用：</span><span class="sxs-lookup"><span data-stu-id="1db3a-123">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>
    
     * <span data-ttu-id="1db3a-124">若要搜尋目前方案中所定義的服務，請按一下 [探索] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1db3a-124">To search for services defined in the current solution, click the **Discover** button.</span></span> 
     * <span data-ttu-id="1db3a-125">若要搜尋所指定位址裝載的服務，請在 [位址] 方塊中輸入服務 URL，然後按一下 [執行] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1db3a-125">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="1db3a-126">若要選取包含 Web 服務中繼資料資訊的 WSDL 檔案，請按一下 [瀏覽] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1db3a-126">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span> 
     
    <span data-ttu-id="1db3a-127">3b.</span><span class="sxs-lookup"><span data-stu-id="1db3a-127">3b.</span></span> <span data-ttu-id="1db3a-128">在 [服務] 方塊中，從搜尋結果清單中選取服務。</span><span class="sxs-lookup"><span data-stu-id="1db3a-128">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="1db3a-129">如有需要，請在對應的 [命名空間] 文字方塊中輸入已產生程式碼的命名空間。</span><span class="sxs-lookup"><span data-stu-id="1db3a-129">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>
    
    <span data-ttu-id="1db3a-130">3c.</span><span class="sxs-lookup"><span data-stu-id="1db3a-130">3c.</span></span> <span data-ttu-id="1db3a-131">按一下 [下一步] 按鈕以開啟 [資料類型選項] 和 [用戶端選項] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1db3a-131">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="1db3a-132">或者，按一下 [完成] 按鈕以使用預設選項。</span><span class="sxs-lookup"><span data-stu-id="1db3a-132">Alternatively, click the **Finish** button to use the default options.</span></span>


4. <span data-ttu-id="1db3a-133">[資料類型選項] 表單可讓您精簡所產生的服務參考組態設定：</span><span class="sxs-lookup"><span data-stu-id="1db3a-133">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

![資料類型選項索引標籤](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

> [!NOTE]
> <span data-ttu-id="1db3a-135">其中一個專案的參考組件內定義服務參考程式碼產生所需的資料類型時，[重複使用參考組件中的類型] 核取方塊選項十分有用。</span><span class="sxs-lookup"><span data-stu-id="1db3a-135">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="1db3a-136">請務必重複使用這些現有資料類型，避免造成編譯時期類型衝突或執行階段問題。</span><span class="sxs-lookup"><span data-stu-id="1db3a-136">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

<span data-ttu-id="1db3a-137">根據專案相依性數目和其他系統效能因素，在載入類型資訊時可能會延遲。</span><span class="sxs-lookup"><span data-stu-id="1db3a-137">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="1db3a-138">除非取消核取 [重複使用參考組件中的類型] 核取方塊，否則會在載入期間停用 [完成] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1db3a-138">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="1db3a-139">完成時，請按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="1db3a-139">Click **Finish** when you are done.</span></span>


<span data-ttu-id="1db3a-140">顯示進度時，此工具會：</span><span class="sxs-lookup"><span data-stu-id="1db3a-140">While displaying progress, the tool:</span></span>

* <span data-ttu-id="1db3a-141">從 WCF 服務下載中繼資料。</span><span class="sxs-lookup"><span data-stu-id="1db3a-141">Downloads metadata from the WCF service.</span></span> 
* <span data-ttu-id="1db3a-142">在名為 *reference.cs* 的檔案中產生服務參考程式碼，並將它新增至 [已連線的服務] 節點下方的專案。</span><span class="sxs-lookup"><span data-stu-id="1db3a-142">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span> 
* <span data-ttu-id="1db3a-143">使用在目標平台上編譯和執行所需的 NuGet 套件參考來更新專案檔 (.csproj)。</span><span class="sxs-lookup"><span data-stu-id="1db3a-143">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![進度視窗](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="1db3a-145">完成這些程序時，您可以建立已產生 WCF 用戶端類型的執行個體，並叫用服務作業。</span><span class="sxs-lookup"><span data-stu-id="1db3a-145">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1db3a-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1db3a-146">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="1db3a-147">意見反應和問題</span><span class="sxs-lookup"><span data-stu-id="1db3a-147">Feedback & questions</span></span>
<span data-ttu-id="1db3a-148">如果您有任何問題或意見反應，請[在 GitHub 上開啟問題](https://github.com/dotnet/wcf/issues/new)。</span><span class="sxs-lookup"><span data-stu-id="1db3a-148">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="1db3a-149">您也可以[在 GitHub 的 WCF 存放庫](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling)檢閱任何現有問題或議題。</span><span class="sxs-lookup"><span data-stu-id="1db3a-149">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="1db3a-150">版本資訊</span><span class="sxs-lookup"><span data-stu-id="1db3a-150">Release notes</span></span>
* <span data-ttu-id="1db3a-151">如需已更新的版本資訊，請參閱[版本資訊](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) (包含已知問題)。</span><span class="sxs-lookup"><span data-stu-id="1db3a-151">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span> 