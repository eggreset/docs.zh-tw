---
title: "IMetaDataDispenserEx::GetOption 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa9db222c81c2d6536b782c3e047e24c773bd018
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="e9af8-102">IMetaDataDispenserEx::GetOption 方法</span><span class="sxs-lookup"><span data-stu-id="e9af8-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="e9af8-103">取得目前中繼資料範圍的指定選項的值。</span><span class="sxs-lookup"><span data-stu-id="e9af8-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="e9af8-104">此選項會控制如何處理目前的中繼資料範圍的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e9af8-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9af8-105">語法</span><span class="sxs-lookup"><span data-stu-id="e9af8-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9af8-106">參數</span><span class="sxs-lookup"><span data-stu-id="e9af8-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="e9af8-107">[in]指定要擷取的選項為 guid 的指標。</span><span class="sxs-lookup"><span data-stu-id="e9af8-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="e9af8-108">請參閱 < 備註 > 一節清單的支援的 Guid。</span><span class="sxs-lookup"><span data-stu-id="e9af8-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e9af8-109">[out]傳回選項的值。</span><span class="sxs-lookup"><span data-stu-id="e9af8-109">[out] The value of the returned option.</span></span> <span data-ttu-id="e9af8-110">此值的型別會指定的選項類型的 variant。</span><span class="sxs-lookup"><span data-stu-id="e9af8-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9af8-111">備註</span><span class="sxs-lookup"><span data-stu-id="e9af8-111">Remarks</span></span>  
 <span data-ttu-id="e9af8-112">下列清單顯示支援這個方法的 Guid。</span><span class="sxs-lookup"><span data-stu-id="e9af8-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="e9af8-113">如需說明，請參閱[imetadatadispenserex:: Setoption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e9af8-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="e9af8-114">如果`optionId`是不在此清單中，這個方法會傳回 HRESULT `E_INVALIDARG`，指出不正確的參數。</span><span class="sxs-lookup"><span data-stu-id="e9af8-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="e9af8-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="e9af8-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="e9af8-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="e9af8-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="e9af8-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="e9af8-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="e9af8-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="e9af8-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="e9af8-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="e9af8-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="e9af8-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="e9af8-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="e9af8-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="e9af8-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9af8-122">需求</span><span class="sxs-lookup"><span data-stu-id="e9af8-122">Requirements</span></span>  
 <span data-ttu-id="e9af8-123">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9af8-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9af8-124">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9af8-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9af8-125">**程式庫：**做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="e9af8-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9af8-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9af8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9af8-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e9af8-127">See Also</span></span>  
 [<span data-ttu-id="e9af8-128">IMetaDataDispenserEx 介面</span><span class="sxs-lookup"><span data-stu-id="e9af8-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="e9af8-129">IMetaDataDispenser 介面</span><span class="sxs-lookup"><span data-stu-id="e9af8-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)