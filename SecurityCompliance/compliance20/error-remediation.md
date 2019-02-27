---
title: 處理資料時發生補救錯誤
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: bf48e605dc321da4b7a9d5343d18f90fbb179073
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296726"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="8020d-102">處理資料時發生補救錯誤</span><span class="sxs-lookup"><span data-stu-id="8020d-102">Error remediation when processing data</span></span>

<span data-ttu-id="8020d-p101">錯誤修復允許 eDiscovery 系統管理員能夠修正防止進階的 eDiscovery （預覽） 適當地處理內容的資料問題。例如，由於檔案鎖定或加密無法處理受到密碼保護的檔案。使用錯誤補救、 eDiscovery 管理員可以下載含有這類錯誤的檔案、 移除密碼保護及上傳的已修復的檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-p101">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content. For example, files that are password protected cannot be processed since the files are locked or encrypted. Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="8020d-106">使用下列工作流程來修復檔案與進階的 eDiscovery （預覽） 案例中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="8020d-106">Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="8020d-107">建立要修復檔案處理錯誤的錯誤補救工作階段</span><span class="sxs-lookup"><span data-stu-id="8020d-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="8020d-108">如果錯誤補救精靈已關閉下列程序期間的任何時候，您可以傳回給錯誤補救工作階段的 [**處理**] 索引標籤來**檢視**下拉式功能表中選取**錯誤補救措施**。</span><span class="sxs-lookup"><span data-stu-id="8020d-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="8020d-109">[**處理**] 索引標籤進階的 eDiscovery （預覽） 案例中選取 [**檢視**下拉式清單功能表中的 [**錯誤**]。</span><span class="sxs-lookup"><span data-stu-id="8020d-109">On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="8020d-p102">選取您要修復按一下旁邊的錯誤類型或檔案類型] 選項按鈕的錯誤。 在下列範例中，我們要補救相關密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-p102">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.  In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="8020d-112">按一下 [ **+ 新錯誤補救方法**。</span><span class="sxs-lookup"><span data-stu-id="8020d-112">Click **+ New error remediation**.</span></span>

    ![錯誤修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="8020d-114">錯誤修復工作階段會開始，開頭準備階段而發生此錯誤的檔案移至安全的 Azure 位置下載位置。</span><span class="sxs-lookup"><span data-stu-id="8020d-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![準備錯誤補救方法](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="8020d-116">準備完成後，按一下 [**下一步： 下載檔案**繼續進行下載。</span><span class="sxs-lookup"><span data-stu-id="8020d-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="8020d-p103">若要下載檔案，指定**供下載的目的路徑**；這是您應該已下載檔案的位置的本機電腦上的路徑。 預設路徑，%userprofile%\downloads\errors、 指向已登入使用者的下載項目資料夾;這可以視需要變更。</span><span class="sxs-lookup"><span data-stu-id="8020d-p103">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.  The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="8020d-120">我們建議您使用本機檔案路徑，而不是遠端網路路徑以達最佳效能。</span><span class="sxs-lookup"><span data-stu-id="8020d-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8020d-121">若您尚未安裝 AzCopy，您可以從這裡來進行安裝：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="8020d-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="8020d-p104">依序按一下 [**複製到剪貼簿**中複製的預先定義的命令。啟動 windows 命令提示字元下、 貼上命令並按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8020d-p104">Copy the predefined command by clicking **Copy to clipboard**. Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="8020d-124">將下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-124">The files will be downloaded.</span></span>

    ![準備錯誤補救方法](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="8020d-126">如果您有執行此命令的問題，請參閱https://go.microsoft.com/fwlink/?linkid=2038117疑難排解秘訣。</span><span class="sxs-lookup"><span data-stu-id="8020d-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="8020d-p105">下載檔案之後, 可以修復它們與適當的工具。受密碼保護之檔案有許多密碼破解您可以使用的工具。如果您知道檔案密碼，您可以開啟其並移除密碼保護。</span><span class="sxs-lookup"><span data-stu-id="8020d-p105">After downloading the files, you can remediate them with an appropriate tool. For password protected files, there are a number of password cracking tools you can use. If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="8020d-p106">IT 重要您保留可識別的已修復檔案的目錄結構和檔案名稱。 所有的命名慣例用於下載的檔案及資料夾進行可能產生關聯回原始的 remdiated 檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-p106">IT is important that you retain the directory structure and file names of the remediated files in tact.  All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="8020d-p107">現在，傳回進階 ediscovery （預覽） 並按一下 [**下一步： 上傳檔案**。 這會將移至下一個步驟可以立即上載的檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-p107">Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.  This will move to the next step where you can now upload the files.</span></span>

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="8020d-135">不必**的檔案位置路徑**] 文字方塊中的已修復檔案的位置然後按一下 [**複製到 clibpboard**。</span><span class="sxs-lookup"><span data-stu-id="8020d-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="8020d-136">貼到 Windows 命令提示字元上命令並按**Enter**以上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="8020d-138">最後，傳回進階 ediscovery （預覽） 並按一下 [**下一步： 處理檔案**。</span><span class="sxs-lookup"><span data-stu-id="8020d-138">Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="8020d-p108">當處理已完成。 您可以返回工作集並查看已修復的檔案。</span><span class="sxs-lookup"><span data-stu-id="8020d-p108">When processing is complete.  You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="8020d-141">檔案會在於時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="8020d-141">What happens when files are remediated</span></span>

<span data-ttu-id="8020d-142">當已修復的檔案上傳時、 原始的中繼資料會保留除了下列欄位：</span><span class="sxs-lookup"><span data-stu-id="8020d-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="8020d-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="8020d-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="8020d-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="8020d-144">ExtractedTextSize</span></span>
- <span data-ttu-id="8020d-145">HasText</span><span class="sxs-lookup"><span data-stu-id="8020d-145">HasText</span></span>
- <span data-ttu-id="8020d-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="8020d-146">IsErrorRemediate</span></span>
- <span data-ttu-id="8020d-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="8020d-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="8020d-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="8020d-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="8020d-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="8020d-149">LoadId</span></span>
- <span data-ttu-id="8020d-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="8020d-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="8020d-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="8020d-151">ProcessingStatus</span></span>
- <span data-ttu-id="8020d-152">文字</span><span class="sxs-lookup"><span data-stu-id="8020d-152">Text</span></span>
- <span data-ttu-id="8020d-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="8020d-153">WordCount</span></span>
- <span data-ttu-id="8020d-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="8020d-154">WorkingsetId</span></span>

<span data-ttu-id="8020d-155">進階 eDiscovery (Preview) 中的所有文件中繼資料欄位的定義，請參閱[文件中繼資料欄位](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="8020d-155">For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>