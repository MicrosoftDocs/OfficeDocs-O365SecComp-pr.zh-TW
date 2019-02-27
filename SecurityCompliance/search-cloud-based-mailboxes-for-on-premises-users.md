---
title: 搜尋 Office 365 中的雲端架構信箱的內部使用者
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用 Office 365 安全性內容搜尋工具&amp;規範中心來搜尋並匯出 MicrosoftTeams 聊天室資料 （稱為 1xN 聊天） Exchange 混合部署中的內部部署使用者。
ms.openlocfilehash: 148a5766342fcdd52e0505a59729cad3d2993908
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296696"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a><span data-ttu-id="74e91-103">搜尋 Office 365 中的雲端架構信箱的內部使用者</span><span class="sxs-lookup"><span data-stu-id="74e91-103">Searching cloud-based mailboxes for on-premises users in Office 365</span></span>

<span data-ttu-id="74e91-p101">如果您的組織具有 Exchange 混合部署並已啟用的 Microsoft 小組，使用者可以使用小組聊天應用程式的立即訊息。雲端使用者的 （也稱為 1xN 聊天） 小組聊天室資料會儲存到其主要的雲端架構信箱。內部使用者使用時的小組聊天應用程式，其主要信箱是位於內部部署。若要解決此限制，Microsoft 已經發行雲端儲存區域 （稱為雲端架構信箱的內部使用者） 儲存內部使用者的小組聊天室資料以建立所在的新功能。這可讓您使用 Office 365 安全性內容搜尋工具&amp;規範中心來搜尋並匯出小組內部使用者的聊天室資料。</span><span class="sxs-lookup"><span data-stu-id="74e91-p101">If your organization has an Exchange hybrid deployment and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging. For the cloud-based user, the Teams chat data (also called 1xN chats) is saved to their primary cloud-based mailbox. When an on-premises user uses the Team chat application, their primary mailbox is located on-premises. To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users. This lets you use the Content Search tool in the Office 365 Security &amp; Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="74e91-109">以下是需求和限制的設定和設定及搜尋雲端架構信箱的內部部署使用者：</span><span class="sxs-lookup"><span data-stu-id="74e91-109">Here are the requirements and limitation for setting up and to set up and search cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="74e91-p102">您在內部部署目錄服務 （如 Active Directory) 中的使用者帳戶必須具有 Azure Active Directory、 Office 365 的目錄服務同步處理。這表示郵件使用者帳戶會在 Office 365 中建立且其主要信箱位於內部部署組織中的使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="74e91-p102">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Office 365. This means that a mail user account is created in Office 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>
    
- <span data-ttu-id="74e91-p103">雲端架構信箱的內部部署使用者是使用唯一的存放區小組聊天室資料。內部部署使用者無法登入雲端架構信箱或以任何方法存取。無法用來傳送或接收電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="74e91-p103">The cloud-based mailbox for on-premises users is used only store Teams chat data. An on-premises user can't sign in to the cloud-based mailbox or access in any way. It can't be used to send or receive email messages.</span></span> 
    
