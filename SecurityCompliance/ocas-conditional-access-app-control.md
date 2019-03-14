---
title: 使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 停止外洩和即時與 Office 365 雲端 App 安全性條件式存取應用程式控制項的外洩。
ms.openlocfilehash: d8370b1e02866db8f92ab7f6a46b06ddc3ed1055
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312100"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a><span data-ttu-id="de5a1-103">使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式</span><span class="sxs-lookup"><span data-stu-id="de5a1-103">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>

|<span data-ttu-id="de5a1-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="de5a1-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="de5a1-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="de5a1-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="de5a1-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="de5a1-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="de5a1-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="de5a1-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="de5a1-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="de5a1-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="de5a1-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="de5a1-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="de5a1-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="de5a1-110">You are here!</span></span>  <br/> [<span data-ttu-id="de5a1-111">下一步</span><span class="sxs-lookup"><span data-stu-id="de5a1-111">Next step</span></span>](ocas-deploy-conditional-access-app-control.md) <br/> |[<span data-ttu-id="de5a1-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="de5a1-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="de5a1-113">在現今的工作場所，它是通常不不足，無法知道發生了什麼雲端環境中的事實之後。</span><span class="sxs-lookup"><span data-stu-id="de5a1-113">In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact.</span></span> <span data-ttu-id="de5a1-114">您要停止外洩和外的洩即時，員工是刻意或出自放之前您的資料和貴組織的風險。</span><span class="sxs-lookup"><span data-stu-id="de5a1-114">You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk.</span></span> <span data-ttu-id="de5a1-115">請務必讓雲端應用程式中進行大部分的工具與服務提供給他們，並讓他們將自己的裝置能夠在您的組織中使用者。</span><span class="sxs-lookup"><span data-stu-id="de5a1-115">It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work.</span></span> <span data-ttu-id="de5a1-116">在此同時，您需要工具，以協助保護組織免於資料外洩，以及資料遭竊，即時。</span><span class="sxs-lookup"><span data-stu-id="de5a1-116">At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time.</span></span> <span data-ttu-id="de5a1-117">Azure Active Directory，以及 Office 365 雲端 App 安全性會將這些功能傳遞全面性及整合的經驗與條件式存取應用程式控制項中。</span><span class="sxs-lookup"><span data-stu-id="de5a1-117">Together with Azure Active Directory, Office 365 Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de5a1-118">若要使用雲端 App 安全性條件式存取應用程式控制，您需要 [Azure Active Directory P1 授權](https://azure.microsoft.com/pricing/details/active-directory/) 和作用中的[Office 365 雲端 App 安全性](office-365-cas-overview.md)訂閱。</span><span class="sxs-lookup"><span data-stu-id="de5a1-118">To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active [Office 365 Cloud App Security](office-365-cas-overview.md) subscription.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="de5a1-119">運作方式</span><span class="sxs-lookup"><span data-stu-id="de5a1-119">How it works</span></span>

<span data-ttu-id="de5a1-120">條件式存取應用程式控制使用反向 proxy 架構，且唯一整合與 Azure AD 條件式存取。</span><span class="sxs-lookup"><span data-stu-id="de5a1-120">Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access.</span></span> <span data-ttu-id="de5a1-121">Azure AD 條件式存取可讓您以強制執行根據特定條件的貴組織的應用程式的存取控制。</span><span class="sxs-lookup"><span data-stu-id="de5a1-121">Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions.</span></span> <span data-ttu-id="de5a1-122">條件定義 *誰* （使用者或群組的使用者） 和 *哪些* （雲端應用程式）， *其中* 條件式存取原則 （哪一個位置和網路） 套用至。</span><span class="sxs-lookup"><span data-stu-id="de5a1-122">The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to.</span></span> <span data-ttu-id="de5a1-123">您已決定條件之後，您可以將使用者路由傳送至 Office 365 雲端 App 安全性可讓您保護資料的條件式存取應用程式控制藉由套用存取及工作階段的控制項。</span><span class="sxs-lookup"><span data-stu-id="de5a1-123">After you’ve determined the conditions, you can route users to Office 365 Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.</span></span>

<span data-ttu-id="de5a1-124">條件式存取應用程式控制可讓使用者應用程式存取及監視和控制存取及工作階段的原則為基礎的即時工作階段。</span><span class="sxs-lookup"><span data-stu-id="de5a1-124">Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies.</span></span> <span data-ttu-id="de5a1-125">存取及工作階段的原則可用內 Cloud App Security 入口網站來進一步調整篩選器及設定要對使用者採取的動作。</span><span class="sxs-lookup"><span data-stu-id="de5a1-125">Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user.</span></span> <span data-ttu-id="de5a1-126">存取及工作階段的原則，您可以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="de5a1-126">With the access and session policies, you can:</span></span>

- <span data-ttu-id="de5a1-127">**下載區塊**： 您可以封鎖的機密文件下載。</span><span class="sxs-lookup"><span data-stu-id="de5a1-127">**Block on download**: You can block the download of sensitive documents.</span></span> <span data-ttu-id="de5a1-128">例如，在未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="de5a1-128">For example, on unmanaged devices.</span></span>

- <span data-ttu-id="de5a1-129">**保護下載**： 而不是封鎖的機密文件下載，您可能需要透過加密下載受保護的文件]。</span><span class="sxs-lookup"><span data-stu-id="de5a1-129">**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download.</span></span> <span data-ttu-id="de5a1-130">此加密可確保文件受到保護，如果資料已下載至不受信任裝置通過驗證使用者的存取。</span><span class="sxs-lookup"><span data-stu-id="de5a1-130">This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device.</span></span>

