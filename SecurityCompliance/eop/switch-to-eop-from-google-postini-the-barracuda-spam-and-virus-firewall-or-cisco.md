---
title: 從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: 本主題的目的在於協助您了解從內部部署電子郵件檢疫裝置或雲端保護服務切換到 Exchange Online Protection (EOP) 的程序，然後提供給您開始使用的說明資源。
ms.openlocfilehash: a1fa7b63dfc1e6eb193d458545722c4b5331bc48
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340754"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a><span data-ttu-id="0ae2e-103">從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP</span><span class="sxs-lookup"><span data-stu-id="0ae2e-103">Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort</span></span>

 <span data-ttu-id="0ae2e-p101">本主題的目的在於協助您了解從內部部署電子郵件檢疫裝置或雲端保護服務切換到 Exchange Online Protection (EOP) 的程序，然後提供給您開始使用的說明資源。有許多垃圾郵件篩選解決方案，但在大多數情況下，切換到 EOP 的程序類型很類似。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p101">The purpose of this topic is to help you understand the process for switching to Exchange Online Protection (EOP) from an on-premises email hygiene appliance or cloud-based protection service, and then to provide you with help resources to get started. There are many spam-filtering solutions, but the process for switching to EOP is similar in most cases.</span></span>
  
<span data-ttu-id="0ae2e-106">如果您是初次使用 EOP 而且想要在決定切換前閱讀其功能概觀，請從 TechNet 上的 [Exchange Online Protection 概觀](exchange-online-protection-overview.md)開始。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-106">If you are new to EOP and you want to read an overview of its features before you decide to switch, start with the [Exchange Online Protection overview](exchange-online-protection-overview.md) on TechNet.</span></span> 
  
<span data-ttu-id="0ae2e-p102">在您切換到 EOP 之前，請思考要在雲端 (使用 Exchange Online)、內部部署或在混合案例中託管 EOP 保護的信箱 (「混合」的意思是，有些信箱裝載於內部部署，有些信箱裝載於 Exchange Online)。每個託管案例：雲端、內部部署和混合式部署都可行，但設定步驟有所不同。下列考量可協助您選擇適當的部署：</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p102">Before you switch to EOP, it's important to think about whether you want to host your EOP-protected mailboxes in the cloud, with Exchange Online, on-premises, or in a hybrid scenario. (Hybrid means that you have some mailboxes hosted on-premises and another portion hosted with Exchange Online.) Each of these hosting scenarios: cloud, on-premises, and hybrid, is possible, but the setup steps can vary. Here are a few considerations to help you choose the appropriate deployment:</span></span>
  
