---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 與 Office 365 進階郵件加密功能掌握 Office 365 郵件加密 (OME)，您可以擴充您的電子郵件安全性設定的自訂品牌範本透過電子郵件到期日。
ms.openlocfilehash: 260e6032d3b7a4c9b81fca73dfbcd57fa01168cb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157665"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="0d0f9-103">為由 Office 365 進階郵件加密所加密的電子郵件設定到期日</span><span class="sxs-lookup"><span data-stu-id="0d0f9-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="0d0f9-104">掌握 Office 365 郵件加密在特定的訂閱中使用 office 365 進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="0d0f9-105">進階的郵件加密包含在[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 企業版 E5 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="0d0f9-106">如果貴組織擁有不包含 Office 365 進階郵件加密的 Office 365 訂閱，您可以以 E5 合規性的進階合規性 SKU 與附加元件形式購買進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-106">If your organization has an Office 365 subscription that doesn't include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="0d0f9-107">您可以使用郵件到期上您的使用者傳送給外部收件者使用 OME 入口網站來存取加密的電子郵件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="0d0f9-108">您強制使用 OME 入口網站，以檢視和回覆加密所使用 Windows Powershell 中指定到期日的自訂品牌的範本貴組織所傳送的電子郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="0d0f9-109">以 O365 全域系統管理員身分，當您套用公司品牌自訂外觀的 Office 365 組織的電子郵件，您也可以指定這些電子郵件訊息的到期日。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-109">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="0d0f9-110">使用 Office 365 進階郵件加密，您可以建立多個範本發出的加密電子郵件從您的組織。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="0d0f9-111">使用範本，您可以控制多久收件者可以存取您的使用者所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="0d0f9-112">當使用者收到郵件已設定到期日時，使用者會看到的包裝函式電子郵件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="0d0f9-113">如果使用者嘗試開啟過期的郵件，則會在 OME 入口網站中出現的錯誤。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="0d0f9-114">您只能設定到期日的電子郵件給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-114">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="0d0f9-115">使用 Office 365 進階郵件加密，只要您將自訂品牌套 Office 365 適用於包裝函式電子郵件符合您要套用該範本的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-115">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="0d0f9-116">此外，您只可以使用到期，如果您使用自訂品牌。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-116">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="0d0f9-117">建立自訂品牌範本，以藉由使用 PowerShell 來強制郵件到期</span><span class="sxs-lookup"><span data-stu-id="0d0f9-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="0d0f9-118">搭配 Office 365 組織中具有全域系統管理員權限的帳戶，[連線到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="0d0f9-119">執行新增 Set-omeconfiguration 指令程式。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="0d0f9-120">其中：</span><span class="sxs-lookup"><span data-stu-id="0d0f9-120">Where:</span></span>

- <span data-ttu-id="0d0f9-121">`Identity`是自訂樣板的名稱。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-121">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="0d0f9-122">`ExternalMailExpiryInDays`識別收件者可以保留郵件過期前的天數。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-122">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="0d0f9-123">您可以使用 1 – 730 天之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="0d0f9-123">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="0d0f9-124">Office 365 進階郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0d0f9-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="0d0f9-125">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="0d0f9-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="0d0f9-126">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="0d0f9-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="0d0f9-127">郵件原則及符合性服務說明</span><span class="sxs-lookup"><span data-stu-id="0d0f9-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)