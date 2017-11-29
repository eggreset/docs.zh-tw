---
title: "CorLinkerOptions 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLinkerOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorLinkerOptions
helpviewer_keywords: CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9d2eb081c7ef0b4feb414011d7246a1e2d6d8192
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="825a1-102">CorLinkerOptions 列舉</span><span class="sxs-lookup"><span data-stu-id="825a1-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="825a1-103">指定旗標，以選取中繼資料連結器的選項。</span><span class="sxs-lookup"><span data-stu-id="825a1-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="825a1-104">語法</span><span class="sxs-lookup"><span data-stu-id="825a1-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="825a1-105">成員</span><span class="sxs-lookup"><span data-stu-id="825a1-105">Members</span></span>  
  
|<span data-ttu-id="825a1-106">成員</span><span class="sxs-lookup"><span data-stu-id="825a1-106">Member</span></span>|<span data-ttu-id="825a1-107">說明</span><span class="sxs-lookup"><span data-stu-id="825a1-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="825a1-108">不會保留私用類型和全域函式。</span><span class="sxs-lookup"><span data-stu-id="825a1-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="825a1-109">會保留私用類型和全域函式。</span><span class="sxs-lookup"><span data-stu-id="825a1-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="825a1-110">需求</span><span class="sxs-lookup"><span data-stu-id="825a1-110">Requirements</span></span>  
 <span data-ttu-id="825a1-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="825a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="825a1-112">**標頭：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="825a1-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="825a1-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="825a1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825a1-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="825a1-114">See Also</span></span>  
 [<span data-ttu-id="825a1-115">中繼資料列舉</span><span class="sxs-lookup"><span data-stu-id="825a1-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)