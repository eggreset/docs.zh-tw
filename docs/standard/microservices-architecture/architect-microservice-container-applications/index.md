---
title: "架構容器和微服務應用程式"
description: "容器化 .NET 應用程式的 .NET 微服務架構 | 架構容器和微服務應用程式"
keywords: "Docker, 微服務, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 360b4745e768a751154f3f1445ffb0bf5b62c825
ms.contentlocale: zh-tw
ms.lasthandoff: 09/05/2017

---
# <a name="architecting-container--and-microservice-based-applications"></a><span data-ttu-id="3229d-104">架構容器和微服務應用程式</span><span class="sxs-lookup"><span data-stu-id="3229d-104">Architecting Container- and Microservice-Based Applications</span></span>

<span data-ttu-id="3229d-105">*Microservices 提供極大的好處，但也會引發龐大的新挑戰。當建立微服務應用程式時，會以微服務架構模式為基礎。*</span><span class="sxs-lookup"><span data-stu-id="3229d-105">*Microservices offer great benefits but also raise huge new challenges. Microservice architecture patterns are fundamental pillars when creating a microservice-based application.*</span></span>

<span data-ttu-id="3229d-106">稍早在本指南中，您了解有關容器和 Docker 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="3229d-106">Earlier in this guide, you learned basic concepts about containers and Docker.</span></span> <span data-ttu-id="3229d-107">這是您開始使用容器所需的基本資訊。</span><span class="sxs-lookup"><span data-stu-id="3229d-107">That was the minimum information you need in order to get started with containers.</span></span> <span data-ttu-id="3229d-108">雖然容器是啟用程式且非常適合微服務，但對微服務架構而言絕非必要，而且本架構章節中的許多架構概念在沒有容器的情況下也適用。</span><span class="sxs-lookup"><span data-stu-id="3229d-108">Although, even when containers are enablers and a great fit for microservices, they are not mandatory for a microservice architecture and many architectural concepts in this architecture section could be applied without containers, too.</span></span> <span data-ttu-id="3229d-109">不過，由於已介紹過容器的重要性，因此本指南會將重點放在這兩者的交集。</span><span class="sxs-lookup"><span data-stu-id="3229d-109">However, this guidance focuses on the intersection of both due to the already introduced importance of containers.</span></span>

<span data-ttu-id="3229d-110">企業應用程式可能很複雜，而且通常是由多個服務而不是單一服務應用程式所組成。</span><span class="sxs-lookup"><span data-stu-id="3229d-110">Enterprise applications can be complex and are often composed of multiple services instead of a single service-based application.</span></span> <span data-ttu-id="3229d-111">針對這些案例，您必須了解其他架構方法，例如微服務和特定領域驅動設計 (Domain-Driven Design，DDD) 模式，以及容器協調流程概念。</span><span class="sxs-lookup"><span data-stu-id="3229d-111">For those cases, you need to understand additional architectural approaches, such as the microservices and certain domain-driven design (DDD) patterns plus container orchestration concepts.</span></span> <span data-ttu-id="3229d-112">請注意，本章不只描述容器上的微服務，也描述任何容器化應用程式。</span><span class="sxs-lookup"><span data-stu-id="3229d-112">Note that this chapter describes not just microservices on containers, but any containerized application, as well.</span></span>

## <a name="container-design-principles"></a><span data-ttu-id="3229d-113">容器設計原則</span><span class="sxs-lookup"><span data-stu-id="3229d-113">Container design principles</span></span>

<span data-ttu-id="3229d-114">在容器模型中，容器映像執行個體代表單一處理序。</span><span class="sxs-lookup"><span data-stu-id="3229d-114">In the container model, a container image instance represents a single process.</span></span> <span data-ttu-id="3229d-115">藉由將容器映像定義為處理序邊界，您可以建立基本類型，以便用來調整處理序或對它進行批次處理。</span><span class="sxs-lookup"><span data-stu-id="3229d-115">By defining a container image as a process boundary, you can create primitives that can be used to scale the process or to batch it.</span></span>

