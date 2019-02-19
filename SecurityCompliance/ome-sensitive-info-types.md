---
title: 敏感資訊的 office 365 郵件加密原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： Office 365 郵件加密的敏感資訊類型現在可原則。
ms.openlocfilehash: e2a72ee85ca65a2fe8ae1543979b51915ff0a88f
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696197"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="b51c7-103">敏感資訊的 office 365 郵件加密原則</span><span class="sxs-lookup"><span data-stu-id="b51c7-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="b51c7-p101">更新 (1/30/19)： 在 10 2018年我們是否正常運作與客戶了解是否我們可以簡化保護自動加密機密根據特定的敏感資訊類型的電子郵件的一小部分範例。我們根據此範例從正數意見反應，決定年 12 月 2018年中展開 [更多樣化的設定檔的承租人。之後通訊後續選取承租人聯播 （英文） 延展，我們接聽您的意見反應及取決於較複雜的環境具有客戶想要更謹慎實作規則與因此我們已調整我們計劃。</span><span class="sxs-lookup"><span data-stu-id="b51c7-p101">Update (1/30/19): In October 2018, we worked with a small sample of customers to understand if we can simplify protection by automatically encrypting sensitive emails based on certain sensitive information types. Based on positive feedback from this sample, we decided to expand to a more diverse profile of tenants in December 2018. After communicating the next roll-out to select tenants, we listened to your feedback and determined that customers with more complex environments wanted to implement the rules more cautiously, and we are therefore adjusting our plans.</span></span>

<span data-ttu-id="b51c7-p102">如果貴組織所選 roll 延展開始 2019 年 1 月 15，我們會不導入自動原則。而我們所上如何即可完成 roll 出自己提供本文中的指示。繼續閱讀以了解如何。</span><span class="sxs-lookup"><span data-stu-id="b51c7-p102">If your organization was selected for the roll-out starting January 15, 2019, we will not roll out the automatic policy. Instead, we are providing instructions in this article on how you can complete the roll-out yourselves. Keep reading to find out how.</span></span>

||
|:-----|
|<span data-ttu-id="b51c7-p103">本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員和 ITPros 的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="b51c7-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a><span data-ttu-id="b51c7-113">如何建立您的租用戶的敏感資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="b51c7-113">How to create the sensitive information type policy for your tenant</span></span>

<span data-ttu-id="b51c7-p104">您可以使用 Exchange 郵件流程規則或 Office 365 資料遺失防護 (DLP) 若要建立的敏感資訊類型原則。若要建立您可以使用 Exchange 系統管理中心 (EAC) 或 PowerShell Exchange 郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="b51c7-p104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create the sensitive information type policy. To create an Exchange mail flow rule you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="b51c7-116">在 EAC 中使用的郵件流程建立原則規則</span><span class="sxs-lookup"><span data-stu-id="b51c7-116">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="b51c7-p105">登入 Exchange 系統管理中心 (EAC)，並移至 [**郵件流程** > **規則**。那里，建立適用於 Office 365 郵件加密條件如顯示狀態的特定關鍵字或訊息或附件中的敏感資訊類型為基礎的規則。</span><span class="sxs-lookup"><span data-stu-id="b51c7-p105">Sign-in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**. There, create a rule that applies Office 365 Message Encryption based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="b51c7-119">若要使用 PowerShell 中的郵件流程規則來建立原則</span><span class="sxs-lookup"><span data-stu-id="b51c7-119">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="b51c7-p106">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段並連線至 Exchange Online。指示，請參閱[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell)。使用 Set-irmconfiguration 和新增 TransporRule cmdlet 來建立原則。</span><span class="sxs-lookup"><span data-stu-id="b51c7-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Use the Set-IRMConfiguration and New-TransporRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="b51c7-123">使用 PowerShell 建立範例郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="b51c7-123">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="b51c7-124">執行下列 PowerShell 中的命令會建立 Exchange 郵件流程規則會自動加密不必與組織外部的電子郵件*僅限加密的*電子郵件或其附件包含下列機密的原則資訊類型：</span><span class="sxs-lookup"><span data-stu-id="b51c7-124">Running the following commands in PowerShell create an Exchange mail flow rule that automatically encrypts emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="b51c7-125">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="b51c7-125">ABA routing number</span></span>
- <span data-ttu-id="b51c7-126">信用卡號</span><span class="sxs-lookup"><span data-stu-id="b51c7-126">Credit card Number</span></span>
- <span data-ttu-id="b51c7-127">藥物強制執行機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="b51c7-127">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="b51c7-p107">美國 / 英國護照號碼</span><span class="sxs-lookup"><span data-stu-id="b51c7-p107">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="b51c7-130">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="b51c7-130">U.S. bank account number</span></span>
- <span data-ttu-id="b51c7-131">美國個別納稅人身分識別碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="b51c7-131">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="b51c7-132">美國社會安全編號 (SSN)</span><span class="sxs-lookup"><span data-stu-id="b51c7-132">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="b51c7-133">收件者如何存取附件</span><span class="sxs-lookup"><span data-stu-id="b51c7-133">How recipients access attachments</span></span>

<span data-ttu-id="b51c7-134">之後，加密郵件的收件者會有未限制存取附件之後存取並開啟加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b51c7-134">Once a message is encrypted, recipients will have unrestricted access to attachments once they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="b51c7-135">若要準備進行這項變更</span><span class="sxs-lookup"><span data-stu-id="b51c7-135">To prepare for this change</span></span>

<span data-ttu-id="b51c7-p108">若要更新任何適用的使用者文件及準備，這項變更組織中的人員的訓練教材。與視使用者共用這些 Office 365 郵件加密的資源：</span><span class="sxs-lookup"><span data-stu-id="b51c7-p108">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="b51c7-138">傳送、 檢視和回覆加密郵件的電腦在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="b51c7-138">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="b51c7-139">Office 365 Essentials 影片： Office 郵件加密</span><span class="sxs-lookup"><span data-stu-id="b51c7-139">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="b51c7-140">檢視稽核記錄中的這些變更</span><span class="sxs-lookup"><span data-stu-id="b51c7-140">View these changes in the Audit log</span></span>

<span data-ttu-id="b51c7-p109">此活動您可以稽核並可供 Office 365 系統管理員。作業是 'New-transportrule' 和程式碼片段的稽核記錄檔中搜尋的安全性 & 規範中心範例稽核項目是下方：</span><span class="sxs-lookup"><span data-stu-id="b51c7-p109">This activity is audited and is available to Office 365 administrators. The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="b51c7-143">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"，"RecordType": 1、"ResultStatus":"True"、"UserKey":"Microsoft 運算子"，"UserType": 3、 [版本]： 1、"工作量":"Exchange"、"ClientIP":"123.456.147.68:17584"，"ObjectId"：""，"UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"的組織"，"值":"123456 221 d-12346"{"Name":"ApplyRightsProtectionTemplate"，"值":"加密"}，{"Name":"Name"，"值":"加密外寄機密電子郵件 （不在] 方塊中的規則）"}，{"Name":"MessageContainsDataClassifications"...]等。*</span><span class="sxs-lookup"><span data-stu-id="b51c7-143">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span> |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="b51c7-144">若要停用或自訂的敏感資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="b51c7-144">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="b51c7-145">一旦您已經建立 Exchange 郵件流程規則，您可以[停用或編輯的規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**中 Exchange admin center (EAC) 和停用規則"*加密外寄機密電子郵件 （不在] 方塊中的規則）*"。</span><span class="sxs-lookup"><span data-stu-id="b51c7-145">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
