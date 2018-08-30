---
title: 確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾
ms.author: krowley
author: kccross
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
description: EOP 客戶的預設反垃圾郵件動作是要將垃圾郵件移至 [收件者的垃圾郵件] 資料夾。為了讓此巨集指令來搭配內部部署信箱，您必須設定 Exchange 傳輸規則來偵測垃圾郵件標頭新增的 EOP 與內部邊緣] 或 [集線伺服器上。這些傳輸規則設定由 SclJunkThreshold 屬性使用 Set-organizationconfig 指令程式將垃圾郵件移至每個信箱的垃圾郵件] 資料夾的垃圾郵件信賴等級 (SCL)。
ms.openlocfilehash: 1b0a9e5ee39820baade714612ca0b0bdb7a81bb9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002852"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="b419a-105">確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾</span><span class="sxs-lookup"><span data-stu-id="b419a-105">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b419a-p102">本主題僅適用於 Exchange Online Protection (EOP) 主控信箱內部部署混合部署中的客戶。信箱已在 Office 365 中完全託管的 Exchange Online 客戶不需要執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b419a-p102">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="b419a-p103">EOP 客戶的預設反垃圾郵件動作是要將垃圾郵件移至 [收件者的垃圾郵件] 資料夾。為了讓此巨集指令來搭配內部部署信箱，您必須設定 Exchange 傳輸規則來偵測垃圾郵件標頭新增的 EOP 與內部邊緣] 或 [集線伺服器上。這些傳輸規則設定由 SclJunkThreshold 屬性使用 Set-organizationconfig 指令程式將垃圾郵件移至每個信箱的垃圾郵件] 資料夾的垃圾郵件信賴等級 (SCL)。</span><span class="sxs-lookup"><span data-stu-id="b419a-p103">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange Transport rules on your on-premises Edge or Hub servers to detect spam headers added by EOP. These Transport rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="b419a-111">若要新增傳輸規則來確定垃圾郵件移至 [垃圾郵件] 資料夾使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b419a-111">To add transport rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="b419a-p104">存取您的內部部署 Exchange server 的 Exchange 管理命令介面。若要了解如何在內部部署 Exchange 組織中開啟 Exchange 管理命令介面，請參閱**開啟命令介面**。</span><span class="sxs-lookup"><span data-stu-id="b419a-p104">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="b419a-114">執行下列命令，將經過內容篩選的垃圾郵件路由傳送至 [垃圾郵件] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="b419a-114">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="b419a-115">其中_NameForRule_是新規則，例如 JunkContentFilteredMail 的名稱。</span><span class="sxs-lookup"><span data-stu-id="b419a-115">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="b419a-116">執行下列命令，讓標示為垃圾郵件的郵件在抵達內容篩選器之前路由傳送至 [垃圾郵件] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="b419a-116">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="b419a-117">其中_NameForRule_是新規則，例如 JunkMailBeforeReachingContentFilter 的名稱。</span><span class="sxs-lookup"><span data-stu-id="b419a-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="b419a-118">執行下列命令，以確定寄件者封鎖清單中的垃圾郵件篩選器原則，例如**寄件者封鎖**清單中的訊息會路由傳送至 [垃圾郵件] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="b419a-118">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="b419a-119">其中_NameForRule_是新規則，例如 JunkMailInSenderBlockList 的名稱。</span><span class="sxs-lookup"><span data-stu-id="b419a-119">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="b419a-p105">如果您不想使用**移至 [垃圾郵件] 資料夾的郵件**巨集指令，您可以選擇您在 Exchange 系統管理中心中的內容篩選器原則中的另一個巨集指令。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。如需這些郵件標頭中的欄位的詳細資訊，請參閱[反垃圾郵件郵件標頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="b419a-p105">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b419a-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b419a-123">See also</span></span>

[<span data-ttu-id="b419a-124">New-transportrule 指令程式</span><span class="sxs-lookup"><span data-stu-id="b419a-124">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

