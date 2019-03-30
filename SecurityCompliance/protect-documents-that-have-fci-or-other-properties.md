---
title: 建立 DLP 原則來保護具有 FCI 或其他屬性的文件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 許多組織都已識別及分類藉由分類屬性在 Windows Server 檔案分類基礎結構 (FCI)、 在 SharePoint 中，此文件內容或文件屬性中的敏感資訊的程序套用的協力廠商系統。 如果這描述您的組織，您可以建立 DLP 原則會辨識已經由 Windows Server FCI 或其他系統，套用至文件的屬性，以便 DLP 原則可以在具有特定的 FCI 或其他的 Office 文件上強制執行的 Office 365屬性的值。
ms.openlocfilehash: ad643c77d477f6b9aaecb122010584510ea9bf7e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000576"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="03049-104">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="03049-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="03049-105">在 Office 365 中，您可以使用資料外洩防護 (DLP) 原則來識別、 監視和保護機密資訊。</span><span class="sxs-lookup"><span data-stu-id="03049-105">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information.</span></span> <span data-ttu-id="03049-106">許多組織都已識別及分類藉由分類屬性在 Windows Server 檔案分類基礎結構 (FCI)、 在 SharePoint 中，此文件內容或文件屬性中的敏感資訊的程序套用的協力廠商系統。</span><span class="sxs-lookup"><span data-stu-id="03049-106">Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system.</span></span> <span data-ttu-id="03049-107">如果這描述您的組織，您可以建立 DLP 原則會辨識已經由 Windows Server FCI 或其他系統，套用至文件的屬性，以便 DLP 原則可以在具有特定的 FCI 或其他的 Office 文件上強制執行的 Office 365屬性的值。</span><span class="sxs-lookup"><span data-stu-id="03049-107">If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![圖表顯示 Office 365 及外部的分類系統](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="03049-109">例如，組織可能使用 Windows Server FCI 使用社會安全號碼，例如個人識別資訊 (PII) 來識別文件，然後藉由設定**個人識別資訊**分類文件類型為基礎的屬性以**高**、**中度**、 **Low**、**公用**或**不 PII**和文件中找到的 PII 的次數。</span><span class="sxs-lookup"><span data-stu-id="03049-109">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document.</span></span> <span data-ttu-id="03049-110">在 Office 365 中，您可以建立 DLP 原則識別該屬性設為特定值，例如 **[高**] 和 [**中等**的文件，然後採取的動作，例如封鎖存取這些檔案。</span><span class="sxs-lookup"><span data-stu-id="03049-110">In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="03049-111">相同的原則可以有另一個採取不同的動作，如果屬性設為 [**低**，例如傳送電子郵件通知的規則。</span><span class="sxs-lookup"><span data-stu-id="03049-111">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="03049-112">如此一來，在 Office 365 中的 DLP 與 Windows Server FCI 整合，並可協助保護 Office 文件上傳或 Windows Server 為基礎的檔案伺服器從共用 Office 365。</span><span class="sxs-lookup"><span data-stu-id="03049-112">In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="03049-113">DLP 原則只會尋找特定的屬性名稱/值組。</span><span class="sxs-lookup"><span data-stu-id="03049-113">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="03049-114">可以用任何文件屬性，只要屬性不會有對應的 managed 的屬性，SharePoint 搜尋。</span><span class="sxs-lookup"><span data-stu-id="03049-114">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="03049-115">例如，SharePoint 網站集合可能會使用名**行程報告**為與名為**客戶**的必要欄位的內容類型。</span><span class="sxs-lookup"><span data-stu-id="03049-115">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="03049-116">每當人員建立行程報表時，必須先輸入客戶名稱。</span><span class="sxs-lookup"><span data-stu-id="03049-116">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="03049-117">此屬性名稱/值組也可用於 DLP 原則 — 例如，如果您想要封鎖存取文件中的外部使用者的 [**客戶**] 欄位包含**Contoso**時的規則。</span><span class="sxs-lookup"><span data-stu-id="03049-117">This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="03049-118">請注意，是否您想要將您的 DLP 原則套用至特定的 Office 365 標籤與內容，您應該不按照這裡的步驟。</span><span class="sxs-lookup"><span data-stu-id="03049-118">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="03049-119">相反地，了解如何[使用標籤作為 DLP 原則的條件](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="03049-119">Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="03049-120">建立 DLP 原則之前</span><span class="sxs-lookup"><span data-stu-id="03049-120">Before you create the DLP policy</span></span>

<span data-ttu-id="03049-121">您可以使用 Windows Server FCI 屬性或其他屬性中的 DLP 原則之前，您需要在 SharePoint 系統管理中心建立 managed 的屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-121">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="03049-122">以下是原因。</span><span class="sxs-lookup"><span data-stu-id="03049-122">Here's why.</span></span>
  
<span data-ttu-id="03049-123">在 SharePoint Online 和商務用 OneDrive，搜尋索引是藉由編目內容的網站 」 上建置。</span><span class="sxs-lookup"><span data-stu-id="03049-123">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites.</span></span> <span data-ttu-id="03049-124">編目程式挑選內容和中繼資料編目屬性的表單中的文件。</span><span class="sxs-lookup"><span data-stu-id="03049-124">The crawler picks up content and metadata from the documents in the form of crawled properties.</span></span> <span data-ttu-id="03049-125">搜尋結構描述可協助編目程式要揀選決定哪些內容和中繼資料。</span><span class="sxs-lookup"><span data-stu-id="03049-125">The search schema helps the crawler decide what content and metadata to pick up.</span></span> <span data-ttu-id="03049-126">中繼資料的範例是作者和文件的標題。</span><span class="sxs-lookup"><span data-stu-id="03049-126">Examples of metadata are the author and the title of a document.</span></span> <span data-ttu-id="03049-127">不過，若要從文件中取得的內容和中繼資料至搜尋索引，編目的屬性必須對應至 managed 屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-127">However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties.</span></span> <span data-ttu-id="03049-128">只有 managed 的屬性會保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="03049-128">Only managed properties are kept in the index.</span></span> <span data-ttu-id="03049-129">例如，作者相關的編目的屬性會對應至 managed 屬性與作者。</span><span class="sxs-lookup"><span data-stu-id="03049-129">For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="03049-130">這是很重要，因為在 Office 365 中的 DLP 以識別並分類您的網站上的敏感資訊並再將該敏感資訊儲存在安全搜尋索引的一部分使用搜尋編目程式。</span><span class="sxs-lookup"><span data-stu-id="03049-130">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="03049-131">當您將文件上傳至 Office 365 時，SharePoint 會自動建立根據文件屬性的編目的屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-131">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="03049-132">但是，若要使用 FCI 或其他屬性中的 DLP 原則，編目屬性，必須對應至 managed 屬性，以便使用該屬性的內容會保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="03049-132">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="03049-133">如需有關搜尋和 managed 的屬性的詳細資訊，請參閱 <<c0>管理 SharePoint Online 的搜尋結構描述。</span><span class="sxs-lookup"><span data-stu-id="03049-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="03049-134">步驟 1： 將具有所需屬性的文件上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="03049-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="03049-135">您首先要上傳文件與您想要參照在 DLP 原則中的屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-135">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="03049-136">Office 365 會偵測屬性，並自動從其建立編目的屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-136">Office 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="03049-137">在下一個步驟中，您將建立的 managed 的屬性，並再將 managed 的屬性對應至這個編目屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-137">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="03049-138">步驟 2： 建立 managed 的屬性</span><span class="sxs-lookup"><span data-stu-id="03049-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="03049-139">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="03049-139">Sign in to the Microsoft 365 admin center.</span></span>
    
2. <span data-ttu-id="03049-140">在左側導覽中，選擇 [**系統管理中心** \> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="03049-140">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="03049-141">You're now in the SharePoint admin center.</span><span class="sxs-lookup"><span data-stu-id="03049-141">You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="03049-142">在左側導覽中，選擇 [**搜尋**\>在 [**搜尋管理**] 頁面上\>**管理搜尋結構描述**。</span><span class="sxs-lookup"><span data-stu-id="03049-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 系統管理中心的搜尋管理頁面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="03049-144">在 [ **Managed 屬性**] 頁面上\>**新增 Managed 屬性**。</span><span class="sxs-lookup"><span data-stu-id="03049-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="03049-146">輸入的名稱和描述屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-146">Enter a name and description for the property.</span></span> <span data-ttu-id="03049-147">此名稱是什麼都會出現在 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="03049-147">This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="03049-148">**類型**，請選擇 [**文字**]。</span><span class="sxs-lookup"><span data-stu-id="03049-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="03049-149">在 [**主要特性**] 下選取 [**可查詢**] 和 [**可擷取**]。</span><span class="sxs-lookup"><span data-stu-id="03049-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="03049-150">在 [**對應至編目屬性**] 下\>**新增對應**。</span><span class="sxs-lookup"><span data-stu-id="03049-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="03049-151">在**編目屬性選項**] 對話方塊\>尋找和選取編目的屬性對應至 Windows Server FCI 屬性或其他屬性，您將您的 DLP 原則中使用\> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="03049-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![選取編目屬性對話方塊](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="03049-153">在頁面底部\> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="03049-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="03049-154">建立使用 FCI 屬性或其他屬性的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="03049-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="03049-155">在這個範例中，組織使用 FCI 其 Windows 伺服器型檔案伺服器上;具體而言，他們使用**個人識別資訊**向與名為的**高**、**中度**、 **Low**、**公用**和**不 PII**的可能值的 FCI 分類屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-155">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="03049-156">現在，想要利用其現有的 FCI 分類其 Office 365 中的 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="03049-156">Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="03049-157">首先，他們可以依照上述步驟，以在 SharePoint Online 中，這會對應至編目屬性會自動建立從 FCI 屬性建立 managed 的屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="03049-158">接下來，在建立 DLP 原則搭配兩者使用**文件屬性包含下列任一值**的條件的兩個規則：</span><span class="sxs-lookup"><span data-stu-id="03049-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="03049-159">**FCI PII 內容-高、 中度**如果 FCI 分類屬性**個人識別資訊**值**高**] 或 [**中等**，且與組織外部人員共用文件的第一個規則限制存取文件。</span><span class="sxs-lookup"><span data-stu-id="03049-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="03049-160">**FCI PII 內容-低**第二個規則會傳送通知如果 FCI 分類屬性**個人識別資訊**值**低**及文件的文件擁有者與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="03049-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="03049-161">使用 PowerShell 建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="03049-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="03049-162">請注意，**文件屬性包含下列任一值**的條件暫時無法提供 UI 的安全性&amp;合規性中心，但您仍然可以使用此條件可使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03049-162">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="03049-163">您可以使用`New\Set\Get-DlpCompliancePolicy`指令程式來使用 DLP 原則，並使用`New\Set\Get-DlpComplianceRule`具有 cmdlet`ContentPropertyContainsWords`參數，以新增**文件屬性包含下列任一值**的條件。</span><span class="sxs-lookup"><span data-stu-id="03049-163">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="03049-164">如需有關這些 cmdlet 的詳細資訊，請參閱[Office 365 安全性&amp;合規性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="03049-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="03049-165">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="03049-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="03049-166">藉由建立原則`New-DlpCompliancePolicy`。</span><span class="sxs-lookup"><span data-stu-id="03049-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="03049-167">以下是建立 DLP 原則套用至所有位置中的 PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="03049-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="03049-168">建立使用上述這兩個規則`New-DlpComplianceRule`、 其中一個規則是**低**的值，而另一個規則是 [**高**] 和 [**中等**值。</span><span class="sxs-lookup"><span data-stu-id="03049-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="03049-169">以下是建立這兩個規則的 PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="03049-169">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="03049-170">請注意，屬性名稱/值組會以引號括住，而且屬性名稱可以指定多個以逗號隔開沒有空格，例如的值`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="03049-170">Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="03049-171">請注意，Windows Server FCI 包含許多內建的屬性，包括在這個範例中所用的**個人識別資訊**。</span><span class="sxs-lookup"><span data-stu-id="03049-171">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="03049-172">每個屬性的可能值可以是不同的每個組織。</span><span class="sxs-lookup"><span data-stu-id="03049-172">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="03049-173">**高**、**中度**和這裡使用的**低**值是僅為範例。</span><span class="sxs-lookup"><span data-stu-id="03049-173">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="03049-174">為您的組織，您可以在 Windows Server 為基礎的檔案伺服器上的檔案伺服器資源管理員檢視其可能的值與 Windows Server FCI 分類屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-174">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="03049-175">如需詳細資訊，請參閱 <<c0>建立分類屬性。</span><span class="sxs-lookup"><span data-stu-id="03049-175">For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="03049-176">完成後，您的原則應該有兩個新的規則，同時使用的**文件屬性包含下列任一值**的條件。</span><span class="sxs-lookup"><span data-stu-id="03049-176">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="03049-177">請注意，這種情況將不會出現在 UI 中，雖然其他條件、 動作和設定將會出現。</span><span class="sxs-lookup"><span data-stu-id="03049-177">Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="03049-178">一個規則封鎖存取內容其中**個人識別資訊**屬性值為 [**高**] 或 [**中等**。</span><span class="sxs-lookup"><span data-stu-id="03049-178">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="03049-179">第二個規則，會將內容相關的通知傳送其中的**個人識別資訊**屬性等於**低**。</span><span class="sxs-lookup"><span data-stu-id="03049-179">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="03049-181">建立 DLP 原則之後</span><span class="sxs-lookup"><span data-stu-id="03049-181">After you create the DLP policy</span></span>

<span data-ttu-id="03049-182">執行以上各節中的步驟，將範本建立 DLP 原則，將會快速偵測內容與該屬性，但僅限內容的新上傳 （這樣的內容編製索引），或如果內容舊，但只要編輯 （這樣的內容重新編製索引）.</span><span class="sxs-lookup"><span data-stu-id="03049-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="03049-183">若要偵測寄件人該屬性的內容，您可能想要手動要求您的文件庫、 網站或網站集合重新編製索引，以便 DLP 原則所知的該屬性具有的所有內容。</span><span class="sxs-lookup"><span data-stu-id="03049-183">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property.</span></span> <span data-ttu-id="03049-184">在 SharePoint Online 中，會自動編目內容根據已定義的編目排程。</span><span class="sxs-lookup"><span data-stu-id="03049-184">In SharePoint Online, content is automatically crawled based on a defined crawl schedule.</span></span> <span data-ttu-id="03049-185">編目程式挑選自前次編目以來已變更及更新的索引的內容。</span><span class="sxs-lookup"><span data-stu-id="03049-185">The crawler picks up content that has changed since the last crawl and updates the index.</span></span> <span data-ttu-id="03049-186">如果您需要您的 DLP 原則來保護內容下一個排程編目之前，您可以採取下列步驟。</span><span class="sxs-lookup"><span data-stu-id="03049-186">If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="03049-187">重新編製索引的網站可能會造成大量負載搜尋系統上。</span><span class="sxs-lookup"><span data-stu-id="03049-187">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="03049-188">不要重新編製索引網站除非您的案例絕對需要它。</span><span class="sxs-lookup"><span data-stu-id="03049-188">Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="03049-189">如需詳細資訊，請參閱[手動要求編目和重新編製索引的網站、 文件庫或清單](http://go.microsoft.com/fwlink/p/?LinkID=627457)。</span><span class="sxs-lookup"><span data-stu-id="03049-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="03049-190">重新編製索引的網站 （選用）</span><span class="sxs-lookup"><span data-stu-id="03049-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="03049-191">在網站上，選擇 [**設定**（在右上方的齒輪圖示） \> **網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="03049-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="03049-192">選擇 [**搜尋**] 下的 [**搜尋與離線可用性** \> **網站重新編製索引**。</span><span class="sxs-lookup"><span data-stu-id="03049-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="03049-193">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="03049-193">More information</span></span>

- [<span data-ttu-id="03049-194">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="03049-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="03049-195">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="03049-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="03049-196">傳送通知並顯示原則提示的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="03049-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="03049-197">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="03049-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="03049-198">敏感資訊類型詳細目錄</span><span class="sxs-lookup"><span data-stu-id="03049-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

