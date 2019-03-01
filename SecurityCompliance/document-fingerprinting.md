---
title: 文件指紋
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: 您的組織中資訊工作者處理許多不同的日常的敏感資訊。文件指紋，有助於您識別用於整個組織的標準表單來保護此資訊。本主題說明的概念文件指紋 」 和 「 如何使用 PowerShell 來建立。
ms.openlocfilehash: 20b9f59902c52d347e7c439cb6f380ee9fd4a30e
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341284"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="86a19-105">文件指紋</span><span class="sxs-lookup"><span data-stu-id="86a19-105">Document Fingerprinting</span></span>

<span data-ttu-id="86a19-p102">您的組織中資訊工作者處理許多不同的日常的敏感資訊。安全性&amp;合規性中心]、 [文件指紋可以方便您藉由識別用於整個組織的標準表單保護此資訊。本主題說明的概念文件指紋 」 和 「 如何使用 PowerShell 來建立。</span><span class="sxs-lookup"><span data-stu-id="86a19-p102">Information workers in your organization handle many kinds of sensitive information during a typical day. In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization. This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="86a19-109">文件指紋的基本案例</span><span class="sxs-lookup"><span data-stu-id="86a19-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="86a19-p103">文件指紋是一種標準表單轉換為敏感資訊類型，您可以使用 DLP 原則規則中的資料外洩防護 (DLP) 功能。例如，您可以建立空白的專利範本為基礎的文件指紋，，然後建立 DLP 原則會偵測和具有敏感內容的所有外寄專利範本填滿的區塊。或者，您可以設定[原則提示](use-notifications-and-policy-tips.md)通知寄件者，他們可能傳送機密資訊，以及寄件者應確認收件者是接收專利限定。此程序的運作方式與您組織中使用任何文字型表單。您可以上傳的表單的其他範例包括：</span><span class="sxs-lookup"><span data-stu-id="86a19-p103">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies. For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in. Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents. This process works with any text-based forms used in your organization. Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="86a19-115">政府表單</span><span class="sxs-lookup"><span data-stu-id="86a19-115">Government forms</span></span>
    
- <span data-ttu-id="86a19-116">1996 年健康保險流通與責任法案 (HIPAA) 符合性表單</span><span class="sxs-lookup"><span data-stu-id="86a19-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="86a19-117">人力資源部門的員工資訊表單</span><span class="sxs-lookup"><span data-stu-id="86a19-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="86a19-118">特別為您的組織建立的自訂表單</span><span class="sxs-lookup"><span data-stu-id="86a19-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="86a19-p104">理想狀況下，貴組織已有已建立的商業實務準則的使用特定表單來傳輸敏感資訊。上載空白表單以轉換為文件指紋，設定相對應的原則之後，DLP 會偵測符合該指紋的輸出郵件中的任何文件。</span><span class="sxs-lookup"><span data-stu-id="86a19-p104">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information. After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="86a19-121">文件指紋的運作方式</span><span class="sxs-lookup"><span data-stu-id="86a19-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="86a19-p105">您可能已猜文件並沒有實際的指紋，但名稱有助於闡述功能。人員的指紋具有獨特的模式的相同方式，在文件會有獨特的文字模式。當您將檔案上傳時，DLP 識別文件中的唯一 word 模式、 會建立文件指紋，根據該模式，並會使用該文件指紋來偵測輸出包含相同的模式的文件。上載表單或範本能夠產生最有效的文件指紋類型。每一位使用者填寫表單時使用同一組原始文字，然後將其本身的文字新增至文件。只要輸出文件未受密碼保護，且包含原始表單中的所有文字，DLP 可決定文件是否符合文件指紋。</span><span class="sxs-lookup"><span data-stu-id="86a19-p105">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature. In the same way that a person's fingerprints have unique patterns, documents have unique word patterns. When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern. That's why uploading a form or template creates the most effective type of document fingerprint. Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document. As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="86a19-128">下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。</span><span class="sxs-lookup"><span data-stu-id="86a19-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="86a19-129">**比對專利範本之文件指紋的專利文件範例**</span><span class="sxs-lookup"><span data-stu-id="86a19-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
<span data-ttu-id="86a19-p106">專利範本包含空白欄位 「 專利標題 」、 「 發明者，」 和 「 描述 」 的每個欄位的描述 — 是 word 模式。當您上傳原始專利範本時，就在一種支援的檔案類型，以純文字。此 word 模式中插入文件指紋，這是小型的 Unicode XML 檔案包含唯一的雜湊值，表示原始文字和指紋的 DLP 轉換會儲存在 Active Directory 中的資料分類為。（為安全起見，原始文件本身並不儲存於服務; 只有雜湊值會儲存，和原始文件無法重建雜湊值。）專利指紋就會變成您可以將關聯的 DLP 原則的敏感資訊類型。指紋關聯的 DLP 原則之後，DLP 偵測任何包含比對專利指紋的文件的外寄電子郵件，並根據貴組織的原則來處理它們。</span><span class="sxs-lookup"><span data-stu-id="86a19-p106">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern. When you upload the original patent template, it's in one of the supported file types and in plain text. DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory. (As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy. After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="86a19-p107">例如，您可能想要設定 [禁止傳送含有專利的外寄郵件的規則員工的 DLP 原則。DLP 會使用專利指紋來偵測專利及封鎖這些電子郵件。或者，您可能想要讓您能夠將專利傳送至其他組織，因為它有業務上的需要這樣的法務部門。您可以允許特定部門傳送機密資訊在 DLP 原則中，建立這些部門的例外狀況，或您可以允許他們覆寫原則提示與業務上理由。</span><span class="sxs-lookup"><span data-stu-id="86a19-p107">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents. DLP will use the patent fingerprint to detect patents and block those emails. Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so. You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="86a19-140">支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="86a19-140">Supported file types</span></span>

<span data-ttu-id="86a19-p108">文件指紋支援所支援的郵件流程規則 （也稱為傳輸規則） 的相同檔案類型。如需支援的檔案類型的清單，請參閱 <<c0>的郵件流程規則內容檢查支援的檔案類型。關於檔案類型的一個快速附註： 郵件流程規則和文件指紋支援.dotx 檔案類型，因為這是在 Word 中的範本檔案可以是令人混淆。當您看到 「 範本 」，這和其他文件指紋的主題中的字時，它是指您已建立為標準表單，不該範本的檔案類型的文件。</span><span class="sxs-lookup"><span data-stu-id="86a19-p108">Document Fingerprinting supports the same file types that are supported in mail flow rules (also known as transport rules). For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). One quick note about file types: neither mail flow rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word. When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="86a19-145">文件指紋的限制</span><span class="sxs-lookup"><span data-stu-id="86a19-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="86a19-146">在下列情況下，文件指紋將不會偵測敏感資訊：</span><span class="sxs-lookup"><span data-stu-id="86a19-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="86a19-147">檔案受密碼保護</span><span class="sxs-lookup"><span data-stu-id="86a19-147">Password protected files</span></span>
    
