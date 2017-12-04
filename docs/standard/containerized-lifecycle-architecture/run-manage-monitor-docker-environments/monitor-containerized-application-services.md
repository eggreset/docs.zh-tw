---
title: "監視進行容器化應用程式服務"
description: "Microsoft 平台和工具與 Docker 容器化應用程式生命週期"
keywords: "Docker, 微服務, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3e4a78eb47d0e6712919c89b6f52ec8e4248fb23
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2017
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="8ea89-104">監視進行容器化應用程式服務</span><span class="sxs-lookup"><span data-stu-id="8ea89-104">Monitor containerized application services</span></span>

<span data-ttu-id="8ea89-105">務必將分割成多個容器和 microservices 的應用程式提供的方式來監視及分析應用程式的行為。</span><span class="sxs-lookup"><span data-stu-id="8ea89-105">It is critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the application.</span></span>

## <a name="microsoft-application-insights"></a><span data-ttu-id="8ea89-106">Microsoft Application Insights</span><span class="sxs-lookup"><span data-stu-id="8ea89-106">Microsoft Application Insights</span></span>

<span data-ttu-id="8ea89-107">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)是監視即時應用程式的可延伸的分析服務。</span><span class="sxs-lookup"><span data-stu-id="8ea89-107">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="8ea89-108">它可以協助您偵測及診斷效能問題，以及了解使用者實際執行的工作與您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ea89-108">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="8ea89-109">它被針對開發人員，可幫助您的意圖，持續改善效能，而且您的服務或應用程式的可用性。</span><span class="sxs-lookup"><span data-stu-id="8ea89-109">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="8ea89-110">Application Insights 適用於 web/服務和獨立各種不同的平台，例如.NET、 Java、 Node.js 和許多其他平台，裝載於內部部署或雲端上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ea89-110">Application Insights works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a><span data-ttu-id="8ea89-111">分析使用 Application Insights 的 QA 環境 Docker 應用程式</span><span class="sxs-lookup"><span data-stu-id="8ea89-111">Analyzing Docker apps in QA environments using Application Insights</span></span>

<span data-ttu-id="8ea89-112">因為它屬於 Docker 時，您可以圖表生命週期事件和效能計數器，從 Application Insights 上的 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="8ea89-112">As it pertains to Docker, you can chart life-cycle events and performance counters from Docker containers on Application Insights.</span></span> <span data-ttu-id="8ea89-113">您只需要執行[應用程式 Insights Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)因為在您的主機和它的容器將會顯示效能計數器的主機，以及其他的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="8ea89-113">You just need to run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) as a container in your host, and it will display performance counters for the host as well as for the other Docker images.</span></span> <span data-ttu-id="8ea89-114">此應用程式 Insights Docker 映像 (圖 6-1） 可協助您監視您容器化應用程式所收集的效能和活動的 Docker 主機 (也就是您 Linux Vm)、 Docker 容器和執行的應用程式的遙測在其中。</span><span class="sxs-lookup"><span data-stu-id="8ea89-114">This Application Insights Docker image (Figure 6-1) helps you to monitor your containerized applications by collecting telemetry about the performance and activity of your Docker host (that is, your Linux VMs), Docker containers and the applications running within them.</span></span>

![範例](./media/image1.png)

<span data-ttu-id="8ea89-116">圖 6-1: Application Insights 監視 Docker 主機和容器</span><span class="sxs-lookup"><span data-stu-id="8ea89-116">Figure 6-1: Application Insights monitoring Docker hosts and containers</span></span>

<span data-ttu-id="8ea89-117">當您執行[應用程式 Insights Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)上 Docker 主機時，您可以從下列：</span><span class="sxs-lookup"><span data-stu-id="8ea89-117">When you run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) on your Docker host, you benefit from the following:</span></span>

-   <span data-ttu-id="8ea89-118">生命週期有關主機上執行的所有容器的遙測，啟動、 停止和等等。</span><span class="sxs-lookup"><span data-stu-id="8ea89-118">Life-cycle telemetry about all the containers running on the host—start, stop, and so on.</span></span>

