---
title: Office 365 技術控制措施
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： Microsoft 的技術控制 practices for Office 365 的概觀。
ms.openlocfilehash: 3fe7f47a2a1903d17c5240a0efec1c2abb94a25d
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090765"
---
# <a name="office-365-technology-controls"></a>Office 365 技術控制措施 

Microsoft 會使用數種工具和技術，以控制、 管理及稽核客戶資料的存取 Exchange Online 和 SharePoint Online，包括 Lockbox 和客戶 Lockbox、 多重要素驗證等等。Yammer Enterprise 使用類似控制項[Yammer Enterprise 存取控制項](office-365-yammer-enterprise-access-controls.md)中所述。

Office 365 工程師零出位置存取 Office 365 的客戶資料，而且必須經過核准程序包含 Microsoft 和 – 如果客戶授權客戶 Lockbox 功能的 Exchange Online 與 SharePoint Online – 客戶核准之前可以發生服務作業的客戶資料的存取。當授與核准時，特定服務的管理帳戶的佈建剛剛時間剛足夠來執行工作所需的服務要求的存取權。

## <a name="lockbox-and-customer-lockbox"></a>Lockbox 和客戶 Lockbox
雖然極罕見，客戶無法從可能會公開 Microsoft 工程師客戶的內容以協助他們有問題的 Microsoft 要求協助。以控制存取至 Exchange Online (包括商務資料儲存在使用者的信箱中的任何 Skype （Skype for Business 涵蓋範圍不包含 Skype 會議廣播錄製或上傳到會議使用者所擁有的內容）) 與 SharePoint Online （其中包含 OneDrive for Business）、 Microsoft 使用呼叫 Lockbox 存取控制系統。任何 Microsoft 工程師可以存取所有的 Exchange Online 或 SharePoint Online 系統或資料之前，必須提交使用 Lockbox 存取要求。使用 Lockbox，則需要提高權限存取所有 Exchange Online 或 SharePoint Online。

Lockbox 處理要求的權限可授與工程師重新執行服務內的操作與管理功能。透過 Lockbox，必須由之前取得能夠存取客戶資料工程師管理員核准的工程師送出要求。在管理員核准時工程師有時間限制與範圍限制資料的存取權客戶能夠在客戶的問題。

