---
title: Office 365 Office 365 安全規範中心內的報告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用 Office 365 安全性 & 規範中心的 SharePoint Online 和 Exchange Online 組織，以及 Azure Active Directory 報表取得各種不同的報告。  '
ms.openlocfilehash: 36e6d3efce1758d52cd30451a2b60b19f4654056
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087302"
---
# <a name="reports-in-the-office-365-security--compliance-center"></a><span data-ttu-id="d0243-103">Office 365 Office 365 安全規範中心內的報告</span><span class="sxs-lookup"><span data-stu-id="d0243-103">Reports in the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="d0243-p101">您可以使用 Office 365 安全性 & 規範中心中的 「**檢視報告**」 頁面快速存取的 SharePoint Online 和 Exchange Online 組織的 [稽核報告]。您也可以存取 Azure Active Directory (AD) 使用者登入報告、 使用者活動報告，並 Azure AD 稽核記錄從 「**檢視報告**」 頁面。這是因為您付費的 Office 365 訂閱包括 Microsoft Azure 免費訂閱。第一次嘗試存取這些 Azure 的報告，您必須完成一次性註冊程序。</span><span class="sxs-lookup"><span data-stu-id="d0243-p101">You can use the **View reports** page in the Office 365 Security & Compliance Center to quickly access audit reports for your SharePoint Online and Exchange Online organizations. You can also access Azure Active Directory (AD) user sign-in reports, user activity reports, and the Azure AD audit log from the **View reports** page. This is because your paid Office 365 subscription includes a free subscription to Microsoft Azure. The first time that you try to access these Azure reports, you will have to complete a one-time registration process.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d0243-108">若要檢視您的 Office 365 組織活動相關的其他報告，請參閱[Office 365 系統管理中心中的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="d0243-108">To view additional reports about activity in your Office 365 organization, see [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).</span></span> 
  
 <span data-ttu-id="d0243-109">**開始之前**</span><span class="sxs-lookup"><span data-stu-id="d0243-109">**Before you begin**</span></span>
  
<span data-ttu-id="d0243-110">您必須在安全性 & 規範中心檢視報表的下列權限。</span><span class="sxs-lookup"><span data-stu-id="d0243-110">You need the following permissions to view reports in the Security & Compliance Center.</span></span>
  
- <span data-ttu-id="d0243-p102">您必須在 Exchange 系統管理中心 (EAC) 中的安全性 & 規範中心檢視報表的安全性讀者角色指派。根據預設，此角色指派給在 EAC 中組織管理和安全性讀者角色群組。</span><span class="sxs-lookup"><span data-stu-id="d0243-p102">You have to be assigned the Security Reader role in the Exchange admin center (EAC) to view reports in the Security & Compliance Center. By default, this role is assigned to the Organization Management and Security Reader role groups in the EAC.</span></span>
    
- <span data-ttu-id="d0243-p103">您必須指定給安全性 & 規範中心以檢視安全性 & 規範中心中的 DLP 報告中的 View-Only DLP 相符性管理角色。根據預設，此角色指派給安全性 & 規範中心的規範管理員、 組織管理、 安全性管理員及安全性讀者角色群組。</span><span class="sxs-lookup"><span data-stu-id="d0243-p103">You have to be assigned the View-Only DLP Compliance Management role in the Security & Compliance Center to view DLP reports in the Security & Compliance Center. By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="d0243-p104">此外，您必須指定給在 EAC 中檢視 DLP 報告中 EAC View-Only 收件者角色。根據預設，此角色指派給在 EAC 中相符性管理、 組織管理及 View-Only Organization Management 角色群組。</span><span class="sxs-lookup"><span data-stu-id="d0243-p104">Additionally, you have to be assigned the View-Only Recipients role in the EAC to view DLP reports in the EAC. By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the EAC.</span></span>
  
 <span data-ttu-id="d0243-117">**若要開啟 [檢視報告] 頁面的安全性 & 規範中心中：**</span><span class="sxs-lookup"><span data-stu-id="d0243-117">**To open the View reports page in the Security & Compliance Center:**</span></span>
  
