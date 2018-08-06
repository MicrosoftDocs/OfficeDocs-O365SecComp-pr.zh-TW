---
title: 設定 Outlook Web App 的 S/MIME 設定
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
description: 為 Exchange 2013 和 Exchange Online 的組織管理員，您可以設定 Outlook Web App 允許傳送與接收 S/MIME 受保護的郵件。使用 SMIMEConfig 指令程式來管理此功能透過 Exchange 管理命令介面介面進行存取。
ms.openlocfilehash: d351129c7e12a66b530e0e4f82107728fd8387ae
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027130"
---
# <a name="configure-smime-settings-for-outlook-web-app"></a><span data-ttu-id="4e6b1-104">設定 Outlook Web App 的 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="4e6b1-104">Configure S/MIME settings for Outlook Web App</span></span>

<span data-ttu-id="4e6b1-p102">身為 Exchange 2013 與 Exchange Online 的組織系統管理員，您可以設定 Outlook Web App 以便傳送和接收受 S/MIME 保護的郵件。使用  `SMIMEConfig` Cmdlet，以透過 Exchange 管理命令介面來管理這項功能。</span><span class="sxs-lookup"><span data-stu-id="4e6b1-p102">As an organization administrator for both Exchange 2013 and Exchange Online, you can set up Outlook Web App to allow sending and receiving S/MIME-protected messages. Use the  `SMIMEConfig` cmdlet to manage this feature through the Exchange Management Shell interface.</span></span> 
  
<span data-ttu-id="4e6b1-107">如需相關資訊 (例如  `get-SMIMEConfig` 和  `set-SMIMEConfig` 的參數和範例詳細說明)，請參閱 [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) 和 [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) 文件。</span><span class="sxs-lookup"><span data-stu-id="4e6b1-107">For more information such as a detailed description of parameters and examples for  `get-SMIMEConfig` and  `set-SMIMEConfig`, see the [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) documentation.</span></span> 
  
<span data-ttu-id="4e6b1-p103">您僅可使用命令介面執行此程序。若要了解如何在內部部署 Exchange 組織中開啟 Exchange 管理命令介面，請參閱**開啟命令介面**。若要了解如何使用 Windows PowerShell 連線至 Exchange Online，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="4e6b1-p103">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="4e6b1-111">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4e6b1-111">For more information</span></span>

[<span data-ttu-id="4e6b1-112">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="4e6b1-112">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  

