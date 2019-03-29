---
title: 管理 Microsoft 365 中的資料外洩事件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明在 Office 365 安全性 & 合規性中心中使用新的資料調查 （預覽） 工具，來管理資料外洩事件。
ms.openlocfilehash: 33943ee4367e01f413cfa7840c796d5197323185
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862555"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>管理 Microsoft 365 中的資料外洩事件 

機密文件發行到未受信任的環境時的資料外洩。 偵測到的資料外洩事件時，務必快速評估的大小和位置的外洩，檢查使用者活動周圍，並再從系統永久清除 spilled 的資料。

## <a name="scope-of-this-article"></a>本文討論範圍

本文提供如何永久移除項目從 Office 365 信箱時，就無法再存取或由使用者或系統管理員可復原清單中的指示。 

> [!NOTE]
> 當您刪除項目位於 SharePoint 或 OneDrive for Business 網站時，他們會保留您刪除其原始位置的時間從 93 天。

## <a name="scenario"></a>案例

您正在其中員工不知情的情況下高度機密文件與多個人員共用透過電子郵件資料外洩事件的通知。 您想要快速評估者接收到此文件，同時內部和外部組織。 您已調查事件之後，您想要與其他現場檢閱，並再永久移除 Office 365 spilled 的資料共用您所發現的錯誤。 調查完成後，您想要移除所有的證據。 

## <a name="workflow"></a>工作流程

以下是使用資料調查 （預覽） 來管理資料外洩事件的工作流程：

1.  建立資料調查。

2.  搜尋 spilled 資料。

3.  檢閱並調查事件。

4.  永久刪除 spilled 的資料。

5.  關閉或刪除調查。


## <a name="before-you-begin"></a>開始之前

- 您將使用在 Office 365 安全性 & 合規性中心中的資料調查 （預覽） 工具，來建立調查、 搜尋 spilled 的資料，請先檢閱和分析。 然後您將使用安全性 & 合規性中心 PowerShell 來從 Office 365 中永久刪除 spilled 的資料。 

- 若要建立調查，您必須是中的安全性 & 合規性中心的符合性系統管理員角色群組的成員。

- 若要刪除的郵件，您必須是安全性 & 合規性中心中 「 組織管理角色群組的成員，或是獲指派 「 搜尋及清除的角色。 如需將使用者新增至角色群組的詳細資訊，請參閱[授與使用者存取安全性 & 合規性中心](../grant-access-to-the-security-and-compliance-center.md)。 

- 若要控制哪些使用者信箱和調查可搜尋的 OneDrive 帳戶，您的組織可以設定合規性界限。 如需詳細資訊，[設定電子文件探索調查的合規性界限](../set-up-compliance-boundaries.md)。 

## <a name="step-1-create-a-data-investigation"></a>步驟 1： 建立資料調查

若要建立資料調查：

