---
title: 將 PST 檔案匯入至 Office 365 的常見問題集
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '常見問題集的系統管理員如何使用 Office 365 匯入服務 organizaiton 的 PST 檔案匯入到 Office 365 信箱。 '
ms.openlocfilehash: 69767353a574336351b01fdc42a9c6117c5c31ed
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999586"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>將 PST 檔案匯入至 Office 365 的常見問題集

**本文適用於系統管理員。您想要將 PST 檔案匯入您自己的信箱？請參閱[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
以下是一些常見問題大量匯入 PST 檔案複製到 Office 365 信箱來使用 Office 365 匯入服務。 如需如何匯入 PST 檔案的詳細資訊，請參閱 < <b0>Overview of 匯入 PST 檔案複製到 Office 365</b0>。
  
## <a name="using-network-upload-to-import-pst-files"></a>使用網路上傳將 PST 檔案匯入

如需逐步指示，請參閱 <<c0>使用網路上傳至 Office 365 的 PST 檔案匯入。
  
 **查看的權限，才能在 Office 365 匯入服務中建立匯入工作？**
  
您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 將 PST 檔案匯入 Office 365 信箱。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
  
此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：
  
- 您必須獲指派 「 郵件收件者角色在 Exchange Online。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必須是 Office 365 組織中的全域系統管理員。
    
> [!TIP]
> 請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。 若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。 
  
 **所在可用的網路上傳？**
  
在美國、 加拿大、 巴西、 英國、 法國、 歐洲、 印度、 東亞、 東南亞 （日本）、 大韓民國和澳洲網路上傳是目前無法使用。 Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在 Microsoft 365 系統管理中心中完成的匯入工作的檔案清單中。 雖然匯入工作仍可能會列在 [**匯入資料到 Office 365** ] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 不過，使用 ANSI PST 檔案格式，例如使用雙位元組字元的語言的檔案集 (DBCS)，也可匯入 Office 365。 如需匯入 ANSI PST 檔案的詳細資訊，請參閱 <<c0>使用網路上傳至匯入組織的 PST 檔案複製到 Office 365中的步驟 4。
  
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
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用磁碟機運送將 PST 檔案匯入

如需逐步指示，請參閱[使用磁碟機運送來匯入 PST 檔案複製到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
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
  
您的硬碟機接收的 Microsoft 資料中心之後，它需要 7 到 10 個工作天來將 PST 檔案上傳至您的組織的 Microsoft Azure 存放區域之間。 將上傳的 PST 檔案至名為**ingestiondata**的 Azure blob 容器。 
  
 **PST 檔案匯入至信箱需要多久的時間？**
  
PST 檔案上傳至 Azure 存放區域後，Office 365 會分析 （以安全無虞的方式） 的 PST 檔案中的資料來識別的項目並包含在 PST 檔案中的不同郵件類型的保留期限。 完成這項分析時，您必須匯入 PST 檔案中的所有資料的選項，或設定篩選器，以控制哪些資料取得匯入。 啟動匯入工作之後，匯入 PST 檔案至 Office 365 信箱至少 24 GB 每日的速率。 如果此工資率不符合您的需求，您可能會考慮其他方法來匯入至 Office 365 的電子郵件資料。 如需詳細資訊，請參閱[將移轉至 Office 365 的多個電子郵件帳戶](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同樣地，如果多個 PST 檔案匯入到同一個信箱，他們會同時匯入。
  
 **Microsoft 將我的 PST 檔案上傳至 Azure 之後，多久他們保持在 Azure 中在被刪除之前？**
  
Azure 儲存體位置中所有的 PST 檔案，為您的組織 （在 blob 容器中名為**ingestiondata** ），會刪除最新的匯入工作在安全性 & 合規性中心的 [**匯入**] 頁面上建立後的 30 天。 
  
這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在安全性 & 合規性中心中完成的匯入工作的檔案清單中。 雖然匯入工作仍可能會列在 [安全性 & 合規性中心的 [**匯入**] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 不過，使用 ANSI PST 檔案格式，例如使用雙位元組字元的語言的檔案集 (DBCS)，也可匯入 Office 365。 如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁碟機運送來匯入 PST 檔案複製到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。
  
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
