---
title: 使用網路上傳將 RMS 加密的 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: 了解如何使用網路上傳將 RMS 加密的 PST 檔案匯入到 Office 365 中的使用者信箱。
ms.openlocfilehash: e14c5a7260bc8b2092075dd2ab711f4da2d3b9c2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157995"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>使用網路上傳將 RMS 加密的 PST 檔案匯入 Office 365

**本文適用於系統管理員。您試圖將 PST 檔案匯入您自己的信箱？請參閱[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用網路上傳將 PST 檔案匯入使用者信箱的選項和 Office 365 匯入服務。 網路上傳表示，您上傳的 PST 檔案在 Microsoft cloud 中的暫時存放區。 然後 Office 365 匯入服務複製的 PST 檔案存放區的目標使用者信箱。 匯入服務的新功能可讓您之前他們所上傳並儲存在 Microsoft cloud 加密您的 PST 檔案。 他們正在匯入至使用者信箱時，這些檔案將會是未加密。 
  
加密及匯入 PST 檔案至 Office 365 信箱所需的步驟如下：
  
[步驟 1： 為 PST 匯入設定 Azure Rights Management](#step-1-set-up-azure-rights-management-for-pst-import)

[步驟 2： 為 PST 匯入產生加密金鑰](#step-2-generate-an-encryption-key-for-pst-import)

[步驟 3： 取得 RMS 租用戶識別碼和授權 URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[步驟 4： 下載 PST 匯入工具，並複製的 SAS URL](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[步驟 5： 加密，並將您的 PST 檔案上傳至 Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[（選用）步驟 6： 檢視清單中的 PST 檔案上傳至 Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步驟 7： 建立 PST 匯入對應檔案](#step-7-create-the-pst-import-mapping-file)

[步驟 8： 在 Office 365 中建立 PST 匯入工作](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> 您必須執行步驟 1 到步驟 4 只有一次，安裝及設定您的組織來加密及匯入 PST 檔案至 Office 365 信箱。 您執行這些步驟之後，請遵循步驟 5 到步驟 8 每個您想要加密、 上傳和匯入 PST 檔案的批次的時間。 
  
如需將資料匯入 Office 365 的詳細資訊，請參閱 < <b0>Overview of 匯入您組織的 PST 檔案至 Office 365</b0>。
  
## <a name="before-you-begin"></a>開始之前

- 您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 將 PST 檔案匯入 Office 365 信箱。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：
    
  - 您必須獲指派 「 郵件收件者角色在 Exchange Online。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
  - 您必須是 Office 365 組織中的全域系統管理員。
    
  > [!TIP]
  > 請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。 若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。 
  
- 您必須以儲存您想要在檔案伺服器或組織中的共用的資料夾上匯入 Office 365 的 PST 檔案。 在步驟 5 中您用來執行 Office 365 ImportTool，這將會加密並上傳的 PST 檔案會儲存此檔案伺服器上或共用資料夾至 Office 365。
    
- 此程序牽涉到複製並儲存加密金鑰、 存放裝置金鑰，以及識別金鑰和 Url 數目的複本。 此資訊將在步驟 5 中用來加密及上傳您的 PST 檔案。 請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。 舉例來說，您可能會將這些資訊儲存於受密碼保護的 Microsoft Word 文件內，或是將它們儲存於已加密的 USB 裝置中。 請參閱範例的這些機碼、 識別碼及 Url[的詳細資訊](#more-information)一節。 
    
- 您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。 您執行這項操作藉由指定中的非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。 如需詳細資訊，請參閱[步驟 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- 在 Exchange 混合式部署中，您可以將 PST 檔案匯入主要信箱位於內部部署使用者的雲端式封存信箱。 您這麼做，執行在 PST 匯入對應檔案中的下列動作：
    
  - 指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。 
    
  - 指定的值 **，則為 TRUE**以`IsArchive`參數。 
    
    如需詳細資訊，請參閱[步驟 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- PST 檔案匯入到 Office 365 信箱之後，為信箱設定保留功能已為期的持續時間。 這表示指派給信箱的保留原則不會處理，直到您關閉保留功能或設定要關閉保留的日期。 為什麼這麼做這樣？ 如果匯入至信箱的郵件都會舊，他們可能會永久刪除 （清除） 因為其保留期間已經過期根據為信箱設定保留設定。 將信箱置於保留功能，可讓信箱擁有者時間來管理這些新匯入郵件或讓您有時間變更信箱的保留設定。 請參閱管理保留功能的相關建議[的詳細資訊](#more-information)一節。 
    
- 如果您不需要加密您的 PST 檔案，您將更新上傳至 Office 365 之前，請參閱[使用網路上傳至 Office 365 的 PST 檔案匯入](use-network-upload-to-import-pst-files.md)。
    
- 如需使用網路上傳將 PST 檔案匯入 Office 365 的常見問題集問題，請參閱 <<c0>匯入 PST 檔案複製到 Office 365 的常見問題。
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>步驟 1： 為 PST 匯入設定 Azure Rights Management

PST 匯入使用 Office 365 中的 Azure 版權管理 (Azure RMS) 服務所提供的加密功能。 這可讓您之前將檔案上傳至 Office 365 加密的 PST 檔案。 
  
為 PST 匯入設定 Azure RMS 包含三個步驟：
  
- [啟動 Azure RMS](#activating-azure-rms)
    
- [設定 RMS in Exchange Online](#configuring-rms-in-exchange-online)
    
- [安裝 Active Directory RMS 用戶端](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>啟動 Azure RMS

Azure RMS 已停用依預設，但您或貴組織中的另一個系統管理員可能已啟用它。 請遵循指示來安裝及啟動 Azure DRM[啟動 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) 。
  
### <a name="configuring-rms-in-exchange-online"></a>設定 RMS in Exchange Online

您已啟動版權管理服務之後下, 一步是設定在 Exchange Online 使用 Azure RMS 設定資訊版權管理 (IRM)。 如需詳細資訊，請參閱 <<c0>將 IRM 設定為使用 Azure Rights Management。
  
1. [使用連線到 Exchange Online 遠端 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 )。
    
2. 執行下列命令，以設定 RMS 金鑰共用 URL。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    使用下表來決定正確的 RMS 金鑰共用位置的貴組織的位置。
    
    |**位置**|**RMS 金鑰共用位置**|
    |:-----|:-----|
    |北美  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |歐盟  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |亞  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南美洲  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 for Government (政府社群雲端)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup>只有已購買 Office 365 for Government Sku （政府社群雲端） 的客戶應該使用此 RMS 金鑰共用位置。 
  
    例如，此命令會設定 RMS Online 金鑰共用位置在 Exchange Online 為北美客戶。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. 執行下列命令，從 RMS Online 匯入受信任發行網域 (TPD)，以您的 Office 365 組織。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD 包含在您的組織，包括加密 PST 檔案中使用 RMS 功能所需的設定。 
    
4. 執行下列命令，以針對您的 Office 365 組織啟用 IRM。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>安裝 Active Directory RMS 用戶端

本節中的最後一個步驟是下載 Rights Management Services (RMS) 用戶端 2.1。 此軟體有助於保護 Azure RMS 的存取，並保護流經使用 Azure RMS 的應用程式的資訊。 在您將用來加密及上傳 PST 檔案在步驟 5 中的同一部電腦上安裝的 RMS 用戶端。 
  
1. 下載[Rights Management Service Client 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)。
    
2. 執行 Active Directory Rights Management Service Client 2.1 精靈來安裝用戶端。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>步驟 2： 為 PST 匯入產生加密金鑰

您已設定 Azure RMS 之後下, 一步是產生加密金鑰 （稱為 「 對稱金鑰） 將會用來加密您上傳至 Office 365 的 PST 檔案。 您將以主體在 Azure Active Directory 服務新增 PST 匯入服務來執行這項操作。 新增此應用程式，為服務主要名稱會允許直接與 Azure Active Directory 進行驗證，當您上傳 PST 匯入服務加密 PST 檔案複製到步驟 5 中的 Azure 儲存體位置。
  
1. 啟動 Windows PowerShell 的 Azure Active Directory 模組。
    
2. 執行下列命令，以連線至 Microsoft Online 服務。
    
    ```
    Connect-MsolService
    ```

3. 輸入您的 Office 365 組織中系統管理員帳戶的認證，然後按一下 [**確定]**。
    
4. 執行下列命令，以產生加密金鑰 （通話的對稱金鑰）。 您將建立新的 PST 加密主體。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    系統會顯示的對稱金鑰以及屬性的新 PST 加密主體。
    
    ![複製並儲存所顯示的對稱金鑰](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 將的對稱金鑰複製到文字編輯器或 Word 檔案。 如先前所述，請確定已採取相關預防措施來保護此檔案。 由於這是唯一的時候，顯示的對稱金鑰，您也可能會考慮採取此視窗的螢幕擷取畫面，並將它儲存至相同的檔案。 
    
    > [!IMPORTANT]
    > 在您建立 PST 加密主體之後，您無法使用**Get-MsolServicePrincipal**指令程式來擷取的對稱金鑰。 這就是為什麼請務必儲存此金鑰。 
  
開啟並連線至 Microsoft Online service，請保留 Active Directory 模組的 Windows PowerShell 的 Azure。 您會在此視窗中的下一個步驟中執行命令。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>步驟 3： 取得 RMS 租用戶識別碼和授權 URL

下一步是以取得租用戶識別碼和 Azure RMS 服務以進行貴組織的授權位置 URL。 複製並儲存到相同的檔案，其中包含從步驟 2 的對稱金鑰的這項資訊。 在步驟 5 中將使用 「 URL 與識別碼 」，來加密您的 PST 檔案。
  
1. Azure Active Directory 模組中的 Windows PowerShell （這連線至 Microsoft Online service），執行下列命令，以連線到 Office 365 組織中的 Azure RMS 服務。
    
    ```
    Connect-AadrmService 
    ```

2. 輸入您的 Office 365 組織中系統管理員帳戶的認證，然後按一下 [**確定]**。
    
3. 執行下列命令，以顯示 Office 365 組織中的 Azure RMS 服務的租用戶識別碼。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    複製並儲存的值為`BPOSId`屬性。 
    
4. 執行下列命令，以顯示您的 Azure RMS 服務的授權位置。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    複製並儲存的值為`LicensingIntranetDistributionPointUrl`屬性。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>步驟 4： 下載 PST 匯入工具，並複製的 SAS URL

既然您已設定 Azure RMS，並取得必要加密 PST 檔案的識別碼下, 一個步驟是下載及安裝的工具，您將會執行在步驟 5 來加密及上傳 PST 檔案至 Office 365。 這些工具是 Azure AzCopy 工具和 Office 365 資料加密工具。 您也將複製 SAS URL 為您的組織。 此 URL 是您的組織和共用的存取簽章 (SAS) 索引鍵的 Microsoft cloud 中的 Azure 儲存體位置的網路 URL 的組合。 此機碼為您提供要上傳 PST 檔案至您的 Azure 儲存體位置的必要權限。 將它儲存到相同的檔案您已在步驟 2 和步驟 3 複製到的其他資訊。 如先前所述，採取預防措施來保護 SAS URL。 
  
> [!IMPORTANT]
> 您必須使用 Azure AzCopy 5.0 版才能成功上傳 PST 檔案至 Azure 儲存體位置。 較新版本的 AzCopy 工具不支援將 PST 檔案匯入至 Office 365。 請務必在此步驟中的程序，從 [**透過網路上傳**] 頁面上下載 AzCopy 工具。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 使用 Office 365 組織中系統管理員帳戶的認證。
    
3. 在左窗格中，按一下 [**資料控管**，然後按一下 [**匯入**。
    
4. 在 [匯入]**** 頁面中，按一下 [移至匯入服務]****。
    
5. 在 [**匯入資料到 Office 365** ] 頁面上，按一下 [**新增工作**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**上傳電子郵件 （PST 檔案）**。
    
6. 在**網路上的檔案上傳**] 頁面的 [步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。
    
7. 顯示 URL 之後，將它複製，並將其儲存在您用來儲存其他按鍵的檔案。 請務必複製完整 URL。 
    
8. 在步驟 3 中，按一下 [**下載 Azure AzCopy 工具**來下載及安裝 Azure AzCopy 工具。 
    
9. 在快顯視窗中，按一下 [執行]**** 來安裝 Azure AzCopy 工具。 
    
    > [!IMPORTANT]
    > 請務必在預設的位置，也就是安裝 Azure AzCopy 工具`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`在執行 64 位元 Windows 電腦上。 這是因為當您在步驟 5 中執行 O365ImportTool.exe，它看起來 AzCopy 工具在此位置。 
  
10. 您已安裝 Azure AzCopy 工具之後，按一下 [**下載 Office 365 資料加密及匯入工具**。
    
11. 在快顯視窗中，按一下 [**儲存** \> O365ImportTool.zip 檔案儲存至資料夾，在本機電腦上的 [**另存為**。 
    
12. 解壓縮 O365ImportTool.zip 檔案。
    
13. 按一下 [**取消**] 以關閉 [**透過網路上傳**] 頁面。 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>步驟 5： 加密，並將您的 PST 檔案上傳至 Office 365

您已經完成步驟 1 到步驟 4 之後，就可以使用 O365ImportTool.exe 工具來加密及上傳 PST 檔案至 Office 365。 此工具會加密您的 PST 檔案再將上傳並將其儲存在 Microsoft cloud 中的 Azure 儲存體位置。 若要完成此步驟，PST 檔案必須位於貴組織的檔案共用內或檔案伺服器中。 在下列程序中，這就是所謂的 [來源目錄]。 每次您執行 O365ImportTool.exe 工具，您就可以指定不同的來源目錄。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
2. 您在步驟 4 中安裝 O365ImportTool.exe 工具的位置移至目錄。
    
3. 執行下列命令，以加密及上傳 PST 檔案至 Office 365。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    下表說明了參數與其需要的值。請注意，您在先前步驟中所取得的資訊，會在這些參數內的值中使用。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |在您的組織，其中包含將上傳至 Office 365 的 PST 檔案中指定的來源目錄。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |會指定您的 Azure RMS 服務的授權位置。 使用的值，`LicensingIntranetDistributionPointUrl`您在步驟 3 中所取得的屬性。 請務必括住的雙引號此參數值 ("")  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |會指定組織的 Azure RMS 的識別碼。 使用的值，`BPOSId`您在步驟 3 中所取得的屬性。  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |步驟 2 中指定您所取得的對稱金鑰。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |會指定是否將透過網路上傳 PST 檔案或硬碟上運送它們。 值`upload`指出上載檔案在網路上。 值`drive`代表您在硬碟上運送 Pst。  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |會指定在其中您的 PST 檔案將可上傳到; Office 365 中的目的地這是您組織的 Azure 儲存體位置。 此參數的值是由從您在步驟 4 中複製的 SAS URL 的網路上傳 URL 所組成。 請務必使用雙引號 (" ") 括住此參數的值。  <br/><br/> **提示：**（選用）您可以在 Azure 儲存體位置以上傳加密的 PST 檔案複製到指定子資料夾。 要這麼做，藉由在網路上傳 URL 中新增 （之後"ingestiondata 」) 的子資料夾位置。 第一個範例不會指定文件庫;這表示 Pst 就會上傳到 （名為*ingestiondata* ） 的根目錄的 Azure 儲存體位置。 第二個範例中的 Azure 儲存體位置的上傳 PST 檔案複製到 （名為*EncryptedPSTs* ） 的子資料夾。           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> 或  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |會指定您組織的 SAS 金鑰。 此參數的值是由 SAS 金鑰，從您在步驟 4 中複製的 SAS URL 所組成。 請注意，第一個字元的 SAS 金鑰問號 (「？ 」)。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |此選用參數指定的遞迴模式，如此 O365ImportTool.exe 工具會將位於所指定的來源目錄中的子資料夾中的 Pst 檔案複製`/srcdir:`參數。  <br/><br/> **附註：** 如果您加入此參數，在子資料夾中的 PST 檔案中會有不同的檔案路徑名稱 Azure 儲存體位置之後他們正在上傳。 您必須在您在步驟 7 中建立的 CSV 檔案中指定的實際檔案路徑名稱。           | `/recurse` <br/> |
   
    以下是 O365ImportTool.exe 工具針對各個參數使用實際值的語法範例：
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    執行此命令之後，狀態郵件會顯示 [顯示進度的加密及上傳的 PST 檔案。 最終狀態郵件會顯示成功加密及上傳檔案的總數。 
    
    > [!TIP]
    > 您已成功執行 O365ImportTool.exe 命令，並確認所有參數正確都無誤後，儲存一份命令列語法以相同的 （安全） 檔案，複製資訊的位置取得在前面的步驟。 然後您可以複製並貼上此命令在命令提示字元中每個您想要執行 O365ImportTool.exe 工具來加密及上傳 PST 檔案至 Office 365 的時間。 您可能要變更的唯一值是針對該組`/srcdir:`和`/upload-dest:`參數。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（選用）步驟 6： 檢視清單中的 PST 檔案上傳至 Office 365

為選用的步驟中，您可以安裝及使用 Microsoft Azure 存放裝置總管 （這是免費，開放原始碼工具） 來檢視您已上傳到 Azure blob 中的 PST 檔案清單。 有三個很好的原因，若要這麼做：
  
- 確認從共用的資料夾或檔案伺服器在組織中的 PST 檔案已成功上傳至 Azure blob。

- 請確認已加密的 PST 檔案。 加密的 PST 檔案有`.pfile`分機附加至 PST 檔名;例如， `pilarp.pst.pfile`。
    
- 每個 PST 檔案上傳至 Azure blob 中的確認檔案名稱 （和子資料夾路徑名稱，如果您包含一個）。 當您要在下一個步驟中建立 PST 對應檔案時，這項功能會很有幫助，因為您必須指定每個 PST 檔案的資料夾路徑名稱及檔名。 驗證這些名稱有助於減少 PST 對應檔中的潛在錯誤。
    
Microsoft Azure 存放裝置總管處於預覽狀態。 
  
 > [!IMPORTANT]
>  您無法使用 Azure 存放裝置總管上傳或修改 PST 檔案。 將 PST 檔案匯入至 Office 365 的唯一支援的方法是使用 AzCopy。 此外，您無法刪除您已上傳到 Azure blob 中的 PST 檔案。 如果您嘗試刪除 PST 檔案，您會收到沒有必要權限的相關錯誤。 請注意從 Azure 存放區域會自動刪除所有的 PST 檔案。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created. 
  
若要安裝 Azure 存放裝置總管並連線至 Azure 存放區域：
  
1. 下載並安裝[Microsoft Azure 存放裝置總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 啟動 Microsoft Azure 存放裝置總管，以滑鼠右鍵按一下左窗格中的**儲存體帳戶**，然後按一下 [**連線到 Azure 儲存體**。 
    
    ![儲存體帳戶上按一下滑鼠右鍵，然後按一下 [連線至 Azure 儲存體](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 在 [**連線到 Azure 儲存體**方塊中，在步驟 4 中貼上您取得 SAS URL，然後按一下 [**下一步**。 
    
    ![在 [連線到 Azure 儲存體頁面] 方塊中貼上 SAS URL](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. 在**連線摘要**] 頁面中，您可以檢閱連線資訊，，，然後按一下 [**連線**。 
    
5. **儲存體帳戶**] 下展開 **(服務 SAS)** 節點，然後再展開**Blob 容器**節點。 
    
6. 以滑鼠右鍵按一下 **ingestiondata**，然後按一下 [ **開啟 Blob 容器編輯器]**。
    
    ![以滑鼠右鍵按一下 ingestiondata，然後按一下 [開啟 Blob 容器編輯器]](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Azure 儲存體] 區域中，與您在步驟 5 中上傳的 PST 檔案清單會顯示。
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. 當您完成使用 Microsoft Azure 存放裝置總管時，以滑鼠右鍵按一下**ingestiondata**，，然後按一下 [中斷與 Azure 存放區域**卸離**。 否則，您會在下一次嘗試附加時收到錯誤。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>步驟 7： 建立 PST 匯入對應檔案

已加密的 PST 檔案並上傳至 Office 365 組織的 Azure 儲存體位置之後下, 一步是建立逗點分隔值 (CSV) 檔案，指定的 PST 檔案將會匯入至使用者信箱。 當您建立 PST 匯入工作時，您將會在下一個步驟提交 CSV 檔案。
  
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

    CSV 檔案的第一列或「標題列」會列出參數，PST 匯入服務將使用這些參數來匯入 PST 檔案至使用者信箱。 每個參數名稱都是以逗號分隔。 在標題列下的每一列，代表了要匯入 PST 檔案至特定信箱的參數值。 您將需要為每個要匯入至使用者信箱的 PST 檔案設定一列。 請務必在對應檔案中，使用您的實際資料來取代預留位置資料。
    
    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 
  
3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定將匯入資料到 Office 365 服務。 若要將 PST 檔案匯入使用者信箱，請使用`Exchange`。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |在您上傳 PST 檔案複製到步驟 5 中的 Azure 儲存體位置中指定的資料夾位置。  <br/>  如果您並未納入選擇性的子資料夾名稱中的網路 URL`/upload-dest:`參數在步驟 5 中將此參數保留空白 CSV 檔案中。 如果您包含的子資料夾名稱，請將其指定這個參數中。 此參數的值是區分大小寫。 無論如何，*未*包含"ingestiondata 」 中的值為`FilePath`參數。  <br/> <br/>**重要：** 檔案路徑名稱大小寫必須使用如果中的 SAS URL 中包含的選用子資料夾名稱相同案例`/upload-dest:`在步驟 5 中的參數。 例如，如果您使用`EncryptedPSTs`之子資料夾名稱在步驟 5 中，然後使用`encryptedpsts`中`FilePath`CSV 檔案中的參數，匯入 PST 檔案將會失敗。 請務必在兩個執行個體中使用相同的案例。           |(保留空白)  <br/> 或  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |指定將匯入至使用者信箱的 PST 檔案名稱。  此參數的值是區分大小寫。 因為加密 PST 檔案上傳至 Azure 儲存體位置，`.pfile`副檔名新增至 PST 檔名。 您必須將新增`.pfile`副檔名名稱的 PST 檔案在 CSV 檔案中。  <br/><br/> **重要：** CSV 檔案中的 PST 檔案名稱的情況必須已上傳至步驟 5 中的 Azure 儲存體位置的 PST 檔案相同。 例如，如果您使用`annb.pst.pfile`中`Name`參數 CSV 檔案中，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入會失敗。 請務必 PST CSV 檔案中的名稱，會使用相同的情況下，為實際的 PST 檔案。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。   <br/> 若要將 PST 檔案匯入非使用中的信箱，您必須指定此參數的信箱 GUID。 若要取得此 GUID，請執行下列 PowerShell 命令在 Exchange Online 中：`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **附註：** 在某些情況下，您可能需要多個信箱相同電子郵件地址，其中一個信箱不在作用中信箱，而其他信箱位於虛刪除 （或非使用中） 的狀態。 在這些情況下，您必須指定信箱 GUID 來唯一識別信箱，若要將 PST 檔案匯入。 若要取得此 GUID 作用中信箱，請執行下列 PowerShell 命令： `Get-Mailbox - <identity of active mailbox> | FL Guid`。 若要取得的 GUID，虛刪除 （或非使用中） 的信箱，請執行此命令`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。 其中有兩個選項：  <br/> **為 FALSE**將 PST 檔案匯入至使用者的主要信箱。  <br/> **True 是表示**將 PST 檔案匯入至使用者的封存信箱。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/><br/> **附註：** 若要將 PST 檔案匯入主要信箱位於內部部署使用者的雲端式封存信箱，只是指定此參數 **，則為 TRUE** ，並指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。           | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於的信箱 （位於相同層級的收件匣資料夾和其他預設信箱資料夾） 的根層級的新資料夾。  <br/>  如果您指定`/`，將 PST 檔案中的項目會被匯入直接在使用者的收件匣] 資料夾。  <br/>  如果您指定`/<foldername>`，將 PST 檔案中的項目將會匯入到名為的子資料夾*\<foldername\> * 。 例如，如果您使用`/ImportedPst`，項目會匯入至名為**ImportedPst**的子資料夾。 這個子資料夾將會位於使用者的收件匣] 資料夾。  <br/><br/> **提示：** 請考慮執行一些測試批次來嘗試使用這個參數，因此您可以決定要匯入 Pst 檔案的最佳資料夾位置。           |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數字值。 此參數用於從中文、 日文和韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常會使用雙位元組字元集 (DBCS) 的字元編碼。 如果這個參數不用來匯入 PST 檔案，用於信箱資料夾名稱 DBCS 的語言，將資料夾名稱是通常亂碼之後匯入它們。 如需支援的值，使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)的清單。  <br/><br/> **附註：** 如先前所述，這是選擇性的參數，您不需要加入 CSV 檔案中。 或者，您可以將它加入並將值保留空白，對一或多個資料列。           |(保留空白)  <br/> 或  <br/>  `932`（這是 ANSI/OEM 日文的程式碼] 頁面上識別碼）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>步驟 8： 在 Office 365 中建立 PST 匯入工作

最後一個步驟是在 Office 365 中的匯入服務中建立 PST 匯入工作。 如先前所述，您會將提交您在步驟 7 中建立 PST 匯入對應檔案。 匯入服務建立新的工作之後，會使用的資訊來取消在對應檔案中的加密及匯入指定的使用者信箱的 PST 檔案 （您所上傳至 Office 365 步驟 5 中）。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 使用 Office 365 組織中系統管理員帳戶的認證。
    
3. 在左窗格中，按一下 [**資料控管**，然後按一下 [**匯入**。
    
4. 在 [匯入]**** 頁面中，按一下 [移至匯入服務]****。
    
5. 在 [**匯入資料到 Office 365** ] 頁面上，按一下 [**新增工作**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**上傳電子郵件 （PST 檔案）**。
    
6. 在 [透過網路上傳檔案]**** 頁面中，按一下 [上傳檔案完成]**** 和 [我可存取對應檔案]**** 核取方塊，接著按 [下一步]****。  
    
7. 為 PST 匯入工作輸入名稱，然後按一下 [下一步]****。
    
8. 按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)來選取您在步驟 7 中建立的 PST 對應檔案。 
    
9. 在 CSV 檔案名稱出現於清單後，請選取該項目，然後按一下 [驗證]**** 來檢查您的 CSV 檔是否有錯誤。  
    
    > [!NOTE]
    > 如同先前的說明，當已加密的 PST 檔案，`.pfile`分機附加至 PST 檔名。 您必須將新增`.pfile`副檔名名稱的 PST 檔案在 CSV 檔案中。 如果您沒有將會失敗的驗證的 CSV 檔案。 
  
    CSV 檔案必須成功通過驗證，才能建立 PST 匯入工作。如果驗證失敗，在 [狀態]**** 欄內按一下 [無效]**** 連結。您的 PST 匯入對應檔案複本已開啟，並針對檔案中每一列有問題項目提供錯誤訊息。 
    
10. 當 PST 對應檔案驗證成功時，請檢閱條款和條件文件，然後按一下 [核取方塊]。
    
11. 按一下 [完成]**** 來提交工作。 
    
    工作會顯示在 [**匯入資料到 Office 365** ] 頁面上的 PST 匯入工作清單中。 
    
12. 選取工作]，然後按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中顯示的狀態資訊。 
    
13. 在詳細資料窗格中，按一下 [檢視詳細資料]****，便可針對選取的工作取得最新的狀態。 
 
## <a name="more-information"></a>詳細資訊

- 為什麼 PST 檔案匯入至 Office 365？
    
  - 它是一個好方法來將貴組織的電子郵件移轉到 Office 365。
    
  - 它可讓您透過下列方式協助解決組織的法務遵循需求︰
    
  - 啟用封存信箱以提供使用者額外的信箱儲存空間。
    
  - 保存信箱以保留內容。
    
  - 使用 Microsoft eDiscovery 工具來搜尋信箱中的內容。
    
  - 使用保留原則來控制信箱內容要保留多久。
    
  - 搜尋 Office 365 稽核記錄的信箱相關的事件。
    
  - 其有助於防止資料遺失。 PST 檔案匯入到 Office 365 信箱的繼承而不是將資料儲存在使用者電腦上的 Exchange Online 的高可用性功能。
    
  - 資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。
    
- 以下是範例的索引鍵、 識別碼及在步驟 2、 3 和 4 中所取得的 Url。 這個範例也包含執行中 O365ImportTool.exe 工具來加密及上傳 PST 檔案至 Office 365 的命令語法。 請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。
    
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

- 如先前所述，Office 365 匯入服務會開啟 PST 檔案匯入至信箱後，（如期的持續時間） 設定保留功能。 這表示*RentionHoldEnabled*屬性設為`True`使其不會處理指派給信箱的保留原則。 這可以讓信箱擁有者時間來管理新匯入郵件藉由防止刪除或封存原則刪除或封存較舊的郵件。 若要管理此保留功能，可採取一些步驟如下： 
    
  - 在一段時間之後, 您可以關閉保留功能來執行`Set-Mailbox -RetentionHoldEnabled $false`命令。 如需相關指示，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/p/?LinkId=544749)。
    
  - 您可以設定保留功能，讓未來某些日期上關閉。 您執行這項操作藉由執行`Set-Mailbox -EndDateForRetentionHold <date>`命令。 例如，假設今天的日期是 2016 年 6 月 1 日，而您想在 30 天中關閉保留功能，您可以執行下列命令： `Set-Mailbox -EndDateForRetentionHold 7/1/2016`。 在此案例中，您會使*RentionHoldEnabled*屬性設定為`True`。 如需詳細資訊，請參閱[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以變更的保留原則，以便更舊版本都已匯入的項目不會立即刪除或移至使用者的封存信箱指派給信箱的設定。 例如，您無法延長刪除或封存原則指派給信箱的保留天數。 在此案例中，您會關閉保留在信箱上變更保留原則的設定之後。 如需詳細資訊，請參閱 < <b0>Set up Office 365 組織中信箱的封存和刪除原則</b0>。
