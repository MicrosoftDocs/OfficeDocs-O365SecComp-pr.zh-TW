---
title: Office 365 中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: 使用 Office 365，您的內容加密靜態及在傳輸，使用最強加密、 通訊協定，以及可用的技術。在 Office 365 中取得加密的概觀。
ms.openlocfilehash: 7099609ca142f6ed094ccafc95aab48059a1aa36
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357504"
---
# <a name="encryption-in-office-365"></a><span data-ttu-id="1988d-104">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="1988d-104">Encryption in Office 365</span></span>

<span data-ttu-id="1988d-p102">加密是檔案保護和資訊保護策略中重要的一部分。閱讀本篇文章以取得用於所有版本的 Office 365 加密的概觀，並從您的組織的密碼保護的 Office 文件的加密設定取得加密工作的說明。</span><span class="sxs-lookup"><span data-stu-id="1988d-p102">Encryption is an important part of your file protection and information protection strategies. Read this article to get an overview of encryption used for all versions of Office 365, and get help with encryption tasks, from setting up encryption for your organization to password-protecting Office documents.</span></span>
  
- <span data-ttu-id="1988d-107">如果您正在尋找憑證和技術，例如 TLS 的相關資訊，請參閱[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="1988d-107">If you're looking for information about certificates and technologies like TLS, see [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).</span></span>

- <span data-ttu-id="1988d-108">如果您要尋找有關如何設定或組織的加密設定的資訊，請參閱 <<c0>設定 Office 365 企業版中的加密。</span><span class="sxs-lookup"><span data-stu-id="1988d-108">If you are looking for information about how to configure or set up encryption for your organization, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).</span></span>

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a><span data-ttu-id="1988d-109">什麼是加密，以及它如何運作的 Office 365？</span><span class="sxs-lookup"><span data-stu-id="1988d-109">What is encryption, and how does it work in Office 365?</span></span>

<span data-ttu-id="1988d-p103">在高的層級，加密是編碼 （稱為純文字） 資料的程序到亦無法使用的人員或電腦中，除非和直到解密加密文字。解密需要授權的使用者擁有的加密金鑰。加密有助於確保只有授權的收件者才能解密內容，例如電子郵件和檔案。</span><span class="sxs-lookup"><span data-stu-id="1988d-p103">At a high level, encryption is the process of encoding your data (referred to as plaintext) into ciphertext that cannot be used by people or computers unless and until the ciphertext is decrypted. Decryption requires an encryption key that only authorized users have. Encryption helps ensure that only authorized recipients can decrypt your content, such as email messages and files.</span></span>
  
<span data-ttu-id="1988d-p104">加密本身無法防止內容，例如檔案、 電子郵件、 行事曆項目，等等，進入一面。加密是您的組織更大的資訊保護策略的一部分。藉由使用加密，您可以協助確保只應該能夠使用加密的資料的人都能夠。</span><span class="sxs-lookup"><span data-stu-id="1988d-p104">Encryption by itself does not prevent content, such as files, email messages, calendar entries, and so on, from getting into the wrong hands. Encryption is part of a larger information protection strategy for your organization. By using encryption, you can help ensure that only those who should be able to use encrypted data are able to.</span></span>
  
