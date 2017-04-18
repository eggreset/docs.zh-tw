---
title: "HOW TO：安全中繼資料端點 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# HOW TO：安全中繼資料端點
服務的中繼資料可能包含有關應用程式而可能會遭到惡意使用者利用的敏感資訊。服務的取用者也可能會要求安全機制來取得關於服務的中繼資料。因此，有時候會需要使用安全端點來發行中繼資料。  
  
 為了保護應用程式端點，中繼資料端點安全通常會以定義於 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的標準安全性機制進行保護 \([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][安全性概觀](../../../../docs/framework/wcf/feature-details/security-overview.md).\)  
  
 本主題會逐步解說建立受 Secure Sockets Layer \(SSL\) 憑證保護之端點 \(也就是 HTTPS 端點\) 的步驟。  
  
### 在程式碼中建立安全的 HTTPS GET 中繼資料端點  
  
1.  使用適當的 X.509 憑證設定連接埠。憑證必須來自受信任的授權單位 \(CA\)，而且必須可以用於「服務授權」。您必須使用 HttpCfg.exe 工具將憑證附加到該連接埠。請參閱 [HOW TO：使用 SSL 憑證設定連接埠](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)。  
  
    > [!IMPORTANT]
    >  憑證的主體或是其網域名稱系統 \(DNS\) 必須符合電腦的名稱。這點是必要條件，因為 HTTPS 機制一開始執行的一個步驟，就是檢查該憑證是否為發行給與其被叫用位址相同的統一資源識別元 \(URI\)。  
  
2.  建立 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 類別的新執行個體。  
  
3.  將 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 類別的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 屬性設定為 `true`。  
  
4.  將 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> 屬性設定為適當的 URL。請注意，如果是指定絕對位址，URL 的開頭就必須是 "https:\/\/" 配置。如果是指定相對位址，您就必須提供服務主機的 HTTPS 起始位址。如果沒有設定這個屬性，預設的位址就會是 ""，或是直接使用服務的 HTTPS 起始位址。  
  
5.  在 <xref:System.ServiceModel.Description.ServiceDescription> 類別之 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 屬性所傳回的行為集合中新增執行個體，如下列程式碼所示。  
  
     [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
     [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]  
  
### 在組態中建立安全的 HTTPS GET 中繼資料端點  
  
1.  將 [\<行為\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 項目新增到服務之組態檔的 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 項目中。  
  
2.  將 [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 項目加入至 [\<行為\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 項目。  
  
3.  將 [\<行為\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 項目加入至 `<serviceBehaviors>` 項目。  
  
4.  將 `<behavior>` 項目的 `name` 屬性設定為適當的值。`name` 屬性 \(Attribute\) 是必要項。下面這個範例會使用值 `mySvcBehavior`。  
  
5.  將 [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)加入至 `<behavior>` 項目。  
  
6.  將 `<serviceMetadata>` 項目的 `httpsGetEnabled` 屬性設定為 `true`。  
  
7.  將 `<serviceMetadata>` 項目的 `httpsGetUrl` 屬性設定為適當的值。請注意，如果是指定絕對位址，URL 的開頭就必須是 "https:\/\/" 配置。如果是指定相對位址，您就必須提供服務主機的 HTTPS 起始位址。如果沒有設定這個屬性，預設的位址就會是 ""，或是直接使用服務的 HTTPS 起始位址。  
  
8.  若要搭配服務使用此行為，請將 [\<服務\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) 項目的 `behaviorConfiguration` 屬性設定為此行為項目之名稱屬性的值。下列組態程式碼會示範完整的範例。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="mySvcBehavior">  
         <serviceMetadata httpsGetEnabled="true"   
              httpsGetUrl="https://localhost:8036/calcMetadata" />  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
     <services>  
      <service behaviorConfiguration="mySvcBehavior"   
            name="Microsoft.Security.Samples.Calculator">  
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"  
       binding="wsHttpBinding" bindingConfiguration=""     
       contract="Microsoft.Security.Samples.ICalculator" />  
      </service>  
     </services>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
## 範例  
 下列範例會建立 <xref:System.ServiceModel.ServiceHost> 類別的執行個體，並新增端點。接下來，這段程式碼會建立 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 類別的執行個體，並設定其中屬性來建立安全的中繼資料交換點。  
  
 [!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
 [!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]  
  
## 編譯程式碼  
 此程式碼範例會使用下列命名空間 \(Namespace\)：  
  
-   <xref:System.ServiceModel?displayProperty=fullName>  
  
-   <xref:System.ServiceModel.Description?displayProperty=fullName>  
  
## 請參閱  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>   
 [HOW TO：使用 SSL 憑證設定連接埠](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [使用憑證](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [中繼資料的安全性考量](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)   
 [確保服務與用戶端的安全](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)