- <span data-ttu-id="74e91-p104">您必須要求提交至 Microsoft 技術支援人員以啟用搜尋小組聊天室資料在雲端架構信箱的內部使用者的組織。請參閱[歸檔 Microsoft 技術支援人員以啟用此功能安全性要求&amp;規範中心](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center)本文中。</span><span class="sxs-lookup"><span data-stu-id="74e91-p104">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users. See [Filing a request with Microsoft Support to enable this feature in the Security &amp; Compliance Center](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center) in this article.</span></span> 
    
 <span data-ttu-id="74e91-p105">**附註：** 小組通道交談永遠儲存在雲端架構信箱與小組相關聯。這表示您可以使用搜尋通道交談而不具有檔案的支援要求內容搜尋。如需關於搜尋小組通道交談，請參閱[搜尋的 Microsoft 小組與 Office 365 群組](content-search.md#searching-microsoft-teams-and-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="74e91-p105">**Note:** Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team. That means you can use Content Search to search channel conversations without have to file a support request. For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="74e91-120">運作方式</span><span class="sxs-lookup"><span data-stu-id="74e91-120">How it works</span></span>

<span data-ttu-id="74e91-p106">如果 Microsoft 小組啟用使用者的內部部署信箱，且其使用者帳戶/身分識別具有已同步至雲端，Microsoft 建立雲端架構信箱儲存 1xN 小組聊天室資料。小組聊天室資料會儲存在雲端架構信箱之後，它已編製索引的搜尋。這可讓您使用內容搜尋 （和 eDiscovery 案例相關聯的搜尋） 搜尋、 預覽，並將內部部署使用者的小組聊天室資料匯出。您也可以使用**\*ComplianceSearch**指令程式在 Office 365 安全性&amp;規範中心 PowerShell 搜尋團隊與內部使用者的聊天室資料。</span><span class="sxs-lookup"><span data-stu-id="74e91-p106">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data. After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search. This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users. You can also use **\*ComplianceSearch** cmdlets in the Office 365 Security &amp; Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="74e91-125">下圖顯示的工作流程的方式小組聊天室的內部使用者的資料可供搜尋、 預覽，並匯出。</span><span class="sxs-lookup"><span data-stu-id="74e91-125">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![雲端中的 Microsoft 小組的內部部署使用者儲存區](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="74e91-127">除了此新功能，仍然可用內容搜尋來搜尋、 預覽，並匯出的小組雲端型 SharePoint 網站] 及 [Exchange 信箱中的內容相關聯每一個 Microsoft 小組及 1xN 小組 Exchange Online 信箱的聊天室資料雲端式的使用者。</span><span class="sxs-lookup"><span data-stu-id="74e91-127">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a><span data-ttu-id="74e91-128">歸檔 Microsoft 技術支援人員以啟用此功能安全性要求&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="74e91-128">Filing a request with Microsoft Support to enable this feature in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="74e91-p107">您必須檔案要求 Microsoft 技術支援人員以啟用您的組織来使用圖形使用者介面在安全性&amp;規範中心搜尋小組聊天室資料在雲端架構信箱的內部部署使用者。請注意這項功能可在 Office 365 安全性&amp;規範中心 PowerShell。您不需要支援要求提交至 PowerShell 用於搜尋的內部部署使用者的小組聊天室資料。</span><span class="sxs-lookup"><span data-stu-id="74e91-p107">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security &amp; Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users. Note that this feature is available in Office 365 Security &amp; Compliance Center PowerShell. You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="74e91-132">當您要求提交至 Microsoft 支援包括下列資訊：</span><span class="sxs-lookup"><span data-stu-id="74e91-132">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="74e91-133">Office 365 組織的預設網域名稱。</span><span class="sxs-lookup"><span data-stu-id="74e91-133">The default domain name of your Office 365 organization.</span></span>
    
- <span data-ttu-id="74e91-p108">租用戶名稱和 Office 365 組織租用戶識別碼。您可以找到這些 Azure Active Directory 入口網站 (在 [**管理**下\>**屬性**)。請參閱[尋找 Office 365 租用戶識別碼](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="74e91-p108">The tenant name and tenant ID of your Office 365 organization. You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**). See [Find your Office 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>
    
- <span data-ttu-id="74e91-p109">下列的標題或支援要求的用途的描述： [啟用應用程式的內部部署使用者內容搜尋]。這有助於路由要求傳送到 Office 365 eDiscovery 工程小組人員實作要求。</span><span class="sxs-lookup"><span data-stu-id="74e91-p109">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span> 
    
<span data-ttu-id="74e91-p110">工程變更後，Microsoft 技術支援人員會傳送給您評估的部署的日期。部署程序通常採用 2-3 週後支援將要求送出的附註。</span><span class="sxs-lookup"><span data-stu-id="74e91-p110">After the engineering change is made, Microsoft Support will send you an estimated deployment date. Note that the deployment process usually takes 2-3 weeks after you submit the support request.</span></span> 
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="74e91-141">在啟用此功能之後會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="74e91-141">What happens after this feature is enabled?</span></span>

<span data-ttu-id="74e91-142">這項功能在 Office 365 組織中部署之後，下列變更進行中內容搜尋並在搜尋相關聯的 eDiscovery 案例中安全性&amp;規範中心：</span><span class="sxs-lookup"><span data-stu-id="74e91-142">After this feature is deployed in your Office 365 organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security &amp; Compliance Center:</span></span>
  
- <span data-ttu-id="74e91-143">在內容搜尋**位置**] 下新增**內部部署使用者的新增 Office 應用程式內容**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="74e91-143">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span> 
    
    ![「 新增內部部署使用者的 Office 應用程式內容 」] 核取方塊新增至內容搜尋使用者介面](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="74e91-145">內部使用者會顯示在使用中選取要搜尋的使用者信箱的內容位置選擇器。</span><span class="sxs-lookup"><span data-stu-id="74e91-145">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span> 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="74e91-146">搜尋團隊在雲端架構信箱的內部部署使用者內容的聊天室</span><span class="sxs-lookup"><span data-stu-id="74e91-146">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="74e91-147">已啟用功能之後，您可以使用內容的搜尋安全性&amp;規範中心搜尋小組聊天室資料在雲端架構信箱的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="74e91-147">After the feature has been enabled, you can use Content Search in the Security &amp; Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> 
  
1. <span data-ttu-id="74e91-148">安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **內容搜尋**</span><span class="sxs-lookup"><span data-stu-id="74e91-148">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**</span></span>
    
2. <span data-ttu-id="74e91-149">在 [**搜尋**] 頁面上，按一下 [![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜尋**。</span><span class="sxs-lookup"><span data-stu-id="74e91-149">On the **Search** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>
    
    <span data-ttu-id="74e91-p111">如先前所述**的內部使用者的新增 Office 應用程式內容**] 核取方塊會顯示 [**位置**] 下。請注意則預設會選取。</span><span class="sxs-lookup"><span data-stu-id="74e91-p111">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**. Note that it is selected by default.</span></span>
    
3. <span data-ttu-id="74e91-p112">建立關鍵字查詢及必要時新增至搜尋查詢的條件。僅針對小組搜尋聊天室資料，您可以在 [**關鍵字**] 方塊中新增下列查詢：</span><span class="sxs-lookup"><span data-stu-id="74e91-p112">Create the keyword query and add conditions to the search query if necessary. To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span> 
    
    ```
    kind:im
    ``` 

4. <span data-ttu-id="74e91-154">此時，您可以選擇其中一個 [**位置**] 下的下列選項：</span><span class="sxs-lookup"><span data-stu-id="74e91-154">At this point, you can choose one of the following options under **Locations**:</span></span>
    
    - <span data-ttu-id="74e91-p113">**所有位置**-選取這個選項可在組織中搜尋之所有使用者的信箱。選取核取方塊時，也可搜尋的內部部署使用者的所有雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="74e91-p113">**All locations** - Select this option to search the mailboxes of all users in your organization. When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span> 
    
    - <span data-ttu-id="74e91-p114">**特定位置**-選取這個選項，然後按一下 [**修改**\>選擇使用者、 群組或小組來搜尋特定的信箱。如先前所述位置選擇將可讓您搜尋內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="74e91-p114">**Specific locations** - Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes. As previously explained, the locations picker will let you search for on-premises users.</span></span> 
    
5. <span data-ttu-id="74e91-p115">儲存並執行搜尋。從雲端架構信箱的內部使用者的任何搜尋結果可以預覽像任何其他搜尋結果。此外，您可以您可以將 （包括小組聊天室的任何資料） 的搜尋結果匯出至 PST 檔案。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="74e91-p115">Save and run the search. Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results. Additionally, you can you can export the search results (including any Teams chat data) to a PST file. For more information, see:</span></span> 
    
    - [<span data-ttu-id="74e91-163">建立新的搜尋</span><span class="sxs-lookup"><span data-stu-id="74e91-163">Create a new search</span></span>](content-search.md#create-a-new-search)
    
    - [<span data-ttu-id="74e91-164">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="74e91-164">Preview search results</span></span>](content-search.md#preview-search-results)
    
    - [<span data-ttu-id="74e91-165">從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="74e91-165">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="74e91-166">使用 PowerShell 搜尋小組聊天室資料在雲端架構信箱的內部使用者</span><span class="sxs-lookup"><span data-stu-id="74e91-166">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="74e91-p116">您可以使用**New ComplianceSearch**和**設定 ComplianceSearch** cmdlet Office 365 安全性&amp;規範中心 PowerShell 搜尋內部部署使用者的雲端架構信箱。如先前所述，您不需要支援要求提交至 PowerShell 用於搜尋的內部部署使用者的小組聊天室資料。</span><span class="sxs-lookup"><span data-stu-id="74e91-p116">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Office 365 Security &amp; Compliance Center PowerShell to search the cloud-based mailbox for on-premises users. As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="74e91-169">[連線至 Office 365 安全性&amp;規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="74e91-169">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="74e91-170">執行下列 PowerShell 命令來建立新的內容會搜尋雲端架構信箱的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="74e91-170">Run the following PowerShell command to create a new content searches the cloud-based mailboxes of on-premises users.</span></span>
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    <span data-ttu-id="74e91-p117">*IncludeUserAppContent*參數用來指定雲端架構信箱的使用者或*ExchangeLocation*參數所指定的使用者。*AllowNotFoundExchangeLocationsEnabled*可讓內部使用者的雲端架構信箱。當您使用`$true`此參數，搜尋的值不會嘗試執行之前，先驗證信箱是否存在。這是因為這些類型的信箱不解決與一般信箱搜尋雲端架構信箱的內部部署使用者所需。</span><span class="sxs-lookup"><span data-stu-id="74e91-p117">The  *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter. The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users. When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs. This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span> 
    
    <span data-ttu-id="74e91-175">下列範例會搜尋小組的聊天室 （亦即立即訊息） 包含關鍵字"redstone"中的雲端架構信箱的 Sara Davis 身為內部部署組織中的使用者 Contoso。</span><span class="sxs-lookup"><span data-stu-id="74e91-175">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="74e91-176">建立新的搜尋之後，請務必使用**開始 ComplianceSearch**指令程式執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="74e91-176">After you create a new search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="74e91-177">使用這些 cmdlet 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="74e91-177">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="74e91-178">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="74e91-178">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [<span data-ttu-id="74e91-179">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="74e91-179">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [<span data-ttu-id="74e91-180">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="74e91-180">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a><span data-ttu-id="74e91-181">已知問題</span><span class="sxs-lookup"><span data-stu-id="74e91-181">Known issues</span></span>

- <span data-ttu-id="74e91-p118">目前，您可以僅搜尋、 預覽並在雲端架構信箱的內容匯出內部部署使用者。將內部部署使用者雲端架構信箱設定保留相關聯的 eDiscovery 案件或將它指派給 Office 365 保留原則不支援。</span><span class="sxs-lookup"><span data-stu-id="74e91-p118">Currently, you can only search, preview, and export content in cloud-based mailboxes for on-premises users. Placing a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case or assigning it to an Office 365 retention policy is not supported.</span></span> 
    
- <span data-ttu-id="74e91-p119">EDiscovery 內容位置選擇包含顯示內部使用者，將可讓您選取其。不過，之前清楚保留不會套用至內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="74e91-p119">The content location picker for eDiscovery holds displays on-premises users and will let you select them. However, as previously explained the hold will not be applied to the on-premises user.</span></span>
    
## <a name="frequently-asked-questions"></a><span data-ttu-id="74e91-186">常見問題集</span><span class="sxs-lookup"><span data-stu-id="74e91-186">Frequently asked questions</span></span>

 <span data-ttu-id="74e91-187">**在雲端架構信箱的內部部署使用者的位置？**</span><span class="sxs-lookup"><span data-stu-id="74e91-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="74e91-188">建立和儲存在相同的資料中心 Office 365 組織中的雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="74e91-188">Cloud-based mailboxes are created and stored in the same datacenter as your Office 365 organization.</span></span> 
  
 <span data-ttu-id="74e91-189">**是否有不支援要求送出任何其他需求吗？**</span><span class="sxs-lookup"><span data-stu-id="74e91-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="74e91-p120">如先前所述，具有 prem 上信箱的使用者的身分識別必須同步處理至雲端架構組織，讓每個內部部署使用者帳戶在 Office 365 中建立對應的郵件使用者帳戶。此外，您的組織必須具備的 Office 365 企業版訂閱，例如 Office 365 企業版 E1、 E3 或 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="74e91-p120">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365. Additionally, your organization must have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span> 
  
 <span data-ttu-id="74e91-192">**是否有遺失小組聊天室資料如果使用者的內部部署信箱移轉至雲端的風險吗？**</span><span class="sxs-lookup"><span data-stu-id="74e91-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="74e91-p121">[否]。當您將主要信箱的內部部署使用者移轉至雲端時，該使用者的小組聊天室資料將移轉至新雲端架構主要信箱。</span><span class="sxs-lookup"><span data-stu-id="74e91-p121">No. When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="74e91-195">**我可以將套用 eDiscovery 保留或 Office 365 的保留原則對內部部署使用者吗？**</span><span class="sxs-lookup"><span data-stu-id="74e91-195">**Can I apply an eDiscovery hold or Office 365 retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="74e91-196">否。</span><span class="sxs-lookup"><span data-stu-id="74e91-196">No.</span></span>
  
 <span data-ttu-id="74e91-197">**內容搜尋尋找舊小組聊天室的內部部署使用者的時間之前我的組織可以送出將要求重新啟用此功能吗？**</span><span class="sxs-lookup"><span data-stu-id="74e91-197">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="74e91-p122">Microsoft 啟動的內部部署使用者的小組聊天室資料儲存在 2018 年 1 月 31、。如此，如果此日期自，已 Active Directory 與 Azure Active Directory 之間同步的內部部署小組使用者身分識別，然後自己小組聊天室的資料會儲存在雲端架構信箱和可供搜尋使用內容搜尋。Microsoft 也儲存在雲端架構信箱的內部部署使用者中的小組聊天室的資料前 2018 年 1 月 31、 運作。更多有關此資訊會是推出。</span><span class="sxs-lookup"><span data-stu-id="74e91-p122">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018. So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data will be stored in a cloud-based mailbox and will be searchable using Content Search. Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users. More information about this will be available soon.</span></span>
