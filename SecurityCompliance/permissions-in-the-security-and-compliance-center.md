---
title: Office 365 安全性權限&amp;規範中心
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d10608af-7934-490a-818e-e68f17d0e9c1
description: Office 365 安全性&amp;規範中心可讓您授與權限執行類似裝置管理、 資料外洩防護、 eDiscovery、 保留、 等等的符合性工作的人員。這些人員可執行您明確授與存取權的工作。若要存取 [安全性]&amp;規範中心，為 Office 365 全域管理員或成員的一或多個安全性的使用者需要&amp;規範中心角色群組。
ms.openlocfilehash: ef281ca7cda706ff78fbf1a5584674cdf41e9025
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741056"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Office 365 安全性權限&amp;規範中心

Office 365 安全性&amp;規範中心可讓您授與權限執行類似裝置管理、 資料外洩防護、 eDiscovery、 保留、 等等的符合性工作的人員。這些人員可執行您明確授與存取權的工作。若要存取 [安全性]&amp;規範中心，為 Office 365 全域管理員或成員的一或多個安全性的使用者需要&amp;規範中心角色群組。
  
在 [安全性] 權限&amp;規範中心為基礎的角色型存取控制 (RBAC) 權限模型。這是相同的權限模型使用 Exchange，因此如果您已熟悉 Exchange，授與權限安全性&amp;規範中心會是非常類似。請務必記住，但該 Exchange 角色群組和安全性&amp;規範中心角色群組不共用成員資格或權限。雖然兩者都有組織管理角色群組，它們都相同。將其授與的權限和角色群組的成員的方式不同。沒有安全性清單&amp;下的規範中心角色群組。
  
