---
title: ManualResetEvent 和 ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d69336bd9e4f4ec06e8319d19c1cdab5cf6e1c89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583314"
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent 和 ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 類別代表必須在收到訊號之後手動重設的本機等候控制代碼事件。 此類別代表其基底類別 <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> 的特殊案例。 如需手動重設事件的用法和功能，請參閱 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 概念文件。  
  
 <xref:System.Threading.ManualResetEvent> 物件會維持收到訊號的狀態，直到其 <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> 方法被呼叫為止。 任何數目的等候執行緒或在收到訊號之後等候事件的執行緒，皆可在物件的狀態為收到訊號時加以釋放。 <xref:System.Threading.ManualResetEvent> 對應至 Win32 `CreateEvent` 呼叫，針對 `bManualReset` 引數指定 `true`。  
  
 在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中，您可以在預期等候時間非常短暫時，以及事件不會跨越處理序界限時，使用 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> 類別來提升效能。 <xref:System.Threading.ManualResetEventSlim> 在等候事件變成收到訊號時會短暫使用忙碌微調。 若等候時間很短，旋轉功能的成本會遠低於使用等候控制代碼來等候。 不過，如果事件未在一定時間內變成收到訊號，<xref:System.Threading.ManualResetEventSlim> 就會訴諸於一般的事件控制代碼等候。  
  
## <a name="see-also"></a>請參閱  
 [執行緒處理](../../../docs/standard/threading/index.md)  
 [執行緒物件和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [等候控制代碼](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore 和 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
