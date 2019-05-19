---
title: 將非 Office 365 的資料載入檢閱集
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
ms.openlocfilehash: 86d858994f95176ea4d415405c4043f7e7c5308e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155005"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="bf141-102">將非 Office 365 的資料載入檢閱集</span><span class="sxs-lookup"><span data-stu-id="bf141-102">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="bf141-103">並非所有文件，您可能需要與 Office 365 進階電子文件探索分析會存在於 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="bf141-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="bf141-104">使用非 Office 365 內容匯入您可以上傳到設定分析進階電子文件與因此檢閱不 live Office 365 中的文件的進階電子文件中的功能。</span><span class="sxs-lookup"><span data-stu-id="bf141-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a review set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="bf141-105">此程序將示範如何將非 Office 365 文件移入進階電子文件探索進行分析。</span><span class="sxs-lookup"><span data-stu-id="bf141-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="bf141-106">進階電子文件為您的組織需要與進階合規性附加元件或 E5 訂閱 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="bf141-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="bf141-107">如果您不具有該計劃，並想要再試進階電子文件，您可以註冊 Office 365 企業版 E5 的試用版。</span><span class="sxs-lookup"><span data-stu-id="bf141-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bf141-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="bf141-108">Before you begin</span></span>

<span data-ttu-id="bf141-109">使用上傳非 Office 365 功能，如本文所述，需要您有下列：</span><span class="sxs-lookup"><span data-stu-id="bf141-109">Using the upload Non-Office 365 feature as described in this article requires that you have the following:</span></span>

- <span data-ttu-id="bf141-110">Office 365 或 Microsoft 365 E5 訂閱或與進階合規性的附加元件訂閱版 E3 訂閱。</span><span class="sxs-lookup"><span data-stu-id="bf141-110">An Office 365 or Microsoft 365 E5 subscription or an E3 subscription with the Advanced Compliance add-on subscription.</span></span>

- <span data-ttu-id="bf141-111">將上傳其非 Office 365 內容的所有 custodians 必須有版 E3 授權來搭配進階合規性的附加元件授權或具有 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="bf141-111">All custodians whose non-Office 365 content will be uploaded must have E3 license with an Advanced Compliance add-on license or have an E5 license.</span></span>

- <span data-ttu-id="bf141-112">現有的進階電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="bf141-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="bf141-113">Custodians 必須新增至這種情況，您將有相關聯的非 Office 365 資料上傳至它們之前。</span><span class="sxs-lookup"><span data-stu-id="bf141-113">Custodians must be added to the case before you upload the non-Office 365 data that's associated to them.</span></span>

- <span data-ttu-id="bf141-114">將上傳的所有檔案必須都位於的資料夾，其中每個資料夾是與特定 custodian 相關聯。</span><span class="sxs-lookup"><span data-stu-id="bf141-114">All files that will be uploaded must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="bf141-115">這些資料夾的名稱必須使用下列的命名格式： *alias@domainname*。</span><span class="sxs-lookup"><span data-stu-id="bf141-115">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="bf141-116">*Alias@domainname*必須是使用者的 Office 365 別名和網域。</span><span class="sxs-lookup"><span data-stu-id="bf141-116">The *alias@domainname* must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="bf141-117">您可以收集所有*alias@domainname*資料夾到根資料夾。</span><span class="sxs-lookup"><span data-stu-id="bf141-117">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="bf141-118">根資料夾僅能包含*alias@domainname*資料夾;寬鬆的檔案不允許的根資料夾中。</span><span class="sxs-lookup"><span data-stu-id="bf141-118">The root folder can only contain the *alias@domainname* folders; loose files aren't allowed in the root folder.</span></span>

   <span data-ttu-id="bf141-119">比方說，您要上傳的非 Office 365 資料的資料夾結構可能與下列相似：</span><span class="sxs-lookup"><span data-stu-id="bf141-119">For example, the folder structure for the non-Office 365 data that you want to upload would be similar to the following:</span></span>

   - <span data-ttu-id="bf141-120">c:\nonO365\ abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf141-120">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="bf141-121">c:\nonO365\ jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf141-121">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="bf141-122">c:\nonO365\ staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf141-122">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="bf141-123">其中 abraham.mcmahon@contoso.com、 jewell.gordon@contoso.com 及 staci.gonzalez@contoso.com 均的情況下 custodians 的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="bf141-123">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![非 Office 365 的資料上傳資料夾結構](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="bf141-125">EDiscovery 管理員 」 或 「 eDiscovery 系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="bf141-125">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>

