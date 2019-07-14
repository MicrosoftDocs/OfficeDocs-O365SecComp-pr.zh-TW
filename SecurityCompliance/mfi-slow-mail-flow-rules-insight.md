---
title: 緩慢的郵件流程規則深入解析
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 系統管理員可以在安全性與合規性中心中的郵件流程儀表板了解緩慢的郵件流程規則深入解析。
ms.openlocfilehash: 4477b388df321ee774ec7916a695cbfc69fc8e87
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598069"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="e5896-103">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="e5896-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="e5896-104">效率不佳的郵件流程規則 （也稱為傳輸規則）可能會延遲您組織的郵件流程。</span><span class="sxs-lookup"><span data-stu-id="e5896-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="e5896-105">此深入解析會報告影響您組織的郵件流程之郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="e5896-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="e5896-106">這類規則的範例為：</span><span class="sxs-lookup"><span data-stu-id="e5896-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="e5896-107">使用**屬於**大型群組的條件。</span><span class="sxs-lookup"><span data-stu-id="e5896-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="e5896-108">使用複雜的規則運算式 (regex) 模式比對的條件。</span><span class="sxs-lookup"><span data-stu-id="e5896-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="e5896-109">使用檢查附件內容的條件。</span><span class="sxs-lookup"><span data-stu-id="e5896-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="e5896-110">此深入解析可協助您識別並調整郵件流程規則，有助於減少郵件流程的延遲。</span><span class="sxs-lookup"><span data-stu-id="e5896-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![安全性與合規性中心中郵件流程儀表板的緩慢的郵件流程規則深入解析](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="e5896-112">當您按下**檢視詳細資料**，可以在顯示的延伸窗格中檢視此規則。</span><span class="sxs-lookup"><span data-stu-id="e5896-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="e5896-113">在延伸窗格中，可以按一下**檢視訊息範例**，查看規則會影響何種類型的郵件。</span><span class="sxs-lookup"><span data-stu-id="e5896-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![在郵件流程儀表板的緩慢的郵件流程規則深入解析中，按一下 [檢視詳細資料] 後顯示的彈出式窗格](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a><span data-ttu-id="e5896-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e5896-115">See also</span></span>

<span data-ttu-id="e5896-116">如需其他郵件流量儀表板中的郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="e5896-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
