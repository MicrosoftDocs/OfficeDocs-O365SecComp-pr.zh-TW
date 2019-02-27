---
title: 搜尋 Office 365 中的雲端架構信箱的內部使用者
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用 Office 365 安全性內容搜尋工具&amp;規範中心來搜尋並匯出 MicrosoftTeams 聊天室資料 （稱為 1xN 聊天） Exchange 混合部署中的內部部署使用者。
ms.openlocfilehash: 148a5766342fcdd52e0505a59729cad3d2993908
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296696"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>搜尋 Office 365 中的雲端架構信箱的內部使用者

如果您的組織具有 Exchange 混合部署並已啟用的 Microsoft 小組，使用者可以使用小組聊天應用程式的立即訊息。雲端使用者的 （也稱為 1xN 聊天） 小組聊天室資料會儲存到其主要的雲端架構信箱。內部使用者使用時的小組聊天應用程式，其主要信箱是位於內部部署。若要解決此限制，Microsoft 已經發行雲端儲存區域 （稱為雲端架構信箱的內部使用者） 儲存內部使用者的小組聊天室資料以建立所在的新功能。這可讓您使用 Office 365 安全性內容搜尋工具&amp;規範中心來搜尋並匯出小組內部使用者的聊天室資料。 
  
以下是需求和限制的設定和設定及搜尋雲端架構信箱的內部部署使用者：
  
- 您在內部部署目錄服務 （如 Active Directory) 中的使用者帳戶必須具有 Azure Active Directory、 Office 365 的目錄服務同步處理。這表示郵件使用者帳戶會在 Office 365 中建立且其主要信箱位於內部部署組織中的使用者相關聯。
    
- 雲端架構信箱的內部部署使用者是使用唯一的存放區小組聊天室資料。內部部署使用者無法登入雲端架構信箱或以任何方法存取。無法用來傳送或接收電子郵件訊息。 
    
