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
description: '了解如何定義的規則時使用的分析和程序的模組中 Office 365 進階 eDiscovery 搜尋時忽略特定的文字。  '
ms.openlocfilehash: 3a4c1d17a9a56d3018509a8dcfd6b49abb951676
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214243"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中設定略過文字分析選項

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
搜尋時忽略文字功能可以套用至所有或任何下列的進階的 eDiscovery 模組： 分析 （附近-重複、 電子郵件執行緒佈景主題） 與相關性。已忽略的文字不會出現在檔案中的相關性，顯示和分析/計算會捨棄已忽略的文字。
  
如果有搜尋時忽略文字功能先前已執行的模組定義搜尋時忽略的文字設定會立即保護加以修改。不過，相關性模組的搜尋時忽略文字功能仍可以隨時變更。
  
## <a name="how-ignore-text-filters-are-applied"></a>如何套用搜尋時忽略文字篩選器

他們所輸入的順序套用多個搜尋時忽略文字篩選。若要變更其套用順序，他們必須刪除並重新輸入想要的順序。
  
例如，如果文字內容："目前 BOB 艾莉斯 CAROL eve 進行"，以下是範例搜尋時忽略文字項目及結果：
  
||||
|:-----|:-----|:-----|
|**忽略文字項目** <br/> |**==\>** <br/> |**結果** <br/> |
|"艾莉斯"，"BOB 收件者 」  <br/> |==\>  <br/> |"目前 EVE 進行"  <br/> |
|"艾莉斯"，"BOB 艾莉斯 CAROL"  <br/> |==\>  <br/> |"目前 BOB CAROL EVE 進行"  <br/> |
   
第二個搜尋時忽略文字項目不會實作因為字串找不到因此套用第一個搜尋時忽略文字之後。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>定義搜尋時忽略的文字時使用規則運算式

定義搜尋時忽略的文字時使用支援規則運算式。規則運算式語法和使用狀況範例如下：
  
- 若要移除 （忽略） 從開始直到線條結尾的文字：
    
     `Begin(.*)$`
    
    其中 「 開始 」 是在一行這個字串初始出現。
    
    例如，如下列文字：
    
    **「 這是第一句和第一行**
    
    **這是第二個句子和第二行"**
    
    規則運算式 first(.\*)$ 會造成：
    
    **"This is**
    
    **這是第二個句子和第二行"**
    
- 若要移除免責聲明與自動插入結尾處的電子郵件執行緒的法律陳述式：
    
     `Begin(.|\s)*End`
    
    其中"Begin"和"結束"是唯一的字串開頭和文字換行的段落的結尾。 
    
    例如，下列的規則運算式將會移除免責聲明及在 Begin 和 End 字串之間的電子郵件執行緒的法律陳述式：
    
    **此訊息包含機密資訊 (。 |\s)\*如果需要驗證，請要求紙版本**
    
- 若要移除 （包含特殊字元） 免責聲明： 
    
    例如，為 （具有以下表示 x 控點的免責聲明） 的下列文字： 
    
    **/\*\ 此郵件包含機密資訊。是**
    
    **是是是是**
    
    **如果驗證才是請要求紙版本。/\*\**
    
    若要移除上述免責聲明的規則運算式應該先： 
    
    **\/\\*\\此訊息包含機密資訊\.(。 |\s)\*如果需要驗證，請要求紙版本\.\/\\*\\**
    
- 規則運算式規則：
    
  - 若為不屬於但不包括空間，"_"英文字母任何字元和"-"必須加上"\"。
    
  - 一般 eExpression 欄位可以不受限制的長度。
    
> [!TIP]
> 說明與之規則運算式的詳細的語法，請參閱：[規則運算式語言集快速參考 （英文）](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>定義搜尋時忽略文字規則

1. 在**管理\>分析\>分析選項**] 索引標籤的 [**搜尋時忽略的文字**] 區段中，按一下 [**+** 新增規則] 圖示。 
    
2. 在 [**新增搜尋時忽略的文字**] 對話方塊的 [**名稱**] 欄位中輸入搜尋時忽略文字規則的名稱。 
    
    ![加入略過的文字](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. [**文字**] 方塊中輸入要忽略的文字。[文字] 欄位允許無限制的數目的字元。 
    
    > [!TIP]
    > 視窗上面所示，按一下 [查看搜尋時忽略文字規則的一般語法指導方針的**燈泡**。 
  
4. 選取**區分大小寫**] 核取方塊，視。 
    
5. 在 [**套用]** 清單中選取要套用之定義的進階的 eDiscovery 模組。 
    
6. 如果您想在範例文字上執行測試，請在 [**輸入**] 文字方塊中輸入範例文字並按一下 [**測試**。結果會顯示在 [**輸出**] 文字方塊中。 
    
7. 按一下 **[確定]** 儲存搜尋時忽略文字規則]。會顯示已定義的搜尋時忽略文字規則。 
    
    ![設定忽略文字名稱](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)

