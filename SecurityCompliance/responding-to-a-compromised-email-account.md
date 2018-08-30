---
title: 對於 Office 365 遭入侵電子郵件帳戶的回覆
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 了解如何將能辨識和回應 Office 365 的入侵的電子郵件帳戶
ms.openlocfilehash: ef97ecd3198234cf2c3d609f81a4a4a8af2c237e
ms.sourcegitcommit: 08f36794552e2213d0baf35180e47744d3e87fe4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2018
ms.locfileid: "23531876"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="74880-103">對於 Office 365 遭入侵電子郵件帳戶的回覆</span><span class="sxs-lookup"><span data-stu-id="74880-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="74880-104">**摘要**了解如何辨識與回應中 Office 365 的入侵的電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="74880-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="74880-105">什麼是 Office 365 危害電子郵件帳戶？</span><span class="sxs-lookup"><span data-stu-id="74880-105">What is a Compromised Email Account in Office 365?</span></span>
<span data-ttu-id="74880-p101">存取 Office 365 信箱、 資料及其他服務、 控制透過認證，例如使用者名稱及密碼或 PIN。當某人以外的預定使用者竊取所需的認證時，會視為竊的認證遭到洩漏。與這些攻擊者可以原始的使用者身分登入，並執行非法動作。使用竊的認證，請攻擊者可以存取使用者的 Office 365 信箱、 SharePoint 資料夾或檔案在使用者的 OneDrive。一個巨集指令一般呈現為原始使用者的電子郵件傳送給內部和外部組織的收件者攻擊。當攻擊者電子郵件電子郵件資料給外部收件者時，這會呼叫資料 exfiltration。</span><span class="sxs-lookup"><span data-stu-id="74880-p101">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="74880-112">徵狀之洩漏的 Office 365 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="74880-112">Symptoms of a Compromised Office 365 Email Account</span></span>
<span data-ttu-id="74880-p102">使用者可能會注意到並報告在 Office 365 信箱不尋常的活動。以下為部分常見徵狀：</span><span class="sxs-lookup"><span data-stu-id="74880-p102">Users may notice and report unusual activity in their Office 365 mailboxes. Here are some common symptoms:</span></span>
- <span data-ttu-id="74880-115">可疑的活動，例如遺失或已刪除的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="74880-115">Suspicious activity, such as missing or deleted emails.</span></span>
- <span data-ttu-id="74880-116">其他使用者可能會收到電子郵件從洩漏的帳戶沒有對應的寄件者**傳送的項目**] 資料夾中現有的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="74880-116">Other users may receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>
- <span data-ttu-id="74880-p103">未預期的使用者或系統管理員所建立的收件匣規則的目前狀態。這些規則可能會自動轉寄未知的地址的電子郵件或將其移至的**註解**、**垃圾郵件**或**RSS 訂閱**的資料夾。</span><span class="sxs-lookup"><span data-stu-id="74880-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>
- <span data-ttu-id="74880-119">全域通訊清單中，可能會變更使用者顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="74880-119">The users display name may be changed in the Global Address List.</span></span>
- <span data-ttu-id="74880-120">使用者的信箱會禁止傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="74880-120">The user's mailbox is blocked from sending email.</span></span>
- <span data-ttu-id="74880-121">在 Microsoft Outlook 或 Microsoft Outlook Web App 中的寄件備份或刪除的郵件資料夾包含一般駭客入侵-帳戶的郵件，例如"I 倫敦、 傳送 money 中前"。</span><span class="sxs-lookup"><span data-stu-id="74880-121">The Sent or Deleted Items folders in Microsoft Outlook or in Microsoft Outlook Web App contain common hacked-- account messages, such as "I'm stuck in London, send money."</span></span>
- <span data-ttu-id="74880-122">已更新不尋常的設定檔的變更，例如名稱、 電話號碼或的郵遞區號。</span><span class="sxs-lookup"><span data-stu-id="74880-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>
- <span data-ttu-id="74880-123">不尋常的認證的變更，例如多項的密碼變更是必要的。</span><span class="sxs-lookup"><span data-stu-id="74880-123">Unusual credential changes, such as multiple password changes are required.</span></span>
- <span data-ttu-id="74880-124">最近新增郵件轉寄。</span><span class="sxs-lookup"><span data-stu-id="74880-124">Mail forwarding was recently added.</span></span>
- <span data-ttu-id="74880-125">最近新增不尋常的簽章，例如假銀行業簽章或解決方法藥物簽章。</span><span class="sxs-lookup"><span data-stu-id="74880-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="74880-p104">如果使用者回報任何上述徵狀，您應該執行進一步調查。Office 365 安全性與規範中心和 Azure 入口網站提供工具來協助您調查的使用者帳戶的懷疑可能遭到洩漏活動。</span><span class="sxs-lookup"><span data-stu-id="74880-p104">If a user reports any of the above symptoms, you should perform further investigation. The Office 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>
- <span data-ttu-id="74880-p105">在 [安全性及規範中心-office 365 整合稽核記錄檢閱可疑帳戶的所有活動篩選的日期範圍跨越來自可疑活動發生為目前日期之前的結果。不要在搜尋期間篩選活動。</span><span class="sxs-lookup"><span data-stu-id="74880-p105">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>
- <span data-ttu-id="74880-p106">使用 Azure AD 登入記錄檔和其他 Azure AD 入口網站中可用的風險報告。檢查這些資料行中的值：</span><span class="sxs-lookup"><span data-stu-id="74880-p106">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal. Examine the values in these columns:</span></span>
    - <span data-ttu-id="74880-132">檢閱 IP 位址</span><span class="sxs-lookup"><span data-stu-id="74880-132">Review IP address</span></span>
    - <span data-ttu-id="74880-133">登入位置</span><span class="sxs-lookup"><span data-stu-id="74880-133">sign-in locations</span></span>
    - <span data-ttu-id="74880-134">登入時間</span><span class="sxs-lookup"><span data-stu-id="74880-134">sign-in times</span></span>
    - <span data-ttu-id="74880-135">登入成功或失敗</span><span class="sxs-lookup"><span data-stu-id="74880-135">sign-in success or failure</span></span>



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="74880-136">如何保護及還原至可疑的電子郵件函數危害 Office 365 帳戶和信箱</span><span class="sxs-lookup"><span data-stu-id="74880-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="74880-137">即使您已經下列存取您的帳戶後，攻擊者可能會有新增後門項目可讓攻擊者能夠繼續帳戶的控制權。</span><span class="sxs-lookup"><span data-stu-id="74880-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="74880-p107">您必須執行所有下列步驟來重新存取您的帳戶以確保不會繼續 hijacker 搭配成效更快控制您的帳戶。下列步驟可協助您移除 hijacker 可能已新增至您的帳戶的任何後門項目。您執行這些步驟之後，建議您執行以確定您的電腦不危害病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="74880-p107">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="74880-141">步驟 1 重設使用者密碼</span><span class="sxs-lookup"><span data-stu-id="74880-141">Step 1 Reset the user's password</span></span>
> [!WARNING]
> <span data-ttu-id="74880-142">當攻擊者仍有權存取信箱此時請不要預定使用者透過電子郵件傳送的新密碼。</span><span class="sxs-lookup"><span data-stu-id="74880-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="74880-143">請重設 Office 365 商務密碼執行某人的其他人的程序的[Admins： 重設 Office 365 商務密碼](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span><span class="sxs-lookup"><span data-stu-id="74880-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span></span>

<span data-ttu-id="74880-144">**注意：**</span><span class="sxs-lookup"><span data-stu-id="74880-144">**Notes:**</span></span>
- <span data-ttu-id="74880-145">請確定密碼強式而且它包含小寫字母、 至少一個數字及至少一個特殊字元。</span><span class="sxs-lookup"><span data-stu-id="74880-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span> 
- <span data-ttu-id="74880-p108">不要重複使用任何上次五個的密碼。即使密碼歷程記錄需求可讓您重複使用最近的密碼，您應該選取的攻擊者無法猜測的某個項目。</span><span class="sxs-lookup"><span data-stu-id="74880-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
- <span data-ttu-id="74880-148">如果您的內部識別同盟與 Office 365，您必須變更密碼內部，然後您必須通知您的危害的管理員。</span><span class="sxs-lookup"><span data-stu-id="74880-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="74880-149">步驟 2 移除可疑的電子郵件轉寄地址</span><span class="sxs-lookup"><span data-stu-id="74880-149">Step 2 Remove suspicious email forwarding addresses</span></span>
1. <span data-ttu-id="74880-150">開啟**Office 365 系統管理中心 > 作用中使用者**。</span><span class="sxs-lookup"><span data-stu-id="74880-150">Open the **Office 365 Admin Center > Active Users**.</span></span>
2. <span data-ttu-id="74880-151">尋找有問題的使用者帳戶並依序展開 [**郵件設定**。</span><span class="sxs-lookup"><span data-stu-id="74880-151">Find the user account in question and expand **Mail Settings**.</span></span>
3. <span data-ttu-id="74880-152">**電子郵件轉寄**，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="74880-152">For **Email forwarding**, click **Edit**.</span></span>
4. <span data-ttu-id="74880-153">移除任何可疑轉寄地址。</span><span class="sxs-lookup"><span data-stu-id="74880-153">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="74880-154">步驟 3 停用任何可疑的收件匣規則</span><span class="sxs-lookup"><span data-stu-id="74880-154">Step 3 Disable any suspicious inbox rules</span></span>
1. <span data-ttu-id="74880-155">登入使用者的信箱使用 Outlook Web App (OWA)。</span><span class="sxs-lookup"><span data-stu-id="74880-155">Sign in to the user's mailbox using Outlook Web App (OWA).</span></span>
2. <span data-ttu-id="74880-156">齒輪圖示上按一下 [並按一下 [**郵件**]。</span><span class="sxs-lookup"><span data-stu-id="74880-156">Click on the gear icon and click **Mail**.</span></span>
3. <span data-ttu-id="74880-157">按一下 [**收件匣及延伸的規則**並檢閱的規則。</span><span class="sxs-lookup"><span data-stu-id="74880-157">Click **Inbox and sweep rules** and review the rules.</span></span>
4. <span data-ttu-id="74880-158">停用或刪除可疑的規則。</span><span class="sxs-lookup"><span data-stu-id="74880-158">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="74880-159">步驟 4 解除使用者傳送郵件</span><span class="sxs-lookup"><span data-stu-id="74880-159">Step 4 Unblock the user from sending mail</span></span>
<span data-ttu-id="74880-160">如果可疑洩漏的信箱用以非法垃圾電子郵件傳送，很可能信箱已被禁止傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="74880-160">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>
1. <span data-ttu-id="74880-161">若要解除封鎖從傳送郵件的信箱，請遵循中[移除使用者、 網域或 IP 位址從封鎖清單之後傳送垃圾電子郵件](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )的程序。</span><span class="sxs-lookup"><span data-stu-id="74880-161">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="74880-162">步驟 5 選用： 封鎖從登入的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="74880-162">Step 5 Optional: Block the user account from signing-in</span></span>
> [!IMPORTANT]
> <span data-ttu-id="74880-163">您可以封鎖從登入直到您認為放心地重新啟用存取可疑入侵的帳戶。</span><span class="sxs-lookup"><span data-stu-id="74880-163">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="74880-164">移至 Office 365 系統管理員中心。</span><span class="sxs-lookup"><span data-stu-id="74880-164">Go to the Office 365 admin center.</span></span>
2. <span data-ttu-id="74880-165">在 Office 365 系統管理中心中，選取 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="74880-165">In the Office 365 admin center, select **Users**.</span></span>
3. <span data-ttu-id="74880-166">選取您要封鎖、 員工，然後選擇 [使用者] 窗格中的 [**登入狀態**] 旁的 [**編輯**</span><span class="sxs-lookup"><span data-stu-id="74880-166">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>
4. <span data-ttu-id="74880-167">在 [**登入狀態**] 窗格中，選擇 [**登入封鎖**，然後**儲存**。</span><span class="sxs-lookup"><span data-stu-id="74880-167">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span> 
5. <span data-ttu-id="74880-168">在 Office 365 系統管理中心，左下功能窗格中，依序展開 [**管理中心**並選取 [ **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="74880-168">In the Office 365 admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>
6. <span data-ttu-id="74880-169">在 Exchange 系統管理中心中，瀏覽至**收件者 > 信箱**。</span><span class="sxs-lookup"><span data-stu-id="74880-169">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>
7. <span data-ttu-id="74880-170">選取使用者、 使用者屬性] 頁面上的 [**行動裝置**，按一下 [**停用 Exchange ActivcSync**和**停用裝置的 OWA**和回答**皆**為兩者。</span><span class="sxs-lookup"><span data-stu-id="74880-170">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>
8. <span data-ttu-id="74880-171">[**電子郵件連線**、**停用**和答覆 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="74880-171">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span> 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="74880-172">步驟 6 選用： 從所有系統管理角色群組中移除可疑洩漏的帳戶</span><span class="sxs-lookup"><span data-stu-id="74880-172">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>
> [!NOTE]
> <span data-ttu-id="74880-173">保護帳戶之後可以還原系統管理角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="74880-173">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="74880-174">Office 365 系統管理中心以全域管理員帳戶登入並開啟 [**作用中使用者**。</span><span class="sxs-lookup"><span data-stu-id="74880-174">Sign in to the Office 365 Admin Center with a global administrator account and open **Active Users**.</span></span>
2. <span data-ttu-id="74880-175">尋找可疑危害帳戶及手動檢查是否有任何系統管理角色指派給帳戶。</span><span class="sxs-lookup"><span data-stu-id="74880-175">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>
3. <span data-ttu-id="74880-176">開啟 [**安全性與規範中心**]。</span><span class="sxs-lookup"><span data-stu-id="74880-176">Open the **Security & Compliance Center**.</span></span>
4. <span data-ttu-id="74880-177">按一下 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="74880-177">Click **Permissions**.</span></span>
5. <span data-ttu-id="74880-p109">手動檢閱查看如果可疑危害帳戶屬於其中的任何角色群組。 如果是： a 按一下角色群組並按一下 [**編輯角色群組**。 b.按一下 [**選擇成員**與**編輯**若要從角色群組移除使用者。</span><span class="sxs-lookup"><span data-stu-id="74880-p109">Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:  a. Click the role group and click **Edit Role Group**.  b. Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>
6. <span data-ttu-id="74880-183">開啟**Exchange 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="74880-183">Open the **Exchange Admin Center**</span></span>
7. <span data-ttu-id="74880-184">按一下 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="74880-184">Click **Permissions**.</span></span>
8. <span data-ttu-id="74880-p110">手動檢閱查看如果可疑危害帳戶屬於其中的任何角色群組。如果是： a 按一下角色群組並按一下 [**編輯**]。 b.從角色群組移除使用者使用 [**成員**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="74880-p110">Manually review the role groups to see if the suspected compromised account is a member of any of them. If it is:  a. Click the role group and click **Edit**.  b. Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="74880-190">步驟 7 選用： 其他預防步驟</span><span class="sxs-lookup"><span data-stu-id="74880-190">Step 7 Optional: Additional precautionary steps</span></span>
1. <span data-ttu-id="74880-p111">請確定您確認您已傳送的項目。您必須通知您的帳戶已危害的連絡人清單上的人員。攻擊者可能會有系統要求他們的 money、 詐騙、 例如擱淺在不同的國家/地區及所需 money，或攻擊者可能會將傳送給他們也劫持其電腦病毒。</span><span class="sxs-lookup"><span data-stu-id="74880-p111">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>
2. <span data-ttu-id="74880-p112">任何其他服務為其替代電子郵件帳戶已遭洩露用此 Exchange 帳戶。首先，執行下列步驟在 Office 365 訂閱，然後為其他帳戶執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="74880-p112">Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>
3. <span data-ttu-id="74880-196">請確定您的連絡人資訊，例如電話號碼和地址正確。</span><span class="sxs-lookup"><span data-stu-id="74880-196">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="74880-197">安全 like cybersecurity 專業人員的 Office 365</span><span class="sxs-lookup"><span data-stu-id="74880-197">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="74880-p113">您的 Office 365 訂閱隨附一組功能強大的安全性功能可用來保護您的資料與您的使用者。 使用[Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法保護您的 Office 365 租用戶。</span><span class="sxs-lookup"><span data-stu-id="74880-p113">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="74880-p114">若要完成工作前 30 天的工作。 這些包含立即影響且為 low 影響您的使用者。</span><span class="sxs-lookup"><span data-stu-id="74880-p114">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="74880-p115">若要完成 90 天的工作。這些需要規劃和實作但大幅改善了安全性狀態的更多時間。</span><span class="sxs-lookup"><span data-stu-id="74880-p115">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="74880-p116">超過 90 天。您在第一個 90 天工作建立這些增強功能。</span><span class="sxs-lookup"><span data-stu-id="74880-p116">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="74880-206">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="74880-206">See also:</span></span>
- [<span data-ttu-id="74880-207">Office 365 的安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="74880-207">Security best practices for Office 365</span></span>](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [<span data-ttu-id="74880-208">偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊</span><span class="sxs-lookup"><span data-stu-id="74880-208">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
- [<span data-ttu-id="74880-209">網際網路犯罪抱怨中心</span><span class="sxs-lookup"><span data-stu-id="74880-209">Internet Crime Complaint Center</span></span>](http://www.ic3.gov/preventiontips.aspx)
- [<span data-ttu-id="74880-210">美國證券業 and Exchange 委員會"網路釣魚"詐騙</span><span class="sxs-lookup"><span data-stu-id="74880-210">Securities and Exchange Commission - "Phishing" Fraud</span></span>](http://www.sec.gov/investor/pubs/phishing.htm)
