---
title: 設定虛擬憑證集合以驗證 S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s 承租人管理員必須設定用以驗證 S/MIME 憑證的虛擬憑證集合。
ms.openlocfilehash: 0e8226ca35e872cd8c7da16ba353bf8b99a6954d
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091055"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a><span data-ttu-id="7869d-103">設定虛擬憑證集合以驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="7869d-103">Set up virtual certificate collection to validate S/MIME</span></span>

<span data-ttu-id="7869d-p101">如果您是租用戶系統管理員，您將必須設定用來驗證 S/MIME 憑證的虛擬憑證集合。此虛擬憑證集合會設定為具有 SST 副檔名的憑證存放區檔案類型。此 SST 檔案中包含所有在驗證 S/MIME 憑證時所將使用的根憑證和中繼憑證。</span><span class="sxs-lookup"><span data-stu-id="7869d-p101">As a tenant administrator you will need to configure a virtual certificate collection that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store file type with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>
  
## <a name="create-and-save-an-sst"></a><span data-ttu-id="7869d-107">建立及儲存 SST</span><span class="sxs-lookup"><span data-stu-id="7869d-107">Create and save an SST</span></span>
<span data-ttu-id="7869d-108"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7869d-108"></span></span>

<span data-ttu-id="7869d-p102">您僅可使用命令介面執行此程序。若要了解如何在內部部署 Exchange 組織中開啟 Exchange 管理命令介面，請參閱**開啟命令介面**。若要了解如何使用 Windows PowerShell 連線至 Exchange Online，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="7869d-p102">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
<span data-ttu-id="7869d-p103">如果您是系統管理員，則可以使用  `Export-Certificate` 指令程式並將類型指定為 SST，從信任的機器匯出憑證，以建立此 SST 檔案。如需  `Export-Certificate` 指令程式的相關資訊，請參閱 [Export-Certificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) 參考主題。</span><span class="sxs-lookup"><span data-stu-id="7869d-p103">As an administrator, you can create this SST file by exporting the certificates from a trusted machine using the  `Export-Certificate` cmdlet and specifying the type as SST. For more information the  `Export-Certificate` cmdlet, see the [Export-Certificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) reference topic.</span></span> 
  
<span data-ttu-id="7869d-p104">SST 檔案產生後，請使用  `Set-Smimeconfig` 指令程式與  _-SMIMECertificateIssuingCA_ 參數，將其儲存在虛擬憑證存放區中。例如：  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span><span class="sxs-lookup"><span data-stu-id="7869d-p104">Once the SST file is generated, use the  `Set-Smimeconfig` cmdlet to save it in the virtual certificate store by using the  _-SMIMECertificateIssuingCA_ parameter. For example:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span></span>
  
## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="7869d-116">確保憑證的有效性</span><span class="sxs-lookup"><span data-stu-id="7869d-116">Ensuring a certificate is valid</span></span>
<span data-ttu-id="7869d-117"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7869d-117"></span></span>

<span data-ttu-id="7869d-p105">Exchange 2013 SP1 首先會檢查 SST 檔案，然後再驗證憑證。如果驗證失敗，它會查看本機電腦憑證存放區，以驗證憑證。這是 Exchange 2013 SP1 的新行為，與舊版的 Exchange 不同。在 Exchange Online 中，驗證時將只會使用 SST。</span><span class="sxs-lookup"><span data-stu-id="7869d-p105">Exchange 2013 SP1 first checks for the SST file and validates the certificate. If the validation fails, it will look at the local machine certificate store to validate the certificate. This behavior is new for Exchange 2013 SP1 and different from prior versions of Exchange. In Exchange Online only the SST will be used for validation.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="7869d-122">相關資訊</span><span class="sxs-lookup"><span data-stu-id="7869d-122">More Information</span></span>
<span data-ttu-id="7869d-123"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7869d-123"></span></span>

[<span data-ttu-id="7869d-124">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="7869d-124">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="7869d-125">Get-smimeconfig</span><span class="sxs-lookup"><span data-stu-id="7869d-125">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  

