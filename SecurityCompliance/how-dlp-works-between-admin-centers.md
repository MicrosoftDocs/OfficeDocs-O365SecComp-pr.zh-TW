---
title: DLP 安全性之間的運作方式&amp;規範中心及 Exchange 系統管理中心
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解如何在 [安全性] 中的 DLP&amp;規範中心可以與 Exchange 系統管理中心的 DLP 和傳輸規則搭配使用。
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215643"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="79768-103">DLP 安全性之間的運作方式&amp;規範中心及 Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="79768-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="79768-104">在 Office 365 中，您可以建立兩個不同的管理中心中的資料遺失防護 (DLP) 原則：</span><span class="sxs-lookup"><span data-stu-id="79768-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="79768-p101">在**安全性&amp;規範中心**，您可以建立單一 DLP 原則可協助保護 SharePoint、 OneDrive 及 Exchange 中的內容。請儘可能我們建議您建立的 DLP 原則。如需詳細資訊，請參閱[安全性 DLP&amp;規範中心](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="79768-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="79768-p102">在**Exchange 系統管理中心**中，您可以建立 DLP 原則可協助保護只能在 Exchange 中的內容。此原則可以使用 Exchange 傳輸規則，所以有更多選項特定來處理郵件。如需詳細資訊，請參閱[在 Exchange 系統管理中心的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。</span><span class="sxs-lookup"><span data-stu-id="79768-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="79768-111">DLP 原則建立這些系統中心運作並排-本主題說明如何。</span><span class="sxs-lookup"><span data-stu-id="79768-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![安全性和規範中心 」 及 Exchange 系統管理中心中的 DLP 頁面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="79768-113">如何安全性 DLP&amp;規範中心搭配 Exchange 系統管理中心的 DLP 和傳輸規則</span><span class="sxs-lookup"><span data-stu-id="79768-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="79768-p103">在 [安全性] 中建立的 DLP 原則之後&amp;規範中心、 原則會部署至所有包含在原則中的位置。如果原則包含 Exchange Online，將原則那里已同步處理及完全以相同方式來建立在 Exchange 系統管理中心的 DLP 原則強制執行。</span><span class="sxs-lookup"><span data-stu-id="79768-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="79768-p104">如果您已在 Exchange 系統管理中心中建立 DLP 原則，這些原則會繼續運作並排您在 [安全性] 中建立的電子郵件的任何原則&amp;規範中心。但是請注意在 Exchange 系統管理中心中建立的規則優先採用。首先，處理所有 Exchange 傳輸規則和 DLP 規則的安全性的然後&amp;都處理規範中心。</span><span class="sxs-lookup"><span data-stu-id="79768-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="79768-119">這表示：</span><span class="sxs-lookup"><span data-stu-id="79768-119">This means that:</span></span>
  
- <span data-ttu-id="79768-120">Exchange 傳輸規則封鎖的郵件將不會取得安全性中建立的 DLP 規則掃描&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="79768-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="79768-121">如果 Exchange 傳輸規則會修改訊息會使其符合 DLP 原則中安全性的方式&amp;規範中心-例如新增外部使用者-則 DLP 規則會偵測這並強制執行原則所需。</span><span class="sxs-lookup"><span data-stu-id="79768-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="79768-122">安全性附註使用"停止處理"巨集指令的 Exchange 傳輸規則不會影響 DLP 處理的規則而且&amp;規範中心-將仍處理它們。</span><span class="sxs-lookup"><span data-stu-id="79768-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="79768-123">原則提示安全性&amp;規範中心與 Exchange 系統管理中心的比較</span><span class="sxs-lookup"><span data-stu-id="79768-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="79768-p105">原則提示可以搭配使用其中一個與 DLP 原則及郵件流程規則建立在 Exchange 系統管理中心，或在 [安全性] 中建立的 DLP 原則&amp;規範中心，但不可同時。這是因為這些原則會儲存在不同的位置，但只能從單一位置可繪製原則提示。</span><span class="sxs-lookup"><span data-stu-id="79768-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="79768-p106">如果您已在 Exchange 系統管理中心，任何您在 [安全性設定的原則提示設定原則提示&amp;規範中心就不會出現在網路上的 Outlook 和 Outlook 2013 及更新版本直到您關閉在 Exchange 系統管理中心中的提示使用者。這可確保您目前的 Exchange 傳輸規則會繼續運作直到您選擇切換至 [安全性]&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="79768-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="79768-128">請注意，雖然只從單一位置可繪製原則提示的電子郵件通知一律傳送，即使您使用 DLP 原則這兩種安全性&amp;規範中心及 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="79768-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

