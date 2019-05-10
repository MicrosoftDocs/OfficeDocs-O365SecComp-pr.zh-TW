---
title: Office 365 客戶加密箱要求
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解客戶加密箱要求可讓您控制如何 Microsoft 支援工程師可以存取您的資料時所遇到的問題。
ms.openlocfilehash: 3a86f3333114f3015b85d8066298f9834737f127
ms.sourcegitcommit: 000548aa269ad775f20af5acd6aa726ac340c793
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2019
ms.locfileid: "33661419"
---
# <a name="customer-lockbox-in-office-365"></a>Office 365 中的客戶加密箱

> [!NOTE]
> 本文提供一種功能，是目前僅適用於 Microsoft 365 E5、 Office 365 E5、 資訊保護和合規性或進階合規性的附加元件訂閱的組織的部署和設定指導。

客戶加密箱能確保 Microsoft 無法存取您的內容，若要執行服務作業不需要明確的核准。 客戶加密箱帶入您存取您的內容要求的核准工作流程。

有時候，Microsoft 工程師協助疑難排解並修正客戶報告的支援程序中的問題。 通常，透過廣泛的遙測修正問題，且偵錯工具 Microsoft 就地其服務。 不過，某些情況下需要 Microsoft 工程師存取客戶內容，來判定其根本原因並修正問題。 客戶加密箱要求工程師的客戶的存取要求核准工作流程中的最後一個步驟。 這可讓組織來核准或拒絕這些要求，並提供給客戶的直接存取控制選項。

