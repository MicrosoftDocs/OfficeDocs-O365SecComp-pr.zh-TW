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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241072"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a><span data-ttu-id="e7012-102">疑難排解 AzCopy 在進階電子文件 （預覽）</span><span class="sxs-lookup"><span data-stu-id="e7012-102">Troubleshoot AzCopy in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="e7012-103">在使用者介面時載入非 Office 365 的資料或錯誤修復進階電子文件 （預覽） 中的文件，提供包含參數與您要上傳檔案儲存位置和 Azure 位置 Azure AzCopy 命令將上傳檔案到的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="e7012-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery (Preview), the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="e7012-104">若要上傳您的文件，您複製此命令，然後再執行命令提示字元處的它在本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="e7012-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="e7012-105">下列螢幕擷取畫面顯示 AzCopy 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="e7012-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![將非 Office 365 檔案上傳](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="e7012-107">在大部分情況下，當您執行時，將運作所提供的命令。</span><span class="sxs-lookup"><span data-stu-id="e7012-107">In most cases, the command that's provided will work when you run it.</span></span> <span data-ttu-id="e7012-108">不過，有可能的情況下時顯示的命令不會成功執行。</span><span class="sxs-lookup"><span data-stu-id="e7012-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="e7012-109">以下是一些可能的原因。</span><span class="sxs-lookup"><span data-stu-id="e7012-109">Here's a few possible reasons.</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="e7012-110">AzCopy 未安裝在本機電腦或未安裝在預設位置</span><span class="sxs-lookup"><span data-stu-id="e7012-110">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="e7012-111">如果未安裝 AzCopy 或會安裝在位置以外預設安裝位置 (也就是`%ProgramFiles(x86)%`)，當您執行 AzCopy 命令時，您可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="e7012-111">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="e7012-112">如果 AzCopy 不是本機電腦上的安裝，您可以在這裡 （正在安裝在預設的位置） 從安裝： [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="e7012-112">If AzCopy isn't install on the local computer, you can install from here (being sure to install it in the default location): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>


<span data-ttu-id="e7012-113">如果 AzCopy 已安裝，但會安裝在不同的預設位置的位置，您可以複製命令、 將它貼到文字檔案，並再將路徑變更至 AzCopy 實際安裝所在的位置。</span><span class="sxs-lookup"><span data-stu-id="e7012-113">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is actually installed.</span></span> <span data-ttu-id="e7012-114">例如，如果 Azcopy 位於`%ProgramFiles%`，然後您可以變更從命令的第一個部分`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`至`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`。</span><span class="sxs-lookup"><span data-stu-id="e7012-114">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="e7012-115">進行這項變更之後，複製文字檔案，然後執行命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="e7012-115">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="e7012-116">如果 AzCopy 會安裝在位置其他然後預設安裝位置，請考慮解除安裝並再重新安裝在預設的位置。</span><span class="sxs-lookup"><span data-stu-id="e7012-116">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="e7012-117">這有助於在未來避免這個問題。</span><span class="sxs-lookup"><span data-stu-id="e7012-117">This will help prevent this issue in the future.</span></span>