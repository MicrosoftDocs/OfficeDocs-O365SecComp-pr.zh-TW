---
title: 在 Office 365 進階電子文件探索中了解文件相似性
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '檢閱 Office 365 進階在 eDiscovery 中的文件相似性值、 最小程度跟必須考量接近重複、 兩個檔案的運作方式。 '
ms.openlocfilehash: eb8f07ceedb10bd0152693dd1e82a28797d86a5a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220423"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b90b0-103">在 Office 365 進階電子文件探索中了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="b90b0-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b90b0-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="b90b0-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b90b0-106">進階 ediscovery 文件相似性是跟為接近重複項目必須考量兩個文件所需的最低層級。</span><span class="sxs-lookup"><span data-stu-id="b90b0-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="b90b0-p102">大部分的商務應用程式的建議使用相似性值的 60%-75%。品質非常不佳光學字元辨識 (OCR) 材料] 可以套用較低的相似性值。</span><span class="sxs-lookup"><span data-stu-id="b90b0-p102">For most business applications, it is recommended to use a Similarity value of 60%-75%. For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b90b0-109">已設定並執行特定案例之後，就無法變更相似性值。</span><span class="sxs-lookup"><span data-stu-id="b90b0-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="b90b0-p103">內 Near duplicate (ND) 設定，則可能會以類似下方的相似性臨界值的層級的文件。文件加入 ND 設定，則必須有至少一個文件中使用超過相似性跟層級設定 ND。</span><span class="sxs-lookup"><span data-stu-id="b90b0-p103">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold. For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="b90b0-112">例如，假設相似性設為 80%、 文件 F1 的格式類似於文件 F2 85%的層級和文件 F2 的格式類似於文件 F3 90%以下層級。</span><span class="sxs-lookup"><span data-stu-id="b90b0-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="b90b0-p104">不過，文件 F1 可能類似文件 F3 層級的僅限 70%，這是低於臨界值。儘管如此，在本例中為文件 F1、 F2 及所有出現在一個 ND F3 設定。同樣地，使用相似性值的 80%，我們可能已建立兩組 EquiSet 1 和 EquiSet 2。EquiSet 1 包含 E1 和 E2 的文件。Equiset 2 包含 F1、 f2 鍵，與下 F3 的文件。</span><span class="sxs-lookup"><span data-stu-id="b90b0-p104">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold. Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set. Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2. EquiSet-1 contains documents E1 and E2. Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="b90b0-118">層級的跟說明如下：</span><span class="sxs-lookup"><span data-stu-id="b90b0-118">The levels of resemblance are illustrated as follows:</span></span>
  
![文件相似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="b90b0-p105">假設另一個文件、 X1、 立即插入。X1 及 E3 之間跟是 87%。同樣地，X1 和 F1 之間跟是 92%。因此，EquiSet-1、-2、 EquiSet 及 X1 會立即結合成一個 ND 設定。</span><span class="sxs-lookup"><span data-stu-id="b90b0-p105">Assume that another document, X1, is now inserted. The resemblance between X1 and E3 is 87%. Similarly, the resemblance between X1 and F1 is 92%. As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![文件相似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="b90b0-125">如果任何兩份文件或已指派給一 ND 組，會一起保持在相同的 ND 集中，即使額外的文件新增至集如果合併集。</span><span class="sxs-lookup"><span data-stu-id="b90b0-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="b90b0-126">合併設定之後，[樞紐分析表文件可以變更新文件新增至集合時。</span><span class="sxs-lookup"><span data-stu-id="b90b0-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b90b0-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b90b0-127">See also</span></span>

[<span data-ttu-id="b90b0-128">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="b90b0-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b90b0-129">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="b90b0-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b90b0-130">設定搜尋時忽略的文字</span><span class="sxs-lookup"><span data-stu-id="b90b0-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b90b0-131">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="b90b0-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b90b0-132">檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="b90b0-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