- <span data-ttu-id="86a19-148">檔案只包含影像</span><span class="sxs-lookup"><span data-stu-id="86a19-148">Files that contain only images</span></span>
    
- <span data-ttu-id="86a19-149">文件未包含原始表單中所有用來建立文件指紋的文字</span><span class="sxs-lookup"><span data-stu-id="86a19-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="86a19-150">使用 PowerShell 來建立根據文件指紋的分類規則套件</span><span class="sxs-lookup"><span data-stu-id="86a19-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="86a19-p109">請注意，您可以目前文件指紋只能使用 PowerShell 建立安全性&amp;合規性中心。若要連線，請參閱[Connect to Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="86a19-p109">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center. To connect, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="86a19-p110">DLP 會使用分類規則套件來偵測敏感內容。若要建立分類規則套件根據文件指紋，請使用**新增 DlpFingerprint**和**新增-dlpsensitiveinformationtype 來**指令程式。**新增 DlpFingerprint**的結果不會被儲存的資料分類規則外部，因為您一律**新增 DlpFingerprint**和**新增-dlpsensitiveinformationtype 來**或執行**組-dlpsensitiveinformationtype 來**在同一個PowerShell 工作階段。下列範例會建立新的文件指紋，根據 C:\My Documents\Contoso Employee Template.docx 檔案。讓您可以先將它**新增-dlpsensitiveinformationtype 來**指令程式搭配使用，相同 PowerShell 工作階段中，您可以儲存為變數的新的指紋。</span><span class="sxs-lookup"><span data-stu-id="86a19-p110">DLP uses classification rule packages to detect sensitive content. To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets. Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session. The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx. You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="86a19-158">現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="86a19-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="86a19-159">您現在可以使用**Get-dlpsensitiveinformationtype 來**指令程式來尋找所有 DLP 資料分類規則套件，且在這個範例中，"Contoso Customer Confidential"資料分類規則套件清單的一部分。</span><span class="sxs-lookup"><span data-stu-id="86a19-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="86a19-p111">最後，將"Contoso Customer Confidential"資料分類規則套件新增至 DLP 原則中的安全性&amp;合規性中心。本範例會新增至現有的 DLP 原則名為 「 ConfidentialPolicy 」 的規則。</span><span class="sxs-lookup"><span data-stu-id="86a19-p111">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center. This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="86a19-p112">您也可以使用 Exchange Online 中的郵件流程規則中的資料分類規則套件，如下列範例所示。若要執行此命令，您必須連線[至 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。也請注意，所花的時間來同步處理從安全性的規則套件的&amp;合規性中心，以在 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="86a19-p112">You can also use the data classification rule package in mail flow rules in Exchange Online, as shown in the following example. To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange admin center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="86a19-165">DLP 現已可偵測符合 Contoso Customer Form.docx 文件指紋的文件。</span><span class="sxs-lookup"><span data-stu-id="86a19-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="86a19-166">語法及參數資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="86a19-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="86a19-167">新 DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="86a19-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="86a19-168">新-dlpsensitiveinformationtype 來</span><span class="sxs-lookup"><span data-stu-id="86a19-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="86a19-169">移除-dlpsensitiveinformationtype 來</span><span class="sxs-lookup"><span data-stu-id="86a19-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="86a19-170">Set-dlpsensitiveinformationtype 來</span><span class="sxs-lookup"><span data-stu-id="86a19-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="86a19-171">Get-dlpsensitiveinformationtype 來</span><span class="sxs-lookup"><span data-stu-id="86a19-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
