---
title: 適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 11/08/2018
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: 擴充 Office 365 進階威脅保護 SharePoint Online、 OneDrive for Business 和 Microsoft 小組以啟用更安全共同作業您的組織中的檔案。
ms.openlocfilehash: 29676bf7c326adf366cca79a59f5b4c40c672baa
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014815"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="df3fa-103">適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="df3fa-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="df3fa-104">Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組的概觀</span><span class="sxs-lookup"><span data-stu-id="df3fa-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="df3fa-p101">定期人員共用檔案並使用 SharePoint、 OneDrive 及 Microsoft 小組共同作業。[Office 365 進階威脅保護](office-365-atp.md)(ATP)，與您的組織共同作業更安全的方式。ATP 協助偵測和封鎖識別為惡意小組網站和文件庫中的檔案。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p101">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams. With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner. ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="df3fa-108">運作方式</span><span class="sxs-lookup"><span data-stu-id="df3fa-108">How it works</span></span>

<span data-ttu-id="df3fa-p102">當 SharePoint Online 中的檔案時、 OneDrive for Business 和 Microsoft 小組已識別為惡意、 ATP 直接整合搭配鎖定該檔案的檔案存放區。下圖顯示在文件庫中偵測到惡意檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p102">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file. The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="df3fa-111">[![檔案的 onedrive for Business 做為惡意偵測到其中一個](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="df3fa-111">[![Files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="df3fa-p103">雖然封鎖的檔案仍會列在文件庫和 web、 手機或桌面應用程式中封鎖的檔案不能是開啟、 複製、 移動或共用。人員可以，但刪除封鎖的檔案。以下使用者的行動裝置的哪些的範例看起來像：</span><span class="sxs-lookup"><span data-stu-id="df3fa-p103">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared. People can, however, delete a blocked file. Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="df3fa-115">[![封鎖的檔案的 OneDrive for Business 刪除 OneDrive 行動裝置應用程式](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="df3fa-115">[![Deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="df3fa-p104">根據 Office 365 的設定方式的人員可能或可能沒有能夠下載封鎖的檔案。以下是使用者的行動裝置上下載封鎖的檔案新外觀：</span><span class="sxs-lookup"><span data-stu-id="df3fa-p104">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file. Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="df3fa-118">[![下載的 onedrive for Business 封鎖的檔案](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="df3fa-118">[![Downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="df3fa-119">若要深入了解，請參閱[開啟 Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="df3fa-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
## <a name="keep-these-points-in-mind"></a><span data-ttu-id="df3fa-120">請記住以下幾點</span><span class="sxs-lookup"><span data-stu-id="df3fa-120">Keep these points in mind</span></span>

- <span data-ttu-id="df3fa-p105">ATP 不會掃描 SharePoint Online、 OneDrive 中每一個單一檔案商務或 Microsoft 小組。這是根據設計。掃描檔案有以非同步方式，透過使用智慧 heuristics 和威脅有空的共用和來賓活動事件來識別惡意檔案的程序。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p105">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams. This is by design. Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="df3fa-p106">請確定您的 SharePoint 網站已設為使用[現代經驗](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。檔案會被識別為惡意及封鎖、 人員即可看到此發生摩登的經驗，但不是 [傳統檢視。ATP 保護適用於是否使用現代經驗] 或 [傳統檢視;不過的封鎖檔案的視覺指標是存在只能在現代經驗。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p106">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view. ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>
    
- <span data-ttu-id="df3fa-127">會被識別為惡意 SharePoint Online 中的檔案、 OneDrive for Business 或 Microsoft 小組會顯示在[Office 365 進階威脅 Protection 的報告](view-reports-for-atp.md)及威脅 Explorer （ [Office 365 威脅智慧](office-365-ti.md)的一部分）。</span><span class="sxs-lookup"><span data-stu-id="df3fa-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in Threat Explorer (part of [Office 365 Threat Intelligence](office-365-ti.md)).</span></span>
    
- <span data-ttu-id="df3fa-p107">ATP 屬於貴組織的整體威脅保護策略中，包含反垃圾郵件和反惡意程式防護，以及安全的連結和安全的附件。若要深入了解，請參閱[Office 365 中的威脅的保護](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p107">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments. To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="df3fa-p108">SharePoint Online 系統管理員可以決定是否要讓使用者能夠下載偵測到為惡意的檔案。做法是執行 Set-spotenant PowerShell 指令程式使用 DisallowInfectedFileDownload 參數 （請參閱[開啟 SharePoint、 OneDrive 及 Microsoft 小組的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)）。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p108">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious. This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="df3fa-132">隔離區中 ATP for SharePoint Online、 OneDrive for Business 和 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="df3fa-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="df3fa-133">開始在落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能&amp;規範中心會被擴充至 ATP for SharePoint Online、 OneDrive for Business 和 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="df3fa-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
  
<span data-ttu-id="df3fa-p109">當 SharePoint Online 中的檔案時、 OneDrive for Business 或 Microsoft 小組識別為惡意除了 ATP 封鎖防止開啟或共用檔案時，該檔案包含在隔離的項目清單。(安全性&amp;規範管理中心，移至**威脅管理** \> **檢閱** \> **隔離**及篩選的**內容**。)</span><span class="sxs-lookup"><span data-stu-id="df3fa-p109">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items. (In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Content**.)</span></span> 
  
<span data-ttu-id="df3fa-136">如果您正在貴組織的 Office 365 安全性小組的一部分，且必須必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)，您可以下載、 版本、 報告及刪除已偵測到為惡意的 ATP 的檔案從隔離區。</span><span class="sxs-lookup"><span data-stu-id="df3fa-136">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="df3fa-p110">**發佈和報告**檔案移除檔案的 ATP 區塊各自的小組網站或文件庫中 SharePoint、 OneDrive 或 Microsoft 小組。使用者是然後能夠開啟、 分享和下載檔案。然後將檔案**傳送報告給 Microsoft**選取選項時，會向 Microsoft 報告為誤判。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p110">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams. Users are then able to open, share, and download the file. And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="df3fa-p111">**刪除檔案**從隔離; 移除檔案不過，只有在正在開啟或共用，仍有封鎖的檔案。檔案必須也會刪除其各自的文件庫或小組網站 （SharePoint Online、 OneDrive for Business 或 Microsoft 小組） 中。</span><span class="sxs-lookup"><span data-stu-id="df3fa-p111">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared. The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="df3fa-142">**下載檔案**可讓您下載及分析之檔案的任何誤判。</span><span class="sxs-lookup"><span data-stu-id="df3fa-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="df3fa-143">後續步驟</span><span class="sxs-lookup"><span data-stu-id="df3fa-143">Next steps</span></span>

1. [<span data-ttu-id="df3fa-144">在 Office 365 ATP 開啟 SharePoint、 OneDrive 及 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="df3fa-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [<span data-ttu-id="df3fa-145">檢視 SharePoint、 OneDrive 或 Microsoft 小組中偵測到惡意檔案的資訊</span><span class="sxs-lookup"><span data-stu-id="df3fa-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