### <a name="customer-lockbox-overview-video"></a>客戶加密箱概觀影片

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> 客戶加密箱支援要求，以存取 Exchange Online、 SharePoint Online 和商務用 OneDrive 中的資料。 若要建議的其他 Office 365 服務的支援，請將要求提交在[Office 365 UserVoice](https://office365.uservoice.com/)。

## <a name="customer-lockbox-workflow"></a>客戶加密箱工作流程

下列步驟概述的一般工作流程，客戶加密箱要求由 Microsoft 工程師起始時：

1. 某人在組織都有其 Office 365 信箱發生問題。

2. 使用者疑難排解問題，但無法修正問題之後，他們會使用 Microsoft 支援服務開啟支援要求。

3. 支援工程師檢閱服務要求，並決定需要存取客戶的 Exchange Online 內容才能修復問題。

4. 支援工程師登入客戶加密箱要求工具，並藉由指定客戶的租用戶名稱、 服務要求編號和資料存取所需的估計的工期進行資料存取要求。

5. Microsoft 支援服務管理員核准要求之後，客戶加密箱傳送客戶組織在指定的核准者暫止的存取要求有關的電子郵件通知 microsoft。

    ![客戶加密箱電子郵件通知的範例](media/CustomerLockbox1.png)

   > [!NOTE]
   > 獲指派 Microsoft 365 系統管理中心中的[客戶加密箱存取核准者](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)系統管理員角色的任何人都可以核准客戶加密箱要求。

7. 核准者登入 Microsoft 365 系統管理中心，並核准要求。 此步驟會觸發可用的稽核記錄的建立，藉由搜尋 Office 365 稽核記錄檔。 如需詳細資訊，請參閱[稽核客戶加密箱要求](#auditing-customer-lockbox-requests)一節。

   如果客戶會拒絕要求或 12 小時內未獲核准要求，要求過期並沒有存取權授與 Microsoft 工程師。

   > [!IMPORTANT]
   > Microsoft 不包含客戶加密箱電子郵件通知要求您登入 Office 365 中的任何連結。

8. 客戶核准要求之後，Microsoft 工程師接收核准訊息、 登入 Exchange Online 中，並修正客戶的問題。 Microsoft 工程師已修正問題之後，自動撤銷存取權的要求持續時間。

> [!NOTE]
> 在 Office 365 稽核記錄檔會記錄所有由 Microsoft 工程師執行的動作。 您可以搜尋並檢閱這些稽核記錄和可以搜尋並檢閱。

## <a name="turn-customer-lockbox-requests-on-or-off"></a>開啟或關閉客戶加密箱要求

Office 365 系統管理員可以開啟的 Microsoft 365 系統管理中心中的客戶加密箱控制項。 客戶加密箱開啟時，Microsoft 必須先取得組織的核准，然後再存取任何其內容。

> [!NOTE]
> 若要執行下列程序，您必須是全域系統管理員在您的 Microsoft 365 或 Office 365 組織，或獲指派 「**客戶加密箱存取核准者**系統管理員角色。

1. 移至 [[https://admin.microsoft.com](https://admin.microsoft.com)並以您的公司或學校帳戶登入。

2. 按一下 [**設定 > 安全性 & 隱私權**]。

    ![編輯客戶加密箱設定在系統管理中心](media/CustomerLockbox2.png)

3. 在**客戶加密箱**並排顯示，按一下 [**編輯**]，然後將切換以**開啟**或**關閉**若要開啟或關閉此功能。

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>核准或拒絕客戶加密箱要求

> [!NOTE]
> 若要執行下列程序，您必須是全域系統管理員在您的 Microsoft 365 或 Office 365 組織，或獲指派 「**客戶加密箱存取核准者**系統管理員角色。

1. 移至 [[https://admin.microsoft.com](https://admin.microsoft.com)並以您的公司或學校帳戶登入。

2. 按一下 [**支援 > 客戶加密箱要求**。

    ![按一下 [支援]，然後按一下 [客戶加密箱要求](media/CustomerLockbox5.png)

    客戶加密箱要求清單隨即顯示。

    ![清單中的客戶加密箱要求](media/CustomerLockbox6.png)

3. 選取客戶加密箱要求，，然後按一下 [**核准**或**拒絕**。

    ![核准或拒絕客戶加密箱要求](media/CustomerLockbox7.png)

    會顯示一則有關的客戶加密箱要求核准的確認訊息。

    ![核准或拒絕客戶加密箱要求](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a>稽核客戶加密箱要求 

會對應到客戶加密箱要求的稽核記錄登入 Office 365 稽核記錄檔，並可使用 Office 365 安全性 & 合規性中心中的 [[稽核記錄搜尋工具](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)。 在 Office 365 稽核記錄檔會記錄與客戶接受或拒絕客戶加密箱要求和 （當核准存取要求），由 Microsoft 工程師執行的動作相關的動作。 您可以搜尋並檢閱這些稽核記錄。

> [!NOTE]
> 您必須獲指派 「 僅檢視稽核記錄檔] 或 [稽核記錄檔角色在 Exchange Online 來搜尋 Office 365 稽核記錄。 如需詳細資訊，請參閱 <<c0>的搜尋稽核記錄中 Office 365 安全性 &amp; 合規性中心。

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>搜尋與客戶加密箱要求相關的活動的稽核記錄檔

以下是如何建立稽核記錄搜尋查詢來傳回與客戶加密箱相關的稽核記錄：

1. 移至 [https://protection.office.com](https://protection.office.com)。
  
2. 使用公司或學校帳戶登入 Office 365。

3. 在安全性 & 合規性中心的左窗格中，按一下 [**搜尋 & 調查** > **稽核記錄搜尋**。

    會顯示 [**稽核記錄搜尋**] 頁面。

    ![稽核記錄搜尋] 頁面](media/auditlogsearch1.png)
  
4. 設定下列搜尋準則：

    a. **活動**-離開此欄位空白，讓搜尋傳回的所有活動的稽核記錄。 這是必要傳回任何與客戶加密箱要求相關的稽核記錄和相對應執行由 Microsoft 工程師的活動。

    b. **開始日期**和**結束日期**-選取的日期和時間範圍以顯示該期間內發生的事件。

    c. **使用者**-離開此欄位空白。

    d. **檔案、 資料夾或網站**-離開此欄位空白。

5. 按一下 [**搜尋**] 以執行使用您的搜尋準則的 [搜尋]。 

    載入的搜尋結果時，在幾分鐘之後他們底下會顯示及**結果**在**稽核記錄搜尋**] 頁面上。

6. 在搜尋結果頁面上，按一下 [**篩選結果**並執行下列其中一個下列事項：

   - 若要顯示在您的組織核准或拒絕客戶加密箱要求核准者與相關的稽核記錄： 中] 底下的 [**活動**] 欄中，輸入**組 AccessToCustomerDataRequest**。

   - 若要顯示在 「 已核准的客戶加密箱要求的回應中執行動作的 Microsoft 工程師與相關的稽核記錄： 在 [**使用者**] 資料行] 方塊中輸入**Microsoft 運算子**。 請注意，工程師所執行的動作顯示的 int [**活動**] 欄位。

      ![篩選要顯示的稽核記錄的 「 Microsoft 運算子 」](media/CustomerLockbox10.png)

7. 在結果清單中，按一下 [將它顯示稽核記錄]。

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>客戶加密箱存取要求的稽核記錄

當您的組織中的人員核准或拒絕客戶加密箱要求時，稽核記錄會記錄在 Office 365 稽核記錄檔中。 此記錄會包含下列資訊。 

| 稽核記錄屬性| 描述|
|:---------- |:----------|
| 日期       | 日期和時間時核准或拒絕客戶加密箱要求。
| IP 位址 | 電腦的 IP 位址的核准者用來核准或拒絕要求。 |
| 使用者       | 服務帳戶 BOXServiceAccount @\[customerforest\]。 prod.outlook.com。            |
| 活動   | 設定 AccessToCustomerDataRequest;這是當您核准或拒絕客戶加密箱要求時，會記錄稽核活動。                                |
| 項目       | 客戶加密箱要求的 Guid                             |

下列螢幕擷取畫面顯示稽核記錄的記錄，會對應至已核准的客戶加密箱要求範例。 如果客戶加密箱要求遭到拒絕， **ApprovalDecision**參數的值會被**拒絕**。

![稽核記錄已核准的客戶加密箱要求](media/CustomerLockbox9.png)

> [!TIP]
> 若要在稽核記錄中顯示的詳細的資訊，請按一下 [**詳細資訊**。

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>由 Microsoft 工程師執行動作的稽核記錄

如先前所述，在稽核記錄檔會記錄之後核准客戶加密箱要求 （和，可能會導致存取客戶內容），由 Microsoft 工程師執行的動作。 這些記錄包含下列資訊。

| 稽核記錄屬性| 描述|
|:---------- |:----------|
| 日期       | 日期時間時所執行的動作。 請注意的客戶加密箱要求受到核准時 4 小時內，將會執行此動作的時間。              |
| IP 位址 | 使用機器 Microsoft 工程師 IP 位址。 |
| 使用者       | Microsoft 運算子;這個值表示此記錄與客戶加密箱要求。                                  |
| 活動   | 由 Microsoft 工程師執行活動的名稱。|
| 項目       | \<空白\>                                             |


## <a name="frequently-asked-questions"></a>常見問題集

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a>若要將客戶加密箱套用在 Office 365 服務？

客戶加密箱目前支援在 Exchange Online、 SharePoint Online 和商務用 OneDrive。

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a>是客戶加密箱可供所有 Office 365 客戶？

客戶加密箱隨附的 Microsoft 365 或 Office 365 E5 訂閱，並可以新增到其他計劃與資訊保護和法規或進階合規性附加元件訂閱。  [方案和價格](https://products.office.com/business/office-365-enterprise-e5-business-software)，請參閱 如需詳細資訊。

#### <a name="what-is-customer-content"></a>什麼是客戶內容？

客戶內容是由 Office 365 服務和應用程式的使用者所建立的資料。 客戶內容的範例包括：

- 電子郵件內文或電子郵件附件

- SharePoint 網站內容

- SharePoint 檔案的內文中的資訊

- Skype 商務簡報檔案內文

- 立即訊息 (IM) 或語音交談

- 客戶所產生的 blob 或結構化的儲存資料 （例如，SQL 容器）

- 客戶自有的安全性資訊 （例如，憑證、 加密金鑰和密碼）

- 推斷，以及所有後續推斷，如果客戶內容會留

如需有關 Office 365 中的客戶內容的詳細資訊，請參閱 < 在<b0>Office 365 信任中心</b0>。

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>要求存取我的內容時，人員會收到通知？

全域系統管理員，且所有人都指派存取核准者系統管理員角色會收到通知客戶加密箱。 這些也是相同的使用者可核准的客戶加密箱要求。

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>誰可以核准或拒絕這些要求在我的組織中？

全域系統管理員，且所有人都指派給客戶加密箱存取核准者系統管理員角色可以核准客戶加密箱要求。 客戶控制項在其組織中的這些角色指派。

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>如何我選擇集客戶加密箱？

全域系統管理員可以啟用並設定 Microsoft 365 或 Microsoft 365 系統管理中心中的客戶加密箱。

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>如果我核准客戶加密箱要求時，可以工程師與什麼如何知道 Microsoft 工程師嗎？

核准客戶加密箱要求之後，Microsoft 工程師授與這些必要的權限，以使用預先核准指令程式來存取客戶內容。 客戶加密箱要求的回應中的 Microsoft 工程師所採取的動作會記錄，並可在 Office 365 安全性 & 合規性中心的稽核記錄檔可存取。

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>如何知道，Microsoft 會遵循核准程序？

您可以將電子郵件核准通知傳送給系統管理員和組織中的 Microsoft 365 系統管理中心中的客戶加密箱要求歷程記錄的核准者交互參照。

Customer Lockbox 隨附於[SOC 1 SSAE 16 稽核報告](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)的最新。 如需詳細資訊，您可以在[Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)找到最新的報表。

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Microsoft 可以修改我的租用戶的核准者的清單嗎？ 如果沒有，如何避免？

全域系統管理員在組織中的可以指定誰可以核准客戶加密箱要求。 這表示僅在 Azure Active Directory 全域系統管理員群組的成員可以指定誰可以核准邀請。 僅由組織管理 Azure Active Directory 中的全域系統管理員群組的成員資格。

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>如果我需要核准其內容的存取要求的詳細資訊嗎？

每個客戶加密箱要求都會包含 Office 365 服務要求數。 您可以連絡 Microsoft 支援服務及參照此服務數目，以取得有關之要求的詳細資訊。

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>當客戶加密箱要求獲得核准時，多久是有效的權限？

目前的存取權限授與 Microsoft 工程師的最大期間為 4 小時。 Microsoft 工程師也可以要求較短的期間。

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>如何取得所有客戶加密箱要求的歷程記錄？

在 Microsoft 365 系統管理中心檢視所有客戶加密箱要求。

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>如何建立內容的存取權要求關聯與相關的稽核記錄檔？

合規性中心活動摘要包含記錄活動的客戶加密箱。 客戶可以交互參照的活動摘要所收到的電子郵件要求對客戶加密箱記錄活動。

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>客戶不會回應客戶加密箱要求時，會發生什麼事？

客戶加密箱要求有預設的持續時間是 12 小時。 如果您未在 12 小時內回應要求，要求將會過期。

#### <a name="what-does-microsoft-when-a-customer-rejects-a-customer-lockbox-request"></a>當客戶拒絕客戶加密箱要求時，用途 Microsoft？

如果客戶拒絕客戶加密箱要求，則會發生任何客戶內容存取權。 如果貴組織中的使用者持續體驗需要存取客戶內容，若要解決此問題： Microsoft 的服務問題，然後服務問題可能會保存與 Microsoft 將會通知使用者有關此。

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>客戶加密箱 atp 保護針對執法機構資料要求或其他協力廠商？

否。 Microsoft 會嚴重採用客戶資料的第三方的要求。 為雲端服務提供者，Microsoft 一律是代表客戶資料的隱私權。 事件中我們取得傳票，Microsoft 會一直嘗試將協力廠商重新導向至客戶取得的資訊。 (讀取將 Smith 的部落格: [ Protecting 客戶資料從政府側錄](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我們會定期發佈有關 Microsoft 收到法律強制執行要求的[詳細的資訊](https://www.microsoft.com/en-us/corporate-responsibility/lerr)。

請參閱[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/default.aspx)有關協力廠商資料要求與[線上服務條款](https://www.microsoft.com/Licensing/product-licensing/products.aspx)] 如需詳細資訊中的 「 外洩的客戶的資料 」 一節。

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Microsoft 如何確保其人員的成員都不會有客戶內容常設存取 Office 365 應用程式中？

Microsoft 會實作廣泛的預防措施，透過訪問控制系統和偵查措施，以識別和解決規避這些訪問控制系統的嘗試。 Office 365 運作時所用的最低權限與剛時間存取原則。 因此，沒有 Microsoft 人員需要存取持續的客戶內容的權限。 如果授與權限時，它是有限的持續時間。 

Office 365 會使用稱為*Lockbox*的存取控制系統，以處理要求的權限，授與執行服務內的作業及系統管理功能的能力。 Operator 必須要求存取使用 Lockbox，然後需要採取動作的要求第二個人員的客戶內容 （例如，核准該） 存取權授與之前。 該第二個人員無法要求者，且必須指定為核准客戶內容存取權。 只有當要求核准運算子並未取得暫時客戶內容存取權。 提高權限時間逾期之後，加密箱會撤銷存取權。

請參閱[線上服務條款](https://www.microsoft.com/licensing/product-licensing/products)] 如需詳細資訊 Microsoft 一般安全性作法。

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>何種情況下 Microsoft 工程師需要存取我的內容？

客戶提出要求進行存取的疑難排解支援要求時最常見的案例，在 Microsoft 工程師需要存取的客戶內容。 Office 365 的置於原則是服務運作沒有 Microsoft 客戶內容存取權。 幾乎所有由 Microsoft 執行的服務作業會完全自動化，並人類參與高度控制和抽象化開客戶內容。 Office 365 的目標是客戶核准的 Microsoft access 的特定要求之前，不需要為支援服務的客戶內容存取權。

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>我已經以為我的資料是安全與 Microsoft 雲端，因此我為什麼需要客戶加密箱？

客戶加密箱藉由提供客戶能夠提供服務作業的明確的存取授權提供額外的控制項。 透過示範程序都可供明確資料的存取授權，客戶加密箱也可協助客戶符合 HIPAA 等 FEDRAMP 特定合規性責任。
