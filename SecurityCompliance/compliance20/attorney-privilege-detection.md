---
title: 設定律師-委託人進階電子文件中的權限偵測
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
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155185"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a><span data-ttu-id="e582f-102">設定進階電子文件中的設定律師-委託人權限偵測 （預覽）</span><span class="sxs-lookup"><span data-stu-id="e582f-102">Set up attorney-client privilege detection (preview) in Advanced eDiscovery</span></span>

<span data-ttu-id="e582f-103">任何探索程序的檢閱部分主要且愈長寬檢閱特殊權限的內容。</span><span class="sxs-lookup"><span data-stu-id="e582f-103">A major and costly aspect of the review portion of any discovery process is reviewing for privileged content.</span></span> <span data-ttu-id="e582f-104">進階電子文件提供 AI 型偵測您的案例中的特殊權限內容，讓您能進行此程序更有效率。</span><span class="sxs-lookup"><span data-stu-id="e582f-104">Advanced eDiscovery provides an AI-based detection of privileged content in your case so that you can make this process more efficient.</span></span> <span data-ttu-id="e582f-105">此功能目前是 beta，eDiscovery 系統管理員已加入至使用該功能。</span><span class="sxs-lookup"><span data-stu-id="e582f-105">As this feature is currently in beta, an eDiscovery Administrator has to opt into the feature to use it.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="e582f-106">它如何運作？</span><span class="sxs-lookup"><span data-stu-id="e582f-106">How does it work?</span></span>

<span data-ttu-id="e582f-107">使用功能開啟，當您分析案例中設定檢閱，透過律師-委託人權限偵測模型執行的所有文件。</span><span class="sxs-lookup"><span data-stu-id="e582f-107">With the feature turned on, when you analyze a review set within a case, all documents run through the attorney-client privilege detection model.</span></span> <span data-ttu-id="e582f-108">模型會查看兩件事：</span><span class="sxs-lookup"><span data-stu-id="e582f-108">The model looks at two things:</span></span>

- <span data-ttu-id="e582f-109">內容： ML 模型會決定要在本質法律文件的內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="e582f-109">Content: the ML model determines the likelihood of the document's content being legal in nature.</span></span>

- <span data-ttu-id="e582f-110">參與者： 律師租用戶的使用者上傳清單時，該模型比較至判斷文件是否有至少一個律師參與者清單對文件的參與者。</span><span class="sxs-lookup"><span data-stu-id="e582f-110">Participants: if there is a user-uploaded list of attorneys for the tenant, the model compares the participants of the document against the list to determine whether the document has at least one attorney participant.</span></span>
<span data-ttu-id="e582f-111">模型會輸出每個文件，這些元件會檢閱集合內的可搜尋的三個值：</span><span class="sxs-lookup"><span data-stu-id="e582f-111">The model outputs three values for every document, all of which will be searchable within a review set:</span></span>

- <span data-ttu-id="e582f-112">內容分數： 正在性質中法律文件的可能性 （介於 0 和 1 之間的分數）</span><span class="sxs-lookup"><span data-stu-id="e582f-112">Content score: the likelihood of the document being legal in nature (score between 0 and 1)</span></span>

- <span data-ttu-id="e582f-113">具有律師： True 是表示如果參與者中找到其中一個 [上傳的律師] 清單中，則為 false 否則或者沒有任何律師清單。</span><span class="sxs-lookup"><span data-stu-id="e582f-113">Has Attorney: True if one of the participants is found in the uploaded attorney list, false otherwise, or if there is no attorney list.</span></span>

-  <span data-ttu-id="e582f-114">可能特殊權限： True 是表示如果內容分數超出臨界值，或具有律師參與者，則為 false 否則。</span><span class="sxs-lookup"><span data-stu-id="e582f-114">Potentially Privileged: True if content score is above threshold or has an attorney participant, false otherwise.</span></span>

## <a name="opting-into-attorney-client-privilege-detection"></a><span data-ttu-id="e582f-115">設定律師-委託人權限偵測到選擇</span><span class="sxs-lookup"><span data-stu-id="e582f-115">Opting into Attorney-client privilege detection</span></span>

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a><span data-ttu-id="e582f-116">步驟 1： 選擇加入到律師-委託人權限偵測 (eDiscovery 系統管理員)</span><span class="sxs-lookup"><span data-stu-id="e582f-116">Step 1: Opt into Attorney-client privilege detection (eDiscovery Admin)</span></span>

<span data-ttu-id="e582f-117">設定律師-委託人權限偵測時的預覽功能，因為您 eDiscovery 系統管理員必須選擇要讓此功能可在您的情況下。</span><span class="sxs-lookup"><span data-stu-id="e582f-117">Because Attorney-client privilege detection is a preview feature, your eDiscovery Administrator needs to opt in to make the feature available in your cases.</span></span>

- <span data-ttu-id="e582f-118">移至 「 設定實驗功能 」 的進階電子文件] 頁面</span><span class="sxs-lookup"><span data-stu-id="e582f-118">Go to "Configure experimental features" from Advanced eDiscovery page</span></span>

- <span data-ttu-id="e582f-119">按一下 「 管理律師-委託人特權偵測 」。</span><span class="sxs-lookup"><span data-stu-id="e582f-119">Click on "Manage Attorney-Client Privilege detection".</span></span>

