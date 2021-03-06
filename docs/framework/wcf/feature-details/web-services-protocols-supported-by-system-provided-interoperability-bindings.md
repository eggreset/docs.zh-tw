---
title: 系統提供的互通性繫結所支援的 Web 服務通訊協定
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: 728dba65a99d71a52551b16e5f1822104ed40ea7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508721"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>系統提供的互通性繫結所支援的 Web 服務通訊協定
Windows Communication Foundation (WCF) 是建置與支援一組稱為 Web 服務規格的規格的 Web 服務交互操作。 為了簡化服務組態以獲得互通性最佳做法，WCF 會引進三種互通系統提供繫結： <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>， <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>，和<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>。 WCF 的互通性與組織先進的結構化 Information Standards (OASIS) 標準，包含一個互通系統提供繫結： <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>。 中繼資料發行集，WCF 會包含兩個系統提供繫結： [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)和[ \<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)。 本主題列出系統提供之繫結支援的規格。  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>basicHttpBinding、wsHttpBinding、ws2007HttpBinding 和 wsDualHttpBinding 繫結支援的 Web 服務通訊協定  
  
### <a name="all-bindings"></a>所有繫結  
 [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)， [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)，和[ \<ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)繫結支援下列通訊協定。  
  
> [!NOTE]
>  如需用於發行中繼資料之繫結的詳細資訊，請參閱本主題中稍後的「系統提供之中繼資料繫結」一節。  
  
