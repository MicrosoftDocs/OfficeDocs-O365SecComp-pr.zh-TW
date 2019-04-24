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
description: 摘要： Microsoft 技術控制項做法的 Office 365 的概觀。
ms.openlocfilehash: a8dcb65880fc729fc067b2f2bcf25c7db76dbca9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262335"
---
# <a name="office-365-technology-controls"></a>Office 365 技術控制 

Microsoft 會使用數種工具和技術，以控制、 管理和對應地稽核存取客戶資料在 Exchange Online 和 SharePoint Online，包括加密箱和客戶加密箱、 多重要素驗證，以及更多。 Yammer 企業使用類似的控制項，如述[Yammer 企業存取控制](office-365-yammer-enterprise-access-controls.md)。

Office 365 工程師能夠零常設存取 Office 365 客戶資料，且必須經過核准程序，其中包含 Microsoft 與 – 如果客戶授權的客戶加密箱功能 Exchange Online 和 SharePoint Online – 客戶核准，才能存取客戶資料的服務作業可能會發生。 當授與核准時，特定服務的系統管理帳戶會佈建剛時間與剛足夠的存取權執行工作所需的服務要求。

## <a name="lockbox-and-customer-lockbox"></a>加密箱和客戶加密箱
雖然很少發生，客戶可以從可能會暴露在客戶的內容的 Microsoft 工程師，協助他們的問題的 Microsoft 要求協助。 控制存取至 Exchange Online (包括商務資料儲存在使用者的信箱中任何商務用 Skype （Skype for Business 涵蓋範圍不包含 Skype 會議廣播錄製或由使用者上傳至會議的內容）) 和 SharePoint Online （其中包含商務用 OneDrive），Microsoft 會使用稱為 Lockbox 的存取控制系統。 任何 Microsoft 工程師存取所有的 Exchange Online 或 SharePoint Online 的系統或資料之前，他們必須送出使用加密箱存取要求。 針對 Exchange Online 或 SharePoint Online 的所有提高權限存取需要使用加密箱。

加密箱處理要求的權限，授與工程師執行服務內的作業及系統管理功能的能力。 透過加密箱，必須由前獲得的權限存取客戶資料的能力工程師管理員核准的工程師送出要求。 在管理員核准時工程師會有時間限制及範圍限制存取客戶資料處理客戶問題。

