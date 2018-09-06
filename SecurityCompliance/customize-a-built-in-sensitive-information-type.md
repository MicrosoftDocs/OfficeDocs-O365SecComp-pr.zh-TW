---
title: 自訂內建機密資訊類型
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2164ce3d-4d64-4283-b6b1-b81fbe835e8e
description: 在內容中尋找機密資訊時，您需要以所謂的規則來說明資訊。資料外洩防護 (DLP) 包含您可以立即使用之最常用機密資訊類型的規則。若要使用這些規則，您必須將其包含在原則中。您也許想要調整這些內建規則以符合貴組織的特定需求，您可以藉由建立自訂機密資訊類型來完成。本主題說明如何自訂其中包含現有規則集合的 XML 檔案，以偵測更大範圍的潛在信用卡資訊。
ms.openlocfilehash: e0a2751ff8d89e664343e91937713af6af74264f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526410"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="486e1-107">自訂內建機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="486e1-107">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="486e1-p102">在內容中尋找機密資訊時，您需要以所謂的規則\*\* 來說明資訊。資料外洩防護 (DLP) 包含您可以立即使用之最常用機密資訊類型的規則。若要使用這些規則，您必須將其包含在原則中。您也許想要調整這些內建規則以符合貴組織的特定需求，您可以藉由建立自訂機密資訊類型來完成。本主題說明如何自訂其中包含現有規則集合的 XML 檔案，以偵測更大範圍的潛在信用卡資訊。</span><span class="sxs-lookup"><span data-stu-id="486e1-p102">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="486e1-p103">您可以採用此範例並且將其套用至其他內建機密資訊類型。如需預設機密資訊類型清單及 XML 定義，請參閱[機密資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="486e1-p103">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="486e1-115">匯出目前規則的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="486e1-115">Export the XML file of the current rules</span></span>

