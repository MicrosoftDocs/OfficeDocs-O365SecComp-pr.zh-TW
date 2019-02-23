---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 系統管理員： 了解如何使用 Office 365 安全性匯入服務&amp;規範中心以大量匯入電子郵件資料 （PST 檔案） 至 Exchange Online 中的使用者信箱。本主題提供常見問題集並說明 PST 匯入程序的運作方式。
ms.openlocfilehash: b6f32a6b5552773c197003ddac41c138539bb6ef
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218043"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a><span data-ttu-id="69308-104">Overview of importing your organization PST files to Office 365</span><span class="sxs-lookup"><span data-stu-id="69308-104">Overview of importing your organization PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="69308-p102">本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span><span class="sxs-lookup"><span data-stu-id="69308-p102">This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>

<span data-ttu-id="69308-p103">您可以使用匯入服務 Office 365 安全性&amp;規範中心以快速大量匯入 PST 檔案至 Office 365 組織中的 Exchange Online 信箱。有兩種方式可以 PST 檔案匯入 Office 365：</span><span class="sxs-lookup"><span data-stu-id="69308-p103">You can use the Import service in the Office 365 Security &amp; Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your Office 365 organization. There are two ways you can import PST files to Office 365:</span></span>
   
- <span data-ttu-id="69308-p104">**網路上傳**![雲端上傳](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)-將 PST 檔案上傳至 Microsoft 雲端 Azure 的暫存位置網路。然後您可使用的匯入 Office 365 服務資料匯入 PST 信箱 Office 365 組織中。</span><span class="sxs-lookup"><span data-stu-id="69308-p104">**Network upload** ![Cloud upload](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the PST data to mailboxes in your Office 365 organization.</span></span> 

- <span data-ttu-id="69308-p105">**磁碟機之後傳送**![硬碟](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png)-將 PST 檔案複製到 BitLocker 加密的硬碟與實際運送給 Microsoft 的磁碟機。當 Microsoft 收到硬碟時、 資料中心人員將資料上傳至 Microsoft 雲端中暫時 Azure 儲存位置。然後您可以使用匯入 Office 365 服務資料匯入 Office 365 組織的信箱。</span><span class="sxs-lookup"><span data-stu-id="69308-p105">**Drive shipping** ![Hard disk](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft. When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the data to mailboxes in your Office 365 organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="69308-115">逐步說明</span><span class="sxs-lookup"><span data-stu-id="69308-115">Step-by-step instructions</span></span>
  
<span data-ttu-id="69308-116">請參閱下列主題的詳細逐步說明大量匯入至 Office 365 組織的 PST 檔案的其中一個。</span><span class="sxs-lookup"><span data-stu-id="69308-116">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 
   
- [<span data-ttu-id="69308-117">使用網路上傳將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="69308-117">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
- [<span data-ttu-id="69308-118">使用磁碟機運送將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="69308-118">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="69308-119">匯入 PST 檔案的運作方式</span><span class="sxs-lookup"><span data-stu-id="69308-119">How importing PST files works</span></span>

<span data-ttu-id="69308-p106">以下是圖及描述之完整 PST 匯入程序。圖顯示主要工作流程並會醒目提示的網路上傳和磁碟機傳送方法之間的差異。</span><span class="sxs-lookup"><span data-stu-id="69308-p106">Here's an illustration and description of the complete PST import process. The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST 匯入程序的工作流程](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="69308-p107">**下載 PST 匯入工具和關鍵私人 Azure 儲存位置**-第一個步驟是要下載 PST 檔案上傳或將其複製到硬碟使用的工具和存取金鑰。您可以取得這些 Office 365 安全性 [**匯入**] 頁面中&amp;規範中心。索引鍵提供 PST 檔案上傳至的私人和安全 Azure 儲存位置的必要權限您 （或 Microsoft 資料中心人員但如果是磁碟機傳送）。此存取索引鍵是唯一的您的組織和協助防止 PST 檔案的未經授權的存取他們正在上傳至 Microsoft cloud 之後。請注意將 PST 檔案匯入 Office 365 不需要有不同的 Azure 訂閱貴組織。</span><span class="sxs-lookup"><span data-stu-id="69308-p107">**Download the PST import tools and key to private Azure storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive. You obtain these from the **Import** page in the Office 365 Security &amp; Compliance Center. The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure storage location. This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud. Note that importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="69308-p108">**上傳] 或 [副本 PST 檔案**-下一步取決於您正在使用網路上傳或磁碟機傳送匯入 PST 檔案。在這兩種情況下，您將使用的工具與您在上一個步驟中取得的安全認證儲存索引鍵。</span><span class="sxs-lookup"><span data-stu-id="69308-p108">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files. In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="69308-p109">**網路上傳**（在步驟 1 中下載） AzCopy.exe 工具可上傳並儲存在 Microsoft 雲端 Azure 的儲存位置的 PST 檔案。請注意 Azure 儲存位置的上傳至 PST 檔案位於同一個地區 Office 365 組織所在的 Microsoft 資料中心。</span><span class="sxs-lookup"><span data-stu-id="69308-p109">**Network upload**The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure storage location in the Microsoft cloud. Note that the Azure storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span> 
    
      <span data-ttu-id="69308-132">若要將其上傳，您想要匯入 Office 365 的 PST 檔案必須位於檔案共用或組織中的檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="69308-132">To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="69308-p110">**磁碟機之後傳送**（在步驟 1 中下載） WAImportExport.exe 工具用來將 PST 檔案複製到硬碟。此工具硬碟與 BitLocker 會加密，則會 Pst 複製到硬碟。像網路上傳您想要複製到硬碟的 PST 檔案必須位於檔案共用或組織中的檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="69308-p110">**Drive shipping**The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive. This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive. Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="69308-p111">**建立 PST 匯入對應檔案**-PST 檔案已上傳至 Azure 儲存位置或複製到硬碟的磁碟機之後下, 一步是建立指定哪些使用者信箱 PST 檔案是否將匯入以逗點分隔的值 (CSV) 檔案 (nd PST 檔案可匯入使用者的主要信箱或封存信箱）。匯入 Office 365 服務將使用的資訊來匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="69308-p111">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure storage location or copied to a hard drive, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox). The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="69308-p112">**建立 PST 匯入工作**-下一個步驟是在 [安全性] 的 [**匯入**] 頁面上建立 PST 匯入工作&amp;規範中心並送出在上一個步驟中建立之 PST 匯入對應檔案。網路上傳 （因為 PST 檔案已上載至 Azure） Office 365 分析 PST 檔案中的資料並再提供讓您設定控制哪些資料實際取得匯入至信箱 PST 匯入對應檔案中指定的篩選器。</span><span class="sxs-lookup"><span data-stu-id="69308-p112">**Create a PST import job** - The next step is to create a PST import job on the **Import** page in the Security &amp; Compliance Center and submit the PST import mapping file created in the previous step. For network upload (because the PST files have been uploaded to Azure) Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="69308-140">磁碟機傳送的一些其他情況將會發生在此程序中的點。</span><span class="sxs-lookup"><span data-stu-id="69308-140">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="69308-141">實體出貨至 （匯入工作會在建立時，會顯示 Microsoft 資料中心的運送位址） 的 Microsoft 資料中心硬碟</span><span class="sxs-lookup"><span data-stu-id="69308-141">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created)</span></span>
    
    - <span data-ttu-id="69308-p113">當 Microsoft 收到硬碟時、 資料中心人員將組織的 Azure 儲存位置上傳 Pst 檔案在硬碟上。如先前所述 PST 檔案上傳至位於相同的區域 Microsoft 資料中心的 Office 365 組織所在 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="69308-p113">When Microsoft receives the hard drive, data center personnel will upload the PSTs files on the hard drive to the Azure storage location for your organization. As previously explained, your PST files are uploaded to a Azure storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="69308-144">在硬碟上的 PST 檔案上傳至 Azure 7 到 10 商務天後 Microsoft 接收硬碟內。</span><span class="sxs-lookup"><span data-stu-id="69308-144">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span> 
  
      <span data-ttu-id="69308-145">網路上傳程序，例如 Office 365 然後分析 PST 檔案中的資料與可讓您設定控制哪些資料實際取得匯入至信箱 PST 匯入對應檔案中指定的篩選器機會。</span><span class="sxs-lookup"><span data-stu-id="69308-145">Like the network upload process, Office 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="69308-146">Microsoft 提供給您的硬碟。</span><span class="sxs-lookup"><span data-stu-id="69308-146">Microsoft ships the hard drive back to you.</span></span> 
    
5. <span data-ttu-id="69308-p114">**篩選所要匯入至信箱的 PST 資料**-Office 365 建立匯入工作後 （與之後的磁碟機傳送工作的 PST 檔案上傳至 Azure 儲存位置） （安全地和安全地） 依照 」 分析的 PST 檔案中的資料用來識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成分析，且資料已準備好要匯入，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。</span><span class="sxs-lookup"><span data-stu-id="69308-p114">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure storage location) Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="69308-p115">**啟動 PST 匯入工作**-開始匯入工作之後，Office 365 資訊檔案中使用 PST 匯入對應從他 Azure 儲存位置的 Pst 檔案匯入至使用者信箱。在 [安全性] 的 [**匯入**] 頁面上會顯示狀態資訊 （包括要匯入每個 PST 檔案的相關資訊） 匯入工作&amp;規範中心。匯入工作完成時，設置**完成**之工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="69308-p115">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure storage location to user mailboxes. Status information about the import job (including information about each PST file being imported) is displayed on the **Import** page in the Security &amp; Compliance Center. When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-office-365"></a><span data-ttu-id="69308-152">為什麼要選擇電子郵件將資料匯入 Office 365？</span><span class="sxs-lookup"><span data-stu-id="69308-152">Why import email data to Office 365?</span></span>

- <span data-ttu-id="69308-153">將 PST 檔案匯入使用者的信箱為貴組織的電子郵件移轉至 Office 365 的其中一個方法。</span><span class="sxs-lookup"><span data-stu-id="69308-153">Importing PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
    
- <span data-ttu-id="69308-p116">您可以使用[智慧型匯入](filter-data-when-importing-pst-files.md)功能來篩選實際取得匯入至目標信箱的 PST 檔案中的項目。此屬性可讓修剪匯入藉由設定篩選器的資料控制哪些資料取得匯入。</span><span class="sxs-lookup"><span data-stu-id="69308-p116">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes. This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="69308-156">將電子郵件資料匯入 Office 365 來可讓您有助於組織的地址規範需求：</span><span class="sxs-lookup"><span data-stu-id="69308-156">Importing email data to Office 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="69308-157">啟用[封存信箱](enable-archive-mailboxes.md)與其他信箱的儲存空間提供使用者[不受限制的封存](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="69308-157">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="69308-158">將信箱[訴訟](https://go.microsoft.com/fwlink/?linkid=841243)保留內容。</span><span class="sxs-lookup"><span data-stu-id="69308-158">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=841243) to retain content.</span></span> 
    
  - <span data-ttu-id="69308-159">使用 「[內容搜尋工具](content-search.md)來搜尋信箱內容。</span><span class="sxs-lookup"><span data-stu-id="69308-159">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="69308-160">使用[eDiscovery 案例](ediscovery-cases.md)來管理您的組織法律調查</span><span class="sxs-lookup"><span data-stu-id="69308-160">Use [eDiscovery cases](ediscovery-cases.md) to mange your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="69308-161">在 [安全性] 中使用[保留原則](retention-policies.md)&amp;規範中心來控制信箱內容保留期限，然後刪除內容之後保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="69308-161">Use [retention policies](retention-policies.md) in the Security &amp; Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 
    
- <span data-ttu-id="69308-p117">將資料匯入 Office 365 協助防止資料遺失。匯入至 Office 365 的電子郵件資料繼承 Exchange Online 的高可用性的功能。</span><span class="sxs-lookup"><span data-stu-id="69308-p117">Importing data to Office 365 helps protect against data loss. Email data that's imported to Office 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="69308-164">因為它會儲存在雲端中的使用者從所有裝置使用 Office 365 中的電子郵件資料。</span><span class="sxs-lookup"><span data-stu-id="69308-164">Email data in Office 365 is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-office-365"></a><span data-ttu-id="69308-165">將 SharePoint 資料匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="69308-165">Importing SharePoint data to Office 365</span></span>

<span data-ttu-id="69308-p118">您也可以在 Office 365 組織中的 SharePoint 網站和 OneDrive 帳戶匯檔案和文件。如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="69308-p118">You can also import files and documents to SharePoint sites and OneDrive accounts in your Office 365 organization. For more information, see the following articles:</span></span>

- [<span data-ttu-id="69308-168">移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69308-168">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [<span data-ttu-id="69308-169">SharePoint 移轉工具簡介</span><span class="sxs-lookup"><span data-stu-id="69308-169">Introducing the SharePoint Migration Tool</span></span>](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [<span data-ttu-id="69308-170">使用 PowerShell 移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69308-170">Migrate to SharePoint Online using PowerShell</span></span>](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- <span data-ttu-id="69308-171">[移轉至 SharePoint Online Azure 的資料] 方塊中的檔案共用內容](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)</span><span class="sxs-lookup"><span data-stu-id="69308-171">[Migrate your file share content to SharePoint Online using the Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)</span></span>


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a><span data-ttu-id="69308-172">常見問題將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="69308-172">Frequently asked questions about importing PST files to Office 365</span></span>
  
<span data-ttu-id="69308-173">以下是一些常見問題使用大量匯入至 Office 365 信箱的 PST 檔案匯入 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="69308-173">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Office 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="69308-174">若要匯入 PST 檔案使用網路上傳</span><span class="sxs-lookup"><span data-stu-id="69308-174">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="69308-175">若要匯入 PST 檔案中使用的磁碟機傳送</span><span class="sxs-lookup"><span data-stu-id="69308-175">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="69308-176">若要匯入 PST 檔案使用網路上傳</span><span class="sxs-lookup"><span data-stu-id="69308-176">Using network upload to import PST files</span></span>

 <span data-ttu-id="69308-177">**不需要在 Office 365 匯入服務中建立匯入工作哪些權限？**</span><span class="sxs-lookup"><span data-stu-id="69308-177">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="69308-p119">您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。或者您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後將自己或其他使用者新增為成員。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="69308-p119">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="69308-183">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="69308-183">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="69308-p120">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="69308-p120">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="69308-186">或</span><span class="sxs-lookup"><span data-stu-id="69308-186">Or</span></span>
    
- <span data-ttu-id="69308-187">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="69308-187">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="69308-p121">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="69308-p121">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="69308-190">**哪裡可用的網路上傳？**</span><span class="sxs-lookup"><span data-stu-id="69308-190">**Where is network upload available?**</span></span>
  
<span data-ttu-id="69308-p122">網路上傳位於目前可用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 中文、 東南亞洲 （日本）、 共和國的韓國及澳洲。網路上傳會提供多個地區中推出。</span><span class="sxs-lookup"><span data-stu-id="69308-p122">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="69308-193">**什麼是匯入 PST 檔案使用網路上傳定價？**</span><span class="sxs-lookup"><span data-stu-id="69308-193">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="69308-194">使用網路上傳匯入 PST 檔案是自由。</span><span class="sxs-lookup"><span data-stu-id="69308-194">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="69308-p123">這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示在清單中的 Office 365 系統管理中心中完成的匯入工作的檔案。匯入工作仍可能會列在 [**匯入至 Office 365 的資料**] 頁面上，雖然 PST 檔案的清單可能空白時檢視較舊的匯入工作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="69308-p123">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="69308-197">**將匯入 Office 365 支援 PST 檔案格式的版本？**</span><span class="sxs-lookup"><span data-stu-id="69308-197">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="69308-p124">有兩個版本的 PST 檔案格式： ANSI 與 Unicode。建議您匯入使用 Unicode PST 檔案格式的檔案。不過，使用 ANSI PST 檔案格式，例如語言之使用雙位元組字元的檔案 (DBCS)，也可匯入 Office 365。如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用網路上傳至匯入至 Office 365 的 PST 檔案](https://go.microsoft.com/fwlink/p/?LinkId=823074)中的步驟 4。</span><span class="sxs-lookup"><span data-stu-id="69308-p124">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).</span></span>
  
<span data-ttu-id="69308-202">此外，從 Outlook 2007 或更新版本的 PST 檔案可以匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="69308-202">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="69308-203">**我將 「 我的 PST 檔案上傳至 Azure 儲存區之後，時間是他們保持在 Azure 中刪除之前？**</span><span class="sxs-lookup"><span data-stu-id="69308-203">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="69308-p125">當您使用的網路上傳方法匯入 PST 檔案時，您將其上傳至名為**ingestiondata**Azure blob 容器。如果沒有匯入工作進行中在 [**匯入**] 頁面中有安全性&amp;規範中心)，然後在 Azure **ingestiondata**容器中的所有 PST 檔案會都刪除 30 天後安全性&amp;規範中心。這也表示您必須建立新的匯入工作安全性&amp;規範中心 （所述之步驟 5 中的網路上傳指示） 內 30 天的上傳 PST 檔案至 Azure。</span><span class="sxs-lookup"><span data-stu-id="69308-p125">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="69308-p126">這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示清單中的安全性完成的匯入工作的檔案&amp;規範中心。雖然匯入工作仍可能會列在 [**匯入**] 頁面上的 [安全性]&amp;規範中心 PST 檔案的清單可能會是空的較舊的匯入工作詳細資料檢視時。</span><span class="sxs-lookup"><span data-stu-id="69308-p126">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="69308-209">**PST 檔案匯入至信箱需要多久的時間？**</span><span class="sxs-lookup"><span data-stu-id="69308-209">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="69308-p127">它取決於您的網路容量，但它通常採用的每個 tb 的資料要上傳至您的組織的 Azure 儲存區的數個小時。PST 檔案複製到 Azure 儲存區之後，會 PST 檔案匯入到 Office 365 信箱至少 24 GB 的每日的速率。如果此速率不符合您的需求，您可能會考慮將電子郵件資料移轉至 Office 365 的其他方法。如需詳細資訊，請參閱 ＜[移轉至 Office 365 的多個電子郵件帳戶的方式](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="69308-p127">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="69308-p128">如果不同的 PST 檔案匯入至不同的目標信箱、 匯入程序會發生平行;換句話說，每 PST/信箱對匯入同時。同樣地，如果多個 PST 檔案匯入至相同信箱，這些會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="69308-p128">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="69308-216">**是否有將郵件大小限制時匯入 PST 檔案？**</span><span class="sxs-lookup"><span data-stu-id="69308-216">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="69308-p129">[是]。如果 PST 檔案包含大於 150 MB 的信箱項目，則會略過之項目的匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="69308-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="69308-219">**是郵件內容，例如郵件已傳送或接收的收件者和其他屬性，PST 檔案匯入至 Office 365 信箱時保留清單？**</span><span class="sxs-lookup"><span data-stu-id="69308-219">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="69308-p130">[是]。原始郵件中繼資料不匯入程序期間變更。</span><span class="sxs-lookup"><span data-stu-id="69308-p130">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="69308-222">**是否有限制 PST 檔案所要匯入信箱資料夾階層中的層級數目吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-222">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="69308-p131">[是]。您不能有個巢狀資料夾 300 或多個層級的 PST 檔案匯入。</span><span class="sxs-lookup"><span data-stu-id="69308-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="69308-225">**可以使用網路上傳至 PST 檔案匯入 Office 365 中的非使用中信箱吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-225">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="69308-226">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="69308-226">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="69308-227">**可以使用網路上傳至 PST 檔案匯入線上封存信箱在 Exchange 混合部署吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-227">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="69308-228">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="69308-228">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="69308-229">**可以使用網路上傳至 PST 檔案匯入 Exchange Online 中公用資料夾嗎？**</span><span class="sxs-lookup"><span data-stu-id="69308-229">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="69308-230">否，您不能 PST 檔案匯入的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="69308-230">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="69308-231">若要匯入 PST 檔案中使用的磁碟機傳送</span><span class="sxs-lookup"><span data-stu-id="69308-231">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="69308-232">**不需要在 Office 365 匯入服務中建立匯入工作哪些權限？**</span><span class="sxs-lookup"><span data-stu-id="69308-232">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="69308-p132">您必須指派信箱匯入匯出至 PST 檔案匯入 Office 365 信箱角色。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。或者您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後將自己或其他使用者新增為成員。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="69308-p132">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="69308-238">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="69308-238">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="69308-p133">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="69308-p133">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="69308-241">或</span><span class="sxs-lookup"><span data-stu-id="69308-241">Or</span></span>
    
- <span data-ttu-id="69308-242">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="69308-242">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="69308-p134">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="69308-p134">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="69308-245">**其中磁碟機傳送可用？**</span><span class="sxs-lookup"><span data-stu-id="69308-245">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="69308-p135">磁碟機傳送位於目前可用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 中文、 東南亞洲 （日本）、 共和國的韓國及澳洲。磁碟機傳送會提供多個地區中推出。</span><span class="sxs-lookup"><span data-stu-id="69308-p135">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="69308-248">**何種商業的授權合約支援的磁碟機傳送？**</span><span class="sxs-lookup"><span data-stu-id="69308-248">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="69308-p136">使用透過 Microsoft Enterprise Agreement (EA) 傳送至 PST 檔案匯入 Office 365 的磁碟機。磁碟機傳送無法透過 Microsoft 產品和服務合約 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="69308-p136">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="69308-251">**什麼是使用傳送至 PST 檔案匯入 Office 365 的磁碟機的定價？**</span><span class="sxs-lookup"><span data-stu-id="69308-251">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="69308-p137">若要使用的磁碟機傳送至 PST 檔案匯入 Office 365 信箱成本是 $2 USD 每 GB 的資料。例如，如果您隨附包含 1000 GB (1 TB) 的 PST 檔案的硬碟，成本是 $2000 USD。您可以使用合作夥伴支付匯入費用。如需尋找協力廠商的資訊，請參閱[尋找 Office 365 協力廠商或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="69308-p137">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="69308-256">**支援何種類型的硬碟的磁碟機傳送？**</span><span class="sxs-lookup"><span data-stu-id="69308-256">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="69308-p138">僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。您可以使用硬碟最多 10 TB。匯入的工作會處理在硬碟上的只有第一個資料量。資料磁碟區必須以 NTFS 格式化。時將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加或 2.5 或 3.5 英吋 SATA II/III 連接器或您可以附加外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 吋 SATA II/III USB 介面卡。</span><span class="sxs-lookup"><span data-stu-id="69308-p138">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="69308-p139">內建的 USB 介面卡隨附的外部硬碟不支援的 Office 365 匯入服務。此外，不能使用的磁碟內外部的硬碟磁碟機的大小寫。請不要隨附外部硬碟。</span><span class="sxs-lookup"><span data-stu-id="69308-p139">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="69308-265">**單一匯入工作可以隨附多少硬碟？**</span><span class="sxs-lookup"><span data-stu-id="69308-265">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="69308-266">您可以隨附最多 10 個硬碟的單一匯入工作。</span><span class="sxs-lookup"><span data-stu-id="69308-266">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="69308-267">**我隨附我硬碟的磁碟機之後，沒有多少時間要取得之 Microsoft 資料中心？**</span><span class="sxs-lookup"><span data-stu-id="69308-267">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="69308-p140">取決於一些事項，例如 Microsoft 資料中心在接近和用以隨附您的硬碟 （例如下, 一步] 時差傳遞、 兩天傳遞或地上傳遞） 何種傳送選項。您可以使用大部分 shippers 追蹤數追蹤您傳送的狀態。</span><span class="sxs-lookup"><span data-stu-id="69308-p140">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="69308-270">**「 我的硬碟抵達 Microsoft 資料中心之後，沒有多少時間來我 PST 檔案上傳至 Azure？**</span><span class="sxs-lookup"><span data-stu-id="69308-270">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="69308-p141">您的硬碟接收於 Microsoft 資料中心之後，則需要 7 到 10 商務數天才能 PST 檔案上傳至您的組織的 Microsoft Azure 儲存區之間。PST 檔案將上傳至名為 Azure blob 容器`ingestiondata`。</span><span class="sxs-lookup"><span data-stu-id="69308-p141">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="69308-273">**PST 檔案匯入至信箱需要多久的時間？**</span><span class="sxs-lookup"><span data-stu-id="69308-273">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="69308-p142">PST 檔案上傳至 Azure 儲存區之後，Office 365 以方式分析 PST 檔案中的資料 （安全且安全的方式） 來識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成這項分析時，您必須匯入 PST 檔案中的所有資料的選項或設定篩選器的控制哪些資料取得匯入。當您啟動匯入工作後，PST 檔案匯入至少 24 GB 每天率的 Office 365 信箱。如果此速率不符合您的需求，您可能會考慮將電子郵件資料匯入 Office 365 的其他方法。如需詳細資訊，請參閱 ＜[移轉至 Office 365 的多個電子郵件帳戶的方式](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="69308-p142">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="69308-p143">如果不同的 PST 檔案匯入至不同的目標信箱、 匯入程序會發生平行;換句話說，每 PST/信箱對匯入同時。同樣地，如果多個 PST 檔案匯入至相同信箱，這些會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="69308-p143">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="69308-281">**Microsoft 將 「 我的 PST 檔案上傳至 Azure 之後，時間是他們保持在 Azure 中刪除之前？**</span><span class="sxs-lookup"><span data-stu-id="69308-281">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="69308-282">所有 PST 檔案在 Azure 的儲存位置的組織 (在名為 blob 容器`ingestiondata`)，會刪除在 [安全性] 的 [**匯入**] 頁面上建立的最新的匯入工作後的 30 天&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="69308-282">All PST files in the Azure storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="69308-p144">這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示清單中的安全性完成的匯入工作的檔案&amp;規範中心。雖然匯入工作仍可能會列在 [**匯入**] 頁面上的 [安全性]&amp;規範中心 PST 檔案的清單可能會是空的較舊的匯入工作詳細資料檢視時。</span><span class="sxs-lookup"><span data-stu-id="69308-p144">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="69308-285">**將匯入 Office 365 支援 PST 檔案格式的版本？**</span><span class="sxs-lookup"><span data-stu-id="69308-285">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="69308-p145">有兩個版本的 PST 檔案格式： ANSI 與 Unicode。建議您匯入使用 Unicode PST 檔案格式的檔案。不過，使用 ANSI PST 檔案格式，例如語言之使用雙位元組字元的檔案 (DBCS)，也可匯入 Office 365。如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用傳送至匯入至 Office 365 組織 PST 檔案的磁碟機](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="69308-p145">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="69308-290">此外，從 Outlook 2007 或更新版本的 PST 檔案可以匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="69308-290">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="69308-291">**是否有將郵件大小限制時匯入 PST 檔案？**</span><span class="sxs-lookup"><span data-stu-id="69308-291">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="69308-p146">[是]。如果 PST 檔案包含大於 150 MB 的信箱項目，則會略過之項目的匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="69308-p146">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="69308-294">**是郵件內容，例如郵件已傳送或接收的收件者和其他屬性，PST 檔案匯入至 Office 365 信箱時保留清單？**</span><span class="sxs-lookup"><span data-stu-id="69308-294">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="69308-p147">[是]。匯入程序期間未變更的原始郵件中繼資料</span><span class="sxs-lookup"><span data-stu-id="69308-p147">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="69308-297">**是否有限制 PST 檔案所要匯入信箱資料夾階層中的層級數目吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-297">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="69308-p148">[是]。您不能有個巢狀資料夾 300 或多個層級的 PST 檔案匯入。</span><span class="sxs-lookup"><span data-stu-id="69308-p148">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="69308-300">**可以使用的磁碟機傳送至 PST 檔案匯入 Office 365 中的非使用中信箱吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-300">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="69308-301">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="69308-301">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="69308-302">**可以使用的磁碟機傳送至 PST 檔案匯入線上封存信箱在 Exchange 混合部署吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-302">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="69308-303">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="69308-303">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="69308-304">**可以使用的磁碟機傳送至 PST 檔案匯入 Exchange Online 中公用資料夾嗎？**</span><span class="sxs-lookup"><span data-stu-id="69308-304">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="69308-305">否，您不能 PST 檔案匯入的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="69308-305">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="69308-306">**可以 Microsoft 清除我硬碟之前所隨附給我, 吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-306">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="69308-p149">否，Microsoft 無法抹除之前傳送其返回客戶的硬碟。硬碟會以相同交易時收到 microsoft 的狀態傳回給您。</span><span class="sxs-lookup"><span data-stu-id="69308-p149">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="69308-309">**Microsoft 切割我硬碟，而非傳送給我可以吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-309">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="69308-p150">否，Microsoft 無法終結您的硬碟。硬碟會以相同交易時收到 microsoft 的狀態傳回給您。</span><span class="sxs-lookup"><span data-stu-id="69308-p150">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="69308-312">**傳回傳送支援何種 courier 服務？**</span><span class="sxs-lookup"><span data-stu-id="69308-312">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="69308-p151">如果您是在美國和歐洲客戶，Microsoft 使用 FedEx 傳回您的硬碟。所有其他區域 （英文）、 Microsoft 使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="69308-p151">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="69308-315">**傳回的運費成本為何？**</span><span class="sxs-lookup"><span data-stu-id="69308-315">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="69308-p152">會傳回運費成本而異，您接近 Microsoft 資料中心的傳送至您的硬碟。Microsoft 將 bill 您 FedEx 或 DHL 帳戶來傳回您的硬碟。傳回傳送的成本是您的責任。</span><span class="sxs-lookup"><span data-stu-id="69308-p152">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="69308-319">**可以使用自訂 courier 傳送服務，例如 FedEx 自訂傳送，以隨附我硬碟向 Microsoft 吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-319">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="69308-320">是。</span><span class="sxs-lookup"><span data-stu-id="69308-320">Yes.</span></span>
  
 <span data-ttu-id="69308-321">**如果我有隨附我硬碟至另一個國家/地區、 是否有我需要執行的任何項目吗？**</span><span class="sxs-lookup"><span data-stu-id="69308-321">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="69308-p153">您以 Microsoft 隨附的硬碟機可能必須跨多語系的框線。如果是這樣，則已負責確保該硬碟及它所包含的資料會匯入及/或匯出符合適用法。之前傳送的硬碟，請確認該磁碟機和資料可以法律上幫助將傳送到指定的 Microsoft 資料中心位顧問。這有助於確保它達到 Microsoft 及時。</span><span class="sxs-lookup"><span data-stu-id="69308-p153">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
