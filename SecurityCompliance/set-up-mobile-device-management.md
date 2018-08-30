---
title: 設定設定行動裝置管理 (MDM) in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: Office 365 內建的行動裝置管理可協助您保護及管理使用者的行動裝置 Iphone、 Ipad、 Androids、 like 及 Windows 電話。若要開始，請遵循下列步驟啟動及設定 Office 365 的行動裝置管理。
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272358"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a><span data-ttu-id="fd498-104">設定設定行動裝置管理 (MDM) in Office 365</span><span class="sxs-lookup"><span data-stu-id="fd498-104">Set up Mobile Device Management (MDM) in Office 365</span></span>

<span data-ttu-id="fd498-p102">內建行動裝置管理 (MDM) for Office 365 可協助您保護及管理使用者的行動裝置 Iphone、 Ipad、 Androids、 like 及 Windows 電話。您可以建立和管理裝置安全性原則、 遠端裝置，並檢視裝置詳細的報告。</span><span class="sxs-lookup"><span data-stu-id="fd498-p102">The built-in Mobile Device Management (MDM) for Office 365 helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones. You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>
  
<span data-ttu-id="fd498-p103">有問題嗎？我們已放入一起[協助地址的一般問題解答常見問題集](frequently-asked-questions-about-mdm.md)。請注意您無法使用[協力廠商： 優惠委派管理](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)來管理行動裝置管理 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fd498-p103">Have questions? We've put together [a FAQ to help address common questions](frequently-asked-questions-about-mdm.md). Be aware that you cannot use a [Partners: Offer delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) to manage Mobile Device Management for Office 365.</span></span> 
  
<span data-ttu-id="fd498-110">裝置管理屬於安全性&amp;規範中心讓您需要那里前往開始進行的 MDM 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="fd498-110">Device management is part of the Security &amp; Compliance Center so you'll need to go there to kick off MDM setup.</span></span>
  
<span data-ttu-id="fd498-111">若要設定行動裝置管理的 Office 365 您需要：</span><span class="sxs-lookup"><span data-stu-id="fd498-111">To set up Mobile Device Management for Office 365 you'll need to:</span></span>
  