<span data-ttu-id="1988d-p105">您可以在同一時間，就地有多層的加密。例如，您可以將加密的電子郵件也經過流向您的電子郵件的通訊通道。您的資料與 Office 365 加密靜態及在傳輸，使用多個強式的加密通訊協定和技術，包括傳輸層安全性/安全通訊端階層 (TLS/SSL)、 網際網路通訊協定安全性 (IPSec)，以及進階加密標準 (AES)。</span><span class="sxs-lookup"><span data-stu-id="1988d-p105">You can have multiple layers of encryption in place at the same time. For example, you can encrypt email messages and also the communication channels through which your email flows. With Office 365, your data is encrypted at rest and in transit, using several strong encryption protocols, and technologies that include Transport Layer Security/Secure Sockets Layer (TLS/SSL), Internet Protocol Security (IPSec), and Advanced Encryption Standard (AES).</span></span>
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a><span data-ttu-id="1988d-119">靜態資料和傳輸中的資料加密</span><span class="sxs-lookup"><span data-stu-id="1988d-119">Encryption for data at rest and data in transit</span></span>

 <span data-ttu-id="1988d-120">**靜態資料的範例**包括已上傳至 SharePoint 文件庫、 Project Online 資料、 skype for Business 會議、 電子郵件訊息和附件儲存在您的 Office 365 中的資料夾中已上載的文件的檔案信箱，並上傳到商務用 OneDrive 檔案。</span><span class="sxs-lookup"><span data-stu-id="1988d-120">**Examples of data at rest** include files that have been uploaded to a SharePoint library, Project Online data, documents that have been uploaded in a Skype for Business meeting, email messages and attachments that are stored in folders in your Office 365 mailbox, and files uploaded to OneDrive for Business.</span></span> 
  
 <span data-ttu-id="1988d-p106">**傳輸中資料的範例**包括正在正在傳遞的郵件會發生在線上會議中的交談。在 Office 365 中，資料是在傳輸途中每當使用者的裝置與 Office 365 伺服器通訊，或 Office 365 伺服器通訊與另一部伺服器時。</span><span class="sxs-lookup"><span data-stu-id="1988d-p106">**Examples of data in transit** include mail messages that are in the process of being delivered, or conversations that are taking place in an online meeting. In Office 365, data is in transit whenever a user's device is communicating with an Office 365 server, or when an Office 365 server is communicating with another server.</span></span> 
  
<span data-ttu-id="1988d-p107">使用 Office 365，您可以有多個圖層與幾種類型的加密來保護您的資料一起運作。下表包含一些範例，與其他資訊連結。</span><span class="sxs-lookup"><span data-stu-id="1988d-p107">With Office 365, you can have multiple layers and kinds of encryption working together to secure your data. The following table includes some examples, with links to additional information.</span></span>
  
