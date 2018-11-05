---
title: 建立自訂機密資訊類型
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在 Office 365 安全性與合規性中心的圖形使用者介面中建立、修改、移除及測試 DLP 的自訂機密資訊類型。
ms.openlocfilehash: 55c7476a1162f657194b9dab4376afb34a76c3f3
ms.sourcegitcommit: e044b4fd72e4151cd17bf2ad05acc057e0c0d45f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2018
ms.locfileid: "25895282"
---
# <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="eb8e2-103">建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-103">Create a custom sensitive information type</span></span>

<span data-ttu-id="eb8e2-p101">Office 365 中的資料外洩防護 (DLP) 包含許多內建[機密資訊類型](what-the-sensitive-information-types-look-for.md)，可讓您在 DLP 原則中使用。這些內件類型可以協助識別及保護信用卡號碼、銀行帳號、護照號碼等等。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p101">Data loss prevention (DLP) in Office 365 includes many [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 

<span data-ttu-id="eb8e2-106">但是，如果您需要識別及保護不同類型的機密資訊 (例如使用貴組織專屬格式的員工識別碼或專案編號)，則可以建立自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-106">But if you need to identify and protect a different type of sensitive information - for example, an employee ID that uses a format specific to your organization - you can create a custom sensitive information type. A sensitive information type is defined in an XML file called a rule package.</span></span>

