---
title: 當寄件者被封鎖無法傳送輸出垃圾郵件的範例通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 當服務，因為傳送輸出垃圾郵件，會封鎖寄件者時，網域系統管理員會指定當您設定輸出垃圾郵件原則將會收到類似下列的通知電子郵件：
ms.openlocfilehash: 04d8bde8e9cadd3525191a5bee7d368229e85056
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260971"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="86e82-103">當寄件者被封鎖無法傳送輸出垃圾郵件的範例通知</span><span class="sxs-lookup"><span data-stu-id="86e82-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="86e82-104">當寄件者封鎖從服務，因為傳送輸出垃圾郵件，指定當您[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)將會收到類似下列的通知電子郵件的網域系統管理員：</span><span class="sxs-lookup"><span data-stu-id="86e82-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="86e82-105">**寄件者地址：** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="86e82-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="86e82-106">**Subject:** 輸出垃圾郵件通知- \<*帳戶名稱*\>封鎖而無法傳送輸出郵件    </span><span class="sxs-lookup"><span data-stu-id="86e82-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="86e82-107">**內文：** 這是從 Exchange Online Protection 垃圾郵件分析系統自動的回覆。</span><span class="sxs-lookup"><span data-stu-id="86e82-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="86e82-108">因為我們已偵測到大量電子郵件標示為垃圾郵件或其他可疑的行為，來自您的組織，您是正在連絡。</span><span class="sxs-lookup"><span data-stu-id="86e82-108">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization.</span></span> <span data-ttu-id="86e82-109">下列的電子郵件帳戶被封鎖無法傳送電子郵件 （他們仍然可以收到電子郵件）：</span><span class="sxs-lookup"><span data-stu-id="86e82-109">The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="86e82-110">\<*帳戶名稱*  \></span><span class="sxs-lookup"><span data-stu-id="86e82-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="86e82-111">很可能此電子郵件帳戶已遭洩露。</span><span class="sxs-lookup"><span data-stu-id="86e82-111">It is likely that this email account has been compromised.</span></span> <span data-ttu-id="86e82-112">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="86e82-112">Please follow these steps:</span></span>
  
1. <span data-ttu-id="86e82-113">解決由您一邊此問題：</span><span class="sxs-lookup"><span data-stu-id="86e82-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="86e82-114">變更帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="86e82-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="86e82-115">決定如何帳戶遭到盜用了。</span><span class="sxs-lookup"><span data-stu-id="86e82-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="86e82-116">採取預防措施以確保不會在一次利用此弱點。</span><span class="sxs-lookup"><span data-stu-id="86e82-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="86e82-117">確認所有違規郵件已清除 [外寄郵件佇列。</span><span class="sxs-lookup"><span data-stu-id="86e82-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="86e82-118">使用一般連絡人管道連絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="86e82-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="86e82-119">說明您必須封鎖而無法傳送郵件的使用者，以及已處理的問題。</span><span class="sxs-lookup"><span data-stu-id="86e82-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="86e82-120">代理程式會使用您提供的資訊，提升其電子郵件地址或解除封鎖的網域建立支援票證。</span><span class="sxs-lookup"><span data-stu-id="86e82-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="86e82-121">地址已解除鎖定的狀態之後和擱置的任何其他問題，您將連接並發出警示，解除封鎖。</span><span class="sxs-lookup"><span data-stu-id="86e82-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="86e82-122">感謝您協助我們中控制垃圾電子郵件。</span><span class="sxs-lookup"><span data-stu-id="86e82-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="86e82-123">Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="86e82-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="86e82-124">\*\*請注意-請不要回應這封電子郵件時傳送來自不受監控的地址\*\*</span><span class="sxs-lookup"><span data-stu-id="86e82-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="86e82-125">您也可以連絡支援透過記載在[說明及支援 eop](eop/help-and-support-for-eop.md)的選項。</span><span class="sxs-lookup"><span data-stu-id="86e82-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  

