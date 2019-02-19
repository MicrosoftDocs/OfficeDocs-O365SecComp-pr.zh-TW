---
title: Office 365 加密 Skype、 OneDrive、 SharePoint 及 Exchange
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 加密 Skype、 OneDrive、 SharePoint 及 Exchange Online 的描述。
ms.openlocfilehash: c8f3658a2d76bd9184babe7729236309ec1feb30
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "29664139"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Skype for Business、 OneDrive for Business、 SharePoint Online、 and Exchange Online 的 office 365 加密

Office 365 是提供廣泛的多層保護在高度安全環境： 實體的資料中心安全性、 網路安全性、 存取安全性、 應用程式安全性及資料安全性。

## <a name="skype-for-business"></a>商務用 Skype
Skype 商務客戶資料可能會儲存在檔案或上傳的會議參與者的簡報的表單中的其餘部分。Web 會議伺服器加密 AES 使用 256 位元金鑰的客戶資料。加密的客戶資料會儲存在檔案共用。每個客戶資料的一部分使用不同的隨機產生的 256 位元金鑰加密。客戶資料的一部分在會議中共用、 Web 會議伺服器會指示以下載加密的客戶資料透過 HTTPS 的會議用戶端。以便進行解密的客戶資料，它傳送至用戶端的對應機碼。Web 會議伺服器也會驗證會議用戶端之前允許用戶端存取會議的客戶資料。加入 Web 會議、 時每個會議用戶端會與會議焦點元件執行前端伺服器內透過 TLS 先建立 SIP] 對話方塊。會議剛好的焦點傳給會議用戶端 Web 會議伺服器所產生驗證 cookie。會議用戶端然後連接到 Web Conferencing server 呈現驗證之伺服器的驗證 cookie。

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和商務用 OneDrive
在 SharePoint Online 中的所有客戶檔案會都受到一定是侷限在單一租用戶的唯一的每個檔案機碼。機碼包括建立和管理 SharePoint Online 服務，或使用客戶索引鍵時，建立與受管理的客戶。檔案上傳、 時加密是由執行 SharePoint Online 中的上傳要求內容之前傳送至 Azure 的儲存裝置。下載檔案時，SharePoint Online 擷取加密的客戶 Azure 儲存的資料為基礎的獨特的文件識別碼和解密的客戶資料之前傳送給使用者。Azure 存放具有無法解密，或甚至是識別或了解客戶資料。所有加密與解密的相同系統的強制執行租用戶隔離，亦即 Azure Active Directory 與 SharePoint Online 中都發生。

Office 365 中的數種工作負載會將資料儲存在 SharePoint Online，包括將所有檔案都儲存在 SharePoint Online 和 OneDrive for Business，它會使用其儲存的 SharePoint Online 的 Microsoft 小組。儲存在 SharePoint Online 中的所有客戶資料加密 （具有一或多個 AES 256 位元索引鍵），且分散於資料中心，如下所示。（此加密程序的每一個步驟是的 FIPS 140-2 層級 2 驗證。如需有關 FIPS 140-2 性的詳細資訊，請參閱[FIPS 140-2 規範](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))）。
- 每個檔案分割為一或多個區塊，視檔案大小而定。每個區塊會使用其唯一 AES 256 位元金鑰進行加密。
- 更新檔案，則當更新的處理方式的相同方式： 變更分割為一或多個區塊和每個區塊加密具有不同的唯一索引鍵。
- 這些區塊 – 檔案、 檔案及更新的差異部分 – 儲存為 blob 在 Azure 的存放區中的隨機分散於多個 Azure 儲存帳戶。 
- 這些區塊的客戶資料的加密金鑰組為本身加密。
   - 用來加密 blob 的機碼儲存在 SharePoint Online 內容資料庫。
   - 內容資料庫會受到資料庫的存取控制及靜態加密。加密被執行[Azure SQL 資料庫](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)中使用[透明資料加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde)(TDE)。（azure SQL 資料庫是支援例如關聯式資料、 JSON 空間，以及 XML 結構的 Microsoft Azure 中的一般用途的關聯式資料庫服務）。在 SharePoint Online、 不在租用戶層級的服務層級都是這些機密資料。（有時稱為主索引鍵） 這些機密資料儲存在稱為 「 機碼儲存在個別安全儲存機制。TDE 提供在作用中的資料庫和資料庫備份和交易記錄檔的其餘部分的安全性。 
   - 當客戶提供選擇性的機碼時，客戶機碼儲存在 Azure 機碼存放庫，並服務使用按鍵來加密租用戶金鑰，這用來加密網站金鑰，然後用來加密檔案層級索引鍵。基本上時客戶提供金鑰, 已導入新的金鑰階層。
