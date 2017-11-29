---
title: "ICorDebugEval::NewObject 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e478f057b3c319d099b0156188f3d1e23bb82e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="7a0ef-102">ICorDebugEval::NewObject 方法</span><span class="sxs-lookup"><span data-stu-id="7a0ef-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="7a0ef-103">配置新的物件執行個體並呼叫指定的建構函式方法。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="7a0ef-104">這個方法是.NET Framework 2.0 版中已過時。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7a0ef-105">使用[icordebugeval2:: Newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)改為。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a0ef-106">語法</span><span class="sxs-lookup"><span data-stu-id="7a0ef-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a0ef-107">參數</span><span class="sxs-lookup"><span data-stu-id="7a0ef-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="7a0ef-108">[in]呼叫建構函式。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="7a0ef-109">[in] `ppArgs` 陣列的大小。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="7a0ef-110">[in]ICorDebugValue 物件陣列，其中每一個都代表要傳遞給建構函式的引數。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a0ef-111">需求</span><span class="sxs-lookup"><span data-stu-id="7a0ef-111">Requirements</span></span>  
 <span data-ttu-id="7a0ef-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a0ef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a0ef-113">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a0ef-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a0ef-114">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a0ef-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a0ef-115">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="7a0ef-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0ef-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7a0ef-116">See Also</span></span>  
 [<span data-ttu-id="7a0ef-117">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="7a0ef-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)