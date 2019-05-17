---
title: 使用範例連接器，來封存 Twitter 資料在 Office 365 （預覽）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 系統管理員可以設定原生連接器 Twitter 資料匯入至 Office 365。 這可讓您封存在 Office 365 中的協力廠商資料來源中的資料，所以您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理貴組織的協力廠商資料的控管。
ms.openlocfilehash: b561c5f471988e567624b49475bbf24a6dd88a2a
ms.sourcegitcommit: 5bd7a97aeab1c89e0a3660ba7bdb3200224107a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2019
ms.locfileid: "34103848"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a><span data-ttu-id="95287-104">使用範例連接器，來封存 Twitter 資料在 Office 365 （預覽）</span><span class="sxs-lookup"><span data-stu-id="95287-104">Use a sample connector to archive Twitter data in Office 365 (Preview)</span></span>

<span data-ttu-id="95287-105">若要封存 Twitter Office 365 中的資料的範例連接器功能是在預覽。</span><span class="sxs-lookup"><span data-stu-id="95287-105">The sample connector feature to archive Twitter data in Office 365 is in Preview.</span></span>

<span data-ttu-id="95287-106">使用安全性 & 在 Office 365 規範中心中的範例連接器，來匯入及封存資料從 Twitter。</span><span class="sxs-lookup"><span data-stu-id="95287-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from Twitter.</span></span> <span data-ttu-id="95287-107">設定後，當您設定範例連接器時，它連線到您的組織 Twitter 帳戶 （按照排程）、 將項目的內容轉換成電子郵件訊息的格式，並再將這些項目匯入至 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="95287-107">After you set up and configure a sample connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="95287-108">在匯入 Twitter 資料之後，您可以套用 Office 365 符合性功能，例如訴訟暫止狀態，內容搜尋，就地封存、 稽核、 監督，與 Office 365 保留原則至信箱中所儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="95287-108">After Twitter data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="95287-109">例如，您可以搜尋使用內容搜尋的協力廠商資料，或其關聯 custodian 進階電子文件探索案例中。</span><span class="sxs-lookup"><span data-stu-id="95287-109">For example,you can search third-party data using Content Search or associate it with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="95287-110">匯入和封存 Twitter 資料 Office 365 中的使用範例連接器，可協助組織符合規範與政府法規的原則。</span><span class="sxs-lookup"><span data-stu-id="95287-110">Using sample connectors to import and archive Twitter data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="95287-111">目前，只有 Twitter 和[Facebook 商務頁面](archive-facebook-data-with-sample-connector.md)的範例連接器可供預覽。</span><span class="sxs-lookup"><span data-stu-id="95287-111">Currently, only the sample connectors for Twitter and [Facebook Business pages](archive-facebook-data-with-sample-connector.md) are available for Preview.</span></span> <span data-ttu-id="95287-112">更多範例連接器即將推出。</span><span class="sxs-lookup"><span data-stu-id="95287-112">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="95287-113">Twitter 設定連接器的必要條件</span><span class="sxs-lookup"><span data-stu-id="95287-113">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="95287-114">您可以設定與設定安全性 & 匯入和封存資料從您的組織 Twitter 帳戶的合規性中心中的範例連接器之前，您必須完成下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="95287-114">You must complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Twitter account.</span></span> 

- <span data-ttu-id="95287-115">您需要 Twitter 帳戶為您的組織;您需要設定連接器時，登入到這個帳戶。</span><span class="sxs-lookup"><span data-stu-id="95287-115">You need a Twitter account for your organization; you'll need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="95287-116">您的組織必須具有有效的 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="95287-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="95287-117">如果您沒有現有的 Azure 訂用帳戶，您可以註冊其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="95287-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="95287-118">註冊免費 1 年 Azure 訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="95287-118">Sign up for a free 1 year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="95287-119">註冊 Pay-As-You-Go Azure 訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="95287-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="95287-120">已內含於您的 Office 365 訂閱的[免費的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)不支援的範例連接器中安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="95287-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="95287-121">您的組織必須同意允許存取您組織中的信箱資料的 Office 365 匯入服務。</span><span class="sxs-lookup"><span data-stu-id="95287-121">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="95287-122">若要同意這項要求，請移到[此頁面上](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，登入的 Office 365 全域管理員認證，並接受要求。</span><span class="sxs-lookup"><span data-stu-id="95287-122">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="95287-123">設定安全性 & 合規性 （步驟 7) 中的自訂連接器的使用者必須獲指派信箱匯入匯出角色在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95287-123">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="95287-124">根據預設，此角色不指派給任何角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95287-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="95287-125">您可以新增 「 信箱匯入 / 匯出 」 角色給組織管理角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95287-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="95287-126">或者，您可以建立新的角色群組、 指派 「 信箱匯入 / 匯出 」 角色，並再將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="95287-126">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="95287-127">如需詳細資訊，請參閱 < 文件中的<b0>建立角色群組</b0>或<b1>修改角色群組</b1>區段 」 管理角色群組在 Exchange Online 」。</span><span class="sxs-lookup"><span data-stu-id="95287-127">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="95287-128">步驟 1： 從 Github 下載預先內建的連接器應用程式套件</span><span class="sxs-lookup"><span data-stu-id="95287-128">Step 1: Download the pre-built connector app package from Github</span></span>

