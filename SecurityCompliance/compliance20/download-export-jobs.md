---
title: 下載匯出工作
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
ms.openlocfilehash: 56ed8eac259974b43ca0cd26b2bd0c339a5fc05b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155145"
---
# <a name="download-export-jobs"></a><span data-ttu-id="13b17-102">下載匯出工作</span><span class="sxs-lookup"><span data-stu-id="13b17-102">Download export jobs</span></span>

<span data-ttu-id="13b17-103">所有匯出的資料會新增至 Microsoft Azure blob。</span><span class="sxs-lookup"><span data-stu-id="13b17-103">All exported data is added to a Microsoft Azure blob.</span></span> <span data-ttu-id="13b17-104">這提供多個選項來處理傳輸的資料。</span><span class="sxs-lookup"><span data-stu-id="13b17-104">This provides multiple options to handle the data downstream.</span></span> <span data-ttu-id="13b17-105">有幾種方式可以存取 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="13b17-105">There are several ways to access an Azure blob.</span></span> <span data-ttu-id="13b17-106">一種方法是使用 Azure 存放裝置總管。</span><span class="sxs-lookup"><span data-stu-id="13b17-106">One method is to use Azure Storage Explorer.</span></span> <span data-ttu-id="13b17-107">此方法支援簡單的連線，瀏覽和下載。</span><span class="sxs-lookup"><span data-stu-id="13b17-107">This method supports simple connection, browsing and downloading.</span></span> <span data-ttu-id="13b17-108">如需詳細資訊，請瀏覽<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span><span class="sxs-lookup"><span data-stu-id="13b17-108">For more information, visit <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span></span>

1.  <span data-ttu-id="13b17-109">若要匯出工作完成後，請下載內容，請移至 [匯出] 索引標籤，並選取 [匯出工作。</span><span class="sxs-lookup"><span data-stu-id="13b17-109">To download content after an export job is complete, go to the Exports tab and select an export job.</span></span>

2.  <span data-ttu-id="13b17-110">延伸的 」 位置] 區段中複製的文字。</span><span class="sxs-lookup"><span data-stu-id="13b17-110">Copy the text in the “Locations” section of the flyout.</span></span>

![](../media/eDiscoExportJob.png)

3.  <span data-ttu-id="13b17-111">開啟 Azure 存放裝置總管，然後按一下 「 連線 」 按鈕</span><span class="sxs-lookup"><span data-stu-id="13b17-111">Open Azure Storage Explorer and click the “Connect” button</span></span>

![](../media/AzureStorageConnect.png)

4.  <span data-ttu-id="13b17-112">選取 [使用共用的存取簽章 URI]，然後按一下 [下一步]</span><span class="sxs-lookup"><span data-stu-id="13b17-112">Select “Use a shared access signature URI” and click next</span></span>

![](../media/AzureStorageConnect2.png)

5.  <span data-ttu-id="13b17-113">將位置文字貼在 URI] 文字方塊中，按一下 [下一步]</span><span class="sxs-lookup"><span data-stu-id="13b17-113">Paste the Location text in the URI text box and click next</span></span>

![](../media/AzureStorageConnect3.png)

6.  <span data-ttu-id="13b17-114">按一下 [連線]</span><span class="sxs-lookup"><span data-stu-id="13b17-114">Click Connect</span></span>

![](../media/AzureStorageConnect4.png)

<span data-ttu-id="13b17-115">這會新增匯出成 Storage Accounts/SAS-Attached 服務/Blob 容器中的物件。</span><span class="sxs-lookup"><span data-stu-id="13b17-115">This will add the export as an object in Storage Accounts/SAS-Attached Services/Blob Containers.</span></span> <span data-ttu-id="13b17-116">您將能夠探索匯出及下載所有或部分匯出。</span><span class="sxs-lookup"><span data-stu-id="13b17-116">You will be able to explore the export and download all or portions of the export.</span></span>

![](../media/AzureStorageConnect5.png)