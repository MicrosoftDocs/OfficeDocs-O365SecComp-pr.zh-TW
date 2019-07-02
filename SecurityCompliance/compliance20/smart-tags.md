---
title: 在高級 eDiscovery 中設定智慧標籤
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 智慧標籤可讓您在閱讀高級 eDiscovery 案例中的內容時套用機器學習功能。 使用智慧標籤群組來顯示機器學習偵測模型的結果, 例如「律師-用戶端」許可權模型。
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703826"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="c88cc-104">在高級 eDiscovery 中設定智慧標籤</span><span class="sxs-lookup"><span data-stu-id="c88cc-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="c88cc-105">Advanced eDiscovery 中的機器學習 (ML) 功能, 可協助您在審閱集中檢查案例檔時, 讓決策程式更有效率。</span><span class="sxs-lookup"><span data-stu-id="c88cc-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="c88cc-106">智慧標籤是在記錄決策時所要採用的 ML 功能: 在審閱期間為檔加上標籤。</span><span class="sxs-lookup"><span data-stu-id="c88cc-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="c88cc-107">當您建立智慧標籤群組時, 如果您與智慧標籤群組相關聯的 ML 模型產生的決策, 就會與標記群組中的標籤一起顯示。</span><span class="sxs-lookup"><span data-stu-id="c88cc-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="c88cc-108">當您檢查特定檔時, 這有助於將 ML 結果資訊即時顯示。</span><span class="sxs-lookup"><span data-stu-id="c88cc-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="c88cc-109">如何設定智慧標籤群組</span><span class="sxs-lookup"><span data-stu-id="c88cc-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="c88cc-110">在 [審閱集] 中, 按一下 [**管理審閱集**], 然後按一下 [**管理標記**]。</span><span class="sxs-lookup"><span data-stu-id="c88cc-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="c88cc-111">按一下 [**新增標記群組**], 然後選取 [**新增智慧標籤群組**]。</span><span class="sxs-lookup"><span data-stu-id="c88cc-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="c88cc-112">選取您想要與標籤群組建立關聯的 ML 模型。</span><span class="sxs-lookup"><span data-stu-id="c88cc-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="c88cc-113">這會建立標記群組和*N*子標記, 其中*N*是模型的可能輸出數目。</span><span class="sxs-lookup"><span data-stu-id="c88cc-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="c88cc-114">例如, 「[律師-用戶端」的許可權偵測模型](attorney-privilege-detection.md)有兩個可能的輸出:</span><span class="sxs-lookup"><span data-stu-id="c88cc-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="c88cc-115">**正值**–用於標記包含律師費-用戶端許可權內容的檔。</span><span class="sxs-lookup"><span data-stu-id="c88cc-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="c88cc-116">**負值**–用來標記不含律師費-用戶端許可權內容的檔。</span><span class="sxs-lookup"><span data-stu-id="c88cc-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="c88cc-117">如果您選取此模型, 就會建立含有兩個子標記的標籤群組 (一個名為**正值**的子標記, 另一個名為**負數**) 做為審閱集。</span><span class="sxs-lookup"><span data-stu-id="c88cc-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="c88cc-118">在此範例中, 每個子標籤都對應至「律師-用戶端」許可權偵測模型的其中一個可能輸出。</span><span class="sxs-lookup"><span data-stu-id="c88cc-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="c88cc-119">您可以選擇性地重新命名標記群組和子標記。</span><span class="sxs-lookup"><span data-stu-id="c88cc-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="c88cc-120">例如, 您可以將**正值**標籤重新命名為 [**特權**], 而 [**負**] 標記則不會有任何**許可權**。</span><span class="sxs-lookup"><span data-stu-id="c88cc-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="c88cc-121">如何使用智慧標籤</span><span class="sxs-lookup"><span data-stu-id="c88cc-121">How to use smart tags</span></span>

<span data-ttu-id="c88cc-122">審閱檔時, 會在適當的子標記旁顯示模型的結果。</span><span class="sxs-lookup"><span data-stu-id="c88cc-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="c88cc-123">例如, 如果您有一個適用于律師-用戶端許可權偵測的智慧標籤群組, 並查看可能有許可權的檔, 則結論的原因會顯示在適當的標記旁。</span><span class="sxs-lookup"><span data-stu-id="c88cc-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="c88cc-124">請務必注意, 標記不會自動套用至檔。</span><span class="sxs-lookup"><span data-stu-id="c88cc-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="c88cc-125">檢閱者會決定如何標記檔。</span><span class="sxs-lookup"><span data-stu-id="c88cc-125">The reviewer makes the decision about how to tag the document.</span></span>