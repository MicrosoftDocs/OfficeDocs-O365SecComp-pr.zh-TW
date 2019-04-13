---
title: Office 365 郵件加密 (OME) 版本比較
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 有助於闡述與不同版本的 Office 365 郵件加密及這兩個方式繼續一起傳遞的功能差異。
ms.openlocfilehash: bb13208e2b630c8a6217b78b48a4cd3bb4b0de79
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836837"
---
# <a name="compare-versions-of-ome"></a>比較 OME 版本

本文會比較舊版 Office 365 郵件加密 (OME) 至全新的 OME 功能。 新功能會合併與較新版本的 OME 和資訊版權管理 (IRM)。 也列出部署至 GCC High 獨特特性。 我們也將說明如何這兩個可以並存於您的 Office 365 組織。

||
|:-----|
|本文屬於較大的一連串的 Office 365 郵件加密的相關文章。 本文適用於系統管理員和 ITPros。 如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>以並排比較的特性與功能

|                                   |舊的功能       |                   |新功能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**功能**                     | **舊版 OME**    | **IRM**           | **全新的 OME 功能** |
|*傳送加密的郵件*        |透過 Exchange 郵件流程規則|使用者啟動 Outlook 桌面或 Outlook 網頁;或透過 Exchange 郵件流程規則|使用者啟動 Outlook 桌面、 Outlook for Mac，或 Outlook 網頁;透過 Exchange 郵件流程規則 （也稱為傳輸規則） 和 Office 365 資料外洩防護 (DLP)|
|*權限管理範本*       |   不適用      |不要轉寄] 選項，自訂範本|不要轉寄] 選項，僅限加密的選項，自訂範本|
|*收件者類型*                   |內部和外部收件者|僅限內部收件者         |內部和外部收件者|
|*內部收件者的經驗*|收件者收到 HTML 郵件時，他們下載，並在網頁瀏覽器或行動應用程式中開啟|在 Outlook 用戶端的原生內嵌體驗|Office 365 收件者的原生內嵌體驗。 所有其他收件者可以讀取 OME 入口網站 （沒有下載或所需的應用程式） 的郵件。|
|*外部收件者的經驗*|收件者收到 HTML 郵件時，他們下載，並在網頁瀏覽器或行動應用程式中開啟|不適用|Office 365 收件者的原生內嵌體驗。 所有其他收件者可以讀取 OME 入口網站 （沒有下載或所需的應用程式） 的郵件。|
|*附件的權限*           |任何附件的限制|受保護的附件|不要轉寄] 選項和自訂範本保護的附件。 系統管理員可以選擇是否與否，會受到保護加密唯讀] 選項的附件。|
|*攜帶您自己的金鑰 (BYOK) 支援*|無                |無               |BYOK 支援          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>透過舊版 OME 的全新的 OME 功能的優點

新功能提供下列優點：

- 能夠使用加密僅限 （這可讓安全共同作業），不要轉寄，並自訂的限制。
- 寄件者可以傳送以手動方式從 Outlook 桌面、 Outlook for Mac 和 Outlook web 用戶端上的新功能會使用加密的郵件。
- 支援的 Outlook 用戶端中使用內嵌體驗前往 office 365 收件者。 或者，系統管理員可以選擇要顯示 Office 365 收件者的品牌的體驗。
- 將 Gmail、 Yahoo 及 Microsoft 帳戶，例如 Office 365 外部帳戶被同盟使用 OME 入口網站，可提供較佳的使用者經驗，讓這些收件者。 所有其他身分識別使用一次性密碼來存取加密的郵件。
- 系統管理員可以自訂品牌，並建立多個品牌的範本。
- 系統管理員可以撤銷電子郵件加密與新功能。
- 新功能提供透過安全性的詳細使用情況報告&amp;合規性中心。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高部署中的 Office 365 郵件加密的獨特特性

如果您打算在 GCC 高的環境中使用 Office 365 郵件加密，有一些唯一特性相關的收件者的經驗。

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>加密的電子郵件從 GCC High GCC High 收件者

寄件者可以手動加密 PC 和 Mac 版 Outlook 和網頁型 Outlook 中的電子郵件或組織可以設定原則以使用 Exchange 郵件流程規則的電子郵件加密。

內 GCC High 收件者收到相同的內嵌所有其他 Office 365 使用者讀取 PC 和 Mac 版 Outlook 和 outlook 網頁版中的體驗。

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>加密的電子郵件從 GCC High 至非 GCC High 收件者

GCC High 內的寄件者可以傳送加密的電子郵件 GCC High 界限之外。

外部 GCC 高，包括商業 Office 365 使用者、 Outlook.com 的使用者，以及其他電子郵件提供者，例如 Gmail 和 Yahoo，其他使用者的所有收件者會收到將收件者重新導向至收件者所在無法讀取 OME 入口網站的包裝函式郵件和回覆訊息。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>舊版 OME 和相同的租用戶中的新功能的共存

您可以在相同的租用戶中使用舊版 OME 與新功能。 身為管理員，您這麼做選擇您想要建立您的郵件流程規則時，使用的 OME 的版本。

- 若要指定了舊版的 OME，請使用 Exchange 郵件流程規則動作**套用 OME 的舊版本**。
- 若要指定新的功能，請使用 Exchange 郵件流程規則動作**套用 Office 365 郵件加密和權限保護**。

使用者可以手動傳送從 Outlook 桌面、 Outlook for Mac 和 outlook 網頁版的新功能會使用加密的郵件。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>從舊版 OME 移轉至新功能

即使 OME 使用兩種版本可同時存在，我們強烈建議您編輯您舊的郵件流程規則使用的新功能時，用於**套用 OME 的舊版本**的規則動作。 更新這些規則，以使用郵件流程規則動作**套用 Office 365 郵件加密和權限保護**。 如需相關指示，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-ome"></a>開始使用 OME

一般而言，全新的 OME 功能時自動啟用 Office 365 組織。 如需組織內全新的 OME 功能的詳細資訊，請參閱 <<c0>設定新的 Office 365 郵件加密功能。

如果您已啟用 Azure 資訊保護了舊版的 OME 會自動啟用 Office 365 組織。 在過去，即使未啟用 Azure 資訊保護，正常運作舊版 OME。 這不再是這種情況。

若要開始使用舊版 OME，如果您已啟用 Azure 資訊保護，只設定使用**套用 OME 的舊版本**的規則動作的郵件流程規則。 如需相關指示，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。