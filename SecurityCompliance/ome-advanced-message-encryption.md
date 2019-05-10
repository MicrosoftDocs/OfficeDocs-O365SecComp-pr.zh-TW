---
title: Office 365 進階郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 在 Office 365 中的進階的郵件加密可協助組織符合其合規義務讓管理員將過期並撤銷透過對加密的電子郵件的 Office 365 入口網站的存取。
ms.openlocfilehash: 5559a2bca4cd804cfcfdf547146eeb416252ca5f
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834902"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="35e92-103">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="35e92-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="35e92-104">掌握 Office 365 郵件加密在特定的訂閱中使用 office 365 進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="35e92-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="35e92-105">進階的郵件加密包含在[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 企業版 E5 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="35e92-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="35e92-106">如果貴組織擁有不包含 Office 365 進階郵件加密的 Office 365 訂閱，您可以以 E5 合規性的進階合規性 SKU 與附加元件形式購買進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="35e92-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="35e92-107">在 Office 365 中的進階的郵件加密可協助客戶符合規範，需要更有彈性的控制項，透過外部收件者，以及其存取權加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35e92-107">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="35e92-108">使用進階郵件加密 Office 365 中，您可以控制自動原則與組織外共用機密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35e92-108">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="35e92-109">您設定這些原則，以識別敏感資訊類型，例如 PII、 金融或狀況識別碼，或您可以使用關鍵字來提升保護。</span><span class="sxs-lookup"><span data-stu-id="35e92-109">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="35e92-110">一旦您設定的原則，您會配對自訂品牌的電子郵件範本的原則，然後再新增額外的控制項，符合原則的電子郵件的到期日。</span><span class="sxs-lookup"><span data-stu-id="35e92-110">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="35e92-111">此外，系統管理員可以更進一步控制透過安全網路入口網站外部存取的任何時候撤銷存取權的郵件加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35e92-111">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="35e92-112">您只能撤銷並設定傳送給外部收件者的電子郵件的到期日。</span><span class="sxs-lookup"><span data-stu-id="35e92-112">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="35e92-113">使用 Office 365 進階郵件加密，只要您套用自訂品牌範本時，Office 365 適用於包裝函式電子郵件符合您要套用該範本的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="35e92-113">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="35e92-114">您只可以撤銷的郵件，並透過入口網站的使用者接收的郵件套用到期日期。</span><span class="sxs-lookup"><span data-stu-id="35e92-114">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="35e92-115">換句話說，電子郵件已套用的自訂品牌範本。</span><span class="sxs-lookup"><span data-stu-id="35e92-115">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="35e92-116">開始使用 Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="35e92-116">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="35e92-117">下列主題說明如何設定及使用進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="35e92-117">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="35e92-118">您的組織必須包含 Office 365 進階郵件加密的訂閱。</span><span class="sxs-lookup"><span data-stu-id="35e92-118">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="35e92-119">如需支援的訂閱的詳細資訊，請參閱[郵件原則及符合性服務說明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="35e92-119">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="35e92-120">如果您沒有 Office 365 郵件加密已設定，請參閱 <<c0>設定新的 Office 365 郵件加密功能。</span><span class="sxs-lookup"><span data-stu-id="35e92-120">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="35e92-121">[設定 Office 365 進階郵件加密所加密的電子郵件的到期日](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="35e92-121">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="35e92-122">控制機密與自動共用組織外部的電子郵件加密的電子郵件的安全 web 入口網站透過存取過期，進而提升保護原則。</span><span class="sxs-lookup"><span data-stu-id="35e92-122">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="35e92-123">[撤銷由 Office 365 進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="35e92-123">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="35e92-124">控制在組織外共用機密電子郵件並撤銷存取透過加密的電子郵件的安全 web 入口網站來加強保護。</span><span class="sxs-lookup"><span data-stu-id="35e92-124">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  