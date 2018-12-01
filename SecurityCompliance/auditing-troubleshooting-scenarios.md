---
title: 搜尋 Office 365 稽核記錄來疑難排解常見的案例
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
description: 您可以使用 Office 365 稽核記錄搜尋工具來協助您疑難排解常見問題，例如調查洩漏的帳戶或找出誰設定信箱的電子郵件轉寄。
ms.openlocfilehash: 930e311712e49214ca2a51e256c29e5f959deab8
ms.sourcegitcommit: c34f1a0d560117153fc9a7b8da8994bc6fc53791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2018
ms.locfileid: "27123896"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a>搜尋 Office 365 稽核記錄來疑難排解常見的案例

本文說明如何使用 Office 365 稽核記錄搜尋工具來協助您疑難排解一般支援案例。這包括使用稽核記錄，以：

- 尋找可用來存取洩漏的帳戶之電腦的 IP 位址
- 決定誰設定信箱的電子郵件轉寄
- 決定使用者是否刪除信箱中的電子郵件項目
- 判斷使用者建立收件匣規則

## <a name="using-the-office-365-audit-log-search-tool"></a>使用 Office 365 稽核記錄搜尋工具

每個本文所述的疑難排解案例根據使用中 [Office 365 安全性及規範中心的稽核記錄搜尋工具。本節列出搜尋稽核記錄所需的權限，並說明的步驟來存取並執行稽核記錄搜尋。每個案例一節提供如何設定稽核記錄搜尋查詢及要符合搜尋準則的稽核記錄中的詳細資訊中尋找的項目相關的特定指示。

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>若要使用稽核記錄搜尋工具所需的權限

您必須指派 「 僅檢視稽核記錄 」 或 「 稽核記錄角色在 Exchange Online 搜尋 Office 365 稽核記錄。根據預設，這些角色被指派給 Exchange 系統管理中心的 [**權限**] 頁面上相符性管理] 和 [組織管理角色群組。如需詳細資訊，請參閱[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。

### <a name="running-audit-log-searches"></a>執行稽核記錄搜尋

本節說明建立和執行稽核記錄搜尋基礎。本文中的每個疑難排解案例中使用這些指示為起點。如需詳細的逐步指示，請參閱 ＜[的搜尋稽核記錄中的 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)。

1. 移至 [https://protection.office.com](https://protection.office.com)。
  
2. 使用公司或學校帳戶登入 Office 365。

3. 在 [安全性及規範中心的左窗格中，按一下 [**搜尋與調查有關** > **稽核記錄搜尋**。
    
    會顯示 [**稽核記錄搜尋**] 頁面。 
    
    ![設定準則，然後按一下 [搜尋] 執行搜尋](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. 您可以設定下列搜尋準則。注意： 此文章中的每個疑難排解案例會建議設定這些欄位的特定指示。
    
    a.**活動**-[下拉式清單，以顯示您可以搜尋的活動。執行搜尋之後，會顯示只選取活動的稽核記錄。選取 [**顯示所有的活動的結果**會顯示所有符合搜尋準則的活動的結果。您也必須將此欄位留白在某些疑難排解案例。
    
    b.**開始日期**] 及 [**結束日期**-選取以顯示該期間內發生之事件的日期和時間範圍。預設會選取過去 7 天。以國際標準時間 (UTC) 格式所呈現的日期和時間。您可以指定的最大的日期範圍為 90 天。

    c.**使用者**在此方塊和再選取一或多個使用者按一下 [顯示搜尋結果的。選取您在此方塊中選取的使用者所執行的活動的稽核記錄所顯示的結果清單中。保留此方塊空白以傳回組織中的所有使用者 （及服務帳戶） 的項目。
    
    d.**檔案、 資料夾或網站**-輸入某些或所有搜尋資料夾包含指定之的關鍵字的檔案相關的活動的檔案或資料夾名稱。您也可以指定的檔案或資料夾的 URL。如果您使用的 URL，請確定此類型的完整的 URL 路徑或如果您只需要輸入 URL 部分不會包含任何特殊字元或空格。保留此方塊空白以傳回組織中的所有檔案及資料夾的項目。此欄位空白中所有的疑難排解案例本文中的記事。
    
5. 按一下 [**搜尋**來執行使用搜尋準則的 [搜尋]。 
    
    會載入搜尋結果，並在幾分鐘之後時顯示下**結果****稽核記錄搜尋**] 頁面上。每個的下列各節會提供有關要查看特定的疑難排解案例的事項指引。

    如需檢視、 篩選或匯出稽核記錄搜尋結果的詳細資訊，請參閱：

    - [檢視搜尋結果](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [篩選搜尋結果](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [匯出搜尋結果](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>尋找可用來存取洩漏的帳戶之電腦的 IP 位址

對應至執行的任何使用者活動的 IP 位址包含在大部分的稽核記錄中。稽核記錄中也包含使用的用戶端的相關資訊。

以下是如何設定此案例的稽核記錄搜尋查詢：

**活動**-如果您案例相關，選取要搜尋特定的活動。疑難排解洩漏帳戶，請考慮選取 [ **Exchange 信箱活動**的**使用者登入信箱**活動。這會傳回顯示登入信箱時所使用的 IP 位址的稽核記錄。否則請將此欄位留白以傳回所有的活動的稽核記錄。 

> [!TIP]
> 此欄位留白將會傳回**UserLoggedIn**活動表示某人已登入 Office 365 使用者帳戶的 Azure Active Directory 活動。使用篩選搜尋結果中顯示**UserLoggedIn**稽核記錄。

**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。

**使用者**-如果您正在調查洩漏的帳戶，選取其帳戶已危害的使用者。這會傳回該使用者帳戶所執行的活動的稽核記錄。

**檔案、 資料夾或網站**層離開此欄位空白。

執行搜尋之後，每個活動的 IP 位址會顯示在搜尋結果中的 [ **IP 位址**] 欄位。按一下 [檢視彈出式] 頁面上的詳細的資訊將搜尋結果中的記錄。

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a>決定誰設定信箱的電子郵件轉寄

當電子郵件轉寄設定信箱時，就會傳送給信箱的電子郵件轉寄給另一個信箱。郵件可以轉接至企業內或組織外的使用者。時在信箱上設定電子郵件轉寄，基礎 Exchange Online 指令程式用為**Set-mailbox**。

以下是如何設定此案例的稽核記錄搜尋查詢：

**活動**-保留空白，讓搜尋傳回的所有活動的稽核記錄此欄位。這會傳回任何必要稽核與**Set-mailbox**指令程式相關的記錄。

**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。

**使用者**-除非您正在調查的電子郵件轉寄特定使用者的問題，此欄位請保留空白。這可協助您識別如果電子郵件轉寄已設定的任何使用者。

**檔案、 資料夾或網站**層離開此欄位空白。

執行搜尋之後，按一下 [搜尋結果頁面上的**篩選結果**。在 [**活動**] 欄標題] 方塊中輸入**Set-mailbox**使僅有稽核記錄的相關**Set-mailbox**指令程式會顯示。

![篩選稽核記錄搜尋的結果](media/emailforwarding1.png)

此時，您必須查看每個稽核記錄，以判斷活動會與電子郵件轉寄的詳細資料。按一下 [顯示**詳細資料**彈出式] 頁面的稽核記錄，然後按一下 [**詳細資訊**。下列螢幕擷取畫面及描述重點信箱已設定指出電子郵件轉寄的資訊。

![稽核記錄的詳細的資訊](media/emailforwarding2.png)

a. **ObjectId**欄位中，已設定電子郵件轉寄的信箱的別名上會顯示。這個信箱也會顯示在 [**項目**] 欄中的搜尋結果頁面上。

b.在 [**參數**] 欄位值*ForwardingSmtpAddress*會表示上信箱的電子郵件轉寄尚未設定。在此範例中是郵件轉寄給電子郵件地址 mike@contoso.com，這是 alpinehouse.onmicrosoft.com 組織外部。

c*則為 True*值*DeliverToMailboxAndForward*參數表示郵件傳送到 sarad@alpinehouse.onmicrosoft.com*及*的複本會轉寄給*ForwardingSmtpAddress 所指定的電子郵件地址*參數，在本例中為 mike@contoso.com。如果*DeliverToMailboxAndForward*參數的值設為*False*，然後電子郵件僅遞給*ForwardingSmtpAddress*參數所指定的地址。它不會傳遞至**ObjectId** ] 欄位中所指定的信箱。

d. **UserId**欄位指出**ObjectId**欄位] 欄位中所指定的信箱設定電子郵件轉寄的使用者。這位使用者也會顯示在搜尋結果頁面上的 [**使用者**] 欄中。在此例中看來之信箱的擁有者其信箱上設定電子郵件轉寄。

如果您決定不應該信箱上設定電子郵件轉寄，您可以在 Exchange Online PowerShell 中執行下列命令來移除：

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

請參閱[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)相關電子郵件轉寄的參數的詳細資訊。

## <a name="determining-if-a-user-deleted-email-items"></a>決定使用者是否刪除電子郵件項目

刪除稽核記錄檔記錄有關之前電子郵件項目儲存至 Office 365 稽核記錄檔、 在組織中每個使用者信箱啟用信箱稽核具有。此外，SoftDelete 和 HardDelete 信箱動作已啟用稽核。指示，請參閱[啟用信箱稽核 Office 365 中](enable-mailbox-auditing.md)。如果使用者已啟用信箱稽核，請使用下列步驟來搜尋稽核記錄已刪除的電子郵件項目的相關的事件。

以下是如何設定此案例的稽核記錄搜尋查詢：

**活動**-下**Exchange 信箱活動**選取一或兩個下列活動：

- **從 [刪除的郵件] 資料夾刪除的郵件**-此活動會對應至**SoftDelete**信箱稽核巨集指令。此活動也會記錄使用者選取它，並按下**Shift + Delete**永久刪除項目。永久刪除項目之後，使用者可以復原它直到刪除項目保留期間到期。

- **從信箱 Purged 郵件**-此活動會對應至**HardDelete**信箱稽核巨集指令。這會記錄時使用者清除項目從 [可復原的項目] 資料夾。系統管理員可以使用在 Office 365 安全性和規範中心] 中的內容搜尋工具來搜尋並保留清除復原的項目直到刪除項目保留期間到期或更久是否為使用者的信箱。

**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。

**使用者**-如果您在此欄位中選取使用者、 稽核記錄搜尋工具會傳回由指定使用者已刪除的郵件 （SoftDeleted 或 HardDeleted） 的電子郵件項目的稽核記錄。在某些情況下，刪除電子郵件的使用者可能不是信箱擁有者。

**檔案、 資料夾或網站**層離開此欄位空白。

執行搜尋之後，您可篩選搜尋結果顯示稽核記錄的硬碟已刪除的項目或的虛刪除項目。按一下 [顯示**詳細資料**彈出式] 頁面的稽核記錄，然後按一下 [**詳細資訊**。已刪除的項目，例如主旨行及時所刪除之項目的位置的其他資訊會顯示在 [ **AffectedItems** ] 欄位。下列螢幕擷取畫面顯示虛刪除的項目及硬碟已刪除的項目**AffectedItems**欄位的範例。

**虛刪除項目的 AffectedItems 欄位的範例**

![虛刪除項目的稽核記錄](media/softdeleteditem.png)

**硬碟已刪除的項目 AffectedItems 欄位的範例**

![硬碟已刪除電子郵件項目的稽核記錄](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a>復原刪除的電子郵件項目

如果刪除的項目保留期間未過期的使用者可以復原虛刪除的項目。在 Exchange Online 中，預設已刪除的項目保留期間為 14 天，但系統管理員可以增加此設定最大值為 30 天。[復原刪除的項目或 Outlook Web App 中的電子郵件](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)本文的指示在復原點使用者刪除項目。

如先前所述，系統管理員可能會無法復原硬碟已刪除的項目如果已刪除的項目保留期間未過期或信箱時保留，直到保留期間到期的項目保留在此情況下。當您執行內容的搜尋時，虛刪除與硬刪除 [可復原的項目] 資料夾中的項目會傳回搜尋結果中符合搜尋查詢。如需執行內容的搜尋的詳細資訊，請參閱[Office 365 中的內容搜尋](content-search.md)。

> [!TIP]
> 若要搜尋的已刪除的電子郵件項目，搜尋全部或部分的主旨行中的稽核記錄的**AffectedItems**欄位所顯示。

## <a name="determining-if-a-user-created-an-inbox-rule"></a>決定使用者是否建立收件匣規則

當使用者建立自己的 Exchange Online 信箱的收件匣規則時、 相對應的稽核記錄會儲存在稽核記錄。如需收件匣規則的詳細資訊，請參閱：

- [使用網路上的 Outlook 中的收件匣規則](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [使用規則管理在 Outlook 中的電子郵件](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

以下是如何設定此案例的稽核記錄搜尋查詢：

**活動**- **Exchange 信箱活動**，選取 [ **New-inboxrule 建立/修改/啟用/停用收件匣規則**。

**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。

**使用者**-除非您正在調查的特定使用者，將此欄位留白。這可協助您識別新任何使用者所設定的收件匣規則。

**檔案、 資料夾或網站**層離開此欄位空白。

執行搜尋之後，此活動的任何稽核記錄會顯示在搜尋結果中。按一下 [顯示**詳細資料**彈出式] 頁面的稽核記錄，然後按一下 [**的詳細資訊**。收件匣規則設定的相關資訊會顯示在 [**參數**] 欄位。下列螢幕擷取畫面及描述醒目提示收件匣規則的相關資訊。

![新的收件匣規則的稽核記錄](media/NewInboxRuleRecord.png)

a. **ObjectId**欄位中，會顯示收件匣規則的完整名稱。此名稱包含使用者的信箱 (例如 SaraD) 的別名和收件匣規則 （例如"移動郵件從系統"） 的名稱。

b.在 [**參數**] 欄位會顯示收件匣規則的條件。在這個範例中，*從*參數指定的條件。定義*從*參數的值會指出收件匣規則會對 admin@alpinehouse.onmicrosoft.com 所傳送的電子郵件。可以用來定義的收件匣規則條件的參數的完整清單，請參閱[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章。

c. *MoveToFolder*參數指定的收件匣規則動作 ；在這個範例中，從 admin@alpinehouse.onmicrosoft.com 接收的郵件會移至名為*AdminSearch*資料夾。也請參閱[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)的完整清單可以用來定義的收件匣規則動作的參數。

d. **UserId**欄位指出建立**ObjectId** field 中指定的收件匣規則的使用者。這位使用者也會顯示在搜尋結果頁面上的 [**使用者**] 欄中。