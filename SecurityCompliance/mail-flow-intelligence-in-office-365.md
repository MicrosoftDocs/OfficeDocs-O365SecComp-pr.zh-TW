---
title: Office 365 中的郵件流程智慧
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: '一般而言，您使用連接器來路由傳送訊息從 Office 365 組織內部的郵件環境。您可能也使用連接器來路由郵件來自 Office 365 協力廠商組織。Office 365 無法傳送連接器透過這些訊息，當他們正在排入佇列 Office 365 中。 '
ms.openlocfilehash: 495d73524afb3ab3a34fd2f1f5f4cd747481f9d8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027620"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="560eb-105">Office 365 中的郵件流程智慧</span><span class="sxs-lookup"><span data-stu-id="560eb-105">Mail flow intelligence in Office 365</span></span>
  
<span data-ttu-id="560eb-p102">一般而言，您使用連接器來路由傳送訊息從 Office 365 組織內部的郵件環境。您可能也使用連接器來路由郵件來自 Office 365 協力廠商組織。Office 365 無法傳送連接器透過這些訊息，當他們正在排入佇列 Office 365 中。Office 365 會繼續重試每封郵件的傳遞 48 小時。48 小時之後已排入佇列的郵件將過期，及訊息將會傳回給原始寄件者的未傳遞回報 （也稱為 NDR 或彈跳訊息）。</span><span class="sxs-lookup"><span data-stu-id="560eb-p102">Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>
  
<span data-ttu-id="560eb-p103">Office 365 中將會產生錯誤時無法使用連接器來傳遞訊息。最常見的錯誤和其解決方案本主題所述。透過連接器傳送的郵件無法傳遞佇列和通知錯誤統稱稱為 「 郵件流程智慧。</span><span class="sxs-lookup"><span data-stu-id="560eb-p103">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as mailflow intelligence.</span></span>
  
 <span data-ttu-id="560eb-114">**目錄**</span><span class="sxs-lookup"><span data-stu-id="560eb-114">**Contents**</span></span>
  
