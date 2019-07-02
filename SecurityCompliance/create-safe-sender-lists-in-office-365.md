---
title: 在 Office 365 中建立安全的寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要確定您收到來自特定寄件者的郵件, 因為您信任它們及其郵件, 您可以在 Exchange 系統管理中心的垃圾郵件篩選原則中調整 [允許] 清單。
ms.openlocfilehash: 4526441c68d187e644a06228c5b1be820968524a
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199564"
---
# <a name="create-safe-sender-lists-in-office-365"></a>在 Office 365 中建立安全的寄件者清單

如果您想要確定使用者收到來自特定寄件者或寄件者的電子郵件, 因為您信任它們及其郵件, 有多個可用的方法可供您選擇。 這些選項包括 Exchange 傳輸規則 (ETRs)、Outlook 安全寄件者、IP 允許清單、反垃圾郵件寄件者/網域允許清單。

> [!IMPORTANT]
> 雖然可以使用 [組織允許清單] 來解決誤報, 但應該將這視為臨時性的解決方案, 並盡可能避免使用。 不建議使用 [允許清單] 來管理 false 陽性, 因為這種方法可能會不小心開啟貴組織, 使其不會受到詐騙、類比及其他攻擊。 如果您要使用允許清單來進行此目的, 您必須小心, 並保留文章以將[垃圾郵件、非垃圾郵件和網路釣魚郵件提交給 Microsoft 進行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)。

設定安全寄件者清單的建議方法是使用 Exchange 傳輸規則 (ETRs), 因為這會提供最大的彈性, 以確保只允許正確的郵件。 *反垃圾郵件原則電子郵件地址*和*網域型允許清單*不像*IP 位址型清單*一樣安全, 因為網域很容易遭到盜用。 但是, 反垃圾郵件原則 IP 允許清單也會顯示風險, 因為它們會允許透過該 IP 傳送的任何網域略過垃圾郵件篩選。 請小心, 並謹慎監視所產生的*任何*例外狀況。

> [!IMPORTANT]
> 關於如何建立**封鎖的寄件者清單**的資訊在[這裡](create-block-sender-lists-in-office-365.md)。

## <a name="options-from-most-to-least-recommended"></a>最多建議的選項

您應該一直限制允許清單, 因為它們略過許多安全性措施。 您必須重新檢查所有允許清單, 做為標準維護的一部分, 讓您知道允許略過的人。 建議的作法是盡可能使用限制的 ETRs。

- Exchange 傳輸規則 (也稱為郵件流程規則) ETRs
- Outlook 安全寄件者
- 反垃圾郵件原則: IP 允許清單
- 反垃圾郵件原則: 寄件者/網域允許清單

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>使用 Exchange 傳輸規則 (ETRs) 允許特定寄件者 (建議)

若要確保您的組織只允許合法郵件, 條件應該是下列其中一項:

