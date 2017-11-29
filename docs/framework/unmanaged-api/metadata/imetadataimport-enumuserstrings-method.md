---
title: "IMetaDataImport::EnumUserStrings 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUserStrings
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 48ec44d993c5cdc2c545125bf8b4bcb80e413f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="db1cb-102">IMetaDataImport::EnumUserStrings 方法</span><span class="sxs-lookup"><span data-stu-id="db1cb-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="db1cb-103">列舉字串語彙基元，其代表目前中繼資料範圍內的硬式編碼字串。</span><span class="sxs-lookup"><span data-stu-id="db1cb-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1cb-104">語法</span><span class="sxs-lookup"><span data-stu-id="db1cb-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db1cb-105">參數</span><span class="sxs-lookup"><span data-stu-id="db1cb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="db1cb-106">[in、 out]列舉值的指標。</span><span class="sxs-lookup"><span data-stu-id="db1cb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="db1cb-107">這必須是 NULL 的第一個呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="db1cb-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="db1cb-108">[out]陣列，用來儲存的字串語彙基元。</span><span class="sxs-lookup"><span data-stu-id="db1cb-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="db1cb-109">[in] `rStrings` 陣列的大小上限。</span><span class="sxs-lookup"><span data-stu-id="db1cb-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="db1cb-110">[out]傳回的字串語彙基元數目`rStrings`。</span><span class="sxs-lookup"><span data-stu-id="db1cb-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db1cb-111">傳回值</span><span class="sxs-lookup"><span data-stu-id="db1cb-111">Return Value</span></span>  
  
|<span data-ttu-id="db1cb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db1cb-112">HRESULT</span></span>|<span data-ttu-id="db1cb-113">說明</span><span class="sxs-lookup"><span data-stu-id="db1cb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="db1cb-114">`EnumUserStrings`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="db1cb-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="db1cb-115">沒有列舉語彙基元。</span><span class="sxs-lookup"><span data-stu-id="db1cb-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="db1cb-116">在此情況下，`pcStrings`為零。</span><span class="sxs-lookup"><span data-stu-id="db1cb-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db1cb-117">備註</span><span class="sxs-lookup"><span data-stu-id="db1cb-117">Remarks</span></span>  
 <span data-ttu-id="db1cb-118">所建立的字串語彙基元[imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="db1cb-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="db1cb-119">這個方法被為了由中繼資料瀏覽器，而不是由編譯器使用。</span><span class="sxs-lookup"><span data-stu-id="db1cb-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1cb-120">需求</span><span class="sxs-lookup"><span data-stu-id="db1cb-120">Requirements</span></span>  
 <span data-ttu-id="db1cb-121">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db1cb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1cb-122">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="db1cb-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db1cb-123">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="db1cb-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db1cb-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1cb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1cb-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="db1cb-125">See Also</span></span>  
 [<span data-ttu-id="db1cb-126">IMetaDataImport 介面</span><span class="sxs-lookup"><span data-stu-id="db1cb-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="db1cb-127">IMetaDataImport2 介面</span><span class="sxs-lookup"><span data-stu-id="db1cb-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)