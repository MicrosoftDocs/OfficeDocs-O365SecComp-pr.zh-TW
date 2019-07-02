---
title: 在高級 eDiscovery 中設定律師-用戶端許可權偵測
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 加入宣告並使用律師-用戶端許可權偵測模型, 以在檢查高級 eDiscovery 案例中的內容時, 使用具有許可權內容的機器學習式偵測。
ms.openlocfilehash: 16a6a215484c35d20fbe071cac033133270b7ea6
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703860"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="228fd-103">在高級 eDiscovery 中設定律師-用戶端許可權偵測</span><span class="sxs-lookup"><span data-stu-id="228fd-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="228fd-104">任何 eDiscovery 程式的審查階段的主要和成本高的層面, 就是檢查檔中的許可權內容。</span><span class="sxs-lookup"><span data-stu-id="228fd-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="228fd-105">高級 eDiscovery 提供電腦對許可權內容的瞭解式偵測, 讓此程式的效率更高。</span><span class="sxs-lookup"><span data-stu-id="228fd-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="228fd-106">這項功能稱為「*律師-用戶端許可權偵測*」。</span><span class="sxs-lookup"><span data-stu-id="228fd-106">This feature is called *attorney-client privilege detection*.</span></span>

> [!NOTE]
> <span data-ttu-id="228fd-107">您必須先選擇「律師-用戶端」的許可權偵測模型, 才能使用它。</span><span class="sxs-lookup"><span data-stu-id="228fd-107">You must opt in to the attorney-client privilege detection model before you can use it.</span></span> <span data-ttu-id="228fd-108">請參閱[步驟 1](#step-1-opt-in-to-attorney-client-privilege-detection)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="228fd-108">See [Step 1](#step-1-opt-in-to-attorney-client-privilege-detection) for instructions.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="228fd-109">它如何運作？</span><span class="sxs-lookup"><span data-stu-id="228fd-109">How does it work?</span></span>

<span data-ttu-id="228fd-110">一旦啟用律師-用戶端許可權偵測, 當您分析考核集中[的資料](analyzing-data-in-review-set.md)時, 律師-用戶端的許可權偵測模型將會處理審閱集中的所有檔。</span><span class="sxs-lookup"><span data-stu-id="228fd-110">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="228fd-111">模型會尋找兩件事:</span><span class="sxs-lookup"><span data-stu-id="228fd-111">The model looks for two things:</span></span>

- <span data-ttu-id="228fd-112">許可權內容–模型使用機器學習來判斷檔中包含法律的內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="228fd-112">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="228fd-113">參與者–作為設定律師-用戶端許可權偵測的一部分, 您必須提交您組織的律師清單。</span><span class="sxs-lookup"><span data-stu-id="228fd-113">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="228fd-114">然後, 模型會將檔的參與者與律師清單進行比較, 以判斷檔是否至少有一個律師參與者。</span><span class="sxs-lookup"><span data-stu-id="228fd-114">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="228fd-115">模型會為每個檔產生下列三個屬性:</span><span class="sxs-lookup"><span data-stu-id="228fd-115">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="228fd-116">**AttorneyClientPrivilegeScore** –檔本質上為法律的可能性。分數的值介於**0**和**1**之間。</span><span class="sxs-lookup"><span data-stu-id="228fd-116">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="228fd-117">**HasAttorney** –如果其中一個檔參與者列出于律師清單, 則此屬性會設為**true** 。否則, 值為**false**。</span><span class="sxs-lookup"><span data-stu-id="228fd-117">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="228fd-118">如果您的組織未上傳律師清單, 則此值也會設為**false** 。</span><span class="sxs-lookup"><span data-stu-id="228fd-118">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="228fd-119">**IsPrivilege** –如果**AttorneyClientPrivilegeScore**的值高於臨界值*或*檔有律師參與者, 則此屬性會設定為**true** 。否則, 此值會設為**false**。</span><span class="sxs-lookup"><span data-stu-id="228fd-119">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="228fd-120">這些屬性 (及其對應值) 會新增至審閱集中檔的檔案中繼資料中, 如下列螢幕擷取畫面所示:</span><span class="sxs-lookup"><span data-stu-id="228fd-120">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![律師-檔案中繼資料中顯示的用戶端許可權屬性](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="228fd-122">這三個屬性也可在檢查集中搜尋。</span><span class="sxs-lookup"><span data-stu-id="228fd-122">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="228fd-123">如需詳細資訊, 請參閱[查詢評審集中的資料](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="228fd-123">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="228fd-124">設定律師-用戶端許可權偵測模型</span><span class="sxs-lookup"><span data-stu-id="228fd-124">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="228fd-125">若要啟用律師-用戶端許可權偵測模型, 您的組織必須加入宣告, 然後上傳律師清單。</span><span class="sxs-lookup"><span data-stu-id="228fd-125">To enable the attorney-client privilege detection model, your organization has to opt-in and then upload an attorney list.</span></span>

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a><span data-ttu-id="228fd-126">步驟 1: 加入宣告律師-用戶端許可權偵測</span><span class="sxs-lookup"><span data-stu-id="228fd-126">Step 1: Opt-in to attorney-client privilege detection</span></span>

<span data-ttu-id="228fd-127">如先前所述, 律師-用戶端許可權偵測模型是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="228fd-127">As previously stated, the attorney-client privilege detection model is in Preview.</span></span> <span data-ttu-id="228fd-128">因此, 在您組織 eDiscovery 系統管理員中的人員 (eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組成員), 必須選擇將模型提供給您的高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="228fd-128">Therefore a person in your organization eDiscovery Administrator (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must opt in to make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="228fd-129">在安全性 & 合規性中心內, 移至**eDiscovery > Advanced ediscovery**。</span><span class="sxs-lookup"><span data-stu-id="228fd-129">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="228fd-130">在 [**高級 eDiscovery** ] 首頁上, 按一下 [**設定**] 磚中的 [設定**實驗的功能**]。</span><span class="sxs-lookup"><span data-stu-id="228fd-130">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**.</span></span>

   ![按一下 [設定實驗功能]](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="228fd-132">在 [**實驗功能**] 索引標籤上, 按一下 [**管理律師-用戶端許可權] 設定**。</span><span class="sxs-lookup"><span data-stu-id="228fd-132">On the **Experimental features** tab, click **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="228fd-133">在 [**律師-用戶端許可權**] 飛入頁面上, 按一下切換以開啟功能, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="228fd-133">On the **Attorney-client privilege** flyout page, click the toggle to turn on the feature and then click **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="228fd-134">步驟 2: 上傳律師清單 (選用)</span><span class="sxs-lookup"><span data-stu-id="228fd-134">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="228fd-135">若要充分利用律師用戶端的許可權偵測模型, 並使用先前所述的\*\*\*\* **授權或可能的特權**偵測結果, 建議您上傳為您的組織運作的律師和法務人員。</span><span class="sxs-lookup"><span data-stu-id="228fd-135">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="228fd-136">若要上傳律師清單以供授權者-用戶端的許可權偵測模型使用:</span><span class="sxs-lookup"><span data-stu-id="228fd-136">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="228fd-137">建立 .csv 檔案 (不含標題列), 並將每個適當人員的電子郵件地址新增到個別的一行。</span><span class="sxs-lookup"><span data-stu-id="228fd-137">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="228fd-138">將此檔案儲存到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="228fd-138">Save this file to your local computer.</span></span>

2. <span data-ttu-id="228fd-139">在 [ **Advanced eDiscovery** ] 首頁上, 按一下 [**設定**] 磚中的 [設定**實驗功能**], 然後按一下 [**管理律師-用戶端許可權] 設定**。</span><span class="sxs-lookup"><span data-stu-id="228fd-139">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**, and then click **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="228fd-140">隨即會顯示 [**律師-用戶端許可權**] 頁面, 並開啟 [**律師-用戶端許可權偵測**] 切換功能。</span><span class="sxs-lookup"><span data-stu-id="228fd-140">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![律師-用戶端許可權飛出頁面](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="228fd-142">按一下 **[流覽]** , 然後尋找並選取您在步驟1中建立的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="228fd-142">Click **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="228fd-143">按一下 [**儲存**] 以上傳律師清單。</span><span class="sxs-lookup"><span data-stu-id="228fd-143">Click **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="228fd-144">使用律師-用戶端許可權偵測模型</span><span class="sxs-lookup"><span data-stu-id="228fd-144">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="228fd-145">請遵循本節中的步驟, 針對審閱集中的檔使用律師-用戶端許可權偵測。</span><span class="sxs-lookup"><span data-stu-id="228fd-145">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="228fd-146">步驟 1: 建立具有律師-用戶端許可權偵測模型的智慧標籤群組</span><span class="sxs-lookup"><span data-stu-id="228fd-146">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="228fd-147">在您的審查程式中查看律師-用戶端許可權偵測結果的其中一個主要方式, 就是使用智慧標籤群組。</span><span class="sxs-lookup"><span data-stu-id="228fd-147">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="228fd-148">智慧標籤群組會指出律師費-用戶端許可權偵測的結果, 並在智慧標籤群組中的標記旁邊以行顯示結果。</span><span class="sxs-lookup"><span data-stu-id="228fd-148">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="228fd-149">這可讓您在檔審閱期間快速找出可能具有特權的檔。</span><span class="sxs-lookup"><span data-stu-id="228fd-149">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="228fd-150">此外, 您也可以使用智慧標籤群組中的標記, 將檔標記為 [有許可權] 或 [非特權]。</span><span class="sxs-lookup"><span data-stu-id="228fd-150">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="228fd-151">如需有關智慧標籤的詳細資訊, 請參閱[在高級 eDiscovery 中設定智慧標籤](smart-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="228fd-151">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="228fd-152">在包含您在步驟1中分析之檔的審閱集中, 按一下 [**管理審閱集**], 然後按一下 [**管理標記**]。</span><span class="sxs-lookup"><span data-stu-id="228fd-152">In the review set that contains the documents that you analyzed in Step 1, click **Manage review set** and then click **Manage tags**.</span></span>
 
2. <span data-ttu-id="228fd-153">在 [**標記**] 下, 按一下 [**新增群組**] 旁的下拉式清單, 然後按一下 [**新增智慧標籤群組**]。</span><span class="sxs-lookup"><span data-stu-id="228fd-153">Under **Tags**, click the pull-down next to **Add group** and then click **Add smart tag group**.</span></span>

   ![按一下 [新增智慧標籤群組]](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="228fd-155">在 [**選擇智慧標籤的模型**] 頁面上, 按一下 [在**律師-用戶端許可權**] 旁的 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="228fd-155">On the **Choose a model for your smart tag** page, click **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="228fd-156">隨即會顯示名為「**律師-用戶端」許可權**的標記群組。</span><span class="sxs-lookup"><span data-stu-id="228fd-156">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="228fd-157">它包含兩個名為**正值**和**負值**的子標記, 這會對應至模型產生的可能結果。</span><span class="sxs-lookup"><span data-stu-id="228fd-157">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![律師-用戶端許可權智慧標籤群組](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="228fd-159">請視需要重新命名標記群組和標記。</span><span class="sxs-lookup"><span data-stu-id="228fd-159">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="228fd-160">例如, 您可以將**肯定**的重新命名為 [**許可權**] 和 [**否定**] 不需要的**許可權**。</span><span class="sxs-lookup"><span data-stu-id="228fd-160">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="228fd-161">步驟 2: 分析審閱集</span><span class="sxs-lookup"><span data-stu-id="228fd-161">Step 2: Analyze a review set</span></span>

<span data-ttu-id="228fd-162">當您分析審閱集中的檔時, 也會執行律師-用戶端許可權偵測模型, 以及對應的屬性 (說明[其運作方式](#how-does-it-work)) 將新增至審閱集中的每一份檔。</span><span class="sxs-lookup"><span data-stu-id="228fd-162">When you analyze the documents in a review set, the attorney-client privilege detection model will also be run and the corresponding properties (described in[How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="228fd-163">如需分析 [查看] 集中資料的詳細資訊, 請參閱[在高級 eDiscovery 中分析審閱集中的資料](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="228fd-163">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="228fd-164">步驟 3: 使用智慧標籤群組以查看許可權內容</span><span class="sxs-lookup"><span data-stu-id="228fd-164">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="228fd-165">在分析檢查集並設定智慧標籤之後, 下一步是審閱檔。</span><span class="sxs-lookup"><span data-stu-id="228fd-165">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="228fd-166">如果模型判定檔有可能有許可權, 則 [**標記] 面板**中對應的智慧標籤將會指出由「律師-用戶端」許可權偵測所產生的下列結果:</span><span class="sxs-lookup"><span data-stu-id="228fd-166">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="228fd-167">如果檔中有可能是合法的內容, 則標籤的**合法內容**會顯示在對應的智慧標籤旁 (在此例中為預設的**正數**標記)。</span><span class="sxs-lookup"><span data-stu-id="228fd-167">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="228fd-168">如果檔有在您組織的律師清單中找到的參與者, 則標籤**律師**會顯示在對應的智慧標籤旁 (在此情況下, 也是預設的**正**標籤)。</span><span class="sxs-lookup"><span data-stu-id="228fd-168">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="228fd-169">如果檔中的內容可能是合法的,*且*在律師清單中找到了參與者, 則會顯示**法律內容**和**律師**標籤。</span><span class="sxs-lookup"><span data-stu-id="228fd-169">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="228fd-170">如果模型決定檔不包含具有法律性質的內容, 或未包含律師清單中的參與者, 則 [標記] 面板中都不會顯示任何標籤。</span><span class="sxs-lookup"><span data-stu-id="228fd-170">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="228fd-171">例如, 下列螢幕擷取畫面顯示兩份檔;第一個專案包含合法的內容, 並有在律師清單中找到的參與者。第二個不包含任何一種, 因此不會顯示任何標籤。</span><span class="sxs-lookup"><span data-stu-id="228fd-171">For example, the following screenshots show two documents; the first one contains content that is legal in nature and has a participant found in the list of attorneys; the second contains neither and therefore doesn't display any labels.</span></span>

![含律師和法律內容標籤的檔](../media/AeDTaggingPanelLegalContentAttorney.png)

![不含任何標籤的檔](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="228fd-174">檢查檔是否包含許可權內容之後, 您可以使用適當的標記來標記檔。</span><span class="sxs-lookup"><span data-stu-id="228fd-174">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>