---
title: 逐步解說：在 WPF 中排列 Windows Form 控制項
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: f2cf82c54724a43a60fb9077c5731d4b4ad2cfd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549655"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>逐步解說：在 WPF 中排列 Windows Form 控制項
本逐步解說會示範如何使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版面配置功能來排列[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]混合式應用程式中的控制項。  
  
 這個逐步解說中所述的工作包括：  
  
-   建立專案。  
  
-   使用預設的版面配置設定。  
  
-   依內容調整大小。  
  
-   使用絕對位置。  
  
-   明確指定大小。  
  
-   設定版面配置屬性。  
  
-   了解疊置順序的限制。  
  
-   停駐。  
  
-   設定可見度。  
  
-   裝載不會自動縮放的控制項。  
  
-   縮放。  
  
-   旋轉。  
  
-   設定邊框距離及邊界。  
  
-   使用動態版面配置容器。  
  
 在此逐步解說中所述的工作的完整程式碼清單，請參閱[排列 Windows Form 控制項中 WPF 範例](http://go.microsoft.com/fwlink/?LinkID=159971)。  
  
 當您完成時，您必須了解[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]版面配置中的功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]為基礎的應用程式。  
  
## <a name="prerequisites"></a>必要條件  
 您需要下列元件才能完成此逐步解說：  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>建立專案  
  
#### <a name="to-create-and-set-up-the-project"></a>建立並設定專案  
  
1.  建立 WPF 應用程式專案，名為`WpfLayoutHostingWf`。  
  
2.  在 [方案總管] 中，加入下列組件的參考。  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  按兩下 MainWindow.xaml，在 XAML 檢視中加以開啟。  
  
4.  在<xref:System.Windows.Window>項目，加入下列[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]命名空間對應。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  在<xref:System.Windows.Controls.Grid>項目集合<xref:System.Windows.Controls.Grid.ShowGridLines%2A>屬性`true`和定義五個資料列和三個資料行。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>使用預設的版面配置設定  
 根據預設，<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目會處理裝載的版面配置[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控制項。  
  
#### <a name="to-use-default-layout-settings"></a>使用預設的版面配置設定  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  按 F5 鍵建置並執行應用程式。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType>控制項出現在<xref:System.Windows.Controls.Canvas>。 裝載的控制項的大小調整為根據其內容，而<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目會調整成足以容納裝載的控制項。  
  
## <a name="sizing-to-content"></a>依內容調整大小  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素可確保裝載的控制項的大小來正確顯示其內容。  
  
#### <a name="to-size-to-content"></a>依內容調整大小  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  按 F5 鍵建置並執行應用程式。 兩個新的按鈕控制項的大小，以顯示較長的文字字串和大字型大小正常運作，而<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目會調整大小以容納裝載的控制項。  
  
## <a name="using-absolute-positioning"></a>使用絕對位置  
 您可以使用絕對位置放置<xref:System.Windows.Forms.Integration.WindowsFormsHost>使用者介面 (UI) 中的任何位置的項目。  
  
#### <a name="to-use-absolute-positioning"></a>使用絕對位置  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  按 F5 鍵建置並執行應用程式。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>項目會放 20 像素為單位，從方格資料格的頂端和左側 20 像素為單位。  
  
## <a name="specifying-size-explicitly"></a>明確指定大小  
 您可以指定的大小<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目使用<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>屬性。  
  
#### <a name="to-specify-size-explicitly"></a>明確指定大小  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  按 F5 鍵建置並執行應用程式。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素設定為大小為 50 像素寬 x 70 像素高，其小於預設版面配置設定。 內容[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]據以重新排列控制項。  
  
## <a name="setting-layout-properties"></a>設定版面配置屬性  
 一律與配置有關的屬性上設定裝載控制項使用之屬性的<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目。 直接在裝載的控制項上設定版面配置屬性，將產生非預期的結果。  
  
 在裝載控制項上設定與配置有關的屬性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]沒有任何作用。  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>查看在裝載控制項上設定屬性的效果  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  在 [方案總管] 中，按兩下 MainWindow.xaml. vb 或 MainWindow.xaml.cs，以便在程式碼編輯器中加以開啟。  
  
3.  下列程式碼複製到`MainWindow`類別定義。  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  按 F5 鍵建置並執行應用程式。  
  
5.  按一下**Click me**  按鈕。 `button1_Click`事件處理常式設定<xref:System.Windows.Forms.Control.Top%2A>和<xref:System.Windows.Forms.Control.Left%2A>裝載控制項上的屬性。 這會造成裝載的控制項內重新定位<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目。 主機會維持相同的螢幕區域，但會裁剪裝載的控制項。 相反地，在裝載的控制項應該永遠填滿<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目。  
  
## <a name="understanding-z-order-limitations"></a>了解疊置順序的限制  
 可見<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目會永遠繪製之上其他 WPF 項目，而且它們可依 z 軸順序不會受到影響。 若要查看此疊置順序的行為，執行下列作業：

