---
title: 使用的磁碟機傳送至您的組織 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '系統管理員： 了解如何將大量匯入您的組織至 Office 365 信箱的 PST 檔案複製到硬碟的 PST 檔案，然後將其傳送給 Microsoft。 '
ms.openlocfilehash: 44ca6e58d9273c73a807ba0b186c47721949c6f6
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223682"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>使用的磁碟機傳送至您的組織 PST 檔案匯入 Office 365

**本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用匯入 Office 365 服務及傳送至大量匯入至使用者信箱的 PST 檔案的磁碟機。傳送表示您將 PST 檔案複製到硬碟機，並將實體隨附給 Microsoft 的磁碟機的磁碟機。當 Microsoft 收到您的硬碟時，資料中心人員會將複製資料從硬碟到 Microsoft 雲端儲存區。然後您必須有機會修剪 PST 資料實際上所匯入至目標信箱設定控制哪些資料取得匯入的篩選。當您啟動匯入工作後，匯入服務匯入 PST 資料存放區從使用者信箱。使用的磁碟機傳送至 PST 檔案匯入使用者的信箱為貴組織的電子郵件移轉至 Office 365 的其中一個方法。
  
若要使用的磁碟機傳送至 PST 檔案匯入 Office 365 信箱所需的步驟如下：
  
