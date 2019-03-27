---
title: 原則與防護組合的方式時郵件紅色標幟
description: 原則的套用，和電子郵件由 EOP，及/或 ATP 標記惡意程式碼、 垃圾郵件、 高信賴度垃圾郵件、 網路釣魚及大量時採取的動作。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365、 安全中心，ATP、 Windows Defender ATP、 Office 365 ATP、 Azure ATP
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7aa0f89eed379273cb069cd65c083749a9552e91
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30926463"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a><span data-ttu-id="1cdc2-104">哪些原則適用於何時多個保護方法與在您的電子郵件上執行的偵測掃描</span><span class="sxs-lookup"><span data-stu-id="1cdc2-104">What policy applies when multiple protection methods and detection scans run on your email</span></span>

<span data-ttu-id="1cdc2-105">有可能，傳入的郵件可能由多個表單的保護 (例如這兩個 EOP*和*ATP)，加上標幟並多個偵測掃描 （例如垃圾郵件*和*網路釣魚）。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-105">Potentially, your incoming mail may be flagged by multiple forms of protection (for example both EOP *and* ATP), and multiple detection scans (such as spam *and* phishing).</span></span> <span data-ttu-id="1cdc2-106">這是可行的因為有 ATP 防網路釣魚原則 ATP 的客戶，與 EOP 客戶的 EOP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-106">This is possible because there are ATP Anti-phishing policies for ATP customers, and EOP Anti-phishing policies for EOP customers.</span></span> <span data-ttu-id="1cdc2-107">這也表示郵件可能會瀏覽多個偵測掃描惡意程式碼、 網路釣魚，與使用者模擬，例如。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-107">This also means the message may navigate multiple detection scans for malware, phishing, and user-impersonation, for example.</span></span> <span data-ttu-id="1cdc2-108">指定所有此活動，可能會有哪些原則適用於某些混淆。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-108">Given all this activity, there may be some confusion as to which policy applies.</span></span>

<span data-ttu-id="1cdc2-109">一般而言，在**CAT （類別）** 屬性中的**X Forefront-反垃圾郵件報告**標頭中識別套用至郵件的原則。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-109">In general, the policy applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="1cdc2-110">如果您有多個反網路釣魚原則時，會套用在最高優先順序的一個。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-110">If you have multiple Anti-phishing policies, the one at the highest priority will apply.</span></span>

<span data-ttu-id="1cdc2-111">下列的原則套用到_所有組織_。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-111">The Policies below apply to _all organizations_.</span></span>

|<span data-ttu-id="1cdc2-112">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1cdc2-112">Priority</span></span> |<span data-ttu-id="1cdc2-113">原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-113">Policy</span></span>  |<span data-ttu-id="1cdc2-114">類別</span><span class="sxs-lookup"><span data-stu-id="1cdc2-114">Category</span></span>  |<span data-ttu-id="1cdc2-115">受管理的位置</span><span class="sxs-lookup"><span data-stu-id="1cdc2-115">Where Managed</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="1cdc2-116">1</span><span class="sxs-lookup"><span data-stu-id="1cdc2-116">1</span></span>     | <span data-ttu-id="1cdc2-117">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="1cdc2-117">Malware</span></span>      | <span data-ttu-id="1cdc2-118">MALW</span><span class="sxs-lookup"><span data-stu-id="1cdc2-118">MALW</span></span>      | <span data-ttu-id="1cdc2-119">惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-119">Malware policy</span></span>   |
|<span data-ttu-id="1cdc2-120">2</span><span class="sxs-lookup"><span data-stu-id="1cdc2-120">2</span></span>     | <span data-ttu-id="1cdc2-121">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="1cdc2-121">Phishing</span></span>     | <span data-ttu-id="1cdc2-122">PHSH</span><span class="sxs-lookup"><span data-stu-id="1cdc2-122">PHSH</span></span>     | <span data-ttu-id="1cdc2-123">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-123">Configure your spam filter policies</span></span>     |
|<span data-ttu-id="1cdc2-124">3</span><span class="sxs-lookup"><span data-stu-id="1cdc2-124">3</span></span>     | <span data-ttu-id="1cdc2-125">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1cdc2-125">High confidence spam</span></span>      | <span data-ttu-id="1cdc2-126">HSPM</span><span class="sxs-lookup"><span data-stu-id="1cdc2-126">HSPM</span></span>        | <span data-ttu-id="1cdc2-127">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-127">Configure your spam filter policies</span></span>        |
|<span data-ttu-id="1cdc2-128">4</span><span class="sxs-lookup"><span data-stu-id="1cdc2-128">4</span></span>     | <span data-ttu-id="1cdc2-129">詐騙</span><span class="sxs-lookup"><span data-stu-id="1cdc2-129">Spoofing</span></span>        | <span data-ttu-id="1cdc2-130">SPOOF</span><span class="sxs-lookup"><span data-stu-id="1cdc2-130">SPOOF</span></span>        | <span data-ttu-id="1cdc2-131">反網路釣魚原則，詐騙智慧</span><span class="sxs-lookup"><span data-stu-id="1cdc2-131">Anti-phishing policy, spoof intelligence</span></span>        |
|<span data-ttu-id="1cdc2-132">5</span><span class="sxs-lookup"><span data-stu-id="1cdc2-132">5</span></span>     | <span data-ttu-id="1cdc2-133">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1cdc2-133">Spam</span></span>         | <span data-ttu-id="1cdc2-134">SPM</span><span class="sxs-lookup"><span data-stu-id="1cdc2-134">SPM</span></span>         | <span data-ttu-id="1cdc2-135">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-135">Configure your spam filter policies</span></span>         |
|<span data-ttu-id="1cdc2-136">6</span><span class="sxs-lookup"><span data-stu-id="1cdc2-136">6</span></span>     | <span data-ttu-id="1cdc2-137">大量</span><span class="sxs-lookup"><span data-stu-id="1cdc2-137">Bulk</span></span>         | <span data-ttu-id="1cdc2-138">BULK</span><span class="sxs-lookup"><span data-stu-id="1cdc2-138">BULK</span></span>        | <span data-ttu-id="1cdc2-139">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-139">Configure your spam filter policies</span></span>         |

