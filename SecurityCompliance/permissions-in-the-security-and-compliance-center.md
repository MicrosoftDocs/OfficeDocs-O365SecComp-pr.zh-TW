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
ms.openlocfilehash: e393bad7c3a57b0734835e56fcd781cc31327c18
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013427"
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
|**eDiscovery 管理員** <br/> | 成員可以在信箱、SharePoint Online 網站和商務用 OneDrive 地點執行搜尋和保留。成員也可以建立及管理 eDiscovery 案例、在案例中新增和移除成員、建立及編輯與案例相關聯的規範搜尋。<br/>  eDiscovery 系統管理員是已被指派其他權限的 eDiscovery 管理員角色群組的成員。eDiscovery 系統管理員可以：<br/>  檢視組織中的所有 eDiscovery 案例。  <br/>  在自行新增為案例的成員之後管理任何 eDiscovery 案例。  <br/>  存取 Office 365 進階 eDiscovery。這是因為 eDiscovery 管理員會自動新增為進階 ediscovery 的管理員。您必須是 eDiscovery 安全性的系統管理員的附註&amp;規範中心以存取進階的 eDiscovery。如需讓使用者 eDiscovery 管理員的詳細資訊，請參閱[Office 365 安全性的 eDiscovery 案例&amp;規範中心](https://go.microsoft.com/fwlink/p/?LinkId=780738)。<br/> 如果您想要授與使用者管理權限進階在 eDiscovery 中但不想要在 [安全性] 中進行 eDiscovery 管理員&amp;規範中心您可以將其新增至 eDiscovery 管理員角色群組，然後將其新增為管理員進階的 eDiscovery。指示，請參閱[設定使用者和 Office 365 進階 ediscovery 案例](https://go.microsoft.com/fwlink/p/?LinkId=780696)。           |
|**組織管理**<sup>1</sup> <br/> |成員可以控制存取安全性功能的權限&amp;規範中心及也管理的裝置管理、 資料外洩防護、 報告及保留設定。  <br/> 請注意，為了讓不是以查看由 MDM 管理 Office 365 的裝置清單的全域管理員的使用者及這些裝置上執行動作，例如 Office 365 中淘汰 MDM 從裝置，使用者必須是 Exchange 系統管理員。  <br/> Office 365 全域管理員會自動新增為此角色群組的成員。           |
|**記錄管理** <br/> |成員可以管理並處置記錄的內容。  <br/> |
|**檢閱者** <br/> |成員只能在 [安全性] eDiscovery 案例] 頁面上檢視的情況下清單&amp;規範中心。他們無法建立、 開啟或管理 eDiscovery 案例。此角色群組的主要目的是要允許成員檢視及存取 case 進階在 eDiscovery 中的資料。  <br/> 這個角色群組具有最嚴格的 eDiscovery 相關權限。  <br/> |
|**安全性管理員** <br/> |此角色群組的成員資格是整個服務進行同步處理與集中管理。此角色群組不是可透過管理員入口網站。此角色群組的成員可能包括跨服務管理員，以及外部合作夥伴群組和 Microsoft 技術支援人員。根據預設，此群組可能未指派任何角色。不過，它會是安全性管理員角色群組的成員，而且會繼承該角色群組的功能。  <br/> 所有的安全性讀者角色加上額外的管理權限的相同服務的數字的唯讀權限： Azure 資訊保護、 身分識別保護中心、 權限的身分識別管理、 監視 Office 365 服務健康情況及 Office 365 安全性&amp;規範中心。  <br/> |
|**安全性讀者** <br/> |成員具有唯讀存取權的身分識別保護中心、 權限的身分識別管理、 監視 Office 365 服務健康情況及 Office 365 安全性的安全性功能的數字&amp;規範中心。  <br/> 此角色群組的成員資格是整個服務進行同步處理與集中管理。此角色群組不是可透過管理員入口網站。此角色群組的成員可能包括跨服務管理員，以及外部合作夥伴群組和 Microsoft 技術支援人員。根據預設，此群組可能未指派任何角色。不過，它會是安全性讀者角色群組的成員並將會繼承該角色群組的功能。  <br/> |
|**服務保證使用者** <br/> |成員可以存取 Office 365 安全性服務保證區段&amp;規範中心。服務保證提供報表及說明 Microsoft 的安全性作法儲存在 Office 365 的客戶資料的文件。它也可提供獨立的協力廠商稽核報告在 Office 365。如需詳細資訊，請參閱[服務 Office 365 安全性保證&amp;規範中心](http://go.microsoft.com/fwlink/p/?LinkID=717765)。<br/> |
|**監督檢閱** <br/> |成員可以建立和管理原則可定義其通訊會受到組織中的檢閱。如需詳細資訊，請參閱 ＜ [Configure 監督檢閱您的組織的原則](configure-supervision-policies.md)。<br/> |
   
> [!NOTE]
> <sup>1</sup>此角色群組不會指派成員至 Office 365 稽核記錄檔中搜尋或使用任何可能包括 Exchange 資料，例如 DLP 或 ATP 報表的報表所需的權限。若要搜尋稽核記錄或檢視所有報告，使用者有指派 Exchange Online 中的權限。這是因為基礎指令程式來搜尋稽核記錄是 Exchange Online 指令程式。Office 365 全域管理員可以搜尋稽核記錄檔並檢視所有報告，因為他們正在自動新增為組織管理角色群組的成員在 Exchange Online。如需詳細資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](https://go.microsoft.com/fwlink/p/?LinkID=708432)。 
  

