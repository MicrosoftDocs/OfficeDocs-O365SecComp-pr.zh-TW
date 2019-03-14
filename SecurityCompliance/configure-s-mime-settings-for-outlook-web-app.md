---
title: Exchange Online 中的 outlook 網頁版設定 S/MIME 設定
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
description: Exchange Online 系統管理員應該如何檢視及設定 Exchange Online 中網頁型 Outlook 中的 S/MIME 設定簡短描述。
ms.openlocfilehash: 005c3075ec8fe6255231ba7358e5b4cc22b92f1d
ms.sourcegitcommit: 8b36bf7949f1769f1418d740293637d60e403f87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30339441"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="94ba4-103">Exchange Online 中的 outlook 網頁版設定 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="94ba4-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="94ba4-104">Exchange online 的系統管理員，您可以設定以允許傳送及接收 S/MIME 保護的郵件 （先前稱為 Outlook Web App） 網頁型 Outlook。</span><span class="sxs-lookup"><span data-stu-id="94ba4-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="94ba4-105">使用**Get-smimeconfig**和**Set-smimeconfig**指令程式來檢視及管理此功能在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="94ba4-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="94ba4-106">若要連接至 Exchange Online PowerShell，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="94ba4-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="94ba4-107">如需詳細的語法及參數資訊，請參閱[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[Set-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="94ba4-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="94ba4-108">Chrome 的考量</span><span class="sxs-lookup"><span data-stu-id="94ba4-108">Considerations for Chrome</span></span>

<span data-ttu-id="94ba4-109">若要使用 S/MIME Google Chrome 網頁瀏覽器中網頁型 Outlook 中，您 （或另一個系統管理員） 必須設定，然後設定名為**ExtensionInstallForcelist**在 Chrome 中安裝 Microsoft S/MIME 分機 Chromium 原則。</span><span class="sxs-lookup"><span data-stu-id="94ba4-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="94ba4-110">原則應使用語法： `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` ，例如： `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。</span><span class="sxs-lookup"><span data-stu-id="94ba4-110">The policy should use the syntax: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` For example: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="94ba4-111">並請注意，將套用此原則需要加入網域的電腦，因此有效率地在 Chrome 中使用 S/MIME 需要加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="94ba4-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="94ba4-112">此步驟是使用 Chrome; 的先決條件它不會取代由使用者安裝 S/MIME 控制項。</span><span class="sxs-lookup"><span data-stu-id="94ba4-112">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="94ba4-113">如需關於<b0>ExtensionInstallForcelist</b0>原則的詳細資訊，請參閱 < <b1>ExtensionInstallForcelist</b1>。</span><span class="sxs-lookup"><span data-stu-id="94ba4-113">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="94ba4-114">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="94ba4-114">For more information</span></span>

[<span data-ttu-id="94ba4-115">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="94ba4-115">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
