---
title: 如何：擴展 TableLayoutPanel 控制項中的資料列和資料行
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a78286be8ef64212d945b3cb11a2963d5a1b2e79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535343"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>如何：擴展 TableLayoutPanel 控制項中的資料列和資料行
中的控制項<xref:System.Windows.Forms.TableLayoutPanel>控制項可以跨越相鄰的資料列和資料行。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
### <a name="to-span-columns-and-rows"></a>若要擴展資料行和資料列  
  
1.  拖曳<xref:System.Windows.Forms.TableLayoutPanel>控制項從**工具箱**拖曳至表單。  
  
2.  拖曳<xref:System.Windows.Forms.Button>控制項從**工具箱**左上方儲存格的<xref:System.Windows.Forms.TableLayoutPanel>控制項。  
  
3.  設定<xref:System.Windows.Forms.Button>控制項的**ColumnSpan**屬性**2**。 請注意，<xref:System.Windows.Forms.Button>控制項跨越的第一個和第二個資料行。  
  
4.  設定<xref:System.Windows.Forms.Button>控制項的**RowSpan**屬性**2**。 請注意，<xref:System.Windows.Forms.Button>控制項跨越的第一個和第二個資料列。  
  
5.  設定<xref:System.Windows.Forms.Button>控制項的**ColumnSpan**屬性**1**。 請注意，<xref:System.Windows.Forms.Button>控制項將移至第一個資料行，並跨越的第一個和第二個資料列。  
  
## <a name="see-also"></a>另請參閱  
 [TableLayoutPanel 控制項](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
