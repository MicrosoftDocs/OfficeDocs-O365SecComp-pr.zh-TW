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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252001"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="b76bb-102">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="b76bb-102">Near duplicate detection</span></span>

<span data-ttu-id="b76bb-103">請考慮一組文件檢閱子集根據相同範本和具有大部分相同重複使用的語言，具有以下，有一些差異。</span><span class="sxs-lookup"><span data-stu-id="b76bb-103">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="b76bb-104">如果檢閱者無法識別此子集、 徹底，檢閱其中並檢閱其餘的差異，他們會不有未接唯一的任何資訊時採取的時間分數，可能需要花它們讀取封面至封面的所有文件。</span><span class="sxs-lookup"><span data-stu-id="b76bb-104">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="b76bb-105">接近重複資料偵測群組在一起，以協助您進行檢閱程序更有效率加 1 類似的文件。</span><span class="sxs-lookup"><span data-stu-id="b76bb-105">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="b76bb-106">它如何運作？</span><span class="sxs-lookup"><span data-stu-id="b76bb-106">How does it work?</span></span>

<span data-ttu-id="b76bb-107">執行接近重複資料偵測時，系統會剖析文字的所有文件。</span><span class="sxs-lookup"><span data-stu-id="b76bb-107">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="b76bb-108">然後，它會比較根據彼此判斷其相似性是否大於設定的臨界值的每個文件。</span><span class="sxs-lookup"><span data-stu-id="b76bb-108">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="b76bb-109">如果是的話，則文件，將群組在一起。</span><span class="sxs-lookup"><span data-stu-id="b76bb-109">If it is, the documents are grouped together.</span></span> <span data-ttu-id="b76bb-110">一旦所有文件有相較，且分組，每個群組的文件會標示為 「 中樞 」;檢閱您的文件，您可以先檢閱樞紐分析表，並檢閱在接近重複組相同的其他文件將重點放在樞紐分析表和檢閱中之文件之間的差異。</span><span class="sxs-lookup"><span data-stu-id="b76bb-110">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>