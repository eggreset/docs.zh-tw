---
title: '符合運算式 （F #）'
description: '了解如何在 F # 比對運算式提供分支運算式的比較，以一組模式為基礎的控制項。'
ms.date: 04/19/2018
ms.openlocfilehash: 22cc4b7a87a60d8a5dcbe05ac5abec5560a37516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565174"
---
# <a name="match-expressions"></a>比對運算式

`match`運算式提供分支運算式的比較，以一組模式為基礎的控制項。

## <a name="syntax"></a>語法

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>備註

模式比對運算式允許複雜分支根據比較結果的測試運算式與一組模式。 在`match`運算式，*測試運算式*與進行比較，每個模式中開啟，並找到相符項目時，對應*結果運算式*評估及產生的值傳回做為比對運算式的值。

模式比對上一個語法中顯示的函式是在哪個模式中執行比對立即的引數的 lambda 運算式。 模式比對上一個語法中顯示的函式就相當於下列項目。

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

如需 lambda 運算式的詳細資訊，請參閱[Lambda 運算式：`fun`關鍵字](functions/lambda-expressions-the-fun-keyword.md)。

完整的模式設定應該涵蓋所有可能的相符的輸入變數。 通常，您可以使用萬用字元模式 (`_`) 來比對任何先前不相符的輸入的值與上一個模式。

下列程式碼將說明部分的方式`match`運算式使用。 參考資料和可用的所有可能模式的範例，請參閱[模式比對](pattern-matching.md)。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>模式成立條件

您可以使用`when`子句指定的變數必須符合才能符合模式的其他條件。 這類子句指*防護*。 後面的運算式`when`除非相符項目對該保護與相關聯的模式，將不評估關鍵字。

下列範例說明如何使用指定的數值範圍變數模式的成立條件。 請注意，多個條件會組合使用布林運算子。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

請注意，因為常值以外的值不能用在模式中，您必須使用`when`子句，如果您有要比較的輸入，針對某個值的某些部分。 下列程式碼所示：

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

請注意，當一個成立條件所涵蓋的等位的模式，成立條件會套用至**所有**的模式，而不只是最後一個。 例如，假設下列程式碼防護`when a > 12`同時適用於`A a`和`B a`:

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a>另請參閱

[F# 語言參考](index.md)  
[使用中模式](active-patterns.md)  
[模式比對](pattern-matching.md)  
