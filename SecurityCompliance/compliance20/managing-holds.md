---
title: 管理保留在 [進階電子文件 （預覽）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fe6ab3a1e1108e9ab2e4fc201357b72a77453d38
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240948"
---
# <a name="manage-holds-in-advanced-ediscovery-preview"></a>管理保留在 [進階電子文件 （預覽）

您可以使用進階電子文件 （預覽） 案例來建立保留來保留可能與您的案例相關的內容。 使用進階電子文件 （預覽） 保留功能，您可以將保留 custodians 和其資料來源上。 此外，您可以保留非 custodial 信箱和 OneDrive for Business 網站。 您也可以將保留在群組信箱、 SharePoint 網站與 OneDrive for Business 網站的 Office 365 群組。 同樣地，您可以保留的信箱和 Microsoft Teams 相關聯的網站。 當您將保留內容的位置時，直到您放開 custodian、 移除特定資料的位置，或完全刪除保留原則，會保留內容。

## <a name="manage-custodian-based-holds"></a>管理 custodian 型保留

在某些情況下，您可能會有一組資料 custodians 您識別並選擇来保留。 在 [進階電子文件 （預覽），當這些 custodians 會處於暫止狀態，使用者和其選取的資料來源會自動新增至 custodian 保留原則。 

若要檢視 custodian 保留原則：

1. 在**安全性 & 合規性中心**中，按一下 [ **eDiscovery > 進階電子文件 （預覽）** 來顯示貴組織中的案例清單。
   
2. 移至要新增您的案例內的 custodians **Custodians** ] 索引標籤。 若要了解如何新增及 custodians 置於進階電子文件 （預覽） 案例內的保留，請參閱[進階電子文件 （預覽） 來新增 Custodians 案例](add-custodians-to-case.md)。 如果您已經加入 custodians 且處於保留狀態，請移至步驟 3。
   
3. 移至 [**保留**] 索引標籤，然後選取 [Custodian 原則。
   
4. 在彈出式頁面中，您可以看到保留原則的統計資料。 您也可以執行動作，例如將查詢套用至您 custodian 型保留。 如需有關建立保留查詢和使用條件的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](../keyword-queries-and-search-conditions.md)。
 
## <a name="manage-non-custodial-holds"></a>管理非 custodial 保留

當您建立保留時，您會有範圍的內容，會保留在指定的內容位置中的下列選項：

  - 您建立其中所有內容都會都被保留無限期保留。 或者，您可以建立查詢式的保留保留放置只有符合搜尋查詢的內容。
  - 您可以指定日期範圍，以保留，已傳送、 接收或建立該日期範圍內的內容。 或者，您可以保留不論當它已傳送、 接收或建立的所有內容。

若要建立進階電子文件 （預覽） 案例保留：

1. 在**安全性 & 合規性中心**中，按一下 [ **eDiscovery > 進階電子文件 （預覽）** 來顯示貴組織中的案例清單。
  
2. 您想要建立保留的案例旁邊，按一下 [**開啟**]。
  
3. 從案例的首頁] 頁面上，按一下 [**保留**] 索引標籤。
  
4. 在 [**保留**] 索引標籤上按一下 [**建立**]。
  
5. 在 [**命名您保留**] 頁面中，為保留命名。 保留名稱必須是您組織中唯一的。
 
6. （選用）在 [**描述**] 方塊中，新增保留的描述。
  
7. 按 [下一步]****。
  
8. 選擇 [內容位置，您想要就地保留。 您可以在保留上放置信箱、 網站及公用資料夾。

   a. **Exchange 電子郵件**-按一下 [**選擇使用者、 群組或小組**，然後按一下 [**選擇使用者、 群組或小組**再次指定信箱置於保留。 使用 [搜尋] 方塊來尋找要就地保留的使用者信箱和通訊群組 （來保留群組成員的信箱）。 您可以也保留相關聯的信箱上的 Office 365 群組或 Microsoft 小組。 選取使用者、 群組、 小組] 核取方塊，按一下 [**選擇**，然後按一下 [**完成**。
 
    > [!NOTE]
    > 當您按一下 **[選擇使用者、 群組或小組**來指定要就地保留的信箱時，會顯示信箱選擇器是空的。 這項設計的目的是提升效能。 若要將人員新增至這份清單中，輸入的名稱 （3 個字元的最少） 在 [搜尋] 方塊中。

    b. **SharePoint 網站**-按一下 [**選擇網站**]，然後按一下 [**選擇網站**再次指定 SharePoint 和 OneDrive for Business 網站置於保留。 輸入您想要就地保留每個網站的 URL。 您也可以新增 SharePoint 網站的 URL 的 Office 365 群組或 Microsoft 小組。 按一下 [**選擇**，然後按一下 [**完成**。
    
     請參閱 < 的祕訣放入保留的 Office 365 群組和 Microsoft Teams<b0>常見問題集</b0>> 一節。

    > [!NOTE]
    > 人員的使用者主要名稱 (UPN) 已變更的少數情況下，其 OneDrive 帳戶的 URL 也會變更以納入新的 UPN。 如果發生這種情況，您必須新增使用者的新 OneDrive URL，並移除舊來修改保留。

     c. **Exchange 公用資料夾**移動開關切換到 [所有位置將放在 Exchange Online 組織中的所有公用資料夾上保留。 請注意，您無法選擇特定公用資料夾移轉至置於保留。 將保留設定為**None** ，如果您不想要的公用資料夾上設定保留功能變數的切換參數。

9. 當您完成新增至保留的內容位置時，按一下 [**下一步**]。
  
10. 若要建立查詢式保留與條件，完成下列設定。 否則，只要按一下 [**下一步**。
    
    - 在 [**關鍵字**] 方塊中類型] 方塊中的搜尋查詢，以便符合搜尋準則的內容會置於保留。 您可以指定關鍵字，郵件內容或文件屬性，例如檔案名稱。 您也可以使用更複雜的查詢，或不使用布林運算子，例如 AND、 OR。 如果您讓 [關鍵字] 方塊空白，則位於指定的內容位置中的所有內容將會都放在保留。

    - 按一下 [**新增**條件，用來新增一或多個條件來縮小搜尋查詢的 [保留]。 每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您建立保留。 例如您可以指定日期範圍，以便電子郵件或站台內遠距的日期所建立的文件會處於暫止狀態。 條件會以 AND 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 保留，表示項目必須滿足的關鍵字查詢和要放在條件。

     如需有關建立搜尋查詢和使用條件的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions)。

12. 設定查詢為基礎之後保留，請按一下 [**下一步**。
 
13. 檢閱設定，然後再按一下 [**建立此保留**。


## <a name="view-hold-statistics"></a>檢視保留統計資料

一些時間之後, 會選取保留的**保留**索引標籤的詳細資料窗格中顯示新保留相關資訊。 此資訊包括的信箱數目站台上的按住並保留已處於內容相關的統計資料，例如總數和大小的項目處於保留狀態，而且上一次的保留所計算的統計資料。 這些保留統計值能協助您識別舉行多少的 eDiscovery 案例相關的內容。

請謹記下列事項需要注意的保留統計資料：

- 保留的項目數總計會指出從會處於保留狀態的所有內容來源的項目數。 如果您已建立查詢式保留功能，這項統計資料會指出符合查詢的項目數。
  
- 保留的項目數也包含的內容位置中找到的未編製索引項目。 請注意，是否您建立查詢式保留時，內容位置中所有未編製索引的項目會處於保留狀態。 這包括未編製索引的項目不符合搜尋準則的查詢式保留和未編製索引的項目可能以外的日期範圍條件。 這是不同於執行內容搜尋] 中，其中不符合搜尋查詢或日期範圍條件會排除的未編製索引項目不包含在搜尋結果時，會發生什麼事。 如需未編製索引的項目的詳細資訊，請參閱 <<c0>已局部編製索引中 Office 365 中的內容搜尋的項目。 

- 您可以取得最新的保留統計資料]，即可更新統計資料，重新執行搜尋估計值，會計算目前的保留的項目數目。

- 若有必要，請按一下 [重新整理，在工具列中，以更新詳細資料窗格中的保留統計資料。

- 若要增加一段時間，因為使用者其信箱或網站是保留通常會傳送或接收新的電子郵件訊息及建立新的 SharePoint 和 OneDrive for Business 文件保留它的內文中的項目數目。

- 如果 SharePoint 網站或 OneDrive 帳戶移至不同的區域，在多地理位置環境中，將不會保留統計資料中包含該網站的統計資料。 不過，在 [網站內容仍是保留。 此外，如果網站移至不同的區域不會更新顯示在保留中的 URL。 您必須編輯保留並更新 URL。

## <a name="frequently-asked-questions"></a>常見問題集

- **如何將其他的 Office 365 群組或 Microsoft Teams 網站對應到 custodian？和在 Office 365 群組和 Microsoft Teams 怎麼約放置 [非-Custodial 保留嗎？** Microsoft Teams 之內建 Office 365 群組。 因此，將它們放入保留電子文件探索案例中是非常類似。 將 Office 365 群組和 Microsoft Teams 上保留時，請保持記住下列事項。
  - 若要將保留位於 Office 365 群組和 Microsoft Teams 的內容，您必須指定信箱和 SharePoint 網站的群組或小組與相關聯。
  
  - 執行**Get UnifiedGroup**指令程式在 Exchange Online 中檢視 Office 365 群組或 Microsoft 小組的內容。 這是一個好方法來取得有相關聯的 Office 365 群組或 Microsoft 小組網站的 URL。 例如，下列指令會選取的內容顯示名為資深領導團隊的 Office 365 群組：


    ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要執行 Get UnifiedGroup 指令程式，您必須獲指派 「 僅檢視收件者角色在 Exchange Online 或是角色群組的成員，才會有指派 「 僅檢視收件者 」 角色。

 - 當使用者的信箱被搜尋時，將不會搜尋任何 Office 365 群組或使用者是屬於 Microsoft 小組。 同樣地，當您將 Office 365 群組或 Microsoft 小組保留，只有群組信箱和群組網站置於保留;OneDrive for Business 網站的群組成員與信箱未處於暫止狀態除非您明確將其新增為 custodians，或將其資料來源保留。 因此，如果您將 Office 365 群組或 Microsoft 小組需要保留的特定 custodian，請考慮將群組信箱與群組網站對應到 custodian (請參閱 Managing Custodians 在進階電子文件 （預覽）)。 如果 Office 365 群組或 Microsoft 小組不是單一 custodian 究，請考慮新增至非-custodial 來源保留。 
 
 - 若要取得的 Office 365 群組或 Microsoft 小組成員的清單，您可以在 Office 365 系統管理中心 [家庭 > 群組] 頁面上檢視的內容。 或者，您可以在 Exchange Online PowerShell 中執行下列命令：

   ``` 
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > 若要執行**Get UnifiedGroupLinks**指令程式，您必須獲指派 「 僅檢視收件者角色在 Exchange Online 或是角色群組的成員，才會有指派 「 僅檢視收件者 」 角色。

- 屬於 Microsoft Teams 通道的通道交談儲存在小組與相關聯的信箱。 同樣地，小組成員共用通道中的檔案會儲存在小組的 SharePoint 網站上。 因此，您必須將 Microsoft 小組信箱和 SharePoint 網站上的保留來保留通話，並在通道中的檔案。
  
- 或者，屬於 Microsoft Teams 中的聊天室清單的交談會儲存在使用者的信箱的使用者參與聊天。  聊天交談中的使用者與共用的檔案會儲存在商務用 OneDrive 網站共用檔案的使用者。 因此，您必須將個別使用者信箱和商務用 OneDrive 網站上保留來保留通話，並在 [聊天室] 清單中的檔案。 
  
- 每個 Microsoft Team 或小組通道包含 Wiki 筆記記錄及共同作業。 Wiki 內容會自動儲存至含有.mht 格式的檔案。 此檔案會儲存在小組的 SharePoint 網站上的 microsoft Teams Wiki 資料文件庫。 您可以將小組的 SharePoint 網站置於保留狀態，保留 Wiki 中放置內容。

  > [!NOTE]
  > 若要保留的 Microsoft Team 或小組通道的 Wiki 內容 （當您將保留小組的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。 如果小組網站上保留，內容會保留在該日期開始在 Wiki。 不過，如果被保留的小組網站和 Wiki 內容已刪除之前 2017 年 6 月 22 日，已不會保留 Wiki 內容。
