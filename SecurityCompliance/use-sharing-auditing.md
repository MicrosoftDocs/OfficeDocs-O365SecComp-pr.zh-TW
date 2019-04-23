---
title: 稽核共用來找出與外部使用者共用的資源
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共用是 SharePoint Online 和商務用 OneDrive 中的主要活動。 系統管理員現在可以使用 Office 365 稽核記錄檔中的共用稽核來判斷如何共用正在使用其組織中。 '
ms.openlocfilehash: 08b511acdf74edac5b2d595d1b60bdd84d630918
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958244"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>稽核共用來找出與外部使用者共用的資源

共用是 SharePoint Online 和商務用 OneDrive 中的主要活動，它廣泛用在 Office 365 組織。 系統管理員現在可以使用 Office 365 稽核記錄檔中的共用稽核來判斷如何共用正在使用其組織中。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint 共用結構描述

共用事件 （排除的共用原則和共用連結的事件） 中主要的一種方式是不同的檔案和資料夾相關的事件： 一個使用者所要採取一些效果在另一位使用者的動作。 例如，使用者 A 可讓使用者 B 存取檔案。 在這個範例中，使用者 A 的*做使用者*且使用者 B 是*目標使用者*。 在 SharePoint 檔案結構描述中之使用者的巨集指令只會影響檔案本身。 當使用者開啟檔案，僅**FileAccessed**事件中所需的資訊是影響之使用者。 若要解決這項差異，沒有個別結構描述，稱為*SharePoint 共用結構描述*，會擷取共用事件的詳細資訊。 這可確保系統管理員有更深入的人員共用資源和使用者資源共用的。 
  
共用結構描述提供兩個額外的欄位與共用事件相關的稽核記錄中： 
  
- **TargetUserOrGroupName** -儲存 UPN 或的目標使用者或群組，資源共用 (在上述範例中的 「 使用者 B 」) 的名稱。 
    
- **TargetUserOrGroupType** -識別是否目標使用者或群組成員、 訪客、 群組或合作夥伴。 
    
這兩個欄位，除了其他屬性，從 Office 365 稽核記錄檔結構描述，例如使用者、 作業及日期可以告訴完整本文*哪些*使用者共用*哪些*資源與*對象**時*的相關資訊。 
  
沒有很重要的共用的本文的另一個資料庫架構屬性。 **EventData**屬性會儲存共用事件相關的其他資訊。 例如，當使用者與其他使用者共用網站，這被透過將目標使用者新增至 SharePoint 群組。 **EventData**屬性擷取此為系統管理員提供內容的其他資訊。 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>SharePoint 共用模型及共用事件

共用實際上定義由三個不同的事件： **SharingSet**、 **SharingInvitationCreated**和**SharingInvitaitonAccepted**。 以下方式共用事件的工作流程登入 Office 365 稽核記錄檔。 
  
