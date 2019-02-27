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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 系統管理員： 了解如何使用 Office 365 安全性匯入服務&amp;規範中心以大量匯入電子郵件資料 （PST 檔案） 至 Exchange Online 中的使用者信箱。本主題提供常見問題集並說明 PST 匯入程序的運作方式。
ms.openlocfilehash: 89aa1a351d0a9bcc70819f4b2657d04adc7599e2
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296776"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> 本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)

您可以使用匯入服務 Office 365 安全性&amp;規範中心以快速大量匯入 PST 檔案至 Office 365 組織中的 Exchange Online 信箱。有兩種方式可以 PST 檔案匯入 Office 365：
   
- **網路上傳**![雲端上傳](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)-將 PST 檔案上傳至 Microsoft 雲端 Azure 的暫存位置網路。然後您可使用的匯入 Office 365 服務資料匯入 PST 信箱 Office 365 組織中。 

- **磁碟機之後傳送**![硬碟](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png)-將 PST 檔案複製到 BitLocker 加密的硬碟與實際運送給 Microsoft 的磁碟機。當 Microsoft 收到硬碟時、 資料中心人員將資料上傳至 Microsoft 雲端中暫時 Azure 儲存位置。然後您可以使用匯入 Office 365 服務資料匯入 Office 365 組織的信箱。

## <a name="step-by-step-instructions"></a>逐步說明
  
請參閱下列主題的詳細逐步說明大量匯入至 Office 365 組織的 PST 檔案的其中一個。 
   
- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)
- [使用磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>匯入 PST 檔案的運作方式

以下是圖及描述之完整 PST 匯入程序。圖顯示主要工作流程並會醒目提示的網路上傳和磁碟機傳送方法之間的差異。
  
![PST 匯入程序的工作流程](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **下載 PST 匯入工具和關鍵私人 Azure 儲存位置**-第一個步驟是要下載 PST 檔案上傳或將其複製到硬碟使用的工具和存取金鑰。您可以取得這些 Office 365 安全性 [**匯入**] 頁面中&amp;規範中心。索引鍵提供 PST 檔案上傳至的私人和安全 Azure 儲存位置的必要權限您 （或 Microsoft 資料中心人員但如果是磁碟機傳送）。此存取索引鍵是唯一的您的組織和協助防止 PST 檔案的未經授權的存取他們正在上傳至 Microsoft cloud 之後。請注意將 PST 檔案匯入 Office 365 不需要有不同的 Azure 訂閱貴組織。 
    
2. **上傳] 或 [副本 PST 檔案**-下一步取決於您正在使用網路上傳或磁碟機傳送匯入 PST 檔案。在這兩種情況下，您將使用的工具與您在上一個步驟中取得的安全認證儲存索引鍵。
    
    - **網路上傳**（在步驟 1 中下載） AzCopy.exe 工具可上傳並儲存在 Microsoft 雲端 Azure 的儲存位置的 PST 檔案。請注意 Azure 儲存位置的上傳至 PST 檔案位於同一個地區 Office 365 組織所在的 Microsoft 資料中心。 
    
      若要將其上傳，您想要匯入 Office 365 的 PST 檔案必須位於檔案共用或組織中的檔案伺服器。
    
    - **磁碟機之後傳送**（在步驟 1 中下載） WAImportExport.exe 工具用來將 PST 檔案複製到硬碟。此工具硬碟與 BitLocker 會加密，則會 Pst 複製到硬碟。像網路上傳您想要複製到硬碟的 PST 檔案必須位於檔案共用或組織中的檔案伺服器。
    
3. **建立 PST 匯入對應檔案**-PST 檔案已上傳至 Azure 儲存位置或複製到硬碟的磁碟機之後下, 一步是建立指定哪些使用者信箱 PST 檔案是否將匯入以逗點分隔的值 (CSV) 檔案 (nd PST 檔案可匯入使用者的主要信箱或封存信箱）。匯入 Office 365 服務將使用的資訊來匯入 PST 檔案。 
    
4. **建立 PST 匯入工作**-下一個步驟是在 [安全性] 的 [**匯入**] 頁面上建立 PST 匯入工作&amp;規範中心並送出在上一個步驟中建立之 PST 匯入對應檔案。網路上傳 （因為 PST 檔案已上載至 Azure） Office 365 分析 PST 檔案中的資料並再提供讓您設定控制哪些資料實際取得匯入至信箱 PST 匯入對應檔案中指定的篩選器。 
    
    磁碟機傳送的一些其他情況將會發生在此程序中的點。
    
    - 實體出貨至 （匯入工作會在建立時，會顯示 Microsoft 資料中心的運送位址） 的 Microsoft 資料中心硬碟
    
    - 當 Microsoft 收到硬碟時、 資料中心人員將組織的 Azure 儲存位置上傳 Pst 檔案在硬碟上。如先前所述 PST 檔案上傳至位於相同的區域 Microsoft 資料中心的 Office 365 組織所在 Azure 儲存位置。
    
      > [!NOTE]
      > 在硬碟上的 PST 檔案上傳至 Azure 7 到 10 商務天後 Microsoft 接收硬碟內。 
  
      網路上傳程序，例如 Office 365 然後分析 PST 檔案中的資料與可讓您設定控制哪些資料實際取得匯入至信箱 PST 匯入對應檔案中指定的篩選器機會。
    
    - Microsoft 提供給您的硬碟。 
    
5. **篩選所要匯入至信箱的 PST 資料**-Office 365 建立匯入工作後 （與之後的磁碟機傳送工作的 PST 檔案上傳至 Azure 儲存位置） （安全地和安全地） 依照 」 分析的 PST 檔案中的資料用來識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成分析，且資料已準備好要匯入，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。 
    
6. **啟動 PST 匯入工作**-開始匯入工作之後，Office 365 資訊檔案中使用 PST 匯入對應從他 Azure 儲存位置的 Pst 檔案匯入至使用者信箱。在 [安全性] 的 [**匯入**] 頁面上會顯示狀態資訊 （包括要匯入每個 PST 檔案的相關資訊） 匯入工作&amp;規範中心。匯入工作完成時，設置**完成**之工作的狀態。
  
## <a name="why-import-email-data-to-office-365"></a>為什麼要選擇電子郵件將資料匯入 Office 365？

- 將 PST 檔案匯入使用者的信箱為貴組織的電子郵件移轉至 Office 365 的其中一個方法。
    
- 您可以使用[智慧型匯入](filter-data-when-importing-pst-files.md)功能來篩選實際取得匯入至目標信箱的 PST 檔案中的項目。此屬性可讓修剪匯入藉由設定篩選器的資料控制哪些資料取得匯入。 
    
- 將電子郵件資料匯入 Office 365 來可讓您有助於組織的地址規範需求：
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)與其他信箱的儲存空間提供使用者[不受限制的封存](unlimited-archiving.md)。 
    
  - 將信箱[訴訟](https://go.microsoft.com/fwlink/?linkid=841243)保留內容。 
    
  - 使用 「[內容搜尋工具](content-search.md)來搜尋信箱內容。 
    
  - 使用[eDiscovery 案例](ediscovery-cases.md)來管理您的組織法律調查 
    
  - 在 [安全性] 中使用[保留原則](retention-policies.md)&amp;規範中心來控制信箱內容保留期限，然後刪除內容之後保留期間到期。 
    
- 將資料匯入 Office 365 協助防止資料遺失。匯入至 Office 365 的電子郵件資料繼承 Exchange Online 的高可用性的功能。
    
- 因為它會儲存在雲端中的使用者從所有裝置使用 Office 365 中的電子郵件資料。
    
## <a name="importing-sharepoint-data-to-office-365"></a>將 SharePoint 資料匯入 Office 365

您也可以在 Office 365 組織中的 SharePoint 網站和 OneDrive 帳戶匯檔案和文件。如需詳細資訊，請參閱下列文章：

- [移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 移轉工具簡介](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [使用 PowerShell 移轉至 SharePoint Online](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [移轉至 SharePoint Online Azure 的資料] 方塊中的檔案共用內容](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>常見問題將 PST 檔案匯入 Office 365
  
以下是一些常見問題使用大量匯入至 Office 365 信箱的 PST 檔案匯入 Office 365 服務。 
  
- [若要匯入 PST 檔案使用網路上傳](#using-network-upload-to-import-pst-files)
  
- [若要匯入 PST 檔案中使用的磁碟機傳送](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>若要匯入 PST 檔案使用網路上傳

 **不需要在 Office 365 匯入服務中建立匯入工作哪些權限？**
  
您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。或者您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後將自己或其他使用者新增為成員。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
  
此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：
  
- 您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。
    
    或
    
- 您必須是 Office 365 組織中的全域管理員。
    
> [!TIP]
> 請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。 
  
 **哪裡可用的網路上傳？**
  
網路上傳位於目前可用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 中文、 東南亞洲 （日本）、 共和國的韓國及澳洲。網路上傳會提供多個地區中推出。
  
 **什麼是匯入 PST 檔案使用網路上傳定價？**
  
使用網路上傳匯入 PST 檔案是自由。
  
這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示在清單中的 Office 365 系統管理中心中完成的匯入工作的檔案。匯入工作仍可能會列在 [**匯入至 Office 365 的資料**] 頁面上，雖然 PST 檔案的清單可能空白時檢視較舊的匯入工作的詳細資料。 
  
 **將匯入 Office 365 支援 PST 檔案格式的版本？**
  
有兩個版本的 PST 檔案格式： ANSI 與 Unicode。建議您匯入使用 Unicode PST 檔案格式的檔案。不過，使用 ANSI PST 檔案格式，例如語言之使用雙位元組字元的檔案 (DBCS)，也可匯入 Office 365。如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用網路上傳至匯入至 Office 365 的 PST 檔案](https://go.microsoft.com/fwlink/p/?LinkId=823074)中的步驟 4。
  
此外，從 Outlook 2007 或更新版本的 PST 檔案可以匯入至 Office 365。
  
 **我將 「 我的 PST 檔案上傳至 Azure 儲存區之後，時間是他們保持在 Azure 中刪除之前？**
  
當您使用的網路上傳方法匯入 PST 檔案時，您將其上傳至名為**ingestiondata**Azure blob 容器。如果沒有匯入工作進行中在 [**匯入**] 頁面中有安全性&amp;規範中心)，然後在 Azure **ingestiondata**容器中的所有 PST 檔案會都刪除 30 天後安全性&amp;規範中心。這也表示您必須建立新的匯入工作安全性&amp;規範中心 （所述之步驟 5 中的網路上傳指示） 內 30 天的上傳 PST 檔案至 Azure。 
  
這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示清單中的安全性完成的匯入工作的檔案&amp;規範中心。雖然匯入工作仍可能會列在 [**匯入**] 頁面上的 [安全性]&amp;規範中心 PST 檔案的清單可能會是空的較舊的匯入工作詳細資料檢視時。 
  
 **PST 檔案匯入至信箱需要多久的時間？**
  
它取決於您的網路容量，但它通常採用的每個 tb 的資料要上傳至您的組織的 Azure 儲存區的數個小時。PST 檔案複製到 Azure 儲存區之後，會 PST 檔案匯入到 Office 365 信箱至少 24 GB 的每日的速率。如果此速率不符合您的需求，您可能會考慮將電子郵件資料移轉至 Office 365 的其他方法。如需詳細資訊，請參閱 ＜[移轉至 Office 365 的多個電子郵件帳戶的方式](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果不同的 PST 檔案匯入至不同的目標信箱、 匯入程序會發生平行;換句話說，每 PST/信箱對匯入同時。同樣地，如果多個 PST 檔案匯入至相同信箱，這些會同時匯入。
  
 **是否有將郵件大小限制時匯入 PST 檔案？**
  
[是]。如果 PST 檔案包含大於 150 MB 的信箱項目，則會略過之項目的匯入程序期間。
  
 **是郵件內容，例如郵件已傳送或接收的收件者和其他屬性，PST 檔案匯入至 Office 365 信箱時保留清單？**
  
[是]。原始郵件中繼資料不匯入程序期間變更。
  
 **是否有限制 PST 檔案所要匯入信箱資料夾階層中的層級數目吗？**
  
[是]。您不能有個巢狀資料夾 300 或多個層級的 PST 檔案匯入。
  
 **可以使用網路上傳至 PST 檔案匯入 Office 365 中的非使用中信箱吗？**
  
是，這項功能現在使用。
  
 **可以使用網路上傳至 PST 檔案匯入線上封存信箱在 Exchange 混合部署吗？**
  
是，這項功能現在使用。
  
 **可以使用網路上傳至 PST 檔案匯入 Exchange Online 中公用資料夾嗎？**
  
否，您不能 PST 檔案匯入的公用資料夾。
  
### <a name="using-drive-shipping-to-import-pst-files"></a>若要匯入 PST 檔案中使用的磁碟機傳送

 **不需要在 Office 365 匯入服務中建立匯入工作哪些權限？**
  
您必須指派信箱匯入匯出至 PST 檔案匯入 Office 365 信箱角色。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。或者您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後將自己或其他使用者新增為成員。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
  
此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：
  
- 您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。
    
    或
    
- 您必須是 Office 365 組織中的全域管理員。
    
> [!TIP]
> 請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。 
  
 **其中磁碟機傳送可用？**
  
磁碟機傳送位於目前可用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 中文、 東南亞洲 （日本）、 共和國的韓國及澳洲。磁碟機傳送會提供多個地區中推出。
  
 **何種商業的授權合約支援的磁碟機傳送？**
  
使用透過 Microsoft Enterprise Agreement (EA) 傳送至 PST 檔案匯入 Office 365 的磁碟機。磁碟機傳送無法透過 Microsoft 產品和服務合約 (MPSA)。
  
 **什麼是使用傳送至 PST 檔案匯入 Office 365 的磁碟機的定價？**
  
若要使用的磁碟機傳送至 PST 檔案匯入 Office 365 信箱成本是 $2 USD 每 GB 的資料。例如，如果您隨附包含 1000 GB (1 TB) 的 PST 檔案的硬碟，成本是 $2000 USD。您可以使用合作夥伴支付匯入費用。如需尋找協力廠商的資訊，請參閱[尋找 Office 365 協力廠商或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **支援何種類型的硬碟的磁碟機傳送？**
  
僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。您可以使用硬碟最多 10 TB。匯入的工作會處理在硬碟上的只有第一個資料量。資料磁碟區必須以 NTFS 格式化。時將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加或 2.5 或 3.5 英吋 SATA II/III 連接器或您可以附加外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 吋 SATA II/III USB 介面卡。
  
> [!IMPORTANT]
> 內建的 USB 介面卡隨附的外部硬碟不支援的 Office 365 匯入服務。此外，不能使用的磁碟內外部的硬碟磁碟機的大小寫。請不要隨附外部硬碟。 
  
 **單一匯入工作可以隨附多少硬碟？**
  
您可以隨附最多 10 個硬碟的單一匯入工作。
  
 **我隨附我硬碟的磁碟機之後，沒有多少時間要取得之 Microsoft 資料中心？**
  
取決於一些事項，例如 Microsoft 資料中心在接近和用以隨附您的硬碟 （例如下, 一步] 時差傳遞、 兩天傳遞或地上傳遞） 何種傳送選項。您可以使用大部分 shippers 追蹤數追蹤您傳送的狀態。
  
 **「 我的硬碟抵達 Microsoft 資料中心之後，沒有多少時間來我 PST 檔案上傳至 Azure？**
  
您的硬碟接收於 Microsoft 資料中心之後，則需要 7 到 10 商務數天才能 PST 檔案上傳至您的組織的 Microsoft Azure 儲存區之間。PST 檔案將上傳至名為 Azure blob 容器`ingestiondata`。 
  
 **PST 檔案匯入至信箱需要多久的時間？**
  
PST 檔案上傳至 Azure 儲存區之後，Office 365 以方式分析 PST 檔案中的資料 （安全且安全的方式） 來識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成這項分析時，您必須匯入 PST 檔案中的所有資料的選項或設定篩選器的控制哪些資料取得匯入。當您啟動匯入工作後，PST 檔案匯入至少 24 GB 每天率的 Office 365 信箱。如果此速率不符合您的需求，您可能會考慮將電子郵件資料匯入 Office 365 的其他方法。如需詳細資訊，請參閱 ＜[移轉至 Office 365 的多個電子郵件帳戶的方式](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果不同的 PST 檔案匯入至不同的目標信箱、 匯入程序會發生平行;換句話說，每 PST/信箱對匯入同時。同樣地，如果多個 PST 檔案匯入至相同信箱，這些會同時匯入。
  
 **Microsoft 將 「 我的 PST 檔案上傳至 Azure 之後，時間是他們保持在 Azure 中刪除之前？**
  
所有 PST 檔案在 Azure 的儲存位置的組織 (在名為 blob 容器`ingestiondata`)，會刪除在 [安全性] 的 [**匯入**] 頁面上建立的最新的匯入工作後的 30 天&amp;規範中心。 
  
這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示清單中的安全性完成的匯入工作的檔案&amp;規範中心。雖然匯入工作仍可能會列在 [**匯入**] 頁面上的 [安全性]&amp;規範中心 PST 檔案的清單可能會是空的較舊的匯入工作詳細資料檢視時。 
  
 **將匯入 Office 365 支援 PST 檔案格式的版本？**
  
有兩個版本的 PST 檔案格式： ANSI 與 Unicode。建議您匯入使用 Unicode PST 檔案格式的檔案。不過，使用 ANSI PST 檔案格式，例如語言之使用雙位元組字元的檔案 (DBCS)，也可匯入 Office 365。如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用傳送至匯入至 Office 365 組織 PST 檔案的磁碟機](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。
  
此外，從 Outlook 2007 或更新版本的 PST 檔案可以匯入至 Office 365。
  
 **是否有將郵件大小限制時匯入 PST 檔案？**
  
[是]。如果 PST 檔案包含大於 150 MB 的信箱項目，則會略過之項目的匯入程序期間。
  
 **是郵件內容，例如郵件已傳送或接收的收件者和其他屬性，PST 檔案匯入至 Office 365 信箱時保留清單？**
  
[是]。匯入程序期間未變更的原始郵件中繼資料
  
 **是否有限制 PST 檔案所要匯入信箱資料夾階層中的層級數目吗？**
  
[是]。您不能有個巢狀資料夾 300 或多個層級的 PST 檔案匯入。
  
 **可以使用的磁碟機傳送至 PST 檔案匯入 Office 365 中的非使用中信箱吗？**
  
是，這項功能現在使用。
  
 **可以使用的磁碟機傳送至 PST 檔案匯入線上封存信箱在 Exchange 混合部署吗？**
  
是，這項功能現在使用。
  
 **可以使用的磁碟機傳送至 PST 檔案匯入 Exchange Online 中公用資料夾嗎？**
  
否，您不能 PST 檔案匯入的公用資料夾。
  
 **可以 Microsoft 清除我硬碟之前所隨附給我, 吗？**
  
否，Microsoft 無法抹除之前傳送其返回客戶的硬碟。硬碟會以相同交易時收到 microsoft 的狀態傳回給您。
  
 **Microsoft 切割我硬碟，而非傳送給我可以吗？**
  
否，Microsoft 無法終結您的硬碟。硬碟會以相同交易時收到 microsoft 的狀態傳回給您。
  
 **傳回傳送支援何種 courier 服務？**
  
如果您是在美國和歐洲客戶，Microsoft 使用 FedEx 傳回您的硬碟。所有其他區域 （英文）、 Microsoft 使用 DHL。
  
 **傳回的運費成本為何？**
  
會傳回運費成本而異，您接近 Microsoft 資料中心的傳送至您的硬碟。Microsoft 將 bill 您 FedEx 或 DHL 帳戶來傳回您的硬碟。傳回傳送的成本是您的責任。
  
 **可以使用自訂 courier 傳送服務，例如 FedEx 自訂傳送，以隨附我硬碟向 Microsoft 吗？**
  
是。
  
 **如果我有隨附我硬碟至另一個國家/地區、 是否有我需要執行的任何項目吗？**
  
您以 Microsoft 隨附的硬碟機可能必須跨多語系的框線。如果是這樣，則已負責確保該硬碟及它所包含的資料會匯入及/或匯出符合適用法。之前傳送的硬碟，請確認該磁碟機和資料可以法律上幫助將傳送到指定的 Microsoft 資料中心位顧問。這有助於確保它達到 Microsoft 及時。