[步驟 1： 下載安全儲存機碼和 PST 匯入工具](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[步驟 2： 將 PST 檔案複製到硬碟](#step-2-copy-the-pst-files-to-the-hard-drive)

[步驟 3： 建立 PST 匯入對應檔案](#step-3-create-the-pst-import-mapping-file)

[步驟 4：在 Office 365 中建立 PST 匯入工作](#step-4-create-a-pst-import-job-in-office-365)

[步驟 5：運送硬碟給 Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[步驟 6： 篩選資料並開始 PST 匯入工作](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> 您必須執行步驟 1 一次向下載入安全儲存金鑰及匯入工具。您執行這些步驟之後，請遵循步驟 2 到步驟 6 的每當您想要運送硬碟給 Microsoft。 
  
針對常詢問過關於使用傳送至 PST 檔案匯入 Office 365，請參閱[使用傳送至 PST 檔匯入的磁碟機的常見問題集](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)的磁碟機的問題。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後再將自己的成員身分或者。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：
    
  - 您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。
    
    或
    
  - 您必須是 Office 365 組織中的全域管理員。
    
    > [!TIP]
    > 請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。 
  
- 您要儲存您想要複製到硬碟上的檔案伺服器或組織中的共用的資料夾的 PST 檔案。步驟 2 中您用來執行 「 Azure 匯入 / 匯出工具 (WAImportExport.exe)，會將複製的 PST 檔案，這個檔案伺服器上儲存或共用資料夾至硬碟。
    
- 僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。您可以使用硬碟最多 10 TB。匯入的工作會處理在硬碟上的只有第一個資料量。資料磁碟區必須以 NTFS 格式化。時將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加或 2.5 或 3.5 英吋 SATA II/III 連接器或您可以附加外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 吋 SATA II/III USB 介面卡。
    
    > [!IMPORTANT]
    > 內建的 USB 介面卡隨附的外部硬碟不支援的 Office 365 匯入服務。此外，不能使用的磁碟內外部的硬碟磁碟機的大小寫。請不要隨附外部硬碟。 
  
- 硬碟複製至 PST 檔案必須使用 BitLocker 加密。您在步驟 2 中執行 WAImportExport.exe 工具可協助您設定 BitLocker。它也會產生 BitLocker 加密金鑰的 Microsoft 資料中心人員會用來存取的磁碟機上傳至 Microsoft 雲端中的 [Azure 存放區] 區域的 PST 檔案。
    
- 透過 Microsoft Enterprise Agreement (EA) 使用的磁碟機傳送。磁碟機傳送無法透過 Microsoft 產品和服務合約 (MPSA)。
    
- PST 檔案匯入 Office 365 信箱使用的磁碟機傳送的成本是 $2 USD 每 GB 的資料。例如，如果您隨附包含 1000 GB (1 TB) 的 PST 檔案的硬碟，成本是 $2000 USD。您可以使用合作夥伴支付匯入費用。如需尋找協力廠商的資訊，請參閱[尋找 Office 365 協力廠商或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
    
- 您或貴組織必須擁有 FedEx 或 DHL 的帳戶。 
    
  - 在美國、 巴西、 和歐洲的組織必須擁有 FedEx 帳戶。
    
  - 在東亞、 東南亞洲 （日本）、 共和國的韓國及澳洲的組織必須擁有 DHL 帳戶。
    
    Microsoft 會使用此帳戶來將硬碟送回給您 (以及計費)。 
    
- 運送給 Microsoft 的硬碟，可能必須跨越國境。在這種情況下，您必須負責確保硬碟機和它所包含的資料，會根據相關的法律匯入和/或匯出。運送硬碟之前，請向您的顧問確認磁碟機及資料可以合法的運送到指定的 Microsoft 資料中心。這是為了確保它及時送達 Microsoft。
    
- 此程序包括複製並儲存的安全認證儲存機碼和 BitLocker 加密金鑰。請務必採取預防措施像您會保護密碼或其他安全性相關的資訊保護這些機碼。例如，您可能會將其儲存至受密碼保護 Microsoft Word 文件或將其儲存至已加密的 USB 磁碟機。請參閱[的詳細資訊](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)] 區段中的這些機碼的範例。 
    
- PST 檔案匯入至 Office 365 信箱之後，為信箱設定保留功能會開啟無限期的持續期間。這表示將不會處理在您關閉保留功能或設定要關閉保留日期之前中指派給信箱的保留原則。為什麼這麼做這？如果舊匯入至信箱的郵件，則它們可能會永久刪除 （清除） 因為其保留期間已過期為基礎之信箱的保留設定。將信箱設定保留功能將會讓信箱擁有者時間來管理這些新匯入訊息或讓您變更信箱的保留設定的時間。請參閱如需管理保留功能的建議[的詳細資訊](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)] 區段。 
    
- 根據預設，可以接收的 Office 365 信箱的最大郵件大小為 35 MB。那是因為信箱的*MaxReceiveSize*屬性的預設值設定為 35 MB。不過，限制的最大郵件的接收大小 Office 365 中為 150 MB。如此若您匯入 PST 檔案包含大於 35 MB，我們會自動將目標信箱上*MaxReceiveSize*屬性的值變更為 150 MB 的匯入 Office 365 服務的項目。這可讓郵件最多可 150 MB 要匯入至使用者信箱。 
    
    > [!TIP]
    > 若要找出郵件的接收大小的信箱，您可以執行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 
  
- 您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。您執行此動作以指定在非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。請參閱[步驟 3： 建立 PST 匯入對應檔案](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)如需詳細資訊。 
    
- 在 Exchange 混合部署中，您可以 PST 檔案匯入雲端式封存信箱的主要信箱位於內部部署的使用者。您這麼做依照 PST 匯入對應檔案中的下列：
    
  - 指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。 
    
  - 指定**TRUE**值`IsArchive`參數。 
    
    請參閱[步驟 3： 建立 PST 匯入對應檔案](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)如需詳細資訊。 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>步驟 1： 下載安全儲存機碼和 PST 匯入工具

第一個步驟是下載的安全認證儲存金鑰及工具，而且您要用以步驟 2 中複製到硬碟的 PST 檔案。
  
> [!IMPORTANT]
> 您必須使用 Azure 匯入/匯出工具版本 1 (WAimportExportV1) 若要使用的磁碟機傳送方法成功匯入 PST 檔案。第 2 版的 Azure 匯入/匯出工具不支援和使用它會導致不正確地準備匯入工作硬碟。請務必下載 Azure 匯入/匯出工具的安全性&amp;規範中心遵循此步驟中的程序。 
  
1. 移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。
    
    > [!NOTE]
    > 之前所述，您必須被指派存取安全性 [**匯入**] 頁面上的適當權限&amp;規範中心。 
  
3. 在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
4. 在 [匯入工作精靈] 中，輸入 PST 匯入工作名稱，並再按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。
    
5. 在 [**選擇匯入工作類型**] 頁面上按一下 [**傳送至我們實體位置的硬碟機**並再按 [**下一步**。
    
    ![按一下 [傳送至我們建立傳送匯入工作的磁碟機的實體位置的硬碟機](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在 [**匯入資料**] 頁面上執行下列兩件事： 
    
    ![複製的安全認證儲存金鑰並下載 Azure 匯入 / 匯出工具在匯入資料] 頁面](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a.在步驟 2 中，按一下 [**複製的安全認證儲存索引鍵**。顯示儲存金鑰後，按一下 [**複製到剪貼簿**然後將其貼並將其儲存至檔案，讓您可以稍後存取。
    
    b.在步驟 3、 下載及安裝 Azure 匯入/匯出 （版本 1） 工具**下載 Azure 匯入/匯出工具**。
    
    - 在快顯視窗中，按一下 [**儲存** \> WaImportExportV1.zip 檔案儲存到資料夾本機電腦上的 [**另存為**。 
    
    - 解壓縮 WaImportExportV1.zip 檔案。
    
7. 按一下 [**取消**] 以關閉精靈。 
    
    您將會回到 [**匯入**] 頁面上的 [安全性]&amp;規範中心當您在步驟 4 中建立匯入工作。 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>步驟 2： 將 PST 檔案複製到硬碟

下一個步驟是使用 WAImportExport.exe 工具來將 PST 檔案複製到硬碟。這項工具硬碟與 BitLocker 會加密、 將 Pst 複製到硬碟，並建立日誌檔案儲存複本的程序的相關資訊。若要完成此步驟，PST 檔案必須位於檔案共用或組織中的檔案伺服器。這就是所謂的下列程序中的來源目錄。 
  
> [!IMPORTANT]
> 硬碟的第一次執行 WAImportExport.exe 工具之後，您必須使用不同的語法每個之後的時間。此語法會說明此程序可將 PST 檔案複製到硬碟的步驟 4 中。 
  
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
    | `/j:` <br/> |指定日誌檔的名稱。此檔案會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。您送交給 Microsoft 的每個硬碟都必須有一個日誌檔案。每次您執行 WAImportTool.exe，將 PST 檔案複製到硬碟時，資訊都將會附加到該磁碟機的日誌檔。 
  <br/> Microsoft 資料中心人員將使用中的資訊的日誌檔案與您在步驟 4 中建立匯入工作相關聯的硬碟並將 PST 檔案上傳至 Microsoft 雲端中的 [Azure 存放區] 區域。  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |指定當硬碟連接至本機電腦時的磁碟機代號。  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |指定複製工作階段的名稱。工作階段的定義是每次執行 WAImportExport.exe 工具，將檔案複製到硬碟的動作。PST 檔案會複製到資料夾，該資料夾是以此參數所指定的工作階段名稱來命名。   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |指定包含要複製工作階段期間的 PST 檔案在組織中的來源目錄。請務必環繞雙引號使用此參數的值 ("")。  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |在 Azure 的存放區] 區域中 Pst 要上傳 Microsoft cloud 指定目的地目錄。您必須使用值`ingestiondata/`。請務必環繞雙引號使用此參數的值 ("")。<br/> （選用） 您也可以新增其他檔案路徑為此參數的值。例如，您可以使用在硬碟上 （轉換成的 URL 格式），來源目錄中指定的檔案路徑`/srcdir:`參數。例如，`\\FILESERVER01\PSTs`變更為`FILESERVER01/PSTs`。在此例中，您仍必須包含`ingestiondata`中的檔案路徑。在此範例中的值是`/dstdir:`參數就是`"ingestiondata/FILESERVER01/PSTs"`。<br/> 若要新增其他檔案路徑的其中一個原因是如果您必須具有相同的檔名的 Pst 檔案。  <br/> > [!NOTE]如果您包括選用 pathname >、 PST 檔案上傳至 Azure 儲存區域後的命名空間將會包含路徑名稱及 PST 檔案名稱 ；例如， `FILESERVER01/PSTs/annb.pst`。如果您未包含路徑名稱、 命名空間是僅限 PST 檔案名稱 ；例如`annb.pst`。           | `/dstdir:"ingestiondata/"` <br/> 或  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |在步驟 1 中指定您取得儲存帳戶機碼。請務必環繞雙引號使用此參數的值 ("")。  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此參數會開啟硬碟的 BitLocker。首次執行 WAImportExport.exe 工具時需要此參數。  <br/> BitLocker 加密金鑰複製到日誌檔案和記錄檔會建立如果您使用`/logfile:`參數。如先前所述的日誌檔案會儲存到 WAImportExport.exe 工具所在的相同資料夾中。<br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |此選用參數會指定儲存記錄檔的資料夾。如果未指定，記錄檔會儲存至相同 WAImportExport.exe 工具所在的資料夾。請務必環繞雙引號使用此參數的值 ("")。  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
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

匯入服務 Microsoft 資料中心人員上傳至 Azure 的存放區從硬碟 PST 檔案之後，將會是以逗號分隔值 (CSV) 檔案，指定哪些使用者信箱 PST PST 匯入對應檔案中使用的資訊檔案會以匯入。當您建立 PST 匯入工作，會送出這個的 CSV 檔案中的下一個步驟。
  
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

    第一列或欄位名稱] 列的 CSV 檔案列出要使用 PST 匯入服務至 PST 檔案匯入使用者信箱的參數。每個參數名稱是以逗號分隔。標頭列] 下方的每一個資料列代表將 PST 檔案匯入特定信箱的參數值。您將需要一列的每個 PST 檔案複製到硬碟。請務必對應檔案中的版面配置區資料取代實際資料。

    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 
  
3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要匯入資料至 Office 365 服務。若要匯入 PST 檔案至使用者信箱，請使用`Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> | PST 檔案會複製到運送硬碟時向 Microsoft Azure 儲存區域中指定的資料夾位置。  <br/>  您新增此資料行中的 CSV 檔案取決於內容中所指定的`/dstdir:`先前步驟中的參數。  <br/>  如果您是使用`/dstdir:"ingestiondata/"`，然後將此參數保留空白 CSV 檔案中。  <br/>  如果您包含的值選用 pathname`/dstdir:`參數 (例如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`，然後使用 CSV 檔案中的此參數 （不包括"ingestiondata"） 的路徑名稱。此參數的值是區分大小寫。<br/>  無論如何，*不*包含"ingestiondata"中的值`FilePath`參數。將此參數保留空白，或指定的選用路徑名稱。<br/> > [!IMPORTANT]> 大小寫的檔案路徑名稱必須是相同的案例中所指定`/dstdir:`先前步驟中的參數。例如，如果您是使用`"ingestiondata/FILESERVER01/PSTs"`子資料夾名稱在先前步驟中，但接著會使用`fileserver01/psts`中`FilePath`CSV 檔中的參數，將會失敗 PST 檔案匯入。請務必在兩個執行個體中使用相同的大小寫。           |(保留空白)  <br/> 或  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |指定要匯入至使用者信箱的 PST 檔案的名稱。此參數的值是區分大小寫。<br/> > [!IMPORTANT]> CSV 檔案中的 PST 檔案名稱的大小寫必須是已上傳至步驟 2 中的 Azure 儲存位置的 PST 檔案相同。例如，如果您使用`annb.pst`中`Name`參數中的 CSV 檔案，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入就會失敗。請務必 PST CSV 檔案中的名稱會使用為實際的 PST 檔案的大小寫相同。           | `annb.pst` <br/> |
    | `Mailbox` <br/> |會指定 PST 檔案將會匯入至信箱的電子郵件地址。請注意您無法指定公用資料夾因為 PST 匯入服務不支援將 PST 檔案匯入的公用資料夾。<br/> 匯入 PST 檔案至不在作用中的信箱，您必須指定此參數的信箱 GUID。若要取得這個 GUID，請執行下列 PowerShell 命令 in Exchange Online：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> 在某些情況下，您可能會有多個信箱使用同一個電子郵件地址，其中一個信箱不在作用中信箱和其他信箱位於虛刪除 （或非使用中） 的狀態。在下列情況下，您必須指定信箱的信箱來唯一地識別要匯入至 PST 檔案的信箱 GUID。若要取得這個作用中信箱的 GUID，請執行下列 PowerShell 命令： `Get-Mailbox <identity of active mailbox> | FL Guid`。若要取得虛刪除 （或非使用中） 的信箱的 GUID，請執行下列命令： `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：<br/> **FALSE**將 PST 檔案匯入使用者的主要信箱。  <br/> **True 是表示**將 PST 檔案匯入使用者的封存信箱。本範例假設[已啟用使用者的封存信箱](enable-archive-mailboxes.md)。如果您將這個參數設定為`TRUE`和未啟用使用者的封存信箱、 匯入的使用者將會失敗。請注意，如果匯入失敗的一位使用者 (因為其封存未啟用且此屬性設為`TRUE`)，將不會影響其他使用者匯入工作。<br/>  如果您將此參數保留空白，PST 檔案匯入使用者的主要信箱。  <br/> **附註：** 匯入 PST 檔案到雲端式封存信箱的主要信箱位於內部部署的使用者，剛指定`TRUE`為此參數指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於信箱 （相同層級 [收件匣] 資料夾和其他預設信箱資料夾） 的根層級的新資料夾。  <br/>  如果您指定`/`、 PST 檔案中的項目會被匯入直接在使用者的 [收件匣] 資料夾。  <br/>  如果您指定`/<foldername>`、 PST 檔案中的項目將會匯入至名為資料夾*\<foldername\> * 。例如，如果您使用`/ImportedPst`、 項目會匯入至名為**ImportedPst**的資料夾。這個資料夾會位於 [收件匣] 資料夾相同層級的使用者的信箱。<br/> |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數值。此參數用於從中文、 日文及韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常使用雙位元組字元集 (DBCS) 的字元編碼。如果此參數不用來匯入 PST 檔案的信箱資料夾名稱使用 DBCS 的語言，則他們正在匯入後通常被混亂資料夾名稱。<br/> 如需使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)支援值的清單。  <br/> > [!NOTE]> 如先前所述，這是選用的參數與您沒有包含 CSV 檔案中。或者您可以將它包含並將此值保留空白的一或多個資料列。           |(保留空白)  <br/> 或  <br/>  `932`（這是程式碼] 頁面上的識別碼 ANSI/OEM 日文）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>步驟 4：在 Office 365 中建立 PST 匯入工作

下一步是建立 Office 365 中的匯入服務中的 PST 匯入工作。如先前所述，您會將提交您在步驟 3 中建立之 PST 匯入對應檔案。建立新的工作之後，匯入服務將使用中的資訊之對應檔案匯入 PST 檔案至指定的使用者信箱後 PST 檔案從硬碟複製到 Azure 儲存區與您建立並啟動匯入工作。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管**] 和 [**匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
    > [!NOTE]
    > 之前所述，您必須被指派存取安全性 [**匯入**] 頁面上的適當權限&amp;規範中心。 
  
4. 輸入 PST 匯入工作、 名稱，然後按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。
    
5. 在 [**選擇匯入工作類型**] 頁面上按一下 [**傳送至我們實體位置的硬碟機**並再按 [**下一步**。
    
    ![按一下 [傳送至我們建立傳送匯入工作的磁碟機的實體位置的硬碟機](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在步驟 6 中，按一下 [**我準備好 「 我的硬碟與存取所需的磁碟機日誌檔案**而且**我有對應檔案的存取權**] 核取方塊中，並再按 [**下一步**。
    
    ![按一下 [步驟 6 中兩個核取方塊](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. 在**選取的磁碟機檔案**] 頁面上按一下 [**選取磁碟機檔案**，並前往 WAImportExport.exe 工具所在的相同資料夾。步驟 2 中建立的日誌檔案複製到此資料夾。
    
    ![按一下 [選取磁碟機的檔案送出時執行 WAImportExport.exe 工具所建立的日誌檔案](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. 選取的日誌檔案 ；例如， `PSTHDD1.jrn`。
    
    > [!TIP]
    > 您在步驟 2 中執行 WAImportExport.exe 工具時所指定的日誌檔案名稱`/j:`參數。 
  
9. 磁碟機檔案的名稱會出現 [**磁碟機的檔案名稱**後，按一下 [**驗證**] 檢查您的磁碟機的檔案有錯誤。 
    
    ![按一下 [驗證來驗證您所選取的磁碟機檔案](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    磁碟機檔案具有建立 PST 匯入工作成功驗證。請注意會成功驗證之後的檔案名稱變更為綠色。如果驗證失敗，請按一下 [**檢視記錄檔]** 連結。會開啟錯誤訊息的資訊為何無法將檔案驗證錯誤報告。 
    
    > [!NOTE]
    > 您必須新增及驗證每個硬碟您向 Microsoft 隨附的日誌檔案。 
  
10. 之後新增及驗證每個硬碟將隨附給 Microsoft 的日誌檔案，按一下 [**下一步**]。
    
11. 按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**選取對應的檔案**送出您在步驟 3 中建立之 PST 匯入對應檔案。 
    
    ![按一下 [選取對應檔案送出 CSV 檔案所建立之匯入工作](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. CSV 名稱之後檔案會出現 [**對應檔案名稱**、 按一下 [**驗證**] 檢查 CSV 檔中的錯誤。 
    
    ![按一下 [驗證] 檢查錯誤的 CSV 檔案](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 檔案具有建立 PST 匯入工作成功驗證。請注意會成功驗證之後的檔案名稱變更為綠色。如果驗證失敗，請按一下 [**檢視記錄檔]** 連結。將開啟驗證錯誤報告失敗的檔案中的每一列的錯誤訊息。 
    
13. PST 對應檔案已成功驗證之後，按一下 [**下一步**]。
    
14. 在**提供連絡人資訊**] 頁面上，請在適用的方塊中輸入連絡人資訊。 
    
    請注意會顯示您出貨至您硬碟的 Microsoft 位置的地址。這個位址會自動產生取決於您的 Office 365 資料中心位置。將此位址複製到檔案或取得螢幕擷取畫面。
    
15. 閱讀條款和條件文件、 [核取方塊，和 [**儲存**] 以送出匯入工作。 
    
    匯入工作成功建立，狀態] 頁面上會顯示說明傳送程序的磁碟機的下一個步驟。
    
16. 在 [**匯入**] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以顯示新的磁碟機傳送匯入工作清單中的匯入工作。請注意狀態會設為**等候追蹤數目**。您也可以按一下 [匯入工作，以顯示狀態彈出式] 頁面，其中包含有關匯入工作的詳細的資訊。
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>步驟 5：運送硬碟給 Microsoft

下一步是隨附向 Microsoft、 硬碟及再提供物料追蹤數及傳回物料資訊之磁碟機傳送工作。由 Microsoft 接收磁碟機之後，它需要資料的 7 到 10 商務天之間中心人員將 PST 檔案上傳至您的組織的 Azure 儲存區。
  
> [!NOTE]
> 如果您沒有提供追蹤號碼並傳回物料資訊建立匯入工作的 14 天內，將過期匯入工作。如果發生這種情況，您必須建立新的磁碟機傳送匯入工作 (請參閱[步驟 4： 在 Office 365 中建立 PST 匯入工作](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) 並重新提交的磁碟機和 PST 匯入對應檔案。 
  
### <a name="ship-the-hard-drive"></a>運送硬碟

當您運送硬碟給 Microsoft 時，請記住下列事項︰
  
- 未隨附的 SATA-USB 配接器;您只能有隨附的硬碟。
    
- 請妥善包裝硬碟；例如，使用防靜電包裝袋或氣泡紙包裝。
    
- 使用您所選擇的出貨承運業者運送硬碟給 Microsoft。
    
- 傳送至您在步驟 4 中建立匯入工作時所顯示的 Microsoft 位置的地址硬碟。請務必在傳送至地址中包含"Office 365 匯入服務 」。
    
- 在您運送硬碟後，請務必寫下出貨承運業者的名稱及追蹤號碼。在下一個步驟中您將提供這些資訊。
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>輸入追蹤號碼，以及其他的送貨資訊

在您運送硬碟給 Microsoft 之後，請在 [匯入] 服務頁面完成下列程序。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在左窗格中，按一下 [**資料控管**和 [**匯入**。
    
3. 在 [**匯入**] 頁面上按一下 [您要輸入的追蹤號碼的磁碟機物料的工作。 
    
4. 在 [狀態彈出式] 頁面上按一下 [**輸入追蹤數字**。
    
5. 請提供下列的送貨資訊︰
    
1. **傳遞電信業者**輸入您用以隨附硬碟向 Microsoft 傳送電信業者的名稱。 
    
2. **追蹤數目**輸入硬碟物料的追蹤號碼。 
    
3. **傳回電信業者帳戶號碼**輸入您的組織帳戶號碼列於下**傳回電信業者**電信業者。Microsoft 會使用 （以及計費） 這個帳戶在您的硬碟隨附給您。請注意在美國和歐洲、 的組織必須具有 FedEx 的帳戶。亞洲與其餘的世界的組織必須具有 DHL 的帳戶。
    
6. 按一下 **[儲存]** 以儲存此資訊供匯入工作使用。 
    
    在 [**匯入**] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以更新的磁碟機傳送匯入工作的資訊。請注意狀態現在已設為**傳送過程中磁碟機**。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步驟 6： 篩選資料並開始 PST 匯入工作

由 Microsoft 接收硬碟機之後，請在 [**匯入**] 頁面的匯入工作的狀態會變更為**磁碟機已接收之**。資料中心人員會使用日誌檔案中的資訊來將 PST 檔案上傳至您的組織的 Azure 儲存區。此時狀態會變更為 [**匯入為正在進行中**。先前所述，它將會接收到您的硬碟上傳 PST 檔案後 7 到 10 商務天之間。
  
PST 檔案上傳至 Azure 之後，狀態會變更為**進行中的分析**。這表示 Office 365 分析 （在安全及安全的方式） PST 檔案中的資料以識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。分析已完成且資料已準備好要匯入、 匯入工作的狀態會變更為**分析已完成**。此時，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在左窗格中，按一下 [**資料控管** > **匯入**。
    
3. 在 [**匯入**] 頁面上按一下 [**準備好要匯入 Office 365**您在步驟 4 中建立之匯入工作。 
    
    ![按一下 [匯入至 Office 365 所建立的匯入工作旁的準備](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    飛入] 頁面會顯示與 PST 檔案的相關資訊及匯入工作的其他資訊。
    
4. 按一下 [**匯入至 Office 365**。
    
5. 會顯示 [**篩選資料**] 頁面。包含資料前瞻產生分析的 PST 檔案上執行的 Office 365，包括資料的保留天數的相關資訊。此時，您必須以篩選要匯入或匯入所有的資料時的資料選項。 
    
    ![您可以修剪 PST 檔案中的資料或將其所有匯入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. 執行下列其中一項操作：
    
    a.以修剪您匯入的資料，按一下 [**是，我要匯入之前加以篩選**。
    
    如需篩選 PST 檔案中的資料，並再啟動匯入工作的詳細逐步指示，請參閱[篩選資料匯入至 Office 365 的 PST 檔案時](filter-data-when-importing-pst-files.md)。
    
    或
    
    b.匯入 PST 檔案中的所有資料，請按一下 [**否，我要匯都入每個項目，** 然後按一下 [**下一步**。
    
7. 如果您選擇要匯入的所有資料，請按一下 [啟動匯都入工作都**匯都入資料**]。 
    
    匯入工作的狀態會顯示在 [**匯入**] 頁面。按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [**狀態**] 欄中的狀態資訊的 [**重新整理**。按一下匯入工作顯示狀態彈出式] 頁面上，以顯示每個要匯入的 PST 檔案的狀態資訊。如果匯入即完成 PST 檔案匯入至使用者信箱，會變更狀態為 [**已完成**。

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>檢視清單中的 PST 檔案上傳至 Office 365

您可以安裝及使用 Microsoft Azure 儲存在檔案總管 （這是免費，開放原始碼工具） 來檢視我們要上載 （由 Microsoft 資料中心人員） 您組織的 Azure 儲存區 PST 檔案的清單。您可以執行此作業以驗證從您傳送給 Microsoft 的硬碟磁碟機的 PST 檔案已成功上傳至 Azure 儲存區。
  
Microsoft Azure 儲存在檔案總管處於預覽。
  
 **重要：** 您無法使用 Azure 儲存在檔案總管上傳或修改 PST 檔案。將 PST 檔案匯入 Office 365 唯一支援的方法是使用 AzCopy。此外，您無法刪除您已上傳至 Azure blob 的 PST 檔案。如果您嘗試刪除 PST 檔案，將會收到有關不會察覺必要的權限的錯誤。請注意 Azure 儲存區域會自動刪除所有 PST 檔案。如果沒有匯入中的工作進度，則中的所有 PST 檔案 * * ingestiondata * * 容器會刪除 30 天後所建立的最新的匯入工作。 
  
若要安裝 Azure 儲存在檔案總管並連線至 Azure 儲存區：
  
1. 請執行下列步驟來取得您的組織共用存取簽章 (SAS) URL。此 URL 會在 Microsoft 雲端組織及 SAS 金鑰 Azure 儲存位置的網路 URL 的組合。此機碼提供存取您的組織 Azure 儲存位置的必要權限。
    
1. 移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
4. 在 [匯入工作精靈] 中，輸入 PST 匯入工作名稱，並再按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。
    
5. 在 [**選擇匯入工作類型**] 頁面上按一下 [**上傳資料**並再按 [**下一步**。
    
6. 在步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。
    
7. 顯示 URL 後，將其複製並將其儲存至檔案。請務必複製整個 URL。
    
    > [!IMPORTANT]
    > 請務必採取預防措施保護 SAS URL。這可以存取您的組織的 Azure 儲存區所使用的任何人。 
  
8. 按一下 [**取消**] 關閉匯入工作精靈]。 
    
2. 下載並安裝[Microsoft Azure 儲存檔案總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
3. 啟動 Microsoft Azure 儲存在檔案總管、 以滑鼠右鍵按一下左窗格中的**存放區的帳戶**和 [**連線至 Azure 存放區**。
    
    ![以滑鼠右鍵按一下 [儲存的帳戶，然後按一下 [連線至 Azure 存放區](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. 按一下 [**使用存取共用簽章 (SAS) URI 或連線字串**再按 [**下一步**。
    
5. 按一下 [**使用 SAS URI**、 在步驟 1 中以底下**URI**] 方塊中貼上您取得 SAS URL 並再按 [**下一步**。
    
6. 在 [**連線摘要**] 頁面上您可以檢閱連線資訊，並再按一下 [**連線**。
    
    開啟**ingestiondata**容器;包含從您的硬碟的 PST 檔案。[**存放區的帳戶**位於**ingestiondata**容器\> **(SAS-Attached Services)** \> **Blob 容器**。
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. 使用 Microsoft Azure 儲存在檔案總管完成作業後，用滑鼠右鍵按一下**ingestiondata**，並再按一下 [**卸離**中斷與 Azure 儲存區的連線。否則，您會收到錯誤的下次您嘗試附加。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>疑難排解提示
<a name="troubleshootingtips"> </a>

- **匯入工作失敗 PST 匯入 CSV 對應檔案中的錯誤因會發生什麼事？** 如果因為對應檔案中的錯誤而失敗匯入工作，您不需要重新隨附硬碟向 Microsoft 才可建立新的匯入工作。那是因為 PST 檔案從您提交硬碟的磁碟機傳送匯入工作已上傳至您的組織的 Azure 儲存區。在此例中您剛才已修正錯誤 PST 匯入 CSV 對應檔，然後建立新的 「 網路上傳"匯入工作並送出修訂的 CSV 對應檔案。若要建立並啟動新的網路上傳匯入工作，請參閱[步驟 5： Office 365 中建立 PST 匯入工作](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步驟 6： 篩選資料並開始 PST 匯入工作](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主題中的 「 使用網路上傳至 PST 檔案匯入 Office 365。 」 
    
    > [!NOTE]
    > 若要協助您疑難排解 PST 匯入 CSV 對應檔案、 使用[Azure 儲存檔案總管](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具來檢視已上傳至 Azure 儲存區的 PST 檔案從您的硬碟**ingestiondata**容器中的資料夾結構。對應檔案錯誤通常是 FilePath 參數值，不正確所造成。此參數會指定在 Azure 的存放區] 區域中 PST 檔案的位置。請參閱[步驟 3](#step-3-create-the-pst-import-mapping-file)中的表格中 FilePath 參數的描述。如先前所述，在 Azure 的存放區] 區域中的 PST 檔案的位置所指定`/dstdir:`您在[步驟 2](#step-2-copy-the-pst-files-to-the-hard-drive)中執行 WAImportExport.exe 工具時的參數。 
  

  
## <a name="more-information"></a>詳細資訊

- 磁碟機傳送是有效的方式大量的封存訊息資料匯入 Office 365 善用可用來在組織的符合性功能。封存的資料匯入至使用者信箱後，您可以：
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)與[自動展開封存](enable-unlimited-archiving.md)的資料提供使用者其他信箱的儲存空間。 
    
  - 將信箱資料的保留[訴訟暫止狀態](https://go.microsoft.com/fwlink/?linkid=856286)。 
    
  - 使用 Microsoft [eDiscovery 工具](search-for-content.md)來搜尋資料。 
    
  - 適用於[Office 365 的保留原則](retention-policies.md)控制之資料的保留期限及要採取的保留期間到期後的動作。 
    
  - [Office 365 稽核記錄](search-the-audit-log-in-security-and-compliance.md)的搜尋與此資料相關的事件。 
    
  - 將資料匯入[非使用中信箱](create-and-manage-inactive-mailboxes.md)的規範目的封存資料。 
    
  - 保護[資料遺失](data-loss-prevention-policies.md)您組織中的機密資訊。 
    
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
   
- 如先前所述的 Office 365 匯入服務會開啟設定 （無限期的持續時間） 之後 PST 檔案匯入至信箱的保留。這表示*RentionHoldEnabled*屬性設為`True`以便將不會處理指派給信箱的保留原則。這可讓管理新匯入訊息來防止刪除或封存原則中刪除或封存舊郵件的信箱擁有者時間。以下是一些以管理此保留所能採取的步驟： 
    
  - 後段特定時間內，您就可以關閉保留功能來執行`Set-Mailbox -RetentionHoldEnabled $false`命令。指示，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/p/?LinkId=544749)。
    
  - 您可以設定保留功能，讓一些日期未來關閉。您執行這項作業執行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假設今天的日期是 2016 年 7 月 1，而且您想關閉在 30 天保留功能，您會執行下列命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此案例中，您會保留*RentionHoldEnabled*屬性設為*True* 。如需詳細資訊，請參閱[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以變更使較舊的項目匯入的將不會立即刪除或移至使用者的封存信箱指派給信箱的保留原則的設定。例如，您無法延長刪除或封存原則指派給信箱的保留時間。在此案例中，您會關閉信箱保留之後變更此保留原則的設定。如需詳細資訊，請參閱 ＜ [Set up Office 365 組織中信箱的封存及刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。
    

  

