---
title: 如何：裁剪影像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 46c559356447688e52508b823cc260c13128208f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553802"
---
# <a name="how-to-crop-an-image"></a>如何：裁剪影像
這個範例示範如何裁剪影像使用<xref:System.Windows.Media.Imaging.CroppedBitmap>。  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> 主要用於編碼影像的裁剪的版本時儲存的檔案。 若要裁剪的影像顯示用途，請參閱[建立裁剪區域](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)主題。  
  
## <a name="example"></a>範例  
 下列[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定義在下面的範例中使用的資源。  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 下列範例會建立映像使用<xref:System.Windows.Media.Imaging.CroppedBitmap>作為其來源。  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>也可用做為另一個來源<xref:System.Windows.Media.Imaging.CroppedBitmap>，鏈結裁剪。 請注意，<xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A>使用相對於來源點陣圖和不初始映像將裁剪的值。  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>另請參閱  
 [建立裁剪區域](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
