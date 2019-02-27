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
# <a name="load-non-office-365-data-into-a-working-set"></a>將非 Office 365 的資料載入工作集

您可能需要使用 Office 365 進階 eDiscovery 分析的不是所有文件將會在 Office 365 live。非 Office 365 內容匯入進階 eDiscovery 可以上傳不 live Office 365 中使用組分析進階 eDiscovery 與因此的文件中的功能。此程序將示範如何將非 Office 365 文件移入進階 eDiscovery 進行分析。

>[!Note]
>進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以註冊 Office 365 企業版 E5 試用版。

## <a name="before-you-begin"></a>開始之前
使用此程序所述的上傳非 Office 365 功能需要您：

- 進階規範的附加元件或 E5 訂閱 Office 365 E3。

- 將上傳其非 Office 365 內容的所有 custodians 必須有都已 E3 進階規範的附加元件或 E5 授權。

- 現有的 eDiscovery 案例。

- 所有上傳的檔案所收集到資料夾，其中有 okay 每一個資料夾以及的資料夾名稱是在此格式*alias@domainname* 。*Alias@domainname*必須是 Office 365 的使用者別名及網域。您可以將根資料夾收集所有*alias@domainname*資料夾。根資料夾只能含有*alias@domainname*資料夾、 根資料夾中必須有沒有寬鬆的檔案。

- 帳戶是 eDiscovery 管理員或 eDiscovery 管理員 Microsoft Azure 儲存安裝工具可存取的非 Office 365 內容的資料夾結構的電腦上。

- 安裝 AzCopy，您可以從這裡執行動作：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>將非 Office 365 內容上載至進階的 eDiscovery

1. EDiscovery 管理員或 eDiscovery 管理員，以開啟 [進階的 eDiscovery，然後將上傳至非 Office 365 資料的大小寫。 按一下 [**處理設定**] 索引標籤上，然後選取您想要將非 Office 365 資料載入工作設定。 如果您無法建立工作集，您可以立即達成。 最後，按一下 [**管理起步設定**則非 Office 365 資料] 區段中的**檢視上傳**

2. 按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。

![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 在精靈的第一個步驟只是準備安全的 Azure blob 要上傳的檔案。 後準備 compelted，按一下 [**下一步： 上傳檔案**] 按鈕。

![非 Office 365 匯入-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在 [**上傳檔案**] 步驟中指定**的檔案位置路徑**] 中，這是您計劃匯入的非 Office 365 資料所在。 設定正確的位置可確保正確更新命令 AzCopy。

> [!NOTE]
> 如果您未安裝 AzCopy，您可以這麼做從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. 按一下 [**複製到剪貼簿**] 連結複製預先定義的命令。啟動 windows 命令提示字元下、 貼上命令並按 enter 鍵。 將檔案將上傳至安全的 Azure blob 儲存的下一個步驟。

![非 Office 365 Import-上傳檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後，傳回給安全性 & 規範，並按一下 [**下一步： 處理檔案**] 按鈕。 這將會引發處理、 擷取文字及編製索引的上傳的檔案。 您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，新的檔案會提供工作集內。 處理完成後，您可以關閉精靈。

![非 Office 365 Import-程序的檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

