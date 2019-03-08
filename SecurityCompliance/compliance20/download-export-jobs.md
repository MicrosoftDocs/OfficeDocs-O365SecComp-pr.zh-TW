---
title: 下載匯出工作
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
ms.openlocfilehash: 904bc5f8a6d6cef937d55336e8f383957713769a
ms.sourcegitcommit: 9f38ba72eba0b656e507860ca228726e4199f7ec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2019
ms.locfileid: "30475693"
---
# <a name="download-export-jobs"></a><span data-ttu-id="f8fc2-102">下載匯出工作</span><span class="sxs-lookup"><span data-stu-id="f8fc2-102">Download export jobs</span></span>

<span data-ttu-id="f8fc2-103">所有匯出的資料會新增至 Microsoft Azure blob。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-103">All exported data is added to a Microsoft Azure blob.</span></span> <span data-ttu-id="f8fc2-104">這提供多個選項來處理傳輸的資料。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-104">This provides multiple options to handle the data downstream.</span></span> <span data-ttu-id="f8fc2-105">有幾種方式可以存取 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-105">There are several ways to access an Azure blob.</span></span> <span data-ttu-id="f8fc2-106">一種方法是使用 Azure 存放裝置總管。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-106">One method is to use Azure Storage Explorer.</span></span> <span data-ttu-id="f8fc2-107">此方法支援簡單的連線，瀏覽和下載。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-107">This method supports simple connection, browsing and downloading.</span></span> <span data-ttu-id="f8fc2-108">如需詳細資訊，請瀏覽<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span><span class="sxs-lookup"><span data-stu-id="f8fc2-108">For more information, visit <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span></span>

1.  <span data-ttu-id="f8fc2-109">若要匯出工作完成後，請下載內容，請移至 [匯出] 索引標籤，並選取 [匯出工作。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-109">To download content after an export job is complete, go to the Exports tab and select an export job.</span></span>

2.  <span data-ttu-id="f8fc2-110">延伸的 」 位置] 區段中複製的文字。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-110">Copy the text in the “Locations” section of the flyout.</span></span>

![](../media/eDiscoExportJob.png)

3.  <span data-ttu-id="f8fc2-111">開啟 Azure 存放裝置總管，然後按一下 「 連線 」 按鈕</span><span class="sxs-lookup"><span data-stu-id="f8fc2-111">Open Azure Storage Explorer and click the “Connect” button</span></span>

![](../media/AzureStorageConnect.png)

4.  <span data-ttu-id="f8fc2-112">選取 [使用共用的存取簽章 URI]，然後按一下 [下一步]</span><span class="sxs-lookup"><span data-stu-id="f8fc2-112">Select “Use a shared access signature URI” and click next</span></span>

![](../media/AzureStorageConnect2.png)

5.  <span data-ttu-id="f8fc2-113">將位置文字貼在 URI] 文字方塊中，按一下 [下一步]</span><span class="sxs-lookup"><span data-stu-id="f8fc2-113">Paste the Location text in the URI text box and click next</span></span>

![](../media/AzureStorageConnect3.png)

6.  <span data-ttu-id="f8fc2-114">按一下 [連線]</span><span class="sxs-lookup"><span data-stu-id="f8fc2-114">Click Connect</span></span>

![](../media/AzureStorageConnect4.png)

<span data-ttu-id="f8fc2-115">這會新增匯出成 Storage Accounts/SAS-Attached 服務/Blob 容器中的物件。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-115">This will add the export as an object in Storage Accounts/SAS-Attached Services/Blob Containers.</span></span> <span data-ttu-id="f8fc2-116">您將能夠探索匯出及下載所有或部分匯出。</span><span class="sxs-lookup"><span data-stu-id="f8fc2-116">You will be able to explore the export and download all or portions of the export.</span></span>

![](../media/AzureStorageConnect5.png)