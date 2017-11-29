---
title: "LogSwitchCallReason 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LogSwitchCallReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: LogSwitchCallReason
helpviewer_keywords: LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 937b26efa79605b585c420db608a938b3ee71f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="415b1-102">LogSwitchCallReason 列舉</span><span class="sxs-lookup"><span data-stu-id="415b1-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="415b1-103">指出在切換偵錯/追蹤時所執行的作業。</span><span class="sxs-lookup"><span data-stu-id="415b1-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415b1-104">語法</span><span class="sxs-lookup"><span data-stu-id="415b1-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="415b1-105">成員</span><span class="sxs-lookup"><span data-stu-id="415b1-105">Members</span></span>  
  
|<span data-ttu-id="415b1-106">成員</span><span class="sxs-lookup"><span data-stu-id="415b1-106">Member</span></span>|<span data-ttu-id="415b1-107">說明</span><span class="sxs-lookup"><span data-stu-id="415b1-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="415b1-108">建立偵錯/追蹤參數。</span><span class="sxs-lookup"><span data-stu-id="415b1-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="415b1-109">偵錯/追蹤交換器已修改。</span><span class="sxs-lookup"><span data-stu-id="415b1-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="415b1-110">切換偵錯/追蹤已刪除。</span><span class="sxs-lookup"><span data-stu-id="415b1-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="415b1-111">需求</span><span class="sxs-lookup"><span data-stu-id="415b1-111">Requirements</span></span>  
 <span data-ttu-id="415b1-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="415b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="415b1-113">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="415b1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="415b1-114">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="415b1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="415b1-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="415b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415b1-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="415b1-116">See Also</span></span>  
 [<span data-ttu-id="415b1-117">偵錯列舉</span><span class="sxs-lookup"><span data-stu-id="415b1-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)