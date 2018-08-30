---
title: 建立 DLP 原則來保護具有 FCI 或其他內容的文件
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: 1b9e3c6c-4308-4a20-b11e-c37b8013e177
description: 許多組織已識別及分類敏感資訊是使用分類屬性在 Windows Server 檔案分類基礎結構 (FCI)、 SharePoint 中的文件屬性或文件屬性中的程序套用的協力廠商系統。如果此說明您的組織，您可以建立的 DLP 原則可辨識屬性已由 Windows Server FCI 或其他系統，套用至文件以便 DLP 原則可以在 Office 文件與特定 FCI 或其他強制執行 Office 365 中屬性的值。
ms.openlocfilehash: 057cdad981249e39d6f39f231d8d60ab977e717a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013687"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="395b4-104">建立 DLP 原則來保護具有 FCI 或其他內容的文件</span><span class="sxs-lookup"><span data-stu-id="395b4-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="395b4-p102">在 Office 365 中，您可以使用資料外洩防護 (DLP) 原則來識別、監視和保護敏感資訊。許多組織都已有其程序，可使用 Windows Server 檔案分類基礎結構 (FCI) 中的分類屬性、SharePoint 中的文件屬性或協力廠商系統所套用的文件屬性，來識別和分類敏感資訊。如果您的組織也是如此，您可以在 Office 365 中建立 DLP 原則來辨識由 Windows Server FCI 或其他系統已套用至文件的屬性，讓 DLP 原則可以強制執行於使用特定 FCI 或其他屬性值的 Office 文件上。</span><span class="sxs-lookup"><span data-stu-id="395b4-p102">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information. Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system. If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![圖表顯示 Office 365 及外部的分類系統](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="395b4-p103">例如您的組織可能會使用 Windows Server FCI 使用社會安全編號，例如的個人識別資訊 (PII) 來識別文件，然後用來分類藉由設定**個人身分資訊**以**高**、**中等**、**低**、**公用**或**不 PII**屬性會根據類型和文件中找到的 PII 次數。在 Office 365 中，您可以建立的 DLP 原則識別該屬性設定為 **[高**] 和 [**中等**特定值的文件，然後採取動作例如封鎖存取這些檔案。將相同的原則可以有另一個採用不同的動作如果屬性設定為 [**低**，例如傳送的電子郵件通知的規則。如此一來，在 Office 365 中的 DLP 會與 Windows Server FCI 整合並可協助保護 Office 文件上傳或共用 Office 365 的 Windows Server 為基礎的檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="395b4-p103">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document. In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files. The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification. In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="395b4-p104">DLP 原則只會尋找特定的屬性名稱/值組。可以使用任何文件屬性，只要有 SharePoint 搜尋的對應的 managed 的屬性的屬性。例如 SharePoint 網站集合可能會使用名為必要欄位名為**客戶****來回報表**內容類型。每當人員會建立來回報表，他們必須輸入客戶名稱。此屬性的名稱/值組也可用於 DLP 原則 — 例如，如果您要封鎖外部使用者的文件時也能存取 「**客戶**」 欄位包含**Contoso**規則。</span><span class="sxs-lookup"><span data-stu-id="395b4-p104">A DLP policy simply looks for a specific property name/value pair. Any document property can be used, as long as the property has a corresponding managed property for SharePoint search. For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**. Whenever a person creates a trip report, they must enter the customer name. This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="395b4-p105">請注意是否您想要將您的 DLP 原則套用至特定的 Office 365 標籤的內容，您應該不遵循的步驟。而是了解如何[使用做為條件 DLP 原則中的標籤](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="395b4-p105">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here. Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="395b4-120">建立 DLP 原則之前</span><span class="sxs-lookup"><span data-stu-id="395b4-120">Before you create the DLP policy</span></span>

<span data-ttu-id="395b4-p106">您可以使用 Windows Server FCI 屬性或其他屬性中的 DLP 原則之前，您需要在 SharePoint 管理中心內建立的 managed 的屬性。以下是為何。</span><span class="sxs-lookup"><span data-stu-id="395b4-p106">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center. Here's why.</span></span>
  
<span data-ttu-id="395b4-p107">範例</span><span class="sxs-lookup"><span data-stu-id="395b4-p107">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="395b4-p108">這是很重要的，因為 Office 365 中的 DLP 會使用搜尋編目程式來識別和分類網站上的敏感資訊，然後將此敏感資訊儲存在搜尋索引的安全區域。當您將文件上傳至 Office 365 時，SharePoint 會根據文件屬性自動建立編目屬性。但若要在 DLP 原則中使用 FCI 或其他屬性，該編目屬性必須對應至 Managed 屬性，使具有該屬性的內容保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="395b4-p108">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index. When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties. But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="395b4-133">如需有關搜尋和 managed 的屬性的詳細資訊，請參閱 ＜ [Manage SharePoint Online 中的搜尋結構描述](http://go.microsoft.com/fwlink/p/?LinkID=627454)。</span><span class="sxs-lookup"><span data-stu-id="395b4-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="395b4-134">步驟 1：將具有所需屬性的文件上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="395b4-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="395b4-p109">您必須先將上傳文件與您想要參考在 DLP 原則的屬性。Office 365 會偵測屬性，並自動從其建立編目的屬性。在下一個步驟中，您將建立的 managed 的屬性，然後將 managed 的屬性對應至此編目屬性。</span><span class="sxs-lookup"><span data-stu-id="395b4-p109">You first need to upload a document with the property that you want to reference in your DLP policy. Office 365 will detect the property and automatically create a crawled property from it. In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="395b4-138">步驟 2：建立 Managed 屬性</span><span class="sxs-lookup"><span data-stu-id="395b4-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="395b4-139">登入 Office 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="395b4-139">Sign in to the Office 365 admin center.</span></span>
    
2. <span data-ttu-id="395b4-p110">在左導覽列中，選擇 [ **Admin 中心** \> **SharePoint**。您現在是在 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="395b4-p110">In the left navigation, choose **Admin centers** \> **SharePoint**. You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="395b4-142">在左導覽列中，選擇 [**搜尋**\>在 [**搜尋管理**] 頁面上\>**管理搜尋結構描述**。</span><span class="sxs-lookup"><span data-stu-id="395b4-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 系統管理中心的搜尋管理頁面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="395b4-144">在 [ **Managed 屬性**] 頁面上\>**新增 Managed 屬性**。</span><span class="sxs-lookup"><span data-stu-id="395b4-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="395b4-p111">輸入屬性的名稱和描述。此名稱將會出現在您的 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="395b4-p111">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="395b4-148">**類型**，選擇 [**文字**]。</span><span class="sxs-lookup"><span data-stu-id="395b4-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="395b4-149">在 [**主要特性**、 選取**設定為可查詢**及**Retrievable**。</span><span class="sxs-lookup"><span data-stu-id="395b4-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="395b4-150">[**對應至編目屬性** \> **新增對應**。</span><span class="sxs-lookup"><span data-stu-id="395b4-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="395b4-151">在 [**編目屬性選取項目**] 對話方塊中\>尋找和選取編目的屬性對應至 Windows Server FCI 屬性或 DLP 原則中要使用其他屬性\> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="395b4-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![選取編目屬性對話方塊](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="395b4-153">在頁面底部\> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="395b4-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="395b4-154">建立使用 FCI 屬性或其他屬性的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="395b4-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="395b4-p112">在這個範例中，組織已在其 Windows Server 為基礎的檔案伺服器 ； 使用 FCI尤其他們所使用且可能的值為**High**、**中等**、**低**、**公用**和**不 PII**名為**個人身分資訊**之 FCI 分類屬性。現在要利用 Office 365 中其 DLP 原則中的其現有 FCI 分類。</span><span class="sxs-lookup"><span data-stu-id="395b4-p112">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**. Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="395b4-157">首先，他們可以依照前述步驟在 SharePoint Online 中建立 Managed 屬性，而此屬性會對應至自動從 FCI 屬性建立的編目屬性。</span><span class="sxs-lookup"><span data-stu-id="395b4-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="395b4-158">接下來，他們建立這兩個規則同時使用**文件摘要資訊包含任何這些值**的條件 DLP 原則：</span><span class="sxs-lookup"><span data-stu-id="395b4-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="395b4-159">**FCI PII 的內容-高]、 [設定一般**如果 FCI 分類屬性**個人身分資訊**等於**高**或**中等**並與組織外部人員共用文件的第一個規則限制存取文件。</span><span class="sxs-lookup"><span data-stu-id="395b4-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="395b4-160">**FCI PII 內容-低**第二個規則傳送通知給 FCI 分類屬性**個人身分資訊**等於**低**及文件的文件擁有者與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="395b4-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="395b4-161">使用 PowerShell 建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="395b4-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="395b4-p113">請注意**文件摘要資訊包含任何這些值**的條件為暫時無法提供的安全性 UI 中&amp;規範中心，但您仍然可以使用這種情況使用 PowerShell。您可以使用`New\Set\Get-DlpCompliancePolicy`指令程式來使用 DLP 原則，並使用`New\Set\Get-DlpComplianceRule`cmdlet 搭配`ContentPropertyContainsWords`參數來新增**文件摘要資訊包含任何這些值**的條件。</span><span class="sxs-lookup"><span data-stu-id="395b4-p113">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell. You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="395b4-164">如需這些 cmdlet 的詳細資訊，請參閱[Office 365 安全性&amp;規範中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="395b4-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="395b4-165">連線至 Office 365 安全性&amp;規範中心使用遠端 PowerShell</span><span class="sxs-lookup"><span data-stu-id="395b4-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="395b4-166">使用建立原則`New-DlpCompliancePolicy`。</span><span class="sxs-lookup"><span data-stu-id="395b4-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="395b4-167">以下是建立套用至所有位置的 DLP 原則的 PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="395b4-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="395b4-168">建立使用上述兩個規則`New-DlpComplianceRule`，其中一項規則是**低**值，而其他規則是 [**高**] 和 [**中等**值。</span><span class="sxs-lookup"><span data-stu-id="395b4-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="395b4-p114">以下是建立這兩個規則的 PowerShell 範例。請注意屬性名稱/值組會以雙引號括住，而且屬性名稱可以指定多個值以任何空格，以逗號分隔類似`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="395b4-p114">Here is a PowerShell example that creates these two rules. Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="395b4-p115">請注意 Windows Server FCI 包含許多內建的屬性，包括在這個範例中所用的**個人識別資訊**。每個屬性的可能值可以是不同的每一個組織。**高**、**中等**和**低**值在這裡使用的僅限範例。您的組織，您可以檢視其可能的值與 Windows Server FCI 分類屬性在 Windows Server 為基礎的檔案伺服器上的檔案伺服器資源管理員。如需詳細資訊，請參閱 ＜ [Create 分類屬性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。</span><span class="sxs-lookup"><span data-stu-id="395b4-p115">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="395b4-p116">完成後，您的原則應該有兩個同時使用**文件摘要資訊包含任何這些值**條件的新規則。請注意此條件可將不會出現在 UI 中上述其他條件、 動作和設定將會出現。</span><span class="sxs-lookup"><span data-stu-id="395b4-p116">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition. Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="395b4-p117">一項規則封鎖的存取權其中**個人身分資訊**屬性等於**高**或**中等**的內容。第二個規則傳送其中**個人身分資訊**屬性等於**低**內容的通知。</span><span class="sxs-lookup"><span data-stu-id="395b4-p117">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**. A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="395b4-181">建立 DLP 原則之後</span><span class="sxs-lookup"><span data-stu-id="395b4-181">After you create the DLP policy</span></span>

<span data-ttu-id="395b4-182">執行前文各節中的步驟會建立快速地將偵測的 DLP 原則內容與該屬性，但只有在 （使內容編製索引） 新上傳的內容，或如果的內容舊但剛編輯 （以便將內容重新編製索引）.</span><span class="sxs-lookup"><span data-stu-id="395b4-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="395b4-p118">若要在所有位置偵測具有該屬性的內容，您可以手動要求您的文件庫、網站或網站集合重新編製索引，使 DLP 原則可辨識具有該屬性的所有內容。在 SharePoint Online 中，內容會根據已定義的編目排程自動編目。編目程式會提取在上次編目後有所變更的內容，並更新索引。如果您在下一次排程的編目之前需要以 DLP 原則保護內容，您可以執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="395b4-p118">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="395b4-p119">重新編製索引的網站可能會造成巨大負載搜尋系統上。不要重新編製索引網站除非您的案例絕對需要。</span><span class="sxs-lookup"><span data-stu-id="395b4-p119">Re-indexing a site can cause a massive load on the search system. Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="395b4-189">如需詳細資訊，請參閱[手動要求編目及重新編製索引的文件庫或清單的網站](http://go.microsoft.com/fwlink/p/?LinkID=627457)。</span><span class="sxs-lookup"><span data-stu-id="395b4-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="395b4-190">為網站重新編製索引 (選用)</span><span class="sxs-lookup"><span data-stu-id="395b4-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="395b4-191">在網站上，選擇 [**設定**（在右上方的齒輪圖示） \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="395b4-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="395b4-192">在 [**搜尋**] 下選擇**搜尋與離線可用性** \> **網站重新編製索引**。</span><span class="sxs-lookup"><span data-stu-id="395b4-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="395b4-193">其他資訊</span><span class="sxs-lookup"><span data-stu-id="395b4-193">More information</span></span>

- [<span data-ttu-id="395b4-194">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="395b4-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="395b4-195">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="395b4-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="395b4-196">針對 DLP 原則傳送通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="395b4-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="395b4-197">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="395b4-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="395b4-198">敏感資訊類型詳細目錄</span><span class="sxs-lookup"><span data-stu-id="395b4-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

