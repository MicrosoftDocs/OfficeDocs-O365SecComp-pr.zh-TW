---
title: 建立、測試及調整 DLP 原則
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '若要開始使用 DLP 原則的最簡單的、 最常見方式是使用其中一個包含在 Office 365 中的範本。 '
ms.openlocfilehash: 1d4697811a5d8dd426fed80d3d60bcd2fbea6335
ms.sourcegitcommit: 42c7ad69f95fc4d2de13293b39cc44931b9f82e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2018
ms.locfileid: "26522785"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="66dc9-103">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="66dc9-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="66dc9-104">**主要作者**</span><span class="sxs-lookup"><span data-stu-id="66dc9-104">**Principal author**</span></span> </br>
<span data-ttu-id="66dc9-105">Paul Cunningham、 Microsoft MVP</span><span class="sxs-lookup"><span data-stu-id="66dc9-105">Paul Cunningham, Microsoft MVP</span></span> </br>
[<span data-ttu-id="66dc9-106">實用 365</span><span class="sxs-lookup"><span data-stu-id="66dc9-106">Practical 365</span></span>](https://practical365.com/) </br>
[<span data-ttu-id="66dc9-107">@Practical365</span><span class="sxs-lookup"><span data-stu-id="66dc9-107">@Practical365</span></span>](https://twitter.com/practical365)</br>
__________________________________________________

<span data-ttu-id="66dc9-p101">資料外洩防護是專門設計來協助防止有意或意外的敏感資訊公開給不想要對象貴組織的 Office 365 的符合性功能。DLP 有其不在 Exchange Server 與 Exchange Online 中的根目錄，也適用於 SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p101">Data loss prevention is a compliance feature of Office 365 that is designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties. DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="66dc9-p102">DLP 使用內容分析引擎来檢查的電子郵件及檔案內容尋找敏感資訊例如信用卡號碼和個人識別資訊 (PII)。敏感資訊通常不應該以電子郵件、 傳送或包含在文件，但不進行例如加密電子郵件訊息或檔案的其他步驟。您可以使用 DLP 偵測敏感資訊並例如採取動作：</span><span class="sxs-lookup"><span data-stu-id="66dc9-p102">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII). Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files. Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="66dc9-113">記錄的事件稽核用途</span><span class="sxs-lookup"><span data-stu-id="66dc9-113">Log the event for auditing purposes</span></span>
- <span data-ttu-id="66dc9-114">顯示一則警告訊息給使用者傳送電子郵件或共用檔案</span><span class="sxs-lookup"><span data-stu-id="66dc9-114">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="66dc9-115">主動封鎖的電子郵件或檔案共用中發生</span><span class="sxs-lookup"><span data-stu-id="66dc9-115">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="66dc9-p103">有時客戶解除 DLP 因為它們不考慮自己有需要保護的資料類型。假設為機密資料，例如醫療記錄或財務資訊僅存在 like 醫療保健產業或執行線上存放區的公司。但是任何商務可以處理敏感資訊經常，即使其不知道該。在試算表的員工名稱及出生的日期是為客戶名稱和信用卡的詳細資訊的試算表為機密。與此類型的資訊與不同浮動周圍超過可能預期，如員工以安靜模式前往其日常性工作，以為 nothing 匯出 CSV 檔案從系統並以電子郵件傳送給其他人。您也可能對頻率員工傳送電子郵件而不考慮後果包含信用卡或銀行業詳細資料。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p103">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting. The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores. But any business can handle sensitive information on a regular basis, even if they don't realize it. A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details. And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone. You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="66dc9-122">DLP 會偵測敏感資訊的方式</span><span class="sxs-lookup"><span data-stu-id="66dc9-122">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="66dc9-p104">可識別敏感資訊的規則運算式 (RegEx) 中的模式比、 組合與其他例如鄰近的指標與特定關鍵字]，以比對的模式。此範例是信用卡號。因為撰寫信用卡號有 16 個位數。不過，這些數字可以寫入以不同的方式，例如 1111年-1111年-1111年-1111、 1111年 1111年 1111年 1111，或 1111111111111111。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p104">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with with other indicators such as the proximity of certain keywords to the matching patterns. An example of this is credit card numbers. A VISA credit card number has 16 digits. However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="66dc9-p105">任何 16 位數字串不一定是信用卡號、 它可能是從說明服務台系統或序號為硬體一段的票證數字。若要告訴信用卡號及無害 16 位數字字串之間的差異，計算會執行 （總和檢查碼） 若要確認號碼符合各種信用卡品牌來自已知的模式。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p105">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware. To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="66dc9-129">此外，例如"因為撰寫"或"AMEX"、 接近度以及可能是信用卡到期日期的日期值的關鍵字的鄰近會也被視為關於資料是否是信用卡號的決策。</span><span class="sxs-lookup"><span data-stu-id="66dc9-129">Furthermore, the proximity of keywords such as “VISA” or “AMEX”, along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="66dc9-130">換句話說，DLP 為智慧通常不夠辨識電子郵件中的下列兩個敘述性文字之間的差異：</span><span class="sxs-lookup"><span data-stu-id="66dc9-130">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="66dc9-p106">"可以您訂購我新膝上型電腦。使用我因為撰寫號碼 」 層 1111年-1111年-1111 1111、 到期 11/22 and 傳送我有時的估計的傳遞日期"。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p106">“Can you order me a new laptop. Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it.”</span></span>
- <span data-ttu-id="66dc9-p107">"我筆記型電腦序號 2222年 2222年-2222年 2222年，而且它已購買 11/2010年上。順便一提，是我旅行因為撰寫尚未？] 核准</span><span class="sxs-lookup"><span data-stu-id="66dc9-p107">“My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010. By the way, is my travel visa approved yet?”</span></span>

<span data-ttu-id="66dc9-135">保留書籤的良好參考會說明如何偵測到每種資訊類型本[主題敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="66dc9-135">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="66dc9-136">要從何處開始與資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="66dc9-136">Where to start with data loss prevention</span></span>

<span data-ttu-id="66dc9-p108">當資料外洩的風險不完全明顯時，很難出其中完全應開始實作 DLP 運作。幸運地是，DLP 原則可以在 「 測試模式 」，讓您若要量測其有效性和正確性您開啟之前執行。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p108">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP. Fortunately, DLP policies can be run in “test mode”, allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="66dc9-p109">可透過 Exchange 系統管理中心中管理 Exchange Online 的 DLP 原則。但是您可以設定透過 [安全性及規範中心的所有工作負載的 DLP 原則讓我將使用此文章中示範的。在 [安全性及規範中心您會發現**資料外洩防護**底下的 DLP 原則 > **原則**。按一下 [在**建立原則**來啟動。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p109">DLP policies for Exchange Online can be managed through the Exchange admin center. But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article. In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**. Click on **Create a policy** to start.</span></span>

<span data-ttu-id="66dc9-p110">Office 365 提供的[DLP 原則範本](what-the-dlp-policy-templates-include.md)可用來建立 DLP 原則的範圍。假設您已準備澳大利亞商務。您可以當做篩選可分為三大類別的財務、 醫療和健康情況及隱私權原則範本以顯示只澳大利亞，相關。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p110">Office 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies. Let's say that you're an Australian business. You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![若要選擇國家或地區的選項](media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="66dc9-147">此示範而言我將會選擇澳大利亞個人識別資訊 (PII) 的資料，包括澳洲稅檔案數 (TFN) 和駕照編號資訊類型。</span><span class="sxs-lookup"><span data-stu-id="66dc9-147">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![若要選擇的原則範本] 選項](media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="66dc9-p111">提供新的 DLP 原則的名稱。預設的名稱會符合 DLP 原則範本，但因為可以從相同的範本建立多個原則您應選擇自己的其他描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p111">Give your new DLP policy a name. The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![選項來命名您的原則](media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="66dc9-p112">選擇 [原則將會套用至的位置。DLP 原則可套用至 Exchange Online、 SharePoint Online 和 OneDrive for Business。我正在移至保留此原則的設定套用至所有位置。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p112">Choose the locations that the policy will apply to. DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business. I am going to leave this policy configured to apply to all locations.</span></span>

![若要選擇的所有位置選項](media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="66dc9-p113">在 [第一個**原則設定**步驟只接受預設值現在。有很多用途 DLP 原則中的自訂，但預設值是不錯的起點。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p113">At the first **Policy Settings** step just accept the defaults for now. There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![若要自訂要保護的內容類型的選項](media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="66dc9-p114">按一下 [**下一步**] 之後將出現與其他的**原則設定**] 頁面上使用多個自訂選項。針對您要測試的原則，以下是您可以開始進行一些調整。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p114">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options. For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="66dc9-p115">我已關閉的現在，這是如果您剛正在測試取出的事項並不想要的任何尚未顯示給使用者的合理步驟的原則提示。原則提示對它們即將違反 DLP 原則的使用者顯示警告。例如 Outlook 使用者會看到它們已附加的檔案包含信用卡號警告和會使其電子郵件給被拒絕。原則提示的目標在於它發生前停止非相容的行為。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p115">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet. Policy tips display warnings to users that they're about to violate a DLP policy. For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected. The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="66dc9-165">我也已降低的執行個體介於 10 到 1，使此原則會偵測任何共用澳大利亞 PII 資料，不只是大量資料的共用。</span><span class="sxs-lookup"><span data-stu-id="66dc9-165">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="66dc9-166">我還已新增附隨報告電子郵件的另一個收件者。</span><span class="sxs-lookup"><span data-stu-id="66dc9-166">I've also added another recipient to the incident report email.</span></span>

![其他原則設定](media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="66dc9-p116">最後，我已設定最初在測試模式中執行此原則。請注意也會停用在測試模式中的原則提示的以下的選項。這可讓您已啟用原則的原則提示，但稍後決定是否要顯示或隱藏它們在測試期間的彈性。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p116">Finally, I've configured this policy to run in test mode initially. Notice there's also an option here to disable policy tips while in test mode. This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![若要先測試出原則選項](media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="66dc9-172">在最後檢閱畫面上按一下 [**建立**完成建立原則。</span><span class="sxs-lookup"><span data-stu-id="66dc9-172">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="66dc9-173">測試 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="66dc9-173">Test a DLP policy</span></span>

<span data-ttu-id="66dc9-p117">新的 DLP 原則會開始約為 1 小時內生效。您可以坐並等待其透過標準使用者活動觸發或您可以嘗試自行觸發。稍早我連結到此[主題敏感資訊類型](what-the-sensitive-information-types-look-for.md)，可提供讓您如何觸發 DLP 符合項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p117">Your new DLP policy will begin to take effect within about 1 hour. You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself. Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="66dc9-p118">例如，我建立本文的 DLP 原則將會偵測澳洲稅檔案數字 (TFN)。根據文件、 相符項目根據下列準則。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p118">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN). According to the documentation, the match is based on the following criteria.</span></span>

![文件等澳洲稅籍編號](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="66dc9-p119">而是鈍方式示範 TFN 偵測、 單字"稅籍編號"電子郵件並關閉鄰近 9 的數字字串會帶到處透過沒有任何問題。不會觸發 DLP 原則的原因是 9 數字字串必須通過指出它是有效的 TFN 而不只是數字的無害字串總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p119">To demonstrate TFN detection in a rather blunt manner, an email with the words “Tax file number” and a 9 digit string in close proximity will sail through without any issues. The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![不會傳遞總和檢查碼的澳洲稅籍編號](media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="66dc9-p120">在比較，單字"稅籍編號"電子郵件與通過總和檢查碼有效 TFN 就會觸發該原則。針對以下記錄使用嗎 TFN 取自產生的網站有效，但不是正版 TFNs。沒有類似的網站所產生[有效但假信用卡號](http://www.fakecreditcardgenerator.net/)。因為其中一個最常見的錯誤測試 DLP 原則時使用的假數字不是有效將不會傳遞總和檢查碼 （與因此將不會觸發該原則） 這類網站是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p120">In comparison, an email with the words “Tax file number” and a valid TFN that passes the checksum will trigger the policy. For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs. There are similar sites that generate [valid but fake credit card numbers](http://www.fakecreditcardgenerator.net/). Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![澳洲稅籍編號傳遞總和檢查碼](media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="66dc9-188">附隨報告電子郵件包括偵測到的敏感資訊類型、 偵測多少個執行個體，並偵測信賴等級。</span><span class="sxs-lookup"><span data-stu-id="66dc9-188">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![偵測到附隨報告顯示稅籍編號](media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="66dc9-p121">如果您在測試模式中保留 DLP 原則並分析附隨報告電子郵件，您可以啟動取得風格的 DLP 原則，以及如何有效它時就會強制執行的正確性。除了附隨報告，您還可以[使用 DLP 報告](view-the-dlp-reports.md)查看原則符合項目的彙總的檢視您的租用戶之間。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p121">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced. In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="66dc9-192">調整的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="66dc9-192">Tune a DLP policy</span></span>

<span data-ttu-id="66dc9-p122">當您分析可能會想要之原則的行為方式有些調整您原則是落在圖形。為簡單的範例中，您可能會決定電子郵件中的一個 TFN 不 （I 認為它仍是，但開始吧與其這是因為示範） 的問題，但兩個或多個執行個體未發生問題。多個執行個體可能是例如員工從 HR 資料庫 CSV 匯出至外部廠商，例如外部的會計服務以電子郵件傳送 risky 案例。必定為某些項目您偏好偵測和封鎖。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p122">As you analyze your policy hits you might want to make some adjustments to how the policies behave. As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem. Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service. Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="66dc9-197">在 [安全性及規範中心您可以編輯現有的原則以調整行為。</span><span class="sxs-lookup"><span data-stu-id="66dc9-197">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![若要編輯原則] 選項](media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="66dc9-199">您可以調整的位置設定使則會套用原則僅為特定的工作量或特定站台和帳戶。</span><span class="sxs-lookup"><span data-stu-id="66dc9-199">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![若要選擇特定位置的選項](media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="66dc9-201">您也可以調整的原則設定和編輯規則，以使它更符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="66dc9-201">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![若要編輯規則的選項](media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="66dc9-203">編輯 DLP 原則內的規則時您可以變更：</span><span class="sxs-lookup"><span data-stu-id="66dc9-203">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="66dc9-204">條件包括類型及數目會觸發規則的機密資料的執行個體。</span><span class="sxs-lookup"><span data-stu-id="66dc9-204">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="66dc9-205">例如限制存取內容所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="66dc9-205">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="66dc9-206">使用者通知會顯示給電子郵件用戶端或網頁瀏覽器中的使用者的原則提示。</span><span class="sxs-lookup"><span data-stu-id="66dc9-206">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="66dc9-207">使用者會覆寫，判斷使用者是否可選擇將其電子郵件或檔案共用仍繼續執行。</span><span class="sxs-lookup"><span data-stu-id="66dc9-207">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="66dc9-208">附隨報告，以通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="66dc9-208">Incident reports, to notify administrators.</span></span>

![若要編輯之規則的組件的選項](media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="66dc9-p123">此示範而言我已加入 user 通知 （請小心沒有足夠的使用者認識訓練這麼做的） 的原則，並允許使用者覆寫原則使用業務上理由或透過標幟為誤判。請注意您也可以自訂電子郵件和原則提示文字是否您想要包含任何貴組織的原則] 中的其他資訊或提示使用者如果有問題連絡支援人員。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p123">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive. Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![使用者通知和覆寫的選項](media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="66dc9-p124">原則都包含大量和低量的處理這兩個規則，因此請務必編輯兩者與您想要的動作。這是將以不同方式視其特性的情況下有機會。例如，您可能會允許低量違規的覆寫但不是允許大量違規的覆寫。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p124">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want. This is an opportunity to treat cases differently depending on their characteristics. For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![高容量與低量的一項規則的規則](media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="66dc9-217">此外，如果您要真的封鎖或限制存取權是違反原則的內容，您需要設定要這樣的規則動作。</span><span class="sxs-lookup"><span data-stu-id="66dc9-217">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![若要限制存取內容的選項](media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="66dc9-p125">後將那些變更儲存至原則設定，也需要傳回主要設定] 頁面上的原則並啟用要顯示給使用者的原則提示此原則會在測試模式時的選項。這是一個有效的方式來將您的使用者，引進 DLP 原則及使用者認識訓練、 執行而不影響到太多誤判造成影響其產能。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p125">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode. This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![若要在測試模式中顯示原則提示] 選項](media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="66dc9-p126">在伺服器端 （或如果您偏好雲端側）、 變更可能不會立即生效，因為各種處理間隔。如果您正在進行會向使用者顯示新的原則提示的 DLP 原則變更，使用者可能不會看到所做的變更會在其 Outlook 用戶端，會每隔 24 小時檢查原則的變更立即生效。如果您想要延展測試的速度加快，您可以使用此登錄修正程式[清除 PolicyNudges 機碼從上次下載時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。Outlook 會下載最新的原則資訊下次您重新啟動並開始撰寫電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p126">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals. If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours. If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="66dc9-226">如果您有啟用的原則提示，使用者會開始請參閱在 Outlook 中的提示，並可以報告誤判您時所發生。</span><span class="sxs-lookup"><span data-stu-id="66dc9-226">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![使用報告誤判選項的原則提示](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="66dc9-228">調查誤判</span><span class="sxs-lookup"><span data-stu-id="66dc9-228">Investigate false positives</span></span>

<span data-ttu-id="66dc9-p127">DLP 原則範本不完美官方現成可用。很有可能您會發現發生在環境中，也就是為何不那麼重要 DLP 部署到簡化您的方式，某些誤判花費的時間來充分測試及調整您的原則。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p127">DLP policy templates are not perfect straight out of the box. It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="66dc9-p128">以下是範例為誤判。此電子郵件會有太問題。使用者為其行動電話號碼提供給某人，並包括其電子郵件簽章。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p128">Here's an example of a false positive. This email is quite harmless. The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![顯示 false 正數資訊的電子郵件](media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="66dc9-235">使用者收到下列警告電子郵件包含敏感資訊原則提示，但尤其是澳洲駕照編號。</span><span class="sxs-lookup"><span data-stu-id="66dc9-235">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![以原則提示中的報告誤判] 選項](media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="66dc9-p129">使用者可以報告誤判，並系統管理員可以尋找到它已經發生的原因。附隨報告電子郵件中的電子郵件會被標記為誤判。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p129">The user can report the false positive, and the administrator can look into why it has occurred. In the incident report email, the email is flagged as a false positive.</span></span>

![附隨報告顯示誤判](media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="66dc9-p130">這個驅動程式授權案例是以深入探究良好的範例。此誤判發生在於"澳洲駕照"類型會觸發 （即使有一個是 10 位數字串的一部分）、 任何 9 數字字串關鍵字"雪梨 nsw"300 個字元距離的原因 （不區分大小寫）。讓它就會觸發的電話號碼和電子郵件簽章，僅因為使用者處於雪梨的變化。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p130">This driver's license case is a good example to dig into. The reason this false positive has occurred is that the “Australian Driver's License” type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords “sydney nsw” (not case sensitive). So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>

<span data-ttu-id="66dc9-p131">有趣的是，如果"雪梨、 NSW"有逗號，就不會觸發 DLP 原則。我有任何想法為何逗點會使任何差異 here 也為何澳洲駕授權資訊類型、 關鍵字中不含其他城市 （英文） 和 states 在澳洲但是那里您前往。如此，可以我們怎麼其相關資訊？有幾個選項。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p131">Interestingly, if “Sydney, NSW” has a comma, the DLP policy is not triggered. I have no idea why a comma makes any difference here, nor why other cities and states in Australia aren't included in the keywords for the Australian driver's license information type, but there you go. So, what can we do about it? There's a couple of options.</span></span>

<span data-ttu-id="66dc9-p132">其中一個選項是從原則移除澳洲駕授權資訊類型。由於 DLP 原則範本的一部分是在該處但我們不強制使用它。如果您只是興趣稅檔案號碼和不驅動程式的授權，您可以只移除。例如，您可以移除低量原則中的規則，但保留在 [大量規則使仍偵測到的多個驅動程式授權的清單。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p132">One option is to remove the Australian driver's license information type from the policy. It's in there because it's part of the DLP policy template, but we're not forced to use it. If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it. For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![若要刪除規則的敏感資訊類型的選項](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="66dc9-252">另一個作法是只要增加的執行個體計數，使駕授權低量僅偵測到如有多個執行個體。</span><span class="sxs-lookup"><span data-stu-id="66dc9-252">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![若要編輯的執行個體計數] 選項](media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="66dc9-p133">除了變更的執行個體計數，您也可以調整的相符項目正確性 （或信賴等級）。如果您的敏感資訊類型具有多個模式，您可以使您的規則比對只特定模式調整 [您的規則上的相符項目精準度。例如，若要協助減少誤判，您可以設定您的規則比對正確性使其符合最高的信賴等級的圖樣。了解信賴等級的計算方式是有點 （和超過此文章範圍），但以下是[如何使用以調整規則的信賴等級](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的理想說明。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p133">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level). If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns. For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level. Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).</span></span>

<span data-ttu-id="66dc9-p134">最後，如果您想要取得甚至更進階選項，您可以自訂任何敏感資訊類型--例如，您可以"雪梨 NSW"從清單中移除之關鍵字[澳洲駕照](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)，以避免誤判觸發上方。若要了解如何使用 XML 和 PowerShell 執行這項作業，請參閱[自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)本主題。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p134">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), to eliminate the false positive triggered above. To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="66dc9-260">關閉 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="66dc9-260">Turn off a DLP policy</span></span>

<span data-ttu-id="66dc9-261">當您很高興的 DLP 原則正確且有效偵測敏感資訊類型，並確認您的使用者準備好要如何處理正在進行中的原則，然後您可以啟用此原則。</span><span class="sxs-lookup"><span data-stu-id="66dc9-261">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![若要開啟 [原則] 選項](media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="66dc9-263">如果您正在等待原則會生效，[連線至 Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)並執行[Get DlpCompliancePolicy 指令程式](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)，請參閱 DistributionStatus 時。</span><span class="sxs-lookup"><span data-stu-id="66dc9-263">If you're waiting to see when the policy will take effect, [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![在 PowerShell 中執行指令程式](media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="66dc9-p135">之後忘記 DLP 原則，您應該執行一些最終測試您進行自己的確定預期的原則動作會發生。如果您嘗試測試之類的信用卡資料、 有網站線上如何產生範例信用卡資訊或其他個人資訊將傳遞總和檢查碼並觸發您的原則。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p135">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring. If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="66dc9-267">允許使用者覆寫原則將會呈現該選項給使用者的原則提示的一部分。</span><span class="sxs-lookup"><span data-stu-id="66dc9-267">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![允許使用者覆寫原則提示](media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="66dc9-269">限制內容的原則會呈現給使用者的警告一部分的原則提示，並防止傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="66dc9-269">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![僅限於該內容的原則提示](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="66dc9-271">摘要</span><span class="sxs-lookup"><span data-stu-id="66dc9-271">Summary</span></span>

<span data-ttu-id="66dc9-p136">資料外洩防護原則是適用於組織之所有類型。測試一些 DLP 原則是因為勝過之類的原則提示、 使用者覆寫及附隨報告控制低風險練習。以安靜模式可以測試以查看您的組織中已經發生何種類型的違規一些 DLP 原則然後並特殊功能原則和低 false 誤判率、 教育使用者 what's 允許並不允許，然後導入 DLP 原則至組織。</span><span class="sxs-lookup"><span data-stu-id="66dc9-p136">Data loss prevention policies are useful for organizations of all types. Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports. You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
