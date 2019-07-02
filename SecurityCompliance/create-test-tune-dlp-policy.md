---
title: 建立、測試及調整 DLP 原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '要開始使用 DLP 原則，最簡單且最常見方式是使用 Office 365 所包含的其中一個範本。 '
ms.openlocfilehash: 32b0b4baa058fda031a58681e107b01bf207da55
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077959"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="71338-103">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="71338-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="71338-104">**主體作者**</span><span class="sxs-lookup"><span data-stu-id="71338-104">**Principal author**</span></span> <br/>
<span data-ttu-id="71338-105">Paul Cunningham, Microsoft MVP</span><span class="sxs-lookup"><span data-stu-id="71338-105">Paul Cunningham, Microsoft MVP</span></span> <br/>
[<span data-ttu-id="71338-106">實際365</span><span class="sxs-lookup"><span data-stu-id="71338-106">Practical 365</span></span>](https://practical365.com/) <br/>
[<span data-ttu-id="71338-107">@Practical365</span><span class="sxs-lookup"><span data-stu-id="71338-107">@Practical365</span></span>](https://twitter.com/practical365)<br/>
__________________________________________________

<span data-ttu-id="71338-108">資料遺失防護是 Office 365 的符合性功能, 其設計目的是協助您的組織防止故意或意外暴露敏感資訊給不需要的各方。</span><span class="sxs-lookup"><span data-stu-id="71338-108">Data loss prevention is a compliance feature of Office 365 that is designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties.</span></span> <span data-ttu-id="71338-109">DLP 在 Exchange Server 和 Exchange Online 中有其根目錄, 也適用于 SharePoint Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="71338-109">DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="71338-110">DLP 會使用內容分析引擎來檢查電子郵件和檔案的內容, 以尋找敏感資訊, 例如信用卡號碼和個人身分識別資訊 (PII)。</span><span class="sxs-lookup"><span data-stu-id="71338-110">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII).</span></span> <span data-ttu-id="71338-111">機密資訊通常不是以電子郵件傳送, 或是包含在檔中, 而不需要額外的步驟, 例如加密電子郵件訊息或檔案。</span><span class="sxs-lookup"><span data-stu-id="71338-111">Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files.</span></span> <span data-ttu-id="71338-112">您可以使用 DLP 來偵測敏感資訊, 並採取下列動作:</span><span class="sxs-lookup"><span data-stu-id="71338-112">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="71338-113">記錄事件以供審計之用</span><span class="sxs-lookup"><span data-stu-id="71338-113">Log the event for auditing purposes</span></span>
- <span data-ttu-id="71338-114">向傳送電子郵件或共用檔案的使用者顯示警告</span><span class="sxs-lookup"><span data-stu-id="71338-114">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="71338-115">主動封鎖電子郵件或檔案共用發生</span><span class="sxs-lookup"><span data-stu-id="71338-115">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="71338-116">有時客戶會因為不考慮需要保護的資料類型而關閉 DLP。</span><span class="sxs-lookup"><span data-stu-id="71338-116">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting.</span></span> <span data-ttu-id="71338-117">假設敏感性資料 (例如醫療記錄或財務資訊) 只存在於健康護理或執行線上存放區的公司。</span><span class="sxs-lookup"><span data-stu-id="71338-117">The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores.</span></span> <span data-ttu-id="71338-118">但是任何公司都可以定期處理機密資訊, 即使他們不認識。</span><span class="sxs-lookup"><span data-stu-id="71338-118">But any business can handle sensitive information on a regular basis, even if they don't realize it.</span></span> <span data-ttu-id="71338-119">員工姓名和出生日期的試算表, 就像是客戶名稱和信用卡詳細資料的試算表一樣。</span><span class="sxs-lookup"><span data-stu-id="71338-119">A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details.</span></span> <span data-ttu-id="71338-120">而這類資訊往往會圍繞您預期的方式來浮動, 因為員工不需要從系統中匯出 CSV 檔案, 並以電子郵件傳送給某人。</span><span class="sxs-lookup"><span data-stu-id="71338-120">And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone.</span></span> <span data-ttu-id="71338-121">您也可能會驚訝于員工傳送包含信用卡或銀行詳細資料的電子郵件的頻率, 不會考慮結果。</span><span class="sxs-lookup"><span data-stu-id="71338-121">You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="71338-122">DLP 如何偵測到敏感資訊</span><span class="sxs-lookup"><span data-stu-id="71338-122">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="71338-123">機密資訊會以正則運算式 (RegEx) 模式比對來識別, 並與其他指標 (例如特定關鍵字接近于相符的模式) 相結合。</span><span class="sxs-lookup"><span data-stu-id="71338-123">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="71338-124">這是信用卡號碼的範例。</span><span class="sxs-lookup"><span data-stu-id="71338-124">An example of this is credit card numbers.</span></span> <span data-ttu-id="71338-125">簽證信用卡號碼有16位數位。</span><span class="sxs-lookup"><span data-stu-id="71338-125">A VISA credit card number has 16 digits.</span></span> <span data-ttu-id="71338-126">不過, 這些數位可以以不同的方式撰寫, 例如1111-1111-1111-1111、1111 1111 1111 1111 或1111111111111111。</span><span class="sxs-lookup"><span data-stu-id="71338-126">However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="71338-127">任何16位數的字串不一定是信用卡號碼, 它可以是服務台系統的票據號碼, 或是硬體的序號。</span><span class="sxs-lookup"><span data-stu-id="71338-127">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="71338-128">若要說明信用卡號碼和無害16位字串之間的差異, 會執行計算 (checksum), 以確認號碼符合各種信用卡品牌的已知模式。</span><span class="sxs-lookup"><span data-stu-id="71338-128">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="71338-129">此外, 像是 "簽證" 或 "AMEX" 之類的關鍵字相近, 也有可能是信用卡到期日的最接近日期值, 也會被視為決定資料是否為信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="71338-129">Furthermore, the proximity of keywords such as “VISA” or “AMEX”, along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="71338-130">換句話說, DLP 通常會非常聰明, 以識別電子郵件中這兩種文字之間的差異:</span><span class="sxs-lookup"><span data-stu-id="71338-130">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="71338-131">「您可以定購新的膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="71338-131">“Can you order me a new laptop.</span></span> <span data-ttu-id="71338-132">使用我的簽證號碼 1111-1111-1111-1111, 到期 11/22, 並在您有它的預估傳遞日期時傳送給我。</span><span class="sxs-lookup"><span data-stu-id="71338-132">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it.”</span></span>
- <span data-ttu-id="71338-133">「我的膝上型電腦序號碼是 2222-2222-2222-2222, 且是在11/2010 上購買。</span><span class="sxs-lookup"><span data-stu-id="71338-133">“My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="71338-134">順便說一下, 我的旅行社是否已核准？</span><span class="sxs-lookup"><span data-stu-id="71338-134">By the way, is my travel visa approved yet?”</span></span>

<span data-ttu-id="71338-135">[保留書簽] 的良好參考是本主題說明如何偵測每種資訊類型的[敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="71338-135">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="71338-136">從資料遺失防護開始的位置</span><span class="sxs-lookup"><span data-stu-id="71338-136">Where to start with data loss prevention</span></span>

<span data-ttu-id="71338-137">當資料洩漏風險完全不明顯時, 就很難完成應該從執行 DLP 開始的地方。</span><span class="sxs-lookup"><span data-stu-id="71338-137">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="71338-138">幸運的是, DLP 原則可以在「測試模式」中執行, 讓您在開啟之前測量它們的效能和準確性。</span><span class="sxs-lookup"><span data-stu-id="71338-138">Fortunately, DLP policies can be run in “test mode”, allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="71338-139">您可以透過 Exchange 系統管理中心來管理 Exchange Online 的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="71338-139">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="71338-140">不過, 您可以透過安全性 & 合規性中心設定所有工作負載的 DLP 原則, 如此將會在本文中用來進行示範。</span><span class="sxs-lookup"><span data-stu-id="71338-140">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="71338-141">在安全性 & 規範中心中, 您會在**資料遺失防護** > **原則**下找到 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="71338-141">In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="71338-142">按一下 [**建立要啟動的原則**]。</span><span class="sxs-lookup"><span data-stu-id="71338-142">Click on **Create a policy** to start.</span></span>

<span data-ttu-id="71338-143">Office 365 提供一系列[dlp 原則範本](what-the-dlp-policy-templates-include.md), 您可以用來建立 dlp 原則。</span><span class="sxs-lookup"><span data-stu-id="71338-143">Office 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies.</span></span> <span data-ttu-id="71338-144">假設您是澳大利亞的商務版。</span><span class="sxs-lookup"><span data-stu-id="71338-144">Let's say that you're an Australian business.</span></span> <span data-ttu-id="71338-145">您可以篩選原則範本, 只顯示與澳大利亞相關的原則範本, 其屬於財務、醫療和健康情況和隱私權的一般類別。</span><span class="sxs-lookup"><span data-stu-id="71338-145">You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![選擇國家或地區的選項](media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="71338-147">在這個示範中, 我將選擇澳大利亞個人身分識別資訊 (PII) 資料, 其中包含澳大利亞稅檔號碼 (TFN) 和駕駛執照號碼的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="71338-147">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![選擇原則範本的選項](media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="71338-149">提供新的 DLP 原則名稱。</span><span class="sxs-lookup"><span data-stu-id="71338-149">Give your new DLP policy a name.</span></span> <span data-ttu-id="71338-150">預設名稱會符合 DLP 原則範本, 但是您應該選擇更具描述性的名稱, 因為可以從相同的範本建立多個原則。</span><span class="sxs-lookup"><span data-stu-id="71338-150">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![用來命名原則的選項](media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="71338-152">選擇原則將套用至的位置。</span><span class="sxs-lookup"><span data-stu-id="71338-152">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="71338-153">DLP 原則可套用至 Exchange Online、SharePoint Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="71338-153">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="71338-154">我要將此原則設定為套用至所有位置。</span><span class="sxs-lookup"><span data-stu-id="71338-154">I am going to leave this policy configured to apply to all locations.</span></span>

![選擇所有位置的選項](media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="71338-156">在第一個**原則設定**步驟中, 立即接受預設值。</span><span class="sxs-lookup"><span data-stu-id="71338-156">At the first **Policy Settings** step just accept the defaults for now.</span></span> <span data-ttu-id="71338-157">在 DLP 原則中有很多您可以執行的自訂, 但預設值是一個不錯的起點。</span><span class="sxs-lookup"><span data-stu-id="71338-157">There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![自訂要保護的內容類型的選項](media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="71338-159">按 **[下一步]** 後, 就會出現額外的 [**原則設定**] 頁面, 其中包含更多自訂選項。</span><span class="sxs-lookup"><span data-stu-id="71338-159">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="71338-160">對於您剛測試的原則, 以下是您可以開始進行一些調整的位置。</span><span class="sxs-lookup"><span data-stu-id="71338-160">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="71338-161">我現在已關閉原則提示, 如果您只是測試專案, 而不想要對使用者顯示任何專案, 則需要採取合理的步驟。</span><span class="sxs-lookup"><span data-stu-id="71338-161">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="71338-162">原則提示會對即將違反 DLP 原則的使用者顯示警告。</span><span class="sxs-lookup"><span data-stu-id="71338-162">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="71338-163">例如, Outlook 使用者會看到一則警告, 指出他們所附加的檔案包含信用卡號碼, 並將拒絕其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="71338-163">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="71338-164">原則提示的目標是在發生之前先停止不相容的行為。</span><span class="sxs-lookup"><span data-stu-id="71338-164">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="71338-165">我也將實例數從10減少為 1, 因此此原則會偵測任何共用的澳大利亞 PII 資料, 而不只是大量共用資料。</span><span class="sxs-lookup"><span data-stu-id="71338-165">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="71338-166">我也已將另一位收件者新增至附隨報告電子郵件。</span><span class="sxs-lookup"><span data-stu-id="71338-166">I've also added another recipient to the incident report email.</span></span>

![其他原則設定](media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="71338-168">最後, 我已將此原則設定為先在測試模式中執行。</span><span class="sxs-lookup"><span data-stu-id="71338-168">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="71338-169">請注意, 在測試模式中也有一個選項可停用原則提示。</span><span class="sxs-lookup"><span data-stu-id="71338-169">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="71338-170">這可讓您靈活地在原則中啟用原則提示, 但接著決定要在測試期間顯示或隱藏它們。</span><span class="sxs-lookup"><span data-stu-id="71338-170">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![先測試原則的選項](media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="71338-172">在最終的 [審閱] 畫面上, 按一下 [**建立**] 以完成建立原則。</span><span class="sxs-lookup"><span data-stu-id="71338-172">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="71338-173">測試 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="71338-173">Test a DLP policy</span></span>

<span data-ttu-id="71338-174">新的 DLP 原則會在大約1小時內開始生效。</span><span class="sxs-lookup"><span data-stu-id="71338-174">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="71338-175">您可以坐下來, 等待正常的使用者活動觸發, 也可以嘗試自行觸發。</span><span class="sxs-lookup"><span data-stu-id="71338-175">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="71338-176">更早的連結到此[主題的敏感資訊類型](what-the-sensitive-information-types-look-for.md), 可提供有關如何觸發 DLP 相符的資訊。</span><span class="sxs-lookup"><span data-stu-id="71338-176">Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="71338-177">例如, 我為本文所建立的 DLP 原則會偵測到澳大利亞稅收檔編號 (TFN)。</span><span class="sxs-lookup"><span data-stu-id="71338-177">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="71338-178">根據檔, 相符項是以下列準則為基礎。</span><span class="sxs-lookup"><span data-stu-id="71338-178">According to the documentation, the match is based on the following criteria.</span></span>

![澳大利亞稅務檔案編號的檔](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="71338-180">若要以較相近的方式示範 TFN 偵測, 您可以在不發生任何問題的情況下, 使用包含 "稅收 file number" 一詞的電子郵件和接近接近的9位數位符串來進行 sail。</span><span class="sxs-lookup"><span data-stu-id="71338-180">To demonstrate TFN detection in a rather blunt manner, an email with the words “Tax file number” and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="71338-181">不觸發 DLP 原則的原因是, 9 位數的字串必須通過校驗和, 表示它是有效的 TFN, 而不只是一種無害的數位字串。</span><span class="sxs-lookup"><span data-stu-id="71338-181">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![未通過校驗和的澳大利亞稅務檔案編號](media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="71338-183">相比之下, 如果電子郵件包含 "稅收 file number" 一詞, 而傳遞校驗和的有效 TFN 會觸發該原則。</span><span class="sxs-lookup"><span data-stu-id="71338-183">In comparison, an email with the words “Tax file number” and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="71338-184">在這裡的記錄中, 所使用的 TFN 是從產生有效但不是正版 TFNs 的網站取得。</span><span class="sxs-lookup"><span data-stu-id="71338-184">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="71338-185">有類似的網站會產生[有效但虛假的信用卡號碼](http://www.fakecreditcardgenerator.net/)。</span><span class="sxs-lookup"><span data-stu-id="71338-185">There are similar sites that generate [valid but fake credit card numbers](http://www.fakecreditcardgenerator.net/).</span></span> <span data-ttu-id="71338-186">這類網站非常有用, 因為測試 DLP 原則時最常見的錯誤之一, 是使用不正確虛設號碼, 而且不會傳遞校驗和 (因此不會觸發原則)。</span><span class="sxs-lookup"><span data-stu-id="71338-186">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![傳遞校驗和的澳大利亞稅務檔案編號](media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="71338-188">[附隨報告] 電子郵件包括偵測到的敏感資訊類型、偵測到的實例數目, 以及偵測的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="71338-188">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![顯示已偵測到稅務檔案號碼的附隨報告](media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="71338-190">如果您在測試模式中保留 DLP 原則, 並分析附隨報告電子郵件, 您可以開始瞭解 DLP 原則的準確性, 以及強制執行的有效程度。</span><span class="sxs-lookup"><span data-stu-id="71338-190">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="71338-191">除了附隨報告之外, 您還可以[使用 DLP 報告](view-the-dlp-reports.md)來查看整個租使用者中原則相符專案的匯總視圖。</span><span class="sxs-lookup"><span data-stu-id="71338-191">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="71338-192">調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="71338-192">Tune a DLP policy</span></span>

<span data-ttu-id="71338-193">當您分析原則擊中時, 您可能會想要對原則的行為進行一些調整。</span><span class="sxs-lookup"><span data-stu-id="71338-193">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="71338-194">簡單的範例是, 您可能會判斷一封電子郵件中的一個 TFN 不是問題 (我認為它仍然是, 但為了示範, 讓我們繼續瞭解), 但有兩個以上的實例是問題。</span><span class="sxs-lookup"><span data-stu-id="71338-194">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="71338-195">多個實例可能是一種危險的案例, 例如員工從 HR 資料庫將 CSV 匯出至外部通訊錄 (例如, 外部會計服務) 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="71338-195">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="71338-196">確實是您想要偵測及封鎖的專案。</span><span class="sxs-lookup"><span data-stu-id="71338-196">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="71338-197">在安全性 & 合規性中心內, 您可以編輯現有原則以調整行為。</span><span class="sxs-lookup"><span data-stu-id="71338-197">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![編輯原則的選項](media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="71338-199">您可以調整位置設定, 讓原則僅套用至特定的工作負載, 或套用至特定的網站和帳戶。</span><span class="sxs-lookup"><span data-stu-id="71338-199">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![選擇特定位置的選項](media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="71338-201">您也可以調整原則設定, 並編輯規則, 以更符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="71338-201">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![編輯規則的選項](media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="71338-203">在 DLP 原則內編輯規則時, 您可以變更:</span><span class="sxs-lookup"><span data-stu-id="71338-203">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="71338-204">條件, 包括將觸發規則之敏感性資料的實例類型和數目。</span><span class="sxs-lookup"><span data-stu-id="71338-204">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="71338-205">採取的動作, 例如限制存取內容。</span><span class="sxs-lookup"><span data-stu-id="71338-205">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="71338-206">使用者通知, 也就是在電子郵件客戶程式或網頁瀏覽器中顯示給使用者的原則提示。</span><span class="sxs-lookup"><span data-stu-id="71338-206">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="71338-207">使用者覆寫, 可決定使用者是否可以選擇繼續進行電子郵件或檔案共用。</span><span class="sxs-lookup"><span data-stu-id="71338-207">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="71338-208">附隨報告, 以通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="71338-208">Incident reports, to notify administrators.</span></span>

![編輯規則部分的選項](media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="71338-210">在這個示範中, 我已將使用者通知新增至原則 (在沒有足夠的使用者意識訓練的情況下, 請小心), 並允許使用者以業務理由覆寫原則, 或將它標記為 false 陽性。</span><span class="sxs-lookup"><span data-stu-id="71338-210">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="71338-211">請注意, 如果您想要包含組織原則的任何其他資訊, 也可以自訂電子郵件和原則提示文字, 或者, 如果有任何問題, 則提示使用者與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="71338-211">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![使用者通知和覆寫的選項](media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="71338-213">原則包含兩個處理高容量和低容量的規則, 因此請務必使用您想要的動作來編輯。</span><span class="sxs-lookup"><span data-stu-id="71338-213">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="71338-214">這是視案例的特性而異的方式。</span><span class="sxs-lookup"><span data-stu-id="71338-214">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="71338-215">例如, 您可能會允許覆寫較低的磁片, 但不允許對高大量違規的覆寫。</span><span class="sxs-lookup"><span data-stu-id="71338-215">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![一種適用于高容量的規則和一種低容量的規則](media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="71338-217">此外, 如果您想要實際封鎖或限制違反原則的內容存取, 您必須設定規則上的動作以執行此動作。</span><span class="sxs-lookup"><span data-stu-id="71338-217">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![限制存取內容的選項](media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="71338-219">將這些變更儲存至原則設定後, 我也必須回到原則的 [主要設定] 頁面, 並啟用當原則處於測試模式時, 向使用者顯示原則提示的選項。</span><span class="sxs-lookup"><span data-stu-id="71338-219">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="71338-220">這是一種有效的方式, 可以將 DLP 原則引入您的使用者, 並進行使用者認知訓練, 而不會有太多影響其生產力的誤報。</span><span class="sxs-lookup"><span data-stu-id="71338-220">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![在測試模式中顯示原則提示的選項](media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="71338-222">在伺服器端 (或您想要的雲端端) 上, 變更可能不會立即生效, 因為有各種處理間隔。</span><span class="sxs-lookup"><span data-stu-id="71338-222">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="71338-223">如果您要進行 DLP 原則變更, 以將新的原則提示顯示給使用者, 使用者可能不會看到其 Outlook 用戶端中的變更會立即生效, 這會檢查每24小時的原則變更。</span><span class="sxs-lookup"><span data-stu-id="71338-223">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="71338-224">如果您想要加快測試的速度, 您可以使用此登錄修補程式,[從 PolicyNudges 機碼清除最後下載的時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。</span><span class="sxs-lookup"><span data-stu-id="71338-224">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="71338-225">Outlook 會在您下次重新開機時下載最新的原則資訊, 並開始撰寫電子郵件。</span><span class="sxs-lookup"><span data-stu-id="71338-225">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="71338-226">如果您已啟用原則提示, 使用者將會開始看到 Outlook 中的秘訣, 而且在發生時可以向您報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="71338-226">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![原則提示, 具有報告 false 正值的選項](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="71338-228">調查誤報</span><span class="sxs-lookup"><span data-stu-id="71338-228">Investigate false positives</span></span>

<span data-ttu-id="71338-229">DLP 原則範本不會完全直接從盒中取出。</span><span class="sxs-lookup"><span data-stu-id="71338-229">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="71338-230">您可能會發現環境中有一些誤報, 這就是為什麼很重要的原因是讓您更容易進入 DLP 部署, 讓您花時間來充分測試和調整原則。</span><span class="sxs-lookup"><span data-stu-id="71338-230">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="71338-231">以下是 false 陽性的範例。</span><span class="sxs-lookup"><span data-stu-id="71338-231">Here's an example of a false positive.</span></span> <span data-ttu-id="71338-232">此電子郵件相當無害。</span><span class="sxs-lookup"><span data-stu-id="71338-232">This email is quite harmless.</span></span> <span data-ttu-id="71338-233">使用者將他們的行動電話號碼提供給某人, 並包含他們的電子郵件簽章。</span><span class="sxs-lookup"><span data-stu-id="71338-233">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![顯示 false 正值資訊的電子郵件](media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="71338-235">但使用者會看到原則提示, 警告他們電子郵件包含敏感資訊, 特別是澳大利亞司機的授權號碼。</span><span class="sxs-lookup"><span data-stu-id="71338-235">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![在原則提示中報告 false 陽性的選項](media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="71338-237">使用者可以報告假肯定, 系統管理員可以查看其發生的原因。</span><span class="sxs-lookup"><span data-stu-id="71338-237">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="71338-238">在附隨報告電子郵件中, 會將電子郵件標示為 false 陽性。</span><span class="sxs-lookup"><span data-stu-id="71338-238">In the incident report email, the email is flagged as a false positive.</span></span>

![顯示 false 正值的附隨報告](media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="71338-240">此驅動程式的授權案例是深入瞭解的一個很好的範例。</span><span class="sxs-lookup"><span data-stu-id="71338-240">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="71338-241">發生這種錯誤的原因是, 任何9位數的字串 (甚至是10位數位符串的一部分) 將會觸發 "澳大利亞 Driver the License" 類型, 這些字元會在300字元接近于關鍵字 "悉尼 nsw" (不區分大小寫)。</span><span class="sxs-lookup"><span data-stu-id="71338-241">The reason this false positive has occurred is that the “Australian Driver's License” type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords “sydney nsw” (not case sensitive).</span></span> <span data-ttu-id="71338-242">因此, 它是由電話號碼和電子郵件簽章觸發, 只是因為使用者在悉尼。</span><span class="sxs-lookup"><span data-stu-id="71338-242">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>

<span data-ttu-id="71338-243">有趣的是, 如果 "悉尼, NSW" 有逗點, 則不會觸發 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="71338-243">Interestingly, if “Sydney, NSW” has a comma, the DLP policy is not triggered.</span></span> <span data-ttu-id="71338-244">我不知道為什麼逗號會在這裡產生任何差異, 而且澳大利亞的其他城市和狀態不會包含在澳大利亞駕照的授權資訊類型的關鍵字中, 但您可以在這裡找到。</span><span class="sxs-lookup"><span data-stu-id="71338-244">I have no idea why a comma makes any difference here, nor why other cities and states in Australia aren't included in the keywords for the Australian driver's license information type, but there you go.</span></span> <span data-ttu-id="71338-245">那麼, 我們可以怎麼做呢？</span><span class="sxs-lookup"><span data-stu-id="71338-245">So, what can we do about it?</span></span> <span data-ttu-id="71338-246">有幾個選項。</span><span class="sxs-lookup"><span data-stu-id="71338-246">There's a couple of options.</span></span>

<span data-ttu-id="71338-247">其中一個選項是從原則移除澳大利亞司機的授權資訊類型。</span><span class="sxs-lookup"><span data-stu-id="71338-247">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="71338-248">因為它是 DLP 原則範本的一部分, 但不會強制您使用它。</span><span class="sxs-lookup"><span data-stu-id="71338-248">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="71338-249">如果您只對稅務檔案編號, 而不是對驅動程式的授權感興趣, 您可以只將它移除。</span><span class="sxs-lookup"><span data-stu-id="71338-249">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="71338-250">例如, 您可以從原則的 [低容量] 規則中移除它, 但將它保留在 [高容量規則] 中, 讓多個驅動程式的清單仍可偵測到。</span><span class="sxs-lookup"><span data-stu-id="71338-250">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![從規則刪除敏感資訊類型的選項](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="71338-252">另一個選項是簡單地增加實例計數, 因此只有當有多個實例時, 才會偵測到低容量的驅動程式授權。</span><span class="sxs-lookup"><span data-stu-id="71338-252">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![編輯實例計數的選項](media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="71338-254">除了變更實例計數之外, 您也可以調整相符精確性 (或信賴等級)。</span><span class="sxs-lookup"><span data-stu-id="71338-254">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="71338-255">如果您的機密資訊類型有多個模式, 您可以調整規則中的相符準確度, 讓您的規則只符合特定模式。</span><span class="sxs-lookup"><span data-stu-id="71338-255">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="71338-256">例如, 為了協助減少誤報, 您可以設定規則的相符準確度, 使其只符合具有最高信賴等級的模式。</span><span class="sxs-lookup"><span data-stu-id="71338-256">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="71338-257">瞭解信賴等級的計算方式有點棘手 (超出此文章的範圍), 但以下是[如何使用信賴等級調整規則](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的好說明。</span><span class="sxs-lookup"><span data-stu-id="71338-257">Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).</span></span>

<span data-ttu-id="71338-258">最後, 如果您想要更深入地取得, 您可以自訂任何敏感資訊類型--例如, 您可以從[澳大利亞駕照](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)的關鍵字清單中移除 "悉尼 NSW", 以消除上述假正向觸發。</span><span class="sxs-lookup"><span data-stu-id="71338-258">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="71338-259">若要瞭解如何使用 XML 和 PowerShell 來執行這項作業, 請參閱本主題關於[自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="71338-259">To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="71338-260">關閉 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="71338-260">Turn off a DLP policy</span></span>

<span data-ttu-id="71338-261">當您很高興, 您的 DLP 原則會正確且有效地偵測敏感資訊類型, 而您的使用者已準備好處理所需的原則, 您就可以啟用該原則。</span><span class="sxs-lookup"><span data-stu-id="71338-261">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![開啟原則的選項](media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="71338-263">如果您要查看原則何時生效, 請連線[至安全性 & 規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) , 並執行[DlpCompliancePolicy 指令程式](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps), 以查看 DistributionStatus。</span><span class="sxs-lookup"><span data-stu-id="71338-263">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![在 PowerShell 中執行 Cmdlet](media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="71338-265">開啟 DLP 原則之後, 您應該對自己執行一些最終測試, 以確保預期的原則動作正在進行中。</span><span class="sxs-lookup"><span data-stu-id="71338-265">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="71338-266">如果您嘗試測試像是信用卡資料之類的內容, 則網站會有有關如何產生範例信用卡或其他個人資訊的資訊, 這些資訊會透過校驗和觸發您的原則。</span><span class="sxs-lookup"><span data-stu-id="71338-266">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="71338-267">允許使用者覆寫的原則會將該選項呈現給使用者, 成為原則提示的一部分。</span><span class="sxs-lookup"><span data-stu-id="71338-267">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![允許使用者覆寫的原則提示](media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="71338-269">限制內容的原則會將警告傳送給使用者, 成為原則提示的一部分, 並防止他們傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="71338-269">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![內容受限的原則提示](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="71338-271">摘要</span><span class="sxs-lookup"><span data-stu-id="71338-271">Summary</span></span>

<span data-ttu-id="71338-272">資料遺失防護原則對所有類型的組織都很有用。</span><span class="sxs-lookup"><span data-stu-id="71338-272">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="71338-273">測試某些 DLP 原則是因為您對原則提示、使用者覆寫及附隨報告等專案所做的控制, 造成的風險很低。</span><span class="sxs-lookup"><span data-stu-id="71338-273">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="71338-274">您可以以安靜模式測試某些 DLP 原則, 以查看組織中已發生的違規類型, 然後使用低 false 正值來製作原則, 並對您的使用者提供允許且不允許的專案, 然後將 DLP 原則推出至公司.</span><span class="sxs-lookup"><span data-stu-id="71338-274">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
