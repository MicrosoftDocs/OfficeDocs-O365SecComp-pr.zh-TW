---
title: 指派安全性 & 合規性中心中的 eDiscovery 權限
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 指派執行使用安全性 & 合規性中心的 eDiscovery 相關工作所需的權限。
ms.openlocfilehash: 5a9036908d97a62897b7d52b875a46008a7a337c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152175"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>指派安全性 & 合規性中心中的 eDiscovery 權限

如果您想使用的 eDiscovery 相關任何的工具安全性 & 在 Office 365 規範中心中的人員，您必須將它們指派適當的權限。 若要這麼做最簡單的方法是安全性 & 合規性中心中的**權限**] 頁面上新增適當的角色群組的人員。 本主題說明執行 eDiscovery 所需的權限-和使用安全性 & 合規性中心的內容搜尋相關工作。 
  
主要 eDiscovery 相關的角色群組中的安全性 & 合規性中心稱為**eDiscovery 管理員**。 有兩個的子群組內這個角色群組。 
  
- **eDiscovery 管理員**-eDiscovery 管理員可以使用 「 內容搜尋 」 工具安全性 & 合規性中心中搜尋內容位置在組織中，執行各種與搜尋相關的動作，例如預覽和匯出搜尋結果。 成員也可以建立及管理 eDiscovery 案例、 新增及移除案例成員、 建立案件保留，及執行與案例中，並存取 Office 365 進階電子文件探索中的案例資料相關聯的內容搜尋。  EDiscovery 管理員，才能存取及管理他們所建立的情況。 無法存取或管理其他 eDiscovery 管理員所建立的案例。 
    
