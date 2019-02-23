---
title: Office 365 中的郵件流程情報
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 系統管理員可了解與 Office 365 （也稱為擁有郵件流程智慧） 中使用連接器的郵件傳遞相關聯的錯誤碼。
ms.openlocfilehash: a679a3a50c2333a9f66509b69ec06ee96960bc83
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218713"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="6f4c2-103">Office 365 中的郵件流程情報</span><span class="sxs-lookup"><span data-stu-id="6f4c2-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="6f4c2-p101">一般而言，您可以使用連接器 Office 365 組織的電子郵件路由傳送至內部部署電子郵件環境。您可能也使用連接器來路由郵件來自 Office 365 協力廠商組織。Office 365 無法傳送連接器透過這些訊息，當他們正在排入佇列 Office 365 中。Office 365 會繼續重試每封郵件的傳遞 48 小時。48 小時之後已排入佇列的郵件將過期，及訊息將會傳回給原始寄件者的未傳遞回報 （也稱為 NDR 或彈跳訊息）。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p101">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="6f4c2-p102">Office 365 中將會產生錯誤時無法使用連接器來傳遞訊息。最常見的錯誤和其解決方案本主題所述。透過連接器傳送的郵件無法傳遞佇列和通知錯誤統稱稱為 「_郵件流程智慧_。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p102">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="6f4c2-112">錯誤代碼： 450 4.4.312 DNS 查詢失敗</span><span class="sxs-lookup"><span data-stu-id="6f4c2-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="6f4c2-p103">通常此錯誤表示 Office 365 嘗試連線至所指定的連接器，但是若要尋找失敗的智慧主機的 IP 位址的 DNS 查詢智慧主機。針對這項錯誤的可能原因如下：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p103">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed. The possible causes for this error are:</span></span>

