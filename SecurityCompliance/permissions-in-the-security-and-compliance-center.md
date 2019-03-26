---
title: Permissions in the Office 365 Security &amp; Compliance Center
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Office 365 安全性&amp;合規性中心可讓您授與權限執行等裝置管理、 資料外洩防護、 eDiscovery、 保留和等等的合規性工作人員。 這些人員可以執行您明確授與他們存取權的工作。 若要存取安全性&amp;合規性中心，使用者必須是 Office 365 全域系統管理員或成員的一或多個安全性&amp;合規性中心角色群組。
ms.openlocfilehash: 9b2692d2afd70be911581caff237e61d405cf10f
ms.sourcegitcommit: 6a7cec7d1f0d3b8d71f313bfa22f44c827de2336
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2019
ms.locfileid: "30798129"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Permissions in the Office 365 Security &amp; Compliance Center

Office 365 安全性&amp;合規性中心可讓您授與權限執行等裝置管理、 資料外洩防護、 eDiscovery、 保留和等等的合規性工作人員。 這些人員可以執行您明確授與他們存取權的工作。 若要存取安全性&amp;合規性中心，使用者必須是 Office 365 全域系統管理員或成員的一或多個安全性&amp;合規性中心角色群組。
  
安全性權限&amp;合規性中心為基礎的角色型存取控制 (RBAC) 權限模型。 這是相同的權限模型，由 Exchange，因此如果您已熟悉 Exchange，授與權限安全性&amp;合規性中心會是非常類似。 請務必記得，不過，該 Exchange 角色群組和安全性&amp;合規性中心角色群組不會共用成員資格或權限。 雖然兩者都有組織管理角色群組，但它們不相同。 將它們授與的權限及角色群組的成員，也會有所不同。 沒有一份安全性&amp;下方的合規性中心角色群組。
  
