---
title: Exchange Online 如何保護您的電子郵件機密資料
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: Office 365 信任中心提供 Office 365 的安全性、 隱私與規範資訊，以及可能會想要知道 Office 365 如何協助保護您提供其資料中心中的機密資料。我們使用稱為分散式金鑰管理員 (DKM) 的技術。
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527277"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="68b6f-104">Exchange Online 如何保護您的電子郵件機密資料</span><span class="sxs-lookup"><span data-stu-id="68b6f-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="68b6f-105">本文說明 Microsoft 如何在其資料中心保護您的電子郵件機密資料。</span><span class="sxs-lookup"><span data-stu-id="68b6f-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="68b6f-106">我們如何保護您所提供的機密資料資訊？</span><span class="sxs-lookup"><span data-stu-id="68b6f-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="68b6f-p102">Office 365 信任中心提供[安全性、 隱私與 Office 365 規範資訊](https://go.microsoft.com/fwlink/?linkid=874644)，以及可能會想要知道 Office 365 如何協助保護您提供其資料中心中的機密資料。我們使用稱為分散式金鑰管理員 (DKM) 的技術。</span><span class="sxs-lookup"><span data-stu-id="68b6f-p102">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters. We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="68b6f-p103">分散式金鑰管理員 (DKM) 是用戶端功能，使用一組秘密金鑰來加密及解密功能。只有在 Active Directory 網域服務中特定安全性群組的成員可以存取這些金鑰以解密 DKM 加密的資料。在 Exchange Online 中，只有 Exchange 處理程序執行的特定服務帳戶屬於該安全性群組。在資料中心的標準作業程序的一部分，是不會將屬於此安全性群組的認證給予任何使用者，因此沒有人具有可以解密這些機密資料之金鑰的存取權。</span><span class="sxs-lookup"><span data-stu-id="68b6f-p103">Distributed Key Manager (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information. Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM. In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group. As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="68b6f-p104">對於偵錯、疑難排解或稽核目的，資料中心系統管理員必須要求較高的權限以取得屬於安全性群組的暫時認證。此程序需要多個層級的法律核准。如果授與存取權時，所有活動會記錄和稽核。此外，存取權只會授與一段時間，在那之後自動到期。</span><span class="sxs-lookup"><span data-stu-id="68b6f-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="68b6f-p105">對於額外保護，DKM 技術包含自動化金鑰變換和封存。這也確保您可以繼續存取舊的內容，而不需無限期地使用相同的金鑰。
</span><span class="sxs-lookup"><span data-stu-id="68b6f-p105">For extra protection, DKM technology includes automated key rollover and archiving. This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="68b6f-119">Exchange Online 在哪些地方使用 DKM？</span><span class="sxs-lookup"><span data-stu-id="68b6f-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="68b6f-p106">Microsoft 會使用 DKM 加密您的 Exchange Online 資料中心的機密資料。例如：</span><span class="sxs-lookup"><span data-stu-id="68b6f-p106">Microsoft uses DKM to encrypt your secrets in Exchange Online datacenters. For example:</span></span>
  
- <span data-ttu-id="68b6f-p107">連線帳戶的電子郵件帳戶認證。連線的帳戶是協力廠商帳戶，例如 Hotmail、Gmail 和 Yahoo! 郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="68b6f-p107">Email account credentials for connected accounts. Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo! mail accounts.</span></span>
    
- <span data-ttu-id="68b6f-p108">版權管理服務 (RMS) 根機碼。這些是客戶機碼的其中一個匯入從 Azure RMS 或客戶的內部部署 Active Directory 網域服務 RMS 部署所用的加密與解密電子郵件與 RMS 或 Office 365 郵件加密 (OME)。</span><span class="sxs-lookup"><span data-stu-id="68b6f-p108">Rights Management service (RMS) root keys. These are customer keys that are either imported from Azure RMS or from customer's on-premises Active Directory Domain Services RMS deployments that are used for encrypting and decrypting emails with RMS or Office 365 Message Encryption (OME).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="68b6f-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="68b6f-127">Related topics</span></span>

[<span data-ttu-id="68b6f-128">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="68b6f-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="68b6f-129">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="68b6f-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="68b6f-130">服務 Office 365 安全性保證&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="68b6f-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