-   <span data-ttu-id="8ea89-119">效能計數器的所有容器： CPU、 記憶體、 網路使用量，等等。</span><span class="sxs-lookup"><span data-stu-id="8ea89-119">Performance counters for all the containers: CPU, memory, network usage, and more.</span></span>

-   <span data-ttu-id="8ea89-120">如果您同時安裝[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)在容器中執行的應用程式，這些應用程式的所有遙測資料會用來識別容器與主機電腦的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="8ea89-120">If you also installed [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in the apps running in the containers, all the telemetry of those apps will have additional properties identifying the container and host machine.</span></span> <span data-ttu-id="8ea89-121">因此，比方說，如果您有一個以上的主機中執行的應用程式的執行個體，您輕鬆地可以篩選您的應用程式遙測，由主應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ea89-121">So, for example, if you have instances of an app running in more than one host, you'll easily be able to filter your app telemetry by host.</span></span>

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a><span data-ttu-id="8ea89-122">設定 Application Insights 以監視 Docker 應用程式和 Docker 主機</span><span class="sxs-lookup"><span data-stu-id="8ea89-122">Setting up Application Insights to monitor Docker applications and Docker hosts</span></span>

<span data-ttu-id="8ea89-123">若要建立 Application Insights 資源，請遵循下列清單中顯示的文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="8ea89-123">To create an Application Insights resource, follow the instructions in the articles presented in the list that follows.</span></span> <span data-ttu-id="8ea89-124">Azure 入口網站會為您建立必要的指令碼。</span><span class="sxs-lookup"><span data-stu-id="8ea89-124">Azure Portal will create the necessary script for you.</span></span>

-   <span data-ttu-id="8ea89-125">**監視 Docker Application Insights 中的應用程式：**[https://docs.microsoft.com/azure/application-insights/app-insights-docker  ](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span><span class="sxs-lookup"><span data-stu-id="8ea89-125">**Monitor Docker applications in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span></span>

-   <span data-ttu-id="8ea89-126">**應用程式在 Docker Hub 和 Github Insights Docker 映像：**</span><span class="sxs-lookup"><span data-stu-id="8ea89-126">**Application Insights Docker image at Docker Hub and Github:**</span></span>  
<span data-ttu-id="8ea89-127">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/)和<https://github.com/Microsoft/ApplicationInsights-Docker></span><span class="sxs-lookup"><span data-stu-id="8ea89-127">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) and <https://github.com/Microsoft/ApplicationInsights-Docker></span></span>

-   <span data-ttu-id="8ea89-128">**設定 ASP.NET 的 Application Insights:**</span><span class="sxs-lookup"><span data-stu-id="8ea89-128">**Set up Application Insights for ASP.NET:**</span></span>  
[<span data-ttu-id="8ea89-129">https://docs.microsoft.com/azure/application-insights/app-insights-asp-net</span><span class="sxs-lookup"><span data-stu-id="8ea89-129">https://docs.microsoft.com/azure/application-insights/app-insights-asp-net</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   <span data-ttu-id="8ea89-130">**網頁的應用程式 Insights:**</span><span class="sxs-lookup"><span data-stu-id="8ea89-130">**Application Insights for web pages:**</span></span>  
<span data-ttu-id="8ea89-131"><https://docs.microsoft.com/azure/application-insights/app-insights-javascript></span><span class="sxs-lookup"><span data-stu-id="8ea89-131"><https://docs.microsoft.com/azure/application-insights/app-insights-javascript></span></span>

## <a name="microsoft-operations-management-suite"></a><span data-ttu-id="8ea89-132">Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="8ea89-132">Microsoft Operations Management Suite</span></span>

<span data-ttu-id="8ea89-133">[Operations Management Suite](http://microsoft.com/oms)是簡化的 IT 管理解決方案，讓記錄分析、 自動化、 備份和站台復原。</span><span class="sxs-lookup"><span data-stu-id="8ea89-133">[Operations Management Suite](http://microsoft.com/oms) is a simplified IT management solution that provides log analytics, automation, backup, and site recovery.</span></span> <span data-ttu-id="8ea89-134">根據[查詢](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/)在 Operations Management Suite，您可以提高[警示](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts)並將設定透過補救[Azure 自動化](https://docs.microsoft.com/azure/automation/)。</span><span class="sxs-lookup"><span data-stu-id="8ea89-134">Based on [queries](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, you can raise [alerts](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) and set remediation via [Azure Automation](https://docs.microsoft.com/azure/automation/).</span></span> <span data-ttu-id="8ea89-135">它也與緊密整合您現有的管理解決方案，以提供單一的半透明窗格的檢視。</span><span class="sxs-lookup"><span data-stu-id="8ea89-135">It also seamlessly integrates with your existing management solutions to provide a single pane-of-glass view.</span></span> <span data-ttu-id="8ea89-136">Operations Management Suite 的資訊可協助您管理及保護在內部部署與雲端基礎結構。</span><span class="sxs-lookup"><span data-stu-id="8ea89-136">Operations Management Suite helps you to manage and protect your on-premises and cloud infrastructure.</span></span>

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a><span data-ttu-id="8ea89-137">[Operations Management Suite](http://microsoft.com/oms) Docker 容器解決方案</span><span class="sxs-lookup"><span data-stu-id="8ea89-137">[Operations Management Suite](http://microsoft.com/oms) Container Solution for Docker</span></span>

<span data-ttu-id="8ea89-138">除了提供重要服務本身，Operations Management Suite 容器解決方案管理和監視 Docker 主機和容器，以顯示的詳細資訊，您的容器和容器主機，執行容器或失敗，並傳送至 Docker 精靈和容器記錄*stdout*和*stderr*。</span><span class="sxs-lookup"><span data-stu-id="8ea89-138">In addition to providing valuable services on its own, the Operations Management Suite Container Solution can manage and monitor Docker hosts and containers by showing information about where your containers and container hosts are, which containers are running or failed, and Docker daemon and container logs sent to *stdout* and *stderr*.</span></span> <span data-ttu-id="8ea89-139">它也會顯示效能度量，例如 CPU、 記憶體、 網路和儲存體容器和主機，以協助您疑難排解並尋找容器有很多雜訊的像素。</span><span class="sxs-lookup"><span data-stu-id="8ea89-139">It also shows performance metrics such as CPU, memory, network, and storage for the container and hosts to help you troubleshoot and find noisy neighbor containers.</span></span>

![](./media/image2.png)

<span data-ttu-id="8ea89-140">圖 6-2： 顯示 Operations Management Suite 的 Docker 容器資訊</span><span class="sxs-lookup"><span data-stu-id="8ea89-140">Figure 6-2: Information about Docker containers shown by Operations Management Suite</span></span>

<span data-ttu-id="8ea89-141">Application Insights 和 Operations Management Suite 焦點放在監視活動。不過，Application Insights 著重於多監視的應用程式本身由於其應用程式內執行的 SDK。</span><span class="sxs-lookup"><span data-stu-id="8ea89-141">Application Insights and Operations Management Suite both focus on monitoring activities; however, Application Insights focuses more on monitoring the apps themselves thanks to its SDK running within the app.</span></span> <span data-ttu-id="8ea89-142">不過，Operations Management Suite 更著重於基礎結構主機，周圍加上它同時提供富彈性，資料驅動型搜尋/查詢系統提供記錄在標尺上的深入分析。</span><span class="sxs-lookup"><span data-stu-id="8ea89-142">However, Operations Management Suite focuses much more on the infrastructure around the hosts, plus it offers deep analysis on logs at scale while providing a very flexible data-driven search/query system.</span></span>

<span data-ttu-id="8ea89-143">Operations Management Suite 會實作為雲端式服務，因為您可以將它啟動並執行快速且需基礎結構服務中的最小投資。</span><span class="sxs-lookup"><span data-stu-id="8ea89-143">Because Operations Management Suite is implemented as a cloud-based service, you can have it up and running quickly with minimal investment in infrastructure services.</span></span> <span data-ttu-id="8ea89-144">新功能會自動傳遞，儲存您從持續性維護和升級的成本。</span><span class="sxs-lookup"><span data-stu-id="8ea89-144">New features are delivered automatically, saving you from ongoing maintenance and upgrade costs.</span></span>

<span data-ttu-id="8ea89-145">使用 Operations Management Suite 容器解決方案，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8ea89-145">Using Operations Management Suite Container Solution, you can do the following:</span></span>

-   <span data-ttu-id="8ea89-146">集中管理及相互關聯數百萬從大規模的 Docker 容器的記錄檔</span><span class="sxs-lookup"><span data-stu-id="8ea89-146">Centralize and correlate millions of logs from Docker containers at scale</span></span>

-   <span data-ttu-id="8ea89-147">請參閱在單一位置中的所有容器主機的資訊</span><span class="sxs-lookup"><span data-stu-id="8ea89-147">See information about all container hosts in a single location</span></span>

-   <span data-ttu-id="8ea89-148">知道哪些容器執行時，哪些映像它們正在執行，並執行所在</span><span class="sxs-lookup"><span data-stu-id="8ea89-148">Know which containers are running, what image they're running, and where they're running</span></span>

-   <span data-ttu-id="8ea89-149">快速診斷可能會造成問題，容器主機的 「 雜訊芳鄰"容器</span><span class="sxs-lookup"><span data-stu-id="8ea89-149">Quickly diagnose "noisy neighbor" containers that can cause problems on container hosts</span></span>

-   <span data-ttu-id="8ea89-150">在容器上看到動作的稽核線索</span><span class="sxs-lookup"><span data-stu-id="8ea89-150">See an audit trail for actions on containers</span></span>

-   <span data-ttu-id="8ea89-151">透過檢視和搜尋沒有遠端 Docker 主機可集中式的記錄進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="8ea89-151">Troubleshoot by viewing and searching centralized logs without remoting to the Docker hosts</span></span>

-   <span data-ttu-id="8ea89-152">尋找可能"雜訊的鄰近項目 」、 在主機上的耗用過多資源的容器</span><span class="sxs-lookup"><span data-stu-id="8ea89-152">Find containers that might be "noisy neighbors" and consuming excess resources on a host</span></span>

-   <span data-ttu-id="8ea89-153">集中式的 CPU、 記憶體、 儲存和容器的網路使用量和效能資訊檢視</span><span class="sxs-lookup"><span data-stu-id="8ea89-153">View centralized CPU, memory, storage, and network usage and performance information for containers</span></span>

-   <span data-ttu-id="8ea89-154">產生測試與 Azure 自動化的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="8ea89-154">Generate test Docker containers with Azure Automation</span></span>

<span data-ttu-id="8ea89-155">您可以查看所執行的查詢類型的效能資訊 = 效能，如圖 6-3 所示。</span><span class="sxs-lookup"><span data-stu-id="8ea89-155">You can see performance information by running queries like Type=Perf, as shown in Figure 6-3.</span></span>

![DockerPerfMetricsView](./media/image3.png)<span data-ttu-id="8ea89-157">{寬度 ="5.78625 in"height ="3.25 in"}</span><span class="sxs-lookup"><span data-stu-id="8ea89-157">{width="5.78625in" height="3.25in"}</span></span>

<span data-ttu-id="8ea89-158">圖 6-3： 效能度量的顯示 Operations Management Suite 的 Docker 主機</span><span class="sxs-lookup"><span data-stu-id="8ea89-158">Figure 6-3: Performance metrics of Docker hosts shown by Operations Management Suite</span></span>

<span data-ttu-id="8ea89-159">儲存查詢也是在 Operations Management Suite 中的標準功能，可協助您讓查詢所找到有用，並找出您的系統中的趨勢。</span><span class="sxs-lookup"><span data-stu-id="8ea89-159">Saving queries is also a standard feature in Operations Management Suite and can help you keep queries you've found useful and discover trends in your system.</span></span>

<span data-ttu-id="8ea89-160">**進一歩** 找到有關安裝和設定 Docker 容器中的方案[Operations Management Suite](http://microsoft.com/oms)，請移至<https://docs.microsoft.com/azure/記錄檔-分析/記錄檔-分析-容器>。</span><span class="sxs-lookup"><span data-stu-id="8ea89-160">**More info** To find information on installing and configuring the Docker container solution in [Operations Management Suite](http://microsoft.com/oms), go to <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8ea89-161">[上一個](管理-生產-docker-environments.md) [下一步] (.../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="8ea89-161">[Previous] (manage-production-docker-environments.md) [Next] (../key-takeaways/index.md)</span></span>