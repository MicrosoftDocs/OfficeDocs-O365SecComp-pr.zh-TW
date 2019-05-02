---
title: 從一個檢閱設定為另一個檢閱設定新增資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 025fd90373313f762ce1d1dab8d48286e32e3cbb
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527141"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="64e9b-102">將資料新增至從另一個檢閱組設定檢閱</span><span class="sxs-lookup"><span data-stu-id="64e9b-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="64e9b-103">在某些情況下，可能需要設想部分文件中的一個檢閱設定及使用其個別另一個檢閱集中。</span><span class="sxs-lookup"><span data-stu-id="64e9b-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="64e9b-104">如果您已下列檢閱集合中的內容，而且想要的資料子集上執行分析，這是特別有用。</span><span class="sxs-lookup"><span data-stu-id="64e9b-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="64e9b-105">若要將內容從一個檢閱設定為另一個使用下列工作流程。</span><span class="sxs-lookup"><span data-stu-id="64e9b-105">Use the following workflow to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="64e9b-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="64e9b-106">Before you begin</span></span>

<span data-ttu-id="64e9b-107">在您開始之前，您需要建立新的檢閱設定為新增的資料。</span><span class="sxs-lookup"><span data-stu-id="64e9b-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="64e9b-108">一組新檢閱可以新增案例**檢閱設定**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="64e9b-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="64e9b-109">如需詳細資訊，請參閱 <<c0>管理檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="64e9b-109">For more information, see [Manage review sets](managing-review-sets.md).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="64e9b-110">步驟 1： 找出要加入至另一個檢閱集的內容</span><span class="sxs-lookup"><span data-stu-id="64e9b-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="64e9b-111">您可以將內容新增至設定藉由選取 [文件格線或搜尋結果中的所有項目中的 [電子郵件和文件檢閱。</span><span class="sxs-lookup"><span data-stu-id="64e9b-111">You can add content to a review set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="64e9b-112">選擇要新增選取的項目，如果選取的項目，按一下 [**動作**]，然後按一下 [**新增至另一個檢閱設定**。</span><span class="sxs-lookup"><span data-stu-id="64e9b-112">If choosing to add selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![加入至另一個檢閱集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="64e9b-114">步驟 2： 指定，將新增至另一個檢閱選項</span><span class="sxs-lookup"><span data-stu-id="64e9b-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="64e9b-115">在**新增至另一檢閱組**彈出式視窗] 頁面上，選擇您想要新增的項目檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="64e9b-115">In the **Add to another review set** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="64e9b-116">選擇是否要新增**選取的項目**或**所有搜尋結果**。</span><span class="sxs-lookup"><span data-stu-id="64e9b-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="64e9b-117">其他資訊提供選項] 來納入所有中繼資料，從項目，並最後中新的檢閱應該包含的文件標記設定。</span><span class="sxs-lookup"><span data-stu-id="64e9b-117">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new review set.</span></span>  <span data-ttu-id="64e9b-118">按一下<b0>[確定]</b0>後的新工作將會建立將內容新增至檢閱設定;您可以監視該工作在 [<b1>作業</b1>] 索引標籤上的進度。如需詳細資訊，請參閱 <<c2>管理工作。</span><span class="sxs-lookup"><span data-stu-id="64e9b-118">After clicking **Ok** a new job will be created to add the content to a review set; you can monitor the progress of that job on the **Job** tab. For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>

![加入至另一個檢閱集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
