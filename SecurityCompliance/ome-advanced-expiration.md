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
description: 在 Office 365 郵件加密 (OME) 頂端有 Office 365 高級郵件加密功能時, 您可以透過自訂的署名範本來設定電子郵件的到期日, 以擴充您的電子郵件安全性。
ms.openlocfilehash: 7c4ad1fb4a91bd62569edc5db9042dfbd2dbd9fe
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852757"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="c14ac-103">為由 Office 365 進階郵件加密所加密的電子郵件設定到期日</span><span class="sxs-lookup"><span data-stu-id="c14ac-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="c14ac-104">Office 365 高級郵件加密可在特定訂閱中的 Office 365 郵件加密上使用。</span><span class="sxs-lookup"><span data-stu-id="c14ac-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="c14ac-105">[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企業版 E5 和 Office 365 教育版 A5 包含先進的郵件加密。</span><span class="sxs-lookup"><span data-stu-id="c14ac-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="c14ac-106">如果您的組織有 Office 365 訂閱, 但未包含 Office 365 的高級郵件加密, 您可以使用 advanced 合規性 SKU 的 E5 符合性, 以附加元件形式購買高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="c14ac-106">If your organization has an Office 365 subscription that doesn't include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="c14ac-107">您可以在電子郵件上使用郵件到期, 您的使用者傳送給使用 OME 入口網站來存取加密電子郵件的外部收件者。</span><span class="sxs-lookup"><span data-stu-id="c14ac-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="c14ac-108">您可以利用在 Windows Powershell 中指定到期日的自訂署名範本, 讓收件者使用 OME 入口網站來查看和回復組織所傳送的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c14ac-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="c14ac-109">作為 O365 全域系統管理員, 當您套用公司品牌以自訂 Office 365 組織的電子郵件訊息的外觀時, 您也可以指定這些電子郵件的到期日。</span><span class="sxs-lookup"><span data-stu-id="c14ac-109">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="c14ac-110">透過 Office 365 高級郵件加密, 您可以為源于您組織的加密電子郵件建立多個範本。</span><span class="sxs-lookup"><span data-stu-id="c14ac-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="c14ac-111">您可以使用範本, 控制收件者存取使用者所傳送之郵件的時間長度。</span><span class="sxs-lookup"><span data-stu-id="c14ac-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="c14ac-112">當使用者收到到期日期設定的郵件時, 使用者會看到包裝電子郵件中的到期日。</span><span class="sxs-lookup"><span data-stu-id="c14ac-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="c14ac-113">如果使用者嘗試開啟過期的郵件, OME 入口網站中就會出現錯誤。</span><span class="sxs-lookup"><span data-stu-id="c14ac-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="c14ac-114">您只能將電子郵件的到期日期設定為外部收件者。</span><span class="sxs-lookup"><span data-stu-id="c14ac-114">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="c14ac-115">Office 365 高級郵件加密: 只要您套用自訂品牌, Office 365 就會將包裝套用至符合您套用範本的郵件流程規則的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c14ac-115">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="c14ac-116">此外, 如果您使用自訂品牌, 您只能使用到期時間。</span><span class="sxs-lookup"><span data-stu-id="c14ac-116">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="c14ac-117">使用 PowerShell 建立自訂品牌範本以強制郵件到期</span><span class="sxs-lookup"><span data-stu-id="c14ac-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="c14ac-118">使用在您的 Office 365 組織中具有全域系統管理員許可權的帳戶, 連線[至 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="c14ac-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="c14ac-119">執行 Set-omeconfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c14ac-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="c14ac-120">其中：</span><span class="sxs-lookup"><span data-stu-id="c14ac-120">Where:</span></span>

- <span data-ttu-id="c14ac-121">`Identity`是自訂範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="c14ac-121">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="c14ac-122">`ExternalMailExpiryInDays`識別收件者在到期之前可以保留郵件的天數。</span><span class="sxs-lookup"><span data-stu-id="c14ac-122">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="c14ac-123">您可以使用1–730天之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="c14ac-123">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="c14ac-124">有關 Office 365 高級郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c14ac-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="c14ac-125">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="c14ac-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="c14ac-126">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="c14ac-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="c14ac-127">郵件原則及符合性服務說明</span><span class="sxs-lookup"><span data-stu-id="c14ac-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
