---
title: Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: 擴充 Office 365 進階威脅防護中 SharePoint Online、 商務用 OneDrive 和 Microsoft Teams 能夠為您的組織更安全的共同作業的檔案。
ms.openlocfilehash: a73f978ca40571e33864061cfe9538033579b3c7
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408258"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1dedd-103">Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dedd-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1dedd-104">Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams 的概觀</span><span class="sxs-lookup"><span data-stu-id="1dedd-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1dedd-105">定期人員共用檔案及共同作業使用 SharePoint、 OneDrive 及 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1dedd-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="1dedd-106">使用[Office 365 進階威脅防護](office-365-atp.md)(ATP)，您的組織可以共同作業更安全的方式。</span><span class="sxs-lookup"><span data-stu-id="1dedd-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="1dedd-107">ATP 可協助偵測並封鎖會被識別為惡意小組網站和文件庫中的檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="1dedd-108">運作方式</span><span class="sxs-lookup"><span data-stu-id="1dedd-108">How it works</span></span>

<span data-ttu-id="1dedd-109">當 SharePoint Online 中的檔案時，OneDrive for Business 和 Microsoft Teams 已識別為惡意，ATP 直接整合到鎖住該檔案的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="1dedd-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="1dedd-110">下圖顯示在文件庫中偵測到惡意檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="1dedd-110">The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="1dedd-111">[![檔案在商務用 OneDrive 中偵測到一個當做惡意攻擊](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="1dedd-111">[![Files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="1dedd-112">雖然封鎖的檔案仍會列在文件庫和 web，行動裝置，或桌面應用程式，封鎖的檔案無法開啟、 複製、 移動或共用。</span><span class="sxs-lookup"><span data-stu-id="1dedd-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="1dedd-113">人員可以不過，刪除封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="1dedd-114">以下使用者的行動裝置的這代表什麼意思範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="1dedd-114">Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="1dedd-115">[![從商務用 OneDrive 中刪除封鎖的檔案，從 OneDrive 行動應用程式](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="1dedd-115">[![Deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="1dedd-116">根據 Office 365 的設定方式，人員可能，或可能無法下載封鎖的檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="1dedd-116">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="1dedd-117">以下是下載封鎖的檔案看起來像是使用者的行動裝置上：</span><span class="sxs-lookup"><span data-stu-id="1dedd-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="1dedd-118">[![下載 onedrive for Business 封鎖的檔案](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="1dedd-118">[![Downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="1dedd-119">若要深入了解，請參閱[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1dedd-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
## <a name="keep-these-points-in-mind"></a><span data-ttu-id="1dedd-120">請記住以下幾點</span><span class="sxs-lookup"><span data-stu-id="1dedd-120">Keep these points in mind</span></span>

- <span data-ttu-id="1dedd-121">ATP 不會掃描每一個檔案中 SharePoint Online、 OneDrive 商務或 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1dedd-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="1dedd-122">這是預設的設計。</span><span class="sxs-lookup"><span data-stu-id="1dedd-122">This is by design.</span></span> <span data-ttu-id="1dedd-123">掃描檔案有以非同步方式，透過使用以及智慧啟發和威脅訊號的共用和來賓活動事件來識別惡意檔案的程序。</span><span class="sxs-lookup"><span data-stu-id="1dedd-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="1dedd-124">請確定您的 SharePoint 網站已設定要使用[的新式體驗](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="1dedd-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="1dedd-125">當檔案識別為惡意及封鎖時，使用者可以看到這已發生的新式體驗，但不是傳統檢視。</span><span class="sxs-lookup"><span data-stu-id="1dedd-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="1dedd-126">ATP 保護套用是否使用新式體驗或傳統檢視;不過，封鎖的檔案的視覺標記有只能在新式體驗。</span><span class="sxs-lookup"><span data-stu-id="1dedd-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>
    
- <span data-ttu-id="1dedd-127">會被識別為惡意 SharePoint Online 中的檔案，商務用 OneDrive 或 Microsoft Teams 會顯示在[Office 365 進階威脅防護的報告](view-reports-for-atp.md)和[瀏覽器 （和即時偵測的資訊）](threat-explorer.md)中。</span><span class="sxs-lookup"><span data-stu-id="1dedd-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>
    
- <span data-ttu-id="1dedd-128">ATP 是貴組織的整體威脅保護策略，其中包含反垃圾郵件和反惡意程式碼防護，以及安全連結和安全附件的一部分。</span><span class="sxs-lookup"><span data-stu-id="1dedd-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="1dedd-129">若要深入了解，請參閱 <<c0>針對 Office 365 中的威脅保護。</span><span class="sxs-lookup"><span data-stu-id="1dedd-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="1dedd-130">SharePoint Online 系統管理員可以決定是否要讓使用者能夠下載偵測到為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="1dedd-131">這是藉由執行 Set-spotenant PowerShell cmdlet 使用 DisallowInfectedFileDownload 參數 （請參閱[在 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams 上開啟](turn-on-atp-for-spo-odb-and-teams.md)）。</span><span class="sxs-lookup"><span data-stu-id="1dedd-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="1dedd-132">隔離區中 ATP sharepoint Online、 商務用 OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dedd-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="1dedd-133">從最遲 2018 年，[隔離](quarantine-email-messages.md)功能的安全性群組開始&amp;合規性中心會正在擴充至 ATP sharepoint Online、 商務用 OneDrive 和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1dedd-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
  
<span data-ttu-id="1dedd-134">當 SharePoint Online 中的檔案時，商務用 OneDrive 或 Microsoft Teams 識別為惡意，除了 ATP 封鎖開啟或共用檔案時，該檔案包含在被隔離的項目清單。</span><span class="sxs-lookup"><span data-stu-id="1dedd-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="1dedd-135">(安全性&amp;合規性中心，移至**威脅管理** \> **檢閱** \> **隔離**及**內容**篩選器。)</span><span class="sxs-lookup"><span data-stu-id="1dedd-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Content**.)</span></span> 
  
<span data-ttu-id="1dedd-136">如果您是貴組織的 Office 365 安全性小組的一部分，而且具有所需之[權限指派在 Office 365 安全性&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)，您可以下載、 版本、 報告及刪除會偵測 crypto ATP 為惡意的檔案從隔離區。</span><span class="sxs-lookup"><span data-stu-id="1dedd-136">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="1dedd-137">**發佈並報告**檔案移除檔案 ATP 區塊各自的小組網站或文件庫中 SharePoint、 OneDrive 或 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1dedd-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="1dedd-138">使用者就可以開啟、 共用及下載檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="1dedd-139">然後將檔案選取 [**傳送報告給 Microsoft** ] 選項時，會向 Microsoft 報告為誤判。</span><span class="sxs-lookup"><span data-stu-id="1dedd-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="1dedd-140">**刪除檔案**從隔離區; 移除檔案不過，只有在所開啟或共用，仍有封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="1dedd-141">也必須在其各自的文件庫或小組網站 （SharePoint Online、 商務用 OneDrive 或 Microsoft Teams） 中刪除檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="1dedd-142">**下載檔案**，可讓您下載並分析任何誤判的檔案。</span><span class="sxs-lookup"><span data-stu-id="1dedd-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="1dedd-143">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1dedd-143">Next steps</span></span>

1. [<span data-ttu-id="1dedd-144">開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dedd-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [<span data-ttu-id="1dedd-145">檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="1dedd-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
