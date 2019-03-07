---
title: DLP 如何安全性 & 規範中心和 Exchange 系統管理中心之間工作
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解 DLP 安全性 & 合規性中心與 DLP 的運作方式，以及郵件流程規則 （傳輸規則） 中 Exchange 系統管理中心。
ms.openlocfilehash: 9912103ec95af9fed61c5c2d52d12b46342d16fb
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454905"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="ceeab-103">DLP 如何安全性 & 規範中心和 Exchange 系統管理中心之間工作</span><span class="sxs-lookup"><span data-stu-id="ceeab-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="ceeab-104">在 Office 365 中，您可以建立兩個不同的系統管理中心中的資料遺失防護 (DLP) 原則：</span><span class="sxs-lookup"><span data-stu-id="ceeab-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="ceeab-105">在**安全性 & 合規性中心**中，您可以建立一個 DLP 原則來協助保護 SharePoint、 OneDrive 及 Exchange 中的內容。</span><span class="sxs-lookup"><span data-stu-id="ceeab-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange.</span></span> <span data-ttu-id="ceeab-106">可能的話，我們建議您建立的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="ceeab-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="ceeab-107">如需詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的 DLP。</span><span class="sxs-lookup"><span data-stu-id="ceeab-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="ceeab-108">在**Exchange 系統管理中心**中，您可以建立 DLP 原則來協助保護只能在 Exchange 中的內容。</span><span class="sxs-lookup"><span data-stu-id="ceeab-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="ceeab-109">此原則可以使用 Exchange 郵件流程規則 （也稱為傳輸規則），使其具有更多選項特定處理電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ceeab-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="ceeab-110">如需詳細資訊，請參閱 <<c0>在 Exchange 系統管理中心中的 DLP。</span><span class="sxs-lookup"><span data-stu-id="ceeab-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="ceeab-111">DLP 原則建立這些系統管理員中心運作並排-本主題說明如何。</span><span class="sxs-lookup"><span data-stu-id="ceeab-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![在安全性與規範中心和 Exchange 系統管理中心中的 DLP 頁面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="ceeab-113">DLP 安全性 & 合規性中心與 Exchange 系統管理中心中的 DLP 和郵件流程規則的運作方式</span><span class="sxs-lookup"><span data-stu-id="ceeab-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="ceeab-114">安全性 & 合規性中心中建立 DLP 原則之後，原則會部署至所有包含的原則中的位置。</span><span class="sxs-lookup"><span data-stu-id="ceeab-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="ceeab-115">如果原則包含 Exchange Online 時，此原則便那里同步處理，並強制執行完全相同的方式與在 Exchange 系統管理中心中建立的 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="ceeab-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="ceeab-116">如果您已在 Exchange 系統管理中心中建立 DLP 原則，這些原則會繼續運作並排任何您建立安全性 & 合規性中心中的電子郵件的原則。</span><span class="sxs-lookup"><span data-stu-id="ceeab-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="ceeab-117">但是請注意，在 Exchange 系統管理中心中建立的規則優先順序。</span><span class="sxs-lookup"><span data-stu-id="ceeab-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="ceeab-118">所有的 Exchange 郵件流程規則會先處理，並接著處理從安全性 & 合規性中心的 DLP 規則。</span><span class="sxs-lookup"><span data-stu-id="ceeab-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="ceeab-119">這表示：</span><span class="sxs-lookup"><span data-stu-id="ceeab-119">This means that:</span></span>
  
- <span data-ttu-id="ceeab-120">Exchange 郵件流程規則封鎖的郵件不會取得安全性 & 合規性中心中建立的 DLP 規則所掃描。</span><span class="sxs-lookup"><span data-stu-id="ceeab-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="ceeab-121">Exchange 郵件流程規則會修改郵件的方式，會使其符合安全性 & 合規性中心中的 DLP 原則-例如新增外部使用者-如果然後 DLP 規則會偵測這，並視需要強制執行原則。</span><span class="sxs-lookup"><span data-stu-id="ceeab-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="ceeab-122">也請注意，使用 「 停止處理 「 巨集指令的 Exchange 郵件流程規則不會影響安全性 & 合規性中心中的 DLP 規則處理-將仍處理它們。</span><span class="sxs-lookup"><span data-stu-id="ceeab-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="ceeab-123">在 Exchange 系統管理中心與安全性 & 合規性中心中的原則提示</span><span class="sxs-lookup"><span data-stu-id="ceeab-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="ceeab-124">在 Exchange 系統管理中心中，建立郵件流程規則與 DLP 原則或安全性 & 合規性中心，但不能兩者同時建立的 DLP 原則，可以使用原則提示。</span><span class="sxs-lookup"><span data-stu-id="ceeab-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="ceeab-125">這是因為這些原則會儲存在不同的位置，但只能從單一位置繪製原則提示。</span><span class="sxs-lookup"><span data-stu-id="ceeab-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="ceeab-126">如果您已在 Exchange 系統管理中心中設定原則提示，您在合規性中心不會出現在 web 和 Outlook 2013 和更新版本直到您在 Outlook 中的使用者安全性 & 中設定任何原則提示就會關閉 Exchange 系統管理中心中的提示。</span><span class="sxs-lookup"><span data-stu-id="ceeab-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="ceeab-127">這可確保您目前的 Exchange 郵件流程規則會繼續處理之前，您選擇要切換至安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ceeab-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="ceeab-128">請注意，雖然原則提示可以只從單一位置繪製，電子郵件通知一律傳送，即使您使用安全性 & 規範中心和 Exchange 系統管理中心中的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="ceeab-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

