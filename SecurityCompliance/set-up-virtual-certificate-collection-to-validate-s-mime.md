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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>設定虛擬憑證集合在 Exchange Online 驗證 S/MIME

系統管理員，您將需要設定 Exchange Online 中用以驗證 S/MIME 憑證的虛擬憑證集合。這個虛擬憑證集合設定成 SST filename 副檔名憑證存放區。SST 檔案包含的所有根和中級驗證 S/MIME 憑證時所使用的憑證。

## <a name="create-and-save-an-sst"></a>建立及儲存 SST

您可以建立此 SST 憑證存放區檔案匯出憑證從信任的電腦使用 Windows PowerShell 中的 [**匯出憑證**指令程式並指定_Type_值為 SST。指示，請參閱[匯出憑證](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。

一旦您有 SST 憑證存放區檔案，使用下列語法在 Exchange Online PowerShell 中的 Exchange Online 的虛擬憑證存放區儲存 SST 檔案內容。若要連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

本範例會匯入 SST 檔案 C:\My Documents\Exported 憑證 Store.sst。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

如需詳細的語法及參數資訊，請參閱[Set-smimeconfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)。

## <a name="ensuring-a-certificate-is-valid"></a>確保憑證的有效性

在 Exchange Online 中，只有 SST 用於憑證驗證。

## <a name="more-information"></a>相關資訊

[可用於訊息簽署和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
