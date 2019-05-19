---
title: 設定虛擬憑證集合在 Exchange Online 以驗證 S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 系統管理員可以了解如何建立虛擬憑證集合會用來驗證 Exchange Online 中的 S/MIME 憑證。
ms.openlocfilehash: 5af332a6daf745ff6bc1334d9bb2b9d3dcb259be
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158315"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="12b54-103">設定虛擬憑證集合在 Exchange Online 以驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="12b54-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="12b54-104">身為系統管理員，您必須在 Exchange Online 中，將會用來驗證 S/MIME 憑證設定虛擬憑證集合。</span><span class="sxs-lookup"><span data-stu-id="12b54-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="12b54-105">此虛擬憑證集合設定為具有 SST 副檔名的憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="12b54-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="12b54-106">此 SST 檔案中包含所有在驗證 S/MIME 憑證時所將使用的根憑證和中繼憑證。</span><span class="sxs-lookup"><span data-stu-id="12b54-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="12b54-107">建立及儲存 SST</span><span class="sxs-lookup"><span data-stu-id="12b54-107">Create and save an SST</span></span>

<span data-ttu-id="12b54-108">您可以建立此 SST 憑證存放區檔案匯出之憑證從信任的機器**匯出憑證**指令程式使用 Windows PowerShell 中和_Type_值指定為 SST。</span><span class="sxs-lookup"><span data-stu-id="12b54-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="12b54-109">如需相關指示，請參閱[匯出憑證](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。</span><span class="sxs-lookup"><span data-stu-id="12b54-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="12b54-110">SST 憑證存放區檔案之後，請在 Exchange Online PowerShell 中使用下列語法，SST 檔案內容儲存在 Exchange Online 的虛擬憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="12b54-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="12b54-111">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="12b54-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="12b54-112">此範例會匯入此 SST 檔案 C:\My Documents\Exported 憑證 Store.sst。</span><span class="sxs-lookup"><span data-stu-id="12b54-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="12b54-113">如需詳細的語法及參數資訊，請參閱 < <b0>Set-smimeconfig</b0>。</span><span class="sxs-lookup"><span data-stu-id="12b54-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="12b54-114">確保憑證的有效性</span><span class="sxs-lookup"><span data-stu-id="12b54-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="12b54-115">在 Exchange Online 中，只有 SST 用於憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="12b54-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="12b54-116">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="12b54-116">More Information</span></span>

[<span data-ttu-id="12b54-117">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="12b54-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="12b54-118">Get-smimeconfig</span><span class="sxs-lookup"><span data-stu-id="12b54-118">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
