---
title: 匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以變更下載到您的電腦時匯出 eDiscovery 搜尋結果的 PST 檔案的預設大小。
ms.openlocfilehash: c01f05a02fd94941eb2eb7a05b4c84ffecec9b39
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522244"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="6626b-103">匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小</span><span class="sxs-lookup"><span data-stu-id="6626b-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="6626b-p101">當您使用 Office 365 eDiscovery 匯出工具來匯出 eDiscovery 搜尋的電子郵件結果從不同的 Microsoft eDiscovery 工具時，可以匯出的 PST 檔案的預設大小為 10 GB。如果您想要變更此預設大小，您可以編輯您用來匯出搜尋結果的電腦上的 Windows 登錄。若要執行這項作業的其中一個原因是讓 PST 檔案可符合抽取式媒體、 這類 DVD、 光碟片或的 USB 磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="6626b-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="6626b-107">Office 365 eDiscovery 匯出工具來匯出搜尋結果時使用 Office 365 安全性內容搜尋&amp;規範中心、 Exchange Online 中的就地 eDiscovery 和 SharePoint Online 中的 eDiscovery 中心。</span><span class="sxs-lookup"><span data-stu-id="6626b-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="6626b-108">建立匯出 eDiscovery 搜尋結果時變更 PST 檔案大小的登錄設定</span><span class="sxs-lookup"><span data-stu-id="6626b-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="6626b-109">您將使用的 eDiscovery 搜尋結果匯出之電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="6626b-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="6626b-110">如果已開啟，關閉 Office 365 eDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="6626b-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="6626b-111">使用.reg; filename 尾碼將下列文字儲存到視窗登錄檔案例如，PstExportSize.reg。</span><span class="sxs-lookup"><span data-stu-id="6626b-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="6626b-p102">在範例中，與上述`PstSizeLimitInBytes`值設為 1,073,741,824 位元組或約 1 GB。以下是一些其他範例值`PstSizeLimitInBytes`設定。</span><span class="sxs-lookup"><span data-stu-id="6626b-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="6626b-114">**大小以 GB 為 (1tb)**</span><span class="sxs-lookup"><span data-stu-id="6626b-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="6626b-115">**大小 （位元組）**</span><span class="sxs-lookup"><span data-stu-id="6626b-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6626b-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="6626b-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="6626b-117">751619277</span><span class="sxs-lookup"><span data-stu-id="6626b-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="6626b-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="6626b-118">2 GB</span></span>  <br/> |<span data-ttu-id="6626b-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="6626b-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="6626b-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="6626b-120">4 GB</span></span>  <br/> |<span data-ttu-id="6626b-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="6626b-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="6626b-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="6626b-122">8 GB</span></span>  <br/> |<span data-ttu-id="6626b-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="6626b-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="6626b-124">變更`PstSizeLimitInBytes`PST 檔案時您匯出搜尋結果，然後儲存檔案的所需的最大大小的值。</span><span class="sxs-lookup"><span data-stu-id="6626b-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="6626b-125">在 Windows 檔案總管中，按一下 [或按兩下您在先前步驟中建立.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="6626b-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="6626b-126">在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。</span><span class="sxs-lookup"><span data-stu-id="6626b-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="6626b-127">出現提示時若要繼續，按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="6626b-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="6626b-128">登錄編輯程式中會顯示訊息，設定已順利新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="6626b-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="6626b-129">您可以重複執行步驟 3-6，以變更的值`PstSizeLimitInBytes`登錄設定。</span><span class="sxs-lookup"><span data-stu-id="6626b-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="6626b-130">關於匯出 eDiscovery 搜尋結果時變更 PST 檔案的預設大小的常見問題集</span><span class="sxs-lookup"><span data-stu-id="6626b-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="6626b-131">**為什麼要選擇是預設的大小為 10 GB？**</span><span class="sxs-lookup"><span data-stu-id="6626b-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="6626b-132">10 GB 的預設大小根據客戶意見反應;10 GB 會是內容的很好的平衡之間最佳單一 PST 以及檔案損毀的最小機會量。</span><span class="sxs-lookup"><span data-stu-id="6626b-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="6626b-133">**我應該增加或減少 PST 檔案的預設大小吗？**</span><span class="sxs-lookup"><span data-stu-id="6626b-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="6626b-p103">客戶通常會降低大小限制，讓他們可以實際隨附其組織中的其他位置的抽取式媒體上能容納的搜尋結果。我們不建議您在因為 PST 檔案大於 10 GB 可能已損毀問題增加預設大小。</span><span class="sxs-lookup"><span data-stu-id="6626b-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="6626b-136">**若要這樣做上有必須哪些電腦？**</span><span class="sxs-lookup"><span data-stu-id="6626b-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="6626b-137">您需要變更執行 Office 365 eDiscovery 匯出工具任何本機電腦上的登錄設定。</span><span class="sxs-lookup"><span data-stu-id="6626b-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="6626b-138">**變更此設定後，我必須重新啟動電腦吗？**</span><span class="sxs-lookup"><span data-stu-id="6626b-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="6626b-p104">否，您不需要重新啟動電腦。但如果執行 Office 365 eDiscovery 匯出工具，您必須關閉並重新啟動它之後變更此設定。</span><span class="sxs-lookup"><span data-stu-id="6626b-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="6626b-141">**沒有取得編輯現有的登錄機碼或沒有取得建立新的金鑰吗？**</span><span class="sxs-lookup"><span data-stu-id="6626b-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="6626b-p105">新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。然後設定編輯每次您變更並重新執行.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="6626b-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
