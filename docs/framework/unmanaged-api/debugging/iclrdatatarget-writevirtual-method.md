---
title: "ICLRDataTarget::WriteVirtual 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.WriteVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ffce593824599e9f8f41c38966b69a9076924608
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="f68b1-102">ICLRDataTarget::WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="f68b1-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="f68b1-103">將資料從指定的緩衝區寫入指定的虛擬記憶體位址。</span><span class="sxs-lookup"><span data-stu-id="f68b1-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f68b1-104">語法</span><span class="sxs-lookup"><span data-stu-id="f68b1-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f68b1-105">參數</span><span class="sxs-lookup"><span data-stu-id="f68b1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f68b1-106">[in]CLRDATA_ADDRESS 儲存的虛擬記憶體位址。</span><span class="sxs-lookup"><span data-stu-id="f68b1-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="f68b1-107">[in]將資料寫入緩衝區的指標。</span><span class="sxs-lookup"><span data-stu-id="f68b1-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="f68b1-108">[in]要寫入的位元組數目。</span><span class="sxs-lookup"><span data-stu-id="f68b1-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="f68b1-109">[out]實際寫入的位元組數目指標。</span><span class="sxs-lookup"><span data-stu-id="f68b1-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f68b1-110">需求</span><span class="sxs-lookup"><span data-stu-id="f68b1-110">Requirements</span></span>  
 <span data-ttu-id="f68b1-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f68b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f68b1-112">**標頭：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f68b1-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f68b1-113">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f68b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f68b1-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f68b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68b1-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f68b1-115">See Also</span></span>  
 [<span data-ttu-id="f68b1-116">ICLRDataTarget 介面</span><span class="sxs-lookup"><span data-stu-id="f68b1-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)