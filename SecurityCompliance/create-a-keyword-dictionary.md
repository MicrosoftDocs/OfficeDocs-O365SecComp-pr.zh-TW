---
title: 建立關鍵字字典
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 識別敏感資訊有時會需要尋找關鍵字，尤其在識別泛用內容 (例如醫療保健相關的通訊) 或不適當或明確的語言時更是需要。儘管您可以建立敏感資訊類型的關鍵字清單，但關鍵字清單的大小會受到限制，而且需要修改 XML 才能建立或編輯它們。關鍵字字典可提供更簡單的關鍵字管理以及更為龐大的關鍵字規模，每部字典最多可支援 100,000 個字詞。
ms.openlocfilehash: 6f0ca634e903509e9c0a92472501341eff7aa3fe
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454835"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="e08c6-105">建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="e08c6-105">Create a keyword dictionary</span></span>

<span data-ttu-id="e08c6-p102">Office 365 中的資料外洩防護 (DLP) 可以識別、監視和保護您的敏感資訊。識別敏感資訊有時會需要尋找關鍵字，尤其在識別泛用內容 (例如醫療保健相關的通訊) 或不適當或明確的語言時更是需要。儘管您可以建立敏感資訊類型的關鍵字清單，但關鍵字清單的大小會受到限制，而且需要修改 XML 才能建立或編輯它們。關鍵字字典可提供更簡單的關鍵字管理以及更為龐大的關鍵字規模，每部字典最多可支援 100000 個字詞。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p102">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information. Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication) or inappropriate or explicit language. While you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them. Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="e08c6-110">建立關鍵字字典的基本步驟</span><span class="sxs-lookup"><span data-stu-id="e08c6-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="e08c6-p103">字典的關鍵字可以來自各種來源，最常來自檔案 (例如 .csv 或 .txt 清單)、來自您直接在 Cmdlet 中輸入的清單，或來自現有的字典。當建立關鍵字字典時，您會依照相同的核心步驟：</span><span class="sxs-lookup"><span data-stu-id="e08c6-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list), from a list you enter directly in the cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="e08c6-113">**連接到安全性與合規性中心 PowerShell** - 請參閱[本主題](https://docs.microsoft.com/zh-TW/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="e08c6-113">**Connect to Security &amp; Compliance Center PowerShell** - see [this topic](https://docs.microsoft.com/zh-TW/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="e08c6-114">**定義關鍵字或從您想要的來源載入關鍵字** - 建立關鍵字字典的 Cmdlet 接受逗點分隔的關鍵字清單，因此這個步驟會根據您的關鍵字來自何處而略有不同。</span><span class="sxs-lookup"><span data-stu-id="e08c6-114">**Define or load your keywords from your intended source** - the cmdlet to create a keyword dictionary accepts a comma-separated list of keywords, so this step will vary slightly depending on where your keywords come from.</span></span> 
    
3. <span data-ttu-id="e08c6-115">**編碼關鍵字** - 一旦載入，就會將它們轉換為位元組陣列，然後再匯入它們。</span><span class="sxs-lookup"><span data-stu-id="e08c6-115">**Encode your keywords** - once loaded, they're converted to a byte array before they're imported.</span></span> 
    
4. <span data-ttu-id="e08c6-116">**建立字典** - 選擇名稱和描述，然後建立字典。</span><span class="sxs-lookup"><span data-stu-id="e08c6-116">**Create your dictionary** - choose a name and description and create your dictionary.</span></span> 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a><span data-ttu-id="e08c6-117">從檔案建立關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="e08c6-117">Create a keyword dictionary from a file</span></span>

