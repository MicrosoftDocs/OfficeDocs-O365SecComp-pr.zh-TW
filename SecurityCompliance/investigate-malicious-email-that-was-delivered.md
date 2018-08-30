---
title: 尋找與調查惡意的電子郵件已傳遞 （Office 365 威脅智慧）
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: 了解如何使用威脅智慧尋找及調查惡意的電子郵件。
ms.openlocfilehash: 9d63bd69e11bca4bc76fa6d6d00a429ed1aac508
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526586"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a><span data-ttu-id="6714c-103">尋找與調查惡意的電子郵件已傳遞 （Office 365 威脅智慧）</span><span class="sxs-lookup"><span data-stu-id="6714c-103">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="6714c-p101">[Office 365 威脅智慧](office-365-ti.md)可讓您調查放在風險的使用者，並採取動作來保護您的組織的活動。例如，如果您組織的安全性小組的一部分，可以尋找及調查可疑的電子郵件已傳遞給您的使用者。您可以使用[瀏覽器威脅](get-started-with-ti.md#threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="6714c-p101">[Office 365 Threat Intelligence](office-365-ti.md) enables you to investigate activities that put your users at risk and take action to protect your organization. For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users. You can do this by using [Threat Explorer](get-started-with-ti.md#threat-explorer).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6714c-p102">在 Office 365 企業版 E5 中使用 office 365 威脅智慧。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買 Office 365 威脅智慧。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[購買或編輯企業版的 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="6714c-p102">Office 365 Threat Intelligence is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Threat Intelligence can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="6714c-110">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="6714c-110">Before you begin...</span></span>

<span data-ttu-id="6714c-111">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="6714c-111">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="6714c-112">您的組織具有[Office 365 威脅智慧](office-365-ti.md)及[指派給 Office 365 中的商務使用者的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="6714c-112">Your organization has [Office 365 Threat Intelligence](office-365-ti.md) and [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
- <span data-ttu-id="6714c-113">[Office 365 稽核記錄](turn-audit-log-search-on-or-off.md)會開啟您的組織。</span><span class="sxs-lookup"><span data-stu-id="6714c-113">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="6714c-p103">您的組織已定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚等等的原則。請參閱[威脅管理 Office 365 安全性&amp;規範中心](threat-management.md)。</span><span class="sxs-lookup"><span data-stu-id="6714c-p103">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on. See [Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md).</span></span>
    
- <span data-ttu-id="6714c-p104">您是 Office 365 全域管理員，或您有安全性管理員或安全性指派搜尋及清除角色&amp;規範中心。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6714c-p104">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="6714c-118">處理可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="6714c-118">Dealing with suspicious emails</span></span>

<span data-ttu-id="6714c-p105">惡意攻擊者可能會傳送郵件給使用者，嘗試和 phish 其認證及存取貴公司機密資料時會 ！若要避免此問題，您應該使用 Office 365，包括 Exchange Online Protection 和進階威脅保護所提供的威脅保護服務。但有當攻擊者無法將郵件傳送給您包含 URL 的使用者，並只更新版本 URL 這時惡意內容 （惡意程式碼等） 的次數。或者，您可能會發現太晚在組織中的使用者已遭洩露，及攻擊時該使用者已危害，用來傳送電子郵件給其他使用者在您的公司該帳戶。清除這兩種案例的一部分，您可能會想要移除使用者收件匣中的電子郵件訊息。像這些情況，您可以運用尋找及移除這些電子郵件訊息的威脅 Explorer ！</span><span class="sxs-lookup"><span data-stu-id="6714c-p105">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets! In order to prevent this, you should use the threat protection services offered by Office 365, including Exchange Online Protection and Advanced Threat Protection. However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.). Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company. As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes. In situations like these, you can leverage Threat Explorer to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="6714c-125">尋找並刪除可疑的電子郵件已傳遞</span><span class="sxs-lookup"><span data-stu-id="6714c-125">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="6714c-p106">[威脅瀏覽器](get-started-with-ti.md#threat-explorer)（也稱為 Explorer），是功能強大的適合多種目的，例如尋找和刪除郵件、 識別惡意的電子郵件寄件者的 IP 位址或開始進一步調查事件。下列程序著重於使用總管來尋找並從收件者的信箱中刪除惡意的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6714c-p106">[Threat Explorer](get-started-with-ti.md#threat-explorer) (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation. The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="6714c-p107">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。這會引導您安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="6714c-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="6714c-130">在左導覽列中，選擇 [ **Threat management** \> **瀏覽器**。</span><span class="sxs-lookup"><span data-stu-id="6714c-130">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="6714c-131">在 [檢視] 功能表中選擇 [**所有電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="6714c-131">In the View menu, choose **All email**.</span></span>
    
    ![使用 [檢視] 功能表選擇電子郵件及內容的報表](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. <span data-ttu-id="6714c-133">請注意會出現在報表，例如**已傳遞**、**未知**，或**傳遞至垃圾郵件**標籤。</span><span class="sxs-lookup"><span data-stu-id="6714c-133">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span>
    
    ![顯示所有的電子郵件資料的威脅瀏覽器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
  
    <span data-ttu-id="6714c-135">（根據對您的組織的電子郵件訊息所採取的動作，您可能會看到其他標籤，例如**封鎖**或**取代**）。</span><span class="sxs-lookup"><span data-stu-id="6714c-135">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="6714c-136">在報表中，選擇 [檢視使用者的收件匣中的結束電子郵件**已傳遞**。</span><span class="sxs-lookup"><span data-stu-id="6714c-136">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span> 
    
    ![按一下 「 傳遞至垃圾郵件 」 從檢視中移除該資料](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. <span data-ttu-id="6714c-138">圖表下方檢閱**電子郵件**清單圖表下方。</span><span class="sxs-lookup"><span data-stu-id="6714c-138">Below the chart, review the **Email** list below the chart.</span></span> 
    
    ![圖表下方檢視所偵測到的電子郵件的清單](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. <span data-ttu-id="6714c-p108">在清單中，選擇檢視該電子郵件訊息的更多詳細資料的項目。例如，您可以按一下 [檢視資訊寄件者、 收件者、 附件及其他類似的電子郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="6714c-p108">In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span>
    
    ![您可以檢視項目，包括詳細資料和任何附件的其他資訊](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="6714c-143">之後檢視的電子郵件的相關資訊，請啟動 **+ 動作**清單中選取一或多個項目。</span><span class="sxs-lookup"><span data-stu-id="6714c-143">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="6714c-p109">使用 [ **+ 動作**] 清單中套用的動作，例如**移至刪除**的項目。這會從收件者的信箱中刪除所選的郵件。</span><span class="sxs-lookup"><span data-stu-id="6714c-p109">Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.</span></span> 
    
    ![當您選取一或多個電子郵件訊息時，您可以選擇從數個可用的動作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a><span data-ttu-id="6714c-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="6714c-147">Related topics</span></span>

[<span data-ttu-id="6714c-148">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="6714c-148">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="6714c-149">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="6714c-149">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="6714c-150">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="6714c-150">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

