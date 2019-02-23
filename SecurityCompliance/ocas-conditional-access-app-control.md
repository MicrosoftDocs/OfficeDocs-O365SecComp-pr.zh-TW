---
title: 使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 停止缺口和遺漏即時與 Office 365 雲端應用程式的安全性設定格式化的條件存取應用程式的控制項。
ms.openlocfilehash: 23c4b29e86eb8ba92cfa8a544d6484965ec6372b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217083"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a><span data-ttu-id="03b34-103">使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式</span><span class="sxs-lookup"><span data-stu-id="03b34-103">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>

|<span data-ttu-id="03b34-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="03b34-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="03b34-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="03b34-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="03b34-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="03b34-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="03b34-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="03b34-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="03b34-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="03b34-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="03b34-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="03b34-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="03b34-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="03b34-110">You are here!</span></span>  <br/> [<span data-ttu-id="03b34-111">後續步驟</span><span class="sxs-lookup"><span data-stu-id="03b34-111">Next step</span></span>](ocas-deploy-conditional-access-app-control.md) <br/> |[<span data-ttu-id="03b34-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="03b34-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="03b34-p101">在今天的工作場所不常足夠知道有什麼新鮮事雲端環境中的事實之後。您想要停止缺口和即時，遺漏之前員工有意或無意放入您的資料與您組織在風險。請務必讓使用者在組織中的最大的服務和工具提供給他們的雲端應用程式]，讓它們將他們自己的裝置能夠運作。同時，您需要的工具來協助保護您的組織從資料外洩和資料竊取、 即時。Azure Active Directory 與 Office 365 雲端應用程式安全性會將這些功能全面性及整合經驗中具有設定格式化的條件的 Access 應用程式控制項。</span><span class="sxs-lookup"><span data-stu-id="03b34-p101">In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact. You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Together with Azure Active Directory, Office 365 Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03b34-118">若要使用雲端應用程式的安全性設定格式化的條件存取應用程式的控制項，您需要 [Azure Active Directory P1 授權](https://azure.microsoft.com/pricing/details/active-directory/) 和使用中的[Office 365 雲端應用程式安全性](office-365-cas-overview.md)訂閱。</span><span class="sxs-lookup"><span data-stu-id="03b34-118">To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active [Office 365 Cloud App Security](office-365-cas-overview.md) subscription.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="03b34-119">運作方式</span><span class="sxs-lookup"><span data-stu-id="03b34-119">How it works</span></span>

<span data-ttu-id="03b34-p102">設定格式化的條件的 Access 應用程式控制項使用反向 proxy 架構及唯一整合 Azure AD 設定格式化的條件的存取權。Azure AD 的設定格式化的條件存取可讓您強制執行在您的組織根據特定條件的應用程式的存取控制。條件定義 *誰* （使用者群組) 與 *何種* （雲端應用程式） 和 *位置* （哪一個位置和網路） 的設定格式化的條件存取原則套用至。判斷條件之後，您可路由使用者給 Office 365 雲端應用程式安全性您可以在其中保護套用存取及工作階段控制項具有設定格式化的條件的 Access 應用程式控制項的資料。</span><span class="sxs-lookup"><span data-stu-id="03b34-p102">Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access. Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions. The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to. After you’ve determined the conditions, you can route users to Office 365 Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.</span></span>

<span data-ttu-id="03b34-p103">設定格式化的條件的 Access 應用程式控制可讓使用者應用程式存取及監視及控制存取及工作階段的原則為基礎的即時工作階段。存取及工作階段的原則可用的雲端應用程式安全性入口網站中進一步調整篩選器並設定在使用者要採取的動作。Access 與工作階段的原則，您可以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="03b34-p103">Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies. Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:</span></span>

- <span data-ttu-id="03b34-p104">**在下載區塊**： 您可以封鎖機密文件下載。例如，在未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="03b34-p104">**Block on download**: You can block the download of sensitive documents. For example, on unmanaged devices.</span></span>

- <span data-ttu-id="03b34-p105">**下載保護**： 而不是封鎖下載 （英文） 的機密文件，您可能需要透過下載加密保護的文件]。此加密可確保受保護的文件與使用者存取通過驗證如果資料下載到不受信任的裝置。</span><span class="sxs-lookup"><span data-stu-id="03b34-p105">**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download. This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device.</span></span>

- <span data-ttu-id="03b34-p106">**監視低信任層級使用者工作階段**： Risky 使用者登入應用程式和其動作會從記錄在工作階段時受監控。您可以調查並分析使用者了解，以及哪些的情況下工作階段原則應套用未來的行為。</span><span class="sxs-lookup"><span data-stu-id="03b34-p106">**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.</span></span>

