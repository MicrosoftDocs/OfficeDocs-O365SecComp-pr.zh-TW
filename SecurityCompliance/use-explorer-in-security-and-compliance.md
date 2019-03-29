---
title: 使用中的安全性威脅總管&amp;合規性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/28/2019
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
ms.openlocfilehash: e6177970edc67c8b9e1c0ae6144f4c37f116012f
ms.sourcegitcommit: 787a0fef671e5dc6f5e805b580321b2edbfad8e9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30989608"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="a1386-103">使用中的安全性威脅總管&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="a1386-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="a1386-104">如果您的組織有[Office 365 進階威脅防護計劃 2](office-365-ti.md) (ATP)，而且您具有必要權限，您可以使用威脅總管 （也稱為總管） 來識別和分析潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="a1386-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) (ATP), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="a1386-105">(使用檔案總管中，安全性&amp;合規性中心，移至**威脅管理** \> **總管**。)</span><span class="sxs-lookup"><span data-stu-id="a1386-105">(To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="a1386-107">瀏覽器是功能強大，接近即時的工具，以協助調查及回應安全性威脅的安全性作業小組&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="a1386-107">Explorer is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a1386-108">以下是一些您可以執行的事項：</span><span class="sxs-lookup"><span data-stu-id="a1386-108">Here are some of the things you can do:</span></span>
- [<span data-ttu-id="a1386-109">請參閱 Office 365 安全性功能所偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="a1386-109">See malware that was detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="a1386-110">檢視網路釣魚 Url 相關資料，並按一下 verdict</span><span class="sxs-lookup"><span data-stu-id="a1386-110">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- [<span data-ttu-id="a1386-111">從瀏覽器中檢視啟動自動的調查及回應程序</span><span class="sxs-lookup"><span data-stu-id="a1386-111">Start an automated investigation and response process from a view in Explorer</span></span>](#start-automated-investigation-and-response)
- <span data-ttu-id="a1386-112">...[以及更多](#more-ways-to-use-explorer)！</span><span class="sxs-lookup"><span data-stu-id="a1386-112">... [and more](#more-ways-to-use-explorer)!</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="a1386-113">請參閱技術電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="a1386-113">See malware detected in email by technology</span></span>

<span data-ttu-id="a1386-114">假設您想要查看電子郵件，並在 Office 365 技術偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="a1386-114">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="a1386-115">若要這麼做，請使用檔案總管的[電子郵件 > 惡意程式碼](threat-explorer-views.md#email--malware)檢視。</span><span class="sxs-lookup"><span data-stu-id="a1386-115">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="a1386-116">在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。</span><span class="sxs-lookup"><span data-stu-id="a1386-116">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="a1386-117">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="a1386-117">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="a1386-118">![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="a1386-118">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="a1386-119">按一下 [**寄件者**，，然後選擇 [**基本** > **偵測技術**。</span><span class="sxs-lookup"><span data-stu-id="a1386-119">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="a1386-120">偵測技術現在可做為報表的篩選。</span><span class="sxs-lookup"><span data-stu-id="a1386-120">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="a1386-121">![惡意程式碼偵測技術](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="a1386-121">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="a1386-122">選取一個選項，，，然後按一下 [重新整理] 按鈕，以套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="a1386-122">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![選取的偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="a1386-124">若要顯示在電子郵件，使用您所選取的技術選項中偵測到的結果惡意程式碼會重新整理報表。</span><span class="sxs-lookup"><span data-stu-id="a1386-124">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="a1386-125">從這裡開始，您可以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="a1386-125">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="a1386-126">檢視網路釣魚 Url 相關資料，並按一下 verdict</span><span class="sxs-lookup"><span data-stu-id="a1386-126">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="a1386-127">假設您想要查看網路釣魚電子郵件，包括允許、 封鎖，並覆寫的 Url 清單中嘗試透過 Url。</span><span class="sxs-lookup"><span data-stu-id="a1386-127">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="a1386-128">若要這麼做，請使用檔案總管的[電子郵件 > 釣魚程式](threat-explorer-views.md#email--phish)檢視。</span><span class="sxs-lookup"><span data-stu-id="a1386-128">To do this, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="a1386-129">在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。</span><span class="sxs-lookup"><span data-stu-id="a1386-129">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="a1386-130">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **釣魚程式**。</span><span class="sxs-lookup"><span data-stu-id="a1386-130">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="a1386-131">![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="a1386-131">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="a1386-132">按一下 [**寄件者**，，然後選擇 [ **Url** > **按一下 verdict**。</span><span class="sxs-lookup"><span data-stu-id="a1386-132">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="a1386-133">選取一或多個選項，例如**封鎖**及**封鎖覆寫**]，然後按一下 [**重新整理**] 按鈕，以套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="a1386-133">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="a1386-134">![Url 並按一下 [結果](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="a1386-134">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="a1386-135">報表會重新整理以顯示已封鎖 （或 [瀏覽儘管警告） 的電子郵件中偵測到的網路釣魚 Url 以及電子郵件傳遞狀態。</span><span class="sxs-lookup"><span data-stu-id="a1386-135">The report refreshes to show detected phishing URLs in email that were blocked (or visited despite a warning), along with email delivery status.</span></span> <span data-ttu-id="a1386-136">從這裡開始，您可以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="a1386-136">From here, you can conduct further analysis.</span></span> <span data-ttu-id="a1386-137">例如，下方圖表，您可以看到貴組織的電子郵件遭到封鎖的上層 Url。</span><span class="sxs-lookup"><span data-stu-id="a1386-137">For example, below the chart, you can see the top URLs that were blocked in your organization's email.</span></span> 

![已封鎖的檔案總管 Url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="a1386-139">選取要檢視的詳細的資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="a1386-139">Select a URL to view more detailed information.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="a1386-140">檢閱報告的使用者的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="a1386-140">Review email messages reported by users</span></span>

<span data-ttu-id="a1386-141">假設您想要查看您組織中的使用者會回報的電子郵件為垃圾郵件、 不是垃圾郵件或網路釣魚使用[報告訊息增益集以進行 Outlook 和 outlook 網頁版](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="a1386-141">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="a1386-142">若要這麼做，請使用[電子郵件 > 使用者回報](threat-explorer-views.md#email--user-reported)檔案總管檢視。</span><span class="sxs-lookup"><span data-stu-id="a1386-142">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="a1386-143">在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。</span><span class="sxs-lookup"><span data-stu-id="a1386-143">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="a1386-144">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **使用者報告**。</span><span class="sxs-lookup"><span data-stu-id="a1386-144">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="a1386-145">![瀏覽器的 [檢視] 功能表](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="a1386-145">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="a1386-146">按一下 [**寄件者**，，然後選擇 [**基本** > **報表類型**。</span><span class="sxs-lookup"><span data-stu-id="a1386-146">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="a1386-147">選取一個選項，例如**釣魚程式**，，然後按一下 [**重新整理**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a1386-147">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="a1386-148">![使用者報告的釣魚程式](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="a1386-148">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="a1386-149">報表會重新整理以顯示您組織中的人員已回報為網路釣魚嘗試的電子郵件的相關資料。</span><span class="sxs-lookup"><span data-stu-id="a1386-149">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="a1386-150">您可以使用此資訊來進一步進行分析，並如有必要，調整您的[ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1386-150">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="a1386-151">啟動自動化的調查及回應</span><span class="sxs-lookup"><span data-stu-id="a1386-151">Start automated investigation and response</span></span>

<span data-ttu-id="a1386-152">（新 ！）[自動化調查及回應](automated-investigation-response-office.md)，最近新增至 ATP 計劃 2，可以儲存您的安全性作業小組很多時間和精力中調查，並減輕網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="a1386-152">(NEW!) [Automated investigation and response](automated-investigation-response-office.md), recently added to ATP Plan 2, can save your security operations team a lot of time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="a1386-153">除了設定可以觸發安全性 playbook 的提醒，您可以從瀏覽器中檢視啟動自動的調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="a1386-153">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="a1386-154">如需這的詳細資訊，請參閱[範例： 安全性系統管理員會觸發從威脅總管調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="a1386-154">For details on this, see [Example: A security administrator triggers an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer"></a><span data-ttu-id="a1386-155">若要使用檔案總管的更多方法</span><span class="sxs-lookup"><span data-stu-id="a1386-155">More ways to use Explorer</span></span>

<span data-ttu-id="a1386-156">除了本文中所述的案例，您有許多詳細報告選項隨附於瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="a1386-156">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer.</span></span> 
- [<span data-ttu-id="a1386-157">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="a1386-157">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="a1386-158">檢視 SharePoint Online、 OneDrive 及 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="a1386-158">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- <span data-ttu-id="a1386-159">[在威脅總管] 中，取得檢視的概觀](threat-explorer-views.md)</span><span class="sxs-lookup"><span data-stu-id="a1386-159">[Get an overview of the views in Threat Explorer](threat-explorer-views.md)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="a1386-160">所需的授權和權限</span><span class="sxs-lookup"><span data-stu-id="a1386-160">Required licenses and permissions</span></span>

<span data-ttu-id="a1386-161">Explorer 隨附於[Office 365 進階威脅防護計劃 2](office-365-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="a1386-161">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="a1386-162">若要檢視並使用檔案總管，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者。</span><span class="sxs-lookup"><span data-stu-id="a1386-162">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="a1386-163">Security&amp;合規性中心，您必須有一個指派的下列角色：</span><span class="sxs-lookup"><span data-stu-id="a1386-163">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="a1386-164">組織管理</span><span class="sxs-lookup"><span data-stu-id="a1386-164">Organization Management</span></span>
    - <span data-ttu-id="a1386-165">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="a1386-165">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="a1386-166">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="a1386-166">Security Reader</span></span>

- <span data-ttu-id="a1386-167">若是 Exchange Online 中，您必須安裝下列其中一個在 Exchange 系統管理中心中指派下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="a1386-167">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="a1386-168">組織管理</span><span class="sxs-lookup"><span data-stu-id="a1386-168">Organization Management</span></span>
    - <span data-ttu-id="a1386-169">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="a1386-169">View-only Organization Management</span></span>
    - <span data-ttu-id="a1386-170">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="a1386-170">View-Only Recipients role</span></span>
    - <span data-ttu-id="a1386-171">合規性管理</span><span class="sxs-lookup"><span data-stu-id="a1386-171">Compliance Management</span></span>

<span data-ttu-id="a1386-172">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="a1386-172">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="a1386-173">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a1386-173">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="a1386-174">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="a1386-174">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
