---
title: UI 自動化執行緒問題
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, threading issues
- threading issues with UI Automation
ms.assetid: 0ab8d42c-5b8b-481b-b788-2caecc2f0191
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: a9f49a99db7a4f7d118bd86bbe723a633c1b10ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409390"
---
# <a name="ui-automation-threading-issues"></a>UI 自動化執行緒問題
> [!NOTE]
>  這份文件適用於想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空間中定義之 Managed <xref:System.Windows.Automation> 類別的 .NET Framework 開發人員。 如需 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新資訊，請參閱 [Windows Automation API：使用者介面自動化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 因為 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 使用 Windows 訊息的方式，當用戶端應用程式嘗試在 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 執行緒上與其自己的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 互動時，會發生衝突。 這些衝突可能會導致效能變得非常緩慢，甚至會讓應用程式停止回應。  
  
 如果您的用戶端應用程式預定要與桌面上的所有項目互動，包括它自己的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]，您應該在不同執行緒上呼叫所有 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 。 其中包括尋找項目 (例如，藉由使用 <xref:System.Windows.Automation.TreeWalker> 或 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 方法) 和使用控制項模式。  
  
 因為一律在非 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 執行緒上呼叫事件處理常式，所以在 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 事件處理常式中，可以安全呼叫[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。 但是，在訂閱可能來自用戶端應用程式 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]的事件時，您必須在非 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>執行緒上呼叫[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 或相關方法。 在相同執行緒上移除事件處理常式。