<span data-ttu-id="486e1-116">若要匯出 XML，您必須[透過遠端 PowerShell 連線到安全性與合規性中心。](https://go.microsoft.com/fwlink/?linkid=799771)。</span><span class="sxs-lookup"><span data-stu-id="486e1-116">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://go.microsoft.com/fwlink/?linkid=799771).</span></span>
  
1. <span data-ttu-id="486e1-p104">在 PowerShell 中，輸入下列項目以在畫面上顯示貴組織的規則。如果您尚未建立自己的規則，則只會看到標示為「Microsoft 規則套件」的預設、內建規則。</span><span class="sxs-lookup"><span data-stu-id="486e1-p104">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>
    
     `Get-DlpSensitiveInformationTypeRulePackage`
    
2. <span data-ttu-id="486e1-p105">藉由輸入下列項目，在變數中儲存貴組織的規則。儲存在變數中可讓項目更方便用於遠端 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="486e1-p105">Store your organization's rules in a in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>
    
     `$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage`
    
3. <span data-ttu-id="486e1-p106">藉由輸入下列項目來製作格式化的 XML 檔案及其所有資料。(`Set-content` 是會將 XML 寫入檔案之 Cmdlet 的一部分。)</span><span class="sxs-lookup"><span data-stu-id="486e1-p106">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
     `Set-Content -path "C:\custompath\exportedRules.xml" -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection`
    
    > [!IMPORTANT]
    > <span data-ttu-id="486e1-p107">請確定您使用規則套件儲存所在的確切檔案路徑。`C:\custompath\` 是預留位置。</span><span class="sxs-lookup"><span data-stu-id="486e1-p107">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="486e1-125">尋找您要在 XML 中修改的規則</span><span class="sxs-lookup"><span data-stu-id="486e1-125">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="486e1-p108">上述 Cmdlet 會匯出整個「規則集合」\*\*，該集合包含我們提供的預設規則。接下來您必須特別尋找您想要修改的「信用卡號碼」規則。</span><span class="sxs-lookup"><span data-stu-id="486e1-p108">The cmdlets above exported the entire  *rule collection*  , which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="486e1-128">使用文字編輯器開啟您在上一節中匯出的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="486e1-128">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="486e1-p109">向下捲動到 `<Rules>` 標記，該標記是包含 DLP 規則的區段開頭。(因為此 XML 檔案包含整個規則集合的資訊，它在頂端包含其他資訊，您必須捲動過去以前往規則。)</span><span class="sxs-lookup"><span data-stu-id="486e1-p109">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. (Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.)</span></span> 
    
3. <span data-ttu-id="486e1-p110">尋找 Func_credit_card\*\* 以尋找「信用卡號碼」規則定義。(在 XML 中，規則名稱不能包含空格，因此空格通常會以底線取代，且規則名稱有時候會是縮寫。範例是美國社會安全號碼規則，它縮寫為 "SSN"。「信用卡號碼」規則 XML 看起來應該像是下列程式碼範例。</span><span class="sxs-lookup"><span data-stu-id="486e1-p110">Look for  *Func_credit_card*  to find the Credit Card Number rule definition. (In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.</span></span> 
    
  ```
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

<span data-ttu-id="486e1-p111">既然您已在 XML 中找到「信用卡號碼」規則定義，可以自訂規則的 XML 以符合您的需求。(如需複習 XML 定義，請參閱本主題頂端的[術語詞彙](#term-glossary)。)</span><span class="sxs-lookup"><span data-stu-id="486e1-p111">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. (For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.)</span></span> 
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="486e1-137">修改 XML 及建立新的機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="486e1-137">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="486e1-p112">首先，您必須建立新的機密資訊類型，因為您無法直接修改預設規則。您可以對自訂機密資訊類型執行各種不同動作，這些動作在[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)中概述。針對此範例，我們保持簡單，只移除確切辨識項並且將關鍵字新增至「信用卡號碼」規則。</span><span class="sxs-lookup"><span data-stu-id="486e1-p112">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="486e1-p113">所有 XML 規則定義都是根據下列一般範本所建置。您需要複製及貼上範本中的「信用卡號碼」定義 XML、修改某些值 (請注意下列範例中的 ". . ." 預留位置)，然後將修改後的 XML 上傳為可在原則中使用的新規則。</span><span class="sxs-lookup"><span data-stu-id="486e1-p113">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="486e1-p114">現在，您有一些項目看起來與下列 XML 類似。因為規則套件和規則是根據其唯一的 GUID 進行識別，所以您必須產生兩個 GUID：一個適用於規則套件、一個用來取代「信用卡號碼」規則的 GUID。(下列程式碼範例中實體識別碼的 GUID，適用於我們的內建規則定義，您需要以新的加以取代。) 有許多方法可以產生 GUID，但是您可以藉由在 PowerShell 中輸入 **[guid]::NewGuid()**，輕鬆地完成。</span><span class="sxs-lookup"><span data-stu-id="486e1-p114">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. (The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.) There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="486e1-149">從機密資訊類型移除確切辨識項需求</span><span class="sxs-lookup"><span data-stu-id="486e1-149">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="486e1-p115">現在，您有新的機密資訊類型可以上傳到安全性與合規性中心，下一步是讓規則更精確。修改規則，讓它只會尋找通過總和檢查碼的 16 位數數字，但是不需要額外 (確切) 辨識項 (例如關鍵字)。若要這麼做，您需要移除會尋找確切辨識項的 XML 部分。確切辨識項在減少誤判方面很有幫助，因為信用卡號碼附近通常會有特定關鍵字或到期日。如果您移除辨識項，也應該藉由降低 `confidenceLevel` (在此範例中是 85) 來調整對於找到信用卡號碼的信心。</span><span class="sxs-lookup"><span data-stu-id="486e1-p115">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific. Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence (for example keywords). To do this, you need to remove the part of the XML that looks for corroborative evidence. Corroborative evidence is very helpful in reducing false positives because usually there are certain keywords or an expiration date near the credit card number. If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="486e1-155">尋找貴組織的特定關鍵字</span><span class="sxs-lookup"><span data-stu-id="486e1-155">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="486e1-p116">您可能想要要求確切辨識項，但是想要不同或額外的關鍵字，而且或許想要變更尋找該辨識項的位置。您可以調整 `patternsProximity` 以將確切辨識項的視窗展開或縮小為大約 16 位數數字。若要新增您自己的關鍵字，您必須定義關鍵字清單並且在規則內參考。下列 XML 會新增關鍵字 "company card" 和 "Contoso card"，這樣在 150 個字元內包含這些片語的任何訊息，都會識別為信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="486e1-p116">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span> 
  
```
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="486e1-160">上傳您的規則</span><span class="sxs-lookup"><span data-stu-id="486e1-160">Upload your rule</span></span>

<span data-ttu-id="486e1-161">若要上傳您的規則，您必須執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="486e1-161">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="486e1-p117">以 Unicode 編碼方式將它儲存為 .xml 檔案。這非常重要，因為如果檔案是以其他編碼方式儲存，則規則不會運作。</span><span class="sxs-lookup"><span data-stu-id="486e1-p117">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. <span data-ttu-id="486e1-164">[透過遠端 PowerShell 連線到安全性與合規性中心。](https://go.microsoft.com/fwlink/?linkid=799771)(機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="486e1-164">[Connect to the Security and Compliance Center via Remote PowerShell.](https://go.microsoft.com/fwlink/?linkid=799771)</span></span>
    
3. <span data-ttu-id="486e1-165">在 PowerShell 中，輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="486e1-165">In the PowerShell command prompt, type the following:</span></span>
    
     <span data-ttu-id="486e1-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`.</span><span class="sxs-lookup"><span data-stu-id="486e1-166"></span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="486e1-p118">請確定您使用規則套件儲存所在的確切檔案路徑。`C:\custompath\` 是預留位置。</span><span class="sxs-lookup"><span data-stu-id="486e1-p118">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="486e1-169">若要確認，輸入 Y，並按下 **ENTER** 鍵。</span><span class="sxs-lookup"><span data-stu-id="486e1-169">To confirm, type Y, and then press **Enter**.</span></span>
    
5. <span data-ttu-id="486e1-170">藉由輸入 `Get-DlpSensitiveInformationType` 來確認您的新規則是否已上傳，這個命令現在會顯示您的規則名稱。</span><span class="sxs-lookup"><span data-stu-id="486e1-170">Verify that your new rule was uploaded by typing  `Get-DlpSensitiveInformationType`, which now displays the name of your rule.</span></span>
    
<span data-ttu-id="486e1-p119">若要開始使用新規則來偵測機密資訊，您需要將規則新增至 DLP 原則。若要深入了解如何將規則新增至原則，請參閱[從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)。</span><span class="sxs-lookup"><span data-stu-id="486e1-p119">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="486e1-173">術語詞彙</span><span class="sxs-lookup"><span data-stu-id="486e1-173">Term glossary</span></span>

<span data-ttu-id="486e1-174">以下是您在此程序期間遇到之術語的定義。</span><span class="sxs-lookup"><span data-stu-id="486e1-174">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="486e1-175">**詞彙**</span><span class="sxs-lookup"><span data-stu-id="486e1-175">**Term**</span></span>|<span data-ttu-id="486e1-176">**定義**</span><span class="sxs-lookup"><span data-stu-id="486e1-176">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="486e1-177">實體</span><span class="sxs-lookup"><span data-stu-id="486e1-177">Entity</span></span>  <br/> |<span data-ttu-id="486e1-p120">實體是我們所謂的機密資訊類型，例如信用卡號碼。每個實體都有唯一的 GUID 作為其識別碼。如果您複製 GUID 並且在 XML 中搜尋，您會找到 XML 規則定義及該 XML 規則的所有當地語系化轉譯。您也可以藉由尋找轉譯的 GUID 並且搜尋該 GUID，來尋找此定義。</span><span class="sxs-lookup"><span data-stu-id="486e1-p120">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>  <br/> |
|<span data-ttu-id="486e1-182">函式</span><span class="sxs-lookup"><span data-stu-id="486e1-182">Functions</span></span>  <br/> |<span data-ttu-id="486e1-p121">XML 檔案參考 `Func_credit_card`，這是已編譯程式碼中的函式。函式是用來執行複雜 regexes 並確認總和檢查碼符合我們的內建規則。因為這是在程式碼中發生，所以部分變數不會在 XML 檔案中顯示。</span><span class="sxs-lookup"><span data-stu-id="486e1-p121">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.  </span></span><br/> |
|<span data-ttu-id="486e1-185">IdMatch</span><span class="sxs-lookup"><span data-stu-id="486e1-185">IdMatch idRef=Regex_email_address</span></span>  <br/> |<span data-ttu-id="486e1-p122">這是模式嘗試比對的識別碼，例如信用卡號碼。您可以在[實體規則](https://support.office.com/article/c4ab8707-0839-4855-9390-3dbcb43475a7.aspx#dlp-entity)中深入了解這個項目和 `Match` 標記。</span><span class="sxs-lookup"><span data-stu-id="486e1-p122">This is the identifier that the pattern is to trying to match—for example, a credit card number. You can read more about this and about the  `Match` tags in [Entity rules](https://support.office.com/article/c4ab8707-0839-4855-9390-3dbcb43475a7.aspx#dlp-entity).  </span></span><br/> |
|<span data-ttu-id="486e1-188">關鍵字清單</span><span class="sxs-lookup"><span data-stu-id="486e1-188">Keyword lists</span></span>  <br/> |<span data-ttu-id="486e1-p123">XML 檔案也會參考 `keyword_cc_verification` 和 `keyword_cc_name`，這是關鍵字清單，我們會從中尋找與實體 `patternsProximity` 的相符項目。目前不會在 XML 中顯示。</span><span class="sxs-lookup"><span data-stu-id="486e1-p123">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.  </span></span><br/> |
|<span data-ttu-id="486e1-191">模式</span><span class="sxs-lookup"><span data-stu-id="486e1-191">Pattern</span></span>  <br/> |<span data-ttu-id="486e1-p124">模式包含機密類型尋找的清單。包含關鍵字、regexes 及內部函式 (執行像是驗證總和檢查碼的工作)。機密資訊類型可以有多個具有唯一信賴度的模式。建立機密資訊類型時，在找到確切辨識項時傳回高信賴度、找到一些確切辨識項或完全找不到時傳回較低信賴度，這非常有用。</span><span class="sxs-lookup"><span data-stu-id="486e1-p124">The pattern contains the list of what the sensitive type is looking for. This includes keywords, regexes, and internal functions (that perform tasks like verifying checksums). Sensitive information types can have multiple patterns with unique confidences. This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>  <br/> |
|<span data-ttu-id="486e1-196">模式 confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="486e1-196">Pattern confidenceLevel</span></span>  <br/> |<span data-ttu-id="486e1-p125">這是 DLP 引擎找到相符項目的信賴等級。此信賴等級與符合模式需求時，模式的相符項目相關聯。這是當使用 Exchange 傳輸規則 (ETR) 時，您應該考慮的信賴度量值。</span><span class="sxs-lookup"><span data-stu-id="486e1-p125">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange transport rules (ETRs).</span></span>  <br/> |
|<span data-ttu-id="486e1-200">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="486e1-200">patternsProximity</span></span>  <br/> |<span data-ttu-id="486e1-201">當我們尋找看起來像是信用卡號碼模式的項目時，`patternsProximity` 是與我們尋找確切辨識項的位置接近的數字。</span><span class="sxs-lookup"><span data-stu-id="486e1-201">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>  <br/> |
|<span data-ttu-id="486e1-202">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="486e1-202">recommendedConfidence</span></span>  <br/> |<span data-ttu-id="486e1-p126">這是我們針對此規則建議的信賴等級。建議的信賴度會套用至實體和親和性。對於實體，永遠不會針對模式的 `confidenceLevel` 評估此數字。這只是一個建議，協助您在想要套用時選擇一個信賴等級。對於親和性，模式的 `confidenceLevel` 必須高於要叫用之 ETR 動作的 `recommendedConfidence` 數字。`recommendedConfidence` 是在會叫用動作之 ETR 中使用的預設信賴等級。如果您想要的話，可以改為根據模式的信賴等級，手動變更要叫用的 ETR。</span><span class="sxs-lookup"><span data-stu-id="486e1-p126">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for an ETR action to be invoked. The  `recommendedConfidence` is the default confidence level used in ETRs that invokes an action. If you want, you can manually change the ETR to be invoked based off the pattern's confidence level, instead.  </span></span><br/> |
   
## <a name="for-more-information"></a><span data-ttu-id="486e1-210">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="486e1-210">For more information</span></span>

- [<span data-ttu-id="486e1-211">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="486e1-211">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="486e1-212">建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="486e1-212">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="486e1-213">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="486e1-213">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    

