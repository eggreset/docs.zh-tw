---
title: "GetQualifierSet 函式 （Unmanaged API 參考）"
description: "GetQualifierSet 函式會擷取針對類別或執行個體設定的限定詞。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetQualifierSet
helpviewer_keywords: GetQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15d384003f3a18124a07d83a8308f4b8a5c6a31b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="getqualifierset-function"></a><span data-ttu-id="45bb9-103">GetQualifierSet 函式</span><span class="sxs-lookup"><span data-stu-id="45bb9-103">GetQualifierSet function</span></span>
<span data-ttu-id="45bb9-104">擷取設定的類別執行個體或類別定義的限定詞。</span><span class="sxs-lookup"><span data-stu-id="45bb9-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="45bb9-105">語法</span><span class="sxs-lookup"><span data-stu-id="45bb9-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="45bb9-106">參數</span><span class="sxs-lookup"><span data-stu-id="45bb9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="45bb9-107">[in]未使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="45bb9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="45bb9-108">[in]指標[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)執行個體。</span><span class="sxs-lookup"><span data-stu-id="45bb9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="45bb9-109">[out]收到允許存取的類別物件限定詞的介面指標。</span><span class="sxs-lookup"><span data-stu-id="45bb9-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="45bb9-110">`ppQualSet` 不可以是 `null`。</span><span class="sxs-lookup"><span data-stu-id="45bb9-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="45bb9-111">如果發生錯誤，不會傳回新的物件，而且指標會保留不變。</span><span class="sxs-lookup"><span data-stu-id="45bb9-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="45bb9-112">傳回值</span><span class="sxs-lookup"><span data-stu-id="45bb9-112">Return value</span></span>

<span data-ttu-id="45bb9-113">這個函式傳回下列值會定義在*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中：</span><span class="sxs-lookup"><span data-stu-id="45bb9-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="45bb9-114">常數</span><span class="sxs-lookup"><span data-stu-id="45bb9-114">Constant</span></span>  |<span data-ttu-id="45bb9-115">值</span><span class="sxs-lookup"><span data-stu-id="45bb9-115">Value</span></span>  |<span data-ttu-id="45bb9-116">說明</span><span class="sxs-lookup"><span data-stu-id="45bb9-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="45bb9-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="45bb9-117">0x80041001</span></span> | <span data-ttu-id="45bb9-118">發生一般失敗。</span><span class="sxs-lookup"><span data-stu-id="45bb9-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="45bb9-119">而會收到 0x80041002</span><span class="sxs-lookup"><span data-stu-id="45bb9-119">0x80041002</span></span> | <span data-ttu-id="45bb9-120">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="45bb9-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="45bb9-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="45bb9-121">0x80041006</span></span> | <span data-ttu-id="45bb9-122">沒有足夠的記憶體可完成作業。</span><span class="sxs-lookup"><span data-stu-id="45bb9-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="45bb9-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="45bb9-123">0x80041008</span></span> | <span data-ttu-id="45bb9-124">參數是`null`。</span><span class="sxs-lookup"><span data-stu-id="45bb9-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="45bb9-125">0</span><span class="sxs-lookup"><span data-stu-id="45bb9-125">0</span></span> | <span data-ttu-id="45bb9-126">函式呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="45bb9-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="45bb9-127">備註</span><span class="sxs-lookup"><span data-stu-id="45bb9-127">Remarks</span></span>

<span data-ttu-id="45bb9-128">此函式會包裝呼叫[IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="45bb9-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="45bb9-129">[IWbemQualifierSet 指標](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)可讓呼叫者新增、 編輯或刪除這些限定詞。</span><span class="sxs-lookup"><span data-stu-id="45bb9-129">The [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="45bb9-130">這類新增、 編輯或刪除限定詞會套用至整個執行個體或類別定義。</span><span class="sxs-lookup"><span data-stu-id="45bb9-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="45bb9-131">需求</span><span class="sxs-lookup"><span data-stu-id="45bb9-131">Requirements</span></span>  
<span data-ttu-id="45bb9-132">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45bb9-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45bb9-133">**標頭：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="45bb9-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="45bb9-134">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45bb9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45bb9-135">請參閱</span><span class="sxs-lookup"><span data-stu-id="45bb9-135">See also</span></span>  
[<span data-ttu-id="45bb9-136">WMI 和效能計數器 （Unmanaged API 參考）</span><span class="sxs-lookup"><span data-stu-id="45bb9-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)