1. <span data-ttu-id="fd498-112">[啟動 [行動裝置管理服務](#activate-the-mobile-device-management-service)</span><span class="sxs-lookup"><span data-stu-id="fd498-112">[Activate the Mobile Device Management service](#activate-the-mobile-device-management-service)</span></span>  
2. [<span data-ttu-id="fd498-113">設定行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="fd498-113">Set up Mobile Device Management</span></span>](#set-up-mobile-device-management)
3. [<span data-ttu-id="fd498-114">請確定使用者註冊其裝置</span><span class="sxs-lookup"><span data-stu-id="fd498-114">Make sure users enroll their devices</span></span>](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a><span data-ttu-id="fd498-115">啟動 [行動裝置管理服務</span><span class="sxs-lookup"><span data-stu-id="fd498-115">Activate the Mobile Device Management service</span></span>

1. <span data-ttu-id="fd498-116">以您的工作或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fd498-116">Sign in to Office 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="fd498-117">移至 [[安全性&amp;規範中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="fd498-117">Go to [Security &amp; Compliance Center](https://protection.office.com).</span></span>
    
3. <span data-ttu-id="fd498-118">瀏覽至 [**資料外洩防護** \> **裝置管理**並按一下 [**我們開始吧**開始進行的啟用程序。</span><span class="sxs-lookup"><span data-stu-id="fd498-118">Navigate to **Data loss prevention** \> **Device management** and click **Let's get started** to kick off the activation process.</span></span> 
    
    ![針對 Office 365 設定行動裝置管理](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. <span data-ttu-id="fd498-p104">我們建立預設的安全性原則來幫助您開始。更新] 頁面上的安全性原則名稱] 和 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="fd498-p104">We created a default security policy for you to help you get started. Update the name of the security policy on this page, and then click **Start setup**.</span></span>
    
    ![設定行動裝置管理安全性原則](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. <span data-ttu-id="fd498-123">您會看見顯示進度設定服務的 [安裝] 畫面。</span><span class="sxs-lookup"><span data-stu-id="fd498-123">You'll see the setup screen that shows progress on setting up the service.</span></span>
    
    ![MDM 安裝進度](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> <span data-ttu-id="fd498-p105">您也可以找到**MDM 安裝程式**透過搜尋。在 Office 365 系統管理中心\>**首頁**] 索引標籤類型的行動裝置管理的**搜尋**方塊中。>![搜尋系統管理中心中的行動裝置管理](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)</span><span class="sxs-lookup"><span data-stu-id="fd498-p105">You can also locate **MDM Setup** through Search. In the Office 365 admin center \> **Home** page, type mobile device management in the **Search** box. > ![Search for mobile device management in the admin center](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)</span></span>
  
<span data-ttu-id="fd498-128">它可以花一些時間來啟動的 Office 365 的行動裝置管理，但其完成時，將會收到電子郵件的說明所採取的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="fd498-128">It can take some time to activate Mobile Device Management for Office 365, but when it finishes, you'll receive an email that explains the next steps to take.</span></span>
  
## <a name="set-up-mobile-device-management"></a><span data-ttu-id="fd498-129">設定行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="fd498-129">Set up Mobile Device Management</span></span>

<span data-ttu-id="fd498-p106">準備好服務時，請完成下列四個步驟以完成安裝程式。您可能需要在 [安全性]**裝置管理**] 頁面上的 [[管理設定](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx)&amp;規範中心來查看下列設定值。</span><span class="sxs-lookup"><span data-stu-id="fd498-p106">When the service is ready, complete the following four steps to finish setup. You may need to click [Manage settings](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx) on the **Device management** page in the Security &amp; Compliance Center to see the following settings.</span></span> 
  
![設定行動裝置管理必要和建議的步驟](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="fd498-133">步驟 1： MDM （必要） 設定網域</span><span class="sxs-lookup"><span data-stu-id="fd498-133">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="fd498-p107">如果您不需要與 Office 365 相關聯的自訂網域或您不管理 Windows 裝置，您可以略過這一節。否則，您需要新增在 DNS 主機的網域的 DNS 記錄。如果您已設定您的網域與 Office 365 的一部分已經、 新增記錄您正在所有設定。新增記錄之後，Office 365 的使用者在組織中使用自訂網域的電子郵件地址與其 Windows 裝置登入已重新導向至在 MDM 中註冊 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fd498-p107">If you don't have a custom domain associated with Office 365 or if you're not managing Windows devices, you can skip this section. Otherwise, you'll need to add DNS records for the domain at your DNS host. If you've added the records already, as part of setting up your domain with Office 365, you're all set. After you add the records, Office 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in MDM for Office 365.</span></span>
  
<span data-ttu-id="fd498-p108">需要協助設定記錄吗？尋找網域註冊機構中所提供[的 Office 365 管理 DNS 記錄時建立 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)中的清單並選取要移至 [建立 DNS 記錄的逐步說明的登錄程式名稱。使用這些指示來新增下列兩個記錄：</span><span class="sxs-lookup"><span data-stu-id="fd498-p108">Need help setting up the records? Find your domain registrar in the list provided in [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) and select the registrar name to go to step-by-step help for creating DNS records. Use those instructions to add the following two records:</span></span> 
  
|<span data-ttu-id="fd498-141">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="fd498-141">**Host name**</span></span>|<span data-ttu-id="fd498-142">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="fd498-142">**Record type**</span></span>|<span data-ttu-id="fd498-143">**地址**</span><span class="sxs-lookup"><span data-stu-id="fd498-143">**Address**</span></span>|<span data-ttu-id="fd498-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fd498-144">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd498-145">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="fd498-145">EnterpriseEnrollment</span></span>  <br/> |<span data-ttu-id="fd498-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd498-146">CNAME</span></span>  <br/> |<span data-ttu-id="fd498-147">EnterpriseEnrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fd498-147">EnterpriseEnrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="fd498-148">3600</span><span class="sxs-lookup"><span data-stu-id="fd498-148">3600</span></span>  <br/> |
|<span data-ttu-id="fd498-149">EnterpriseRegistration</span><span class="sxs-lookup"><span data-stu-id="fd498-149">EnterpriseRegistration</span></span>  <br/> |<span data-ttu-id="fd498-150">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd498-150">CNAME</span></span>  <br/> |<span data-ttu-id="fd498-151">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fd498-151">EnterpriseRegistration.windows.net</span></span>  <br/> |<span data-ttu-id="fd498-152">3600</span><span class="sxs-lookup"><span data-stu-id="fd498-152">3600</span></span>  <br/> |
   
<span data-ttu-id="fd498-153">新增兩個記錄之後，回到安全性&amp;規範中心及瀏覽至 [**裝置管理** \> **管理設定**以完成下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="fd498-153">After you add the two records, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="fd498-154">步驟 2： （必要） Configure iOS 裝置 APNs 憑證</span><span class="sxs-lookup"><span data-stu-id="fd498-154">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="fd498-155">若要管理 iPad 和 Iphone iOS 裝置，您需要建立 APNs 憑證。</span><span class="sxs-lookup"><span data-stu-id="fd498-155">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>
  
<span data-ttu-id="fd498-156">若要這樣做，遵循的步驟**設定**連結上的**行動裝置管理] 頁面上的安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="fd498-156">To do this, follow the steps from the **Set up** links on the **Setup mobile device management page**.</span></span>
  
1. <span data-ttu-id="fd498-157">**Configure iOS 裝置 APNs 憑證**] 旁邊選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="fd498-157">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="fd498-158">選取 [**下載 CSR 檔案**並儲存至兩者的憑證簽署要求將記住您電腦上。</span><span class="sxs-lookup"><span data-stu-id="fd498-158">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![安裝 APN 憑證] 對話方塊](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="fd498-160">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="fd498-160">Select **Next**.</span></span>
    
4. <span data-ttu-id="fd498-161">建立 APN 憑證。</span><span class="sxs-lookup"><span data-stu-id="fd498-161">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="fd498-162">選取 [ **Apple APNS 入口網站**來開啟 Apple 推入憑證入口網站。</span><span class="sxs-lookup"><span data-stu-id="fd498-162">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![使用選取的 Apple APNS 入口網站安裝 APN 通知 cert 對話方塊](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="fd498-164">使用 Apple ID 登入</span><span class="sxs-lookup"><span data-stu-id="fd498-164">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fd498-p109">使用 Apple 識別碼即使管理帳戶的使用者離開會與您的組織中保留電子郵件帳戶相關聯的公司。因為您需要該是時候來更新憑證時所使用的相同識別碼儲存此識別碼。</span><span class="sxs-lookup"><span data-stu-id="fd498-p109">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="fd498-167">選取 [**建立憑證**並接受**使用規定**。</span><span class="sxs-lookup"><span data-stu-id="fd498-167">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="fd498-168">**瀏覽**至您下載到您的電腦從 Office 365 和選取 [**上傳**的憑證簽署要求。</span><span class="sxs-lookup"><span data-stu-id="fd498-168">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="fd498-169">**下載**建立 Apple 推入憑證入口網站到您的電腦 APN 憑證。</span><span class="sxs-lookup"><span data-stu-id="fd498-169">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="fd498-170">如果您無法下載憑證，重新整理瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="fd498-170">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="fd498-171">前往 Office 365 並選取 [**下一步**取得**上傳 APNS 憑證**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="fd498-171">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="fd498-172">瀏覽至您下載從 Apple 推入憑證入口網站的 APN 憑證。</span><span class="sxs-lookup"><span data-stu-id="fd498-172">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![按一下 [瀏覽] 按鈕選取 APNS cert 從 Apple 下載](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="fd498-174">選取 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="fd498-174">Select **Finish**.</span></span>
    
<span data-ttu-id="fd498-175">新增 APN 憑證之後，回到安全性&amp;規範中心及瀏覽至 [**裝置管理** \> **管理設定**以完成下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="fd498-175">After you add APN Certificate, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="fd498-176">步驟 3： 多重要素驗證設定 （建議使用）</span><span class="sxs-lookup"><span data-stu-id="fd498-176">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="fd498-p110">如果您沒有看到 [**建議步驟**的多重要素驗證 (MFA)，您可以略過這一節。如果列出此選項，我們建議您在 Office 365 註冊程序的行動裝置管理安全性 Azure AD 入口網站中開啟 MFA。它會依預設已關閉。</span><span class="sxs-lookup"><span data-stu-id="fd498-p110">If you don't see multi-factor authentication (MFA) under **Recommended steps**, you can skip this section. If this option is listed, we recommend you turn on MFA in the Azure AD portal to increase the security of the Mobile Device Management for Office 365 enrollment process. It is turned off by default.</span></span>
  
<span data-ttu-id="fd498-p111">MFA 可協助保護安全登入 Office 365 的行動裝置註冊需要驗證第二個表單。使用者所需確認電話、 文字訊息或應用程式通知使用者的行動裝置上正確地輸入工作的帳戶密碼之後。他們只可以註冊使用者的裝置後完成這第二種形式的驗證。使用者的裝置會在行動裝置管理註冊 Office 365 後，使用者可以存取 Office 365 資源與剛其工作的帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd498-p111">MFA helps secure the sign in to Office 365 for mobile device enrollment by requiring a second form of authentication. Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password. They can only enroll their device after this second form of authentication is completed. After users' devices are enrolled in Mobile Device Management for Office 365, users can access Office 365 resources with just their work account.</span></span>
  
<span data-ttu-id="fd498-p112">旁**設定多重要素驗證**，請選取 [**設定**]。若要了解如何在 Azure AD 入口網站中開啟 MFA，請參閱[設定多重要素驗證](https://go.microsoft.com/fwlink/p/?LinkId=519255)。</span><span class="sxs-lookup"><span data-stu-id="fd498-p112">Next to **Set up multi-factor authentication**, select **Set up**. To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>
  
<span data-ttu-id="fd498-186">設定 「 MFA 之後，回到安全性&amp;規範中心及瀏覽至 [**裝置管理** \> **管理設定**以完成下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="fd498-186">After you set up MFA, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="fd498-187">步驟 4： （建議使用） 管理裝置安全性原則</span><span class="sxs-lookup"><span data-stu-id="fd498-187">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="fd498-p113">下一步是建立及部署可協助保護您的 Office 365 組織資料的裝置安全性原則。例如，您可以協助防止資料遺失如果使用者藉由建立原則來鎖定裝置 5 分鐘的閒置時間後失去使用者的裝置和裝置 3 登入失敗之後清除。</span><span class="sxs-lookup"><span data-stu-id="fd498-p113">The next step is to create and deploy device security policies to help protect your Office 365 organization's data. For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after 5 minutes of inactivity and have devices wiped after 3 sign-in failures.</span></span>
  
<span data-ttu-id="fd498-190">在**安全性&amp;規範中心**、 移至 [**安全性原則** \> **裝置安全性原則**建立裝置安全性原則和存取規則。</span><span class="sxs-lookup"><span data-stu-id="fd498-190">In the **Security &amp; Compliance Center**, go to **Security policies** \> **Device security policies** to create device security policies and access rules.</span></span> 
  
![新增裝置安全性原則](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
<span data-ttu-id="fd498-192">如需如何建立新原則的逐步指示，請參閱[建立及部署裝置安全性原則](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fd498-192">For step by step instructions on how to create a new policy, see [Create and deploy device security policies](create-device-security-policies.md).</span></span>
  
> [!TIP]
>  <span data-ttu-id="fd498-p114">當您建立新的原則時，您可能會想要將原則設定為允許存取和報告原則違規使用者的裝置不符合原則是。這可讓您查看多少行動裝置會受到而封鎖存取 Office 365 的原則。> 每個人都部署在組織中的新原則之前，建議您測試少數使用者所使用的裝置上。> 此外，部署原則之前，可讓您知道 MDM 的裝置註冊 Office 365 的潛在影響的組織。根據您如何設定原則，存取 Office 365 可能會遭到封鎖不遵守其 （非相容裝置） 裝置。非相容裝置也可能必須安裝的應用程式、 相片和其註冊的裝置，可能會刪除如果清除裝置時的其他個人資訊。更多資訊： [Office 365 的行動裝置](wipe-a-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="fd498-p114">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user's device isn't compliant with the policy. This lets you see how many mobile devices would be impacted by the policy without blocking access to Office 365. >  Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users. >  Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in MDM for Office 365. Depending on how you set up the policies, devices that don't comply with them (non-compliant devices) could be blocked from accessing Office 365. Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped. More info: [Wipe a mobile device in Office 365](wipe-a-mobile-device.md).</span></span> 
  
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="fd498-200">請確定使用者註冊其裝置</span><span class="sxs-lookup"><span data-stu-id="fd498-200">Make sure users enroll their devices</span></span>

<span data-ttu-id="fd498-p115">您已建立及部署的行動裝置管理原則之後，裝置原則可套用至您組織中的每個授權的 Office 365 使用者將會在的下次登入 Office 365 從使用者的行動裝置時收到註冊訊息。他們必須完成註冊並啟用步驟他們才能存取 Office 365 電子郵件和文件。請參閱[註冊您的公司或學校的行動裝置](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="fd498-p115">After you've created and deployed a mobile device management policy, each licensed Office 365 user in your organization that the device policy applies to will receive an enrollment message the next time they sign into Office 365 from their mobile device. They must complete the enrollment and activation steps before they can access Office 365 email and documents. See [Enroll your mobile device for work or school](enroll-your-mobile-device.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fd498-p116">如果使用者的偏好的語言不受支援的註冊程序，使用者可能會收到另一種語言註冊通知和其行動裝置上的步驟。並非所有語言都支援的 Office 365 中目前都支援的行動裝置上的註冊程序。</span><span class="sxs-lookup"><span data-stu-id="fd498-p116">If a user's preferred language isn't supported by the enrollment process, users may receive enrollment notification and steps on their mobile devices in another language. Not all languages supported in Office 365 are currently supported for the enrollment process on mobile devices.</span></span> 
  
<span data-ttu-id="fd498-206">Android 或 iOS 裝置使用的使用者，才能安裝的公司入口網站應用程式註冊程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd498-206">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fd498-207">相關主題</span><span class="sxs-lookup"><span data-stu-id="fd498-207">Related Topics</span></span>

[<span data-ttu-id="fd498-208">行動裝置管理功能</span><span class="sxs-lookup"><span data-stu-id="fd498-208">Capabilities of Mobile Device Management</span></span>](capabilities-of-mobile-device-management.md)
  
[<span data-ttu-id="fd498-209">建立及部署裝置安全性原則</span><span class="sxs-lookup"><span data-stu-id="fd498-209">Create and deploy device security policies</span></span>](create-device-security-policies.md)
  

