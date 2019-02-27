---
title: 設定虛擬憑證集合在 Exchange Online 驗證 S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 系統管理員可以了解如何建立用以驗證 S/MIME 憑證 in Exchange Online 的虛擬憑證集合。
ms.openlocfilehash: 2aa6e529f5ca374af6fe6d80a403058a8b6e468a
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296946"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="24a80-103">設定虛擬憑證集合在 Exchange Online 驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="24a80-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="24a80-p101">系統管理員，您將需要設定 Exchange Online 中用以驗證 S/MIME 憑證的虛擬憑證集合。這個虛擬憑證集合設定成 SST filename 副檔名憑證存放區。SST 檔案包含的所有根和中級驗證 S/MIME 憑證時所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="24a80-p101">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="24a80-107">建立及儲存 SST</span><span class="sxs-lookup"><span data-stu-id="24a80-107">Create and save an SST</span></span>

<span data-ttu-id="24a80-p102">您可以建立此 SST 憑證存放區檔案匯出憑證從信任的電腦使用 Windows PowerShell 中的 [**匯出憑證**指令程式並指定_Type_值為 SST。指示，請參閱[匯出憑證](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。</span><span class="sxs-lookup"><span data-stu-id="24a80-p102">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST. For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="24a80-p103">一旦您有 SST 憑證存放區檔案，使用下列語法在 Exchange Online PowerShell 中的 Exchange Online 的虛擬憑證存放區儲存 SST 檔案內容。若要連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="24a80-p103">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store. To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="24a80-112">本範例會匯入 SST 檔案 C:\My Documents\Exported 憑證 Store.sst。</span><span class="sxs-lookup"><span data-stu-id="24a80-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="24a80-113">如需詳細的語法及參數資訊，請參閱[Set-smimeconfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="24a80-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="24a80-114">確保憑證的有效性</span><span class="sxs-lookup"><span data-stu-id="24a80-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="24a80-115">在 Exchange Online 中，只有 SST 用於憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="24a80-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="24a80-116">相關資訊</span><span class="sxs-lookup"><span data-stu-id="24a80-116">More Information</span></span>

[<span data-ttu-id="24a80-117">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="24a80-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="24a80-118">Get-smimeconfig</span><span class="sxs-lookup"><span data-stu-id="24a80-118">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
