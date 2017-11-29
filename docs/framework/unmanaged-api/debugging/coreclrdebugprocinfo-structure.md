---
title: "CoreClrDebugProcInfo 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53616fb8e947d2a301dcfcb4e3870a9a9dc36ec1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="d41b1-102">CoreClrDebugProcInfo 結構</span><span class="sxs-lookup"><span data-stu-id="d41b1-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="d41b1-103">代表正在遠端電腦上執行的處理序。</span><span class="sxs-lookup"><span data-stu-id="d41b1-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d41b1-104">語法</span><span class="sxs-lookup"><span data-stu-id="d41b1-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d41b1-105">成員</span><span class="sxs-lookup"><span data-stu-id="d41b1-105">Members</span></span>  
  
|<span data-ttu-id="d41b1-106">成員</span><span class="sxs-lookup"><span data-stu-id="d41b1-106">Member</span></span>|<span data-ttu-id="d41b1-107">說明</span><span class="sxs-lookup"><span data-stu-id="d41b1-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="d41b1-108">作業系統指派的處理序識別碼。</span><span class="sxs-lookup"><span data-stu-id="d41b1-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="d41b1-109">在目標電腦上執行之遠端偵錯 Proxy 所指派的處理序識別碼。</span><span class="sxs-lookup"><span data-stu-id="d41b1-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="d41b1-110">這個識別碼回收的頻率比作業系統識別碼少。</span><span class="sxs-lookup"><span data-stu-id="d41b1-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="d41b1-111">處理序的命令列。</span><span class="sxs-lookup"><span data-stu-id="d41b1-111">Command-line of the process.</span></span> <span data-ttu-id="d41b1-112">這個成員可能會被截斷。</span><span class="sxs-lookup"><span data-stu-id="d41b1-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d41b1-113">需求</span><span class="sxs-lookup"><span data-stu-id="d41b1-113">Requirements</span></span>  
 <span data-ttu-id="d41b1-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d41b1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d41b1-115">**標頭：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d41b1-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d41b1-116">**程式庫：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d41b1-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d41b1-117">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d41b1-117">**.NET Framework Versions:** 3.5 SP1</span></span>