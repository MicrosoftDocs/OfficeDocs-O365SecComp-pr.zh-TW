---
title: 匯出 eDiscovery 搜尋結果從 Office 365 時所增加的下載速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何設定 Windows 登錄，以增加資料輸送量下載搜尋結果時及搜尋資料從 Office 365 安全性&amp;規範中心與 Office 365 進階 eDiscovery。
ms.openlocfilehash: a05c2b786d1d1de7ff5014d12c708484345f908b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038116"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="385d4-103">匯出 eDiscovery 搜尋結果從 Office 365 時所增加的下載速度</span><span class="sxs-lookup"><span data-stu-id="385d4-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="385d4-p101">當您使用 Office 365 eDiscovery 匯出工具下載 Office 365 安全性內容的搜尋結果&amp;規範中心或下載資料從 Office 365 進階 eDiscovery，此工具會啟動並行匯出數目若要下載到本機電腦的資料的作業。根據預設，並行作業的數目設為您使用下載資料的電腦中的核心數 8 的次數。例如，如果您有雙核心電腦 （這表示一個晶片上的兩個集中處理單位），同時匯出作業的預設數為 16。若要增加的資料傳輸輸送量與提升並下載程序，您可以依您用以下載搜尋結果的電腦上設定 Windows 登錄設定增加並行作業數目。為了提升並下載程序，建議您開始使用設定為 24 並行作業。</span><span class="sxs-lookup"><span data-stu-id="385d4-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="385d4-p102">如果您透過低頻寬網路下載搜尋結果，請增加此設定可能會造成負面影響。或者，您可以增加 （並行作業的數目上限為 512） 高頻寬網路中的多個 24 並行作業的設定。設定此登錄設定之後，您可能必須將它變更為找出最佳的並行環境作業數目。</span><span class="sxs-lookup"><span data-stu-id="385d4-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="385d4-112">建立登錄設定來匯出資料時變更並行作業的數目</span><span class="sxs-lookup"><span data-stu-id="385d4-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="385d4-113">您將使用的安全性下載搜尋結果的電腦上執行下列程序&amp;規範中心或進階的 eDiscovery 的資料。</span><span class="sxs-lookup"><span data-stu-id="385d4-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="385d4-114">如果已開啟，關閉 Office 365 eDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="385d4-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="385d4-115">使用.reg; filename 尾碼將下列文字儲存到視窗登錄檔案例如，ConcurrentOperations.reg。</span><span class="sxs-lookup"><span data-stu-id="385d4-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="385d4-116">為舊清楚，建議您開始使用 24 並行作業，然後變更此設定可分別。</span><span class="sxs-lookup"><span data-stu-id="385d4-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="385d4-117">在 Windows 檔案總管中，按一下 [或按兩下您在上一個步驟中建立.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="385d4-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="385d4-118">在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。</span><span class="sxs-lookup"><span data-stu-id="385d4-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="385d4-119">出現提示時若要繼續，按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="385d4-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="385d4-120">登錄編輯程式中會顯示訊息，設定已順利新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="385d4-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="385d4-121">您可以重複執行步驟 2-5 變更的值`DownloadConcurrency`登錄設定。</span><span class="sxs-lookup"><span data-stu-id="385d4-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="385d4-p103">建立或變更之後`DownloadConcurrency`登錄設定，請務必建立新的匯出工作或重新啟動現有匯出工作的搜尋結果或要下載的資料。請參閱如需詳細資訊[的詳細資訊](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)] 區段。</span><span class="sxs-lookup"><span data-stu-id="385d4-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="385d4-124">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="385d4-124">More information</span></span>

- <span data-ttu-id="385d4-p104">新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。然後`DownloadConcurrency`登錄設定編輯每次您變更並重新執行.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="385d4-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="385d4-p105">Office 365 eDiscovery 匯出工具會使用[Azure AzCopy 公用程式](https://go.microsoft.com/fwlink/?linkid=849949)的安全性下載搜尋資料&amp;規範中心或進階的 eDiscovery。設定`DownloadConcurrency`登錄設定就類似於執行 AzCopy 公用程式時使用 **/NC**參數。所以的登錄設定`"DownloadConcurrency=24"`必須使用的參數值相同的效果`/NC:24`與 AzCopy 公用程式。</span><span class="sxs-lookup"><span data-stu-id="385d4-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="385d4-p106">如果您要停止匯出下載仍在建構中，然後將其重新 （嘗試再次下載搜尋結果）、 Office 365 eDiscovery 匯出工具將嘗試繼續執行相同的下載。如此，如果您啟動的下載 （英文）、 停止，並再變更`DownloadConcurrency`登錄設定，下載可能會失敗如果重新啟動 （依序按一下 [**下載匯出結果**)。這是因為匯出工具會嘗試將繼續先前下載 （英文） 使用因為您已變更的登錄設定不正確的設定。</span><span class="sxs-lookup"><span data-stu-id="385d4-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="385d4-p107">因此，之後變更`DownloadConcurrency`登錄設定，請先重新啟動匯出工作 （依序按一下 [**重新啟動匯出**) 中的 [安全性]&amp;規範中心。然後您可以下載匯出的結果。如需匯出搜尋結果和資料的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="385d4-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="385d4-136">從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="385d4-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="385d4-137">在 Office 365 進階電子文件探索中匯出結果</span><span class="sxs-lookup"><span data-stu-id="385d4-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
