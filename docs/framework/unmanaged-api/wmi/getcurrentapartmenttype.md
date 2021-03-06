---
title: GetCurrentApartmentType 函式 （Unmanaged API 參考）
description: GetCurrentApartmentType 函式會擷取呼叫端執行的所在的 apartment 的型別。
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca7b5fa5bf6d845d542d3e80c0571e59f3d4c1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461720"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType 函式
擷取的 apartment 呼叫者正在執行的所在的型別。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>參數

`vFunc`  
[in]未使用這個參數。

`ptr`  
[in]指標[IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx)執行個體。

`aptType`  
[out]指標[APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx)列舉值，指出呼叫端的 apartment。

## <a name="return-value"></a>傳回值


|常數  |值  |描述  |
|---------|---------|---------|
| `S_OK` | 0 | 已順利完成函式。 |
| `E_FAIL` | 0x80000008 | 呼叫端不在 apartment 中執行。 |
  
## <a name="remarks"></a>備註

此函式會包裝呼叫[IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx)方法。

## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另請參閱  
[WMI 和效能計數器 （Unmanaged API 參考）](index.md)
