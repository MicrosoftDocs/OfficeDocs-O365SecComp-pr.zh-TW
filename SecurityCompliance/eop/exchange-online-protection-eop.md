---
title: 'Exchange Online Protection '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: 以下是您應該要知道您開始使用 EOP 之前的一些事項。
ms.openlocfilehash: fc5ea726de190395407952ceac69c4c682ac8f67
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341744"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection 

歡迎使用 Microsoft Exchange Online Protection (EOP) 託管的電子郵件篩選服務。開始使用 EOP 和此內容前，您必須先注意下列事項：
  
- 若要深入了解 EOP，請查看 [Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)。其他有用的資源包括＜[Exchange Online Protection 概觀](exchange-online-protection-overview.md)＞、＜[EOP 一般常見問題集](eop-general-faq.md)＞和＜[EOP 功能](eop-features.md)＞，以及＜[Exchange Online Protection 首頁](https://go.microsoft.com/fwlink/?LinkId=279912)＞。
    
- 若要開始使用 EOP，新客戶請前往[設定 EOP 服務](set-up-your-eop-service.md)。本主題提供可協助 EOP 順利運作的步驟。您也可以觀看＜[EOP 快速入門影片](videos-for-getting-started-with-eop.md)＞上播放的一系列簡介視訊。
    
- 如果您需要其他協助或想要分享意見，[EOP 論壇](https://go.microsoft.com/fwlink/?LinkId=285351)是很理想的起點。 
    
- 您可以使用任何 TechNet 頁面右上方的 [匯出] 選項來新增主題，然後將它們匯出至 PDF 檔案。 
    
## <a name="eop-help-for-administrators"></a>適用於系統管理員的 EOP 說明

適用於 EOP 系統管理員的說明內容由下列頂層類別組成：
  
- [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 介紹 EOP 的運作方式，並提供其他資訊連結。 
    
- [EOP 功能](eop-features.md) 提供一份 EOP 中可用的功能清單。 
    
- [EOP 快速入門影片](videos-for-getting-started-with-eop.md) 以詳述一般設定工作的一系列視訊來介紹 EOP。 
    
- [設定 EOP 服務](set-up-your-eop-service.md) 提供 EOP 服務的設定步驟，以及其他資訊的連結。 
    
- [從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md) 說明從其他電子郵件保護產品切換到 EOP 的程序。 
    
- [管理收件者和 EOP 中的系統管理員角色群組](manage-recipients-and-admin-role-groups-in-eop.md)說明如何管理收件者，以及如何將使用者指派給系統管理員角色群組。 
    
- [EOP 中的郵件流程](mail-flow-in-eop.md) 說明如何使用連接器來設定自訂郵件流程案例、如何管理與服務相關的網域，以及如何啟用目錄架構邊緣封鎖 (DBEB) 功能。 
    
- [設定 EOP 的最佳作法](best-practices-for-configuring-eop.md) 說明在您設定和佈建服務之後的建議組態設定和考量。 
    
- [郵件原則及 EOP 中的符合性](messaging-policy-and-compliance-in-eop.md)說明如何使用 Exchange 郵件流程規則 （也稱為傳輸規則） 來強制執行特定公司規定與政策，以及如何使用稽核報告來追蹤服務的組態變更。 
    
- [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx) 說明垃圾郵件篩選和惡意程式碼篩選，以及顯示如何進行自訂以滿足貴組織的需求。此外，還說明系統管理員和使用者可以對隔離郵件執行的工作。 
    
- [Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md) 說明可用的報告和疑難排解工具。 
    
- [Exchange 系統管理中心在 Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md)說明如何存取和瀏覽 Exchange 系統管理中心 (EAC) 管理介面，以便管理 EOP 服務。 
    
- [Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx) 提供遠端 PowerShell 的相關資訊，讓您可以從命令列管理 EOP 服務。 
    
- [EOP 的說明和支援](help-and-support-for-eop.md) 提供有關取得說明和技術支援的資訊。 
    
## <a name="eop-help-for-end-users"></a>適用於使用者的 EOP 說明
<a name="sectionSection1"> </a>

可協助 EOP 使用者來管理垃圾郵件的說明內容包含下列主題：
  
- [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx) 說明使用者如何在垃圾郵件隔離使用者介面中尋找和釋出其自己的垃圾隔離郵件，並選擇性地向 Microsoft 報告這些郵件不是垃圾郵件。 
        
- [提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)描述使用者可以提交垃圾郵件 （垃圾） 和非垃圾郵件 （非垃圾郵件） 郵件提交給 Microsoft 的不同方式。本主題包含 Microsoft Outlook 和網頁 （原先稱為 Outlook Web App） 上的 Outlook 中可用的報告工具的連結。 
    
- [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md) 描述使用者可以如何提交惡意程式碼使其通過篩選器，或者提交錯誤識別為惡意程式碼的檔案。 
    
- 使用者可以新增特定使用者或網域至安全的寄件者或封鎖的寄件者清單在 Outlook 或網頁型 Outlook 中設定其垃圾郵件設定。請注意，來自封鎖的寄件者傳送的郵件已標示為垃圾郵件，不會被拒絕，這表示他們可以擷取從垃圾郵件] 資料夾或隔離 （視而定，您的系統管理員已設定的服務來傳送垃圾郵件。）如需詳細資訊，請參閱 <<c0>使用報告訊息增益集。
    
- [EOP 的說明和支援](help-and-support-for-eop.md) 提供有關取得說明和技術支援的資訊。 
    
