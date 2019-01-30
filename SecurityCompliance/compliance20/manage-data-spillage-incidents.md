---
title: 管理 Microsoft 365 中的建立資料 spillage 事件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明如何使用 Office 365 安全性 & 規範中心新資料調查 （預覽） 工具來管理資料 spillage 事件。
ms.openlocfilehash: d863d87cc667b9695f9bf619c35575715dfa144e
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636614"
---
# <a name="managing-a-data-spillage-incident-in-microsoft-365"></a>管理 Microsoft 365 中的建立資料 spillage 事件 

機密文件發行至不受信任的環境時資料 spillage。當偵測到資料 spillage 事件時，務必快速評估的大小及位置的 spillage、 檢查周圍、 使用者活動及則從系統永久清除 spilled 的資料。

## <a name="scope-of-this-article"></a>本文的範圍

本文提供如何將永久移除項目從 Office 365 信箱所以不再是可存取或依使用者或系統管理員可復原清單中的指示。 

> [!NOTE]
> 當您刪除項目位於 SharePoint 或 OneDrive 商務網站時，他們會保留從您從其原始位置刪除時間 93 天。

## <a name="scenario"></a>案例

您正在得知其中員工不知情的情況下高度機密文件與多人共用透過電子郵件資料 spillage 事件。您想要快速評估者接收到此文件、 內部和外部組織。您已調查事件之後，您想與其他現場，檢閱，然後從 Office 365 永久移除 spilled 的資料共用您發現項目。將正在調查完成後，您要移除所有證據。 

## <a name="workflow"></a>工作流程

以下是使用資料調查 （預覽） 來管理資料 spillage 事件的工作流程：

1.  建立資料調查。

2.  搜尋 spilled 資料。

3.  檢閱並調查事件。

4.  永久刪除 spilled 的資料。

5.  關閉或刪除調查。


## <a name="before-you-begin"></a>開始之前

- 您將使用在 Office 365 安全性 & 規範中心中的資料調查 （預覽） 工具建立調查、 spilled 資料、 搜尋並檢閱並進行分析。然後您將使用安全性 & 規範中心 PowerShell 從 Office 365 永久刪除 spilled 的資料。 

- 若要建立調查，您必須是在安全性 & 規範中心規範系統管理員角色群組的成員。

- 若要刪除的郵件，您必須在安全性 & 規範中心組織管理角色群組的成員或指派搜尋及清除的角色。如需將使用者新增至角色群組的資訊，請參閱[授與使用者存取安全性 & 規範中心](../grant-access-to-the-security-and-compliance-center.md)。 

- 若要控制哪些使用者信箱與調查可搜尋的 OneDrive 帳戶，您的組織可以設定規範界限。如需詳細資訊，[設定 eDiscovery 調查的規範界限](../set-up-compliance-boundaries.md)。 

## <a name="step-1-create-a-data-investigation"></a>步驟 1： 建立資料調查

若要建立資料調查：

