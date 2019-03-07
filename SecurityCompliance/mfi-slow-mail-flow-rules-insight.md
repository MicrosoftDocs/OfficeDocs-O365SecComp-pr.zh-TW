---
title: 緩慢的郵件流程規則深入解析
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 系統管理員可以了解在 Office 365 安全性 & 合規性中心中的郵件流程儀表板中緩慢的郵件流程規則深入解析。
ms.openlocfilehash: 8188ee0da15ac337499866783ca4f2d893062d5b
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454875"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="1d45e-103">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="1d45e-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="1d45e-104">無效率的郵件流程規則 （也稱為傳輸規則） 可能會導致為您的組織的郵件流程延遲。</span><span class="sxs-lookup"><span data-stu-id="1d45e-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="1d45e-105">此深入了解報告貴組織的郵件流程造成影響的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="1d45e-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="1d45e-106">以下是這些類型的規則的範例：</span><span class="sxs-lookup"><span data-stu-id="1d45e-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="1d45e-107">使用大型群組**成員**的條件。</span><span class="sxs-lookup"><span data-stu-id="1d45e-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="1d45e-108">使用複雜的規則運算式 (regex) 模式比對的條件。</span><span class="sxs-lookup"><span data-stu-id="1d45e-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="1d45e-109">使用內容檢查附件中的條件。</span><span class="sxs-lookup"><span data-stu-id="1d45e-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="1d45e-110">深入了解可協助您識別並微調郵件流程規則來協助減少郵件流程延遲。</span><span class="sxs-lookup"><span data-stu-id="1d45e-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![緩慢的郵件流程規則深入了解在 Office 365 安全性 & 合規性中心中的郵件流程儀表板](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="1d45e-112">當您按一下 [**檢視詳細資料**時，彈出式視窗窗格會顯示您可以在此檢閱規則。</span><span class="sxs-lookup"><span data-stu-id="1d45e-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="1d45e-113">在彈出式視窗窗格中，也可以按一下 [**檢視範例郵件**若要查看何種郵件受影響的規則。</span><span class="sxs-lookup"><span data-stu-id="1d45e-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![彈出式視窗窗格中按一下 [檢視詳細資料]，在 [郵件流程儀表板中緩慢的郵件流程規則深入解析後](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)
