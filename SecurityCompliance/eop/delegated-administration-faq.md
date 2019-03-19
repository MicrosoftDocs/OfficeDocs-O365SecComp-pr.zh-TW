---
title: 委派管理常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: 針對想要執行委派的 Office 365 管理工作的 Microsoft 合作夥伴和轉銷售，包括能夠管理其他承租人 (公司) 的 Exchange Online Protection (EOP)，本主題提供常見問題與解答。
ms.openlocfilehash: 61f939932ab221343b67f87dd5c63f6697e70026
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670438"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="34ff7-103">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="34ff7-103">Delegated administration FAQ</span></span>

<span data-ttu-id="34ff7-104">針對想要執行委派的 Office 365 管理工作的 Microsoft 合作夥伴和轉銷售，包括能夠管理其他承租人 (公司) 的 Exchange Online Protection (EOP)，本主題提供常見問題與解答。</span><span class="sxs-lookup"><span data-stu-id="34ff7-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated Office 365 administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>
  
 <span data-ttu-id="34ff7-105">**問：我是轉銷商，需要管理客戶的承租人；該怎麼做？**</span><span class="sxs-lookup"><span data-stu-id="34ff7-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>
  
<span data-ttu-id="34ff7-106">答：是。</span><span class="sxs-lookup"><span data-stu-id="34ff7-106">A.</span></span> <span data-ttu-id="34ff7-107">如果您的 Microsoft 合作夥伴或轉銷商，而且您已簽署最多可為 Microsoft 顧問，您可以要求權限管理在系統管理中心內其租用戶。</span><span class="sxs-lookup"><span data-stu-id="34ff7-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="34ff7-108">這稱為委派管理，以及它可讓您管理其 Office 365 租用戶中 （包括 EOP 設定） 如果當您已在組織內系統管理員。</span><span class="sxs-lookup"><span data-stu-id="34ff7-108">This is known as delegated administration, and it allows you to manage their Office 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="34ff7-109">執行委派的管理的步驟如下所示：</span><span class="sxs-lookup"><span data-stu-id="34ff7-109">The steps for performing delegated administration are as follows:</span></span>
  
1. <span data-ttu-id="34ff7-110">註冊成為 [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits)。</span><span class="sxs-lookup"><span data-stu-id="34ff7-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>
    
2. <span data-ttu-id="34ff7-p102">註冊 Office 365 委派管理。客戶必須將委派管理員的身分授權給您，您才可以開始管理客戶的帳戶。若要取得核准，您需要先[將委派管理的邀請寄給他們](https://go.microsoft.com/fwlink/?LinkId=396829)。(您也可以稍後再提供委派管理給客戶。)</span><span class="sxs-lookup"><span data-stu-id="34ff7-p102">Sign up for Office 365 delegated administration. Before you can start administering a customer's account, they must authorize you as a delegated administrator. To obtain their approval, you first [send them an offer for delegated administration](https://go.microsoft.com/fwlink/?LinkId=396829). (You can also offer delegated administration to your customer at a later time.)</span></span> 
    
3. <span data-ttu-id="34ff7-115">使用＜[新增或刪除委派的管理員](https://go.microsoft.com/fwlink/?LinkId=396831)＞中所述的步驟來建立委派管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="34ff7-115">Create the delegated admin account using the steps documented in [Add or delete a delegated admin](https://go.microsoft.com/fwlink/?LinkId=396831).</span></span>
    
<span data-ttu-id="34ff7-116">請參閱＜[合作夥伴：建立業務以及管理您的 Office 365 合作夥伴帳戶](https://go.microsoft.com/fwlink/?LinkId=301485)＞，以取得如何設定 Office 365 委派管理的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="34ff7-116">Visit [Partners: Build your business and administer your Office 365 partner account](https://go.microsoft.com/fwlink/?LinkId=301485) for more information about how to set up Office 365 delegated administration.</span></span> 
  
 <span data-ttu-id="34ff7-117">**問：我是客戶，不是轉銷商，該如何為子承租人設定委派的系統管理員？**</span><span class="sxs-lookup"><span data-stu-id="34ff7-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>
  
<span data-ttu-id="34ff7-p103">答：委派的管理目前僅適用於轉銷商和合作夥伴。不過，我們提供範例 Windows PowerShell 指令碼，可協助您將原則套用到您的子承租人 (公司)。如需詳細資訊，請參閱 [套用 EOP 設定至多個承租人的範例指令碼](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="34ff7-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>
  
 <span data-ttu-id="34ff7-122">**問：可以防止我的子承租人管理員修改我的原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="34ff7-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>
  
<span data-ttu-id="34ff7-p104">答：Office 365 目前不具備這項功能。</span><span class="sxs-lookup"><span data-stu-id="34ff7-p104">A. Office 365 does not currently have this capability.</span></span>
  
 <span data-ttu-id="34ff7-125">**問：我可以取得所有子承租人的彙總報告嗎？**</span><span class="sxs-lookup"><span data-stu-id="34ff7-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>
  
<span data-ttu-id="34ff7-126">答：是。</span><span class="sxs-lookup"><span data-stu-id="34ff7-126">A.</span></span> <span data-ttu-id="34ff7-127">跨您管理公司的合併報告不適用於 Micrsoft 365 系統管理中心報告這一次。</span><span class="sxs-lookup"><span data-stu-id="34ff7-127">Consolidated reporting across the companies you manage is not available for the Micrsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="34ff7-128">不過，這可以透過遠端 Windows PowerShell 或[報告 web 服務](https://go.microsoft.com/fwlink/?LinkId=279926)。</span><span class="sxs-lookup"><span data-stu-id="34ff7-128">However, this can be done via remote Windows PowerShell or the [reporting web service](https://go.microsoft.com/fwlink/?LinkId=279926).</span></span> 
  

