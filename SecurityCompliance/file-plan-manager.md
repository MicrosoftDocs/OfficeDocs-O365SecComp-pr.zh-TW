---
title: 檔案計劃管理員的概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 檔案計劃管理員提供對於保留標籤和原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。
ms.openlocfilehash: 4feacf20444591f6da2d55a928a81e86b56c5d9a
ms.sourcegitcommit: 9f34ace6bbe3d5e07e24ebaae96613750869cddf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2018
ms.locfileid: "25019274"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="34799-103">檔案計劃管理員的概觀</span><span class="sxs-lookup"><span data-stu-id="34799-103">Overview of file plan manager</span></span>

<span data-ttu-id="34799-104">檔案計劃管理員提供對於保留標籤和原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。</span><span class="sxs-lookup"><span data-stu-id="34799-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![檔案計劃頁面](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a><span data-ttu-id="34799-106">重要：此功能目前僅作為 Office 365 Preview 程式的一部分</span><span class="sxs-lookup"><span data-stu-id="34799-106">Important: This feature is currently available only as part of the Office 365 Preview program</span></span>

<span data-ttu-id="34799-107">如果貴組織已註冊 Office 365 Preview 程式，則您會在您的租用戶中看到這項功能。</span><span class="sxs-lookup"><span data-stu-id="34799-107">You will see this feature in your tenant only if your organization has enrolled in the Office 365 Preview program.</span></span>

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="34799-108">存取檔案計劃管理員</span><span class="sxs-lookup"><span data-stu-id="34799-108">Accessing file plan manager</span></span>

<span data-ttu-id="34799-109">存取檔案計劃管理員有兩個需求，需求如下：</span><span class="sxs-lookup"><span data-stu-id="34799-109">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="34799-110">Office 365 企業版 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="34799-110">An Office 365 Enterprise E5 subscription with user licenses.</span></span>
- <span data-ttu-id="34799-111">使用者已獲指派「安全性與合規性中心」的下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="34799-111">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="34799-112">保留管理員</span><span class="sxs-lookup"><span data-stu-id="34799-112">Retention Manager</span></span>
    - <span data-ttu-id="34799-113">僅檢視保留管理員</span><span class="sxs-lookup"><span data-stu-id="34799-113">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="34799-114">瀏覽您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="34799-114">Navigating your file plan</span></span>

<span data-ttu-id="34799-115">檔案計劃管理員可讓您更輕鬆地從單一檢視，查看所有保留標籤和原則及其設定。</span><span class="sxs-lookup"><span data-stu-id="34799-115">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="34799-116">請注意，在檔案計劃外部所建立的保留標籤可以在檔案計劃中使用，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="34799-116">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="34799-117">在 [檔案計劃標籤]\*\*\*\* 索引標籤上，下列額外資訊和功能可供使用：</span><span class="sxs-lookup"><span data-stu-id="34799-117">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="34799-118">標籤設定資料行</span><span class="sxs-lookup"><span data-stu-id="34799-118">Label settings columns</span></span>
 
- <span data-ttu-id="34799-p101">[根據]\*\*\*\* 會識別觸發程序類型，該觸發程序會開始保留期間。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="34799-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="34799-121">事件</span><span class="sxs-lookup"><span data-stu-id="34799-121">Event</span></span>
    - <span data-ttu-id="34799-122">建立時機</span><span class="sxs-lookup"><span data-stu-id="34799-122">When created</span></span>
    - <span data-ttu-id="34799-123">上次修改時間</span><span class="sxs-lookup"><span data-stu-id="34799-123">When last modified</span></span>
    - <span data-ttu-id="34799-124">套用標籤時機</span><span class="sxs-lookup"><span data-stu-id="34799-124">When labeled</span></span>
- <span data-ttu-id="34799-p102">[記錄]\*\*\*\* 會識別項目是否會在套用標籤時變成宣告的記錄。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="34799-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="34799-127">否</span><span class="sxs-lookup"><span data-stu-id="34799-127">No</span></span>
    - <span data-ttu-id="34799-128">是</span><span class="sxs-lookup"><span data-stu-id="34799-128">Yes</span></span>
    - <span data-ttu-id="34799-129">Yes(Regulatory)</span><span class="sxs-lookup"><span data-stu-id="34799-129">Yes(Regulatory)</span></span>
- <span data-ttu-id="34799-p103">[保留]\*\*\*\* 會識別保留類型。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="34799-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="34799-132">保留</span><span class="sxs-lookup"><span data-stu-id="34799-132">Keep</span></span>
    - <span data-ttu-id="34799-133">保留與刪除</span><span class="sxs-lookup"><span data-stu-id="34799-133">Keep and delete</span></span>
    - <span data-ttu-id="34799-134">刪除</span><span class="sxs-lookup"><span data-stu-id="34799-134">Delete</span></span>
