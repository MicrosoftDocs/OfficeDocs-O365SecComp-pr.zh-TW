---
title: Office 365 雲端應用程式安全性的工作階段原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: Office 365 的雲端應用程式安全性工作階段的原則啟用即時工作階段層級監控、 可更精細的可見性到 Office 365 應用程式和功能需要您設定的使用者工作階段的原則不同的動作。允許或完全封鎖存取，而非工作階段控制您可以同時監控使用設定格式化的條件的 Access 應用程式控制項的反向 proxy 功能的工作階段和/或限制特定的工作階段活動允許存取。
ms.openlocfilehash: 0dbfb3e5827fb76e52f0262333d372860f0cb58a
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103338"
---
# <a name="session-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="e00c1-104">Office 365 雲端應用程式安全性的工作階段原則</span><span class="sxs-lookup"><span data-stu-id="e00c1-104">Session policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="e00c1-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e00c1-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e00c1-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e00c1-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e00c1-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e00c1-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e00c1-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e00c1-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e00c1-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="e00c1-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e00c1-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="e00c1-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="e00c1-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="e00c1-111">You are here!</span></span>  <br/> [<span data-ttu-id="e00c1-112">下一步</span><span class="sxs-lookup"><span data-stu-id="e00c1-112">Next step</span></span>](ocas-access-policies.md) <br/> |[<span data-ttu-id="e00c1-113">開始使用</span><span class="sxs-lookup"><span data-stu-id="e00c1-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="e00c1-p102">Office 365 的雲端應用程式安全性工作階段的原則啟用即時工作階段層級監控、 可更精細的可見性到 Office 365 應用程式和功能需要您設定的使用者工作階段的原則不同的動作。允許或完全封鎖存取，而非工作階段控制您可以同時監控使用設定格式化的條件的 Access 應用程式控制項的反向 proxy 功能的工作階段和/或限制特定的工作階段活動允許存取。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p102">Office 365 Cloud App Security session policies enable real-time session-level monitoring, affording you granular visibility into Office 365 apps and the ability to take different actions depending on the policy you set for a user session. Instead of allowing or blocking access completely, with session control you can allow access while monitoring the session and/or limit specific session activities using the reverse proxy capabilities of Conditional Access App Control.</span></span>

<span data-ttu-id="e00c1-p103">例如，您可以決定可從受管理的裝置，或來自特定位置的工作階段，您要允許使用者存取該應用程式，但也限制機密檔案的下載或需要特定文件受到保護時下載 （英文）。工作階段的原則可讓您設定這些使用者工作階段的控制項，並允許存取並可讓您：</span><span class="sxs-lookup"><span data-stu-id="e00c1-p103">For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app but also limit the download of sensitive files or require that certain documents be protected upon download. Session policies enable you to set these user-session controls and allow access and enables you to:</span></span>

