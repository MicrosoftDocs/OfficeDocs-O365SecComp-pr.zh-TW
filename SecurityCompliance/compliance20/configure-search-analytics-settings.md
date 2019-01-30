---
title: 設定搜尋和分析設定
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9528a4bcfaa77f2e232b25d03eda46cce42ebb9
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607559"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="c0472-102">設定搜尋和分析設定</span><span class="sxs-lookup"><span data-stu-id="c0472-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="c0472-103">接近重複項目及電子郵件超執行緒</span><span class="sxs-lookup"><span data-stu-id="c0472-103">Near duplicates and email threading</span></span>

<span data-ttu-id="c0472-104">此區段中，您可以設定的參數重複資料偵測、 接近重複資料偵測、 和電子郵件執行緒。</span><span class="sxs-lookup"><span data-stu-id="c0472-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="c0472-p101">啟用/停用： 包括重複資料偵測、 接近重複資料偵測、 和電子郵件執行緒分析流程啟用時的一部分。因為它們建置彼此，您必須啟用所有的或停用所有。</span><span class="sxs-lookup"><span data-stu-id="c0472-p101">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled. Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="c0472-107">臨界值： 如果兩個文件的相似性層級超出臨界值，這些皆會置中接近重複的設定相同。</span><span class="sxs-lookup"><span data-stu-id="c0472-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="c0472-p102">根據預設隱藏重複項目： 在此設定時，會在設定預設的工作中套用隱藏重複文件的篩選器。可以在必要時設定工作中手動移除篩選。</span><span class="sxs-lookup"><span data-stu-id="c0472-p102">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default. The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="c0472-p103">字數目最小值/上限： 接近重複項目和電子郵件超執行緒會執行僅在字數目最小值和最單字的最大數目至少要有的文件。如需詳細資訊，請參閱[接近重複資料偵測](near-duplicates.md)和[電子郵件執行緒](email-threading.md)。</span><span class="sxs-lookup"><span data-stu-id="c0472-p103">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words. For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="c0472-112">主題</span><span class="sxs-lookup"><span data-stu-id="c0472-112">Themes</span></span>

<span data-ttu-id="c0472-113">此區段中，您可以設定為佈景主題的參數。</span><span class="sxs-lookup"><span data-stu-id="c0472-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="c0472-114">啟用/停用： 包括叢集分析流程啟用時的一部分的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="c0472-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="c0472-p104">動態動態調整的佈景主題數目上限： 在某些情況下，沒有足夠的文件產生所需的佈景主題數目。如果開啟此設定，然後而不是嘗試強制所需的數目上限佈景主題，系統會調整佈景主題數目上限動態。</span><span class="sxs-lookup"><span data-stu-id="c0472-p104">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes. If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="c0472-117">佈景主題數目上限： 想要的佈景主題數目</span><span class="sxs-lookup"><span data-stu-id="c0472-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="c0472-118">包含佈景主題中的數字： 啟用時，它會加上號碼中的產生佈景主題時。</span><span class="sxs-lookup"><span data-stu-id="c0472-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="c0472-119">光學字元辨識 (OCR)</span><span class="sxs-lookup"><span data-stu-id="c0472-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="c0472-120">當開啟此設定時，會執行 OCR 上以便他們可以搜尋 ingested 分割工作的圖像。</span><span class="sxs-lookup"><span data-stu-id="c0472-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="c0472-121">搜尋時忽略的文字</span><span class="sxs-lookup"><span data-stu-id="c0472-121">Ignore text</span></span>

<span data-ttu-id="c0472-p105">有其中某些敘述性文字會降低分析，例如冗長的免責聲明取得新增至特定電子郵件的電子郵件的內容不論品質的執行個體。如果您已清楚這種情況下，您可以藉由指定的文字 （支援 RegEx） 和其從分析排除此文字的文字排除的模組。</span><span class="sxs-lookup"><span data-stu-id="c0472-p105">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email. If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>