- <span data-ttu-id="34799-p104">[處置]\*\*\*\* 會識別保留期間結束時內容會發生什麼情形。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="34799-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="34799-137">Null</span><span class="sxs-lookup"><span data-stu-id="34799-137">Null</span></span>
    - <span data-ttu-id="34799-138">不執行任何動作</span><span class="sxs-lookup"><span data-stu-id="34799-138">No action necessary.</span></span>
    - <span data-ttu-id="34799-139">自動刪除</span><span class="sxs-lookup"><span data-stu-id="34799-139">Auto-delete</span></span>
    - <span data-ttu-id="34799-140">需要檢閱 (也稱為處置檢閱)</span><span class="sxs-lookup"><span data-stu-id="34799-140">Review required (aka Disposition review)</span></span>

![檔案計劃中的標籤設定](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="34799-142">標籤檔案計劃描述元資料行</span><span class="sxs-lookup"><span data-stu-id="34799-142">Label file plan descriptors columns</span></span>

<span data-ttu-id="34799-p105">您現在可以在保留標籤組態中包含詳細資訊。將檔案計劃描述元插入標籤可以改善檔案計劃的管理性和組織。</span><span class="sxs-lookup"><span data-stu-id="34799-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="34799-p106">為了讓您開始使用，檔案計劃管理員會為以下項目提供現成的值：函式/部門、分類、授權類型和佈建/引文。您可以在建立或編輯保留標籤時新增檔案計劃描述元值。</span><span class="sxs-lookup"><span data-stu-id="34799-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="34799-147">以下是建立或編輯保留標籤時的檔案計劃描述元步驟檢視。</span><span class="sxs-lookup"><span data-stu-id="34799-147">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![檔案計劃描述元](media/file-plan-descriptors.png)

<span data-ttu-id="34799-149">以下是檔案計劃管理員的標籤索引標籤上，檔案計劃描述元的檢視。</span><span class="sxs-lookup"><span data-stu-id="34799-149">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="34799-151">從檔案計劃匯出標籤</span><span class="sxs-lookup"><span data-stu-id="34799-151">Export labels out of your file plan</span></span>

<span data-ttu-id="34799-152">您可以從檔案計劃管理員將所有保留標籤的詳細資料匯出至 .csv 檔案，以協助您加速與貴組織中資料控管專案關係人進行的定期合規性檢閱。</span><span class="sxs-lookup"><span data-stu-id="34799-152">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="34799-153">若要匯出所有保留標籤，請移至 [檔案計劃管理員]\*\*\*\* \> [檔案計劃動作]\*\*\*\* \> [匯出標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34799-153">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![匯出檔案計劃的選項](media/file-plan-export-labels-option.png)

<span data-ttu-id="34799-155">包含所有現有保留標籤的 \*.csv 檔案隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="34799-155">A \*.csv file containing all existing retention labels will open.</span></span>

![顯示所有保留標籤的 CSV 檔案](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="34799-157">將標籤匯入至您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="34799-157">Import labels into your file plan</span></span>

<span data-ttu-id="34799-158">您可以從檔案計劃管理員大量匯入新的標籤，以及修改現有的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="34799-158">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="34799-159">若要匯入新的保留標籤以及對現有保留標籤進行更新，請移至 [檔案計劃管理員]\*\*\*\* \> [檔案計劃動作]\*\*\*\* \> [匯入標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34799-159">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![匯入檔案計劃的選項](media/file-plan-import-labels-option.png)

![下載空白檔案計劃範本的選項](media/file-plan-blank-template-option.png)

<span data-ttu-id="34799-162">下載空白範本 (或從匯出目前的檔案計劃開始)。</span><span class="sxs-lookup"><span data-stu-id="34799-162">Download a blank template (or start from an export of your current file plan).</span></span>

![在 Excel 中開啟空白檔案計劃範本](media/file-plan-blank-template.png)

<span data-ttu-id="34799-164">填入範本 (項目有效值的參考資訊即將推出)。</span><span class="sxs-lookup"><span data-stu-id="34799-164">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![已填入資訊的檔案計劃範本](media/file-plan-filled-out-template.png)

<span data-ttu-id="34799-166">上傳已填入資訊的範本，檔案計劃管理員會驗證項目並且顯示匯入統計資料。</span><span class="sxs-lookup"><span data-stu-id="34799-166">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![檔案計劃匯入統計資料](media/file-plan-import-statistics.png)

<span data-ttu-id="34799-168">匯入完成後，返回檔案計劃管理員，將新標籤指派給新的或現有的原則。</span><span class="sxs-lookup"><span data-stu-id="34799-168">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![發佈標籤的選項](media/file-plan-publish-labels-option.png)

