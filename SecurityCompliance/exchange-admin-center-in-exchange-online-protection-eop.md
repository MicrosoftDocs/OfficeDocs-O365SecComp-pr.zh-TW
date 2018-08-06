---
title: 'Exchange Online Protection 中的 Exchange 系統管理中心 '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
description: Exchange 系統管理中心 (EAC) 是 Microsoft Exchange Online Protection (EOP) 的 Web 式管理主控台。
ms.openlocfilehash: 99640e561b41e47a74e7c22f0bbdcacd0dd80bd7
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026310"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="b4413-103">Exchange Online Protection 中的 Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="b4413-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="b4413-104">Exchange 系統管理中心 (EAC) 是 Microsoft Exchange Online Protection (EOP) 的 Web 式管理主控台。</span><span class="sxs-lookup"><span data-stu-id="b4413-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="b4413-p101">在尋找本主題的 Exchange 2013 版本嗎？請參閱[Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b4413-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="b4413-p102">在尋找本主題的 Exchange Online 版本嗎？請參閱[Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b4413-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="b4413-109">存取 EAC</span><span class="sxs-lookup"><span data-stu-id="b4413-109">Accessing the EAC</span></span>

<span data-ttu-id="b4413-p103">在大多數情況下，EOP 客戶會透過 Office 365 系統管理中心存取 EAC。您可在 **[管理磚]** (位於 **[自有磚]** 旁) 的下拉式功能表中找到 EOP 的連結。按一下 **[管理磚]** 並從下拉式功能表中選取 **[Exchange Online Protection]** 以將您帶往 EAC。</span><span class="sxs-lookup"><span data-stu-id="b4413-p103">In most cases, EOP customers will access the EAC through the Office 365 admin center. You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile. Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="b4413-p104">您也可以透過下列 URL 直接存取 EAC 登入頁面：https://admin.protection.outlook.com/ecp/\<companydomain\>。例如，https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。指定使用者認證後，您會被直接帶往 EAC。</span><span class="sxs-lookup"><span data-stu-id="b4413-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="b4413-116">EAC 中常見的使用者介面元素</span><span class="sxs-lookup"><span data-stu-id="b4413-116">Common user interface elements in the EAC</span></span>
<span data-ttu-id="b4413-117"><a name="BKMK_CommonUserInterfaceElements"> </a></span><span class="sxs-lookup"><span data-stu-id="b4413-117"></span></span>

<span data-ttu-id="b4413-118">本節說明 EMC 中的使用者介面元素。</span><span class="sxs-lookup"><span data-stu-id="b4413-118">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="b4413-120">功能窗格</span><span class="sxs-lookup"><span data-stu-id="b4413-120">Feature Pane</span></span>

<span data-ttu-id="b4413-p105">這是您在 EAC 中執行大部分工作時的第一個導覽層級。功能窗格依功能區域組織。</span><span class="sxs-lookup"><span data-stu-id="b4413-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="b4413-123">**收件者** 您可在此檢視內部使用者和外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="b4413-123">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="b4413-124">**權限** 您可在此管理系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="b4413-124">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="b4413-125">**規範管理** 您可在此尋找稽核記錄和報告，例如系統管理員角色群組報告。</span><span class="sxs-lookup"><span data-stu-id="b4413-125">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="b4413-126">**保護** 您可在此管理組織的反惡意程式碼和反垃圾郵件保護，以及管理隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="b4413-126">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="b4413-127">**郵件流程** 您可在此管理規則、公認的網域和連接器，以及執行郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="b4413-127">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="b4413-128">索引標籤</span><span class="sxs-lookup"><span data-stu-id="b4413-128">Tabs</span></span>

<span data-ttu-id="b4413-p106">索引標籤是您的第二個導覽層級。每一個功能區都包含不同的索引標籤，各自代表一項功能。</span><span class="sxs-lookup"><span data-stu-id="b4413-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="b4413-131">工具列</span><span class="sxs-lookup"><span data-stu-id="b4413-131">Toolbar</span></span>

