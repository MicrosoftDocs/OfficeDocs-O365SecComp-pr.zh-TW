---
title: 使用客戶金鑰控制 Office 365 中的資料
ms.author: krowley
author: kccross
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
description: 了解如何設定客戶金鑰的 Office 365 的 Exchange Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive。 使用客戶金鑰，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。
ms.openlocfilehash: 219ddb94727cd2b708f734a77a8397b3bc3f1064
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258351"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>使用客戶金鑰控制 Office 365 中的資料

使用客戶金鑰，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。 換句話說，客戶金鑰可讓客戶將使用其機碼，所屬的加密層。 存放的資料包括 Exchange Online 資料和儲存在信箱的商務用 Skype 資料，以及儲存在 SharePoint Online 中和商務用 OneDrive 中的檔案。
  
您可以使用客戶金鑰的 Office 365 之前，您必須先設定 Azure。 本主題說明您必須建立及設定所需的 Azure 資源遵循的步驟，並接著設定 Office 365 中的客戶金鑰提供的步驟。 完成 Azure 的安裝程式之後，您可以判斷哪個原則，因此，哪一個機碼，將指派給信箱和您的組織中的檔案。 信箱及未將指派原則的檔案會使用加密原則控制並由 Microsoft 管理。 如需有關客戶金鑰或的一般概觀，請參閱[Office 365 常見問題集的客戶金鑰](service-encryption-with-customer-key-faq.md)。
  
> [!IMPORTANT]
> 我們強烈建議您遵循本主題中的最佳作法。 這些稱為**提示**和**重要**。 客戶金鑰可讓您控制其範圍可以是高達整個組織的根加密金鑰。 這表示與這些機碼所產生的錯誤造成廣泛的影響，而且可能會造成服務中斷或冒用您的資料遺失。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>開始之前設定客戶金鑰
<a name="Beforeyoustart"> </a>

在您開始之前，先確認您有適當的授權為您的組織。 在 Office 365 中的客戶金鑰是 Office 365 E5 或進階合規性 SKU 中提供。
  
