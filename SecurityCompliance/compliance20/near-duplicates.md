---
title: 近似重複項偵測
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
ms.openlocfilehash: 941809193a3342d8c7b9de991370848aee4af070
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30294936"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="5fbb2-102">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="5fbb2-102">Near duplicate detection</span></span>

<span data-ttu-id="5fbb2-p101">請考慮一組文件檢閱子集根據相同的範本和具有多半相同未定案的語言，具有以下及有一些差異。如果檢閱者無法找出這個子集、 徹底，檢閱其中一個並檢閱其餘的差異，他們就不具有未接唯一的任何資訊時考慮只在轉眼間格式化的時間會有採取加以讀取所有文件封面至封面。接近重複資料偵測群組加 1 類似的文件一起幫助您讓您檢閱程序工作更有效率。</span><span class="sxs-lookup"><span data-stu-id="5fbb2-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="5fbb2-106">它如何運作？</span><span class="sxs-lookup"><span data-stu-id="5fbb2-106">How does it work?</span></span>

<span data-ttu-id="5fbb2-p102">執行接近重複資料偵測時，系統會剖析文字的所有文件。然後，它會比較針對彼此判斷其相似性是否超過設定的臨界值的所有文件。如果它是文件會群組在一起。之後的所有文件有已比較及分組，從每個群組中的文件被標示為 「 樞紐分析;"檢閱您的文件，您可以先檢閱 [樞紐分析表並檢閱在接近重複組相同的其他文件著重在樞紐分析表及檢閱中的文件之間的差異。</span><span class="sxs-lookup"><span data-stu-id="5fbb2-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>