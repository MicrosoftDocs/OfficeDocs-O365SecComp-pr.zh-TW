---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 系統管理員： 了解如何使用匯入服務安全性 & 合規性中心中大量匯入電子郵件資料 （PST 檔案） 到 Exchange Online 中的使用者信箱。 本主題提供常見問題集，並說明 PST 匯入程序的運作方式。
ms.openlocfilehash: ab623c531f5e322a99aef5c8c33f110fc140a6f7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154217"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> 本文適用於系統管理員。 您是否正嘗試匯入 PST 檔案到自己的信箱？ 請參閱[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)

您可以用於匯入服務的安全性 & 合規性中心快速大量匯入 PST 檔案複製到 Exchange Online 信箱在您的 Office 365 組織中。 有兩種方式，您可以將 PST 檔案匯入至 Office 365:
   
- **網路上傳**![雲端上傳](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)-透過網路以 Microsoft cloud 中的暫存的 Azure 儲存體位置上傳的 PST 檔案。 然後您可以使用 Office 365 匯入服務資料匯入 PST 信箱 Office 365 組織中。 

- **磁碟機運送**![硬碟](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png)-將 PST 檔案複製到 BitLocker 加密的硬碟與實際運送給 Microsoft 的磁碟機。 當 Microsoft 收到硬碟時，資料中心人員將資料上傳至 Microsoft cloud 中的暫存的 Azure 儲存體位置。 然後您可以使用 Office 365 匯入服務將 Office 365 組織中將資料匯入信箱。

## <a name="step-by-step-instructions"></a>逐步指示
  
請參閱下列主題中的大量匯入組織的 PST 檔案複製到 Office 365 的詳細逐步說明。 
   
- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)
- [使用磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>匯入 PST 檔案的運作方式

以下是圖例和完整的 PST 匯入程序的說明。 圖例會顯示主要工作流程，並會醒目提示的網路上傳和磁碟機運送方法之間的差異。
  
![PST 匯入程序的工作流程](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **下載 PST 匯入工具及金鑰為私人的 Azure 儲存體位置**-第一個步驟是下載用來上傳的 PST 檔案或將其複製到硬碟的工具和存取索引鍵。 您取得這些從安全性 & 合規性中心中的 [**匯入**] 頁面。 機碼上傳 PST 檔案至私人且安全的 Azure 儲存體位置的必要權限可提供您 （或 Microsoft 資料中心人員在磁碟機運送的情況下）。 此便捷鍵是唯一的您的組織，並協助防止未經授權的存取您的 PST 檔案之後他們正在上傳至 Microsoft 雲端。 請注意，將 PST 檔案匯入至 Office 365 不會要求您的組織有不同的 Azure 訂用帳戶。 
    
2. **上傳或將 PST 檔案複製**-下一步取決於您是否使用網路上傳或磁碟機運送將 PST 檔案匯入。 在這兩種情況下，您將使用工具和您在上一個步驟中所取得的安全存放裝置金鑰。
    
    - **網路上傳**AzCopy.exe 工具 （在步驟 1 中下載） 用來上傳，並在 Microsoft cloud 中的 Azure 儲存體位置儲存您的 PST 檔案。 請注意，您所上傳您的 PST 檔案至 Azure 儲存體位置位於同一個區域 Office 365 組織所在的 Microsoft 資料中心。 
    
      若要將其上傳，您想要匯入 Office 365 的 PST 檔案必須位於您組織中檔案共用或檔案。
    
    - **磁碟機運送**WAImportExport.exe 工具 （在步驟 1 中下載） 用來將您的 PST 檔案複製到硬碟。 這項工具硬碟使用 BitLocker 會加密，並再將 Pst 複製到硬碟。 像網路上傳的 PST 檔案，您想要複製到硬碟必須位於您組織中檔案共用或檔案。
    
3. **建立 PST 匯入對應檔案**-已上傳至 Azure 儲存體位置或複製到硬碟的 PST 檔案之後下, 一步是建立指定哪些使用者信箱的 PST 檔案會匯入至逗點分隔的值 (CSV) 檔案 (nd PST 檔案可以匯入至使用者的主要信箱或封存信箱）。 Office 365 匯入服務將使用資訊匯入 PST 檔案。 
    
4. **建立 PST 匯入工作**-下一個步驟是在安全性 & 合規性中心的 [**匯入**] 頁面上建立 PST 匯入工作並提交在上一個步驟中建立 PST 匯入對應檔案。 網路上傳 （因為已上載的 PST 檔案至 Azure） Office 365 分析的 PST 檔案中的資料，然後讓您有機會將篩選器來控制哪些資料實際取得匯入至 PST 匯入對應檔案中指定的信箱。 
    
    磁碟機運送的其他事項，即會發生在此程序中的點。
    
    - 實際運送硬碟給 Microsoft 資料中心 （建立匯入工作時，會顯示 Microsoft 資料中心的交貨地址）
    
    - 當 Microsoft 收到硬碟時，資料中心人員會至貴組織的 Azure 儲存體位置上傳 Pst 檔案在硬碟上。 如先前所述，您的 PST 檔案上傳至 Azure 儲存體位於相同的區域 Microsoft 資料中心的 Office 365 組織所在的位置。
    
      > [!NOTE]
      > 硬碟上的 PST 檔案上傳至 Azure 7 到 10 個工作天後 Microsoft 收到硬碟內。 
  
      網路上傳程序，例如 Office 365，然後分析的 PST 檔案中的資料，並讓您有機會將篩選器來控制哪些資料實際取得匯入至 PST 匯入對應檔案中指定的信箱。
    
    - Microsoft 發行給您的硬碟機。 
    
5. **篩選器，將會匯入至信箱的 PST 資料**-Office 365 建立匯入工作後 （和之後從磁碟機運送工作的 PST 檔案上傳至 Azure 儲存體位置） （安全且安全地） 由會分析的 PST 檔案中的資料用來識別項目並包含在 PST 檔案中的不同郵件類型的保留的期限。 當分析已完成，且可匯入資料時，您可以選擇要匯入 PST 檔案中所包含的所有資料，或您可以修剪匯入藉由設定篩選器來控制哪些資料取得匯入的資料。 
    
6. **啟動 PST 匯入工作**-啟動匯入工作後，Office 365 使用中的資訊 PST 匯入對應檔案從他的 Azure 儲存體位置的 Pst 檔案匯入至使用者信箱。 在安全性 & 合規性中心的 [**匯入**] 頁面上會顯示 （包括資訊匯入每個 PST 檔案） 匯入工作的狀態資訊。 匯入工作完成時，工作的狀態設為**完成**。
  
## <a name="why-import-email-data-to-office-365"></a>為什麼要匯入 Office 365 電子郵件資料？

- 將 PST 檔案匯入至使用者信箱是一種方式將貴組織的電子郵件移轉到 Office 365。
    
- 您可以使用[智慧型匯入](filter-data-when-importing-pst-files.md)功能來篩選實際取得匯入至目標信箱的 PST 檔案中的項目。 此屬性可讓您修剪所設定的篩選器，匯入的資料來控制哪些資料取得匯入。 
    
- 將電子郵件資料匯入 Office 365 讓您透過下列方式協助解決組織的法務遵循需求：
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)及[無限制封存](unlimited-archiving.md)以提供使用者額外的信箱儲存空間。 
    
  - 將信箱設[為訴訟暫止](https://go.microsoft.com/fwlink/?linkid=841243)來保留的內容。 
    
  - 使用[內容搜尋 」 工具](content-search.md)來搜尋的信箱內容。 
    
  - 使用[eDiscovery 案例](ediscovery-cases.md)來管理貴組織的法律調查 
    
  - 使用[保留原則](retention-policies.md)中的安全性 & 合規性中心，以控制多久信箱內容會保留，，，然後刪除內容之後保留期間到期。 

  - 使用[監督原則](supervision-policies.md)來檢查以確定其符合郵件標準，然後新增分類類型的郵件。
    
- 將資料匯入 Office 365，可協助防止資料遺失。 匯入至 Office 365 的電子郵件資料會繼承 Exchange Online 的高可用性的功能。
    
- Office 365 中的電子郵件資料是可從所有的裝置的使用者，因為它會儲存在雲端中。
    
## <a name="importing-sharepoint-data-to-office-365"></a>將 SharePoint 資料匯入 Office 365

您也可以匯入檔案和文件至 SharePoint 網站與 OneDrive 帳戶 Office 365 組織中。 如需詳細資訊，請參閱下列文章：

- [移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 移轉工具簡介](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [使用 PowerShell 移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [將您的檔案共用內容移轉至 SharePoint Online 使用 Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>關於將 PST 檔案匯入至 Office 365 常見問題
  
以下是一些常見問題大量匯入 PST 檔案複製到 Office 365 信箱來使用 Office 365 匯入服務。 
  
- [使用網路上傳將 PST 檔案匯入](#using-network-upload-to-import-pst-files)
  
- [使用磁碟機運送將 PST 檔案匯入](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>使用網路上傳將 PST 檔案匯入

 **查看的權限，才能在 Office 365 匯入服務中建立匯入工作？**
  
您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 將 PST 檔案匯入 Office 365 信箱。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
  
此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：
  
- 您必須獲指派 「 郵件收件者角色在 Exchange Online。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必須是 Office 365 組織中的全域系統管理員。
    
> [!TIP]
> 請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。 若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。 
  
 **所在可用的網路上傳？**
  
Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在 Microsoft 365 系統管理中心中完成的匯入工作的檔案清單中。 雖然匯入工作仍可能會列在 [**匯入資料到 Office 365** ] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 不過，使用 ANSI PST 檔案格式，例如使用雙位元組字元的語言的檔案集 (DBCS)，也可匯入 Office 365。 如需匯入 ANSI PST 檔案的詳細資訊，請參閱 <<c0>使用網路上傳至匯入 PST 檔案複製到 Office 365中的步驟 4。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **我將我的 PST 檔案上傳至 Azure 存放區域之後，多久他們保持在 Azure 中在被刪除之前？**
  
當您使用網路上傳方法匯入 PST 檔案時，您將它們上載至名為**ingestiondata**Azure blob 容器。 如果沒有匯入工作進行中**匯入**] 頁面上中有安全性 & 合規性中心），然後在 Azure 中的 [ **ingestiondata** ] 容器中的所有 PST 檔案會都刪除 30 天後安全性 & 中建立的最新的匯入工作合規性中心。 這也表示您必須建立新的匯入工作安全性 & （所述步驟 5 中的網路上傳指示） 的合規性中心中的將 PST 檔案上傳至 Azure 的 30 天內。 
  
這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在安全性 & 合規性中心中完成的匯入工作的檔案清單中。 雖然匯入工作仍可能會列在 [安全性 & 合規性中心的 [**匯入**] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。 
  
 **PST 檔案匯入至信箱需要多久的時間？**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. PST 檔案複製到 Azure 的儲存區之後，匯入 PST 檔案至 Office 365 信箱至少 24 GB 每日的速率。 如果此工資率不符合您的需求，您可以考慮將電子郵件資料移轉到 Office 365 的其他方法。 如需詳細資訊，請參閱[將移轉至 Office 365 的多個電子郵件帳戶](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同樣地，如果多個 PST 檔案匯入到同一個信箱，他們會同時匯入。
  
 **Is there a message size limit when importing PST files?**
  
是。 如果 PST 檔案包含大於 150 MB 的信箱項目，將匯入程序期間略過項目。
  
 **是郵件內容，例如當郵件已傳送或接收的收件者及其他屬性，當 PST 檔案匯入到 Office 365 信箱時保留清單？**
  
是。 在匯入程序期間不變更原始郵件中繼資料。
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **可以使用網路上傳將 PST 檔案匯入 Exchange Online 中公用資料夾？**
  
否，您無法將 PST 檔案匯入公用資料夾。
  
### <a name="using-drive-shipping-to-import-pst-files"></a>使用磁碟機運送將 PST 檔案匯入

 **查看的權限，才能在 Office 365 匯入服務中建立匯入工作？**
  
您必須被指派信箱匯入匯出角色將 PST 檔案匯入 Office 365 信箱。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
  
此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：
  
- 您必須獲指派 「 郵件收件者角色在 Exchange Online。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必須是 Office 365 組織中的全域系統管理員。
    
> [!TIP]
> 請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。 若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。 
  
 **其中磁碟機運送可用？**
  
磁碟機運送位於目前無法使用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 東亞、 東南亞 （日本）、 大韓民國和澳洲。 Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
磁碟機運送將 PST 檔案匯入 Office 365 可透過 Microsoft Enterprise Agreement (EA)。 磁碟機運送無法透過 Microsoft 產品和服務合約 (MPSA)。
  
 **使用磁碟機運送將 PST 檔案匯入 Office 365 價格是什麼？**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. 如需尋找合作夥伴的詳細資訊，請參閱[尋找您的 Office 365 合作夥伴或轉銷商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **What kind of hard drives are supported for drive shipping?**
  
僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 英吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。 You can use hard drives up to 10 TB. 對於匯入工作，將會處理只有第一個資料磁碟區在硬碟上。 The data volume must be formatted with NTFS. 當將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加 2.5 或 3.5 英吋 SATA II/III 連接器或外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 英吋 SATA II/III USB 介面卡，您可以附加。
  
> [!IMPORTANT]
> Office 365 匯入服務不支援外部硬碟隨附內建的 USB 介面卡。 Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **我的硬碟送達 Microsoft 資料中心之後，多久需要若要將 「 我的 PST 檔案上傳至 Azure？**
  
您的硬碟機接收的 Microsoft 資料中心之後，它需要 7 到 10 個工作天來將 PST 檔案上傳至您的組織的 Microsoft Azure 存放區域之間。 將上傳的 PST 檔案至名為的 Azure blob 容器`ingestiondata`。 
  
 **PST 檔案匯入至信箱需要多久的時間？**
  
PST 檔案上傳至 Azure 存放區域後，Office 365 會分析 （以安全無虞的方式） 的 PST 檔案中的資料來識別的項目並包含在 PST 檔案中的不同郵件類型的保留期限。 完成這項分析時，您必須匯入 PST 檔案中的所有資料的選項，或設定篩選器，以控制哪些資料取得匯入。 啟動匯入工作之後，匯入 PST 檔案至 Office 365 信箱至少 24 GB 每日的速率。 如果此工資率不符合您的需求，您可能會考慮其他方法來匯入至 Office 365 的電子郵件資料。 如需詳細資訊，請參閱[將移轉至 Office 365 的多個電子郵件帳戶](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同樣地，如果多個 PST 檔案匯入到同一個信箱，他們會同時匯入。
  
 **Microsoft 將我的 PST 檔案上傳至 Azure 之後，多久他們保持在 Azure 中在被刪除之前？**
  
Azure 儲存體位置中所有的 PST 檔案，為您的組織 (名為的 blob 容器中`ingestiondata`)，會刪除最新的匯入工作在安全性 & 合規性中心的 [**匯入**] 頁面上建立後的 30 天。 
  
這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在安全性 & 合規性中心中完成的匯入工作的檔案清單中。 雖然匯入工作仍可能會列在 [安全性 & 合規性中心的 [**匯入**] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 不過，使用 ANSI PST 檔案格式，例如使用雙位元組字元的語言的檔案集 (DBCS)，也可匯入 Office 365。 如需匯入 ANSI PST 檔案的詳細資訊，請參閱 < 步驟 3 中<b0>使用磁碟機運送來匯入至 Office 365 組織 PST 檔案</b0>。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
是。 如果 PST 檔案包含大於 150 MB 的信箱項目，將匯入程序期間略過項目。
  
 **是郵件內容，例如當郵件已傳送或接收的收件者及其他屬性，當 PST 檔案匯入到 Office 365 信箱時保留清單？**
  
是。 在匯入程序期間不變更原始郵件中繼資料
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **可以使用磁碟機運送將 PST 檔案匯入 Exchange Online 中公用資料夾？**
  
否，您無法將 PST 檔案匯入公用資料夾。
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft 可以切割我而不是傳送給我的硬碟？**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **寄回支援哪些快遞服務？**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **傳回的運費成本為何？**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **可以使用自訂 courier 傳送服務，例如 FedEx 自訂傳送，運送硬碟給 Microsoft 嗎？**
  
是。
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