- 您必須要求提交至 Microsoft 技術支援人員以啟用搜尋小組聊天室資料在雲端架構信箱的內部使用者的組織。請參閱[歸檔 Microsoft 技術支援人員以啟用此功能安全性要求&amp;規範中心](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center)本文中。 
    
 **附註：** 小組通道交談永遠儲存在雲端架構信箱與小組相關聯。這表示您可以使用搜尋通道交談而不具有檔案的支援要求內容搜尋。如需關於搜尋小組通道交談，請參閱[搜尋的 Microsoft 小組與 Office 365 群組](content-search.md#searching-microsoft-teams-and-office-365-groups)。
  
## <a name="how-it-works"></a>運作方式

如果 Microsoft 小組啟用使用者的內部部署信箱，且其使用者帳戶/身分識別具有已同步至雲端，Microsoft 建立雲端架構信箱儲存 1xN 小組聊天室資料。小組聊天室資料會儲存在雲端架構信箱之後，它已編製索引的搜尋。這可讓您使用內容搜尋 （和 eDiscovery 案例相關聯的搜尋） 搜尋、 預覽，並將內部部署使用者的小組聊天室資料匯出。您也可以使用**\*ComplianceSearch**指令程式在 Office 365 安全性&amp;規範中心 PowerShell 搜尋團隊與內部使用者的聊天室資料。 
  
下圖顯示的工作流程的方式小組聊天室的內部使用者的資料可供搜尋、 預覽，並匯出。
  
![雲端中的 Microsoft 小組的內部部署使用者儲存區](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
除了此新功能，仍然可用內容搜尋來搜尋、 預覽，並匯出的小組雲端型 SharePoint 網站] 及 [Exchange 信箱中的內容相關聯每一個 Microsoft 小組及 1xN 小組 Exchange Online 信箱的聊天室資料雲端式的使用者。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a>歸檔 Microsoft 技術支援人員以啟用此功能安全性要求&amp;規範中心

您必須檔案要求 Microsoft 技術支援人員以啟用您的組織来使用圖形使用者介面在安全性&amp;規範中心搜尋小組聊天室資料在雲端架構信箱的內部部署使用者。請注意這項功能可在 Office 365 安全性&amp;規範中心 PowerShell。您不需要支援要求提交至 PowerShell 用於搜尋的內部部署使用者的小組聊天室資料。 
  
當您要求提交至 Microsoft 支援包括下列資訊：
  
- Office 365 組織的預設網域名稱。
    
- 租用戶名稱和 Office 365 組織租用戶識別碼。您可以找到這些 Azure Active Directory 入口網站 (在 [**管理**下\>**屬性**)。請參閱[尋找 Office 365 租用戶識別碼](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。
    
- 下列的標題或支援要求的用途的描述： [啟用應用程式的內部部署使用者內容搜尋]。這有助於路由要求傳送到 Office 365 eDiscovery 工程小組人員實作要求。 
    
工程變更後，Microsoft 技術支援人員會傳送給您評估的部署的日期。部署程序通常採用 2-3 週後支援將要求送出的附註。 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>在啟用此功能之後會發生什麼事？

這項功能在 Office 365 組織中部署之後，下列變更進行中內容搜尋並在搜尋相關聯的 eDiscovery 案例中安全性&amp;規範中心：
  
- 在內容搜尋**位置**] 下新增**內部部署使用者的新增 Office 應用程式內容**] 核取方塊。 
    
    ![「 新增內部部署使用者的 Office 應用程式內容 」] 核取方塊新增至內容搜尋使用者介面](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- 內部使用者會顯示在使用中選取要搜尋的使用者信箱的內容位置選擇器。 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>搜尋團隊在雲端架構信箱的內部部署使用者內容的聊天室

已啟用功能之後，您可以使用內容的搜尋安全性&amp;規範中心搜尋小組聊天室資料在雲端架構信箱的內部部署使用者。 
  
1. 安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **內容搜尋**
    
2. 在 [**搜尋**] 頁面上，按一下 [![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜尋**。
    
    如先前所述**的內部使用者的新增 Office 應用程式內容**] 核取方塊會顯示 [**位置**] 下。請注意則預設會選取。
    
3. 建立關鍵字查詢及必要時新增至搜尋查詢的條件。僅針對小組搜尋聊天室資料，您可以在 [**關鍵字**] 方塊中新增下列查詢： 
    
    ```
    kind:im
    ``` 

4. 此時，您可以選擇其中一個 [**位置**] 下的下列選項：
    
    - **所有位置**-選取這個選項可在組織中搜尋之所有使用者的信箱。選取核取方塊時，也可搜尋的內部部署使用者的所有雲端架構信箱。 
    
    - **特定位置**-選取這個選項，然後按一下 [**修改**\>選擇使用者、 群組或小組來搜尋特定的信箱。如先前所述位置選擇將可讓您搜尋內部部署使用者。 
    
5. 儲存並執行搜尋。從雲端架構信箱的內部使用者的任何搜尋結果可以預覽像任何其他搜尋結果。此外，您可以您可以將 （包括小組聊天室的任何資料） 的搜尋結果匯出至 PST 檔案。如需詳細資訊，請參閱： 
    
    - [建立新的搜尋](content-search.md#create-a-new-search)
    
    - [預覽搜尋結果](content-search.md#preview-search-results)
    
    - [從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>使用 PowerShell 搜尋小組聊天室資料在雲端架構信箱的內部使用者

您可以使用**New ComplianceSearch**和**設定 ComplianceSearch** cmdlet Office 365 安全性&amp;規範中心 PowerShell 搜尋內部部署使用者的雲端架構信箱。如先前所述，您不需要支援要求提交至 PowerShell 用於搜尋的內部部署使用者的小組聊天室資料。 
  
1. [連線至 Office 365 安全性&amp;規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
    
2. 執行下列 PowerShell 命令來建立新的內容會搜尋雲端架構信箱的內部部署使用者。
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    *IncludeUserAppContent*參數用來指定雲端架構信箱的使用者或*ExchangeLocation*參數所指定的使用者。*AllowNotFoundExchangeLocationsEnabled*可讓內部使用者的雲端架構信箱。當您使用`$true`此參數，搜尋的值不會嘗試執行之前，先驗證信箱是否存在。這是因為這些類型的信箱不解決與一般信箱搜尋雲端架構信箱的內部部署使用者所需。 
    
    下列範例會搜尋小組的聊天室 （亦即立即訊息） 包含關鍵字"redstone"中的雲端架構信箱的 Sara Davis 身為內部部署組織中的使用者 Contoso。
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   建立新的搜尋之後，請務必使用**開始 ComplianceSearch**指令程式執行搜尋。 
  
使用這些 cmdlet 的詳細資訊，請參閱：
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>已知問題

- 目前，您可以僅搜尋、 預覽並在雲端架構信箱的內容匯出內部部署使用者。將內部部署使用者雲端架構信箱設定保留相關聯的 eDiscovery 案件或將它指派給 Office 365 保留原則不支援。 
    
- EDiscovery 內容位置選擇包含顯示內部使用者，將可讓您選取其。不過，之前清楚保留不會套用至內部部署使用者。
    
## <a name="frequently-asked-questions"></a>常見問題集

 **在雲端架構信箱的內部部署使用者的位置？**
  
建立和儲存在相同的資料中心 Office 365 組織中的雲端架構信箱。 
  
 **是否有不支援要求送出任何其他需求吗？**
  
 如先前所述，具有 prem 上信箱的使用者的身分識別必須同步處理至雲端架構組織，讓每個內部部署使用者帳戶在 Office 365 中建立對應的郵件使用者帳戶。此外，您的組織必須具備的 Office 365 企業版訂閱，例如 Office 365 企業版 E1、 E3 或 E5 訂閱。 
  
 **是否有遺失小組聊天室資料如果使用者的內部部署信箱移轉至雲端的風險吗？**
  
[否]。當您將主要信箱的內部部署使用者移轉至雲端時，該使用者的小組聊天室資料將移轉至新雲端架構主要信箱。
  
 **我可以將套用 eDiscovery 保留或 Office 365 的保留原則對內部部署使用者吗？**
  
否。
  
 **內容搜尋尋找舊小組聊天室的內部部署使用者的時間之前我的組織可以送出將要求重新啟用此功能吗？**
  
Microsoft 啟動的內部部署使用者的小組聊天室資料儲存在 2018 年 1 月 31、。如此，如果此日期自，已 Active Directory 與 Azure Active Directory 之間同步的內部部署小組使用者身分識別，然後自己小組聊天室的資料會儲存在雲端架構信箱和可供搜尋使用內容搜尋。Microsoft 也儲存在雲端架構信箱的內部部署使用者中的小組聊天室的資料前 2018 年 1 月 31、 運作。更多有關此資訊會是推出。
