---
title: 如何避免 Office 365 發生誤判
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: 了解如何避免 Office 365 誤判，並篩選出真正的電子郵件與垃圾郵件。
ms.openlocfilehash: 10d71519da1639073122b0a89652753f466f6dbe
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341474"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a><span data-ttu-id="a0764-103">如何在 Office 365 中防止實際電子郵件被標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="a0764-103">How to prevent real email from being marked as spam in Office 365</span></span>

 <span data-ttu-id="a0764-104">**您的實際電子郵件將在 Office 365 中被標示為垃圾郵件嗎？請執行此動作。**</span><span class="sxs-lookup"><span data-stu-id="a0764-104">**Is your real email getting marked as spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="a0764-p101">如果發生誤判，您應使用[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)向 Microsoft 回報該郵件。此外，您可以將郵件*以附件方式*轉寄到 not_junk@office365.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="a0764-p101">If you get a false positive, you should report the message to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can forward the message *as an attachment* to not_junk@office365.microsoft.com.</span></span>

<span data-ttu-id="a0764-107">**重要** 如果您未以附件形式轉寄郵件，則標頭將會遺失，而且我們將無法改善 Office 365 中的垃圾郵件篩選功能。</span><span class="sxs-lookup"><span data-stu-id="a0764-107">**Important** If you do not forward the messages as an attachment, then the headers will be missing and we will be unable to improve the junk mail filtering in Office 365.</span></span>
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a><span data-ttu-id="a0764-108">判斷郵件被標示為垃圾郵件的原因</span><span class="sxs-lookup"><span data-stu-id="a0764-108">Determine the reason why the message was marked as spam</span></span>