- <span data-ttu-id="6f4c2-115">沒有問題與網域的 DNS 裝載服務 （維護您網域的代表性頁面的名稱伺服器的方）。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="6f4c2-116">您的網域已最近過期，因此無法擷取 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="6f4c2-117">最近已變更您的網域的 MX 記錄，及 Office 365 的 DNS 伺服器仍有先前快取的 DNS 網域的資訊。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="6f4c2-118">如何修正錯誤代碼 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="6f4c2-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="6f4c2-119">使用您的 DNS 裝載服務來找出並修正此問題與您的網域。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="6f4c2-120">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），請連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="6f4c2-121">錯誤代碼： 450 4.4.315 連線逾時</span><span class="sxs-lookup"><span data-stu-id="6f4c2-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="6f4c2-p104">通常這表示 Office 365 無法連線至目的地的電子郵件伺服器。錯誤詳細資料會說明問題。例如：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p104">Typically, this means Office 365 can't connect to the destination email server. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="6f4c2-125">您的內部部署電子郵件伺服器已離線。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="6f4c2-126">中有錯誤的連接器智慧主機設定，讓 Office 365 嘗試連線至了錯誤的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="6f4c2-127">如何修正錯誤代碼 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="6f4c2-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="6f4c2-p105">了解哪些案例適用於，並進行必要的修正。例如，如果郵件流程運作正確，且尚未變更連接器的設定，您需要檢查內部部署電子郵件環境如果伺服器已關閉，或者已有任何變更至您的網路基礎結構 （例如，您已變更的網際網路服務提供者，所以您現在有不同的 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p105">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="6f4c2-130">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），請連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="6f4c2-131">錯誤代碼： 450 4.4.316 拒絕連線</span><span class="sxs-lookup"><span data-stu-id="6f4c2-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="6f4c2-p106">通常此錯誤表示 Office 365 時遇到的連線錯誤它嘗試連線至目的地的電子郵件伺服器。這項錯誤的可能原因為您的防火牆會封鎖來自 Office 365 IP 位址的連線。或者，這項錯誤可能是根據設計如果您已完全移轉您的內部 Office 365 的電子郵件系統並關閉 [您的內部部署電子郵件環境。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p106">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="6f4c2-135">如何修正錯誤代碼 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="6f4c2-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="6f4c2-p107">如果您有內部部署環境中的信箱，您需要修改允許來自 TCP 連接埠 25 上的 Office 365 IP 位址的連線至內部部署電子郵件伺服器在防火牆設定。如需 Office 365 IP 位址的清單，請參閱[Office 365 Url 和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p107">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="6f4c2-p108">如果沒有多個郵件應該傳遞至內部部署環境中，按一下 [**立即修正**警示中讓 Office 365 可立即拒絕無效的收件者的郵件。這會降低超出您的組織配額無效收件者，這可能會影響正常的郵件傳遞的風險。或者，您可以使用下列指示以手動方式修正的問題：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="6f4c2-141">在[Exchange 系統管理中心 (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) Office 365 中，停用或刪除將來自 Office 365 的電子郵件傳遞至您的內部部署電子郵件環境的連接器：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="6f4c2-142">在 EAC 中，移至 [**郵件流程** \> **連接器**。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="6f4c2-143">選取 [**從**值**Office 365**的連接器和**以**值**貴組織的電子郵件伺服器**並執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="6f4c2-144">依序按一下 [**刪除**刪除連接器![移除圖示](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="6f4c2-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="6f4c2-145">依序按一下 [**編輯**停用連接線![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)及取消核取**加以開啟**。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="6f4c2-p109">變更**授權\*\*\*\*內部轉送**從您的內部電子郵件環境與相關聯的 Office 365 中公認的網域。指示，請參閱[管理公認的網域在 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428)。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p109">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="6f4c2-p110">**請注意**： 30 分鐘和一小時之間這些變更時間才會生效通常。在一個小時後確認不會再收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p110">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="6f4c2-150">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="6f4c2-151">錯誤代碼： 450 4.4.317 無法連線至遠端伺服器</span><span class="sxs-lookup"><span data-stu-id="6f4c2-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="6f4c2-p111">通常此錯誤表示 Office 365 連線至目的地的電子郵件伺服器，但伺服器回應立即錯誤為或不符合的連線需求。錯誤詳細資料會說明問題。例如：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p111">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="6f4c2-155">目的地電子郵件伺服器回應 「 無法使用服務 」 錯誤，指出伺服器無法與 Office 365 保持通訊。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="6f4c2-156">若要要求 TLS] 設定連接器，但目的地的電子郵件伺服器不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="6f4c2-157">如何修正錯誤代碼 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="6f4c2-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="6f4c2-158">確認的 TLS 設定內部部署電子郵件伺服器的憑證及連接器上的 TLS 設定。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="6f4c2-159">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="6f4c2-160">錯誤代碼： 450 4.4.318 突然關閉連線</span><span class="sxs-lookup"><span data-stu-id="6f4c2-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="6f4c2-p112">通常此錯誤表示 Office 365 通訊搭配內部部署電子郵件環境，因此已中斷連線發生問題。針對這項錯誤的可能原因如下：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p112">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped. The possible causes for this error are:</span></span>

- <span data-ttu-id="6f4c2-163">防火牆使用 SMTP 封包檢查規則，這些規則未運作正常。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="6f4c2-164">您的內部部署電子郵件伺服器未運作正常 （例如服務擱置、 當機次數或低系統資源），這會導致逾時時間伺服器並關閉 Office 365 的連線。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="6f4c2-165">有內部部署環境與 Office 365 之間的網路問題。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="6f4c2-166">如何修正錯誤代碼 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="6f4c2-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="6f4c2-167">了解哪些案例適用於，並進行必要的修正。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="6f4c2-168">如果問題由內部部署環境與 Office 365 之間的網路問題所造成，請連絡您的網路小組來排除此問題。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="6f4c2-169">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="6f4c2-170">錯誤代碼： 450 4.7.320 憑證驗證失敗</span><span class="sxs-lookup"><span data-stu-id="6f4c2-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="6f4c2-p113">通常此錯誤表示 Office 365 嘗試驗證目的地的電子郵件伺服器的憑證時遭遇到錯誤。錯誤詳細資料會說明錯誤。例如：</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p113">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server. The error details will explain the error. For example:</span></span>

- <span data-ttu-id="6f4c2-174">憑證到期</span><span class="sxs-lookup"><span data-stu-id="6f4c2-174">Certificate expired</span></span>

- <span data-ttu-id="6f4c2-175">憑證主旨不符</span><span class="sxs-lookup"><span data-stu-id="6f4c2-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="6f4c2-176">不再是有效的憑證</span><span class="sxs-lookup"><span data-stu-id="6f4c2-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="6f4c2-177">如何修正錯誤代碼 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="6f4c2-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="6f4c2-178">修正憑證或連接器上的設定以便在 Office 365 中的訊息排入佇列可以傳送。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="6f4c2-179">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="6f4c2-180">其他錯誤碼</span><span class="sxs-lookup"><span data-stu-id="6f4c2-180">Other error codes</span></span>

<span data-ttu-id="6f4c2-p114">Office 365 的郵件傳遞至您的內部發生問題或協力廠商電子郵件伺服器。使用**目的地伺服器**資訊錯誤檢查您的環境的問題或修改連接器，如果有設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-p114">Office 365 is having difficulty delivering messages to your on-premises or partner email server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="6f4c2-183">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6f4c2-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