- <span data-ttu-id="e582f-120">按一下切換以開啟該功能。</span><span class="sxs-lookup"><span data-stu-id="e582f-120">Click on the toggle to turn the feature on.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="e582f-121">步驟 2： 上傳律師 （選用） 的清單</span><span class="sxs-lookup"><span data-stu-id="e582f-121">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="e582f-122">為了充分利用律師-委託人權限偵測我們建議您為公司提供的電子郵件地址律師或合法的人物代表工作清單。</span><span class="sxs-lookup"><span data-stu-id="e582f-122">In order to take full advantage of attorney-client privilege detection we recommend providing a list of email addresses lawyers or legal personas who work for the company.</span></span> <span data-ttu-id="e582f-123">清單應該不標頭的 CSV，每行一個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e582f-123">The list should be a header-less CSV, with one email address per line.</span></span>

## <a name="leveraging-attorney-client-privilege-detection"></a><span data-ttu-id="e582f-124">利用律師-委託人權限偵測</span><span class="sxs-lookup"><span data-stu-id="e582f-124">Leveraging attorney-client privilege detection</span></span> 

### <a name="step-1-analyze-a-review-set"></a><span data-ttu-id="e582f-125">步驟 1： 分析檢閱設定</span><span class="sxs-lookup"><span data-stu-id="e582f-125">Step 1: Analyze a review set</span></span>

<span data-ttu-id="e582f-126">當您分析您檢閱設定時，也將會執行律師-委託人權限偵測。</span><span class="sxs-lookup"><span data-stu-id="e582f-126">When you analyze your review set, attorney-client privilege detection will be run as well.</span></span> <span data-ttu-id="e582f-127">若要深入了解分析檢閱集中的資料，請參閱[中檢閱設定進階 eDiscovery 中分析資料](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="e582f-127">To learn more about analyzing data in review set, please refer to [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="e582f-128">步驟 2： 建立律師-委託人權限偵測模型的智慧標籤群組</span><span class="sxs-lookup"><span data-stu-id="e582f-128">Step 2: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="e582f-129">您可以使用律師-委託人權限偵測的結果檢閱程序中的主要方法是使用智慧標籤群組。</span><span class="sxs-lookup"><span data-stu-id="e582f-129">One of the main ways you can consume the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="e582f-130">智慧標籤群組採取 ML 模型的結果，並顯示模型中內嵌標記旁的結果，讓您輕鬆地耗用模型的結果，其中相關，與檢閱程序中使用標記，如同任何其他標記您的標記面板中。</span><span class="sxs-lookup"><span data-stu-id="e582f-130">Smart tag groups take the results of an ML model and show the results of the model in-line next to the tags, so that you can easily consume the results of the model where relevant, and use the tags in your review process as you would any other tags in your tagging panel.</span></span> <span data-ttu-id="e582f-131">請參閱[Set up ML 輔助檢閱進階電子文件中的智慧標籤](smart-tags.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e582f-131">Please refer to [Set up smart tags for ML-assisted review in Advanced eDiscovery](smart-tags.md) for more information.</span></span>

- <span data-ttu-id="e582f-132">在 「 管理標籤 」 中，按一下 [在 「 新增智慧標籤區段 」。</span><span class="sxs-lookup"><span data-stu-id="e582f-132">In "Manage tags", click on "Add smart tag section".</span></span>

- <span data-ttu-id="e582f-133">選取 「 律師-委託人權限偵測 」。</span><span class="sxs-lookup"><span data-stu-id="e582f-133">Select "Attorney-client privilege detection".</span></span> <span data-ttu-id="e582f-134">您會看到的已建立標記群組和兩個標記，對應至在模型中的可能結果。</span><span class="sxs-lookup"><span data-stu-id="e582f-134">You will see that a tag group and two tags, corresponding to the possible results of the model, have been created.</span></span>

- <span data-ttu-id="e582f-135">請重新命名標記群組和標記，視您檢閱。</span><span class="sxs-lookup"><span data-stu-id="e582f-135">Rename the tag group and tags as you see fit for your review.</span></span>

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a><span data-ttu-id="e582f-136">步驟 3： 使用 [智慧標籤] 群組的權限檢閱</span><span class="sxs-lookup"><span data-stu-id="e582f-136">Step 3: Use the smart tag group for privilege review</span></span>

<span data-ttu-id="e582f-137">當您檢閱文件中，如果模型已決定文件可能特殊權限時，對應的智慧標籤會公開結果：</span><span class="sxs-lookup"><span data-stu-id="e582f-137">When you review a document, if the model has determined that the document is potentially privileged, the corresponding smart tag will expose the result:</span></span>

- <span data-ttu-id="e582f-138">如果文件有可能是法律性質的內容，對應的智慧標籤旁邊會出現 「 法律內容 」 標籤。</span><span class="sxs-lookup"><span data-stu-id="e582f-138">If the document has content that may be legal in nature, a "Legal content" label will appear next to the corresponding smart tag.</span></span>

- <span data-ttu-id="e582f-139">如果文件上傳的律師清單中找到的參與者，對應的智慧標籤旁邊會出現 「 律師 」 標籤。</span><span class="sxs-lookup"><span data-stu-id="e582f-139">If the document has a participant that is found in the uploaded attorney list, an "Attorney" label will appear next to the corresponding smart tag.</span></span>