<span data-ttu-id="1cdc2-140">此外，這些原則套用至_組織的 ATP_。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-140">In addition, these policies apply to _organizations with ATP_.</span></span>

|<span data-ttu-id="1cdc2-141">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1cdc2-141">Priority</span></span> |<span data-ttu-id="1cdc2-142">原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-142">Policy</span></span>  |<span data-ttu-id="1cdc2-143">類別</span><span class="sxs-lookup"><span data-stu-id="1cdc2-143">Category</span></span>  |<span data-ttu-id="1cdc2-144">受管理的位置</span><span class="sxs-lookup"><span data-stu-id="1cdc2-144">Where Managed</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="1cdc2-145">7</span><span class="sxs-lookup"><span data-stu-id="1cdc2-145">7</span></span>     | <span data-ttu-id="1cdc2-146">網域冒充</span><span class="sxs-lookup"><span data-stu-id="1cdc2-146">Domain Impersonation</span></span>         | <span data-ttu-id="1cdc2-147">DIMP</span><span class="sxs-lookup"><span data-stu-id="1cdc2-147">DIMP</span></span>         | <span data-ttu-id="1cdc2-148">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-148">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>        |
|<span data-ttu-id="1cdc2-149">8</span><span class="sxs-lookup"><span data-stu-id="1cdc2-149">8</span></span>     | <span data-ttu-id="1cdc2-150">使用者冒充</span><span class="sxs-lookup"><span data-stu-id="1cdc2-150">User Impersonation</span></span>        | <span data-ttu-id="1cdc2-151">UIMP</span><span class="sxs-lookup"><span data-stu-id="1cdc2-151">UIMP</span></span>         | <span data-ttu-id="1cdc2-152">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-152">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>         |

<span data-ttu-id="1cdc2-153">例如，如果您有兩個原則：</span><span class="sxs-lookup"><span data-stu-id="1cdc2-153">As an example, if you have two policies:</span></span>

|<span data-ttu-id="1cdc2-154">原則</span><span class="sxs-lookup"><span data-stu-id="1cdc2-154">Policy</span></span>  |<span data-ttu-id="1cdc2-155">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1cdc2-155">Priority</span></span>  |<span data-ttu-id="1cdc2-156">使用者/網域冒充</span><span class="sxs-lookup"><span data-stu-id="1cdc2-156">User/Domain Impersonation</span></span>  |<span data-ttu-id="1cdc2-157">反詐騙</span><span class="sxs-lookup"><span data-stu-id="1cdc2-157">Anti-spoofing</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="1cdc2-158">A</span><span class="sxs-lookup"><span data-stu-id="1cdc2-158">A</span></span>     | <span data-ttu-id="1cdc2-159">1</span><span class="sxs-lookup"><span data-stu-id="1cdc2-159">1</span></span>        | <span data-ttu-id="1cdc2-160">開啟</span><span class="sxs-lookup"><span data-stu-id="1cdc2-160">On</span></span>        |<span data-ttu-id="1cdc2-161">關閉</span><span class="sxs-lookup"><span data-stu-id="1cdc2-161">Off</span></span>         |
|<span data-ttu-id="1cdc2-162">B</span><span class="sxs-lookup"><span data-stu-id="1cdc2-162">B</span></span>     | <span data-ttu-id="1cdc2-163">2</span><span class="sxs-lookup"><span data-stu-id="1cdc2-163">2</span></span>        | <span data-ttu-id="1cdc2-164">關閉</span><span class="sxs-lookup"><span data-stu-id="1cdc2-164">Off</span></span>        | <span data-ttu-id="1cdc2-165">開啟</span><span class="sxs-lookup"><span data-stu-id="1cdc2-165">On</span></span>        |

<span data-ttu-id="1cdc2-166">如果郵件有已識別為_使用者模擬_和_詐騙_（請參閱反詐騙於上表中），而且相同一組使用者原則的範圍限於原則 B，然後郵件會加上標幟，並將視為_詐騙_，但不是正確巨集指令會套用於自反詐騙已關閉，因為**詐騙執行於優先順序較高 (4) 與使用者模擬 (8)**。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-166">If a message comes in identified as both _user impersonation_ and _spoofing_ (see anti-spoofing in the table above), and the same set of users scoped to policy A is scoped to policy B, then the message is flagged and treated as a _spoof_, but no action is applied since Anti-spoofing is turned off, and because **spoof runs at a higher priority (4) than User Impersonation (8)**.</span></span>

<span data-ttu-id="1cdc2-167">若要讓其他類型的網路釣魚原則套用，您將需要調整的各種不同的原則套用到使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="1cdc2-167">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies apply to.</span></span>



