---
title: 在 SharePoint Online 中的病毒偵測
ms.author: krowley
author: kccross
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
description: Office 365 可協助您的環境免受病毒偵測使用者上傳至 SharePoint Online 的檔案中的惡意程式碼。掃描檔案有病毒之後其上傳。若檔案已發現受到感染、 屬性設定，讓使用者無法下載或同步處理檔案。
ms.openlocfilehash: d39a5be525e25de8206e8d4219d9c83bfa6eaae0
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212963"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="47017-105">在 SharePoint Online 中的病毒偵測</span><span class="sxs-lookup"><span data-stu-id="47017-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="47017-p102">Office 365 可協助您的環境免受病毒偵測使用者上傳至 SharePoint Online 的檔案中的惡意程式碼。掃描檔案有病毒之後其上傳。若檔案已發現受到感染、 屬性設定，讓使用者無法下載或同步處理檔案。</span><span class="sxs-lookup"><span data-stu-id="47017-p102">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online. Files are scanned for viruses after they are uploaded. If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="47017-p103">SharePoint Online 這些防毒功能是包含病毒的方式。它們不適用對象為惡意程式碼為您的環境的防禦措施的單一資料點。我們建議所有客戶評估及實作不同的層級的反惡意程式碼保護並套用保護您的企業基礎結構的最佳作法。如需策略和最佳作法的詳細資訊，請參閱 ＜ [Security for Office 365 的最佳作法](security-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="47017-p103">These antivirus capabilities in SharePoint Online are a way to contain viruses. They aren't intended as a single point of defense against malware for your environment. We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure. For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="47017-113">受到感染的檔案上傳至 SharePoint Online 發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="47017-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="47017-p104">Office 365 使用一般的病毒偵測引擎。引擎會以非同步方式執行內 SharePoint Online 和掃描之後他們正在上傳的檔案。當包含病毒而找到的檔案時、 標記使它無法再下載。4 月 2018年中我們移除了掃描的檔案有 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="47017-p104">Office 365 uses a common virus detection engine. The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded. When a file is found to contain a virus, it's flagged so that it can't be downloaded again. In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="47017-118">以下是會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="47017-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="47017-119">使用者上傳至 SharePoint Online 的檔案。</span><span class="sxs-lookup"><span data-stu-id="47017-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="47017-120">病毒偵測引擎會掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="47017-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="47017-121">如果有找到病毒、 病毒引擎會指出受到感染的檔案上設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="47017-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="47017-122">當使用者嘗試使用瀏覽器下載受到感染的檔案有什麼？</span><span class="sxs-lookup"><span data-stu-id="47017-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="47017-123">如果檔案感染病毒，使用者無法使用瀏覽器從 SharePoint Online 下載檔案。</span><span class="sxs-lookup"><span data-stu-id="47017-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="47017-124">以下是會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="47017-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="47017-125">使用者開啟網頁瀏覽器，並嘗試從 SharePoint Online 下載受到感染的檔案。</span><span class="sxs-lookup"><span data-stu-id="47017-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="47017-p105">使用者是指定已偵測到病毒警告。使用者是指定下載檔案，並嘗試清除其使用自己的防毒軟體的選項。</span><span class="sxs-lookup"><span data-stu-id="47017-p105">The user is given a warning that a virus has been detected. The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="47017-p106">您可以使用**DisallowInfectedFileDownload**參數 Set-spotenant 指令程式不允許使用者下載偵測到的檔案，甚至是在 [防毒] 警告視窗中。請參閱 [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="47017-p106">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window. See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="47017-130">當 OneDrive sync 用戶端嘗試以同步處理受到感染的檔案會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="47017-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="47017-p107">如果檔案包含病毒而使用者同步的檔案與新的 OneDrive sync 用戶端 (OneDrive.exe) 或上一個 OneDrive for Business sync 用戶端 (Groove.exe)、 是否 sync 用戶端將不會下載它。Sync 用戶端將會顯示無法同步處理之檔案的通知。</span><span class="sxs-lookup"><span data-stu-id="47017-p107">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  