<span data-ttu-id="b4413-p107">按一下大部分的索引標籤時，會看到一個工具列。工具列上的圖示會執行特定動作。下表描述圖示及其動作。</span><span class="sxs-lookup"><span data-stu-id="b4413-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="b4413-135">**圖示**</span><span class="sxs-lookup"><span data-stu-id="b4413-135">**Icon**</span></span>|<span data-ttu-id="b4413-136">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b4413-136">**Name**</span></span>|<span data-ttu-id="b4413-137">**Action**</span><span class="sxs-lookup"><span data-stu-id="b4413-137">**Action**</span></span>|
|:-----|:-----|:-----|
|![加入圖示](media/ITPro-EAC-AddIcon.png)           <br/> |<span data-ttu-id="b4413-139">新增</span><span class="sxs-lookup"><span data-stu-id="b4413-139">Add, New</span></span>  <br/> |<span data-ttu-id="b4413-p108">使用此圖示來建立新的物件。這些圖示中有些擁有一個關聯的向下箭號，您可以按一下以顯示所能建立的其他物件。</span><span class="sxs-lookup"><span data-stu-id="b4413-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![編輯圖示](media/ITPro-EAC-EditIcon.png)           <br/> |<span data-ttu-id="b4413-143">編輯</span><span class="sxs-lookup"><span data-stu-id="b4413-143">Edit</span></span>  <br/> |<span data-ttu-id="b4413-144">使用此圖示來編輯物件。</span><span class="sxs-lookup"><span data-stu-id="b4413-144">Use this icon to edit an object.</span></span>  <br/> |
|![刪除圖示](media/ITPro-EAC-DeleteIcon.png)           <br/> |<span data-ttu-id="b4413-146">刪除</span><span class="sxs-lookup"><span data-stu-id="b4413-146">Delete</span></span>  <br/> |<span data-ttu-id="b4413-p109">使用此圖示來刪除物件。部分刪除圖示擁有一個向下箭號，您可以按一下以顯示額外選項。</span><span class="sxs-lookup"><span data-stu-id="b4413-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![搜尋圖示](media/ITPro-EAC-.png)           <br/> |<span data-ttu-id="b4413-150">搜尋</span><span class="sxs-lookup"><span data-stu-id="b4413-150">Search</span></span>  <br/> |<span data-ttu-id="b4413-151">使用此圖示來開啟搜尋方塊，您可在此處輸入想要尋找之物件的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="b4413-151">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![重新整理圖示](media/ITPro-EAC-RefreshIcon.png)           <br/> |<span data-ttu-id="b4413-153">重新整理</span><span class="sxs-lookup"><span data-stu-id="b4413-153">Refresh</span></span>  <br/> |<span data-ttu-id="b4413-154">使用此圖示來重新整理清單檢視。</span><span class="sxs-lookup"><span data-stu-id="b4413-154">Use this icon to refresh the list view.</span></span>  <br/> |
|![更多選項圖示](media/ITPro-EAC-MoreOptionsIcon.png)           <br/> |<span data-ttu-id="b4413-156">更多選項</span><span class="sxs-lookup"><span data-stu-id="b4413-156">More options</span></span>  <br/> |<span data-ttu-id="b4413-p110">使用此圖示來檢視更多可對該索引標籤之物件執行的動作。例如，在 **[收件者 \> 使用者]** 中按一下此圖示會顯示可執行 **[進階搜尋]** 的選項。  </span><span class="sxs-lookup"><span data-stu-id="b4413-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![向上箭號圖示](media/ITPro-EAC-UpArrowIcon.png)![向下箭號圖示](media/ITPro-EAC-DownArrowIcon.png)           <br/> |<span data-ttu-id="b4413-161">向上鍵和向下鍵</span><span class="sxs-lookup"><span data-stu-id="b4413-161">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="b4413-162">使用這些圖示向上或向下移動物件的優先順序。</span><span class="sxs-lookup"><span data-stu-id="b4413-162">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![[移除] 圖示](media/ITPro-EAC-RemoveIcon.png)           <br/> |<span data-ttu-id="b4413-164">移除</span><span class="sxs-lookup"><span data-stu-id="b4413-164">Remove</span></span>  <br/> |<span data-ttu-id="b4413-165">使用此圖示來移除清單中的物件。</span><span class="sxs-lookup"><span data-stu-id="b4413-165">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="b4413-166">清單檢視</span><span class="sxs-lookup"><span data-stu-id="b4413-166">List View</span></span>

