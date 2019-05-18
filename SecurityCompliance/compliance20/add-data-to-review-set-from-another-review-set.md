---
title: 從一個檢閱設定為另一個檢閱設定新增資料
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
description: ''
ms.openlocfilehash: 9dc75717ac0a57c8ccb38b1e01ec2fcb9c5737ab
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151965"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="2f00d-102">將資料新增至從另一個檢閱組設定檢閱</span><span class="sxs-lookup"><span data-stu-id="2f00d-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="2f00d-103">在某些情況下，可能需要設想部分文件中的一個檢閱設定及使用其個別另一個檢閱集中。</span><span class="sxs-lookup"><span data-stu-id="2f00d-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="2f00d-104">如果您已下列檢閱集合中的內容，而且想要的資料子集上執行分析，這是特別有用。</span><span class="sxs-lookup"><span data-stu-id="2f00d-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="2f00d-105">請依照將內容從設定到另一個檢閱本文中的工作流程。</span><span class="sxs-lookup"><span data-stu-id="2f00d-105">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2f00d-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="2f00d-106">Before you begin</span></span>

<span data-ttu-id="2f00d-107">在您開始之前，您需要建立新的檢閱設定為新增的資料。</span><span class="sxs-lookup"><span data-stu-id="2f00d-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="2f00d-108">一組新檢閱可以新增案例**檢閱設定**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="2f00d-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="2f00d-109">如需詳細資訊，請參閱 <<c0>建立檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="2f00d-109">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="2f00d-110">步驟 1： 找出要加入至另一個檢閱集的內容</span><span class="sxs-lookup"><span data-stu-id="2f00d-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="2f00d-111">您可以從一個檢閱設選取來源檢閱設定或 b seleting 傳回所有項目中的特定文件的另一個檢閱設定查詢所新增的內容。</span><span class="sxs-lookup"><span data-stu-id="2f00d-111">You can add content from one review set to another one by selecting specific documents in the source review set or b seleting all items returned by review set query.</span></span>  <span data-ttu-id="2f00d-112">如果您要新增選取的項目，請選取的項目，按一下 [**動作**]，然後按一下 [**新增至另一個檢閱設定**。</span><span class="sxs-lookup"><span data-stu-id="2f00d-112">If you're adding selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![加入至另一個檢閱集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="2f00d-114">步驟 2： 指定，將新增至另一個檢閱選項</span><span class="sxs-lookup"><span data-stu-id="2f00d-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="2f00d-115">在**新增至另一個檢閱設定選項**彈出式視窗] 頁面上，選擇您想要新增的項目檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="2f00d-115">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="2f00d-116">選擇是否要新增**選取的項目**或**所有搜尋結果**。</span><span class="sxs-lookup"><span data-stu-id="2f00d-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="2f00d-117">其他資訊提供選項] 來納入所有中繼資料，從項目和是否包含標記 （藉由選取 [**標籤**] 核取方塊），從來源檢閱設定文件加入至新的檢閱集合時。</span><span class="sxs-lookup"><span data-stu-id="2f00d-117">Additional information provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** checkbox) from the source review set when the documents are added to the new review set.</span></span>  

![加入至另一個檢閱集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="2f00d-119">按一下 **[確定]** 後，新的工作 （名為**新增資料至另一個檢閱設定**） 會建立將內容新增至另一個檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="2f00d-119">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to a another review set.</span></span>  <span data-ttu-id="2f00d-120">您可以前往**工作**] 索引標籤，並監視此工作的進度。</span><span class="sxs-lookup"><span data-stu-id="2f00d-120">You can go to **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="2f00d-121">如需詳細資訊，請參閱 <<c0>管理工作。</span><span class="sxs-lookup"><span data-stu-id="2f00d-121">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
