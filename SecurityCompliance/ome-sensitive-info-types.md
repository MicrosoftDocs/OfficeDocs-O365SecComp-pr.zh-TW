---
title: 使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要： Office 365 敏感資訊類型的郵件加密原則。
ms.openlocfilehash: 44966303ec7c58fdd82f733e1922073de848cf73
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834832"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="543d8-103">使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="543d8-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="543d8-104">您可以使用 [Exchange 郵件流程規則] 或 [Office 365 資料外洩防護 (DLP) 來建立敏感資訊類型原則與 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="543d8-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="543d8-105">若要建立 Exchange 郵件流程規則，您可以使用 Exchange 系統管理中心 (EAC) 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="543d8-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="543d8-106">若要建立原則在 EAC 中使用郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="543d8-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="543d8-107">登入 Exchange 系統管理中心 (EAC)，並移至 [**郵件流程** > **規則**。</span><span class="sxs-lookup"><span data-stu-id="543d8-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="543d8-108">在 [規則] 頁面上建立適用於 Office 365 郵件加密的規則。</span><span class="sxs-lookup"><span data-stu-id="543d8-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="543d8-109">您可以建立規則，例如目前狀態的特定關鍵字或郵件或附件中的敏感資訊類型的條件為基礎。</span><span class="sxs-lookup"><span data-stu-id="543d8-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="543d8-110">若要建立原則藉由使用 PowerShell 中的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="543d8-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="543d8-111">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段，連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="543d8-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="543d8-112">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="543d8-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="543d8-113">使用 Set-irmconfiguration 和 New-transportrule 指令程式來建立原則。</span><span class="sxs-lookup"><span data-stu-id="543d8-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="543d8-114">使用 PowerShell 建立範例郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="543d8-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="543d8-115">若要建立 Exchange 郵件流程規則，會自動加密傳送與組織外部的電子郵件的 PowerShell 中執行下列命令*僅加密*原則如果電子郵件或其附件包含下列的敏感資訊類型：</span><span class="sxs-lookup"><span data-stu-id="543d8-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="543d8-116">阿拉巴馬州銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="543d8-116">ABA routing number</span></span>
- <span data-ttu-id="543d8-117">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="543d8-117">Credit card Number</span></span>
- <span data-ttu-id="543d8-118">藥物執法機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="543d8-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="543d8-119">美國 / 英國</span><span class="sxs-lookup"><span data-stu-id="543d8-119">U.S. / U.K.</span></span> <span data-ttu-id="543d8-120">護照號碼</span><span class="sxs-lookup"><span data-stu-id="543d8-120">passport number</span></span>
- <span data-ttu-id="543d8-121">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="543d8-121">U.S. bank account number</span></span>
- <span data-ttu-id="543d8-122">美國個別 Taxpayer 識別號碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="543d8-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="543d8-123">美國社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="543d8-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="543d8-124">收件者存取附件的方式</span><span class="sxs-lookup"><span data-stu-id="543d8-124">How recipients access attachments</span></span>

<span data-ttu-id="543d8-125">Office 365 加密郵件之後，收件者有不受限制存取附件當他們存取，並開啟其加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="543d8-125">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="543d8-126">若要準備進行這項變更</span><span class="sxs-lookup"><span data-stu-id="543d8-126">To prepare for this change</span></span>

<span data-ttu-id="543d8-127">若要更新任何適用的使用者文件和訓練資料準備，這項變更您組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="543d8-127">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="543d8-128">視您的使用者與共用這些 Office 365 郵件加密的資源：</span><span class="sxs-lookup"><span data-stu-id="543d8-128">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="543d8-129">傳送、 檢視和回覆加密郵件的電腦版 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="543d8-129">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="543d8-130">Office 365 基本版影片： Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="543d8-130">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="543d8-131">稽核記錄中檢視這些變更</span><span class="sxs-lookup"><span data-stu-id="543d8-131">View these changes in the Audit log</span></span>

<span data-ttu-id="543d8-132">Office 365 稽核這項活動，並可供 Office 365 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="543d8-132">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="543d8-133">這項操作是 'New-transportrule' 和程式碼片段範例稽核項目，從 [稽核記錄中搜尋的安全性 & 合規性中心的低於：</span><span class="sxs-lookup"><span data-stu-id="543d8-133">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="543d8-134">若要停用或自訂的敏感資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="543d8-134">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="543d8-135">一旦您已經建立 Exchange 郵件流程規則，您可以[停用或編輯規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**在 Exchange 系統管理中心 (EAC) 和停用的規則 「*加密外寄機密電子郵件 （超出方塊規則）*」。</span><span class="sxs-lookup"><span data-stu-id="543d8-135">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
