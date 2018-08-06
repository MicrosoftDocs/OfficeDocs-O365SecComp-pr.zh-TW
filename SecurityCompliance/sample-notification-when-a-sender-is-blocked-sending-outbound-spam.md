---
title: 當封鎖寄件者時傳送輸出垃圾郵件的範例通知
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
description: 當封鎖寄件者時從因為傳送輸出垃圾郵件服務時，網域系統會指定當您設定輸出垃圾郵件原則將會收到類似下列的通知電子郵件：
ms.openlocfilehash: c9954d3ea16582a66185d574bcb5fc8a1aeebbf9
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027460"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="3b134-103">當封鎖寄件者時傳送輸出垃圾郵件的範例通知</span><span class="sxs-lookup"><span data-stu-id="3b134-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="3b134-104">當從因為傳送輸出服務封鎖寄件者時垃圾郵件]，指定當您[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)將會收到類似下列的通知電子郵件網域系統：</span><span class="sxs-lookup"><span data-stu-id="3b134-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="3b134-105">**寄件者地址：** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3b134-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="3b134-106">**Subject:** 輸出垃圾郵件通知- \<*帳戶名稱*\>禁止傳送輸出郵件    </span><span class="sxs-lookup"><span data-stu-id="3b134-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="3b134-107">**本文：** 這是從 Exchange Online Protection 垃圾郵件分析系統自動的回覆。</span><span class="sxs-lookup"><span data-stu-id="3b134-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="3b134-p101">因為我們已偵測到大量電子郵件標示為垃圾郵件或其他可疑的行為，源自組織您所要連絡。下列的電子郵件帳戶被封鎖從傳送電子郵件 （他們仍然可以收到電子郵件）：</span><span class="sxs-lookup"><span data-stu-id="3b134-p101">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization. The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="3b134-110">\<*帳戶名稱*  \></span><span class="sxs-lookup"><span data-stu-id="3b134-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="3b134-p102">很有可能已遭洩露此電子郵件帳戶。請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3b134-p102">It is likely that this email account has been compromised. Please follow these steps:</span></span>
  
1. <span data-ttu-id="3b134-113">解決在您藉由這個問題：</span><span class="sxs-lookup"><span data-stu-id="3b134-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="3b134-114">變更帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="3b134-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="3b134-115">決定危害之帳戶的方式。</span><span class="sxs-lookup"><span data-stu-id="3b134-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="3b134-116">若要確保不會在一次利用此弱點的預防措施。</span><span class="sxs-lookup"><span data-stu-id="3b134-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="3b134-117">確認所有的違規郵件已清除 [外寄郵件佇列。</span><span class="sxs-lookup"><span data-stu-id="3b134-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="3b134-118">連絡 Microsoft 支援人員使用一般的連絡人通道。</span><span class="sxs-lookup"><span data-stu-id="3b134-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="3b134-119">說明您必須以禁止傳送郵件的使用者及已應付問題。</span><span class="sxs-lookup"><span data-stu-id="3b134-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="3b134-120">代理程式會建立支援票證您提供和呈報它的電子郵件地址或解除封鎖的網域資訊。</span><span class="sxs-lookup"><span data-stu-id="3b134-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="3b134-121">地址已解除封鎖後, 擱置的任何其他問題，您將會是連絡和解除封鎖收到通知。</span><span class="sxs-lookup"><span data-stu-id="3b134-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="3b134-122">感謝您協助我們在控制的垃圾電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3b134-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="3b134-123">Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="3b134-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="3b134-124">\*\*請注意-請勿回覆這封電子郵件出就會從不受監控的地址\*\*</span><span class="sxs-lookup"><span data-stu-id="3b134-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="3b134-125">您也可以連絡支援透過[說明](eop/help-and-support-for-eop.md)及支援 EOP 所記載的選項。</span><span class="sxs-lookup"><span data-stu-id="3b134-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  