![權限] 頁面上，在 Office 365 安全性&amp;合規性中心](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>成員、 角色和角色群組之間的關係

**角色**會授與權限執行的一組工作;例如，專案管理角色可讓人員使用 eDiscovery 案例。 
  
**角色群組**是一組角色可讓跨安全性執行其工作的人員&amp;合規性中心;例如，「 合規性系統管理員角色群組包含角色案例管理、 內容搜尋與組織組態 （加上其他人），因為是合規性系統管理員的人員會需要這些執行其工作的工作的權限。 
  
安全性&amp;合規性中心包含最常見的工作和函式，您將需要指派人員的預設角色群組。 我們建議您只為**成員**的個別使用者新增至預設的角色群組。 
  
![圖表顯示角色和成員的角色群組關聯性](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
您可以編輯或刪除現有的角色群組，但我們不建議這。 而非編輯預設的角色群組，您可以將它複製、 修改它，並再將它儲存以不同的名稱。
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>使用安全性功能所需的權限&amp;合規性中心

下表列出用於安全性的預設角色群組&amp;合規性中心。 若要授與權限給使用者，讓執行規範工作，將其新增至適當的安全性&amp;合規性中心角色群組。
  
管理安全性的權限&amp;合規性中心只可讓使用者存取可用安全性中的符合性功能&amp;本身合規性中心。 如果您想要授與其他不在 [安全性中的符合性功能的權限&amp;合規性中心，例如 Exchange 郵件流程規則 （也稱為傳輸規則），您必須使用 Exchange 系統管理中心。
  
若要查看如何授與存取權的安全性&amp;合規性中心，嗎？ 請查看[讓使用者能夠存取 Office 365 合規性系統管理中心](grant-access-to-the-security-and-compliance-center.md)。
  
|**角色群組**|**描述**|
|:-----|:-----|
|**合規性管理員**<sup>1</sup> <br/> |成員可以管理裝置管理、 資料外洩防護、 報告和保留的設定。  <br/> |
|**規範資料管理員** <br/> |成員可以管理裝置管理、 資料保護、 資料外洩防護、 報告和保留的設定。  <br/> |
|**eDiscovery 管理員** <br/> | 成員可以執行搜尋和就地保留信箱、 SharePoint Online 網站與 OneDrive 商務位置。 成員可以也建立及管理 eDiscovery 案例、 新增及移除案例成員、 建立及編輯與案例中，並存取 Office 365 進階電子文件探索中的案例資料相關聯的內容搜尋。 <br/><br/>EDiscovery 系統管理員是 eDiscovery 管理員角色群組的成員獲指派其他權限。 除了電子文件探索管理員可以執行的工作，eDiscovery 系統管理員可以：  <br/><br/>  • 在組織中檢視所有 eDiscovery 案例。  <br/>  • 在自行新增為案例的成員之後管理任何 eDiscovery 案例。  <br/><br/>EDiscovery 管理員與 eDiscovery 系統管理員的主要差異是 eDiscovery 管理員可以存取安全性 [ **eDiscovery 案例**] 頁面列出的所有案例&amp;合規性中心。 電子文件探索管理員只能存取他們所建立的情況下或它們必須是成員的情況。  如需 eDiscovery 系統管理員進行使用者的詳細資訊，請參閱[指派 Office 365 安全性中的 eDiscovery 權限&amp;合規性中心](assign-ediscovery-permissions.md)。 <br/> |
|**郵件流程管理員** <br/> |成員可以監視及檢視郵件流程見解和安全性 & 合規性中心內的報告。 全域系統管理員可以新增至此群組中，一般使用者，但如果使用者不是 Exchange 系統管理員群組的成員，使用者將無法存取 Exchange 系統相關工作。  <br/> |
|**組織管理**<sup>1</sup> <br/> |成員可以控制存取安全性功能的權限&amp;合規性中心，以及管理裝置管理、 資料外洩防護、 報告和保留的設定。  <br/> 請注意，為了讓不是全域系統管理員才能查看 Office 365 的 MDM 所管理的裝置清單的使用者與這些裝置上執行動作，例如 Office 365，從 MDM 淘汰裝置，使用者必須是 Exchange 系統管理員。  <br/> Office 365 全域系統管理員會自動新增為此角色群組的成員。           |
|**記錄管理** <br/> |成員可以管理和處置記錄內容。  <br/> |
|**檢閱者** <br/> |成員只能檢視安全性中的 eDiscovery 案例] 頁面上的案例清單&amp;合規性中心。 他們無法建立、 開啟或管理 eDiscovery 案例。 這個角色群組的主要目的是允許成員可以檢視及存取案例進階電子文件中的資料。  <br/> 這個角色群組具有最嚴格的 eDiscovery 相關權限。  <br/> |
|**安全性系統管理員** <br/> |這個角色群組的成員可能包括跨服務管理員，以及外部合作夥伴群組與 Microsoft 支援服務。 根據預設，此群組可能無法指定任何角色。 不過，它將會在 Azure Active Directory 中的安全性管理員角色的成員，而且會繼承該角色的功能。 集中管理的權限，變更此角色，在 [Azure Active Directory 系統管理中心-如需詳細資訊，請參閱[在 Azure Active Directory 系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 如果您編輯安全性 & 合規性中心在此角色群組時，這些變更僅適用於安全性 & 規範中心和不能以任何其他服務，而在 Azure Active Directory 系統管理中心中所做的變更會影響所有的服務。<br/> 所有 「 安全性讀取者 」 角色，再加上的相同服務的其他系統管理權限的數字的唯讀權限： Azure 資訊保護、 身分識別防護中心、 特殊權限的身分識別管理、 監視 Office 365 服務健康情況及 Office 365 安全性&amp;合規性中心。  <br/> |
|**安全性運算子** <br/> |成員可以管理安全性警示，並且也檢視報表與安全性功能的設定。 <br/> |
|**安全性讀取者** <br/> |成員具有唯讀存取權的身分識別防護中心、 特殊權限的身分識別管理、 監視 Office 365 服務健康情況和 Office 365 安全性的安全性功能的數字&amp;合規性中心。  <br/> 此角色群組的成員資格是服務之間同步處理，並集中管理。 這個角色群組的成員可能包括跨服務管理員，以及外部合作夥伴群組與 Microsoft 支援服務。 根據預設，此群組可能無法指定任何角色。 不過，它將會在 Azure Active Directory 安全性讀取者角色的成員，而且會繼承該角色的功能。 集中管理的權限，變更此角色，在 [Azure Active Directory 系統管理中心-如需詳細資訊，請參閱[在 Azure Active Directory 系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 如果您編輯安全性 & 合規性中心在此角色群組時，這些變更僅適用於安全性 & 規範中心和不能以任何其他服務，而在 Azure Active Directory 系統管理中心中所做的變更會影響所有的服務。<br/> |
|**服務保證使用者** <br/> |成員可以存取 Office 365 安全性中的服務保證區段&amp;合規性中心。 服務保證提供報表及說明 Microsoft 的安全性作法，儲存在 Office 365 的客戶資料的文件。 它也會提供有關 Office 365 的獨立第三方稽核報告。 如需詳細資訊，請參閱[服務在 Office 365 安全性保證&amp;合規性中心](http://go.microsoft.com/fwlink/p/?LinkID=717765)。  <br/> |
|**主管檢閱** <br/> |成員可以建立及管理定義其原則通訊受限於組織中的檢閱。 如需詳細資訊，請參閱 <<c0>設定主管檢閱您組織的原則。  <br/> |
   
> [!NOTE]
> <sup>1</sup>此角色群組不會將成員指派 Office 365 稽核記錄中搜尋或使用任何報告，其中可能包含 Exchange 資料，例如 DLP 或 ATP 報告所需的權限。 若要搜尋稽核記錄，或若要檢視所有報告，使用者必須被指派 Exchange Online 中的權限。 這是因為基礎指令程式用來搜尋稽核記錄是 Exchange Online cmdlet。 Office 365 全域系統管理員可以搜尋稽核記錄，並檢視所有報告，因為就會自動新增為 Organization Management 角色群組的成員。 在 Exchange Online。 如需詳細資訊，請參閱[搜尋稽核記錄以在 Office 365 安全性&amp;合規性中心](https://go.microsoft.com/fwlink/p/?LinkID=708432)。 
  
## <a name="mapping-of-role-groups-to-assigned-roles"></a>對應的角色指派的角色群組

根據預設，角色群組會有一組的角色指派給他們。 此表格顯示指派給每個角色群組的角色。

|**角色群組**|**指派的角色**|
|:-----|:-----|
|**合規性管理員** <br/> |僅檢視保留管理 <br/>管理提醒 <br/>僅檢視管理提醒 <br/>僅限檢視裝置管理 <br/>組織組態 <br/>DLP 符合性管理 <br/>僅限檢視 IB 相符性管理 <br/>處理管理 <br/>僅限檢視 DLP 符合性管理 <br/>RecordManagement <br/>IB 相符性管理 <br/>僅檢視稽核記錄 <br/>合規性管理員 <br/>裝置管理 <br/>符合性搜尋 <br/>專案管理 <br/>保留管理 <br/>僅限檢視的記錄管理 <br/>僅限檢視收件者 <br/>保留 <br/> |
|**規範資料管理員** <br/> |僅檢視保留管理 <br/>管理提醒 <br/>敏感度標籤系統管理員 <br/>僅檢視管理提醒 <br/>僅限檢視裝置管理 <br/>組織組態 <br/>DLP 符合性管理 <br/>僅限檢視 IB 相符性管理 <br/>處理管理 <br/>僅限檢視 DLP 符合性管理 <br/>RecordManagement <br/>IB 相符性管理 <br/>僅檢視稽核記錄 <br/>合規性管理員 <br/>裝置管理 <br/>符合性搜尋 <br/>保留管理 <br/>僅限檢視的記錄管理 <br/>僅限檢視收件者<br/> |
|**eDiscovery 管理員** <br/> |匯出 <br/>RMS 解密 <br/>Custodian <br/>通訊 <br/>檢閱 <br/>預覽 <br/>符合性搜尋 <br/>專案管理 <br/>保留 <br/> |
|**郵件流程管理員** <br/> |僅限檢視收件者 <br/>  |
|**組織管理** <br/> |僅檢視保留管理 <br/>管理提醒 <br/>角色管理 <br/>敏感度標籤系統管理員 <br/>僅檢視管理提醒 <br/>僅限檢視裝置管理 <br/>組織組態 <br/>DLP 符合性管理 <br/>僅限檢視 IB 相符性管理 <br/>處理管理 <br/>僅限檢視 DLP 符合性管理 <br/>RecordManagement <br/>稽核記錄檔 <br/>IB 相符性管理 <br/>安全性讀取者 <br/>安全性系統管理員 <br/>服務保證檢視 <br/>搜尋及清除 <br/>僅檢視稽核記錄 <br/>合規性管理員 <br/>裝置管理 <br/>符合性搜尋 <br/>專案管理 <br/>保留管理 <br/>僅限檢視的記錄管理 <br/>僅限檢視收件者 <br/>保留 <br/> |
|**記錄管理** <br/> |RecordManagement <br/>稽核記錄檔 <br/>保留管理 <br/> |
|**檢閱者** <br/> |檢閱 <br/> |
|**安全性系統管理員** <br/> |管理提醒 <br/>敏感度標籤系統管理員 <br/>僅檢視管理提醒 <br/>僅限檢視裝置管理 <br/>DLP 符合性管理 <br/>僅限檢視 IB 相符性管理 <br/>僅限檢視 DLP 符合性管理 <br/>稽核記錄檔 <br/>IB 相符性管理 <br/>安全性系統管理員 <br/>僅檢視稽核記錄 <br/>裝置管理 <br/> |
|**安全性運算子** <br/> |管理提醒 <br/>僅檢視管理提醒 <br/>僅限檢視裝置管理 <br/>僅限檢視 IB 相符性管理 <br/>僅限檢視 DLP 符合性管理 <br/>安全性讀取者 <br/>僅檢視稽核記錄 <br/>符合性搜尋 <br/> |
|**安全性讀取者** <br/> |僅檢視管理提醒 <br/>僅限檢視裝置管理 <br/>僅限檢視 IB 相符性管理 <br/>僅限檢視 DLP 符合性管理 <br/>安全性讀取者 <br/> |
|**服務保證使用者** <br/> |服務保證檢視 <br/> |
|**主管檢閱** <br/> |主管檢閱管理員 <br/> |
