---
title: 在 Exchange Online 中 outlook web 上的 S/MIME 設定
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online 管理員必須執行檢視和 Exchange Online 中 web 上的 Outlook 中設定 S/MIME 簡短描述。
ms.openlocfilehash: 74d2f37f0cabc0b49abdd78d2a10928b543fd615
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295356"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="f5df6-103">在 Exchange Online 中 outlook web 上的 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="f5df6-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="f5df6-p101">身為 Exchange online 管理員，您可以設定 Outlook （前身為 Outlook Web App） 在 web 上允許傳送與接收 S/MIME 受保護的郵件。使用**Get-smimeconfig**和**Set-smimeconfig**指令程式來檢視及管理此功能在 Exchange Online PowerShell。若要連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="f5df6-p101">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages. Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell. To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="f5df6-107">如需詳細的語法及參數資訊，請參閱[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[Set-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f5df6-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="f5df6-108">Chrome 的考量</span><span class="sxs-lookup"><span data-stu-id="f5df6-108">Considerations for Chrome</span></span>

<span data-ttu-id="f5df6-p102">若要使用 S/MIME Google Chrome 網頁瀏覽器中網頁上的 Outlook 中，您 （或另一個系統管理員） 必須設定及設定名為**ExtensionInstallForcelist** Chrome 中安裝 Microsoft S/MIME 延伸 Chromium 原則。原則應該使用下列的語法：`<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`例如： `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。此步驟會使用 Chrome; 的先決條件它不會取代會安裝在使用者的 S/MIME 控制項。如需有關**ExtensionInstallForcelist**原則的詳細資訊，請參閱[ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="f5df6-p102">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome. The policy should use the syntax: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` For example: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users. For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f5df6-113">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f5df6-113">For more information</span></span>

[<span data-ttu-id="f5df6-114">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="f5df6-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