- 用來重新組合之檔案的對應會儲存加密金鑰，分開解密它們所需之主要金鑰及內容資料庫中。
- Azure 存放區中的每個帳戶有自己的唯一認證每種存取類型 （讀取、 寫入、 列舉和刪除）。每一組認證保存在安全的金鑰存放區並定期重新整理。如前文所述，有三種不同存放區各有不同的函數：
- 客戶資料會儲存為 Azure 存放在加密 blob。每個區塊的客戶資料的按鍵是加密和分開儲存在內容資料庫中。本身的客戶資料會保留任何線索來方式進行解密。
- 內容資料庫是 SQL Server 資料庫。它會保留找出與重新組合客戶資料 blob 保存在 Azure 儲存為加密那些 blob 所需的按鍵所需的地圖。不過，機碼設為加密 （如上所述） 並保存在不同的索引鍵存放區本身擷取。
- 金鑰存放區已從內容資料庫與 Azure 儲存實體分開。它會保留內容資料庫中的加密金鑰組保留每個 Azure 儲存容器和主要金鑰的認證。

每個 – Azure blob 存放區、 內容資料庫及索引鍵存放區 – 這三個儲存元件是實體分開。保存在任何一種元件的資訊為其本身上無法使用。無法存取所有三個，很難擷取至區塊的機碼、 解密使其可、 索引鍵關聯及其對應的區塊、 解密每個區塊，或重建其構成區塊中的文件的按鍵。

保護資料中心的機器上的實體磁碟磁碟區、 的 BitLocker 憑證儲存在安全存放庫 （SharePoint Online 秘密存放區） 受保護伺服器陣列的索引鍵。

保護個別 blob 機碼下 TDE 鍵會儲存在兩個位置：
- 安全存放庫以裝載 BitLocker 憑證以及保護伺服器陣列鍵 ； 所與
- 在 [受管理的 Azure SQL 資料庫的安全存放庫。

SharePoint Online 中的機密儲存和委派給每個 SharePoint Online 的伺服器陣列所需，也可以保留可用來存取 Azure 儲存容器的認證。這些認證是 Azure 儲存 SAS 簽章，個別的認證來讀取或寫入資料，以及套用使其自動-到期每 60 天的原則。不同的認證用來讀取或寫入資料 （不可同時具備） 與 SharePoint Online 的伺服器陣列不會授與權限來列舉。

> 附註的 Office 365 美國政府客戶、 資料 blob 儲存在 Azure 美國政府存放區中。此外，存取 Office 365 美國政府中的 SharePoint Online 機碼僅限於已特別篩選的 Office 365 人員。Azure 美國政府作業人員用來加密資料 blob 的 SharePoint Online 主要儲存區不需要存取。

如需 SharePoint Online 和 OneDrive for Business 的資料加密的詳細資訊，請參閱[OneDrive for Business 和 SharePoint Online 中的資料加密](https://technet.microsoft.com/en-us/library/dn905447.aspx)。

### <a name="list-items-in-sharepoint-online"></a>SharePoint Online 中的清單項目
會較小的區塊客戶臨或所建立的資料可以更動態 live 網站內，例如使用者建立的清單中的列、 SharePoint Online 的部落格、 或 SharePoint Online 的 wiki 頁面內的項目中的個別文章的清單項目。清單項目是儲存在內容資料庫 （Azure SQL 資料庫） 與以 TDE 保護。

## <a name="encryption-of-data-in-transit"></a>傳輸中資料的加密
在OneDrive for Business 和 SharePoint Online 中，資料進出資料中心的方式有兩種。
- **用戶端與伺服器之間的通訊**通訊 OneDrive for Business 跨網際網路使用 SSL/TLS 連線。所有的 SSL 連線會建立使用 2048年位元金鑰。
- **資料中心之間移動資料**的資料中心之間移動資料的主要原因是啟用嚴重損壞修復的地理位置複寫。例如，SQL Server 交易記錄檔與 blob 存放區差異旅行社沿著此管道。雖然此資料已經會使用私人網路傳輸，其進一步受到適合的類別加密。


## <a name="exchange-online"></a>Exchange Online
Exchange Online 使用 BitLocker 所有信箱資料，並[BitLocker 加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)中所述的 BitLocker 組態。服務層級加密加密層級的信箱的所有信箱資料。 

服務層加密，以及 Office 365 支援客戶金鑰、 內建置於服務加密。客戶機碼是 Microsoft managed 金鑰] 選項也是在 Microsoft 的藍圖的 Exchange Online 服務加密。此方法的加密提供由於它所提供之伺服器管理員及解密的資料所需的密碼編譯按鍵區隔而且加密直接套用至資料 （在未提供 BitLocker 增加的保護使用 BitLocker，由它套用在邏輯磁碟磁碟區加密對比） 從 Exchange 伺服器中複製任何客戶資料仍會保留加密。

Exchange Online 服務加密的範圍會儲存在 Exchange Online 中的其餘部分的客戶資料。（Skype for Business 幾乎所有使用者產生將內容都儲存在使用者的 Exchange Online 信箱與因此繼承的 Exchange Online 服務加密功能）。
