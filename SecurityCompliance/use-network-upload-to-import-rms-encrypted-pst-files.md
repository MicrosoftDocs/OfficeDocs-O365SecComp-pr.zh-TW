---
title: 使用網路上傳將 RMS 加密的 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: 了解如何使用網路上傳至 RMS 加密 PST 檔案匯入 Office 365 中的使用者信箱。
ms.openlocfilehash: 8f08b17b5b975316afaf9545d5ba42057f35deca
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296576"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>使用網路上傳將 RMS 加密的 PST 檔案匯入 Office 365

**本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用網路上傳至 PST 檔案匯入使用者信箱的選項和匯入 Office 365 服務。網路上傳表示您上載 PST 檔案中 Microsoft cloud 暫時存放區。則 Office 365 匯入服務會複製 PST 檔案存放區從目標使用者信箱。匯入服務的新功能可讓您之前在其上傳並儲存在 Microsoft cloud 加密 PST 檔案。當他們正在匯入至使用者信箱這些檔案都會未加密。 
  
加密和 PST 檔案匯入 Office 365 信箱所需的步驟如下：
  
[步驟 1：為 PST 匯入設定 Azure Rights Management ](#step-1-set-up-azure-rights-management-for-pst-import)

[步驟 2：為 PST 匯入產生加密金鑰](#step-2-generate-an-encryption-key-for-pst-import)

[步驟 3： 取得 RMS 租用戶識別碼和授權的 URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[步驟 4： 下載 PST 匯入工具並複製 SAS URL](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[步驟 5： 加密和您 PST 檔案上傳至 Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[（選用）步驟 6： 檢視清單中的 PST 檔案上傳至 Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步驟 7： 建立 PST 匯入對應檔案](#step-7-create-the-pst-import-mapping-file)

[步驟 8：在 Office 365 中建立 PST 匯入工作](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> 您必須執行步驟 1 到步驟 4 只有一次安裝及設定您的組織來加密及 PST 檔案匯入 Office 365 信箱。您執行這些步驟之後，請遵循步驟 5 到步驟 8 每一個您想要加密、 上傳及匯入 PST 檔案的批次的時間。 
  
如需將資料匯入 Office 365 的詳細資訊，請參閱 ＜ [Overview of 匯入至 Office 365 貴組織 PST 檔案](importing-pst-files-to-office-365.md)。
  
## <a name="before-you-begin"></a>開始之前

- 您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後再將自己的成員身分或者。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：
    
  - 您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。
    
    或
    
  - 您必須是 Office 365 組織中的全域管理員。
    
  > [!TIP]
  > 請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。 
  
- 您要儲存您想要匯入 Office 365 上的檔案伺服器或組織中的共用的資料夾的 PST 檔案。在步驟 5 中，您用來執行 Office 365 ImportTool，由其將會加密並上傳儲存此檔案伺服器上或共用資料夾至 Office 365 的 PST 檔案。
    
- 此程序包括複製並儲存加密金鑰、 儲存機碼和識別機碼和 Url 的數字的複本。此資訊會用於加密和上傳 PST 檔案之步驟 5。請務必採取預防措施來保護這些剛剛像您會保護密碼或其他安全性相關資訊。例如您可能會將其儲存至受密碼保護 Microsoft Word 文件或將其儲存至已加密的 USB 磁碟機。請參閱[的詳細資訊](#more-information)] 區段中的下列機碼、 識別碼、 及 Url 的範例。 
    
- 您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。您執行此動作以指定在非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。如需詳細資訊，請參閱[步驟 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- 在 Exchange 混合部署中，您可以 PST 檔案匯入雲端式封存信箱的主要信箱位於內部部署的使用者。您這麼做依照 PST 匯入對應檔案中的下列：
    
  - 指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。 
    
  - 指定**TRUE**值`IsArchive`參數。 
    
    如需詳細資訊，請參閱[步驟 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- PST 檔案匯入至 Office 365 信箱之後，為信箱設定保留功能會開啟無限期的持續期間。這表示將不會處理在您關閉保留功能或設定要關閉保留日期之前中指派給信箱的保留原則。為什麼這麼做這？如果舊匯入至信箱的郵件，則它們可能會永久刪除 （清除） 因為其保留期間已過期為基礎之信箱的保留設定。將信箱設定保留功能將會讓信箱擁有者時間來管理這些新匯入訊息或讓您變更信箱的保留設定的時間。請參閱如需管理保留功能的建議[的詳細資訊](#more-information)] 區段。 
    
- 如果您不需要加密 PST 檔案您將其上傳至 Office 365 之前，請參閱[使用網路上傳至匯入至 Office 365 的 PST 檔案](use-network-upload-to-import-pst-files.md)。
    
- 如需使用網路上傳至 PST 檔案匯入 Office 365 常見問題集問題，請參閱 ＜[常見問題集匯入至 Office 365 的 PST 檔案](faqimporting-pst-files-to-office-365.md)。
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>步驟 1：為 PST 匯入設定 Azure Rights Management 

PST 匯入使用 Office 365 的 Azure 版權管理 (Azure RMS) 服務所提供的加密功能。這可讓您將它們上載到 Office 365 之前加密 PST 檔案。 
  
設定 Azure RMS PST 匯入包含三個步驟：
  
- [啟動 Azure RMS](#activate-azure-rms)
    
- [設定 RMS in Exchange Online](#configure-rms-in-exchange-online)
    
- [安裝 Active Directory RMS 用戶端](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>啟動 Azure RMS

Azure RMS 已停用根據預設，但寄件者或組織中的其他系統管理員可能已啟動它。遵循指示安裝並啟動 Azure DRM[啟動 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) 。
  
### <a name="configuring-rms-in-exchange-online"></a>設定 RMS in Exchange Online

您已啟動版權管理服務之後下, 一步是設定在 Exchange Online 使用 Azure RMS 設定資訊版權管理 (IRM)。如需詳細資訊，請參閱 ＜[設定 IRM 以使用 Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816)。
  
1. [連線至 Exchange Online 使用遠端 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 )。
    
2. 執行下列命令來設定 RMS 金鑰共用 URL。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    請根據貴組織的所在位置，透過下表來判斷正確的 RMS 金鑰共用位置。
    
    |**位置**|**RMS 金鑰共用位置**|
    |:-----|:-----|
    |北美  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |歐盟  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |亞洲  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南美洲  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 for Government (政府社群雲端)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup>只有已購買 Office 365 for Government Sku （政府社群雲端） 的客戶應該使用此 RMS 金鑰共用位置。 
  
    例如，此命令會設定 RMS Online 金鑰共用位置在 Exchange Online 客戶位於 「 北美地區 」 的。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. 執行下列命令以從 RMS Online 的受信任的發行網域 (TPD) 匯入 Office 365 組織。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD 包含在組織中使用 RMS 功能所需的設定，其包括加密 PST 檔案。  
    
4. 執行下列命令以針對 Office 365 組織啟用 IRM。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>安裝 Active Directory RMS 用戶端

本節中的最後一個步驟是下載 Rights Management Services (RMS) 用戶端 2.1。此軟體可協助保護 Azure RMS 存取並保護通過使用 Azure 您安裝的應用程式在您將用來加密和上傳步驟 5 中的 PST 檔案的相同電腦上的 RMS 用戶端的資訊。 
  
1. 下載[Rights Management Service 用戶端 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)。
    
2. 執行 Active Directory Rights Management Service Client 2.1 精靈來安裝用戶端。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>步驟 2：為 PST 匯入產生加密金鑰

您已設定 「 Azure RMS 之後下, 一步是產生會用來加密您上傳到 Office 365 的 PST 檔案的加密金鑰 （稱為 「 對稱的索引鍵）。您將做為服務主要 Azure Active Directory 中新增 PST 匯入服務來執行這項作業。將此應用程式以服務主要名稱會允許您將上傳時直接與 Azure Active Directory 進行驗證 PST 匯入 service 加密的 Azure 儲存位置中之步驟 5 的 PST 檔案。
  
1. 啟動 Windows powershell 的 Azure Active Directory 模組。
    
2. 執行下列命令來連接 Microsoft Online Service。
    
    ```
    Connect-MsolService
    ```

3. 輸入 Office 365 組織中系統管理員帳戶的認證並再按一下 [**確定]**。
    
4. 執行下列命令來產生加密金鑰 (稱為對稱金鑰)。您將以透過建立新 PST 加密主體的方式進行。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    系統會顯示新 PST 加密主體的對稱金鑰以及屬性。
    
    ![複製並儲存所顯示的對稱金鑰](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 將對稱金鑰複製到文字檔案或 Word 檔案中。如先前所述，請確定已採取相關預防措施來保護此檔案。因為對稱金鑰僅會顯示這一次，所以您可以考慮擷取此視窗的螢幕擷取畫面，然後將其儲存至相同檔案中。  
    
    > [!IMPORTANT]
    > 在您建立 PST 加密主體後，將無法使用 **Get-MsolServicePrincipal** 指令程式來擷取對稱金鑰。這就是儲存金鑰為何如此重要的原因。 
  
開啟並連線至 Microsoft Online 服務保留 Azure Active Directory 的 Windows PowerShell 模組。您將在此視窗的下一個步驟中執行的命令。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>步驟 3： 取得 RMS 租用戶識別碼和授權的 URL

下一個步驟是取得租用戶識別碼和 Azure RMS 服務組織的授權的位置 URL。複製並將此資訊儲存至相同檔案包含從步驟 2 對稱的索引鍵。識別碼和 URL 將用於在步驟 5 來加密 PST 檔案。
  
1. Azure Active Directory 模組 （這連線至 Microsoft Online 服務） 的 Windows powershell 中執行下列命令來連線到 Office 365 組織中的 Azure RMS 服務。
    
    ```
    Connect-AadrmService 
    ```

2. 輸入您的 Office 365 組織中系統管理員帳戶的認證並再按一下 [**確定]**。
    
3. 執行下列命令以顯示 Office 365 組織租用戶識別碼 Azure RMS 服務。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    複製並儲存的值`BPOSId`屬性。 
    
4. 執行下列命令以顯示 Azure RMS 服務授權的位置。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    複製並儲存的值`LicensingIntranetDistributionPointUrl`屬性。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>步驟 4： 下載 PST 匯入工具並複製 SAS URL

現在您已設定 Azure RMS 並取得必要加密 PST 檔案的識別碼下, 一步是下載並安裝到 Office 365 的工具，將會執行在步驟 5 中加密及上傳 PST 檔案。這些工具的 Azure AzCopy 工具與 Office 365 資料加密工具。您也將您的組織複製 SAS URL。此 URL 會在 Microsoft 雲端組織和共用存取簽章 (SAS) 金鑰 Azure 儲存位置的網路 URL 的組合。此機碼提供 PST 檔案上傳至 Azure 儲存位置的必要權限。將它儲存到同一個檔案您是否已在步驟 2 和步驟 3 中複製的其他資訊。先前所述，請以保護 SAS URL。 
  
> [!IMPORTANT]
> 您必須使用 Azure AzCopy 5.0 版成功 PST 檔案上傳至 Azure 儲存位置。較新版本的 AzCopy 工具不支援將 PST 檔案匯入 Office 365。請務必 AzCopy 工具從**上傳檔案透過網路**頁面下載遵循此步驟中的程序。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 使用 Office 365 組織中系統管理員帳戶的認證。
    
3. 在左窗格中，按一下 [**資料控管**和 [**匯入**。
    
4. 在 [**匯入**] 頁面上，按一下 [**移至 [匯入服務**。
    
5. 在 [ **Office 365 的匯入資料**] 頁面上按一下 [**新增工作**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**上傳的電子郵件 （PST 檔案）**。
    
6. 按一下 [**上傳檔案透過網路**] 頁面的 [步驟 2 中的 [**顯示網路上傳 SAS URL**]。
    
7. 顯示 URL 後，將其複製並將它儲存在您儲存其他按鍵的檔案。請務必複製整個 URL。 
    
8. 在步驟 3 中，按一下 [**下載 Azure AzCopy 工具**下載並安裝 Azure AzCopy 工具。 
    
9. 在快顯視窗中，按一下 [安裝 Azure AzCopy 工具的 [**執行**]。 
    
    > [!IMPORTANT]
    > 請務必在預設位置是安裝 Azure AzCopy 工具`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`的電腦上執行 64 位元 Windows。那是因為當您在步驟 5 中執行 O365ImportTool.exe，它會尋找在此位置的 AzCopy 工具。 
  
10. 您已安裝 Azure AzCopy 工具之後，按一下 [**下載 Office 365 資料加密及匯入工具**。
    
11. 在快顯視窗中，按一下 [**儲存** \> O365ImportTool.zip 檔案儲存到資料夾本機電腦上的 [**另存為**。 
    
12. 解壓縮 O365ImportTool.zip 檔案。
    
13. 按一下 [**取消**] 關閉 [**上傳檔案透過網路**] 頁面。 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>步驟 5： 加密和您 PST 檔案上傳至 Office 365

完成步驟 1 到步驟 4 之後，即可使用 O365ImportTool.exe 工具來加密和 PST 檔案上傳至 Office 365。這項工具會加密 PST 檔案，然後上傳並將其儲存在 Microsoft 雲端 Azure 的儲存位置。若要完成此步驟，PST 檔案必須位於檔案共用或組織中的檔案伺服器。這就是所謂的下列程序中的來源目錄。每次執行 O365ImportTool.exe 工具，您將可以指定不同的來源目錄。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
2. 移至您在步驟 4 中安裝 O365ImportTool.exe 工具的目錄。
    
3. 執行下列命令來加密和 PST 檔案上傳至 Office 365。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    下表說明了參數與其需要的值。請注意，您在先前步驟中所取得的資訊，會在這些參數內的值中使用。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |指定包含要上傳至 Office 365 的 PST 檔案在組織中的來源目錄。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |指定授權 Azure RMS 服務的位置。使用的值`LicensingIntranetDistributionPointUrl`您在步驟 3 中取得的屬性。請務必環繞雙引號使用此參數的值 ("")<br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |指定 Azure RMS 組織的識別碼。使用的值`BPOSId`您在步驟 3 中取得的屬性。<br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |步驟 2 中指定所取得的對稱金鑰。請務必環繞雙引號使用此參數的值 ("")。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |會指定是否將 PST 檔案上傳透過網路或隨附其硬碟上。此值`upload`指出您已透過網路上載的檔案。此值`drive`表示您要傳送 Pst 硬碟上。<br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |在 Office 365 PST 檔案要上傳至 ； 指定目的地這是您的組織 Azure 儲存位置。此參數的值是由您在步驟 4 中複製 SAS URL 中的網路上傳 URL 所組成。請務必環繞雙引號使用此參數的值 ("")。<br/><br/> **提示：**（選用）您可以在 Azure 的儲存位置上傳至的加密的 PST 檔案中指定的子資料夾。您執行方法是在網路上傳 URL 中新增子資料夾位置 （之後"ingestiondata")。第一個範例不會指定子資料夾;這表示 Pst 將可上傳到根目錄 （名為*ingestiondata* ） 的 Azure 儲存位置。第二個範例 Azure 儲存位置中的上傳至 （名為*EncryptedPSTs* ） 的子資料夾的 PST 檔案。           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> 或  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |會指定您組織的 SAS 索引鍵。此參數的值是由 SAS 金鑰與您在步驟 4 中複製 SAS URL 所組成。請注意 SAS 機碼中的第一個字元為問號 ("？")。請務必環繞雙引號使用此參數的值 ("")。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |使 O365ImportTool.exe 工具會將位於所指定的來源目錄中的子資料夾中的 Pst 檔案複製此選用參數會指定遞迴模式`/srcdir:`參數。  <br/><br/> **附註：** 如果加上此參數，在子資料夾中的 PST 檔案不同的檔案路徑名稱中有 Azure 的儲存位置之後他們正在上傳。您必須在您在步驟 7 中建立 CSV 檔案中指定的實際檔案路徑名稱。           | `/recurse` <br/> |
   
    這是 O365ImportTool.exe 工具針對各個參數使用實際值的語法範例︰
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    在您執行命令後，便會顯示 PST 檔案加密及上傳進度的狀態訊息。最終狀態訊息會顯示已成功加密及上傳的檔案總數。  
    
    > [!TIP]
    > 您已順利執行 O365ImportTool.exe 命令並確認所有參數正確都無誤後，命令列語法到您複製資訊相同 （安全） 檔案的複本儲存您在取得上述步驟。然後您可以命令複製並貼入此命令提示字元中每一個您想要執行 O365ImportTool.exe 工具來加密和 PST 檔案上傳至 Office 365 的時間。您可能必須變更的唯一值是針對該組`/srcdir:`和`/upload-dest:`參數。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（選用）步驟 6： 檢視清單中的 PST 檔案上傳至 Office 365

為選用的步驟，您可以安裝及使用 Microsoft Azure 儲存在檔案總管 （這是免費，開放原始碼工具） 來檢視您已上傳至 Azure blob PST 檔案的清單。為達成此目的三種很好的原因有：
  
- 確認 PST 檔案從共用的資料夾或檔案伺服器在組織中的已成功上傳至 Azure blob。

- 確認已加密的 PST 檔案。加密的 PST 檔案有`.pfile`附加至 PST 檔案名稱 ； 的副檔名例如， `pilarp.pst.pfile`。
    
- 確認每個 PST 檔案上傳至 Azure blob 的檔案名稱 （和子資料夾 pathname 如果包含一個）。當您建立對應檔案中的下一個步驟因為您有指定的資料夾路徑名稱和每個 PST 檔案的檔案名稱 PST，這是很有幫助。確認這些名稱可以協助降低您 PST 對應檔案中的潛在錯誤。
    
Microsoft Azure 儲存在檔案總管處於預覽。 
  
 > [!IMPORTANT]
>  您無法使用 Azure 儲存在檔案總管上傳或修改 PST 檔案。將 PST 檔案匯入 Office 365 唯一支援的方法是使用 AzCopy。此外，您無法刪除您已上傳至 Azure blob 的 PST 檔案。如果您嘗試刪除 PST 檔案，將會收到有關不會察覺必要的權限的錯誤。請注意 Azure 儲存區域會自動刪除所有 PST 檔案。如果有任何匯入工作進行，然後所有 PST 檔案中的 [ **ingestiondata** ] 容器中會不刪除 30 天後所建立的最新的匯入工作。 
  
若要安裝 Azure 儲存在檔案總管並連線至 Azure 儲存區：
  
1. 下載並安裝[Microsoft Azure 儲存檔案總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 啟動 Microsoft Azure 儲存在檔案總管、 以滑鼠右鍵按一下左窗格中的**存放區的帳戶**和 [**連線至 Azure 存放區**。 
    
    ![以滑鼠右鍵按一下 [儲存的帳戶，然後按一下 [連線至 Azure 存放區](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 在 [**連接到 Azure 存放區**] 下方，在步驟 4 中貼上您取得 SAS URL] 和 [**下一步**。 
    
    ![在連接至 Azure 存放區] 頁面上的方塊中貼上 SAS URL](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. 在 [**連線摘要**] 頁面上您可以檢閱連線資訊，並再按一下 [**連線**。 
    
5. [**存放區的帳戶**] 下展開 **(服務 SAS)** ] 節點，然後展開**Blob 容器**] 節點。 
    
6. 以滑鼠右鍵按一下**ingestiondata**，並再按一下 [**開啟 Blob 容器編輯器**。
    
    ![以滑鼠右鍵按一下 ingestiondata，然後按一下 [開啟 Blob 容器編輯器]](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    會顯示 Azure 存放區] 區域中，您在步驟 5 中上傳的 PST 檔案的清單。
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. 使用 Microsoft Azure 儲存在檔案總管完成作業後，用滑鼠右鍵按一下**ingestiondata**，並再按一下 [**卸離**中斷與 Azure 儲存區的連線。否則，您會收到錯誤的下次您嘗試附加。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>步驟 7： 建立 PST 匯入對應檔案

PST 檔案已加密及上傳至 Office 365 組織 Azure 儲存位置之後下, 一步是建立逗點分隔值 (CSV) 檔案，指定 PST 檔案會以匯入的使用者信箱。當您建立 PST 匯入工作，會送出這個的 CSV 檔案中的下一個步驟。
  
1. [下載 PST 匯入對應檔案的複本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。 
    
2. 開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    第一列或欄位名稱] 列的 CSV 檔案列出要使用 PST 匯入服務至 PST 檔案匯入使用者信箱的參數。每個參數名稱是以逗號分隔。標頭列] 下方的每一個資料列代表將 PST 檔案匯入特定信箱的參數值。您將需要一列的每一個您想要匯入使用者信箱的 PST 檔案。請務必對應檔案中的版面配置區資料取代實際資料。
    
    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 
  
3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要匯入資料至 Office 365 服務。若要匯入 PST 檔案至使用者信箱，請使用`Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |在 Azure 的儲存位置上傳至 PST 檔案中之步驟 5 中指定的資料夾位置。  <br/>  如果您沒有加入選用的子資料夾名稱中的網路 URL 中`/upload-dest:`參數在步驟 5 中，將此參數保留空白 CSV 檔案中。如果在包含子資料夾名稱，請將它指定這個參數中。此參數的值是區分大小寫。無論如何，*不*包含"ingestiondata"中的值`FilePath`參數。<br/> <br/>**重要：** 大小寫的檔案路徑名稱必須是所用如果 SAS URL 中包含的選用子資料夾名稱相同案例`/upload-dest:`在步驟 5 中的參數。例如，如果您是使用`EncryptedPSTs`的子資料夾名稱在步驟 5 中，然後使用`encryptedpsts`中`FilePath`CSV 檔中的參數，將會失敗 PST 檔案匯入。請務必在兩個執行個體中使用相同的大小寫。           |(保留空白)  <br/> 或  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |指定要匯入至使用者信箱的 PST 檔案的名稱。此參數的值是區分大小寫。因為加密 PST 檔案上傳至 Azure 儲存位置、`.pfile`副檔名新增至 PST 檔案名稱。您必須新增`.pfile`延伸模組名稱的 PST 檔案 CSV 檔案中。<br/><br/> **重要：** CSV 檔案中的 PST 檔案名稱的大小寫必須已上傳至 Azure 儲存位置中之步驟 5 的 PST 檔案相同。例如，如果您使用`annb.pst.pfile`中`Name`參數中的 CSV 檔案，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入就會失敗。請務必 PST CSV 檔案中的名稱會使用為實際的 PST 檔案的大小寫相同。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。   <br/> 匯入 PST 檔案至不在作用中的信箱，您必須指定此參數的信箱 GUID。若要取得這個 GUID，請執行下列 PowerShell 命令 in Exchange Online：`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **附註：** 在某些情況下，您可能會有多個信箱使用同一個電子郵件地址，其中一個信箱不在作用中信箱和其他信箱位於虛刪除 （或非使用中） 的狀態。在下列情況下，您有指定信箱的信箱來唯一地識別要匯入至 PST 檔案的信箱 GUID。若要取得這個作用中信箱的 GUID，請執行下列 PowerShell 命令： `Get-Mailbox - <identity of active mailbox> | FL Guid`。若要取得虛刪除 （或非使用中） 的信箱的 GUID，請執行此命令`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：<br/> **FALSE**將 PST 檔案匯入使用者的主要信箱。  <br/> **True 是表示**將 PST 檔案匯入使用者的封存信箱。  <br/>  如果您將此參數保留空白，PST 檔案匯入使用者的主要信箱。  <br/><br/> **附註：** 匯入 PST 檔案到雲端式封存信箱的主要信箱位於內部部署的使用者，只要指定此參數 **，則為 TRUE** ，並指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。           | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於信箱 （相同層級 [收件匣] 資料夾和其他預設信箱資料夾） 的根層級的新資料夾。  <br/>  如果您指定`/`、 PST 檔案中的項目會被匯入直接在使用者的 [收件匣] 資料夾。  <br/>  如果您指定`/<foldername>`、 PST 檔案中的項目將會匯入至名為子資料夾*\<foldername\> * 。例如，如果您是使用`/ImportedPst`、 項目會匯入至名為**ImportedPst**子資料夾。這個子資料夾會位於使用者的 [收件匣] 資料夾。<br/><br/> **提示：** 請考慮執行一些測試批次到實驗這個參數讓您可以決定要匯入至 Pst 檔案的最佳資料夾位置。           |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數值。此參數用於從中文、 日文及韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常使用雙位元組字元集 (DBCS) 的字元編碼。如果此參數不用來匯入 PST 檔案的信箱資料夾名稱使用 DBCS 的語言，則他們正在匯入後通常被混亂資料夾名稱。如需使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)支援值的清單。<br/><br/> **附註：** 如先前另有說明，這是選用的參數與您沒有包含 CSV 檔案中。或者您可以將它包含並將此值保留空白的一或多個資料列。           |(保留空白)  <br/> 或  <br/>  `932`（這是程式碼] 頁面上的識別碼 ANSI/OEM 日文）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>步驟 8：在 Office 365 中建立 PST 匯入工作

最後一個步驟是在 Office 365 中的匯入服務中建立 PST 匯入工作。如先前所述，您會將提交您在步驟 7 中建立之 PST 匯入對應檔案。匯入服務建立新的工作之後，將會解除對應檔案中使用的資訊層加密和 （您所上傳到步驟 5 中的 Office 365） PST 檔案匯入指定的使用者信箱。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 使用 Office 365 組織中系統管理員帳戶的認證。
    
3. 在左窗格中，按一下 [**資料控管**和 [**匯入**。
    
4. 在 [**匯入**] 頁面上，按一下 [**移至 [匯入服務**。
    
5. 在 [ **Office 365 的匯入資料**] 頁面上按一下 [**新增工作**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**上傳的電子郵件 （PST 檔案）**。
    
6. 在 [**上傳檔案透過網路**] 頁面上，按一下 [ **I 完成上傳我檔案****我有對應檔案的存取權**的核取方塊，，然後按一下 [**下一步]**。 
    
7. 輸入 PST 匯入工作、 名稱，然後按 [**下一步**。
    
8. 按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)選取您在步驟 7 中建立的對應 PST 檔案。 
    
9. CSV 檔案的名稱會出現在清單之後，加以選取並再按一下 [**驗證**] 檢查 CSV 檔中的錯誤。 
    
    > [!NOTE]
    > 為舊清楚，加密的 PST 檔案時，`.pfile`副檔名會附加至 PST 檔案名稱。您必須新增`.pfile`延伸模組名稱的 PST 檔案 CSV 檔案中。如果您未驗證的 CSV 檔案將會失敗。 
  
    CSV 檔案具有建立 PST 匯入工作成功驗證。如果驗證失敗，請按一下 [**狀態**] 欄中的**無效**的連結。將開啟的 PST 匯入對應檔案的複本失敗的檔案中的每一列的錯誤訊息。 
    
10. 當 PST 對應檔案驗證成功時，請檢閱條款和條件文件，然後按一下 [核取方塊]。
    
11. 按一下 [**完成**] 以送出工作。 
    
    此工作會顯示在**Office 365 的匯入資料**] 頁面上的 PST 匯入工作清單中。 
    
12. 選取此工作，按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中顯示狀態資訊。 
    
13. 在 [詳細資料] 窗格中，按一下 [**檢視詳細資料]** 以取得最新狀態的選取工作]。 
 
## <a name="more-information"></a>詳細資訊

- 為什麼要選擇 PST 檔案匯入 Office 365？
    
  - 它是一個好方法來將組織的電子郵件移轉至 Office 365。
    
  - 它可讓您透過下列方式協助解決組織的法務遵循需求︰
    
  - 啟用封存信箱以提供使用者額外的信箱儲存空間。
    
  - 保存信箱以保留內容。
    
  - 使用 Microsoft eDiscovery 工具來搜尋信箱中的內容。
    
  - 使用保留原則來控制信箱內容要保留多久。
    
  - 搜尋 Office 365 信箱相關的事件稽核記錄。
    
  - 它可協助防止資料遺失。Office 365 信箱將會匯入的 PST 檔案繼承 Exchange Online 的高可用性的功能而非儲存在使用者電腦上的資料。
    
  - 資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。
    
- 以下是範例金鑰、 識別碼、 及取得步驟 2、 3 及 4 中的 Url。此範例也會包含您執行在 O365ImportTool.exe 工具來加密及上傳 PST 檔案至 Office 365 的命令語法。請務必採取預防措施來保護這些剛剛像您會保護密碼或其他安全性相關資訊。
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- 如先前所述的 Office 365 匯入服務會開啟設定 （無限期的持續時間） 之後 PST 檔案匯入至信箱的保留。這表示*RentionHoldEnabled*屬性設為`True`以便將不會處理指派給信箱的保留原則。這可讓管理新匯入訊息來防止刪除或封存原則中刪除或封存舊郵件的信箱擁有者時間。以下是一些以管理此保留所能採取的步驟： 
    
  - 後段特定時間內，您就可以關閉保留功能來執行`Set-Mailbox -RetentionHoldEnabled $false`命令。指示，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/p/?LinkId=544749)。
    
  - 您可以設定保留功能，讓一些日期未來關閉。您執行這項作業執行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假設今天的日期是 2016 年 7 月 1，而且您想關閉在 30 天保留功能，您會執行下列命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此案例中，您會將保留*RentionHoldEnabled*屬性設定為`True`。如需詳細資訊，請參閱[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以變更使較舊的項目匯入的將不會立即刪除或移至使用者的封存信箱指派給信箱的保留原則的設定。例如，您無法延長刪除或封存原則指派給信箱的保留時間。在此案例中，您會關閉信箱保留之後變更此保留原則的設定。如需詳細資訊，請參閱 ＜ [Set up Office 365 組織中信箱的封存及刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。
