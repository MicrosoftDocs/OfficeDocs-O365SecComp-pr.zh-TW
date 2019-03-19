---
title: 'Exchange Online Protection 中的 Exchange 系統管理中心 '
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Exchange 系統管理中心 (EAC) 是 Microsoft Exchange Online Protection (EOP) 的 Web 式管理主控台。
ms.openlocfilehash: d1e3ee90f3df20359634ae55286270b49d766324
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670428"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="2f58c-103">Exchange Online Protection 中的 Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="2f58c-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="2f58c-104">Exchange 系統管理中心 (EAC) 是 Microsoft Exchange Online Protection (EOP) 的 Web 式管理主控台。</span><span class="sxs-lookup"><span data-stu-id="2f58c-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="2f58c-p101">在尋找本主題的 Exchange 2013 版本嗎？請參閱[Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="2f58c-p102">在尋找本主題的 Exchange Online 版本嗎？請參閱[Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="2f58c-109">存取 EAC</span><span class="sxs-lookup"><span data-stu-id="2f58c-109">Accessing the EAC</span></span>

<span data-ttu-id="2f58c-110">在大多數情況下，EOP 客戶會透過 Microsoft 365 系統管理中心存取 EAC。</span><span class="sxs-lookup"><span data-stu-id="2f58c-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="2f58c-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span><span class="sxs-lookup"><span data-stu-id="2f58c-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="2f58c-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span><span class="sxs-lookup"><span data-stu-id="2f58c-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="2f58c-p104">您也可以透過下列 URL 直接存取 EAC 登入頁面：https://admin.protection.outlook.com/ecp/\<companydomain\>。例如，https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。指定使用者認證後，您會被直接帶往 EAC。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="2f58c-116">EAC 中常見的使用者介面元素</span><span class="sxs-lookup"><span data-stu-id="2f58c-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="2f58c-117">本節說明 EMC 中的使用者介面元素。</span><span class="sxs-lookup"><span data-stu-id="2f58c-117">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="2f58c-119">功能窗格</span><span class="sxs-lookup"><span data-stu-id="2f58c-119">Feature Pane</span></span>

<span data-ttu-id="2f58c-p105">這是您在 EAC 中執行大部分工作時的第一個導覽層級。功能窗格依功能區域組織。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="2f58c-122">**收件者** 您可在此檢視內部使用者和外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="2f58c-122">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="2f58c-123">**權限** 您可在此管理系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="2f58c-123">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="2f58c-124">**規範管理** 您可在此尋找稽核記錄和報告，例如系統管理員角色群組報告。</span><span class="sxs-lookup"><span data-stu-id="2f58c-124">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="2f58c-125">**保護** 您可在此管理組織的反惡意程式碼和反垃圾郵件保護，以及管理隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="2f58c-125">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="2f58c-126">**郵件流程** 您可在此管理規則、公認的網域和連接器，以及執行郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="2f58c-126">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="2f58c-127">定位字元</span><span class="sxs-lookup"><span data-stu-id="2f58c-127">Tabs</span></span>

<span data-ttu-id="2f58c-128">索引標籤是您的第二個導覽層級。</span><span class="sxs-lookup"><span data-stu-id="2f58c-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="2f58c-129">每一個功能區都包含不同的索引標籤，各自代表一項功能。</span><span class="sxs-lookup"><span data-stu-id="2f58c-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="2f58c-130">工具列</span><span class="sxs-lookup"><span data-stu-id="2f58c-130">Toolbar</span></span>

