---
title: 使用磁碟機運送來匯入組織 PST 檔案至 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '系統管理員： 了解如何大量匯入組織的 PST 檔案複製到 Office 365 信箱將 PST 檔案複製到硬碟，然後將它傳送給 Microsoft。 '
ms.openlocfilehash: d0e2c155c267939755a85f30f1ad234dc57cfe5f
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999986"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>使用磁碟機運送來匯入組織 PST 檔案至 Office 365

**本文適用於系統管理員。您試圖將 PST 檔案匯入您自己的信箱？請參閱[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用 Office 365 匯入服務和磁碟機運送至大量匯入 PST 檔案複製到使用者信箱。 磁碟機運送代表您將 PST 檔案複製到硬碟，並實際運送磁碟機給 Microsoft。 當 Microsoft 收到您的硬碟時，資料中心人員會將資料從硬碟複製到 Microsoft Cloud 中的儲存區域。 然後您有機會修剪實際所匯入至目標信箱設定篩選器來控制哪些資料取得匯入 PST 資料。 啟動匯入工作之後，匯入服務從匯入 PST 資料存放區至使用者信箱。 使用磁碟機運送將 PST 檔案匯入使用者的信箱是一種方式將貴組織的電子郵件移轉到 Office 365。
  
若要使用的磁碟機運送將 PST 檔案匯入 Office 365 信箱所需的步驟如下：
  
[步驟 1： 下載 PST 匯入工具與安全存放裝置金鑰](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[步驟 2： 將 PST 檔案複製到硬碟](#step-2-copy-the-pst-files-to-the-hard-drive)

[步驟 3： 建立 PST 匯入對應檔案](#step-3-create-the-pst-import-mapping-file)

[步驟 4：在 Office 365 內建立 PST 匯入工作](#step-4-create-a-pst-import-job-in-office-365)

[步驟 5：運送硬碟給 Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[步驟 6： 篩選資料，並啟動 PST 匯入工作](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> 您必須執行步驟 1 一次向下載入安全存放裝置金鑰] 和 [匯入工具。 您執行這些步驟之後，請遵循步驟 2 到步驟 6 每的次您要運送硬碟給 Microsoft。 
  
常見問題關於使用磁碟機運送將 PST 檔案匯入 Office 365，請參閱[使用磁碟機運送將 PST 檔案匯入的常見問題集](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 將 PST 檔案匯入 Office 365 信箱。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：
    
  - 您必須獲指派 「 郵件收件者角色在 Exchange Online。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
  - 您必須是 Office 365 組織中的全域系統管理員。
    
    > [!TIP]
    > 請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。 若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。 
  
- 您需要將想要複製到硬碟上的 PST 檔案，儲存於檔案伺服器上，或是貴組織的共用資料夾。 在步驟 2 中，您會執行 Azure 匯入 / 匯出工具 (WAImportExport.exe)，將複製的 PST 檔案會儲存此檔案伺服器上或共用資料夾到硬碟。
    
- 僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 英吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。 You can use hard drives up to 10 TB. 對於匯入工作，將會處理只有第一個資料磁碟區在硬碟上。 The data volume must be formatted with NTFS. 當將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加 2.5 或 3.5 英吋 SATA II/III 連接器或外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 英吋 SATA II/III USB 介面卡，您可以附加。
    
    > [!IMPORTANT]
    > Office 365 匯入服務不支援外部硬碟隨附內建的 USB 介面卡。 Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
- 您的 PST 檔案所複製到的硬碟，必須使用 BitLocker 加密。 您在步驟 2 中執行的 WAImportExport.exe 工具，會幫助您設定 BitLocker。 它也會產生 BitLocker 加密金鑰，Microsoft 資料中心人員用來存取的磁碟機上傳的 PST 檔案至 Microsoft cloud 中的 [Azure 儲存體] 區域。
    
- 磁碟機運送是可透過 Microsoft Enterprise Agreement (EA)。 磁碟機運送無法透過 Microsoft 產品和服務合約 (MPSA)。
    
- 將 PST 檔案匯入 Office 365 信箱使用磁碟機運送的成本是 $2 USD 每 GB 的資料。 例如，如果您運送硬碟包含 1000 GB (1 TB) 的 PST 檔案時，成本是 $2000 USD。 You can work with a partner to pay the import fee. 如需尋找合作夥伴的詳細資訊，請參閱[尋找您的 Office 365 合作夥伴或轉銷商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
    
- 您或貴組織必須擁有 FedEx 或 DHL 的帳戶。 
    
  - 在美國、 巴西、 及歐洲的組織必須擁有 FedEx 帳戶。
    
  - 在東亞、 東南亞 （日本）、 大韓民國和澳洲的組織必須擁有 DHL 帳戶。
    
    Microsoft 會使用此帳戶來將硬碟送回給您 (以及計費)。 
    
- 運送給 Microsoft 的硬碟，可能必須跨越國境。在這種情況下，您必須負責確保硬碟機和它所包含的資料，會根據相關的法律匯入和/或匯出。運送硬碟之前，請向您的顧問確認磁碟機及資料可以合法的運送到指定的 Microsoft 資料中心。這是為了確保它及時送達 Microsoft。
    
- 此程序包含複製並儲存安全存放裝置金鑰和 BitLocker 加密金鑰。 請務必採取預防措施來保護這些金鑰，就如同您保護密碼或其他安全性相關的資訊一樣。 舉例來說，您可能會將這些資訊儲存於受密碼保護的 Microsoft Word 文件內，或是將它們儲存於已加密的 USB 磁碟機中。 請參閱這些機碼的範例[的詳細資訊](#more-information)一節。 
    
- PST 檔案匯入到 Office 365 信箱之後，為信箱設定保留功能已為期的持續時間。 這表示指派給信箱的保留原則不會處理，直到您關閉保留功能或設定要關閉保留的日期。 為什麼這麼做這樣？ 如果匯入至信箱的郵件都會舊，他們可能會永久刪除 （清除） 因為其保留期間已經過期根據為信箱設定保留設定。 將信箱置於保留功能，可讓信箱擁有者時間來管理這些新匯入郵件或讓您有時間變更信箱的保留設定。 請參閱管理保留功能的相關建議[的詳細資訊](#more-information)一節。 
    
- 根據預設，可由 Office 365 信箱接收的最大郵件大小為 35 MB。 這是因為信箱的*MaxReceiveSize*屬性的預設值設為 35 MB。 不過，此限制的 Office 365 中的最大郵件收到的大小為 150 MB。 因此，如果您匯入 PST 檔案中若包含大於 35 MB，我們會自動將目標信箱上的*MaxReceiveSize*屬性的值變更為 150 MB 的 Office 365 匯入服務的項目。 這可讓郵件最多 150 MB，以匯入至使用者信箱。 
    
    > [!TIP]
    > 若要找出郵件的接收大小針對信箱，您可以在 Exchange Online PowerShell 中執行此命令： `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 
  
- 您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。 您執行這項操作藉由指定中的非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。 請參閱[步驟 3： 建立 PST 匯入對應檔案](#step-3-create-the-pst-import-mapping-file)如需詳細資訊。 
    
- 在 Exchange 混合式部署中，您可以將 PST 檔案匯入主要信箱位於內部部署使用者的雲端式封存信箱。 您這麼做，執行在 PST 匯入對應檔案中的下列動作：
    
  - 指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。 
    
  - 指定的值 **，則為 TRUE**以`IsArchive`參數。 
    
    請參閱[步驟 3： 建立 PST 匯入對應檔案](#step-3-create-the-pst-import-mapping-file)如需詳細資訊。 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>步驟 1： 下載 PST 匯入工具與安全存放裝置金鑰

第一個步驟是下載安全存放裝置金鑰及工具，而且您將使用在 [步驟 2 來將 PST 檔案複製到硬碟。
  
> [!IMPORTANT]
> 您必須使用 Azure 匯入/匯出工具版本 1 (WAimportExportV1) 順利使用的磁碟機運送方法，以匯入 PST 檔案。 不支援的 Azure 匯入/匯出工具第 2 版，並使用它將會導致不正確地匯入工作準備硬碟。 請務必在此步驟中的程序，從安全性 & 合規性中心下載 Azure 匯入/匯出工具。 
  
1. 移至 [[https://compliance.microsoft.com/](https://compliance.microsoft.com/)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **匯入**。
    
    > [!NOTE]
    > 如先前所述，您必須被指派存取安全性 & 合規性中心中的 [**匯入**] 頁面上的適當權限。 
  
3. 在 [**匯入**] 頁面上，按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
4. 在匯入工作精靈] 為 PST 匯入工作中，輸入名稱，然後按一下 [**下一步**。 使用小寫字母、 數字、 連字號和底線。 您不能使用大寫字母，或在名稱中包含空格。
    
5. 在 [**選擇匯入工作類型**] 頁面上，按一下 [**運送硬碟給我們的實體位置的其中一個**，然後按一下 [**下一步**。
    
    ![按一下 [運送硬碟給其中一個建立的磁碟機運送匯入工作我們實體位置](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在 [**匯入資料**] 頁面上，執行下列兩件事： 
    
    ![複製安全存放裝置金鑰並下載匯入資料] 頁面上的 [Azure 匯入 / 匯出工具](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. 在步驟 2 中，按一下 [**複製安全存放裝置金鑰**。 顯示存放裝置金鑰之後，按一下 [**複製到剪貼簿**然後將它貼並將其儲存至檔案，以便您可以稍後再存取。
    
    b. 在 [步驟 3 中，**下載 Azure 匯入/匯出工具**來下載及安裝 Azure 匯入/匯出 （第 1 版） 工具。
    
    - 在快顯視窗中，按一下 [**儲存** \> WaImportExportV1.zip 檔案儲存至資料夾，在本機電腦上的 [**另存為**。 
    
    - 解壓縮 WaImportExportV1.zip 檔案。
    
7. 按一下 [**取消**] 以關閉精靈。 
    
    您會回到 [**匯入**] 頁面中的安全性 & 合規性中心當您在步驟 4 中建立匯入工作。 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>步驟 2： 將 PST 檔案複製到硬碟

下一個步驟是使用 WAImportExport.exe 工具，將 PST 檔案複製到硬碟。 這個工具會使用 BitLocker 加密硬碟、將 PST 複製到硬碟，並建立日誌檔案，儲存複製程序的相關資訊。 若要完成此步驟，PST 檔案必須位於貴組織的檔案共用內或檔案伺服器中。 在下列程序中，這就是所謂的 [來源目錄]。 
  
> [!IMPORTANT]
> 在硬碟首次執行 WAImportExport.exe 工具之後，每次您都必須使用不同的語法。 此語法會將 PST 檔案複製到硬碟此程序的步驟 4 中說明。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
    > [!TIP]
    > 如果您以系統管理員身分執行命令提示字元 (當您開啟時選取「以系統管理員身分執行」)，在命令提示字元視窗中，將顯示錯誤訊息。這可以協助您進行關於執行 WAImportExport.exe 工具問題的疑難排解。 
  
2. 移至您在步驟 1 中安裝 WAImportExport.exe 工具的目錄。
    
3. 首次執行下列命令，您會使用 WAImportExport.exe 來將 PST 檔案複製到硬碟。

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    下表說明了參數與其需要的值。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |指定日誌檔的名稱。 此檔案會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。 您送交給 Microsoft 的每個硬碟都必須有一個日誌檔案。 每次您執行 WAImportTool.exe，將 PST 檔案複製到硬碟時，資訊都將會附加到該磁碟機的日誌檔。  <br/> Microsoft 資料中心人員將使用中的資訊，日誌檔案與您在步驟 4 中建立匯入工作建立關聯的硬碟機，並將 PST 檔案上傳至 Microsoft 雲端中的 [Azure 儲存體] 區域。  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |指定當硬碟連接至本機電腦時的磁碟機代號。  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |指定複製工作階段的名稱。工作階段的定義是每次執行 WAImportExport.exe 工具，將檔案複製到硬碟的動作。PST 檔案會複製到資料夾，該資料夾是以此參數所指定的工作階段名稱來命名。   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |指定貴組織內的來源目錄，該目錄包含在工作階段期間要複製的 PST 檔案。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |將上傳 Pst 的 Microsoft cloud 中的 [Azure 儲存體] 區域中指定的目的地目錄。 您必須使用值`ingestiondata/`。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> 您也可以選擇性新增其他檔案路徑至此參數的值。 例如，您可以使用來源目錄 （轉換為 URL 格式） 的硬碟磁碟機，所在中所指定的檔案路徑`/srcdir:`參數。 例如，`\\FILESERVER01\PSTs`會變更為`FILESERVER01/PSTs`。 在此情況下，您仍然必須包含`ingestiondata`中的檔案路徑。 此範例中的值是`/dstdir:`參數可能`"ingestiondata/FILESERVER01/PSTs"`。  <br/> 新增其他檔案路徑的原因之一，是您具有相同檔名的 PST 檔案。  <br/> > [!NOTE]> 如果加上選擇性路徑名稱之後則上傳至 Azure 存放區域, 的 PST 檔案的命名空間會包含路徑名稱及的 PST 檔案名稱;例如， `FILESERVER01/PSTs/annb.pst`。 如果您未包含路徑名稱，命名空間是只 PST 檔名;例如`annb.pst`。           | `/dstdir:"ingestiondata/"` <br/> 或  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |指定您在步驟 1 中所取得的安全存放裝置帳戶金鑰。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此參數會開啟硬碟的 BitLocker。 首次執行 WAImportExport.exe 工具時需要此參數。  <br/> BitLocker 加密金鑰會複製到日誌檔案及記錄檔，如果您使用，會建立`/logfile:`參數。 如先前所解釋，檔案會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |此選擇性參數會指定要儲存記錄檔的資料夾。 如果未指定，記錄檔就會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    這是 WAImportExport.exe 工具針對各個參數使用實際值的語法範例︰
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    在您執行命令後，便會顯示 PST 檔案複製到硬碟進度的狀態訊息。最終狀態訊息會顯示已成功複製的檔案總數。 
    
4. 以後每次您執行 WAImportExport.ext 工具，將 PST 檔案複製到相同的硬碟時，都要執行此命令。

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    這是以後執行工作階段，將 PST 檔案複製到相同的硬碟時的語法範例。  

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>步驟 3： 建立 PST 匯入對應檔案

匯入服務的 Microsoft 資料中心人員可以上傳 Azure 儲存體區從硬碟的 PST 檔案之後，會使用的資訊在 PST 匯入對應檔案中，這是逗號分隔值 (CSV) 檔案，指定哪些使用者信箱 PST檔案會匯入至。 當您建立 PST 匯入工作時，您將會在下一個步驟提交 CSV 檔案。
  
1. [下載 PST 匯入對應檔案的複本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
2. 開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    CSV 檔案的第一列或「標題列」會列出參數，PST 匯入服務將使用這些參數來匯入 PST 檔案至使用者信箱。 每個參數名稱都是以逗號分隔。 在標題列下的每一列，代表了要匯入 PST 檔案至特定信箱的參數值。 每個要複製到硬碟的 PST 檔案，都會需要一個資料列。 請務必在對應檔案中，使用您的實際資料來取代預留位置資料。

    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 
  
3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定將匯入資料到 Office 365 服務。 若要將 PST 檔案匯入使用者信箱，請使用`Exchange`。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | PST 檔案將會複製到時運送硬碟給 Microsoft Azure 儲存體區域中指定的資料夾位置。  <br/>  您在 CSV 檔案中此欄中新增的功能取決於所指定的`/dstdir:`在先前步驟中的參數。 如果您沒有子資料夾上的來源位置，然後中的值`FilePath`參數必須包含相對路徑的文件庫;例如，/folder1/user1 /。  <br/>  如果您使用`/dstdir:"ingestiondata/"`，然後將此參數保留空白 CSV 檔案中。  <br/>  如果您將包含值的選擇性路徑名稱`/dstdir:`參數 (例如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`，然後將 （不包括 「 ingestiondata 」） 的路徑名稱用於 CSV 檔案中此參數。 此參數的值是區分大小寫。  <br/>  無論如何，*未*包含"ingestiondata 」 中的值為`FilePath`參數。 將此參數保留空白，或指定的選擇性路徑名稱。  <br/> > [!IMPORTANT]> 案例的檔案路徑名稱必須是相同的案例中所指定`/dstdir:`在先前步驟中的參數。 例如，如果您使用`"ingestiondata/FILESERVER01/PSTs"`子資料夾名稱在先前步驟中，然後使用，但`fileserver01/psts`中`FilePath`CSV 檔案中的參數，匯入 PST 檔案將會失敗。 請務必在兩個執行個體中使用相同的案例。           |(保留空白)  <br/> 或  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |指定將匯入至使用者信箱的 PST 檔案名稱。  此參數的值是區分大小寫。  <br/> > [!IMPORTANT]> CSV 檔案中的 PST 檔案名稱的情況必須是已上傳至步驟 2 中的 Azure 儲存體位置的 PST 檔案相同。 例如，如果您使用`annb.pst`中`Name`參數 CSV 檔案中，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入會失敗。 請務必 PST CSV 檔案中的名稱，會使用相同的情況下，為實際的 PST 檔案。           | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。  請注意，您無法指定公用資料夾，因為 PST 匯入服務不支援將 PST 檔案匯入公用資料夾。  <br/> 若要將 PST 檔案匯入非使用中的信箱，您必須指定此參數的信箱 GUID。 若要取得此 GUID，請執行下列 PowerShell 命令在 Exchange Online 中：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> 在某些情況下，您可能需要多個信箱相同電子郵件地址，其中一個信箱不在作用中信箱，而其他信箱位於虛刪除 （或非使用中） 的狀態。 在這些情況下，您必須指定信箱 GUID，以唯一識別信箱，若要將 PST 檔案匯入。 若要取得此 GUID 作用中信箱，請執行下列 PowerShell 命令： `Get-Mailbox <identity of active mailbox> | FL Guid`。 若要取得的 GUID，虛刪除 （或非使用中） 的信箱，請執行此命令： `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。 其中有兩個選項：  <br/> **為 FALSE**將 PST 檔案匯入至使用者的主要信箱。  <br/> **True 是表示**將 PST 檔案匯入至使用者的封存信箱。 This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). 如果您將這個參數設定為`TRUE`和未啟用使用者的封存信箱，該使用者的匯入就會失敗。 請注意，如果匯入失敗一位使用者 (因為他們的封存未啟用，而且此屬性設為`TRUE`)，將不會影響中匯入工作的其他使用者。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> **附註：** 若要將 PST 檔案匯入主要信箱位於內部部署使用者的雲端式封存信箱，只是指定`TRUE`此參數，並指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於的信箱 （位於相同層級的收件匣資料夾和其他預設信箱資料夾） 的根層級的新資料夾。  <br/>  如果您指定`/`，將 PST 檔案中的項目會被匯入直接在使用者的收件匣] 資料夾。  <br/>  如果您指定`/<foldername>`，將 PST 檔案中的項目將會匯入至名為資料夾*\<foldername\> * 。 例如，如果您使用`/ImportedPst`，項目會匯入至名為**ImportedPst**資料夾。 這個資料夾將會位於收件匣資料夾相同層級的使用者信箱。  <br/> |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數字值。 此參數用於從中文、 日文和韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常會使用雙位元組字元集 (DBCS) 的字元編碼。 如果這個參數不用來匯入 PST 檔案，用於信箱資料夾名稱 DBCS 的語言，將資料夾名稱是通常亂碼之後匯入它們。  <br/> 如需支援的值，使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)的清單。  <br/> > [!NOTE]> 如先前所述，這是選擇性的參數，您不需要加入 CSV 檔案中。 或者，您可以將它加入並將值保留空白，對一或多個資料列。           |(保留空白)  <br/> 或  <br/>  `932`（這是 ANSI/OEM 日文的程式碼] 頁面上識別碼）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>步驟 4：在 Office 365 中建立 PST 匯入工作

下一步是在 Office 365 中的匯入服務中建立 PST 匯入工作。 如先前所解釋，您將會提交在步驟 3 中所建立的 PST 匯入對應檔案。 在您建立新的工作之後，匯入服務將會匯入 PST 檔案至指定的使用者信箱的 PST 檔案會從硬碟複製到 Azure 的儲存區，並建立並啟動匯入工作之後就在對應檔案中使用的資訊。
  
1. 移至 [[https://compliance.microsoft.com](https://compliance.microsoft.com)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管**，然後按一下 [**匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
    > [!NOTE]
    > 如先前所述，您必須被指派存取安全性 & 合規性中心中的 [**匯入**] 頁面上的適當權限。 
  
4. 為 PST 匯入工作中，輸入名稱，然後按一下 [**下一步**。 使用小寫字母、 數字、 連字號和底線。 您不能使用大寫字母，或在名稱中包含空格。
    
5. 在 [**選擇匯入工作類型**] 頁面上，按一下 [**運送硬碟給我們的實體位置的其中一個**，然後按一下 [**下一步**。
    
    ![按一下 [運送硬碟給其中一個建立的磁碟機運送匯入工作我們實體位置](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在步驟 6 中，按一下 [**我已備妥我的硬碟**存取所需的磁碟機日誌檔案並且讓**我擁有存取權的對應檔案**] 核取方塊中，，然後按 [**下一步**。
    
    ![按一下 [步驟 6 中的兩個核取方塊](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. 在 [**選取的磁碟機檔案**] 頁面上，按一下 [**選取磁碟機檔案**]，然後前往 WAImportExport.exe 工具所在的相同資料夾。 在步驟 2 中所建立的日誌檔案已複製到此資料夾。
    
    ![按一下 [選取的磁碟機檔案送出時執行 WAImportExport.exe 工具所建立的日誌檔案](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. 選取日誌檔案;例如， `PSTHDD1.jrn`。
    
    > [!TIP]
    > 當您在步驟 2 中執行 WAImportExport.exe 工具時，日誌檔案名稱所指定的`/j:`參數。 
  
9. 磁碟機檔案的名稱會出現在**磁碟機的檔案名稱**之後，按一下 [**驗證**] 來檢查您的磁碟機檔中的錯誤。 
    
    ![按一下 [驗證] 來驗證您所選取的磁碟機檔案](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    磁碟機檔案已成功驗證，以建立 PST 匯入工作。 請注意它成功驗證之後，將會變更為綠色的檔案名稱。 如果驗證失敗，按一下 [**檢視記錄檔]** 連結。 驗證錯誤報表開啟時，並為錯誤郵件檔案的失敗原因的相關資訊。 
    
    > [!NOTE]
    > 您必須新增，然後驗證您運送至 Microsoft 每個硬碟的日誌檔案。 
  
10. 新增並驗證您將運送至 Microsoft 每個硬碟的日誌檔案後, 按一下 [**下一步**]。
    
11. 按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)提交您在步驟 3 中建立 PST 匯入對應檔案的 [**選取對應檔案**。 
    
    ![按一下 [選取對應檔以提交 CSV 檔案剛才匯入工作](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. CSV 名稱之後檔案會出現在 [**檔案名稱對應**] 下，按一下 [**驗證**] 來檢查您 CSV 檔中的錯誤。 
    
    ![按一下 [驗證] 來檢查錯誤的 CSV 檔案](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 檔案必須成功通過驗證，才能建立 PST 匯入工作。 請注意它成功驗證之後，將會變更為綠色的檔案名稱。 如果驗證失敗，按一下 [**檢視記錄檔]** 連結。 將開啟的驗證錯誤報告在失敗的檔案中的每一列的錯誤訊息。 
    
13. 成功驗證 PST 對應檔案之後，按一下 [**下一步**]。
    
14. 在**提供的連絡人資訊**] 頁面上，請在適用的方塊中輸入您的連絡資訊。 
    
    請注意，顯示您所運送硬碟給 Microsoft 位置的地址。 這個地址是自動產生取決於您 Office 365 資料中心位置。 請將此地址複製到檔案，或取得螢幕擷取畫面。
    
15. 閱讀條款和條件文件、 按一下核取方塊，，然後按一下 [**儲存**] 以送出匯入工作。 
    
    成功建立匯入工作時，狀態] 頁面上，會顯示說明磁碟機運送程序的下一個步驟。
    
16. 在 [**匯入**] 頁面上，按一下 [![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以顯示新的磁碟機運送匯入工作清單中的匯入工作。 請注意狀態設為**等候追蹤號碼**。 您也可以按一下 [匯入工作，以顯示 [狀態] 彈出式頁面，其中包含有關匯入工作的詳細的資訊。
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>步驟 5：運送硬碟給 Microsoft

下一步是運送硬碟給 Microsoft]，然後提供運送的追蹤號碼和傳回運送磁碟機運送工作的資訊。 Microsoft 所接收的磁碟機之後，它會之間所採取 7 和 10 個工作天內的資料中心人員，以將您的 PST 檔案上傳至您的組織的 Azure 儲存體區域。
  
> [!NOTE]
> 如果您沒有提供追蹤號碼，以及傳回運送資訊建立匯入工作的 14 天內，將會過期匯入工作。 如果發生這種情況，您必須建立新的磁碟機運送匯入工作 (請參閱[步驟 4： 在 Office 365 內建立 PST 匯入工作](#step-4-create-a-pst-import-job-in-office-365)) 並重新提交磁碟機和 PST 匯入對應檔案。 
  
### <a name="ship-the-hard-drive"></a>運送硬碟

當您運送硬碟給 Microsoft 時，請記住下列事項︰
  
- 請勿運送 SATA 轉 USB 介面卡;您只需要運送硬碟。
    
- 請妥善包裝硬碟；例如，使用防靜電包裝袋或氣泡紙包裝。
    
- 使用您所選擇的出貨承運業者運送硬碟給 Microsoft。
    
- 將硬碟運送到您在步驟 4 中，建立匯入工作時所顯示的 Microsoft 地點。 請務必在寄送地址中包含「Office 365 匯入服務」。
    
- 在您運送硬碟後，請務必寫下出貨承運業者的名稱及追蹤號碼。在下一個步驟中您將提供這些資訊。
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>輸入追蹤號碼，以及其他的送貨資訊

在您運送硬碟給 Microsoft 之後，請在 [匯入] 服務頁面完成下列程序。
  
1. 移至 [[https://compliance.microsoft.com](https://compliance.microsoft.com)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在左窗格中，按一下 [**資料控管**，然後按一下 [**匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [您要輸入追蹤號碼的磁碟機運送工作。 
    
4. 在 [狀態] 彈出式頁面中，按一下 [**輸入追蹤號碼**。
    
5. 請提供下列的送貨資訊︰
    
1. **出貨承運業者**輸入您用來運送硬碟給 Microsoft 傳遞電信業者的名稱。 
    
2. **追蹤號碼**鍵入硬碟運送的追蹤號碼。 
    
3. **傳回電訊廠商帳戶號碼**輸入您的組織帳戶號碼的列在下**傳回電訊廠商**電訊廠商。 Microsoft 會使用 （以及計費） 此帳戶對運送硬碟給您。 請注意在美國及歐洲的組織必須擁有 FedEx 帳戶。 在 Asia 和其餘的世界，組織必須擁有 DHL 帳戶。
    
6. 按一下 **[儲存]** 以儲存此資訊供匯入工作使用。 
    
    在 [**匯入**] 頁面上，按一下 [![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以更新的磁碟機運送匯入工作的資訊。 請注意，現在狀態設定為 **[磁碟機在運輸中]**。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步驟 6： 篩選資料，並啟動 PST 匯入工作

Microsoft 收到您的硬碟時後，在 [**匯入**] 頁面匯入工作的狀態會變更為**接收到的磁碟機**。 資料中心人員會使用日誌檔案中的資訊，以將您的 PST 檔案上傳至您的組織的 Azure 儲存體區域。 此時，狀態將變更為 **[匯入進行中]**。 如先前所述，它會之間所採取 7 到 10 個工作天之後收到您的硬碟上傳的 PST 檔案。
  
PST 檔案上傳至 Azure 之後，狀態會變更為**在進行中的分析**。 這表示 Office 365 會分析 （以安全無虞的方式） 的 PST 檔案中的資料來識別的項目並包含在 PST 檔案中的不同郵件類型的保留期限。 當完成分析，且可匯入資料時，匯入工作的狀態會變更為**分析已完成**。 此時，您可以選擇要匯入 PST 檔案中所包含的所有資料，或您可以修剪匯入藉由設定篩選器來控制哪些資料取得匯入的資料。
  
1. 移至 [[https://compliance.microsoft.com](https://compliance.microsoft.com)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在左窗格中，按一下 [**資料控管** > **匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [**準備好匯入至 Office 365**匯入工作，您在步驟 4 中建立。 
    
    ![按一下 [準備好剛才匯入工作旁匯入 Office 365](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    飛入] 頁面上的會顯示 PST 檔案的相關資訊與匯入工作的其他資訊。
    
4. 按一下 [**匯入至 Office 365**。
    
5. 會顯示 [**篩選您的資料**] 頁面。 它會包含所產生的 Office 365，包括的保留天數之資料的相關資訊的 PST 檔案上執行的分析資料見解。 此時，您必須篩選，則會匯入或所有的資料是匯入資料的選項。 
    
    ![您可以修剪 PST 檔案中的資料，或匯入 xxx xx](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. 執行下列其中一項動作：
    
    a. 若要修剪您匯入的資料，按一下 [**是，我想要匯入之前先加以篩選**。
    
    如需篩選的 PST 檔案中的資料，並再啟動匯入工作的詳細逐步指示，請參閱[篩選資料匯入至 Office 365 的 PST 檔案時](filter-data-when-importing-pst-files.md)。
    
    或
    
    b. 若要匯入 PST 檔案中的所有資料，請按一下 [**否，我想要匯都入每個項目，** 然後按一下 [**下一步**。
    
7. 如果您選擇要匯入的所有資料，請按一下 [都啟動匯都入工作的 [**匯都入資料**]。 
    
    匯入工作的狀態會顯示在 [**匯入**] 頁面。 按一下 [![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以更新顯示在 [**狀態**] 欄中的狀態資訊。 按一下 [匯入工作，以顯示 [狀態] 彈出式頁面，會顯示每個 PST 檔案匯入的狀態資訊。 當匯入完成，且已匯入 PST 檔案到使用者信箱時，狀態將變更為 **[已完成]**。

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>檢視上傳至 Office 365 的 PST 檔案清單

您可以安裝及使用 Microsoft Azure 存放裝置總管 （這是免費，開放原始碼工具） 來檢視清單中，我們正在上傳 PST 檔案 （由 Microsoft 資料中心人員） 至您的組織的 Azure 儲存體區域。 您可以執行此作業以驗證從您傳送給 Microsoft 硬碟的 PST 檔案已成功上傳至 Azure 存放區域。
  
Microsoft Azure 存放裝置總管處於預覽狀態。
  
 **重要：** 您無法使用 Azure 存放裝置總管上傳或修改 PST 檔案。 將 PST 檔案匯入至 Office 365 的唯一支援的方法是使用 AzCopy。 此外，您無法刪除您已上傳到 Azure blob 中的 PST 檔案。 如果您嘗試刪除 PST 檔案，您會收到沒有必要權限的相關錯誤。 請注意從 Azure 存放區域會自動刪除所有的 PST 檔案。 如果有任何的匯入工作正在進行中，然後中的所有 PST 檔案 * * ingestiondata * * 容器會刪除最新的匯入工作建立後的 30 天。 
  
若要安裝 Azure 存放裝置總管並連線至 Azure 存放區域：
  
1. 執行下列步驟，以取得貴組織的共用的存取簽章 (SAS) URL。 此 URL 是您的組織和 SAS 金鑰 Microsoft cloud 中的 Azure 儲存體位置的網路 URL 的組合。 此機碼為您提供存取貴組織的 Azure 儲存體位置的必要權限。
    
1. 移至 [[https://compliance.microsoft.com/](https://compliance.microsoft.com/)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
4. 在匯入工作精靈] 為 PST 匯入工作中，輸入名稱，然後按一下 [**下一步**。 使用小寫字母、 數字、 連字號和底線。 您不能使用大寫字母，或在名稱中包含空格。
    
5. 在 [**選擇匯入工作類型**] 頁面上，按一下 [**上傳您的資料**，然後按一下 [**下一步**。
    
6. 在步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。
    
7. 顯示 URL 之後，將它複製，並將其儲存至檔案。 請務必複製完整 URL。
    
    > [!IMPORTANT]
    > 請務必採取預防措施來保護 SAS URL。 這可以用任何人都能夠存取貴組織的 Azure 儲存體區域。 
  
8. 按一下 [**取消**] 關閉匯入工作精靈]。 
    
2. 下載並安裝[Microsoft Azure 存放裝置總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
3. 啟動 Microsoft Azure 存放裝置總管，以滑鼠右鍵按一下左窗格中的**儲存體帳戶**，然後按一下 [**連線到 Azure 儲存體**。
    
    ![儲存體帳戶上按一下滑鼠右鍵，然後按一下 [連線至 Azure 儲存體](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. 按一下 [**使用共用的存取簽章 (SAS) URI 或連線字串**，然後按一下 [**下一步**。
    
5. 按一下 [**使用 SAS URI**，在步驟 1 中，在下方**URI**] 方塊中貼上您取得 SAS URL，然後按一下 [**下一步**。
    
6. 在**連線摘要**] 頁面中，您可以檢閱連線資訊，，，然後按一下 [**連線**。
    
    開啟 [ **ingestiondata** ] 容器。它包含的 PST 檔案從您的硬碟。 [ **Ingestiondata** ] 容器，即可找到**儲存體帳戶** \> **（SAS-Attached 服務）** \> **Blob 容器**。
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. 當您完成使用 Microsoft Azure 存放裝置總管時，以滑鼠右鍵按一下**ingestiondata**，，然後按一下 [中斷與 Azure 存放區域**卸離**。 否則，您會在下一次嘗試附加時收到錯誤。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>疑難排解提示
<a name="troubleshootingtips"> </a>

- **匯入工作失敗，因為 PST 匯入 CSV 對應檔案中的錯誤時，會發生什麼事？** 如果匯入工作失敗，因為在對應檔案中的錯誤，您不必重新運送硬碟給 Microsoft，以建立新的匯入工作。 這是因為從硬碟您上傳的 PST 檔案的磁碟機運送匯入工作已上傳至您的組織的 Azure 儲存體區域。 在此情況下，您只需要在 PST 匯入 CSV 對應檔案中，修正錯誤再建立新的 「 網路上傳 「 匯入工作並提交修訂的 CSV 對應檔案。 若要建立並啟動新的網路上傳匯入工作，請參閱[步驟 5： 在 Office 365 內建立 PST 匯入工作](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步驟 6： 篩選資料，以及開始 PST 匯入工作](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主題中的 「 使用網路上傳將 PST 檔案匯入 Office 365。 」 
    
    > [!NOTE]
    > 為了協助您疑難排解在 PST 匯入 CSV 對應檔案，使用[Azure 存放裝置總管](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具來檢視的資料夾結構中已上傳至 Azure 存放區域的 PST 檔案從您的硬碟的**ingestiondata**容器。 對應檔案錯誤通常被因 FilePath 參數中不正確的值。 此參數會指定在 [Azure 儲存體區域 PST 檔案的位置。 請參閱 < 在<b0>步驟 3</b0>中的資料表中 FilePath 參數的描述。 如先前所述，在 [Azure 儲存體區域中的 PST 檔案的位置依指定`/dstdir:`參數，當您在[步驟 2](#step-2-copy-the-pst-files-to-the-hard-drive)中執行 WAImportExport.exe 工具時。 
  

  
## <a name="more-information"></a>詳細資訊

- 磁碟機運送是有效的方法若要利用可供貴組織的符合性功能的 Office 365 匯入大量的封存的郵件資料。 封存的資料會匯入至使用者信箱之後，您可以：
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)與[自動展開封存](enable-unlimited-archiving.md)的資料提供使用者額外信箱儲存空間。 
    
  - 將信箱置於[訴訟暫止](https://go.microsoft.com/fwlink/?linkid=856286)來保留資料。 
    
  - 使用 Microsoft [eDiscovery 工具](search-for-content.md)來搜尋資料。 
    
  - 適用於[Office 365 保留原則](retention-policies.md)來控制資料會保留多久，以及在保留期間到期之後要採取動作。 
    
  - 搜尋的[Office 365 稽核記錄](search-the-audit-log-in-security-and-compliance.md)，與此資料相關的事件。 
    
  - 資料匯入到[非使用中信箱](create-and-manage-inactive-mailboxes.md)，以封存資料，以便符合規範。 
    
  - 保護貴組織免於[資料遺失](data-loss-prevention-policies.md)的敏感資訊。 
    
- 以下是安全存放裝置帳戶金鑰和 BitLocker 加密金鑰的範例。此範例也會包含您要複製 PST 檔案到硬碟，所執行的 WAImportExport.exe 命令的語法。請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- 如先前所述，Office 365 匯入服務會開啟 PST 檔案匯入至信箱後，（如期的持續時間） 設定保留功能。 這表示*RentionHoldEnabled*屬性設為`True`使其不會處理指派給信箱的保留原則。 這可以讓信箱擁有者時間來管理新匯入郵件藉由防止刪除或封存原則刪除或封存較舊的郵件。 若要管理此保留功能，可採取一些步驟如下： 
    
  - 在一段時間之後, 您可以關閉保留功能來執行`Set-Mailbox -RetentionHoldEnabled $false`命令。 如需相關指示，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/p/?LinkId=544749)。
    
  - 您可以設定保留功能，讓未來某些日期上關閉。 您執行這項操作藉由執行`Set-Mailbox -EndDateForRetentionHold <date>`命令。 例如，假設今天的日期是 2016 年 6 月 1 日，而您想在 30 天中關閉保留功能，您可以執行下列命令： `Set-Mailbox -EndDateForRetentionHold 7/1/2016`。 在此案例中，您會使*RentionHoldEnabled*屬性設為*True*。 如需詳細資訊，請參閱[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以變更的保留原則，以便更舊版本都已匯入的項目不會立即刪除或移至使用者的封存信箱指派給信箱的設定。 例如，您無法延長刪除或封存原則指派給信箱的保留天數。 在此案例中，您會關閉保留在信箱上變更保留原則的設定之後。 如需詳細資訊，請參閱 < <b0>Set up Office 365 組織中信箱的封存和刪除原則</b0>。
    

  

