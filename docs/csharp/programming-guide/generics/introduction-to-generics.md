---
title: 泛型簡介 (C# 程式設計手冊)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 892b6bfe5cf18bde91221bb8b2fa7ca7a2813870
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321242"
---
# <a name="introduction-to-generics-c-programming-guide"></a>泛型簡介 (C# 程式設計手冊)
泛型類別和方法將再使用性、型別安全和效率三者結合在一起，發揮了非泛型類別和方法所無法提供的功能。 泛型最常搭配在其上操作的集合和方法使用。 .NET Framework 2.0 版類別庫提供了新的命名空間 <xref:System.Collections.Generic>，其中包含數個新的泛型集合類別。 建議以 .NET Framework 2.0 和更新版本為目標的所有應用程式都使用新的泛型集合類別，而不是舊版的非泛型集合類別，例如 <xref:System.Collections.ArrayList>。 如需詳細資訊，請參閱 [.NET 的泛型](../../../standard/generics/index.md)。  
  
 當然，您也可以建立自訂的泛型型別和方法，自行處理泛型化的問題，並設計型別安全且有效率的模式。 下列程式碼範例顯示一個簡單的泛型連結清單類別，以供示範之用 (在大部分情況下，您應該使用 .NET Framework 類別庫提供的 <xref:System.Collections.Generic.List%601> 類別，而不要自行建立類別)。在幾個位置會使用型別參數 `T`，這些位置一般會使用具象類型來表示清單中儲存的項目類型。 這個參數可以用於下列方面：  
  
-   作為 `AddHead` 方法中的方法參數類型。  
  
-   作為巢狀 `Node` 類別中 `Data` 屬性的傳回型別。  
  
-   作為巢狀類別中私用成員 `data` 的類型。  
  
 請注意，T 可用於巢狀 `Node` 類別。 當 `GenericList<T>` 以具象類型具現化時 (例如具現化為 `GenericList<int>`)，所出現的每個 `T` 都會以 `int` 取代。  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 下列程式碼範例示範用戶端程式碼如何使用泛型 `GenericList<T>` 類別建立整數清單。 您只要變更型別引數，就能輕鬆修改下列的程式碼來建立字串清單或任何其他自訂類型的清單：  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>請參閱  
 <xref:System.Collections.Generic>  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [泛型](../../../csharp/programming-guide/generics/index.md)
