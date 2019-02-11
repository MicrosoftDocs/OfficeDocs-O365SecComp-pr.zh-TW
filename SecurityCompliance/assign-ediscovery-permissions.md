---
title: Office 365 安全性 eDiscovery 權限指派&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 指派權限才能執行 eDiscovery 相關的工作使用安全性&amp;規範中心。
ms.openlocfilehash: 95f0ed171c37ec84ca8bb8f00e69ab0318cd31cd
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29741156"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a>Office 365 安全性 eDiscovery 權限指派&amp;規範中心

如果您想使用 eDiscovery 相關任何的工具 Office 365 安全性人員&amp;規範中心，您必須將它們指派適當的權限。為達成此目的最簡單的方法是在 Office 365 安全性**權限**] 頁面上新增適當的角色群組的人員&amp;規範中心。本主題說明執行 eDiscovery 相關之工作使用安全性所需的權限&amp;規範中心。 
  
主要 eDiscovery 相關的角色群組安全性&amp;規範中心會呼叫**eDiscovery 管理員**。有兩個子群組內此角色群組。 
  
- **eDiscovery 經理**-eDiscovery 管理員可以使用 「 內容搜尋工具安全性&amp;規範中心來執行各種與搜尋相關動作，例如預覽與匯出搜尋及搜尋組織中的內容位置結果。成員也可以建立與管理 eDiscovery 案例、 新增和移除成員案例、 建立 case 保留及執行內容與案例中為及存取 Office 365 進階 ediscovery case 資料相關聯的搜尋。 EDiscovery 管理員，才能存取及管理他們所建立的案例。他們無法存取或管理其他 eDiscovery 管理員所建立的案例。 
    
- **eDiscovery 管理員**-eDiscovery 管理員 eDiscovery 管理員角色群組的成員，且可以執行相同的內容搜尋與 eDiscovery 管理員可執行區分管理相關的工作。此外，eDiscovery 管理員可以： 
    
  - 存取已列在 [安全性] 中的**eDiscovery 案例**] 頁面上的所有案例&amp;規範中心。 

  - 存取 case 進階 eDiscovery 針對在組織中任何案例中的資料。
    
  - 在自行新增為案例的成員之後管理任何 eDiscovery 案例。
  
  請參閱您可能會想 eDiscovery 管理員在組織中原因[的詳細資訊](#more-information)] 區段中。 

> [!NOTE]
> 若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。  
  
## <a name="before-you-begin"></a>開始之前

- 您必須是 「 組織管理角色群組的成員 （或要指派的角色管理角色） 指派 eDiscovery 權限安全性&amp;規範中心。
    
- 您可以使用[Add-rolegroupmember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx)指令程式的安全性&amp;規範中心 PowerShell 將擁有郵件功能的安全性群組新增為 eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組的成員。不過，您無法將擁有郵件功能的安全性群組新增至 eDiscovery 管理員子群組。請參閱如需詳細資訊[的詳細資訊](#more-information)] 區段。 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a>在 [安全性] 中的 eDiscovery 權限指派&amp;規範中心

1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在 [安全性] 的左窗格中&amp;規範中心按一下**權限**，然後再按一下 [ **eDiscovery 管理員**] 旁的核取方塊。
    
4. 在 [ **eDiscovery 管理員**彈出式] 頁面上執行根據想要指定 eDiscovery 權限的下列其中之一。 
    
  - **若要讓使用者 eDiscovery 管理員****EDiscovery 管理員**] 旁按一下 [**編輯**]。[**選定 eDiscovery 管理員**，按一下 [**編輯**] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增]**。選取的使用者 （或使用者） 您要新增為 eDiscovery 管理員] 中，然後按一下 [**新增]**。新增使用者完成後，按一下 [**完成**]。然後，在 [**編輯選擇 eDiscovery 管理員**彈出式] 頁面上按一下 [**儲存**] 以將變更儲存至 eDiscovery 管理員成員資格。 
    
  - **若要讓使用者 eDiscovery 管理員****EDiscovery 管理員**] 旁按一下 [**編輯**]。[**選定 eDiscovery 管理員**，按一下 [**編輯**] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增]**。選取的使用者 （或使用者） 您要新增為 eDiscovery 管理員，然後按一下 [**新增]**。新增使用者完成後，按一下 [**完成**]。然後，在 [**編輯選擇 eDiscovery 管理員**彈出式] 頁面上按一下 [**儲存**] 以將變更儲存至 eDiscovery 管理員的成員資格。 
    
