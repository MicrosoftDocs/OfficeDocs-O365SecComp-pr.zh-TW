---
title: Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/11/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全的連結功能所提供 Office 文件和電子郵件訊息中的超連結的時間按一下 [的驗證。若要從網路釣魚和其他攻擊保護您的組織使用安全的連結。
ms.openlocfilehash: 4d83aa65af47ea6723d6e2042c230fb2b07c174c
ms.sourcegitcommit: 065f5e72676511b5ecf7f10a17685999780e92d8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29888029"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="f9a12-104">Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="f9a12-104">Office 365 ATP Safe Links</span></span>

## <a name="overview-of-office-365-atp-safe-links"></a><span data-ttu-id="f9a12-105">Overview of Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="f9a12-105">Overview of Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9a12-p102">本文適用於企業客戶的。如果您是家庭使用者尋找關於在 Outlook 中的安全連結的資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f9a12-p103">Office 365 ATP 安全連結 （[進階威脅保護](office-365-atp.md)的一部分） 可協助保護您的組織所提供的[電子郵件](#how-atp-safe-links-works-with-email)和[Office 文件](#how-atp-safe-links-works-with-office-documents)中的網址 (Url) 的時間按一下 [驗證。保護是透過[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定 Office 365 安全性小組的定義。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p103">Office 365 ATP Safe Links (part of [Advanced Threat Protection](office-365-atp.md)) can help protect your organization by providing time-of-click verification of web addresses (URLs) in [email messages](#how-atp-safe-links-works-with-email) and [Office documents](#how-atp-safe-links-works-with-office-documents). Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="f9a12-p104">一旦您 ATP 安全連結原則已備妥、 Office 365 全域管理員、 安全性管理員及安全性讀取者可以在[進階威脅保護的檢視報告](view-reports-for-atp.md)。這些報告中的資訊可協助您需要進一步的步驟來保護您的組織或研究安全性事件的安全性小組。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p104">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>

<span data-ttu-id="f9a12-p105">為[新的功能會新增至 ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp)，您的 Office 365 安全性小組可以新增或編輯您的組織 ATP 安全連結的原則。此外，您可能會注意到的變更與改良功能，例如我們新修訂的[警告頁面](atp-safe-links-warning-pages.md)並呈現在 Outlook 中的原生連結。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p105">As [new features are added to ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp), your Office 365 security team can add or edit your organization's ATP Safe Links policies. In addition, you might notice changes and improvements, such as our newly revised [warning pages](atp-safe-links-warning-pages.md) and native link rendering in Outlook.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="f9a12-114">ATP 安全連結中的運作方式與 Url 電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9a12-114">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="f9a12-115">在高層級，以下是 ATP 安全連結 protection 中的運作方式的 Url （架設在 Office 365 中，不在內部部署） 的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="f9a12-115">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="f9a12-116">人員接收電子郵件訊息，部份只包含 Url。</span><span class="sxs-lookup"><span data-stu-id="f9a12-116">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="f9a12-117">所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選、 簽章型惡意程式碼保護，反垃圾郵件和反惡意軟體篩選器會套用。</span><span class="sxs-lookup"><span data-stu-id="f9a12-117">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="f9a12-118">電子郵件會進入人的收件匣。</span><span class="sxs-lookup"><span data-stu-id="f9a12-118">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="f9a12-119">使用者登入 Office 365 中，並移至其電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="f9a12-119">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="f9a12-120">使用者開啟電子郵件訊息，並按一下在電子郵件訊息的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9a12-120">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="f9a12-p106">ATP 安全連結功能立即檢查才能開啟之網站的 URL。為封鎖惡意或安全可識別的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p106">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="f9a12-123">如果 URL 包含在[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f9a12-123">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="f9a12-124">如果組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL，[警告] 頁面](atp-safe-links-warning-pages.md)隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f9a12-124">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="f9a12-125">如果已決定要惡意的網站 URL，[警告] 頁面](atp-safe-links-warning-pages.md)隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f9a12-125">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="f9a12-126">如果您的組織[ATP 安全連結原則](set-up-atp-safe-links-policies.md)中已掃描這類內容和 URL 會前往可下載的檔案，則會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="f9a12-126">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="f9a12-127">如果 URL 決定要安全，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f9a12-127">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="f9a12-128">ATP 安全連結中的運作方式與 Url 的 Office 文件</span><span class="sxs-lookup"><span data-stu-id="f9a12-128">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="f9a12-129">在高層級，以下是 ATP 安全連結 protection 中的運作方式 Url 的 Office 365 ProPlus 應用程式 （Word、 Excel 及 PowerPoint Windows 或 Mac 上 iOS 或 Android 裝置、 Windows、 OneNote Online 與 Office Online 上的 Visio 的 Office 應用程式上的目前版本）：</span><span class="sxs-lookup"><span data-stu-id="f9a12-129">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="f9a12-p107">人員在其電腦、 智慧型手機、 或平板電腦上安裝 Office 365 ProPlus。（或者，使用 Office Online 在其瀏覽器）。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p107">People have installed Office 365 ProPlus on their computer, smartphone, or tablet. (Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="f9a12-p108">使用者開啟 Word、 Excel、 PowerPoint 或 Visio 並登入 Office 365 企業版使用其工作或學校的帳戶。文件包含 Url。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p108">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="f9a12-134">當使用者按一下在文件中的 URL 時、 連結會檢查 ATP 安全連結服務。</span><span class="sxs-lookup"><span data-stu-id="f9a12-134">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="f9a12-135">如果 URL 包含在[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者會對網站進行。</span><span class="sxs-lookup"><span data-stu-id="f9a12-135">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="f9a12-136">如果組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL，使用者會前往[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-136">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="f9a12-137">如果已決定要惡意的網站 URL，使用者會前往[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-137">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="f9a12-138">如果[ATP 安全連結原則](set-up-atp-safe-links-policies.md)中已掃描這類下載項目和 URL 會前往可下載的檔案，則會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="f9a12-138">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="f9a12-139">如果 URL 會被視為安全，使用者會進行瀏覽網站。</span><span class="sxs-lookup"><span data-stu-id="f9a12-139">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="f9a12-140">如何取得 ATP 安全連結保護</span><span class="sxs-lookup"><span data-stu-id="f9a12-140">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="f9a12-p109">首先，請確定您的訂閱包括[進階威脅保護](office-365-atp.md)。ATP 隨附於中訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p109">First, make sure your subscription includes [Advanced Threat Protection](office-365-atp.md). ATP is included in in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 
  
<span data-ttu-id="f9a12-p110">接下來，請確定您 ATP 安全連結原則所定義。（請參閱[Set up Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)）。ATP 安全連結功能已啟用：</span><span class="sxs-lookup"><span data-stu-id="f9a12-p110">Next, make sure your ATP Safe Links policies are defined. (See [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).) ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="f9a12-p111">**ATP 安全連結原則已設定**用於電子郵件和 Word、 Excel、 PowerPoint 及 Visio 文件。（請參閱[Set up ATP Office 365 中的安全連結原則](set-up-atp-safe-links-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p111">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="f9a12-p112">**Office 365 用戶端應用程式設定為使用經過驗證**（這是 Office 文件中的 ATP 安全連結保護）。（請參閱[Office 2016 現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)）。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p112">**Office 365 client apps are configured to use Modern Authentication** (this is for ATP Safe Links protection in Office documents). (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="f9a12-p113">**使用者已登入 Office 365**使用其工作或學校的帳戶。（請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p113">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="f9a12-152">**貴組織的電子郵件通過 Exchange Online Protection**。</span><span class="sxs-lookup"><span data-stu-id="f9a12-152">**Your organization's email passes through Exchange Online Protection**.</span></span>  

<span data-ttu-id="f9a12-153">若要定義 （或編輯） ATP 原則，您必須具有角色如下表所示的其中一個：</span><span class="sxs-lookup"><span data-stu-id="f9a12-153">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="f9a12-154">角色</span><span class="sxs-lookup"><span data-stu-id="f9a12-154">Role</span></span>  |<span data-ttu-id="f9a12-155">Where/如何指派</span><span class="sxs-lookup"><span data-stu-id="f9a12-155">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="f9a12-156">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="f9a12-156">Office 365 Global Administrator</span></span> |<span data-ttu-id="f9a12-p114">若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p114">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="f9a12-159">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="f9a12-159">Security Administrator</span></span> |<span data-ttu-id="f9a12-160">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="f9a12-160">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="f9a12-161">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="f9a12-161">Exchange Online Organization Management</span></span> |<span data-ttu-id="f9a12-162">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="f9a12-162">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="f9a12-163">或</span><span class="sxs-lookup"><span data-stu-id="f9a12-163">or</span></span> <br>  <span data-ttu-id="f9a12-164">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="f9a12-164">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="f9a12-165">如何讓確定 ATP 安全連結保護已備妥</span><span class="sxs-lookup"><span data-stu-id="f9a12-165">How to make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="f9a12-p115">以全域管理員或安全性管理員，請務必檢閱您[ATP 安全連結原則](set-up-atp-safe-links-policies.md)。ATP 安全連結原則會決定是否保護適用於電子郵件訊息中有超連結只或 Url 中的 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p115">As a global administrator or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

<span data-ttu-id="f9a12-168">貴組織的安全性小組 ATP 安全連結原則已備妥之後，可以看到您的組織由[Advanced 威脅保護的檢視報告](view-reports-for-atp.md)ATP 安全連結保護正常運作的方式，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f9a12-168">After ATP Safe Links policies are in place, your organization's security team can see see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span> 

## <a name="example-scenarios"></a><span data-ttu-id="f9a12-169">範例案例</span><span class="sxs-lookup"><span data-stu-id="f9a12-169">Example scenarios</span></span>
  
<span data-ttu-id="f9a12-p116">下表說明 ATP 安全連結保護可能的位置或備妥可能不是幾個案例。（在所有這些情況下，我們假設組織有 Office 365 企業版 E5。）</span><span class="sxs-lookup"><span data-stu-id="f9a12-p116">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="f9a12-172">**範例案例**</span><span class="sxs-lookup"><span data-stu-id="f9a12-172">**Example scenario**</span></span>|<span data-ttu-id="f9a12-173">**ATP 安全連結保護沒有在此例中套用吗？**</span><span class="sxs-lookup"><span data-stu-id="f9a12-173">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9a12-p117">Jean 是群組的有 ATP 安全連結原則涵蓋 Url 電子郵件和 Office 文件中的成員。Jean 有人傳送，開啟 PowerPoint 簡報，然後按一下 [在簡報中的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p117">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a PowerPoint presentation that someone sent, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="f9a12-p118">[是]。定義 ATP 安全連結原則套用至 Jean 的群組、 Jean 的電子郵件、 和 Jean 隨即開啟，只要 Jean 登入的 Word、 Excel、 PowerPoint 或 Visio 文件及 Windows、 iOS 或 Android 裝置上使用 Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p118">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="f9a12-p119">Chris 的組織，不通用或安全性管理員已尚未定義任何 ATP 安全連結原則。Chris 會收到電子郵件包含惡意網站的 URL。Chris 會察覺不到 URL 為惡意並按一下連結。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p119">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="f9a12-p120">[否]。針對在組織中所有人涵蓋 Url 的預設原則必須定義備妥要保護的順序。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p120">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="f9a12-p121">Pat 的組織，不通用或安全性管理員已定義或尚未編輯的任何 ATP 安全連結原則。Pat 開啟 Word 文件並按一下檔案中的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p121">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="f9a12-p122">包含 Office 文件的 [否]。 的原則必須定義備妥要保護的順序。請參閱 ＜ [Set up Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p122">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="f9a12-p123">Lee 的組織具有的 ATP 安全連結原則`http://tailspintoys.com`列為封鎖網站。Lee 接收電子郵件訊息內含 URL `http://tailspintoys.com/aboutus/trythispage`。Lee 點選 URL。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p123">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="f9a12-p124">整個網站與所有的清單中包括它的子頁面是否封鎖 Url 而定。請參閱 ＜ [Set up 自訂封鎖 Url 清單使用 ATP 安全的連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p124">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="f9a12-193">李明、 Jean 的同事將電子郵件傳送至 Jean、 不知道電子郵件包含惡意 URL。</span><span class="sxs-lookup"><span data-stu-id="f9a12-193">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="f9a12-p125">針對在組織內傳送的電子郵件是否定義 ATP 安全連結原則而定。請參閱 ＜ [Set up Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a12-p125">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |


  