- <span data-ttu-id="03b34-133">**封鎖存取**： 您可以完全封鎖使用者即將從未受管理的裝置或非公司網路的特定應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="03b34-133">**Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.</span></span>

- <span data-ttu-id="03b34-134">**建立唯讀模式**： 監視與封鎖自訂應用程式中的活動，您可建立的特定使用者的特定應用程式以唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="03b34-134">**Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.</span></span>

- <span data-ttu-id="03b34-p107">**Restrict 來自非公司網路的使用者工作階段**： 允許使用者存取的受保護的應用程式不屬於您公司的網路位置的限制] 存取權。下載 （英文） 的機密運送已封鎖或受保護。</span><span class="sxs-lookup"><span data-stu-id="03b34-p107">**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access. The download of sensitive materials is blocked or protected.</span></span>

### <a name="how-session-control-works"></a><span data-ttu-id="03b34-137">工作階段控制的運作方式</span><span class="sxs-lookup"><span data-stu-id="03b34-137">How session control works</span></span>

<span data-ttu-id="03b34-p108">建立工作階段原則與設定格式化的條件的 Access 應用程式控制項可讓您控制使用者工作階段所透過反向 proxy 而不是將使用者重新導向直接給應用程式。然後起使用者要求和回應移到 Office 365 雲端應用程式安全性而不是直接以應用程式。</span><span class="sxs-lookup"><span data-stu-id="03b34-p108">Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app. From then on, user requests and responses go through Office 365 Cloud App Security rather than directly to the app.</span></span>

<span data-ttu-id="03b34-p109">若要讓使用者在工作階段，所有相關的 Url、 Java 指令碼和應用程式工作階段中的 cookie 已取代為 Office 365 雲端應用程式安全性 Url。例如，如果應用程式會傳回具有以 myapp.com 結尾之網域的連結] 頁面上，連結會取代以類似如下的網域： myapp.com.us.cas.ms</span><span class="sxs-lookup"><span data-stu-id="03b34-p109">To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Office 365 Cloud App Security URLs. For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms</span></span>

<span data-ttu-id="03b34-p110">此方法不需要您在裝置上安裝任何項目。監視研討會未受管理裝置時理想此方法。</span><span class="sxs-lookup"><span data-stu-id="03b34-p110">This method doesn't require you to install anything on the device. This method is ideal when monitoring sessions from unmanaged devices.</span></span>

<span data-ttu-id="03b34-144">工作階段導向到 Office 365 雲端應用程式安全性之後，您可以選擇下列動作：</span><span class="sxs-lookup"><span data-stu-id="03b34-144">After a session is directed through Office 365 Cloud App Security, the following actions can be done:</span></span>

1. <span data-ttu-id="03b34-145">檢查使用者活動的流量</span><span class="sxs-lookup"><span data-stu-id="03b34-145">Inspect the traffic for user activities</span></span>

2. <span data-ttu-id="03b34-146">Office 365 雲端應用程式安全性活動記錄檔中顯示的已識別的活動</span><span class="sxs-lookup"><span data-stu-id="03b34-146">Display the identified activities in the Office 365 Cloud App Security Activity log</span></span>

3. <span data-ttu-id="03b34-147">儲存流量記錄及分析它們</span><span class="sxs-lookup"><span data-stu-id="03b34-147">Save the traffic logs and analyze them</span></span>

4. <span data-ttu-id="03b34-148">讓管理員可以將匯出的流量記錄檔</span><span class="sxs-lookup"><span data-stu-id="03b34-148">Enable the admin to export the traffic logs</span></span>

5. <span data-ttu-id="03b34-149">在工作階段強制施行原則</span><span class="sxs-lookup"><span data-stu-id="03b34-149">Enforce policies on the session</span></span>

## <a name="managed-device-identification"></a><span data-ttu-id="03b34-150">受管理的裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="03b34-150">Managed device identification</span></span>

<span data-ttu-id="03b34-p111">設定格式化的條件的 Access 應用程式控制項可讓您建立或不受管理的裝置是否必須考量事項的原則。若要識別是否或不受管理的裝置，會使用此功能：</span><span class="sxs-lookup"><span data-stu-id="03b34-p111">Conditional Access App Control enables you to create policies that take into account whether a device is managed or not. To identify whether a device is managed or not, the feature uses:</span></span>