<span data-ttu-id="95287-129">第一個步驟是下載 Twitter 範例連接器應用程式將用來連線到您的 Twitter 帳戶，並擷取資料，因此您可以將它匯入 Office 365 的 Twitter API 的程式碼。</span><span class="sxs-lookup"><span data-stu-id="95287-129">The first step is to download the source code for the Twitter sample connector app that will use a Twitter API to connect to your Twitter account and extract data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="95287-130">移至[這個 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="95287-130">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="95287-131">[最新版本中，按一下 [ **SampleConnector.zip**檔案。</span><span class="sxs-lookup"><span data-stu-id="95287-131">Under the latest release, click the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="95287-132">ZIP 檔案儲存到您本機電腦上的位置。</span><span class="sxs-lookup"><span data-stu-id="95287-132">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="95287-133">您將此 zip 檔案上傳到步驟 4 中的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="95287-133">You'll upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="95287-134">步驟 2： 在 Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="95287-134">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="95287-135">下一步是註冊新的應用程式在 Azure Active Directory (AAD)。</span><span class="sxs-lookup"><span data-stu-id="95287-135">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="95287-136">此應用程式將會對應至將在步驟 4 中 Twitter 連接器實作的 web 應用程式資源。</span><span class="sxs-lookup"><span data-stu-id="95287-136">This app will correspond to the web app resource that you'll implement in Step 4 for the Twitter connector.</span></span> 

<span data-ttu-id="95287-137">如需逐步指示，請參閱[步驟 2： 在 Azure Active Directory 中建立的應用程式](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="95287-137">For step-by-step instructions, see [Step 2: Create an app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="95287-138">期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。</span><span class="sxs-lookup"><span data-stu-id="95287-138">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="95287-139">在部署程序稍後步驟，就會使用這些值。</span><span class="sxs-lookup"><span data-stu-id="95287-139">The values for these will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="95287-140">AAD 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="95287-140">AAD application ID</span></span>
- <span data-ttu-id="95287-141">AAD 應用程式密碼</span><span class="sxs-lookup"><span data-stu-id="95287-141">AAD application secret</span></span>
- <span data-ttu-id="95287-142">AAD 應用程式的 Uri</span><span class="sxs-lookup"><span data-stu-id="95287-142">AAD application Uri</span></span>
- <span data-ttu-id="95287-143">租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="95287-143">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="95287-144">步驟 3： 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="95287-144">Step 3: Create an Azure storage account</span></span>

<span data-ttu-id="95287-145">為貴組織部署 Twitter 連接器將上傳您在此步驟中建立的 Azure 儲存體位置從 Twitter 的項目。</span><span class="sxs-lookup"><span data-stu-id="95287-145">The Twitter connector that you deploy for your organization will upload the items from Twitter to the Azure storage location that you create in this step.</span></span> <span data-ttu-id="95287-146">在安全性 & （在步驟 7) 的合規性中心建立自訂連接器之後，Office 365 匯入服務將 Twitter 將資料複製從 Azure 儲存體位置到 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="95287-146">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Twitter data from the Azure storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="95287-147">如同先前所述[的必要條件](#prerequisites-for-setting-up-a-connector-for-twitter)] 區段中，您必須建立 Azure 儲存體帳戶的有效 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="95287-147">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure storage account.</span></span>

<span data-ttu-id="95287-148">如需逐步指示，請參閱[步驟 3： 建立 Azure 儲存體帳戶](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="95287-148">For step-by-step instructions, see [Step 3: Create an Azure storage account](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="95287-149">完成此步驟中 （藉由遵循的逐步指示） 的期間，您將儲存的連線字串產生的 Uri。</span><span class="sxs-lookup"><span data-stu-id="95287-149">During the completion of this step (by following the step-by-step instructions) you'll save the connection string Uri that is generated.</span></span> <span data-ttu-id="95287-150">在步驟 4 中的 Azure 中建立 web 應用程式資源時，您將使用此字串。</span><span class="sxs-lookup"><span data-stu-id="95287-150">You'll use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="95287-151">步驟 4： 在 Azure 中建立 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="95287-151">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="95287-152">下一步是在 Azure 中建立 web 應用程式資源 Twitter 連接器。</span><span class="sxs-lookup"><span data-stu-id="95287-152">The next step is to create a web app resource in Azure for the Twitter connector.</span></span> 

<span data-ttu-id="95287-153">如需逐步指示，請參閱[步驟 4： 在 Azure 中建立新的 web 應用程式資源](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)。</span><span class="sxs-lookup"><span data-stu-id="95287-153">For step-by-step instructions, see [Step 4: Create a new web app resource in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="95287-154">期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （完成上述步驟之後，您已複製到文字檔案） 時建立的 web 應用程式資源。</span><span class="sxs-lookup"><span data-stu-id="95287-154">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="95287-155">APISecretKey – 您會在完成此步驟中; 的期間建立此密碼步驟 7 中，將使用它。</span><span class="sxs-lookup"><span data-stu-id="95287-155">APISecretKey – You will create this secret during the completion of this step; it will be used in Step 7.</span></span>
- <span data-ttu-id="95287-156">StorageAccountConnectionString – 您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri 的連接字串。</span><span class="sxs-lookup"><span data-stu-id="95287-156">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>
- <span data-ttu-id="95287-157">tenantId – 您在步驟 2 中的 Azure Active Directory 中建立 Twitter 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="95287-157">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="95287-158">此外，您會在此步驟中部署 Twitter 連接器應用程式的原始碼上載 SampleConnector.zip （下載檔案，您在步驟 1 中）。</span><span class="sxs-lookup"><span data-stu-id="95287-158">Additionally, you will upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Twitter connector app.</span></span>

<span data-ttu-id="95287-159">之後完成此步驟，請務必要複製之 Azure 應用程式服務 URL (例如， https://twitterconnector.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="95287-159">After completing this step, be sure to copy the Azure app service URL (for example, https://twitterconnector.azurewebsites.net).</span></span> <span data-ttu-id="95287-160">您將需要使用此功能來完成步驟 5、 步驟 6 和步驟 7）。</span><span class="sxs-lookup"><span data-stu-id="95287-160">You'll need to use this to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-create-developer-app-on-twitter"></a><span data-ttu-id="95287-161">步驟 5： 在 Twitter 上建立開發人員應用程式</span><span class="sxs-lookup"><span data-stu-id="95287-161">Step 5: Create developer app on Twitter</span></span>

<span data-ttu-id="95287-162">下一步是建立和設定的應用程式開發人員在 Twitter 上。</span><span class="sxs-lookup"><span data-stu-id="95287-162">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="95287-163">您在步驟 7 中建立的自訂連接器會使用 Twitter 應用程式互動 Twitter API 以取得資料從您的組織 Twitter 帳戶。</span><span class="sxs-lookup"><span data-stu-id="95287-163">The custom connector that you create in Step 7 will use the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="95287-164">如需逐步指示，請參閱[步驟 5： 建立 Twitter 應用程式](deploy-twitter-connector.md#step-5-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="95287-164">For step-by-step instructions, see [Step 5: Create the Twitter app](deploy-twitter-connector.md#step-5-create-the-twitter-app).</span></span>

<span data-ttu-id="95287-165">期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。</span><span class="sxs-lookup"><span data-stu-id="95287-165">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="95287-166">這些值會用於步驟 6 中設定 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="95287-166">The values for these will be used to configure the Twitter connector app in Step 6.</span></span>

- <span data-ttu-id="95287-167">在 twitter 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="95287-167">Twitter application ID</span></span>
- <span data-ttu-id="95287-168">在 twitter 應用程式密碼 （API 祕密金鑰）</span><span class="sxs-lookup"><span data-stu-id="95287-168">Twitter application secret (API secret key)</span></span>
- <span data-ttu-id="95287-169">在 twitter 用戶端權杖</span><span class="sxs-lookup"><span data-stu-id="95287-169">Twitter client token</span></span>
- <span data-ttu-id="95287-170">Twitter 語彙基元的用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="95287-170">Twitter client token secret</span></span>

## <a name="step-6-configure-the-twitter-connector-app"></a><span data-ttu-id="95287-171">步驟 6： 設定 Twitter 連接器應用程式</span><span class="sxs-lookup"><span data-stu-id="95287-171">Step 6: Configure the Twitter connector app</span></span>

<span data-ttu-id="95287-172">下一步是將組態設定新增至您上傳時您在步驟 4 中建立 Azure 的 web 應用程式資源 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="95287-172">The next step is to add configurations settings to the Twitter connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="95287-173">您將移至您的連接器應用程式的 [首頁] 頁面上，並設定其來這麼做。</span><span class="sxs-lookup"><span data-stu-id="95287-173">You'll do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="95287-174">如需逐步指示，請參閱[步驟 6： 設定連接器的 web 應用程式](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="95287-174">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="95287-175">期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成上述步驟之後，您已複製到文字檔案）：</span><span class="sxs-lookup"><span data-stu-id="95287-175">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="95287-176">在 twitter 應用程式識別碼 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="95287-176">Twitter application ID (obtained in Step 5)</span></span>
- <span data-ttu-id="95287-177">在 twitter 應用程式密碼 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="95287-177">Twitter application secret (obtained in Step 5)</span></span>
- <span data-ttu-id="95287-178">在 twitter 用戶端語彙基元 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="95287-178">Twitter client token (obtained in Step 5)</span></span>
- <span data-ttu-id="95287-179">在 twitter 用戶端 token 密碼 （在步驟 5 中所取得）</span><span class="sxs-lookup"><span data-stu-id="95287-179">Twitter client token secret (obtained in Step 5)</span></span>
- <span data-ttu-id="95287-180">Azure Active Directory 應用程式識別碼 （在步驟 2 中所取得的 AAD 應用程式識別碼）</span><span class="sxs-lookup"><span data-stu-id="95287-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="95287-181">Azure Active Directory 應用程式密碼 （在步驟 2 中所取得的 AAD 應用程式密碼）</span><span class="sxs-lookup"><span data-stu-id="95287-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="95287-182">Azure Active Directory 應用程式的 Uri (AAD 應用程式的 Uri 取得在步驟 2; 例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span><span class="sxs-lookup"><span data-stu-id="95287-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="95287-183">步驟 7： 設立安全性 & 合規性中心中的自訂連接器</span><span class="sxs-lookup"><span data-stu-id="95287-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="95287-184">最後一個步驟是設定安全性 & 會從資料匯入您的組織 Twitter 帳戶指定的信箱，Office 365 中的規範中心中的自訂連接器。</span><span class="sxs-lookup"><span data-stu-id="95287-184">The final step is to set up the custom connector in the Security & Compliance Center that will import data from your organization's Twitter account to a specified mailbox in Office 365.</span></span> <span data-ttu-id="95287-185">您已成功完成此步驟之後，Office 365 匯入服務會啟動將資料從 Twitter 匯入 Office 365 的程序。</span><span class="sxs-lookup"><span data-stu-id="95287-185">After you successfully complete this step, the Office 365 Import service will start the process of importing data from Twitter to Office 365.</span></span> 

<span data-ttu-id="95287-186">如需逐步指示，請參閱[步驟 7： 設定安全性與合規性中心中的自訂連接器](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="95287-186">For step-by-step instructions, see [Step 7: Set up a custom connector in the security and compliance center](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center).</span></span> 

<span data-ttu-id="95287-187">期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成步驟之後，您已複製到文字檔案）。</span><span class="sxs-lookup"><span data-stu-id="95287-187">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="95287-188">Azure 應用程式服務的 URL (取得在步驟 4; 例如https://twitterconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="95287-188">Azure app service URL (obtained in Step 4; for example https://twitterconnector.azurewebsites.net)</span></span>
- <span data-ttu-id="95287-189">APISecretKey （，您在步驟 4 中建立）</span><span class="sxs-lookup"><span data-stu-id="95287-189">APISecretKey (that you created in Step 4)</span></span>
