---
title: 從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: '從 Office 365 安全性內容搜尋匯出搜尋結果&amp;規範中心到本機電腦。Emaill 電子郵件結果會匯出成 PST 檔案。內容從 SharePoint 和 OneDrive for Business 的網站會匯出為原生 Office 文件。 '
ms.openlocfilehash: 739d2c162dac938d593e0b65ebca3bf2101ec469
ms.sourcegitcommit: 87a3ca55b6e9cf7e9ccf73e64013dc78dd7660f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2018
ms.locfileid: "25494064"
---
# <a name="export-content-search-results-from-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="d5826-105">從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="d5826-105">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="d5826-p102">成功執行內容的搜尋之後，您可以將搜尋結果匯出到本機電腦。當您將電子郵件結果匯出時，他們正在為 PST 檔案下載到電腦。當您匯出 SharePoint 與內容 OneDrive for Business 的網站時，都要匯出的原生 Office 文件複本。有一些額外的文件和隨附匯出的搜尋結果的報告。</span><span class="sxs-lookup"><span data-stu-id="d5826-p102">After a Content Search is successfully run, you can export the search results to a local computer. When you export email results, they're downloaded to your computer as PST files. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents are exported. There are additional documents and reports that are included with the exported search results.</span></span>
  
<span data-ttu-id="d5826-p103">此外，當您將其匯出 （做為個別的郵件） 將解密的內容的搜尋結果中包含任何 RMS 加密電子郵件。預設會啟用此解密功能的 eDiscovery 管理員角色群組的成員。這是因為 RMS 解密管理角色指派給此角色群組。匯出搜尋結果時請參閱如需詳細資訊 RMS 解密[的詳細資訊](#more-information)] 區段。</span><span class="sxs-lookup"><span data-stu-id="d5826-p103">Additionally, any RMS-encrypted email messages that are included in the results of a Content Search will be decrypted when you export them (as individual messages). This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. See the [More information](#more-information) section for details about RMS decryption when you export search results.</span></span> 
  
<span data-ttu-id="d5826-114">匯出內容的搜尋結果包括準備結果，並再將它們下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d5826-114">Exporting the results of a Content Search involves preparing the results, and then downloading them to a local computer.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d5826-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="d5826-115">Before you begin</span></span>

- <span data-ttu-id="d5826-p104">若要匯出搜尋結果，您必須指定給 Office 365 安全性的匯出管理角色&amp;規範中心。此角色指派給內建的 eDiscovery 管理員角色群組。它不是預設指派給組織管理角色群組。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p104">To export search results, you have to be assigned the Export management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager role group. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="d5826-120">您要用來匯出搜尋結果的電腦必須符合下列系統需求：</span><span class="sxs-lookup"><span data-stu-id="d5826-120">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="d5826-121">Windows 7 和更新版本的 32 或 64 位元版本


</span><span class="sxs-lookup"><span data-stu-id="d5826-121">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="d5826-122">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d5826-122">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="d5826-123">支援的瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="d5826-123">A supported browser:</span></span>
    
     - <span data-ttu-id="d5826-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d5826-124">Microsoft Edge</span></span>
    
        <span data-ttu-id="d5826-125">或</span><span class="sxs-lookup"><span data-stu-id="d5826-125">OR</span></span>
    
     - <span data-ttu-id="d5826-126">Microsoft Internet Explorer 10 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d5826-126">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="d5826-p105">**附註：** Microsoft 不會製造協力廠商擴充功能或 ClickOnce 應用程式的附加元件。不支援將匯出使用不受支援的瀏覽器與協力廠商擴充功能或附加元件的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d5826-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
- <span data-ttu-id="d5826-p106">當您下載搜尋結果 （步驟 2 中所述） 時，您可以藉由您用來匯出搜尋結果的電腦上設定 Windows 登錄設定增加下載速度。如需詳細資訊，請參閱[增加匯出 eDiscovery 搜尋結果從 Office 365 時的下載速度](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p106">When you download search results (described in Step 2), you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
    
- <span data-ttu-id="d5826-p107">當您將搜尋結果匯出資料會暫時儲存在 Microsoft 雲端中的唯一 Microsoft Azure 儲存位置之前就會下載至您的本機電腦。請確定您的組織可以連線到 Azure，這是在端點**\*。 blob.core.windows.net** （萬用字元代表您匯出的唯一識別碼）。會在建立之後的兩週刪除搜尋結果資料從 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="d5826-p107">When you export search results, the data is temporarily stored in a unique Microsoft Azure storage location in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage location two weeks after it's created.</span></span> 
    
- <span data-ttu-id="d5826-p108">如果貴組織使用 proxy 伺服器與網際網路通訊，您需要在您使用匯出搜尋結果 （因此匯出工具可以驗證的 proxy 伺服器） 的電腦上定義之 proxy 伺服器設定。若要這樣做，開啟*machine.config*檔案中找出您的 Windows 版本的位置。</span><span class="sxs-lookup"><span data-stu-id="d5826-p108">If your organization uses a proxy server to communicate with the Internet, you need to define the proxy server settings on the computer that you use to export the search results (so the export tool can be authenticated by your proxy server). To do this, open the  *machine.config*  file in the location that matches your version of Windows.</span></span> 
    
  - <span data-ttu-id="d5826-136">**32 位元** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="d5826-136">**32-bit** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span></span>
    
  - <span data-ttu-id="d5826-137">**64 位元** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="d5826-137">**64-bit** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span></span>
    
    <span data-ttu-id="d5826-p109">之間某*machine.config*檔案中新增下列幾行`<configuration>`和`</configuration>`標記。請務必取代`ProxyServer`和`Port`與您的組織 ； 正確的值例如， `proxy01.contoso.com:80` 。</span><span class="sxs-lookup"><span data-stu-id="d5826-p109">Add the following lines to the  *machine.config*  file somewhere between the  `<configuration>` and  `</configuration>` tags. Be sure to replace  `ProxyServer` and  `Port` with the correct values for your organization; for example,  `proxy01.contoso.com:80` .</span></span> 
    
    ```
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="http://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- <span data-ttu-id="d5826-140">請參閱] 區段中的限制匯出搜尋結果的說明。</span><span class="sxs-lookup"><span data-stu-id="d5826-140">See the  section for a description of the limits for exporting search results.</span></span> 
    
- <span data-ttu-id="d5826-p110">要匯出的 PST 檔案大小上限為 10 GB。如果您想要變更此預設大小，您可以編輯您用來匯出搜尋結果的電腦上的 Windows 登錄。請參閱 ＜ [Change 匯出 eDiscovery 搜尋結果時 PST 檔案的大小](change-the-size-of-pst-files-when-exporting-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p110">The maximum size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
## <a name="step-1-prepare-search-results-for-export"></a><span data-ttu-id="d5826-144">步驟 1： 準備搜尋結果的匯出</span><span class="sxs-lookup"><span data-stu-id="d5826-144">Step 1: Prepare search results for export</span></span>

<span data-ttu-id="d5826-p111">第一個步驟是準備匯出搜尋結果。當您準備結果時，其上傳至 Microsoft 雲端 Azure 的儲存位置。請注意，從信箱和網站的內容上傳在 2 GB 的每小時最大速率。</span><span class="sxs-lookup"><span data-stu-id="d5826-p111">The first step is to prepare the search results for exporting. When you prepare results, they are uploaded to an Azure storage location in the Microsoft cloud. Note that content from mailboxes and sites is uploaded at a maximum rate of 2 GB per hour.</span></span>
  
1. <span data-ttu-id="d5826-148">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="d5826-148">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="d5826-149">登入 Office 365 中，使用您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d5826-149">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="d5826-150">在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]\*\*\*\* \> [內容搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5826-150">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="d5826-151">在 [**內容搜尋**] 頁面上選取 [搜尋。</span><span class="sxs-lookup"><span data-stu-id="d5826-151">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="d5826-152">在詳細資料] 窗格中，[**匯出至電腦的結果**，請按一下 [**開始匯出**。</span><span class="sxs-lookup"><span data-stu-id="d5826-152">In the details pane, under **Export results to a computer**, click **Start export**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5826-p112">如果超過 7 天的搜尋結果，系統會提示您更新的搜尋結果。如果發生這種情況，取消匯出、 所選的搜尋] 的詳細資料] 窗格中按一下 [**更新搜尋結果**並更新結果之後再啟動匯出。</span><span class="sxs-lookup"><span data-stu-id="d5826-p112">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="d5826-155">在**匯出搜尋結果**頁面] 下方**包含這些項目] 搜尋中的**，選擇下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="d5826-155">On the **Export the search results** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="d5826-156">僅匯出已編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="d5826-156">Export only indexed items</span></span>
    
    - <span data-ttu-id="d5826-157">已編製索引和部分已編製索引的項目匯出</span><span class="sxs-lookup"><span data-stu-id="d5826-157">Export indexed and partially indexed items</span></span>
    
    - <span data-ttu-id="d5826-158">只有部分已編製索引的項目匯出</span><span class="sxs-lookup"><span data-stu-id="d5826-158">Export only partially indexed items</span></span>
    
    <span data-ttu-id="d5826-p113">如需說明如何部分已編製索引的項目相關[的詳細資訊](#more-information)] 區段，請參閱都要匯出。如需詳細部分已編製索引的項目，請參閱[部分編製索引內容的搜尋中的項目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p113">See the [More information](#more-information) section for a description about how partially indexed items are exported. For more information about partially indexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="d5826-161">在 [**匯出 Exchange 內容**，選擇下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="d5826-161">Under **Export Exchange content as**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="d5826-p114">**每個信箱的一個 PST 檔案**-匯出搜尋結果會包含每個使用者信箱的一個 PST 檔案。從使用者的封存信箱的任何結果包含在相同的 PST 檔案中。請注意此選項會重現來源信箱的信箱資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="d5826-p114">**One PST file for each mailbox** - Exports one PST file for each user mailbox that contains search results. Any results from the user's archive mailbox are included in the same PST file. Note that this option reproduces the mailbox folder structure from the source mailbox.</span></span> 
    
    - <span data-ttu-id="d5826-p115">**包含所有郵件的一部 PST 檔案**-匯出單一 PST 檔案 （名為*Exchange.pst* ） 包含在搜尋中包含的所有來源信箱的搜尋結果。請注意此選項會重現每封郵件的信箱資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="d5826-p115">**One PST file containing all messages** - Exports a single PST file (named  *Exchange.pst*  ) that contains the search results from all source mailboxes included in the search. Note that this option reproduces the mailbox folder structure for each message.</span></span> 
    
    - <span data-ttu-id="d5826-p116">**一個 PST 檔案包含單一資料夾中的所有郵件**-匯出所有郵件，其中單一 PST 檔案的搜尋結果都位於單一的最上層資料夾。此選項可讓檢閱者不必瀏覽每個項目的原始的信箱資料夾結構檢閱 （項目排序所傳送的日期） 的時間先後順序中的項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-p116">**One PST file containing all messages in a single folder** - Exports search results to a single PST file where all messages are located in a single, top-level folder. This option lets reviewers review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span> 
    
    - <span data-ttu-id="d5826-p117">**個別郵件**-匯出搜尋結果以個別的電子郵件訊息方式使用.msg 格式。如果您選取此選項時，電子郵件搜尋結果匯出至資料夾檔案系統中。用於個別郵件的資料夾路徑是如果您匯出至 PST 檔案的結果會使用一個相同。</span><span class="sxs-lookup"><span data-stu-id="d5826-p117">**Individual messages** - Exports search results as individual email messages, using the .msg format. If you select this option, email search results are exported to a folder in the file system. The folder path for individual messages is the same as the one used if you exported the results to PST files.</span></span> 
    
      > [!IMPORTANT]
      > <span data-ttu-id="d5826-p118">若要解密 RMS 加密郵件時所要匯出，您必須將電子郵件搜尋結果匯出成個別的郵件。如果您將搜尋結果匯出成 PST 檔案加密的郵件會保持加密。</span><span class="sxs-lookup"><span data-stu-id="d5826-p118">To decrypt RMS-encrypted messages when they're exported, you must export email search results as individual messages. Encrypted messages will remain encrypted if you export the search results as a PST file.</span></span> 
  
8. <span data-ttu-id="d5826-p119">按一下 [**啟用重複資料刪除**] 核取方塊來排除重複的郵件。只有當內容來源的搜尋包含 Exchange 信箱或公用資料夾會出現此選項。</span><span class="sxs-lookup"><span data-stu-id="d5826-p119">Click the **Enable de-duplication** checkbox to exclude duplicate messages. This option appears only if the content sources of the search includes Exchange mailboxes or public folders.</span></span> 
    
    <span data-ttu-id="d5826-p120">如果您選取這個選項，即使所搜尋的信箱中找到多份相同的訊息將會匯出只有一個複本的訊息。匯出結果報表 (Results.csv) 將會包含每個重複的郵件複本的資料列，讓您可以識別信箱 （或公用資料夾） 且包含重複的郵件的複本。如需詳細資訊需重複資料刪除和如何重複的項目會識別出，請參閱[重複資料刪除 eDiscovery 搜尋結果中](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p120">If you select this option, only one copy of a message will be exported even if multiple copies of the same message are found in the mailboxes that were searched. The export results report (Results.csv) will contain a row for every copy of a duplicate message so that you can identify the mailboxes (or public folders) that contain a copy of the duplicate message. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
    
9. <span data-ttu-id="d5826-p121">按一下 [要匯出的 SharePoint 文件的所有版本的**SharePoint 文件包含版本**核取方塊。只有當內容來源的搜尋包含 SharePoint 或 OneDrive for Business 的網站會出現此選項。</span><span class="sxs-lookup"><span data-stu-id="d5826-p121">Click the **Include versions for SharePoint documents** checkbox to export all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span> 
    
10. <span data-ttu-id="d5826-p122">按一下 [**匯出檔案壓縮 (zip) 的資料夾中**的核取方塊可將搜尋結果匯出到壓縮資料夾。只有當您選擇 Exchange 的項目匯出為個別郵件時及搜尋結果包含 SharePoint 或 OneDrive 文件時使用此選項。此選項主要用於解決 Windows 檔案路徑名稱 260 字元限制時都要匯出的項目。請參閱"檔名的匯出的項目 」 的[詳細資訊](#more-information)] 區段中。</span><span class="sxs-lookup"><span data-stu-id="d5826-p122">Click the **Export files in a compressed (zipped) folder** checkbox to export search results to compressed folders. This option is available only when you choose to export Exchange items as individual messages and when the search results include SharePoint or OneDrive documents. This option is primarily used to work around the 260 character limit in Windows file path names when items are exported. See the "Filenames of exported items" in the [More information](#more-information) section.</span></span> 
    
11. <span data-ttu-id="d5826-185">按一下 [**開始匯出**]。</span><span class="sxs-lookup"><span data-stu-id="d5826-185">Click **Start export**.</span></span>
    
    <span data-ttu-id="d5826-p123">在搜尋結果已備妥下載，這表示他們正在要上傳至 Microsoft 雲端 Azure 儲存位置。備妥可供下載的搜尋結果時，**下載匯出結果**連結詳細資料窗格中會顯示 [**匯出至電腦的結果**。</span><span class="sxs-lookup"><span data-stu-id="d5826-p123">The search results are prepared for downloading, which means they're being uploaded to the Azure storage location in the Microsoft cloud. When the search results are ready for download, the **Download exported results** link is displayed under **Export results to a computer** in the details pane.</span></span> 
  
## <a name="step-2-download-the-search-results"></a><span data-ttu-id="d5826-188">步驟 2： 下載搜尋結果</span><span class="sxs-lookup"><span data-stu-id="d5826-188">Step 2: Download the search results</span></span>

<span data-ttu-id="d5826-189">下一步是從 Azure 儲存位置的搜尋結果下載至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d5826-189">The next step is to download the search results from the Azure storage location to your local computer.</span></span>
  
<span data-ttu-id="d5826-p124">如先前所述，您可以藉由您用來匯出搜尋結果的電腦上設定 Windows 登錄設定增加下載速度。如需詳細資訊，請參閱[增加匯出 eDiscovery 搜尋結果從 Office 365 時的下載速度](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p124">As previously explained, you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="d5826-192">在您啟動 [**匯出至電腦的結果**，匯出搜尋的詳細資料窗格中，按一下 [**下載匯出的結果**。</span><span class="sxs-lookup"><span data-stu-id="d5826-192">In the details pane for the search that you started the export for, under **Export results to a computer**, click **Download exported results**.</span></span>
    
    <span data-ttu-id="d5826-193">**下載 （英文） 匯出結果**] 視窗會顯示並包含下列有關搜尋結果將會下載到您的電腦的資訊。</span><span class="sxs-lookup"><span data-stu-id="d5826-193">The **Download exported results** window is displayed and contains the following information about the search results that will be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="d5826-194">將下載的項目數目。</span><span class="sxs-lookup"><span data-stu-id="d5826-194">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="d5826-195">將下載的項目估計總數。</span><span class="sxs-lookup"><span data-stu-id="d5826-195">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="d5826-p125">將匯出已編製索引或未編製索引的項目。未編製索引的項目是具備可辨識的格式、已進行加密，或因為其他原因而未編製索引的項目。如需詳細資訊，請參閱[Unindexed items in Content Search](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p125">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons. For more information, see [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
    - <span data-ttu-id="d5826-199">是否下載 SharePoint 文件的版本。</span><span class="sxs-lookup"><span data-stu-id="d5826-199">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="d5826-p126">匯出準備程序的狀態。您可以開始下載搜尋結果，即使資料的準備工作尚未完成。</span><span class="sxs-lookup"><span data-stu-id="d5826-p126">The status of the export preparation process. You can start downloading search results even if the preparation of the data isn't complete.</span></span>
    
2. <span data-ttu-id="d5826-p127">**匯出金鑰**，請按一下 [**複製到剪貼簿**。您將在步驟 5 中使用此機碼下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d5826-p127">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the search results.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5826-204">因為任何人都可以安裝並啟動 eDiscovery 匯出工具，然後使用此金鑰來下載搜尋結果，請務必採取預防措施來保護此金鑰，如同您用來保護密碼或其他安全性相關資訊的方式。 </span><span class="sxs-lookup"><span data-stu-id="d5826-204">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search results, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="d5826-205">按一下 [**下載結果**。</span><span class="sxs-lookup"><span data-stu-id="d5826-205">Click **Download results**.</span></span>
    
4. <span data-ttu-id="d5826-206">如果系統提示您安裝**MicrosoftOffice 365 eDiscovery 匯出工具**，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="d5826-206">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="d5826-207">在**eDiscovery 匯出工具**中，貼上您在步驟 2 中適當的方塊中複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="d5826-207">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="d5826-208">按一下 [瀏覽]\*\*\*\* 以指定搜尋結果檔案要下載到的位置。</span><span class="sxs-lookup"><span data-stu-id="d5826-208">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d5826-209">由於磁碟活動 （讀取和寫入） 高數量，您應該下載搜尋結果至本機磁碟機;不要下載至對應的網路磁碟機或其他網路位置。</span><span class="sxs-lookup"><span data-stu-id="d5826-209">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
1. <span data-ttu-id="d5826-210">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="d5826-210">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="d5826-p128">**EDiscovery 匯出工具**會顯示狀態資訊匯出程序，包括評估會有數 （與大小） 的其餘的項目下載。匯出程序完成時，您可以存取已下載的所在位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="d5826-p128">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    

  
## <a name="more-information"></a><span data-ttu-id="d5826-213">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d5826-213">More information</span></span>
<span data-ttu-id="d5826-214"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="d5826-214"></span></span>

<span data-ttu-id="d5826-215">以下是匯出搜尋結果的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d5826-215">Here's more information about exporting search results.</span></span>
  
[<span data-ttu-id="d5826-216">匯出的限制</span><span class="sxs-lookup"><span data-stu-id="d5826-216">Export limits</span></span>](export-search-results.md#export-limits)
  
[<span data-ttu-id="d5826-217">匯出報告</span><span class="sxs-lookup"><span data-stu-id="d5826-217">Export reports</span></span>](export-search-results.md#export-reports)
  
[<span data-ttu-id="d5826-218">匯出部分已編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="d5826-218">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)
  
[<span data-ttu-id="d5826-219">匯出個別郵件或 PST 檔</span><span class="sxs-lookup"><span data-stu-id="d5826-219">Exporting individual messages or PST files</span></span>](export-search-results.md#Exporting-individual-messages-or-PST-files)
  
[<span data-ttu-id="d5826-220">解密受 RMS 加密的郵件</span><span class="sxs-lookup"><span data-stu-id="d5826-220">Decrypting RMS-encrypted messages</span></span>](export-search-results.md#Decrypting-RMS-encrypted-messages)
  
[<span data-ttu-id="d5826-221">檔名的匯出的項目</span><span class="sxs-lookup"><span data-stu-id="d5826-221">Filenames of exported items</span></span>](export-search-results.md#Filenames-of-exported-items)
  
[<span data-ttu-id="d5826-222">其他</span><span class="sxs-lookup"><span data-stu-id="d5826-222">Miscellaneous</span></span>](export-search-results.md#miscellaneous)
  
 ### <a name="export-limits"></a><span data-ttu-id="d5826-223">匯出的限制</span><span class="sxs-lookup"><span data-stu-id="d5826-223">Export limits</span></span>
  
- <span data-ttu-id="d5826-224">匯出搜尋結果的安全性&amp;規範中心 」 有下列限制：</span><span class="sxs-lookup"><span data-stu-id="d5826-224">Exporting search results from the Security &amp; Compliance Center has the following limits:</span></span>
    
  - <span data-ttu-id="d5826-p129">您可以從單一內容搜尋匯出最大值為 2 TB 的資料。如果大於 2 TB 的搜尋結果，請考慮使用日期範圍或其他類型的篩選器縮小搜尋結果的總大小。</span><span class="sxs-lookup"><span data-stu-id="d5826-p129">You can export a maximum of 2 TB of data from a single Content Search. If the search results are larger than 2 TB, consider using date ranges or other types of filters to decrease the total size of the search results.</span></span>
    
  - <span data-ttu-id="d5826-227">您的組織可以將最大值為 2 TB 的資料匯出期間單一整天。</span><span class="sxs-lookup"><span data-stu-id="d5826-227">Your organization can export a maximum of 2 TB of data during a single day.</span></span>
    
  - <span data-ttu-id="d5826-228">您最多可以在組織內同時執行 10 個匯出。</span><span class="sxs-lookup"><span data-stu-id="d5826-228">You can have a maximum of 10 exports running at the same time within your organization.</span></span>
    
  - <span data-ttu-id="d5826-229">單一使用者可以同時執行三個匯出的最大的值。</span><span class="sxs-lookup"><span data-stu-id="d5826-229">A single user can run a maximum of three exports at the same time.</span></span>
    
  - <span data-ttu-id="d5826-230">匯出內容的搜尋報告不會計算針對任何匯出限制。</span><span class="sxs-lookup"><span data-stu-id="d5826-230">Exporting Content Search reports doesn't count against any of the export limits.</span></span> 
    
- <span data-ttu-id="d5826-231">如先前所述，從信箱和網站的搜尋結果上傳至 Azure 儲存位置 (中所述[步驟 1： 準備搜尋結果的匯出](export-search-results.md#step1)) 在 2 GB 的每小時最大速率。</span><span class="sxs-lookup"><span data-stu-id="d5826-231">As previously stated, search results from mailboxes and sites are uploaded to the Azure storage location (as described in [Step 1: Prepare search results for export](export-search-results.md#step1)) at a maximum rate of 2 GB per hour.</span></span>
    
- <span data-ttu-id="d5826-p130">預設可匯出的 PST 檔案大小上限為 10 GB。這表示如果搜尋結果從使用者的信箱超過 10 GB，將兩個 （或多個） 不同的 PST 檔案中匯出信箱的搜尋結果。此外，如果您選擇要匯出單一的 PST 檔案中的所有搜尋結果，PST 檔案將會是濺至其他 PST 檔案，如搜尋結果的總大小大於 10 GB。如果您想要變更此預設大小，您可以編輯您用來匯出搜尋結果的電腦上的 Windows 登錄。請參閱 ＜ [Change 匯出 eDiscovery 搜尋結果時 PST 檔案的大小](change-the-size-of-pst-files-when-exporting-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p130">The maximum size of a PST file that can be exported is 10 GB by default. That means if the search results from a user's mailbox are larger than 10 GB, the search results for the mailbox will be exported in two (or more) separate PST files. Additionally, if you choose to export all search results in a single PST file, the PST file will be spilt into additional PST files if the total size of the search results is larger than 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
    <span data-ttu-id="d5826-p131">此外，特定信箱的搜尋結果將不會被這些分散多個 PST 檔案從單一信箱的內容設定為超過 10 GB。如果您選擇要匯出搜尋結果在一個 PST 檔案所包含單一資料夾中的所有郵件及搜尋結果超過 10 GB、 項目來仍組織先後順序，讓他們將濺至其他傳送 d 為基礎的 PST 檔案著。</span><span class="sxs-lookup"><span data-stu-id="d5826-p131">Additionally, the search results from a specific mailbox won't be divided among multiple PST files unless the content from a single mailbox is more than 10 GB. If you chose to export the search results in one PST file for that contains all messages in a single folder and the search results are larger than 10 GB, the items are still organized in chronological order, so they will be spilt into additional PST files based on the sent date.</span></span>
     
 ### <a name="export-reports"></a><span data-ttu-id="d5826-239">匯出報告</span><span class="sxs-lookup"><span data-stu-id="d5826-239">Export reports</span></span>
  
- <span data-ttu-id="d5826-240">當您將搜尋結果匯出下列報告是除了在搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d5826-240">When you export search results, the following reports are included in addition to the search results.</span></span>
    
  - <span data-ttu-id="d5826-p132">**匯出摘要**Excel 文件包含匯出的摘要。這包括資訊例如所搜尋的內容來源數目、 從搜尋結果中與估計及下載項目數已匯出的估計和下載大小。</span><span class="sxs-lookup"><span data-stu-id="d5826-p132">**Export Summary** An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the estimated and downloaded sizes of the search results, and the estimated and downloaded number of items that were exported.</span></span> 
    
  - <span data-ttu-id="d5826-243">**資訊清單**資訊清單檔案 （以 XML 格式），其中包含搜尋結果中包含每個項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d5826-243">**Manifest** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
  - <span data-ttu-id="d5826-p133">**結果**Excel 文件包含每個項目下載 （英文） 做為自訂的搜尋結果的相關資訊。為電子郵件、 結果記錄檔包含每個郵件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="d5826-p133">**Results** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
      - <span data-ttu-id="d5826-246">來源信箱中訊息的位置 (包括訊息位於主要或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="d5826-246">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
        
      - <span data-ttu-id="d5826-247">送出或收到郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="d5826-247">The date the message was sent or received.</span></span>
        
      - <span data-ttu-id="d5826-248">郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="d5826-248">The Subject line from the message.</span></span>
        
      - <span data-ttu-id="d5826-249">郵件的寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="d5826-249">The sender and recipients of the message.</span></span>
        
      - <span data-ttu-id="d5826-p134">郵件是否重複的郵件如果匯出搜尋結果時啟用 [重複] 選項。重複的郵件識別為重複的郵件的**重複項目**資料行中有一個值。**重複的項目**] 欄中的值包含已匯出的郵件項目識別碼。如需詳細資訊，請參閱 ＜ [eDiscovery 搜尋結果中的重複資料刪除](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p134">Whether the message is a duplicate message if you enabled the de-duplication option when exporting the search results. Duplicate messages will have a value in the **Duplicate to Item** column that identifies the message as a duplicate. The value in the **Duplicate to Item** column contains the item identity of the message that was exported. For more information, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
        
      <span data-ttu-id="d5826-254">文件從 SharePoint 和 OneDrive for Business 網站的結果記錄檔包含每個文件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="d5826-254">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
        
      - <span data-ttu-id="d5826-255">文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="d5826-255">The URL for the document.</span></span>
        
      - <span data-ttu-id="d5826-256">文件庫所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="d5826-256">The URL for the site collection where the document is located.</span></span>
        
      - <span data-ttu-id="d5826-257">上次修改文件的日期。</span><span class="sxs-lookup"><span data-stu-id="d5826-257">The date that the document was last modified.</span></span>
        
      - <span data-ttu-id="d5826-258">(位於結果記錄檔中的 [主旨] 欄) 的文件名稱。</span><span class="sxs-lookup"><span data-stu-id="d5826-258">The name of the document (which is located in the Subject column in the result log).</span></span>
    
  - <span data-ttu-id="d5826-p135">**編製索引的項目**Excel 文件包含將搜尋結果中包含任何部分已編製索引項目的相關資訊。如果您未包含部分已編製索引的項目時產生搜尋結果報表，這份報告仍會下載，但會是空的。</span><span class="sxs-lookup"><span data-stu-id="d5826-p135">**Unindexed Items** An Excel document that contains information about any partially indexed items that would be included in the search results. If you don't include partially indexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span> 
    
  - <span data-ttu-id="d5826-p136">**錯誤與警告**包含錯誤和警告發生在匯出期間的檔案。請參閱錯誤詳細資料欄中的每個個別的錯誤或警告的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="d5826-p136">**Errors and Warnings** Contains errors and warnings for files encountered during export. See the Error Details column for information specific to each individual error or warning.</span></span> 
    
  - <span data-ttu-id="d5826-p137">**已略過的項目**當您匯出搜尋結果從 SharePoint 和 OneDrive for Business 的網站時，匯出通常會包含略過的項目報告 (SkippedItems.csv)。在此報告中所引用的項目通常不會下載，例如資料夾或文件的項目設定。無法匯出此項目類型是根據設計。對於其他項目，已略過 '錯誤類型' 與 ' 錯誤詳細資料 」 欄位中略過的項目] 報告顯示原因項目已略過且） 與其他搜尋結果的下載 （英文）。</span><span class="sxs-lookup"><span data-stu-id="d5826-p137">**Skipped Items** When you export search results from SharePoint and OneDrive for Business sites, the export will usually include a skipped items report (SkippedItems.csv). The items cited in this report are typically items that won't be downloaded, such as a folder or a document set. Not exporting this types of items is by design. For other items that were skipped, the 'Error Type' and 'Error Details' field in the skipped items report show the reason the item was skipped and wasn't download with the other search results.</span></span> 
    
  - <span data-ttu-id="d5826-267">**追蹤記錄檔**包含匯出程序的詳細的記錄資訊並可協助您在匯出期間發現的問題。</span><span class="sxs-lookup"><span data-stu-id="d5826-267">**Trace Log** Contains detailed logging information about the export process and can help uncover issues during export.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d5826-p138">您只可以匯出這些文件而不需要以實際的搜尋結果匯出。請參閱[匯出內容搜尋報告](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p138">You can just export these documents without having to export the actual search results. See [Export a Content Search report](export-a-content-search-report.md).</span></span> 
  
 ### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="d5826-270">匯出部分已編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="d5826-270">Exporting partially indexed items</span></span>
  
- <span data-ttu-id="d5826-p139">如果您要匯出的信箱項目從搜尋結果中傳回所有的信箱項目內容搜尋 (因為沒有關鍵字其中包含在搜尋查詢)，部分已編製索引的項目將不會複製至 PST 檔案包含編製索引的項目。這是因為規則的搜尋結果中自動包含所有項目，包括任何部分已編製索引的項目。這表示部分已編製索引的項目會包含 PST 檔案 （或以個別的訊息） 中包含的其他、 已編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-p139">If you're exporting mailbox items from a content search that returns all mailbox items in the search results (because no keywords where included in the search query), partially indexed items won't be copied to the PST file that contains the unindexed items. This is because all items, including any partially indexed items, are automatically included in the regular search results. This means that partially indexed items will be included in a PST file (or as individual messages) that contains the other, indexed items.</span></span>
    
    <span data-ttu-id="d5826-p140">此外，如果您匯出已編製索引和部分已編製索引項目或只有已編製索引的項目匯出內容的搜尋所傳回的所有項目，將會下載相同的項目數。發生即使預估的搜尋結果的內容搜尋 (顯示在搜尋中的統計資料安全性&amp;規範中心) 仍將會包含不同的評估的部分已編製索引的項目數。例如，假設包含所有的項目 （不在搜尋查詢關鍵字） 搜尋評估顯示發現 1000 個項目和發現也到 200 部分已編製索引的項目。在此例中 1000 個項目包含部分已編製索引的項目因為搜尋會傳回所有項目。換句話說，有 1000 項目總數 （如您預期） 傳回搜尋，並不 1200 項目。如果您匯出此搜尋結果，並選擇匯出編製索引並部分編製索引的項目 （或只是已編製索引的項目），然後將會下載 1000 個項目。同樣地，這是因為部分已編製索引的項目所含的規則 （已編製索引） 結果當您使用空白的搜尋查詢傳回的所有項目。在同一個範例中，如果您選擇只有部分已編製索引的項目匯出再僅 200 編製索引項目會下載。</span><span class="sxs-lookup"><span data-stu-id="d5826-p140">Additionally, if you export both the indexed and partially indexed items or if you export only the indexed items from a content search that returns all items, the same number of items will be downloaded. This happens even though the estimated search results for the content search (displayed in the search statistics in the Security &amp; Compliance Center) will still include a separate estimate for the number of partially indexed items. For example, let's say that the estimate for a search that includes all items (no keywords in the search query) shows that 1,000 items were found and that 200 partially indexed items were also found. In this case, the 1,000 items include the partially indexed items because the search returns all items. In other words, there are 1,000 total items returned by the search, and not 1,200 items (as you might expect). If you export the results of this search and choose to export indexed and partially indexed items (or just indexed items), then 1,000 items will be downloaded. Again, that's because partially indexed items are included with the regular (indexed) results when you use a blank search query to return all items. In this same example, if you choose to export only partially indexed items, then only the 200 unindexed items would be downloaded.</span></span>
    
    <span data-ttu-id="d5826-282">也請注意在上述範例中 （當已編製索引和部分已編製索引的項目匯出或匯出唯一索引的項目），匯出的搜尋結果所含之**匯出摘要**報告嗎清單 1000 個項目估計項目及下載 1000如先前所述的相同原因的項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-282">Also note that in the previous example (when you export indexed and partially indexed items or you export only indexed items) , the **Export Summary** report included with the exported search results would list 1,000 items estimated items and 1,000 downloaded items for the same reasons as previously described.</span></span> 
    
- <span data-ttu-id="d5826-p141">如果您要匯出結果的搜尋特定的內容位置或組織中的所有內容位置的搜尋，將會匯出只有部分項目從含有符合搜尋準則的項目的內容位置。換句話說，如果沒有搜尋結果中的信箱或站台，然後任何部分編製索引的信箱中的項目或將不會匯出的網站。此原因是匯出部分已編製索引的項目從許多組織中的位置可能會增加匯出錯誤的機率並增加匯出及下載的搜尋結果所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="d5826-p141">If the search that you're exporting results from was a search of specific content locations or all content locations in your organization, only the partially items from content locations that contain items that match the search criteria will be exported. In other words, if no search results are found in a mailbox or site, then any partially indexed items in that mailbox or site won't be exported. The reason for this is that exporting partially indexed items from lots of locations in the organization might increase the likelihood of export errors and increase the time it takes to export and download the search results.</span></span>
    
    <span data-ttu-id="d5826-286">若要從搜尋的所有內容的位置匯出部分已編製索引的項目，設定搜尋以傳回所有項目 （搜尋查詢中移除任何關鍵字），然後將匯出只有部分已編製索引的項目匯出搜尋結果時。</span><span class="sxs-lookup"><span data-stu-id="d5826-286">To export partially indexed items from all content locations for a search, configure the search to return all items (by removing any keywords from the search query) and then export only partially indexed items when you export the search results.</span></span>
    
    ![編製索引的項目匯出使用 thrid 匯出選項](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- <span data-ttu-id="d5826-p142">當匯出搜尋結果從 SharePoint 或 OneDrive for Business 的網站能夠編製索引的項目匯出也取決於您選取 [匯出] 選項及網站的搜尋是否包含符合搜尋準則的已編製索引項目。例如，如果您搜尋特定的 SharePoint 或 OneDrive 商務網站並無搜尋結果，然後未編製索引的項目從這些網站將會匯出如果您選擇 [已編製索引及編製索引的項目匯出的第二個 [匯出] 選項。如果從站台已編製索引項目沒有符合搜尋準則，然後從該網站的所有編製索引項目將會匯出匯出已編製索引及編製索引項目時。下圖說明根據網站包含符合搜尋準則的已編製索引項目匯出選項。</span><span class="sxs-lookup"><span data-stu-id="d5826-p142">When exporting search results from SharePoint or OneDrive for Business sites, the ability to export unindexed items also depends on the export option that you select and whether a site that was searched contains an indexed item that matches the search criteria. For example, if you search specific SharePoint or OneDrive for Business sites and no search results are found, then no unindexed items from those sites will be exported if you choose the second export option to export both indexed and unindexed items. If an indexed item from a site does match the search criteria, then all unindexed items from that site will be exported when exporting both indexed and unindexed items. The following illustration describes the export options based on whether or not a site contains an indexed item that matches the search criteria.</span></span>
    
    ![選擇 [匯出] 選項為基礎的網站包含符合搜尋準則的已編製索引項目](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    <span data-ttu-id="d5826-p143">A-僅限已編製索引的項目符合搜尋準則會匯出。不匯出的任何部分已編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-p143">A - Only indexed items that matches the search criteria are exported. No partially indexed items are exported.</span></span>
    
    <span data-ttu-id="d5826-p144">B-如果沒有已編製索引的項目從網站符合搜尋準則，部分已編製索引的項目從該相同的網站不匯出。如果搜尋結果中傳回已編製索引的項目從網站，都要匯出的部分已編製索引的項目從該網站。換句話說，都要匯出只有部分已編製索引項目從網站包含符合搜尋準則的項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-p144">B - If no indexed items from a site match the search criteria, then partially indexed items from that same site aren't exported. If indexed items from a site are returned in the search results, then the partially indexed items from that site are exported. In other words, only the partially indexed items from sites that contain items that match the search criteria are exported.</span></span>
    
    <span data-ttu-id="d5826-298">C-匯出搜尋中的所有網站的所有部分已編製索引項目，不論網站是否包含符合搜尋準則的項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-298">C - All partially indexed items from all sites in the search are exported, regardless of whether a site contains items that match the search criteria.</span></span>
    
    <span data-ttu-id="d5826-299">如果您選擇要匯出部分已編製索引的項目，部分已編製索引的信箱項目會匯出在個別的 PST 檔案無論您選擇 [**匯出 Exchange 內容**下的選項。</span><span class="sxs-lookup"><span data-stu-id="d5826-299">If you choose to export partially indexed items, partially indexed mailbox items are exported in a separate PST file regardless of the option that you choose under **Export Exchange content as**.</span></span>

- <span data-ttu-id="d5826-p145">如果部分已編製索引的項目會傳回在搜尋結果 （因為其他屬性的部分已編製索引的項目符合搜尋準則），則這些部分已編製索引會匯出與一般的搜尋結果。因此，如果您選擇 [匯出已編製索引的項目和部分已編製索引的項目 （選取**所有項目，包括類有無法辨認的格式來加密或未編製索引的其他原因**的 [匯出] 選項），部分已編製索引的項目匯出與一般結果將會列在 Results.csv 報表。他們將不會列在花很多的 items.csv 報表中。</span><span class="sxs-lookup"><span data-stu-id="d5826-p145">If partially indexed items are returned in the search results (because other properties of an partially indexed items matched the search criteria), then those partially indexed are exported with the regular search results. So, if you choose to export both indexed items and partially indexed items (by selecting the **All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons** export option), the partially indexed items exported with the regular results will be listed in the Results.csv report. They will not be listed in the Unindexed items.csv report.</span></span>
    
 ### <a name="exporting-individual-messages-or-pst-files"></a><span data-ttu-id="d5826-303">匯出個別郵件或 PST 檔</span><span class="sxs-lookup"><span data-stu-id="d5826-303">Exporting individual messages or PST files</span></span>
  
- <span data-ttu-id="d5826-p146">如果郵件的檔案路徑名稱超過最大字元限制 windows、 會截斷檔案路徑名稱。但原始的檔案路徑名稱將會列在資訊清單和 ResultsLog。</span><span class="sxs-lookup"><span data-stu-id="d5826-p146">If the file path name of a message exceeds the maximum character limit for Windows, the file path name is truncated. But the original file path name will be listed in the Manifest and ResultsLog.</span></span>
    
- <span data-ttu-id="d5826-p147">如先前所述的電子郵件的搜尋結果匯出至資料夾檔案系統中。用於個別郵件的資料夾路徑會複寫使用者的信箱中的資料夾路徑。例如，針對名為"ContosoCase101"的搜尋使用者的收件匣中的郵件會位於資料夾路徑`~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`。</span><span class="sxs-lookup"><span data-stu-id="d5826-p147">As previously explained, email search results are exported to a folder in the file system. The folder path for individual messages would replicate the folder path in the user's mailbox. For example, for a search named "ContosoCase101" messages in a user's inbox would be located in the folder path  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`.</span></span> 
    
- <span data-ttu-id="d5826-p148">如果您選擇要匯出一個包含單一資料夾中的所有郵件的 PST 檔案中的電子郵件、**刪除項目**] 資料夾及**搜尋資料夾**] 資料夾包含在 PST 資料夾的最上層網站。這些資料夾會是空的。</span><span class="sxs-lookup"><span data-stu-id="d5826-p148">If you choose to export email messages in one PST file containing all messages in a single folder, a **Deleted Items** folder and a **Search Folders** folder are included in the top level of the PST folder. These folders will be empty.</span></span> 
  
 ### <a name="decrypting-rms-encrypted-messages"></a><span data-ttu-id="d5826-311">解密受 RMS 加密的郵件</span><span class="sxs-lookup"><span data-stu-id="d5826-311">Decrypting RMS-encrypted messages</span></span>
  