![權限] 頁面上的 Office 365 安全性&amp;規範中心](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>成員、角色和角色群組的關係

**角色** 會授與執行一組工作的權限，例如，專案管理角色可讓人員使用 eDiscovery 案例。 
  
**角色群組**是一組角色能夠讓使用者執行其工作之間的安全性&amp;規範中心;例如，規範系統管理員角色群組包含角色案例管理、 內容搜尋與組織組態 （以及其他人） 因為某人身為規範系統將會需要這些工作執行其工作的權限。 
  
安全性&amp;規範中心包括預設角色群組的最常見的工作並指派人員所需的功能。建議您只將做為**成員**的個別使用者新增至預設角色群組。 
  
![圖表顯示角色和成員的角色群組關聯性](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
您可以編輯或刪除現有的角色群組，但是我們不建議這。而非編輯預設角色群組，您可以將其複製、 修改它，然後儲存使用不同的名稱。
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>使用安全性功能所需的權限&amp;規範中心

下表列出預設角色群組所能使用安全性&amp;規範中心。授與權限來執行規範工作的使用者，將其新增至適當的安全性&amp;規範中心角色群組。
  
管理安全性權限&amp;規範中心僅讓使用者可以存取規範功能所提供的安全性&amp;規範中心本身擷取。如果您想要授與其他不在 [安全性] 中的符合性功能的權限&amp;規範中心，例如 Exchange 傳輸規則，您需要使用 Exchange 系統管理中心。
  
若要了解如何存取權授與安全性&amp;規範中心、 取出[授與使用者存取 Office 365 規範系統管理中心](grant-access-to-the-security-and-compliance-center.md)。
  
|**角色群組**|**描述**|
|:-----|:-----|
|**規範系統管理員**<sup>1</sup> <br/> |成員可以管理裝置管理、 資料外洩防護、 報告及保留的設定。  <br/> |
|**eDiscovery 管理員** <br/> | 成員可執行搜尋和就地保留信箱、 SharePoint Online 網站及 OneDrive 商務位置。成員可以也建立與管理 eDiscovery 案例、 新增和移除成員案例、 建立及編輯與案例中為及存取 Office 365 進階 ediscovery case 資料相關聯的內容搜尋。<br/><br/>EDiscovery 管理員是尚未指派的其他權限之 eDiscovery 管理員角色群組的成員。EDiscovery 管理員可以執行的工作，除了 eDiscovery 管理員可以：<br/><br/>  • [檢視組織中所有的 eDiscovery 案例。  <br/>  • [伺服器陣列之後大小寫的成員身分新增自行管理任何 eDiscovery 案例。  <br/><br/>EDiscovery 管理員和 eDiscovery 管理員的主要差異在於 eDiscovery 管理員可以存取已列在 [安全性] 中的**eDiscovery 案例**] 頁面上的所有案例&amp;規範中心。EDiscovery 管理員只能存取他們所建立的情況下或之成員的情況。 如需讓使用者 eDiscovery 管理員的詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。<br/>           |
|**組織管理**<sup>1</sup> <br/> |成員可以控制存取安全性功能的權限&amp;規範中心及也管理的裝置管理、 資料外洩防護、 報告及保留設定。  <br/> 請注意，為了讓不是以查看由 MDM 管理 Office 365 的裝置清單的全域管理員的使用者及這些裝置上執行動作，例如 Office 365 中淘汰 MDM 從裝置，使用者必須是 Exchange 系統管理員。  <br/> Office 365 全域管理員會自動新增為此角色群組的成員。           |
|**記錄管理** <br/> |成員可以管理並處置記錄的內容。  <br/> |
|**檢閱者** <br/> |成員只能在 [安全性] eDiscovery 案例] 頁面上檢視的情況下清單&amp;規範中心。他們無法建立、 開啟或管理 eDiscovery 案例。此角色群組的主要目的是要允許成員檢視及存取 case 進階在 eDiscovery 中的資料。  <br/> 這個角色群組具有最嚴格的 eDiscovery 相關權限。  <br/> |
|**安全性管理員** <br/> |此角色群組的成員可能包括跨服務管理員，以及外部合作夥伴群組和 Microsoft 技術支援人員。根據預設，此群組可能未指派任何角色。不過，它會在 Azure Active Directory 中的安全性管理員角色的成員並將會繼承該角色的功能。集中管理的權限，變更此角色在 Azure Active Directory 系統管理中心-如需詳細資訊，請參閱[在 Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。如果您編輯安全性 & 規範中心在此角色群組，這些變更僅適用於安全性 & 規範中心並沒有任何其他服務，而在 Azure Active Directory 管理中心內所做的變更會影響所有服務。<br/> 所有的安全性讀者角色加上額外的管理權限的相同服務的數字的唯讀權限： Azure 資訊保護、 身分識別保護中心、 權限的身分識別管理、 監視 Office 365 服務健康情況及 Office 365 安全性&amp;規範中心。  <br/> |
|**安全性讀者** <br/> |成員具有唯讀存取權的身分識別保護中心、 權限的身分識別管理、 監視 Office 365 服務健康情況及 Office 365 安全性的安全性功能的數字&amp;規範中心。  <br/> 此角色群組的成員資格是整個服務進行同步處理與集中管理。此角色群組的成員可能包括跨服務管理員，以及外部合作夥伴群組和 Microsoft 技術支援人員。根據預設，此群組可能未指派任何角色。不過，它會在 Azure Active Directory 中的安全性管理員角色的成員並將會繼承該角色的功能。集中管理的權限，變更此角色在 Azure Active Directory 系統管理中心-如需詳細資訊，請參閱[在 Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。如果您編輯安全性 & 規範中心在此角色群組，這些變更僅適用於安全性 & 規範中心並沒有任何其他服務，而在 Azure Active Directory 管理中心內所做的變更會影響所有服務。<br/> |
|**服務保證使用者** <br/> |成員可以存取 Office 365 安全性服務保證區段&amp;規範中心。服務保證提供報表及說明 Microsoft 的安全性作法儲存在 Office 365 的客戶資料的文件。它也可提供獨立的協力廠商稽核報告在 Office 365。如需詳細資訊，請參閱[服務 Office 365 安全性保證&amp;規範中心](http://go.microsoft.com/fwlink/p/?LinkID=717765)。<br/> |
|**監督檢閱** <br/> |成員可以建立和管理原則可定義其通訊會受到組織中的檢閱。如需詳細資訊，請參閱 ＜ [Configure 監督檢閱您的組織的原則](configure-supervision-policies.md)。<br/> |
   
> [!NOTE]
> <sup>1</sup>此角色群組不會指派成員至 Office 365 稽核記錄檔中搜尋或使用任何可能包括 Exchange 資料，例如 DLP 或 ATP 報表的報表所需的權限。若要搜尋稽核記錄或檢視所有報告，使用者有指派 Exchange Online 中的權限。這是因為基礎指令程式來搜尋稽核記錄是 Exchange Online 指令程式。Office 365 全域管理員可以搜尋稽核記錄檔並檢視所有報告，因為他們正在自動新增為組織管理角色群組的成員在 Exchange Online。如需詳細資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](https://go.microsoft.com/fwlink/p/?LinkID=708432)。 
  

