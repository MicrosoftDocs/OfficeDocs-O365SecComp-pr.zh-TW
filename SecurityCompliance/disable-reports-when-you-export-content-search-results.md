---
title: 當您將 Office 365 安全性的內容的搜尋結果匯出停用報告&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 編輯 Windows 登錄本機電腦上的 Office 365 安全性匯出內容的搜尋結果時停用報告&amp;Comliance 中心。停用這些報告可加速下載時間及儲存的磁碟空間。
ms.openlocfilehash: 3c09e0563ddd4469f21950dc3a698ce08b0014df
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527279"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="52412-104">當您將 Office 365 安全性的內容的搜尋結果匯出停用報告&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="52412-104">Disable reports when you export Content Search results in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="52412-p102">當您使用 Office 365 eDiscovery 匯出工具匯出其結果的安全性內容搜尋&amp;規範中心工具自動建立並匯出包含匯出內容的其他資訊的兩個報表。這些報告是 Results.csv 檔案和 Manifest.xml 檔 （請參閱本主題中針對這些報告的詳細描述的[常見問題集需停用匯出報告](#frequently-asked-questions-about-disabling-export-reports)」 一節）。因為這些檔案可能會很大，您可加速下載時間並儲存由防止這些檔案所匯出的磁碟空間。您可以變更您用來匯出搜尋結果的電腦上的 Windows 登錄。如果您想要包含於稍後的報告，您可以編輯登錄設定。</span><span class="sxs-lookup"><span data-stu-id="52412-p102">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security &amp; Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content. These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports). Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported. You can do this by changing the Windows Registry on the computer that you use to export the search results. If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="52412-110">建立停用匯出報告的登錄設定</span><span class="sxs-lookup"><span data-stu-id="52412-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="52412-111">您將使用來匯出內容的搜尋結果的電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="52412-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="52412-112">如果已開啟，關閉 Office 365 eDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="52412-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="52412-113">執行下列一或兩個以下步驟，哪些匯出報告視您要停用。</span><span class="sxs-lookup"><span data-stu-id="52412-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="52412-114">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="52412-114">**Results.csv**</span></span>
    
      <span data-ttu-id="52412-115">使用.reg; filename 尾碼將下列文字儲存至 Windows 登錄檔案例如，DisableResultsCsv.reg。</span><span class="sxs-lookup"><span data-stu-id="52412-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="52412-116">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="52412-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="52412-117">使用.reg; filename 尾碼將下列文字儲存至 Windows 登錄檔案例如，DisableManifestXml.reg。</span><span class="sxs-lookup"><span data-stu-id="52412-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="52412-118">在 Windows 檔案總管中，按一下 [或按兩下您在先前步驟中建立.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="52412-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="52412-119">在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。</span><span class="sxs-lookup"><span data-stu-id="52412-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="52412-120">出現提示時若要繼續，按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="52412-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="52412-121">登錄編輯程式中會顯示訊息，設定已順利新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="52412-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="52412-122">編輯若要重新啟用匯出報告的登錄設定</span><span class="sxs-lookup"><span data-stu-id="52412-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="52412-p103">如果您停用 Results.csv 和 Manifest.xml 報告在先前程序中建立.reg 檔案，您可以編輯這些重新啟用報表以便與搜尋結果匯出的檔案。同樣地，您將使用來匯出內容的搜尋結果的電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="52412-p103">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results. Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="52412-125">如果已開啟，關閉 Office 365 eDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="52412-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="52412-126">編輯一或兩個您在前一程序中建立.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="52412-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="52412-127">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="52412-127">**Results.csv**</span></span>
    
        <span data-ttu-id="52412-p104">開啟 [記事本] 中的 DisableResultsCsv.reg 檔案變更值`False`至`True`，然後儲存檔案。例如，編輯檔案之後，它看起來類似：</span><span class="sxs-lookup"><span data-stu-id="52412-p104">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="52412-130">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="52412-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="52412-p105">開啟 [記事本] 中的 DisableManifestXml.reg 檔案變更值`False`至`True`，然後儲存檔案。例如，編輯檔案之後，它看起來類似：</span><span class="sxs-lookup"><span data-stu-id="52412-p105">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="52412-133">在 Windows 檔案總管中，按一下 [或按兩下您在上一個步驟中編輯.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="52412-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="52412-134">在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。</span><span class="sxs-lookup"><span data-stu-id="52412-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="52412-135">出現提示時若要繼續，按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="52412-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="52412-136">登錄編輯程式中會顯示訊息，設定已順利新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="52412-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="52412-137">停用匯出報表相關的常見問題集</span><span class="sxs-lookup"><span data-stu-id="52412-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="52412-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="52412-138"></span></span>

 <span data-ttu-id="52412-139">**Results.csv 和 Manifest.xml 報表有哪些？**</span><span class="sxs-lookup"><span data-stu-id="52412-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="52412-140">Results.csv 和 Manifest.xml 檔案包含已匯出的內容的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="52412-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="52412-p106">包含每個項目下載 （英文） 做為自訂的搜尋結果的相關資訊**Results.csv** Excel 文件。為電子郵件、 結果記錄檔包含每個郵件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="52412-p106">**Results.csv** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="52412-143">來源信箱中訊息的位置 (包括訊息位於主要或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="52412-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="52412-144">送出或收到郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="52412-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="52412-145">郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="52412-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="52412-146">郵件的寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="52412-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="52412-p107">郵件是否重複的郵件如果您啟用重複資料刪除匯出搜尋結果時。重複的郵件會識別將郵件當做重複的**父項目識別碼**] 欄中有一個值。**父項目識別碼**] 欄中的值是已匯出之郵件的 [**項目 DocumentId** ] 欄中的值相同。</span><span class="sxs-lookup"><span data-stu-id="52412-p107">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results. Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate. The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="52412-150">文件從 SharePoint 和 OneDrive for Business 網站的結果記錄檔包含每個文件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="52412-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="52412-151">文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="52412-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="52412-152">文件庫所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="52412-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="52412-153">上次修改文件的日期。</span><span class="sxs-lookup"><span data-stu-id="52412-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="52412-154">(位於結果記錄檔中的 [主旨] 欄) 的文件名稱。</span><span class="sxs-lookup"><span data-stu-id="52412-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="52412-p108">**Manifest.xml**資訊清單檔案 （以 XML 格式），其中包含搜尋結果中包含每個項目的相關資訊。在此報告中的資訊是 Results.csv 報表相同，但它的格式指定所電子探索參照模型 (EDRM)。如需 EDRM 的詳細資訊，請移至[https://www.edrm.net](https://www.edrm.net)。</span><span class="sxs-lookup"><span data-stu-id="52412-p108">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results. The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM). For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="52412-158">**何時應該使用停用匯出這些報告？**</span><span class="sxs-lookup"><span data-stu-id="52412-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="52412-p109">您的特定需求而定。許多組織不需要搜尋結果的其他資訊並不需要這些報告。</span><span class="sxs-lookup"><span data-stu-id="52412-p109">It depends on your specific needs. Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="52412-161">**若要這樣做上有必須哪些電腦？**</span><span class="sxs-lookup"><span data-stu-id="52412-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="52412-162">您必須在執行 Office 365 eDiscovery 匯出工具的任何本機電腦的登錄設定變更。</span><span class="sxs-lookup"><span data-stu-id="52412-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="52412-163">**變更此設定後，我必須重新啟動電腦吗？**</span><span class="sxs-lookup"><span data-stu-id="52412-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="52412-p110">否，您不需要重新啟動電腦。但如果執行 Office 365 eDiscovery 匯出工具，來關閉再重新啟動它之後變更登錄設定。</span><span class="sxs-lookup"><span data-stu-id="52412-p110">No, you don't have to restart the computer. But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="52412-166">**沒有取得編輯現有的登錄機碼或沒有取得建立新的金鑰吗？**</span><span class="sxs-lookup"><span data-stu-id="52412-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="52412-p111">新的登錄機碼會建立第一次執行您在本主題中的程序中建立的.reg 檔案。然後設定編輯每次您變更並重新執行.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="52412-p111">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
