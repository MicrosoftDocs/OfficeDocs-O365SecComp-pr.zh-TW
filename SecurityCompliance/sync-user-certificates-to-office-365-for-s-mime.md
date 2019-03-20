---
title: 將使用者憑證同步至 Office 365 進行 S/MIME 處理
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 在設定正確的憑證之前，任何人都無法傳送受 S/MIME 保護的郵件。為了透過 Exchange Online 傳送加密郵件，寄件者的電子郵件程式會使用收件者的公用憑證為郵件加密。這個公用的 X.509 憑證必須發行至 Office 365。
ms.openlocfilehash: 927f6b4c7a166ee35e11a8712cc99054b0e67dee
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692562"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="8184a-105">將使用者憑證同步至 Office 365 進行 S/MIME 處理</span><span class="sxs-lookup"><span data-stu-id="8184a-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="8184a-106">任何人都可以傳送受 S/MIME 保護的郵件在 Exchange Online 之前，請將適當的憑證必須設定。</span><span class="sxs-lookup"><span data-stu-id="8184a-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="8184a-107">若要傳送加密的郵件，透過 Exchange Online，寄件者的電子郵件應用程式會使用收件者的公用憑證來加密郵件。</span><span class="sxs-lookup"><span data-stu-id="8184a-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="8184a-108">這個公用的 X.509 憑證必須發行至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8184a-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="8184a-109">同步處理支援 S/MIME 的憑證</span><span class="sxs-lookup"><span data-stu-id="8184a-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="8184a-110">設定 S/MIME 的首要步驟，是在您的本機 Active Directory 網域服務中核發憑證並加以發行。</span><span class="sxs-lookup"><span data-stu-id="8184a-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="8184a-111">如需管理 Exchange Server 中的憑證的詳細資訊，請參閱[Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8184a-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="8184a-112">您的憑證發行後，使用 Azure Active Directory 同步處理工具來同步處理至 Office 365 的使用者資料從您的內部部署 Exchange 環境。</span><span class="sxs-lookup"><span data-stu-id="8184a-112">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="8184a-113">如需有關此程序的詳細資訊，請參閱[DirSync： 目錄同步處理工具版本的版本歷程記錄](https://go.microsoft.com/fwlink/p/?LinkId=392587)。</span><span class="sxs-lookup"><span data-stu-id="8184a-113">For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="8184a-114">以及其他目錄資料，針對 S/MIME 用途同步處理工具會同步處理每個使用者物件的**userCertificate**和**userSMIMECertificate**屬性，讓資料可用來簽署及加密郵件。</span><span class="sxs-lookup"><span data-stu-id="8184a-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="8184a-115">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8184a-115">More Information</span></span>

[<span data-ttu-id="8184a-116">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="8184a-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="8184a-117">Azure Active Directory 同步處理工具</span><span class="sxs-lookup"><span data-stu-id="8184a-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
