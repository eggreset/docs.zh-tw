---
title: "ICorDebugValue2::GetExactType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue2.GetExactType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e061e0cd1d467a556c7dd1bd6298784d015aa94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="18e10-102">ICorDebugValue2::GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="18e10-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="18e10-103">「 ICorDebugType 」 物件，表示要取得的介面指標<xref:System.Type>的這個值。</span><span class="sxs-lookup"><span data-stu-id="18e10-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e10-104">語法</span><span class="sxs-lookup"><span data-stu-id="18e10-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18e10-105">參數</span><span class="sxs-lookup"><span data-stu-id="18e10-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="18e10-106">[out]位址指標`ICorDebugType`物件，代表<xref:System.Type>的這個 「 ICorDebugValue2 」 物件所代表的值。</span><span class="sxs-lookup"><span data-stu-id="18e10-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18e10-107">備註</span><span class="sxs-lookup"><span data-stu-id="18e10-107">Remarks</span></span>  
 <span data-ttu-id="18e10-108">感知泛型`GetExactType`方法會取代兩者[icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)和[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法，每個傳回之類型值的相關資訊.</span><span class="sxs-lookup"><span data-stu-id="18e10-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e10-109">需求</span><span class="sxs-lookup"><span data-stu-id="18e10-109">Requirements</span></span>  
 <span data-ttu-id="18e10-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18e10-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e10-111">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18e10-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18e10-112">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18e10-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18e10-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18e10-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e10-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="18e10-114">See Also</span></span>  
 