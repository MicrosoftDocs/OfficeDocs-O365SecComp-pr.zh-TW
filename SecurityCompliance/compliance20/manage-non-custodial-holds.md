---
title: 進階 eDiscovery （預覽） 來管理保留
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
description: ''
ms.openlocfilehash: 75ddbcfb401d285dfb7a4b610e3f0709e21946f2
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607572"
---
# <a name="rename-this-page-and-md-file-to-managing-holds"></a>重新命名此頁面及 MD 檔案，以 「 管理保留"

# <a name="holds-in-advanced-ediscovery-preview"></a>進階 eDiscovery (Preview) 中的保留
您可以使用進階的 eDiscovery （預覽） 案例來建立保留来保留可能是您案例相關的內容。使用進階的 eDiscovery （預覽） 保留功能，您可以利用保留 custodians 和其資料來源。此外，您可以利用非 custodial 保留對信箱和 OneDrive for Business 的網站。您也可以將保留群組信箱、 SharePoint 網站及 OneDrive 商務網站的 Office 365 群組。同樣地，您可以利用保留對信箱和相關聯的 Microsoft 小組網站。當您保留上放置的內容位置時，內容會保留直到您放開 okay、 移除特定資料位置，或完全刪除保留原則。

## <a name="manage-custodian-based-holds"></a>管理 Okay 型保留

在某些情況下，您可能需要一組資料 custodians 您識別並選擇来保留。進階的 ediscovery （預覽），這些 custodians thold，當使用者和自己所選取的資料來源會自動新增至 okay 保留原則。 

若要檢視 okay 保留原則：

1. **安全性 & 規範中心**中，按一下 [ **eDiscovery > 進階的 eDiscovery （預覽）** 若要在組織中顯示的情況下的清單。
   
2. 瀏覽至要新增您的案例中的 custodians **Custodians** ] 索引標籤。若要了解如何新增及上的進行 custodians 保留進階的 eDiscovery （預覽） 案例中，瀏覽**案例中管理 Custodians**一節。如果您已新增 custodians 並處於保留狀態，移至步驟 3。
   
3. 瀏覽至 [**保留**] 索引標籤並選取 Okay 原則。
   
4. 在詳細資料彈出式中，您可以看到保留原則的統計資料。您也可以執行像是將查詢套用至您 okay 型保留的動作。如需建立保留查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions )
 
## <a name="manage-non-custodial-holds"></a>管理非 Custodial 保留
當您建立保留時，您有下列選項的範圍會保留在指定的內容位置的內容：
  - 您建立的所有內容都處於保留狀態設為無限期保留。或者，您可以建立查詢式的保留僅符合內容的搜尋查詢處於保留狀態。
  - 您可以指定日期範圍，以保留已傳送、 接收到，或建立的日期範圍內的內容。或者，您可以保留不論當它已傳送、 接收到，或建立的所有內容。

