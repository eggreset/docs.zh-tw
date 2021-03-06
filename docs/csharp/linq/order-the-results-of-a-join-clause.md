---
title: 排序 join 子句的結果 (C# 中的 LINQ)
description: 了解如何在 C# 中排序 LINQ join 子句的結果。
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: e4a12b6f9b4a99decb1f64524ebe67a196084a04
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404732"
---
# <a name="order-the-results-of-a-join-clause"></a>排序 join 子句的結果

本例示範如何排序聯結作業的結果。 請注意，排序是在聯結後執行。 雖然您可以在聯結之前使用 `orderby` 子句搭配一或多個來源序列，但通常不建議這麼做。 某些 LINQ 提供者在聯結後可能不會保留排序。

## <a name="example"></a>範例

此查詢會建立群組聯結，然後根據類別項目排序仍在範圍內的群組。 在匿名型別初始設定式內，子查詢會排序產品序列中的所有相符項目。

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>另請參閱

[Language-Integrated Query (LINQ)](index.md)  
[orderby 子句](../language-reference/keywords/orderby-clause.md)  
[join 子句](../language-reference/keywords/join-clause.md)  