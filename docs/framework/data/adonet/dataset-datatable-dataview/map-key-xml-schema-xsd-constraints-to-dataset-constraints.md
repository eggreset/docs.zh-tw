---
title: 將 key XML 結構描述 (XSD) 條件約束對應至資料集條件約束
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: ad39fd75a3f8872ed2c24a65481209e3c772a638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757862"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>將 key XML 結構描述 (XSD) 條件約束對應至資料集條件約束
在結構描述中，您可以指定的項目上的索引鍵條件約束，或屬性使用**金鑰**項目。 具有指定索引鍵條件約束的項目或屬性，在任何結構描述執行個體中都必須具有唯一的值，且不可具有 Null 值。  
  
 索引鍵條件約束類似唯一的條件約束，唯一的不同處定義索引鍵條件約束的資料行不能有 Null 值。  
  
 下表概述**msdata**屬性中，您可以指定**金鑰**項目。  
  
|屬性名稱|描述|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|如果指定這個屬性，則它的值會被當成條件約束名稱使用。 否則，**名稱**屬性提供條件約束名稱的值。|  
|**msdata:PrimaryKey**|如果`PrimaryKey="true"`沒有、 **IsPrimaryKey**條件約束屬性設定為**true**，因此讓它成為主索引鍵。 **AllowDBNull**資料行屬性設定為**false**，因為主索引鍵不能有 null 值。|  
  
 在轉換結構描述在指定索引鍵條件約束時，對應處理序會建立唯一條件約束的資料表上**AllowDBNull** column 屬性設定為**false**中每個資料行條件約束。 **IsPrimaryKey**唯一條件約束的屬性也會設為**false**除非您已指定`msdata:PrimaryKey="true"`上**金鑰**項目。 它與結構描述 (其中 `PrimaryKey="true"`) 中唯一的條件約束相同。  
  
 在下列結構描述範例中，**金鑰**元素上指定索引鍵條件約束**CustomerID**項目。  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 **金鑰**項目指定的值**CustomerID**子項目**客戶**項目必須具有唯一值，並不能有 null 值。 轉譯 XML 結構描述定義語言 (XSD) 結構描述的過程中，對應處理序會建立下表：  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 XML 結構描述對應也會建立**UniqueConstraint**上**CustomerID**資料行，如下所示<xref:System.Data.DataSet>。 (為了便於了解，此處僅顯示相關屬性)。  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 在**資料集**所產生， **IsPrimaryKey**屬性**UniqueConstraint**設**true**因為結構描述指定`msdata:PrimaryKey="true"`中**金鑰**項目。  
  
 值**ConstraintName**屬性**UniqueConstraint**中**資料集**值**即**屬性中指定**金鑰**結構描述中的項目。  
  
## <a name="see-also"></a>另請參閱  
 [將 XML 結構描述 (XSD) 條件約束對應至資料集條件約束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [從 XML 結構描述 (XSD) 產生資料集關聯](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