- <span data-ttu-id="03b34-153">相容的裝置</span><span class="sxs-lookup"><span data-stu-id="03b34-153">Compliant devices</span></span>

- <span data-ttu-id="03b34-154">已加入網域的裝置</span><span class="sxs-lookup"><span data-stu-id="03b34-154">Domain-joined devices</span></span>

- <span data-ttu-id="03b34-155">用戶端憑證部署</span><span class="sxs-lookup"><span data-stu-id="03b34-155">Client certificates deployment</span></span>

### <a name="compliant-and-domain-joined-devices"></a><span data-ttu-id="03b34-156">符合且已加入網域的裝置</span><span class="sxs-lookup"><span data-stu-id="03b34-156">Compliant and domain-joined devices</span></span>

<span data-ttu-id="03b34-p112">Azure AD 的設定格式化的條件存取讓符合且已加入網域的裝置資訊直接傳遞至 Office 365 雲端應用程式安全性。如此，存取原則] 或 [工作階段原則可以被開發篩選器所使用的裝置狀態。如需詳細資訊，請參閱 [在 Azure Active Directory 中的裝置管理的簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="03b34-p112">Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Office 365 Cloud App Security. From there, an access policy or a session policy can be developed that uses device state as a filter. For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>

### <a name="client-certificate-authenticated-devices"></a><span data-ttu-id="03b34-160">用戶端憑證驗證裝置</span><span class="sxs-lookup"><span data-stu-id="03b34-160">Client-certificate authenticated devices</span></span>

<span data-ttu-id="03b34-p113">裝置識別碼機制可從相關裝置使用用戶端憑證要求驗證。您也可以使用現有的用戶端憑證已經進行了部署在您的組織或聯播 （英文） 新的用戶端憑證以受管理的裝置。然後您使用這些憑證的顯示狀態設定存取與工作階段的原則。如需如何部署用戶端憑證請參閱 [部署設定格式化的條件應用程式的存取控制 Office 365 應用程式](ocas-deploy-conditional-access-app-control.md)。</span><span class="sxs-lookup"><span data-stu-id="03b34-p113">The device identification mechanism can request authentication from relevant devices using client certificates. You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices. You then use the presence of those certificates to set access and session policies. For information on how to deploy client certificates see [Deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span></span>

## <a name="supported-apps-and-clients"></a><span data-ttu-id="03b34-165">支援的應用程式及用戶端</span><span class="sxs-lookup"><span data-stu-id="03b34-165">Supported apps and clients</span></span>

<span data-ttu-id="03b34-166">Office 365 的設定格式化的條件 Access 應用程式控制項支援下列精選應用程式：</span><span class="sxs-lookup"><span data-stu-id="03b34-166">Conditional Access App Control for Office 365 supports the following featured apps:</span></span>

- <span data-ttu-id="03b34-167">Exchange Online （預覽）</span><span class="sxs-lookup"><span data-stu-id="03b34-167">Exchange Online (preview)</span></span>

- <span data-ttu-id="03b34-168">OneDrive for Business （預覽）</span><span class="sxs-lookup"><span data-stu-id="03b34-168">OneDrive for Business (preview)</span></span>

- <span data-ttu-id="03b34-169">Power BI （預覽）</span><span class="sxs-lookup"><span data-stu-id="03b34-169">Power BI (preview)</span></span>

- <span data-ttu-id="03b34-170">SharePoint Online （預覽）</span><span class="sxs-lookup"><span data-stu-id="03b34-170">SharePoint Online (preview)</span></span>

- <span data-ttu-id="03b34-171">（預覽） 的 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="03b34-171">Microsoft Teams (preview)</span></span>

- <span data-ttu-id="03b34-172">Yammer （預覽）</span><span class="sxs-lookup"><span data-stu-id="03b34-172">Yammer (preview)</span></span>

<span data-ttu-id="03b34-173">其他應用程式均已持續在-boarded 工作階段控制。</span><span class="sxs-lookup"><span data-stu-id="03b34-173">Additional apps are being continuously on-boarded to session control.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03b34-174">後續步驟</span><span class="sxs-lookup"><span data-stu-id="03b34-174">Next steps</span></span>

- [<span data-ttu-id="03b34-175">為 Office 365 應用程式部署條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="03b34-175">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="03b34-176">深入了解 Office 365 雲端應用程式安全性的工作階段原則</span><span class="sxs-lookup"><span data-stu-id="03b34-176">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="03b34-177">深入了解 Office 365 雲端應用程式安全性存取原則</span><span class="sxs-lookup"><span data-stu-id="03b34-177">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 