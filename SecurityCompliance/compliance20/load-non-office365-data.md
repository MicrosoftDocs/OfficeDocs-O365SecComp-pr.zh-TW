---
title: 將非 Office 365 的資料載入工作集
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
ms.openlocfilehash: b177fc292c748f21907621196dc28d6b8fe17959
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296786"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="6d85c-102">將非 Office 365 的資料載入工作集</span><span class="sxs-lookup"><span data-stu-id="6d85c-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="6d85c-p101">您可能需要使用 Office 365 進階 eDiscovery 分析的不是所有文件將會在 Office 365 live。非 Office 365 內容匯入進階 eDiscovery 可以上傳不 live Office 365 中使用組分析進階 eDiscovery 與因此的文件中的功能。此程序將示範如何將非 Office 365 文件移入進階 eDiscovery 進行分析。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="6d85c-p102">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以註冊 Office 365 企業版 E5 試用版。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6d85c-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="6d85c-108">Before you begin</span></span>
<span data-ttu-id="6d85c-109">使用此程序所述的上傳非 Office 365 功能需要您：</span><span class="sxs-lookup"><span data-stu-id="6d85c-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="6d85c-110">進階規範的附加元件或 E5 訂閱 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="6d85c-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="6d85c-111">將上傳其非 Office 365 內容的所有 custodians 必須有都已 E3 進階規範的附加元件或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="6d85c-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="6d85c-112">現有的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="6d85c-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="6d85c-p103">所有上傳的檔案所收集到資料夾，其中有 okay 每一個資料夾以及的資料夾名稱是在此格式*alias@domainname* 。*Alias@domainname*必須是 Office 365 的使用者別名及網域。您可以將根資料夾收集所有*alias@domainname*資料夾。根資料夾只能含有*alias@domainname*資料夾、 根資料夾中必須有沒有寬鬆的檔案。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="6d85c-117">帳戶是 eDiscovery 管理員或 eDiscovery 管理員 Microsoft Azure 儲存安裝工具可存取的非 Office 365 內容的資料夾結構的電腦上。</span><span class="sxs-lookup"><span data-stu-id="6d85c-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="6d85c-118">安裝 AzCopy，您可以從這裡執行動作：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="6d85c-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="6d85c-119">將非 Office 365 內容上載至進階的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6d85c-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="6d85c-p104">EDiscovery 管理員或 eDiscovery 管理員，以開啟 [進階的 eDiscovery，然後將上傳至非 Office 365 資料的大小寫。 按一下 [**處理設定**] 索引標籤上，然後選取您想要將非 Office 365 資料載入工作設定。 如果您無法建立工作集，您可以立即達成。 最後，按一下 [**管理起步設定**則非 Office 365 資料] 區段中的**檢視上傳**</span><span class="sxs-lookup"><span data-stu-id="6d85c-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="6d85c-124">按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。</span><span class="sxs-lookup"><span data-stu-id="6d85c-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="6d85c-p105">在精靈的第一個步驟只是準備安全的 Azure blob 要上傳的檔案。 後準備 compelted，按一下 [**下一步： 上傳檔案**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![非 Office 365 匯入-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="6d85c-p106">在 [**上傳檔案**] 步驟中指定**的檔案位置路徑**] 中，這是您計劃匯入的非 Office 365 資料所在。 設定正確的位置可確保正確更新命令 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="6d85c-131">如果您未安裝 AzCopy，您可以這麼做從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="6d85c-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="6d85c-p107">按一下 [**複製到剪貼簿**] 連結複製預先定義的命令。啟動 windows 命令提示字元下、 貼上命令並按 enter 鍵。 將檔案將上傳至安全的 Azure blob 儲存的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![非 Office 365 Import-上傳檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="6d85c-p108">最後，傳回給安全性 & 規範，並按一下 [**下一步： 處理檔案**] 按鈕。 這將會引發處理、 擷取文字及編製索引的上傳的檔案。 您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，新的檔案會提供工作集內。 處理完成後，您可以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="6d85c-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![非 Office 365 Import-程序的檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