Office 365 的客戶 Lockbox 可協助您符合法規責任，例如找到 FedRAMP 和 HIPAA，如果您需要進行中的程序的明確資料存取授權。在極罕見的執行個體時的 Microsoft 服務工程師需要存取您的資料，您存取授與該只以解決問題所需的資料及有限的時間。支援工程師所採取的動作會記錄稽核用途和存取透過[Office 365 管理活動 API](https://msdn.microsoft.com/library/office/dn707383.aspx)和[安全性和規範中心 」](http://protection.office.com/)。客戶 Lockbox 客戶插入 Lockbox 核准程序，並提供控制授權的 Microsoft 存取其 Exchange Online 或 SharePoint Online 內容的服務作業的能力。

>**請注意**： 客戶 Lockbox 是可在[Office 365 企業版 E5](https://products.office.com/business/office-365-enterprise-e5-business-software)以及附加元件購買，但必須採取手動巨集指令在 Office 365 系統管理中心 (在 [服務設定 |客戶 Lockbox) 若要啟用它。如需詳細資訊，請參閱[Office 365 客戶 Lockbox 要求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。

Lockbox 系統所處理的 Exchange Online 與 SharePoint Online 的所有服務要求。和客戶 Lockbox 與任何可能強制執行這些服務具有衝擊客戶資料的存取權的服務作業會通過 Lockbox 核准程序，然後啟用核准或拒絕要求之後客戶。
 
*圖 1-客戶 Lockbox 工作流程*

如果要求遭拒由客戶、 Microsoft 工程師將不會有客戶的內容的存取權並將無法完成服務作業。如果要求由客戶核准、 Microsoft 工程師將具有受限剛剛-時間內容的存取權的客戶透過受監視及限制的管理介面。Lockbox 和客戶 Lockbox 所有核准的存取是唯一的使用者，讓工程師努力其處理的客戶資料可進行追蹤。

## <a name="just-in-time-access"></a>剛-時間存取
Microsoft 使用 Office 365 剛剛-時間 (JIT) 存取當中進一步減輕認證竄改和側面攻擊的風險。JIT 移除常設系統管理存取服務，並取代的功能提升到這些角色隨選這些權利。從系統管理員移除持續性的權限可確保僅當他們所需並移除為公司的認證竊取情況所造成的風險所提供的認證。

JIT 存取模型需要要求提高的權限的系統管理負有有限期間工程師。此外，OCEs 使用電腦產生的複雜密碼與所建立的暫時帳戶並授與只允許他們執行工作所需的角色。例如，系統管理存取權授與的 Lockbox 是時間繫結和授與存取權的時間取決於所要求的角色。工程師指定 Lockbox 系統要求期間所需的時間存取的持續期間。Lockbox 系統將會拒絕的要求其中所要求的時間超過最大允許提高權限的時間。提高權限要求的到期後移除系統管理存取和到期暫時帳戶。

時獲得授權，並核准存取 （例如偵錯系統）、 工程師接收所產生的授權系統核准提高權限存取要求每次單次使用系統管理密碼。此密碼會由工程師複製到安全的密碼、 不同的 Microsoft 企業環境、 工程師認證及良好僅針對提升權限的存取已核准的工作階段。

## <a name="constrained-management-interfaces"></a>限制的管理介面
OCEs 使用兩種管理介面來執行管理工作： 透過安全的終端機服務閘道 (TSGs) 和遠端 PowerShell 遠端桌面。在這些管理介面有軟體原則及放置哪些應用程式可執行的重要限制哪些命令和 cmdlet 的存取控制可用。 

Office 365 伺服器並行工作階段限制一個工作階段的每個服務小組系統管理員，每部伺服器。TSGs 設定以允許使用者只有單一並行工作階段並不允許多個工作階段。TSGs 允許 Office 365 服務小組管理員連線至多部伺服器同時，使用每部伺服器，在單一工作階段，讓系統管理員可以有效地執行其職責。服務小組管理員沒有 TSGs 自己的任何權限。TSG 僅用於強制執行多重要素驗證 (MFA) 和加密需求。服務小組管理員會連接至特定伺服器透過 TSG，一旦特定伺服器會強制執行系統管理員每一個工作階段的限制。

使用方式限制與 Office 365 人員連線及設定需求的 Active Directory 群組原則所建立。這些原則包含下列特性：
- TSGs 設定為使用[FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 驗證的加密
- TSG 工作階段已設為 30 分鐘的閒置時間之後中斷
- TSG 工作階段設定為自動記錄關閉 24 小時之後

連線至 TSGs 還需要 MFA 使用不同的實體智慧卡及工程師 Microsoft 公司認證不同的帳戶。工程師會發出不同智慧卡各種平台和機密資料管理平台可用以確保安全儲存的認證。TSGs 使用 Active Directory 群組原則以控制哪些使用者可以登入遠端伺服器、 數允許的工作階段與閒置逾時設定。其他原則已備妥限制存取允許應用程式和限制網際網路存取。

除了使用特別設定 TSGs 為遠端存取的 Exchange Online 可讓使用者與服務工程師作業角色存取特定使用遠端 PowerShell 的實際執行伺服器上的系統管理功能。為達成此目的，使用者必須授權唯讀 （偵錯） 存取 Office 365 實際執行環境。最低權限呈報會啟用它已啟用 TSGs Lockbox 程序的方式相同。

遠端存取已有負載平衡的虛擬 IP 做為存取的單一資料點的每個資料中心。可執行遠端 PowerShell 指令程式根據中存取宣告取得在驗證期間識別的最低權限層級。這些指令程式是可存取及執行由使用者連線使用此方法僅系統管理功能。遠端 PowerShell 用來限制的命令可工程師，根據透過 Lockbox 程序授與存取權的層級範圍。例如 Exchange Online 中 Get-mailbox 可能可以聯繫，但不是 Set-mailbox。