> [!NOTE]
> 您也可以使用**Add eDiscoveryCaseAdmin**指令程式，讓使用者 eDiscovery 管理員。不過，使用者必須具有案例管理角色才可以使用此指令程式，使其 eDiscovery 管理員。如需詳細資訊，請參閱 ＜ [Add eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217)。 
  
在 [安全性]**權限**] 頁面上&amp;規範中心，您也可以指派使用者 eDiscovery 相關的權限透過將它們新增至 [規範管理員、 組織管理及檢閱者 」 角色群組。EDiscovery 與相關 RBAC 角色指派給每個這些角色群組的說明，請參閱[RBAC 角色與 eDiscovery 相關](#rbac-roles-related-to-ediscovery)] 區段中。 

## <a name="rbac-roles-related-to-ediscovery"></a>EDiscovery 與相關的 RBAC 角色

下表列出 eDiscovery 相關的 RBAC 角色的安全性 & 規範中心並指出每個角色指派給預設的內建角色群組。 
    
|**角色**|**規範系統管理員**|**eDiscovery 管理員 & 管理員**|**組織管理**|**檢閱者**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|管理 （英文） <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|合規性搜尋 <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|匯出 <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|保留 <br/>  |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|預覽 <br/>  | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|檢閱  <br/>  | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|RMS 解密 <br/>  ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|搜尋和清除 <br/> | <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
下列各節說明上表中所列的 eDiscovery 相關 RBAC 角色。

### <a name="case-management"></a>管理 （英文）

此角色可讓使用者建立、 編輯、 刪除及控制安全性 & 規範中心中的 eDiscovery 案例的存取。如需詳細資訊，請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](manage-ediscovery-cases.md)。如先前所述，使用者必須具有案例管理角色才可以使用**Add eDiscoveryCaseAdmin**指令程式，使其 eDiscovery 管理員。 

### <a name="compliance-search"></a>合規性搜尋

此角色可讓使用者在安全性 & 規範中心來搜尋信箱與公用資料夾、 SharePoint Online 網站、 OneDrive for Business 網站 Skype for Business 交談、 Office 365 群組及 Microsoft 小組執行內容搜尋工具。此角色可讓使用者取得搜尋結果的評估並建立匯出報告，但其他角色不需要修改初始化內容搜尋動作，例如預覽、 匯出或刪除搜尋結果。

請注意使用者指派規範搜尋角色但不需要預覽角色可預覽其預覽巨集指令具有起始由使用者指派角色預覽搜尋結果。沒有預覽角色的使用者可以預覽最多 2 週的初始預覽巨集指令建立後的結果。

同樣地，指派給使用者的規範搜尋角色，但沒有角色可以下載中的匯出巨集指令具有由已指派 「 匯出 」 角色的使用者起始的搜尋結果匯出。沒有匯出角色的使用者可以下載最多 2 週後的初始匯出巨集指令建立的搜尋結果。之後，他們將無法除非某人匯出角色與重新啟動匯出下載結果。

如需詳細資訊，請參閱[Office 365 中的內容搜尋](content-search.md)。 

### <a name="export"></a>匯出

角色可讓使用者將內容的搜尋結果匯出至本機電腦。它也可讓其準備分析進階在 eDiscovery 中搜尋結果。 

如需匯出搜尋結果的詳細資訊，請參閱[Office 365 安全性 & 規範中心的搜尋結果匯出](export-search-results.md)。

### <a name="hold"></a>保留

此角色可讓使用者將內容放入信箱、 公用資料夾、 網站、 商務交談的 Skype 按住上的 Office 365 群組。保留內容時，內容擁有者將仍能修改或刪除原始的內容，但會保留內容，直到撤除或保留期間到期。 

如需保留的詳細資訊，請參閱：

- [在 Office 365 安全性 & 規範中心中的 eDiscovery 案例](ediscovery-cases.md) 
- [保留原則概觀](retention-policies.md)

### <a name="preview"></a>預覽

此角色可讓使用者檢視內容的搜尋所傳回的項目清單。他們也必須能夠開啟並檢視來檢視其內容清單中的每個項目。

### <a name="review"></a>檢閱 

此角色可讓使用者存取 Office 365 進階 ediscovery 案件資料。此角色的主要目的是讓使用者能夠存取進階 eDiscovery。會指定給此角色的使用者可以看到並開啟安全性 & 他們是成員的規範中心 [eDiscovery] 頁面上的情況下的清單。使用者存取的安全性 & 規範中心的案例之後，他們可以按一下 [**進階 ediscovery 參數**來存取及分析中進階 eDiscovery 案例的資料。此角色不允許使用者預覽與案例相關聯之內容搜尋的結果或執行其他內容搜尋或案例的管理工作。

### <a name="rms-decrypt"></a>RMS 解密

此角色可讓使用者解密 RMS 加密電子郵件訊息時匯出進階在 eDiscovery 中搜尋結果或準備進行分析的搜尋結果。如需關於解密在匯出期間的搜尋結果，請參閱[Office 365 安全性 & 規範中心的搜尋結果匯出](export-search-results.md)。

### <a name="search-and-purge"></a>搜尋和清除

此角色可讓使用者執行大量移除相符的內容的搜尋準則的資料。如需詳細資訊，請參閱[Search for 和 Office 365 組織中的刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。 


## <a name="more-information"></a>詳細資訊

- **為什麼要選擇建立 [eDiscovery 管理員？** 如先前清楚，系統管理員是可以檢視及存取您組織中所有的 eDiscovery 案例 eDiscovery 管理員角色群組的成員 eDiscovery。這項功能來存取所有的 eDiscovery 案例有兩個重要的用途： 
    
  - 如果 eDiscovery 案例的唯一成員的人員離開貴組織，因為他們未成員任何人 （包括組織管理角色群組的成員或另一個 eDiscovery 管理員角色群組的成員） 是可存取該 eDiscovery 案例案例。在此情況下，就會有任何方法，以存取案例中的資料。但 eDiscovery 管理員可以存取所有在組織中的 eDiscovery 案例，因為他們可以檢視案例安全性&amp;規範中心並將其本身或另一個 eDiscovery 管理員新增為大小寫的成員。
    
  - EDiscovery 系統管理員可以檢視及存取所有的 eDiscovery 案例，因為他們可以稽核和監督所有案例和相關聯規範搜尋。這有助於防止任何誤用規範搜尋或 eDiscovery 案例。與因為 eDiscovery 系統管理員可以存取規範搜尋結果中的潛在敏感資訊，您應該限制的 eDiscovery 管理員的使用者數目。
    
    此外，eDiscovery 安全性管理員&amp;規範中心會自動新增為進階 ediscovery 的管理員。這表示人員必須 eDiscovery 管理員，才可執行進階的 eDiscovery、 使用者設定、 建立的情況下，以及將資料匯入案例的管理工作。
    
- **可以新增群組安全性 eDiscovery 管理員角色群組的成員身分&amp;規範中心吗？** 如先前清楚，您可以使用**Add-rolegroupmember**指令程式的安全性 eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組的成員身分新增擁有郵件功能的安全性群組&amp;規範中心 PowerShell。例如，您可以執行下列命令以將擁有郵件功能的安全性群組新增至 eDiscovery 管理員角色群組。 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    請注意 Exchange 通訊群組或 Office 365 群組不受支援。您必須使用擁有郵件功能的安全群組，其中您可以在 Exchange Online PowerShell 中使用建立` New-DistributionGroup -Type Security `命令。您也可以建立擁有郵件功能的安全性群組 （及新增成員） Exchange 系統管理中心或 Office 365 系統管理中心中。請注意可能需要最多 60 分鐘後您建立的新擁有郵件功能的安全性設為可用來新增至 eDiscovery 管理員角色群組。 
    
    也為先前所述，您不能進行擁有郵件功能的安全性 eDiscovery 管理員群組**新增 eDiscoveryCaseAdmin**指令程式使用安全性&amp;規範中心 PowerShell。您只可以將個別使用者新增為 eDiscovery 管理員。 
    
    請注意也無法新增具有郵件功能的安全性群組為大小寫的成員。
