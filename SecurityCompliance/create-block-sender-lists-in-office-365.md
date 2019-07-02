---
title: 在 Office 365 中建立封鎖寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 封鎖寄件者清單選項包括 Outlook 封鎖的寄件者、反垃圾郵件寄件者/網域封鎖清單、IP 封鎖清單, 以及 Exchange 傳輸規則 (ETRs) 也稱為郵件流程規則。
ms.openlocfilehash: 9933cb79b7dce949384815a7b2ed8a9ac8a7824b
ms.sourcegitcommit: f96029928a6cdd141783026d57bc2179d7963af6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017685"
---
# <a name="create-block-sender-lists-in-office-365"></a>在 Office 365 中建立封鎖寄件者清單

有時, 您必須封鎖寄件者的不想要的電子郵件。 有幾種方法可供選擇。 這些選項包括 Outlook 封鎖的寄件者、反垃圾郵件寄件者/網域封鎖清單、IP 封鎖清單和 Exchange 傳輸規則 (ETRs, 也稱為郵件流程規則)。

> [!NOTE]
> 雖然組織區塊清單可以用來解決漏報 (遺漏的垃圾郵件), 但這些候選人也應該提交給 Microsoft 進行分析。 使用封鎖清單來管理漏報會大幅增加您的管理負荷。 如果您要使用封鎖清單來達到此目的, 您必須同時將[垃圾郵件、非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)。

設定封鎖寄件者清單的適當方法, 會視影響範圍而有所不同。 針對單一使用者影響, 正確的解決方案可能是使用 Outlook 封鎖的寄件者, 但如果多位使用者或所有使用者都受到影響, 則其中一個其他選項會更合適。

## <a name="options-from-least-to-broadest-scope"></a>從最低到最廣泛的範圍的選項

建立封鎖清單時, 請務必根據影響範圍 (受影響的人員數目) 來挑選適當的方法, 使其符合封鎖方法的廣度。 以下所列的選項會依範圍和廣度來排序。 清單從窄到範圍, 但閱讀完整建議的*詳細*資料。

- Outlook 封鎖的寄件者
- 反垃圾郵件原則: 寄件者/網域封鎖清單
- Exchange 傳輸規則 (也稱為郵件流程規則) ETRs
- 反垃圾郵件原則: IP 封鎖清單

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 封鎖的寄件者

當只有少量的使用者受到影響時, 就應該使用 Outlook 封鎖的寄件者, 因為這只會影響傳送給他們的郵件。

> [!IMPORTANT]
> 如果不想要的郵件是來自可信且可識別來源的簡報, 請從電子郵件取消訂閱, 以防止使用者日後收到電子郵件。

[Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[outlook 用戶端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之間的設定步驟是不同的。 **當郵件因為封鎖的寄件者而成功封鎖時, 您會在 X Forefront-反垃圾郵件中看到 SFV: BLK** , 表示郵件遭到封鎖。

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>使用反垃圾郵件原則寄件者/網域封鎖清單

當多個使用者受到影響時, 範圍就會變寬, 而且您必須使用全公司的寄件者/網域封鎖清單反垃圾郵件原則。 您可以在 [[設定您的垃圾郵件篩選原則](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)] 檔中找到詳細步驟。 透過此方法封鎖的任何郵件都會遵循原則中所設定的垃圾郵件動作。

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>使用 Exchange 傳輸規則 (ETRs) 來封鎖特定寄件者

如果您需要封鎖傳送給特定使用者或整個組織的郵件, 則可以使用 ETRs (也稱為郵件流程規則)。 ETRs 比較靈活, 因為它們可以觸發寄件者電子郵件地址或網域, 以及郵件中的關鍵字和其他屬性。 這種靈活性可讓您建立部分對完成的區塊。 [請按一下以取得建立 ETR (也稱為郵件流程規則) 的步驟](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

> [!IMPORTANT]
> 建立的規則非常簡單, 因此很** 重要的是, 您可能會認為所使用的準則盡可能具體。 此外, 請務必在您建立的規則上啟用審核, 並進行測試, 以確保一切正常運作。

## <a name="use-anti-spam-policy-ip-block-lists"></a>使用反垃圾郵件原則 IP 封鎖清單

當您無法使用其中一個選項來封鎖寄件者時, 可以使用反** 垃圾郵件原則的 IP 封鎖清單。 您[可以在 [設定連線篩選原則] 一文中找到詳細步驟](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。 請務必將封鎖的 Ip 清單保留在此處,*不*建議使用 IP 位址範圍。 **

您應該*特別*避免新增屬於消費者服務或共用基礎結構的 ip 位址範圍, 也請確定您已查看允許的 ip 地址清單, 做為定期維護的一部分。 **因為允許專案可以開啟受攻擊的路由, 所以您必須仔細管理此清單, 並定期移除不再需要的允許專案。** 此外, 如果您要在安全寄件者清單中允許, 請務必閱讀並瞭解在*[Office 365 中建立安全寄件者清單中](create-safe-sender-lists-in-office-365.md)* 的風險和防範措施。