1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 安全性 & 規範中心，按一下 [**資料調查**。
 
4. 在 [**資料調查 （預覽）** ] 頁面上按一下 [**建立新的調查**。
    
5. 在 [**新的資料將正在調查**彈出式] 頁面上授與調查有關 （必要） 的名稱，然後輸入選用調查數字及描述。請注意的名稱必須是唯一您組織中。

6. 下**您想要建立此調查之後設定其他設定吗？**，執行下列其中一個動作：

    - 按一下 [**是]** 以建立調查，並在新的案例中顯示 [**設定**] 頁面。這可讓您將成員新增至調查。
    
    - 按一下 [**否]** 剛建立調查並顯示在 [**資料調查 （預覽）** ] 頁面上的情況下的清單中。如果您選擇這個選項，您會新增將用於將正在調查及預設搜尋及分析設定的唯一成員。您可以將成員新增或變更設定之後建立調查有關的任何時間。

7. 按一下 [**儲存**] 以建立調查。

    新的調查會顯示在 [**資料調查 （預覽）** ] 頁面上的清單。 

8. 若要開啟 [將正在調查，按一下 [將正在調查的名稱。 

    將正在調查的 [**首頁**] 索引標籤會顯示。 

> [!TIP]
> 請考慮建立調查的命名慣例並提供您可以在名稱和描述，讓您可以找出並參照未來如有必要的資訊為多。
 
## <a name="step-2-search-for-the-spilled-data"></a>步驟 2： 搜尋 spilled 資料 
 
如果您知道哪些的使用者想要搜尋溢出資料，您可以將其新增為其他人感興趣的將其資料來源對應至將正在調查並快速搜尋其信箱和 OneDrive 帳戶。若要將興趣的人員新增至調查，[**感興趣的人員**，和 [**新增人員感興趣**。 

在 [**搜尋**] 索引標籤中，您可以建立搜尋以尋找 spilled 的資料。您將會使用您用來找出要刪除這些[步驟 4](##step-4:-permanently-delete-the-spilled-data)中的相同郵件的 spilled 的資料的同一個搜尋查詢。如需建立搜尋的詳細資訊，請參閱 ＜ [Create 搜尋以收集資料](create-search-to-collect-data.md)。

執行搜尋之後，您可預覽搜尋結果和檢視搜尋統計資料來評估效益的搜尋查詢的範例。一旦您識別您要從 Office 365 中刪除的項目，您可以按一下 [**事件**] 索引標籤的 [然後建立事件並新增包含這些項目的搜尋結果。 

若要這樣做，按一下您想要調查的搜尋。在 [彈出式] 頁面上按一下 [**新增結果事件**並遵循指示。然後事件中檢閱個別的文件、 調查誰有存取權的文件和匯出文件。若要只刪除而不是檢閱這些文件，請前往[步驟 4](##step-4:-permanently-delete-the-spilled-data)。 

> [!IMPORTANT]
> 搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。例如，如果您搜尋包含社會安全號碼與您的文件會使用其為在搜尋查詢關鍵字，您必須刪除事後以避免進一步 spillage 查詢。您可以刪除搜尋或刪除整個調查有關在[步驟 5](##step-5:-close-or-delete-investigation)。 

## <a name="step-3-review-and-investigate"></a>步驟 3： 檢閱及調查 

在調查，移至 [**事件**] 索引標籤上，按一下 [在您在上一個步驟中建立事件。完成處理工作及搜尋結果會新增至事件之後，您可以檢閱其原生格式、 文字格式或附近原生格式中的個別文件。您可以建立額外的查詢以進一步縮小的文件及標籤文件以指出從您正在調查的研究結果清單。

若要群組文件，並取得更多協助您檢閱，按一下 [**管理事件**。在 [**分析**] 磚中按一下 [**分析**]。這將會執行進階的分析例如重複資料偵測、 電子郵件超執行緒，以及佈景主題分析。如需詳細資訊，請參閱：

- [近似重複項偵測](near-duplicates.md)
- [電子郵件威脅](email-threading.md)
- [佈景主題](themes.md)

若要決定哪些使用者參與資料 spillage，您可以在事件中建立新的查詢，然後使用 [寄件者/作者和收件者條件。這會建立所有寄件者、 收件者和收集的資料已加入至事件中找到的作者的清單。請務必檢查清單，以判斷清單中是否有任何外部使用者。如需詳細資訊，請參閱[搜尋條件](../keyword-queries-and-search-conditions.md#search-conditions)。

## <a name="step-4-permanently-delete-the-spilled-data"></a>步驟 4： 永久刪除 spilled 的資料

### <a name="deleting-mailbox-items"></a>刪除的信箱項目

檢閱並驗證的搜尋結果包含只必須要刪除的電子郵件訊息之後，您可以永久刪除這些執行**新增 ComplianceSearchAction-清除-PurgeType HardDelete**命令中安全性 & 規範中心 PowerShell。指示，請參閱[搜尋和刪除電子郵件訊息](../search-for-and-delete-messages-in-your-organization.md)。 

請注意，如果您的組織中的信箱啟用單一項目復原永久刪除項目會保留在使用者的 [可復原的項目] 資料夾中 （且可供系統管理員存取） 直到刪除項目保留期間端點 （預設值為 14 天）。此外，如果任何包含溢出資料的信箱處於合法持有或是指派給保留原則，就的訊息將會保留在可復原的項目] 資料夾直到撤除或排除信箱的保留原則。硬碟刪除郵件立即，需要執行其他工作。指示，請參閱[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)。  

> [!IMPORTANT]
> 記錄管理或法務部門檢查之前先移除保留或保留原則。您的組織可能會有定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。 

### <a name="deleting-site-items"></a>刪除網站項目

商務帳戶從 SharePoint 網站或 OneDrive 永久刪除文件，您必須將它刪除而且然後您必須從網站刪除然後將其從網站集合資源回收筒刪除。指示，請參閱[刪除文件中的 SharePoint 和 OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。

或者，您可以刪除可能包含溢出資料整個網站集合。指示，請參閱[刪除網站集合](https://docs.microsoft.com/sharepoint/delete-site-collection)。

## <a name="step-5-close-or-delete-the-investigation"></a>步驟 5： 關閉或刪除調查

刪除來源的內容位置 （信箱或網站） 中的文件之後，您仍必須將您新增至事件為您正在調查的一部分這些文件的複本。若要避免進一步資料 spillage，則應考慮刪除調查。

若要刪除調查：

1. 在 [**設定**] 索引標籤上按一下 [**將正在調查資訊**]。
2. 按一下 [**刪除案例**。 

如果您不需要刪除調查或您要儲存您收集期間調查有關的資訊，您可以按一下 [**關閉案例**。日後，您可以重新開啟關閉的調查。