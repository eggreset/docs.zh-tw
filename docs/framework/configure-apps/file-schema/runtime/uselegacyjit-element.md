---
title: '&lt;useLegacyJit&gt;項目'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd0ae1a44b41ddcae2149bcf685871a37dd01b06
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="ltuselegacyjitgt-element"></a>&lt;useLegacyJit&gt;項目

決定通用語言執行平台是否針對 Just-In-Time 編譯使用舊版 64 位元 JIT 編譯器。  
  
\<configuration>  
\<執行階段 >  
\<useLegacyJit >
  
## <a name="syntax"></a>語法  
  
```xml
<useLegacyJit enabled=0|1 />
```

項目名稱`useLegacyJit`會區分大小寫。
  
## <a name="attributes-and-elements"></a>屬性和元素

下列章節說明屬性、子元素和父元素。  
  
### <a name="attributes"></a>屬性  
  
| 屬性 | 描述                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | 必要屬性。<br><br>指定執行階段是否使用傳統的 64 位元 JIT 編譯器。 |  
  
### <a name="enabled-attribute"></a>啟用的屬性  
  
| 值 | 描述                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Common language runtime 會使用新的 64 位元 JIT 編譯器包含在.NET Framework 4.6 和更新版本。 |  
| 1     | Common language runtime 會使用較舊的 64 位元 JIT 編譯器。                                                     |  
  
### <a name="child-elements"></a>子元素

無
  
### <a name="parent-elements"></a>父元素  
  
| 元素         | 描述                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | 通用語言執行平台和 .NET Framework 應用程式所使用之每個組態檔中的根項目。 |  
| `runtime`       | 包含有關執行階段初始化選項的資訊。                                                        |  
  
## <a name="remarks"></a>備註  

從.NET Framework 4.6 開始，通用語言執行平台預設會使用新的 64 位元編譯器 Just-In-Time (JIT) 編譯的。 在某些情況下，這可能會導致從已由舊版的 64 位元 JIT 編譯器的 JIT 編譯的應用程式程式碼的行為差異。 藉由設定`enabled`屬性`<useLegacyJit>`元素`1`，您可以停用新的 64 位元 JIT 編譯器，而是在編譯應用程式使用舊版的 64 位元 JIT 編譯器。  
  
> [!NOTE]
> `<useLegacyJit>`項目會影響只有 64 位元 JIT 編譯。 32 位元 JIT 編譯器的編譯不受影響。  
  
不使用組態檔設定，您可以啟用舊版的 64 位元 JIT 編譯器，另外兩種方式：  
  
- 設定環境變數

  設定`COMPLUS_useLegacyJit`環境變數設為  `0` （使用新的 64 位元 JIT 編譯器） 或`1`（使用較舊的 64 位元 JIT 編譯器）：
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  環境變數具有*全域範圍*，也就是說，它會影響的電腦上執行的所有應用程式。 如果設定，它可覆寫應用程式組態檔設定。 環境變數名稱不區分大小寫。
  
- 新增登錄機碼

  您可以藉由新增啟用舊版的 64 位元 JIT 編譯器`REG_DWORD`值設為 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`或`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`登錄中的索引鍵。 值為`useLegacyJit`。 如果值為 0，則會使用新的編譯器。 如果值為 1，會啟用舊版的 64 位元 JIT 編譯器。 登錄值名稱不區分大小寫。
  
  值來加入`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`金鑰會影響電腦上執行的所有應用程式。 值來加入`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`金鑰會影響目前使用者所執行的所有應用程式。 如果電腦透過多個使用者帳戶設定，只有目前使用者所執行的應用程式會受到影響，除非此值會加入至其他使用者的登錄機碼。 加入`<useLegacyJit>`項目至組態檔覆寫登錄設定，如果它們存在。  
  
## <a name="example"></a>範例  

下列組態檔停用與新的 64 位元 JIT 編譯器編譯，而是使用舊版的 64 位元 JIT 編譯器。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱

[\<runtime > 項目](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
[\<設定 > 項目](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
[風險降低：新的 64 位元 JIT 編譯器](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
