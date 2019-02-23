---
title: Office 365 郵件加密版本比較
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 可協助說明在兩個繼續以共同運作的方式與不同版本的 Office 365 郵件加密，以及傳送的功能差異。
ms.openlocfilehash: 477fbe8f9d71bd92225a7ba5043576f164933b4e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216673"
---
# <a name="compare-versions-of-ome"></a>比較 OME 版本

本文會比較新的 OME 功能以舊版 Office 365 郵件加密。新功能且購 OME 和資訊版權管理 (IRM) 的較新版本。我們也會介紹如何兩者可以在 Office 365 組織共存。

||
|:-----|
|本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員和 ITPros 的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>以並排比較的特性與功能

|                                   |舊的功能       |                   |新功能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**功能**                     | **舊版 OME**    | **IRM**           | **OME 的新功能** |
|*傳送加密的郵件*        |透過 Exchange 郵件流程規則|從 Outlook 桌面或 Outlook Web; 上的起始的使用者或透過 Exchange 郵件流程規則|從 Outlook 桌面、 Outlook for Mac 或 Outlook Web; 上的起始的使用者透過 Exchange 傳輸規則和 Office 365 資料外洩防護 (DLP)|
|*權限管理範本*       |   不適用      |不要轉寄選項和自訂範本|不要轉寄] 選項、 僅限加密的選項和自訂範本|
|*收件者類型*                   |內部和外部收件者|僅限內部收件者         |內部和外部收件者|
|*內部收件者的體驗*|收件者會收到他們下載並在網頁瀏覽器或行動裝置應用程式中開啟 HTML 郵件|在 Outlook 用戶端的原生內嵌經驗|Office 365 的收件者的原生內嵌體驗。所有其他收件者可以讀取郵件從 OME 入口網站 （沒有下載 （英文） 或應用程式所需）。|
|*外部收件者經驗*|收件者會收到他們下載並在網頁瀏覽器或行動裝置應用程式中開啟 HTML 郵件|不適用|Office 365 的收件者的原生內嵌體驗。所有其他收件者可以讀取郵件從 OME 入口網站 （沒有下載 （英文） 或應用程式所需）。|
|*附件的權限*           |不受限制的附件|保護|保護不要轉寄選項和自訂範本。系統管理員可以選擇是否或未保護加密唯讀] 選項的附件。|
|*將您自己的索引鍵 (BYOK) 支援*|無                |無               |BYOK 支援          |
||

## <a name="advantages-of-using-the-new-ome-capabilities-over-legacy-ome"></a>舊版 OME 優於使用新的 OME 功能

新功能提供下列優點：

- 能夠使用加密唯讀 （可讓安全共同作業、） 不要轉寄，以及自訂的限制。
- 寄件者可以傳送郵件加密使用手動從 Outlook 桌面、 Outlook for Mac 和 Outlook web 用戶端上的新功能。
- Office 365 的收件者取得中支援的 Outlook 用戶端使用內嵌經驗。或者，系統管理員可以選擇要顯示 Office 365 的收件者加上品牌的體驗。
- Office 365 外部例如 Gmail、 Yahoo、 與 Microsoft 帳戶的帳戶是 OME 入口網站，這些收件者提供更好的使用者經驗與同盟。所有其他身分識別使用一次性複雜的程式碼來存取加密的郵件。
- 系統管理員可以自訂品牌和建立多個品牌的範本。
- 系統管理員可以撤銷的新功能使用加密的電子郵件。
- 新功能提供詳細的使用情形報告透過安全性&amp;規範中心。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>舊版 OME 與同一個承租戶中的新功能共存

您可以在同一個承租戶中使用舊版 OME 及新功能。以管理員身分您這麼做選擇 OME 您想要建立您的郵件流程規則時使用的版本。

- 若要指定舊版的 OME，使用 Exchange 郵件流程規則動作 」 套用 OME 舊版"。
- 若要指定新的功能，請使用 Exchange 郵件流程規則動作 」 套用 Office 365 郵件加密和權限保護"。

使用者也可以傳送郵件加密使用手動從 Outlook 桌面、 Outlook for Mac 和 Outlook web 用戶端上的新功能。

## <a name="migrating-from-legacy-ome-to-the-new-capabilities"></a>從舊版 OME 移轉至新的功能

即使這兩個版本的 OME 可以並存，我們強烈建議您編輯您舊的郵件流程規則使用的規則動作的 「 適用於舊版 OME"使用藉由指定的郵件流程規則動作 」 適用於 Office 365 郵件加密的新功能與權限保護"。指示，請參閱[定義郵件流程規則來加密 Office 365 中的電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="getting-started-with-ome"></a>OME 快速入門

一般而言，針對 Office 365 組織自動啟用新的 OME 功能。如果您已經準備好要開始使用在組織內的新 OME 功能，請參閱[Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)。

如果您已啟用 Azure 資訊保護舊版的 OME 會自動啟用 Office 365 組織。在過去，舊版 OME 正常運作即使未啟用 Azure 資訊保護。不再是這樣。

若要開始使用舊版 OME，如果您已啟用 Azure 資訊保護，您只需要為設定郵件流程規則使用 「 套用 OME 舊版"之規則動作。指示，請參閱[定義郵件流程規則來加密 Office 365 中的電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。