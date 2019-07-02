---
title: 處理資料時的錯誤補救
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8653ebd82e9c045c4fc49b00fcb82bf22ab3f906
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547938"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="3e189-102">處理資料時的錯誤補救</span><span class="sxs-lookup"><span data-stu-id="3e189-102">Error remediation when processing data</span></span>

<span data-ttu-id="3e189-103">錯誤修正功能可讓 eDiscovery 系統管理員修正資料問題, 使高級 eDiscovery 無法正確處理內容。</span><span class="sxs-lookup"><span data-stu-id="3e189-103">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="3e189-104">例如, 由於檔案受到鎖定或加密, 因此無法處理受到密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="3e189-105">使用錯誤修正功能, eDiscovery 系統管理員可以下載有這類錯誤的檔案、移除密碼保護並上傳修正的檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="3e189-106">使用下列工作流程修復高級 eDiscovery 案例中含有錯誤的檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="3e189-107">建立錯誤修復會話以修正含有處理錯誤的檔案</span><span class="sxs-lookup"><span data-stu-id="3e189-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="3e189-108">如果在下列程式中隨時關閉錯誤修正嚮導, 您可以在 [ **View** ] 下拉式功能表中選取 [**錯誤 remediations** ], 從 [**處理**] 索引標籤傳回錯誤修正會話。</span><span class="sxs-lookup"><span data-stu-id="3e189-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="3e189-109">在高級 eDiscovery 案例的 [**處理**] 索引標籤上, 選取 [ **View** ] 下拉式功能表中的 [**錯誤**]。</span><span class="sxs-lookup"><span data-stu-id="3e189-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="3e189-110">按一下 [錯誤類型] 或 [檔案類型] 旁的選項按鈕, 選取您要修正的錯誤。</span><span class="sxs-lookup"><span data-stu-id="3e189-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="3e189-111">在下列範例中, 我們正在修正受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="3e189-112">按一下 [ **+ 新的錯誤修復**]。</span><span class="sxs-lookup"><span data-stu-id="3e189-112">Click **+ New error remediation**.</span></span>

    ![錯誤修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="3e189-114">錯誤修正會話將從準備階段開始, 其中含有錯誤的檔案會複製到安全的 Azure 位置, 以便下載這些檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-114">The error remediation session will begin, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![準備錯誤修復](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="3e189-116">準備完成後, 請按 **[下一步]: 下載**檔案以繼續下載。</span><span class="sxs-lookup"><span data-stu-id="3e189-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="3e189-118">若要下載檔案, 請指定**下載的目的地路徑**;這是您的本機電腦上應該下載檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="3e189-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="3e189-119">預設路徑%USERPROFILE%\Downloads\errors, 指向登入使用者的下載資料夾;您可以視需要變更。</span><span class="sxs-lookup"><span data-stu-id="3e189-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="3e189-120">建議您使用本機檔案路徑, 而非遠端網路路徑, 以取得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="3e189-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e189-121">如果您尚未安裝 AzCopy, 您可以從下列位置進行安裝:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="3e189-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="3e189-122">按一下 [**複製至剪貼**簿], 複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="3e189-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="3e189-123">啟動 windows 命令提示字元, 貼上命令, 然後按**enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="3e189-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="3e189-124">將下載檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-124">The files will be downloaded.</span></span>

    ![準備錯誤修復](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="3e189-126">如果提供的 AzCopy 命令失敗, 請參閱[在高級 eDiscovery 中疑難排解 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="3e189-126">If the supplied AzCopy command fails, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="3e189-127">下載檔案之後, 您可以使用適當的工具進行修復。</span><span class="sxs-lookup"><span data-stu-id="3e189-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="3e189-128">對於密碼保護的檔案, 您可以使用許多密碼破解工具。</span><span class="sxs-lookup"><span data-stu-id="3e189-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="3e189-129">如果您知道檔案的密碼, 您可以開啟檔案並移除密碼保護。</span><span class="sxs-lookup"><span data-stu-id="3e189-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3e189-130">請務必在 tact 中保留已修正檔案的目錄結構和檔案名。</span><span class="sxs-lookup"><span data-stu-id="3e189-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="3e189-131">下載的檔案和資料夾中所使用的所有命名慣例, 都能讓 remdiated 檔案回到原始檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="3e189-132">現在, 回到 [Advanced eDiscovery], 然後按 **[下一步]: 上傳檔案]**。</span><span class="sxs-lookup"><span data-stu-id="3e189-132">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="3e189-133">這會移至下一個步驟, 您現在可以在其中上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-133">This will move to the next step where you can now upload the files.</span></span>

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="3e189-135">在 [檔案**位置路徑**] 文字方塊中, 指定已修正檔案的位置, 然後按一下 [**複製到剪貼**簿]。</span><span class="sxs-lookup"><span data-stu-id="3e189-135">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="3e189-136">將命令貼到 Windows 命令提示字元, 然後按**enter**上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6 .png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="3e189-138">最後, 回到 [Advanced eDiscovery], 然後按 **[下一步]: 處理**檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-138">Finally, return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="3e189-139">處理完成時。</span><span class="sxs-lookup"><span data-stu-id="3e189-139">When processing is complete.</span></span>  <span data-ttu-id="3e189-140">您可以回到 [審閱] 集, 並查看修正的檔案。</span><span class="sxs-lookup"><span data-stu-id="3e189-140">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="3e189-141">修正檔案時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="3e189-141">What happens when files are remediated</span></span>

<span data-ttu-id="3e189-142">當上傳修正的檔案時, 會保留原始的中繼資料, 但不包括下欄欄位:</span><span class="sxs-lookup"><span data-stu-id="3e189-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="3e189-143">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="3e189-143">ExtractedTextSize</span></span>
- <span data-ttu-id="3e189-144">HasText</span><span class="sxs-lookup"><span data-stu-id="3e189-144">HasText</span></span>
- <span data-ttu-id="3e189-145">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="3e189-145">IsErrorRemediate</span></span>
- <span data-ttu-id="3e189-146">LoadId</span><span class="sxs-lookup"><span data-stu-id="3e189-146">LoadId</span></span>
- <span data-ttu-id="3e189-147">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="3e189-147">ProcessingErrorMessage</span></span>
- <span data-ttu-id="3e189-148">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="3e189-148">ProcessingStatus</span></span>
- <span data-ttu-id="3e189-149">Text</span><span class="sxs-lookup"><span data-stu-id="3e189-149">Text</span></span>
- <span data-ttu-id="3e189-150">WordCount</span><span class="sxs-lookup"><span data-stu-id="3e189-150">WordCount</span></span>
- <span data-ttu-id="3e189-151">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="3e189-151">WorkingsetId</span></span>

<span data-ttu-id="3e189-152">如需高級 eDiscovery 中所有檔元資料欄位的定義, 請參閱[檔元資料欄位](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="3e189-152">For a definition of all document metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
