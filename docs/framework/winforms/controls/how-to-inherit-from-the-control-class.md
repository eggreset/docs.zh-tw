---
title: 如何：繼承自 Control 類別
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: da80d46f27d7cd721af7a9600d2b0cde84876d23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534579"
---
# <a name="how-to-inherit-from-the-control-class"></a>如何：繼承自 Control 類別
如果您想要建立使用 Windows Form 上的完全自訂控制項，您應該繼承自<xref:System.Windows.Forms.Control>類別。 同時繼承自<xref:System.Windows.Forms.Control>類別會要求您執行詳細的規劃和實作，它也提供您選項的最大範圍。 繼承自<xref:System.Windows.Forms.Control>，繼承的非常基本的功能可讓工作的控制項。 繼承的功能<xref:System.Windows.Forms.Control>類別會處理透過鍵盤和滑鼠的使用者輸入，定義範圍和控制項的大小、 提供的 windows 控制代碼，並提供訊息處理和安全性。 它不會併入任何繪製功能 (在此例中是控制項圖形化介面的實際轉譯)，也不會併入任何特定的使用者互動功能。 您必須透過自訂程式碼來提供上述一切。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
### <a name="to-create-a-custom-control"></a>建立自訂控制項  
  
1.  建立新的 [Windows 應用程式] 或 [Windows 控制項程式庫] 專案。  
  
2.  從 [專案] 功能表中，選擇 [新增類別]。  
  
3.  在 [新增項目] 對話方塊中，按一下 [自訂控制項]。  
  
     新的自訂控制項會新增至您的專案。  
  
4.  按 F7 鍵，開啟自訂控制項的 [程式碼編輯器]。  
  
5.  找出<xref:System.Windows.Forms.Control.OnPaint%2A>方法，將會是空的呼叫除了<xref:System.Windows.Forms.Control.OnPaint%2A>基底類別的方法。  
  
6.  修改程式碼，以併入您要用於控制項的任何自訂繪製功能。  
  
     如需撰寫程式碼來轉譯控制項圖形的相關資訊，請參閱[自訂控制項繪製和轉譯](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)。  
  
7.  實作您的控制項將併入的任何自訂方法、屬性或事件。  
  
8.  儲存並測試您的控制項。  
  
## <a name="see-also"></a>另請參閱  
 [各種自訂控制項](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [操作說明：繼承自 UserControl 類別](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [操作說明：繼承自現有的 Windows Forms 控制項](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [操作說明：撰寫 Windows Forms 的控制項](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Visual Basic 中的繼承事件處理常式疑難排解](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [在設計階段開發 Windows Forms 控制項](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
