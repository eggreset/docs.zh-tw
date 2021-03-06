---
title: 如何：驗證代表日期或時間的字串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647858"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>如何：驗證代表日期或時間的字串 (Visual Basic)
下列程式碼範例會設定`Boolean`值，指出字串是否表示有效的日期或時間。  
  
## <a name="example"></a>範例  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 取代`("01/01/03")`和`"9:30 PM"`與您想要驗證的時間與日期。 您可以取代其他硬式編碼字串的字串`String`變數，或使用的方法，傳回字串，例如`InputBox`。  
  
## <a name="robust-programming"></a>穩固程式設計  
 使用這個方法來驗證該字串，然後再嘗試轉換`String`至`DateTime`變數。 您可以藉由先檢查日期或時間，避免產生在執行階段例外狀況。  
  
## <a name="see-also"></a>另請參閱  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [在 Visual Basic 中驗證字串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
