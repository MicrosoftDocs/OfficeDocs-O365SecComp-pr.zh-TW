---
title: 整合 Office 365 威脅情報與 Windows Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: 整合 Office 365 進階威脅保護與 Windows 防禦者進階威脅保護查看 threat management 的詳細的資訊。
ms.openlocfilehash: 48e879c1d41b5aa662f5128e234be91eb8225e7b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014765"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="59b48-103">整合 Office 365 威脅情報與 Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="59b48-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="59b48-p101">如果您組織的安全性小組的一部分，可以整合 Office 365 與 Windows 防禦者進階威脅保護 (ATP)。這可協助您快速了解當您正在調查 Office 365 中的潛在威脅是否使用者的機器是否在風險。例如，啟用整合後，您將能夠如何許多最近提醒那些傳真機具有 Windows 防禦者 ATP 中也會看見機器偵測到的電子郵件之郵件的收件者所使用的清單。</span><span class="sxs-lookup"><span data-stu-id="59b48-p101">If you are part of your organization's security team, you can integrate Office 365 with Windows Defender Advanced Threat Protection (ATP). This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender ATP.</span></span>
  
<span data-ttu-id="59b48-107">下圖顯示 [**裝置**] 索引標籤您會看見時有啟用 Windows 防禦者 ATP 整合：</span><span class="sxs-lookup"><span data-stu-id="59b48-107">The following image shows the **Devices** tab that you'll see when have Windows Defender ATP integration enabled:</span></span> 
  
![啟用 Windows 防禦者 ATP 時，您可以看到機器提醒的清單。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="59b48-p102">在這個範例中，您可以看到電子郵件之收件者有四部機器和一個具有 Windows 防禦者 ATP 通知。按一下機器連結會開啟 [電腦] 頁面上的 Windows 防禦者 ATP 新的索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="59b48-p102">In this example, you can see that the recipients of the email message have four machines and one has an alert in Windows Defender ATP. Clicking the link to a machine opens the machine page in Windows Defender ATP in a new tab.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="59b48-111">需求</span><span class="sxs-lookup"><span data-stu-id="59b48-111">Requirements</span></span>

- <span data-ttu-id="59b48-112">您的組織必須具有 Office 365 威脅智慧及 Windows 防禦者 ATP。</span><span class="sxs-lookup"><span data-stu-id="59b48-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="59b48-p103">您必須是 Office 365 全域管理員或已指派中的安全性管理員角色[安全性&amp;規範中心](https://protection.office.com)。(請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="59b48-p103">You must be an Office 365 global administrator or have a security administrator role assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="59b48-115">您必須具有 Office 365 威脅智慧及 Windows 防禦者 ATP 入口網站存取權。</span><span class="sxs-lookup"><span data-stu-id="59b48-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender ATP portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="59b48-116">整合 Windows 防禦者 ATP Office 365 威脅智慧</span><span class="sxs-lookup"><span data-stu-id="59b48-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="59b48-117">整合 Office 365 威脅智慧與 Windows 防禦者 ATP 已設定在 Office 365 和 Windows 防禦者 ATP 入口網站中。</span><span class="sxs-lookup"><span data-stu-id="59b48-117">Integrating Office 365 Threat Intelligence with Windows Defender ATP is set up both in Office 365 and in the Windows Defender ATP portal.</span></span>
  
1. <span data-ttu-id="59b48-118">為 Office 365 全域或安全性管理員，請移至[https://protection.office.com](https://protection.office.com)和登入 Office 365 您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="59b48-118">As an Office 365 global or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="59b48-119">選擇 [ **Threat management** \> **威脅瀏覽器**。</span><span class="sxs-lookup"><span data-stu-id="59b48-119">Choose **Threat management** \> **Threat explorer**.</span></span>
    
3. <span data-ttu-id="59b48-120">按一下 [**更多**] 功能表選擇**WDATP 設定**。</span><span class="sxs-lookup"><span data-stu-id="59b48-120">On the **More** menu, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="59b48-121">選取 [**連線至 Windows ATP**。</span><span class="sxs-lookup"><span data-stu-id="59b48-121">Select **Connect to Windows ATP**.</span></span>
    
<span data-ttu-id="59b48-p104">您已變更 Office 365 中的設定之後，您必須啟用 Windows 防禦者 ATP 的連線。若要這樣做，請參閱 ＜ [Use Windows 防禦者進階威脅保護入口網站](https://go.microsoft.com/fwlink/?linkid=859690)。</span><span class="sxs-lookup"><span data-stu-id="59b48-p104">After you have changed the settings in Office 365, you must enable the connection from Windows Defender ATP. To do that, see [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="59b48-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="59b48-124">Related topics</span></span>

[<span data-ttu-id="59b48-125">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="59b48-125">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="59b48-126">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="59b48-126">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

