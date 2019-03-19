---
title: 確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何路由傳送垃圾郵件使用者垃圾郵件資料夾在 Exchange Online Protection。
ms.openlocfilehash: aada143944acf594e3ec0e873d022d7e2d45b003
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670548"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="aef94-103">確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾</span><span class="sxs-lookup"><span data-stu-id="aef94-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aef94-104">本主題僅適用於主控信箱的內部混合部署中的 Exchange Online Protection (EOP) 客戶。</span><span class="sxs-lookup"><span data-stu-id="aef94-104">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment.</span></span> <span data-ttu-id="aef94-105">信箱已完全裝載於 Office 365 的 Exchange Online 客戶不需要執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="aef94-105">Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="aef94-106">EOP 客戶的預設反垃圾郵件動作，就是將垃圾郵件移至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="aef94-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="aef94-107">為了讓此動作可搭配內部部署信箱，您必須在您的內部邊緣] 或 [集線伺服器，以偵測 EOP 所新增的垃圾郵件標頭上設定 Exchange 郵件流程規則 （也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="aef94-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="aef94-108">這些郵件流程規則設定垃圾郵件信賴等級 (SCL) 的 Set-organizationconfig 指令程式的 SclJunkThreshold 內容所用來將垃圾郵件移至每個信箱的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="aef94-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="aef94-109">若要新增郵件流程規則，以確保垃圾郵件移至 [垃圾郵件] 資料夾使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef94-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="aef94-110">存取內部部署 Exchange 伺服器的 Exchange 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="aef94-110">Access the Exchange Management Shell for your on-premises Exchange server.</span></span> <span data-ttu-id="aef94-111">若要了解如何在內部部署 Exchange 組織中開啟 Exchange 管理命令介面，請參閱 **Open the Shell** 。</span><span class="sxs-lookup"><span data-stu-id="aef94-111">To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="aef94-112">執行下列命令，將經過內容篩選的垃圾郵件路由傳送至 [垃圾郵件] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="aef94-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="aef94-113">_NameForRule_所在的新規則，例如 JunkContentFilteredMail 的名稱。</span><span class="sxs-lookup"><span data-stu-id="aef94-113">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="aef94-114">執行下列命令，讓標示為垃圾郵件的郵件在抵達內容篩選器之前路由傳送至 [垃圾郵件] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="aef94-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="aef94-115">_NameForRule_所在的新規則，例如 JunkMailBeforeReachingContentFilter 的名稱。</span><span class="sxs-lookup"><span data-stu-id="aef94-115">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="aef94-116">執行下列命令，以確定寄件者封鎖清單中的垃圾郵件篩選原則，例如**寄件者封鎖**清單中，郵件會路由傳送至 [垃圾郵件] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="aef94-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="aef94-117">_NameForRule_所在的新規則，例如 JunkMailInSenderBlockList 的名稱。</span><span class="sxs-lookup"><span data-stu-id="aef94-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="aef94-118">如果您不想要使用 [**移至垃圾郵件] 資料夾的郵件**] 動作，您可以選擇另一個巨集指令中 Exchange 系統管理中心中內容篩選原則。</span><span class="sxs-lookup"><span data-stu-id="aef94-118">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="aef94-119">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="aef94-119">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="aef94-120">如需這些欄位中的郵件標頭的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="aef94-120">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  

> [!TIP]
> <span data-ttu-id="aef94-121">如果您不想要使用 [**移至垃圾郵件] 資料夾的郵件**] 動作，您可以選擇另一個巨集指令中 Exchange 系統管理中心中內容篩選原則。</span><span class="sxs-lookup"><span data-stu-id="aef94-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="aef94-122">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="aef94-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="aef94-123">如需這些欄位中的郵件標頭的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="aef94-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
> 
## <a name="see-also"></a><span data-ttu-id="aef94-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aef94-124">See also</span></span>

[<span data-ttu-id="aef94-125">New-transportrule 指令程式</span><span class="sxs-lookup"><span data-stu-id="aef94-125">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

