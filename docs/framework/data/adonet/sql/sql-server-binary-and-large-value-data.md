---
title: SQL Server 二進位和大量數值資料
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: c0202f6dc17d36fafb28206e17b71fc6d68d88c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363402"
---
# <a name="sql-server-binary-and-large-value-data"></a>SQL Server 二進位和大量數值資料
SQL Server 提供 `max` 規範，可擴充 `varchar`、`nvarchar` 和 `varbinary` 資料類型的儲存容量。 `varchar(max)``nvarchar(max)`，和`varbinary(max)`統稱為 「*大數值資料型別*。 您可以使用大數值資料型別來儲存最多可達 2^31-1 位元組的資料。  
  
 SQL Server 2008 導入了 FILESTREAM 屬性。這個屬性不是資料型別，而是可針對資料行定義的屬性，允許大數值資料儲存在檔案系統上，而非資料庫中。  
  
## <a name="in-this-section"></a>本節內容  
 [在 ADO.NET 中修改大量數值 (max) 資料](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 說明如何使用大型值資料類型。  
  
 [FILESTREAM 資料](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 說明如何使用儲存在 SQL Server 2008 中的大數值資料搭配 FILESTREAM 屬性。  
  
## <a name="see-also"></a>另請參閱  
 [SQL Server 資料類型和 ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [ADO.NET 中的 SQL Server 資料作業](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [在 ADO.NET 中擷取和修改資料](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
