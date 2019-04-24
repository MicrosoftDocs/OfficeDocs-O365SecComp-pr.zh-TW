---
title: 在 Office 365 進階電子文件探索中設定略過文字分析選項
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解如何定義規則以在 Office 365 進階電子文件探索中使用的分析和處理序模組時，略過特定的文字。  '
ms.openlocfilehash: 3a4c1d17a9a56d3018509a8dcfd6b49abb951676
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260817"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="36eb6-103">在 Office 365 進階電子文件探索中設定略過文字分析選項</span><span class="sxs-lookup"><span data-stu-id="36eb6-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="36eb6-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="36eb6-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="36eb6-106">略過文字功能可以套用至所有或任何下列的進階電子文件模組： 分析 （近似重複項目，電子郵件執行緒，佈景主題） 與相關性。</span><span class="sxs-lookup"><span data-stu-id="36eb6-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="36eb6-107">略過的文字不會出現在將檔案顯示在 [相關性，並分析/計算會捨棄略過的文字。</span><span class="sxs-lookup"><span data-stu-id="36eb6-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="36eb6-108">如果略過文字功能先前定義已執行的模組，略過文字設定現在被防止要修改的影響。</span><span class="sxs-lookup"><span data-stu-id="36eb6-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="36eb6-109">不過，相關性模組的略過文字功能仍然可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="36eb6-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="36eb6-110">如何套用略過文字篩選器</span><span class="sxs-lookup"><span data-stu-id="36eb6-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="36eb6-111">所輸入的順序套用多個略過文字篩選器。</span><span class="sxs-lookup"><span data-stu-id="36eb6-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="36eb6-112">若要變更已套用的順序，他們必須刪除並重新輸入想要的順序。</span><span class="sxs-lookup"><span data-stu-id="36eb6-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="36eb6-113">例如，如果文字的內容: 「 目前 BOB ALICE CAROL eve 進行 」，以下是搜尋時忽略的文字項目和結果的範例：</span><span class="sxs-lookup"><span data-stu-id="36eb6-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="36eb6-114">**略過的文字項目**</span><span class="sxs-lookup"><span data-stu-id="36eb6-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="36eb6-115">**Results**</span><span class="sxs-lookup"><span data-stu-id="36eb6-115">**Results**</span></span> <br/> |
|<span data-ttu-id="36eb6-116">「 ALICE 」、 「 BOB 收件者 」</span><span class="sxs-lookup"><span data-stu-id="36eb6-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="36eb6-117">「 目前 EVE 進行 」</span><span class="sxs-lookup"><span data-stu-id="36eb6-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="36eb6-118">「 ALICE"，"BOB ALICE CAROL 」</span><span class="sxs-lookup"><span data-stu-id="36eb6-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="36eb6-119">「 目前 BOB CAROL EVE 進行 」</span><span class="sxs-lookup"><span data-stu-id="36eb6-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="36eb6-120">因為字串找不到因此套用略過的第一個文字後，不被實作的第二個略過文字項目。</span><span class="sxs-lookup"><span data-stu-id="36eb6-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="36eb6-121">定義搜尋時忽略的文字時使用規則運算式</span><span class="sxs-lookup"><span data-stu-id="36eb6-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="36eb6-122">定義搜尋時忽略的文字時使用的支援規則運算式。</span><span class="sxs-lookup"><span data-stu-id="36eb6-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="36eb6-123">規則運算式語法和使用狀況的範例如下：</span><span class="sxs-lookup"><span data-stu-id="36eb6-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="36eb6-124">若要移除 （忽略） 從開始，直到線條結尾的文字：</span><span class="sxs-lookup"><span data-stu-id="36eb6-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="36eb6-125">其中 「 開始 」 是此字串在一行之初始項目。</span><span class="sxs-lookup"><span data-stu-id="36eb6-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="36eb6-126">例如，針對下列文字：</span><span class="sxs-lookup"><span data-stu-id="36eb6-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="36eb6-127">**「 這是第一個句子和第一行**</span><span class="sxs-lookup"><span data-stu-id="36eb6-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="36eb6-128">**這是第二個句子和第二行 」**</span><span class="sxs-lookup"><span data-stu-id="36eb6-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="36eb6-129">規則運算式 first(.\*)$ 會導致：</span><span class="sxs-lookup"><span data-stu-id="36eb6-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="36eb6-130">**「 這是**</span><span class="sxs-lookup"><span data-stu-id="36eb6-130">**"This is**</span></span>
    
    <span data-ttu-id="36eb6-131">**這是第二個句子和第二行 」**</span><span class="sxs-lookup"><span data-stu-id="36eb6-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="36eb6-132">若要移除的免責聲明與自動插入的電子郵件執行緒結尾處的法律陳述式：</span><span class="sxs-lookup"><span data-stu-id="36eb6-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="36eb6-133">其中 「 開始 」 和 「 結束 」 是唯一的字串的開頭和換行的文字段落的結尾。</span><span class="sxs-lookup"><span data-stu-id="36eb6-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="36eb6-134">例如，下列規則運算式會移除免責聲明和已 Begin 和 End 字串之間的電子郵件執行緒中的法律陳述式：</span><span class="sxs-lookup"><span data-stu-id="36eb6-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="36eb6-135">**此郵件會包含機密資訊 (。 |\s)\*如果需要驗證，則請要求紙版本**</span><span class="sxs-lookup"><span data-stu-id="36eb6-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="36eb6-136">若要移除免責聲明 （包括特殊字元）：</span><span class="sxs-lookup"><span data-stu-id="36eb6-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="36eb6-137">例如，針對 （使用免責聲明這裡以 x 控點） 的下列文字：</span><span class="sxs-lookup"><span data-stu-id="36eb6-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="36eb6-138">**/\*\ 此郵件會包含機密資訊。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="36eb6-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="36eb6-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="36eb6-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="36eb6-140">\**xxxx xxxx 如果驗證是必要的請要求書面版的版本。/\*\**</span><span class="sxs-lookup"><span data-stu-id="36eb6-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="36eb6-141">若要移除上述免責聲明的規則運算式應該先：</span><span class="sxs-lookup"><span data-stu-id="36eb6-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="36eb6-142">**\/\\*\\此郵件會包含機密資訊\.(。 |\s)\*如果需要驗證，則請要求紙版本\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="36eb6-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="36eb6-143">規則運算式規則：</span><span class="sxs-lookup"><span data-stu-id="36eb6-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="36eb6-144">為不屬於空間，「 _ 」 除了英文字母的任何字元和 「-」 必須加上"\"。</span><span class="sxs-lookup"><span data-stu-id="36eb6-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="36eb6-145">一般 eExpression 欄位可以是無限制的長度。</span><span class="sxs-lookup"><span data-stu-id="36eb6-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="36eb6-146">說明與規則運算式的詳細的語法，請參閱：[規則運算式語言-快速參考](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36eb6-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="36eb6-147">定義規則，略過的文字</span><span class="sxs-lookup"><span data-stu-id="36eb6-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="36eb6-148">在 [**管理\>分析\>分析選項**] 索引標籤的 [**略過的文字**] 區段中，按一下 [**+** 圖示以新增規則。</span><span class="sxs-lookup"><span data-stu-id="36eb6-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="36eb6-149">在 [**新增略過的文字**] 對話方塊中，在 [**名稱**] 欄位中，輸入略過文字規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="36eb6-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![加入略過的文字](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="36eb6-151">在 [**文字**] 方塊中，輸入要忽略的文字。</span><span class="sxs-lookup"><span data-stu-id="36eb6-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="36eb6-152">[文字] 欄位允許的字元數目不受限制。</span><span class="sxs-lookup"><span data-stu-id="36eb6-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="36eb6-153">上方視窗所示，按一下 [若要查看略過文字規則的一般語法指導方針的**燈泡**。</span><span class="sxs-lookup"><span data-stu-id="36eb6-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="36eb6-154">如有需要，請選取**區分大小寫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="36eb6-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="36eb6-155">在 [**套用至**] 清單中，選取用來套用定義的進階電子文件模組。</span><span class="sxs-lookup"><span data-stu-id="36eb6-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="36eb6-156">如果您想在範例文字上執行測試，請在 [**輸入**文字] 方塊中輸入範例文字，然後按一下 [**測試**。</span><span class="sxs-lookup"><span data-stu-id="36eb6-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="36eb6-157">結果會顯示在 [**輸出**] 文字方塊中。</span><span class="sxs-lookup"><span data-stu-id="36eb6-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="36eb6-158">按一下 **[確定]** 以儲存搜尋時忽略文字規則]。</span><span class="sxs-lookup"><span data-stu-id="36eb6-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="36eb6-159">會顯示已定義的搜尋時忽略文字規則。</span><span class="sxs-lookup"><span data-stu-id="36eb6-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![設定忽略文字名稱](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="36eb6-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="36eb6-161">See also</span></span>

[<span data-ttu-id="36eb6-162">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="36eb6-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="36eb6-163">了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="36eb6-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="36eb6-164">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="36eb6-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="36eb6-165">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="36eb6-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="36eb6-166">檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="36eb6-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