1. <span data-ttu-id="d0243-118">請移至 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。</span><span class="sxs-lookup"><span data-stu-id="d0243-118">Go to [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).</span></span>
    
2. <span data-ttu-id="d0243-119">登入 Office 365 使用 Office 365 組織中的使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="d0243-119">Sign in to Office 365 using the credentials for a user account in your Office 365 organization.</span></span>
    
<span data-ttu-id="d0243-120">在**檢視報告**」 頁面上，您可以檢視下列類型的報告：</span><span class="sxs-lookup"><span data-stu-id="d0243-120">On the **View reports** page, you can view the following types of reports:</span></span> 
  
- [<span data-ttu-id="d0243-121">EOP 中的稽核報告</span><span class="sxs-lookup"><span data-stu-id="d0243-121">Auditing reports</span></span>](#auditing-reports)
- [<span data-ttu-id="d0243-122">監督檢閱報告</span><span class="sxs-lookup"><span data-stu-id="d0243-122">Supervisory review report</span></span>](#supervisory-review-report)
- [<span data-ttu-id="d0243-123">資料外洩防護報告</span><span class="sxs-lookup"><span data-stu-id="d0243-123">Data loss prevention reports</span></span>](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a><span data-ttu-id="d0243-124">稽核報告</span><span class="sxs-lookup"><span data-stu-id="d0243-124">Auditing reports</span></span>

<span data-ttu-id="d0243-125">下表說明安全性 & 規範中心**檢視報告**] 頁面的 [**稽核**] 區段中報告。</span><span class="sxs-lookup"><span data-stu-id="d0243-125">The following table describes the reports in the **Auditing** section on the **View reports** page in the Security & Compliance Center.</span></span> 
  
|<span data-ttu-id="d0243-126">**[報告]**</span><span class="sxs-lookup"><span data-stu-id="d0243-126">**Report**</span></span>|<span data-ttu-id="d0243-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="d0243-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d0243-128">**Office 365 稽核記錄報告**</span><span class="sxs-lookup"><span data-stu-id="d0243-128">**Office 365 audit log report**</span></span> <br/> |<span data-ttu-id="d0243-p105">您可以在 Office 365 組織中搜尋使用者與系統管理活動的 Office 365 稽核記錄。報表會包含項目使用者和系統活動在 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Azure Active Directory，這是 Office 365 的目錄服務。如需詳細資訊，請參閱 ＜[的搜尋稽核登入 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="d0243-p105">You can search the Office 365 audit log for user and admin activity in your Office 365 organization. The report contains entries user and admin activity in Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory, which is the directory service for Office 365. For more information, see [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).  </span></span><br/> |
|<span data-ttu-id="d0243-132">**Azure AD 報告**</span><span class="sxs-lookup"><span data-stu-id="d0243-132">**Azure AD reports**</span></span> <br/> |<span data-ttu-id="d0243-p106">要尋找不尋常或可疑登入活動的 Office 365 組織中，您可以使用登入及活動 Microsoft Azure 中的報告。您也可以在 Azure AD 稽核記錄檔檢視事件。若要在 Azure 中檢視報表，只要按一下**檢視 Azure AD 報表**。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d0243-p106">To look for unusual or suspicious sign-in activity in your Office 365 organization, you can use sign-in and activity reports in Microsoft Azure. You can also view events in the Azure AD audit log. To view reports in Azure, just click **View Azure AD reports**. For more information, see: </span></span><br/><br/><span data-ttu-id="d0243-137">[使用您在 Office 365 中可用的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d0243-137">[Use your free Azure Active Directory subscription in Office 365](use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <br/> <span data-ttu-id="d0243-138">[檢視您存取及使用狀況報告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。</span><span class="sxs-lookup"><span data-stu-id="d0243-138">[View your access and usage reports](http://go.microsoft.com/fwlink/p/?LinkId=506902).</span></span>  <br/> |
|<span data-ttu-id="d0243-139">**Exchange 稽核報告**</span><span class="sxs-lookup"><span data-stu-id="d0243-139">**Exchange audit reports**</span></span> <br/> | <span data-ttu-id="d0243-p107">您可以使用 Office 365 中的稽核功能追蹤對您的 Exchange Online 設定組織的系統管理員所做的變更。由 Microsoft 資料中心管理員或委派的管理員對您的 Exchange Online 組織也會記錄的變更。Exchange online，系統管理員稽核記錄已啟用根據預設，因此您不需要執行任何動作加以開啟。Exchange Online 也提供信箱稽核記錄功能讓您追蹤對信箱的信箱擁有者以外的其他人存取。您必須針對每一個您想要追蹤非擁有者存取的信箱啟用信箱稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="d0243-p107">You can use the auditing functionality in Office 365 to track changes made to your Exchange Online configuration by your organization's administrators. Changes made to your Exchange Online organization by a Microsoft data center administrator or by a delegated administrator are also logged. For Exchange Online, administrator audit logging is enabled by default, so you don't have to do anything to turn it on. Exchange Online also provides mailbox audit logging to let you track access to mailboxes by someone other than the mailbox owner. You have to enable mailbox audit logging for each mailbox that you want to track non-owner access.  </span></span><br/>  <span data-ttu-id="d0243-p108">系統管理和信箱稽核記錄，您可以執行稽核報告] 檢視稽核記錄項目。您也可以匯出信箱並管理稽核記錄，這 24 小時內的 XML 檔案附加至電子郵件傳送給您。</span><span class="sxs-lookup"><span data-stu-id="d0243-p108">For both admin and mailbox audit logging, you can run audit reports to view the audit log entries. You can also export mailbox and admin audit logs, which are sent to you within 24 hours in an XML file that is attached to email message. </span></span><br/><br/><span data-ttu-id="d0243-147">如需匯出稽核記錄的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d0243-147">For more information about exporting audit logs, see:</span></span>  <br/><br/> [<span data-ttu-id="d0243-148">匯出信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="d0243-148">Export mailbox audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [<span data-ttu-id="d0243-149">檢視和匯出資料中心管理稽核記錄</span><span class="sxs-lookup"><span data-stu-id="d0243-149">View and export the datacenter admin audit log</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [<span data-ttu-id="d0243-150">搜尋角色群組變更或管理員稽核記錄檔</span><span class="sxs-lookup"><span data-stu-id="d0243-150">Search the role group changes or administrator audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   <span data-ttu-id="d0243-151">[Exchange 稽核報告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。</span><span class="sxs-lookup"><span data-stu-id="d0243-151">[Exchange auditing reports](http://go.microsoft.com/fwlink/p/?LinkID=395232).</span></span>  <br/> |
   
## <a name="supervisory-review-report"></a><span data-ttu-id="d0243-152">監督檢閱報告</span><span class="sxs-lookup"><span data-stu-id="d0243-152">Supervisory review report</span></span>

<span data-ttu-id="d0243-p109">搭配監督檢閱報告，您可以在組織中看到監督檢閱的所有原則的狀態。如需詳細資訊，請參閱 ＜ [Configure 監督檢閱您的組織的原則](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d0243-p109">With the supervisory review report, you can see the status of all the supervisory review policies in your organization. For more information, see [Configure supervisory review policies for your organization](configure-supervision-policies.md).</span></span>
  
## <a name="data-loss-prevention-reports"></a><span data-ttu-id="d0243-155">資料外洩防護報告</span><span class="sxs-lookup"><span data-stu-id="d0243-155">Data loss prevention reports</span></span>

<span data-ttu-id="d0243-p110">資料外洩防護 (DLP) 報告包含 DLP 原則的相關資訊及規則已套用至內容包含在 Office 365 組織中的機密資料。您也可以設定報表以顯示已根據您的 DLP 原則和規則的 DLP 動作的相關資訊。如需詳細資訊，請參閱 ＜[資料外洩防護報告] 檢視](view-the-dlp-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="d0243-p110">Data loss prevention (DLP) reports contain information about the DLP policies and rules that have been applied to content contain sensitive data in your Office 365 organization. You can also configure the report to display information about DLP actions that were based on your DLP policy and rules. For more information, see [View the report for data loss prevention](view-the-dlp-reports.md).</span></span>
