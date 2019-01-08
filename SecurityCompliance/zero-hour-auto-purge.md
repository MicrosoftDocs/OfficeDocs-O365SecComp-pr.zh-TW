---
title: 零時差自動清除 - 防範垃圾郵件和惡意程式碼
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零小時自動清除 (ZAP) 是電子郵件保護功能，可偵測到的郵件垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，並再轉譯無害惡意的內容。如何 ZAP 執行此動作而定的偵測到惡意內容類型。
ms.openlocfilehash: 1e90e69018b7640bb36011287abd5bcd77d43358
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749317"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零時差自動清除 - 防範垃圾郵件和惡意程式碼

## <a name="overview"></a>概觀

零小時自動清除 (ZAP) 是電子郵件保護功能，可偵測到的郵件 phish、 垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，並再轉譯無害惡意的內容。如何 ZAP 執行此動作而定的偵測到; 惡意內容類型郵件可以 zapped 因為郵件內容、 Url 或附件。
  
ZAP 皆可使用的預設值是包含任何包含 Exchange Online 信箱的 Office 365 訂閱的 Exchange Online Protection。

依預設，會開啟 ZAP 但必須符合下列條件：
  
- **垃圾郵件動作**設為**移至 [垃圾郵件] 資料夾的郵件**。 <br/>您也可以建立新的垃圾郵件篩選器原則只套用一組使用者如果您不想要 ZAP 所篩選的所有信箱。

- 使用者已保留其預設的垃圾郵件設定和不具有已關閉垃圾郵件保護。（如需在 Outlook 中的使用者選項的詳細資訊，請參閱[變更在垃圾郵件篩選保護層級](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)）。 
  
## <a name="how-does-zap-work"></a>ZAP 如何運作？

Office 365 更新反垃圾郵件引擎和惡意程式碼中的簽章即時每天。不過，您的使用者可能仍屬惡意郵件傳遞至其收件匣的各種包括如果內容 weaponized 之後會傳遞至使用者的原因。ZAP 解決此問題持續監視更新至 Office 365 垃圾郵件和惡意程式碼簽章。ZAP 可以尋找及移除已在使用者的收件匣中的先前已傳遞的郵件。 

- 識別為垃圾郵件的郵件，ZAP 會將未讀取的郵件移至使用者的垃圾郵件資料夾。 

- 識別為垃圾郵件的郵件，ZAP 會將郵件移至使用者的垃圾郵件資料夾，不論是否已讀取的電子郵件。

- 為新偵測到惡意程式碼、 ZAP 會移除電子郵件，不論是否已讀取的電子郵件附件。 
  
ZAP 動作是一致的信箱使用者;它們不會收到通知如果移動電子郵件訊息。
  
允許清單、[郵件流程規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)及使用者的規則或其他篩選器優先於 ZAP。
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>若要檢閱或設定垃圾郵件篩選器原則
  
1. 移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。

2. **威脅管理**] 下選擇 [**反垃圾郵件**]。

3. 檢閱的標準設定。 

4. 如果您想要自訂您的設定，選取 [**自訂**] 索引標籤，並開啟的**自訂設定**。編輯您的設定，如果您想選擇 **+ 建立原則**來新增新的原則。 
    
## <a name="to-see-if-zap-moved-your-message"></a>若要查看 ZAP 是否移動郵件

如果您想要查看 ZAP 如果移動郵件，您可以使用[威脅保護狀態報表](view-email-security-reports.md#threat-protection-status-report)（或[威脅 Explorer](use-explorer-in-security-and-compliance.md)）。
    
## <a name="to-disable-zap"></a>若要停用 ZAP
  
如果您想要停用您的 Office 365 租用戶的 ZAP 或一組使用者，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)、 EOP 指令程式的**ZapEnabled**參數。
    
在下列範例中，ZAP 已停用名為"Test"的內容篩選原則。
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>常見問題集

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>如果合法的訊息移至 [垃圾郵件] 資料夾發生什麼情況？
  
您應該遵循 false 測的標準報表程序。郵件會從收件匣移至垃圾郵件資料夾的唯一原因是因為此服務已決定郵件是垃圾郵件或惡意。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>如果使用 Office 365 隔離而不是垃圾郵件資料夾吗？
  
ZAP 不會將郵件移至隔離區從收件匣這一次。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>如果我有自訂郵件流程規則 （封鎖 / 允許規則） 吗？
  
由系統管理員 （郵件流程規則） 或封鎖及允許規則建立的規則優先採用。這類郵件會排除功能準則。
  
## <a name="related-topics"></a>相關主題

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](block-email-spam-to-prevent-false-negatives.md)
  

