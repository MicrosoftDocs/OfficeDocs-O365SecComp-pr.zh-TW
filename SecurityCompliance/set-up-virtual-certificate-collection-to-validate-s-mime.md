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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>設定虛擬憑證集合在 Exchange Online 以驗證 S/MIME

身為系統管理員，您必須在 Exchange Online 中，將會用來驗證 S/MIME 憑證設定虛擬憑證集合。 此虛擬憑證集合設定為具有 SST 副檔名的憑證存放區。 此 SST 檔案中包含所有在驗證 S/MIME 憑證時所將使用的根憑證和中繼憑證。

## <a name="create-and-save-an-sst"></a>建立及儲存 SST

您可以建立此 SST 憑證存放區檔案匯出之憑證從信任的機器**匯出憑證**指令程式使用 Windows PowerShell 中和_Type_值指定為 SST。 如需相關指示，請參閱[匯出憑證](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。

SST 憑證存放區檔案之後，請在 Exchange Online PowerShell 中使用下列語法，SST 檔案內容儲存在 Exchange Online 的虛擬憑證存放區。 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

此範例會匯入此 SST 檔案 C:\My Documents\Exported 憑證 Store.sst。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

如需詳細的語法及參數資訊，請參閱 < <b0>Set-smimeconfig</b0>。

## <a name="ensuring-a-certificate-is-valid"></a>確保憑證的有效性

在 Exchange Online 中，只有 SST 用於憑證驗證。

## <a name="more-information"></a>詳細資訊

[可用於訊息簽署和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