- <span data-ttu-id="de5a1-131">**監視低信任層級使用者工作階段**： 當他們登入應用程式和其動作會從記錄在工作階段中，會監視有風險的使用者。</span><span class="sxs-lookup"><span data-stu-id="de5a1-131">**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session.</span></span> <span data-ttu-id="de5a1-132">您可以調查並分析使用者了解，並在哪些條件下工作階段應該將原則套用在未來的行為。</span><span class="sxs-lookup"><span data-stu-id="de5a1-132">You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.</span></span>

- <span data-ttu-id="de5a1-133">**封鎖存取**： 您完全可以封鎖特定應用程式為使用者即將從受管理的裝置或非公司網路的存取。</span><span class="sxs-lookup"><span data-stu-id="de5a1-133">**Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.</span></span>

- <span data-ttu-id="de5a1-134">**建立唯讀模式**： 藉由監視及封鎖自訂應用程式內的活動，您可以建立針對特定使用者的特定應用程式以唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="de5a1-134">**Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.</span></span>

- <span data-ttu-id="de5a1-135">**從非公司網路的限制使用者工作階段**： 允許使用者從不屬於您公司的網路位置存取受保護的應用程式限制] 存取權。</span><span class="sxs-lookup"><span data-stu-id="de5a1-135">**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access.</span></span> <span data-ttu-id="de5a1-136">封鎖或受保護的敏感資料的下載。</span><span class="sxs-lookup"><span data-stu-id="de5a1-136">The download of sensitive materials is blocked or protected.</span></span>

### <a name="how-session-control-works"></a><span data-ttu-id="de5a1-137">工作階段控制的運作方式</span><span class="sxs-lookup"><span data-stu-id="de5a1-137">How session control works</span></span>

<span data-ttu-id="de5a1-138">使用條件式存取應用程式控制建立工作階段原則可讓您控制使用者工作階段所透過反向 proxy 而不是將使用者重新導向直接對應用程式。</span><span class="sxs-lookup"><span data-stu-id="de5a1-138">Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app.</span></span> <span data-ttu-id="de5a1-139">之後，請於使用者要求和回應移到 Office 365 雲端 App 安全性，而不是直接對應用程式。</span><span class="sxs-lookup"><span data-stu-id="de5a1-139">From then on, user requests and responses go through Office 365 Cloud App Security rather than directly to the app.</span></span>

