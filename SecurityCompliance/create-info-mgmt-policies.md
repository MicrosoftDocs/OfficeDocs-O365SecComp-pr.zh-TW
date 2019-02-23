---
title: 建立與套用資料的資訊管理原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
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
description: 資訊管理原則啟用多久要保留稽核人員用來做什麼內容，並新增條碼的內容控制項為組織或文件的標籤。原則可協助強制遵守法律及政府規定或內部商務程序。身為管理員，您可以設定原則以控制如何追蹤文件及多久要保留的文件。
ms.openlocfilehash: d4161ad3684a006f0e4b2b9e0e856ea0a8aa67fc
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214693"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="20987-105">建立與套用資料的資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="20987-105">Create and apply information management policies</span></span>

<span data-ttu-id="20987-p102">資訊管理原則啟用多久要保留稽核人員用來做什麼內容，並新增條碼的內容控制項為組織或文件的標籤。原則可協助強制遵守法律及政府規定或內部商務程序。身為管理員，您可以設定原則以控制如何追蹤文件及多久要保留的文件。</span><span class="sxs-lookup"><span data-stu-id="20987-p102">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents. A policy can help enforce compliance with legal and governmental regulations or internal business processes. As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="20987-109">您可以建立資訊管理原則可以在三個不同的位置的網站階層中從最大到最窄：</span><span class="sxs-lookup"><span data-stu-id="20987-109">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="20987-110">建立網站集合內的多個內容類型上使用的原則。</span><span class="sxs-lookup"><span data-stu-id="20987-110">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="20987-111">建立網站內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="20987-111">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="20987-112">建立清單或文件庫的原則。</span><span class="sxs-lookup"><span data-stu-id="20987-112">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="20987-113">如需詳細資訊，請參閱[資訊管理原則簡介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="20987-113">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="20987-114">建立網站集合內的多個內容類型的原則</span><span class="sxs-lookup"><span data-stu-id="20987-114">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="20987-115"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-115"></span></span>

<span data-ttu-id="20987-p103">為確保資訊原則套用至網站集合內的特定類型的所有文件，請考慮建立網站集合層級的原則與稍後將原則套用至內容類型。這些被所謂的網站集合原則。</span><span class="sxs-lookup"><span data-stu-id="20987-p103">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types. These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="20987-p104">在網站集合首頁\>**設定**![標題列上的 SharePoint 2016 設定] 按鈕。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-p104">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Site Settings**.</span></span>
    
    <span data-ttu-id="20987-120">在 SharePoint 群組連接網站中，按一下 [**設定**]、 按一下 [**網站內容**]，和 [**網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-120">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="20987-121">在 [網站設定] 頁面上的 [**網站集合管理** \> **內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="20987-121">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![在 [網站設定] 頁面上的內容類型原則範本連結](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="20987-123">在 [原則] 頁面上\>**建立**。</span><span class="sxs-lookup"><span data-stu-id="20987-123">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="20987-124">輸入的名稱和描述的原則，並接著撰寫說明使用者原則是針對簡短的原則陳述式。</span><span class="sxs-lookup"><span data-stu-id="20987-124">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="20987-125">請參閱下一個區段上建立網站內容類型以了解如何設定您想要將原則建立關聯之的功能的原則。</span><span class="sxs-lookup"><span data-stu-id="20987-125">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="20987-126">選擇 [確定]。</span><span class="sxs-lookup"><span data-stu-id="20987-126">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="20987-127">建立網站內容類型的原則</span><span class="sxs-lookup"><span data-stu-id="20987-127">Create a policy for a site content type</span></span>
<span data-ttu-id="20987-128"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-128"></span></span>

<span data-ttu-id="20987-p105">新增資訊管理原則至內容類型容易與多個清單或文件庫建立關聯的原則功能。您可以選擇加入現有的資訊管理原則至內容類型或建立唯一原則專屬的個別的內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-p105">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries. You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="20987-p106">您也可以新增資訊管理原則至內容類型專屬於清單。這有將原則套用至該清單中所使用的內容類型的項目僅的影響。</span><span class="sxs-lookup"><span data-stu-id="20987-p106">You can also add an information management policy to a content type that is specific to lists. This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="20987-p107">在網站集合首頁\>**設定**![標題列上的 SharePoint 2016 設定] 按鈕。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-p107">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Site Settings**.</span></span>
    
    <span data-ttu-id="20987-135">在 SharePoint 群組連接網站中，按一下 [**設定**]、 按一下 [**網站內容**]，和 [**網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-135">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="20987-136">在 [網站設定] 頁面上的 [ **Web Designer 圖庫** \> **網站內容類型**。</span><span class="sxs-lookup"><span data-stu-id="20987-136">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![在 [網站設定] 頁面上的網站內容類型連結](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="20987-138">在 [網站內容類型的設定] 頁面上，選取您想要新增至原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-138">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="20987-139">在 [網站內容類型] 頁面上的 [**設定**] 下\>**資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-139">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="20987-140">在 [編輯原則] 頁面上輸入的名稱和描述的原則，並接著撰寫說明使用者原則是針對的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="20987-140">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="20987-141">在下一步] 區段中，選取您想要新增至您的資訊管理原則的個別原則功能。</span><span class="sxs-lookup"><span data-stu-id="20987-141">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![類型的內容的原則](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="20987-143">若要指定文件與受限於此原則相關的項目保留期間，選擇 [**啟用保留**，然後指定保留期間，以及您想要發生的項目到期時的動作。</span><span class="sxs-lookup"><span data-stu-id="20987-143">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="20987-144">若要指定保留期間</span><span class="sxs-lookup"><span data-stu-id="20987-144">To specify a retention period</span></span>
    
||||||<span data-ttu-id="20987-145">**1。**</span><span class="sxs-lookup"><span data-stu-id="20987-145">**1.**</span></span>|<span data-ttu-id="20987-146">\* \* 選擇 \* \*...新增記錄的保留階段 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="20987-146">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="20987-147">2.</span><span class="sxs-lookup"><span data-stu-id="20987-147">2.</span></span>  <br/> | <span data-ttu-id="20987-p108">選取指定的文件或項目設定為到期時保留期間選項。執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="20987-p108">Select a retention period option to specify when documents or items are set to expire. Do one of the following:  </span></span><br/>  <span data-ttu-id="20987-150">若要設定之下**事件**的日期屬性為基礎的到期日期\>**這個階段基礎關閉項目上的 [日期] 屬性**，然後選取 [文件或項目動作 （例如，建立或修改） 與此動作 （之後的時間單位例如的天數、 月數或年數） 當您想要到期的項目。</span><span class="sxs-lookup"><span data-stu-id="20987-150">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="20987-151">若要使用的自訂保留公式來決定到期日，選擇 [**這個伺服器上安裝自訂保留公式來設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-151">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="20987-152">> [!NOTE]> 這個選項只有如果管理員已設定的自訂公式。</span><span class="sxs-lookup"><span data-stu-id="20987-152">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="20987-153">3.</span><span class="sxs-lookup"><span data-stu-id="20987-153">3.</span></span>  <br/> |<span data-ttu-id="20987-p109">只有在您定義的原則清單、 文件庫或內容類型已有與其相關聯的工作流程使用**啟動工作流程**] 選項。您再將獲得選擇所要選擇的工作流程。</span><span class="sxs-lookup"><span data-stu-id="20987-p109">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it. You will then be given a choice of workflows to choose from.  </span></span><br/> |
||||||<span data-ttu-id="20987-156">4.</span><span class="sxs-lookup"><span data-stu-id="20987-156">4.</span></span>  <br/> |<span data-ttu-id="20987-157">在 [**循環**] 區段中選取 [**重複這個階段動作...** 並輸入想要再度發生的動作的頻率。</span><span class="sxs-lookup"><span data-stu-id="20987-157">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="20987-p110">> [!NOTE]> 只有當您所選取的巨集指令可以重複使用此選項。例如，您無法設定**永久刪除**動作的循環。</span><span class="sxs-lookup"><span data-stu-id="20987-p110">> [!NOTE]>  This option is only available if the action you selected can be repeated. For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="20987-160">5.</span><span class="sxs-lookup"><span data-stu-id="20987-160">5.</span></span>  <br/> |<span data-ttu-id="20987-161">選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="20987-161">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="20987-162">若要啟用稽核文件與受限於此原則相關的項目，請選擇 [**啟用稽核**]，並再指定您想要稽核的事件。</span><span class="sxs-lookup"><span data-stu-id="20987-162">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="20987-163">若要啟用稽核</span><span class="sxs-lookup"><span data-stu-id="20987-163">To enable auditing</span></span>
    
||||||<span data-ttu-id="20987-164">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="20987-164">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="20987-165">在 [編輯原則] 頁面上 \* ***下\*\*\*\*稽核** **\>** **啟用稽核*** *，然後選取您要保留稽核事件旁的核取方塊軌跡 for.* \* \* 和</span><span class="sxs-lookup"><span data-stu-id="20987-165">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="20987-166">**2.**</span><span class="sxs-lookup"><span data-stu-id="20987-166">**2.**</span></span> <br/> |<span data-ttu-id="20987-167">**若要提示使用者插入到文件，這些條碼\*\*\*\*選擇\*\*\*\*提示使用者插入條碼儲存或列印前\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="20987-167">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="20987-168">**3.**</span><span class="sxs-lookup"><span data-stu-id="20987-168">**3.**</span></span> <br/> |<span data-ttu-id="20987-169">**選擇\*\*\*\*[確定]** \* \* 將稽核功能套用到原則。</span><span class="sxs-lookup"><span data-stu-id="20987-169">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="20987-p111">稽核原則功能可讓組織可以建立及分析文件和清單項目如工作清單、 議題清單、 討論區群組和行事曆的稽核線索。此原則功能提供記錄事件，例如時檢視、 編輯或刪除內容稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="20987-p111">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars. This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="20987-p112">啟用稽核時的資訊管理原則的一部分，管理員可以原則使用情況報告採用 Microsoft Excel 中並的摘要目前使用中檢視稽核資料。管理員可以使用這些報告來決定如何在組織內使用的資訊。這些報告也可協助組織驗證及其法規相符的文件或調查潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="20987-p112">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage. Administrators can use these reports to determine how information is being used within the organization. These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="20987-175">稽核記錄會記錄下列資訊：事件名稱、事件的日期和時間，以及執行動作之使用者的系統名稱。</span><span class="sxs-lookup"><span data-stu-id="20987-175">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="20987-p113">啟用條碼之後之原則的一部分，他們會加入至文件屬性及顯示要套用條碼的文件的頁首區域中。標籤，例如條碼也可以手動移除文件。您可以指定是否要包含條碼列印或儲存項目時，是否應提示使用者或如果應該手動插入條碼 2010年中使用 [**插入**] 索引標籤 Office 版本程式]。</span><span class="sxs-lookup"><span data-stu-id="20987-p113">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied. Like labels, barcodes can also be manually removed from a document. You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="20987-179">若要啟用條碼</span><span class="sxs-lookup"><span data-stu-id="20987-179">To enable barcodes</span></span>
    
||||||<span data-ttu-id="20987-180">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="20987-180">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="20987-181">**在 [編輯原則] 頁面上的 [**條碼**\> **啟用條碼**。**</span><span class="sxs-lookup"><span data-stu-id="20987-181">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="20987-182">**2.**</span><span class="sxs-lookup"><span data-stu-id="20987-182">**2.**</span></span> <br/> |<span data-ttu-id="20987-183">若要提示使用者將這些條碼插入至文件，請選擇 [**提示使用者插入條碼儲存或列印前**。</span><span class="sxs-lookup"><span data-stu-id="20987-183">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="20987-184">**3.**</span><span class="sxs-lookup"><span data-stu-id="20987-184">**3.**</span></span> <br/> |<span data-ttu-id="20987-185">選擇 **[確定]** 將條碼功能套用至原則。</span><span class="sxs-lookup"><span data-stu-id="20987-185">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="20987-p114">條碼原則將會產生程式碼 39 標準條碼。每個條碼映像包含代表條碼值條碼符號下方的文字。這可讓即使掃描硬體無法使用時要使用的條碼資料。使用者可以手動輸入的條碼號碼到 [搜尋] 方塊中找出在網站上的項目。</span><span class="sxs-lookup"><span data-stu-id="20987-p114">The barcode policy generates Code 39 standard barcodes. Each barcode image includes text below the barcode symbol that represents the barcode value. This enables the barcode data to be used even when scanning hardware is not available. Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="20987-190">若要要求會受限於此原則的文件有標籤，並選擇 [**啟用標籤**，然後指定您想要之標籤的設定。</span><span class="sxs-lookup"><span data-stu-id="20987-190">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="20987-191">若要啟用標籤</span><span class="sxs-lookup"><span data-stu-id="20987-191">To enable labels</span></span>
    
||||||<span data-ttu-id="20987-192">**1。**</span><span class="sxs-lookup"><span data-stu-id="20987-192">**1.**</span></span>|<span data-ttu-id="20987-193">\* \* 若要要求使用者將標籤新增至文件，請選擇 [**插入標籤儲存或列印前的提示使用者**。</span><span class="sxs-lookup"><span data-stu-id="20987-193">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="20987-194">> [!NOTE]若要讓標籤變成選用項目、 > 請勿選取這個核取方塊。</span><span class="sxs-lookup"><span data-stu-id="20987-194">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="20987-195">2.</span><span class="sxs-lookup"><span data-stu-id="20987-195">2.</span></span>  <br/> |<span data-ttu-id="20987-196">若要鎖定標籤，使其無法變更其插入後，選擇 [**標籤新增後避免變更**]。</span><span class="sxs-lookup"><span data-stu-id="20987-196">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="20987-p115">此設定會防止更新之後標籤已經插入如 Word、 Excel、 或 PowerPoint 用戶端應用程式內的項目標籤文字。如果您想要更新時，會更新此文件或項目屬性的標籤，請勿選取這個核取方塊。</span><span class="sxs-lookup"><span data-stu-id="20987-p115">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint. If you want the label to be updated when the properties for this document or item are updated, do not select this check box.  </span></span><br/> |
||||||<span data-ttu-id="20987-199">3.</span><span class="sxs-lookup"><span data-stu-id="20987-199">3.</span></span>  <br/> |<span data-ttu-id="20987-p116">在 [標籤格式] 方塊中，輸入文字標籤為您想要顯示。標籤可以包含最多 10 個資料行參考、 每一種可以長達 255 個字元。若要建立您的標籤格式，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="20987-p116">In the Label format box, enter the text for the label as you want it to be displayed. Labels can contain up to 10 column references, each of which can be up to 255 characters long. To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="20987-p117">輸入您想要包含在這些看起來要的順序排列的標籤中的資料行的名稱。在大括弧括住資料行名稱 ({})、 [編輯原則] 頁面上的範例所示。</span><span class="sxs-lookup"><span data-stu-id="20987-p117">Type the names of the columns that you want to include in the label in the order in which you want them to appear. Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="20987-205">在 [編輯原則] 頁面上的範例所示，輸入識別方括弧外的資料行的文字。</span><span class="sxs-lookup"><span data-stu-id="20987-205">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="20987-206">4.</span><span class="sxs-lookup"><span data-stu-id="20987-206">4.</span></span>  <br/> |<span data-ttu-id="20987-207">若要新增分行符號，輸入您想要顯示的分行符號**\n** 。</span><span class="sxs-lookup"><span data-stu-id="20987-207">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="20987-208">5.</span><span class="sxs-lookup"><span data-stu-id="20987-208">5.</span></span>  <br/> |<span data-ttu-id="20987-209">選取字型大小與您想，並指定您是否要在標籤置於左、 置中或文件內的右邊的樣式。</span><span class="sxs-lookup"><span data-stu-id="20987-209">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="20987-p118">選取字型和使用者的電腦可用的樣式。字型大小會影響多少文字可以顯示在標籤上。</span><span class="sxs-lookup"><span data-stu-id="20987-p118">Select a font and style that are available on the users' computers. The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="20987-212">6.</span><span class="sxs-lookup"><span data-stu-id="20987-212">6.</span></span>  <br/> |<span data-ttu-id="20987-p119">輸入高度及寬度的標籤。標籤高度範圍是從.25 英吋到 20 英吋，並標籤寬度的範圍可從.25 英吋為 20 英吋。標籤文字標籤 image 內一律垂直置中。</span><span class="sxs-lookup"><span data-stu-id="20987-p119">Enter the height and width of the label. Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches. Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="20987-216">7.</span><span class="sxs-lookup"><span data-stu-id="20987-216">7.</span></span>  <br/> |<span data-ttu-id="20987-217">選擇 [**重新整理**預覽標籤內容]。</span><span class="sxs-lookup"><span data-stu-id="20987-217">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="20987-218">選擇 [確定]。</span><span class="sxs-lookup"><span data-stu-id="20987-218">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="20987-219">建立清單、文件庫或資料夾的原則 (位置保留原則)</span><span class="sxs-lookup"><span data-stu-id="20987-219">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="20987-220"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-220"></span></span>

<span data-ttu-id="20987-p120">您可以定義僅適用於特定清單、 文件庫或資料夾的保留原則。不過，如果您建立保留原則如此一來，您不能重複使用此原則在其他清單、 文件庫、 資料夾或網站與您無法將網站集合原則套用至基礎的位置原則。</span><span class="sxs-lookup"><span data-stu-id="20987-p120">You can define a retention policy that applies only to a specific list, library or folder. However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="20987-p121">如果您想要將單一的保留原則套用至所有類型的單一位置中的內容，您很有可能要使用以位置為主的保留。中其他大多數的情況下，您會想要確認已指定的所有內容類型的保留原則。</span><span class="sxs-lookup"><span data-stu-id="20987-p121">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention. In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="20987-225">除非您選擇要中斷繼承和定義新的保留原則層級的子每一個子資料夾會繼承其父項、 保留原則。</span><span class="sxs-lookup"><span data-stu-id="20987-225">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="20987-226">如果您想要定義保留以外的資訊管理原則至清單或文件庫，您需要定義與清單或文件庫相關聯的每個個別清單內容類型的資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="20987-226">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="20987-p122">如果在任何時候您決定切換從內容類型至清單或文件庫的位置型原則、 保留原則將用作位置為基礎的原則。所有其他管理原則 （稽核、 條碼，以及條碼） 將會繼承自相關的內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-p122">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy. All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="20987-p123">架構的位置原則可用來停用的文件庫和資料夾以保留功能停用網站集合之用。這可讓網站集合管理員以確保其內容類型原則清單中系統管理員的架構的位置原則不會被覆寫。</span><span class="sxs-lookup"><span data-stu-id="20987-p123">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature. This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="20987-231">您至少需要管理清單權限變更清單或文件庫的資訊管理原則設定。</span><span class="sxs-lookup"><span data-stu-id="20987-231">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="20987-232">瀏覽至想要指定的資訊管理原則的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="20987-232">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="20987-233">在功能區上選擇 [**文件庫**或**清單**] 索引標籤\>**文件庫設定**] 或 [**清單設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-233">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="20987-234">在 SharePoint Online 中，按一下 [**設定**] 並再按一下 [**清單設定**] 或 [**文件庫設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-234">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="20987-235">[**權限與管理**\> **資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-235">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![文件庫設定] 頁面上的資訊管理原則連結](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="20987-237">在 [資訊管理原則設定] 頁面上，確認的清單或文件庫的保留來源設為文件庫和資料夾。</span><span class="sxs-lookup"><span data-stu-id="20987-237">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="20987-p124">如果**內容類型**顯示為來源，請按一下 [**變更來源**] 和 [**文件庫和資料夾**。您會收到通知內容類型的保留原則將會被忽略。選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="20987-p124">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**. You are alerted that content type retention policies will be ignored. Choose **OK**.</span></span> 
    
5. <span data-ttu-id="20987-241">在 [編輯原則] 頁面上的 [**文件庫以保留排程**] 下輸入您要建立之原則的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="20987-241">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="20987-242">選擇 [**新增保留階段...**</span><span class="sxs-lookup"><span data-stu-id="20987-242">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="20987-243">請注意下記錄，您可以選擇選取 [記錄] 選項的定義不同保留階段定義記錄的保留原則。</span><span class="sxs-lookup"><span data-stu-id="20987-243">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="20987-p125">在階段 [屬性] 對話方塊中，選取 [可指定當設定到期的文件或項目保留期間] 選項。執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="20987-p125">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire. Do one of the following:</span></span>
    
  - <span data-ttu-id="20987-246">若要設定之下**事件**的日期屬性為基礎的到期日期\>**這個階段基礎關閉項目上的 [日期] 屬性**，然後選取 [文件或項目動作 （例如，建立或修改） 與此動作 （之後的時間單位例如的天數、 月數或年數） 當您想要到期的項目。</span><span class="sxs-lookup"><span data-stu-id="20987-246">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="20987-247">若要使用的自訂保留公式來決定到期日，選擇 [**這個伺服器上安裝自訂保留公式來設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-247">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="20987-248">如果您的系統管理員所自訂公式設定，這個選項只有。</span><span class="sxs-lookup"><span data-stu-id="20987-248">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="20987-p126">在 [**巨集指令**，指定您想要的文件或項目到期時。若要啟用特定動作至文件或項目 （例如刪除） 的發生，請從清單中選取動作。</span><span class="sxs-lookup"><span data-stu-id="20987-p126">Under **Action**, specify what you want to happen when the document or item expires. To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="20987-p127">只有在您定義的原則清單、 文件庫或內容類型已有與其相關聯的工作流程使用**啟動工作流程**] 選項。您再將獲得選擇所要選擇的工作流程。</span><span class="sxs-lookup"><span data-stu-id="20987-p127">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it. You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="20987-253">[**循環**，選擇 [**重複這個階段動作...** 並輸入想要再度發生的動作的頻率。</span><span class="sxs-lookup"><span data-stu-id="20987-253">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="20987-p128">只有當您所選取的巨集指令可以重複使用此選項。例如，您無法設定**永久刪除**動作的循環。</span><span class="sxs-lookup"><span data-stu-id="20987-p128">This option is only available if the action you selected can be repeated. For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="20987-256">選擇 [確定]。</span><span class="sxs-lookup"><span data-stu-id="20987-256">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="20987-257">將網站集合原則套用至內容類型</span><span class="sxs-lookup"><span data-stu-id="20987-257">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="20987-258"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-258"></span></span>

<span data-ttu-id="20987-p129">如果資訊管理原則已經已為網站建立為網站集合原則，您可以將其中一個原則套用至內容類型。依照此您可以將相同的原則套用至多種內容類型的網站集合中不共用相同的上層內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-p129">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type. By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="20987-p130">若您想要將原則套用至網站集合中的多個內容類型和您必須設定受管理的中繼資料服務，您可以使用內容類型發佈發佈出資訊管理原則至多個網站集合。請參閱一節[將原則套用到整個網站集合的內容類型](create-info-mgmt-policies.md#__apply_a_policy)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="20987-p130">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections. See the section [Apply a policy to content types across site collections](create-info-mgmt-policies.md#__apply_a_policy) for more information.</span></span> 
  
1. <span data-ttu-id="20987-263">瀏覽至清單或文件庫包含您要套用原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-263">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="20987-264">在功能區上選擇 [**文件庫**或**清單**] 索引標籤\>**文件庫設定**] 或 [**清單設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-264">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="20987-265">在 SharePoint Online 中，按一下 [**設定**] 並再按一下 [**清單設定**] 或 [**文件庫設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-265">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="20987-266">[**權限與管理** \> **資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-266">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![文件庫設定] 頁面上的資訊管理原則連結](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="20987-268">確認原則來源已設定與**內容類型**，並在 [**內容類型原則**選取您要套用之原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-268">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="20987-269">在 [**指定原則** \> **使用網站集合原則**]，然後選取 [您想要從清單中套用的原則。</span><span class="sxs-lookup"><span data-stu-id="20987-269">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="20987-270">如果未**使用網站集合原則**選項，沒有網站集合原則已定義的網站集合。</span><span class="sxs-lookup"><span data-stu-id="20987-270">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="20987-271">選擇 [確定]。</span><span class="sxs-lookup"><span data-stu-id="20987-271">Choose **OK**.</span></span>
    
     <span data-ttu-id="20987-p131">如果您正在處理的文件庫或清單支援多種內容類型的管理、**內容類型**下您可以選擇您要指定的資訊管理原則的內容類型。這將會前往直接上面的步驟 5。</span><span class="sxs-lookup"><span data-stu-id="20987-p131">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy. This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="20987-274">將原則套用到網站集合</span><span class="sxs-lookup"><span data-stu-id="20987-274">Apply a policy across site collections</span></span>
<span data-ttu-id="20987-275"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-275"></span></span>

<span data-ttu-id="20987-p132">共用跨網站集合的內容類型所使用的受管理的中繼資料服務應用程式設定 [內容類型發佈。內容類型發佈功能可協助您管理內容與中繼資料一致地跨網站因為可建立及集中，更新內容類型及更新可延展發佈至多個訂閱的網站集合或 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="20987-p132">Share content types across site collections by using a Managed Metadata service application to set up content type publishing. Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="20987-278">從現有的原則以使用跨網站集合中建立範本</span><span class="sxs-lookup"><span data-stu-id="20987-278">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="20987-279"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-279"></span></span>

<span data-ttu-id="20987-p133">您可以定義資訊管理原則，然後建立從其使用跨多個網站集合所需的 [範本。如果您想要有資訊原則、 的備份或使用內容類型發佈的跨網站集合套用某個原則之替代方法以可用也可以使用此方法。您可以從一個網站集合匯出原則，然後匯入它已儲存的位置或另一個網站集合中建立範本或之原則的備份。</span><span class="sxs-lookup"><span data-stu-id="20987-p133">You can define an information management policy and then create a template from it to use as needed across multiple site collections. This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections. You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="20987-p134">如果您使用匯出/匯入功能的方式，讓一組的原則範本，請記住，在於原則.xml 檔案中的唯一識別碼。因此，您不能匯入該原則至網站一次以上而不變更此唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="20987-p134">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file. Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="20987-285">匯出原則</span><span class="sxs-lookup"><span data-stu-id="20987-285">Export a policy</span></span>
<span data-ttu-id="20987-286"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-286"></span></span>

1. <span data-ttu-id="20987-287">在 [網站集合首頁] 頁面上選擇 [**設定**![執行的網站設定的小型設定齒輪表示。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-287">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="20987-288">在 SharePoint 群組連接網站中，按一下 [**設定**]、 按一下 [**網站內容**]，和 [**網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-288">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="20987-289">在 [網站設定] 頁面上的 [**網站集合管理** \> **內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="20987-289">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![在 [網站設定] 頁面上的內容類型原則範本連結](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="20987-291">選擇您想要匯出的原則\>捲軸底部\>**匯出**。</span><span class="sxs-lookup"><span data-stu-id="20987-291">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="20987-p135">提示儲存或開啟的檔案，並選擇 [**儲存**，然後選取要儲存之檔案的位置。請務必選取 [可匯入之原則的網站集合的位置。</span><span class="sxs-lookup"><span data-stu-id="20987-p135">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to. Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="20987-294">[下載完成] 對話方塊顯示時，選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="20987-294">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="20987-295">原則匯入至不同的網站集合</span><span class="sxs-lookup"><span data-stu-id="20987-295">Import a policy to a different site collection</span></span>
<span data-ttu-id="20987-296"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="20987-296"></span></span>

<span data-ttu-id="20987-p136">匯入的資訊管理原則可讓您可以套用至網站或清單層級任何指定的網站集合內的多個內容類型。執行此動作的優點有兩個層面： 您不需要重新定義及套用該原則上每個內容類型，以及您可以更輕鬆地管理原則修改所進行的變更只是一個位置原則。</span><span class="sxs-lookup"><span data-stu-id="20987-p136">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection. The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="20987-299">在您要套用之原則的網站集合的 [首頁] 頁面上選擇 [**設定**![執行的網站設定的小型設定齒輪表示。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-299">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="20987-300">在 SharePoint 群組連接網站中，按一下 [**設定**]、 按一下 [**網站內容**]，和 [**網站設定**。</span><span class="sxs-lookup"><span data-stu-id="20987-300">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="20987-301">在 [網站設定] 頁面上的 [**網站集合管理** \> **內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="20987-301">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="20987-302">在 [原則] 頁面上\>**匯入** \> **瀏覽]** 尋找原則的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="20987-302">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="20987-303">選取已在其中儲存之原則的 XML 檔案\>**開啟**。</span><span class="sxs-lookup"><span data-stu-id="20987-303">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="20987-304">在匯入網站集合原則] 頁面上\>**匯入**新增原則至網站集合。</span><span class="sxs-lookup"><span data-stu-id="20987-304">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="20987-305">匯入的原則現在可以套用至一或多個網站或清單層級的內容類型。</span><span class="sxs-lookup"><span data-stu-id="20987-305">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
[<span data-ttu-id="20987-306">資訊管理原則啟用多久要保留稽核人員用來做什麼內容，並新增條碼的內容控制項為組織或文件的標籤。原則可協助強制遵守法律及政府規定或內部商務程序。身為管理員，您可以設定原則以控制如何追蹤文件及多久要保留的文件。您可以建立資訊管理原則可以在三個不同的位置的網站階層中從最大到最窄： 建立要在網站集合內的多個內容類型上使用的原則。建立網站內容類型的原則。建立清單或文件庫的原則。如需詳細資訊，請參閱資訊管理原則簡介。</span><span class="sxs-lookup"><span data-stu-id="20987-306">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents. A policy can help enforce compliance with legal and governmental regulations or internal business processes. As an administrator, you can set up a policy to control how to track documents and how long to retain documents.You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:Create a policy to use on multiple content types within a site collection.Create a policy for a site content type.Create a policy for a list or library.For more information, see Introduction to information management policies.</span></span>](create-info-mgmt-policies.md#__top)
  

