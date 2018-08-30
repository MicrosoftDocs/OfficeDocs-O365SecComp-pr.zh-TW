---
title: 在 Office 365 進階電子文件探索中設定略過文字分析選項
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解如何定義的規則時使用的分析和程序的模組中 Office 365 進階 eDiscovery 搜尋時忽略特定的文字。  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526796"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="402d8-103">在 Office 365 進階電子文件探索中設定略過文字分析選項</span><span class="sxs-lookup"><span data-stu-id="402d8-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="402d8-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="402d8-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="402d8-p102">搜尋時忽略文字功能可以套用至所有或任何下列的進階的 eDiscovery 模組： 分析 （附近-重複、 電子郵件執行緒佈景主題） 與相關性。已忽略的文字不會出現在檔案中的相關性，顯示和分析/計算會捨棄已忽略的文字。</span><span class="sxs-lookup"><span data-stu-id="402d8-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="402d8-p103">如果有搜尋時忽略文字功能先前已執行的模組定義搜尋時忽略的文字設定會立即保護加以修改。不過，相關性模組的搜尋時忽略文字功能仍可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="402d8-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="402d8-110">如何套用搜尋時忽略文字篩選器</span><span class="sxs-lookup"><span data-stu-id="402d8-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="402d8-p104">他們所輸入的順序套用多個搜尋時忽略文字篩選。若要變更其套用順序，他們必須刪除並重新輸入想要的順序。</span><span class="sxs-lookup"><span data-stu-id="402d8-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="402d8-113">例如，如果文字內容："目前 BOB 艾莉斯 CAROL eve 進行"，以下是範例搜尋時忽略文字項目及結果：</span><span class="sxs-lookup"><span data-stu-id="402d8-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="402d8-114">**忽略文字項目**</span><span class="sxs-lookup"><span data-stu-id="402d8-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="402d8-115">**結果**</span><span class="sxs-lookup"><span data-stu-id="402d8-115">**Results**</span></span> <br/> |
|<span data-ttu-id="402d8-116">"艾莉斯"，"BOB 收件者 」</span><span class="sxs-lookup"><span data-stu-id="402d8-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="402d8-117">"目前 EVE 進行"</span><span class="sxs-lookup"><span data-stu-id="402d8-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="402d8-118">"艾莉斯"，"BOB 艾莉斯 CAROL"</span><span class="sxs-lookup"><span data-stu-id="402d8-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="402d8-119">"目前 BOB CAROL EVE 進行"</span><span class="sxs-lookup"><span data-stu-id="402d8-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="402d8-120">第二個搜尋時忽略文字項目不會實作因為字串找不到因此套用第一個搜尋時忽略文字之後。</span><span class="sxs-lookup"><span data-stu-id="402d8-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="402d8-121">定義搜尋時忽略的文字時使用規則運算式</span><span class="sxs-lookup"><span data-stu-id="402d8-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="402d8-p105">定義搜尋時忽略的文字時使用支援規則運算式。規則運算式語法和使用狀況範例如下：</span><span class="sxs-lookup"><span data-stu-id="402d8-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="402d8-124">若要移除 （忽略） 從開始直到線條結尾的文字：</span><span class="sxs-lookup"><span data-stu-id="402d8-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="402d8-125">其中 「 開始 」 是在一行這個字串初始出現。</span><span class="sxs-lookup"><span data-stu-id="402d8-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="402d8-126">例如，如下列文字：</span><span class="sxs-lookup"><span data-stu-id="402d8-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="402d8-127">**「 這是第一句和第一行**</span><span class="sxs-lookup"><span data-stu-id="402d8-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="402d8-128">**這是第二個句子和第二行"**</span><span class="sxs-lookup"><span data-stu-id="402d8-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="402d8-129">規則運算式 first(.\*)$ 會造成：</span><span class="sxs-lookup"><span data-stu-id="402d8-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="402d8-130">**"This is**</span><span class="sxs-lookup"><span data-stu-id="402d8-130">**"This is**</span></span>
    
    <span data-ttu-id="402d8-131">**這是第二個句子和第二行"**</span><span class="sxs-lookup"><span data-stu-id="402d8-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="402d8-132">若要移除免責聲明與自動插入結尾處的電子郵件執行緒的法律陳述式：</span><span class="sxs-lookup"><span data-stu-id="402d8-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="402d8-133">其中"Begin"和"結束"是唯一的字串開頭和文字換行的段落的結尾。</span><span class="sxs-lookup"><span data-stu-id="402d8-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="402d8-134">例如，下列的規則運算式將會移除免責聲明及在 Begin 和 End 字串之間的電子郵件執行緒的法律陳述式：</span><span class="sxs-lookup"><span data-stu-id="402d8-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="402d8-135">**此訊息包含機密資訊 (。 |\s)\*如果需要驗證，請要求紙版本**</span><span class="sxs-lookup"><span data-stu-id="402d8-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="402d8-136">若要移除 （包含特殊字元） 免責聲明：</span><span class="sxs-lookup"><span data-stu-id="402d8-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="402d8-137">例如，為 （具有以下表示 x 控點的免責聲明） 的下列文字：</span><span class="sxs-lookup"><span data-stu-id="402d8-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="402d8-138">**/\*\ 此郵件包含機密資訊。是**</span><span class="sxs-lookup"><span data-stu-id="402d8-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="402d8-139">**是是是是**</span><span class="sxs-lookup"><span data-stu-id="402d8-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="402d8-140">\**如果驗證才是請要求紙版本。/\*\**</span><span class="sxs-lookup"><span data-stu-id="402d8-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="402d8-141">若要移除上述免責聲明的規則運算式應該先：</span><span class="sxs-lookup"><span data-stu-id="402d8-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="402d8-142">**\/\\*\\此訊息包含機密資訊\.(。 |\s)\*如果需要驗證，請要求紙版本\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="402d8-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="402d8-143">規則運算式規則：</span><span class="sxs-lookup"><span data-stu-id="402d8-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="402d8-144">若為不屬於但不包括空間，"_"英文字母任何字元和"-"必須加上"\"。</span><span class="sxs-lookup"><span data-stu-id="402d8-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="402d8-145">一般 eExpression 欄位可以不受限制的長度。</span><span class="sxs-lookup"><span data-stu-id="402d8-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="402d8-146">說明與之規則運算式的詳細的語法，請參閱：[規則運算式語言集快速參考 （英文）](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="402d8-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="402d8-147">定義搜尋時忽略文字規則</span><span class="sxs-lookup"><span data-stu-id="402d8-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="402d8-148">在**管理\>分析\>分析選項**] 索引標籤的 [**搜尋時忽略的文字**] 區段中，按一下 [**+** 新增規則] 圖示。</span><span class="sxs-lookup"><span data-stu-id="402d8-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="402d8-149">在 [**新增搜尋時忽略的文字**] 對話方塊的 [**名稱**] 欄位中輸入搜尋時忽略文字規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="402d8-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![加入略過的文字](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="402d8-p106">[**文字**] 方塊中輸入要忽略的文字。[文字] 欄位允許無限制的數目的字元。</span><span class="sxs-lookup"><span data-stu-id="402d8-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="402d8-153">視窗上面所示，按一下 [查看搜尋時忽略文字規則的一般語法指導方針的**燈泡**。</span><span class="sxs-lookup"><span data-stu-id="402d8-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="402d8-154">選取**區分大小寫**] 核取方塊，視。</span><span class="sxs-lookup"><span data-stu-id="402d8-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="402d8-155">在 [**套用]** 清單中選取要套用之定義的進階的 eDiscovery 模組。</span><span class="sxs-lookup"><span data-stu-id="402d8-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="402d8-p107">如果您想在範例文字上執行測試，請在 [**輸入**] 文字方塊中輸入範例文字並按一下 [**測試**。結果會顯示在 [**輸出**] 文字方塊中。</span><span class="sxs-lookup"><span data-stu-id="402d8-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="402d8-p108">按一下 **[確定]** 儲存搜尋時忽略文字規則]。會顯示已定義的搜尋時忽略文字規則。</span><span class="sxs-lookup"><span data-stu-id="402d8-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![設定忽略文字名稱](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="402d8-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="402d8-161">See also</span></span>

[<span data-ttu-id="402d8-162">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="402d8-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="402d8-163">了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="402d8-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="402d8-164">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="402d8-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="402d8-165">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="402d8-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="402d8-166">檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="402d8-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