<span data-ttu-id="de5a1-140">若要保留使用者的工作階段，所有相關的 Url，Java 指令碼，以及在應用程式工作階段中的 cookie 會取代與 Office 365 雲端 App 安全性 Url。</span><span class="sxs-lookup"><span data-stu-id="de5a1-140">To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Office 365 Cloud App Security URLs.</span></span> <span data-ttu-id="de5a1-141">例如，如果應用程式會傳回其網域結尾 myapp.com 的連結] 頁面上，連結會取代以類似的網域： myapp.com.us.cas.ms</span><span class="sxs-lookup"><span data-stu-id="de5a1-141">For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms</span></span>

<span data-ttu-id="de5a1-142">此方法不需要您安裝在裝置上的任何項目。</span><span class="sxs-lookup"><span data-stu-id="de5a1-142">This method doesn't require you to install anything on the device.</span></span> <span data-ttu-id="de5a1-143">監視從未受控裝置的工作階段時，這個方法是理想。</span><span class="sxs-lookup"><span data-stu-id="de5a1-143">This method is ideal when monitoring sessions from unmanaged devices.</span></span>

<span data-ttu-id="de5a1-144">工作階段會導向到 Office 365 雲端 App 安全性後，可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="de5a1-144">After a session is directed through Office 365 Cloud App Security, the following actions can be done:</span></span>

1. <span data-ttu-id="de5a1-145">檢查使用者活動的流量</span><span class="sxs-lookup"><span data-stu-id="de5a1-145">Inspect the traffic for user activities</span></span>

2. <span data-ttu-id="de5a1-146">在 Office 365 雲端 App 安全性活動記錄檔中顯示的已識別的活動</span><span class="sxs-lookup"><span data-stu-id="de5a1-146">Display the identified activities in the Office 365 Cloud App Security Activity log</span></span>

3. <span data-ttu-id="de5a1-147">儲存流量記錄檔和分析</span><span class="sxs-lookup"><span data-stu-id="de5a1-147">Save the traffic logs and analyze them</span></span>

4. <span data-ttu-id="de5a1-148">啟用流量記錄匯出系統管理員</span><span class="sxs-lookup"><span data-stu-id="de5a1-148">Enable the admin to export the traffic logs</span></span>

