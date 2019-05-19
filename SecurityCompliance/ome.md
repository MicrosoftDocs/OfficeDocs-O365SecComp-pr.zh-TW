---
title: Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 使用 Office 365 郵件加密，組織可以傳送和接收您組織內部和外部的人員之間的加密的電子郵件訊息。 電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。
ms.openlocfilehash: d9716d3021f4190f1679a5d387e9378b60586154
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157585"
---
# <a name="office-365-message-encryption"></a>Office 365 郵件加密

人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。

使用 Office 365 郵件加密，組織可以傳送和接收您組織內部和外部的人員之間的加密的電子郵件訊息。 Office 365 郵件加密的運作與 Outlook.com、 yahoo ！、 Gmail，以及其他電子郵件服務。 電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。
  
本文的其餘部分套用至全新的 OME 功能。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 郵件加密的運作方式

Office 365 郵件加密是 Microsoft Azure 版權管理 (Azure RMS) 屬於 Azure 資訊保護為基礎的線上服務。 這包括加密、 identity 及授權的原則，以協助保護您的電子郵件。 您可以使用版權管理範本、[不要轉寄] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)，並[僅加密選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)來加密郵件。

使用者接著可以加密電子郵件和各種 Office 365 附件使用這些選項。 支援的附件類型的完整清單，請參閱[「 檔案類型所涵蓋當他們會附加至郵件的 IRM 原則 」 中的電子郵件的 IRM 的簡介](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。

身為管理員，您也可以定義郵件流程規則來套用保護。 例如，您可以建立的規則，需要加密的所有郵件傳送給特定收件者，或包含特定字詞，在 [主旨] 行中，且同時指定收件者不能複製或列印郵件的內容。

與舊版的 OME 中，不同的新功能可提供整合的寄件者體驗，無論您在您的組織內或 Office 365 外部的收件者傳送郵件。 此外，收件者收到受保護的電子郵件訊息傳送到 Office 365 帳戶，在 Outlook 2016 或網頁型 Outlook 中不需要採取任何其他的動作，來檢視郵件。 順暢地運作。 也使用其他電子郵件用戶端和電子郵件服務提供者的收件者有較佳的體驗。 如詳細資訊，請參閱[了解如何在 Office 365 中受保護的郵件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)，以及[如何開啟受保護的郵件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

OME 舊版和全新的 OME 功能之間的差異的詳細清單，請參閱[比較 OME 的版本](ome-version-comparison.md)。

當有人傳送符合加密郵件流程規則的電子郵件訊息時，將郵件加密之前傳送它。 使用 Outlook 用戶端來讀取郵件的所有 Office 365 使用者都收到原生、 頂級閱讀加密和權限保護郵件的經驗，即使它們不在 [寄件者相同的組織。 支援的 Outlook 用戶端包括 Outlook 桌面、 Outlook Mac、 Outlook mobile 上 iOS 和 Android，和 Outlook 網頁 （原先稱為 Outlook Web App）。
  
收件者加密郵件的接收傳送到其 Outlook.com、 Gmail 和 Yahoo 帳戶的已加密或權限保護郵件接收將其導向至 OME 入口網站可以輕易地認證使用 Microsoft 帳戶，Gmail，包裝函式郵件或Yahoo 認證。
  
讀取加密或權限保護郵件以外的 Outlook 用戶端上的使用者也使用 OME 入口網站來檢視所收到的加密和權限保護郵件。

此外，如果受保護的郵件寄件者位於 GCC High 和收件者是外部 GCC 高，包括商業 Office 365 使用者、 Outlook.com 使用者和使用者的其他電子郵件提供者，例如 Gmail 中，收件者會收到重新導向至包裝函式郵件收件者所在可以閱讀和回覆郵件 OME 入口網站。 否則，如果寄件者和收件者都 GCC 高的環境中，然後使用 Outlook 用戶端來讀取郵件的收件者收到原生、 頂級閱讀加密和權限保護郵件的經驗，即使它們不在相同組織中作為寄件者。 如需在 GCC High 的不同經驗的詳細資訊，請參閱[比較 OME 的版本](ome-version-comparison.md)。
  
我們已增加訊息和附件，您可以使用 ome 一次來加密的大小限制。 如需限制的詳細資訊，請參閱 < <b0>Exchange Online 限制</b0>。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>OME 掌握 Office 365 進階郵件加密的運作方式

Office 365 進階郵件加密可讓您建立多個品牌範本，因此您可以微調控制收件者的郵件，並建立自訂品牌的經驗來支援各種不同的組織結構。

您在 Office 365 協助進階郵件加密符合規範，需要更有彈性控制外部收件者的存取權加密的電子郵件。 使用進階郵件加密在 Office 365 中，以系統管理員身分，您可以控制自動偵測敏感資訊類型 （例如 PII、 金融或狀況識別碼） 或關鍵字，以增強的原則與組織外共用機密電子郵件透過加密的電子郵件的安全 web 入口網站來存取由過期的保護。 此外，為您可以進一步控制透過 Office 365 入口網站外部存取的任何時間撤銷存取電子郵件加密的電子郵件系統。

郵件被撤銷及到期僅適用於您的使用者傳送給您的 Office 365 組織外收件者的電子郵件。 此外，收件者必須透過入口網站來存取電子郵件。 為了確保收件者使用入口網站來接收電子郵件，您設定適用於包裝函式的自訂品牌範本。 然後，您套用郵件流程規則中的品牌範本。 如需進階郵件加密的詳細資訊，請參閱 < <b0>Office 365 進階郵件加密</b0>。

## <a name="defining-rules-for-office-365-message-encryption"></a>定義 Office 365 郵件加密的規則

Exchange Online 和 Exchange Online Protection 的系統管理員定義郵件流程規則是一種方式來啟用 Office 365 郵件加密的新功能。 這些規則決定應該在哪些條件電子郵件加密的郵件。 當規則設定的加密巨集指令時，任何符合規則條件的郵件加密之前，他們所傳送。
  
郵件流程規則有彈性，讓您合併條件，因此您可以符合單一規則中的特定安全性需求。 例如，您可以建立規則以加密包含指定的關鍵字，而且寄送到外部收件者的所有郵件。 Office 365 郵件加密的新功能也加密的加密的電子郵件的收件者的回覆。
  
如需如何建立郵件流程規則，以利用全新的 OME 功能的詳細資訊，請參閱 < <b0>Define Rules for Office 365 Message Encryption</b0>。
  
## <a name="get-started-with-the-new-ome-capabilities"></a>全新的 OME 功能快速入門

如果您已準備好要開始使用您的組織內全新的 OME 功能，請參閱 <<c0>設定新的 Office 365 郵件加密功能。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>傳送、 檢視和回覆加密的電子郵件訊息

使用 Office 365 郵件加密，使用者可以從 Outlook 和 outlook 網頁版傳送加密的電子郵件。 此外，系統管理員可以設定自動加密根據關鍵字比對或其他條件的電子郵件在 Office 365 中的郵件流程規則。
  
收件者的已加密郵件身為 Office 365 組織中無法讀取順暢地在任何版本的 Outlook，包括電腦版 Outlook、 Outlook for Mac、 網頁型 Outlook、 Outlook for iOS 和 Android 版 Outlook 中的這些郵件。 收到其他電子郵件用戶端上的已加密的郵件的使用者可以在 OME 入口網站中檢視訊息。
  
如需如何傳送和檢視加密的郵件的詳細指引，看看下列文章：
  
|||
|:-----|:-----|
|請閱讀本文...]  <br/> |如果您是...  <br/> |
|[了解 Office 365 中受保護的郵件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |使用者想要深入了解如何加密訊息的工作，且您可以使用哪些選項。  <br/> |
|[如何開啟受保護的郵件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |想要讀取受保護的郵件已傳送至您的使用者。 本文包含資訊閱讀在數個版本的 Outlook，並從不同的電子郵件帳戶，例如 gmail 和 yahoo ！ 包括 Office 365 外部的郵件 帳戶。  <br/> |
|[傳送、 檢視和回覆加密郵件在 Outlook 中](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |想要傳送、 檢視或從 Outlook 回覆加密的郵件使用者。 即使您不屬於 Office 365 組織，仍會接收傳送至您在 Outlook 中的加密郵件的通知。 如需如何檢視和回覆加密郵件傳送從 Office 365 的指示使用這篇文章。  <br/> |
|[傳送數位簽章或加密郵件](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |使用者想要傳送、 檢視或回覆加密的郵件使用 Outlook for mac。 本文也會涵蓋使用 OME，例如 S/MIME 以外的加密方法。  <br/> |
|[在 Android 裝置上檢視加密的郵件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |如果使用者已收到郵件加密與 Office 365 郵件加密您的 Android 裝置上，您可以使用免費 OME 檢視器應用程式，檢視郵件並傳送加密的回覆。 本文說明如何。  <br/> |
|[在 iPhone 或 iPad 上檢視加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |如果使用者已收到郵件加密與 Office 365 郵件加密在 iPhone 或 iPad 上的，您可以使用免費 OME 檢視器應用程式，檢視郵件並傳送加密的回覆。 本文說明如何。  <br/> |
||