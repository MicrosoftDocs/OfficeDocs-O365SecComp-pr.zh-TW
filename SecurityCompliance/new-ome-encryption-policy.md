---
title: 新的 Office 365 郵件加密原則敏感資訊
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 新 Office 365 郵件加密的原則機密資訊。
ms.openlocfilehash: d0ec5ef22da4742c8cd3d1c56d27b505911fca58
ms.sourcegitcommit: af8e503f20588e8fb992fc5b95d571b7bd89b15d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2018
ms.locfileid: "27371261"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="c50ba-103">新的 Office 365 郵件加密原則敏感資訊</span><span class="sxs-lookup"><span data-stu-id="c50ba-103">New Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="c50ba-p101">我們會建立新的自動原則將會套用至所有電子郵件包含敏感資訊及的寄往組織外部的 Office 365 郵件加密的 Office 365 租用戶中。這個新的 Exchange 郵件流程規則將會自動建立 Office 365 租用戶中使預設會保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="c50ba-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="how-will-this-work"></a><span data-ttu-id="c50ba-106">如何將這項工作？</span><span class="sxs-lookup"><span data-stu-id="c50ba-106">How will this work?</span></span>

<span data-ttu-id="c50ba-p102">您的組織會收到通知在 Office 365 郵件內通知您將在您的租用戶中建立此自動的原則所在的日期。會提供您至少 30 天的通知，您還必須加入確認程序擴充的選項。您可能想可能會選擇退出分析的藍本是如果您有機密類型已掃描的第 3 廠商資料外洩防護解決方案。</span><span class="sxs-lookup"><span data-stu-id="c50ba-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types.</span></span>

## <a name="new-policy-details"></a><span data-ttu-id="c50ba-109">新原則的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c50ba-109">New policy details</span></span>

<span data-ttu-id="c50ba-110">將會自動加密不必與組織外部的電子郵件在組織中建立新的 Exchange 郵件流程規則*只加密*如果它們包含以下敏感資訊類型的原則：</span><span class="sxs-lookup"><span data-stu-id="c50ba-110">A new Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if they contain the following sensitive information types:</span></span>

- <span data-ttu-id="c50ba-111">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="c50ba-111">ABA routing number</span></span>
- <span data-ttu-id="c50ba-112">信用卡號</span><span class="sxs-lookup"><span data-stu-id="c50ba-112">Credit card Number</span></span>
- <span data-ttu-id="c50ba-113">藥物強制執行機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="c50ba-113">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="c50ba-p103">美國 / 英國護照號碼</span><span class="sxs-lookup"><span data-stu-id="c50ba-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="c50ba-116">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="c50ba-116">U.S. bank account number</span></span>
- <span data-ttu-id="c50ba-117">美國個別納稅人身分識別碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="c50ba-117">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="c50ba-118">美國社會安全編號 (SSN)</span><span class="sxs-lookup"><span data-stu-id="c50ba-118">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="c50ba-119">完全機密類型依您組織的地區設定而異和會傳達給訊息中心通知中。</span><span class="sxs-lookup"><span data-stu-id="c50ba-119">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="c50ba-120">我需要如何準備，這項變更？</span><span class="sxs-lookup"><span data-stu-id="c50ba-120">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="c50ba-p104">您沒有更新或修改這個新的變更之前的任何現有 Office 365 組態設定。不過，您可能要更新任何適用的使用者文件及準備，這項變更組織中的人員的訓練教材。與視使用者共用這些 Office 365 郵件加密的資源：</span><span class="sxs-lookup"><span data-stu-id="c50ba-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="c50ba-124">傳送、 檢視和回覆加密郵件的電腦在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="c50ba-124">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="c50ba-125">Office 365 Essentials 影片： Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="c50ba-125">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="c50ba-126">此變更會表示在稽核記錄檔的方式？</span><span class="sxs-lookup"><span data-stu-id="c50ba-126">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="c50ba-p105">此活動您可以稽核和客戶使用。 作業是 'New-transportrule' 和程式碼片段的稽核記錄檔中搜尋的安全性與規範中心範例稽核項目是下方：</span><span class="sxs-lookup"><span data-stu-id="c50ba-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="c50ba-129">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"，"RecordType": 1、"ResultStatus":"True"、"UserKey":"Microsoft 運算子"，"UserType": 3、 [版本]： 1、"工作量":"Exchange"、"ClientIP":"123.456.147.68:17584"，"ObjectId"：""，"UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"的組織"，"值":"123456 221 d-12346"{"Name":"ApplyRightsProtectionTemplate"，"值":"加密"}，{"Name":"Name"，"值":"加密外寄機密電子郵件 （不在] 方塊中的規則）"}，{"Name":"MessageContainsDataClassifications"等。*</span><span class="sxs-lookup"><span data-stu-id="c50ba-129">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="c50ba-130">如何我選擇延展？</span><span class="sxs-lookup"><span data-stu-id="c50ba-130">How do I opt-out?</span></span>

<span data-ttu-id="c50ba-131">如果您想要選擇加入延展這項變更，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c50ba-131">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="c50ba-132">以全域管理員角色的使用者身分連線至[Exchange Online PowerShell](https://aka.ms/exopowershell) 。</span><span class="sxs-lookup"><span data-stu-id="c50ba-132">Connect to [Exchange Online PowerShell](https://aka.ms/exopowershell) as a user with the global administrator role.</span></span>
2.  <span data-ttu-id="c50ba-133">在驗證後執行下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="c50ba-133">Run the following code after authenticating:</span></span>

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a><span data-ttu-id="c50ba-134">如何停用自動原則？</span><span class="sxs-lookup"><span data-stu-id="c50ba-134">How do I disable the automatic policy?</span></span>

<span data-ttu-id="c50ba-135">如果您沒有選擇出這項變更與 Exchange 郵件規則已建立，您可以[停用規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**中 Exchange admin center (EAC) 並停用"*輸出加密的規則機密的電子郵件 （不在] 方塊中的規則）*"。</span><span class="sxs-lookup"><span data-stu-id="c50ba-135">If you didn’t opt-out of this change and the Exchange mail rule has already been created, you can [disable the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
