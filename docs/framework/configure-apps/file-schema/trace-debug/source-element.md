---
title: '&lt;來源&gt;項目'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b7c2a71b129a0ad7d1c2a72b18b8a69a111f9495
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752568"
---
# <a name="ltsourcegt-element"></a>&lt;來源&gt;項目
指定起始追蹤訊息的追蹤來源。  
  
 \<configuration>  
\<system.diagnostics >  
\<來源 >  
\<來源 >  
  
## <a name="syntax"></a>語法  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|`name`|選擇性屬性。<br /><br /> 指定追蹤來源的名稱。|  
|`switchName`|選擇性屬性。<br /><br /> 應用程式中，指定追蹤交換器執行個體的名稱。 如果參數不會識別在`<switches>`項目，此值會指定交換器層級。|  
|`switchType`|選擇性屬性。<br /><br /> 指定追蹤參數的類型。 如果有的話，類型必須是有效的類別名稱，並不能是空的字串。|  
|`extraAttribute`|選擇性屬性。<br /><br /> 指定的值所識別的追蹤來源特定屬性<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>該追蹤來源的方法。|  
  
### <a name="child-elements"></a>子項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|包含收集、 儲存和路由傳送訊息的接聽程式。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|`configuration`|通用語言執行平台和 .NET Framework 應用程式所使用之每個組態檔中的根項目。|  
|`system.diagnostics`|指定用於收集、儲存及路由傳送訊息的追蹤接聽項，以及設定追蹤參數的層級。|  
|`sources`|包含起始追蹤訊息的追蹤來源。|  
  
## <a name="remarks"></a>備註  
 此項目可以用於電腦組態檔 (Machine.config) 和應用程式組態檔。  
  
## <a name="example"></a>範例  
 下列範例示範如何使用`<source>`要加入追蹤來源項目的`mySource`和設定來源交換器層級具名`sourceSwitch`。 主控台追蹤接聽程式會加入，將追蹤資訊寫入主控台。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 [追蹤和偵錯設定結構描述](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [追蹤參數](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
