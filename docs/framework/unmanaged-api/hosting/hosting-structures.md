---
title: "裝載結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 24f6d667399d788d12d368832ed4d8638d29a0f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-structures"></a><span data-ttu-id="e416d-102">裝載結構</span><span class="sxs-lookup"><span data-stu-id="e416d-102">Hosting Structures</span></span>
<span data-ttu-id="e416d-103">本章節描述裝載 API 所使用的 unmanaged 的結構。</span><span class="sxs-lookup"><span data-stu-id="e416d-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e416d-104">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e416d-104">In This Section</span></span>  
 [<span data-ttu-id="e416d-105">AssemblyBindInfo 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="e416d-106">提供參考組件的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="e416d-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="e416d-107">BucketParameters 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="e416d-108">儲存目前與事件相關聯的例外狀況事件和參數的型別名稱。</span><span class="sxs-lookup"><span data-stu-id="e416d-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="e416d-109">COR_GC_STATS 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="e416d-110">提供有關 common language runtime (CLR) 記憶體回收機制統計資料。</span><span class="sxs-lookup"><span data-stu-id="e416d-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="e416d-111">COR_GC_THREAD_STATS 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="e416d-112">包含記憶體回收相關的每個執行緒統計資料。</span><span class="sxs-lookup"><span data-stu-id="e416d-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="e416d-113">CustomDumpItem 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="e416d-114">描述要加入至自訂的傾印在錯誤報告中的項目。</span><span class="sxs-lookup"><span data-stu-id="e416d-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="e416d-115">MDAInfo 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="e416d-116">提供有關的詳細資料`Event_MDAFired`事件，以觸發建立的 managed 偵錯助理 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="e416d-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="e416d-117">ModuleBindInfo 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="e416d-118">提供參考的模組和包含它的組件的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="e416d-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="e416d-119">StackOverflowInfo 結構</span><span class="sxs-lookup"><span data-stu-id="e416d-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="e416d-120">因為溢位而擲回的例外狀況會儲存發生溢位和資訊的類型。</span><span class="sxs-lookup"><span data-stu-id="e416d-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e416d-121">相關章節</span><span class="sxs-lookup"><span data-stu-id="e416d-121">Related Sections</span></span>  
 [<span data-ttu-id="e416d-122">裝載 Coclass</span><span class="sxs-lookup"><span data-stu-id="e416d-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="e416d-123">裝載介面</span><span class="sxs-lookup"><span data-stu-id="e416d-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="e416d-124">已被取代的 CLR 裝載函式</span><span class="sxs-lookup"><span data-stu-id="e416d-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="e416d-125">裝載列舉</span><span class="sxs-lookup"><span data-stu-id="e416d-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)