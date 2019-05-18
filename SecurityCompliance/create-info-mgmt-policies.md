---
title: 建立並套用的資訊管理原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
description: 資訊管理原則可讓貴組織控制多久要保留內容，以稽核人員用來做什麼內容，並加入條碼] 或 [文件的標籤。 原則可協助強制執行規範與法律和政府法規或內部商務程序。 身為管理員，您可以設定的原則來控制如何追蹤的文件，以及要保留的文件。
ms.openlocfilehash: 43a39b316f5c1e77ef9576324518dfe228ff35a6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151235"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="b4492-105">建立並套用的資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="b4492-105">Create and apply information management policies</span></span>

<span data-ttu-id="b4492-106">資訊管理原則可讓貴組織控制多久要保留內容，以稽核人員用來做什麼內容，並加入條碼] 或 [文件的標籤。</span><span class="sxs-lookup"><span data-stu-id="b4492-106">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="b4492-107">原則可協助強制執行規範與法律和政府法規或內部商務程序。</span><span class="sxs-lookup"><span data-stu-id="b4492-107">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="b4492-108">身為管理員，您可以設定的原則來控制如何追蹤的文件，以及要保留的文件。</span><span class="sxs-lookup"><span data-stu-id="b4492-108">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="b4492-109">您可以建立資訊管理原則，可在三個不同地點網站在階層中，從最大範圍以最窄：</span><span class="sxs-lookup"><span data-stu-id="b4492-109">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="b4492-110">建立要用於網站集合內的多個內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-110">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="b4492-111">建立網站內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-111">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="b4492-112">建立清單或文件庫的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-112">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="b4492-113">如需詳細資訊，請參閱 <<c0>的資訊管理原則簡介。</span><span class="sxs-lookup"><span data-stu-id="b4492-113">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="b4492-114">建立網站集合內的多個內容類型的原則</span><span class="sxs-lookup"><span data-stu-id="b4492-114">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="b4492-115"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-115"></span></span>

<span data-ttu-id="b4492-116">若要確保資訊原則會套用至特定類型的網站集合內的所有文件，請考慮建立網站集合層級的原則和稍後將原則套用至內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-116">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="b4492-117">這些稱為網站集合原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-117">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="b4492-118">在網站集合首頁\>**設定**![標題列上的 [SharePoint 2016 設定] 按鈕。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="b4492-118">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="b4492-119">\> [網站設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-119">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b4492-120">在 SharePoint 群組連接網站中，按一下 [**設定**] [**網站內容**]，，然後按一下 [**網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-120">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b4492-121">在 [網站設定] 頁面上的 [**網站集合管理**] 下\>**內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="b4492-121">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![在 [網站設定] 頁面上的內容類型原則範本連結](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="b4492-123">在 [原則] 頁面上\>**建立**。</span><span class="sxs-lookup"><span data-stu-id="b4492-123">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="b4492-124">輸入的名稱和描述原則] 中，然後寫入說明使用者的原則是用於簡短的原則陳述式。</span><span class="sxs-lookup"><span data-stu-id="b4492-124">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="b4492-125">在 [建立網站內容類型，以了解如何設定您想要與之原則關聯之的功能的原則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="b4492-125">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="b4492-126">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-126">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="b4492-127">建立網站內容類型的原則</span><span class="sxs-lookup"><span data-stu-id="b4492-127">Create a policy for a site content type</span></span>
<span data-ttu-id="b4492-128"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-128"></span></span>

<span data-ttu-id="b4492-129">新增資訊管理原則至內容類型可以輕易與多個清單或文件庫建立關聯的原則功能。</span><span class="sxs-lookup"><span data-stu-id="b4492-129">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="b4492-130">您可以選擇加入現有的資訊管理原則至內容類型或建立唯一原則專屬於個別的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-130">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="b4492-131">您也可以新增資訊管理原則至內容類型的特定清單。</span><span class="sxs-lookup"><span data-stu-id="b4492-131">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="b4492-132">這有將原則套用至該清單中所使用的內容類型的項目只的效果。</span><span class="sxs-lookup"><span data-stu-id="b4492-132">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="b4492-133">在網站集合首頁\>**設定**![標題列上的 [SharePoint 2016 設定] 按鈕。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="b4492-133">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="b4492-134">\> [網站設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-134">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b4492-135">在 SharePoint 群組連接網站中，按一下 [**設定**] [**網站內容**]，，然後按一下 [**網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-135">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b4492-136">在 [網站設定] 頁面的 [**網站設計工具庫**] 底下\>**網站內容類型**。</span><span class="sxs-lookup"><span data-stu-id="b4492-136">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![在 [網站設定] 頁面上的網站內容類型連結](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="b4492-138">在 [網站內容類型設定] 頁面上，選取您想要新增至原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-138">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="b4492-139">在 [網站內容類型] 頁面上的 [**設定**] 下\>**資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-139">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="b4492-140">在 [編輯原則] 頁面上輸入的名稱和描述原則] 中，然後寫入說明使用者的原則是針對的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="b4492-140">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="b4492-141">在下一個區段中，選取您想要新增至您的資訊管理原則的個別原則功能。</span><span class="sxs-lookup"><span data-stu-id="b4492-141">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![類型的內容的原則](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="b4492-143">若要指定的文件與受限於此原則的項目保留期間內，選擇 [**啟用保留**，然後指定保留期間，以及您想要的項目到期時，就會發生的動作。</span><span class="sxs-lookup"><span data-stu-id="b4492-143">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="b4492-144">若要指定保留期間</span><span class="sxs-lookup"><span data-stu-id="b4492-144">To specify a retention period</span></span>
    
||||||<span data-ttu-id="b4492-145">**1.**</span><span class="sxs-lookup"><span data-stu-id="b4492-145">**1.**</span></span>|<span data-ttu-id="b4492-146">\* \* 選擇 \* \*...新增的記錄保留階段 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b4492-146">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b4492-147">2.</span><span class="sxs-lookup"><span data-stu-id="b4492-147">2.</span></span>  <br/> | <span data-ttu-id="b4492-148">選取 [保留期間的選項，以指定當文件或項目設定為過期。</span><span class="sxs-lookup"><span data-stu-id="b4492-148">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="b4492-149">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="b4492-149">Do one of the following:</span></span>  <br/>  <span data-ttu-id="b4492-150">若要設定之下**事件**的日期屬性為基礎的到期日\>**此階段以關閉項目的日期屬性為基礎**，然後選取 [文件或項目動作 （例如，建立或修改） 並在此巨集指令 （之後的時間增量單位例如，天數、 月數或年數） 當您想要到期的項目。</span><span class="sxs-lookup"><span data-stu-id="b4492-150">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="b4492-151">若要使用自訂保留公式來決定到期日，請選擇 [**此伺服器上安裝自訂保留公式來設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-151">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="b4492-152">> [!NOTE]> 這個選項才可用如果由您的系統管理員已設定自訂的公式。</span><span class="sxs-lookup"><span data-stu-id="b4492-152">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="b4492-153">3.</span><span class="sxs-lookup"><span data-stu-id="b4492-153">3.</span></span>  <br/> |<span data-ttu-id="b4492-154">**啟動工作流程**] 選項是您要定義的原則清單、 文件庫或內容類型已有與它相關聯的工作流程時，才可以使用。</span><span class="sxs-lookup"><span data-stu-id="b4492-154">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="b4492-155">您接著會指定可從中選擇工作流程。</span><span class="sxs-lookup"><span data-stu-id="b4492-155">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-156">4.</span><span class="sxs-lookup"><span data-stu-id="b4492-156">4.</span></span>  <br/> |<span data-ttu-id="b4492-157">在 [**循環**] 區段中，選取 [**重複此階段的動作...** 然後輸入您想要再度發生的動作的頻率。</span><span class="sxs-lookup"><span data-stu-id="b4492-157">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="b4492-158">> [!NOTE]> 這個選項才可用如果可以重複運用您所選取的巨集指令。</span><span class="sxs-lookup"><span data-stu-id="b4492-158">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="b4492-159">例如，您無法設定 [**永久刪除**] 動作的循環。</span><span class="sxs-lookup"><span data-stu-id="b4492-159">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="b4492-160">5.</span><span class="sxs-lookup"><span data-stu-id="b4492-160">5.</span></span>  <br/> |<span data-ttu-id="b4492-161">選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-161">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="b4492-162">若要啟用受限於此原則的項目與文件的稽核，選擇 [**啟用稽核**]，，然後指定您想要稽核的事件。</span><span class="sxs-lookup"><span data-stu-id="b4492-162">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="b4492-163">若要啟用稽核</span><span class="sxs-lookup"><span data-stu-id="b4492-163">To enable auditing</span></span>
    
||||||<span data-ttu-id="b4492-164">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="b4492-164">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="b4492-165">在 [編輯原則] 頁面中，\* ***下\*\*\*\*稽核** **\>** **啟用稽核*** *，，然後選取您想要保留稽核事件旁的核取方塊軌跡 for.* \* \*</span><span class="sxs-lookup"><span data-stu-id="b4492-165">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b4492-166">**2.**</span><span class="sxs-lookup"><span data-stu-id="b4492-166">**2.**</span></span> <br/> |<span data-ttu-id="b4492-167">**若要提示使用者插入到文件，這些條碼\*\*\*\*選擇\*\*\*\*若要插入條碼儲存或列印前的提示使用者\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="b4492-167">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="b4492-168">**3.**</span><span class="sxs-lookup"><span data-stu-id="b4492-168">**3.**</span></span> <br/> |<span data-ttu-id="b4492-169">**選擇\*\*\*\*確定**\* \* 將稽核功能套用到原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-169">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="b4492-170">稽核原則功能可讓組織建立和分析文件和清單項目，例如任務清單、 問題清單、 討論群組和行事曆的稽核線索。</span><span class="sxs-lookup"><span data-stu-id="b4492-170">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="b4492-171">此原則功能提供會記錄事件，例如檢視、 編輯或刪除內容時稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b4492-171">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="b4492-172">稽核資訊管理原則的過程中啟用時，系統管理員可以檢視稽核資料的彙總目前使用的採用在 Microsoft Excel 中原則使用情況報告中。</span><span class="sxs-lookup"><span data-stu-id="b4492-172">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="b4492-173">系統管理員可以使用這些報告來決定如何在組織內使用的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4492-173">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="b4492-174">這些報告還可協助組織來確認及其法規合規性的文件或調查潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="b4492-174">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="b4492-175">稽核記錄會記錄下列資訊： 事件名稱、 日期和時間的事件，並執行動作之使用者的系統名稱。</span><span class="sxs-lookup"><span data-stu-id="b4492-175">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="b4492-176">當條碼啟用原則的一部分時，他們會加入至文件屬性，並顯示在標頭] 區域中要套用之條碼的文件。</span><span class="sxs-lookup"><span data-stu-id="b4492-176">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="b4492-177">標籤，例如條碼可以也是以手動方式移除文件。</span><span class="sxs-lookup"><span data-stu-id="b4492-177">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="b4492-178">您可以指定是否應該包含條碼列印或儲存項目時提示使用者，或如果應手動插入條碼 2010年中使用 [**插入**] 索引標籤 Office 發行方案。</span><span class="sxs-lookup"><span data-stu-id="b4492-178">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="b4492-179">若要啟用條碼</span><span class="sxs-lookup"><span data-stu-id="b4492-179">To enable barcodes</span></span>
    
||||||<span data-ttu-id="b4492-180">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="b4492-180">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="b4492-181">**在 [編輯原則] 頁面的 [**條碼**\> **啟用條碼**。**</span><span class="sxs-lookup"><span data-stu-id="b4492-181">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b4492-182">**2.**</span><span class="sxs-lookup"><span data-stu-id="b4492-182">**2.**</span></span> <br/> |<span data-ttu-id="b4492-183">若要提示使用者將這些條碼插入至文件，選擇 [**插入條碼儲存或列印前的提示使用者**。</span><span class="sxs-lookup"><span data-stu-id="b4492-183">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-184">**3.**</span><span class="sxs-lookup"><span data-stu-id="b4492-184">**3.**</span></span> <br/> |<span data-ttu-id="b4492-185">選擇 **[確定]** 以套用至原則的條碼功能。</span><span class="sxs-lookup"><span data-stu-id="b4492-185">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="b4492-186">條碼原則會產生程式碼 39 標準條碼。</span><span class="sxs-lookup"><span data-stu-id="b4492-186">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="b4492-187">每個條碼映像包含條碼符號代表條碼值下方的文字。</span><span class="sxs-lookup"><span data-stu-id="b4492-187">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="b4492-188">這可讓即使掃描硬體無法使用時要使用的條碼資料。</span><span class="sxs-lookup"><span data-stu-id="b4492-188">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="b4492-189">使用者可以手動輸入的條碼號碼到搜尋方塊中，以找出在網站上的項目。</span><span class="sxs-lookup"><span data-stu-id="b4492-189">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="b4492-190">若要要求都受限於此原則的文件具有標籤，選擇 [**啟用標籤**]，然後指定您想要之標籤的設定。</span><span class="sxs-lookup"><span data-stu-id="b4492-190">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="b4492-191">若要啟用標籤</span><span class="sxs-lookup"><span data-stu-id="b4492-191">To enable labels</span></span>
    
||||||<span data-ttu-id="b4492-192">**1.**</span><span class="sxs-lookup"><span data-stu-id="b4492-192">**1.**</span></span>|<span data-ttu-id="b4492-193">\* \* 若需要使用者將標籤新增至文件，請選擇 [**插入標籤儲存或列印前的提示使用者**]。</span><span class="sxs-lookup"><span data-stu-id="b4492-193">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="b4492-194">> [!NOTE]> 若要讓標籤變成選用，請勿選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b4492-194">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="b4492-195">2.</span><span class="sxs-lookup"><span data-stu-id="b4492-195">2.</span></span>  <br/> |<span data-ttu-id="b4492-196">若要鎖定標籤，使它無法變更具有已插入後，選擇 [**標籤新增後避免變更**]。</span><span class="sxs-lookup"><span data-stu-id="b4492-196">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="b4492-197">此設定可防止標籤文字更新之後標籤已插入 Word、 Excel 或 PowerPoint 等用戶端應用程式內的項目。</span><span class="sxs-lookup"><span data-stu-id="b4492-197">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="b4492-198">如果您想要針對此文件或項目，屬性會更新時，會更新的標籤，請勿選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b4492-198">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-199">3.</span><span class="sxs-lookup"><span data-stu-id="b4492-199">3.</span></span>  <br/> |<span data-ttu-id="b4492-200">在 [標籤格式] 方塊中，輸入的文字標籤，為您想要顯示。</span><span class="sxs-lookup"><span data-stu-id="b4492-200">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="b4492-201">標籤可以包含最多 10 個資料行參照，每一種可以是最多 255 個字元。</span><span class="sxs-lookup"><span data-stu-id="b4492-201">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="b4492-202">若要建立您的標籤的格式，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b4492-202">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="b4492-203">輸入您想要包含在您想要顯示的順序中的標籤中的資料行的名稱。</span><span class="sxs-lookup"><span data-stu-id="b4492-203">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="b4492-204">以大括弧括住的資料行名稱 ({})、 [編輯原則] 頁面上的範例所示。</span><span class="sxs-lookup"><span data-stu-id="b4492-204">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="b4492-205">在 [編輯原則] 頁面上的範例所示，請輸入要識別括號，外部的資料行文字。</span><span class="sxs-lookup"><span data-stu-id="b4492-205">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-206">4.</span><span class="sxs-lookup"><span data-stu-id="b4492-206">4.</span></span>  <br/> |<span data-ttu-id="b4492-207">若要新增分行符號，請輸入**\n**您想要顯示的分行符號。</span><span class="sxs-lookup"><span data-stu-id="b4492-207">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-208">5.</span><span class="sxs-lookup"><span data-stu-id="b4492-208">5.</span></span>  <br/> |<span data-ttu-id="b4492-209">選取的字型的大小和樣式，然後指定是否要讓標籤置於左、 置中或文件內的權限。</span><span class="sxs-lookup"><span data-stu-id="b4492-209">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="b4492-210">選取的字型和使用者的電腦可用的樣式。</span><span class="sxs-lookup"><span data-stu-id="b4492-210">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="b4492-211">字型的大小會影響多少文字可以顯示在標籤上。</span><span class="sxs-lookup"><span data-stu-id="b4492-211">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-212">6.</span><span class="sxs-lookup"><span data-stu-id="b4492-212">6.</span></span>  <br/> |<span data-ttu-id="b4492-213">輸入標籤寬度與高度。</span><span class="sxs-lookup"><span data-stu-id="b4492-213">Enter the height and width of the label.</span></span> <span data-ttu-id="b4492-214">標籤高度可介於.25 英吋到 20 英吋，並標籤寬度可介於.25 英吋到 20 英吋。</span><span class="sxs-lookup"><span data-stu-id="b4492-214">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="b4492-215">標籤文字永遠垂直置中對齊標籤 image 內。</span><span class="sxs-lookup"><span data-stu-id="b4492-215">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="b4492-216">7.</span><span class="sxs-lookup"><span data-stu-id="b4492-216">7.</span></span>  <br/> |<span data-ttu-id="b4492-217">選擇 [**重新整理**預覽標籤內容]。</span><span class="sxs-lookup"><span data-stu-id="b4492-217">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="b4492-218">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-218">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="b4492-219">建立清單、文件庫或資料夾的原則 (位置保留原則)</span><span class="sxs-lookup"><span data-stu-id="b4492-219">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="b4492-220"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-220"></span></span>

<span data-ttu-id="b4492-221">您可以定義僅適用於特定清單、 文件庫或資料夾的保留原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-221">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="b4492-222">不過，如果您建立保留原則如此一來，您不能重複使用在其他清單、 文件庫、 資料夾或網站，此原則，您無法將網站集合原則套用至基礎的位置原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-222">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="b4492-223">如果您想要將一個保留原則套用至所有類型的內容，在單一位置，您很可能是要使用位置型保留。</span><span class="sxs-lookup"><span data-stu-id="b4492-223">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="b4492-224">其他大部分的情況下，您會想要確認指定的保留原則時，則適用於所有的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-224">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="b4492-225">除非您選擇中斷繼承，並定義新的保留原則，在子系層級，每一個子資料夾會繼承其父系的保留原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-225">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="b4492-226">如果您想要定義保留以外的資訊管理原則至清單或文件庫，您需要定義該清單或文件庫相關聯的每個個別清單內容類型的資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-226">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="b4492-227">如果在任何時候您決定切換從內容類型至清單或文件庫的位置原則，僅保留原則將用作位置為基礎的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-227">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="b4492-228">所有其他管理原則 （稽核、 條碼和條碼） 將會從相關聯的內容類型繼承而來。</span><span class="sxs-lookup"><span data-stu-id="b4492-228">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="b4492-229">按照位置原則可以停用網站集合停用的文件庫和資料夾型保留功能。</span><span class="sxs-lookup"><span data-stu-id="b4492-229">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="b4492-230">這可讓網站集合管理員，以確保其內容類型原則的清單管理員架構的位置原則不會被覆寫。</span><span class="sxs-lookup"><span data-stu-id="b4492-230">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="b4492-231">您至少需要管理清單權限，若要變更清單或文件庫的資訊管理原則設定。</span><span class="sxs-lookup"><span data-stu-id="b4492-231">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="b4492-232">瀏覽至您想要指定的資訊管理原則的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="b4492-232">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="b4492-233">功能區上，選擇 [**文件庫**或**清單**] 索引標籤\>**文件庫設定**] 或 [**清單設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-233">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="b4492-234">在 SharePoint Online 中，按一下 [**設定**]，然後按一下 [**清單設定**] 或 [**文件庫設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-234">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="b4492-235">在 [**權限與管理**] 下\>**資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-235">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![資訊管理原則連結的文件庫設定] 頁面上](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="b4492-237">在 [資訊管理原則設定] 頁面上，請確定來源的保留清單或文件庫設為文件庫和資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4492-237">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="b4492-238">如果**內容類型**出現做為來源，請按一下 [**變更來源**]，然後按一下 [**文件庫和資料夾**。</span><span class="sxs-lookup"><span data-stu-id="b4492-238">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="b4492-239">您會收到通知的內容類型的保留原則將被忽略。</span><span class="sxs-lookup"><span data-stu-id="b4492-239">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="b4492-240">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-240">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="b4492-241">在編輯原則] 頁面的 [**文件庫以保留排程**，輸入您要建立原則的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="b4492-241">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="b4492-242">選擇 [**新增保留階段...**</span><span class="sxs-lookup"><span data-stu-id="b4492-242">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="b4492-243">請注意，在記錄，您可以選擇要選取的記錄] 選項的定義不同的保留階段來定義不同的保留原則的記錄。</span><span class="sxs-lookup"><span data-stu-id="b4492-243">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="b4492-244">在階段 [屬性] 對話方塊中，選取 [保留期間的選項，以指定當設定到期的文件或項目。</span><span class="sxs-lookup"><span data-stu-id="b4492-244">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="b4492-245">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="b4492-245">Do one of the following:</span></span>
    
  - <span data-ttu-id="b4492-246">若要設定之下**事件**的日期屬性為基礎的到期日\>**此階段以關閉項目的日期屬性為基礎**，然後選取 [文件或項目動作 （例如，建立或修改） 並在此巨集指令 （之後的時間增量單位例如，天數、 月數或年數） 當您想要到期的項目。</span><span class="sxs-lookup"><span data-stu-id="b4492-246">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="b4492-247">若要使用自訂保留公式來決定到期日，請選擇 [**此伺服器上安裝自訂保留公式來設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-247">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b4492-248">如果您的系統管理員已設定的自訂公式，此選項只有。</span><span class="sxs-lookup"><span data-stu-id="b4492-248">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="b4492-249">在 [**巨集指令**，指定您想要在文件或項目到期時，即會發生。</span><span class="sxs-lookup"><span data-stu-id="b4492-249">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="b4492-250">若要啟用特定動作發生的文件或項目 （例如刪除），請從清單中選取動作。</span><span class="sxs-lookup"><span data-stu-id="b4492-250">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="b4492-251">**啟動工作流程**] 選項是您要定義的原則清單、 文件庫或內容類型已有與它相關聯的工作流程時，才可以使用。</span><span class="sxs-lookup"><span data-stu-id="b4492-251">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="b4492-252">您接著會指定可從中選擇工作流程。</span><span class="sxs-lookup"><span data-stu-id="b4492-252">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="b4492-253">在 [**循環**，] 下選擇 [**重複此階段的動作...** 然後輸入您想要再度發生的動作的頻率。</span><span class="sxs-lookup"><span data-stu-id="b4492-253">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b4492-254">如果您選取的動作可以重複的話，這個選項只有。</span><span class="sxs-lookup"><span data-stu-id="b4492-254">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="b4492-255">例如，您無法設定 [**永久刪除**] 動作的循環。</span><span class="sxs-lookup"><span data-stu-id="b4492-255">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="b4492-256">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-256">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="b4492-257">將網站集合原則套用至內容類型</span><span class="sxs-lookup"><span data-stu-id="b4492-257">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="b4492-258"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-258"></span></span>

<span data-ttu-id="b4492-259">如果資訊管理原則已建立您的網站為網站集合原則，您可以將其中一個原則套用至內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-259">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="b4492-260">執行此動作，您可以將相同的原則套用至多個內容類型網站集合中不會共用相同的上層內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-260">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="b4492-261">如果您想要將原則套用至網站集合中的多個內容類型，而且您必須設定 Managed Metadata Service，您可以使用內容類型發佈來發佈出資訊管理原則至多個網站集合。</span><span class="sxs-lookup"><span data-stu-id="b4492-261">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="b4492-262">請參閱 > 一節[將跨網站集合原則套用](#apply-a-policy-across-site-collections)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b4492-262">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="b4492-263">瀏覽至清單或文件庫包含您想要套用原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-263">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="b4492-264">功能區上，選擇 [**文件庫**或**清單**] 索引標籤\>**文件庫設定**] 或 [**清單設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-264">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="b4492-265">在 SharePoint Online 中，按一下 [**設定**]，然後按一下 [**清單設定**] 或 [**文件庫設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-265">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="b4492-266">在 [**權限與管理**] 下\>**資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="b4492-266">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![資訊管理原則連結的文件庫設定] 頁面上](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="b4492-268">確認原則來源設定至**內容類型**，並在 [**內容類型原則**選取您想要套用原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-268">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="b4492-269">在 [**指定原則** \> **使用網站集合原則**]，然後選取 [您想要從清單套用的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-269">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b4492-270">如果無法使用 [**使用網站集合原則**] 選項，沒有網站集合原則已定義的網站集合。</span><span class="sxs-lookup"><span data-stu-id="b4492-270">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="b4492-271">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4492-271">Choose **OK**.</span></span>
    
     <span data-ttu-id="b4492-272">如果您正在使用的文件庫或清單支援多種內容類型的管理，請在 [**內容類型**您可以選擇您想要指定的資訊管理原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-272">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="b4492-273">這將帶您直接向上方步驟 5。</span><span class="sxs-lookup"><span data-stu-id="b4492-273">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="b4492-274">將原則套用跨網站集合</span><span class="sxs-lookup"><span data-stu-id="b4492-274">Apply a policy across site collections</span></span>
<span data-ttu-id="b4492-275"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-275"></span></span>

<span data-ttu-id="b4492-276">共用跨網站集合的內容類型所使用的 Managed Metadata service 應用程式設定內容類型發佈。</span><span class="sxs-lookup"><span data-stu-id="b4492-276">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="b4492-277">內容類型發佈功能可協助您管理內容和中繼資料一致地跨網站因為內容類型可建立及更新集中，並可將更新出發佈到多個訂閱的網站集合或 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b4492-277">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="b4492-278">從現有的原則，以使用跨網站集合建立範本</span><span class="sxs-lookup"><span data-stu-id="b4492-278">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="b4492-279"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-279"></span></span>

<span data-ttu-id="b4492-280">您可以定義資訊管理原則，然後建立它，視需要跨多個網站集合使用的 [範本。</span><span class="sxs-lookup"><span data-stu-id="b4492-280">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="b4492-281">如果想要備份的資訊原則，或者也可以用為替代方法，以使用內容類型發佈跨網站集合套用某個原則，可以使用此方法。</span><span class="sxs-lookup"><span data-stu-id="b4492-281">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="b4492-282">從一個網站集合匯出原則，然後匯入它的儲存位置，或到另一個網站集合中建立的範本或原則的備份。</span><span class="sxs-lookup"><span data-stu-id="b4492-282">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="b4492-283">如果您使用匯出/匯入功能的方式，讓一組原則範本，請記住，在於原則.xml 檔案中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b4492-283">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="b4492-284">因此，您不能匯入該原則網站一次以上而不需要變更此唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b4492-284">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="b4492-285">匯出的原則</span><span class="sxs-lookup"><span data-stu-id="b4492-285">Export a policy</span></span>
<span data-ttu-id="b4492-286"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-286"></span></span>

1. <span data-ttu-id="b4492-287">在 [網站集合首頁] 頁面上，選擇 [**設定**![小型設定] 齒輪圖示，所需的網站設定的位置。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-287">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b4492-288">在 SharePoint 群組連接網站中，按一下 [**設定**] [**網站內容**]，，然後按一下 [**網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-288">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b4492-289">在 [網站設定] 頁面上的 [**網站集合管理**] 下\>**內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="b4492-289">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![在 [網站設定] 頁面上的內容類型原則範本連結](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="b4492-291">選擇您想要匯出的原則\>捲動到底部\>**匯出**。</span><span class="sxs-lookup"><span data-stu-id="b4492-291">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="b4492-292">在提示儲存] 或 [開啟檔案時，請選擇 [**儲存**]，然後選取要儲存之檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="b4492-292">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="b4492-293">請務必選取可匯入原則的網站集合的位置。</span><span class="sxs-lookup"><span data-stu-id="b4492-293">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="b4492-294">[下載完成] 對話方塊顯示時，選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b4492-294">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="b4492-295">原則匯入至不同網站集合</span><span class="sxs-lookup"><span data-stu-id="b4492-295">Import a policy to a different site collection</span></span>
<span data-ttu-id="b4492-296"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="b4492-296"></span></span>

<span data-ttu-id="b4492-297">匯入的資訊管理原則可讓您將它套用至網站或清單層級任何特定的網站集合內的多個內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-297">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="b4492-298">執行此動作的優點有兩個層面： 您不必重新定義，並將原則套用在每個內容類型，並變更在一個位置原則，您可以更輕鬆地管理原則的修改。</span><span class="sxs-lookup"><span data-stu-id="b4492-298">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="b4492-299">在您想要套用原則的網站集合的 [首頁] 頁面上，選擇 [**設定**![小型設定] 齒輪圖示，所需的網站設定的位置。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-299">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="b4492-300">在 SharePoint 群組連接網站中，按一下 [**設定**] [**網站內容**]，，然後按一下 [**網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="b4492-300">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="b4492-301">在 [網站設定] 頁面上的 [**網站集合管理**] 下\>**內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="b4492-301">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="b4492-302">在 [原則] 頁面上\>**匯入** \> **瀏覽]** 尋找原則的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="b4492-302">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="b4492-303">選取原則已儲存在其中的 XML 檔案\>**開啟**。</span><span class="sxs-lookup"><span data-stu-id="b4492-303">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="b4492-304">在匯入網站集合原則] 頁面上\>**匯入**来新增至網站集合中的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-304">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="b4492-305">您匯入的原則，現在可以套用至一或多個網站或清單層級的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b4492-305">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="b4492-306">資訊管理原則可讓貴組織控制多久要保留內容，以稽核人員用來做什麼內容，並加入條碼] 或 [文件的標籤。</span><span class="sxs-lookup"><span data-stu-id="b4492-306">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="b4492-307">原則可協助強制執行規範與法律和政府法規或內部商務程序。</span><span class="sxs-lookup"><span data-stu-id="b4492-307">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="b4492-308">身為管理員，您可以設定的原則來控制如何追蹤的文件，以及要保留的文件。</span><span class="sxs-lookup"><span data-stu-id="b4492-308">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="b4492-309">您可以建立資訊管理原則，可在三個不同地點網站在階層中，從最大範圍以最窄：</span><span class="sxs-lookup"><span data-stu-id="b4492-309">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="b4492-310">建立要用於網站集合內的多個內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-310">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="b4492-311">建立網站內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-311">Create a policy for a site content type.</span></span>
- <span data-ttu-id="b4492-312">建立清單或文件庫的原則。</span><span class="sxs-lookup"><span data-stu-id="b4492-312">Create a policy for a list or library.</span></span>

<span data-ttu-id="b4492-313">如需詳細資訊，請參閱 <<c0>的資訊管理原則簡介。</span><span class="sxs-lookup"><span data-stu-id="b4492-313">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