- [<span data-ttu-id="560eb-115">錯誤代碼： 450 4.4.312 DNS 查詢失敗</span><span class="sxs-lookup"><span data-stu-id="560eb-115">Error code: 450 4.4.312 DNS query failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [<span data-ttu-id="560eb-116">錯誤代碼： 450 4.4.315 連線逾時</span><span class="sxs-lookup"><span data-stu-id="560eb-116">Error code: 450 4.4.315 Connection timed out</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [<span data-ttu-id="560eb-117">錯誤代碼： 450 4.4.316 拒絕連線</span><span class="sxs-lookup"><span data-stu-id="560eb-117">Error code: 450 4.4.316 Connection refused</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [<span data-ttu-id="560eb-118">錯誤代碼： 450 4.4.317 無法連線至遠端伺服器</span><span class="sxs-lookup"><span data-stu-id="560eb-118">Error code: 450 4.4.317 Cannot connect to remote server</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [<span data-ttu-id="560eb-119">錯誤代碼： 450 4.4.318 突然關閉連線</span><span class="sxs-lookup"><span data-stu-id="560eb-119">Error code: 450 4.4.318 Connection was closed abruptly</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [<span data-ttu-id="560eb-120">錯誤代碼： 450 4.7.320 憑證驗證失敗</span><span class="sxs-lookup"><span data-stu-id="560eb-120">Error code: 450 4.7.320 Certificate validation failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="560eb-121">錯誤代碼： 450 4.4.312 DNS 查詢失敗</span><span class="sxs-lookup"><span data-stu-id="560eb-121">Error code: 450 4.4.312 DNS query failed</span></span>
<span data-ttu-id="560eb-122"><a name="ErrorCode44312"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-122"></span></span>

<span data-ttu-id="560eb-p104">這個錯誤通常表示 Office 365 嘗試連線至智慧主機所指定的連接器，但 DNS 查詢以尋找智慧主機的 IP 位址失敗。針對這項錯誤的可能原因如下：</span><span class="sxs-lookup"><span data-stu-id="560eb-p104">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host IP addresses failed. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="560eb-125">沒有問題與網域的 DNS 裝載服務 （維護您網域的代表性頁面的名稱伺服器的方）。</span><span class="sxs-lookup"><span data-stu-id="560eb-125">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>
    
- <span data-ttu-id="560eb-126">您的網域已最近過期，因此無法擷取 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="560eb-126">Your domain has recently expired, so the MX record can't be retrieved.</span></span>
    
- <span data-ttu-id="560eb-127">最近已變更您的網域的 MX 記錄，及 Office 365 的 DNS 伺服器仍有先前快取的 DNS 網域的資訊。</span><span class="sxs-lookup"><span data-stu-id="560eb-127">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>
    
<span data-ttu-id="560eb-128">您需要修正的 DNS 問題的處理的 DNS 裝載服務。</span><span class="sxs-lookup"><span data-stu-id="560eb-128">You need to fix the DNS issue by working with your DNS hosting service.</span></span>
  
<span data-ttu-id="560eb-129">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-129">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="560eb-130">錯誤代碼： 450 4.4.315 連線逾時</span><span class="sxs-lookup"><span data-stu-id="560eb-130">Error code: 450 4.4.315 Connection timed out</span></span>
<span data-ttu-id="560eb-131"><a name="ErrorCode44315"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-131"></span></span>

<span data-ttu-id="560eb-p105">通常這表示 Office 365 無法連線至目的地郵件伺服器。錯誤詳細資料會說明問題。例如：</span><span class="sxs-lookup"><span data-stu-id="560eb-p105">Typically, this means Office 365 can't connect to the destination messaging server. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="560eb-135">您內部部署郵件伺服器已離線。</span><span class="sxs-lookup"><span data-stu-id="560eb-135">Your on-premises messaging server is down.</span></span>
    
- <span data-ttu-id="560eb-136">中有錯誤的連接器智慧主機設定，讓 Office 365 嘗試連線至了錯誤的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="560eb-136">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>
    
<span data-ttu-id="560eb-p106">了解哪些案例適用於，並進行必要的修正。例如，如果郵件流程運作正確，且尚未變更連接器的設定，您需要檢查您的內部郵件環境如果伺服器已關閉，或者已有任何變更至您的網路基礎結構 （例如，您已變更的網際網路服務提供者，所以您現在有不同的 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="560eb-p106">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises messaging environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed Internet service providers, so you now have different IP addresses).</span></span>
  
<span data-ttu-id="560eb-139">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-139">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="560eb-140">錯誤代碼： 450 4.4.316 拒絕連線</span><span class="sxs-lookup"><span data-stu-id="560eb-140">Error code: 450 4.4.316 Connection refused</span></span>
<span data-ttu-id="560eb-141"><a name="ErrorCode44316"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-141"></span></span>

<span data-ttu-id="560eb-p107">通常此錯誤表示 Office 365 時遇到的連線錯誤它嘗試連線至目的地郵件伺服器。這項錯誤的可能原因為您的防火牆會封鎖來自 Office 365 IP 位址的連線。或這項錯誤可能是根據設計如果您已完全移轉您的內部郵件至 Office 365 系統並關閉 [您的內部郵件環境。</span><span class="sxs-lookup"><span data-stu-id="560eb-p107">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination messaging server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises messaging system to Office 365 and shut down your on-premises messaging environment..</span></span>
  
- <span data-ttu-id="560eb-p108">如果您有內部部署環境中的信箱，您需要修改您的防火牆設定以允許 TCP 連接埠 25 上的 Office 365 IP 位址從連線到您的內部通訊的伺服器。如需 Office 365 IP 位址的清單，請參閱[Office 365 Url 和 IP 位址範圍](https://go.microsoft.com/fwlink/p/?linkid=228887)。</span><span class="sxs-lookup"><span data-stu-id="560eb-p108">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises messaging servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=228887).</span></span>
    
- <span data-ttu-id="560eb-p109">如果沒有多個郵件應該傳遞至內部部署環境中，按一下 [**立即修正**警示中讓 Office 365 可立即拒絕無效的收件者的郵件。這會降低超出您的組織配額無效收件者，這可能會影響正常的郵件傳遞的風險。或者，您可以使用下列指示以手動方式修正的問題：</span><span class="sxs-lookup"><span data-stu-id="560eb-p109">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span> 
    
  - <span data-ttu-id="560eb-p110">停用或刪除來自 Office 365 的連接器至內部部署環境： Office 365 系統管理中心\>**系統中心** \> **Exchange** \> **郵件流程** \> **連接器**\>選取**從**值**Office 365**的連接器及**以**值**貴組織的電子郵件伺服器**。依序按一下 [**刪除**刪除連接器![刪除圖示](media/ITPro-EAC-DeleteIcon.png)，或按一下 [**編輯**停用連接線![編輯圖示](media/ITPro-EAC-EditIcon.png)及取消核取**加以開啟**。</span><span class="sxs-lookup"><span data-stu-id="560eb-p110">Disable or delete the connector from Office 365 to your on-premises environment: Office 365 admin center \> **Admin centers** \> **Exchange** \> **Mail flow** \> **Connectors** \> select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server**. Delete the connector by clicking **Delete**![Delete icon](media/ITPro-EAC-DeleteIcon.png), or disable the connector by clicking **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png) and unchecking **Turn it on**.</span></span>
    
  - <span data-ttu-id="560eb-p111">變更與內部具有相關聯的 Office 365 中公認的網域從**內部轉送**至**授權**的郵件環境。指示，請參閱[管理 Exchange Online 中公認的網域](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx)。</span><span class="sxs-lookup"><span data-stu-id="560eb-p111">Change the accepted domain in Office 365 that's associated with your on-premises messaging environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span></span>
    
    <span data-ttu-id="560eb-p112">**請注意**： 30 分鐘和一小時之間這些變更時間才會生效通常。在一個小時後確認不會再收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="560eb-p112">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>
    
<span data-ttu-id="560eb-156">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-156">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="560eb-157">錯誤代碼： 450 4.4.317 無法連線至遠端伺服器</span><span class="sxs-lookup"><span data-stu-id="560eb-157">Error code: 450 4.4.317 Cannot connect to remote server</span></span>
<span data-ttu-id="560eb-158"><a name="ErrorCode44317"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-158"></span></span>

<span data-ttu-id="560eb-p113">通常此錯誤表示 Office 365 連線至目的地郵件伺服器，但伺服器回應立即錯誤為或不符合的連線需求。錯誤詳細資料會說明問題。例如：</span><span class="sxs-lookup"><span data-stu-id="560eb-p113">Typically, this error means Office 365 connected to the destination messaging server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="560eb-162">目的地訊息伺服器回應 「 無法使用服務 」 錯誤，指出伺服器無法與 Office 365 保持通訊。</span><span class="sxs-lookup"><span data-stu-id="560eb-162">The destination messaging server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>
    
- <span data-ttu-id="560eb-163">若要要求 TLS] 設定連接器，但目的地郵件伺服器不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="560eb-163">The connector is configured to require TLS, but the destination messaging server doesn't support TLS.</span></span>
    
<span data-ttu-id="560eb-164">確認您內部部署的憑證的 TLS 設定訊息伺服器及連接器上的 TLS 設定。</span><span class="sxs-lookup"><span data-stu-id="560eb-164">Verify the TLS settings and certificates on your on-premises messaging servers, and the TLS settings on the connector.</span></span>
  
<span data-ttu-id="560eb-165">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-165">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="560eb-166">錯誤代碼： 450 4.4.318 突然關閉連線</span><span class="sxs-lookup"><span data-stu-id="560eb-166">Error code: 450 4.4.318 Connection was closed abruptly</span></span>
<span data-ttu-id="560eb-167"><a name="ErrorCode44318"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-167"></span></span>

<span data-ttu-id="560eb-p114">這個錯誤通常表示 Office 365 與內部通訊發生問題郵件環境，因此已中斷連線。針對這項錯誤的可能原因如下：</span><span class="sxs-lookup"><span data-stu-id="560eb-p114">Typically, this error means Office 365 is having difficulty communicating with your on-premises messaging environment, so the connection was dropped. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="560eb-170">防火牆使用 SMTP 封包檢查規則，這些規則未運作正常。</span><span class="sxs-lookup"><span data-stu-id="560eb-170">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>
    
- <span data-ttu-id="560eb-171">您內部部署郵件伺服器未運作正常 （例如服務擱置、 當機次數或低系統資源），會導致逾時時間的伺服器，並關閉 Office 365 的連線。</span><span class="sxs-lookup"><span data-stu-id="560eb-171">Your on-premises messaging server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>
    
- <span data-ttu-id="560eb-p115">有內部部署環境與 Office 365 之間的網路問題。如果問題持續發生，請連絡您的網路小組來排除此問題。</span><span class="sxs-lookup"><span data-stu-id="560eb-p115">There are network issues between your on-premises environment and Office 365. If the problem persists, contact your network team to troubleshoot the issue.</span></span>
    
<span data-ttu-id="560eb-174">了解哪些案例適用於，並進行必要的修正。</span><span class="sxs-lookup"><span data-stu-id="560eb-174">Find out which scenario applies to you, and make the necessary corrections.</span></span>
  
<span data-ttu-id="560eb-175">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-175">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="560eb-176">錯誤代碼： 450 4.7.320 憑證驗證失敗</span><span class="sxs-lookup"><span data-stu-id="560eb-176">Error code: 450 4.7.320 Certificate validation failed</span></span>
<span data-ttu-id="560eb-177"><a name="ErrorCode47320"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-177"></span></span>

<span data-ttu-id="560eb-p116">通常此錯誤表示 Office 365 嘗試驗證目的地通訊伺服器的憑證時遭遇到錯誤。錯誤詳細資料會說明錯誤。例如：</span><span class="sxs-lookup"><span data-stu-id="560eb-p116">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination messaging server. The error details will explain the error. For example:</span></span>
  
- <span data-ttu-id="560eb-181">憑證到期</span><span class="sxs-lookup"><span data-stu-id="560eb-181">Certificate expired</span></span>
    
- <span data-ttu-id="560eb-182">憑證主旨不符</span><span class="sxs-lookup"><span data-stu-id="560eb-182">Certificate subject mismatch</span></span>
    
- <span data-ttu-id="560eb-183">不再是有效的憑證</span><span class="sxs-lookup"><span data-stu-id="560eb-183">Certificate is no longer valid</span></span>
    
<span data-ttu-id="560eb-184">請在使 Office 365can 中已排入佇列的郵件傳遞修正憑證或連接器。</span><span class="sxs-lookup"><span data-stu-id="560eb-184">Please fix the certificate or the connector so that queued messages in Office 365can be delivered.</span></span>
  
<span data-ttu-id="560eb-185">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-185">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="other-error-codes"></a><span data-ttu-id="560eb-186">其他錯誤碼</span><span class="sxs-lookup"><span data-stu-id="560eb-186">Other error codes</span></span>
<span data-ttu-id="560eb-187"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="560eb-187"></span></span>

<span data-ttu-id="560eb-p117">Office 365 問題發生提供訊息給您的內部或協力廠商訊息伺服器。使用**目的地伺服器**資訊錯誤檢查您的環境的問題或修改連接器，如果有設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="560eb-p117">Office 365 is having difficulty delivering messages to your on-premises or partner messaging server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 
  
<span data-ttu-id="560eb-190">如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="560eb-190">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  

