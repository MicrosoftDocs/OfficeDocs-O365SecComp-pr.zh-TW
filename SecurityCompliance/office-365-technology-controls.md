---
title: Office 365 技術控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Office 365 的 Microsoft 技術控制作法概述。'
ms.openlocfilehash: ce2e09ce7db881197d2598c52283ecde7ed46e61
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622433"
---
# <a name="office-365-technology-controls"></a>Office 365 技術控制 

Microsoft 會使用多種工具和技術, 控制、管理和審核其線上服務中的客戶資料存取。 這些適用于 Exchange Online、SharePoint Online、密碼箱和客戶加密箱、多重要素驗證等等。 Yammer 會使用[Yammer 企業存取控制](office-365-yammer-enterprise-access-controls.md)中所述的類似控制項。

Office 365 工程師在存取 Office 365 客戶資料時, 可讓您取得任何許可權。 工程師必須先完成 Microsoft 核准程式, 才能存取服務作業的客戶資料。 如果客戶授權 Exchange Online 和 SharePoint Online 的客戶加密箱功能, 則存取客戶資料需要客戶核准。 經過核准後, 服務特定的系統管理帳戶就會為服務要求所需的工作布建即時存取。

## <a name="lockbox-and-customer-lockbox"></a>密碼箱和客戶加密箱

雖然極少, 客戶可以向 Microsoft 索取協助, 以將客戶內容公開給 Microsoft 工程師。 若要控制對 Exchange Online 的存取, Microsoft 會使用稱為「密碼箱」的存取控制系統。 在任何 Microsoft 工程師存取任何 Exchange Online 或 SharePoint Online 系統或資料之前, 必須使用密碼箱提交存取要求。 所有 Exchange Online 和 SharePoint Online 的服務要求都是由密碼箱系統處理。 使用密碼箱和客戶加密箱, 所有核准的存取都可透過唯一的使用者進行追蹤, 讓工程師負責處理客戶資料。

> [!NOTE]
> Exchange Online 包含任何儲存在使用者信箱中的商務用 Skype 資料。 商務用 skype 覆蓋率不包含 Skype 會議廣播錄製或使用者上傳給會議的內容。 SharePoint Online 包含商務用 OneDrive。

密碼箱處理要求的許可權, 可讓工程師在服務內執行操作和系統管理功能。 工程師透過加密箱提交要求, Microsoft 管理員必須先核准要求, 工程師才能存取客戶資料。 管理員核准之後, 工程師對客戶資料有時間限制和範圍限制存取, 以處理客戶的問題。

針對 Office 365 的客戶加密箱, 如果您需要明確資料存取授權的程式, 則可協助您符合合規性義務。 這是某些規範標準 (如 FedRAMP 和 HIPAA) 的必要條件。 客戶加密箱會將您插入密碼箱核准程式, 並讓您能夠控制 Microsoft 對您的 Exchange Online 或 SharePoint Online 內容的授權, 以進行服務作業。

在 Microsoft 服務工程師需要存取資料時, 在極少的情況下, 您只會授與解決問題所需的資料, 並限制在一段時間內。 如果您拒絕存取要求, Microsoft 工程師將無法存取您的內容, 也無法完成服務作業。 如果您核准要求, Microsoft 工程師就會透過受監視和限制的管理介面, 以有限的即時存取內容。

