---
title: 如何減少 Office 365 中的垃圾郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: 了解最常用來協助減少 Office 365 中垃圾郵件的方式。
ms.openlocfilehash: 7c2ea48c4244d2b86f01c89decd4add006f21a5c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157345"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>如何減少 Office 365 中的垃圾郵件

 **您在 Office 365 收到太多垃圾郵件嗎？請執行此動作。**
  
我們強烈建議您[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)來回報郵件誤判的狀況，以協助我們改善篩選器。此外，您可以將郵件*以附件方式*轉寄到 junk@office365.microsoft.com 或 phish@office365.microsoft.com (如果網路釣魚郵件)。

> [!TIP]
> 如果您認為郵件是垃圾郵件，而且郵件也位於垃圾郵件資料夾，那就沒有問題。如果您完全不想在信箱中看到垃圾郵件，則應該變更反垃圾郵件原則來隔離郵件。如需隔離郵件的詳細資訊，請參閱[隔離Office 365 中的電子郵件](quarantine-email-messages.md) (機器翻譯)。

## <a name="fixing-allowed-spam"></a>修正允許的垃圾郵件

我們經常看到客戶因為設定錯誤而將垃圾郵件收到收件匣中。其中最常見的是在郵件流程規則 (也稱為傳輸規則) 中將網域設定為繞過篩選器，或將您的網域設定在允許/安全寄件者清單中。這樣不好，因為原本會被攔截的這些郵件會跳過垃圾郵件篩選。  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>收到太多垃圾郵件的其他常見原因解決方案

為了保護您免於收到太多垃圾郵件，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。
  
### <a name="for-admins"></a>若為系統管理員

- **將您的 DNS 記錄指向 Office 365** 為了讓 EOP 提供最佳防護，所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 Office 365，而且只能指向 Office 365。請參閱[當您管理 DNS 記錄時建立 Office 365 的 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) (機器翻譯)。
    
- 
  **啟用所有信箱上的垃圾郵件規則** 根據預設，垃圾郵件篩選動作會設為 [將郵件移至垃圾郵件資料夾]****。如果這是您目前喜好的垃圾郵件原則動作，則每個信箱[也須啟用垃圾郵件規則](https://support.office.com/zh-TW/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (英文)。若要進行此檢查，您可以對一或多個信箱執行 Get-MailboxJunkEmailConfiguration Cmdlet。例如，您可能會對所有信箱進行此檢查，方法為執行 Cmdlet：Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    檢視輸出時，Enable 屬性應該設為 True。若設為 false，您可以執行 Set-MailboxJunkEmailConfiguration，將它變更為 True。
    
- **在內部部署 Exchange Server 中建立郵件流程規則** 如果您使用的是 Exchange Online Protection，但您的信箱位於內部部署 Exchange Server，則您需要在內部部署 Exchange Server 中建立幾個郵件流程規則。請參閱 [EOP 專屬的指示](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)) (英文)。
    
- 
  **將大量電子郵件標示為垃圾郵件** 大量電子郵件是使用者可能已註冊，但仍有可能不想要的電子郵件。在郵件標頭中，於 X-Microsoft-Antispam 標頭中尋找 BCL (大量信賴等級) 屬性。如果 BCL 值小於垃圾郵件篩選器中設定的閾值，您可能想要調整閾值，而不是將這些類型的大宗郵件標示為垃圾郵件。不同的使用者對於[大量電子郵件的處理方式](https://docs.microsoft.com/zh-TW/office365/SecurityCompliance/bulk-complaint-level-values) (英文) 各有不同的容錯和喜好設定。您可以針對不同的使用者喜好設定建立不同的原則或規則。 
    
- **立即封鎖寄件者**：在需要立即封鎖寄件者的情況下，您可以透過電子郵件地址、網域或 IP 位址來進行封鎖。請參閱[使用 EAC 來建立郵件流程規則，以封鎖來自網域或使用者的郵件](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user)。請注意，使用者允許清單上的項目能夠覆寫系統管理員的封鎖設定。
    
- **為使用者開啟回報郵件增益集** 我們建議建議您[為使用者啟用回報郵件增益集](enable-the-report-message-add-in.md)。身為系統管理員，您也可以檢視使用者傳送的意見反應，並使用任何模式，來調整任何可能造成問題的設定。
- **啟用 [DKIM](use-dkim-to-validate-outbound-email.md)** 以簽署所有外寄郵件，藉此提高您的網域和租用戶中的安全性。
 > [!TIP]
> 啟用 DKIM 之後，您必須啟用 [DMARC](use-dkim-to-validate-outbound-email.md)，因為此記錄會驗證 DKIM 和 SPF 是否正確運作，而一般來說，因為 O365 會管理您的私人和公用對稱金鑰，偽造的電子郵件不會有簽章。
    
### <a name="for-users"></a>若為使用者

- **啟用垃圾郵件規則，並檢查您的允許清單** 檢查垃圾郵件動作規則是否已啟用，以及寄件者或寄件者的網域是否未設為要在您的個人允許清單中略過。存取這些設定的最佳方式來自[封鎖或允許 (垃圾郵件設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) (機器翻譯)。當您在那裡時，也可以選擇封鎖寄件者的電子郵件地址或網域。
    
- **向 Microsoft 報告垃圾郵件** 透過[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) (機器翻譯)，向 Microsoft 報告垃圾郵件。此外，您可以將郵件傳送至 junk@office365.microsoft.com，並將一或多封郵件附加到報告。
    
    **重要** 如果您未以附件形式轉寄郵件，則標頭將會遺失，而且我們將無法改善 (英文) Office 365 中的垃圾郵件篩選功能。 
    
- **從大量電子郵件取消訂閱** 如果郵件是您已註冊的項目 (例如電子報、產品公告等)，而且其包含的連結來自聲譽卓著的來源，則您可能只想取消訂閱。Office 365 通常不會將這些郵件視為垃圾郵件。您也可以選擇封鎖寄件者，或要求系統管理員進行將導致所有大宗郵件被視為垃圾郵件的變更。