<span data-ttu-id="e08c6-p104">通常當您需要建立大型字典時，可以使用來自檔案或從其他來源匯出之清單的關鍵字。在此情況下，您將建立一部關鍵字字典，其中包含一個清單，列出要在外部電子郵件中篩檢的不適當語言。首先您需要[連接到 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/zh-TW/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p104">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You need to first [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/zh-TW/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="e08c6-121">將關鍵字複製到文字檔案，並確定每個關鍵字位於個別行。</span><span class="sxs-lookup"><span data-stu-id="e08c6-121">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="e08c6-p105">使用 Unicode 編碼來儲存檔案。在 [記事本] \> [另存新檔]\*\*\*\* \> [編碼]\*\*\*\* \> [Unicode]\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p105">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="e08c6-124">執行下列 Cmdlet 將檔案讀成變數：</span><span class="sxs-lookup"><span data-stu-id="e08c6-124">Read the file into a variable by running this cmdlet:</span></span>
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. <span data-ttu-id="e08c6-125">執行下列 Cmdlet 來建立字典：</span><span class="sxs-lookup"><span data-stu-id="e08c6-125">Create the dictionary by running this cmdlet:</span></span>
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="e08c6-126">修改現有的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="e08c6-126">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="e08c6-p106">您可能需要修改其中一部關鍵字字典中的關鍵字，或修改其中一部內建字典。在此範例中，我們將在 PowerShell 中修改一些字詞、將這些字詞儲存在本機 (在這裡您可以使用編輯器來修改它們)，然後適當地更新先前的字詞。首先，擷取字典物件：</span><span class="sxs-lookup"><span data-stu-id="e08c6-p106">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries. In this example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place. First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="e08c6-p107">列印 `$dict` 將顯示各種變數。關鍵字本身會儲存在後端上的物件中，但 `$dict.KeywordDictionary` 包含它們的字串表示，您將用來修改字典。在修改字典之前，您需要使用 `.split(',')` 方法，將一串字詞變回陣列。然後，您將使用 `.trim()` 方法，清除關鍵字之間不需要的空格，只留下要使用的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p107">Printing  `$dict` will show the various variables. The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary. Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method. Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="e08c6-p108">現在您將從字典中移除一些字詞。因為範例字典只有幾個關鍵字，所以您可以輕鬆地略過移除，直接匯出字典，並在 [記事本] 中編輯該字典，但字典通常包含大量文字，因此您首先將學習此方法，以在 PowerShell 中輕鬆地編輯它們。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p108">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="e08c6-p109">在最後一個步驟中，您已將關鍵字儲存到陣列。有幾種方法可[從陣列中移除字詞](https://go.microsoft.com/fwlink/p/?linkid=852620) (英文)，但直接方法為建立您要從字典中移除之字詞的陣列，然後只將不在要移除之字詞清單中的字典字詞複製到其中。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p109">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://go.microsoft.com/fwlink/p/?linkid=852620), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="e08c6-p110">執行命令 `$terms` 來顯示目前的字詞清單。命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="e08c6-p110">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="e08c6-140">執行下列命令來指定您想要移除的字詞：</span><span class="sxs-lookup"><span data-stu-id="e08c6-140">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="e08c6-141">執行下列命令來實際移除清單中的字詞：</span><span class="sxs-lookup"><span data-stu-id="e08c6-141">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="e08c6-p111">執行命令 `$updatedTerms` 來顯示已更新的字詞清單。命令的輸出看起來像這樣 (已移除指定的字詞)：</span><span class="sxs-lookup"><span data-stu-id="e08c6-p111">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="e08c6-p112">現在將字典儲存在本機，並再新增一些字詞。在 PowerShell 中，您可以直接在這裡新增字詞，但您仍需要在本機匯出檔案，以確保它是以 Unicode 編碼儲存，且包含 BOM。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p112">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="e08c6-146">執行下列命令，將字典儲存在本機：</span><span class="sxs-lookup"><span data-stu-id="e08c6-146">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="e08c6-p113">現在只需開啟檔案、新增其他字詞，並以 Unicode 編碼 (UTF-16) 儲存。現在，您將上傳更新的字詞並適當地更新字典。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p113">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="e08c6-p114">現在您已適當地更新字典。請注意，`Identity` 欄位會採用字典的名稱。如果您也想要使用 `set-` Cmdlet 來變更字典的名稱，只需將 `-Name` 參數與新的字典名稱新增至上述的命令即可。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p114">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="e08c6-152">使用自訂敏感資訊類型和 DLP 原則中的關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="e08c6-152">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="e08c6-p115">關鍵字字典可以做為自訂機密資訊類型之比對需求的一部分，或做為機密資訊類型本身。兩者都需要[在 Office 365 安全性與合規性中心 PowerShell 中建立自訂機密資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。請依照連結文章中的指示來建立機密資訊類型。一旦有了 XML，您將需要字典的 GUID 識別碼才能使用它。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p115">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves. Both require [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). Follow the instructions in the linked article to create a sensitive information type. Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="e08c6-157">若要取得字典的身分識別，請執行下列命令，然後複製 **Identity** 屬性值：</span><span class="sxs-lookup"><span data-stu-id="e08c6-157">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="e08c6-158">此命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="e08c6-158">The output of the command looks like this:</span></span>
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

<span data-ttu-id="e08c6-p116">將身分識別貼入您的自訂敏感資訊類型的 XML 並上傳它。現在字典將出現在敏感資訊類型的清單中，而且您可以在原則中直接使用它，同時指定需要比對多少個關鍵字。</span><span class="sxs-lookup"><span data-stu-id="e08c6-p116">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