- <span data-ttu-id="0ae2e-p103">**內部部署信箱的 EOP 保護** 如果有想要使用的現有郵件託管基礎結構，或有將信箱保留在內部部署的業務需求，而且想要 EOP 的雲端電子郵件保護，則適合使用此案例。 [切換至獨立式 EOP](#BKMK_SwitchStandalone.md)詳細說明此案例。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p103">**EOP protection with on-premises mailboxes** This scenario is appropriate if you have existing mail-hosting infrastructure you want to use, or you have business requirements to keep mailboxes on-premises, and you want EOP's cloud-based email protection. [Switch to EOP standalone](#BKMK_SwitchStandalone.md) describes this scenario in more detail.</span></span> 
    
- <span data-ttu-id="0ae2e-p104">**Exchange Online 信箱的 EOP 保護** 如果您想要 EOP 保護而所有信箱都裝載在雲端，則適合使用此案例。這可協助您降低複雜度，因為您不需維護內部部署的郵件伺服器。 [切換至 Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO) 說明此案例。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p104">**EOP protection with Exchange Online mailboxes** This scenario is appropriate if you want EOP protection and all of your mailboxes hosted in the cloud. It can help you reduce complexity, because you don't have to maintain on-premises messaging servers. [Switch to Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO) describes this scenario.</span></span> 
    
- <span data-ttu-id="0ae2e-p105">**混合信箱的 EOP 保護** 也許您想要雲端信箱，但您必須將某些使用者的信箱保留在內部部署。如果您希望有些信箱裝載於內部部署，而有些信箱裝載於 Exchange Online，則選擇此案例。 [切換至混合解決方案](#BKMK_SwitchHybrid.md)說明此案例。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p105">**EOP protection with hybrid mailboxes** Perhaps you want cloud mailboxes, but you need to keep mailboxes for some users on-premises. Choose this scenario if you want some mailboxes hosted on-premises and another portion hosted with Exchange Online. [Switch to a hybrid solution](#BKMK_SwitchHybrid.md) describes this scenario.</span></span> 
    
## <a name="switch-to-eop-standalone"></a><span data-ttu-id="0ae2e-118">切換至獨立式 EOP</span><span class="sxs-lookup"><span data-stu-id="0ae2e-118">Switch to EOP standalone</span></span>
<span data-ttu-id="0ae2e-119"><a name="BKMK_SwitchStandalone"> </a></span><span class="sxs-lookup"><span data-stu-id="0ae2e-119"></span></span>

<span data-ttu-id="0ae2e-p106">如果您目前將信箱託管於內部部署，而且使用內部部署保護裝置或雲端郵件保護服務，即可切換至 EOP，充分利用其保護功能和可用性。若要在獨立環境中設定 EOP (這表示您將信箱託管於內部部署並使用 EOP 提供郵件保護)，可以遵循[設定 EOP 服務](set-up-your-eop-service.md)中簡述的步驟。本主題檢視設定 EOP 保護的步驟，包含註冊、新增網域以及設定郵件流程與連接器。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p106">If you currently host your mailboxes on premises and use an on-premises protection appliance or a cloud messaging-protection service, you can switch to EOP to take advantage of its protection features and availability. To set up EOP in a standalone scenario, which means you host your mailboxes on premises and use EOP to provide email protection, you can follow the steps outlined in [Set up your EOP service](set-up-your-eop-service.md). The topic outlines the steps for setting up EOP protection, which include sign up, adding your domain, and setting up mail flow with connectors.</span></span>
  
## <a name="switch-to-exchange-online"></a><span data-ttu-id="0ae2e-123">切換至 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0ae2e-123">Switch to Exchange Online</span></span>
<span data-ttu-id="0ae2e-124"><a name="BKMK_SwitchEXO"> </a></span><span class="sxs-lookup"><span data-stu-id="0ae2e-124"></span></span>

<span data-ttu-id="0ae2e-p107">或許您有以內部部署裝置保護的內部部署信箱，而想要換成 Exchange Online 雲端託管信箱與 EOP 保護，以享有 Office 365 雲端郵件和保護功能。若要開始進行，您可以註冊 Office 365 並新增網域。此案例不需要設定連接器，因為沒有任何資料路由傳送至內部部署信箱。從 [Office 365 註冊頁面](https://www.microsoft.com/en-us/office365/online-software.aspx)開始([開始使用 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407)提供用於熟悉其功能的資源)。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p107">Perhaps you have on-premises mailboxes protected by an on-premises appliance, and you want to jump to Exchange Online cloud-hosted mailboxes and EOP protection to take advantage of Office 365 cloud messaging and protection features. To get started, you can sign up for Office 365 and add your domain. This scenario doesn't require you to setup connectors, because there isn't any routing to on-premises mailboxes. Begin at the [Office 365 sign up page](https://www.microsoft.com/en-us/office365/online-software.aspx). ([Get started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407) provides resources to get familiar with its features.)</span></span> 
  
<span data-ttu-id="0ae2e-130">在 Office 365 設定過程中，您將建立雲端信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-130">During the Office 365 setup process, you will create your cloud-based mailbox users.</span></span>
  
## <a name="switch-to-a-hybrid-solution"></a><span data-ttu-id="0ae2e-131">切換至混合解決方案</span><span class="sxs-lookup"><span data-stu-id="0ae2e-131">Switch to a hybrid solution</span></span>
<span data-ttu-id="0ae2e-132"><a name="BKMK_SwitchHybrid"> </a></span><span class="sxs-lookup"><span data-stu-id="0ae2e-132"></span></span>

<span data-ttu-id="0ae2e-p108">您可能因為業務需求或法規考量，只想要將部分信箱移至雲端。當您部署混合案例時，可根據業務需求將信箱移至雲端。遷移至具有 EOP 保護的混合案例，比移至全雲端案例更加複雜，但 Microsoft 提供了完整的混合支援和豐富的資源，讓您能更加輕鬆地移至混合案例。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p108">You may want to move only a portion of your mailboxes to the cloud because of business requirements or regulatory considerations. When you deploy a hybrid scenario, you can move mailboxes to the cloud as your business requirements dictate. Migrating to a hybrid scenario with EOP protection is more complicated than moving to an all-cloud scenario, but Microsoft provides full hybrid support and ample resources to make the move to hybrid easier.</span></span>
  
<span data-ttu-id="0ae2e-p109">如果考慮採用混合式部署，[Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)是最佳起點。此外，您一定要了解在混合案例中路由傳送郵件的各種方法。[Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx)說明每種類型，以便您根據業務需求來選擇最佳路由案例。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p109">The best place to start, if you are considering a hybrid deployment, is [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx). Additionally, there are a few different ways you can route mail in a hybrid scenario that are important to understand. [Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx) explains each type, so you can choose the best routing scenario, based on your business requirements.</span></span> 
  
## <a name="migration-planning"></a><span data-ttu-id="0ae2e-139">遷移規劃</span><span class="sxs-lookup"><span data-stu-id="0ae2e-139">Migration planning</span></span>
<span data-ttu-id="0ae2e-140"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="0ae2e-140"></span></span>

<span data-ttu-id="0ae2e-141">當您決定切換至 EOP 時，請務必提供下列方面的特殊考量：</span><span class="sxs-lookup"><span data-stu-id="0ae2e-141">When you decide to switch to EOP, make sure you give special consideration to the following areas:</span></span>
  
- <span data-ttu-id="0ae2e-p110">**自訂篩選規則**如果您有自訂篩選] 或 [商務原則規則來捕捉特定的垃圾郵件，我們建議使用預設設定嘗試 EOP，一段，移轉您的規則之前。EOP 提供具有預設設定的企業級垃圾郵件保護，它可能會發現，您不需要將部分規則遷移至 EOP。當然，如果您有就地強制執行特定自訂業務原則的規則，您可以建立這些。[郵件流程規則 （傳輸規則） 在 Exchange Online Protection](mail-flow-rules-transport-rules-0.md)提供在 EOP 中建立郵件流程規則的詳細的指示。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p110">**Custom Filtering Rules** If you have custom filtering or business-policy rules to catch specific spam, we recommend that you try EOP with the default settings for a period, before you migrate your rules. EOP offers enterprise-level spam protection with the default settings, it may turn out that you don't need to migrate some of your rules to EOP. Of course, if you have rules in place that enforce specific custom business policies, you can create those. [Mail flow rules (transport rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) provides detailed instructions for creating mail flow rules in EOP.</span></span> 
    
- <span data-ttu-id="0ae2e-p111">**IP 允許清單與 IP 封鎖清單**如果您有每位使用者允許清單與封鎖清單，讓一些時間才能將清單複製到 EOP，您的安裝程式程序的一部分。如需 IP 允許清單與 IP 封鎖清單，請參閱[Configure the connection filter policy ](../configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p111">**IP allow lists and IP block lists** If you have per-user allow lists and block lists, allow some time to copy the lists to EOP as part of your setup process. For more information about IP allow lists and IP block lists, see [Configure the connection filter policy](../configure-the-connection-filter-policy.md).</span></span>
    
- <span data-ttu-id="0ae2e-p112">**安全通訊** 如果合作夥伴要求郵件必須加密，建議您在 Exchange 系統管理中心設定此案例。若要設定此案例，請參閱 [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p112">**Secure Communication** If you have a partner that requires encrypted messaging, we recommend that you set this up in the Exchange admin center. To configure this scenario, see [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx).</span></span>
    
> [!TIP]
> <span data-ttu-id="0ae2e-p113">當您從內部部署裝置切換至 EOP 時，有可能將裝置或伺服器保留在原地，以執行業務規則檢查。例如，若裝置對輸出郵件執行自訂篩選，而且希望繼續這麼做，您可以設定 EOP，在郵件路由傳送至網際網路之前，直接傳送至此裝置進行額外篩選。[Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)說明如何在此情況下設定郵件流程。</span><span class="sxs-lookup"><span data-stu-id="0ae2e-p113">When you switch from an on-premises appliance to EOP, it is possible to leave your appliance or a server in place that performs business rule checks. For instance, if your appliance performs custom filtering on outbound mail, and you want it to continue doing so, you can configure EOP to send mail directly to the appliance for additional filtering, before it is routed to the Internet. [Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx) shows you how to set up mail flow in this case.</span></span> 
  

