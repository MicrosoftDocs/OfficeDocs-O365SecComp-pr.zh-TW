---
title: Exchange Online 中的 outlook 網頁版設定 S/MIME 設定
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online 系統管理員應該如何檢視及設定 Exchange Online 中網頁型 Outlook 中的 S/MIME 設定簡短描述。
ms.openlocfilehash: 2be1d7599d65601671504b7d6caf03e915f10fff
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153855"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Exchange Online 中的 outlook 網頁版設定 S/MIME 設定

Exchange online 的系統管理員，您可以設定以允許傳送及接收 S/MIME 保護的郵件 （先前稱為 Outlook Web App） 網頁型 Outlook。 使用**Get-smimeconfig**和**Set-smimeconfig**指令程式來檢視及管理此功能在 Exchange Online PowerShell。 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

如需詳細的語法及參數資訊，請參閱[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[Set-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。

## <a name="considerations-for-chrome"></a>Chrome 的考量

若要使用 S/MIME Google Chrome 網頁瀏覽器中網頁型 Outlook 中，您 （或另一個系統管理員） 必須設定，然後設定名為**ExtensionInstallForcelist**在 Chrome 中安裝 Microsoft S/MIME 分機 Chromium 原則。 原則值是`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。 並請注意，將套用此原則需要加入網域的電腦，因此有效率地在 Chrome 中使用 S/MIME 需要加入網域的電腦。

如需關於<b0>ExtensionInstallForcelist</b0>原則的詳細資訊，請參閱 < <b1>ExtensionInstallForcelist</b1>。

此步驟是使用 Chrome; 的先決條件它不會取代由使用者安裝 S/MIME 控制項。 下載並安裝 S/MIME 控制項網頁型 Outlook 中 S/MIME 其第一次使用時，系統會提示使用者。 或者，使用者可以主動移至其 Outlook 設定上的 web 若要下載連結，取得控制項中的**S/MIME** 。

## <a name="for-more-information"></a>如需詳細資訊

[可用於訊息簽署和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)