<span data-ttu-id="eb8e2-107">自訂機密資訊類型的基礎部分如下：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-107">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="eb8e2-108">**主要模式**：員工識別碼、專案編號等等。這通常由規則運算式 (RegEx) 識別，但它也可以是關鍵字清單。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-108">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="eb8e2-p102">**其他辨識項**：假設您正在尋找九位數的員工識別碼。並非所有的九位數都是員工識別碼，因此您可以搜尋其他文字：像是 "employee"、"badge"、"ID" 這類的關鍵字，或其他以規則運算式為基礎的文字模式。此支援辨識項 (也稱為_支援_或_確切_辨識項)，可增加在內容中找到的九位數確實為員工識別碼的可能性。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p102">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="eb8e2-p103">**字元近似值**：主要模式與支援辨識項彼此越接近，偵測到的內容越可能是您要尋找的內容，這是合理的。您可以指定主要模式與支援辨識項之間的字元距離 (也稱為_近似值視窗_)，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p103">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![確切辨識項和近似值視窗的圖表](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="eb8e2-p104">**信賴等級**：您具有的支援辨識項越多，相符項目包含您要尋找的機密資訊的可能性就越高。您可以針對使用更多辨識項偵測到的相符項目指派更高等級的信賴。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p104">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="eb8e2-p105">滿足條件時，模式會傳回計數和信賴等級，您可以在 DLP 原則的條件中使用。當您將會偵測機密資訊類型的條件新增至 DLP 原則時，可以編輯計數和信賴等級，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p105">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>

    ![執行個體計數和比對正確性選項](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

<span data-ttu-id="eb8e2-120">若要在 Office 365 安全性與合規性中心建立自訂機密資訊類型，您有下列選項：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-120">To create custom sensitive information types in the Office 365 Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="eb8e2-p106">**使用 UI**：這種方法更輕鬆且更快，但您具有的設定選項比 PowerShell 少。本主題的其餘內容將說明這些程序。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p106">**Use the UI**: This method is easier and faster, but you have less configuration options than PowerShell. The rest of this topic describes these procedures.</span></span>

- <span data-ttu-id="eb8e2-p107">**使用 PowerShell**：這種方法需要您先建立 XML 檔案 (稱為_規則套件_)，其中包含一或多個機密資訊類型，然後使用 PowerShell 來匯入規則套件 (與建立規則套件相較，匯入規則套件更容易解決。這種方法遠比 UI 複雜得多，但您有更多的設定選項。如需相關指示，請參閱[在 Office 365 安全性與合規性中心 PowerShell 中建立自訂機密資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p107">**Use PowerShell**: This method requires that you first create an XML file (called a _rule package_) that contains one or more sensitive information types, and then you use PowerShell to import the rule package (importing the rule package is trivial compared to creating the rule package. This method is much more complex than the UI, but you have more configuration options. For instructions, see [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

<span data-ttu-id="eb8e2-126">下表說明重要差異：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-126">The differences are described in the following list.</span></span>

|<span data-ttu-id="eb8e2-127">UI 中的自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-127">Custom sensitive information types in the UI</span></span>|<span data-ttu-id="eb8e2-128">PowerShell 中的自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-128">Custom sensitive information types in PowerShell</span></span>|
|:-----|:-----|
|<span data-ttu-id="eb8e2-129">名稱與描述為同一種語言。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-129">Name and Description are in one language.</span></span>|<span data-ttu-id="eb8e2-130">支援名稱與描述使用多種語言。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-130">Supports multiple languages for Name and Description.</span></span>|
|<span data-ttu-id="eb8e2-131">支援一種模式。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-131">Supports one pattern.</span></span>|<span data-ttu-id="eb8e2-132">支援多種模式。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-132">Supports multiple patterns.</span></span>|
|<span data-ttu-id="eb8e2-133">支援辨識項可以是：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-133">Supporting evidence can be:</span></span> <br/><span data-ttu-id="eb8e2-134">• 規則運算式</span><span class="sxs-lookup"><span data-stu-id="eb8e2-134">• Regular expressions</span></span> <br/><span data-ttu-id="eb8e2-135">• 關鍵字</span><span class="sxs-lookup"><span data-stu-id="eb8e2-135">• Keywords</span></span> <br/><span data-ttu-id="eb8e2-136">• 關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="eb8e2-136">• Keyword dictionaries</span></span>|<span data-ttu-id="eb8e2-137">支援辨識項可以是：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-137">Supporting evidence can be:</span></span> <br/><span data-ttu-id="eb8e2-138">• 規則運算式</span><span class="sxs-lookup"><span data-stu-id="eb8e2-138">• Regular expressions</span></span> <br/><span data-ttu-id="eb8e2-139">• 關鍵字</span><span class="sxs-lookup"><span data-stu-id="eb8e2-139">• Keywords</span></span> <br/><span data-ttu-id="eb8e2-140">• 關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="eb8e2-140">• Keyword dictionaries</span></span> <br/><span data-ttu-id="eb8e2-141">• [內建 DLP 函數](what-the-dlp-functions-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="eb8e2-141">• [Built-in DLP functions](what-the-dlp-functions-look-for.md)</span></span>|
|<span data-ttu-id="eb8e2-142">自訂機密資訊類型會新增到名為 Microsoft.SCCManaged.CustomRulePack 的規則套件</span><span class="sxs-lookup"><span data-stu-id="eb8e2-142">Custom sensitive information types are added to the rule package named Microsoft.SCCManaged.CustomRulePack</span></span>|<span data-ttu-id="eb8e2-143">您最多可以建立 10 個包含自訂機密資訊類型的規則套件。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-143">You can create up to 10 rule packages that contain custom sensitive information types.</span></span>|
|<span data-ttu-id="eb8e2-144">模式比對需要偵測主要模式及所有支援辨識項 (使用隱含的 AND 運算子)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-144">Pattern match requires the detection of the primary pattern and all supporting evidence (the implicit AND operator is used).</span></span>|<span data-ttu-id="eb8e2-145">模式比對需要偵測主要模式及可設定數量的支援辨識項 (可以使用隱含的 AND 及 OR 運算子)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-145">Pattern match requires the detection of the primary pattern and a configurable amount of supporting evidence (implicit AND and OR operators can be used).</span></span>|

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eb8e2-146">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="eb8e2-146">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eb8e2-147">若要開啟安全性與合規性中心，請參閱[移至 Office 365 安全性與合規性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-147">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="eb8e2-p108">自訂機密資訊類型需要熟悉規則運算式 (RegEx)。如需用於處理文字之 Boost.RegEx (先前稱為 RegEx++) 引擎的詳細資訊，請參閱 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p108">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="eb8e2-p109">Microsoft 客戶服務與支援中心無法協助提供自訂內容比對定義 (建立自訂分類或規則運算式模式)。支援工程師可以提供有限的功能支援 (例如，基於測試目的提供範例規則運算式模式，或協助對未如預期般觸發的現有規則運算式模式進行疑難排解)，但無法保證任何自訂內容比對開發作業將符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p109">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="eb8e2-p110">DLP 會使用搜尋編目程式來識別並分類 SharePoint Online 和商務用 OneDrive 中的機密資訊。若要識別現有內容中的新自訂機密資訊類型，必須重新編目內容。內容是根據排程來重新編目，但您可以手動重新編目網站集合、清單或文件庫的內容。如需詳細資訊，請參閱[手動要求編目或重新檢索網站、文件庫或清單](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p110">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="eb8e2-156">在安全性與合規性中心建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-156">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="eb8e2-157">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-157">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="eb8e2-158">這些設定不言而喻，並會在精靈的關聯頁面上加以說明：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-158">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="eb8e2-159">**名稱**</span><span class="sxs-lookup"><span data-stu-id="eb8e2-159">**Name**</span></span>

- <span data-ttu-id="eb8e2-160">**描述**</span><span class="sxs-lookup"><span data-stu-id="eb8e2-160">**Description**</span></span>

- <span data-ttu-id="eb8e2-161">**近似值**</span><span class="sxs-lookup"><span data-stu-id="eb8e2-161">**Proximity**</span></span>

- <span data-ttu-id="eb8e2-162">**信賴等級**</span><span class="sxs-lookup"><span data-stu-id="eb8e2-162">**Confidence level**</span></span>

- <span data-ttu-id="eb8e2-163">**主要模式元素** (關鍵字、規則運算式或字典)</span><span class="sxs-lookup"><span data-stu-id="eb8e2-163">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="eb8e2-164">選用的**支援模式元素** (關鍵字、規則運算式或字典) 及其對應**最低成本**值。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-164">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="eb8e2-p111">以下是案例：您想要一個自訂機密資訊類型，偵測內容中 9 位數的員工編號，以及關鍵字 "employee"、"ID" 及 "badge"。若要建立此自訂機密資訊類型，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p111">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="eb8e2-167">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-167">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

2. <span data-ttu-id="eb8e2-168">在開啟的 [**選擇名稱和描述**] 頁面中，輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-168">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="eb8e2-169">**名稱**：員工識別碼。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-169">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="eb8e2-170">**描述**：偵測九位數 Contoso 員工編號。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-170">**Description** Detect nine-digit Contoso employee ID numbers.</span></span>

  <span data-ttu-id="eb8e2-171">完成後，按 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-171">When you're finished, click **Save**.</span></span>

3. <span data-ttu-id="eb8e2-172">在 [**比對需求**] 頁面中，按一下 [**新增元素**] 來設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-172">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

  - <span data-ttu-id="eb8e2-173">**偵測包含下列項目的內容**：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-173">**Detect content containing**:</span></span>
 
    <span data-ttu-id="eb8e2-p112">a 按一下 [**其中任一個**]，然後選取 [**規則運算式**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p112">a. Click **Any of these** and select **Regular expression**.</span></span>

    <span data-ttu-id="eb8e2-p113">b. 在規則運算式方塊中，輸入 `(\s)(\d{9})(\s)` (以空格括住九位數的號碼)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p113">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
  - <span data-ttu-id="eb8e2-178">**支援項目**：按一下 [**新增支援項目**]，然後選取 [**包含此關鍵字清單**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-178">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

  - <span data-ttu-id="eb8e2-179">在出現的 [**包含此關鍵字清單**] 區域中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-179">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

    - <span data-ttu-id="eb8e2-180">**關鍵字清單**：輸入下列值：員工、識別碼、徽章。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-180">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

    - <span data-ttu-id="eb8e2-181">**最小計數**：保留預設值 1。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-181">**Minimum count**: Leave the default value 1.</span></span>

  - <span data-ttu-id="eb8e2-182">保留預設**信賴等級**值 60。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-182">Leave the default **Confidence level** value 60.</span></span> 

  - <span data-ttu-id="eb8e2-183">保留預設**字元近似值** 300。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-183">Leave the default **Character proximity** value 300.</span></span>

  <span data-ttu-id="eb8e2-184">完成後，按 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-184">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="eb8e2-185">在開啟的 [**檢閱並完成**] 頁面上，檢閱設定並按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-185">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

5. <span data-ttu-id="eb8e2-p114">下一個頁面鼓勵您測試新的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。否則，按一下 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p114">The next page encourages you to test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). Otherwise, click **Cancel**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="eb8e2-189">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="eb8e2-189">How do you know this worked?</span></span>

<span data-ttu-id="eb8e2-190">若要確認您已成功建立新的機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-190">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="eb8e2-191">移至 [**分類**] \> [**機密資訊類型**]，並確認已列出新的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-191">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="eb8e2-p115">測試新的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p115">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="eb8e2-194">在安全性與合規性中心修改自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-194">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="eb8e2-p116">**附註**：您只能修改自訂機密資訊類型，不能修改內建的機密資訊類型。但您可以使用 PowerShell 來匯出內建的自訂機密資訊類型、自訂它們，並將其匯入為自訂機密資訊類型。如需詳細資訊，請參閱[自訂內建的機密資訊類型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p116">**Note**: You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

<span data-ttu-id="eb8e2-198">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後選取您想要修改的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-198">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select the custom sensitive information type that you want to modify.</span></span>

<span data-ttu-id="eb8e2-p117">這裡提供與您在安全性與合規性中心建立自訂機密資訊類型時相同的選項。如需詳細資訊，請參閱[在安全性與合規性中心建立自訂機密資訊類型](#create-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p117">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="eb8e2-201">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="eb8e2-201">How do you know this worked?</span></span>

<span data-ttu-id="eb8e2-202">若要確認您已成功修改機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-202">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="eb8e2-203">移至 [**分類**] \> [**機密資訊類型**]，以驗證已修改之自訂機密資訊類型的內容。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-203">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span>

  - <span data-ttu-id="eb8e2-p118">測試已修改的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p118">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="eb8e2-206">移除安全性與合規性中心的自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-206">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="eb8e2-207">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eb8e2-207">**Notes**:</span></span>

- <span data-ttu-id="eb8e2-208">您只能移除自訂機密資訊類型，不能移除內建的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-208">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="eb8e2-209">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-209">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="eb8e2-210">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後選取一或多個您想要移除的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-210">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="eb8e2-211">在開啟的飛出視窗中，按一下 [**刪除**] (或 [**刪除機密資訊類型**]，如果您已選取多個的話)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-211">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

3. <span data-ttu-id="eb8e2-212">在出現的警告訊息中，按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-212">In the warning that appears, click yes.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="eb8e2-213">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="eb8e2-213">How do you know this worked?</span></span>

<span data-ttu-id="eb8e2-214">若要確認您已成功移除自訂機密資訊類型，請移至 [**分類**] \> [**機密資訊類型**]，以確認不再列出自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-214">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>


## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="eb8e2-215">在安全性與合規性中心測試自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="eb8e2-215">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="eb8e2-216">在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-216">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="eb8e2-p119">選取要測試的一或多個自訂機密資訊類型。在開啟的飛出視窗中，按一下 [**測試類型**] (或 [**測試機密資訊類型**]，如果您已選取多個的話)。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-p119">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

3. <span data-ttu-id="eb8e2-219">在開啟的頁面上，拖放檔案，或按一下 [**瀏覽**] 並選取檔案，來上傳要測試的文件。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-219">On the page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

4. <span data-ttu-id="eb8e2-220">按一下 [**測試**] 按鈕，來測試文件以在檔案中進行模式比對。</span><span class="sxs-lookup"><span data-stu-id="eb8e2-220">Click the **Test** button to test the document for pattern matches in the file.</span></span>
