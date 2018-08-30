---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/03/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: 安全的附件功能提供時間按一下 [驗證電子郵件附件。使用安全附件來自惡意檔案人員保護您的組織傳送或接收電子郵件中。
ms.openlocfilehash: 0a28923bff8aa2cd987159edd3cad77ed42f80f4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526752"
---
# <a name="office-365-atp-safe-attachments"></a><span data-ttu-id="453ec-104">Office 365 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="453ec-104">Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="453ec-p102">ATP 安全附件 （搭配[ATP 安全連結](atp-safe-links.md)） 是[Office 365 進階威脅保護](office-365-atp.md)(ATP) 的一部分。ATP 安全附件功能檢查電子郵件附件遭到惡意，並再採取的動作來保護您的組織。ATP 安全附件功能會保護您的組織根據您的 Office 365 全域或安全性管理員所設定的[ATP 安全附件的原則](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="453ec-p102">ATP Safe Attachments (along with [ATP Safe Links](atp-safe-links.md)) is part of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). The ATP Safe Attachments feature checks to see if email attachments are malicious, and then takes action to protect your organization. The ATP Safe Attachments feature protects your organization according to [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) that are set by your Office 365 global or security administrators.</span></span> 
  
<span data-ttu-id="453ec-p103">開始在落後年 3 月 2018年及向下一個幾週數、 ATP 保護正在延伸至檔案的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組。若要深入了解，請參閱[Office 365 進階威脅 Protection for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="453ec-p103">Beginning in late March 2018 and over the next several weeks, ATP protection is being extended to files in SharePoint Online, OneDrive for Business, and Microsoft Teams. To learn more, see [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>
       
## <a name="how-it-works"></a><span data-ttu-id="453ec-110">運作方式</span><span class="sxs-lookup"><span data-stu-id="453ec-110">How it works</span></span>

<span data-ttu-id="453ec-p104">ATP 安全附件功能會檢查您的組織中的人員的電子郵件附件。如果 ATP 安全附件原則已備妥某人所涵蓋的原則 「 Office 365 中檢視的電子郵件，檢查有其電子郵件附件並採取適當的動作，根據 ATP 安全附件原則。根據您的原則定義的方式、 人員可以繼續使用不知情屬於它們確實傳送惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="453ec-p104">The ATP Safe Attachments feature checks email attachments for people in your organization. When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies. Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="453ec-114">以下是兩個範例錯 ATP 安全附件。</span><span class="sxs-lookup"><span data-stu-id="453ec-114">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="453ec-p105">**範例 1： 電子郵件附件**假設 Lee 接收電子郵件具有附件。它不是以 Lee 明顯是否附件安全或實際包含惡意程式碼的設計用來竊取 Lee 使用者認證。Lee 的組織中的安全性管理員會定義 ATP 安全附件原則幾天以上。使用 ATP 安全附件功能，電子郵件附件形式開啟且 Lee 收到它之前在虛擬環境中測試。如果設為惡意決定附件，它將會自動移除。附件安全時，它會開啟如預期般 Lee 按一下其上時。</span><span class="sxs-lookup"><span data-stu-id="453ec-p105">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment. It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal the Lee's user credentials. In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago. With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it. If the attachment is determined to be malicious, it will be removed automatically. If the attachment is safe, it will open as expected when Lee clicks on it.</span></span> 
    
- <span data-ttu-id="453ec-p106">**範例 2： SharePoint Online 中的檔案**假設 Jean 接收到的檔案和上載到 SharePoint Online 中的文件庫。Jean 共用檔案的連結與其餘的小組不知道該檔案實際惡意。幸運地是， [SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)偵測到惡意檔案並封鎖它。稍後，在幾天後 Chris 會移到開啟的文件。雖然 Chris 可以看到該檔案有，Chris 無法開啟或共用，以防止 Chris 的電腦與其他人從惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="453ec-p106">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online. Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious. Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it. A few days later, Chris goes to open the document. Although Chris can see the file is there, Chris cannot open or share it, which prevents Chris's computer and others from the malicious file.</span></span> 
    
<span data-ttu-id="453ec-p107">ATP 安全附件原則可套用到特定的人員或組織中的群組或整個網域。若要深入了解，請參閱**[Set up Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="453ec-p107">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain. To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span> 
  
## <a name="how-to-get-atp-safe-attachments"></a><span data-ttu-id="453ec-128">如何取得 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="453ec-128">How to get ATP Safe Attachments</span></span>

<span data-ttu-id="453ec-p108">ATP 安全附件功能是進階威脅保護，其中包含在 Office 365 企業版 E5 的一部分。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買進階威脅保護。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[購買或編輯企業版的 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="453ec-p108">The ATP Safe Attachments feature is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span>
  
<span data-ttu-id="453ec-132">ATP 安全附件功能才適用情況：</span><span class="sxs-lookup"><span data-stu-id="453ec-132">The ATP Safe Attachments feature applies when:</span></span>
  
- <span data-ttu-id="453ec-p109">ATP 安全附件的原則設定。（請參閱[Set up Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="453ec-p109">ATP Safe Attachments policies are set up. (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md).)</span></span>
    
- <span data-ttu-id="453ec-p110">使用者已登入 Office 365 使用其工作或學校的帳戶。（請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="453ec-p110">Users have signed into Office 365 using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a><span data-ttu-id="453ec-137">如何知道 ATP 安全附件保護是否就緒</span><span class="sxs-lookup"><span data-stu-id="453ec-137">How to know if ATP Safe Attachments protection is in place</span></span>

 <span data-ttu-id="453ec-138">[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)必須設為就地 ATP 安全附件 protection 順序定義。</span><span class="sxs-lookup"><span data-stu-id="453ec-138">[ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) must be defined in order for ATP Safe Attachments protection to be in place.</span></span> 
  
<span data-ttu-id="453ec-139">請參閱服務正常運作方式的其中一個好方法是檢視[進階威脅 Protection 的報告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="453ec-139">One good way to see how the service is working is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
  
<span data-ttu-id="453ec-p111">此外下, 表說明幾個案例。在所有這些情況下，我們假設組織有 Office 365 企業版 E5，其中包含進階威脅保護。</span><span class="sxs-lookup"><span data-stu-id="453ec-p111">In addition, the following table describes some example scenarios. In all of these cases, we assume the organization has Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="453ec-142">**範例案例**</span><span class="sxs-lookup"><span data-stu-id="453ec-142">**Example scenario**</span></span>|<span data-ttu-id="453ec-143">**ATP 安全附件保護沒有在此例中套用吗？**</span><span class="sxs-lookup"><span data-stu-id="453ec-143">**Does ATP Safe Attachments protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="453ec-144">Pat 的組織具有 Office 365 企業版 E5，但無人有任何原則尚未定義 ATP 安全附件。</span><span class="sxs-lookup"><span data-stu-id="453ec-144">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP Safe Attachments yet.</span></span>  <br/> |<span data-ttu-id="453ec-p112">[否]。雖然此功能可提供，至少一個 ATP 安全附件原則必須定義設為就地 ATP 安全附件保護的順序。</span><span class="sxs-lookup"><span data-stu-id="453ec-p112">No. Although the feature is available, at least one ATP Safe Attachments policy must be defined in order for ATP Safe Attachments protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="453ec-p113">Lee 是在 Contoso sales 部門的員工。Lee 的組織中進行的財務員工僅適用於具有 ATP 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="453ec-p113">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP Safe Attachments policy in place that applies to finance employees only.</span></span>  <br/> |<span data-ttu-id="453ec-p114">[否]。在此例中，finance 員工具有 ATP 安全附件保護，但其他包括銷售部門的員工會等到包含這些群組原則所定義。</span><span class="sxs-lookup"><span data-stu-id="453ec-p114">No. In this case, finance employees would have ATP Safe Attachments protection, but other employees, including the sales department, would not until policies that include those groups are defined.</span></span>  <br/> |
|<span data-ttu-id="453ec-p115">昨天、 Jean 的組織在 Office 365 系統管理員設定套用至所有員工 ATP 安全附件原則。稍早今天 Jean 接收包含附件的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="453ec-p115">Yesterday, an Office 365 administrator at Jean's organization set up an ATP Safe Attachments policy that applies to all employees. Earlier today, Jean received an email message that includes an attachment.</span></span>  <br/> |<span data-ttu-id="453ec-p116">[是]。在這個範例中，Jean 已授權的進階威脅保護，並已定義包含 Jean ATP 安全附件原則。它通常採用的新原則才會生效跨資料中心來; 約 30 分鐘因為在此例中通過一天、 原則應作用中。</span><span class="sxs-lookup"><span data-stu-id="453ec-p116">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP Safe Attachments policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>  <br/> |
|<span data-ttu-id="453ec-p117">Chris 的組織中的位置在組織中所有人 ATP 安全附件原則與具有 Office 365 企業版 E5。Chris 會收到電子郵件帶有附件，並將組織以外的其他人郵件轉寄。</span><span class="sxs-lookup"><span data-stu-id="453ec-p117">Chris's organization has Office 365 Enterprise E5 with ATP Safe Attachments policies in place for everyone in the organization. Chris receives an email that has an attachment, and forwards the message to others who are outside the organization.</span></span>  <br/> |<span data-ttu-id="453ec-p118">ATP 安全附件保護已備妥 Chris 接收的郵件。如果收件者的組織也已經備妥的 ATP 安全附件原則，則 Chris 轉寄的郵件會是受限於這些原則轉寄的郵件送達時。</span><span class="sxs-lookup"><span data-stu-id="453ec-p118">ATP Safe Attachments protection is in place for messages that Chris receives. If the recipients' organizations also have ATP Safe Attachments policies in place, then the message that Chris forwards would be subject to those policies when the forwarded message arrives.</span></span>  <br/> |
|<span data-ttu-id="453ec-p119">李明組織 ATP 安全附件原則中進行，而且已開啟[ATP for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)。李明假設 SharePoint Online 中的每個檔案已掃描及安全開啟或下載。</span><span class="sxs-lookup"><span data-stu-id="453ec-p119">Jamie's organization has ATP Safe Attachments policies in place, and [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) has been turned on. Jamie assumes that every file in SharePoint Online has been scanned and is safe to open or download.  </span></span><br/> |<span data-ttu-id="453ec-p120">ATP 安全附件保護已備妥根據定義; 的原則但是，這不代表掃描的 SharePoint Online、 OneDrive for Business 或 Microsoft 小組中每一個單一檔案。（若要深入了解，請參閱[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)）。</span><span class="sxs-lookup"><span data-stu-id="453ec-p120">ATP Safe Attachments protection is in place according to the policies that are defined; however, this does not mean that every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams is scanned. (To learn more, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).)  </span></span><br/> |
   
## <a name="submitting-files-for-malware-analysis"></a><span data-ttu-id="453ec-164">惡意程式碼分析的檔案送出</span><span class="sxs-lookup"><span data-stu-id="453ec-164">Submitting files for malware analysis</span></span>

<span data-ttu-id="453ec-165">如果您收到您想要詢問 Microsoft 分析的檔案，請造訪[送出惡意程式碼分析的檔案](https://aka.ms/wdsi/submit)。</span><span class="sxs-lookup"><span data-stu-id="453ec-165">If you receive a file that you want to ask Microsoft to analyze, visit [Submit a file for malware analysis](https://aka.ms/wdsi/submit).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="453ec-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="453ec-166">Related topics</span></span>

[<span data-ttu-id="453ec-167">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="453ec-167">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="453ec-168">設定 Office 365 中的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="453ec-168">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="453ec-169">SharePoint、 OneDrive 及 Microsoft 小組 ATP</span><span class="sxs-lookup"><span data-stu-id="453ec-169">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)
  
[<span data-ttu-id="453ec-170">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="453ec-170">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="453ec-171">Office 365 中的 ATP 防網路釣魚功能</span><span class="sxs-lookup"><span data-stu-id="453ec-171">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  
[<span data-ttu-id="453ec-172">進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="453ec-172">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

