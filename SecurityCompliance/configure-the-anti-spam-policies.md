---
title: 設定反垃圾郵件原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: 垃圾郵件篩選會自動啟用的全公司透過預設的反垃圾郵件原則 （連線篩選器、 垃圾郵件篩選器及輸出垃圾郵件）。身為管理員，您可以檢視和編輯，但是無法刪除預設反垃圾郵件原則，讓它們專門針對最符合您組織的需求。精確性，您也可以建立自訂原則並將它們套用至指定的使用者、 群組或網域中，您組織中。根據預設，自訂原則優先於預設原則，但您可以變更您的原則的優先順序。
ms.openlocfilehash: 3e972a150b70f1081cb4c3b5e3672a3acba34785
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340964"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="b7e25-106">設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="b7e25-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="b7e25-p102">垃圾郵件篩選會自動啟用的全公司透過預設的反垃圾郵件原則 （連線篩選器、 垃圾郵件篩選器及輸出垃圾郵件）。身為管理員，您可以檢視和編輯，但是無法刪除預設反垃圾郵件原則，讓它們專門針對最符合您組織的需求。精確性，您也可以建立自訂原則並將它們套用至指定的使用者、 群組或網域中，您組織中。根據預設，自訂原則優先於預設原則，但您可以變更您的原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="b7e25-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="b7e25-111">如需設定反垃圾郵件原則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="b7e25-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="b7e25-112">設定連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="b7e25-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="b7e25-113">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="b7e25-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="b7e25-p103">為 EOP 獨立版客戶： 根據預設，EOP 內容篩選將偵測到垃圾郵件的郵件傳送至每個收件者的垃圾郵件] 資料夾。不過，為了確保 [**移至垃圾郵件] 資料夾的郵件**] 動作將會使用內部部署信箱，您必須設定兩個 Exchange 郵件流程規則 （也稱為傳輸規則） 上您的內部部署伺服器，以偵測所新增的垃圾郵件標頭EOP。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e25-p103">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="b7e25-117">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="b7e25-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

