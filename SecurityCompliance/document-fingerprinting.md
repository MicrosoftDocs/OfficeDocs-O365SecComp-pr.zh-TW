---
title: 文件指紋
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: 組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。 「文件指紋」可識別您的組織中所使用的標準表單，以協助您保護此類資訊。 本主題說明的概念文件指紋 」 和 「 如何使用 PowerShell 來建立。
ms.openlocfilehash: 2b8e4fd6b286f2c1a5c67863957f2b04fbef31b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256894"
---
# <a name="document-fingerprinting"></a>文件指紋

組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。 安全性&amp;合規性中心]、 [文件指紋可以方便您藉由識別用於整個組織的標準表單保護此資訊。 本主題說明的概念文件指紋 」 和 「 如何使用 PowerShell 來建立。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>文件指紋的基本案例

文件指紋是一種標準表單轉換為敏感資訊類型，您可以使用 DLP 原則規則中的資料外洩防護 (DLP) 功能。 例如，您可以根據空白專利範本建立文件指紋，然後再建立 DLP 原則，以偵測及封鎖所有填入敏感內容的傳出專利範本。 或者，您可以設定[原則提示](use-notifications-and-policy-tips.md)通知寄件者，他們可能傳送機密資訊，以及寄件者應確認收件者是接收專利限定。 此程序適用於您的組織中所使用的任何文字型表單。 您可以上傳的表單還包括： 
  
- 政府表單
    
- 1996 年健康保險流通與責任法案 (HIPAA) 符合性表單
    
- 人力資源部門的員工資訊表單
    
- 特別為您的組織建立的自訂表單
    
在理想情況下，您的組織應已建立使用特定表單來傳輸敏感資訊的商業實務準則。 上載空白表單以轉換為文件指紋，設定相對應的原則之後，DLP 會偵測符合該指紋的輸出郵件中的任何文件。
  
## <a name="how-document-fingerprinting-works"></a>文件指紋的運作方式

您可能已猜到文件並沒有實際的指紋，但此名稱仍有助於闡述功能。 如同人類的指紋具有獨特的型態，文件也會有獨特的文字模式。 當您將檔案上傳時，DLP 識別文件中的唯一 word 模式、 會建立文件指紋，根據該模式，並會使用該文件指紋來偵測輸出包含相同的模式的文件。 正因如此，上載表單或範本能夠產生最有效的文件指紋類型。 每個填寫表單的人都會使用同一組原始文字，然後再將其本身的文字新增至文件中。 只要輸出文件未受密碼保護，且包含原始表單中的所有文字，DLP 可決定文件是否符合文件指紋。
  
下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。
  
**比對專利範本之文件指紋的專利文件範例**

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
專利範本包含空白欄位 「 專利標題 」、 「 發明者，」 和 「 描述 」 的每個欄位的描述 — 是 word 模式。 當您上傳原始專利範本時，就在一種支援的檔案類型，以純文字。 此 word 模式中插入文件指紋，這是小型的 Unicode XML 檔案包含唯一的雜湊值，表示原始文字和指紋的 DLP 轉換會儲存在 Active Directory 中的資料分類為。 （為安全起見，原始文件本身並不儲存於服務; 只有雜湊值會儲存，和原始文件無法重建雜湊值。）專利指紋就會變成您可以將關聯的 DLP 原則的敏感資訊類型。 指紋關聯的 DLP 原則之後，DLP 偵測任何包含比對專利指紋的文件的外寄電子郵件，並根據貴組織的原則來處理它們。 

例如，您可以設定 DLP 原則，以防止正職員工對外傳送包含專利的郵件。 DLP 會使用專利指紋來偵測專利及封鎖這些電子郵件。 或者，您可以允許法務部門將專利傳送至其他組織，因為這是業務上的需要。 您可以在 DLP 原則中建立特定部門的例外狀況，以允許這些部門傳送敏感資訊，或者，您可以允許他們以業務理由覆寫原則提示。
  
### <a name="supported-file-types"></a>支援的檔案類型

文件指紋支援所支援的郵件流程規則 （也稱為傳輸規則） 的相同檔案類型。 如需支援的檔案類型的清單，請參閱 <<c0>的郵件流程規則內容檢查支援的檔案類型。 關於檔案類型的一個快速附註： 郵件流程規則和文件指紋支援.dotx 檔案類型，因為這是在 Word 中的範本檔案可以是令人混淆。 您在本主題和其他文件指紋主題中所看見的「範本」一詞，都是指您建立為標準表單的文件，而不是範本檔案類型。
  
#### <a name="limitations-of-document-fingerprinting"></a>文件指紋的限制

在下列情況下，文件指紋將不會偵測敏感資訊：
  
- 檔案受密碼保護
    
- 檔案只包含影像
    
- 文件未包含原始表單中所有用來建立文件指紋的文字
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>使用 PowerShell 來建立根據文件指紋的分類規則套件

請注意，您可以目前文件指紋只能使用 PowerShell 建立安全性&amp;合規性中心。 若要連線，請參閱[連線到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

DLP 會使用分類規則套件來偵測敏感內容。 若要建立分類規則套件根據文件指紋，請使用**新增 DlpFingerprint**和**新增-dlpsensitiveinformationtype 來**指令程式。 **新增 DlpFingerprint**的結果不會被儲存的資料分類規則外部，因為您一律**新增 DlpFingerprint**和**新增-dlpsensitiveinformationtype 來**或執行**組-dlpsensitiveinformationtype 來**在同一個PowerShell 工作階段。 下列範例會根據 C:\My Documents\Contoso Employee Template.docx 檔案建立新的文件指紋。 讓您可以先將它**新增-dlpsensitiveinformationtype 來**指令程式搭配使用，相同 PowerShell 工作階段中，您可以儲存為變數的新的指紋。 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

您現在可以使用**Get-dlpsensitiveinformationtype 來**指令程式來尋找所有 DLP 資料分類規則套件，且在這個範例中，"Contoso Customer Confidential"資料分類規則套件清單的一部分。 
  
最後，將"Contoso Customer Confidential"資料分類規則套件新增至 DLP 原則中的安全性&amp;合規性中心。 本範例會新增至現有的 DLP 原則名為 「 ConfidentialPolicy 」 的規則。

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

您也可以使用 Exchange Online 中的郵件流程規則中的資料分類規則套件，如下列範例所示。 若要執行此命令，您必須連線[至 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 也請注意，所花的時間來同步處理從安全性的規則套件的&amp;合規性中心，以在 Exchange 系統管理中心。
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP 現已可偵測符合 Contoso Customer Form.docx 文件指紋的文件。
  
語法及參數資訊，請參閱：

- [新 DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [新-dlpsensitiveinformationtype 來](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [移除-dlpsensitiveinformationtype 來](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Set-dlpsensitiveinformationtype 來](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-dlpsensitiveinformationtype 來](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
