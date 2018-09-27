---
title: 設定 Office 365 ATP 安全附件原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/8/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: 定義電子郵件中的惡意檔案的保護貴組織的原則安全的附件。
ms.openlocfilehash: bc52522a45071776835efe20f57cf37c415d2436
ms.sourcegitcommit: 9826013c3e0532ae5d01b3d88a14691f8dd0f6b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25092939"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a><span data-ttu-id="45b6a-103">設定 Office 365 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="45b6a-103">Set up Office 365 ATP Safe Attachments policies</span></span>

<span data-ttu-id="45b6a-p101">人員定期傳送、 接收及共用文件、 簡報、 試算表等的附件。您不一定容易告訴附件是否安全或惡意只是透過查看 [電子郵件訊息。而您想要的最後一項重點是以取得，透過惡意附件混亂您的組織。幸運地是，可以協助[Office 365 進階威脅保護](office-365-atp.md)(ATP)。您可以設定[ATP 安全附件](atp-safe-attachments.md)原則以協助確保貴組織保護會遭受攻擊由不安全的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p101">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more. It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message. And the last thing you want is a malicious attachment to get through, wreaking havoc for your organization. Fortunately, [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) can help. You can set up [ATP Safe Attachments](atp-safe-attachments.md) policies to help ensure that your organization is protected against attacks by unsafe email attachments.</span></span> 
  
## <a name="what-to-do"></a><span data-ttu-id="45b6a-109">該怎麼辦</span><span class="sxs-lookup"><span data-stu-id="45b6a-109">What to do</span></span> 
  
1. [<span data-ttu-id="45b6a-110">請先檢閱必要條件</span><span class="sxs-lookup"><span data-stu-id="45b6a-110">Review the prerequisites</span></span>](#review-the-prerequisites)
    
2. [<span data-ttu-id="45b6a-111">設定 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="45b6a-111">Set up an ATP Safe Attachments policy</span></span>](#set-up-an-atp-safe-attachments-policy)
    
3. [<span data-ttu-id="45b6a-112">了解 ATP 安全附件原則選項</span><span class="sxs-lookup"><span data-stu-id="45b6a-112">Learn about ATP Safe Attachments policy options</span></span>](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="45b6a-113">步驟 1： 檢閱必要條件</span><span class="sxs-lookup"><span data-stu-id="45b6a-113">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="45b6a-114">請確定您的組織具有[Office 365 進階威脅保護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="45b6a-114">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="45b6a-115">請確定您具有必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="45b6a-115">Make sure that you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="45b6a-p102">[了解 ATP 安全附件原則選項](#learn-about-atp-safe-attachments-policy-options)（在本文）。雖然掃描附件有一些選項，例如 [監視] 或 [取代] 選項，可能會導致次要電子郵件的延遲。若要避免郵件延遲回應，請考慮使用[動態傳遞和預覽](dynamic-delivery-and-previewing.md)。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p102">[Learn about ATP Safe Attachments policy options](#learn-about-atp-safe-attachments-policy-options) (in this article). Some options, such as the Monitor or Replace options, can result in a minor delay of email while attachments are scanned. To avoid message delays, consider using [dynamic delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
    
- <span data-ttu-id="45b6a-119">可讓您新增或更新原則散佈到所有 Office 365 資料中心的最多 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="45b6a-119">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a><span data-ttu-id="45b6a-120">步驟 2： 設定 （或編輯） ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="45b6a-120">Step 2: Set up (or edit) an ATP Safe Attachments policy</span></span>

> [!TIP]
> <span data-ttu-id="45b6a-p103">您可以設定使用下列任一 ATP 安全附件原則 Office 365 安全性&amp;規範中心 」 或 「 Exchange 系統管理中心 (EAC)。**建議使用 Office 365 安全性&amp;規範中心**。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p103">You can set up an ATP Safe Attachments policy using either the Office 365 Security &amp; Compliance Center or the Exchange admin center (EAC). **We recommend using the Office 365 Security &amp; Compliance Center**.</span></span> 
  
1. <span data-ttu-id="45b6a-123">以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="45b6a-123">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="45b6a-124">Office 365 安全性&amp;規範中心的左的功能窗格的 [**威脅管理**] 下選擇**原則** \> **安全的附件**。</span><span class="sxs-lookup"><span data-stu-id="45b6a-124">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>
    
3. <span data-ttu-id="45b6a-p104">如果您看到**開啟 SharePoint、 OneDrive 及 Microsoft 小組 ATP**，我們建議您選取這個選項。這可讓[Office 365 進階威脅 Protection for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)的 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p104">If you see **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, we recommend that you select this option. This will enable [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) for your Office 365 environment.</span></span> 
    
4. <span data-ttu-id="45b6a-127">選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**))，開始建立您的原則。</span><span class="sxs-lookup"><span data-stu-id="45b6a-127">Choose **New** (the New button resembles a plus sign ( **+**)) to start creating your policy.</span></span>
    
5. <span data-ttu-id="45b6a-128">指定名稱、 描述與原則設定。</span><span class="sxs-lookup"><span data-stu-id="45b6a-128">Specify the name, description, and settings for the policy.</span></span>
    
    <span data-ttu-id="45b6a-129">**範例：** 若要設定的原則稱為 「 沒有延遲 」 立即將所有人的郵件，然後將它們掃描後重新附加的附件，您可能會指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="45b6a-129">**Example:** To set up a policy called "no delays" that delivers everyone's messages immediately and then reattaches attachments after they're scanned, you might specify the following settings:</span></span> 
    
      - <span data-ttu-id="45b6a-130">在 [**名稱**] 方塊中輸入沒有延遲。</span><span class="sxs-lookup"><span data-stu-id="45b6a-130">In the **Name** box, type no delays.</span></span>
    
      - <span data-ttu-id="45b6a-131">在 [**描述**] 方塊中輸入描述 like 立即傳送郵件並將重新附加附件之後掃描。</span><span class="sxs-lookup"><span data-stu-id="45b6a-131">In the **Description** box, type a description like, Delivers messages immediately and reattaches attachments after scanning.</span></span>
    
      - <span data-ttu-id="45b6a-p105">在 [回應] 區段中，選擇 [**動態的傳遞**選項。（[解更多關於動態傳遞和 ATP 安全附件預覽](dynamic-delivery-and-previewing.md)）。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p105">In the response section, choose the **Dynamic Delivery** option. ([Learn more about dynamic delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).)</span></span>
    
      - <span data-ttu-id="45b6a-134">**重新導向附件**] 區段中選取 [啟用重新導向及輸入 Office 365 全域管理員、 安全性管理員或安全性分析師將調查惡意附件的電子郵件地址] 選項。</span><span class="sxs-lookup"><span data-stu-id="45b6a-134">In the **Redirect attachment** section, select the option to enable redirect and type the email address of your Office 365 global administrator, security administrator, or security analyst who will investigate malicious attachments.</span></span> 
    
      - <span data-ttu-id="45b6a-p106">在**套用至**] 區段中，選擇 [**收件者的網域是**，，然後選取您的網域。選擇 [**新增**]，然後選擇 [ **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p106">In the **Applied To** section, choose **The recipient domain is**, and then select your domain. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="45b6a-137">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="45b6a-137">Choose **Save**.</span></span>
    
<span data-ttu-id="45b6a-p107">請考慮組織的多個 ATP 安全附件原則設定。這些原則會套用他們正在**ATP 安全附件**] 頁面將列出的順序。已定義或編輯原則後，允許至少 30 分鐘的原則才會生效整個 Microsoft 資料中心。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p107">Consider setting up multiple ATP Safe Attachments policies for your organization. These policies will be applied in the order they're listed on the **ATP Safe Attachments** page. After a policy has been defined or edited, allow at least 30 minutes for the polices to take effect throughout Microsoft datacenters.</span></span> 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a><span data-ttu-id="45b6a-141">步驟 3： 了解 ATP 安全附件原則選項</span><span class="sxs-lookup"><span data-stu-id="45b6a-141">Step 3: Learn about ATP Safe Attachments policy options</span></span>

<span data-ttu-id="45b6a-p108">當您設定好您 ATP 安全附件的原則，您選擇針對許多選項，包括監視、 封鎖、 Replace、 動態傳遞等等。萬一您想知道這些選項所執行的動作下, 表摘要說明每個其效果。</span><span class="sxs-lookup"><span data-stu-id="45b6a-p108">As you set up your ATP Safe Attachments policies, you choose from among many options, including Monitor, Block, Replace, Dynamic Delivery, and so on. In case you're wondering about what these options do, the following table summarizes each and its effect.</span></span>
  
|<span data-ttu-id="45b6a-144">**選項**</span><span class="sxs-lookup"><span data-stu-id="45b6a-144">**Option**</span></span>|<span data-ttu-id="45b6a-145">**效果**</span><span class="sxs-lookup"><span data-stu-id="45b6a-145">**Effect**</span></span>|<span data-ttu-id="45b6a-146">**當您想要使用：**</span><span class="sxs-lookup"><span data-stu-id="45b6a-146">**Use when you want to:**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45b6a-147">**Off**</span><span class="sxs-lookup"><span data-stu-id="45b6a-147">**Off**</span></span> <br/> |<span data-ttu-id="45b6a-148">不會掃描附件的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="45b6a-148">Does not scan attachments for malware</span></span>  <br/> <span data-ttu-id="45b6a-149">不會延遲郵件傳遞</span><span class="sxs-lookup"><span data-stu-id="45b6a-149">Does not delay message delivery</span></span>  <br/> |<span data-ttu-id="45b6a-150">關閉掃描程式內部的寄件者、 掃描、 傳真] 或將只會將傳送已知的良好的附件的智慧主機</span><span class="sxs-lookup"><span data-stu-id="45b6a-150">Turn scanning off for internal senders, scanners, faxes, or smart hosts that will only send known, good attachments</span></span>  <br/> <span data-ttu-id="45b6a-151">防止不必要的路由的內部郵件的延遲</span><span class="sxs-lookup"><span data-stu-id="45b6a-151">Prevent unnecessary delays in routing internal mail</span></span>  <br/> <span data-ttu-id="45b6a-152">**此選項不建議大多數使用者使用。可讓您關閉 ATP 安全附件掃描程式內部的寄件者一小群。**</span><span class="sxs-lookup"><span data-stu-id="45b6a-152">**This option is not recommended for most users. It enables you to turn ATP Safe Attachments scanning off for a small group of internal senders.**</span></span>           |
|<span data-ttu-id="45b6a-153">**監視**</span><span class="sxs-lookup"><span data-stu-id="45b6a-153">**Monitor**</span></span> <br/> |<span data-ttu-id="45b6a-154">將附件的郵件，然後時會有什麼與偵測到惡意程式碼來追蹤</span><span class="sxs-lookup"><span data-stu-id="45b6a-154">Delivers messages with attachments and then tracks what happens with detected malware</span></span>  <br/> |<span data-ttu-id="45b6a-155">請參閱偵測到惡意程式碼會在組織中的其中</span><span class="sxs-lookup"><span data-stu-id="45b6a-155">See where detected malware goes in your organization</span></span>  <br/> |
|<span data-ttu-id="45b6a-156">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="45b6a-156">**Block**</span></span> <br/> |<span data-ttu-id="45b6a-157">防止從繼續偵測到惡意程式碼附件的郵件</span><span class="sxs-lookup"><span data-stu-id="45b6a-157">Prevents messages with detected malware attachments from proceeding</span></span>  <br/> <span data-ttu-id="45b6a-158">將偵測到惡意程式碼的郵件傳送至[Office 365 中的隔離](manage-quarantined-messages-and-files.md)其中的安全性管理員或分析師可以檢閱及釋出 （或刪除） 那些郵件</span><span class="sxs-lookup"><span data-stu-id="45b6a-158">Sends messages with detected malware to [quarantine in Office 365](manage-quarantined-messages-and-files.md) where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> <span data-ttu-id="45b6a-159">自動封鎖未來的訊息與附件</span><span class="sxs-lookup"><span data-stu-id="45b6a-159">Blocks future messages and attachments automatically</span></span>  <br/> |<span data-ttu-id="45b6a-160">可重複使用相同的惡意程式碼附件的攻擊貴組織保護</span><span class="sxs-lookup"><span data-stu-id="45b6a-160">Safeguard your organization from repeated attacks using the same malware attachments</span></span>  <br/> |
|<span data-ttu-id="45b6a-161">**取代**</span><span class="sxs-lookup"><span data-stu-id="45b6a-161">**Replace**</span></span> <br/> |<span data-ttu-id="45b6a-162">會移除偵測到惡意程式碼的附件</span><span class="sxs-lookup"><span data-stu-id="45b6a-162">Removes detected malware attachments</span></span>  <br/> <span data-ttu-id="45b6a-163">通知收件者已移除附件</span><span class="sxs-lookup"><span data-stu-id="45b6a-163">Notifies recipients that attachments have been removed</span></span>  <br/> <span data-ttu-id="45b6a-164">將偵測到惡意程式碼的郵件傳送至[Office 365 中的隔離](manage-quarantined-messages-and-files.md)其中的安全性管理員或分析師可以檢閱及釋出 （或刪除） 那些郵件</span><span class="sxs-lookup"><span data-stu-id="45b6a-164">Sends messages with detected malware to [quarantine in Office 365](manage-quarantined-messages-and-files.md) where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> |<span data-ttu-id="45b6a-165">引發給收件者的附件已移除因偵測到惡意程式碼的可見性</span><span class="sxs-lookup"><span data-stu-id="45b6a-165">Raise visibility to recipients that attachments were removed because of detected malware</span></span>  <br/> |
|<span data-ttu-id="45b6a-166">**動態傳遞**</span><span class="sxs-lookup"><span data-stu-id="45b6a-166">**Dynamic Delivery**</span></span> <br/> |<span data-ttu-id="45b6a-167">傳送立即訊息</span><span class="sxs-lookup"><span data-stu-id="45b6a-167">Delivers messages immediately</span></span>  <br/> <span data-ttu-id="45b6a-168">直到掃描已完成，然後將偵測到任何惡意程式碼時重新附加附件的附件取代預留位置檔案</span><span class="sxs-lookup"><span data-stu-id="45b6a-168">Replaces attachments with a placeholder file until scanning is complete, and then reattaches the attachments if no malware is detected</span></span>  <br/> <span data-ttu-id="45b6a-169">包含附件預覽功能大部分的 Pdf 和 Office 檔案掃描期間</span><span class="sxs-lookup"><span data-stu-id="45b6a-169">Includes attachment previewing capabilities for most PDFs and Office files during scanning</span></span>  <br/> <span data-ttu-id="45b6a-170">將偵測到惡意程式碼的郵件傳送至其中的安全性管理員或分析師可以檢閱及釋出 （或刪除） 那些郵件隔離</span><span class="sxs-lookup"><span data-stu-id="45b6a-170">Sends messages with detected malware to Quarantine where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> [<span data-ttu-id="45b6a-171">了解動態傳遞和 ATP 安全附件預覽</span><span class="sxs-lookup"><span data-stu-id="45b6a-171">Learn about dynamic delivery and previewing with ATP Safe Attachments</span></span>](dynamic-delivery-and-previewing.md) <br/> |<span data-ttu-id="45b6a-172">避免郵件延遲時防止惡意檔案中的收件者</span><span class="sxs-lookup"><span data-stu-id="45b6a-172">Avoid message delays while protecting recipients from malicious files</span></span>  <br/> <span data-ttu-id="45b6a-173">啟用時掃描正在進行預覽附件安全模式中的收件者</span><span class="sxs-lookup"><span data-stu-id="45b6a-173">Enable recipients to preview attachments in safe mode while scanning is taking place</span></span>  <br/> |
|<span data-ttu-id="45b6a-174">**啟用重新導向**</span><span class="sxs-lookup"><span data-stu-id="45b6a-174">**Enable redirect**</span></span> <br/> |<span data-ttu-id="45b6a-175">適用於選擇監視器、 封鎖或取代選項</span><span class="sxs-lookup"><span data-stu-id="45b6a-175">Applies when the Monitor, Block, or Replace option is chosen</span></span>  <br/> <span data-ttu-id="45b6a-176">傳送給指定的電子郵件地址的附件安全性管理員或分析師其中調查</span><span class="sxs-lookup"><span data-stu-id="45b6a-176">Sends attachments to a specified email address where security administrators or analysts can investigate</span></span>  <br/> |<span data-ttu-id="45b6a-177">啟用安全性管理員和分析師研究可疑的附件</span><span class="sxs-lookup"><span data-stu-id="45b6a-177">Enable security administrators and analysts to research suspicious attachments</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="45b6a-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="45b6a-178">Related topics</span></span>

[<span data-ttu-id="45b6a-179">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="45b6a-179">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="45b6a-180">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="45b6a-180">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="45b6a-181">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="45b6a-181">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="45b6a-182">設定 Office 365 中的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="45b6a-182">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="45b6a-183">進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="45b6a-183">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="45b6a-184">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="45b6a-184">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

