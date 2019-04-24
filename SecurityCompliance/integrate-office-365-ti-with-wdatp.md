---
title: 整合 Office 365 進階的威脅防護與 Windows Defender 進階威脅防護
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
description: 整合 Windows Defender 進階威脅防護來威脅管理的詳細的資訊請參閱 < Office 365 進階威脅防護。
ms.openlocfilehash: 832b9c6bc600366e1ed6b7c6e60442bec8b5002c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254420"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="cd495-103">整合 Office 365 進階的威脅防護與 Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="cd495-103">Integrate Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="cd495-104">如果您是貴組織的安全性小組的一部分，您可以使用 Windows Defender 進階威脅防護整合 Office 365 進階威脅防護和回應功能相關的調查。</span><span class="sxs-lookup"><span data-stu-id="cd495-104">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and related investigation and response features with Windows Defender Advanced Threat Protection.</span></span> <span data-ttu-id="cd495-105">這可協助您快速了解您正在調查 Office 365 中的威脅時是否使用者的電腦是否處於風險。</span><span class="sxs-lookup"><span data-stu-id="cd495-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="cd495-106">例如，一旦啟用整合，您將能夠查看機器所使用的郵件收件者偵測到的電子郵件，以及如何在 Windows Defender 進階威脅防護中的許多最近的通知這些機器有。</span><span class="sxs-lookup"><span data-stu-id="cd495-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="cd495-107">下圖顯示 [**裝置**] 索引標籤，您會看到已啟用 Windows Defender 進階威脅防護整合的時機：</span><span class="sxs-lookup"><span data-stu-id="cd495-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![啟用 Windows Defender ATP 時，您可以看到機器警示的清單。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="cd495-109">在這個範例中，您可以看到電子郵件的收件者有四種裝置，以及其他有警示。</span><span class="sxs-lookup"><span data-stu-id="cd495-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="cd495-110">Windows Defender 進階威脅防護入口網站中，按一下 [裝置] 連結開啟其頁面。</span><span class="sxs-lookup"><span data-stu-id="cd495-110">Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cd495-111">需求</span><span class="sxs-lookup"><span data-stu-id="cd495-111">Requirements</span></span>

- <span data-ttu-id="cd495-112">您的組織必須擁有 Office 365 進階的威脅防護方案 2 （或 Office 365 E5） 以及 Windows Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="cd495-112">Your organization must have Office 365 Advanced Threat Protection Plan 2 (or Office 365 E5) and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="cd495-113">您必須是 Office 365 全域管理員或具有安全性系統管理員角色 （例如安全性管理員） 中指派[安全性&amp;合規性中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="cd495-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="cd495-114">(請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="cd495-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="cd495-115">您必須具有安全性 & 合規性中心中的 Office 365 威脅總管和 Windows Defender 進階威脅防護入口網站存取權。</span><span class="sxs-lookup"><span data-stu-id="cd495-115">You must have access to both Office 365 Threat Explorer in the Security & Compliance Center and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a><span data-ttu-id="cd495-116">將 Windows Defender ATP 與整合 Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="cd495-116">To integrate Office 365 Advanced Threat Protection with Windows Defender ATP</span></span>

<span data-ttu-id="cd495-117">整合 Office 365 進階威脅防護與 Windows Defender 進階威脅防護會設定使用這兩種安全性 & 合規性中心與 Windows Defender 進階威脅防護入口網站。</span><span class="sxs-lookup"><span data-stu-id="cd495-117">Integrating Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection is set up by using both the Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="cd495-118">為 Office 365 全域系統管理員或安全性系統管理員，請移至[https://protection.office.com](https://protection.office.com)並以 Office 365 您公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="cd495-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="cd495-119">選擇 [**威脅管理** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="cd495-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="cd495-120">![威脅管理] 功能表中的 explorer](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="cd495-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="cd495-121">在螢幕的右上角，選擇 [ **WDATP 設定**。</span><span class="sxs-lookup"><span data-stu-id="cd495-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="cd495-122">在 [Windows Defender ATP 連線] 對話方塊中，開啟連線到 Windows ATP。</span><span class="sxs-lookup"><span data-stu-id="cd495-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Windows Defender ATP 連線](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="cd495-124">啟用 Windows Defender 進階威脅防護中的連線。</span><span class="sxs-lookup"><span data-stu-id="cd495-124">Enable the connection in Windows Defender Advanced Threat Protection.</span></span> <span data-ttu-id="cd495-125">請參閱[使用 Windows Defender 進階威脅防護入口網站](https://go.microsoft.com/fwlink/?linkid=859690)。</span><span class="sxs-lookup"><span data-stu-id="cd495-125">See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="cd495-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="cd495-126">Related topics</span></span>

[<span data-ttu-id="cd495-127">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="cd495-127">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="cd495-128">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="cd495-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

