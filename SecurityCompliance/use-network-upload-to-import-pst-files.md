---
title: 使用網路上傳至您組織 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 系統管理員： 了解如何使用網路上傳將大量匯入多個 PST 檔案複製到 Office 365 中的使用者信箱。
ms.openlocfilehash: 73123d5f36a01b31cfc38e6404bd400bb722fb36
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958574"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>使用網路上傳至您組織 PST 檔案匯入 Office 365

> [!NOTE]
> 本文適用於系統管理員。 您是否正嘗試匯入 PST 檔案到自己的信箱？ 請參閱[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
以下是使用網路上傳至大量匯入多個 PST 檔案複製到 Office 365 信箱所需的逐步指示。 如需使用網路上傳大量匯入 PST 檔案複製到 Office 365 信箱，請參閱[使用網路上傳將 PST 檔案匯入的常見問題集](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)的常見問題集問題。
  
[步驟 1： 複製 SAS URL，並安裝 Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[步驟 2： 將您的 PST 檔案上傳至 Office 365](#step-2-upload-your-pst-files-to-office-365)

[（選用）步驟 3： 檢視清單中的 PST 檔案上傳至 Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步驟 4： 建立 PST 匯入對應檔案](#step-4-create-the-pst-import-mapping-file)

[步驟 5： 在 Office 365 中建立 PST 匯入工作](#step-5-create-a-pst-import-job-in-office-365)

[步驟 6： 篩選資料，並啟動 PST 匯入工作](#step-6-filter-data-and-start-the-pst-import-job)

附註您必須先執行步驟 1 只有一次將 PST 檔案匯入 Office 365 信箱。 您執行這些步驟之後，請遵循步驟 2 到步驟 6 每的次您要上傳及匯入 PST 檔案的批次。

## <a name="before-you-begin"></a>開始之前
  
- 您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 將 PST 檔案匯入 Office 365 信箱。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：
    
  - 您必須獲指派 「 郵件收件者角色在 Exchange Online。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Or
    
  - 您必須是 Office 365 組織中的全域系統管理員。
    
  > [!TIP]
    > 請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。 若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。 
  
- 將 PST 檔案匯入至 Office 365 的唯一支援的方法是使用 Azure AzCopy 工具，如本主題所述。 您無法使用 Azure 存放裝置總管上傳 PST 檔案直接至 Azure 存放區域。
    
- 您必須以儲存您想要在檔案伺服器或組織中的共用的資料夾上匯入 Office 365 的 PST 檔案。 在步驟 2 中，您會執行 Azure AzCopy 工具，將上傳的 PST 檔案會儲存此檔案伺服器上或共用資料夾至 Office 365。
    
- 此程序牽涉到複製並儲存一份含有便捷鍵的 URL。 此資訊將用於在步驟 2 中上傳您的 PST 檔案，並在 [步驟 3 如果您想要檢視上傳至 Office 365 的 PST 檔案清單。 請務必採取預防措施來保護此 URL，像是會保護密碼或其他安全性相關的資訊。 例如您可能會將它儲存至受密碼保護 Microsoft Word 文件或加密的 USB 磁碟機。 請參閱 <<c0>的詳細資訊] 區段中，此範例結合 URL 和金鑰。 
    
- 您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。 您執行這項操作藉由指定中的非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。 在本主題的資訊中的**指示**] 索引標籤上，請參閱 「 步驟 4 」。 
    
- 在 Exchange 混合式部署中，您可以將 PST 檔案匯入主要信箱位於內部部署使用者的雲端式封存信箱。 您這麼做，執行在 PST 匯入對應檔案中的下列動作：
    
  - 指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。 
    
  - 指定的值 **，則為 TRUE**以`IsArchive`參數。 
    
    如需詳細資訊，請參閱 「[步驟 4](#step-4-create-the-pst-import-mapping-file) 」。 
    
- PST 檔案匯入到 Office 365 信箱之後，為信箱設定保留功能已為期的持續時間。 這表示指派給信箱的保留原則不會處理，直到您關閉保留功能或設定要關閉保留的日期。 為什麼這麼做這樣？ 如果匯入至信箱的郵件都會舊，他們可能會永久刪除 （清除） 因為其保留期間已經過期根據為信箱設定保留設定。 將信箱置於保留功能，可讓信箱擁有者時間來管理這些新匯入郵件或讓您有時間變更信箱的保留設定。 請參閱本主題中針對管理保留功能的相關建議的**詳細資訊**] 索引標籤。 
    
- 根據預設，可由 Office 365 信箱接收的最大郵件大小為 35 MB。 這是因為信箱的*MaxReceiveSize*屬性的預設值設為 35 MB。 不過，此限制的 Office 365 中的最大郵件收到的大小為 150 MB。 因此，如果您匯入 PST 檔案中若包含大於 35 MB，我們會自動將目標信箱上的*MaxReceiveSize*屬性的值變更為 150 MB 的 Office 365 匯入服務的項目。 這可讓郵件最多 150 MB，以匯入至使用者信箱。 
    
    > [!TIP]
    > 若要找出郵件的接收大小針對信箱，您可以在 Exchange Online PowerShell 中執行此命令： `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>步驟 1： 複製 SAS URL，並安裝 Azure AzCopy

第一個步驟是下載及安裝 Azure AzCopy 工具，也就是您用來上傳 PST 檔案複製到 Office 365 來執行步驟 2 中的工具。 您也將複製 SAS URL 為您的組織。 此 URL 是您的組織和共用的存取簽章 (SAS) 索引鍵的 Microsoft cloud 中的 Azure 儲存體位置的網路 URL 的組合。 此機碼為您提供要上傳 PST 檔案至您的 Azure 儲存體位置的必要權限。 請務必採取預防措施來保護 SAS URL。 它是唯一的您的組織，並將在步驟 2 中使用。

> [!IMPORTANT]
> 若要匯入 PST 檔案使用網路上傳方法，我們建議您使用的版本，可以在下列程序之步驟 6b 中下載 Azure AzCopy。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **匯入**。
    
    > [!NOTE]
    > 您必須被指派存取安全性 & 合規性中心中的 [**匯入**] 頁面上的適當權限。 請參閱 <<c0>開始之前> 一節的詳細資訊。 
    
3. 在 [**匯入**] 頁面上，按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
    匯入工作精靈隨即顯示。
    
4. 為 PST 匯入工作中，輸入名稱，然後按一下 [**下一步**。 使用小寫字母、 數字、 連字號和底線。 您不能使用大寫字母，或在名稱中包含空格。
    
5. 在**您要上傳或運送資料？** ] 頁面上，按一下 [**上傳您的資料**，然後按一下 [**下一步**。
    
    ![按一下 [上傳您的資料，以建立網路上傳來匯入工作](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在 [**匯入資料**] 頁面上，執行下列兩件事： 
    
    ![複製 SAS URL，並下載 Azure AzCopy 工具匯入資料] 頁面上](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. 在步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。 SAS URL 會顯示之後，按一下 [**複製到剪貼簿**然後將它貼並將其儲存至檔案，以便您可以稍後再存取。
    
    b. 在步驟 3 中，按一下 [**下載 Azure AzCopy**下載並安裝 Azure AzCopy 工具]。 在快顯視窗中，按一下 [安裝 AzCopy 的 [**執行**]。 
    
> [!NOTE]
> 您可以將保留 [**匯入資料**] 頁面上開啟 （以防您需要再次複製的 SAS URL） 或按一下 [**取消**] 以關閉它。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>步驟 2： 將您的 PST 檔案上傳至 Office 365

現在您可以使用 AzCopy.exe 工具來上傳 PST 檔案至 Office 365。 此工具會將上傳，並將其儲存在 Microsoft cloud 中的 Azure 儲存體位置。 如先前所述，您上傳您的 PST 檔案至 Azure 儲存體位置位於同一個區域 Office 365 組織所在的 Microsoft 資料中心。 若要完成此步驟，PST 檔案必須位於貴組織的檔案共用內或檔案伺服器中。 在下列程序中，這就是所謂的 [來源目錄]。 每次您執行 [AzCopy 工具] 中，您可以指定不同的來源目錄。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
2. 移至您在步驟 1 中安裝 AzCopy.exe 工具的目錄。 如果您在預設位置安裝工具，請移至`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。
    
3. 執行下列命令，以將 PST 檔案上傳至 Office 365。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > 您必須指定目錄，作為在上述命令中; 的來源位置您不能指定個別的 PST 檔案。 將上傳的來源目錄中的所有 PST 檔案。
 
    下表說明 AzCopy.exe 參數和其所需的值。 您在上一個步驟中所取得的資訊用於這些參數的值。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |在您的組織，其中包含將上傳至 Office 365 的 PST 檔案中指定的來源目錄。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |步驟 1 中指定您所取得的 SAS URL。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> **提示：**（選用）您可以在 Azure 儲存體位置以上傳 PST 檔案複製到指定子資料夾。 要這麼做，藉由在 SAS URL 中新增 （之後"ingestiondata 」) 的子資料夾位置。 第一個範例不會指定文件庫;這表示 Pst 就會上傳到 （名為*ingestiondata* ） 的根目錄的 Azure 儲存體位置。 Azure 儲存體位置的根目錄中的第二個範例上傳 PST 檔案複製到 （名為*PSTFiles* ） 的子資料夾。  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Or  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |將詳細狀態訊息輸出到記錄檔。根據預設，在 %LocalAppData%\Microsoft\Azure\AzCopy 中，詳細資訊記錄檔的名稱為 AzCopyVerbose.log。如果您在此選項中指定現有檔案位置，詳細資訊記錄檔會附加至該檔案。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |此選用參數指定的遞迴模式，如此 AzCopy 工具會將位於所指定的來源目錄中的子資料夾中的 Pst 檔案複製`/Source:`參數。  <br/> **附註：** 如果您加入此參數，在子資料夾中的 PST 檔案中會有不同的檔案路徑名稱 Azure 儲存體位置之後他們正在上傳。 您必須在您在步驟 4 中建立的 CSV 檔案中指定的實際檔案路徑名稱。  <br/> | `/S` <br/> |
    | `/Y` <br/> |當您將 PST 檔案上傳至 Azure 儲存體位置時，此必要的參數可讓唯寫的 SAS 語彙基元的使用。 您在步驟 1 中取得的 SAS URL (與中指定`/Dest:`參數) 是唯寫的 SAS URL，這就是為什麼您必須包含此參數。 請注意，唯寫的 SAS URL 將不會使您無法使用 Azure 存放裝置總管檢視 Azure 儲存體位置上傳的 PST 檔案清單。  <br/> | `/Y` <br/> |
   
這是 AzCopy.exe 工具針對各個參數使用實際值的語法範例︰
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

在您執行命令後，便會顯示 PST 檔案上傳進度的狀態訊息。最終狀態訊息會顯示已成功上傳的檔案總數。 

> [!TIP]
> 您已成功執行 AzCopy.exe 命令，並確認所有參數正確都無誤後，儲存一份命令列語法以相同的 （安全） 檔案，複製資訊的位置取得在步驟 1 中。 然後您可以複製並貼上此命令在命令提示字元中每個您想要執行 AzCopy.exe 工具，以將 PST 檔案上傳至 Office 365 的時間。 您可能要變更的唯一值是針對該組`/Source:`參數。 這視 PST 檔案所在的來源目錄而定。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（選用）步驟 3： 檢視清單中的 PST 檔案上傳至 Office 365

為選用的步驟中，您可以安裝及使用 Microsoft Azure 存放裝置總管 （這是免費，開放原始碼工具） 來檢視您已上傳到 Azure blob 中的 PST 檔案清單。 以下為執行這項作業的兩個好處：
  
- 確認從共用的資料夾或檔案伺服器在組織中的 PST 檔案已成功上傳至 Azure blob。
    
- 每個 PST 檔案上傳至 Azure blob 中的確認檔案名稱 （和子資料夾路徑名稱，如果您包含一個）。 當您要在下一個步驟中建立 PST 對應檔案時，這項功能會很有幫助，因為您必須指定每個 PST 檔案的資料夾路徑名稱及檔名。 驗證這些名稱有助於減少 PST 對應檔中的潛在錯誤。
    
Microsoft Azure 存放裝置總管處於預覽狀態。
  
> [!IMPORTANT]
> 您無法使用 Azure 存放裝置總管上傳或修改 PST 檔案。 將 PST 檔案匯入至 Office 365 的唯一支援的方法是使用 AzCopy。 此外，您無法刪除您已上傳到 Azure blob 中的 PST 檔案。 如果您嘗試刪除 PST 檔案，您會收到沒有必要權限的相關錯誤。 請注意從 Azure 存放區域會自動刪除所有的 PST 檔案。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.
  
若要安裝 Azure 存放裝置總管並連線至 Azure 存放區域：
  
1. 下載並安裝[Microsoft Azure 存放裝置總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 啟動 Microsoft Azure 存放裝置總管，以滑鼠右鍵按一下左窗格中的**儲存體帳戶**，然後按一下 [**連線到 Azure 儲存體**。
    
    ![儲存體帳戶上按一下滑鼠右鍵，然後按一下 [連線至 Azure 儲存體](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 按一下 [**使用共用的存取簽章 (SAS) URI 或連線字串**，然後按一下 [**下一步**。
    
4. 按一下 [**使用 SAS URI**，在步驟 1 中取得的 SAS URL 貼入**URI**] 下的方塊，然後按一下 [**下一步**。
    
5. 在**連線摘要**] 頁面中，您可以檢閱連線資訊，，，然後按一下 [**連線**。
    
    開啟 [ **ingestiondata** ] 容器。它包含您在步驟 2 中上傳的 PST 檔案。 [ **Ingestiondata** ] 容器，即可找到**儲存體帳戶** \> **（SAS-Attached 服務）** \> **Blob 容器**。 
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. 當您完成使用 Microsoft Azure 存放裝置總管時，以滑鼠右鍵按一下**ingestiondata**，，然後按一下 [中斷與 Azure 存放區域**卸離**。 否則，您會在下一次嘗試附加時收到錯誤。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>步驟 4： 建立 PST 匯入對應檔案

已上載的 PST 檔案至 Office 365 組織的 Azure 儲存體位置之後下, 一步是建立逗點分隔值 (CSV) 檔案，指定的 PST 檔案將會匯入至使用者信箱。 當您建立 PST 匯入工作時，您將送出這個的 CSV 檔案中的下一個步驟。
  
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
    CSV 檔案的第一列或「標題列」會列出參數，PST 匯入服務將使用這些參數來匯入 PST 檔案至使用者信箱。 每個參數名稱都是以逗號分隔。 在標題列下的每一列，代表了要匯入 PST 檔案至特定信箱的參數值。 您將需要為每個要匯入至使用者信箱的 PST 檔案設定一列。 請務必在對應檔案中，使用您的實際資料來取代預留位置資料。

   **附註：** 不會變更標題列，以及 SharePoint 參數; 中的任何項目PST 匯入程序期間，會忽略它們。 

 3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。


    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定將匯入資料到 Office 365 服務。 若要將 PST 檔案匯入使用者信箱，請使用`Exchange`。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |在您上傳 PST 檔案複製到步驟 2 中的 Azure 儲存體位置中指定的資料夾位置。  <br/> 如果您並未納入選擇性的子資料夾名稱中的 SAS URL`/Dest:`參數在步驟 2 中，將此參數保留空白 CSV 檔案中。 如果您包含的子資料夾名稱，這個參數中指定它 （請參閱第二個範例）。 此參數的值是區分大小寫。  <br/> 無論如何，*未*包含"ingestiondata 」 中的值為`FilePath`參數。  <br/><br/> **重要：** 檔案路徑名稱大小寫必須與您使用如果中的 SAS URL 中包含的選用子資料夾名稱的大小寫相同`/Dest:`在步驟 2 中的參數。 例如，如果您使用`PSTFiles`之子資料夾名稱在步驟 2 中，然後使用`pstfiles`中`FilePath`CSV 檔案中的參數，匯入 PST 檔案將會失敗。 請務必在兩個執行個體中使用相同的案例。  <br/> |(保留空白)  <br/> Or  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |指定將匯入至使用者信箱的 PST 檔案名稱。  此參數的值是區分大小寫。  <br/> <br/>**重要：** CSV 檔案中的 PST 檔案名稱的情況必須已上傳至步驟 2 中的 Azure 儲存體位置的 PST 檔案相同。 例如，如果您使用`annb.pst`中`Name`參數 CSV 檔案中，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入會失敗。 請務必 PST CSV 檔案中的名稱，會使用相同的情況下，為實際的 PST 檔案。  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。  請注意，您無法指定公用資料夾，因為 PST 匯入服務不支援將 PST 檔案匯入公用資料夾。  <br/> 若要將 PST 檔案匯入非使用中的信箱，您必須指定此參數的信箱 GUID。 若要取得此 GUID，請執行下列 PowerShell 命令在 Exchange Online 中：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**附註：** 在某些情況下，您可能需要多個信箱相同電子郵件地址，其中一個信箱不在作用中信箱，而其他信箱位於虛刪除 （或非使用中） 的狀態。 在這些情況下，您必須指定信箱 GUID，以唯一識別信箱，若要將 PST 檔案匯入。 若要取得此 GUID 作用中信箱，請執行下列 PowerShell 命令： `Get-Mailbox <identity of active mailbox> | FL Guid`。 若要取得的 GUID，虛刪除 （或非使用中） 的信箱，請執行此命令`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。  <br/> | `annb@contoso.onmicrosoft.com` <br/> Or  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。 其中有兩個選項：  <br/><br/>**FALSE** -匯入 PST 檔案至使用者的主要信箱。  <br/> **TRUE** -匯入 PST 檔案至使用者的封存信箱。 This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). <br/><br/>如果您將這個參數設定為`TRUE`和未啟用使用者的封存信箱，該使用者的匯入就會失敗。 請注意，如果匯入失敗一位使用者 (因為他們的封存未啟用，而且此屬性設為`TRUE`)，將不會影響中匯入工作的其他使用者。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> <br/>**附註：** 若要將 PST 檔案匯入主要信箱位於內部部署使用者的雲端式封存信箱，只是指定`TRUE`此參數，並指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。  <br/> | `FALSE` <br/> Or  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於的信箱 （位於相同層級的收件匣資料夾和其他預設信箱資料夾） 的根層級的新資料夾。  <br/>  如果您指定`/`，將 PST 檔案中的項目會被匯入直接在使用者的收件匣] 資料夾。  <br/><br/>  如果您指定`/<foldername>`，將 PST 檔案中的項目將會匯入至名為資料夾*\<foldername\> * 。 例如，如果您使用`/ImportedPst`，項目會匯入至名為**ImportedPst**資料夾。 這個資料夾將會位於收件匣資料夾相同層級的使用者信箱。  <br/><br/> **提示：** 請考慮執行一些測試批次來嘗試使用這個參數，因此您可以決定要匯入 Pst 檔案的最佳資料夾位置。  <br/> |(保留空白)  <br/> Or  <br/>  `/` <br/> Or  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數字值。 此參數用於從中文、 日文和韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常會使用雙位元組字元集 (DBCS) 的字元編碼。 如果這個參數不用來匯入 PST 檔案，用於信箱資料夾名稱 DBCS 的語言，將資料夾名稱是通常亂碼之後匯入它們。  <br/><br/> 如需支援的值，使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)的清單。  <br/> <br/>**附註：** 如先前所述，這是選擇性的參數，您不需要加入 CSV 檔案中。 或者，您可以將它加入並將值保留空白，對一或多個資料列。  <br/> |(保留空白)  <br/> Or  <br/>  `932`（這是 ANSI/OEM 日文的程式碼] 頁面上識別碼）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>步驟 5： 在 Office 365 中建立 PST 匯入工作

下一步是在 Office 365 中的匯入服務中建立 PST 匯入工作。 如先前所述，您會將提交您在步驟 4 中建立 PST 匯入對應檔案。 在您建立新的工作之後，Office 365 分析的 PST 檔案中的資料，並再讓您有機會來篩選資料的實際取得匯入 PST 匯入對應檔案中指定的信箱 （請參閱 「[步驟 6](#step-6-filter-data-and-start-the-pst-import-job)）。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並登入 Office 365 組織中系統管理員帳戶使用的認證。 
    
2. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管**，然後按一下 [**匯入**。
    
3. 在 [**匯入**] 頁面上，按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。
    
    **附註：** 您必須被指派適當的權限，若要存取 [**匯入**] 頁面中的安全性 & 合規性中心，以建立新的匯入工作。 請參閱 <<c0>開始之前> 一節的詳細資訊。 
    
4. 為 PST 匯入工作中，輸入名稱，然後按一下 [**下一步**。 使用小寫字母、 數字、 連字號和底線。 您不能使用大寫字母，或在名稱中包含空格。
    
5. 在**您要上傳或運送資料？** ] 頁面上，按一下 [**上傳您的資料**，然後按一下 [**下一步**。
    
    ![按一下 [上傳您的資料，以建立網路上傳來匯入工作](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在步驟 4 中**匯入資料**] 頁面上，按一下 [**完成上傳我的檔案**而且**我有對應檔案的存取權**的核取方塊，，然後按一下 [**下一步]**。
    
    ![按一下 [步驟 4 中的兩個核取方塊](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. 在 [**選取的對應檔案**] 頁面上，按一下 [**選取對應檔案**送出您在步驟 4 中建立 PST 匯入對應檔案。 
    
    ![按一下 [選取對應檔以提交 CSV 檔案剛才匯入工作](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. CSV 名稱之後檔案會出現在 [**檔案名稱對應**] 下，按一下 [**驗證**] 來檢查您 CSV 檔中的錯誤。 
    
    ![按一下 [驗證] 來檢查錯誤的 CSV 檔案](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 檔案必須成功通過驗證，才能建立 PST 匯入工作。 請注意它成功驗證之後，將會變更為綠色的檔案名稱。 如果驗證失敗，按一下 [**檢視記錄檔]** 連結。 將開啟的驗證錯誤報告在失敗的檔案中的每一列的錯誤訊息。 
    
9. 成功驗證 PST 對應檔案之後，閱讀條款和條件文件中，，，然後按一下核取方塊。
    
10. 按一下 [**儲存**] 來提交工作，，然後按一下 [**關閉之後已成功建立工作。** 
    
    顯示狀態彈出式頁面時，**在進行中的分析**的狀態和新的匯入工作會顯示在 [**匯入**] 頁面上的清單中。 
    
11. 按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新顯示在 [**狀態**] 欄中的狀態資訊。 當分析已完成，且可匯入資料時，狀態會變更為**分析已完成**。
    
    您可以按一下 [匯入工作，以顯示 [狀態] 彈出式頁面，其中包含的每個對應檔案中列出的 PST 檔案匯入工作，例如狀態的詳細的資訊。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步驟 6： 篩選資料，並啟動 PST 匯入工作

您在步驟 5 中建立匯入工作之後，Office 365 會分析 （以安全無虞的方式） 的 PST 檔案中的資料所識別的項目並包含在 PST 檔案中的不同郵件類型的保留期限。 當分析已完成，且可匯入資料時，您可以選擇要匯入 PST 檔案中所包含的所有資料，或您可以修剪匯入藉由設定篩選器來控制哪些資料取得匯入的資料。
  
1. 在**匯入**頁面的安全性 & 合規性中心，按一下 [**準備好匯入至 Office 365**匯入工作在步驟 5 中所建立。 
    
    ![按一下 [準備好剛才匯入工作旁匯入 Office 365](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    飛入] 頁面上的會顯示 PST 檔案的相關資訊與匯入工作的其他資訊。
    
2. 在彈出式頁面上，按一下 [**匯入至 Office 365**。
    
    會顯示 [**篩選您的資料**] 頁面。 它會包含所產生的 Office 365，包括的保留天數之資料的相關資訊的 PST 檔案上執行的分析資料見解。 此時，您必須篩選，則會匯入或所有的資料是匯入資料的選項。 
    
    ![您可以修剪 PST 檔案中的資料，或匯入 xxx xx](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 執行下列其中一項動作：
    
    a. 若要修剪您匯入的資料，按一下 [**是，我想要匯入之前先加以篩選**。
    
    如需篩選的 PST 檔案中的資料，並再啟動匯入工作的詳細逐步指示，請參閱[篩選資料匯入至 Office 365 的 PST 檔案時](filter-data-when-importing-pst-files.md)。
    
    Or
    
    b. 若要匯入 PST 檔案中的所有資料，請按一下 [**否，我想要匯都入每個項目，** 然後按一下 [**下一步**。
    
4. 如果您選擇要匯入的所有資料，請按一下 [都啟動匯都入工作的 [**匯都入資料**]。 
    
    匯入工作的狀態會顯示在 [**匯入**] 頁面。 按一下 [![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以更新顯示在 [**狀態**] 欄中的狀態資訊。 按一下 [匯入工作，以顯示 [狀態] 彈出式頁面，會顯示每個 PST 檔案匯入的狀態資訊。 

## <a name="how-the-import-process-works"></a>匯入程序的運作方式
  
您可以使用網路上傳選項和 Office 365 匯入服務，以大量匯入 PST 檔案複製到使用者信箱。 網路上傳表示，您上傳的 PST 檔案在 Microsoft cloud 中的暫時存放區。 然後 Office 365 匯入服務複製的 PST 檔案存放區的目標使用者信箱。
  
以下是圖和網路上傳程序，將 PST 檔案匯入 Office 365 中的信箱的描述。
  
![工作流程的網路上傳將 PST 檔案匯入 Office 365 的程序](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **下載 PST 匯入工具及金鑰為私人的 Azure 儲存體位置**-第一個步驟是下載 Azure AzCopy 命令列工具，用來將 PST 檔案上傳至 Microsoft 雲端中的 Azure 儲存體位置便捷鍵。 您取得這些從安全性 & 合規性中心中的 [**匯入**] 頁面。 機碼 （稱為 「 安全的存取簽章 (SAS) 索引鍵，為您提供必要的權限，來上傳 PST 檔案複製至私人並保護 Azure 儲存體位置。 此便捷鍵是唯一的您的組織，並協助防止未經授權的存取您的 PST 檔案之後他們正在上傳至 Microsoft 雲端。 請注意，將 PST 檔案匯入至 Office 365 不會要求您的組織有不同的 Azure 訂用帳戶。 
    
2. **上傳 PST 檔案複製到 Azure 的儲存位置**的下一個步驟是使用 AzCopy.exe 工具 （在步驟 1 中下載） 上傳並將您的 PST 檔案儲存在位於相同的區域 Microsoft 資料中心的 Azure 儲存體位置其中您的 Office 365組織位於。 若要將其上傳，您想要匯入 Office 365 的 PST 檔案必須位於您組織中檔案共用或檔案。
    
    請注意，若要檢視的 PST 檔案清單之後他們正在上傳至 Azure 儲存體位置,，您可以執行選擇性步驟。
    
3. **建立 PST 匯入對應檔案**-已上載的 PST 檔案至 Azure 儲存體位置之後，下一步是建立指定的使用者信箱的 PST 檔案會匯入至，請注意 PST 檔案，可以是以逗號分隔的值 (CSV) 檔案 匯入至使用者的主要信箱或封存信箱。 Office 365 匯入服務將 PST 檔案匯入，以使用 CSV 檔案中的資訊。
    
4. **建立 PST 匯入工作**-下一個步驟是在安全性 & 合規性中心的 [**匯入**] 頁面上建立 PST 匯入工作並提交在上一個步驟中建立 PST 匯入對應檔案。 建立匯入工作之後，Office 365 分析的 PST 檔案中的資料，然後讓您有機會將篩選器來控制哪些資料實際取得匯入至 PST 匯入對應檔案中指定的信箱。 
    
5. **篩選器，將會匯入至信箱的 PST 資料**-建立並啟動匯入工作後，Office 365 分析的 PST 檔案中的資料 （安全且安全地） 所識別的項目並包含在 PST 檔案中的不同郵件類型的保留期限. 當分析已完成，且可匯入資料時，您可以選擇要匯入 PST 檔案中所包含的所有資料，或您可以修剪匯入藉由設定篩選器來控制哪些資料取得匯入的資料。
    
6. **啟動 PST 匯入工作**-啟動匯入工作後，Office 365 使用中的資訊 PST 匯入對應檔案從他的 Azure 儲存體位置的 Pst 檔案匯入至使用者信箱。 在安全性 & 合規性中心的 [**匯入**] 頁面上會顯示 （包括資訊匯入每個 PST 檔案） 匯入工作的狀態資訊。 匯入工作完成時，工作的狀態設為**完成**。
  
## <a name="more-information"></a>詳細資訊

- 為什麼 PST 檔案匯入至 Office 365？
    
  - 它是一個好方法來匯入 Office 365 組織的封存的郵件資料。
    
  - 資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。
    
  - 它可以協助解決組織的法務遵循需求，可讓您將 Office 365 合規性功能套用至資料，從您匯入 PST 檔案。 其中包括：
    
  - 啟用[封存信箱](enable-archive-mailboxes.md)及[自動展開封存](enable-unlimited-archiving.md)，讓使用者以其他信箱儲存空間來儲存您匯入的資料。 
    
  - 將信箱設[為訴訟暫止](https://go.microsoft.com/fwlink/?linkid=856286)保留您匯入的資料。 
    
  - 使用 Microsoft [eDiscovery 工具](search-for-content.md)來搜尋您匯入的資料。 
    
  - 使用[Office 365 保留原則](retention-policies.md)來控制要保留多久您匯入的資料，以及在保留期間到期之後要採取動作。 
    
  - 搜尋[Office 365 稽核記錄](search-the-audit-log-in-security-and-compliance.md)會影響您匯入資料的信箱相關事件。 
    
  - 將資料匯入封存資料，以便符合規範的[非使用中信箱](create-and-manage-inactive-mailboxes.md)。 
    
  - 使用[資料外洩防護原則](data-loss-prevention-policies.md)來防止從組織外部洩漏的敏感資料。 
  
- 以下是範例在步驟 1 中所取得之共用的存取簽章 (SAS) url。 此範例也包含您要上傳 PST 檔案複製到 Office 365 執行 AzCopy.exe 工具命令的語法。 請務必採取預防措施來保護 SAS URL，如同您可以保護密碼或其他安全性相關的資訊。

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
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is June 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