1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在安全性 & 合規性中心中，按一下 [**資料調查**。
 
4. 在 [**資料調查 （預覽）** ] 頁面上，按一下 [**建立新的調查**。
    
5. 在**新的資料調查**彈出式頁面上，提供調查 （必要） 的名稱，然後輸入選用調查數目和描述。 請注意，必須在您的組織中是唯一名稱。

6. **您想要設定其他設定之後建立此調查？**，執行下列其中一項：

    - 按一下 [ **]** 來建立和調查]，並顯示 [**設定**] 頁面中新的案例。 這可讓您將成員新增至調查。
    
    - 按一下 [**否]** 剛建立調查，並顯示於 [**資料調查 （預覽）** ] 頁面上的案例清單。 如果您選擇此選項，您將會新增將用調查，以及預設搜尋和分析設定的唯一成員。 您可以將成員新增或變更設定之後建立調查的任何時間。

7. 按一下 [**儲存**] 以建立調查。

    新調查會顯示在**資料調查 （預覽）** 頁面上的清單。 

8. 若要開啟 [調查，請按一下 [調查的名稱。 

    針對調查 [**首頁**] 索引標籤會顯示。 

> [!TIP]
> 請考慮建立調查的命名慣例，並提供最多為讓您可以找出並參照在未來必要時，您可以在名稱和描述的資訊。
 
## <a name="step-2-search-for-the-spilled-data"></a>步驟 2： 搜尋 spilled 資料 
 
如果您知道想要搜尋溢出資料的使用者，您可以將其新增為調查對應及其資料來源，並快速搜尋其信箱和 OneDrive 帳戶感興趣的人員。 若要新增調查感興趣的人員，按一下 [**感興趣的人員**，，，然後按一下 [**新增人員感興趣**。 

在 [**搜尋**] 索引標籤中，您可以建立搜尋來尋找 spilled 的資料。 您會使用您用來尋找要刪除這些相同的郵件，在[步驟 4](#step-4-permanently-delete-the-spilled-data)中的 spilled 的資料的相同搜尋查詢。 如需建立搜尋的詳細資訊，請參閱 <<c0>建立 「 搜尋 」 來收集資料。

執行搜尋之後，您可以預覽搜尋結果和檢視搜尋統計資料，來評估您的搜尋查詢的有效性的範例。 一旦您找出您想要從 Office 365 中刪除的項目，您可以**事件**] 索引標籤，然後建立事件並增加搜尋結果包含這些項目。 

若要這麼做，請按一下您想要調查的搜尋。 在彈出式頁面上，按一下 [**新增結果事件**，並遵循指示。 然後中意外事件，檢閱個別文件、 調查誰有權存取的文件和匯出文件。 只刪除而不是檢閱這些文件，請移至[步驟 4](#step-4-permanently-delete-the-spilled-data)。 

> [!IMPORTANT]
> 您在搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。 例如，如果您正在搜尋包含社會安全號碼與您的文件使用 as 關鍵字搜尋查詢中，您必須刪除之後，避免發生外洩的查詢。 您可以刪除搜尋，或刪除整個調查在[步驟 5](#step-5-close-or-delete-the-investigation)。 

## <a name="step-3-review-and-investigate"></a>步驟 3： 檢閱和調查 

在調查，前往 [**事件**] 索引標籤上，按一下 [您在上一個步驟中建立事件。 完成處理工作，並在搜尋結果會新增至事件之後，您可以檢閱其原生格式、 文字格式或附近原生格式中的個別文件。 您可以建立額外的查詢，以進一步縮小的文件和標記文件，以指出您調查從結果清單。

若要群組文件，並取得更多協助您檢閱，請按一下 [**管理事件**。 在 [**分析**] 磚中，按一下 [**分析**]。 這將會執行進階的分析，例如重複資料偵測、 電子郵件執行緒，以及佈景主題分析。 如需詳細資訊，請參閱：

- [近似重複項偵測](near-duplicates.md)
- [電子郵件威脅](email-threading.md)
- [佈景主題](themes.md)

若要決定哪些使用者參與資料外洩，您可以在事件中建立新的查詢，然後使用 [寄件者/作者和收件者條件。 這會建立一份所有寄件者、 收件者及收集的資料已加入至事件中找到的作者。 請務必檢查清單，以判斷在清單中是否有任何外部使用者。 如需詳細資訊，請參閱 <<c0>搜尋條件。

## <a name="step-4-permanently-delete-the-spilled-data"></a>步驟 4： 永久刪除 spilled 的資料

### <a name="deleting-mailbox-items"></a>刪除信箱項目

檢閱並驗證搜尋結果包含只必須刪除電子郵件之後，您可以永久刪除它們執行**New-compliancesearchaction-清除-PurgeType HardDelete**命令中安全性 & 合規性中心 PowerShell。 如需相關指示，請參閱[搜尋並刪除電子郵件訊息](../search-for-and-delete-messages-in-your-organization.md)。 

請注意，如果貴組織中信箱的已啟用單一項目復原永久刪除項目會保留在使用者的 [可復原的項目] 資料夾中 （以及由系統管理員可以存取） 直到已刪除的項目保留期間結束 （預設值為 14 天）。 此外，如果任何包含溢出資料的信箱位於合法持有或指派到保留原則後，清除的郵件仍會保留在 [可復原的項目] 資料夾中，直到移除保留或從保留原則中排除信箱。 若要實刪除的郵件立即，您必須執行加入工作。 如需相關指示，請參閱 <<c0>可復原的項目保留的雲端架構信箱上的資料夾內刪除項目。  

> [!IMPORTANT]
> 移除保留或保留原則之前，先檢查與您的記錄管理或法務部門。 您的組織可能會有一個原則來定義是否要保留的信箱上或資料外洩事件會優先採用。 

### <a name="deleting-site-items"></a>刪除站台的項目

若要永久刪除文件的 SharePoint 網站或 OneDrive 商務帳戶，您必須刪除它，然後您必須從網站刪除再刪除網站集合資源回收筒。 如需相關指示，請參閱[刪除文件中的 SharePoint 和 OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。

或者，您可以刪除可能包含溢出資料整個網站集合。 如需相關指示，請參閱[刪除網站集合](https://docs.microsoft.com/sharepoint/delete-site-collection)。

## <a name="step-5-close-or-delete-the-investigation"></a>步驟 5： 關閉或刪除調查

刪除文件中的來源的內容位置 （信箱或網站） 之後，您仍然必須這些您加入在調查中事件的文件的複本。 若要避免進一步的資料外洩，您應該考慮刪除調查。

若要刪除調查：

1. 在 [**設定**] 索引標籤中，按一下 [**調查的資訊**。

2. 按一下 [**刪除案例**。 

如果您不需要刪除調查，或您想要儲存您在調查期間收集到的資訊，您可以按一下 [**關閉案例**。 日後，您可以重新開啟關閉的調查。