<span data-ttu-id="3229d-116">當您設計容器映像時，您會在 Dockerfile 中看到 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/) 定義。</span><span class="sxs-lookup"><span data-stu-id="3229d-116">When you design a container image, you will see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/) definition in the Dockerfile.</span></span> <span data-ttu-id="3229d-117">這會定義處理序，其存留期間可控制容器的存留期。</span><span class="sxs-lookup"><span data-stu-id="3229d-117">This defines the process whose lifetime controls the lifetime of the container.</span></span> <span data-ttu-id="3229d-118">當處理序完成時，容器生命週期即告結束。</span><span class="sxs-lookup"><span data-stu-id="3229d-118">When the process completes, the container lifecycle ends.</span></span> <span data-ttu-id="3229d-119">容器可能代表長時間執行的處理序 (例如網頁伺服器)，但也可能代表短期處理序 (例如之前可能已實作為 Azure [WebJobs](https://docs.microsoft.com/azure/app-service-web/websites-webjobs-resources) 的批次工作)。</span><span class="sxs-lookup"><span data-stu-id="3229d-119">Containers might represent long-running processes like web servers, but can also represent short-lived processes like batch jobs, which formerly might have been implemented as Azure [WebJobs](https://docs.microsoft.com/azure/app-service-web/websites-webjobs-resources).</span></span>

<span data-ttu-id="3229d-120">如果處理序失敗，容器會結束並由 Orchestrator 接管。</span><span class="sxs-lookup"><span data-stu-id="3229d-120">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="3229d-121">如果 Orchestrator 已設定為保留五個執行中的執行個體，且其中一個失敗，Orchestrator 將會建立另一個容器執行個體，來取代失敗的處理序。</span><span class="sxs-lookup"><span data-stu-id="3229d-121">If the orchestrator was configured to keep five instances running and one fails, the orchestrator will create another container instance to replace the failed process.</span></span> <span data-ttu-id="3229d-122">在批次工作中，處理序是透過參數來啟動。</span><span class="sxs-lookup"><span data-stu-id="3229d-122">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="3229d-123">當處理序完成時，工作即告完成。</span><span class="sxs-lookup"><span data-stu-id="3229d-123">When the process completes, the work is complete.</span></span>

<span data-ttu-id="3229d-124">您可能發現有時需要在單一容器中執行多個處理序。</span><span class="sxs-lookup"><span data-stu-id="3229d-124">You might find a scenario where you want multiple processes running in a single container.</span></span> <span data-ttu-id="3229d-125">在此情況下，由於每個容器只能有一個進入點，因此您可以在容器中執行指令碼來視需要啟動許多程式。</span><span class="sxs-lookup"><span data-stu-id="3229d-125">For that scenario, since there can be only one entry point per container, you could run a script within the container that launches as many programs as needed.</span></span> <span data-ttu-id="3229d-126">例如，您可以使用 [Supervisor](http://supervisord.org/) 或類似工具，在單一容器中啟動多個處理序。</span><span class="sxs-lookup"><span data-stu-id="3229d-126">For example, you can use [Supervisor](http://supervisord.org/) or a similar tool to take care of launching multiple processes inside a single container.</span></span> <span data-ttu-id="3229d-127">不過，即使您可能發現在每個容器中保留多個處理序的架構，但該方法並不常見。</span><span class="sxs-lookup"><span data-stu-id="3229d-127">However, even though you can find architectures that hold multiple processes per container, that approach it is not very common.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3229d-128">[上一個] (../net-core-net-framework-containers/official-net-docker-images.md) [下一個] (containerize-monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="3229d-128">[Previous] (../net-core-net-framework-containers/official-net-docker-images.md) [Next] (containerize-monolithic-applications.md)</span></span>
