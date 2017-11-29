---
title: "ICorDebugILCode2 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILCode2
api_location: mscordbi.dll
api_type: COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fd6b7b6b097010a307abbc260cda7c4b73e0f00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="eb88a-102">ICorDebugILCode2 介面</span><span class="sxs-lookup"><span data-stu-id="eb88a-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="eb88a-103">[在 .NET Framework 4.5.2 及更新版本中支援]</span><span class="sxs-lookup"><span data-stu-id="eb88a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="eb88a-104">以邏輯方式擴充[ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)介面，提供方法，傳回的語彙基元函式的區域變數簽章，而且，它將對應剖析工具檢測中繼語言 (IL) 位移至原始方法 IL位移。</span><span class="sxs-lookup"><span data-stu-id="eb88a-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb88a-105">方法</span><span class="sxs-lookup"><span data-stu-id="eb88a-105">Methods</span></span>  
  
|<span data-ttu-id="eb88a-106">方法</span><span class="sxs-lookup"><span data-stu-id="eb88a-106">Method</span></span>|<span data-ttu-id="eb88a-107">說明</span><span class="sxs-lookup"><span data-stu-id="eb88a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb88a-108">GetInstrumentedILMap 方法</span><span class="sxs-lookup"><span data-stu-id="eb88a-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="eb88a-109">將分析工具中的已檢測 IL 位移對應傳回至此執行個體的原始方法 IL 位移。</span><span class="sxs-lookup"><span data-stu-id="eb88a-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="eb88a-110">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="eb88a-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="eb88a-111">針對此執行個體表示的函式，取得區域變數簽章的中繼資料語彙基元。</span><span class="sxs-lookup"><span data-stu-id="eb88a-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb88a-112">需求</span><span class="sxs-lookup"><span data-stu-id="eb88a-112">Requirements</span></span>  
 <span data-ttu-id="eb88a-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb88a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb88a-114">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb88a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb88a-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb88a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb88a-116">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb88a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb88a-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eb88a-117">See Also</span></span>  
 [<span data-ttu-id="eb88a-118">ICorDebugILCode 介面</span><span class="sxs-lookup"><span data-stu-id="eb88a-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [<span data-ttu-id="eb88a-119">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="eb88a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="eb88a-120">偵錯</span><span class="sxs-lookup"><span data-stu-id="eb88a-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)