<span data-ttu-id="2f58c-p107">按一下大部分的索引標籤時，會看到一個工具列。工具列上的圖示會執行特定動作。下表描述圖示及其動作。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="2f58c-134">**圖示**</span><span class="sxs-lookup"><span data-stu-id="2f58c-134">**Icon**</span></span>|<span data-ttu-id="2f58c-135">**名稱**</span><span class="sxs-lookup"><span data-stu-id="2f58c-135">**Name**</span></span>|<span data-ttu-id="2f58c-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="2f58c-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![加入圖示](media/ITPro-EAC-AddIcon.gif)           <br/> |<span data-ttu-id="2f58c-138">新增</span><span class="sxs-lookup"><span data-stu-id="2f58c-138">Add, New</span></span>  <br/> |<span data-ttu-id="2f58c-p108">使用此圖示來建立新的物件。這些圖示中有些擁有一個關聯的向下箭號，您可以按一下以顯示所能建立的其他物件。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![編輯圖示](media/ITPro-EAC-EditIcon.gif)           <br/> |<span data-ttu-id="2f58c-142">編輯</span><span class="sxs-lookup"><span data-stu-id="2f58c-142">Edit</span></span>  <br/> |<span data-ttu-id="2f58c-143">使用此圖示來編輯物件。</span><span class="sxs-lookup"><span data-stu-id="2f58c-143">Use this icon to edit an object.</span></span>  <br/> |
|![刪除圖示](media/ITPro-EAC-DeleteIcon.gif)           <br/> |<span data-ttu-id="2f58c-145">刪除</span><span class="sxs-lookup"><span data-stu-id="2f58c-145">Delete</span></span>  <br/> |<span data-ttu-id="2f58c-p109">使用此圖示來刪除物件。部分刪除圖示擁有一個向下箭號，您可以按一下以顯示額外選項。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![搜尋圖示](media/ITPro-EAC-.gif)           <br/> |<span data-ttu-id="2f58c-149">搜尋</span><span class="sxs-lookup"><span data-stu-id="2f58c-149">Search</span></span>  <br/> |<span data-ttu-id="2f58c-150">使用此圖示來開啟搜尋方塊，您可在此處輸入想要尋找之物件的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="2f58c-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![重新整理圖示](media/ITPro-EAC-RefreshIcon.gif)           <br/> |<span data-ttu-id="2f58c-152">重新整理</span><span class="sxs-lookup"><span data-stu-id="2f58c-152">Refresh</span></span>  <br/> |<span data-ttu-id="2f58c-153">使用此圖示來重新整理清單檢視。</span><span class="sxs-lookup"><span data-stu-id="2f58c-153">Use this icon to refresh the list view.</span></span>  <br/> |
|![更多選項圖示](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |<span data-ttu-id="2f58c-155">更多選項</span><span class="sxs-lookup"><span data-stu-id="2f58c-155">More options</span></span>  <br/> |<span data-ttu-id="2f58c-p110">使用此圖示來檢視更多可對該索引標籤之物件執行的動作。例如，在 **[收件者 \> 使用者]** 中按一下此圖示會顯示可執行 **[進階搜尋]** 的選項。  </span><span class="sxs-lookup"><span data-stu-id="2f58c-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![向上箭號圖示](media/ITPro-EAC-UpArrowIcon.gif)![向下箭號圖示](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |<span data-ttu-id="2f58c-160">向上鍵和向下鍵</span><span class="sxs-lookup"><span data-stu-id="2f58c-160">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="2f58c-161">使用這些圖示向上或向下移動物件的優先順序。</span><span class="sxs-lookup"><span data-stu-id="2f58c-161">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![[移除] 圖示](media/ITPro-EAC-RemoveIcon.gif)           <br/> |<span data-ttu-id="2f58c-163">移除</span><span class="sxs-lookup"><span data-stu-id="2f58c-163">Remove</span></span>  <br/> |<span data-ttu-id="2f58c-164">使用此圖示來移除清單中的物件。</span><span class="sxs-lookup"><span data-stu-id="2f58c-164">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="2f58c-165">清單檢視</span><span class="sxs-lookup"><span data-stu-id="2f58c-165">List View</span></span>

<span data-ttu-id="2f58c-p111">當您選取索引標籤時，大部分情況下會看見清單檢視。EAC 清單檢視內可檢視的限制約為 10,000 個物件。此外，也包括分頁功能，所以你可以將結果分頁顯示。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="2f58c-169">詳細資料窗格</span><span class="sxs-lookup"><span data-stu-id="2f58c-169">Details Pane</span></span>

<span data-ttu-id="2f58c-p112">當您從清單檢視中選取物件時，該物件的相關資訊就會顯示在詳細資料窗格中。在部分情況下，詳細資料窗格包括管理工作。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="2f58c-172">自有磚與說明</span><span class="sxs-lookup"><span data-stu-id="2f58c-172">Me tile and Help</span></span>

<span data-ttu-id="2f58c-p113">**[自有磚]** 可讓您登出 EAC，然後以不同使用者的身分登入。您可以從 **[說明]**![說明圖示](media/ITPro-EAC-HelpIcon.gif) 下拉式功能表執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2f58c-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="2f58c-175">**說明：** 按一下 ![說明圖示](media/ITPro-EAC-HelpIcon.gif) 即可檢視線上說明內容。</span><span class="sxs-lookup"><span data-stu-id="2f58c-175">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span> 
    
2. <span data-ttu-id="2f58c-p114">**停用說明泡泡圖** [說明泡泡圖] 會在您建立或編輯物件時，顯示欄位的內容說明。您可以關閉 [說明泡泡圖]，或是在停用的狀態下將它開啟。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="2f58c-178">**著作權** 按一下此連結可以閱讀 Exchange Online Protection 的著作權聲明。</span><span class="sxs-lookup"><span data-stu-id="2f58c-178">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="2f58c-179">**隱私權** 按一下可閱讀 Exchange Online Protection 的隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="2f58c-179">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="2f58c-180">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="2f58c-180">Supported Browsers</span></span>

<span data-ttu-id="2f58c-p115">為享有 EAC 最佳使用體驗，建議您一律使用最新的瀏覽器、Office 用戶端和應用程式。我們也建議您隨時安裝最新的軟體更新。如需此服務支援的瀏覽器和系統需求的詳細資訊，請參閱＜[Office 365 系統需求](https://go.microsoft.com/fwlink/p/?LinkID=402699)＞。</span><span class="sxs-lookup"><span data-stu-id="2f58c-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="2f58c-184">EOP 的支援語言</span><span class="sxs-lookup"><span data-stu-id="2f58c-184">Supported languages in EOP</span></span>

<span data-ttu-id="2f58c-185">Exchange Online Protection 支援且可使用下列語言。</span><span class="sxs-lookup"><span data-stu-id="2f58c-185">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="2f58c-186">阿姆哈拉文</span><span class="sxs-lookup"><span data-stu-id="2f58c-186">Amharic</span></span>
    
- <span data-ttu-id="2f58c-187">阿拉伯文</span><span class="sxs-lookup"><span data-stu-id="2f58c-187">Arabic</span></span>
    
- <span data-ttu-id="2f58c-188">巴斯克文 (巴斯克文)</span><span class="sxs-lookup"><span data-stu-id="2f58c-188">Basque (Basque)</span></span>
    
- <span data-ttu-id="2f58c-189">孟加拉文 (印度)</span><span class="sxs-lookup"><span data-stu-id="2f58c-189">Bengali (India)</span></span>
    
- <span data-ttu-id="2f58c-190">保加利亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-190">Bulgarian</span></span>
    
- <span data-ttu-id="2f58c-191">卡達隆尼亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-191">Catalan</span></span>
    
- <span data-ttu-id="2f58c-192">簡體中文</span><span class="sxs-lookup"><span data-stu-id="2f58c-192">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="2f58c-193">繁體中文</span><span class="sxs-lookup"><span data-stu-id="2f58c-193">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="2f58c-194">克羅埃西亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-194">Croatian</span></span>
    
- <span data-ttu-id="2f58c-195">捷克文</span><span class="sxs-lookup"><span data-stu-id="2f58c-195">Czech</span></span>
    
- <span data-ttu-id="2f58c-196">丹麥文</span><span class="sxs-lookup"><span data-stu-id="2f58c-196">Danish</span></span>
    
- <span data-ttu-id="2f58c-197">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="2f58c-197">Dutch</span></span>
    
- <span data-ttu-id="2f58c-198">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="2f58c-198">Dutch</span></span>
    
- <span data-ttu-id="2f58c-199">英文</span><span class="sxs-lookup"><span data-stu-id="2f58c-199">English</span></span>
    
- <span data-ttu-id="2f58c-200">愛沙尼亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-200">Estonian</span></span>
    
- <span data-ttu-id="2f58c-201">菲律賓文 (菲律賓)</span><span class="sxs-lookup"><span data-stu-id="2f58c-201">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="2f58c-202">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="2f58c-202">Finnish</span></span>
    
- <span data-ttu-id="2f58c-203">法文</span><span class="sxs-lookup"><span data-stu-id="2f58c-203">French</span></span>
    
- <span data-ttu-id="2f58c-204">加里斯亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-204">Galician</span></span>
    
- <span data-ttu-id="2f58c-205">德文</span><span class="sxs-lookup"><span data-stu-id="2f58c-205">German</span></span>
    
- <span data-ttu-id="2f58c-206">希臘文</span><span class="sxs-lookup"><span data-stu-id="2f58c-206">Greek</span></span>
    
- <span data-ttu-id="2f58c-207">古吉拉特文</span><span class="sxs-lookup"><span data-stu-id="2f58c-207">Gujarati</span></span>
    
- <span data-ttu-id="2f58c-208">希伯來文</span><span class="sxs-lookup"><span data-stu-id="2f58c-208">Hebrew</span></span>
    
- <span data-ttu-id="2f58c-209">印度文</span><span class="sxs-lookup"><span data-stu-id="2f58c-209">Hindi</span></span>
    
- <span data-ttu-id="2f58c-210">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="2f58c-210">Hungarian</span></span>
    
- <span data-ttu-id="2f58c-211">冰島文</span><span class="sxs-lookup"><span data-stu-id="2f58c-211">Icelandic</span></span>
    
- <span data-ttu-id="2f58c-212">印尼文</span><span class="sxs-lookup"><span data-stu-id="2f58c-212">Indonesian</span></span>
    
- <span data-ttu-id="2f58c-213">義大利文</span><span class="sxs-lookup"><span data-stu-id="2f58c-213">Italian</span></span>
    
- <span data-ttu-id="2f58c-214">日文</span><span class="sxs-lookup"><span data-stu-id="2f58c-214">Japanese</span></span>
    
- <span data-ttu-id="2f58c-215">埃納德文</span><span class="sxs-lookup"><span data-stu-id="2f58c-215">Kannada</span></span>
    
- <span data-ttu-id="2f58c-216">哈薩克文</span><span class="sxs-lookup"><span data-stu-id="2f58c-216">Kazakh</span></span>
    
- <span data-ttu-id="2f58c-217">史瓦希里文</span><span class="sxs-lookup"><span data-stu-id="2f58c-217">Kiswahili</span></span>
    
- <span data-ttu-id="2f58c-218">韓文</span><span class="sxs-lookup"><span data-stu-id="2f58c-218">Korean</span></span>
    
- <span data-ttu-id="2f58c-219">拉脫維亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-219">Latvian</span></span>
    
- <span data-ttu-id="2f58c-220">立陶宛文</span><span class="sxs-lookup"><span data-stu-id="2f58c-220">Lithuanian</span></span>
    
- <span data-ttu-id="2f58c-221">馬來文 (汶萊)</span><span class="sxs-lookup"><span data-stu-id="2f58c-221">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="2f58c-222">馬來文 (馬來西亞)</span><span class="sxs-lookup"><span data-stu-id="2f58c-222">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="2f58c-223">馬來亞拉姆文</span><span class="sxs-lookup"><span data-stu-id="2f58c-223">Malayalam</span></span>
    
- <span data-ttu-id="2f58c-224">馬拉提文</span><span class="sxs-lookup"><span data-stu-id="2f58c-224">Marathi</span></span>
    
- <span data-ttu-id="2f58c-225">挪威文 (巴克摩)</span><span class="sxs-lookup"><span data-stu-id="2f58c-225">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="2f58c-226">挪威文 (尼洛斯克)</span><span class="sxs-lookup"><span data-stu-id="2f58c-226">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="2f58c-227">歐利亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-227">Oriya</span></span>
    
- <span data-ttu-id="2f58c-228">波斯文</span><span class="sxs-lookup"><span data-stu-id="2f58c-228">Persian</span></span>
    
- <span data-ttu-id="2f58c-229">波蘭文</span><span class="sxs-lookup"><span data-stu-id="2f58c-229">Polish</span></span>
    
- <span data-ttu-id="2f58c-230">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="2f58c-230">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="2f58c-231">葡萄牙文 (葡萄牙)</span><span class="sxs-lookup"><span data-stu-id="2f58c-231">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="2f58c-232">羅馬尼亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-232">Romanian</span></span>
    
- <span data-ttu-id="2f58c-233">俄文</span><span class="sxs-lookup"><span data-stu-id="2f58c-233">Russian</span></span>
    
- <span data-ttu-id="2f58c-234">塞爾維亞文 (斯拉夫、塞爾維亞)</span><span class="sxs-lookup"><span data-stu-id="2f58c-234">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="2f58c-235">塞爾維亞文 (拉丁)</span><span class="sxs-lookup"><span data-stu-id="2f58c-235">Serbian (Latin)</span></span>
    
- <span data-ttu-id="2f58c-236">斯洛伐克文</span><span class="sxs-lookup"><span data-stu-id="2f58c-236">Slovak</span></span>
    
- <span data-ttu-id="2f58c-237">斯洛維尼亞文</span><span class="sxs-lookup"><span data-stu-id="2f58c-237">Slovenian</span></span>
    
- <span data-ttu-id="2f58c-238">西班牙文</span><span class="sxs-lookup"><span data-stu-id="2f58c-238">Spanish</span></span>
    
- <span data-ttu-id="2f58c-239">瑞典文</span><span class="sxs-lookup"><span data-stu-id="2f58c-239">Swedish</span></span>
    
- <span data-ttu-id="2f58c-240">坦米爾文</span><span class="sxs-lookup"><span data-stu-id="2f58c-240">Tamil</span></span>
    
- <span data-ttu-id="2f58c-241">特拉古文</span><span class="sxs-lookup"><span data-stu-id="2f58c-241">Telugu</span></span>
    
- <span data-ttu-id="2f58c-242">泰文</span><span class="sxs-lookup"><span data-stu-id="2f58c-242">Thai</span></span>
    
- <span data-ttu-id="2f58c-243">土耳其文</span><span class="sxs-lookup"><span data-stu-id="2f58c-243">Turkish</span></span>
    
- <span data-ttu-id="2f58c-244">烏克蘭文</span><span class="sxs-lookup"><span data-stu-id="2f58c-244">Ukrainian</span></span>
    
- <span data-ttu-id="2f58c-245">烏都文</span><span class="sxs-lookup"><span data-stu-id="2f58c-245">Urdu</span></span>
    
- <span data-ttu-id="2f58c-246">越南文</span><span class="sxs-lookup"><span data-stu-id="2f58c-246">Vietnamese</span></span>
    
- <span data-ttu-id="2f58c-247">威爾斯文</span><span class="sxs-lookup"><span data-stu-id="2f58c-247">Welsh</span></span>
    