<span data-ttu-id="b4413-p111">當您選取索引標籤時，大部分情況下會看見清單檢視。EAC 清單檢視內可檢視的限制約為 10,000 個物件。此外，也包括分頁功能，所以你可以將結果分頁顯示。</span><span class="sxs-lookup"><span data-stu-id="b4413-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="b4413-170">詳細資料窗格</span><span class="sxs-lookup"><span data-stu-id="b4413-170">Details Pane</span></span>

<span data-ttu-id="b4413-p112">當您從清單檢視中選取物件時，該物件的相關資訊就會顯示在詳細資料窗格中。在部分情況下，詳細資料窗格包括管理工作。</span><span class="sxs-lookup"><span data-stu-id="b4413-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="b4413-173">自有磚與說明</span><span class="sxs-lookup"><span data-stu-id="b4413-173">Me tile and Help</span></span>

<span data-ttu-id="b4413-p113">**[自有磚]** 可讓您登出 EAC，然後以不同使用者的身分登入。您可以從 **[說明]**![說明圖示](media/ITPro-EAC-HelpIcon.png) 下拉式功能表執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b4413-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.png) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="b4413-176">**說明：** 按一下 ![說明圖示](media/ITPro-EAC-HelpIcon.png) 即可檢視線上說明內容。</span><span class="sxs-lookup"><span data-stu-id="b4413-176">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.png) to view the online help content.</span></span> 
    
2. <span data-ttu-id="b4413-p114">**停用說明泡泡圖** [說明泡泡圖] 會在您建立或編輯物件時，顯示欄位的內容說明。您可以關閉 [說明泡泡圖]，或是在停用的狀態下將它開啟。</span><span class="sxs-lookup"><span data-stu-id="b4413-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="b4413-179">**著作權** 按一下此連結可以閱讀 Exchange Online Protection 的著作權聲明。</span><span class="sxs-lookup"><span data-stu-id="b4413-179">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="b4413-180">**隱私權** 按一下可閱讀 Exchange Online Protection 的隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="b4413-180">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="b4413-181">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="b4413-181">Supported Browsers</span></span>
<span data-ttu-id="b4413-182"><a name="BKMK_SupportedBrowsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b4413-182"></span></span>

