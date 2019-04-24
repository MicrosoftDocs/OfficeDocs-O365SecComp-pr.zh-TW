---
title: Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 03/05/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全連結功能提供 Office 文件和電子郵件訊息中的超連結的時間按一下 [的驗證。 若要從網路釣魚和其他攻擊保護您的組織使用安全連結。
ms.openlocfilehash: 7dacb4184ff0b99887b2aa5f3fe2e65cd58c5b6b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32249553"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="31643-104">Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="31643-104">Office 365 ATP Safe Links</span></span>

## <a name="overview-of-office-365-atp-safe-links"></a><span data-ttu-id="31643-105">Office 365 ATP 安全連結概觀</span><span class="sxs-lookup"><span data-stu-id="31643-105">Overview of Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31643-106">本文適用於 Office 365 企業版客戶。</span><span class="sxs-lookup"><span data-stu-id="31643-106">This article is intended for Office 365 Enterprise customers.</span></span> <span data-ttu-id="31643-107">如果您使用 Outlook.com、 Office 365 家用版、 Office 365 個人或，而且您正在尋找在 Outlook 中的安全連結的相關資訊，請參閱 <<c0>進階 Outlook.com 安全性。</span><span class="sxs-lookup"><span data-stu-id="31643-107">If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="31643-108">Office 365 ATP 安全連結 （[進階威脅防護](office-365-atp.md)的一部分） 可協助保護您的組織藉由提供的[電子郵件](#how-atp-safe-links-works-with-urls-in-email)和[Office 文件](#how-atp-safe-links-works-with-urls-in-office-documents)中的網址 (Url) 的時間按一下 [驗證。</span><span class="sxs-lookup"><span data-stu-id="31643-108">Office 365 ATP Safe Links (part of [Advanced Threat Protection](office-365-atp.md)) can help protect your organization by providing time-of-click verification of web addresses (URLs) in [email messages](#how-atp-safe-links-works-with-urls-in-email) and [Office documents](#how-atp-safe-links-works-with-urls-in-office-documents).</span></span> <span data-ttu-id="31643-109">保護是透過[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定 Office 365 安全性小組的定義。</span><span class="sxs-lookup"><span data-stu-id="31643-109">Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="31643-110">一旦您 ATP 安全連結原則已備妥，Office 365 全域系統管理員、 安全性管理員和安全性讀取者可以[檢視報告，進階威脅防護](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-110">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span> <span data-ttu-id="31643-111">這些報告中的資訊可協助您採取進一步的步驟，以保護您的組織或研究安全性事件的安全性小組。</span><span class="sxs-lookup"><span data-stu-id="31643-111">The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>

<span data-ttu-id="31643-112">為[ATP 會新增新的功能](office-365-atp.md#new-features-in-office-365-atp)，您的 Office 365 安全性小組可以新增或編輯您的組織[ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-112">As [new features are added to ATP](office-365-atp.md#new-features-in-office-365-atp), your Office 365 security team can add or edit your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> <span data-ttu-id="31643-113">此外，您可能會注意到的變更和增強功能，例如我們新修訂的[警告頁面](atp-safe-links-warning-pages.md)以及在 Outlook 中呈現的原生連結。</span><span class="sxs-lookup"><span data-stu-id="31643-113">In addition, you might notice changes and improvements, such as our newly revised [warning pages](atp-safe-links-warning-pages.md) and native link rendering in Outlook.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="31643-114">ATP 安全連結的運作方式與 Url 以電子郵件</span><span class="sxs-lookup"><span data-stu-id="31643-114">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="31643-115">在高的層級，以下是 ATP 安全連結保護中的運作方式的 Url （裝載於 Office 365，不在內部） 的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="31643-115">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="31643-116">人員會收到電子郵件訊息，其中有些包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="31643-116">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="31643-117">所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選，簽章型惡意程式碼防護，反垃圾郵件和反惡意軟體篩選器。</span><span class="sxs-lookup"><span data-stu-id="31643-117">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="31643-118">電子郵件會送達人民收件匣。</span><span class="sxs-lookup"><span data-stu-id="31643-118">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="31643-119">使用者登入 Office 365，並移至其電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="31643-119">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="31643-120">使用者開啟電子郵件訊息，並按一下電子郵件訊息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-120">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="31643-121">ATP 安全連結功能立即檢查才能開啟之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-121">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="31643-122">URL 被識別為惡意，/ 安全封鎖。</span><span class="sxs-lookup"><span data-stu-id="31643-122">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="31643-123">如果 URL 包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="31643-123">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="31643-124">組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-124">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="31643-125">已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-125">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="31643-126">如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="31643-126">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="31643-127">如果 URL 會決定為了安全起見，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="31643-127">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="31643-128">ATP 安全連結的運作方式與 Url 中的 Office 文件</span><span class="sxs-lookup"><span data-stu-id="31643-128">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="31643-129">在高的層級，以下是 ATP 安全連結保護中的運作方式 Url 的 Office 365 專業增強版應用程式 （目前版本的 Word、 Excel 及 PowerPoint Windows 或 Mac、 iOS 或 Android 裝置，Visio 在 Windows、 OneNote Online 和 Office Online 上的 Office 應用程式上）：</span><span class="sxs-lookup"><span data-stu-id="31643-129">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="31643-130">人員在其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="31643-130">People have installed Office 365 ProPlus on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="31643-131">（或者，他們會使用 Office Online 在其瀏覽器中）。</span><span class="sxs-lookup"><span data-stu-id="31643-131">(Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="31643-132">使用者開啟 Word、 Excel、 PowerPoint 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="31643-132">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="31643-133">文件中包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="31643-133">The document contains URLs.</span></span>
    
3. <span data-ttu-id="31643-134">當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。</span><span class="sxs-lookup"><span data-stu-id="31643-134">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="31643-135">如果 URL 是包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="31643-135">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="31643-136">URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-136">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="31643-137">如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-137">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="31643-138">如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="31643-138">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="31643-139">URL 會被視為安全，如果使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="31643-139">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="31643-140">如何取得 ATP 安全連結保護</span><span class="sxs-lookup"><span data-stu-id="31643-140">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="31643-141">**首先，請確定您的訂閱包含[進階威脅防護](office-365-atp.md)**。</span><span class="sxs-lookup"><span data-stu-id="31643-141">**First, make sure your subscription includes [Advanced Threat Protection](office-365-atp.md)**.</span></span> <span data-ttu-id="31643-142">ATP 隨附於在 [訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果貴組織擁有不包含 Office 365 ATP 的 Office 365 訂閱，您可能可以當作附加元件購買 ATP。</span><span class="sxs-lookup"><span data-stu-id="31643-142">ATP is included in in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="31643-143">如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="31643-143">For more information, see the following resources:</span></span> 

- [<span data-ttu-id="31643-144">Office 365 進階威脅防護方案和價格</span><span class="sxs-lookup"><span data-stu-id="31643-144">Office 365 Advanced Threat Protection plans and pricing</span></span>](https://products.office.com/exchange/advance-threat-protection)

- [<span data-ttu-id="31643-145">Office 365 進階威脅防護服務說明</span><span class="sxs-lookup"><span data-stu-id="31643-145">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
<span data-ttu-id="31643-146">**接下來，確定已定義的 ATP 安全連結原則**。</span><span class="sxs-lookup"><span data-stu-id="31643-146">**Next, make sure your ATP Safe Links policies are defined**.</span></span> <span data-ttu-id="31643-147">（請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)）。ATP 安全連結功能已啟用：</span><span class="sxs-lookup"><span data-stu-id="31643-147">(See [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).) ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="31643-148">ATP 安全連結原則設定電子郵件和 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="31643-148">ATP Safe Links policies are set up for email and for Office documents.</span></span> <span data-ttu-id="31643-149">（請參閱[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="31643-149">(See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="31643-150">Office 365 用戶端應用程式都設定為使用新式驗證 （這是在 Office 文件中的 ATP 安全連結保護）。</span><span class="sxs-lookup"><span data-stu-id="31643-150">Office 365 client apps are configured to use Modern Authentication (this is for ATP Safe Links protection in Office documents).</span></span> <span data-ttu-id="31643-151">（請參閱[適用於 Office 2016 的新式驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)）。</span><span class="sxs-lookup"><span data-stu-id="31643-151">(See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="31643-152">使用者已登入 Office 365 中，使用其公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="31643-152">Users have signed into Office 365 using their work or school account.</span></span> <span data-ttu-id="31643-153">（請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="31643-153">(See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="31643-154">貴組織的電子郵件通過 Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="31643-154">Your organization's email passes through Exchange Online Protection.</span></span>  

<span data-ttu-id="31643-155">**也請確定您具有必要權限**。</span><span class="sxs-lookup"><span data-stu-id="31643-155">**Also make sure you have the necessary permissions**.</span></span> <span data-ttu-id="31643-156">若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="31643-156">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="31643-157">下表說明一些範例：</span><span class="sxs-lookup"><span data-stu-id="31643-157">Some examples are described in the following table:</span></span>

|<span data-ttu-id="31643-158">角色</span><span class="sxs-lookup"><span data-stu-id="31643-158">Role</span></span>  |<span data-ttu-id="31643-159">位置/方式指派</span><span class="sxs-lookup"><span data-stu-id="31643-159">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="31643-160">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="31643-160">Office 365 Global Administrator</span></span> |<span data-ttu-id="31643-161">若要購買 Office 365 註冊的人員是預設的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="31643-161">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="31643-162">（請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。</span><span class="sxs-lookup"><span data-stu-id="31643-162">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="31643-163">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="31643-163">Security Administrator</span></span> |<span data-ttu-id="31643-164">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="31643-164">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="31643-165">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="31643-165">Exchange Online Organization Management</span></span> |<span data-ttu-id="31643-166">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="31643-166">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="31643-167">或</span><span class="sxs-lookup"><span data-stu-id="31643-167">or</span></span> <br>  <span data-ttu-id="31643-168">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="31643-168">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="31643-169">如何讓確定 ATP 安全連結保護已經準備就緒</span><span class="sxs-lookup"><span data-stu-id="31643-169">How to make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="31643-170">以全域管理員或安全性系統管理員，請務必定期檢閱您的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="31643-170">As a global administrator or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) regularly.</span></span> <span data-ttu-id="31643-171">ATP 安全連結原則決定是否保護套用至電子郵件訊息中的超連結只，或 Url Office 文件中。</span><span class="sxs-lookup"><span data-stu-id="31643-171">ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

<span data-ttu-id="31643-172">ATP 安全連結原則已備妥之後，可以看到貴組織的安全性小組您的組織由[進階威脅防護的檢視報表](view-reports-for-atp.md)ATP 安全連結保護正常運作的方式，請參閱。</span><span class="sxs-lookup"><span data-stu-id="31643-172">After ATP Safe Links policies are in place, your organization's security team can see see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span> 

## <a name="example-scenarios"></a><span data-ttu-id="31643-173">範例案例</span><span class="sxs-lookup"><span data-stu-id="31643-173">Example scenarios</span></span>
  
<span data-ttu-id="31643-174">下表說明 ATP 安全連結保護其中可能或可能無法就地幾個案例。</span><span class="sxs-lookup"><span data-stu-id="31643-174">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place.</span></span> <span data-ttu-id="31643-175">（在所有這些情況下，我們假設該組織有 Office 365 企業版 E5。）</span><span class="sxs-lookup"><span data-stu-id="31643-175">(In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="31643-176">**範例案例**</span><span class="sxs-lookup"><span data-stu-id="31643-176">**Example scenario**</span></span>|<span data-ttu-id="31643-177">**ATP 安全連結保護不會在此情況下套用嗎？**</span><span class="sxs-lookup"><span data-stu-id="31643-177">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="31643-178">Jean 是群組的有涵蓋 Url 電子郵件和 Office 文件中的 ATP 安全連結原則成員。</span><span class="sxs-lookup"><span data-stu-id="31643-178">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents.</span></span> <span data-ttu-id="31643-179">Jean 有人傳送時，開啟 PowerPoint 簡報，然後按一下 [在簡報中的 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-179">Jean opens a PowerPoint presentation that someone sent, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="31643-180">是。</span><span class="sxs-lookup"><span data-stu-id="31643-180">Yes.</span></span> <span data-ttu-id="31643-181">所定義的 ATP 安全連結原則套用到 Jean 的群組、 Jean 的電子郵件，並 Jean 隨即開啟，只要 Jean 登入的 Word、 Excel、 PowerPoint 或 Visio 文件和 Windows、 iOS 或 Android 裝置上使用 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="31643-181">The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="31643-182">Chris 的組織，不全域或安全性中的系統管理員已尚未定義任何 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="31643-182">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet.</span></span> <span data-ttu-id="31643-183">Chris 會收到一封電子郵件包含惡意網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-183">Chris receives an email that contains a URL to a malicious website.</span></span> <span data-ttu-id="31643-184">Chris 是察覺不到 URL 為惡意，並按下的連結。</span><span class="sxs-lookup"><span data-stu-id="31643-184">Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="31643-185">否。</span><span class="sxs-lookup"><span data-stu-id="31643-185">No.</span></span> <span data-ttu-id="31643-186">對組織中的每個人都涵蓋 Url 的預設原則必須定義要就地保護的順序。</span><span class="sxs-lookup"><span data-stu-id="31643-186">The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="31643-187">在 Pat 的組織，不全域或安全性系統管理員已定義，或尚未編輯任何 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="31643-187">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet.</span></span> <span data-ttu-id="31643-188">Pat 開啟 Word 文件，並按一下 [在檔案中的 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-188">Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="31643-189">否。</span><span class="sxs-lookup"><span data-stu-id="31643-189">No.</span></span> <span data-ttu-id="31643-190">原則，其中包含 Office 文件必須定義要就地保護的順序。</span><span class="sxs-lookup"><span data-stu-id="31643-190">A policy that includes Office documents must be defined in order for protection to be in place.</span></span> <span data-ttu-id="31643-191">請參閱 <<c0>設定 Office 365 中的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="31643-191">See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).</span></span>  <br/> |
|<span data-ttu-id="31643-192">Lee 的組織已有的 ATP 安全連結原則`http://tailspintoys.com`列為遭到封鎖的網站。</span><span class="sxs-lookup"><span data-stu-id="31643-192">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website.</span></span> <span data-ttu-id="31643-193">Lee 收到電子郵件訊息包含的 URL `http://tailspintoys.com/aboutus/trythispage`。</span><span class="sxs-lookup"><span data-stu-id="31643-193">Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="31643-194">Lee 按一下 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-194">Lee clicks the URL.</span></span>  <br/> |<span data-ttu-id="31643-195">這取決於是否整個網站及其所有的清單中包含它的子頁面封鎖 Url。</span><span class="sxs-lookup"><span data-stu-id="31643-195">It depends on whether the entire site and all its subpages are included in the list of blocked URLs.</span></span> <span data-ttu-id="31643-196">請參閱 <<c0>設定自訂封鎖 Url 清單使用 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="31643-196">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>  <br/> |
|<span data-ttu-id="31643-197">李明，Jean 的同事，將電子郵件傳送至 Jean，不了解電子郵件包含惡意 URL。</span><span class="sxs-lookup"><span data-stu-id="31643-197">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="31643-198">這取決於是否 ATP 安全連結原則所定義的組織內傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="31643-198">It depends on whether ATP Safe Links policies are defined for email sent within the organization.</span></span> <span data-ttu-id="31643-199">請參閱 <<c0>設定 Office 365 中的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="31643-199">See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).</span></span>  <br/> |


  

