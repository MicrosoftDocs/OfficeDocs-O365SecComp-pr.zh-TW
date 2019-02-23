---
title: 整合 Office 365 威脅情報與 Windows Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 整合 Office 365 進階威脅保護與 Windows 防禦者進階威脅保護查看 threat management 的詳細的資訊。
ms.openlocfilehash: 892d04152d6029c48a52d37c6235d45a8ba67b81
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222812"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="04383-103">整合 Office 365 威脅情報與 Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="04383-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="04383-p101">如果您組織的安全性小組的一部分，您可以使用 Windows 防禦者進階威脅保護整合 Office 365 進階威脅保護和威脅智慧功能。這可協助您快速了解當您正在調查 Office 365 中的潛在威脅是否使用者的機器是否在風險。例如，啟用整合後，您將能夠許多最近提醒那些傳真機有 Windows 防禦者進階威脅 Protection 中的方式，以及查看機器偵測到的電子郵件之郵件的收件者所使用的清單。</span><span class="sxs-lookup"><span data-stu-id="04383-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="04383-107">下圖顯示 [**裝置**] 索引標籤您會看見時有啟用 Windows 防禦者進階威脅保護整合：</span><span class="sxs-lookup"><span data-stu-id="04383-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![啟用 Windows 防禦者 ATP 時，您可以看到機器提醒的清單。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="04383-p102">在這個範例中，您可以看到電子郵件之收件者有四種裝置和一個具有通知。按一下 [裝置] 連結 Windows 防禦者進階威脅保護入口網站中開啟其頁面。</span><span class="sxs-lookup"><span data-stu-id="04383-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="04383-111">需求</span><span class="sxs-lookup"><span data-stu-id="04383-111">Requirements</span></span>

- <span data-ttu-id="04383-112">您的組織必須具有 Office 365 威脅智慧及 Windows 防禦者 ATP。</span><span class="sxs-lookup"><span data-stu-id="04383-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="04383-p103">您必須是 Office 365 全域管理員或已指派中的安全性管理員角色 （例如安全性管理員）[安全性&amp;規範中心](https://protection.office.com)。(請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="04383-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="04383-115">您必須具有 Office 365 威脅智慧及 Windows 防禦者進階威脅保護入口網站存取權。</span><span class="sxs-lookup"><span data-stu-id="04383-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="04383-116">整合 Windows 防禦者 ATP Office 365 威脅智慧</span><span class="sxs-lookup"><span data-stu-id="04383-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="04383-117">整合 Office 365 威脅智慧與 Windows 防禦者進階威脅保護會設定使用這兩種 Office 365 安全性 & 規範中心和 Windows 防禦者進階威脅保護入口網站。</span><span class="sxs-lookup"><span data-stu-id="04383-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="04383-118">為 Office 365 全域管理員或安全性管理員，請移至[https://protection.office.com](https://protection.office.com)和登入 Office 365 您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="04383-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="04383-119">選擇 [ **Threat management** \> **瀏覽器**。</span><span class="sxs-lookup"><span data-stu-id="04383-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="04383-120">![Threat Management] 功能表中的瀏覽器](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="04383-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="04383-121">在螢幕右上角選擇**WDATP 設定**。</span><span class="sxs-lookup"><span data-stu-id="04383-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="04383-122">在 [Windows 防禦者 ATP 連線] 對話方塊中，開啟連接到 Windows ATP。</span><span class="sxs-lookup"><span data-stu-id="04383-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Windows 防禦者 ATP 連線](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="04383-p104">啟用 Windows 防禦者進階威脅 Protection 中的連線。請參閱 ＜ [Use Windows 防禦者進階威脅保護入口網站](https://go.microsoft.com/fwlink/?linkid=859690)。</span><span class="sxs-lookup"><span data-stu-id="04383-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="04383-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="04383-126">Related topics</span></span>

[<span data-ttu-id="04383-127">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="04383-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="04383-128">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="04383-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

