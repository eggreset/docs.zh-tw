---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: 37c83a9c1062fe074e41ec5db211fd513355c045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518482"
---
# <a name="sqlstoreextensibility"></a>SQLStoreExtensibility
這個範例示範 SQL 工作流程執行個體存放區中已提升屬性的使用方式和組態。 SQL 工作流程執行個體存放區是以 SQL 為基礎的執行個體存放區實作。 它允許執行個體在 SQL Server 或 SQL Server Express 資料庫中來回儲存及載入其狀態。 存放區擴充性功能可讓使用者定義儲存在執行個體存放區中的屬性。 這些屬性會顯示在提升屬性檢視表中，供使用者查詢屬性。  
  
 這個範例是由實作計數服務的工作流程所組成。 一旦叫用服務的 Start 方法，服務就會從 0 計數到 29。 計數器每 2 秒遞增一次。 每次計數後，工作流程會保存。 目前計數器值會儲存在執行個體存放區中做為已提升的屬性。  
  
 計數工作流程是由工作流程服務主機自我主控的。 此程式的 `Main` 方法會執行下列動作：  
  
-   建立主控計數工作流程的工作流程服務主機，以及定義可用來連接至計數工作流程的端點。  
  
-   定義 SQL 工作流程執行個體存放區行為，用來設定 SQL 工作流程執行個體存放區。 此存放區根據指示將 `CountStatus` 視為已提升的屬性。  
  
-   建立會呼叫計數工作流程 Start 方法的用戶端。  
  
 一旦程式啟動，計數器會自動開始計數。 請注意，載入執行個體以及設定 SQL 工作流程執行個體存放區可能要花幾秒才能完成。  
  
 若要將計數器值提升為自訂屬性，必須執行下列步驟：  
  
1.  `CounterStatus` 類別定義型別為 <xref:System.Activities.Persistence.PersistenceParticipant> 的執行個體例外狀況，通常活動會使用它來供應狀態變數。 `Count` 定義為唯寫值。 當工作流程執行個體達到保存點時，執行個體延伸將 `Count` 屬性儲存至持續性資料集合中。  
  
2.  在建立執行個體存放區時，透過 `CountStatus` 方法定義新屬性 `store.Promote()`。  
  
3.  工作流程的 `SaveCounter` 活動將目前計數器值指派至 `Count` 狀態欄位。  
  
### <a name="to-use-this-sample"></a>若要使用這個範例  
  
1.  建立執行個體存放區資料庫。  
  
    1.  開啟 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示字元。  
  
    2.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示字元中，巡覽至範例目錄 (\WF\Basic\Persistence\SqlStoreExtensibility\CS)，並執行 CreateInstanceStore.cmd。  
  
        > [!WARNING]
        >  CreateInstanceStore.cmd 指令碼會嘗試在 SQL Server 2008 Express 預設執行個體上建立資料庫。 如果您想要在不同的執行個體上安裝資料庫，請修改指令碼。  
  
2.  開啟 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，並載入 SqlStoreExtensibility.sln 方案，然後按 CTRL+SHIFT+B 加以建置。  
  
    > [!WARNING]
    >  如果在非預設的 SQL Server 執行個體上安裝資料庫，請在建置方案之前，先更新程式碼中的連接字串。  
  
3.  瀏覽至專案的 bin 目錄 (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) 中執行範例，以系統管理員權限[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]、 以滑鼠右鍵按一下 SqlStoreExtensibility.exe 並選取**身分執行系統管理員**。  
  
### <a name="to-verify-the-sample-is-working-correctly"></a>若要驗證範例是否正常執行  
  
1.  若要檢視選取的執行個體資料表的內容中使用 SQL Server Management Studio**資料庫**， **InstanceStore**，然後**System.ServiceModel.Activities.DurableInstancing.InstanceTable**在 [物件總管] 中，以滑鼠右鍵按一下**System.ServiceModel.Activities.DurableInstancing.InstanceTable**選取**選取前 1000 個資料列**。 如需有關 SQL Server Management Studio 的詳細資訊，請參閱[SQL Server Management Studio 簡介](http://go.microsoft.com/fwlink/?LinkId=165645)  
  
2.  觀察列出的工作流程執行個體。  
  
3.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示字元中，執行位於範例目錄 (\WF\Basic\Persistence\SqlStoreExtensibility) 的 QueryInstanceStore.cmd 指令碼。  
  
4.  觀察計數器值顯示在底下**CountStatus**。  
  
5.  執行幾次指令碼以查看**CountStats**值變更。  
  
6.  按 Enter 鍵，結束工作流程應用程式。  
  
### <a name="to-uninstall-the-sample"></a>若要解除安裝範例  
  
1.  執行位於範例目錄 (\WF\Basic\Persistence\SqlStoreExtensibility) 的 RemoveInstanceStore.cmd 指令碼，即可移除執行個體存放區資料庫。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至[Windows Communication Foundation (WCF) 和適用於.NET Framework 4 的 Windows Workflow Foundation (WF) 範例](http://go.microsoft.com/fwlink/?LinkId=150780)下載所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a>另請參閱  
 [工作流程持續性](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [工作流程服務](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [AppFabric 主控與持續性範例](http://go.microsoft.com/fwlink/?LinkId=193961)
