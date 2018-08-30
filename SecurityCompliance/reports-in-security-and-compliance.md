---
title: Reports in Office 365 安全性&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用 Office 365 安全性&amp;規範中心若要取得的 SharePoint Online 和 Exchange Online 組織的各種報告以及 Azure Active Directory 報告。  '
ms.openlocfilehash: 0b633583e14a18c7cf579d10462cf41714397812
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526233"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a>Reports in Office 365 安全性&amp;規範中心

您可以使用 「**檢視報告**」 頁面中的 Office 365 安全性&amp;規範中心以快速存取您的 SharePoint Online 與 Exchange Online 組織的稽核報告。您也可以存取 Azure Active Directory (AD) 使用者登入報告、 使用者活動報告，並 Azure AD 稽核記錄從 「**檢視報告**」 頁面。這是因為您付費的 Office 365 訂閱包括 Microsoft Azure 免費訂閱。第一次嘗試存取這些 Azure 的報告，您必須完成一次性註冊程序。 
  
> [!TIP]
> 若要檢視您的 Office 365 組織活動相關的其他報告，請參閱[Office 365 系統管理中心中的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。 
  
 **開始之前**
  
您需要下列權限若要檢視報告安全性&amp;規範中心。
  
- 您必須指定給 Exchange 系統管理中心 (EAC) 中 [安全性] 檢視報表中的安全性讀者角色&amp;規範中心。根據預設，此角色指派給在 EAC 中組織管理和安全性讀者角色群組。
    
- 您必須指定給安全性的 DLP 相符性管理角色&amp;規範中心檢視 DLP 報告 （與 DLP 原則） 安全性&amp;規範中心。根據預設，此角色指派給規範管理員、 組織管理和安全性管理員角色群組安全性&amp;規範中心。
    
此外，您必須指定給在 EAC 中檢視 DLP 報告 （與 DLP 原則） 的資料外洩防護角色在 EAC 中。根據預設，此角色指派給在 EAC 中相符性管理] 和 [組織管理角色群組。
  
 **若要開啟 [檢視報告] 頁面上安全性&amp;規範中心：**
  
1. 移至 [ [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 登入 Office 365 使用 Office 365 組織中的使用者帳戶的認證。
    
在**檢視報告**」 頁面上，您可以檢視下列類型的報告： 
  
- [EOP 中的稽核報告](#auditing-reports)
- [監督檢閱報告](#supervisory-review-report)
- [資料外洩防護報告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>稽核報告

下表說明安全性中**檢視報告**」 頁面的 [**稽核**] 區段中報告&amp;規範中心。 
  
|**報告**|**描述**|
|:-----|:-----|
|**Office 365 稽核記錄報告** <br/> |您可以在 Office 365 組織中搜尋使用者與系統管理活動的 Office 365 稽核記錄。報表會包含項目使用者和系統活動在 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Azure Active Directory，這是 Office 365 的目錄服務。如需詳細資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。<br/> |
|**Azure AD 報告** <br/> |要尋找不尋常或可疑登入活動的 Office 365 組織中，您可以使用登入及活動 Microsoft Azure 中的報告。您也可以在 Azure AD 稽核記錄檔檢視事件。若要在 Azure 中檢視報表，只要按一下**檢視 Azure AD 報表**。如需詳細資訊，請參閱：<br/><br/>[使用您在 Office 365 中可用的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [檢視您存取及使用狀況報告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。  <br/> |
|**Exchange 稽核報告** <br/> | 您可以使用 Office 365 中的稽核功能追蹤對您的 Exchange Online 設定組織的系統管理員所做的變更。由 Microsoft 資料中心管理員或委派的管理員對您的 Exchange Online 組織也會記錄的變更。Exchange online，系統管理員稽核記錄已啟用根據預設，因此您不需要執行任何動作加以開啟。Exchange Online 也提供信箱稽核記錄功能讓您追蹤對信箱的信箱擁有者以外的其他人存取。您必須針對每一個您想要追蹤非擁有者存取的信箱啟用信箱稽核記錄。<br/>  系統管理和信箱稽核記錄，您可以執行稽核報告] 檢視稽核記錄項目。您也可以匯出信箱並管理稽核記錄，這 24 小時內的 XML 檔案附加至電子郵件傳送給您。<br/><br/>如需匯出稽核記錄的詳細資訊，請參閱：  <br/><br/> [匯出信箱稽核記錄](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [檢視和匯出資料中心管理稽核記錄](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [搜尋角色群組變更或管理員稽核記錄檔](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 稽核報告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>監督檢閱報告

搭配監督檢閱報告，您可以在組織中看到監督檢閱的所有原則的狀態。如需詳細資訊，請參閱 ＜ [Configure 監督檢閱您的組織的原則](configure-supervision-policies.md)。
  
## <a name="data-loss-prevention-reports"></a>資料外洩防護報告

資料外洩防護 (DLP) 報告包含 DLP 原則的相關資訊及規則已套用至內容包含在 Office 365 組織中的機密資料。您也可以設定報表以顯示已根據您的 DLP 原則和規則的 DLP 動作的相關資訊。如需詳細資訊，請參閱 ＜[資料外洩防護報告] 檢視](view-the-dlp-reports.md)。
