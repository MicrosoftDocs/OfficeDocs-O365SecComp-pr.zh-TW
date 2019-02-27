---
title: 將使用者憑證同步至 Office 365 進行 S/MIME 處理
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 在設定正確的憑證之前，任何人都無法傳送受 S/MIME 保護的郵件。為了透過 Exchange Online 傳送加密郵件，寄件者的電子郵件程式會使用收件者的公用憑證為郵件加密。這個公用的 X.509 憑證必須發行至 Office 365。
ms.openlocfilehash: 35de3ba34be48a8553c7034f646576e4fca8b870
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30294996"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="2e394-105">將使用者憑證同步至 Office 365 進行 S/MIME 處理</span><span class="sxs-lookup"><span data-stu-id="2e394-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="2e394-p102">任何人都可以在 Exchange Online 中傳送 S/MIME 受保護的訊息之前，將適當的憑證必須設定。若要傳送加密的郵件通過 Exchange Online、 寄件者的電子郵件應用程式會使用加密郵件收件者的公用憑證。此公用的 X.509 憑證具有要發佈至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2e394-p102">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up. To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message. This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="2e394-109">同步處理支援 S/MIME 的憑證</span><span class="sxs-lookup"><span data-stu-id="2e394-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="2e394-p103">開始設定來使用 S/MIME 發出憑證並將其發佈您的本機 Active Directory 網域服務中。如需管理 Exchange Server 中的憑證的詳細資訊，請參閱[Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2e394-p103">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service. For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="2e394-p104">發佈憑證之後，請使用 Azure Active Directory 同步作業工具來同步處理至 Office 365 的使用者資料從內部部署 Exchange 環境。如需有關此程序的詳細資訊，請參閱[DirSync： 目錄同步作業工具版本版本歷程記錄](https://go.microsoft.com/fwlink/p/?LinkId=392587)。</span><span class="sxs-lookup"><span data-stu-id="2e394-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="2e394-114">搭配同步處理 S/MIME 用途的其他目錄資料工具會同步處理每個使用者物件的**userCertificate**和**userSMIMECertificate**屬性讓資料可用來簽署和加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="2e394-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="2e394-115">相關資訊</span><span class="sxs-lookup"><span data-stu-id="2e394-115">More Information</span></span>

[<span data-ttu-id="2e394-116">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="2e394-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="2e394-117">Azure Active Directory 同步處理工具</span><span class="sxs-lookup"><span data-stu-id="2e394-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
