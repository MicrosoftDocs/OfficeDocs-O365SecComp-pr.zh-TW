---
title: 電子郵件執行緒
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
ms.openlocfilehash: ca4823ecfc06ddc0ef6f6840ad55fec492ac472c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258791"
---
# <a name="email-threading"></a><span data-ttu-id="8d1b6-102">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="8d1b6-102">Email threading</span></span>

<span data-ttu-id="8d1b6-103">請考慮有一段時間移電子郵件交談。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-103">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="8d1b6-104">在大多數情況下，在執行緒上的最後一個電子郵件會包含所有上述的電子郵件; 的內容檢閱最後一個電子郵件將會提供執行緒上發生的交談的完整內容。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-104">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="8d1b6-105">電子郵件執行緒識別這類電子郵件，以便檢閱者可以檢閱收集文件的分數，而不會遺失任何內容。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-105">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="8d1b6-106">電子郵件執行緒做什麼？</span><span class="sxs-lookup"><span data-stu-id="8d1b6-106">What does email threading do?</span></span>

<span data-ttu-id="8d1b6-107">每個電子郵件和 desconstructs 電子郵件執行緒會剖析至個別郵件;每個電子郵件是個別郵件的鏈結之一。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-107">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="8d1b6-108">然後，它會分析工作集至判斷一封電子郵件是否有獨特的內容，或如果鏈結完全不同的電子郵件中包含的所有電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-108">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="8d1b6-109">在結尾的電子郵件會分成四種類別：</span><span class="sxs-lookup"><span data-stu-id="8d1b6-109">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="8d1b6-110">**Inclusive**： 最後一封電子郵件中的具有唯一的內容，且電子郵件的所有其他的內容完全包含此電子郵件中的電子郵件中所含的附件。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="8d1b6-111">**減 Inclusive**： 最後一封電子郵件中的具有唯一的內容，但電子郵件並不包含一些其他的內容完全包含此電子郵件中的電子郵件中所含的附件。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="8d1b6-112">**內含的複本**： 完全相同的 [內含/內含減電子郵件複本</span><span class="sxs-lookup"><span data-stu-id="8d1b6-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="8d1b6-113">**None**： 這封電子郵件的內容完全包含至少一個電子郵件標示為 [內含/內含減號。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="8d1b6-114">如何是否不同於 Outlook 中的交談？</span><span class="sxs-lookup"><span data-stu-id="8d1b6-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="8d1b6-115">一眼這聲音非常類似於 Outlook 中的交談群組。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-115">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="8d1b6-116">不過，有一些重要的差別。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-116">However, there are some important distinctions.</span></span> <span data-ttu-id="8d1b6-117">請考慮到兩個交談; got 分叉電子郵件交談比方說，有人回應電子郵件不是最新的交談中讓交談中的最後兩個電子郵件兩者都有唯一的內容。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-117">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="8d1b6-118">Outlook 會仍組成群組加入單一對話; 電子郵件閱讀的最後一個電子郵件會表示缺少倒數第二個電子郵件，也包含唯一內容的內容。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-118">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="8d1b6-119">因為電子郵件執行緒剖析出每封電子郵件到個別元件，並比較它們，電子郵件執行緒會將標記這兩個最後兩個電子郵件為 inclusives，確保，您就不會遺漏任何內容，只要讀取所有的電子郵件標示為 （含）。</span><span class="sxs-lookup"><span data-stu-id="8d1b6-119">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>