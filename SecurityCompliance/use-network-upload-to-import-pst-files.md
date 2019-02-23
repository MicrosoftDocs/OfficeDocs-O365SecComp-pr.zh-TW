---
title: 使用網路上傳至您的組織 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 系統管理員： 了解如何使用網路上傳至大量匯入至 Office 365 中的使用者信箱的多個 PST 檔案。
ms.openlocfilehash: a92217ad4126851a042b3492614aaa35ef215f61
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223602"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>使用網路上傳至您的組織 PST 檔案匯入 Office 365

> [!NOTE]
> 本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
以下是使用網路上傳至大量匯入至 Office 365 信箱的多個 PST 檔案所需的逐步指示。如需使用網路上傳大量匯入至 Office 365 信箱的 PST 檔案，請參閱[使用匯入 PST 檔案的網路上傳的常見問題集](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)的常見問題集問題。
  
[步驟 1： 複製 SAS URL 並安裝 Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[步驟 2： 將 PST 檔案上傳至 Office 365](#step-2-upload-your-pst-files-to-office-365)

[（選用）步驟 3： 檢視清單中的 PST 檔案上傳至 Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步驟 4： 建立 PST 匯入對應檔案](#step-4-create-the-pst-import-mapping-file)

[步驟 5：在 Office 365 中建立 PST 匯入工作](#step-5-create-a-pst-import-job-in-office-365)

[步驟 6： 篩選資料並開始 PST 匯入工作](#step-6-filter-data-and-start-the-pst-import-job)

請注意您必須執行一次只能步驟 1 至 PST 檔案匯入 Office 365 信箱。您執行這些步驟之後，請遵循步驟 2 到步驟 6 每一個您想要上傳並匯入 PST 檔案的批次的時間。

## <a name="before-you-begin"></a>開始之前
  
- 您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後再將自己的成員身分或者。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：
    
  - 您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。
    
    或
    
  - 您必須是 Office 365 組織中的全域管理員。
    
  > [!TIP]
    > 請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。 
  
- 將 PST 檔案匯入 Office 365 唯一支援的方法是使用 Azure AzCopy 工具，如本主題所述。您無法使用 Azure 儲存在檔案總管 PST 檔案上傳直接至 Azure 儲存區。
    
- 您要儲存您想要匯入 Office 365 上的檔案伺服器或組織中的共用的資料夾的 PST 檔案。在步驟 2 中，您將執行 Azure AzCopy 工具將上傳儲存此檔案伺服器上或共用資料夾至 Office 365 的 PST 檔案。
    
- 此程序包括複製並儲存一份包含便捷鍵的 URL。此資訊的使用中上傳您的 PST 檔案的步驟 2 和步驟 3 中若要檢視的上傳至 Office 365 的 PST 檔案清單。請務必採取預防措施像您會保護密碼或其他安全性相關的資訊保護此 URL。例如您可能會將其儲存至受密碼保護 Microsoft Word 文件或已加密的 USB 磁碟機。請參閱[的詳細資訊](#more-information)] 區段中的此範例會合併的 URL 及索引鍵。 
    
- 您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。您執行此動作以指定在非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。請參閱步驟 4 如本主題中的 [**說明**] 索引標籤。 
    
- 在 Exchange 混合部署中，您可以 PST 檔案匯入雲端式封存信箱的主要信箱位於內部部署的使用者。您這麼做依照 PST 匯入對應檔案中的下列：
    
  - 指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。 
    
  - 指定**TRUE**值`IsArchive`參數。 
    
    如需詳細資訊，請參閱[步驟 4](#step-4-create-the-pst-import-mapping-file) 。 
    
- PST 檔案匯入至 Office 365 信箱之後，為信箱設定保留功能會開啟無限期的持續期間。這表示將不會處理在您關閉保留功能或設定要關閉保留日期之前中指派給信箱的保留原則。為什麼這麼做這？如果舊匯入至信箱的郵件，則它們可能會永久刪除 （清除） 因為其保留期間已過期為基礎之信箱的保留設定。將信箱設定保留功能將會讓信箱擁有者時間來管理這些新匯入訊息或讓您變更信箱的保留設定的時間。請參閱本主題中針對有關管理保留功能的建議的**詳細資訊**] 索引標籤。 
    
- 根據預設，可以接收的 Office 365 信箱的最大郵件大小為 35 MB。那是因為信箱的*MaxReceiveSize*屬性的預設值設定為 35 MB。不過，限制的最大郵件的接收大小 Office 365 中為 150 MB。如此若您匯入 PST 檔案包含大於 35 MB，我們會自動將目標信箱上*MaxReceiveSize*屬性的值變更為 150 MB 的匯入 Office 365 服務的項目。這可讓郵件最多可 150 MB 要匯入至使用者信箱。 
    
    > [!TIP]
    > 若要找出郵件的接收大小的信箱，您可以執行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>步驟 1： 複製 SAS URL 並安裝 Azure AzCopy

第一個步驟是下載並安裝 Azure AzCopy 工具，這是您用來執行步驟 2 中 PST 檔案上傳至 Office 365 的工具。您也將您的組織複製 SAS URL。此 URL 會在 Microsoft 雲端組織和共用存取簽章 (SAS) 金鑰 Azure 儲存位置的網路 URL 的組合。此機碼提供 PST 檔案上傳至 Azure 儲存位置的必要權限。請務必採取預防措施保護 SAS URL。它是唯一的您的組織並將用於在步驟 2。

> [!IMPORTANT]
> 匯入 PST 檔案使用網路上傳方法，建議您依照下列程序中的步驟 6b 可以下載的 Azure AzCopy 的版本。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。
    
    > [!NOTE]
    > 您必須被指派存取安全性 [**匯入**] 頁面上的適當權限&amp;規範中心。請參閱 ＜**開始之前**] 區段中的詳細資訊。 
    
3. 在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
    匯入工作精靈] 會顯示。
    
4. 輸入 PST 匯入工作、 名稱，然後按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。
    
5. 在**您要上傳或隨附的資料吗？** 頁面、 按一下 [**上傳資料**然後再按一下 [**下一步**。
    
    ![按一下 [上傳您若要建立網路上傳的資料匯入工作](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在 [**匯入資料**] 頁面上執行下列兩件事： 
    
    ![複製 SAS URL 並下載 [匯入資料] 頁面上的 [Azure AzCopy 工具](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a.在步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。顯示 SAS URL 後，按一下 [**複製到剪貼簿**然後將其貼並將其儲存至檔案，讓您可以稍後存取。
    
    b.在步驟 3 中，按一下 [**下載 Azure AzCopy**下載並安裝 Azure AzCopy 工具。在快顯視窗中，按一下 [**執行**] 表示安裝 AzCopy。 
    
> [!NOTE]
> 您可以 [**匯入資料**] 頁面上保持在開啟狀態 （以防您需要再次複製 SAS URL） 或按一下 [**取消**] 以關閉它。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>步驟 2： 將 PST 檔案上傳至 Office 365

現在您已經準備好要用以 AzCopy.exe 工具 PST 檔案上傳至 Office 365。這項工具上傳並將其儲存在 Microsoft 雲端 Azure 的儲存位置。如先前所述 Azure 儲存位置的上傳至 PST 檔案位於同一個地區 Office 365 組織所在的 Microsoft 資料中心。若要完成此步驟，PST 檔案必須位於檔案共用或組織中的檔案伺服器。這就是所謂的下列程序中的來源目錄。每次執行 AzCopy 工具，您可以指定不同的來源目錄。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
2. 移至目錄您在步驟 1 安裝 AzCopy.exe 工具。如果您安裝此工具預設位置中，移至`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。
    
3. 執行下列命令以將 PST 檔案上傳至 Office 365。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    下表說明參數和其所需的值。請注意您在上一個步驟是取得此資訊可用值為這些參數。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |指定包含要上傳至 Office 365 的 PST 檔案在組織中的來源目錄。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |在步驟 1 中指定您取得 SAS URL。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> **提示：**（選用）您可以在 Azure 的儲存位置上傳至 PST 檔案中指定的子資料夾。您執行方法是新增 SAS URL 中的子資料夾位置 （之後"ingestiondata")。第一個範例不會指定子資料夾;這表示 Pst 將可上傳到根目錄 （名為*ingestiondata* ） 的 Azure 儲存位置。第二個範例 Azure 儲存位置的根目錄中的上傳至 （名為*PSTFiles* ） 的子資料夾的 PST 檔案。<br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> 或  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |將詳細狀態訊息輸出到記錄檔。根據預設，在 %LocalAppData%\Microsoft\Azure\AzCopy 中，詳細資訊記錄檔的名稱為 AzCopyVerbose.log。如果您在此選項中指定現有檔案位置，詳細資訊記錄檔會附加至該檔案。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |使 AzCopy 工具會將位於所指定的來源目錄中的子資料夾中的 Pst 檔案複製此選用參數會指定遞迴模式`/Source:`參數。  <br/> **附註：** 如果加上此參數，在子資料夾中的 PST 檔案不同的檔案路徑名稱中有 Azure 的儲存位置之後他們正在上傳。您必須在您在步驟 4 中建立 CSV 檔案中指定的實際檔案路徑名稱。<br/> | `/S` <br/> |
    | `/Y` <br/> |此必要的參數可讓唯寫 SAS 權杖使用當您將 PST 檔案上傳至 Azure 儲存位置。您在步驟 1 中取得 SAS URL (並指定在`/Dest:`參數) 是唯寫 SAS URL，這是您必須包含此參數的原因。請注意唯寫 SAS URL 將無法防止您使用 Azure 儲存在檔案總管檢視 PST 檔案上傳至 Azure 儲存位置的清單。<br/> | `/Y` <br/> |
   
這是 AzCopy.exe 工具針對各個參數使用實際值的語法範例︰
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

在您執行命令後，便會顯示 PST 檔案上傳進度的狀態訊息。最終狀態訊息會顯示已成功上傳的檔案總數。 

> [!TIP]
> 您已順利執行 AzCopy.exe 命令並確認所有參數正確都無誤後，命令列語法到您複製資訊相同 （安全） 檔案的複本儲存您取得在步驟 1 中。然後您可以命令複製並貼入此命令提示字元中每一個您想要執行 AzCopy.exe 工具至 PST 檔案上傳至 Office 365 的時間。您可能必須變更的唯一值是針對該組`/Source:`參數。這取決於 PST 檔案的所在位置的來源目錄。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（選用）步驟 3： 檢視清單中的 PST 檔案上傳至 Office 365

為選用的步驟，您可以安裝及使用 Microsoft Azure 儲存在檔案總管 （這是免費，開放原始碼工具） 來檢視您已上傳至 Azure blob PST 檔案的清單。為達成此目的兩種很好的原因有：
  
- 確認 PST 檔案從共用的資料夾或檔案伺服器在組織中的已成功上傳至 Azure blob。
    
- 確認每個 PST 檔案上傳至 Azure blob 的檔案名稱 （和子資料夾 pathname 如果包含一個）。當您建立對應檔案中的下一個步驟因為您有指定的資料夾路徑名稱和每個 PST 檔案的檔案名稱 PST，這是很有幫助。確認這些名稱可以協助降低您 PST 對應檔案中的潛在錯誤。
    
Microsoft Azure 儲存在檔案總管處於預覽。
  
> [!IMPORTANT]
> 您無法使用 Azure 儲存在檔案總管上傳或修改 PST 檔案。將 PST 檔案匯入 Office 365 唯一支援的方法是使用 AzCopy。此外，您無法刪除您已上傳至 Azure blob 的 PST 檔案。如果您嘗試刪除 PST 檔案，將會收到有關不會察覺必要的權限的錯誤。請注意 Azure 儲存區域會自動刪除所有 PST 檔案。如果有任何匯入工作進行，然後所有 PST 檔案中的 [ **ingestiondata** ] 容器中會不刪除 30 天後所建立的最新的匯入工作。
  
若要安裝 Azure 儲存在檔案總管並連線至 Azure 儲存區：
  
1. 下載並安裝[Microsoft Azure 儲存檔案總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 啟動 Microsoft Azure 儲存在檔案總管、 以滑鼠右鍵按一下左窗格中的**存放區的帳戶**和 [**連線至 Azure 存放區**。
    
    ![以滑鼠右鍵按一下 [儲存的帳戶，然後按一下 [連線至 Azure 存放區](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 按一下 [**使用存取共用簽章 (SAS) URI 或連線字串**再按 [**下一步**。
    
4. 按一下 [**使用 SAS URI**、 在步驟 1 中所取得 SAS URL 貼入底下**URI**] 方塊並再按 [**下一步**。
    
5. 在 [**連線摘要**] 頁面上您可以檢閱連線資訊，並再按一下 [**連線**。
    
    開啟**ingestiondata**容器;包含您在步驟 2 中上傳的 PST 檔案。[**存放區的帳戶**位於**ingestiondata**容器\> **(SAS-Attached Services)** \> **Blob 容器**。 
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. 使用 Microsoft Azure 儲存在檔案總管完成作業後，用滑鼠右鍵按一下**ingestiondata**，並再按一下 [**卸離**中斷與 Azure 儲存區的連線。否則，您會收到錯誤的下次您嘗試附加。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>步驟 4： 建立 PST 匯入對應檔案

Azure 儲存位置的 Office 365 組織已上載的 PST 檔案之後下, 一步是建立逗點分隔值 (CSV) 檔案，指定 PST 檔案會以匯入的使用者信箱。當您建立 PST 匯入工作，將送出這個的 CSV 檔案中的下一個步驟。
  
1. [下載 PST 匯入對應檔案的複本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
2. 開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    第一列或欄位名稱] 列的 CSV 檔案列出要使用 PST 匯入服務至 PST 檔案匯入使用者信箱的參數。每個參數名稱是以逗號分隔。標頭列] 下方的每一個資料列代表將 PST 檔案匯入特定信箱的參數值。您將需要一列的每一個您想要匯入使用者信箱的 PST 檔案。請務必對應檔案中的版面配置區資料取代實際資料。

   **附註：** 並不會變更標題列，包括 SharePoint 參數 ； 中的任何項目這些都會被忽略 PST 匯入程序期間。 

 3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。


    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要匯入資料至 Office 365 服務。若要匯入 PST 檔案至使用者信箱，請使用`Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |在 Azure 的儲存位置上傳至 PST 檔案步驟 2 中的指定的資料夾位置。  <br/> 如果您沒有加入選用的子資料夾名稱中 SAS URL 中`/Dest:`參數在步驟 2 中，將此參數保留空白 CSV 檔案中。如果您加入子資料夾名稱，會將它指定這個參數中 （請參閱第二個範例）。此參數的值是區分大小寫。<br/> 無論如何，*不*包含"ingestiondata"中的值`FilePath`參數。  <br/><br/> **重要：** 大小寫的檔案路徑名稱必須是所用如果 SAS URL 中包含的選用子資料夾名稱的大小寫相同`/Dest:`步驟 2 中的參數。例如，如果您是使用`PSTFiles`的子資料夾名稱步驟 2 中，然後使用`pstfiles`中`FilePath`CSV 檔中的參數，將會失敗 PST 檔案匯入。請務必在兩個執行個體中使用相同的大小寫。<br/> |(保留空白)  <br/> 或  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |指定要匯入至使用者信箱的 PST 檔案的名稱。此參數的值是區分大小寫。<br/> <br/>**重要：** CSV 檔案中的 PST 檔案名稱的大小寫必須已上傳至步驟 2 中的 Azure 儲存位置的 PST 檔案相同。例如，如果您使用`annb.pst`中`Name`參數中的 CSV 檔案，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入就會失敗。請務必 PST CSV 檔案中的名稱會使用為實際的 PST 檔案的大小寫相同。<br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |會指定 PST 檔案將會匯入至信箱的電子郵件地址。請注意您無法指定公用資料夾因為 PST 匯入服務不支援將 PST 檔案匯入的公用資料夾。<br/> 匯入 PST 檔案至不在作用中的信箱，您必須指定此參數的信箱 GUID。若要取得這個 GUID，請執行下列 PowerShell 命令 in Exchange Online：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**附註：** 在某些情況下，您可能會有多個信箱使用同一個電子郵件地址，其中一個信箱不在作用中信箱和其他信箱位於虛刪除 （或非使用中） 的狀態。在下列情況下，您必須指定信箱的信箱來唯一地識別要匯入至 PST 檔案的信箱 GUID。若要取得這個作用中信箱的 GUID，請執行下列 PowerShell 命令： `Get-Mailbox <identity of active mailbox> | FL Guid`。若要取得虛刪除 （或非使用中） 的信箱的 GUID，請執行此命令`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。<br/> | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：<br/><br/>**FALSE** -將 PST 檔案匯入使用者的主要信箱。  <br/> **True 是表示**-將 PST 檔案匯入使用者的封存信箱。本範例假設[已啟用使用者的封存信箱](enable-archive-mailboxes.md)。<br/><br/>如果您將這個參數設定為`TRUE`和未啟用使用者的封存信箱、 匯入的使用者將會失敗。請注意，如果匯入失敗的一位使用者 (因為其封存未啟用且此屬性設為`TRUE`)，將不會影響其他使用者匯入工作。<br/>  如果您將此參數保留空白，PST 檔案匯入使用者的主要信箱。  <br/> <br/>**附註：** 匯入 PST 檔案到雲端式封存信箱的主要信箱位於內部部署的使用者，剛指定`TRUE`為此參數指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於信箱 （相同層級 [收件匣] 資料夾和其他預設信箱資料夾） 的根層級的新資料夾。  <br/>  如果您指定`/`、 PST 檔案中的項目會被匯入直接在使用者的 [收件匣] 資料夾。  <br/><br/>  如果您指定`/<foldername>`、 PST 檔案中的項目將會匯入至名為資料夾*\<foldername\> * 。例如，如果您使用`/ImportedPst`、 項目會匯入至名為**ImportedPst**的資料夾。這個資料夾會位於 [收件匣] 資料夾相同層級的使用者的信箱。<br/><br/> **提示：** 請考慮執行一些測試批次到實驗這個參數讓您可以決定要匯入至 Pst 檔案的最佳資料夾位置。  <br/> |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數值。此參數用於從中文、 日文及韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常使用雙位元組字元集 (DBCS) 的字元編碼。如果此參數不用來匯入 PST 檔案的信箱資料夾名稱使用 DBCS 的語言，則他們正在匯入後通常被混亂資料夾名稱。<br/><br/> 如需使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)支援值的清單。  <br/> <br/>**附註：** 如先前另有說明，這是選用的參數與您沒有包含 CSV 檔案中。或者您可以將它包含並將此值保留空白的一或多個資料列。<br/> |(保留空白)  <br/> 或  <br/>  `932`（這是程式碼] 頁面上的識別碼 ANSI/OEM 日文）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>步驟 5：在 Office 365 中建立 PST 匯入工作

下一步是建立 Office 365 中的匯入服務中的 PST 匯入工作。如先前所述，您會將提交您在步驟 4 中建立之 PST 匯入對應檔案。建立新的工作之後，Office 365 分析 PST 檔案中的資料，然後您機會來篩選實際取得匯入至信箱 PST 匯入對應檔案中指定的資料 （請參閱[步驟 6](#step-6-filter-data-and-start-the-pst-import-job)）。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管**] 和 [**匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
    **附註：** 您必須被指派適當的權限來存取 [**匯入**] 頁面上的 [安全性]&amp;規範中心以建立新的匯入工作。請參閱 ＜**開始之前**] 區段中的詳細資訊。 
    
4. 輸入 PST 匯入工作、 名稱，然後按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。
    
5. 在**您要上傳或隨附的資料吗？** 頁面、 按一下 [**上傳資料**然後再按一下 [**下一步**。
    
    ![按一下 [上傳您若要建立網路上傳的資料匯入工作](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在步驟 4 中**匯入資料**] 頁面上，按一下 [ **I 完成上傳我檔案****我有對應檔案的存取權**的核取方塊，，然後按一下 [**下一步]**。
    
    ![按一下 [步驟 4 中兩個核取方塊](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. 在 [**選取對應檔案**] 頁面上按一下 [**選取對應檔案**送出您在步驟 4 中建立之 PST 匯入對應檔案。 
    
    ![按一下 [選取對應檔案送出 CSV 檔案所建立之匯入工作](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. CSV 名稱之後檔案會出現 [**對應檔案名稱**、 按一下 [**驗證**] 檢查 CSV 檔中的錯誤。 
    
    ![按一下 [驗證] 檢查錯誤的 CSV 檔案](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 檔案具有建立 PST 匯入工作成功驗證。請注意會成功驗證之後的檔案名稱變更為綠色。如果驗證失敗，請按一下 [**檢視記錄檔]** 連結。將開啟驗證錯誤報告失敗的檔案中的每一列的錯誤訊息。 
    
9. PST 對應檔案已成功驗證之後，閱讀條款和條件文件，並再按一下 [核取方塊。
    
10. 按一下 [**儲存**] 以送出工作及 [**關閉**之後已成功建立的工作。 
    
    顯示狀態彈出式] 頁面上，**進行中的分析**的狀態及新的匯入工作會顯示在 [**匯入**] 頁面上的清單中。 
    
11. 按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [**狀態**] 欄中的狀態資訊。分析完成且資料已準備好要匯入、 狀態會變更為**分析已完成**。
    
    您可以按一下 [匯入工作，以顯示狀態彈出式] 頁面，其中包含的每個對應檔案中所列的 PST 檔案匯入工作等狀態的詳細的資訊。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步驟 6： 篩選資料並開始 PST 匯入工作

您在步驟 5 中建立匯入工作之後，Office 365 以方式分析 PST 檔案中的資料 （安全且安全的方式） 所識別的項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成分析，且資料已準備好要匯入，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。
  
1. 在 [安全性] 的 [**匯入**] 頁面上&amp;規範中心，按一下 [**準備好要匯入 Office 365**在步驟 5 中所建立的匯入工作。 
    
    ![按一下 [匯入至 Office 365 所建立的匯入工作旁的準備](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    飛入] 頁面會顯示與 PST 檔案的相關資訊及匯入工作的其他資訊。
    
2. 在 [彈出式] 頁面上按一下 [**匯入至 Office 365**。
    
    會顯示 [**篩選資料**] 頁面。包含資料前瞻產生分析的 PST 檔案上執行的 Office 365，包括資料的保留天數的相關資訊。此時，您必須以篩選要匯入或匯入所有的資料時的資料選項。 
    
    ![您可以修剪 PST 檔案中的資料或將其所有匯入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 執行下列其中一項操作：
    
    a.以修剪您匯入的資料，按一下 [**是，我要匯入之前加以篩選**。
    
    如需篩選 PST 檔案中的資料，並再啟動匯入工作的詳細逐步指示，請參閱[篩選資料匯入至 Office 365 的 PST 檔案時](filter-data-when-importing-pst-files.md)。
    
    或
    
    b.匯入 PST 檔案中的所有資料，請按一下 [**否，我要匯都入每個項目，** 然後按一下 [**下一步**。
    
4. 如果您選擇要匯入的所有資料，請按一下 [啟動匯都入工作都**匯都入資料**]。 
    
    匯入工作的狀態會顯示在 [**匯入**] 頁面。按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [**狀態**] 欄中的狀態資訊的 [**重新整理**。按一下匯入工作顯示狀態彈出式] 頁面上，以顯示每個要匯入的 PST 檔案的狀態資訊。 

## <a name="how-the-import-process-works"></a>匯入程序的運作方式
  
您可以使用網路上傳選項及匯入 Office 365 服務以大量匯入至使用者信箱的 PST 檔案。網路上傳表示您上載 PST 檔案中 Microsoft cloud 暫時存放區。則 Office 365 匯入服務會複製 PST 檔案存放區從目標使用者信箱。
  
以下是圖與 PST 檔案匯入 Office 365 中的信箱的網路上傳程序的描述。
  
![工作流程的網路上傳至 PST 檔案匯入 Office 365 的程序](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **下載 PST 匯入工具和關鍵私人 Azure 儲存位置**-第一個步驟是下載 Azure AzCopy 命令列工具及便捷鍵用來將 PST 檔案上傳至 Microsoft 雲端 Azure 的儲存位置。您可以取得這些 Office 365 安全性 [**匯入**] 頁面中&amp;規範中心。索引鍵 （稱為安全存取簽章 (SAS) 金鑰、 可提供必要的權限至 PST 檔案上傳至私人及保護 Azure 儲存位置。此存取索引鍵是唯一的您的組織和協助防止 PST 檔案的未經授權的存取他們正在上傳至 Microsoft cloud 之後。請注意將 PST 檔案匯入 Office 365 不需要有不同的 Azure 訂閱貴組織。 
    
2. 使用 AzCopy.exe 工具 （在步驟 1 中下載） 上傳並儲存在位於相同的區域 Microsoft 資料中心 Azure 儲存位置的 PST 檔案**上傳至 Azure 儲存位置的 PST 檔案**-下一步是其中您的 Office 365組織所在。若要將其上傳，您想要匯入 Office 365 的 PST 檔案必須位於檔案共用或組織中的檔案伺服器。
    
    請注意您可以檢視他們正在上傳至 Azure 儲存位置之後的 PST 檔案的清單執行選用步驟。
    
3. **建立 PST 匯入對應檔案**-以 Azure 儲存位置已上載的 PST 檔案之後下, 一步是建立指定哪些使用者信箱的 PST 檔案將是以，請注意可以是 PST 檔案匯入的以逗號分隔的值 (CSV) 檔案 匯入使用者的主要信箱或封存信箱。匯入 Office 365 服務會使用 CSV 檔案中的資訊來匯入 PST 檔案。
    
4. **建立 PST 匯入工作**-下一個步驟是在 [安全性] 的 [**匯入**] 頁面上建立 PST 匯入工作&amp;規範中心並送出在上一個步驟中建立之 PST 匯入對應檔案。建立匯入工作之後，Office 365 分析 PST 檔案中的資料並再讓您在設定控制哪些資料實際取得匯入至信箱 PST 匯入對應檔案中指定的篩選器。 
    
5. **篩選所要匯入至信箱的 PST 資料**-建立並啟動匯入工作之後，Office 365 分析 PST 檔案中的資料 （安全地和安全地） 所識別的項目及 PST 檔案中包含的不同郵件類型的保留時間下限.完成分析，且資料已準備好要匯入，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。
    
6. **啟動 PST 匯入工作**-開始匯入工作之後，Office 365 資訊檔案中使用 PST 匯入對應從他 Azure 儲存位置的 Pst 檔案匯入至使用者信箱。在 [安全性] 的 [**匯入**] 頁面上會顯示狀態資訊 （包括要匯入每個 PST 檔案的相關資訊） 匯入工作&amp;規範中心。匯入工作完成時，設置**完成**之工作的狀態。
  
## <a name="more-information"></a>詳細資訊

- 為什麼要選擇 PST 檔案匯入 Office 365？
    
  - 是您的組織封存訊息資料匯入 Office 365 的好方法。
    
  - 資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。
    
  - 可讓您從您所匯入 PST 檔案套用到資料的 Office 365 的符合性功能協助組織的地址規範需求。這包括：
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)並提供使用者其他信箱的儲存空間來儲存您所匯入資料的 [[自動展開封存](enable-unlimited-archiving.md)。 
    
  - 進行信箱您所匯入資料的保留 [[訴訟暫止狀態](https://go.microsoft.com/fwlink/?linkid=856286)。 
    
  - 使用 Microsoft [eDiscovery 工具](search-for-content.md)來搜尋您匯入的資料。 
    
  - 使用[Office 365 的保留原則](retention-policies.md)以控制的保留期限您匯入的資料，以及要採取的保留期間到期後的動作。 
    
  - 搜尋[Office 365 稽核記錄](search-the-audit-log-in-security-and-compliance.md)的信箱相關的事件會影響您匯入的資料。 
    
  - 將資料匯入[非使用中信箱](create-and-manage-inactive-mailboxes.md)的規範目的封存資料。 
    
  - 若要防止機密資料流失貴組織的內部使用[的資料外洩防護原則](data-loss-prevention-policies.md)。 
  
- 以下是範例取得在步驟 1 中的共用存取簽章 (SAS) URL。這個範例也會包含命令執行 AzCopy.exe 工具 PST 檔案上傳至 Office 365 的語法。請務必採取預防措施就像您會保護密碼或其他安全性相關的資訊保護 SAS URL。

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  **True** so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the **Set-Mailbox -RetentionHoldEnabled $false** command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 8/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
