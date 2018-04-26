---
title: '%= 運算子 (C# 參考)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 864b96dcf16e4756cd0e74a6e02297660e72357e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4ee4b-102">%= 運算子 (C# 參考)</span><span class="sxs-lookup"><span data-stu-id="4ee4b-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="4ee4b-103">餘數指派運算子。</span><span class="sxs-lookup"><span data-stu-id="4ee4b-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ee4b-104">備註</span><span class="sxs-lookup"><span data-stu-id="4ee4b-104">Remarks</span></span>  
 <span data-ttu-id="4ee4b-105">使用 `%=` 指派運算子的運算式，例如</span><span class="sxs-lookup"><span data-stu-id="4ee4b-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="4ee4b-106">相當於</span><span class="sxs-lookup"><span data-stu-id="4ee4b-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="4ee4b-107">但只會評估 `x` 一次。</span><span class="sxs-lookup"><span data-stu-id="4ee4b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="4ee4b-108">對於要計算除法運算後餘數的數值類型，已預先定義 [/ 運算子](../../../csharp/language-reference/operators/remainder-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="4ee4b-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="4ee4b-109">無法直接多載 `%=` 運算子，但使用者定義型別可以多載 [% 運算子](../../../csharp/language-reference/operators/remainder-operator.md) (請參閱 [operator (C# 參考)](../../../csharp/language-reference/keywords/operator.md))。</span><span class="sxs-lookup"><span data-stu-id="4ee4b-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee4b-110">範例</span><span class="sxs-lookup"><span data-stu-id="4ee4b-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4ee4b-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="4ee4b-111">See Also</span></span>  
 [<span data-ttu-id="4ee4b-112">C# 參考</span><span class="sxs-lookup"><span data-stu-id="4ee4b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4ee4b-113">C# 程式設計指南</span><span class="sxs-lookup"><span data-stu-id="4ee4b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4ee4b-114">C# 運算子</span><span class="sxs-lookup"><span data-stu-id="4ee4b-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)