![共用稽核的運作方式的流程圖](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
當使用者 （影響之使用者） 想要與另一位使用者 （目標使用者） 共用資源時，SharePoint （或商務用 OneDrive） 會先檢查目標使用者的電子郵件地址是否已在組織的目錄中的使用者帳戶相關聯。 如果目標使用者位於組織的目錄中，SharePoint 會執行下列動作：
  
-  立即將指派的目標使用者權限來存取資源。 
    
- 將共用通知傳送至目標使用者的電子郵件地址。
    
- 記錄**SharingSet**事件。 
    
 如果目標使用者的使用者帳戶不在組織的目錄，SharePoint 會執行下列動作： 
  
- 建立共用邀請，並將其傳送到的目標使用者的電子郵件地址。
    
- 記錄**SharingInvitationCreated**事件。 
    
    > [!NOTE]
    > **SharingInvitationCreated**事件相關聯最一律外部或是使用來賓身分共用時的目標使用者沒有存取共用的資源。 
  
當在目標使用者接受已傳送給他們 （藉由按一下邀請中的連結），SharePoint 共用邀請記錄**SharingInvitationAccepted**事件，並指派的目標使用者權限來存取資源。 在目標使用者的其他資訊也會記錄，例如邀請傳送至使用者和實際接受邀請之使用者的身分識別。 在某些情況下，這些使用者 （或電子郵件地址） 可能會不同。 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>如何找出與外部使用者共用的資源

系統管理員的一般需求建立指與組織外部使用者共用的所有資源的清單。 藉由使用 Office 365 中的共用稽核，系統管理員現在可以產生這份清單。 方法如下。
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>步驟 1： 搜尋共用事件，並將結果匯出至 CSV 檔案

第一個步驟是搜尋共用事件的 Office 365 稽核記錄檔。 如需詳細資訊 （包括的必要權限） 的相關搜尋稽核記錄，請參閱 <<c0>的搜尋稽核記錄中的安全性 &amp; 合規性中心。
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在 [安全性 & 合規性中心的左窗格中，按一下 [**搜尋**  > **稽核記錄搜尋**。
    
    會顯示 [**稽核記錄搜尋**] 頁面。 
    
4. [**活動**，按一下 [**共用活動**搜尋僅適用於共用事件。 
    
    ![在活動下方，選取 [共用活動](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  選取要尋找共用所發生事件的期間內的日期和時間範圍。 
    
6. 按一下 [**搜尋**] 以執行搜尋。 
    
7. 搜尋完成時執行和結果會顯示，請按一下 [**匯出結果** \> **下載所有結果**。
    
    選取 [匯出] 選項後，會提示您開啟或儲存該 CSV 檔案的視窗底部會顯示訊息。
    
8. 按一下 [**儲存** \> **另存為**並在本機電腦上將 CSV 檔案儲存至資料夾。 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>步驟 2： 篩選與外部使用者共用的資源的 CSV 檔案

下一步是**SharingSet**和**SharingInvitationCreated**事件，將 CSV 篩選，並顯示這些事件**TargetUserOrGroupType**屬性所在**來賓**。 若要這麼做，您將在 Excel 中使用 Power Query 功能。 在 Excel 2016 中執行下列程序。 
  
1. 在 Excel 2016 中，開啟空白活頁簿。
    
2. 按一下 [**資料**] 索引標籤。 
    
3. 按一下 [**新增查詢** \> **檔案從** \> **從 CSV**。
    
    ![在 [資料] 索引標籤中，選取 [新增查詢、 從檔案中，選取，然後選取從 CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. 在步驟 1 中開啟您已下載的 CSV 檔案。
    
    在 [查詢編輯器] 中開啟 CSV 檔案。 請注意，有四個欄：**時間**、**使用者**、**動作**和**詳細資料**。 [**詳細資料**] 欄是多重屬性的欄位。 下一步是建立新的資料行的每個 [**詳細資料**] 欄中的屬性。 
    
5. 選取 [**詳細資料**] 欄中，，然後按一下 [**首頁**] 索引標籤上的 [**分割資料行** \> **的分隔符號**。
    
    ![在 [首頁] 索引標籤上按一下分割資料行，然後按一下 [由分隔符號](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. 在 [**分割資料行來分隔字元**] 視窗中，執行下列動作： 
    
      - 在 [**選取或輸入分隔符號**，選取 [**逗點**。
    
      - 在 [**分割**] 下選取 [**在分隔符號的每個項目**。
    
7. 按一下 [確定]。
    
    [**詳細資料**] 欄分割成多個資料行。 每個新的欄名為**Detail.1**、 **Detail.2**、 **Detail.3**，等等。 您會注意到**Detail.n**欄中的每個儲存格中的值以在屬性名稱例如，**作業： SharingSet**、**作業： SharingInvitationAccepted**和**作業： SharingInvitationCreated**。
    
    ![[詳細資料] 欄分割成多個資料行，其中每個屬性](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. 在 [**檔案**] 索引標籤中，按一下 [**關閉&amp;負載**以關閉 [查詢編輯器，並開啟 Excel 活頁簿中的檔案。 
    
    下一步是以篩選要只會顯示**SharingSet**和**SharingInvitationCreated**事件的檔案。 
    
9. 移至 [**首頁**] 索引標籤，然後選取 [**動作**] 資料行。 
    
10. 在**排序&amp;篩選**下拉式清單中，清除所有選項，然後選取 [ **SharingSet**和**SharingInvitationCreated**，並按一下 [**確定]**。
    
    Excel 會顯示**SharingSet**和**SharingInvitationCreated**事件的資料列。 
    
11. 移至名為**Detail.17** （或哪一個資料行包含**TargetUserOrGroupType**屬性） 的資料行，然後選取它。 
    
12. 在**排序&amp;篩選**下拉式清單中，清除所有選項，然後選取 [ **TargetUserOrGroupType:Guest**，並按一下 [**確定]**。
    
    現在 Excel 顯示**SharingInvitationCreated**和**SharingSet**事件，而在目標使用者是您組織外的列，因為值**TargetUserOrGroupType:Guest**識別外部使用者。 
    
下表會顯示指定的日期範圍內的來賓使用者與共用資源組織中所有使用者。
  
![在 Office 365 中的共用活動的稽核記錄](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
雖然它不會納入前一個表格， **Detail.10**資料行 （或哪一個資料行包含**ObjectId**屬性） 會識別已與目標使用者; 共用的資源例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。
  
> [!TIP]
> 如果您想要識別當來賓使用者已實際上指派權限可存取資源 (而不是只的資源，其中與他們共用)，重複步驟 10、 11 和 12，及**SharingInvitationAccepted**和**SharingSet 篩選**步驟 10 中的事件。 