5. <span data-ttu-id="de5a1-149">在 [工作階段上強制執行原則</span><span class="sxs-lookup"><span data-stu-id="de5a1-149">Enforce policies on the session</span></span>

## <a name="managed-device-identification"></a><span data-ttu-id="de5a1-150">受管理的裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="de5a1-150">Managed device identification</span></span>

<span data-ttu-id="de5a1-151">條件式存取應用程式控制可讓您建立原則，請考量是否或不受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="de5a1-151">Conditional Access App Control enables you to create policies that take into account whether a device is managed or not.</span></span> <span data-ttu-id="de5a1-152">若要識別是否或不受管理的裝置，功能會使用：</span><span class="sxs-lookup"><span data-stu-id="de5a1-152">To identify whether a device is managed or not, the feature uses:</span></span>

- <span data-ttu-id="de5a1-153">符合規範的裝置</span><span class="sxs-lookup"><span data-stu-id="de5a1-153">Compliant devices</span></span>

- <span data-ttu-id="de5a1-154">已加入網域的裝置</span><span class="sxs-lookup"><span data-stu-id="de5a1-154">Domain-joined devices</span></span>

- <span data-ttu-id="de5a1-155">用戶端憑證部署</span><span class="sxs-lookup"><span data-stu-id="de5a1-155">Client certificates deployment</span></span>

### <a name="compliant-and-domain-joined-devices"></a><span data-ttu-id="de5a1-156">相容] 和 [已加入網域的裝置</span><span class="sxs-lookup"><span data-stu-id="de5a1-156">Compliant and domain-joined devices</span></span>

<span data-ttu-id="de5a1-157">Azure AD 條件式存取讓相容和已加入網域的裝置資訊直接傳遞至 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="de5a1-157">Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Office 365 Cloud App Security.</span></span> <span data-ttu-id="de5a1-158">從那裡，存取原則或工作階段的原則可以開發做為篩選條件所使用的裝置狀態。</span><span class="sxs-lookup"><span data-stu-id="de5a1-158">From there, an access policy or a session policy can be developed that uses device state as a filter.</span></span> <span data-ttu-id="de5a1-159">如需詳細資訊，請參閱 <<c0>Azure Active Directory 中的裝置管理的簡介。</span><span class="sxs-lookup"><span data-stu-id="de5a1-159">For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>

### <a name="client-certificate-authenticated-devices"></a><span data-ttu-id="de5a1-160">用戶端憑證驗證裝置</span><span class="sxs-lookup"><span data-stu-id="de5a1-160">Client-certificate authenticated devices</span></span>

<span data-ttu-id="de5a1-161">裝置識別碼機制可要求從相關裝置使用用戶端憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="de5a1-161">The device identification mechanism can request authentication from relevant devices using client certificates.</span></span> <span data-ttu-id="de5a1-162">您可以使用現有的用戶端憑證已部署在您的組織或首度發行新的用戶端憑證至受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="de5a1-162">You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices.</span></span> <span data-ttu-id="de5a1-163">然後，您會使用這些憑證的目前狀態設定存取和工作階段的原則。</span><span class="sxs-lookup"><span data-stu-id="de5a1-163">You then use the presence of those certificates to set access and session policies.</span></span> <span data-ttu-id="de5a1-164">如需如何部署用戶端憑證的詳細資訊請參閱 <<c0>部署條件式應用程式的存取控制 Office 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="de5a1-164">For information on how to deploy client certificates see [Deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span></span>

## <a name="supported-apps-and-clients"></a><span data-ttu-id="de5a1-165">支援的應用程式和用戶端</span><span class="sxs-lookup"><span data-stu-id="de5a1-165">Supported apps and clients</span></span>

<span data-ttu-id="de5a1-166">條件式存取應用程式控制項的 Office 365 支援下列精選的應用程式：</span><span class="sxs-lookup"><span data-stu-id="de5a1-166">Conditional Access App Control for Office 365 supports the following featured apps:</span></span>

- <span data-ttu-id="de5a1-167">Exchange Online （預覽）</span><span class="sxs-lookup"><span data-stu-id="de5a1-167">Exchange Online (preview)</span></span>

- <span data-ttu-id="de5a1-168">OneDrive for Business （預覽）</span><span class="sxs-lookup"><span data-stu-id="de5a1-168">OneDrive for Business (preview)</span></span>

- <span data-ttu-id="de5a1-169">Power BI （預覽）</span><span class="sxs-lookup"><span data-stu-id="de5a1-169">Power BI (preview)</span></span>

- <span data-ttu-id="de5a1-170">SharePoint Online （預覽）</span><span class="sxs-lookup"><span data-stu-id="de5a1-170">SharePoint Online (preview)</span></span>

- <span data-ttu-id="de5a1-171">Microsoft Teams （預覽）</span><span class="sxs-lookup"><span data-stu-id="de5a1-171">Microsoft Teams (preview)</span></span>

- <span data-ttu-id="de5a1-172">Yammer （預覽）</span><span class="sxs-lookup"><span data-stu-id="de5a1-172">Yammer (preview)</span></span>

<span data-ttu-id="de5a1-173">其他應用程式正在持續在-boarded 工作階段控制。</span><span class="sxs-lookup"><span data-stu-id="de5a1-173">Additional apps are being continuously on-boarded to session control.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de5a1-174">後續步驟</span><span class="sxs-lookup"><span data-stu-id="de5a1-174">Next steps</span></span>

- [<span data-ttu-id="de5a1-175">為 Office 365 應用程式部署條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="de5a1-175">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="de5a1-176">了解 Office 365 雲端 App 安全性中的工作階段原則</span><span class="sxs-lookup"><span data-stu-id="de5a1-176">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="de5a1-177">了解 Office 365 雲端 App 安全性中的存取原則</span><span class="sxs-lookup"><span data-stu-id="de5a1-177">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 