接著，若要了解概念與本主題中的程序，您應檢閱[Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文件。 此外，熟悉 Azure，例如，[租用戶](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)中所用詞彙。
  
客戶金鑰，包括文件中，提供意見反應傳送您的意見、 建議和觀點來看給 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>設定 Office 365 客戶金鑰的概觀
<a name="Overview"> </a>

若要設定客戶金鑰您將會完成這些工作。 本主題的其餘部分提供每個任務或參閱程序中每個步驟的詳細資訊的連結的詳細的指示。
  
**Azure 和 Microsoft FastTrack： 中**
  
您將會透過遠端連線到 Azure PowerShell 完成大部分的這些工作。 為了獲得最佳結果，使用版本 4.4.0 或更新版本的 Azure PowerShell。
  
- [建立兩個新的 Azure 訂閱](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [註冊 Azure 訂用帳戶使用強制保留期間](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    註冊可能需要一至五個工作天。
    
- [將要求提交至 Office 365 啟用客戶金鑰](controlling-your-data-using-customer-key.md#FastTrack)
    
    一旦您已經建立兩個新的 Azure 訂閱，您需要完成裝載於 Microsoft FastTrack 入口網站 web 表單送出適當的客戶金鑰提供要求。 **FastTrack 小組不會使用客戶金鑰提供協助。Office 只使用 FastTrack 入口網站，讓您將表單送出，並協助我們的客戶金鑰追蹤相關提供**。
  
一旦您已經提交客戶金鑰提供的功能，Microsoft 檢閱您的要求，並通知您，當您可以繼續進行其餘的設定工作。 此程序可能需要多達五個工作天。
    
- [在每個訂閱中建立 Azure 金鑰保存庫進階版](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [將權限指派給每個金鑰保存庫](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [啟用，並確認虛刪除上您金鑰保存庫](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [索引鍵新增至每個金鑰保存庫是藉由建立或匯入金鑰](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [請檢查您的金鑰的復原層級](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [備份的 Azure 金鑰保存庫](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [驗證 Azure Key Vault 組態設定](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [取得每一個 Azure Key Vault 機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**在 Office 365:**
  
Exchange Online 和商務用 Skype:
  
- [建立資料加密原則 (DEP) 以用於 Exchange Online 與 Skype for Business](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [將 DEP 指派給信箱](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [驗證信箱加密](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online 和商務用 OneDrive:
  
- [建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [驗證群組網站、 小組網站和商務用 OneDrive 的加密](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在完成工作 Azure 金鑰保存庫和 Microsoft FastTrack 的客戶金鑰
<a name="AzureSteps"> </a>

在完成這些工作 Azure 金鑰保存庫以設定 Office 365 客戶金鑰。 您必須完成這些步驟，不論是否您想要設定客戶金鑰的 Exchange Online 與 Skype for Business 或 SharePoint Online 和 OneDrive 商務或 Office 365 中的所有支援服務。
  
### <a name="create-two-new-azure-subscriptions"></a>建立兩個新的 Azure 訂閱
<a name="Create2newsubs"> </a>

兩個 Azure 訂用帳戶所需的客戶金鑰。 最佳作法是，Microsoft 建議您建立新 Azure 訂用帳戶使用使用客戶金鑰。 Azure Key Vault 機碼僅可以授權中相同的 Azure Active Directory (AAD) 租用戶的應用程式，您必須建立新的訂用帳戶使用相同 Azure AD 租用戶搭配 Office 365 組織 DEPs 將被指派。 例如，使用 Office 365 組織中具備全域系統管理員權限您公司或學校帳戶。 如需詳細步驟，請參閱[註冊為組織的 Azure](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 客戶金鑰需要兩個機碼，針對每個資料加密原則 (DEP)。 若要達成這個目的，您必須建立兩個 Azure 訂用帳戶。 最佳作法是，Microsoft 建議您有一個索引鍵設定每個訂閱中組織的個別成員。 此外，這些 Azure 訂用帳戶應該只用於 Office 365 管理加密金鑰。 這會保護您的組織，以防您運算子的其中一個不小心、 刻意，或惡意刪除或否則 mismanages 他們所負責的機碼。 <br/> 我們建議您設定新的 Azure 訂閱僅用於使用客戶金鑰管理 Azure Key Vault 資源使用。 沒有任何實用的限制，您可以建立您組織的 Azure 訂用帳戶的數目。 遵循這些最佳作法將最小化人為錯誤的影響同時來管理客戶金鑰所使用的資源可協助。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>將要求提交至 Office 365 啟用客戶金鑰
<a name="FastTrack"> </a>

一旦您已完成的 Azure 的步驟，您需要提供中提交要求[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。 一旦您已經提交要求透過 FastTrack 的入口網站，Microsoft 會驗證 Azure Key Vault 組態資料和連絡人您所提供的資訊。 您在您有關授權主管的優惠表單所做的選擇是組織的要徑和必要的客戶金鑰註冊完成。 您在表單中選取您組織的主管會用來確定任何要求撤銷並銷毀客戶金鑰資料加密原則搭配使用的所有金鑰的授權。 您需要 Exchange Online 和商務用 Skype 商務涵蓋範圍與第二次若要啟動的 SharePoint Online 和商務用 OneDrive 的客戶金鑰啟用客戶金鑰執行一次此步驟。
  
若要提交啟動客戶金鑰供應項目，請完成下列步驟：
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，登入[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。
    
2. 一旦您登入，瀏覽至**儀表板**。
    
3. 選擇 [**提供**，並檢閱目前提供的清單。
    
4. 選擇 [**了解更多**適用於您的提供： 
    
  - **Exchange Online 和商務用 Skype:****Exchange 的客戶金鑰**優惠上選擇 [**了解更多**]。 
    
  - **SharePoint Online 和商務用 OneDrive:** 選擇**更了解**在**SharePoint 和商務用 OneDrive 的客戶金鑰**優惠。 
    
5. 在 [**提供詳細資料**] 頁面上，選擇 [**建立要求**。
    
6. 填寫所有適用的詳細資訊以及提供表單上的要求的資訊。 請特別注意哪些人員的您選擇貴組織要授權核准永久和不能復原損毀的加密金鑰和資料。 當您完成表單時，選擇 [**提交**]。
    
    此程序可能需要多達五個工作天後已經被 Microsoft 通知您的要求。
    
7. 仍繼續前往強制保留期間下一節。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>註冊 Azure 訂用帳戶使用強制保留期間
<a name="RegisterSubsforMRP"> </a>

暫時性或永久性遺失根加密金鑰可以是干擾或甚至重大服務作業，而且可能會導致資料遺失。 基於這個理由，使用客戶金鑰時所用的資源會需要加強保護。 當您使用客戶金鑰的所有 Azure 資源提供的保護機制以外的預設設定。 Azure 訂用帳戶可以標記或的方式，可防止即時和冒用取消註冊。 這稱為 「 註冊強制保留期間內 」。 若要在強制保留期間內註冊 Azure 訂用帳戶所需的步驟需要與 Office 365 小組共同作業。 此程序可能需要一至五個工作天。 先前，這是有時稱為 「 不取消 」。
  
再連絡 Office 365 小組，您必須執行下列步驟，每個 Azure 訂用帳戶，您使用客戶金鑰：
  
1. 登入您使用 Azure PowerShell 的 Azure 訂用帳戶。 如需相關指示，請參閱[登入 Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
2. 執行登錄 AzureRmProviderFeature cmdlet 來註冊您的訂閱使用強制保留期間。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. 請連絡 Microsoft 以已完成的程序。 SharePoint 和 OneDrive for Business 小組，請連絡[spock@microsoft.com](mailto:spock@microsoft.com)。 Exchange Online 和商務用 Skype，請連絡[exock@microsoft.com](mailto:exock@microsoft.com)。 服務層級協議 (SLA) 完成此程序是五個工作天後 Microsoft 已收到通知 （及驗證），您已經註冊您的訂閱使用強制保留期間。 在您的電子郵件中包括下列項目：
    
    **主旨**： 客戶金鑰\<*您的租用戶的完整網域名稱*\> 
    
    **Body**： 您想要有強制保留期間完成的訂閱識別碼。 
    
4. 一旦您會收到通知 microsoft 註冊完畢，確認您的註冊的狀態執行 Get AzureRmProviderFeature 指令程式，如下所示：
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. 驗證之後 Get AzureRmProviderFeature cmdlet 從**註冊 State**屬性會傳回**已登錄**值，執行下列命令，以完成程序：
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每個訂閱中建立 Azure 金鑰保存庫進階版
<a name="CreateKeyVault"> </a>

中[開始使用 Azure 金鑰保存庫](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)]，將引導您完成安裝及啟動 Azure PowerShell，連線至您的 Azure 訂用帳戶、 建立資源群組，和建立金鑰保存庫，在記載的步驟來建立金鑰保存庫資源群組。
  
當您建立金鑰保存庫時，您必須選擇 SKU: [標準] 或 [進階版。 標準 SKU 可讓軟體-沒有任何硬體安全性模組 (HSM) 金鑰保護-受到保護的 Azure Key Vault 機碼和進階版 SKU 可讓 Hsm 用於 Key Vault 機碼的保護。 客戶金鑰會接受使用任一種 SKU 的金鑰保存庫，但是 Microsoft 強烈建議您使用僅限進階版 SKU。 作業成本，有兩種類型的索引鍵是相同的因此在成本的唯一差別是每月的每個 HSM 保護索引鍵的成本。 如需詳細資訊，請參閱[Key Vault 價格](https://azure.microsoft.com/pricing/details/key-vault/)。 
  
> [!IMPORTANT]
> 實際執行資料，請使用進階版 SKU 金鑰保存庫和 HSM 受保護的機碼，然後只使用標準的 SKU 金鑰保存庫和機碼進行測試和驗證。 
  
每個 Office 365 服務與您會使用客戶金鑰，請建立金鑰保存庫中每個您所建立的兩個 Azure 訂閱。 例如，Exchange Online 和商務用 Skype 僅商務或 SharePoint Online 和僅商務用 OneDrive，您將建立僅有一組的保存庫。 若要啟用 Exchange Online 和 SharePoint Online 客戶金鑰，您會建立兩組金鑰保存庫。
  
使用金鑰保存庫，以反映您將關聯保存庫 DEP 的預定的用法的命名慣例。 請參閱下方命名慣例建議的最佳作法章節內容。
  
建立每個資料加密原則保存庫不同，配對集。 針對 Exchange Online，會在您選擇的資料加密原則範圍當您將原則指派給信箱。 信箱可以有指派後，只有一個原則，您可以建立最多了 50 個原則。 SharePoint online 原則範圍是所有地理位置或地理位置中組織內的資料。
  
建立的金鑰保存庫也需要 Azure 的資源群組，請建立後金鑰保存庫需要儲存容量 （雖然很小） 和記錄，Key Vault 若啟用，也會產生儲存的資料。 最佳作法是，Microsoft 建議使用不同的系統管理員來管理每個資源群組，以符合一組系統管理員會管理相關的所有客戶金鑰資源管理。
  
> [!IMPORTANT]
> 若要達到最大的可用性，您金鑰保存庫應該接近您的 Office 365 服務的區域。 例如，如果您的 Exchange Online 組織位於 「 北美地區 」，請將您金鑰保存庫放在 「 北美地區 」。 在歐洲 Exchange Online 組織時，將您金鑰保存庫放在 Europe。<br/>使用共同的前置字元的金鑰保存庫，並加入，所用縮寫和金鑰保存庫和金鑰的範圍 (例如，為保存庫內 「 北美地區 」，名稱可能配對的所在位置的 Contoso SharePoint 服務 Contoso O365SP-NA VaultA1 和Contoso-O365SP-NA-VaultA2。 儲藏室名稱是在 Azure 中的全域唯一字串，所以您可能需要嘗試變化的您想要的名稱，以防其他 Azure 客戶已宣告的所需的名稱。 2017 年 7 月起儲藏室名稱無法變更，所以最佳作法是已安裝程式撰寫的計劃，並使用第二個人員若要確認已正確執行計劃。<br/>如果可能的話，建立您保存庫非成對的區域。 成對的 Azure 區域服務失敗網域內提供高可用性。 因此，區域的配對可以視為彼此的備份區域。 這表示會被放置在一個區域 Azure 資源會自動獲得容錯透過配對區域權限。 基於這個理由，選擇區域所在位置，都在使用中的可用性的兩個區域的總計的配對的表示 DEP 中所使用的兩個保存庫的區域。 大部分的地區只需要兩個區域，因此無法還可以選取 [非成對的區域。 如果可能，請選擇 [與相依性搭配使用，將兩個保存庫中非成對的兩個區域 這會受益總共四個區域的可用性。 如需詳細資訊，請參閱[商務持續性與災害復原 (BCDR): Azure 成對區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)的目前區域配對的清單。 
  
### <a name="assign-permissions-to-each-key-vault"></a>將權限指派給每個金鑰保存庫
<a name="KeyVaultPerms"> </a>

針對每個金鑰保存庫，您必須定義三個不同的客戶金鑰，根據您實作的權限集。 例如，您需要定義一組權限，如下列各項：
  
- **Key vault 系統管理員**將為組織執行日常管理您金鑰保存庫。 這些工作包括備份、 建立、 取得、 匯入清單，以及還原。 
    
    > [!IMPORTANT]
    > 權限指派給金鑰保存庫系統管理員不會納入權限可以刪除索引鍵。 這是蓄意和重要的作法。 刪除加密金鑰不通常是，因為這樣永久執行等到資料。 最佳作法是不要不此權限授與金鑰保存庫管理員預設。 相反地，保留這的金鑰保存庫參與者，並只將其指派給短期為基礎的系統管理員一旦清楚了解所造成的影響也了解。 
  
    若要將這些權限指派給您的 Office 365 組織中的使用者，登入您使用 Azure PowerShell 的 Azure 訂用帳戶。 如需相關指示，請參閱[登入 Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
- 執行設定 AzureRmKeyVaultAccessPolicy cmdlet 來指派必要權限。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  例如：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- **Key vault 參與者**可以變更 Azure 金鑰保存庫的權限本身擷取。 您需要變更這些權限，如員工離開或加入您的小組，或在極罕見的情況下，機碼地窖管理員合法需要刪除或還原金鑰的權限。 這組金鑰保存庫參與者需要被授與您金鑰保存庫**參與者**角色。 您可以使用 Azure Resource Manager 指派此角色。 如需詳細步驟，請參閱 <<c0>管理 Azure 訂用帳戶資源的存取權的 Use Role-Based 存取控制。 會建立訂閱的系統管理員存取此以隱含方式，以及將其他系統管理員指派給參與者角色。
    
- 如果您想使用客戶金鑰 Exchange Online 與 Skype for Business，您需要的權限授與使用金鑰保存庫代表 Exchange Online 與 Skype for Business 的 Office 365。 同樣地，如果您想使用客戶金鑰 SharePoint Online 和 OneDrive for Business，您需要新增使用金鑰保存庫代表 SharePoint Online 和 OneDrive for Business 的 Office 365 的權限。 若要將權限授與 Office 365，執行**組 AzureRmKeyVaultAccessPolicy**指令程式使用下列語法： 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    其中：
    
  - *vaultname*是您建立金鑰保存庫的名稱。 
    
  - Exchange Online 和商務用 Skype，取代與*Office 365 appID*`00000002-0000-0ff1-ce00-000000000000`
    
  - 若是 SharePoint Online 和商務用 OneDrive，取代與*Office 365 appID*`00000003-0000-0ff1-ce00-000000000000`
    
  範例： 設定 Exchange Online 和商務用 Skype 的權限：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  範例： 設定 SharePoint Online 和商務用 OneDrive 的權限
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>啟用，並確認虛刪除上您金鑰保存庫
<a name="SoftDelete"> </a>

當您可以快速復原您的金鑰時，您的可能性會較經驗延伸的服務中斷因為意外或惡意刪除索引鍵。 您要啟用此設定，稱為 「 虛刪除時，您才能使用您的金鑰使用客戶金鑰。 啟用虛刪除，可讓您要刪除的 90 天內復原機碼或保存庫，而不必從備份還原。
  
若要啟用虛刪除您金鑰保存庫，請完成下列步驟：
  
1. 登入您使用 Windows Powershell 的 Azure 訂用帳戶。 如需相關指示，請參閱[登入 Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。
    
2. 執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。 在這個範例中， *vaultname*是您要為其啟用虛刪除金鑰保存庫的名稱： 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. 確認虛刪除執行**Get AzureRmKeyVault**指令程式時，已針對金鑰保存庫。 虛刪除的設定是否正確的金鑰保存庫，虛刪除已啟用？屬性會傳回**True**值： 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>索引鍵新增至每個金鑰保存庫是藉由建立或匯入金鑰
<a name="AddKeystoKeyVault"> </a>

有兩種方式可將機碼新增至 Azure 金鑰保存庫;您可以直接在金鑰保存庫中建立機碼，或您可以匯入金鑰。 直接在金鑰保存庫中建立機碼時，若為較複雜的方法，匯入金鑰可讓您總控制如何產生金鑰。
  
若要直接在您金鑰保存庫中建立機碼，執行[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)指令程式，如下所示： 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：
  
-  *vaultname*是您要建立的機碼金鑰保存庫的名稱。 
    
-  *keyname*是您要給新的金鑰的名稱。 
    
    > [!TIP]
    > 使用類似的命名慣例，上面所述的金鑰保存庫名稱機碼。 如此一來，在 [顯示機碼名稱的工具，字串自我描述。 
  
- 如果您想要保護 HSM 索引鍵，請確定您指定**HSM**作為_目的地_參數值，否則指定**軟體**。
    
For example,
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

若要直接將您金鑰保存庫，匯入金鑰，您需要有 Thales nShield 硬體安全性模組。
  
有些組織偏好使用這個方法可以建立其機碼，與此 provenance 方法也會提供下列：
  
- 用於匯入工具組包含從 Thales 金鑰 Exchange 機碼 (KEK) 是用來加密您產生的機碼不是可匯出的證明，並產生 Thales 已生產正版 HSM 內。
    
- 工具組包含從 Azure Key Vault 安全性世界也已產生上生產 Thales 正版 HSM Thales 證明。 此證明能就能確信您 Microsoft 也使用正版 Thales 硬體。
    
請與您安全性群組來決定是否需要上述 attestations。 建立主要內部部署，然後匯入您金鑰保存庫的詳細步驟，請參閱[如何產生，並且傳送 HSM 保護 Azure Key Vault 機碼](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。 若要在每個金鑰保存庫中建立的機碼中使用 Azure 的指示。
  
### <a name="check-the-recovery-level-of-your-keys"></a>請檢查您的金鑰的復原層級
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 需要 Azure Key Vault 訂閱設為不會取消和使用客戶金鑰的機碼已啟用的虛刪除。 您可以透過查看 [您的機碼中的 [復原層級加以確認。
  
若要檢查的金鑰，請在 Azure PowerShell 復原層級執行 Get AzureKeyVaultKey 指令程式，如下所示：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

如果_復原層級_屬性可傳回的值為**復原 + ProtectedSubscription**以外的任何項目，您必須以檢閱本主題，並確認您是否已遵循所有訂閱置於 [不要取消] 清單中的步驟和您必須在每個您金鑰保存庫上啟用的虛刪除。
  
### <a name="backup-azure-key-vault"></a>備份的 Azure 金鑰保存庫
<a name="BackupAzureKeyVaultkeys"> </a>

緊接在建立或變更索引鍵，以執行備份，然後儲存的備份，線上和離線複本。 離線複本應該不連接到任何網路時，例如實體安全或商業儲存體設備中。 至少一份備份應該儲存在發生災害時可存取的位置。 備份 blob 是唯一的還原金鑰內容應該 Key Vault 機碼會永久移除或否則呈現 [無法正常運作。 按鍵的 Azure Key Vault 外部，且匯入至 Azure Key Vault 切勿做為備份，因為若要使用金鑰的客戶金鑰所需的中繼資料與外部索引鍵不存在。 僅備份採取從 Azure 金鑰保存庫可用於還原作業，使用客戶金鑰。 因此，它是不可或缺的 Azure Key Vault 備份進行後金鑰已上傳或建立。
  
若要建立 Azure Key Vault 機碼的備份，執行[備份 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)指令程式，如下所示：
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

請確定您的輸出檔使用後置`.backup`。
  
此指令程式所產生的輸出檔進行加密，並不能使用外部 Azure 金鑰保存庫。 可以從中執行備份的 Azure 訂用帳戶，才能還原備份。
  
> [!TIP]
> 對於輸出檔案中，選擇 [儲藏室名稱和機碼名稱的組合。 這樣會使檔案名稱自我描述。 它也能確保備份的檔案名稱執行動作不會發生衝突。 
  
例如：
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>驗證 Azure Key Vault 組態設定
<a name="Validateconfiguration"> </a>

執行 DEP 中使用機碼之前的驗證是選擇性作業，但強烈建議。 特別是，如果您使用的步驟來設定您的機碼和保存庫以外，本主題中所述，您應該先驗證您的 Azure Key Vault 資源的健康狀況，再設定客戶金鑰。
  
若要確認您的金鑰已啟用的 get、 wrapKey，以及 unwrapKey 作業：
  
執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)指令程式，如下所示： 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

在輸出中，尋找適當的存取原則和 Exchange Online 的身分識別 (GUID) 或 SharePoint Online 的身分識別 (GUID)。 所有三個以上的權限必須都顯示權限] 之下，機碼。
  
如果存取原則設定不正確，請執行組 AzureRmKeyVaultAccessPolicy 指令程式，如下所示：
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，針對 Exchange Online 和商務用 Skype:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，對於 SharePoint Online 和商務用 OneDrive:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

若要確認您執行[Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)指令程式，如下所示的機碼未設定到期日： 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

客戶金鑰無法使用過期的索引鍵，並嘗試使用過期的索引鍵的作業會失敗，但可能會造成服務中斷。 我們強烈建議使用客戶金鑰與金鑰沒有到期日。 到期日，一旦設定，不能移除，但是可加以變更至不同的日期。 如果機碼必須使用已設定到期日，請將到期值變更為 12/31/9999。 包含到期日的機碼設為日期以外 12/31/9999 不會通過 Office 365 驗證。
  
若要變更已設定為 12/31/9999 以外的任何數值的到期日，執行[組 AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)指令程式，如下所示： 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不在您使用客戶金鑰的加密金鑰設定到期日。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>取得每一個 Azure Key Vault 機碼的 URI
<a name="GetKeyURI"> </a>

一旦您已完成設定您金鑰保存庫 Azure 中的所有步驟，並新增您的金鑰，請執行下列命令，以取得每個金鑰保存庫中的索引鍵的 URI。 您將需要使用這些 Uri，當您建立及更新版本中，指派每個 DEP 因此儲存此資訊在安全的地方。 請記得執行此命令一次的每個金鑰保存庫。
  
在 Azure PowerShell:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365： 客戶金鑰設定 Exchange Online 和商務用 Skype
<a name="AzureSteps"> </a>

開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。 如需資訊，請參閱[Azure 金鑰保存庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)。 
  
若要設定 Exchange Online 和商務用 Skype 的客戶金鑰，您必須透過遠端連線到 Exchange Online 使用 Windows PowerShell 執行這些步驟。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>建立資料加密原則 (DEP) 以用於 Exchange Online 與 Skype for Business
<a name="CreateDEP4EXOSkype"> </a>

DEP 是一組儲存在 Azure 金鑰保存庫中的機碼相關聯。 您可以指派 DEP 至 Office 365 中的信箱。 Office 365 然後會使用該原則中所識別的金鑰來加密信箱。 若要建立 DEP，您需要您稍早取得 Key Vault Uri。 如需相關指示，請參閱[Obtain 每一個 Azure Key Vault 機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
請記住 ！ 當您建立 DEP 時，您會指定位於兩個不同的 Azure 金鑰保存庫中的兩個索引鍵。 請確定這些機碼位於兩個不同的 Azure 區域，以確保異地備援。
  
若要建立 DEP，請遵循下列步驟：
  
1. 在您的本機電腦上使用公司或學校帳戶具有 Office 365 組織中，開啟 Windows PowerShell 並執行下列命令[連接至 Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)的全域系統管理員權限。 
    
   ```
   $UserCredential = Get-Credential
   ```

2. 在 [Windows PowerShell 認證要求] 對話方塊中，輸入您的工作或學校帳戶資訊、 按一下 [**確定**]，然後輸入下列命令。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 執行下列命令。
    
   ```
   Import-PSSession $Session
   ```

4. 若要建立 DEP，使用新 DataEncryptionPolicy 指令程式輸入下列命令。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：
    
   -  *PolicyName*是您想要用於此原則的名稱。 名稱不可包含空格。 例如，USA_mailboxes。 
    
   -  *PolicyDescription*是可協助您記住原則是針對原則的使用者易記描述。 您可以在描述中包含空格。 例如，根機碼 USA 和其領域中的信箱。 
    
   -  *KeyVaultURI1*是原則中的第一個索引鍵的 URI。 例如 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。 
    
   -  *KeyVaultURI2*是原則中的第二個機碼的 URI。 例如 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。 分隔兩個 Uri 以逗號和空格。 
    
   範例：
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>將 DEP 指派給信箱
<a name="assignDEPtomailbox"> </a>

使用 Set-mailbox 指令程式，將 DEP 指派給信箱。 一旦您指派原則時，Office 365 加密，您可以信箱與相依性中所指定的金鑰
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中*MailboxIdParameter*指定的信箱。 如需將 Set-mailbox cmdlet 的詳細資訊，請參閱[Set-mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。
  
### <a name="validate-mailbox-encryption"></a>驗證信箱加密
<a name="validatemailboxencryption"> </a>

加密的信箱可能需要一些時間。 第一次原則指派] 中，針對信箱也之前必須完成從一個資料庫移至另一個服務可以加密信箱。 我們建議您等候 72 小時，再嘗試驗證加密之後變更 DEP 或第一次您指派 DEP 到信箱。
  
使用 Get-mailboxstatistics 指令程式來決定是否信箱已加密。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果信箱尚未加密，IsEncrypted 屬性會傳回的值 **，則為 true**如果信箱已加密和**false**值。 

完成信箱移動的時間取決於您所指派的第一次，DEP 的信箱數目，以及信箱的大小。 如果信箱已不加密您指派 DEP 的時間從一週後，請使用 New-moverequest 指令程式起始未加密的信箱的信箱移動。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365： 設定 SharePoint Online 和商務用 OneDrive 的客戶金鑰
<a name="AzureSteps"> </a>

開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。 如需資訊，請參閱[Azure 金鑰保存庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)。 
  
若要設定客戶金鑰的 SharePoint Online 和商務用 OneDrive，您必須透過遠端連線到 SharePoint Online Windows powershell 執行這些步驟。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置
<a name="CreateDEP4SPOODfB"> </a>

DEP 是一組儲存在 Azure 金鑰保存庫中的機碼相關聯。 您可以將 DEP 套用至所有您在一個地理位置，也稱為 「 地理位置的資料。 如果您使用 Office 365 的多地理位置功能 （目前處於預覽） 時，您可以建立一個 DEP 每個地理位置。 如果您不使用多地理位置，您可以在 Office 365 中建立一個 DEP，以用於 SharePoint Online 和 OneDrive for Business。 Office 365 然後會使用 DEP 中所識別的金鑰來加密的地理位置中的資料。 若要建立 DEP，您需要您稍早取得 Key Vault Uri。 如需相關指示，請參閱[Obtain 每一個 Azure Key Vault 機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
請記住 ！ 當您建立 DEP 時，您會指定位於兩個不同的 Azure 金鑰保存庫中的兩個索引鍵。 請確定這些機碼位於兩個不同的 Azure 區域，以確保異地備援。
  
若要建立 DEP，您需要使用 Windows PowerShell 從遠端連線至 SharePoint Online。
  
1. 在您的本機電腦上使用公司或學校帳戶具有 Office 365 組織中，[連線到 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)的全域系統管理員權限。
    
2. 在 Microsoft SharePoint Online 管理命令介面中，執行[註冊 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx)指令程式，如下所示： 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   當您註冊 DEP 時，加密會開始於地理位置中的資料。 這可能需要一些時間。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>驗證群組網站、 小組網站和商務用 OneDrive 的加密
<a name="validateencryptionSPO"> </a>

您可以檢查的加密狀態，藉由執行 Get SPODataEncryptionPolicy 指令程式，如下所示：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的輸出包含：
  
- 主索引鍵的 URI。
    
- 第二個機碼的 URI。
    
- 地理加密狀態。 可能的狀態包括：
    
  - **未註冊：** 客戶金鑰加密尚未套用。 
    
  - **註冊：** 已套用客戶金鑰加密及加密正在您的檔案。 如果您地理位置是在此狀態下，您將也會顯示資訊上，讓您可以監視加密進度百分比的地理位置中的網站都已完成。 
    
  - **註冊：** 已套用客戶金鑰加密，並已加密的所有網站中的所有檔案。 
    
  - **循環：** 索引鍵 roll 正在進行中。 如果您地理位置是在此狀態下，您將也會顯示資訊上百分比的網站都已完成金鑰 roll 作業，以便您可以監視進度。 
    
## <a name="managing-customer-key-for-office-365"></a>管理 office 365 的客戶金鑰
<a name="ManageCustomerKey"> </a>

您的 Office 365 設定客戶金鑰之後，您可以執行下列的其他管理工作。
  
- [還原 Azure Key Vault 機碼](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [循環或旋轉的機碼中使用客戶金鑰的 Azure Key Vault](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [管理金鑰保存庫的權限](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [決定指派給信箱 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>還原 Azure Key Vault 機碼
<a name="RestoreAzureKeyVaultKeys"> </a>

之前執行還原，請使用虛刪除所提供的復原功能。 當您使用客戶金鑰的所有索引鍵所需已啟用的虛刪除。 虛刪除 bot 資源回收筒，並允許復原 90 天，而不需要還原。 在特殊或不尋常的情況，例如，如果金鑰或金鑰保存庫將會遺失時，應該只需要還原。 如果您必須使用客戶金鑰還原金鑰使用 Azure PowerShell 中執行還原 AzureKeyVaultKey cmdlet，如下所示：
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

例如：
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果在金鑰保存庫中已經存在具有相同名稱的索引鍵，將會失敗的還原作業。 還原 AzureKeyVaultKey 還原所有的主要版本和所有的中繼資料，包括機碼名稱機碼。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>循環或旋轉的機碼中使用客戶金鑰的 Azure Key Vault
<a name="RollCKkey"> </a>

循環機碼，則不需要透過任一 Azure Key Vault 或客戶金鑰。 此外，使用 HSM 保護的索引鍵是幾乎不可能危害。 即使根機碼所擁有的惡意的動作項目中沒有可行的情況下使用它來解密資料，因為只有 Office 365 程式碼知道如何使用它的方法。 不過，循環機碼是由支援客戶金鑰。
  
> [!CAUTION]
> 僅將清除技術原因存在或規範需求規定您必須回復索引鍵時使用客戶金鑰加密金鑰。 此外，請勿刪除或已與原則相關聯的任何索引鍵。 當您還原您的機碼，有將內容加密與先前的機碼。 例如，當作用中信箱將會重新加密常見問題，非使用中，中斷連線，並已停用信箱可能仍將加密與先前的機碼之中。 SharePoint Online 執行備份的內容進行還原和復原，因此有可能仍會使用較舊的機碼的封存的內容。 <br/> 若要確保您的資料安全，SharePoint Online 可讓要進行一次不超過一個金鑰復原作業。 如果您想要將這兩個機碼金鑰保存庫中，您需要稍候的第一項重要 roll 作業完全完成。 我們建議在不同的時間間隔，錯開金鑰 roll 作業，所以這不是此問題:。 
  
當您還原金鑰時，您要求新版本的現有的索引鍵。 若要要求新版本的現有的索引鍵，您可以使用相同的指令程式，[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)，具有相同的語法，用來在第一時間建立的機碼。
  
例如：
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

在這個範例中，因為已經名為**Contoso-O365EX-NA-VaultA1-Key001**機碼存在於**Contoso O365EX-NA VaultA1**儲藏室，將會建立新的主要版本。 此作業會新增新的主要版本。 這項作業會保留重要舊版中的索引鍵的版本歷程記錄，以便仍可解密先前使用該金鑰加密的資料。 當您完成循環 DEP 相關聯的任何按鍵時，您必須執行其他的指令程式，以確保客戶金鑰會開始使用新的金鑰。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>啟用 Exchange Online 和商務用 Skype 之後您將旋轉或 Azure 金鑰保存庫中的機碼，使用新的金鑰

當您展開任一 DEP 相關聯的 Azure Key Vault 機碼搭配 Exchange Online 與 Skype for Business，您必須執行下列命令，以更新 DEP 及啟用 Office 365，若要開始使用新的金鑰。
  
以指示要用於新的金鑰加密中執行組 DataEncryptionPolicy 指令程式，如下所示的 Office 365 信箱的客戶金鑰：
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

48 小時內，使用此原則加密作用中信箱將會變成與更新的索引鍵關聯。 使用 < <b0>Determine DEP 指派給信箱</b0>的步驟，檢查信箱 DataEncryptionPolicyID 屬性的值。 一旦套用更新的機碼，將會變更此屬性的值。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>啟用 SharePoint Online 和商務用 OneDrive 之後您將旋轉或 Azure 金鑰保存庫中的機碼，使用新的金鑰

當您展開任一 DEP 相關聯的 Azure Key Vault 機碼搭配 SharePoint Online 和 OneDrive for Business，您必須執行[更新 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx)指令程式來更新 DEP，並啟用 Office 365，若要開始使用新的金鑰。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

這會啟動 SharePoint Online 和商務用 OneDrive 的重要 roll 作業。 此巨集指令不即時運算]。 若要查看機碼的復原作業的進度，執行 Get SPODataEncryptionPolicy 指令程式，如下所示：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>管理金鑰保存庫的權限
<a name="Managekeyvaultperms"> </a>

多個 cmdlet 可供使用，可讓您檢視，如有必要，移除金鑰保存庫的權限。 您可能需要移除權限，例如，當員工離開小組。
  
若要檢視金鑰保存庫的權限，請執行 Get AzureRmKeyVault 指令程式：
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

例如：
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要移除系統管理員權限，請執行移除 AzureRmKeyVaultAccessPolicy 指令程式：
  
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

若要判斷 DEP 指派給信箱，請使用 Get-mailboxstatistics 指令程式。 此 cmdlet 會傳回的唯一識別碼 (GUID)。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

其中*GeneralMailboxOrMailUserIdParameter*指定的信箱。 如需 Get-mailboxstatistics 指令程式的詳細資訊，請參閱[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。
  
使用 GUID 來找出信箱執行下列 cmdlet 來指派 DEP 的易記名稱。
  
```
Get-DataEncryptionPolicy <GUID>
```

*GUID*是上一個步驟中的 Get-mailboxstatistics 指令程式所傳回的 GUID。 
  

