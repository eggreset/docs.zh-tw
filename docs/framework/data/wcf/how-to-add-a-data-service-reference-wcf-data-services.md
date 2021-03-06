---
title: 如何：加入資料服務參考 (WCF 資料服務)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: a8dcc01fb7a564a363cabed6a22738cd520d317f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356227"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>如何：加入資料服務參考 (WCF 資料服務)
您可以使用**加入服務參考**將參考加入至 Visual Studio 中的對話方塊[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]。 這樣可以讓您更輕鬆地在 Visual Studio 開發的用戶端應用程式中存取資料服務。 當您完成此程序時，會根據從資料服務取得的中繼資料產生資料類別。 如需詳細資訊，請參閱[產生資料服務用戶端程式庫](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)。  
  
### <a name="to-add-a-data-service-reference"></a>加入資料服務參考  
  
1.  (選擇性) 如果資料服務不是方案的一部分且尚未執行，請啟動資料服務，並且記下資料服務的 URI。  
  
2.  以滑鼠右鍵按一下 用戶端專案，然後選取**加入服務參考**。  
  
3.  如果資料服務目前方案的一部分，請按一下**探索**。  
  
     -或-  
  
     在**位址**文字方塊中，輸入基底 URL 的資料服務，例如`http://localhost:1234/Northwind.svc`，然後按一下 **移**。  
  
4.  按一下 [確定 **Deploying Office Solutions**]。  
  
     這將會加入包含資料類別的新程式碼檔案，可用於存取資料服務資源物件，並與其進行互動。  
  
## <a name="see-also"></a>另請參閱  
 [快速入門](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
