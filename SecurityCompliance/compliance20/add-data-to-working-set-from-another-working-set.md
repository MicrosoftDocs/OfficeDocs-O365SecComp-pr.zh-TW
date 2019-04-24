---
title: 將資料從一個工作集新增至另一個工作集
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
ms.openlocfilehash: e9e34d112cb84c27fec35e752eb2bfcbfe3136a3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243427"
---
# <a name="add-data-to-a-working-set-from-another-working-set"></a><span data-ttu-id="1c12e-102">從另一個工作集將資料新增至工作集</span><span class="sxs-lookup"><span data-stu-id="1c12e-102">Add data to a working set from another working set</span></span>
<span data-ttu-id="1c12e-103">在某些情況下，它可能需要設想部分文件中的一個工作集，並在另一個工作集合中個別工作與其。</span><span class="sxs-lookup"><span data-stu-id="1c12e-103">In some cases, it may be necessary to carve out a portion of documents from one working set and work with them individually in another working set.</span></span>  <span data-ttu-id="1c12e-104">如果您已下列工作集合中的內容，而且想要的資料子集上執行分析，這是特別有用。</span><span class="sxs-lookup"><span data-stu-id="1c12e-104">This is especially useful if you've culled content in a working set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="1c12e-105">若要將內容從一個工作集新增至另一個使用下列工作流程。</span><span class="sxs-lookup"><span data-stu-id="1c12e-105">Use the following workflow to add content from one working set to another.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="1c12e-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="1c12e-106">Before you start</span></span>
<span data-ttu-id="1c12e-107">在您開始之前，您需要建立新的工作集。</span><span class="sxs-lookup"><span data-stu-id="1c12e-107">Before you start, you'll need to create a new working set.</span></span>  <span data-ttu-id="1c12e-108">可以透過 [*處理設定*] 索引標籤[了解更多](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets)加入新的工作集。</span><span class="sxs-lookup"><span data-stu-id="1c12e-108">A new working set can be added through the *Working sets* tab [Learn more](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets).</span></span>

## <a name="step-1-identify-content-to-add-to-another-working-set"></a><span data-ttu-id="1c12e-109">步驟 1： 找出要加入至另一個工作集內容</span><span class="sxs-lookup"><span data-stu-id="1c12e-109">Step 1: Identify content to add to another working set</span></span>
<span data-ttu-id="1c12e-110">您可以將內容新增至工作集所選取的電子郵件和文件中的文件格線或搜尋結果中的所有項目。</span><span class="sxs-lookup"><span data-stu-id="1c12e-110">You can add content to a working set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="1c12e-111">選擇要新增選取的項目，如果選取的項目，然後按一下 [*動作*] 下拉式然後*加入另一個工作集*。</span><span class="sxs-lookup"><span data-stu-id="1c12e-111">If choosing to add selected items, select the items and click the *Action* drop down then *Add to another working set*.</span></span>

![新增至另一個工作集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-workings-set"></a><span data-ttu-id="1c12e-113">步驟 2： 指定將新增至另一個運作方式的選項</span><span class="sxs-lookup"><span data-stu-id="1c12e-113">Step 2: Specify options for adding to another workings set</span></span>
<span data-ttu-id="1c12e-114">在 [*新增] 以另一個工作設定選項*彈出式視窗中，首先選擇您想要新增的項目工作集。</span><span class="sxs-lookup"><span data-stu-id="1c12e-114">In the *Add to another working set options* flyout, first choose the working set you want to add the items to.</span></span>  <span data-ttu-id="1c12e-115">選擇是否要新增所有搜尋結果] 或 [選定項目。</span><span class="sxs-lookup"><span data-stu-id="1c12e-115">Choose whether to add All search results or Selected items.</span></span>  <span data-ttu-id="1c12e-116">其他資訊提供選項] 來納入所有中繼資料，從項目並最後中新的工作集應該包含的文件標籤。</span><span class="sxs-lookup"><span data-stu-id="1c12e-116">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new working set.</span></span>  <span data-ttu-id="1c12e-117">按一下 *[確定]* 新的工作會建立將內容新增至工作集之後，您可以監視進度的[工作](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20)] 索引標籤中的工作![新增至另一個工作集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span><span class="sxs-lookup"><span data-stu-id="1c12e-117">After clicking *OK* a new job will be created to add the content to a working set, you can monitor the progress of that job in the [Jobs](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20) tab. ![Add to another working set](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span></span>
