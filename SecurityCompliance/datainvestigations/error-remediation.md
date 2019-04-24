---
title: 錯誤修復時處理資料來進行調查
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
ms.openlocfilehash: b78a8e45ffb0833dec5116ff637cd0930387ebfe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258861"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="1cf36-102">錯誤修復時處理資料來進行調查</span><span class="sxs-lookup"><span data-stu-id="1cf36-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="1cf36-103">錯誤修復允許現場修正正確處理內容時，防止資料調查 （預覽） 的資料問題的能力。</span><span class="sxs-lookup"><span data-stu-id="1cf36-103">Error remediation allows investigators the ability to rectify data issues which prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="1cf36-104">例如，因為檔案已鎖定或加密，無法處理受到密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="1cf36-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="1cf36-105">使用錯誤修復，現場可以下載這類錯誤的檔案、 移除密碼保護和修復的檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="1cf36-105">Using error remediation, investigators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="1cf36-106">使用下列工作流程來修復檔案與資料調查 （預覽） 案例中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="1cf36-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="1cf36-107">建立要修復檔案與處理錯誤的錯誤修復工作階段</span><span class="sxs-lookup"><span data-stu-id="1cf36-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="1cf36-108">如果錯誤修復精靈已關閉隨時在下列程序期間，您可以傳回的錯誤修復工作階段 [**處理**] 索引標籤選取 [**檢視**] 下拉式功能表中的 [**錯誤補救措施**。</span><span class="sxs-lookup"><span data-stu-id="1cf36-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="1cf36-109">**處理**] 索引標籤上的資料調查 （預覽） 案例中，選取 [**檢視**] 下拉式功能表中的 [**錯誤**]。</span><span class="sxs-lookup"><span data-stu-id="1cf36-109">On the **Processing** tab in an Data Investigations (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="1cf36-110">選取您要修復]，即可錯誤類型或檔案類型] 旁的 [選項] 按鈕的錯誤。</span><span class="sxs-lookup"><span data-stu-id="1cf36-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="1cf36-111">在下列範例中，我們正在修復密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="1cf36-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="1cf36-112">按一下 [ **+ 新錯誤修復**]。</span><span class="sxs-lookup"><span data-stu-id="1cf36-112">Click **+ New error remediation**.</span></span>

    ![錯誤修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="1cf36-114">錯誤修復工作階段會開始，開始準備階段，而發生錯誤的檔案移至安全的 Azure 位置下載位置。</span><span class="sxs-lookup"><span data-stu-id="1cf36-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![準備錯誤修復](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="1cf36-116">準備工作完成後，按一下 [**下一步： 下載檔案**繼續進行下載。</span><span class="sxs-lookup"><span data-stu-id="1cf36-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="1cf36-118">若要下載檔案，指定 [**下載的目的路徑**;這是您應該已下載檔案的位置的本機電腦上的路徑。</span><span class="sxs-lookup"><span data-stu-id="1cf36-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="1cf36-119">預設路徑，%userprofile%\downloads\errors，指向登入使用者的下載項目資料夾;這可以視需要變更。</span><span class="sxs-lookup"><span data-stu-id="1cf36-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="1cf36-120">我們建議而不是遠端網路路徑使用本機檔案路徑，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="1cf36-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cf36-121">如果您未安裝 AzCopy，您可以從這裡安裝它：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="1cf36-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="1cf36-122">按一下 [**複製到剪貼簿**複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="1cf36-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="1cf36-123">啟動 windows 命令提示字元中，貼上] 命令，並按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="1cf36-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="1cf36-124">將下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="1cf36-124">The files will be downloaded.</span></span>

    ![準備錯誤修復](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="1cf36-126">如果您執行此命令的問題，請參閱https://go.microsoft.com/fwlink/?linkid=2038117如需疑難排解秘訣。</span><span class="sxs-lookup"><span data-stu-id="1cf36-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="1cf36-127">下載檔案之後, 您可以使用適當工具修復它們。</span><span class="sxs-lookup"><span data-stu-id="1cf36-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="1cf36-128">密碼保護之檔案有許多密碼破解您可以使用的工具。</span><span class="sxs-lookup"><span data-stu-id="1cf36-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="1cf36-129">如果您知道之檔案的密碼，您可以將其開啟，並移除密碼保護。</span><span class="sxs-lookup"><span data-stu-id="1cf36-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="1cf36-130">IT 很重要，您會保留原封不動的修復檔案的目錄結構和檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="1cf36-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="1cf36-131">所有命名慣例用於下載的檔案和資料夾會讓您能夠建立回原始的 remdiated 檔案的關聯。</span><span class="sxs-lookup"><span data-stu-id="1cf36-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="1cf36-132">現在，返回資料調查 （預覽），然後按一下 [**下一步： 將檔案上傳**。</span><span class="sxs-lookup"><span data-stu-id="1cf36-132">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="1cf36-133">這將會移到下一步： 您現在可以上載檔案。</span><span class="sxs-lookup"><span data-stu-id="1cf36-133">This will move to the next step where you can now upload the files.</span></span>

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="1cf36-135">請指定**的檔案位置路徑**] 文字方塊中，在修復檔案的位置然後按一下 [**複製到 clibpboard**。</span><span class="sxs-lookup"><span data-stu-id="1cf36-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="1cf36-136">貼上命令到 Windows 命令提示字元，並按**Enter** ，以將檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="1cf36-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="1cf36-138">最後，返回 [資料調查 （預覽），然後按一下 [**下一步： 處理檔案**。</span><span class="sxs-lookup"><span data-stu-id="1cf36-138">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="1cf36-139">當處理已完成。</span><span class="sxs-lookup"><span data-stu-id="1cf36-139">When processing is complete.</span></span>  <span data-ttu-id="1cf36-140">您可以返回工作集，並查看修復的檔案。</span><span class="sxs-lookup"><span data-stu-id="1cf36-140">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="1cf36-141">當檔案修復時，會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="1cf36-141">What happens when files are remediated</span></span>

<span data-ttu-id="1cf36-142">當修復的檔案上傳時，原始的中繼資料會保留除了下列欄位：</span><span class="sxs-lookup"><span data-stu-id="1cf36-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="1cf36-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="1cf36-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="1cf36-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="1cf36-144">ExtractedTextSize</span></span>
- <span data-ttu-id="1cf36-145">HasText</span><span class="sxs-lookup"><span data-stu-id="1cf36-145">HasText</span></span>
- <span data-ttu-id="1cf36-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="1cf36-146">IsErrorRemediate</span></span>
- <span data-ttu-id="1cf36-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="1cf36-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="1cf36-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="1cf36-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="1cf36-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="1cf36-149">LoadId</span></span>
- <span data-ttu-id="1cf36-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="1cf36-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="1cf36-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="1cf36-151">ProcessingStatus</span></span>
- <span data-ttu-id="1cf36-152">Text</span><span class="sxs-lookup"><span data-stu-id="1cf36-152">Text</span></span>
- <span data-ttu-id="1cf36-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="1cf36-153">WordCount</span></span>
- <span data-ttu-id="1cf36-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="1cf36-154">WorkingsetId</span></span>

<span data-ttu-id="1cf36-155">如需資料調查 （預覽） 中的所有文件中繼資料欄位的定義，請參閱 <<c0>文件的中繼資料欄位。</span><span class="sxs-lookup"><span data-stu-id="1cf36-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>