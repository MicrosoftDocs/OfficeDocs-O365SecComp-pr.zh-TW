---
title: 使用客戶金鑰控制 Office 365 中的資料
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: 了解如何設定客戶金鑰 for Office 365 的 Exchange Online、 Skype Business、 SharePoint Online 和 OneDrive for Business。與客戶金鑰您控制您組織的加密金鑰及使用方式來加密的 Microsoft 資料中心的靜態資料的 Office 365，則設定。
ms.openlocfilehash: a14a213951bc87e4106e150c88c6b1461a5e685e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218753"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>使用客戶金鑰控制 Office 365 中的資料

與客戶金鑰您控制組織的加密金鑰並使用這些加密 Microsoft 資料中心的靜態資料的 Office 365，則設定。靜態資料包括從 Exchange Online 和 Skype 會儲存在信箱和 SharePoint Online 中儲存的檔案中的企業版及 OneDrive for Business 的資料。
  
您必須設定 Azure 才可以使用 Office 365 的客戶機碼。本主題說明您必須遵循以建立並設定必要的 Azure 資源的步驟，然後步驟安裝 Office 365 中的客戶索引鍵設定。Azure 安裝程式完成之後，您可以決定哪個原則，與因此哪些機碼，將指派給信箱與您組織中的檔案。信箱與檔案的未指派的原則將會使用加密原則控制及管理 microsoft。客戶機碼的詳細資訊或的一般概觀，請參閱[Office 365 常見問題集的客戶機碼](service-encryption-with-customer-key-faq.md)。
  
> [!IMPORTANT]
> 我們強烈建議您遵循此主題中的最佳作法。這些被呼叫所佔的**提示**以及**重要**。客戶機碼可讓您控制其範圍可大為整個組織的根加密金鑰。這表示與這些機碼所產生的錯誤造成廣泛的影響，而且可能會造成服務中斷或無法挽回的資料損失。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>開始之前客戶機碼設定
<a name="Beforeyoustart"> </a>

您開始之前，請確認您具有適當的授權您的組織。在 Office 365 中的客戶機碼是 Office 365 E5 或進階規範 SKU 中提供。
  
然後，了解的概念和本主題中的程序，您應該檢閱[Azure 機碼存放庫](https://azure.microsoft.com/en-us/documentation/services/key-vault/)的文件。此外，熟悉使用 Azure，例如[租用戶](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)中的條款。
  
若要提供意見反應客戶金鑰，包括文件，將您的想法、 建議和觀點 （英文） 傳送至 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>設定 Office 365 的客戶機碼的概觀 （英文)
<a name="Overview"> </a>

若要設定客戶機碼所完成這些工作。本主題的其餘部分提供詳細的說明每一項工作或取出程序中的每個步驟的詳細資訊連結。
  
**在 Azure 和 Microsoft FastTrack：**
  
您將透過遠端連線到 Azure PowerShell 完成大部分的這些工作。為了獲得最佳結果，使用版本 4.4.0 或更新版本的 Azure PowerShell。
  
