---
title: WCF 組態結構描述
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: bcbc12d35dae59fcd43d5fbf2d4c936c8e4a4423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357024"
---
# <a name="wcf-configuration-schema"></a>WCF 組態結構描述
Windows Communication Foundation (WCF) 組態項目可讓您設定 WCF 服務和用戶端應用程式。 您可使用[組態編輯器工具 (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 來建立並修改用戶端與服務的組態檔。 由於組態檔採用 XML 格式，因此，如果要使用文字編輯器手動編輯這些檔案，則必須熟悉 XML。 否則，您可能會碰到 XML 項目標記或屬性找不到等問題， 因為 XML 項目標記與屬性有區分大小寫。  
  
 WCF 組態系統根據<xref:System.Configuration>命名空間。 因此，您可以使用 <xref:System.Configuration> 命名空間提供的所有標準功能，例如組態鎖定、加密與合併，以提升應用程式及其組態的安全性。 如需這些概念的詳細資訊，請參閱下列主題。  
  
 [加密組態資訊](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [鎖定組態設定](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 本節說明每個組態項目的所有可能值，以及項目如何與其他 WCF 組態項目互動。 下圖說明 WCF 組態結構描述。  
  
 ![WCF 組態結構描述](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  您應該保護在應用程式組態檔 (app.config) 具有適當存取控制清單 (ACL) 以避免任何潛在的安全性威脅的 WCF 組態區段。  例如，您要確定只有適當人員才能存取或修改應用程式繫結上的安全性設定，或是服務組態檔的服務模型區段。  
  
## <a name="in-this-section"></a>本節內容  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 說明 `ServiceModel` 項目。  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 設定 SMSvcHost.exe 工具。  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 使用 <xref:System.Runtime.Serialization.DataContractSerializer> 等序列化程式時，設定選項的最上層項目。  
  
## <a name="related-sections"></a>相關章節  
 [設定 Windows Communication Foundation 應用程式](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 描述如何設定 WCF 服務和用戶端。
