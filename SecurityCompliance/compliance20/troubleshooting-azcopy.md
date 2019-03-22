---
title: 疑難排解 AzCopy 在進階電子文件 （預覽）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9711bee4ec9a61510b47568df37dfd3135e1e00c
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2019
ms.locfileid: "30742497"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a>疑難排解 AzCopy 在進階電子文件 （預覽）

在使用者介面時載入非 Office 365 的資料或錯誤修復進階電子文件 （預覽） 中的文件，提供包含參數與您要上傳檔案儲存位置和 Azure 位置 Azure AzCopy 命令將上傳檔案到的儲存位置。 若要上傳您的文件，您複製此命令，然後再執行命令提示字元處的它在本機電腦上。  下列螢幕擷取畫面顯示 AzCopy 命令的範例：

![將非 Office 365 檔案上傳](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

在大部分情況下，當您執行時，將運作所提供的命令。 不過，有可能的情況下時顯示的命令不會成功執行。 以下是一些可能的原因。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy 未安裝在本機電腦或未安裝在預設位置

如果未安裝 AzCopy 或會安裝在位置以外預設安裝位置 (也就是`%ProgramFiles(x86)%`)，當您執行 AzCopy 命令時，您可能會收到下列錯誤：

    The system cannot find the path specified.

如果 AzCopy 不是本機電腦上的安裝，您可以在這裡 （正在安裝在預設的位置） 從安裝： [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。


如果 AzCopy 已安裝，但會安裝在不同的預設位置的位置，您可以複製命令、 將它貼到文字檔案，並再將路徑變更至 AzCopy 實際安裝所在的位置。 例如，如果 Azcopy 位於`%ProgramFiles%`，然後您可以變更從命令的第一個部分`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`至`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`。 進行這項變更之後，複製文字檔案，然後執行命令提示字元。

> [!TIP]
> 如果 AzCopy 會安裝在位置其他然後預設安裝位置，請考慮解除安裝並再重新安裝在預設的位置。 這有助於在未來避免這個問題。