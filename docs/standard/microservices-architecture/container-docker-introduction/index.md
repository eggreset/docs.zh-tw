---
title: "容器和 Docker 簡介"
description: "容器化 .NET 應用程式的 .NET 微服務架構 | 容器和 Docker 簡介"
keywords: "Docker, 微服務, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 28a6e17f9c36d937ef323276c7ccc8c099844be7
ms.contentlocale: zh-tw
ms.lasthandoff: 09/05/2017

---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="81f4c-104">容器和 Docker 簡介</span><span class="sxs-lookup"><span data-stu-id="81f4c-104">Introduction to Containers and Docker</span></span>

<span data-ttu-id="81f4c-105">容器化是一種軟體開發方法，在此方法中，應用程式或服務、其相依性及其組態 (抽象化為部署資訊清單檔) 會封裝在一起，成為一個容器映像。</span><span class="sxs-lookup"><span data-stu-id="81f4c-105">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="81f4c-106">容器化應用程式可以當作一個單位來測試，並以容器映像執行個體形式部署至主機作業系統 (OS)。</span><span class="sxs-lookup"><span data-stu-id="81f4c-106">The containerized application can be tested as a unit and deployed as a container image instance to the host operating system (OS).</span></span>

<span data-ttu-id="81f4c-107">就像是貨櫃允許利用船隻、火車或貨車運輸貨物，而不論內含哪種貨物，軟體容器是軟體的標準單位，可包含不同的程式碼和相依性。</span><span class="sxs-lookup"><span data-stu-id="81f4c-107">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="81f4c-108">以此方式容器化軟體可讓開發人員和 IT 專業人員只需要一點修改或不需要任何修改，就能跨環境進行部署。</span><span class="sxs-lookup"><span data-stu-id="81f4c-108">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="81f4c-109">容器也可讓不同的應用程式在共用 OS 上彼此隔離。</span><span class="sxs-lookup"><span data-stu-id="81f4c-109">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="81f4c-110">容器化應用程式會在容器主機上執行，再於 OS (Linux 或 Windows) 上執行。</span><span class="sxs-lookup"><span data-stu-id="81f4c-110">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="81f4c-111">因此，容器所需空間明顯小於虛擬機器 (VM) 映像。</span><span class="sxs-lookup"><span data-stu-id="81f4c-111">Containers therefore have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="81f4c-112">每個容器可以執行整個 Web 應用程式或服務，如圖 2-1 所示。</span><span class="sxs-lookup"><span data-stu-id="81f4c-112">Each container can run a whole web application or a service, as shown in Figure 2-1.</span></span> <span data-ttu-id="81f4c-113">在此範例中，Docker 主機是容器主機，而 App1、App2、Svc 1 和 Svc 2 是容器化應用程式或服務。</span><span class="sxs-lookup"><span data-stu-id="81f4c-113">In this example, Docker host is a container host, and App1, App2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

![](./media/image1.png)

<span data-ttu-id="81f4c-114">**圖 2-1**.</span><span class="sxs-lookup"><span data-stu-id="81f4c-114">**Figure 2-1**.</span></span> <span data-ttu-id="81f4c-115">在容器主機上執行的多個容器</span><span class="sxs-lookup"><span data-stu-id="81f4c-115">Multiple containers running on a container host</span></span>

<span data-ttu-id="81f4c-116">容器化的另一個優點是延展性。</span><span class="sxs-lookup"><span data-stu-id="81f4c-116">Another benefit of containerization is scalability.</span></span> <span data-ttu-id="81f4c-117">您可以針對短期工作建立新的容器，以更快擴充。</span><span class="sxs-lookup"><span data-stu-id="81f4c-117">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="81f4c-118">從應用程式的觀點來看，具現化映像 (建立容器) 類似於具現化處理序 (例如服務或 Web 應用程式)。</span><span class="sxs-lookup"><span data-stu-id="81f4c-118">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="81f4c-119">不過，為了可靠起見，當您在多部主機伺服器之間執行相同映像的多個執行個體時，您通常需要在不同的主機伺服器或 VM 中，或是不同的容錯網域中，執行各個容器 (映像執行個體)。</span><span class="sxs-lookup"><span data-stu-id="81f4c-119">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="81f4c-120">簡單來說，容器在整個應用程式生命週期工作流程中，提供隔離、可攜性、彈性、延展性和控制能力等優點。</span><span class="sxs-lookup"><span data-stu-id="81f4c-120">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the whole application lifecycle workflow.</span></span> <span data-ttu-id="81f4c-121">最重要的優點是為開發與作業提供隔離。</span><span class="sxs-lookup"><span data-stu-id="81f4c-121">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="81f4c-122">[上一個] (../index.md) [下一個] (docker-defined.md)</span><span class="sxs-lookup"><span data-stu-id="81f4c-122">[Previous] (../index.md) [Next] (docker-defined.md)</span></span>
