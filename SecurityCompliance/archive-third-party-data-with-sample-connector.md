---
title: 使用範例連接器來封存 Office 365 （預覽） 中的協力廠商資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 系統管理員可以設定協力廠商資料匯入 Facebook 商務頁面、 LinkedIn 公司頁面等立即 Bloomberg 資料來源的原生的連接器。 這可讓您封存在 Office 365 中的協力廠商資料來源中的資料，所以您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理貴組織的協力廠商資料的控管。
ms.openlocfilehash: bca193753d0a63de867bdb11cfce3918c124f429
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/25/2019
ms.locfileid: "33307826"
---
# <a name="use-sample-connectors-to-archive-third-party-data-in-office-365-preview"></a><span data-ttu-id="ec51b-104">使用範例連接器來封存 Office 365 （預覽） 中的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="ec51b-104">Use sample connectors to archive third-party data in Office 365 (Preview)</span></span>

<span data-ttu-id="ec51b-105">若要封存 Office 365 中的協力廠商資料的範例連接器功能是在預覽。</span><span class="sxs-lookup"><span data-stu-id="ec51b-105">The sample connector feature to archive third-party data in Office 365 is in Preview.</span></span>

<span data-ttu-id="ec51b-106">使用安全性 & 在 Office 365 規範中心中的範例連接器，來匯入及封存如 Facebook、 LinkedIn、 Twitter 和 Bloomberg 協力廠商資料來源中的資料。</span><span class="sxs-lookup"><span data-stu-id="ec51b-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from a third-party data sources such as Facebook, LinkedIn, Twitter, and Bloomberg.</span></span> <span data-ttu-id="ec51b-107">設定後，當您設定範例連接器時，它連接至 （按照排程） 的協力廠商資料來源、 將項目的內容轉換成電子郵件訊息的格式，並再將這些項目匯入至 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ec51b-107">After you set up and configure a sample connector, it connects to the third-party data source (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="ec51b-108">協力廠商資料匯入之後，您可以將 Office 365 符合性功能，例如訴訟暫止狀態，內容搜尋、 就地封存、 稽核、 監督，與 Office 365 保留原則套用至協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="ec51b-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies to the third-party data.</span></span> <span data-ttu-id="ec51b-109">例如，當信箱處於訴訟暫止狀態或指派到保留原則時，仍會保留協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="ec51b-109">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the third-party data will be retained.</span></span> <span data-ttu-id="ec51b-110">您可以搜尋協力廠商資料使用內容搜尋，或其關聯 custodian 進階電子文件探索案例中。</span><span class="sxs-lookup"><span data-stu-id="ec51b-110">You can search third-party data using Content Search or associate it with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="ec51b-111">使用匯入和封存 Office 365 中的協力廠商資料的範例連接器，可協助組織符合規範與政府法規的原則。</span><span class="sxs-lookup"><span data-stu-id="ec51b-111">Using sample connectors to import and archive third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="ec51b-112">目前，只有 Facebook 商務頁面的範例連接器是供預覽。</span><span class="sxs-lookup"><span data-stu-id="ec51b-112">Currently, only the sample connector for Facebook Business pages is available for Preview.</span></span> <span data-ttu-id="ec51b-113">更多範例連接器即將推出。</span><span class="sxs-lookup"><span data-stu-id="ec51b-113">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="ec51b-114">設定 Facebook 商務頁面的連接器的必要條件</span><span class="sxs-lookup"><span data-stu-id="ec51b-114">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="ec51b-115">您可以設定和安全性 & 合規性中心，以匯入及封存資料從您的組織 Facebook 商務頁面中設定的範例連接器之前，您必須完成下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="ec51b-115">You must complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="ec51b-116">您需要的 Facebook 帳戶貴組織的業務頁面 （您需要設定連接器時，登入到這個帳戶）。</span><span class="sxs-lookup"><span data-stu-id="ec51b-116">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="ec51b-117">目前，您可以僅封存資料從 Facebook 商務頁面;您無法封存資料從個別 Facebook 設定檔。</span><span class="sxs-lookup"><span data-stu-id="ec51b-117">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="ec51b-118">您的組織必須具有有效的 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="ec51b-118">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="ec51b-119">如果您沒有現有的 Azure 訂用帳戶，您可以註冊其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="ec51b-119">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="ec51b-120">註冊免費 1 年 Azure 訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="ec51b-120">Sign up for a free 1 year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="ec51b-121">註冊 Pay-As-You-Go Azure 訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="ec51b-121">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="ec51b-122">已內含於您的 Office 365 訂閱的[免費的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)不支援的範例連接器中安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ec51b-122">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="ec51b-123">您的組織必須同意允許存取您組織中的信箱資料的 Office 365 匯入服務。</span><span class="sxs-lookup"><span data-stu-id="ec51b-123">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="ec51b-124">若要同意這項要求，請移到[此頁面上](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，登入的 Office 365 全域管理員認證，並接受要求。</span><span class="sxs-lookup"><span data-stu-id="ec51b-124">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="ec51b-125">設定安全性 & 合規性 （步驟 7) 中的自訂連接器的使用者必須獲指派信箱匯入匯出角色在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ec51b-125">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ec51b-126">根據預設，此角色不指派給任何角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ec51b-126">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="ec51b-127">您可以新增 「 信箱匯入 / 匯出 」 角色給組織管理角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ec51b-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ec51b-128">或者，您可以建立新的角色群組、 指派 「 信箱匯入 / 匯出 」 角色，並再將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="ec51b-128">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ec51b-129">如需詳細資訊，請參閱 < 文件中的<b0>建立角色群組</b0>或<b1>修改角色群組</b1>區段 」 管理角色群組在 Exchange Online 」。</span><span class="sxs-lookup"><span data-stu-id="ec51b-129">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="ec51b-130">步驟 1： 從 Github 下載預先內建的連接器應用程式套件</span><span class="sxs-lookup"><span data-stu-id="ec51b-130">Step 1: Download the pre-built connector app package from Github</span></span>

<span data-ttu-id="ec51b-131">第一個步驟是下載預先內建 Facebook 連接器應用程式將用來連線至您的 Facebook 商務頁面並解壓縮 Facebook 資料，讓您可以將它匯入 Office 365 的 Facebook API 的程式碼。</span><span class="sxs-lookup"><span data-stu-id="ec51b-131">The first step is to download the source code for the pre-built Facebook connector app that will use a Facebook API to connect to your Facebook Business pages and extract Facebook data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="ec51b-132">移至[這個 GitHub 網站](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="ec51b-132">Go to [this GitHub site](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="ec51b-133">[最新版本中，按一下 [ **SampleConnector.zip**檔案。</span><span class="sxs-lookup"><span data-stu-id="ec51b-133">Under the latest release, click the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="ec51b-134">ZIP 檔案儲存到您本機電腦上的位置。</span><span class="sxs-lookup"><span data-stu-id="ec51b-134">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="ec51b-135">您將此 zip 檔案上傳到步驟 4 中的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="ec51b-135">You'll upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="ec51b-136">步驟 2： 在 Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="ec51b-136">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="ec51b-137">下一步是註冊新的應用程式在 Azure Active Directory (AAD)。</span><span class="sxs-lookup"><span data-stu-id="ec51b-137">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="ec51b-138">此應用程式將會對應至您將 Facebook 連接器在步驟 4 中實作的 web 應用程式資源。</span><span class="sxs-lookup"><span data-stu-id="ec51b-138">This app will correspond to the web app resource that you'll implement in Step 4 for the Facebook connector.</span></span> 

<span data-ttu-id="ec51b-139">如需逐步指示，請參閱 <<c0>建立 Azure Active Directory 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec51b-139">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="ec51b-140">期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。</span><span class="sxs-lookup"><span data-stu-id="ec51b-140">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="ec51b-141">在部署程序稍後步驟，就會使用這些值。</span><span class="sxs-lookup"><span data-stu-id="ec51b-141">The values for these will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="ec51b-142">AAD 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="ec51b-142">AAD application ID</span></span>
- <span data-ttu-id="ec51b-143">AAD 應用程式密碼</span><span class="sxs-lookup"><span data-stu-id="ec51b-143">AAD application secret</span></span>
- <span data-ttu-id="ec51b-144">AAD 應用程式的 Uri</span><span class="sxs-lookup"><span data-stu-id="ec51b-144">AAD application Uri</span></span>
- <span data-ttu-id="ec51b-145">租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="ec51b-145">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="ec51b-146">步驟 3： 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="ec51b-146">Step 3: Create an Azure storage account</span></span>

<span data-ttu-id="ec51b-147">為貴組織部署 Facebook 連接器將上傳您在此步驟中建立的 Azure 儲存體位置從 Facebook 商務網頁的項目。</span><span class="sxs-lookup"><span data-stu-id="ec51b-147">The Facebook Connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure storage location that you create in this step.</span></span> <span data-ttu-id="ec51b-148">在安全性 & （在步驟 7) 的合規性中心建立自訂連接器之後，Office 365 匯入服務將 Facebook 將資料複製從 Azure 儲存體位置到 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ec51b-148">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Facebook data from the Azure storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="ec51b-149">如同先前所述[的必要條件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)] 區段中，您必須建立 Azure 儲存體帳戶的有效 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="ec51b-149">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure storage account.</span></span>

<span data-ttu-id="ec51b-150">如需逐步指示，請參閱 <<c0>建立 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="ec51b-150">For step-by-step instructions, see [Create an Azure storage account](deploy-facebook-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="ec51b-151">完成此步驟中 （藉由遵循的逐步指示） 的期間，您將儲存的連線字串產生的 Uri。</span><span class="sxs-lookup"><span data-stu-id="ec51b-151">During the completion of this step (by following the step-by-step instructions) you'll save the connection string Uri that is generated.</span></span> <span data-ttu-id="ec51b-152">在步驟 4 中的 Azure 中建立 web 應用程式資源時，您將使用此字串。</span><span class="sxs-lookup"><span data-stu-id="ec51b-152">You'll use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="ec51b-153">步驟 4： 在 Azure 中建立 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="ec51b-153">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="ec51b-154">下一步是在 Azure 中建立 web 應用程式資源 Facebook 連接器。</span><span class="sxs-lookup"><span data-stu-id="ec51b-154">The next step is to create a web app resource in Azure for the Facebook Connector.</span></span> 

<span data-ttu-id="ec51b-155">如需逐步指示，請參閱 <<c0>建立新的 web 應用程式資源在 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="ec51b-155">For step-by-step instructions, see [Create a new web app resource in Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="ec51b-156">期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （完成上述步驟之後，您已複製到文字檔案） 時建立的 web 應用程式資源。</span><span class="sxs-lookup"><span data-stu-id="ec51b-156">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="ec51b-157">APISecretKey – 您會在完成此步驟中; 的期間建立此密碼步驟 7 中，將使用它。</span><span class="sxs-lookup"><span data-stu-id="ec51b-157">APISecretKey – You will create this secret during the completion of this step; it will be used in Step 7.</span></span>
- <span data-ttu-id="ec51b-158">StorageAccountConnectionString – 您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri 的連接字串。</span><span class="sxs-lookup"><span data-stu-id="ec51b-158">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>
- <span data-ttu-id="ec51b-159">tenantId – 您在步驟 2 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="ec51b-159">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="ec51b-160">此外，您會在此步驟中部署 Facebook 連接器應用程式的原始碼上載 SampleConnector.zip （下載檔案，您在步驟 1 中）。</span><span class="sxs-lookup"><span data-stu-id="ec51b-160">Additionally, you will upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Facebook connector app.</span></span>

<span data-ttu-id="ec51b-161">之後完成此步驟，請務必要複製的應用程式服務的 URL (例如， https://fbconnector.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="ec51b-161">After completing this step, be sure to copy the app Service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="ec51b-162">您將需要使用此功能來完成步驟 5、 步驟 6 和步驟 7）。</span><span class="sxs-lookup"><span data-stu-id="ec51b-162">You'll need to use this to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-register-the-web-app-on-facebook"></a><span data-ttu-id="ec51b-163">步驟 5： 註冊在 Facebook 上的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="ec51b-163">Step 5: Register the web app on Facebook</span></span>

<span data-ttu-id="ec51b-164">下一步是建立及設定新的應用程式在 Facebook 上。</span><span class="sxs-lookup"><span data-stu-id="ec51b-164">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="ec51b-165">您在步驟 7 中建立的自訂連接器會使用 Facebook web app 與 Facebook API，以取得從貴組織的 Facebook 商務資料互動。</span><span class="sxs-lookup"><span data-stu-id="ec51b-165">The custom connector that you create in Step 7 will use the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="ec51b-166">如需逐步指示，請參閱[註冊 Facebook 應用程式](deploy-facebook-connector.md#step-5-register-the-facebook-app)。</span><span class="sxs-lookup"><span data-stu-id="ec51b-166">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-5-register-the-facebook-app).</span></span>

<span data-ttu-id="ec51b-167">期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。</span><span class="sxs-lookup"><span data-stu-id="ec51b-167">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="ec51b-168">這些值會用來在步驟 6 中設定 Facebook 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec51b-168">The values for these will be used to configure the Facebook connector app in Step 6.</span></span>

- <span data-ttu-id="ec51b-169">Facebook 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="ec51b-169">Facebook application ID</span></span>
- <span data-ttu-id="ec51b-170">Facebook 應用程式密碼</span><span class="sxs-lookup"><span data-stu-id="ec51b-170">Facebook application secret</span></span>
- <span data-ttu-id="ec51b-171">Facebook webhooks 驗證權杖</span><span class="sxs-lookup"><span data-stu-id="ec51b-171">Facebook webhooks verify token</span></span>

## <a name="step-6-configure-the-facebook-connector-app"></a><span data-ttu-id="ec51b-172">步驟 6： 設定 Facebook 連接器應用程式</span><span class="sxs-lookup"><span data-stu-id="ec51b-172">Step 6: Configure the Facebook connector app</span></span>

<span data-ttu-id="ec51b-173">下一步是將組態設定新增至您上傳時您在步驟 4 中建立 Azure 的 web 應用程式資源 Facebook 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec51b-173">The next step is to add configurations settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="ec51b-174">您將移至您的連接器應用程式的 [首頁] 頁面上，並設定其來這麼做。</span><span class="sxs-lookup"><span data-stu-id="ec51b-174">You'll do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="ec51b-175">如需逐步指示，請參閱[步驟 6： 設定連接器的 web 應用程式](deploy-facebook-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="ec51b-175">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-facebook-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="ec51b-176">期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成上述步驟之後，您已複製到文字檔案）：</span><span class="sxs-lookup"><span data-stu-id="ec51b-176">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="ec51b-177">Facebook 應用程式識別碼 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="ec51b-177">Facebook application ID (obtained in Step 5)</span></span>
- <span data-ttu-id="ec51b-178">Facebook 應用程式密碼 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="ec51b-178">Facebook application secret (obtained in Step 5)</span></span>
- <span data-ttu-id="ec51b-179">Facebook webhooks 驗證權杖 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="ec51b-179">Facebook webhooks verify token (obtained in Step 5)</span></span>
- <span data-ttu-id="ec51b-180">Azure Active Directory 應用程式識別碼 （在步驟 2 中所取得的 AAD 應用程式識別碼）</span><span class="sxs-lookup"><span data-stu-id="ec51b-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="ec51b-181">Azure Active Directory 應用程式密碼 （在步驟 2 中所取得的 AAD 應用程式密碼）</span><span class="sxs-lookup"><span data-stu-id="ec51b-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="ec51b-182">Azure Active Directory 應用程式的 Uri (AAD 應用程式的 Uri 取得在步驟 2; 例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span><span class="sxs-lookup"><span data-stu-id="ec51b-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="ec51b-183">步驟 7： 設立安全性 & 合規性中心中的自訂連接器</span><span class="sxs-lookup"><span data-stu-id="ec51b-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="ec51b-184">最後一個步驟是設定安全性 & 會從資料匯入 Facebook 商務頁面指定的信箱，Office 365 中的規範中心中的自訂連接器。</span><span class="sxs-lookup"><span data-stu-id="ec51b-184">The final step is to set up the custom connector in the Security & Compliance Center that will import data from your Facebook Business pages to a specified mailbox in Office 365.</span></span> <span data-ttu-id="ec51b-185">您已成功完成此步驟之後，Office 365 匯入服務會啟動將資料從您的 Facebook 商務頁面匯入 Office 365 的程序。</span><span class="sxs-lookup"><span data-stu-id="ec51b-185">After you successfully complete this step, the Office 365 Import service will start the process of importing data from your Facebook Business pages to Office 365.</span></span> 

<span data-ttu-id="ec51b-186">如需逐步指示，請參閱 <<c0>設定安全性 &amp; 合規性中心中的自訂連接器。</span><span class="sxs-lookup"><span data-stu-id="ec51b-186">For step-by-step instructions, see [Set up a custom connector in the Security & Compliance Center](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center).</span></span> 

<span data-ttu-id="ec51b-187">期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成步驟之後，您已複製到文字檔案）。</span><span class="sxs-lookup"><span data-stu-id="ec51b-187">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="ec51b-188">Azure 應用程式服務的 URL (取得在步驟 4; 例如https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="ec51b-188">Azure app service URL (obtained in Step 4; for example https://fbconnector.azurewebsites.net)</span></span>
- <span data-ttu-id="ec51b-189">APISecretKey （，您在步驟 4 中建立）</span><span class="sxs-lookup"><span data-stu-id="ec51b-189">APISecretKey (that you created in Step 4)</span></span>
