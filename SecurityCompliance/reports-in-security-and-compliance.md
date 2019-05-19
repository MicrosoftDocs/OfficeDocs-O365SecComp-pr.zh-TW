---
title: 安全規範中心內的報告
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用安全性 & 合規性中心來取得各種報告您的 SharePoint Online 和 Exchange Online 組織，以及 Azure Active Directory 的報告。  '
ms.openlocfilehash: 979eb59ed0adf115b9cdda4cd99f97845e9b4b4c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157227"
---
# <a name="reports-in-the-security--compliance-center"></a>安全規範中心內的報告

您可以使用安全性 & 合規性中心中的 [**檢視報告**] 頁面上，快速存取您的 SharePoint Online 和 Exchange Online 組織的 [稽核報告。 您也可以存取 Azure Active Directory (AD) 使用者登入報告，使用者活動報告，並從 [**檢視報告**] 頁面上的 Azure AD 稽核記錄。 這是因為您付費的 Office 365 訂閱包含免費的 Microsoft Azure 訂閱。 第一次，您嘗試存取這些 Azure 的報告，您必須完成一次性的註冊程序。 
  
> [!TIP]
> 若要檢視 Office 365 組織中的活動相關的其他報告，請參閱 <<c0>在 Microsoft 365 系統管理中心的活動報告。 
  
 **開始之前**
  
您需要下列權限，才能檢視安全性 & 合規性中心中的報告。
  
- 您必須獲指派安全性讀取者 」 角色在 Exchange 系統管理中心 (EAC) 中的安全性 & 合規性中心檢視報告。 根據預設，此角色被指派給在 EAC 中的組織管理和安全性讀取者角色群組。
    
- 您必須被指派安全性 & 合規性中心，以檢視 DLP 報告中的安全性 & 合規性中心中的僅限檢視 DLP 符合性管理角色。 根據預設，此角色被指派給安全性 & 合規性中心的符合性系統管理員、 組織管理、 安全性系統管理員和安全性讀取者角色群組。

- 此外，您必須獲指派 「 僅檢視收件者角色，在 EAC 中，在 EAC 中檢視 DLP 報告。 根據預設，此角色被指派給在 EAC 中的規範管理、 組織管理和 View-Only Organization Management 角色群組。
  
 **若要開啟 [檢視報告] 頁面的安全性 & 合規性中心中：**
  
1. 請移至 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 登入 Office 365 使用 Office 365 組織中的使用者帳戶的認證。
    
在 [**檢視報告**] 頁面上，您可以檢視下列類型的報告： 
  
- [稽核報告](#auditing-reports)
- [主管檢閱報告](#supervisory-review-report)
- [資料外洩防護報告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>稽核報告

下表說明 [**稽核**] 區段中安全性 & 合規性中心中的 [**檢視報告**] 頁面上的報告。 
  
|**Report**|**描述**|
|:-----|:-----|
|**Office 365 稽核記錄報告** <br/> |您可以在 Office 365 組織中搜尋使用者和系統管理員活動的 Office 365 稽核記錄檔。 報告中包含的項目使用者和系統管理員活動，在 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Azure Active Directory，也就是 Office 365 的目錄服務。 如需詳細資訊，請參閱 <<c0>的搜尋稽核記錄在 Office 365。  <br/> |
|**Azure AD 報告** <br/> |若要尋找不尋常或可疑登入活動在 Office 365 組織中，您可以使用登入和活動在 Microsoft Azure 中的報告。 您也可以在 Azure AD 稽核記錄檔檢視事件。 若要在 Azure 中檢視報表，只要按一下**檢視 Azure AD 報告**。 如需詳細資訊，請參閱： <br/><br/>[使用 Office 365 中免費的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [檢視您存取及使用狀況的報告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。  <br/> |
|**Exchange 稽核報告** <br/> | 您可以使用 Office 365 中的稽核功能來追蹤對您的 Exchange Online 設定您的組織系統管理員所做的變更。 也會記錄由 Microsoft 資料中心系統管理員或委派的系統管理員對您的 Exchange Online 組織所做的變更。 針對 Exchange Online，系統管理員稽核記錄已根據預設，因此您不需要執行任何動作以將它開啟。 Exchange Online 也提供信箱稽核記錄，可讓您追蹤信箱擁有者以外的人收到存取信箱。 您必須針對您想要追蹤之非擁有者存取的每個信箱啟用信箱稽核記錄。  <br/>  對於系統管理員及信箱稽核記錄，您可以執行稽核報告，即可檢視稽核記錄項目。 您也可以匯出信箱和系統管理員稽核記錄，這些記錄會在 24 小時內，以 XML 檔案附加在電子郵件訊息中傳送給您。 <br/><br/>如需匯出稽核記錄的詳細資訊，請參閱：  <br/><br/> [匯出信箱稽核記錄](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [檢視和匯出資料中心系統管理員稽核記錄](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [搜尋角色群組變更或管理員稽核記錄檔](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 稽核報告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>主管檢閱報告

主管檢閱 」 報告，您可以看見組織中的所有主管檢閱原則的狀態。 如需詳細資訊，請參閱 <<c0>設定主管檢閱您組織的原則。
  
## <a name="data-loss-prevention-reports"></a>資料外洩防護報告

資料外洩防護 (DLP) 報告包含 DLP 原則的相關資訊，以及已套用至內容的規則包含 Office 365 組織中的敏感資料。 您也可以設定報告，即可顯示根據 DLP 原則和規則之動作的相關資訊。 如需詳細資訊，請參閱[檢視資料外洩防護的報告](view-the-dlp-reports.md)。
