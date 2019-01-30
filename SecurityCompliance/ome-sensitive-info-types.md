---
title: 新的 Office 365 郵件加密原則敏感資訊
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/16/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 自動套用至所有的承租人啟用的敏感資訊類型的 Office 365 郵件加密原則。
ms.openlocfilehash: f83bf0fe572586b3becf2dd53395e611bdaaea24
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614377"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="1aca1-103">敏感資訊的 office 365 郵件加密原則</span><span class="sxs-lookup"><span data-stu-id="1aca1-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="1aca1-p101">選取 [群組依據其組織大小與複雜性郵件流程的承租人我們執行的動作將會套用至含有機密特定類型的電子郵件的 Office 365 郵件加密的 Office 365 租用戶中的新自動原則低速 roll 出資訊。我們要測試此承租人一小群具有。此原則將不會導所有組織及考量等組織大小與複雜性郵件流程將可用來判斷此 roll 延展的資格。如果您的組織已選取此聯播 （英文） 時，您會收到通知在 Office 365 郵件內通知您在其建立此自動原則和至少 30 天的通知] 與 [加入確認程序擴充選項指定的日期。如果您不想要建立此原則的 Microsoft 等待，但想要這麼自己，您可以建立使用 Exchange Mail Flow 規則此自動原則。</span><span class="sxs-lookup"><span data-stu-id="1aca1-p101">For a select group of tenants, based on their organization size and complexity of mail flow, we are doing a slow roll-out of a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to emails that contain certain types of sensitive information. We are testing this with a small group of tenants. This policy will not be rolled out to all organizations and considerations such as organization size and complexity of mail flow will be used to determine the eligibility for this roll-out. If your organization is selected for this roll-out, you will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created and you will be given at least a 30-day notice and the option to opt-out. If you don't want to wait for Microsoft to create this policy and would like to do so yourselves, you can create this automatic policy using Exchange Mail Flow rules.</span></span>

## <a name="when-to-expect-the-update-for-your-tenant"></a><span data-ttu-id="1aca1-107">預期更新您的租用戶的時機</span><span class="sxs-lookup"><span data-stu-id="1aca1-107">When to expect the update for your tenant</span></span>

<span data-ttu-id="1aca1-p102">您的組織會收到通知在 Office 365 郵件內通知您將在您的租用戶中建立此自動的原則所在的日期。會提供您至少 30 天的通知，您還必須加入確認程序擴充的選項。您可能想可能會選擇退出分析的藍本是如果您有機密類型已掃描的第 3 廠商資料外洩防護解決方案。更多詳細資料如何選擇延展可用本文稍後的。</span><span class="sxs-lookup"><span data-stu-id="1aca1-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types. More details on how to opt-out are available later in this article.</span></span>

## <a name="sensitive-information-type-policy-details"></a><span data-ttu-id="1aca1-111">敏感資訊類型原則的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="1aca1-111">Sensitive information type policy details</span></span>

<span data-ttu-id="1aca1-112">Exchange 郵件流程規則將會自動加密不必與組織外部的電子郵件在組織中建立*僅限加密的*電子郵件或其附件包含以下敏感資訊類型的原則：</span><span class="sxs-lookup"><span data-stu-id="1aca1-112">An Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="1aca1-113">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="1aca1-113">ABA routing number</span></span>
- <span data-ttu-id="1aca1-114">信用卡號</span><span class="sxs-lookup"><span data-stu-id="1aca1-114">Credit card Number</span></span>
- <span data-ttu-id="1aca1-115">藥物強制執行機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="1aca1-115">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="1aca1-p103">美國 / 英國護照號碼</span><span class="sxs-lookup"><span data-stu-id="1aca1-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="1aca1-118">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="1aca1-118">U.S. bank account number</span></span>
- <span data-ttu-id="1aca1-119">美國個別納稅人身分識別碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="1aca1-119">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="1aca1-120">美國社會安全編號 (SSN)</span><span class="sxs-lookup"><span data-stu-id="1aca1-120">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="1aca1-121">完全機密類型依您組織的地區設定而異和會傳達給訊息中心通知中。</span><span class="sxs-lookup"><span data-stu-id="1aca1-121">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="1aca1-122">我需要如何準備，這項變更？</span><span class="sxs-lookup"><span data-stu-id="1aca1-122">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="1aca1-p104">您沒有更新或修改這個新的變更之前的任何現有 Office 365 組態設定。不過，您可能要更新任何適用的使用者文件及準備，這項變更組織中的人員的訓練教材。與視使用者共用這些 Office 365 郵件加密的資源：</span><span class="sxs-lookup"><span data-stu-id="1aca1-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="1aca1-126">傳送、 檢視和回覆加密郵件的電腦在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="1aca1-126">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="1aca1-127">Office 365 Essentials 影片： Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="1aca1-127">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="1aca1-128">此變更會表示在稽核記錄檔的方式？</span><span class="sxs-lookup"><span data-stu-id="1aca1-128">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="1aca1-p105">此活動您可以稽核和客戶使用。 作業是 'New-transportrule' 和程式碼片段的稽核記錄檔中搜尋的安全性 & 規範中心範例稽核項目是下方：</span><span class="sxs-lookup"><span data-stu-id="1aca1-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="1aca1-131">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"，"RecordType": 1、"ResultStatus":"True"、"UserKey":"Microsoft 運算子"，"UserType": 3、 [版本]： 1、"工作量":"Exchange"、"ClientIP":"123.456.147.68:17584"，"ObjectId"：""，"UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"的組織"，"值":"123456 221 d-12346"{"Name":"ApplyRightsProtectionTemplate"，"值":"加密"}，{"Name":"Name"，"值":"加密外寄機密電子郵件 （不在] 方塊中的規則）"}，{"Name":"MessageContainsDataClassifications"等。*</span><span class="sxs-lookup"><span data-stu-id="1aca1-131">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="1aca1-132">如何我選擇延展？</span><span class="sxs-lookup"><span data-stu-id="1aca1-132">How do I opt-out?</span></span>

<span data-ttu-id="1aca1-133">如果您想要選擇加入延展這項變更，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1aca1-133">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="1aca1-p106">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段並連線至 Exchange Online。指示，請參閱[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="1aca1-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>
2. <span data-ttu-id="1aca1-136">執行 Set-irmconfiguration 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1aca1-136">Run the Set-IRMConfiguration cmdlet as follows:</span></span>

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-or-customize-the-automatic-policy"></a><span data-ttu-id="1aca1-137">如何停用或自訂自動原則？</span><span class="sxs-lookup"><span data-stu-id="1aca1-137">How do I disable or customize the automatic policy?</span></span>

<span data-ttu-id="1aca1-138">如果您沒有選擇出這項變更與 Exchange 郵件流程規則已建立，您可以[停用或編輯的規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**中 Exchange admin center (EAC) 和停用"*加密的規則輸出機密電子郵件 （不在] 方塊中的規則）*"。</span><span class="sxs-lookup"><span data-stu-id="1aca1-138">If you didn’t opt-out of this change and the Exchange mail flow rule has already been created, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
