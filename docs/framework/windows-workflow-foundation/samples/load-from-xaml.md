---
title: 從 XAML 載入
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: f17bbf19e4ae97dfb7a281f3f5504618611ace7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514803"
---
# <a name="load-from-xaml"></a>從 XAML 載入
這個範例示範如何動態載入 XAML 工作流程，而不必執行 XamlBuildTask 工具。 這個範例會改為呼叫 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 方法。 此範例是載入 XAML 工作流程使用的 Windows Presentation Foundation (WPF) 用戶端應用程式<xref:System.Activities.XamlIntegration.ActivityXamlServices>類別，並執行。 使用 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 類別載入工作流程之後，就會傳回可以執行的 <xref:System.Activities.DynamicActivity%601>。  
  
#### <a name="to-use-this-sample"></a>若要使用這個範例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 開啟 [LoadFromXAML.sln] 方案檔案。  
  
2.  若要建置此方案，請按 CTRL+SHIFT+B。  
  
3.  若要執行此方案，請按下 CTRL+F5。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至[Windows Communication Foundation (WCF) 和適用於.NET Framework 4 的 Windows Workflow Foundation (WF) 範例](http://go.microsoft.com/fwlink/?LinkId=150780)下載所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`