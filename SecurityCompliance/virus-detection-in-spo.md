---
title: 在 SharePoint Online 中的病毒偵測
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/14/2019
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 可協助防止惡意程式碼中的環境，藉由使用者上傳到 SharePoint Online 檔案中偵測有病毒。 掃描檔案有病毒後它們上傳。 如果找到受感染的檔案時，屬性是設定，讓使用者無法下載，或將檔案同步。
ms.openlocfilehash: d4f18c84935d9c6e1d3f135bbda6c40737956ae7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266819"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="86bc3-105">在 SharePoint Online 中的病毒偵測</span><span class="sxs-lookup"><span data-stu-id="86bc3-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="86bc3-106">Office 365 可協助防止惡意程式碼中的環境，藉由使用者上傳到 SharePoint Online 檔案中偵測有病毒。</span><span class="sxs-lookup"><span data-stu-id="86bc3-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="86bc3-107">掃描檔案有病毒後它們上傳。</span><span class="sxs-lookup"><span data-stu-id="86bc3-107">Files are scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="86bc3-108">如果找到受感染的檔案時，屬性是設定，讓使用者無法下載，或將檔案同步。</span><span class="sxs-lookup"><span data-stu-id="86bc3-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86bc3-109">SharePoint Online 中的這些防毒功能是含有病毒的方式。</span><span class="sxs-lookup"><span data-stu-id="86bc3-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="86bc3-110">它們不適合以防範惡意程式碼為您的環境的單一資料點。</span><span class="sxs-lookup"><span data-stu-id="86bc3-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="86bc3-111">我們鼓勵所有客戶評估和實作各種層級的反惡意程式碼保護，以及套用保護您的企業版基礎結構的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="86bc3-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="86bc3-112">如需策略和最佳作法的詳細資訊，請參閱 < <b0>Office 365 的安全性最佳做法</b0>。</span><span class="sxs-lookup"><span data-stu-id="86bc3-112">For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="86bc3-113">當受感染的檔案上傳至 SharePoint Online 時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="86bc3-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="86bc3-114">Office 365 使用常見的病毒偵測引擎。</span><span class="sxs-lookup"><span data-stu-id="86bc3-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="86bc3-115">引擎內 SharePoint Online 中，以非同步方式執行，並掃描檔案之後他們正在上傳。</span><span class="sxs-lookup"><span data-stu-id="86bc3-115">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="86bc3-116">找到檔案時含有病毒的郵件，就會標示，因此無法再次下載。</span><span class="sxs-lookup"><span data-stu-id="86bc3-116">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="86bc3-117">年 4 月 2018 年，我們移除了掃描檔案的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="86bc3-117">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="86bc3-118">以下是會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="86bc3-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="86bc3-119">使用者上傳至 SharePoint Online 檔案。</span><span class="sxs-lookup"><span data-stu-id="86bc3-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="86bc3-120">病毒偵測引擎掃描的檔案。</span><span class="sxs-lookup"><span data-stu-id="86bc3-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="86bc3-121">如果找到病毒，則病毒引擎會指出受到感染的檔案上設定屬性。</span><span class="sxs-lookup"><span data-stu-id="86bc3-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="86bc3-122">當使用者嘗試使用瀏覽器來下載受到感染的檔案時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="86bc3-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="86bc3-123">如果檔案感染病毒，使用者使用瀏覽器，無法下載檔案從 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="86bc3-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="86bc3-124">以下是會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="86bc3-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="86bc3-125">使用者開啟網頁瀏覽器，並嘗試從 SharePoint Online 下載受到感染的檔案。</span><span class="sxs-lookup"><span data-stu-id="86bc3-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="86bc3-126">使用者是指定已偵測到病毒警告。</span><span class="sxs-lookup"><span data-stu-id="86bc3-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="86bc3-127">使用者是指定選項，下載檔案，並嘗試清除其使用自己的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="86bc3-127">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="86bc3-128">您可以使用**DisallowInfectedFileDownload**參數 Set-spotenant 指令程式不允許使用者下載偵測到的檔案，即使是在 [防毒] 警告視窗。</span><span class="sxs-lookup"><span data-stu-id="86bc3-128">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="86bc3-129">請參閱 [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="86bc3-129">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="86bc3-130">OneDrive 同步處理用戶端嘗試同步處理受感染的檔案時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="86bc3-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="86bc3-131">是否使用者同步處理檔案與新的 OneDrive 同步處理用戶端 (OneDrive.exe) 或前一個 OneDrive for Business 同步處理用戶端 (Groove.exe)，如果檔案包含病毒而，同步處理用戶端將不會下載它。</span><span class="sxs-lookup"><span data-stu-id="86bc3-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="86bc3-132">同步處理用戶端將會顯示無法同步處理檔案的通知。</span><span class="sxs-lookup"><span data-stu-id="86bc3-132">The sync client will display a notification that the file can't be synced.</span></span>
  

