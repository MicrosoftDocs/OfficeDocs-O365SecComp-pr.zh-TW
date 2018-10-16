---
title: Office 365 中使用客戶金鑰的服務加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: 除了 [比較基準，透過 BitLocker 與分散式金鑰管理員 (DKM)、 已啟用的磁碟區層級加密 Office 365 提供新增一層的 Office 365，包括資料從 Exchange 中的客戶內容應用程式層級的加密線上商務、 SharePoint Online、 及 OneDrive for Business Skype。這會呼叫服務加密。
ms.openlocfilehash: ceba35233872bb65b7706ed4e11a263057adc6c1
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575327"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Office 365 中使用客戶金鑰的服務加密常見問題集

除了 [比較基準，透過 BitLocker 與分散式金鑰管理員 (DKM)、 已啟用的磁碟區層級加密 Office 365 提供新增一層的 Office 365，包括資料從 Exchange 中的客戶內容應用程式層級的加密線上商務、 SharePoint Online、 及 OneDrive for Business Skype。這會呼叫服務加密。
  
客戶金鑰內建服務加密，並讓您提供與用來加密 Office 365 中的靜態資料的[線上服務合約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中所述的控制機碼。客戶機碼可協助您符合法規責任因為控制 Office 365 使用解密資料的加密金鑰。
  
若要提供意見反應客戶金鑰，包括文件，將您的想法、 建議] 和觀點 （英文） 傳送至 customerkeyfeedback@microsoft.com。
  
## <a name="what-is-service-encryption-with-customer-key"></a>什麼是服務加密與客戶金鑰？

客戶金鑰增強了您的組織能夠符合指定按鍵的排列方式與雲端服務提供者的規範需求的需求。與客戶金鑰您提供並控制在 Office 365 的資料在-其餘應用程式層級的加密金鑰。因此，您可能會演練控制項和撤銷貴組織的機碼，您應該決定結束服務。由 grant 機碼，此資料是服務無法讀取。主要撤銷是向資料刪除路徑上的第一個步驟。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>客戶鍵所涵蓋靜態何種 Office 365 資料？
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

涵蓋 SharePoint Online 網站內容儲存在該網站上的檔案與檔案上傳至 OneDrive for Business。討論 Exchange Online 信箱內容 （電子郵件內文、 行事曆項目及內容的電子郵件附件）。涵蓋從 Skype for Business 的文字交談，但未涵蓋 Skype 會議廣播錄製和 Skype 會議內容上傳。Skype 會議廣播和 Skype 會議內容的上傳 Office 365 中的所有其他內容一同加密，但我們目前不提供客戶控制的加密金鑰。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>客戶機碼和將您自己鍵 (BYOK) 與 Azure 資訊 Protection for Exchange Online 之間的差異為何？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

這兩個選項可讓您提供並控制您自己的加密金鑰;不過，服務加密與客戶金鑰加密靜態，位於 Office 365 伺服器在-rest 時的 Exchange Online 的 Azure 資訊保護 BYOK 加密中傳輸您資料並提供持續性線上與離線資料保護電子郵件訊息與 Office 365 的附件。客戶金鑰及 BYOK Azure 資訊保護 Exchange Online 的互補，且您選擇使用 Microsoft 的服務-受管理的機碼或您自己的機碼，是否加密您的資料在 rest 和傳送過程中可提供來自新增的保護惡意的攻擊。
  
與 Exchange Online 的 Azure 資訊保護 BYOK 被提供 in Office 365 郵件加密功能。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>沒有 Office 365 郵件加密和將您自己的金鑰與 Azure 資訊保護變更 Microsoft 的方法如 subpoenas 協力廠商資料要求吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

[否]。Office 365 郵件加密和選項提供並控制您自己的加密金鑰與將您自己鍵 (BYOK) Azure 資訊保護 (AIP) 不是以回應 law 強制執行 subpoenas 而設計。必須滿足其內部或外部規範責任的規範著重客戶的設計旨在與 BYOK for AIP office 365 郵件加密。Microsoft 非常嚴重採用客戶資料的第三方的要求。做為雲端服務提供者，我們一律主張的客戶資料的隱私。我們要取得傳票、 可行我們永遠嘗試將第三方重新導向至客戶資訊。(請參閱此 Smith 的部落格： [＜ Protecting 政府側錄的客戶資料](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我們會定期發行我們會收到的要求的詳細的資訊[如下](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
請參閱[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/default.aspx)有關協力廠商資料要求和 「 洩漏的客戶資料 」 在[線上服務合約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)的詳細資訊。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>服務加密與客戶金鑰是否變更 Microsoft 的方法與協力廠商資料要求例如 subpoenas 吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

[否]。客戶金鑰不是以回應 law 強制執行 subpoenas 而設計。它是以符合其內部或外部規範義務規範客戶的設計。Microsoft 非常嚴重採用客戶資料的第三方的要求。做為雲端服務提供者，我們一律主張的客戶資料的隱私。我們要取得傳票、 可行我們永遠嘗試將第三方重新導向至客戶資訊。(請參閱此 Smith 的部落格： [＜ Protecting 政府側錄的客戶資料](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我們會定期發行我們會收到的要求的詳細的資訊[如下](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
請參閱[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)有關協力廠商資料要求和 「 洩漏的客戶資料 」 在[線上服務合約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)的詳細資訊。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>是 FastTrack 支援可用於實作客戶金鑰吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

[否]。FastTrack 只用來收集所需註冊客戶機碼的租用戶和服務組態資訊。客戶金鑰提供發佈透過 FastTrack 使可相當方便地客戶和合作夥伴送出這個使用的相同方法所需的資訊及簡化的封存客戶提供產品項目中的資料。
  
如果您需要超過文件的其他支援，請連絡 Microsoft 諮詢服務 (ATL-MCS-001)、 Premier 欄位工程 (PFE) 或 Microsoft 協力廠商尋求協助。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>如果我金鑰已毀損，如何可以使用復原？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性金鑰提供復原未預期的遺失根按鍵的管理功能。如果您遺失根機碼，連絡 Microsoft 支援與 Microsoft 會協助您透過啟用可用性機碼的程序。您將使用的可用性金鑰移轉至新的資料加密原則與您佈建的新機碼。 
  
## <a name="what-is-the-availability-key"></a>什麼是可用性金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性機碼是當您建立的資料加密原則佈建的根機碼。儲存及受保護的 Office 365 中的可用性金鑰及具有相同的作用類似於提供您用於服務加密客戶機碼的兩個根機碼。不同於您所提供且管理 Azure 機碼存放庫中的機碼，您無法直接存取可用性機碼。儲存空間及可用性機碼的控制項是刻意不同 Azure 機碼存放庫機碼的三個原因： 首先，可用性金鑰提供高可用性功能時的 Office 365 服務已無法與主控 Azure 機碼中的機碼存放庫 ；其次，可用性金鑰提供 」 會自動換行派對杯"功能時，這兩個 Azure 金鑰儲藏室金鑰會遺失;和第三之邏輯控制項的區隔提供深入防禦提供保護，避免所有機碼從單一的攻擊遺失或失敗點。共用保護機碼，同時使用各種模式保護和處理程序的金鑰管理責任最終可減少的所有按鍵 （與因此資料） 將會遺失或毀損的風險。Microsoft 提供權力透過損毀的可用性機碼。根據設計，在 Microsoft 無人具有存取權的可用性金鑰-僅限可供 Office 365 服務的程式碼存取。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>可以建立多少資料加密原則 (DEPs)？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 您可以建立最多 50 DEPs。 
  
 **SharePoint Online 和 OneDrive for Business:** DEP 套用至一的地理位置，也稱為 「 地理位置中的資料。如果您使用 Office 365 的多重地理位置功能，您可以建立一個 DEP 個別地理位置。如果您不使用多個地理位置，您可以建立一個相依性
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>可以指派資料加密原則之前的信箱移轉至雲端吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

[是]。您可用於 Windows PowerShell cmdlet Set-mailuser 指派資料加密原則 (DEP) 之前的信箱移轉至 Office 365 使用者。當您這樣做時，會使用內容移轉指派的 DEP 加密信箱的內容。這可以是比之後已移轉信箱指派 DEP 以及然後等候才可以天數需要數小時或可能的地方加密更有效率。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>如何確認會在啟動與客戶金鑰加密和 Office 365 已完成加密與客戶金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 您可以[連線到 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) ，然後使用 **[Get-mailboxstatistics]** cmdlet 針對您想要檢查的信箱。Get-mailboxstatistics 指令程式的輸出，在_IsEncrypted_屬性會傳回的值**則為 true**如果加密信箱及**false**的值如果原本不是。如果要加密信箱、 _DataEncryptionPolicyID_屬性的傳回值為 DEP 用來加密之信箱的 GUID。執行此 cmdlet 的詳細資訊，請參閱[Get-mailboxstatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx)和使用 PowerShell 與 Exchange Online。 
  
如果信箱不加密等候從指派 DEP 時間 72 小時後，引發信箱移動。若要這樣做，[連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)與然後使用 New-moverequest 指令程式，並提供信箱的別名，如下所示： 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online 和 OneDrive for Business:** 您可以[連線至 SharePoint Online PowerShell](https://technet.microsoft.com/en-us/library/fp161372.aspx)，然後使用 **[Get-SPODataEncryptionPolicy]** 指令程式來檢查您的租用戶的狀態。* *_狀態_* * 如果已啟用客戶金鑰加密和已加密的所有網站中的所有檔案屬性會傳回**登錄**值。如果仍然正在進行加密，則此指令程式提供有關哪些百分比網站已完成。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>如果我想要切換至一組不同的按鍵，沒有多少時間的一組新的金鑰來保護我的資料？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 可能很多達 72 小時信箱根據新資料加密原則 (DEP) 防止新 DEP 指派給信箱的時間。 
  
 **SharePoint Online 和 OneDrive for Business:** 它可以需要最多四個小時之後已指派新的金鑰重新加密整個租用。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>我現有的資料儲存沒有任何時候加密時解密或加密與客戶金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

[否]。在 DKM BitLocker 與 Office 365 服務中的其餘部分一律加密資料。如需詳細資訊，請參閱"安全性、 隱私權和 office 365 規範資訊 」，以及[如何 Exchange Online 保護您的電子郵件機密資料](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)。
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>如果我不想再使用客戶管理加密金鑰，可以使用切換至 Microsoft managed 金鑰吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 尚未。這會受到支援 Microsoft managed 金鑰與 Office 365 中的服務加密廣泛導之後。我們預期導入此服務中之後我們釋服務加密與客戶機碼。 
  
 **SharePoint Online 和 OneDrive for Business:**[是]。您可以選擇要還原為使用 Microsoft managed 金鑰分別為每個地理位置 （如果您使用多個地理位置功能） 或所有資料如果它是在單一地理位置。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>如果我遺失我機碼，沒有多少時間復原服務可用性使用復原金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 一旦您呼叫使用的可用性索引鍵時，信箱都可存取分鐘內。 
  
 **SharePoint Online 和 OneDrive for Business:** 這項作業是您所擁有的網站數目調和間距。一旦您呼叫 Microsoft 使用可用性金鑰，您將會是完全線上約四個小時內。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>可用性機碼是如何使用與 Exchange Online？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

有三種方法用於可用性金鑰與 Exchange Online：
  
- 服務可用性-的 Azure 機碼存放庫機碼的代理人連線。
    
- 動作起始由 Office 365 服務程式碼-例如搜尋索引建立或信箱移動。
    
- 從主要遺失-如單一 DEP 相關聯這兩個 Azure 機碼存放庫機碼故障中復原
    
 **使用可用的服務可用性金鑰可行 Azure 機碼存放庫機碼的代理人連線。**
  
Office 365 的 Exchange Online 使用可用性金鑰用於服務可用性和復原從不健康的客戶金鑰狀態。有的客戶機碼所使用的金鑰階層。下圖說明此階層。
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Office 365 無法使用這兩個 Azure 機碼存放庫機碼的單一資料加密原則 (DEP) 時，可以使用可用性金鑰變更為新的 DEP Office 365 決定是否要使用的可用性金鑰根據是否有不同的服務可用性使用者初始化的活動，例如使用者下載電子郵件至 Outlook 用戶端或系統起始活動，例如信箱內容編製索引或 eDiscovery 搜尋時觸發程序。
  
Office 365 會依照此程序以回應使用者起始動作來決定是否要使用的使用者信箱的可用性機碼：
  
1. Office 365 讀取 DEP 對其指派信箱以判斷 Azure 機碼存放庫中的兩個客戶機碼的位置。
    
2. Office 365 隨機選擇其中一個兩個客戶機碼從 DEP 並將要求傳送至 Azure 機碼存放庫來解除包裝客戶金鑰 DEP 機碼。
    
3. 如果將要求重新解除包裝 DEP 重要使用客戶鍵會失敗並傳回錯誤、 Office 365 第二個將要求傳送至 Azure 機碼存放庫，這次是指示其使用替代 （秒） 客戶機碼。
    
4. 如果第二個要求給解除包裝 DEP 金鑰使用客戶重要失敗而且會傳回錯誤，Office 365 會檢查這兩個要求的結果：
    
  - 如果檢查判斷錯誤不執行動作的反映客戶 identity 由明確巨集指令，Office 365 會使用可用性金鑰解密 DEP 機碼。DEP 鍵然後用以解密信箱金鑰並完成使用者要求。
    
    在此例中 Azure 金鑰儲藏室列傳原因是無法回應或無法連線。Office 365 內沒有決定如果客戶刻意已撤銷存取權之按鍵的方式。
    
  - 如果檢查指出該謹慎地做出動作所呈現客戶金鑰無法使用已則不會使用可用性金鑰、 使用者要求失敗，和使用者會收到錯誤訊息，例如登入失敗。
    
    在這種情況下，客戶是由注意會影響服務，和客戶機碼的條件為不健康。例如，如果客戶組織中所有信箱使用單一 DEP，客戶可能會遇到時遇到的普遍失敗的使用者無法存取其信箱的位置。這可確保這兩個客戶機碼不健康時，客戶由注意需要修正的狀況及服務還原到狀況良好狀態。
    
 **使用可用性金鑰的 Office 365 服務的程式碼所起始的動作。**
  
Office 365 服務的程式碼一律具有有效的登入權杖並不會遭到封鎖。因此，直到已刪除的可用性金鑰，因此可以動作起始，或是給 Office 365 服務的程式碼，例如搜尋索引建立內部或移動的信箱。
  
 **使用可用性金鑰復原重要遺失。**
  
您可以使用可用性機碼從相關聯相同的 DEP 所述的常見問題集項目答覆"如果我金鑰已毀損，如何可以我復原？"這兩個 Azure 機碼存放庫機碼故障中復原。
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>如何可用性金鑰搭配使用 SharePoint Online 和 OneDrive for Business？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint Online 和 OneDrive for Business 架構和實作客戶金鑰及可用性的機碼是不同 Exchange Online 和 Skype for Business。
  
當客戶會移至客戶受管理的機碼時，Office 365 建立承租人特定中間鍵 (TIK)。Office 365 加密 TIK 兩次，一次使用每個客戶機碼，並將儲存 TIK 的兩個加密的版本。儲存 TIK 的加密的版本，並 TIK 與客戶機碼僅可以解密的郵件。TIK 然後用來加密網站機碼，然後用來加密 blob 機碼。其本身的 blob 加密和儲存在 Microsoft Azure Blob 存放區服務。
  
Office 365 會依照此程序來存取 blob 具有檔案的客戶資料：
  
1. 解密使用客戶金鑰 TIK。
    
2. 您可以使用解密的 TIK 解密網站機碼。
    
3. 使用已解密的站台金鑰解密 blob 機碼。
    
4. 您可以使用解密的 blob 金鑰解密 blob。
    
當解密 TIK、 Office 365 問題兩個解密要求至 Azure 機碼存放庫稍微位移。若要完成的第一個提供於取消其他要求的結果。
  
以防客戶失去存取其客戶機碼，Office 365 也會 TIK 加密與可用性機碼，並將此儲存搭配使用每個客戶金鑰加密 TIKs。使用可用性金鑰加密 TIK 只適用於客戶呼叫 Microsoft 當他們有遺失存取其機碼，，意外或惡意編列復原路徑。
  
可用性及向外的原因，已解密的 TIKs 快取中的時間限制記憶體快取。兩個小時才能 TIK 快取設定為過期，Office 365 嘗試解密每個 TIK。解密 TIKs 延伸的快取週期。如果 TIK 解密大量時間而失敗 Office 365 會產生提醒通知工程之前的快取到期時間。只有當客戶呼叫 Microsoft Office 365 會啟動復原作業，包括解密 TIK 與一組新的 Microsoft 的秘密存放區和 onboarding 再次使用 [解密租用戶中儲存與可用性金鑰 TIK客戶提供 Azure 機碼存放庫機碼。
  
從今天、 客戶機碼被涉及 Azure blob 存放區，但不是 SharePoint Online 的清單項目或中繼資料儲存在 SQL 資料庫中儲存的 SharePoint Online 檔案資料之加密與解密鏈結中。Office 365 不使用的可用性金鑰 SharePoint Online 或 OneDrive for Business 以外，前文所述案例為起始的客戶。客戶 Lockbox 受人工的存取權的客戶資料。
  
## <a name="how-is-customer-key-licensed"></a>如何授權客戶金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

客戶機碼是 Office 365 企業版套件、"E5"及進階規範 SKU 中提供。此外，客戶必須也購買使用 Azure 機碼存放庫的適當的授權。
  
從客戶機優點每位使用者必須如果他們想要由客戶機碼所涵蓋授權。
  
SharePoint Online 的 Office 365 系統管理員設定客戶機碼也需要授權，才能執行安裝步驟。此外，此功能的優點使用者需要用來將授權給-這包括網站擁有人和任何使用者存取使用客戶金鑰加密的一或多個網站上的檔案。外部使用者不需要授權存取使用客戶金鑰加密的一或多個網站上的檔案。
  
Exchange online 必須授權"user"信箱和 「 郵件使用者 」 的信箱。所有其他人，例如共用信箱不需要有授權客戶機碼。若要檢查您的 Exchange Online 信箱正確授權，請執行下列 cmdlet：
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

如果字串 BPOS_S_EquivioAnalytics 存在，則信箱適當的授權。如果不是，您必須套用適當的權限才可使用此信箱的客戶金鑰功能。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>可以啟用試用訂閱的客戶金鑰吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

[否]。根據定義，試用版訂閱有限制的存留期。裝載於試用版訂閱的加密金鑰還會遺失試用存留期的結尾。由於 Microsoft 不能與無法防止客戶重要的客戶資料放在試用版訂閱中，會禁止客戶金鑰搭配試用版訂閱。
  
## <a name="how-much-will-using-customer-key-cost"></a>多少會使用客戶金鑰成本吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

除了授權所需的客戶索引鍵、 客戶將可能會形成機碼存放庫使用的成本。[Azure 機碼存放庫定價的詳細資訊](https://azure.microsoft.com/en-us/pricing/details/key-vault/)說明成本模型，並將會協助進行評估。沒有預測因為使用模式而異可能會形成任何客戶會實際成本方法。經驗顯示成本很低及通常落在範圍的 $0.002 以 $0.005 每位使用者每月加上 HSM 備份金鑰的成本。成本也將會根據由客戶及 Azure 使用的儲存總量 Azure 機碼存放庫記錄檔選擇的記錄組態而不同。 
  
## <a name="for-more-information"></a>相關資訊
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

若要開始使用客戶金鑰，請參閱[控制您使用客戶金鑰的 Office 365 中的資料](controlling-your-data-using-customer-key.md)。
  

