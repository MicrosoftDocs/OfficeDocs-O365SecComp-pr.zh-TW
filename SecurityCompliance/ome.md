---
title: Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 與 Office 365 郵件加密，您的組織可以傳送和接收組織內外的人員之間的加密電子郵件訊息。電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。
ms.openlocfilehash: ae66ca79b2b0464e11d27fef553faccfd4787d75
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526652"
---
# <a name="office-365-message-encryption"></a>Office 365 郵件加密

與 Office 365 郵件加密，您的組織可以傳送和接收組織內外的人員之間的加密電子郵件訊息。Office 365 郵件加密適用於 Outlook.com、 yahoo ！、 Gmail、 及其他電子郵件服務。電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。
  
本文屬於較大的一系列有關 Office 365 郵件加密的文章。使用下表以快速找出所需的資訊。
  
|||
|:-----|:-----|
|請閱讀本文章...  <br/> |如果您是...  <br/> |
|[了解 Office 365 中受保護的郵件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |使用者想要深入了解如何加密訊息工時和，您可以使用哪些選項。  <br/> |
|[如何開啟受保護的郵件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |想要讀取受保護的郵件已傳送給您的使用者。本文包含讀取數個版本的 Outlook 並從不同的電子郵件帳戶，例如 gmail 和 yahoo ！ 帳戶包括 Office 365 外部郵件的相關資訊。  <br/> |
|[傳送、 檢視和回覆加密郵件在 Outlook 中](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |想要傳送、 檢視和回覆加密郵件從 Outlook 使用者。即使您不是 Office 365 組織的成員，仍會收到通知傳送給您在 Outlook 中的加密郵件。如需如何檢視及回覆加密郵件傳送來自 Office 365 中的指示使用本文。  <br/> |
|[傳送數位簽署或加密郵件](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |使用者想要傳送、 檢視和回覆加密郵件使用 Outlook for mac。本文也會涵蓋使用 OME、 S/MIME 等以外的加密方法。  <br/> |
|[Android 裝置上檢視加密的郵件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |一般使用者已收到郵件加密與 Office 365 郵件加密 Android 裝置上的，您可以使用免費的 OME 檢視器應用程式來檢視郵件，並傳送加密的回覆。本文說明如何。  <br/> |
|[在 iPhone 或 iPad 上檢視加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |一般使用者已收到郵件加密與 Office 365 郵件加密 iPhone 或 iPad 上的，您可以使用免費的 OME 檢視器應用程式來檢視郵件，並傳送加密的回覆。本文說明如何。  <br/> |
|Office 365 郵件加密 (OME) （本文）  <br/> |Office 365 或 Exchange Online Protection 系統管理員想要了解您可以在哪裡找到的其他資源。  <br/> |
|[Office 365 郵件加密常見問題集](ome-faq.md) <br/> |Office 365 或 Exchange Online Protection 的系統管理員通常想要的答案集包括授權及新功能與舊版 OME 之間的比較。  <br/> |
|[設定全新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md) <br/> |Office 365 或 Exchange Online Protection 系統管理員想要了解如何設定 Office 365 組織的新 Office 365 郵件加密功能。  <br/> |
|[定義加密 Office 365 中的電子郵件的郵件流程規則](define-mail-flow-rules-to-encrypt-email.md) <br/> |具有已設定 Office 365 郵件加密和您的 Office 365 或 Exchange Online Protection 系統管理員就可以定義自動加密電子郵件從您的組織傳送的郵件流程規則。  <br/> |
|[管理 Office 365 郵件加密](manage-office-365-message-encryption.md) <br/> |Office 365 或 Exchange Online Protection 系統管理員已經有設定 Office 365 郵件加密和想要設定的 OME 的選用設定。  <br/> |
|[將貴組織的品牌新增至您的加密郵件](add-your-organization-brand-to-encrypted-messages.md) <br/> |Office 365 或 Exchange Online Protection 系統管理員想要套用公司品牌來自訂貴組織的 Office 365 郵件加密的電子郵件的外觀及 OME 入口網站的內容。  <br/> |
|Office 365 郵件加密的[郵件原則及符合性服務說明](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption) <br/> |尋找 Office 365 郵件加密功能的詳細說明，包括支援 Sku，可從 Office 365。  <br/> |
|[Office 365 郵件加密的舊版資訊](legacy-information-for-message-encryption.md) <br/> |具有已設定 Office 365 郵件加密和您的 Office 365 或 Exchange Online Protection 系統管理員想 OME 正常運作之前版本的新功能的相關資訊。雖然您無法設定新部署的新功能不使用 OME、 Microsoft 繼續支援現有的部署。  <br/> |
   
本文的其餘部分套用至新的 OME 功能。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 郵件加密的運作方式

Office 365 郵件加密是一種線上服務的內建 Microsoft Azure 版權管理 (Azure RMS) 的 Azure 資訊保護的一部分。Office 365 系統管理員可以定義郵件流程規則來決定加密的條件。例如，規則可能需要所有寄給特定收件者的郵件的加密。
  
當有人傳送電子郵件訊息 Exchange Online 中符合加密郵件流程規則時，將郵件加密之前已傳送。使用 Outlook 用戶端讀取郵件的所有 Office 365 使用者會都收到原生、 頂級即使它們不位於相同組織為寄件者讀取加密和權限保護之郵件的體驗。支援的 Outlook 用戶端包括 Outlook 桌面、 Outlook Mac 行動裝置上 iOS 及 android （英文）、 Outlook 和 Outlook Web App。
  
收件者加密郵件的接收加密或權限受到保護的郵件傳送給其 Outlook.com、 Gmail、 和 Yahoo 帳戶可以輕鬆地 OME 入口網站使用其 Microsoft 帳戶或 Gmail 或 Yahoo 認證來驗證。
  
讀取加密或權限受到保護的郵件在未使用 Outlook 用戶端的使用者也會使用 OME 入口網站檢視加密和權限受到保護時收到的郵件。
  
我們已增加訊息與附件，您可以使用 Office 365 郵件加密來加密的大小限制。如需限制的詳細資訊，請參閱[Exchange Online 限制。](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
  
## <a name="defining-rules-for-office-365-message-encryption"></a>定義 Office 365 郵件加密的規則
<a name="Rules"> </a>

若要啟用 Office 365 郵件加密的新功能的其中一個方法是 Exchange Online 與 Exchange Online Protection 系統管理員可以定義郵件流程規則。這些規則決定應該下何種條件電子郵件加密的郵件。當加密巨集指令設定規則時，任何符合的規則條件的郵件加密之前他們正在傳送。
  
郵件流程規則具有彈性，讓您可以讓您可以符合特定安全性需求中單一規則合併條件。例如，您可以建立加密包含指定的關鍵字和定址給外部收件者的所有郵件的規則。Office 365 郵件加密的新功能也會加密從加密的電子郵件的收件者的回覆。
  
如需如何建立郵件流程規則，以利用新 OME 功能的詳細資訊，請參閱[Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>傳送、檢視和回覆加密的電子郵件
<a name="SendRecip"> </a>

使用 Office 365 郵件加密，使用者可以從 Outlook 和 Outlook web 上的傳送加密的電子郵件。此外，系統管理員可以設定 Office 365 中的郵件流程規則設為自動加密關鍵字相符或其他情況為基礎的電子郵件。
  
收件者加密郵件的 Office 365 組織中將能夠讀取順暢地中任何版本的 Outlook，包括電腦的 Outlook、 Outlook for Mac、 網路上的 Outlook、 iOS、 Outlook 和 Outlook for android （英文) 的那些郵件。接收加密的郵件上其他電子郵件用戶端的使用者可以檢視 OME 入口網站中的郵件。
  
如需如何傳送和檢視加密的郵件的詳細指引，看看這些文章：
  
- [如何開啟受保護的郵件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)
    
- [傳送、 檢視和回覆加密郵件在 Outlook 中](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
    
## <a name="get-started-with-the-new-ome-capabilities"></a>開始使用新的 OME 功能
<a name="SendRecip"> </a>

如果您已經準備好要開始使用在組織內的新 OME 功能，請參閱[Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)。
  