<span data-ttu-id="a0764-p102">您可以[檢視電子郵件訊息標頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)並判定發生何種問題，來解決 Office 365 中的許多垃圾郵件問題。您需要尋找名為 X-Forefront-Antispam-Report 的標頭。您可以[深入了解反垃圾郵件標頭](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a0764-p102">Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. You will need to look for a header named X-Forefront-Antispam-Report. You can [learn more about anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="a0764-112">在標頭中，尋找下列標題和值。</span><span class="sxs-lookup"><span data-stu-id="a0764-112">In the header, look for the following headings and values.</span></span>
  
### <a name="x-forefront-antispam-report"></a><span data-ttu-id="a0764-113">X-Forefront-Antispam-Report</span><span class="sxs-lookup"><span data-stu-id="a0764-113">X-Forefront-Antispam-Report</span></span>

- <span data-ttu-id="a0764-114">**SFV:SPM** 表示郵件已因 EOP 垃圾郵件篩選而標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="a0764-114">**SFV:SPM** Indicates that the message was marked as spam because of the EOP spam filters.</span></span> 

- <span data-ttu-id="a0764-115">**SFV:BLK** 表示郵件已標示為垃圾郵件，因為寄件地址是在收件者封鎖的寄件者清單上。</span><span class="sxs-lookup"><span data-stu-id="a0764-115">**SFV:BLK** Indicates that the message was marked as spam because the sending address is on the recipient's Blocked Senders List.</span></span> 
    
- <span data-ttu-id="a0764-p103">**SFV:SKS** 表示在篩選內容之前已將郵件標示為垃圾郵件。這可能包括將郵件標示為垃圾郵件的郵件流程規則 (也稱為傳輸規則)。執行郵件追蹤，來查看是否已觸發可能設定高垃圾郵件信賴等級 (SCL) 的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="a0764-p103">**SFV:SKS** Indicates that the message was marked as spam prior to the content filter. This could include a transport rule marking the message as spam. Run a message trace to see if a transport rule triggered which may have set a high spam confidence level (SCL).</span></span> 
    
- <span data-ttu-id="a0764-119">**SFV:SKB** 表示郵件已標示為垃圾郵件，因為它符合垃圾郵件篩選原則中的封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="a0764-119">**SFV:SKB** Indicates that the message was marked as spam because it matched a block list in the spam filter policy.</span></span> 
    
- <span data-ttu-id="a0764-p104">**SFV:BULK** 表示位於 x-microsoft-antispam 的大量抱怨層級 (BCL) 值高於已對內容篩選器設定的大量閾值。大量電子郵件是使用者可能已註冊，但仍有可能不想要的電子郵件。在郵件標頭中，於 X-Microsoft-Antispam 標頭中尋找 BCL (大量信賴等級) 屬性。如果 BCL 值小於垃圾郵件篩選器中設定的閾值，您可能想要調整閾值，而不是將這些類型的大宗郵件標示為垃圾郵件。不同的使用者對於[大量電子郵件的處理方式](https://docs.microsoft.com/zh-TW/office365/SecurityCompliance/bulk-complaint-level-values) (英文) 各有不同的容錯和喜好設定。您可以針對不同的使用者喜好設定建立不同的原則或規則。</span><span class="sxs-lookup"><span data-stu-id="a0764-p104">**SFV:BULK** Indicates that the Bulk Complaint Level (BCL) value located in the x-microsoft-antispam header is above the Bulk threshold that has been set for the content filter. Bulk email is email which users may have signed up for, but may still be undesirable. In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the Spam Filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email is handled](https://docs.microsoft.com/zh-TW/office365/SecurityCompliance/bulk-complaint-level-values). You can create different policies or rules for different user preferences.</span></span>
    
- <span data-ttu-id="a0764-p105">**CAT:SPOOF** 或 **CAT:PHISH** 表示郵件似乎是詐騙郵件，表示無法驗證郵件來源，且可能是可疑的郵件。如果有效，寄件者將需要確定它們具有適當的 SPF 及 DKIM 設定。如需詳細資訊，請檢查 Authentication-Results 標頭。雖然可能很難讓所有寄件者都使用適當的電子郵件驗證方法，但略過這些檢查可能風險極大，而且是造成危害的首要原因。</span><span class="sxs-lookup"><span data-stu-id="a0764-p105">**CAT:SPOOF** or **CAT:PHISH** Indicates that the message appears to be spoofed, meaning that the message source cannot be validated and could be suspicious. If valid, the sender will need to make sure that they have proper SPF and DKIM configuration. Check the Authentication-Results header for more information. Although it may be difficult to get all senders to use proper email authentication methods, bypassing these checks can be extremely dangerous and is the top cause of compromises.</span></span> 
    
### <a name="x-customspam"></a><span data-ttu-id="a0764-130">x-customspam</span><span class="sxs-lookup"><span data-stu-id="a0764-130">x-customspam</span></span>

- <span data-ttu-id="a0764-p106">若出現此標頭，表示郵件已標示為垃圾郵件，因為已在您的垃圾郵件篩選器中啟用其中一個[進階垃圾郵件選項](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) (機器翻譯)。除非您需要這些功能，否則我們建議您使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="a0764-p106">The presence of this header indicates that the message was marked as spam because one of the [advanced spam options is enabled](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in your spam filter. Unless you need these features, we recommend that you use the default settings.</span></span> 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a><span data-ttu-id="a0764-133">造成太多垃圾郵件之其他原因的解決方案</span><span class="sxs-lookup"><span data-stu-id="a0764-133">Solutions to additional causes of too much spam</span></span>

<span data-ttu-id="a0764-p107">若要有效地運作，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。</span><span class="sxs-lookup"><span data-stu-id="a0764-p107">In order to work effectively, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="a0764-137">若為系統管理員</span><span class="sxs-lookup"><span data-stu-id="a0764-137">For admins</span></span>

- <span data-ttu-id="a0764-p108">**將您的 DNS 記錄指向 Office 365** 為了讓 EOP 提供防護，所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 Office 365，而且只能指向 Office 365。如果您的 MX 未指向 Office 365，則 EOP 不會為您的使用者提供垃圾郵件篩選功能。在您想要使用其他服務或應用裝置，為您的網域提供垃圾郵件篩選功能的情況下，您應該考慮在 EOP 中停用垃圾郵件保護。做法為建立一個郵件流程規則，將 SCL 值設為 -1。如果您稍後決定要使用 EOP，請務必移除此郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="a0764-p108">**Point your DNS records to Office 365** In order for EOP to provide protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. If your MX does not point to Office 365, then EOP will not provide spam filtering for your users. In the situation where you wish to use another service or appliance to provide spam filtering for your domain, you should consider disabling the spam protection in EOP. You can do this by creating a transport rule that sets the SCL value to -1. If you later decide to use EOP, make sure to remove this transport rule.</span></span> 
    
- <span data-ttu-id="a0764-p109">**為使用者開啟回報郵件增益集** 我們建議您[為使用者啟用回報郵件增益集](enable-the-report-message-add-in.md)。身為系統管理員，您也可以檢視使用者傳送的意見反應，並使用任何模式，來調整任何可能造成問題的設定。</span><span class="sxs-lookup"><span data-stu-id="a0764-p109">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for your users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
    
### <a name="for-users"></a><span data-ttu-id="a0764-145">若為使用者</span><span class="sxs-lookup"><span data-stu-id="a0764-145">For users</span></span>
    
- <span data-ttu-id="a0764-p110">**建立安全寄件者清單**使用者可從將他們所信任的寄件者地址新增到 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) 或 [Outlook 網頁版](https://go.microsoft.com/fwlink/p/?LinkId=294862)中的安全寄件者清單。若要開始使用 Outlook 網頁版，請選擇 [設定]\*\*\*\*![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \>[選項]\*\*\*\* \> [封鎖或允許]\*\*\*\*。下列圖表顯示新增某項目到安全寄件者清單的範例。</span><span class="sxs-lookup"><span data-stu-id="a0764-p110">**Create a safe sender list** Users can add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.</span></span>
  
![在 Outlook 網頁版中新增安全寄件者](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
<span data-ttu-id="a0764-p111">EOP 將信任使用者的安全寄件者人和收件人，但不會信任安全的網域。不管是透過 Outlook 網頁版新增的網域，或是使用目錄同步處理新增到 Outlook 並進行同步處理的網域，都是如此。</span><span class="sxs-lookup"><span data-stu-id="a0764-p111">EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.</span></span>

- <span data-ttu-id="a0764-p112">**停用 Outlook 中的 SmartScreen 篩選**如果您使用舊版 Outlook 桌面用戶端，您應該停用已終止的 SmartScreen 篩選功能。啟用將會造成誤判。如果執行已更新的桌面 Outlook 用戶端，並不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="a0764-p112">**Disable SmartScreen filtering in Outlook** If you are using an older Outlook desktop client, you should disable the SmartScreen filtering functionality, which has been discontinued. If enabled, it can cause false positives. This should not be required if running an updated desktop Outlook client.</span></span>

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a><span data-ttu-id="a0764-155">疑難排解：即使 EOP 將郵件標示為非垃圾郵件，它仍然跑到垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0764-155">Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam</span></span>
<span data-ttu-id="a0764-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="a0764-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span></span>

<span data-ttu-id="a0764-p113">如果您的使用者在 Outlook 中啟用了「僅限安全清單：只有來自安全寄件者清單或安全收件者清單上的人員或網域所寄出的郵件才會傳送到您的收件匣」，除非寄件者位於收件者的安全寄件者清單中，否則所有電子郵件將進入垃圾郵件資料夾。無論 EOP 將郵件標示為非垃圾郵件，或是您在EOP 設定規則將郵件標示為非垃圾郵件，這個情況都會發生。</span><span class="sxs-lookup"><span data-stu-id="a0764-p113">If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.</span></span>
  
<span data-ttu-id="a0764-159">您可以遵照 [Outlook：可停用垃圾電子郵件 UI 和篩選機制的原則設定](https://support.microsoft.com/zh-TW/kb/2180568) (機器翻譯) 中的指示，為您的 Outlook 使用者停用 [僅限安全清單] 選項。</span><span class="sxs-lookup"><span data-stu-id="a0764-159">You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/zh-TW/kb/2180568).</span></span>
  
<span data-ttu-id="a0764-160">如果您是在 Outlook 網頁版中查看郵件，則會顯示一個黃色安全提示，指出郵件位於垃圾郵件資料夾，因為寄件者不在收件者的安全寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="a0764-160">If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.</span></span>
  
<span data-ttu-id="a0764-p114">當您查看郵件標題，它可能包含 SFV:SKN (IP 允許或 ETR 允許) 或 SFV:NSPM (非垃圾郵件) 戳記，但郵件仍然被放在使用者的垃圾郵件資料夾中。郵件標題中不會有任何資訊顯示使用者已啟用「僅限安全清單」。因為使用者在 Outlook 中設定的「僅限安全清單」選項會覆寫 EOP 設定，所以會發生這個情況。</span><span class="sxs-lookup"><span data-stu-id="a0764-p114">If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting.</span></span> 
  
 <span data-ttu-id="a0764-164">**驗證為什麼來自安全寄件者的郵件在郵件標題中被標示為非垃圾郵件，但卻仍進入使用者的垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="a0764-164">**To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder**</span></span>
  
1. <span data-ttu-id="a0764-165">若要了解如何連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="a0764-165">To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> 
    
2. <span data-ttu-id="a0764-166">執行下列命令，檢視使用者的垃圾電子郵件組態設定：</span><span class="sxs-lookup"><span data-stu-id="a0764-166">Run the following command to view the user's junk email configuration settings:</span></span>
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- <span data-ttu-id="a0764-167">如果 TrustedListsOnly 設為 True，表示已啟用此設定</span><span class="sxs-lookup"><span data-stu-id="a0764-167">If TrustedListsOnly is set to True, it means that this setting is enabled</span></span>
- <span data-ttu-id="a0764-168">如果 ContactsTrusted 設為 True，表示使用者信任連絡人和安全寄件者</span><span class="sxs-lookup"><span data-stu-id="a0764-168">If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders</span></span>
- <span data-ttu-id="a0764-169">TrustedSendersAndDomains 會列出使用者安全寄件者清單的內容</span><span class="sxs-lookup"><span data-stu-id="a0764-169">The TrustedSendersAndDomains lists the contents of the user's Safe Senders list</span></span>


## <a name="eop-only-customers-use-directory-synchronization"></a><span data-ttu-id="a0764-170">只使用 EOP 的客戶：使用目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="a0764-170">EOP-only customers: use directory synchronization</span></span>

<span data-ttu-id="a0764-p115">如果您是只使用 EOP 的客戶，即您訂閱 EOP 服務以與內部部署 (Exchange) 電子郵件伺服器搭配使用，則應使用目錄同步處理將使用者設定與服務同步。這樣做可確保 EOP 信任您的安全寄件者清單。如需詳細資訊，請參閱[在 EOP 中管理郵件使用者](https://go.microsoft.com/fwlink/?LinkId=534098)中的「使用目錄同步處理來管理郵件使用者」(機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="a0764-p115">If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises (Exchange) email server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).</span></span>