- <span data-ttu-id="d5826-p149">如先前所述解密 RMS 加密郵件時您匯出，您必須將搜尋結果匯出成個別的郵件。如果您將搜尋結果匯出至 PST 檔案時，會維持加密 RMS 加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="d5826-p149">As previously explained, to decrypt RMS-encrypted messages when you export them, you have to export the search results as individual messages. If you export search results to a PST file, RMS-encrypted messages will remain encrypted.</span></span>
    
- <span data-ttu-id="d5826-p150">內容搜尋的 RMS 解密功能不會解密加密與 Office 365 郵件加密 (OME) 匯出搜尋結果時的郵件。不過，使用 OME 加密郵件傳送使用者在組織中，如果使用者的 [寄件備份] 資料夾中的郵件複本未加密和會讓使用者可以檢視已匯出之後。不過，如果使用 OME 加密的郵件會接收您組織中的使用者，他們將不會解密的郵件他們正在匯出之後。如需 OME 的詳細資訊，請參閱[Office 365 郵件加密](https://go.microsoft.com/fwlink/p/?linkid=844966)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p150">The RMS decryption feature in Content Search doesn't decrypt messages encrypted with Office 365 Message Encryption (OME) when you export search results. However, if a message encrypted with OME is sent by a user in your organization, the copy of the message in the user's Sent folder isn't encrypted and will be viewable after it's exported. However, if messages encrypted with OME are received by users in your organization, they won't be decrypted after they're exported. For more information about OME, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966).</span></span>
    
- <span data-ttu-id="d5826-p151">已解密的郵件會被識別**ResultsLog**報告。這份報告包含名為**解碼狀態**] 欄及**Decoded**此欄中的值會識別郵件已解密。</span><span class="sxs-lookup"><span data-stu-id="d5826-p151">Messages that are decrypted are identified in the **ResultsLog** report. This report contains a column named **Decode Status**, and a value of **Decoded** in this column identifies the messages the were decrypted.</span></span> 
    
