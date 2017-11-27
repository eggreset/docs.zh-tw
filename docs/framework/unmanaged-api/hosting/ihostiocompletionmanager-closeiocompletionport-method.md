---
title: "IHostIoCompletionManager::CloseIoCompletionPort 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 066d51c821cf86522ffaca4c15db360ce96ed773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="f84c6-102">IHostIoCompletionManager::CloseIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="f84c6-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="f84c6-103">要求主機關閉的連接埠已開啟的檔案之前呼叫， [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f84c6-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f84c6-104">語法</span><span class="sxs-lookup"><span data-stu-id="f84c6-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f84c6-105">參數</span><span class="sxs-lookup"><span data-stu-id="f84c6-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="f84c6-106">[in]若要關閉的連接埠控制代碼。</span><span class="sxs-lookup"><span data-stu-id="f84c6-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f84c6-107">傳回值</span><span class="sxs-lookup"><span data-stu-id="f84c6-107">Return Value</span></span>  
  
|<span data-ttu-id="f84c6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f84c6-108">HRESULT</span></span>|<span data-ttu-id="f84c6-109">描述</span><span class="sxs-lookup"><span data-stu-id="f84c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f84c6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f84c6-110">S_OK</span></span>|<span data-ttu-id="f84c6-111">`CloseIoCompletionPort`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="f84c6-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="f84c6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f84c6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f84c6-113">Common language runtime (CLR) 尚未載入到處理程序，或 CLR 正在中它無法執行 managed 程式碼，或成功地處理呼叫的狀態。</span><span class="sxs-lookup"><span data-stu-id="f84c6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f84c6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f84c6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f84c6-115">呼叫已逾時。</span><span class="sxs-lookup"><span data-stu-id="f84c6-115">The call timed out.</span></span>|  
|<span data-ttu-id="f84c6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f84c6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f84c6-117">呼叫端未擁有鎖定。</span><span class="sxs-lookup"><span data-stu-id="f84c6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f84c6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f84c6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f84c6-119">事件已取消時封鎖的執行緒或 fiber 等候它。</span><span class="sxs-lookup"><span data-stu-id="f84c6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f84c6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f84c6-120">E_FAIL</span></span>|<span data-ttu-id="f84c6-121">發生未知的嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="f84c6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f84c6-122">方法會傳回 E_FAIL CLR 已不再可用的處理序內。</span><span class="sxs-lookup"><span data-stu-id="f84c6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f84c6-123">裝載方法的後續呼叫會傳回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f84c6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f84c6-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f84c6-124">E_INVALIDARG</span></span>|<span data-ttu-id="f84c6-125">傳遞了無效的連接埠控制代碼。</span><span class="sxs-lookup"><span data-stu-id="f84c6-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f84c6-126">備註</span><span class="sxs-lookup"><span data-stu-id="f84c6-126">Remarks</span></span>  
 <span data-ttu-id="f84c6-127">`hPort`必須是已由先前呼叫所建立的連接埠的控制代碼`CreateIoCompletionPort`。</span><span class="sxs-lookup"><span data-stu-id="f84c6-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f84c6-128">需求</span><span class="sxs-lookup"><span data-stu-id="f84c6-128">Requirements</span></span>  
 <span data-ttu-id="f84c6-129">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f84c6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f84c6-130">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f84c6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f84c6-131">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="f84c6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f84c6-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f84c6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84c6-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f84c6-133">See Also</span></span>  
 [<span data-ttu-id="f84c6-134">ICLRIoCompletionManager 介面</span><span class="sxs-lookup"><span data-stu-id="f84c6-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="f84c6-135">IHostIoCompletionManager 介面</span><span class="sxs-lookup"><span data-stu-id="f84c6-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)