- [建立兩個新的 Azure 訂閱](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [註冊使用的必要項目保留期間的 Azure 訂閱](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    註冊可能需要一至五個工作天。
    
- [送出要求啟用 Office 365 的客戶金鑰](controlling-your-data-using-customer-key.md#FastTrack)
    
    一旦您已經建立兩個新的 Azure 訂閱，您將需要適當的客戶金鑰優惠要求送出完成裝載於 Microsoft FastTrack 入口網站的 web 表單。**FastTrack 小組不會提供客戶機碼。只允許您送出表單，並協助客戶鍵追蹤相關提供我們使用 FastTrack 入口網站的 office**。
  
一旦您已送出客戶金鑰產品項目、 Microsoft 檢閱您的要求，並通知您時可以繼續進行安裝工作的其餘部分。此程序可能需要最多可以有五個工作天。
    
- [在每一個訂閱中建立 premium Azure 機碼存放庫](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [權限指派給每個主要的存放庫](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [啟用，然後確認可以在您的主要保存庫虛刪除](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [索引鍵新增至每個主要存放庫是藉由建立或匯入金鑰](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [檢查您的機碼的復原層級](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [備份 Azure 的主要存放庫](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [驗證 Azure 機碼存放庫組態設定](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [取得每個 Azure 機碼存放庫機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**在 Office 365：**
  
Exchange Online 和 Skype for Business:
  
- [建立用於資料加密原則 (DEP) 與 Exchange Online 和 Skype for Business](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [DEP 指派給信箱](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [驗證信箱加密](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online 和 OneDrive for Business:
  
- [建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [驗證的群組網站和小組網站、 OneDrive for Business 的加密](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure 機碼存放庫和 Microsoft FastTrack 客戶機碼中完成工作
<a name="AzureSteps"> </a>

若要設定 Office 365 的客戶金鑰完成 Azure 機碼存放庫中的這些工作。您必須完成下列步驟，不論是否您想要設定客戶機碼的 Exchange Online 和 Skype 商務或 SharePoint Online 以及 OneDrive for Business 或 Office 365 中的所有受支援服務。
  
### <a name="create-two-new-azure-subscriptions"></a>建立兩個新的 Azure 訂閱
<a name="Create2newsubs"> </a>

兩個 Azure 訂閱所需的客戶機碼。最佳作法是 Microsoft 建議您與客戶機碼建立新的 Azure 訂閱使用。Azure 機碼存放庫機碼僅可以授權中相同的 Azure Active Directory (AAD) 租用戶的應用程式，您必須建立新的訂閱使用相同的 Azure AD 租用戶搭配 Office 365 組織要指派 DEPs。例如，使用您在 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶。如需詳細步驟，請參閱[註冊為組織的 Azure](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 客戶金鑰需要兩個機碼針對每個資料加密原則 (DEP)。若要達到此目的，您必須建立兩個 Azure 訂閱。最佳作法是 Microsoft 建議您必須在每一個訂閱中設定一個金鑰貴組織的個別成員。此外，這些 Azure 訂閱應該只用於 Office 365 的管理加密金鑰。這會保護您的組織以防您運算子的其中一個意外、 刻意，或惡意刪除或否則 mismanages 他們是負責的按鍵。<br/> 我們建議您設定新的 Azure 訂閱只用於與客戶金鑰管理 Azure 機碼存放庫資源使用。有不受實用的 Azure 您可以為您的組織建立的訂閱數限制。遵循這些最佳作法將最小化人工錯誤的影響同時協助管理客戶機碼所使用的資源。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>送出要求啟用 Office 365 的客戶金鑰
<a name="FastTrack"> </a>

一旦您已經完成的 Azure 的步驟，您將需要產品項目中提交要求[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。一旦您已送出要求透過 FastTrack 的入口網站、 Microsoft 驗證 Azure 機碼存放庫組態資料與連絡人您所提供的資訊。您在貴組織的授權主管有關產品項目表單所做的選擇是要徑和所需完成的客戶金鑰註冊。您在表單中選取您組織的主管會用來確保撤銷並終結客戶索引鍵資料加密原則搭配使用的所有按鍵任何要求的確實性。您需要執行一次此步驟才能啟用 Exchange Online 和 Skype 的商務涵蓋範圍與第二次啟動客戶機碼的 SharePoint Online 和 OneDrive for Business 的客戶金鑰。
  
若要送出產品啟用客戶金鑰項目，請完成下列步驟：
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶登入[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。
    
2. 一旦您的登入，瀏覽至**儀表板**。
    
3. 選擇**提供**，並查看目前提供的清單。
    
4. 選擇**了解更多**的產品套用至您的項目： 
    
  - **Exchange Online 和 Skype for Business:****Exchange 的客戶金鑰**優惠上選擇 [**了解更多**]。 
    
  - **SharePoint Online 和 OneDrive for Business:** 選擇**更了解**在**SharePoint 和 OneDrive for Business 的客戶金鑰**產品項目。 
    
5. **提供詳細資料**] 索引標籤上選擇 [**建立要求**。
    
6. 填寫所有適用的詳細資訊與產品項目表單上要求的資訊。請特別注意您組織的哪些主管的選擇您要授權核准永久並指出損毀的加密金鑰及資料。一旦您已經完成表單，選擇 [**送出**]。
    
    此程序可能需要最多可以有五個工作天後已經被 Microsoft 通知您的要求。
    
7. 繼續前往下列必要項目保留期間] 區段。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>註冊使用的必要項目保留期間的 Azure 訂閱
<a name="RegisterSubsforMRP"> </a>

暫時性或永久性的遺失根加密金鑰可以是非常中斷或甚至是災難性服務作業，而且可能會導致資料遺失。此原因的客戶金鑰搭配使用的資源需要強式保護。客戶金鑰搭配使用的所有 Azure 資源提供保護機制以外的預設設定。Azure 訂閱可以標記或登錄會防止即時和冒用取消的方式。這被稱為註冊的必要項目保留期間。為必要項目保留期間註冊 Azure 訂閱所需的步驟需要與 Office 365 小組共同作業。此程序可能需要一至五個工作天。先前，這是有時稱為 「 無法取消"。
  
再連絡 Office 365 小組，您必須執行下列步驟每個 Azure 訂閱搭配客戶機碼：
  
1. 登入您使用 Azure PowerShell 的 Azure 訂閱。指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
2. 執行登錄 AzureRmProviderFeature cmdlet 以註冊您的訂閱若要使用的必要項目保留期間。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. 請連絡 Microsoft 以已完成的程序。SharePoint 和 OneDrive for Business 小組、 連絡[spock@microsoft.com](mailto:spock@microsoft.com)。Exchange Online 與 Skype for Business，請連絡[exock@microsoft.com](mailto:exock@microsoft.com)。服務層級協議 (SLA) 完成此程序的五個工作天後 Microsoft 通知 （並之後驗證） 的已註冊您的訂閱若要使用的必要項目保留期間。在您的電子郵件中包括下列：
    
    **主旨**： 客戶金鑰\<*您的租用戶完整網域名稱*\> 
    
    **內文**： 要具有必要項目保留期間完成的訂閱識別碼。 
    
4. 一旦您會收到通知 microsoft 註冊已完成，確認您註冊的狀態執行 Get AzureRmProviderFeature 指令程式，如下所示：
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. 檢查**登錄 State**屬性取得 AzureRmProviderFeature 指令程式會傳回的值為**Registered**，執行下列命令以完成程序：
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每一個訂閱中建立 premium Azure 機碼存放庫
<a name="CreateKeyVault"> </a>

中[快速入門 Azure 機碼存放庫](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)，這會引導您安裝並啟動 PowerShell 的 windows Azure、 連線至您的 Azure 訂閱、 建立資源群組，及建立主要存放庫中所記載的步驟來建立主要存放庫資源群組。
  
當您建立主要存放庫時，您必須選擇 SKU： 標準版或 Premium。標準 SKU 允許以使用-有無硬體安全性模組 (HSM) 金鑰保護-軟體保護 Azure 機碼存放庫機碼並 Premium SKU 允許 Hsm 用於金鑰儲藏室機碼的保護。客戶金鑰接受主要保存庫使用任一 SKU，但是 Microsoft 強烈建議您使用僅限 Premium SKU。使用任一類型的機碼的作業成本是相同，因此成本中唯一的不同是每月每個 HSM 保護索引鍵的成本。如需詳細資訊，請參閱[定價機碼存放庫](https://azure.microsoft.com/pricing/details/key-vault/)。 
  
> [!IMPORTANT]
> 用於實際執行資料的 Premium SKU 主要保存庫和 HSM 受保護的機碼並僅可用於標準 SKU 主要保存庫和機碼為了測試及驗證。 
  
每個 Office 365 服務用以客戶機碼，建立主要存放庫中每個您所建立的兩個 Azure 訂閱。例如 Exchange Online 與 Skype 僅商務或 SharePoint Online 和 OneDrive for Business 僅，您會建立只能有一組的保存庫。若要啟用 Exchange Online 和 SharePoint Online 客戶金鑰，您會建立兩個配對的主要保存庫。
  
使用主要保存庫，以反映您將關聯將保存庫 DEP 的預定的用法的命名慣例。請參閱下方的命名慣例建議最佳作法一節。
  
建立每個資料加密原則保存庫個別、 配對集。Exchange Online 的資料加密原則範圍是選擇您將原則指派給信箱時。信箱可以有一個原則指派，而您可以建立多達了大約 50 個原則。SharePoint Online 的原則範圍是所有地理位置或地理位置中組織內的資料。
  
主要保存庫的建立也需要 Azure 資源群組，請的建立自主要保存庫需要儲存容量 （雖然很小） 和機碼存放庫記錄，如果啟用，也會產生儲存的資料。最佳作法是 Microsoft 建議使用不同的系統管理員管理每個資源] 群組中，以使用系統管理員將管理相關的所有客戶機碼資源的一組對齊管理。
  
> [!IMPORTANT]
> 若要提高可用性，您重要保存庫應該在您的 Office 365 服務接近的地區。例如，如果您的 Exchange Online 組織位於 「 北美地區 」，置於您重要保存庫 「 北美地區 」。如果您的 Exchange Online 組織位於歐洲、 置於 Europe 您重要保存庫。<br/>使用主要保存庫，常見的前置詞，包括使用的縮寫和主要儲藏室和機碼的範圍 (例如，如 Contoso SharePoint service 將保存庫所在的 「 北美地區 」，可能兩個名稱為 Contoso O365SP-NA VaultA1 和Contoso-O365SP-NA-VaultA2。存放庫名稱為全域唯一字串，內 Azure，所以您可能需要以防其他 Azure 客戶同時已經宣告所要的名稱會嘗試變化的您想要的名稱。年 7 月 2017年存放庫名稱無法變更，所以最佳作法是已安裝的書寫的計畫和確認正確地執行計劃時使用的第二個的人員。<br/>請儘可能建立您保存庫非配對地區中。成對的 Azure 區域 （英文） 提供服務的失敗網域間的高可用性。因此，區域的配對可以是視為彼此的備份區域。這表示放在一個區域中的 Azure 資源自動取得容錯透過成對的區域。基於此選擇兩個保存庫所在的區域是只有兩個區域的可用性總共正在使用的配對的表示 DEP 中所使用的區域。大部分的地理位置只有兩個區域，讓它尚未可能選取非配對區域 （英文）。請儘可能選擇用於 DEP 將兩個保存庫中非成對的兩個地區這可藉由總共四個區域的可用性而獲益。如需詳細資訊，請參閱[商務持續力和災害復原 (BCDR)： Azure 配對區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)區域成對的目前清單。 
  
### <a name="assign-permissions-to-each-key-vault"></a>權限指派給每個主要的存放庫
<a name="KeyVaultPerms"> </a>

每個主要的存放庫，您必須定義三個不同的實作根據客戶機碼權限。例如，您將需要定義一組權限的下列各項：
  
- **機碼存放庫系統管理員**將執行的主要的儲藏室日常管理您的組織。這些工作包括備份、 建立、 取得、 匯入] 清單中，並還原。 
    
    > [!IMPORTANT]
    > 指派給主要儲藏室系統管理員的權限集不包括權限可以刪除索引鍵。這是刻意及重要的作法。刪除加密金鑰不通常是，由於所以永久執行終結資料。最佳作法是不要不授與此權限主要儲藏室系統管理員預設。而此齊備的重要儲藏室參與者並只將其指派給短期為基礎的系統管理員瞭解後果清楚了解之後。 
  
    若要將這些權限指派給 Office 365 組織中的使用者，登入您使用 Azure PowerShell 的 Azure 訂閱。指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
- 執行設定 AzureRmKeyVaultAccessPolicy 指令程式來指派必要權限。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  例如：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- **機碼存放庫參與者**可以變更 Azure 機碼存放庫的權限本身擷取。您需要變更這些權限如下員工離開或加入您的小組，或在極罕見的情況下的按鍵地窖管理員合法需要刪除或還原金鑰的權限。這組重要儲藏室參與者必須被授與您主要的存放庫的**參與者**角色的設定。您可以使用 Azure 資源管理員指派此角色。如需詳細步驟，請參閱[Use Role-Based 存取控制來管理 Azure 訂閱資源的存取權](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。建立訂閱的系統管理員存取此隱含，以及指派給參與者角色的其他管理員的能力。
    
- 如果您想要使用與 Exchange Online 和 Skype 的客戶金鑰 for Business，您需要使用 Exchange Online 和 Skype 代表鍵儲藏室 for Business 的 Office 365 授與權限。同樣地，如果您想要使用客戶金鑰 SharePoint Online 以及 OneDrive for Business，您需要新增使用主要儲藏室代表 SharePoint Online 和 OneDrive for Business 的 Office 365 的權限。若要授與權限至 Office 365、 執行**組 AzureRmKeyVaultAccessPolicy**指令程式使用下列語法： 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    其中：
    
  - *vaultname*是您建立主要存放庫的名稱。 
    
  - Exchange Online 與 Skype for Business，取代與*Office 365 應用程式識別碼*`00000002-0000-0ff1-ce00-000000000000`
    
  - SharePoint Online 和 OneDrive for Business，將與*Office 365 應用程式識別碼*`00000003-0000-0ff1-ce00-000000000000`
    
  範例： 設定 Exchange Online 和 Skype for Business 的權限：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  範例： 設定 SharePoint Online 和 OneDrive for Business 的權限
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>啟用，然後確認可以在您的主要保存庫虛刪除
<a name="SoftDelete"> </a>

當您可以快速地復原您的機碼時，就可能無法體驗擴充的服務中斷因為意外或惡意刪除機碼。您必須啟用此設定，稱為柔刪除，才可以使用您的金鑰與客戶機碼。啟用軟體刪除可讓您不必從備份中還原刪除的 90 天內復原機碼或保存庫。
  
若要啟用軟體刪除上您重要保存庫，完成下列步驟：
  
1. 登入您使用 Windows Powershell 的 Azure 訂閱。指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。
    
2. 執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault)指令程式。在這個範例中， *vaultname*是您要為其啟用虛刪除主要存放庫的名稱： 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. 確認虛刪除已針對重要儲藏室執行**Get AzureRmKeyVault**指令程式。虛刪除的設定是否正確的主要儲藏室、 虛刪除已啟用吗？屬性會傳回**True**的值： 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>索引鍵新增至每個主要存放庫是藉由建立或匯入金鑰
<a name="AddKeystoKeyVault"> </a>

有兩種方式將機碼新增至 Azure 機碼存放庫 ；您可以直接在機碼存放庫中建立機碼或您可以匯入金鑰。直接在機碼存放庫中建立機碼是較不複雜的方法，而匯入金鑰可讓您控制如何產生金鑰總數。
  
若要直接在您主要的存放庫中建立機碼，如下執行[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)指令程式： 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：
  
-  *vaultname*是您要建立的機碼主要存放庫的名稱。 
    
-  *keyname*是您要給新機碼的名稱。 
    
    > [!TIP]
    > 如前文所述的重要保存庫使用類似的命名慣例機碼的名稱。如此一來，顯示機碼名稱的工具，在字串自我描述。 
  
- 如果您想要保護 HSM 鍵，請確定您指定**HSM**為_目的地_參數值，否則指定**軟體**。
    
例如，
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

若要直接將您主要的存放庫，匯入金鑰，您需要有 Thales nShield 硬體安全性模組。
  
有些組織偏好這種方法來建立其機碼，與此 provenance 方法也會提供下列：
  
- 用於匯入工具集包括從 Thales 金鑰 Exchange 索引鍵 (KEK) 用來加密您產生的金鑰不是可匯出的審查及產生內已由 Thales 生產正版 HSM。
    
- 工具集包含從 Thales Azure 機碼存放庫安全性 world 也已產生在生產由 Thales 正版 HSM 審查。此審查證明您 Microsoft 也使用正版 Thales 硬體。
    
檢查與您決定是否需要上述 attestations 的安全性群組。建立主要內部部署和匯入到您的主要存放庫的詳細步驟，請參閱[如何產生及傳輸 HSM 保護 Azure 機碼存放庫的機碼](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。使用 Azure 指示每一個主要的存放庫中建立機碼。
  
### <a name="check-the-recovery-level-of-your-keys"></a>檢查您的機碼的復原層級
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 需要 Azure 機碼存放庫訂閱設為不要取消及客戶機碼所使用的按鍵已啟用的虛刪除。您可以透過查看 [您的機碼中的 [復原層級加以確認。
  
若要檢查 Azure PowerShell 中的索引鍵的復原層級，如下所示執行 Get AzureKeyVaultKey 指令程式：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

如果_復原層級_屬性會傳回**發生無法復原 + ProtectedSubscription**值以外，您必須以檢閱本主題，並確定您已遵循所有訂閱置於 [不要取消清單中的步驟及您必須在每個您重要保存庫上啟用的虛刪除。
  
### <a name="backup-azure-key-vault"></a>備份 Azure 的主要存放庫
<a name="BackupAzureKeyVaultkeys"> </a>

緊接在建立或任何變更機碼，執行備份與儲存區的線上及離線的備份複本。離線複本應該不會連線至任何網路，例如在實體安全或商業儲存設備。備份至少一個複本應儲存在會在發生災害時可以存取的位置。備份 blob 是應該金鑰儲藏室機碼是永久移除或否則呈現 [無法正常運作還原主要材料的唯一方法。外部 Azure 機碼存放庫，且已匯入至 Azure 機碼存放庫的機碼不能限定備份因為具有外部索引鍵不存在的中繼資料時所需的客戶使用按鍵的按鍵。僅取自 Azure 機碼存放庫的備份可搭配還原作業的客戶機碼。因此，很重要的 Azure 機碼存放庫備份進行之後金鑰已上傳或建立。
  
若要建立 Azure 機碼存放庫機碼的備份，以下列方式執行[備份 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet：
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

請確定您的輸出檔案使用尾碼`.backup`。
  
此指令程式所產生的輸出檔案加密，而且不能使用外部 Azure 機碼存放庫。可以只以拍攝備份時的 Azure 訂閱還原備份。
  
> [!TIP]
> 輸出檔，選擇您的存放庫名稱和機碼名稱的組合。這會使檔案名稱自我描述。它也會確保備份的檔案名稱執行動作不會發生衝突。 
  
例如：
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>驗證 Azure 機碼存放庫組態設定
<a name="Validateconfiguration"> </a>

執行驗證之前使用機碼中 DEP 是選擇性的但強烈建議。特別是，如果您使用步驟來設定您的機碼和保存庫本主題所述的錯誤以外，您應該驗證 Azure 機碼存放庫資源的健康狀況之前設定客戶金鑰。
  
若要確認您的機碼已啟用 get、 wrapKey，以及 unwrapKey 作業：
  
執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)指令程式，如下所示： 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

在輸出中尋找適當的存取原則與 Exchange Online 的身分識別 (GUID) 或 SharePoint Online 的身分識別 (GUID)。所有三個以上的權限必須是底下都顯示的權限機碼。
  
如果存取原則設定不正確，請執行組 AzureRmKeyVaultAccessPolicy 指令程式，如下所示：
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，用於 Exchange Online 和 Skype for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，用於 SharePoint Online 和 OneDrive for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

若要確認到期沒有為您執行[Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)指令程式，如下所示的機碼設定： 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

過期的索引鍵不能使用客戶金鑰並嘗試使用過期的索引鍵的作業會失敗，並可能造成服務中斷。我們強烈建議客戶金鑰搭配使用的按鍵沒有到期。設定，則無法移除，但可以變更為不同的日期之後到期日期。如果金鑰必須使用已到期設定到期日值變更為 12/31/9999。除了比 12/31/9999 不會將 Office 365 驗證傳遞機碼以到期設定日期。
  
若要變更已設定為 12/31/9999 以外的任何數值到期，以下列方式執行[組 AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet： 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不在您使用與客戶機碼的加密金鑰設定到期日。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>取得每個 Azure 機碼存放庫機碼的 URI
<a name="GetKeyURI"> </a>

一次完成設定您的主要保存庫 Azure 中的所有步驟並新增機碼，執行下列命令以取得每個主要的存放庫中的機碼的 URI。您將需要使用這些 Uri 當您建立及更新版本、 指派每個 DEP 因此請儲存此資訊安全的位置。請記得執行此命令一次的每個主要的存放庫。
  
在 Azure PowerShell：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365： 設定 Exchange Online 和 Skype for Business 的客戶機碼
<a name="AzureSteps"> </a>

開始之前，請確定您已完成工作所需設定 「 Azure 機碼存放庫。請參閱[在 Azure 機碼存放庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)的資訊。 
  
若要設定客戶機碼的 Exchange Online 和 Skype for Business，必須從遠端連線至 Exchange Online 使用 Windows PowerShell 來執行這些步驟。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>建立用於資料加密原則 (DEP) 與 Exchange Online 和 Skype for Business
<a name="CreateDEP4EXOSkype"> </a>

DEP 是一組儲存在 Azure 機碼存放庫中的機碼的相關聯。您可以指派 DEP 給 Office 365 中的信箱。Office 365 接著會使用該原則中所識別的按鍵來加密信箱。若要建立 DEP，您需要您稍早取得金鑰儲藏室 Uri。請參閱指示[取得每個 Azure 機碼存放庫機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
請記得 ！當您建立 DEP 時，您會指定兩個位於兩個不同的 Azure 金鑰保存庫中的索引鍵。請確定這些機碼位於兩個不同的 Azure 區域以確保地理冗餘。
  
若要建立 DEP 請遵循下列步驟：
  
1. 在您的本機電腦上使用的工作或學校 Office 365 組織中開啟 Windows PowerShell 並執行下列命令的 [[連線至 Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)中具有全域系統管理員權限。 
    
   ```
   $UserCredential = Get-Credential
   ```

2. 在 Windows PowerShell 認證要求] 對話方塊中，輸入您的工作或學校帳戶資訊、 按一下 [**確定**] 並再輸入下列命令。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 執行下列命令。
    
   ```
   Import-PSSession $Session
   ```

4. 若要建立 DEP，使用新增 DataEncryptionPolicy 指令程式輸入下列命令。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：
    
   -  *Policyname 就*是您想要使用之原則的名稱。名稱不得包含空格。例如，USA_mailboxes。 
    
   -  *PolicyDescription*是可協助您記住此原則會針對原則的使用者易記描述。您可以在 [描述包含空格。例如，根中 USA 和其領域之信箱的索引鍵。 
    
   -  *KeyVaultURI1*是原則中的第一個索引鍵的 URI。例如， https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。 
    
   -  *KeyVaultURI2*是原則中的第二個機碼的 URI。例如， https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。分隔兩個逗號及空間 Uri。 
    
   範例：
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>DEP 指派給信箱
<a name="assignDEPtomailbox"> </a>

使用 Set-mailbox 指令程式將 DEP 指派給信箱。Office 365 一旦您指派原則時，可以使用 DEP 中指定的金鑰加密信箱
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中*MailboxIdParameter*會指定信箱。如需 Set-mailbox 指令程式的詳細資訊，請參閱[Set-mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。
  
### <a name="validate-mailbox-encryption"></a>驗證信箱加密
<a name="validatemailboxencryption"> </a>

加密信箱可能需要一些時間。第一次原則指派、 信箱也之前必須完成從一個資料庫移動至另一個服務可以加密信箱。我們建議您等待 72 小時嘗試之後變更 DEP 或第一次您 DEP 信箱指派驗證加密之前。
  
使用 Get-mailboxstatistics 指令程式來決定是否加密信箱。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果未加密之信箱 IsEncrypted 屬性會傳回的值**則為 true**如果加密信箱及的值為**false** 。 

完成信箱移動的時間取決於您將指派 DEP 第一次的信箱數目時的信箱大小。如果尚未從一週後加密信箱指派 DEP、 使用 New-moverequest 指令程式起始之未加密的信箱的信箱移動。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365： 設定 SharePoint Online 和 OneDrive for Business 的客戶機碼
<a name="AzureSteps"> </a>

開始之前，請確定您已完成工作所需設定 「 Azure 機碼存放庫。請參閱[在 Azure 機碼存放庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)的資訊。 
  
若要設定客戶機碼的 SharePoint Online 和 OneDrive for Business，必須從遠端連線至 SharePoint Online Windows powershell 來執行這些步驟。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置
<a name="CreateDEP4SPOODfB"> </a>

DEP 是一組儲存在 Azure 機碼存放庫中的機碼的相關聯。您可以將 DEP 套用至所有的單一地理位置，也稱為 「 地理位置資料。如果您使用 Office 365 的多重地理位置功能 （目前 Preview) 中，您可以建立一個 DEP 個別地理位置。如果您不使用多個地理位置，您可以在 Office 365 中建立一個 DEP 搭配 SharePoint Online 和 OneDrive for Business。Office 365 接著會使用 DEP 中所識別的按鍵來加密您的地理位置中的資料。若要建立 DEP，您需要您稍早取得金鑰儲藏室 Uri。請參閱指示[取得每個 Azure 機碼存放庫機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
請記得 ！當您建立 DEP 時，您會指定兩個位於兩個不同的 Azure 金鑰保存庫中的索引鍵。請確定這些機碼位於兩個不同的 Azure 區域以確保地理冗餘。
  
若要建立 DEP，您需要使用 Windows PowerShell 遠端連接至 SharePoint Online。
  
1. 在您的本機電腦上使用的工作或學校 Office 365 組織中[連線至 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)中具有全域系統管理員權限。
    
2. Microsoft SharePoint Online 管理命令介面中，執行[註冊 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx)指令程式，如下所示： 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   當您註冊 DEP 時，地理位置中的資料在上一開始會加密。這可能需要一些時間。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>驗證的群組網站和小組網站、 OneDrive for Business 的加密
<a name="validateencryptionSPO"> </a>

您可以檢查的加密狀態執行 Get SPODataEncryptionPolicy 指令程式，如下所示：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的輸出包含：
  
- 主索引鍵的 URI。
    
- 次要機碼的 URI。
    
- 地理位置加密狀態。狀態可能包括：
    
  - **取消登錄：** 尚未套用客戶金鑰加密。 
    
  - **登錄：** 已套用客戶金鑰加密及加密正在您的檔案。如果您地理位置是在此狀態下，您將也會顯示資訊上以便您可以監視加密進度何種百分比地理位置中的網站皆已完成。 
    
  - **登錄：** 套用客戶金鑰加密和已加密的所有網站中的所有檔案。 
    
  - **循環：** 主要 roll 正在進行中。如果您地理位置是在此狀態下，您將也會顯示資訊上何種百分比的網站，讓您可以監視進度完成的主要聯播 （英文） 作業。 
    
## <a name="managing-customer-key-for-office-365"></a>管理 office 365 的客戶金鑰
<a name="ManageCustomerKey"> </a>

您針對 Office 365 設定客戶金鑰之後，您可以執行下列其他管理工作。
  
- [還原 Azure 機碼存放庫機碼](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [啟用或旋轉和客戶金鑰使用 Azure 機碼存放庫中的索引鍵](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [管理主要存放庫的權限](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [決定指派給信箱 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>還原 Azure 機碼存放庫機碼
<a name="RestoreAzureKeyVaultKeys"> </a>

在執行還原、 之前使用虛刪除所提供的復原功能。客戶金鑰搭配使用的所有索引鍵所需已啟用的虛刪除。虛刪除 bot 資源回收筒，並允許復原多達 90 天而不需要還原。超重度或不尋常的情況，例如金鑰或金鑰儲藏室中斷時應該只需要還原。如果您必須使用客戶金鑰還原金鑰使用 Azure PowerShell 中執行還原 AzureKeyVaultKey 指令程式，如下所示：
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

例如：
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果主要存放庫中已經存在具有相同名稱的機碼，將會失敗的還原作業。還原 AzureKeyVaultKey 還原所有的主要版本和所有中繼資料包括機碼名稱的索引鍵。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>啟用或旋轉和客戶金鑰使用 Azure 機碼存放庫中的索引鍵
<a name="RollCKkey"> </a>

啟用機碼不需要透過其中一個 Azure 機碼存放庫或客戶機碼。此外，使用 HSM 受到保護的機碼是幾乎很難危害。即使根機碼所擁有的惡意動作項目中沒有使用解密的資料，因為只有 Office 365 的程式碼知道如何使用它的任何可行的方法。不過，啟用金鑰客戶鍵所支援。
  
> [!CAUTION]
> 僅能復原清除技術原因存在於或規範需求以指定您必須將索引鍵時與客戶金鑰一起使用的加密金鑰。此外，不要刪除任何按鍵或已與原則產生關聯。當您首次機碼、 有將內容加密與先前的符號。例如時使用中的信箱，將會重新加密常見問題，不在作用中已中斷連線，但已停用信箱仍可能會加密與先前的符號。SharePoint Online 執行備份的內容還原及復原用途，因此仍可能使用較舊的機碼封存的內容。<br/> 若要確保資料的安全，SharePoint Online 會允許設為正在進行一次不超過一個索引鍵首次作業。如果您想要在主要儲藏室彙兩者的機碼，則需要等待第一項重要聯播 （英文） 作業完全完成。我們建議是在不同的時間間隔錯開主要聯播 （英文） 作業使這不是發生問題。 
  
當您首次金鑰時，您要求的現有的索引鍵的新版本。若要要求新版本的現有的索引鍵、 您可以使用同一個指令程式[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)，具有相同的語法您用以最初建立的機碼。
  
例如：
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

在這個範例中，由於金鑰名為**Contoso-O365EX-NA-VaultA1-Key001**已經存在於**Contoso O365EX-NA VaultA1**存放庫將會建立新的主要版本。作業將新的主要版本。這項作業會保留主要索引鍵的版本歷程記錄中的舊版使仍進行解密先前與該金鑰加密資料。一旦您完成啟用關聯 DEP 任意鍵，接著您必須執行額外的指令程式來確保客戶金鑰一開始會使用新金鑰。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>啟用 Exchange Online 和 Skype for Business 首次或旋轉 Azure 機碼存放庫中的機碼之後使用新的金鑰

當您首次任一 DEP 相關聯的 Azure 機碼存放庫按鍵搭配 Exchange Online 和 Skype for Business，您必須執行下列命令來更新 DEP 並啟用 Office 365 開始使用新的金鑰。
  
若要指示客戶機碼，以使用新的金鑰來加密 Office 365 中的信箱，如下所示執行組 DataEncryptionPolicy cmdlet：
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

48 小時內使用此原則加密的作用中信箱會成為與更新的索引鍵關聯。使用 ＜ [Determine DEP 指派給信箱](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)的步驟來查看信箱的 DataEncryptionPolicyID 屬性的值。此屬性的值會變更之後已套用更新的索引鍵。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>讓 SharePoint Online 和 OneDrive for Business，以使用新的金鑰後您首次或旋轉 Azure 機碼存放庫中的機碼

當您首次任一 DEP 相關聯的 Azure 機碼存放庫按鍵用於 SharePoint Online 和 OneDrive for Business，您必須執行[更新 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx)指令程式來更新 DEP 並啟用 Office 365 開始使用新的金鑰。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

這會啟動 SharePoint Online 和 OneDrive for Business 的重要聯播 （英文） 作業。無法立即此巨集指令。若要查看機碼的首次作業的進度，以下列方式執行 Get SPODataEncryptionPolicy cmdlet：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>管理主要存放庫的權限
<a name="Managekeyvaultperms"> </a>

現已提供數個 cmdlet 可讓您檢視和必要的話，移除重要的存放庫的權限。您可能需要移除權限，例如員工離開小組。
  
若要檢視主要存放庫的權限，請執行 Get AzureRmKeyVault cmdlet：
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

例如：
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要移除的管理員權限，執行移除 AzureRmKeyVaultAccessPolicy cmdlet：
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

例如：
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>決定指派給信箱 DEP
<a name="DeterminemailboxDEP"> </a>

若要判斷指派給信箱 DEP，請使用 Get-mailboxstatistics 指令程式。此指令程式會傳回的唯一識別碼 (GUID)。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

其中*GeneralMailboxOrMailUserIdParameter*會指定信箱。如需 Get-mailboxstatistics 指令程式的詳細資訊，請參閱[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。
  
使用 GUID 來找出對其執行下列指令程式來指派信箱 DEP 的易記名稱。
  
```
Get-DataEncryptionPolicy <GUID>
```

其中*的 GUID*是 Get-mailboxstatistics 指令程式在上一個步驟中所傳回的 GUID。 
  