|<span data-ttu-id="1988d-125">**種類的內容**</span><span class="sxs-lookup"><span data-stu-id="1988d-125">**Kinds of Content**</span></span>|<span data-ttu-id="1988d-126">**加密技術**</span><span class="sxs-lookup"><span data-stu-id="1988d-126">**Encryption Technologies**</span></span>|<span data-ttu-id="1988d-127">**若要了解更多的資源**</span><span class="sxs-lookup"><span data-stu-id="1988d-127">**Resources to learn more**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1988d-p108">在裝置上的檔案。這可以包含的資料夾，儲存在電腦、 平板電腦或手機上的 Office 文件或資料儲存至 Microsoft 雲端中儲存的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="1988d-p108">Files on a device. This can include email messages saved in a folder, Office documents saved on a computer, tablet, or phone, or data saved to the Microsoft cloud.</span></span>  <br/> |<span data-ttu-id="1988d-p109">在 Microsoft 資料中心中的 BitLocker。BitLocker 也可用於用戶端機器，例如 Windows 電腦和平板電腦</span><span class="sxs-lookup"><span data-stu-id="1988d-p109">BitLocker in Microsoft datacenters. BitLocker can also be used on client machines, such as Windows computers and tablets</span></span>  <br/> <span data-ttu-id="1988d-132">在 Microsoft 資料中心中的分散式金鑰管理員 (DKM)</span><span class="sxs-lookup"><span data-stu-id="1988d-132">Distributed Key Manager (DKM) in Microsoft datacenters</span></span>  <br/> <span data-ttu-id="1988d-133">Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="1988d-133">Customer Key for Office 365</span></span>  <br/> |[<span data-ttu-id="1988d-134">Windows IT 中心： BitLocker</span><span class="sxs-lookup"><span data-stu-id="1988d-134">Windows IT Center: BitLocker</span></span>](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [<span data-ttu-id="1988d-135">Microsoft 信任中心： 加密</span><span class="sxs-lookup"><span data-stu-id="1988d-135">Microsoft Trust Center: Encryption</span></span>](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [<span data-ttu-id="1988d-136">雲端安全性控制系列： 靜態加密資料</span><span class="sxs-lookup"><span data-stu-id="1988d-136">Cloud security controls series: Encrypting Data at Rest</span></span>](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [<span data-ttu-id="1988d-137">Exchange Online 如何保護您的電子郵件機密資料</span><span class="sxs-lookup"><span data-stu-id="1988d-137">How Exchange Online secures your email secrets</span></span>](exchange-online-secures-email-secrets.md) <br/> [<span data-ttu-id="1988d-138">使用客戶金鑰控制 Office 365 中的資料</span><span class="sxs-lookup"><span data-stu-id="1988d-138">Controlling your data in Office 365 using Customer Key</span></span>](controlling-your-data-using-customer-key.md) <br/> |
|<span data-ttu-id="1988d-p110">在使用者間傳輸的檔案。這可以包含 Office 文件或使用者之間共用的 SharePoint 清單項目。</span><span class="sxs-lookup"><span data-stu-id="1988d-p110">Files in transit between users. This can include Office documents or SharePoint list items shared between users.</span></span>  <br/> |<span data-ttu-id="1988d-141">TLS 傳輸中的檔案</span><span class="sxs-lookup"><span data-stu-id="1988d-141">TLS for files in transit</span></span>  <br/> |<span data-ttu-id="1988d-142">[商務用 OneDrive 和 SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="1988d-142">[Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md)</span></span> <br/> [<span data-ttu-id="1988d-143">線上商務用 Skype： 安全性和封存</span><span class="sxs-lookup"><span data-stu-id="1988d-143">Skype for Business Online: Security and Archiving</span></span>](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|<span data-ttu-id="1988d-p111">收件者之間傳送的電子郵件。這包括 Exchange online 託管的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1988d-p111">Email in transit between recipients. This includes email hosted by Exchange Online.</span></span>  <br/> |<span data-ttu-id="1988d-146">Azure 版權管理、 S/MIME 與 TLS 傳輸中的電子郵件的 office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="1988d-146">Office 365 Message Encryption with Azure Rights Management, S/MIME, and TLS for email in transit</span></span>  <br/> |[<span data-ttu-id="1988d-147">Office 365 郵件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="1988d-147">Office 365 Message Encryption (OME)</span></span>](ome.md) <br/> [<span data-ttu-id="1988d-148">Office 365 中的電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="1988d-148">Email encryption in Office 365</span></span>](email-encryption.md) <br/> [<span data-ttu-id="1988d-149">Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線</span><span class="sxs-lookup"><span data-stu-id="1988d-149">How Exchange Online uses TLS to secure email connections in Office 365</span></span>](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a><span data-ttu-id="1988d-150">如果我需要更多控制加密以符合安全性與合規性需求？</span><span class="sxs-lookup"><span data-stu-id="1988d-150">What if I need more control over encryption to meet security and compliance requirements?</span></span>

<span data-ttu-id="1988d-p112">Microsoft 受管理的磁碟區加密、 檔案加密，以及 Office 365 中的信箱加密解決方案，除了客戶管理選項可用來符合更嚴格的安全性與合規性需求。這類解決方案會使用與 Office 365 的 Azure 版權管理 (Azure RMS)。</span><span class="sxs-lookup"><span data-stu-id="1988d-p112">In addition to Microsoft-managed solutions of volume encryption, file encryption, and mailbox encryption in Office 365, customer-managed options can be used to meet more stringent security and compliance requirements. Such solutions use Azure Rights Management (Azure RMS) together with Office 365.</span></span>
  
<span data-ttu-id="1988d-153">請參閱若要了解更多的下列資源：</span><span class="sxs-lookup"><span data-stu-id="1988d-153">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="1988d-154">什麼是 Azure 版權管理？</span><span class="sxs-lookup"><span data-stu-id="1988d-154">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [<span data-ttu-id="1988d-155">在 Office 365 系統管理中心啟動版權管理</span><span class="sxs-lookup"><span data-stu-id="1988d-155">Activate Rights Management in the Office 365 admin center</span></span>](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [<span data-ttu-id="1988d-156">Set up Information Rights Management (IRM) in SharePoint admin center</span><span class="sxs-lookup"><span data-stu-id="1988d-156">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>](set-up-irm-in-sp-admin-center.md)

## <a name="how-do-i"></a><span data-ttu-id="1988d-157">我要如何...]</span><span class="sxs-lookup"><span data-stu-id="1988d-157">How do I...</span></span>

|<span data-ttu-id="1988d-158">**若要此工作**</span><span class="sxs-lookup"><span data-stu-id="1988d-158">**To do this task**</span></span>|<span data-ttu-id="1988d-159">**請參閱這些資源**</span><span class="sxs-lookup"><span data-stu-id="1988d-159">**See these resources**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1988d-160">設定我的組織的加密</span><span class="sxs-lookup"><span data-stu-id="1988d-160">Set up encryption for my organization</span></span>  <br/> |[<span data-ttu-id="1988d-161">設定 Office 365 企業版中的加密</span><span class="sxs-lookup"><span data-stu-id="1988d-161">Set up encryption in Office 365 Enterprise</span></span>](set-up-encryption.md) <br/> |
|<span data-ttu-id="1988d-162">在 Office 365 中檢視詳細資料的憑證、 技術及 TLS 加密套件</span><span class="sxs-lookup"><span data-stu-id="1988d-162">View details about certificates, technologies, and TLS cipher suites in Office 365</span></span>  <br/> |[<span data-ttu-id="1988d-163">關於 Office 365 中加密的技術詳細資料</span><span class="sxs-lookup"><span data-stu-id="1988d-163">Technical details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md) <br/> |
|<span data-ttu-id="1988d-164">使用行動裝置上的已加密郵件</span><span class="sxs-lookup"><span data-stu-id="1988d-164">Work with encrypted messages on a mobile device</span></span>  <br/> |[<span data-ttu-id="1988d-165">在 Android 裝置上檢視加密的郵件</span><span class="sxs-lookup"><span data-stu-id="1988d-165">View encrypted messages on your Android device</span></span>](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [<span data-ttu-id="1988d-166">在 iPhone 或 iPad 上檢視加密的郵件</span><span class="sxs-lookup"><span data-stu-id="1988d-166">View encrypted messages on your iPhone or iPad</span></span>](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|<span data-ttu-id="1988d-167">加密文件使用密碼保護</span><span class="sxs-lookup"><span data-stu-id="1988d-167">Encrypt a document using password protection</span></span>  <br/><br/>  <span data-ttu-id="1988d-p113">目前，在 Office Online 中不支援密碼保護。使用桌上型版本的 Word、 Excel 及 PowerPoint 的密碼保護。</span><span class="sxs-lookup"><span data-stu-id="1988d-p113">Currently, password protection is not supported in Office Online. Use desktop versions of Word, Excel, and PowerPoint for password protection.</span></span>           |<span data-ttu-id="1988d-170">[文件、 活頁簿或簡報中新增或移除保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（選擇 [**新增保護**] 區段中，並再查看 [**以密碼加密]** ）</span><span class="sxs-lookup"><span data-stu-id="1988d-170">[Add or remove protection in your document, workbook, or presentation](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Choose an **Add protection** section, and then see **Encrypt with Password** )</span></span>  <br/> |
|<span data-ttu-id="1988d-171">移除文件的加密</span><span class="sxs-lookup"><span data-stu-id="1988d-171">Remove encryption from a document</span></span>  <br/> |<span data-ttu-id="1988d-172">[文件、 活頁簿或簡報中新增或移除保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（選擇**移除保護**] 區段中，並再查看 [**移除密碼加密**）</span><span class="sxs-lookup"><span data-stu-id="1988d-172">[Add or remove protection in your document, workbook, or presentation](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Choose a **Remove protection** section, and then see **Remove password encryption** )</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="1988d-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="1988d-173">Related topics</span></span>

[<span data-ttu-id="1988d-174">規劃 Office 365 安全性和資訊保護功能</span><span class="sxs-lookup"><span data-stu-id="1988d-174">Plan for Office 365 security and information protection capabilities</span></span>](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[<span data-ttu-id="1988d-175">安全性與合規性 Office 365 商務版-系統管理說明</span><span class="sxs-lookup"><span data-stu-id="1988d-175">Security and Compliance in Office 365 for business - Admin Help</span></span>](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

