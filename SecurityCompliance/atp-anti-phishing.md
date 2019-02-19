---
title: Office 365 中的 ATP 防網路釣魚功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP 反網路釣魚是 Office 365 進階威脅保護的一部分。ATP 反網路釣魚適用於搭配模擬偵測演算法的機器學習模型的一組提供保護商品和矛網路釣魚攻擊的內送郵件。所有訊息都是因偵測網路釣魚郵件，以及用來防止各種使用者和網域模擬攻擊的進階演算法一組經過訓練的機器學習模型廣泛設定而異。
ms.openlocfilehash: 3cd786de403bd2fe4fcdd5d53f3f825c6e4e8a40
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "29889246"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="201df-105">Office 365 中的 ATP 防網路釣魚功能</span><span class="sxs-lookup"><span data-stu-id="201df-105">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="201df-p102">ATP 反網路釣魚是[Office 365 進階威脅保護](office-365-atp.md)的一部分。ATP 反網路釣魚適用於搭配模擬偵測演算法的機器學習模型的一組提供保護商品和矛網路釣魚攻擊的內送郵件。所有訊息都是因偵測網路釣魚郵件，以及用來防止各種使用者和網域模擬攻擊的進階演算法一組經過訓練的機器學習模型廣泛設定而異。ATP 反網路釣魚保護您的組織根據至原則之設定的 Office 365 全域或安全性管理員。</span><span class="sxs-lookup"><span data-stu-id="201df-p102">ATP anti-phishing is part of [Office 365 Advanced Threat Protection](office-365-atp.md). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="201df-110">若要深入了解，請參閱[Set up Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="201df-110">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="201df-p103">ATP 反網路釣魚只有在進階威脅 Protection，其中包含在訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="201df-p103">ATP anti-phishing is only available in Advanced Threat Protection, which is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="201df-113">ATP 反網路釣魚的運作方式</span><span class="sxs-lookup"><span data-stu-id="201df-113">How ATP anti-phishing works</span></span>

<span data-ttu-id="201df-p104">ATP 反網路釣魚會檢查郵件可能是網路釣魚指標的內送郵件。每當使用者是原則所涵蓋 ATP （安全附件、 安全的連結或反網路釣魚） 學習分析決定如果原則可套用至郵件與適當的動作是郵件的模型的多部電腦來評估傳入訊息進行設定的原則為基礎。</span><span class="sxs-lookup"><span data-stu-id="201df-p104">ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="201df-p105">ATP 反網路釣魚讓 Office 365 全域管理員或安全性管理員可定義提供理想的網路釣魚攻擊包含模擬的使用者或網域的原則。（或兩者）。Office 365 全域管理員或安全性管理員定義哪些使用者和網域應保護免受模擬攻擊使用下列任一原則內的使用者或網域或使用信箱智慧固定的清單。信箱智慧是使用者的電子郵件習慣及個人連絡人的進階的知識。ATP 可學習如何每個個別的使用者會與其他組織內外的使用者通訊和建立這些關係的對應設定。本藍圖可讓 ATP 了解如何確定右邊的郵件會被識別為模擬的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="201df-p105">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="201df-p106">ATP 反網路釣魚原則可套用到特定的一段的人員或組織中的群組或整個網域或所有自訂的網域。若要深入了解，請參閱[Set up Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="201df-p106">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="201df-124">如何取得 ATP 反網路釣魚</span><span class="sxs-lookup"><span data-stu-id="201df-124">How to get ATP anti-phishing</span></span>

<span data-ttu-id="201df-p107">ATP 反網路釣魚功能屬於[進階威脅保護](office-365-atp.md);不過，當反網路釣魚原則會定義套用 ATP 反網路釣魚保護。（一個範例是模擬為基礎的原則）。請參閱 ＜ [Set up Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="201df-p107">ATP Anti-Phishing features are part of [Advanced Threat Protection](office-365-atp.md); however, ATP anti-phishing protection applies when anti-phishing policies are defined. (One example is an impersonation-based policy.) See [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="201df-127">如何知道 ATP 反網路釣魚是否就緒</span><span class="sxs-lookup"><span data-stu-id="201df-127">How to know if ATP anti-phishing is in place</span></span>

<span data-ttu-id="201df-p108">ATP 反網路釣魚原則必須定義 protection 設為 [作用中的順序。檢查這第一次以確認保護已備妥。</span><span class="sxs-lookup"><span data-stu-id="201df-p108">ATP anti-phishing policies must be defined in order for protection to be in effect. Check this first to verify protection is in place.</span></span>

<span data-ttu-id="201df-p109">此外，報表可用來顯示服務組織的運作方式。若要深入了解，請參閱[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="201df-p109">In addition, reports are available to show how the service is working for your organization. To learn more, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="201df-132">ATP 反網路釣魚機器學習作用中的特定使用者的模型，使用者必須已定義的[ATP 安全附件](atp-safe-attachments.md)、 [ATP 安全連結](atp-safe-links.md)或 ATP 反網路釣魚原則的一部分。</span><span class="sxs-lookup"><span data-stu-id="201df-132">For ATP anti-phishing machine learning models to be active for a particular user, that user must be part of a defined [ATP Safe attachments](atp-safe-attachments.md), [ATP Safe Links](atp-safe-links.md), or ATP Anti-Phishing policy.</span></span> 

<span data-ttu-id="201df-p110">下表說明幾個範例案例。在每個這些範例中，組織使用 Office 365 企業版 E5，其中包含進階威脅保護。</span><span class="sxs-lookup"><span data-stu-id="201df-p110">The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="201df-135">**範例案例**</span><span class="sxs-lookup"><span data-stu-id="201df-135">**Example scenario**</span></span>|<span data-ttu-id="201df-136">**ATP 反網路釣魚沒有在此例中套用吗？**</span><span class="sxs-lookup"><span data-stu-id="201df-136">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="201df-137">Pat 的組織具有 Office 365 企業版 E5，但無人已定義 ATP 安全附件、 ATP 安全連結或尚未進階網路釣魚 ATP 的任何原則。</span><span class="sxs-lookup"><span data-stu-id="201df-137">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="201df-p111">[否]。雖然有提供功能，必須至少一個 ATP 原則定義學習模型 ATP 電腦運作的順序。進行模擬 ATP 反網路釣魚原則也必須備妥。</span><span class="sxs-lookup"><span data-stu-id="201df-p111">No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="201df-p112">Lee 是在 Contoso sales 部門的員工。Lee 的組織中進行的財務員工僅適用於具有 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="201df-p112">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="201df-p113">[否]。在此例中 ATP 反網路釣魚 （機器模型和模擬保護） 會套用至 finance 員工但不是會包括銷售部門的其他員工。</span><span class="sxs-lookup"><span data-stu-id="201df-p113">No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="201df-p114">昨天、 Jean 的組織在 Office 365 系統管理員設定套用至所有員工 ATP 反網路釣魚原則。稍早今天 Jean 接收電子郵件訊息內含該原則所涵蓋模擬。</span><span class="sxs-lookup"><span data-stu-id="201df-p114">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="201df-p115">[是]。在這個範例中，Jean 已授權的進階威脅保護，並已定義包含 Jean ATP 反網路釣魚原則。它通常採用的新原則才會生效跨資料中心來; 約 30 分鐘因為在此例中通過一天、 原則應作用中。</span><span class="sxs-lookup"><span data-stu-id="201df-p115">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="201df-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="201df-150">Related topics</span></span>

[<span data-ttu-id="201df-151">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="201df-151">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="201df-152">Office 365 的反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="201df-152">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="201df-153">設定 Office 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="201df-153">Set up anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
  
[<span data-ttu-id="201df-154">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="201df-154">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="201df-155">設定 Office 365 中的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="201df-155">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="201df-156">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="201df-156">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="201df-157">設定 Office 365 中的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="201df-157">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="201df-158">進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="201df-158">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