<span data-ttu-id="b4413-p115">為享有 EAC 最佳使用體驗，建議您一律使用最新的瀏覽器、Office 用戶端和應用程式。我們也建議您隨時安裝最新的軟體更新。如需此服務支援的瀏覽器和系統需求的詳細資訊，請參閱＜[Office 365 系統需求](https://go.microsoft.com/fwlink/p/?LinkID=402699)＞。</span><span class="sxs-lookup"><span data-stu-id="b4413-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="b4413-186">EOP 的支援語言</span><span class="sxs-lookup"><span data-stu-id="b4413-186">Supported languages in EOP</span></span>
<span data-ttu-id="b4413-187"><a name="BKMK_SupportedLanguages"> </a></span><span class="sxs-lookup"><span data-stu-id="b4413-187"></span></span>

<span data-ttu-id="b4413-188">Exchange Online Protection 支援且可使用下列語言。</span><span class="sxs-lookup"><span data-stu-id="b4413-188">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="b4413-189">阿姆哈拉文</span><span class="sxs-lookup"><span data-stu-id="b4413-189">Amharic</span></span>
    
- <span data-ttu-id="b4413-190">阿拉伯文</span><span class="sxs-lookup"><span data-stu-id="b4413-190">Arabic</span></span>
    
- <span data-ttu-id="b4413-191">巴斯克文 (巴斯克文)</span><span class="sxs-lookup"><span data-stu-id="b4413-191">Basque (Basque)</span></span>
    
- <span data-ttu-id="b4413-192">孟加拉文 (印度)</span><span class="sxs-lookup"><span data-stu-id="b4413-192">Bengali (India)</span></span>
    
- <span data-ttu-id="b4413-193">保加利亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-193">Bulgarian</span></span>
    
- <span data-ttu-id="b4413-194">卡達隆尼亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-194">Catalan</span></span>
    
- <span data-ttu-id="b4413-195">簡體中文</span><span class="sxs-lookup"><span data-stu-id="b4413-195">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="b4413-196">繁體中文</span><span class="sxs-lookup"><span data-stu-id="b4413-196">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="b4413-197">克羅埃西亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-197">Croatian</span></span>
    
- <span data-ttu-id="b4413-198">捷克文</span><span class="sxs-lookup"><span data-stu-id="b4413-198">Czech</span></span>
    
- <span data-ttu-id="b4413-199">丹麥文</span><span class="sxs-lookup"><span data-stu-id="b4413-199">Danish</span></span>
    
- <span data-ttu-id="b4413-200">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="b4413-200">Dutch</span></span>
    
- <span data-ttu-id="b4413-201">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="b4413-201">Dutch</span></span>
    
- <span data-ttu-id="b4413-202">英文</span><span class="sxs-lookup"><span data-stu-id="b4413-202">English</span></span>
    
- <span data-ttu-id="b4413-203">愛沙尼亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-203">Estonian</span></span>
    
- <span data-ttu-id="b4413-204">菲律賓文 (菲律賓)</span><span class="sxs-lookup"><span data-stu-id="b4413-204">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="b4413-205">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="b4413-205">Finnish</span></span>
    
- <span data-ttu-id="b4413-206">法文</span><span class="sxs-lookup"><span data-stu-id="b4413-206">French</span></span>
    
- <span data-ttu-id="b4413-207">加里斯亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-207">Galician</span></span>
    
- <span data-ttu-id="b4413-208">德文</span><span class="sxs-lookup"><span data-stu-id="b4413-208">German</span></span>
    
- <span data-ttu-id="b4413-209">希臘文</span><span class="sxs-lookup"><span data-stu-id="b4413-209">Greek</span></span>
    
- <span data-ttu-id="b4413-210">古吉拉特文</span><span class="sxs-lookup"><span data-stu-id="b4413-210">Gujarati</span></span>
    
- <span data-ttu-id="b4413-211">希伯來文</span><span class="sxs-lookup"><span data-stu-id="b4413-211">Hebrew</span></span>
    
- <span data-ttu-id="b4413-212">印度文</span><span class="sxs-lookup"><span data-stu-id="b4413-212">Hindi</span></span>
    
- <span data-ttu-id="b4413-213">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="b4413-213">Hungarian</span></span>
    
- <span data-ttu-id="b4413-214">冰島文</span><span class="sxs-lookup"><span data-stu-id="b4413-214">Icelandic</span></span>
    
- <span data-ttu-id="b4413-215">印尼文</span><span class="sxs-lookup"><span data-stu-id="b4413-215">Indonesian</span></span>
    
- <span data-ttu-id="b4413-216">義大利文</span><span class="sxs-lookup"><span data-stu-id="b4413-216">Italian</span></span>
    
- <span data-ttu-id="b4413-217">日文</span><span class="sxs-lookup"><span data-stu-id="b4413-217">Japanese</span></span>
    
- <span data-ttu-id="b4413-218">埃納德文</span><span class="sxs-lookup"><span data-stu-id="b4413-218">Kannada</span></span>
    
- <span data-ttu-id="b4413-219">哈薩克文</span><span class="sxs-lookup"><span data-stu-id="b4413-219">Kazakh</span></span>
    
- <span data-ttu-id="b4413-220">史瓦希里文</span><span class="sxs-lookup"><span data-stu-id="b4413-220">Kiswahili</span></span>
    
- <span data-ttu-id="b4413-221">韓文</span><span class="sxs-lookup"><span data-stu-id="b4413-221">Korean</span></span>
    
- <span data-ttu-id="b4413-222">拉脫維亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-222">Latvian</span></span>
    
- <span data-ttu-id="b4413-223">立陶宛文</span><span class="sxs-lookup"><span data-stu-id="b4413-223">Lithuanian</span></span>
    
- <span data-ttu-id="b4413-224">馬來文 (汶萊)</span><span class="sxs-lookup"><span data-stu-id="b4413-224">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="b4413-225">馬來文 (馬來西亞)</span><span class="sxs-lookup"><span data-stu-id="b4413-225">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="b4413-226">馬來亞拉姆文</span><span class="sxs-lookup"><span data-stu-id="b4413-226">Malayalam</span></span>
    
- <span data-ttu-id="b4413-227">馬拉提文</span><span class="sxs-lookup"><span data-stu-id="b4413-227">Marathi</span></span>
    
- <span data-ttu-id="b4413-228">挪威文 (巴克摩)</span><span class="sxs-lookup"><span data-stu-id="b4413-228">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="b4413-229">挪威文 (尼洛斯克)</span><span class="sxs-lookup"><span data-stu-id="b4413-229">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="b4413-230">歐利亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-230">Oriya</span></span>
    
- <span data-ttu-id="b4413-231">波斯文</span><span class="sxs-lookup"><span data-stu-id="b4413-231">Persian</span></span>
    
- <span data-ttu-id="b4413-232">波蘭文</span><span class="sxs-lookup"><span data-stu-id="b4413-232">Polish</span></span>
    
- <span data-ttu-id="b4413-233">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="b4413-233">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="b4413-234">葡萄牙文 (葡萄牙)</span><span class="sxs-lookup"><span data-stu-id="b4413-234">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="b4413-235">羅馬尼亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-235">Romanian</span></span>
    
- <span data-ttu-id="b4413-236">俄文</span><span class="sxs-lookup"><span data-stu-id="b4413-236">Russian</span></span>
    
- <span data-ttu-id="b4413-237">塞爾維亞文 (斯拉夫、塞爾維亞)</span><span class="sxs-lookup"><span data-stu-id="b4413-237">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="b4413-238">塞爾維亞文 (拉丁)</span><span class="sxs-lookup"><span data-stu-id="b4413-238">Serbian (Latin)</span></span>
    
- <span data-ttu-id="b4413-239">斯洛伐克文</span><span class="sxs-lookup"><span data-stu-id="b4413-239">Slovak</span></span>
    
- <span data-ttu-id="b4413-240">斯洛維尼亞文</span><span class="sxs-lookup"><span data-stu-id="b4413-240">Slovenian</span></span>
    
- <span data-ttu-id="b4413-241">西班牙文</span><span class="sxs-lookup"><span data-stu-id="b4413-241">Spanish</span></span>
    
- <span data-ttu-id="b4413-242">瑞典文</span><span class="sxs-lookup"><span data-stu-id="b4413-242">Swedish</span></span>
    
- <span data-ttu-id="b4413-243">坦米爾文</span><span class="sxs-lookup"><span data-stu-id="b4413-243">Tamil</span></span>
    
- <span data-ttu-id="b4413-244">特拉古文</span><span class="sxs-lookup"><span data-stu-id="b4413-244">Telugu</span></span>
    
- <span data-ttu-id="b4413-245">泰文</span><span class="sxs-lookup"><span data-stu-id="b4413-245">Thai</span></span>
    
- <span data-ttu-id="b4413-246">土耳其文</span><span class="sxs-lookup"><span data-stu-id="b4413-246">Turkish</span></span>
    
- <span data-ttu-id="b4413-247">烏克蘭文</span><span class="sxs-lookup"><span data-stu-id="b4413-247">Ukrainian</span></span>
    
- <span data-ttu-id="b4413-248">烏都文</span><span class="sxs-lookup"><span data-stu-id="b4413-248">Urdu</span></span>
    
- <span data-ttu-id="b4413-249">越南文</span><span class="sxs-lookup"><span data-stu-id="b4413-249">Vietnamese</span></span>
    
- <span data-ttu-id="b4413-250">威爾斯文</span><span class="sxs-lookup"><span data-stu-id="b4413-250">Welsh</span></span>
    