- <span data-ttu-id="bf141-126">具有非 Office 365 內容的資料夾結構的存取權的電腦上安裝 Microsoft Azure 儲存體工具。</span><span class="sxs-lookup"><span data-stu-id="bf141-126">Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="bf141-127">安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="bf141-127">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="bf141-128">非 Office 365 內容上傳至進階電子文件</span><span class="sxs-lookup"><span data-stu-id="bf141-128">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="bf141-129">EDiscovery 管理員或 eDiscovery 系統管理員，以開啟 [進階電子文件，然後將上傳到非 Office 365 資料的案例]。</span><span class="sxs-lookup"><span data-stu-id="bf141-129">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="bf141-130">**檢閱 [設定**] 索引標籤，然後選取您想要將非 Office 365 資料載入檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="bf141-130">Click the **review sets** tab, then select the review set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="bf141-131">如果您未建立檢閱設定，您可以立即執行。</span><span class="sxs-lookup"><span data-stu-id="bf141-131">If you have not already created a review set, you can do so now.</span></span>  <span data-ttu-id="bf141-132">最後，按一下 [**管理檢閱設定**，然後按一下 [**檢視上傳**中 \* \* 非 Office 365 [資料] 磚。</span><span class="sxs-lookup"><span data-stu-id="bf141-132">Finally, click **Manage review set** and then click **View uploads** in the \*\*Non-Office 365 data tile.</span></span>

2. <span data-ttu-id="bf141-133">按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。</span><span class="sxs-lookup"><span data-stu-id="bf141-133">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

   ![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="bf141-135">在精靈中的第一個步驟只會準備要上傳檔案的安全 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="bf141-135">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="bf141-136">準備完成之後，按一下 [**下一步： 將檔案上傳**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bf141-136">Once preparation is completed, click the **Next: Upload files** button.</span></span>

   ![非 Office 365 匯入-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="bf141-138">在 [**上傳檔案**] 步驟中，指定**的檔案位置路徑**] 中，這是您計劃匯入非 Office 365 資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="bf141-138">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="bf141-139">設定正確的位置可確保正確更新命令 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="bf141-139">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bf141-140">如果您未安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="bf141-140">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="bf141-141">按一下 [**複製到剪貼簿**] 連結，將複製的預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="bf141-141">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="bf141-142">啟動 windows 命令提示字元中，貼上命令並按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="bf141-142">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="bf141-143">檔案就會上傳到安全的 Azure blob 儲存的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="bf141-143">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

   ![非-Office 365 匯入-上傳檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![非 Office 365 匯入-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="bf141-146">如果提供的 AzCopy 命令失敗，請參閱[疑難排解 AzCopy 進階電子文件中](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="bf141-146">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

6. <span data-ttu-id="bf141-147">最後，傳回回到安全性 & 合規性，並按一下 [**下一步： 處理檔案**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bf141-147">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="bf141-148">這將會引發處理、 文字擷取和編製索引的上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="bf141-148">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="bf141-149">您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，新的檔案則可在檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="bf141-149">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the review set.</span></span>  <span data-ttu-id="bf141-150">處理完成後，您可以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="bf141-150">Once processing is complete, you can dismiss the wizard.</span></span>

   ![非-Office 365 匯入的程序檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

