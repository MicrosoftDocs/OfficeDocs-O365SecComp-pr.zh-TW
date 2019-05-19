---
title: 設定律師-委託人權限偵測進階電子文件中的智慧標籤
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
ms.openlocfilehash: 5310acad1aa1bc2e01cbabee69dd7bb38084bd9a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153965"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a><span data-ttu-id="8acfd-102">設定 ML 輔助檢閱進階電子文件中的智慧標籤</span><span class="sxs-lookup"><span data-stu-id="8acfd-102">Set up smart tags for ML-assisted review in Advanced eDiscovery</span></span>

<span data-ttu-id="8acfd-103">進階電子文件中的機器學習功能原本用意是為了讓文件上的決策程序更有效率。</span><span class="sxs-lookup"><span data-stu-id="8acfd-103">Machine learning capabilities in Advanced eDiscovery are meant to help make decision process on documents more efficient.</span></span> <span data-ttu-id="8acfd-104">智慧標籤是可將機器學習到的記錄決策的功能： 標記和標記群組。</span><span class="sxs-lookup"><span data-stu-id="8acfd-104">Smart tags is a way to bring the machine learning capabilities into where the decisions are recorded: tags and tag groups.</span></span> <span data-ttu-id="8acfd-105">當您建立的智慧標籤群組時，然後對應至群組 ML 模型的決策也會顯示在-線環繞，具有可協助您] 群組中的標記，請參閱在資訊中的列，它們依內容相關性成為最有意義。</span><span class="sxs-lookup"><span data-stu-id="8acfd-105">When you create a smart tag group, then the decisions of the ML model mapped to the group will be shown in-line with the tags in the group to help you see the information in-line, where they contextually make most sense.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="8acfd-106">如何設定的智慧標籤群組</span><span class="sxs-lookup"><span data-stu-id="8acfd-106">How to set up a smart tag group</span></span>

1. <span data-ttu-id="8acfd-107">在 [檢閱設定，請移至**管理檢閱組** -> **管理標記**。</span><span class="sxs-lookup"><span data-stu-id="8acfd-107">In a review set, go to **Manage review set** -> **Manage tags**.</span></span>

2. <span data-ttu-id="8acfd-108">按一下 [**新增標籤群組**旁的下拉式]，然後選取 [**新增智慧標籤群組**。</span><span class="sxs-lookup"><span data-stu-id="8acfd-108">Click on the drop-down next to **Add tag group** and select **Add smart tag group**.</span></span>

3. <span data-ttu-id="8acfd-109">選取您想要對應至這個群組的模型。</span><span class="sxs-lookup"><span data-stu-id="8acfd-109">Select the model you want to map to this group.</span></span> <span data-ttu-id="8acfd-110">這會建立標籤] 區段中，N 子系標記，其中 N 是可能輸出模型的數目。</span><span class="sxs-lookup"><span data-stu-id="8acfd-110">This will create a tag section and N child tags, where N is the number of possible outputs of the model.</span></span> <span data-ttu-id="8acfd-111">比方說，律師-委託人權限偵測模型有兩個可能的輸出的特殊權限和特殊權限;選取此模型會建立兩個的子系標記中檢閱設定，每個對應至下列其中一個可能的輸出。</span><span class="sxs-lookup"><span data-stu-id="8acfd-111">For instance, attorney-client privilege detection model has two possible outputs - privileged and not privileged; selecting this model will create two child tags in the review set, each corresponding to one of the possible outputs.</span></span>

4. <span data-ttu-id="8acfd-112">請重新命名標記群組和標記，請參閱填滿。</span><span class="sxs-lookup"><span data-stu-id="8acfd-112">Rename the tag group and tags as you see fit.</span></span>

## <a name="how-to-use-a-smart-tag-group"></a><span data-ttu-id="8acfd-113">如何使用智慧標籤的群組</span><span class="sxs-lookup"><span data-stu-id="8acfd-113">How to use a smart tag group</span></span>

<span data-ttu-id="8acfd-114">檢閱文件時, 模型的結果將會公開旁的適當的標籤值。</span><span class="sxs-lookup"><span data-stu-id="8acfd-114">When reviewing a document, the model's results will be exposed next to the appropriate tag value.</span></span> <span data-ttu-id="8acfd-115">比方說，如果您有一個智慧標籤群組的設定律師-委託人權限偵測和您檢閱模型已決定文件可能特殊權限，您會看到的原因，適當的標籤旁。</span><span class="sxs-lookup"><span data-stu-id="8acfd-115">For instance, if you have a smart tag group for attorney-client privilege detection and you review a document that the model has decided is potentially privileged, you will see the reason for that next to the appropriate tag.</span></span> <span data-ttu-id="8acfd-116">請務必注意，不會自動套用標籤;如不管您的目的，標記內的智慧標籤群組法案就像一般的標記，不同之處在於公開模型的結果旁邊適當時機。</span><span class="sxs-lookup"><span data-stu-id="8acfd-116">It is important to note that the tag is not automatically applied; for all intents and purposes, tags within a smart tag group act just like normal tags, except that they expose the model results next to them when appropriate.</span></span>