1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  按 F5 鍵建置並執行應用程式。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素已經繪製在標籤項目上方。  


## <a name="docking"></a>停駐  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 項目支援[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]停駐。 設定<xref:System.Windows.Controls.DockPanel.Dock%2A>附加停駐在裝載的控制項的屬性<xref:System.Windows.Controls.DockPanel>項目。  
  
#### <a name="to-dock-a-hosted-control"></a>停駐裝載的控制項  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  按 F5 鍵建置並執行應用程式。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素停駐在右邊的 list<xref:System.Windows.Controls.DockPanel>項目。  
  
## <a name="setting-visibility"></a>設定可見度  
 您可以讓您[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控制隱藏或摺疊它，藉由設定<xref:System.Windows.UIElement.Visibility%2A>屬性<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目。 當控制項隱藏時，它不會顯示，但會佔據版面配置空間。 當控制項摺疊時，它不會顯示，也不會佔據配置空間。  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>設定裝載控制項的可見度  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，將下列程式碼複製到類別定義中。  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  按 F5 鍵建置並執行應用程式。  
  
4.  按一下**按一下讓看不到** 按鈕，使<xref:System.Windows.Forms.Integration.WindowsFormsHost>不可見的項目。  
  
5.  按一下**按一下以摺疊**按鈕隱藏<xref:System.Windows.Forms.Integration.WindowsFormsHost>版面配置中的項目完全。 當[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控制項摺疊、 周圍的項目就會重新排列，以佔用的空間。  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>裝載不會自動縮放的控制項  
 某些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控制項有固定的大小和執行自動縮放以填滿配置中的可用空間。 例如，<xref:System.Windows.Forms.MonthCalendar>控制項會顯示每個月固定間距。  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>裝載不會自動縮放的控制項  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  按 F5 鍵建置並執行應用程式。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>項目置於格線資料列，但它不會延伸以填滿可用空間。 如果視窗是夠大，您可能會看到兩個或多個月，顯示託管<xref:System.Windows.Forms.MonthCalendar>控制項，但這些置中對齊的資料列中。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版面配置引擎中心無法調整大小以填滿可用空間的項目。  
  
## <a name="scaling"></a>縮放  
 不同於 WPF 項目，大部分的 Windows Form 控制項不會持續擴充。 若要提供自訂縮放比例，您覆寫<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>方法。 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>使用預設行為縮放裝載的控制項  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  按 F5 鍵建置並執行應用程式。 裝載的控制項及其周圍元素會縮放 0.5 倍。 不過，裝載控制項的字型不會進行縮放。

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>旋轉  
 不同於 WPF 項目，Windows Form 控制項不支援循環。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>項目將不會與其他 WPF 項目套用旋轉轉換時才會旋轉。 任何旋轉以外值 180 度引發<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>事件。
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>查看混合式應用程式中的旋轉效果  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  按 F5 鍵建置並執行應用程式。 裝載的控制項不會旋轉，但其周圍元素會旋轉 180 度。 您可能必須調整視窗大小來查看元素。  
 

## <a name="setting-padding-and-margins"></a>設定邊框距離及邊界  
 填補和邊界[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版面配置，類似填補和邊界[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。 只要設定<xref:System.Windows.Controls.Control.Padding%2A>和<xref:System.Windows.FrameworkElement.Margin%2A>屬性<xref:System.Windows.Forms.Integration.WindowsFormsHost>項目。  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>設定裝載控制項的邊框距離及邊界  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  按 F5 鍵建置並執行應用程式。 填補和邊界設定會套用至主控[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控制項相同的方式會將它們套用在[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。  
  
## <a name="using-dynamic-layout-containers"></a>使用動態版面配置容器  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 提供兩個動態的版面配置容器，<xref:System.Windows.Forms.FlowLayoutPanel>和<xref:System.Windows.Forms.TableLayoutPanel>。 您也可以使用這些容器中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版面配置。  
  
#### <a name="to-use-a-dynamic-layout-container"></a>使用動態版面配置容器  
  
1.  複製成下列 XAML<xref:System.Windows.Controls.Grid>項目。  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，將下列程式碼複製到類別定義中。  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  將呼叫加入`InitializeFlowLayoutPanel`建構函式中的方法。  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  按 F5 鍵建置並執行應用程式。 <xref:System.Windows.Forms.Integration.WindowsFormsHost>項目都會填入<xref:System.Windows.Controls.DockPanel>，和<xref:System.Windows.Forms.FlowLayoutPanel>排列其子控制項中的預設<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 設計工具](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [WindowsFormsHost 元素的配置考量](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [排列 Windows Form 控制項中的 WPF 範例](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [逐步解說：在 WPF 中裝載 Windows Forms 複合控制項](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [逐步解說：在 Windows Forms 中裝載 WPF 複合控制項](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
