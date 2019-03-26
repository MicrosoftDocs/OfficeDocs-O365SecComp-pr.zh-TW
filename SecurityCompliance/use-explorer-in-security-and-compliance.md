---
title: 使用中的安全性威脅總管&amp;合規性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解 （也稱為威脅總管） 的瀏覽器安全性&amp;合規性中心。
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732256"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="587a2-103">使用中的安全性威脅總管&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="587a2-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="587a2-104">如果您的組織有[Office 365 進階威脅防護計劃 2](office-365-ti.md)，而且您具有必要權限，您可以使用威脅總管來識別和分析潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="587a2-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), and you have the necessary permissions, you can use Threat Explorer to identify and analyze threats.</span></span> <span data-ttu-id="587a2-105">例如，您可以識別並刪除惡意電子郵件已傳遞，或請參閱 Office 365 安全性功能所攔截惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="587a2-105">For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features.</span></span> <span data-ttu-id="587a2-106">威脅總管 （也稱為 Explorer）] 是功能強大的接近即時的工具，以協助調查及回應安全性威脅的安全性作業小組&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="587a2-106">Threat Explorer (also referred to as Explorer) is a powerful near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span>
  
![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="587a2-108">若要使用檔案總管中，安全性&amp;合規性中心，移至**威脅管理** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="587a2-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="587a2-109">Office 365 威脅情報現在是 Office 365 進階威脅防護計劃 2，以及其他威脅保護功能。</span><span class="sxs-lookup"><span data-stu-id="587a2-109">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="587a2-110">若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="587a2-110">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="587a2-111">Explorer 概觀</span><span class="sxs-lookup"><span data-stu-id="587a2-111">Explorer overview</span></span>

<span data-ttu-id="587a2-112">如果您的組織有[Office 365 威脅調查及回應功能](office-365-ti.md)（隨附於 ATP 計劃 2），而且您具有必要權限，您可以使用威脅總管 （也稱為總管） 來識別和分析潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="587a2-112">If your organization has [Office 365 Threat investigation and response capabilities](office-365-ti.md) (this is included in ATP Plan 2), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="587a2-113">(安全性&amp;合規性中心，移至**威脅管理** \> **總管**。)</span><span class="sxs-lookup"><span data-stu-id="587a2-113">(In the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="587a2-115">本文說明您可以運用檔案總管的一些事項 （有許多更多的可能性）：</span><span class="sxs-lookup"><span data-stu-id="587a2-115">This article describes a few things you can do with Explorer (there are many more possibilities):</span></span>

- <span data-ttu-id="587a2-116">[請參閱電子郵件中偵測到惡意程式碼何種](#see-malware-detected-in-email-by-technology)，和威脅防護技術 (反惡意程式碼防護，ATP 安全附件，等等。)</span><span class="sxs-lookup"><span data-stu-id="587a2-116">[See what kinds of malware were detected in email](#see-malware-detected-in-email-by-technology), and by threat protection technology (anti-malware protection, ATP Safe Attachments, etc.)</span></span>

- <span data-ttu-id="587a2-117">[檢視關於網路釣魚連結 (Url) 的資料](#view-data-about-phishing-urls-and-click-verdict)，且哪些按一下 [結果 (Url 封鎖、 允許，或造訪儘管警告)</span><span class="sxs-lookup"><span data-stu-id="587a2-117">[View data about phishing links (URLs)](#view-data-about-phishing-urls-and-click-verdict), and what the click verdicts were (URLs blocked, allowed, or visited despite warnings)</span></span>

- <span data-ttu-id="587a2-118">[檢閱電子郵件訊息，已回報為垃圾郵件，不是垃圾郵件或網路釣魚](#review-email-messages-reported-by-users)，並識別任何趨勢 (例如 a 大於郵件報告為釣魚程式的一般數目)</span><span class="sxs-lookup"><span data-stu-id="587a2-118">[Review email messages that were reported as Junk, Not Junk, or Phishing](#review-email-messages-reported-by-users), and identify any trends (such as a larger than usual number of messages reported as Phish)</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="587a2-119">請參閱技術電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="587a2-119">See malware detected in email by technology</span></span>

<span data-ttu-id="587a2-120">假設您想要查看電子郵件，並在 Office 365 技術偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="587a2-120">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="587a2-121">若要這麼做，請使用檔案總管的[電子郵件 > 惡意程式碼](threat-explorer-views.md#email--malware)檢視。</span><span class="sxs-lookup"><span data-stu-id="587a2-121">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="587a2-122">在 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。</span><span class="sxs-lookup"><span data-stu-id="587a2-122">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="587a2-123">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="587a2-123">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="587a2-124">![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="587a2-124">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="587a2-125">按一下 [**寄件者**，，然後選擇 [**基本** > **偵測技術**。</span><span class="sxs-lookup"><span data-stu-id="587a2-125">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="587a2-126">偵測技術現在可做為報表的篩選。</span><span class="sxs-lookup"><span data-stu-id="587a2-126">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="587a2-127">![惡意程式碼偵測技術](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="587a2-127">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="587a2-128">選取一個選項，，，然後按一下 [重新整理] 按鈕，以套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="587a2-128">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![選取的偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="587a2-130">若要顯示在電子郵件，使用您所選取的技術選項中偵測到的結果惡意程式碼會重新整理報表。</span><span class="sxs-lookup"><span data-stu-id="587a2-130">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="587a2-131">從這裡開始，您可以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="587a2-131">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="587a2-132">檢視網路釣魚 Url 相關資料，並按一下 verdict</span><span class="sxs-lookup"><span data-stu-id="587a2-132">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="587a2-133">假設您想要查看網路釣魚電子郵件，包括允許、 封鎖，並覆寫的 Url 清單中嘗試透過 Url。</span><span class="sxs-lookup"><span data-stu-id="587a2-133">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="587a2-134">若要這麼做，請使用檔案總管的[電子郵件 > 釣魚程式](threat-explorer-views.md#email--phish)檢視。</span><span class="sxs-lookup"><span data-stu-id="587a2-134">To do this, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="587a2-135">在 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。</span><span class="sxs-lookup"><span data-stu-id="587a2-135">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="587a2-136">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **釣魚程式**。</span><span class="sxs-lookup"><span data-stu-id="587a2-136">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="587a2-137">![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="587a2-137">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="587a2-138">按一下 [**寄件者**，，然後選擇 [ **Url** > **按一下 verdict**。</span><span class="sxs-lookup"><span data-stu-id="587a2-138">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="587a2-139">選取一或多個選項，例如**封鎖**及**封鎖覆寫**]，然後按一下 [**重新整理**] 按鈕，以套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="587a2-139">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="587a2-140">![Url 並按一下 [結果](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="587a2-140">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="587a2-141">報表會重新整理以顯示已封鎖 （或 [瀏覽儘管警告） 的電子郵件中偵測到的網路釣魚 Url 以及電子郵件傳遞狀態。</span><span class="sxs-lookup"><span data-stu-id="587a2-141">The report refreshes to show detected phishing URLs in email that were blocked (or visited despite a warning), along with email delivery status.</span></span> <span data-ttu-id="587a2-142">從這裡開始，您可以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="587a2-142">From here, you can conduct further analysis.</span></span> <span data-ttu-id="587a2-143">例如，下方圖表，您可以看到貴組織的電子郵件遭到封鎖的上層 Url。</span><span class="sxs-lookup"><span data-stu-id="587a2-143">For example, below the chart, you can see the top URLs that were blocked in your organization's email.</span></span> 

![已封鎖的檔案總管 Url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="587a2-145">選取要檢視的詳細的資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="587a2-145">Select a URL to view more detailed information.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="587a2-146">檢閱報告的使用者的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="587a2-146">Review email messages reported by users</span></span>

<span data-ttu-id="587a2-147">假設您想要查看您組織中的使用者會回報的電子郵件為垃圾郵件、 不是垃圾郵件或網路釣魚使用[報告訊息增益集以進行 Outlook 和 outlook 網頁版](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="587a2-147">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="587a2-148">若要這麼做，請使用[電子郵件 > 使用者回報](threat-explorer-views.md#email--user-reported)檔案總管檢視。</span><span class="sxs-lookup"><span data-stu-id="587a2-148">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="587a2-149">在 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。</span><span class="sxs-lookup"><span data-stu-id="587a2-149">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="587a2-150">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **使用者報告**。</span><span class="sxs-lookup"><span data-stu-id="587a2-150">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="587a2-151">![瀏覽器的 [檢視] 功能表](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="587a2-151">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="587a2-152">按一下 [**寄件者**，，然後選擇 [**基本** > **報表類型**。</span><span class="sxs-lookup"><span data-stu-id="587a2-152">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="587a2-153">選取一個選項，例如**釣魚程式**，，然後按一下 [**重新整理**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="587a2-153">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="587a2-154">![使用者報告的釣魚程式](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="587a2-154">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="587a2-155">報表會重新整理以顯示您組織中的人員已回報為網路釣魚嘗試的電子郵件的相關資料。</span><span class="sxs-lookup"><span data-stu-id="587a2-155">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="587a2-156">您可以使用此資訊來進一步進行分析，並如有必要，調整您的[ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="587a2-156">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="theres-more"></a><span data-ttu-id="587a2-157">沒有更多 ！</span><span class="sxs-lookup"><span data-stu-id="587a2-157">There's more!</span></span>

<span data-ttu-id="587a2-158">除了本文中所述的三個案例，您有許多報告案例隨附於瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="587a2-158">In addition to the three scenarios outlined in this article, you have many reporting scenarios available with Explorer.</span></span> <span data-ttu-id="587a2-159">以下是幾個例子：</span><span class="sxs-lookup"><span data-stu-id="587a2-159">Here are a few more examples:</span></span>

- [<span data-ttu-id="587a2-160">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="587a2-160">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="587a2-161">檢視 SharePoint Online、 OneDrive 及 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="587a2-161">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

- <span data-ttu-id="587a2-162">[在威脅總管] 中，取得檢視的概觀](threat-explorer-views.md)</span><span class="sxs-lookup"><span data-stu-id="587a2-162">[Get an overview of the views in Threat Explorer](threat-explorer-views.md)</span></span>

## <a name="how-to-get-explorer"></a><span data-ttu-id="587a2-163">如何取得總管</span><span class="sxs-lookup"><span data-stu-id="587a2-163">How to get Explorer</span></span>

<span data-ttu-id="587a2-164">Explorer 隨附於[Office 365 進階威脅防護計劃 2](office-365-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="587a2-164">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="587a2-165">若要檢視並使用檔案總管，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者。</span><span class="sxs-lookup"><span data-stu-id="587a2-165">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="587a2-166">Security&amp;合規性中心，您必須有一個指派的下列角色：</span><span class="sxs-lookup"><span data-stu-id="587a2-166">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="587a2-167">組織管理</span><span class="sxs-lookup"><span data-stu-id="587a2-167">Organization Management</span></span>
    - <span data-ttu-id="587a2-168">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="587a2-168">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="587a2-169">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="587a2-169">Security Reader</span></span>

- <span data-ttu-id="587a2-170">若是 Exchange Online 中，您必須安裝下列其中一個在 Exchange 系統管理中心中指派下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="587a2-170">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="587a2-171">組織管理</span><span class="sxs-lookup"><span data-stu-id="587a2-171">Organization Management</span></span>
    - <span data-ttu-id="587a2-172">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="587a2-172">View-only Organization Management</span></span>
    - <span data-ttu-id="587a2-173">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="587a2-173">View-Only Recipients role</span></span>
    - <span data-ttu-id="587a2-174">合規性管理</span><span class="sxs-lookup"><span data-stu-id="587a2-174">Compliance Management</span></span>

<span data-ttu-id="587a2-175">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="587a2-175">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="587a2-176">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="587a2-176">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="587a2-177">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="587a2-177">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a><span data-ttu-id="587a2-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="587a2-178">Related topics</span></span>

- [<span data-ttu-id="587a2-179">自動化的調查及回應 （空調）</span><span class="sxs-lookup"><span data-stu-id="587a2-179">Automated Investigation and Response (AIR)</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="587a2-180">威脅總管檢視</span><span class="sxs-lookup"><span data-stu-id="587a2-180">Threat Explorer views</span></span>](threat-explorer-views.md)

- [<span data-ttu-id="587a2-181">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="587a2-181">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
