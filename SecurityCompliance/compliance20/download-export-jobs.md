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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32251889"
---
# <a name="download-export-jobs"></a>下載匯出工作

所有匯出的資料會新增至 Microsoft Azure blob。 這提供多個選項來處理傳輸的資料。 有幾種方式可以存取 Azure blob。 一種方法是使用 Azure 存放裝置總管。 此方法支援簡單的連線，瀏覽和下載。 如需詳細資訊，請瀏覽<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer>

1.  若要匯出工作完成後，請下載內容，請移至 [匯出] 索引標籤，並選取 [匯出工作。

2.  延伸的 」 位置] 區段中複製的文字。

![](../media/eDiscoExportJob.png)

3.  開啟 Azure 存放裝置總管，然後按一下 「 連線 」 按鈕

![](../media/AzureStorageConnect.png)

4.  選取 [使用共用的存取簽章 URI]，然後按一下 [下一步]

![](../media/AzureStorageConnect2.png)

5.  將位置文字貼在 URI] 文字方塊中，按一下 [下一步]

![](../media/AzureStorageConnect3.png)

6.  按一下 [連線]

![](../media/AzureStorageConnect4.png)

這會新增匯出成 Storage Accounts/SAS-Attached 服務/Blob 容器中的物件。 您將能夠探索匯出及下載所有或部分匯出。

![](../media/AzureStorageConnect5.png)