支援工程師採取的動作會記錄下來以供審計使用, 並可透過[Office 365 管理活動 API](https://msdn.microsoft.com/library/office/dn707383.aspx)和[安全性與合規性中心](http://protection.office.com/)進行存取。

>[!NOTE]
> 您可以在[Office 365 企業版 E5](https://products.office.com/business/office-365-enterprise-e5-business-software)中使用客戶加密箱, 做為附加元件購買。 如需詳細資訊，請參閱 [Office 365 Customer Lockbox 要求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。

## <a name="just-in-time-access"></a>即時存取

Microsoft 會使用 Office 365 的即時 (JIT) 存取原則, 以緩解認證篡改風險和側向攻擊。 JIT 會移除服務的持續式系統管理存取, 並將權利取代為根據需求提升至這些角色的能力。 從系統管理員移除持續性存取權限, 可確保認證只有在需要時才可供使用, 並降低認證盜竊風險。

JIT 存取模型要求工程師要求更高的許可權, 以執行系統管理責任。 此外, 工程師會使用以機器產生的複雜密碼建立的暫時帳戶, 並僅授與允許他們執行必要工作的角色。 例如, 由密碼箱所授與的系統管理存取是時間限制的, 而且所授與的存取時間取決於要求的角色。 工程師指定要求存取密碼箱系統所需的時間。 當要求的時間超過提升的最大允許時間時, 加密箱系統會拒絕要求。 到期之後, 系統會移除系統管理存取權, 而暫時帳戶就會過期。

當授權和核准存取時, 工程師會收到由授權系統所產生的一次性管理密碼。 每次核准存取許可權要求時, 都會產生新密碼。 密碼會被覆制到密碼安全, 並與工程師的 Microsoft 公司環境認證分開, 而且只適用于已核准的較高存取會話。

## <a name="constrained-management-interfaces"></a>受限制的管理介面

工程師會使用兩個管理介面來執行管理工作: 透過安全的終端機服務閘道 (TSGs) 和遠端 PowerShell 的遠端桌面。 在這些管理介面中, 軟體原則和存取控制措施對執行哪些應用程式以及可用的命令和 Cmdlet 有很大的限制。

Office 365 伺服器會將同時會話限制為每個服務小組管理員、每個伺服器上的一個會話。 TSGs 只允許使用者使用單一併行會話, 且不允許多個會話。 TSGs 允許 Office 365 服務小組管理員同時連線至多部伺服器, 讓系統管理員可以有效地執行其職責。 服務小組管理員不具備 TSGs 本身的任何許可權。 TSG 僅用於強制執行多重要素驗證 (MFA) 和加密需求。 一旦服務小組管理員透過 TSG 連線至特定伺服器, 特定伺服器就會強制執行每個系統管理員的會話限制。

Office 365 人員的使用限制和連線與設定需求是由 Active Directory 群組原則所建立。 這些原則包含下列特性:

- TSGs 只使用[FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 驗證的加密。
- 在非活動狀態30分鐘後, TSG 會話會中斷連線。
- TSG 會話會在24小時後自動登出。

連線至 TSGs 時, 也需要使用個別的實體智慧卡, 以及與工程師的 Microsoft 公司認證不同的帳戶。 工程師會對各種平臺和機密管理平臺發出不同的智慧卡, 以確保認證的安全儲存。 TSGs 使用 Active Directory 群組原則來控制誰可以登入遠端伺服器、允許的會話數目, 以及閒置超時設定。 其他原則會限制允許的應用程式存取, 並限制網際網路存取。

除了使用特別設定的 TSGs 進行遠端存取之外, Exchange Online 可讓具有服務工程師作業角色的使用者使用遠端 PowerShell 來存取生產伺服器上的特定管理功能。 若要這麼做, 使用者必須獲得 Office 365 實際執行環境的唯讀 (debug) 存取權。 啟用許可權提升的方式, 與使用密碼箱處理常式啟用 TSGs 的方式相同。

針對遠端存取, 每個資料中心都有一個負載平衡的虛擬 IP, 可作為單一存取點。 可用的遠端 PowerShell Cmdlet 是根據驗證期間取得之存取權宣告中所識別的許可權層級。 這些 Cmdlet 僅提供使用此方法連線的使用者可存取的唯一系統管理功能。 遠端 PowerShell 限制可供工程師使用的命令範圍, 而且會根據通過密碼箱處理常式所授與的存取層級而定。 例如, 在 Exchange Online 中, 可能會有取得信箱, 但設定信箱則不會有。
