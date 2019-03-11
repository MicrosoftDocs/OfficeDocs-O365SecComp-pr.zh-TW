---
title: 零時差自動清除 - 防範垃圾郵件和惡意程式碼
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: 零時差自動清除 (ZAP) 是偵測到郵件與垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，電子郵件保護功能，並再呈現無害惡意內容。 如何 ZAP 執行此動作，則偵測到的惡意內容類型而定。
ms.openlocfilehash: b28de1b05843e3f5b0f6e7fc905c96f094c277f9
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524017"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零時差自動清除 - 防範垃圾郵件和惡意程式碼

## <a name="overview"></a>概觀

零時差自動清除 (ZAP) 是偵測到的郵件釣魚程式、 垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，電子郵件保護功能，並再呈現無害惡意內容。 ZAP 如何這取決於偵測到; 惡意內容類型郵件可以 zapped 由於郵件內容、 Url 或附件。
  
ZAP 是隨附於預設隨附於任何 Office 365 訂用帳戶，包含 Exchange Online 信箱的 Exchange Online Protection。

ZAP 已開啟根據預設，但必須符合下列條件：
  
- **垃圾郵件動作**設為**移至垃圾郵件] 資料夾的郵件**。 <br/>您也可以建立僅適用於一群使用者如果您不想所有信箱移轉至雲端過濾的 ZAP 新垃圾郵件篩選原則。

- 使用者有保留其預設垃圾郵件設定]，且已不會關閉垃圾郵件保護。 （如需在 Outlook 中的使用者選項的詳細資訊，請參閱[變更的垃圾郵件篩選器中的保護層級](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)）。 
  
## <a name="how-does-zap-work"></a>ZAP 的運作方式？

Office 365 更新反垃圾郵件引擎和惡意程式碼中的簽章即時每日。 不過，您的使用者仍可能會收到惡意的郵件傳遞到不同的原因，包括內容 weaponized 之後會傳遞至使用者的收件匣。 ZAP 解決此問題持續監視更新的 Office 365 垃圾郵件和惡意程式碼簽章。 ZAP 可以找出並移除先前已傳遞的郵件已在使用者的收件匣中。 

- 識別為垃圾郵件的郵件，ZAP 會將未閱讀的郵件移至使用者的垃圾郵件資料夾。 

- 識別為釣魚程式的郵件，ZAP 會將郵件移至使用者的垃圾郵件] 資料夾，不論是否已讀取電子郵件。

- 新偵測到惡意程式碼，ZAP 會移除電子郵件，不論是否已讀取電子郵件附件。 
  
ZAP 動作是很完美的信箱使用者資訊。如果移動電子郵件訊息時，它們不會通知。
  
允許清單、[郵件流程規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)及使用者規則或其他篩選器會優先於 ZAP。
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>若要檢視或設定的垃圾郵件篩選原則
  
1. 移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。

2. **威脅管理**] 下選擇 [**反垃圾郵件**]。

3. 檢閱標準設定。 

4. 如果您想要自訂您的設定，選取 [**自訂**] 索引標籤，並開啟 [**自訂設定**。 編輯您的設定，如果您想，選擇 [ **+ 建立原則**來新增新的原則。 
    
## <a name="to-see-if-zap-moved-your-message"></a>若要查看 ZAP 是否移動郵件

如果您想要看到 ZAP 如果移動您的郵件，您可以使用[威脅保護狀態報表](view-email-security-reports.md#threat-protection-status-report)（或[威脅總管](use-explorer-in-security-and-compliance.md)）。
    
## <a name="to-disable-zap"></a>若要停用 ZAP
  
如果您想要停用您 Office 365 租用戶時能量光束或一組使用者，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)，EOP 指令程式的**ZapEnabled**參數。
    
在下列範例中，ZAP 已停用名為"Test"的內容篩選原則。
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>常見問題集

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>如果合法郵件移至 [垃圾郵件] 資料夾，會發生什麼事？
  
您應該遵循誤判正常的報告程的序。 郵件會從收件匣移至 [垃圾郵件] 資料夾的唯一原因可能因為服務已決定郵件是垃圾郵件或惡意。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>如果使用 Office 365 隔離而不是垃圾郵件資料夾？
  
ZAP 不會將郵件移至隔離區從收件匣這一次。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>如果我有自訂郵件流程規則 （封鎖 / 允許規則）？
  
建立由系統管理員 （郵件流程規則）] 或 [封鎖] 和 [允許規則的規則的優先順序。 這類郵件會排除功能準則。
  
## <a name="related-topics"></a>相關主題

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](reduce-spam-email.md)
  