|分類|通訊協定|規格和用法|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`、`WSHttpBinding` 和 `WS2007HttpBinding` 使用 HTTP 和 HTTPS 傳輸。|  
|訊息|MTOM|[MTOM](http://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`、`wsHttpBinding` 和 `ws2007HttpBinding` 支援訊息傳輸最佳化機制 (MTOM)。 預設不使用。 若要使用 MTOM，請將 `messageEncoding` 屬性設為 `"Mtom"`。<br /><br /> 範例：<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|中繼資料|WSDL 1.1|[WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF 會使用 Web 服務描述語言 (WSDL) 來描述服務。|  
|中繼資料|WS-Policy|[WS-Policy](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> WCF 會使用 Ws-policy 規格與定義域特定的判斷提示來描述服務需求和功能。|  
|中繼資料|WS-Policy 1.5|[Ws-policy 1.5](http://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> WCF 會使用 Ws-policy 規格與定義域特定的判斷提示來描述服務需求和功能。|  
|中繼資料|WS-PolicyAttachment|[WS-PolicyAttachment](http://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> WCF 實作 Ws-policyattachment 以附加原則運算式，在各種範圍中 Web 服務描述語言 (WSDL)。|  
|中繼資料|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF 實作 Ws-metadataexchange 以擷取 XML 結構描述、 WSDL 和 Ws-policy。|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|分類|通訊協定|規格和用法|  
|--------------|--------------|-----------------------------|  
|訊息|SOAP 1.1|[SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> 為了與 Basic Profile 1.1 保持一致，`basicHttpBinding` 項目實作 SOAP 1.1 訊息通訊協定。|  
|安全性|WSS SOAP 訊息安全性 1.0|[WSS SOAP 訊息安全性 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> 為了與 Basic Security Profile 保持一致，`basicHttpBinding` 項目實作 Web 服務安全性 (WSS) SOAP 訊息安全性 1.0 規格，以用於使用者名稱/密碼和 X.509 型的安全性。<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 UsernameToken 設定檔 1.0|[WSS SOAP 訊息安全性 UsernameToken 設定檔 1.0](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 X.509 憑證權杖設定檔 1.0|[WSS SOAP 訊息安全性 X.509 憑證權杖設定檔 1.0](http://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding、ws2007HttpBinding 和 wsDualHttpBinding  
  
|分類|通訊協定|規格和用法|  
|--------------|--------------|-----------------------------|  
|訊息|SOAP 1.2|[入門](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [訊息架構](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [附加 （包括 HTTP 繫結）](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|訊息|Ws-addressing 2005/08|[Web 服務定址 1.0-核心](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web 服務定址 1.0-SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> `wsHttpBinding`、`ws2007HttpBinding` 和 `wsDualHttpBinding` 會實作全球資訊網協會 (W3C) WS-Addressing 建議，以啟用非同步訊息、訊息相互關聯和傳輸中性的定址機制。<br /><br /> 雖然 WS-* 規格允許 WS-Addressing 標頭加密，但是 WCF 並不提供這項支援。|  
|傳訊|WS-Addressing 1.0 - 中繼資料|[Ws-addressing 1.0 中繼資料](http://www.w3.org/2007/05/addressing/metadata)會啟用此通訊協定的支援設定的原則版本中 ServiceMetadata 行為-policyversion 設 1.2 （預設值），符合 Ws-addressing 的 wsdl，wsdl 描述與policyversion 設為 1.5，wsdl 描述會符合 ws 定址的中繼資料。<br /><br /> 雖然 WS-* 規格允許 WS-Addressing 標頭加密，但是 WCF 並不提供這項支援。|  
|安全性|WSS SOAP 訊息安全性 1.0|[WSS SOAP 訊息安全性 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> `securityMode` 屬性設為 "wsSecurityOverHttp" (預設值) 且使用 `wsSecurity` 子項目設定參數時使用。<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 UsernameToken 設定檔 1.1|[WSS SOAP 訊息安全性 UsernameToken 設定檔 1.0](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Username" 時使用。<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 X.509 憑證權杖設定檔 1.1|[WSS SOAP 訊息安全性 X.509 憑證權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> 用於在 `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Username"、"Certificate" 或 "None" 時保護訊息。 此外，當 `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Certificate" 時，請使用此規格進行用戶端驗證。<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 Kerberos 權杖設定檔 1.1|[WSS SOAP 訊息安全性 Kerberos 權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> 用於在 `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Windows" 時進行驗證和保護訊息。<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|安全性|WS-SecureConversation|[WS-SecureConversation](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> 用於當 `security/@mode` 屬性設為 "Message"，且 `message/@establishSecurityContext` 屬性設為 "true" (預設值) 時提供安全的工作階段。|  
|安全性|WS-Trust|[WS-Trust](http://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> WS-SecureConversation (請參閱前述) 所使用。|  
|可信賴傳訊|WS-ReliableMessaging|[WS-ReliableMessaging](http://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> 當繫結設定為使用 `reliableSession` 時使用。<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|異動|WS-AtomicTransaction|[WS-AtomicTransaction](http://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> 用於異動管理員之間的通訊。 WCF 用戶端和服務永遠使用本機交易管理員。|  
|異動|WS-Coordination|[WS-Coordination](http://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> 用於當 `flowTransactions` 屬性設為 "Allowed" 或 "Required" 時流動交易內容。<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding 和 ws2007FederationHttpBinding  
 [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)和[ \<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)引入聯合案例中，提供支援，其中第三個項目合作對象會簽發權杖，用來驗證用戶端。 除了 `wsHttpBinding` 使用的通訊協定外，`wsFederationHttpBinding` 還使用：  
  
-   `WS-Trust`，進行權杖發行。  
  
-   WSS 安全性判斷提示標記語言 (SAML) 權杖設定檔 1.0 和 1.1，適用於最常見的發行權杖格式。  
  
 範例：  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"   
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =   
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 如需詳細資訊，請參閱[同盟](../../../../docs/framework/wcf/feature-details/federation.md)。  
  
## <a name="system-provided-metadata-bindings"></a>系統提供之中繼資料繫結  
 下表說明系統提供之互通中繼資料繫結所支援的通訊協定，該繫結由 <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType> 類別公開。  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 [ \<MexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)繫結支援下列通訊協定。 如需有關如何使用這個繫結的詳細資訊，請參閱[發行中繼資料](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)。  
  
|分類|通訊協定|規格和用法|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)|  
|訊息|SOAP 1.2|[入門](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [訊息架構](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [附加 （包括 HTTP 繫結）](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|訊息|Ws-addressing 2005/08|[Web 服務定址 1.0-核心](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web 服務定址 1.0-SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|中繼資料|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF 實作 Ws-metadataexchange 以擷取 XML 結構描述、 WSDL 和 Ws-policy。|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)支援下列通訊協定。 如需有關如何使用這個繫結的詳細資訊，請參閱[發行中繼資料](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)。  
  
|分類|通訊協定|規格和用法|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> 已啟用傳輸安全性。|  
|訊息|SOAP 1.2|[入門](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [訊息架構](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [附加 （包括 HTTP 繫結）](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|訊息|Ws-addressing 2005/08|[Web 服務定址 1.0-核心](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web 服務定址 1.0-SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|中繼資料|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF 實作 Ws-metadataexchange 以擷取 XML 結構描述、 WSDL 和 Ws-policy。|  
  
## <a name="see-also"></a>另請參閱  
 [系統提供的繫結](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)  
 [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)  
 [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)  
 [\<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)  
 [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