- <span data-ttu-id="d5826-p152">目前此解密功能不包括商務網站的 SharePoint 和 OneDrive 加密的內容。當您將其匯出將解密僅 RMS 加密電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d5826-p152">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="d5826-322">如果 RMS 加密電子郵件訊息的附件 （例如文件或另一個電子郵件訊息） 也加密，只有最上層的電子郵件將解密的郵件。</span><span class="sxs-lookup"><span data-stu-id="d5826-322">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="d5826-p153">您無法預覽 RMS 加密電子郵件訊息。若要檢視加密的郵件，您必須將它匯出。</span><span class="sxs-lookup"><span data-stu-id="d5826-p153">You can't preview an RMS-encrypted email message. To view an encrypted message, you have to export it.</span></span>
    
- <span data-ttu-id="d5826-p154">如果您需要避免有人解密 RMS 加密的郵件，您必須複製以建立自訂角色群組 （內建的 eDiscovery 管理員角色群組），然後從自訂角色群組中移除 [RMS 解密管理角色。然後將新增您不想將郵件解密自訂角色群組的成員身分的人員。</span><span class="sxs-lookup"><span data-stu-id="d5826-p154">If you need to prevent someone from decrypting RMS-encrypted messages, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
  
 ### <a name="filenames-of-exported-items"></a><span data-ttu-id="d5826-327">檔名的匯出的項目</span><span class="sxs-lookup"><span data-stu-id="d5826-327">Filenames of exported items</span></span>
  
- <span data-ttu-id="d5826-p155">電子郵件與網站文件匯出至您的本機電腦的完整路徑名稱只有 （作業系統所加諸） 260 個字元限制。匯出的項目的完整路徑名稱包含的項目原始位置和搜尋結果會下載到本機電腦上的資料夾位置。例如，如果您指定下載將搜尋結果`C:\Users\Admin\Desktop\SearchResults`在 eDiscovery 匯出工具] 然後下載電子郵件項目的的完整路徑名稱就是`C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`。</span><span class="sxs-lookup"><span data-stu-id="d5826-p155">There is a 260-character limit (imposed by the operating system) for the full path name for email messages and site documents exported to your local computer. The full path name for exported items includes the item's original location and the folder location on the local computer where the search results are downloaded to. For example, if you specify to download the search results to  `C:\Users\Admin\Desktop\SearchResults` in the eDiscovery Export tool, then the full pathname for a downloaded email item would be  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`.</span></span>
    
    <span data-ttu-id="d5826-331">若超過 260 個字元限制，就會截斷的完整路徑名稱為項目。</span><span class="sxs-lookup"><span data-stu-id="d5826-331">If the 260-character limit is exceeded, the full path name for an item will be truncated.</span></span>
    
  - <span data-ttu-id="d5826-332">如果的完整路徑名稱的長度超過 260 個字元，將會取得限制 ； 縮短檔案名稱請注意截斷檔案名稱 （不含副檔名） 不會為小於 8 個字元。</span><span class="sxs-lookup"><span data-stu-id="d5826-332">If the full path name is longer than 260 characters, the file name will be shortened to get under the limit; note that the truncated filename (excluding the file extension) won't be less than 8 characters.</span></span>
    
  - <span data-ttu-id="d5826-p156">如果仍然之後縮短檔案名稱過長的完整路徑名稱、 項目是從其目前的位置移至上層資料夾。如果 pathname 仍是太長，然後重複程序： 縮短檔案名稱，如果需要重新移至父項資料夾。此程序會重複，直到的完整路徑名稱是 260 個字元限制。</span><span class="sxs-lookup"><span data-stu-id="d5826-p156">If the full path name is still too long after shortening the file name, the item is moved from its current location to the parent folder. If the pathname is still too long, then the process is repeated: shorten the filename, and if necessary move again to the parent folder. This process is repeated until the full pathname is under the 260-character limit.</span></span>
    
  - <span data-ttu-id="d5826-336">版本號碼如果截斷的完整路徑名稱已經存在，將會新增至結尾的檔案名稱 ；例如， `statusmessage(2).msg`。</span><span class="sxs-lookup"><span data-stu-id="d5826-336">If a truncated full path name already exists, a version number will be added to the end of the filename; for example,  `statusmessage(2).msg`.</span></span>
    
    <span data-ttu-id="d5826-337">若要協助減輕這個問題，請考慮下載至短的路徑名稱 ； 位置的搜尋結果例如，下載至名為資料夾的 [搜尋結果`C:\Results`會匯出的項目數超過其下載至名為資料夾的路徑名稱新增較少的字元`C:\Users\Admin\Desktop\Results`。</span><span class="sxs-lookup"><span data-stu-id="d5826-337">To help mitigate this issue, consider downloading search results to a location with a short path name; for example, downloading search results to a folder named  `C:\Results` would add fewer characters to the path names of exported items than downloading them to a folder named  `C:\Users\Admin\Desktop\Results`.</span></span>
    
- <span data-ttu-id="d5826-p157">當您匯出網站文件時，也有可能會修改文件的原始檔案名稱。發生這種情況特別針對已從 SharePoint 或 OneDrive 刪除已處於保留狀態的商務網站的文件。刪除位於保留在網站的文件之後，刪除之文件自動移至保留保留文件庫網站 （也就建立站台已處於保留狀態時）。當已刪除的文件移至保留保留文件庫時，隨機產生且唯一的識別碼會附加到原始文件的檔案名稱。例如，如果文件的檔案名稱是`FY2017Budget.xlsx`該文件稍後被刪除並移至的保留保留文件庫中，移至保留保留文件庫的文件的檔案名稱會以類似如下修改`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`。如果保留保留文件庫中的文件會比對內容的搜尋查詢和搜尋結果匯出，匯出的檔案會有已修改的檔案名稱 ；在此範例中是匯出之文件的檔案名稱`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`。</span><span class="sxs-lookup"><span data-stu-id="d5826-p157">When you export site documents, it's also possible that the original file name of a document will be modified. This happens specifically for documents that have been deleted from a SharePoint or OneDrive for Business site that's been placed on hold. After a document that's located on a site that's on hold is deleted, the deleted document is automatically moved to the Preservation Hold library for the site (which was created when the site was placed on hold). When the deleted document is moved to the Preservation Hold library, a randomly-generated and unique ID is appended to the original filename of the document. For example, if the filename for a document is  `FY2017Budget.xlsx` and that document is later deleted and moved to the Preservation Hold library, the filename of the document that is moved to the Preservation Hold library is modified to something like  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`. If a document in the Preservation Hold library matches the query of a Content Search and you export the results of that search, the exported file will have the modified filename; in this example, the filename of the exported document would be  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.</span></span>
    
    <span data-ttu-id="d5826-p158">此外，當修改位於保留網站上的文件 （與已啟用版本控制網站中的文件庫） 檔案的複本保留保留文件庫中自動建立。在此例中隨機產生及唯一識別碼也會附加至文件複製到保留保留文件庫的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="d5826-p158">Additionally, when a document located on a site that's on hold is modified (and versioning for the document library in the site has been enabled), a copy of the file is automatically created in the Preservation Hold library. In this case, a randomly-generated and unique ID is also appended to the filename of the document that's copied to the Preservation Hold library.</span></span>
    
    <span data-ttu-id="d5826-p159">原因 filenames 已移動或複製到保留保留文件庫的文件以防止衝突的檔名。如需將保留放置網站及保留保留文件庫的詳細資訊，請參閱 ＜ [Overview of 就地保留在 SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)。</span><span class="sxs-lookup"><span data-stu-id="d5826-p159">The reason why filenames of documents that are moved or copied to the Preservation Hold library is to prevent conflicting filenames. For more information about placing a hold on sites and the Preservation Hold library, see [Overview of in-place hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).</span></span>
    
 ### <a name="miscellaneous"></a><span data-ttu-id="d5826-348">其他</span><span class="sxs-lookup"><span data-stu-id="d5826-348">Miscellaneous</span></span>
  
- <span data-ttu-id="d5826-p160">所有的搜尋結果並匯出報告都包含在具有相同名稱作為內容的搜尋資料夾。已匯出的電子郵件訊息位於名為**Exchange**的資料夾。文件位於名為**SharePoint**的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d5826-p160">All search results and the export reports are included in a folder that has the same name as the Content Search. The email messages that were exported are located in a folder named **Exchange**. Documents are located in a folder named **SharePoint**.</span></span> 
    
- <span data-ttu-id="d5826-p161">當文件都要匯出至您的本機電腦維護上 SharePoint 和 OneDrive for Business 的網站的文件的檔案系統中繼資料。表示文件摘要資訊、 例如建立和上次修改日期、 都要匯出的文件時不變更。</span><span class="sxs-lookup"><span data-stu-id="d5826-p161">The file system metadata for documents on SharePoint and OneDrive for Business sites is maintained when documents are exported to your local computer. That means document properties, such as created and last modified dates, aren't changed when documents are exported.</span></span>