- **eDiscovery 系統管理員**-eDiscovery 系統管理員是 eDiscovery 管理員角色群組的成員，並可以執行相同的內容搜尋和 eDiscovery 管理員可執行區分大小管理相關的工作。 此外，eDiscovery 系統管理員可以： 
    
  - 存取安全性 & 合規性中心**eDiscovery 案例**] 頁面列出的所有案例。 

  - 存取組織中任何案例的進階電子文件中的案例資料。
    
  - 在自行新增為案例的成員之後管理任何 eDiscovery 案例。
  
  請參閱您可能想 eDiscovery 系統管理員在組織中原因的[詳細資訊](#more-information)一節。 

> [!NOTE]
> 若要分析使用進階電子文件的使用者資料，使用者 (資料的 custodian) 必須被指派 Office 365 E5 授權。 或者，使用 Office 365 E1 或 E3 授權的使用者可被指派的進階電子文件獨立授權。 系統管理員和法務人員對於已指派給的情況下，並使用進階電子文件探索分析資料不需要 E5 授權。  
  
## <a name="before-you-begin"></a>開始之前

- 您必須是 「 組織管理 」 角色群組的成員 （或獲指派 「 角色管理角色） 來指派安全性 & 合規性中心中的 eDiscovery 權限。
    
- 您可以使用[Add-rolegroupmember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx)指令程式的安全性 & 合規性中心 PowerShell 中，將擁有郵件功能的安全性群組新增為 eDiscovery 管理員子群組，在 [eDiscovery 管理員角色群組的成員。 不過，您無法將擁有郵件功能的安全性群組新增至 eDiscovery 管理員子群組。 請參閱如需詳細資訊的[詳細資訊](#more-information)一節。 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>指派安全性 & 合規性中心中的 eDiscovery 權限

1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在安全性與合規性中心的左窗格中，按一下 [**權限**，，然後按一下 [ **eDiscovery 管理員**] 旁的核取方塊。
    
4. 在**eDiscovery 管理員**彈出式頁面上，執行下列其中一個下列根據您想要指派 eDiscovery 權限。 
    
  - **若要讓使用者成為 eDiscovery 管理員****EDiscovery 管理員**]，旁邊按一下 [**編輯**]。 在**選取 eDiscovery 管理員**]，按一下 [**編輯**]，然後按一下![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增**。 選取的使用者 （或使用者） 您要新增為 eDiscovery 管理員] 中，然後按一下 [**新增]**。 當您完成新增使用者後時，按一下 [**完成**]。 然後，在**編輯選擇 eDiscovery 管理員**彈出式頁面上，按一下 [**儲存**] 以儲存 eDiscovery 管理員成員資格的變更。 
    
  - **若要讓使用者成為 eDiscovery 系統管理員****EDiscovery 系統管理員**]，旁邊按一下 [**編輯**]。 在**選取的 eDiscovery 系統管理員**]，按一下 [**編輯**]，然後按一下![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增**。 選取的使用者 （或使用者） 您要新增為 eDiscovery 系統管理員，然後按一下 [**新增]**。 當您完成新增使用者後時，按一下 [**完成**]。 然後，在**編輯選擇 [eDiscovery 系統管理員**彈出式頁面上，按一下 [**儲存**] 以儲存 eDiscovery 系統管理員成員資格的變更。 
    
> [!NOTE]
> 您也可以使用**新增 eDiscoveryCaseAdmin**指令程式，以讓使用者成為 eDiscovery 系統管理員。 不過，使用者必須具有的大小寫管理角色之後才能使用此指令程式，讓它們 eDiscovery 系統管理員。 如需詳細資訊，請參閱 < <b0>Add eDiscoveryCaseAdmin</b0>。 
  
在安全性 & 合規性中心的**權限**] 頁面上，您也可以指派使用者 eDiscovery 相關權限，藉由將它們新增至的符合性系統管理員、 組織管理和檢閱者 」 角色群組。 EDiscovery 相關 RBAC 角色指派給每個角色群組的說明，請參閱[RBAC 角色與 eDiscovery 相關](#rbac-roles-related-to-ediscovery)章節。 

## <a name="rbac-roles-related-to-ediscovery"></a>與 eDiscovery 相關的 RBAC 角色

下表列出安全性 & 合規性中心的 eDiscovery 相關 RBAC 角色，並指出每個角色指派給預設的內建角色群組。 
    
|**Role**|**合規性管理員**|**eDiscovery 管理員 & 系統管理員**|**組織管理**|**檢閱者**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|專案管理 <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|合規性搜尋 <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|匯出 <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|保留 <br/>  |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|預覽 <br/>  | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|檢閱 <br/>  | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|RMS 解密 <br/>  ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|搜尋及清除 <br/> | <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
下列各節說明每一個表格中所列的 eDiscovery 相關 RBAC 角色。

### <a name="case-management"></a>專案管理

此角色可讓使用者建立、 編輯、 刪除及控制安全性 & 合規性中心中的 eDiscovery 案例的存取。 如需詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的管理 eDiscovery 案例。 如先前所述，使用者必須具有大小寫管理角色之前您可以使用**新增 eDiscoveryCaseAdmin**指令程式，讓它們 eDiscovery 系統管理員。 

### <a name="compliance-search"></a>合規性搜尋

此角色可讓使用者在安全性 & 合規性中心來搜尋信箱及公用資料夾、 SharePoint Online 網站、 Skype for Business 對話、 Office 365 群組和 Microsoft Teams 的 OneDrive for Business 網站中執行內容搜尋工具。 此角色可讓使用者取得預估搜尋結果，並建立匯出報告，但其他角色所需啟動等預覽、 匯出或刪除搜尋結果的內容搜尋動作。

附註使用者指派 「 符合性搜尋 」 角色，但沒有 「 預覽 」 角色可以預覽中的預覽巨集指令具有已指派角色預覽使用者所起始的搜尋的結果。 沒有角色預覽使用者可以預覽結果，最多 2 週後的初始預覽巨集指令所建立的。

同樣地，使用者指派 「 符合性搜尋 」 角色，但沒有角色可以下載中的匯出巨集指令具有起始已指派 「 匯出 」 角色的使用者搜尋的結果匯出。 沒有 「 匯出 」 角色的使用者可以下載最多 2 週後的初始匯出巨集指令所建立的搜尋的結果。 之後，他們將無法下載結果，除非具有 「 匯出 」 角色的人員重新啟動匯出。

如需詳細資訊，請參閱 <<c0>在 Office 365 中的內容搜尋。 

### <a name="export"></a>匯出

角色可讓使用者將內容搜尋結果匯出至本機電腦。 它也可讓他們準備進階 eDiscovery 中分析的搜尋結果。 

如需匯出搜尋結果的詳細資訊，請參閱 <<c0>匯出搜尋結果從安全性 &amp; 合規性中心。

### <a name="hold"></a>保留

此角色可讓使用者將內容放在信箱、 公用資料夾、 網站、 Skype for Business 交談，按住不放在 Office 365 群組。 保留內容時，內容的擁有者仍能修改或刪除原始的內容，但會保留內容，直到移除保留，或直到保留期間到期為止。 

如需有關保留的詳細資訊，請參閱：

- [eDiscovery 案例](ediscovery-cases.md) 
- [保留原則概觀](retention-policies.md)

### <a name="preview"></a>預覽

此角色可讓使用者檢視從內容搜尋所傳回的項目清單。 他們將還能夠開啟並檢視清單中要檢視其內容的每個項目。

### <a name="review"></a>檢閱

此角色可讓使用者存取案例在 Office 365 進階電子文件探索中的資料。 此角色的主要用途是讓使用者能夠存取進階電子文件。 獲指派此角色的使用者可以看到和安全性 & 他們是成員的合規性中心中開啟 [eDiscovery] 頁面上的案例清單。 使用者存取安全性 & 合規性中心中的案例之後，他們可以按一下 [**切換至進階電子文件**存取及分析進階電子文件中的案例資料。 此角色不允許使用者以預覽與案例相關聯的內容搜尋的結果，或執行其他內容搜尋] 或 [大小寫的管理工作。

### <a name="rms-decrypt"></a>RMS 解密

此角色可讓使用者解密 RMS 加密電子郵件訊息時匯出進階 eDiscovery 中搜尋結果或準備搜尋結果進行分析。 如需有關在匯出期間解密搜尋結果的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md)。

### <a name="search-and-purge"></a>搜尋及清除

此角色可讓使用者執行大量移除的比對的內容搜尋的準則的資料。 如需詳細資訊，請參閱[搜尋並刪除 Office 365 組織中的電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。 


## <a name="more-information"></a>詳細資訊

- **為什麼要建立 eDiscovery 管理員？** 如同先前的說明的 eDiscovery 系統管理員是 eDiscovery 管理員角色群組可以檢視及存取組織中的所有 eDiscovery 案例的成員。 這項功能來存取所有 eDiscovery 案例有兩個重要目的： 
    
  - 如果身為 eDiscovery 案例唯一成員的人員離開您的組織，沒有任何人 (包括「組織管理」角色群組的成員或「eDiscovery 管理員」角色群組的其他成員) 可以存取該 eDiscovery 案例，因為他們不是案例的成員。 在此情況下，完全無法存取案例的資料。 但 eDiscovery 系統管理員可以存取組織中的所有 eDiscovery 案例，因為他們可以檢視這種情況，並將自己或其他 eDiscovery 管理員新增為案例的成員。
    
  - EDiscovery 系統管理員可以檢視和存取所有 eDiscovery 案例，因為他們可以稽核和確立 「 所有 」 案例及相關聯的符合性搜尋。 這有助於防止任何誤用的符合性搜尋或 eDiscovery 案例。 因為 eDiscovery 系統管理員可以存取的符合性搜尋結果中的潛在機密資訊，您應該限制 eDiscovery 系統管理員的人數。
    
    此外，eDiscovery 系統管理員會自動新增為進階電子文件中的系統管理員。 這表示某個人必須 eDiscovery 系統管理員，才能在進階電子文件，例如使用者設定、 建立的情況下，以及將資料匯入至案例中執行的管理工作。
    
- **可以加入群組 eDiscovery 管理員角色群組的成員身分嗎？** 如先前所述，您可以使用**Add-rolegroupmember**指令程式的安全性 & 合規性中心 PowerShell 中擁有郵件功能的安全性群組新增 eDiscovery 管理員子群組，在 [eDiscovery 管理員角色群組的成員身分。 例如，您可以執行下列命令，以啟用郵件功能的安全性群組新增至 「 eDiscovery 管理員 」 角色群組。 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    請注意，不支援 Exchange 通訊群組或 Office 365 群組。 您必須使用擁有郵件功能的安全性] 群組，您可以建立 Exchange Online PowerShell 中使用` New-DistributionGroup -Type Security `命令。 您也可以建立擁有郵件功能的安全性群組 （及新增成員） 中 Exchange 系統管理中心或 Microsoft 365 系統管理中心。 請注意，可能需要最多 60 分鐘之後建立的新郵件安全性，可供新增至 eDiscovery 管理員角色群組。 
    
    也如先前所述，您就無法進行郵件安全性群組 eDiscovery 系統管理員的安全性 & 合規性中心 PowerShell 中使用**新增 eDiscoveryCaseAdmin**指令程式。 您只可以將個別使用者新增為 eDiscovery 系統管理員。 
    
    請注意，您也無法新增為擁有郵件功能的安全性群組為案例的成員。