- 使用傳送網域的寄件者驗證狀態。 方法是檢查驗證結果標頭, 以確定它包含 "dmarc = pass" 或 "dmarc = bestguesspass"。 這可確保傳送網域已經過驗證, 而且不會遭到盜用。 按一下以取得有關[SPF](https://docs.microsoft.com/en-us/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)和[DMARC](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dmarc-to-validate-email)電子郵件驗證的詳細資訊。

- 或者, 如果傳送網域沒有驗證, 請使用傳送網域*加上*傳送 IP (或 IP 範圍)。 請務必盡可能*限制*您的目標, 讓您盡可能安全地執行此動作。 *不*建議使用大於/24 的 IP 範圍。 避免新增屬於消費者服務或共用基礎結構的 IP 位址範圍。

> [!IMPORTANT]
> 如果您允許 NATted 的 IP 位址, 您應該知道該 NAT 集區所涉及的機器, 才能知道允許的範圍。 請注意, IP 位址可能會變更, 而 NAT 參與者也可能會變更。 您必須重新檢查所有允許清單, 包括 IP 允許做為標準維護的一部分。

- 您*可以選擇性*地新增郵件來自組織外部的條件 (這是隱含的, 但將它新增為可能無法正確設定之內部部署伺服器的條件)。

- *(選用*) 如果您可以識別電子郵件主旨或內文中的任何唯一關鍵字或片語, 請使用此資訊做為額外限制郵件流程規則所允許之電子郵件的額外條件。

規則上的動作必須遵循下列模式:

1. 將垃圾郵件信賴等級 (SCL) 設為-1 (略過垃圾郵件篩選)。

2. 新增 X 標頭, 以指出規則的功能。 在下列範例中, 您可以新增簡易標頭 "X-ETR: 略過驗證的發件`contoso.com`人的垃圾郵件篩選」。 如果您在此規則中有一個以上的網域, 您可以視需要變更標頭文字。**當郵件因為 ETR 而跳過篩選時, 它會在 X Forefront-反垃圾郵件報告標頭中戳記 SFV: SKN**(**如果它位於 IP 允許清單中, 它也會戳記 IPV: CAL**)。 這會協助疑難排解。

![用來略過垃圾郵件篩選的 GUI。](media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> 若要略過垃圾郵件篩選的條件, 請勿將郵件流程規則設定為僅*寄件者網域*。 此方法會大幅增加垃圾郵件寄件者可以偽造傳送網域的風險 (或模擬完整的電子郵件地址) 略過所有垃圾郵件篩選、寄件者驗證檢查, 且郵件會抵達人員的收件匣。

![如何將 SCL 設為減號。](media/2-AllowList-SetsSCLMinus1.png)

不要將您擁有的網域或常用網域 (例如`microsoft.com`) 新增至郵件流程規則做為條件。 這會被視為高風險, 因為它會建立不良參與者的機會, 以傳送您本來就會被篩選掉的郵件。

[請按一下以取得建立 ETR (也稱為郵件流程規則) 的步驟](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

## <a name="use-outlook-safe-senders-end-user-managed"></a>使用 Outlook 安全寄件者 (使用者管理)

使用者也可以透過 Outlook 安全寄件者來傳送位址, 而不是全域授權位址、網域或 IP 位址。 [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[outlook 用戶端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之間的設定步驟會有所不同。 **當郵件因為安全寄件者而成功授權時, 您會在 X Forefront-反垃圾郵件報告中看到 SFV: SFE** , 表示會略過垃圾郵件/詐騙/網路釣魚篩選。

## <a name="use-anti-spam-policy-ip-allow-lists"></a>使用反垃圾郵件原則 IP 允許清單

當您在驗證寄件者驗證時, 無法使用 ETRs 全域允許特定寄件者, 或將網域和 IP 彼此結合時, 下一個最佳選項是將寄件者新增至*反垃圾郵件原則 IP 允許清單*。 您[可以在設定連線篩選原則檔中找到詳細步驟](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。 請務必將允許的 IP 位址清單保持在最小值, 並避免使用 IP 位址範圍。 避免新增屬於消費者服務或共用基礎結構的 IP 位址範圍, 也請*確定*您定期查看允許的 ip 地址清單, 並移除不再需要的位址。

> [!CAUTION]
> 將反垃圾郵件原則設定為只允許依據寄件者 IP 位址, 會導致略過來自該 IP 位址的所有郵件的垃圾郵件篩選允許規則。 這會造成對您傳送您要篩選掉的郵件的不良參與者傳送高風險。此方法也會跳過所有垃圾郵件篩選、寄件者驗證檢查, 以及郵件會落在使用者的收件匣中, 以增加風險。

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>使用反垃圾郵件原則寄件者/網域允許清單

最不可取的選項是以寄件者/網域進行授權。 如果完全忽略垃圾郵件/詐騙/網路釣魚防護, 且不會評估寄件者驗證, 請*盡可能*避免此選項。 此方法會增加您從不良參與者接收郵件的風險, 且僅在測試時才暫時建議使用。 您可以在 [[設定您的垃圾郵件篩選原則](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)] 檔中找到詳細步驟。

> [!CAUTION]
> 將反垃圾郵件原則設定為 [*允許寄件者/允許網域*] 會導致郵件跳過 a 來自允許清單中的寄件者的郵件, 或 b) 來自允許網域的任何寄件者的郵件。 此方法會大幅增加垃圾郵件寄件者可以偽造的傳送網域 (或模擬完整電子郵件地址), 以跳過所有垃圾郵件篩選、寄件者驗證檢查, 並將郵件直接傳送至人員的收件匣。
> 
> 不要將您擁有或常用網域的網域 (例如`microsoft.com`) 新增至郵件流程規則做為條件。 此方法會被視為高風險, 因為它會建立不良參與者的機會, 以傳送您本來會被篩選掉的郵件, 進而增加風險。

> [!IMPORTANT]
> 關於如何建立**封鎖的寄件者清單**的資訊在[這裡](create-block-sender-lists-in-office-365.md)。