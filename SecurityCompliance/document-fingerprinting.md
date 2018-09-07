---
title: 文件指紋
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: 在組織中的資訊工作者處理許多種期間一般 1 天的機密資訊。文件指紋讓您用來識別整個組織中使用的標準表單來保護這項資訊更容易。本主題說明的概念文件指紋，以及如何建立 web 應用程式使用 PowerShell。
ms.openlocfilehash: d73b769e7a014f2642a0fcd66cc6a500c68c46c3
ms.sourcegitcommit: 4be502d1fc6cbaef4c72d599758d51efe3a173c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2018
ms.locfileid: "23867489"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="0d165-105">文件指紋</span><span class="sxs-lookup"><span data-stu-id="0d165-105">Document Fingerprinting</span></span>

<span data-ttu-id="0d165-p102">在組織中的資訊工作者處理許多種期間一般 1 天的機密資訊。安全性&amp;規範中心、 文件指紋便於供您用來識別整個組織中使用的標準表單來保護此資訊。本主題說明的概念文件指紋，以及如何建立 web 應用程式使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0d165-p102">Information workers in your organization handle many kinds of sensitive information during a typical day. In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization. This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="0d165-109">文件指紋的基本案例</span><span class="sxs-lookup"><span data-stu-id="0d165-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="0d165-p103">文件指紋是會將標準表單轉換成敏感資訊類型，可讓您用 DLP 原則規則中的資料遺失防護 (DLP) 功能。例如，您可以建立空白的專利範本為基礎的文件指紋，然後建立 [偵測的 DLP 原則和封鎖敏感內容的所有傳出專利範本填入。（選用） 您可以設定[原則提示](use-notifications-and-policy-tips.md)通知寄件者可能會將傳送機密資訊和寄件者應確認收件者是以接收所含之專利權合格。此程序適用於您組織中使用任何文字型表單。您可以上傳的表單之其他範例包括：</span><span class="sxs-lookup"><span data-stu-id="0d165-p103">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies. For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in. Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents. This process works with any text-based forms used in your organization. Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="0d165-115">政府表單</span><span class="sxs-lookup"><span data-stu-id="0d165-115">Government forms</span></span>
    
- <span data-ttu-id="0d165-116">1996 年健康保險流通與責任法案 (HIPAA) 符合性表單</span><span class="sxs-lookup"><span data-stu-id="0d165-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="0d165-117">人力資源部門的員工資訊表單</span><span class="sxs-lookup"><span data-stu-id="0d165-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="0d165-118">特別為您的組織建立的自訂表單</span><span class="sxs-lookup"><span data-stu-id="0d165-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="0d165-p104">理想狀況下，您的組織已有建立的商務作法並使用特定表單傳輸的機密資訊。上傳要轉換成文件指紋及相對應的原則設定的空白表單之後，DLP 會偵測任何文件中比對該指紋的外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="0d165-p104">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information. After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="0d165-121">文件指紋的運作方式</span><span class="sxs-lookup"><span data-stu-id="0d165-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="0d165-p105">您可能已經已猜測文件沒有實際指紋，但名稱可協助說明此功能。人員指紋具有唯一模式相同的方式、 文件有唯一的字模式。當您上傳的檔案時，DLP 識別文件中的唯一 word 圖樣、 建立文件指紋根據該模式，以及使用該文件指紋偵測包含相同的輸出文件。這就是為什麼上載表單或範本建立文件指紋的最有效類型。填寫表單時的所有人使用原始組相同的文字，然後將其自己的文字新增至文件。只要撥出的文件不受密碼保護及包含原始表單中的所有文字，DLP 可以判斷文件是否符合的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="0d165-p105">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature. In the same way that a person's fingerprints have unique patterns, documents have unique word patterns. When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern. That's why uploading a form or template creates the most effective type of document fingerprint. Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document. As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="0d165-128">下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。</span><span class="sxs-lookup"><span data-stu-id="0d165-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="0d165-129">**比對專利範本之文件指紋的專利文件範例**</span><span class="sxs-lookup"><span data-stu-id="0d165-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
<span data-ttu-id="0d165-p106">專利範本包含空白欄位"專利 title，""發明者，"和"Description"和每個欄位的描述 — 這是 word 圖樣。時原始的專利範本上傳，是一種支援的檔案類型及純文字。DLP 轉換成文件指紋，這是小型的 Unicode XML 這個字模式檔案包含代表原始文字和指紋的唯一雜湊值儲存在 Active Directory 中的資料分類為。（做為安全性量、 原始文件本身不儲存在服務 ； 儲存雜湊值，和原始文件無法重建的雜湊值從。）專利指紋會變成可與 DLP 原則建立關聯的敏感資訊類型。指紋關聯的 DLP 原則後，DLP 偵測到任何包含比對專利指紋的文件的外寄電子郵件，並根據貴組織的原則來處理它們。</span><span class="sxs-lookup"><span data-stu-id="0d165-p106">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern. When you upload the original patent template, it's in one of the supported file types and in plain text. DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory. (As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy. After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="0d165-p107">例如，您可能要禁止傳送含有所含之專利權的外寄郵件的規則員工的 DLP 原則設定。DLP 將會使用專利指紋偵測所含之專利權並封鎖這些電子郵件。或者，您可能會想要讓您能夠將傳送至其他組織所含之專利權，因為它需要這麼商務的法務部門。您可以讓傳送機密資訊在 DLP 原則中，建立這些部門的例外狀況的特定部門或您可以讓它們可以覆寫原則提示與業務上理由。</span><span class="sxs-lookup"><span data-stu-id="0d165-p107">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents. DLP will use the patent fingerprint to detect patents and block those emails. Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so. You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="0d165-140">支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="0d165-140">Supported file types</span></span>

<span data-ttu-id="0d165-p108">文件指紋支援相同的傳輸規則中所支援的檔案類型。如需支援的檔案類型的清單，請參閱[的郵件流程規則內容檢查支援的檔案類型](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。關於檔案類型的一個快速筆記： 傳輸規則或文件指紋支援.dotx 檔案類型，因為這是在 Word 中的範本檔案可以是混淆。當您看到單字"template"中此憑證與其他文件指紋的主題時，它是指已建立成為標準表單不範本檔案類型的文件。</span><span class="sxs-lookup"><span data-stu-id="0d165-p108">Document Fingerprinting supports the same file types that are supported in transport rules. For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). One quick note about file types: neither transport rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word. When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="0d165-145">文件指紋的限制</span><span class="sxs-lookup"><span data-stu-id="0d165-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="0d165-146">文件指紋將不會在下列情況偵測敏感資訊：</span><span class="sxs-lookup"><span data-stu-id="0d165-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="0d165-147">檔案受密碼保護</span><span class="sxs-lookup"><span data-stu-id="0d165-147">Password protected files</span></span>
    
- <span data-ttu-id="0d165-148">檔案只包含影像</span><span class="sxs-lookup"><span data-stu-id="0d165-148">Files that contain only images</span></span>
    
- <span data-ttu-id="0d165-149">文件未包含原始表單中所有用來建立文件指紋的文字</span><span class="sxs-lookup"><span data-stu-id="0d165-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="0d165-150">使用 PowerShell 建立分類規則套件為基礎的文件指紋</span><span class="sxs-lookup"><span data-stu-id="0d165-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="0d165-p109">請注意您可以僅限透過 PowerShell 安全性目前建立文件指紋&amp;規範中心。若要連線，請參閱[Connect to Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0d165-p109">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center. To connect, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="0d165-p110">DLP 使用分類規則套件來偵測敏感內容。若要建立文件指紋為基礎的分類規則套件，請使用**新增 DlpFingerprint**和**新增 DlpSensitiveInformationType** cmdlet。**新增 DlpFingerprint**的結果不會被儲存外部資料分類規則，因為您一律**新增 DlpFingerprint**和**新增 DlpSensitiveInformationType**或執行**組 DlpSensitiveInformationType**在同一個PowerShell 工作階段。下列範例會建立新的文件指紋根據檔案 C:\My Documents\Contoso Employee Template.docx。儲存新的指紋為變數，以便使用與**新增 DlpSensitiveInformationType**指令程式在相同的 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="0d165-p110">DLP uses classification rule packages to detect sensitive content. To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets. Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session. The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx. You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="0d165-158">現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="0d165-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="0d165-159">您現在可以使用**Get DlpSensitiveInformationType**指令程式來尋找所有的 DLP 資料分類規則套件，且在本例中為"Contoso Customer Confidential"資料分類規則套件清單的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d165-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="0d165-p111">最後，將"Contoso Customer Confidential"的資料分類規則套件新增至 DLP 原則安全性&amp;規範中心。本範例會新增至現有的 DLP 原則名為"ConfidentialPolicy"的規則。</span><span class="sxs-lookup"><span data-stu-id="0d165-p111">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center. This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="0d165-p112">您也可以使用資料分類規則套件中的 Exchange Online 傳輸規則在下列範例所示。若要執行此命令，您需要連線[至 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。也請注意所花的時間來同步處理的安全性規則套件&amp;規範中心 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="0d165-p112">You can also use the data classification rule package in transport rules in Exchange Online, as shown in the following example. To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange Admin Center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="0d165-165">DLP 現已可偵測符合 Contoso Customer Form.docx 文件指紋的文件。</span><span class="sxs-lookup"><span data-stu-id="0d165-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="0d165-166">下列的語法及參數資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="0d165-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="0d165-167">新 DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="0d165-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="0d165-168">新 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="0d165-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="0d165-169">移除 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="0d165-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="0d165-170">設定 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="0d165-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="0d165-171">取得 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="0d165-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