- [<span data-ttu-id="e00c1-118">監視所有的活動</span><span class="sxs-lookup"><span data-stu-id="e00c1-118">Monitor all activities</span></span>](#monitor-all-activities)

- [<span data-ttu-id="e00c1-119">封鎖所有的下載項目</span><span class="sxs-lookup"><span data-stu-id="e00c1-119">Block all downloads</span></span>](#block-all-downloads)

- [<span data-ttu-id="e00c1-120">封鎖特定活動</span><span class="sxs-lookup"><span data-stu-id="e00c1-120">Block specific activities</span></span>](#block-specific-activities)

- [<span data-ttu-id="e00c1-121">保護檔案上下載 （英文）</span><span class="sxs-lookup"><span data-stu-id="e00c1-121">Protect files on download</span></span>](#protect-files-on-download)

## <a name="prerequisites-to-using-session-policies"></a><span data-ttu-id="e00c1-122">若要使用的工作階段的原則的必要條件</span><span class="sxs-lookup"><span data-stu-id="e00c1-122">Prerequisites to using session policies</span></span>

- <span data-ttu-id="e00c1-123">Azure AD Premium P1 授權</span><span class="sxs-lookup"><span data-stu-id="e00c1-123">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="e00c1-124">相關的 Office 365 應用程式應該是 [部署與設定格式化的條件的 Access 應用程式控制項](ocas-deploy-conditional-access-app-control.md)</span><span class="sxs-lookup"><span data-stu-id="e00c1-124">The relevant Office 365 apps should be [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md)</span></span>

- <span data-ttu-id="e00c1-125"> [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 應該在將使用者重新導向至 Office 365 雲端應用程式安全性的地方</span><span class="sxs-lookup"><span data-stu-id="e00c1-125">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="e00c1-126">建立 Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="e00c1-126">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="e00c1-p104">Azure Active Directory 設定格式化的條件存取原則與雲端應用程式安全性工作階段的原則中運作 tandem 檢查每個使用者工作階段並決定每個應用程式的原則。若要在 Azure AD 設定條件式存取原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="e00c1-p104">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app. To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="e00c1-p105">設定 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 使用者或群組的使用者與您想要使用設定格式化的條件的 Access 應用程式控制項的控制項的應用程式的工作分派。請注意： 唯一的應用程式已 [部署與設定格式化的條件的 Access 應用程式控制項](ocas-deploy-conditional-access-app-control.md) 將會受到此原則。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p105">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for a user or group of users and the app you want to control with the Conditional Access App Control. NOTE: Only apps that were [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md) will be affected by this policy.</span></span>

2. <span data-ttu-id="e00c1-131">選取 [ **使用設定格式化的條件存取應用程式控制強制執行限制**路由使用者傳送至 Office 365 雲端應用程式安全性  **工作階段**中 ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e00c1-131">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** in the **Session** page.</span></span>

## <a name="create-a-cloud-app-security-session-policy"></a><span data-ttu-id="e00c1-132">建立的雲端應用程式安全性工作階段的原則</span><span class="sxs-lookup"><span data-stu-id="e00c1-132">Create a Cloud App Security session policy</span></span>

<span data-ttu-id="e00c1-133">若要建立新的工作階段的原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="e00c1-133">To create a new session policy, follow this procedure:</span></span>

1. <span data-ttu-id="e00c1-134">在 [入口網站中，選取 **控制項** 後面 **的原則**。</span><span class="sxs-lookup"><span data-stu-id="e00c1-134">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="e00c1-135">在 [ **原則** ] 頁面上，按一下 [ **建立原則** 並選取 [ **工作階段的原則**。</span><span class="sxs-lookup"><span data-stu-id="e00c1-135">In the **Policies** page, click **Create policy** and select **Session policy**.</span></span>

3. <span data-ttu-id="e00c1-136">在 [ **工作階段原則** ] 視窗中，指派的原則名稱</span><span class="sxs-lookup"><span data-stu-id="e00c1-136">In the **Session policy** window, assign a name for your policy</span></span>

4. <span data-ttu-id="e00c1-137">在 **工作階段控制類型** 欄位：</span><span class="sxs-lookup"><span data-stu-id="e00c1-137">In the **Session control type** field:</span></span>
    
    - <span data-ttu-id="e00c1-p106">選取 [ **僅限監視器** 如果您只想要監視使用者所擁有的活動。這項選擇會建立監視器唯一原則您所選取其中所有的登入、 探索下載及活動類型將會下載應用程式。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p106">Select **Monitor only** if you only want to monitor activities by users. This selection will create a Monitor only policy for the apps you selected where all sign-ins, heuristic downloads, and Activity types will be downloaded.</span></span>
    
    - <span data-ttu-id="e00c1-p107">選取 [ **控制檔案下載 （英文） （使用 DLP)** 如果您想要監視使用者活動。您可以採取其他動作類似封鎖或保護使用者下載。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p107">Select **Control file download (with DLP)** if you want to monitor user activities. You can take additional actions like block or protect downloads for users.</span></span>
    
    - <span data-ttu-id="e00c1-p108">選取 [ **封鎖活動** 封鎖特定的活動，您可以選擇使用 **活動類型** 篩選。從選取的應用程式的所有活動可以監視 （以及報告活動記錄檔中）。如果您選取 [ **封鎖**您選取的特定活動將會遭到封鎖 巨集指令。如果您選取 [ **測試**您所選取的特定活動會引發警告 巨集指令且已開啟的提醒。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p108">Select **Block activities** to block specific activities, which you can select using the **Activity type** filter. All activities from selected apps will be monitored (and reported in the Activity log). The specific activities you select will be blocked if you select the **Block** action. The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

5. <span data-ttu-id="e00c1-p109">下的 [ **活動來源** 在 **符合下列所有的活動** ] 區段中，選取要套用至原則的其他活動篩選器。這些篩選器可以包括下列選項：</span><span class="sxs-lookup"><span data-stu-id="e00c1-p109">Under **Activity source** in the **Activities matching all of the following** section, select additional activity filters to apply to the policy. These filters can include the following options:</span></span>
    
    - <span data-ttu-id="e00c1-148">**裝置標記**： 使用此篩選器來識別未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="e00c1-148">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="e00c1-149">**位置**： 使用此篩選器來識別不明 （與因此 risky） 的位置。</span><span class="sxs-lookup"><span data-stu-id="e00c1-149">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="e00c1-150">**IP 位址**： 使用此篩選來篩選每個 IP 位址] 或 [使用先前指派的 IP 位址標記。</span><span class="sxs-lookup"><span data-stu-id="e00c1-150">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="e00c1-p110">**使用者代理程式 tag**： 使用此篩選器以啟用大概識別行動裝置與桌面應用程式。此篩選器可以設定為等於或不等於 **Native client**。此篩選應比照您各個雲端應用程式的行動電話和桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p110">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or doesn't equal **Native client**. This filter should be tested against your mobile and desktop apps for each cloud app.</span></span><br><span data-ttu-id="e00c1-p111">請注意： 工作階段的原則不支援行動電話和桌面應用程式。行動應用程式和桌面應用程式也可以是封鎖或允許藉由建立存取原則。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p111">NOTE: Session policies don’t support mobile and desktop apps. Mobile apps and desktop apps can also be blocked or allowed by creating an access policy.</span></span>

6. <span data-ttu-id="e00c1-p112">如果您選取的選項來 **控制檔案下載 （英文） （使用 DLP)**、 下的 [ **活動來源**  **符合下列所有檔案**中 ] 區段中，選取要套用至原則的其他檔案篩選器。這些篩選器可以包括下列選項：</span><span class="sxs-lookup"><span data-stu-id="e00c1-p112">If you selected the option to **Control file download (with DLP)**, under **Activity source** in the **Files matching all of the following** section, select additional file filters to apply to the policy. These filters can include the following options:</span></span>
        
    - <span data-ttu-id="e00c1-p113">**分類標籤** -如果您的組織使用 Azure 資訊保護和資料已受到其分類標籤使用此篩選器。您可以當做篩選依據分類標籤套用至他們的檔案。如 Azure 資訊保護整合的相關資訊，請參閱 [Azure 資訊保護整合](https://docs.microsoft.com/cloud-app-security/azip-integration)。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p113">**Classification label** - Use this filter if your organization uses Azure Information Protection and your data has been protected by its Classification labels. You can filter files based on the Classification label you applied to them. For more information about integration with Azure Information Protection, see [Azure Information Protection integration](https://docs.microsoft.com/cloud-app-security/azip-integration).</span></span>
        
    - <span data-ttu-id="e00c1-161">**檔案名稱** -使用此篩選器原則套用至特定的檔案。</span><span class="sxs-lookup"><span data-stu-id="e00c1-161">**File name** - Use this filter to apply the policy to specific files.</span></span>
        
    - <span data-ttu-id="e00c1-162">**檔案類型** -使用此篩選器原則套用至特定檔案類型，例如封鎖下載所有.xls 檔案。</span><span class="sxs-lookup"><span data-stu-id="e00c1-162">**File type** - Use this filter to apply the policy to specific file types, for example, block download for all .xls files.</span></span>
    
    - <span data-ttu-id="e00c1-163">在 **內容檢查** ] 區段中，設定是否要讓 DLP 引擎掃描文件及檔案內容。</span><span class="sxs-lookup"><span data-stu-id="e00c1-163">In the **Content inspection** section, set whether you want to enable the DLP engine to scan documents and file content.</span></span>
    
    - <span data-ttu-id="e00c1-164">在 [ **動作**] 下選取其中一個下列項目：</span><span class="sxs-lookup"><span data-stu-id="e00c1-164">Under **Actions**, select one of the following items:</span></span>
        
        - <span data-ttu-id="e00c1-165">**測試 （監視所有的活動）**： 設定此巨集指令，明確允許您設定的原則篩選依據的下載 （英文）。</span><span class="sxs-lookup"><span data-stu-id="e00c1-165">**Test (Monitor all activities)**: Set this action to explicitly allow download according to the policy filters you set.</span></span>
        
        - <span data-ttu-id="e00c1-p114">**區塊 （封鎖檔案下載 （英文） 和監視所有的活動）**： 設定來明確封鎖根據您所設定的原則篩選器的下載 （英文） 此巨集指令。如需詳細資訊，請參閱 [封鎖下載運作的方式](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download)。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p114">**Block (Block file download and monitor all activities)**: Set this action to explicitly block download according to the policy filters you set. For more information, see [How block download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download).</span></span>
        
        - <span data-ttu-id="e00c1-p115">**Protect （套用分類標籤來下載和監控所有的活動）**： 此選項才可用如果您選取 [ **控制檔案下載 （英文） （使用 DLP)** 下 **工作階段的原則**。如果您的組織使用 Azure 資訊保護，您可以將 **動作** 套用分類標籤設定在 Azure 資訊保護的檔案。如需詳細資訊，請參閱 [如何保護下載運作](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download)。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p115">**Protect (Apply classification label to download and monitor all activities)**: This option is only available if you selected **Control file download (with DLP)** under **Session policy**. If your organization uses Azure Information Protection, you can set an **Action** to apply a classification label set in Azure Information Protection to the file. For more information, see [How protect download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download).</span></span>

7. <span data-ttu-id="e00c1-p116">您可以 **建立原則的嚴重性與每個相符的事件通知** 並設定提醒的限制。選取您要做為電子郵件、 文字訊息，或兩者的警示。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p116">You can **Create an alert for each matching event with the policy's severity** and set an alert limit. Select whether you want the alert as an email, a text message, or both.</span></span>

## <a name="monitor-all-activities"></a><span data-ttu-id="e00c1-173">監視所有的活動</span><span class="sxs-lookup"><span data-stu-id="e00c1-173">Monitor all activities</span></span>

<span data-ttu-id="e00c1-p117">當您建立工作階段原則時、 原則會比對每個使用者工作階段會重新導向至工作階段控制項而不是應用程式直接。使用者會看到讓他們知道其工作階段的各個受監控的監控通知。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p117">When you create a session policy, each user session that matches the policy is redirected to session control rather than to the app directly. The user will see a monitoring notice to let them know that their sessions are being monitored.</span></span>

<span data-ttu-id="e00c1-176">如果您不想要通知使用者他們正在受監視，您可以停用通知訊息。</span><span class="sxs-lookup"><span data-stu-id="e00c1-176">If you don't want to notify the user that they're being monitored, you can disable the notification message.</span></span>

1. <span data-ttu-id="e00c1-177">[設定商旅中，選取 [ **一般設定**]。</span><span class="sxs-lookup"><span data-stu-id="e00c1-177">Under the settings cog, select **General settings**.</span></span>

2. <span data-ttu-id="e00c1-178">那麼， **設定格式化的條件的 Access 應用程式控制項**下 選取 **使用者監控** 並 **通知使用者**取消選取 [ ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e00c1-178">Then, under **Conditional Access App Control** select **User monitoring** and unselect the **Notify users** checkbox.</span></span>

<span data-ttu-id="e00c1-p118">若要讓使用者工作階段、 設定格式化的條件的 Access 應用程式控制項取代所有相關的 Url、 Java 指令碼及 cookie 內保持在應用程式工作階段與 Office 365 雲端應用程式安全性 Url。例如，如果應用程式會傳回的連結] 頁面上之網域結尾`myapp.com`、 設定格式化的條件的 Access 應用程式控制項的連結取代為結尾類似如下的網域`myapp.com.us.cas.ms`。如此一來監視整個工作階段的 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p118">To keep the user within the session, Conditional Access App Control replaces all the relevant URLs, Java scripts, and cookies within the app session with Office 365 Cloud App Security URLs. For example, if the app returns a page with links whose domains ends with `myapp.com`, Conditional Access App Control replaces the links with domains ending with something like `myapp.com.us.cas.ms`. This way the entire session is monitored by Office 365 Cloud App Security.</span></span>

<span data-ttu-id="e00c1-p119">設定格式化的條件的 Access 應用程式控制記錄透過它傳送每個使用者工作階段的流量記錄檔。流量記錄檔包含的時間、 IP、 使用者代理程式、 瀏覽的 Url，並的位元組數目上傳及下載。這些記錄會分析和連續報表 **雲端應用程式的安全性設定格式化的條件存取應用程式的控制項**，會新增至雲端探索儀表板中的雲端探索報表的清單。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p119">Conditional Access App Control records the traffic logs of every user session that is routed through it. The traffic logs include the time, IP, user agent, URLs visited, and the number of bytes uploaded and downloaded. These logs are analyzed and a continuous report, **Cloud App Security Conditional Access App Control**, is added to the list of Cloud Discovery reports in the Cloud Discovery dashboard.</span></span>

### <a name="to-export-these-logs"></a><span data-ttu-id="e00c1-185">若要匯出這些記錄檔：</span><span class="sxs-lookup"><span data-stu-id="e00c1-185">To export these logs:</span></span>

1. <span data-ttu-id="e00c1-186">移至 [設定商旅然後按一下 [ **設定格式化的條件存取應用程式的控制項**。</span><span class="sxs-lookup"><span data-stu-id="e00c1-186">Go to the settings cog and click **Conditional Access App Control**.</span></span>

2. <span data-ttu-id="e00c1-187">在表格的右側，按一下 [export] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e00c1-187">On the right side of the table, click the export button.</span></span><br>![export] 按鈕](media/image3.png)<br>

3. <span data-ttu-id="e00c1-p120">選取範圍的報告並按一下 [ **匯出**]。此程序可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p120">Select the range of the report and click **Export**. This process may take some time.</span></span>

### <a name="to-download-the-exported-log"></a><span data-ttu-id="e00c1-191">若要下載匯出的記錄檔：</span><span class="sxs-lookup"><span data-stu-id="e00c1-191">To download the exported log:</span></span>

1. <span data-ttu-id="e00c1-192">準備報表之後，請移至 [ **設定** ，然後 **匯出報告**。</span><span class="sxs-lookup"><span data-stu-id="e00c1-192">After the report is ready, go to **Settings** and then **Exported reports**.</span></span>

2. <span data-ttu-id="e00c1-193">在表格中，從 **設定格式化的條件的 Access 應用程式控制項的流量記錄檔**的清單中選取相關的報告 並按一下 [下載]。</span><span class="sxs-lookup"><span data-stu-id="e00c1-193">In the table, select the relevant report from the list of **Conditional Access App Control traffic logs** and click download.</span></span><br><span data-ttu-id="e00c1-194">![下載 （英文） 按鈕](media/image4.png)</span><span class="sxs-lookup"><span data-stu-id="e00c1-194">![download button](media/image4.png)</span></span><br>

## <a name="block-all-downloads"></a><span data-ttu-id="e00c1-195">封鎖所有的下載項目</span><span class="sxs-lookup"><span data-stu-id="e00c1-195">Block all downloads</span></span>

<span data-ttu-id="e00c1-p121">當 **封鎖** 設定為 **巨集指令** 想要的雲端應用程式安全性工作階段原則中取得、 設定格式化的條件的 Access 應用程式控制項禁止使用者下載每個原則的檔案篩選檔案。下載 （英文） 事件辨識 Office 365 雲端應用程式安全性每個應用程式的使用者啟動下載時。設定格式化的條件的 Access 應用程式控制項介入可防止執行的即時為止。設定格式化的條件的 Access 應用程式控制項時接收的訊號會接收使用者已初始化的下載 （英文），傳回 **下載限制** 訊息給使用者及下載的檔案取代的文字檔案。可設定及自訂的工作階段的原則給使用者的文字檔案的訊息。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p121">When **Block** is set as the **Action** you want to take in the Cloud App Security session policy, Conditional Access App Control prevents a user from downloading a file per the policy’s file filters. A download event is recognized by Office 365 Cloud App Security for each app when a user starts a download. Conditional Access App Control intervenes in real time to prevent it from running. When the signal is received that a user has initiated a download, Conditional Access App Control returns a **Download restricted** message to the user and replaces the downloaded file with a text file. The text file's message to the user can be configured and customized from the session policy.</span></span>

## <a name="block-specific-activities"></a><span data-ttu-id="e00c1-201">封鎖特定活動</span><span class="sxs-lookup"><span data-stu-id="e00c1-201">Block specific activities</span></span>

<span data-ttu-id="e00c1-p122">時 **封鎖活動** 設為 [ **活動類型**，您可以選取要封鎖特定應用程式中的特定活動。從選取的應用程式的所有活動會監視和報告活動記錄檔中。如果您選取 [ **封鎖**您選取的特定活動將會遭到封鎖 巨集指令。如果您選取的 **測試**巨集指令且提醒您所選取的特定活動會引發警告開啟。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p122">When **Block activities** is set as the **Activity type**, you can select specific activities to block in specific apps. All activities from selected apps will be monitored and reported in the Activity log. The specific activities you select will be blocked if you select the **Block** action. The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="e00c1-206">**封鎖特定活動** 並將其套用到特定群組以建立您的組織完整唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="e00c1-206">**Block specific activities** and apply it to specific groups to create a comprehensive read-only mode for your organization.</span></span>

## <a name="protect-files-on-download"></a><span data-ttu-id="e00c1-207">保護檔案上下載 （英文）</span><span class="sxs-lookup"><span data-stu-id="e00c1-207">Protect files on download</span></span>

<span data-ttu-id="e00c1-p123">選取 [ **封鎖活動** 封鎖特定的活動，您可以找到使用 **活動類型** 篩選。從選取的應用程式的所有活動可以監視 （以及報告活動記錄檔中）。如果您選取 [ **封鎖**您選取的特定活動將會遭到封鎖 巨集指令。如果您選取 [ **測試**您所選取的特定活動會引發警告 巨集指令且已開啟的提醒。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p123">Select **Block activities** to block specific activities, which you can find using the **Activity type** filter. All activities from selected apps will be monitored (and reported in the Activity log). The specific activities you select will be blocked if you select the **Block** action. The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="e00c1-p124">當 **Protect** 設定為 **巨集指令** 要採取的雲端應用程式安全性工作階段原則中，設定格式化的條件的 Access 應用程式控制強制執行每個原則的檔案篩選檔案的標籤和後續保護。標籤設定在 Azure 資訊保護主控台和 **Protect** 必須選取要顯示在雲端應用程式安全性原則選項的標籤內。當已選取 [標籤，及下載檔案符合準則的雲端應用程式安全性原則時，label 及相對應的保護 （具有權限） 會套用至在下載時的檔案。原始檔案仍會保留做為-雖然現在保護下載的檔案位於雲端應用程式。使用者嘗試存取該檔案必須符合所套用的保護決定的權限需求。</span><span class="sxs-lookup"><span data-stu-id="e00c1-p124">When **Protect** is set as the **Action** to be taken in the Cloud App Security session policy, Conditional Access App Control enforces the labeling and subsequent protection of a file per the policy’s file filters. Labels are configured in the Azure Information Protection console and **Protect** must be selected within the label for it to appear as an option in the Cloud App Security policy. When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label, and corresponding protection (with permissions) is applied to the file upon download. The original file remains as-is in the cloud app while the downloaded file is now protected. Users who try to access the file must meet the permission requirements determined by the protection applied.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e00c1-217">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e00c1-217">Next steps</span></span>

- [<span data-ttu-id="e00c1-218">深入了解 Office 365 雲端應用程式安全性存取原則</span><span class="sxs-lookup"><span data-stu-id="e00c1-218">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md)

- [<span data-ttu-id="e00c1-219">使用 Azure AD 條件式存取應用程式控制功能未受管理的裝置上封鎖下載項目</span><span class="sxs-lookup"><span data-stu-id="e00c1-219">Blocking downloads on unmanaged devices using Azure AD Conditional Access App Control capabilities</span></span>](https://docs.microsoft.com/en-us/cloud-app-security/use-case-proxy-block-session-aad)