若要建立保留 eDiscovery 案例：
  1. **安全性 & 規範中心**中，按一下 [ **eDiscovery > 進階的 eDiscovery （預覽）** 若要在組織中顯示的情況下的清單。
  
  2. 按一下您想要建立的保留案例] 旁的 [開啟]。
  
  3. 在 [**首頁**] 索引標籤的大小寫按一下 [**保留**] 索引標籤。
  
  4. 在 [**保留**] 索引標籤上按一下 [**建立**]。
  
  5. 在 [名稱保留] 頁面中，提供保留的名稱。保留名稱必須是在組織中唯一的。
 
  6. （選用）在 [描述] 方塊中新增的保留的描述。
  
  7. 按 [下一步]。
  
  8. 選擇您想要進行的內容位置保留。您可以在保留上放置信箱、 網站及公用資料夾。a. **Exchange 電子郵件**-[**選擇使用者、 群組或小組**和 [**選擇使用者、 群組或小組**一次。若要指定要保留信箱。使用 [搜尋] 方塊中找到使用者信箱使用者和通訊群組 （置於群組成員的信箱保留） 至保留。您也可撥打相關聯的信箱上的保留供 Office 365 群組或 Microsoft 小組。選取使用者、 群組、 小組] 核取方塊、 按一下 [**選擇**] 和 [**完成**。
 
    [!NOTE]
    當您按一下 [**選擇使用者、 群組或小組**來指定要保留信箱，會顯示信箱選擇是空的。這是由設計，以提升效能。若要將人員新增至這份清單中，輸入的名稱 （至少要有 3 個字元） 在 [搜尋] 方塊中。


    b. **SharePoint 網站**-按一下 [**選擇的網站**] 和 [**選擇網站**一次以指定 SharePoint 和 OneDrive for Business 網站置於保留。輸入您想要保留每個網站的 URL。您也可以針對 Office 365 群組或 Microsoft 小組新增 SharePoint 網站的 URL。按一下 [**選擇**] 和 [**完成**。
    
     請參閱**FAQ** ] 區段中放入保留的 Office 365 群組及 Microsoft 小組的秘訣。

    [!NOTE]
    在極罕見的人員的使用者主體名稱 (UPN) 已變更案例中，其 OneDrive 帳戶的 URL 會變更要併入新的 UPN。如果發生這種情況，您必須新增使用者的新 OneDrive URL 並移除舊來修改保留。

     c. **Exchange 公用資料夾**-將切換參數移至組織保留的所有位置將放在 Exchange Online 中的所有公用資料夾。請注意，您無法選擇特定公用資料夾遷移至放入保留。保留設定成 [**無**如果您不想要的公用資料夾上設定保留切換參數。

  9. 當您完成新增至保留的內容位置時，按一下 [**下一步**]。
  
  10. 若要建立條件查詢式保留，請完成下列設定。否則請只是按一下 [**下一步**。1.1 中 [關鍵字] 方塊中，類型] 方塊中的搜尋查詢以便符合搜尋準則的內容放入保留。您可以指定關鍵字、 郵件內容或文件屬性，例如檔案名稱。您也可以使用或不使用布林運算子，例如 AND、 OR 的較複雜查詢。如果您遺漏保留空白，則將會位於指定之內容的位置中的所有內容都放在 [關鍵字] 方塊。

    1.2 按一下 [**新增**條件新增一或多個條件，縮減保留搜尋查詢]。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您建立保留。例如您可以指定日期範圍，讓電子郵件或站台建立日期範圍內的文件會處於保留狀態。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢 AND 運算子。表示項目必須滿足的關鍵字查詢及可放置在此條件就會保留。

     如需建立搜尋查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions)。

  11. 設定查詢式之後保留、 按一下 [**下一步**。
 
  12. 檢閱您的設定] 和 [**建立此保留**。


## <a name="view-hold-statistics"></a>檢視保留統計資料
一些時間之後的新保留的相關資訊會顯示所選保留 [**保留**] 索引標籤的詳細資料窗格中。此資訊包含的信箱數目上的網站保留與已對內容的相關的統計資料保留，例如處於保留狀態的總人數及的項目大小和上次所計算的統計資料的保留。這些保留統計值能協助您識別要保留多少 eDiscovery 案例相關的內容。

保留有關保留統計資料記住下列事項：

  - 保留的項目數總計會指出從保留的所有內容來源的項目數。如果您已建立查詢式保留功能，這次統計指出符合查詢的項目數。
  - 保留的項目數也包含編製索引的內容位置中找到的項目。如果您建立查詢式保留，內容的位置中的所有編製索引項目會放在保留的記事。這包括編製索引的項目不符合搜尋準則的查詢式保留及編製索引的項目可能屬於以外的日期範圍條件。這是與當您執行內容搜尋] 中編製索引的項目已不符合搜尋查詢或排除的日期範圍條件不包含在搜尋結果中有什麼不同。編製索引的項目相關的詳細資訊，請參閱 [Office 365 中的內容搜尋中部分索引項目] (https://docs.microsoft.com/en-us/office365/SecurityCompliance/partially-indexed-items-in-content-search)。 
  - 您可以透過按一下 [更新統計資料以重新執行計算保留的項目數目前的搜尋預估取得最新的保留統計資料。
  - 若有必要，請按一下 [重新整理在工具列中要更新的詳細資料窗格中的保留統計資料。
  - 因為其信箱或網站會保留使用者通常會傳送或接收新的電子郵件訊息和建立新的 SharePoint 和 OneDrive for Business 文件增加一段時間保留它的一般上的項目數目。

[!NOTE]
如果當移至不同的區域在多個地理位置環境中的 SharePoint 網站或 OneDrive 帳戶時，該網站的統計資料將不會包含在保留統計資料。不過，在網站中的內容仍能音樂。此外，如果網站移至不同的區域不會更新顯示在保留中的 URL。您必須編輯保留及更新 URL。

## <a name="faq"></a>常見問題集
- **如何 okay 以對應其他 Office 365 群組或 Microsoft 小組網站？與不住放置非-Custodial 暫止 Office 365 群組及 Microsoft 小組？** Office 365 群組之內建的 Microsoft 小組。因此，將其置於保留 eDiscovery 案例中是非常類似。將 Office 365 群組和上的 Microsoft 小組保留狀態時請記住下列事項。
  - 若要放置音樂位於 Office 365 群組及 Microsoft 小組中的內容，您必須指定的信箱與 SharePoint 網站的群組或小組與之相關聯。
  
  - 執行**Get UnifiedGroup** cmdlet 在 Exchange Online 中檢視 Office 365 群組或 Microsoft 小組的屬性。這是一個好方法來取得具有相關聯的 Office 365 群組或 Microsoft 小組網站的 URL。例如，下列命令會顯示所選的屬性名為資深領導小組 Office 365 群組：

'' powershell

    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    '''

 [!NOTE]
 若要執行 Get UnifiedGroup 指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。

 - 當使用者的信箱搜尋時，將不會搜尋所有 Office 365 群組或使用者為其成員的 Microsoft 小組。同樣地，當撥打 Office 365 群組或 Microsoft 小組保留，只有群組信箱和群組網站會放在保留;信箱和 OneDrive for Business 網站群組成員的不處於保留狀態除非您明確地將其新增為 custodians 或將其資料來源保留。因此，如果您在會放置在 Office 365 群組或 Microsoft 小組需要保留特定 okay，請考慮將群組網站及群組信箱對應至 okay (請參閱管理 Custodians 進階 eDiscovery (Preview) 中)。如果 Office 365 群組或 Microsoft 小組不能歸因於單一 okay，請考慮新增至非-custodial 來源保留。 
 
 - 若要取得 Office 365 群組或 Microsoft 小組成員的清單，您可以在 Office 365 系統管理中心首頁 > 群組] 頁面上檢視屬性。或者，您可以在 Exchange Online PowerShell 中執行下列命令：

    '' powershell
    
        Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
        '''

[!NOTE]
若要執行 Get UnifiedGroupLinks 指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。

- 屬於 Microsoft 小組通道的通道交談會儲存在具有小組與相關聯的信箱。同樣地，小組成員共用通道中的檔案都會儲存在團隊的 SharePoint 網站上。因此，您必須將 Microsoft 小組信箱和 SharePoint 網站上的保留要保留交談和通道中的檔案。
  
- 或者，是 [聊天室] 清單中的 Microsoft 小組的一部分的交談會儲存在信箱的使用者參與交談。 使用者共用聊天交談中的檔案儲存在 OneDrive for Business 網站共用檔案的使用者。因此，您必須將個別使用者信箱並 OneDrive for Business 網站上按住保留交談和在 [聊天室] 清單中的檔案。 
  
- 每個 Microsoft 小組或小組通道包含 Wiki 筆記記錄與共同作業。Wiki 內容會自動儲存至含有.mht 格式的檔案。此檔案儲存在團隊的 SharePoint 網站上的小組 Wiki 資料文件庫。您可以利用音樂 Wiki 內容所保留上放置團隊的 SharePoint 網站。

[!Note]
要保留的 Microsoft 小組或小組通道 Wiki 內容 （如果您保留上放置團隊的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。如果小組網站上保留，將啟動到期保留內容 wiki （英文）。不過，如果小組網站會保留與 Wiki 內容已遭刪除之前 2017 年 6 月 22 Wiki 內容已不會保留。
   