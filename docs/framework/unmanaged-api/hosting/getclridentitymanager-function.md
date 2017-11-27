---
title: "GetCLRIdentityManager 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCLRIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: GetCLRIdentityManager
helpviewer_keywords: GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddc0395b6fd659ecd6a26a3132fccc65bbb961fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="bcfb9-102">GetCLRIdentityManager 函式</span><span class="sxs-lookup"><span data-stu-id="bcfb9-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="bcfb9-103">取得可讓 common language runtime (CLR) 來管理身分識別的介面指標。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="bcfb9-104">此函式中已被取代[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfb9-105">語法</span><span class="sxs-lookup"><span data-stu-id="bcfb9-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcfb9-106">參數</span><span class="sxs-lookup"><span data-stu-id="bcfb9-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="bcfb9-107">[in]A `REFIID` （介面識別項），指定要取得的介面。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="bcfb9-108">此值必須是 IID_ICLRAssemblyIdentityManager 或 IID_ICLRHostBindingPolicyManager。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="bcfb9-109">[out]中的其中一個位址的指標[ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)或[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)物件。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcfb9-110">備註</span><span class="sxs-lookup"><span data-stu-id="bcfb9-110">Remarks</span></span>  
 <span data-ttu-id="bcfb9-111">呼叫[GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)函式可取得的指標`GetCLRIdentityManager`函式。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfb9-112">需求</span><span class="sxs-lookup"><span data-stu-id="bcfb9-112">Requirements</span></span>  
 <span data-ttu-id="bcfb9-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcfb9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfb9-114">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bcfb9-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bcfb9-115">**程式庫：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="bcfb9-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="bcfb9-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfb9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfb9-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bcfb9-117">See Also</span></span>  
 [<span data-ttu-id="bcfb9-118">已被取代的 CLR 裝載函式</span><span class="sxs-lookup"><span data-stu-id="bcfb9-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)