Office 365 客戶加密箱可協助您符合合規性責任，例如 FedRAMP 和 HIPAA、 中找到，如果您需要在進行中的程序進行明確資料的存取授權。 在極罕見的執行個體時的 Microsoft 服務工程師需要存取您的資料，您授與該存取才能解決此問題： 所需的資料和有限的時間。 支援工程師所採取的動作用途的稽核記錄，並可透過[Office 365 管理活動 API](https://msdn.microsoft.com/library/office/dn707383.aspx)和[安全性與合規性中心](http://protection.office.com/)。 客戶加密箱客戶插入 Lockbox 核准程序，並讓其能夠控制 Microsoft access 在其 Exchange Online 或 SharePoint Online 內容的服務作業的授權。

>**附註**： 客戶加密箱程式能在[Office 365 企業版 E5](https://products.office.com/business/office-365-enterprise-e5-business-software) ，作為附加元件形式購買，但您必須採取手動的動作，在 Microsoft 365 系統管理中心 (在 [服務設定 |客戶加密箱） 來啟用它。 如需詳細資訊，請參閱 [Office 365 Customer Lockbox 要求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。

Exchange Online 和 SharePoint Online 的所有服務要求是由加密箱系統都處理。 並與客戶加密箱強制執行存取這些服務客戶資料的曝光度與任何服務作業會通過 Lockbox 核准程序，然後可讓客戶核准或拒絕要求之後。
 
*圖 1-客戶加密箱工作流程*

如果由客戶，則會拒絕要求，Microsoft 工程師將不會有的客戶內容存取權，並將無法完成服務作業。 如果要求核准由客戶，Microsoft 工程師將有限剛時間客戶內容存取權的透過監視和限制的管理介面。 加密箱與客戶加密箱，所有核准的存取是唯一的使用者，讓工程師負責其處理客戶資料可進行追蹤。

## <a name="just-in-time-access"></a>剛-階段存取
Microsoft 會使用剛-時間 (JIT) 存取原則的 Office 365，以進一步降低認證竄改和側面攻擊的風險。 JIT 移除服務持續性系統管理存取權，並取代，視需要提升這些角色到這些權利。 從系統管理員移除持續的權限，可確保認證可用的只有當他們所需，而且會移除在認證遭竊的情況下公司所面臨的風險。

JIT access 模型需要工程師要求提升的權限來執行系統管理職責劃分有限的一段。 此外，OCEs 使用暫時帳戶，建立以電腦產生的複雜密碼，並授與只允許他們能執行必要的工作的角色。 例如，系統管理存取權授與的加密箱是時間繫結，並授與存取權的時間量取決於所要求的角色。 工程師指定加密箱系統要求期間所需的時間存取權的持續的時間。 加密箱系統將會拒絕的要求其中所要求的時間超過最大允許提高權限的時間。 在提高權限要求的到期日之後, 移除系統管理存取權，暫時帳戶已過期。

當授權並核准 （例如，若要偵錯系統） 的存取，工程師就會收到所產生的授權系統核准提高權限的存取要求每次使用一次系統管理密碼。 此密碼由工程師複製到安全密碼、 是不同於 Microsoft 公司環境中，工程師的認證，而且僅適合提高權限的存取受到核准的工作階段。

## <a name="constrained-management-interfaces"></a>限制的管理介面
OCEs 使用兩個管理介面來執行系統管理工作： 透過安全的終端機服務閘道 (TSGs) 和遠端 PowerShell 的遠端桌面。 在這些管理介面有軟體原則和存取控制，放置在可執行哪些應用程式的重大限制哪些命令和 cmdlet 可用。 

Office 365 伺服器將並行工作階段限制一工作階段的每個服務小組系統管理員，每個伺服器。 TSGs 設定以允許只會在單一的並行工作階段的使用者，並不允許多個工作階段。 TSGs 允許連線至多部伺服器同時，使用每個伺服器，在單一工作階段，讓系統管理員可以有效地執行其職責劃分的 Office 365 服務小組系統管理員。 服務小組系統管理員沒有 TSGs 本身的任何權限。 TSG 僅用於強制執行多重要素驗證 (MFA) 和加密的需求。 一旦服務小組管理員連線到 TSG 透過特定伺服器，特定的伺服器會強制執行系統管理員每一個工作階段的限制。

流量限制和 Office 365 人員的連線及設定需求的 Active Directory 群組原則所建立。 這些原則包含下列特性：
- TSGs 經設定為使用[FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 驗證的加密
- TSG 工作階段都設定為 30 分鐘一段時間之後中斷
- TSG 工作階段都設定為自動記錄關閉 24 小時之後

連線至 TSGs 也需要使用不同的實體智慧卡及是分開的工程師 Microsoft 公司認證的帳戶的 MFA。 工程師會發出不同智慧卡進行各種平台，而且機密資料管理平台可用以確保安全認證儲存。 TSGs 使用 Active Directory 群組原則以控制可以登入遠端伺服器，允許工作階段及閒置逾時設定的數目。 其他原則已備妥以限制存取以允許應用程式，以及限制網際網路存取。

除了使用特別設定 TSGs 遠端存取 Exchange Online 可讓服務工程師作業角色具有存取特定系統管理功能，使用遠端 PowerShell 的實際執行伺服器上的使用者。 若要這麼做，使用者必須針對 Office 365 實際執行環境的唯讀 （偵錯） 存取權限。 權限提升已啟用它已啟用 TSGs 使用的加密箱程序的方式相同。

遠端存取，如有位於負載平衡的虛擬 IP 做為存取的單一資料點的每個資料中心。 取得在驗證期間存取宣告中所識別的特殊權限層級根據可執行的遠端 PowerShell cmdlet。 這些 cmdlet 都是可存取並執行由使用者連線使用此方法僅系統管理功能。 遠端 PowerShell 用來限制的命令提供給工程師，以根據透過加密箱程序授與的存取層級範圍。 例如，在 Exchange Online 中，Get-mailbox 可能會提供，但不是會將 Set-mailbox。
