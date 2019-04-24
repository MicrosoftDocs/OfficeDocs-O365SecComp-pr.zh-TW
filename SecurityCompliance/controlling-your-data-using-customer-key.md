---
title: 使用客戶金鑰控制 Office 365 中的資料
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: 了解如何設定客戶金鑰的 Office 365 的 Exchange Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive。 使用客戶金鑰，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。
ms.openlocfilehash: 219ddb94727cd2b708f734a77a8397b3bc3f1064
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258351"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="b1281-104">使用客戶金鑰控制 Office 365 中的資料</span><span class="sxs-lookup"><span data-stu-id="b1281-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="b1281-105">使用客戶金鑰，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b1281-105">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="b1281-106">換句話說，客戶金鑰可讓客戶將使用其機碼，所屬的加密層。</span><span class="sxs-lookup"><span data-stu-id="b1281-106">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="b1281-107">存放的資料包括 Exchange Online 資料和儲存在信箱的商務用 Skype 資料，以及儲存在 SharePoint Online 中和商務用 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="b1281-107">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="b1281-108">您可以使用客戶金鑰的 Office 365 之前，您必須先設定 Azure。</span><span class="sxs-lookup"><span data-stu-id="b1281-108">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="b1281-109">本主題說明您必須建立及設定所需的 Azure 資源遵循的步驟，並接著設定 Office 365 中的客戶金鑰提供的步驟。</span><span class="sxs-lookup"><span data-stu-id="b1281-109">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="b1281-110">完成 Azure 的安裝程式之後，您可以判斷哪個原則，因此，哪一個機碼，將指派給信箱和您的組織中的檔案。</span><span class="sxs-lookup"><span data-stu-id="b1281-110">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="b1281-111">信箱及未將指派原則的檔案會使用加密原則控制並由 Microsoft 管理。</span><span class="sxs-lookup"><span data-stu-id="b1281-111">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="b1281-112">如需有關客戶金鑰或的一般概觀，請參閱[Office 365 常見問題集的客戶金鑰](service-encryption-with-customer-key-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="b1281-112">For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1281-113">我們強烈建議您遵循本主題中的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="b1281-113">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="b1281-114">這些稱為**提示**和**重要**。</span><span class="sxs-lookup"><span data-stu-id="b1281-114">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="b1281-115">客戶金鑰可讓您控制其範圍可以是高達整個組織的根加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-115">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="b1281-116">這表示與這些機碼所產生的錯誤造成廣泛的影響，而且可能會造成服務中斷或冒用您的資料遺失。</span><span class="sxs-lookup"><span data-stu-id="b1281-116">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="b1281-117">開始之前設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-117">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="b1281-118"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-118"></span></span>

<span data-ttu-id="b1281-119">在您開始之前，先確認您有適當的授權為您的組織。</span><span class="sxs-lookup"><span data-stu-id="b1281-119">Before you get started, be sure you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="b1281-120">在 Office 365 中的客戶金鑰是 Office 365 E5 或進階合規性 SKU 中提供。</span><span class="sxs-lookup"><span data-stu-id="b1281-120">Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="b1281-121">接著，若要了解概念與本主題中的程序，您應檢閱[Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文件。</span><span class="sxs-lookup"><span data-stu-id="b1281-121">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation.</span></span> <span data-ttu-id="b1281-122">此外，熟悉 Azure，例如，[租用戶](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)中所用詞彙。</span><span class="sxs-lookup"><span data-stu-id="b1281-122">Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="b1281-123">客戶金鑰，包括文件中，提供意見反應傳送您的意見、 建議和觀點來看給 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b1281-123">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="b1281-124">設定 Office 365 客戶金鑰的概觀</span><span class="sxs-lookup"><span data-stu-id="b1281-124">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="b1281-125"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-125"></span></span>

<span data-ttu-id="b1281-126">若要設定客戶金鑰您將會完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="b1281-126">To set up Customer Key you will complete these tasks.</span></span> <span data-ttu-id="b1281-127">本主題的其餘部分提供每個任務或參閱程序中每個步驟的詳細資訊的連結的詳細的指示。</span><span class="sxs-lookup"><span data-stu-id="b1281-127">The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="b1281-128">**Azure 和 Microsoft FastTrack： 中**</span><span class="sxs-lookup"><span data-stu-id="b1281-128">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="b1281-129">您將會透過遠端連線到 Azure PowerShell 完成大部分的這些工作。</span><span class="sxs-lookup"><span data-stu-id="b1281-129">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="b1281-130">為了獲得最佳結果，使用版本 4.4.0 或更新版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1281-130">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="b1281-131">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="b1281-131">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="b1281-132">註冊 Azure 訂用帳戶使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="b1281-132">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="b1281-133">註冊可能需要一至五個工作天。</span><span class="sxs-lookup"><span data-stu-id="b1281-133">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="b1281-134">將要求提交至 Office 365 啟用客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-134">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="b1281-135">一旦您已經建立兩個新的 Azure 訂閱，您需要完成裝載於 Microsoft FastTrack 入口網站 web 表單送出適當的客戶金鑰提供要求。</span><span class="sxs-lookup"><span data-stu-id="b1281-135">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="b1281-136">**FastTrack 小組不會使用客戶金鑰提供協助。Office 只使用 FastTrack 入口網站，讓您將表單送出，並協助我們的客戶金鑰追蹤相關提供**。</span><span class="sxs-lookup"><span data-stu-id="b1281-136">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="b1281-137">一旦您已經提交客戶金鑰提供的功能，Microsoft 檢閱您的要求，並通知您，當您可以繼續進行其餘的設定工作。</span><span class="sxs-lookup"><span data-stu-id="b1281-137">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks.</span></span> <span data-ttu-id="b1281-138">此程序可能需要多達五個工作天。</span><span class="sxs-lookup"><span data-stu-id="b1281-138">This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="b1281-139">在每個訂閱中建立 Azure 金鑰保存庫進階版</span><span class="sxs-lookup"><span data-stu-id="b1281-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="b1281-140">將權限指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="b1281-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="b1281-141">啟用，並確認虛刪除上您金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="b1281-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="b1281-142">索引鍵新增至每個金鑰保存庫是藉由建立或匯入金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="b1281-143">請檢查您的金鑰的復原層級</span><span class="sxs-lookup"><span data-stu-id="b1281-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="b1281-144">備份的 Azure 金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="b1281-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="b1281-145">驗證 Azure Key Vault 組態設定</span><span class="sxs-lookup"><span data-stu-id="b1281-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="b1281-146">取得每一個 Azure Key Vault 機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="b1281-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="b1281-147">**在 Office 365:**</span><span class="sxs-lookup"><span data-stu-id="b1281-147">**In Office 365:**</span></span>
  
<span data-ttu-id="b1281-148">Exchange Online 和商務用 Skype:</span><span class="sxs-lookup"><span data-stu-id="b1281-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="b1281-149">建立資料加密原則 (DEP) 以用於 Exchange Online 與 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1281-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="b1281-150">將 DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="b1281-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="b1281-151">驗證信箱加密</span><span class="sxs-lookup"><span data-stu-id="b1281-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="b1281-152">SharePoint Online 和商務用 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="b1281-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="b1281-153">建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置</span><span class="sxs-lookup"><span data-stu-id="b1281-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="b1281-154">驗證群組網站、 小組網站和商務用 OneDrive 的加密</span><span class="sxs-lookup"><span data-stu-id="b1281-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="b1281-155">在完成工作 Azure 金鑰保存庫和 Microsoft FastTrack 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="b1281-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-156"></span></span>

<span data-ttu-id="b1281-157">在完成這些工作 Azure 金鑰保存庫以設定 Office 365 客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-157">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365.</span></span> <span data-ttu-id="b1281-158">您必須完成這些步驟，不論是否您想要設定客戶金鑰的 Exchange Online 與 Skype for Business 或 SharePoint Online 和 OneDrive 商務或 Office 365 中的所有支援服務。</span><span class="sxs-lookup"><span data-stu-id="b1281-158">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="b1281-159">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="b1281-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="b1281-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-160"></span></span>

<span data-ttu-id="b1281-161">兩個 Azure 訂用帳戶所需的客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-161">Two Azure subscriptions are required for Customer Key.</span></span> <span data-ttu-id="b1281-162">最佳作法是，Microsoft 建議您建立新 Azure 訂用帳戶使用使用客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-162">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="b1281-163">Azure Key Vault 機碼僅可以授權中相同的 Azure Active Directory (AAD) 租用戶的應用程式，您必須建立新的訂用帳戶使用相同 Azure AD 租用戶搭配 Office 365 組織 DEPs 將被指派。</span><span class="sxs-lookup"><span data-stu-id="b1281-163">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned.</span></span> <span data-ttu-id="b1281-164">例如，使用 Office 365 組織中具備全域系統管理員權限您公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1281-164">For example, using your work or school account that has global administrator privileges in your Office 365 organization.</span></span> <span data-ttu-id="b1281-165">如需詳細步驟，請參閱[註冊為組織的 Azure](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="b1281-165">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1281-166">客戶金鑰需要兩個機碼，針對每個資料加密原則 (DEP)。</span><span class="sxs-lookup"><span data-stu-id="b1281-166">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="b1281-167">若要達成這個目的，您必須建立兩個 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1281-167">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="b1281-168">最佳作法是，Microsoft 建議您有一個索引鍵設定每個訂閱中組織的個別成員。</span><span class="sxs-lookup"><span data-stu-id="b1281-168">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="b1281-169">此外，這些 Azure 訂用帳戶應該只用於 Office 365 管理加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-169">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="b1281-170">這會保護您的組織，以防您運算子的其中一個不小心、 刻意，或惡意刪除或否則 mismanages 他們所負責的機碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-170">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="b1281-171">我們建議您設定新的 Azure 訂閱僅用於使用客戶金鑰管理 Azure Key Vault 資源使用。</span><span class="sxs-lookup"><span data-stu-id="b1281-171">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="b1281-172">沒有任何實用的限制，您可以建立您組織的 Azure 訂用帳戶的數目。</span><span class="sxs-lookup"><span data-stu-id="b1281-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="b1281-173">遵循這些最佳作法將最小化人為錯誤的影響同時來管理客戶金鑰所使用的資源可協助。</span><span class="sxs-lookup"><span data-stu-id="b1281-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="b1281-174">將要求提交至 Office 365 啟用客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="b1281-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-175"></span></span>

<span data-ttu-id="b1281-176">一旦您已完成的 Azure 的步驟，您需要提供中提交要求[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="b1281-176">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="b1281-177">一旦您已經提交要求透過 FastTrack 的入口網站，Microsoft 會驗證 Azure Key Vault 組態資料和連絡人您所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="b1281-177">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="b1281-178">您在您有關授權主管的優惠表單所做的選擇是組織的要徑和必要的客戶金鑰註冊完成。</span><span class="sxs-lookup"><span data-stu-id="b1281-178">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="b1281-179">您在表單中選取您組織的主管會用來確定任何要求撤銷並銷毀客戶金鑰資料加密原則搭配使用的所有金鑰的授權。</span><span class="sxs-lookup"><span data-stu-id="b1281-179">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="b1281-180">您需要 Exchange Online 和商務用 Skype 商務涵蓋範圍與第二次若要啟動的 SharePoint Online 和商務用 OneDrive 的客戶金鑰啟用客戶金鑰執行一次此步驟。</span><span class="sxs-lookup"><span data-stu-id="b1281-180">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="b1281-181">若要提交啟動客戶金鑰供應項目，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b1281-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="b1281-182">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，登入[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="b1281-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="b1281-183">一旦您登入，瀏覽至**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="b1281-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="b1281-184">選擇 [**提供**，並檢閱目前提供的清單。</span><span class="sxs-lookup"><span data-stu-id="b1281-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="b1281-185">選擇 [**了解更多**適用於您的提供：</span><span class="sxs-lookup"><span data-stu-id="b1281-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="b1281-186">**Exchange Online 和商務用 Skype:\*\*\*\*Exchange 的客戶金鑰**優惠上選擇 [**了解更多**]。</span><span class="sxs-lookup"><span data-stu-id="b1281-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="b1281-187">**SharePoint Online 和商務用 OneDrive:** 選擇**更了解**在**SharePoint 和商務用 OneDrive 的客戶金鑰**優惠。</span><span class="sxs-lookup"><span data-stu-id="b1281-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="b1281-188">在 [**提供詳細資料**] 頁面上，選擇 [**建立要求**。</span><span class="sxs-lookup"><span data-stu-id="b1281-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="b1281-189">填寫所有適用的詳細資訊以及提供表單上的要求的資訊。</span><span class="sxs-lookup"><span data-stu-id="b1281-189">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="b1281-190">請特別注意哪些人員的您選擇貴組織要授權核准永久和不能復原損毀的加密金鑰和資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-190">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="b1281-191">當您完成表單時，選擇 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="b1281-191">Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="b1281-192">此程序可能需要多達五個工作天後已經被 Microsoft 通知您的要求。</span><span class="sxs-lookup"><span data-stu-id="b1281-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="b1281-193">仍繼續前往強制保留期間下一節。</span><span class="sxs-lookup"><span data-stu-id="b1281-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="b1281-194">註冊 Azure 訂用帳戶使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="b1281-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="b1281-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-195"></span></span>

<span data-ttu-id="b1281-196">暫時性或永久性遺失根加密金鑰可以是干擾或甚至重大服務作業，而且可能會導致資料遺失。</span><span class="sxs-lookup"><span data-stu-id="b1281-196">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="b1281-197">基於這個理由，使用客戶金鑰時所用的資源會需要加強保護。</span><span class="sxs-lookup"><span data-stu-id="b1281-197">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="b1281-198">當您使用客戶金鑰的所有 Azure 資源提供的保護機制以外的預設設定。</span><span class="sxs-lookup"><span data-stu-id="b1281-198">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="b1281-199">Azure 訂用帳戶可以標記或的方式，可防止即時和冒用取消註冊。</span><span class="sxs-lookup"><span data-stu-id="b1281-199">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="b1281-200">這稱為 「 註冊強制保留期間內 」。</span><span class="sxs-lookup"><span data-stu-id="b1281-200">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="b1281-201">若要在強制保留期間內註冊 Azure 訂用帳戶所需的步驟需要與 Office 365 小組共同作業。</span><span class="sxs-lookup"><span data-stu-id="b1281-201">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team.</span></span> <span data-ttu-id="b1281-202">此程序可能需要一至五個工作天。</span><span class="sxs-lookup"><span data-stu-id="b1281-202">This process can take from one to five business days.</span></span> <span data-ttu-id="b1281-203">先前，這是有時稱為 「 不取消 」。</span><span class="sxs-lookup"><span data-stu-id="b1281-203">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="b1281-204">再連絡 Office 365 小組，您必須執行下列步驟，每個 Azure 訂用帳戶，您使用客戶金鑰：</span><span class="sxs-lookup"><span data-stu-id="b1281-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="b1281-205">登入您使用 Azure PowerShell 的 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1281-205">Log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="b1281-206">如需相關指示，請參閱[登入 Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b1281-206">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="b1281-207">執行登錄 AzureRmProviderFeature cmdlet 來註冊您的訂閱使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="b1281-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="b1281-208">請連絡 Microsoft 以已完成的程序。</span><span class="sxs-lookup"><span data-stu-id="b1281-208">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="b1281-209">SharePoint 和 OneDrive for Business 小組，請連絡[spock@microsoft.com](mailto:spock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b1281-209">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="b1281-210">Exchange Online 和商務用 Skype，請連絡[exock@microsoft.com](mailto:exock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b1281-210">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="b1281-211">服務層級協議 (SLA) 完成此程序是五個工作天後 Microsoft 已收到通知 （及驗證），您已經註冊您的訂閱使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="b1281-211">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="b1281-212">在您的電子郵件中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="b1281-212">Include the following in your email:</span></span>
    
    <span data-ttu-id="b1281-213">**主旨**： 客戶金鑰\<*您的租用戶的完整網域名稱*\></span><span class="sxs-lookup"><span data-stu-id="b1281-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="b1281-214">**Body**： 您想要有強制保留期間完成的訂閱識別碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="b1281-215">一旦您會收到通知 microsoft 註冊完畢，確認您的註冊的狀態執行 Get AzureRmProviderFeature 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="b1281-216">驗證之後 Get AzureRmProviderFeature cmdlet 從**註冊 State**屬性會傳回**已登錄**值，執行下列命令，以完成程序：</span><span class="sxs-lookup"><span data-stu-id="b1281-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="b1281-217">在每個訂閱中建立 Azure 金鑰保存庫進階版</span><span class="sxs-lookup"><span data-stu-id="b1281-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="b1281-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-218"></span></span>

<span data-ttu-id="b1281-219">中[開始使用 Azure 金鑰保存庫](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)]，將引導您完成安裝及啟動 Azure PowerShell，連線至您的 Azure 訂用帳戶、 建立資源群組，和建立金鑰保存庫，在記載的步驟來建立金鑰保存庫資源群組。</span><span class="sxs-lookup"><span data-stu-id="b1281-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="b1281-220">當您建立金鑰保存庫時，您必須選擇 SKU: [標準] 或 [進階版。</span><span class="sxs-lookup"><span data-stu-id="b1281-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="b1281-221">標準 SKU 可讓軟體-沒有任何硬體安全性模組 (HSM) 金鑰保護-受到保護的 Azure Key Vault 機碼和進階版 SKU 可讓 Hsm 用於 Key Vault 機碼的保護。</span><span class="sxs-lookup"><span data-stu-id="b1281-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="b1281-222">客戶金鑰會接受使用任一種 SKU 的金鑰保存庫，但是 Microsoft 強烈建議您使用僅限進階版 SKU。</span><span class="sxs-lookup"><span data-stu-id="b1281-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="b1281-223">作業成本，有兩種類型的索引鍵是相同的因此在成本的唯一差別是每月的每個 HSM 保護索引鍵的成本。</span><span class="sxs-lookup"><span data-stu-id="b1281-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="b1281-224">如需詳細資訊，請參閱[Key Vault 價格](https://azure.microsoft.com/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="b1281-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b1281-225">實際執行資料，請使用進階版 SKU 金鑰保存庫和 HSM 受保護的機碼，然後只使用標準的 SKU 金鑰保存庫和機碼進行測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="b1281-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="b1281-226">每個 Office 365 服務與您會使用客戶金鑰，請建立金鑰保存庫中每個您所建立的兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="b1281-226">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="b1281-227">例如，Exchange Online 和商務用 Skype 僅商務或 SharePoint Online 和僅商務用 OneDrive，您將建立僅有一組的保存庫。</span><span class="sxs-lookup"><span data-stu-id="b1281-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="b1281-228">若要啟用 Exchange Online 和 SharePoint Online 客戶金鑰，您會建立兩組金鑰保存庫。</span><span class="sxs-lookup"><span data-stu-id="b1281-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="b1281-229">使用金鑰保存庫，以反映您將關聯保存庫 DEP 的預定的用法的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="b1281-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="b1281-230">請參閱下方命名慣例建議的最佳作法章節內容。</span><span class="sxs-lookup"><span data-stu-id="b1281-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="b1281-231">建立每個資料加密原則保存庫不同，配對集。</span><span class="sxs-lookup"><span data-stu-id="b1281-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="b1281-232">針對 Exchange Online，會在您選擇的資料加密原則範圍當您將原則指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="b1281-233">信箱可以有指派後，只有一個原則，您可以建立最多了 50 個原則。</span><span class="sxs-lookup"><span data-stu-id="b1281-233">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="b1281-234">SharePoint online 原則範圍是所有地理位置或地理位置中組織內的資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-234">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="b1281-235">建立的金鑰保存庫也需要 Azure 的資源群組，請建立後金鑰保存庫需要儲存容量 （雖然很小） 和記錄，Key Vault 若啟用，也會產生儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="b1281-236">最佳作法是，Microsoft 建議使用不同的系統管理員來管理每個資源群組，以符合一組系統管理員會管理相關的所有客戶金鑰資源管理。</span><span class="sxs-lookup"><span data-stu-id="b1281-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1281-237">若要達到最大的可用性，您金鑰保存庫應該接近您的 Office 365 服務的區域。</span><span class="sxs-lookup"><span data-stu-id="b1281-237">To maximize availability, your key vaults should be in regions close to your Office 365 service.</span></span> <span data-ttu-id="b1281-238">例如，如果您的 Exchange Online 組織位於 「 北美地區 」，請將您金鑰保存庫放在 「 北美地區 」。</span><span class="sxs-lookup"><span data-stu-id="b1281-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="b1281-239">在歐洲 Exchange Online 組織時，將您金鑰保存庫放在 Europe。</span><span class="sxs-lookup"><span data-stu-id="b1281-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="b1281-240">使用共同的前置字元的金鑰保存庫，並加入，所用縮寫和金鑰保存庫和金鑰的範圍 (例如，為保存庫內 「 北美地區 」，名稱可能配對的所在位置的 Contoso SharePoint 服務 Contoso O365SP-NA VaultA1 和Contoso-O365SP-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="b1281-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="b1281-241">儲藏室名稱是在 Azure 中的全域唯一字串，所以您可能需要嘗試變化的您想要的名稱，以防其他 Azure 客戶已宣告的所需的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1281-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="b1281-242">2017 年 7 月起儲藏室名稱無法變更，所以最佳作法是已安裝程式撰寫的計劃，並使用第二個人員若要確認已正確執行計劃。</span><span class="sxs-lookup"><span data-stu-id="b1281-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="b1281-243">如果可能的話，建立您保存庫非成對的區域。</span><span class="sxs-lookup"><span data-stu-id="b1281-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="b1281-244">成對的 Azure 區域服務失敗網域內提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="b1281-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="b1281-245">因此，區域的配對可以視為彼此的備份區域。</span><span class="sxs-lookup"><span data-stu-id="b1281-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="b1281-246">這表示會被放置在一個區域 Azure 資源會自動獲得容錯透過配對區域權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="b1281-247">基於這個理由，選擇區域所在位置，都在使用中的可用性的兩個區域的總計的配對的表示 DEP 中所使用的兩個保存庫的區域。</span><span class="sxs-lookup"><span data-stu-id="b1281-247">For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="b1281-248">大部分的地區只需要兩個區域，因此無法還可以選取 [非成對的區域。</span><span class="sxs-lookup"><span data-stu-id="b1281-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="b1281-249">如果可能，請選擇 [與相依性搭配使用，將兩個保存庫中非成對的兩個區域</span><span class="sxs-lookup"><span data-stu-id="b1281-249">If possible, choose two non-paired regions for the two vaults used with a DEP.</span></span> <span data-ttu-id="b1281-250">這會受益總共四個區域的可用性。</span><span class="sxs-lookup"><span data-stu-id="b1281-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="b1281-251">如需詳細資訊，請參閱[商務持續性與災害復原 (BCDR): Azure 成對區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)的目前區域配對的清單。</span><span class="sxs-lookup"><span data-stu-id="b1281-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="b1281-252">將權限指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="b1281-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="b1281-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-253"></span></span>

<span data-ttu-id="b1281-254">針對每個金鑰保存庫，您必須定義三個不同的客戶金鑰，根據您實作的權限集。</span><span class="sxs-lookup"><span data-stu-id="b1281-254">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="b1281-255">例如，您需要定義一組權限，如下列各項：</span><span class="sxs-lookup"><span data-stu-id="b1281-255">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="b1281-256">**Key vault 系統管理員**將為組織執行日常管理您金鑰保存庫。</span><span class="sxs-lookup"><span data-stu-id="b1281-256">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="b1281-257">這些工作包括備份、 建立、 取得、 匯入清單，以及還原。</span><span class="sxs-lookup"><span data-stu-id="b1281-257">These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b1281-258">權限指派給金鑰保存庫系統管理員不會納入權限可以刪除索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b1281-258">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="b1281-259">這是蓄意和重要的作法。</span><span class="sxs-lookup"><span data-stu-id="b1281-259">This is intentional and an important practice.</span></span> <span data-ttu-id="b1281-260">刪除加密金鑰不通常是，因為這樣永久執行等到資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-260">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="b1281-261">最佳作法是不要不此權限授與金鑰保存庫管理員預設。</span><span class="sxs-lookup"><span data-stu-id="b1281-261">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="b1281-262">相反地，保留這的金鑰保存庫參與者，並只將其指派給短期為基礎的系統管理員一旦清楚了解所造成的影響也了解。</span><span class="sxs-lookup"><span data-stu-id="b1281-262">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="b1281-263">若要將這些權限指派給您的 Office 365 組織中的使用者，登入您使用 Azure PowerShell 的 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1281-263">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="b1281-264">如需相關指示，請參閱[登入 Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b1281-264">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="b1281-265">執行設定 AzureRmKeyVaultAccessPolicy cmdlet 來指派必要權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="b1281-266">例如：</span><span class="sxs-lookup"><span data-stu-id="b1281-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="b1281-267">**Key vault 參與者**可以變更 Azure 金鑰保存庫的權限本身擷取。</span><span class="sxs-lookup"><span data-stu-id="b1281-267">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="b1281-268">您需要變更這些權限，如員工離開或加入您的小組，或在極罕見的情況下，機碼地窖管理員合法需要刪除或還原金鑰的權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-268">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="b1281-269">這組金鑰保存庫參與者需要被授與您金鑰保存庫**參與者**角色。</span><span class="sxs-lookup"><span data-stu-id="b1281-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="b1281-270">您可以使用 Azure Resource Manager 指派此角色。</span><span class="sxs-lookup"><span data-stu-id="b1281-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="b1281-271">如需詳細步驟，請參閱 <<c0>管理 Azure 訂用帳戶資源的存取權的 Use Role-Based 存取控制。</span><span class="sxs-lookup"><span data-stu-id="b1281-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="b1281-272">會建立訂閱的系統管理員存取此以隱含方式，以及將其他系統管理員指派給參與者角色。</span><span class="sxs-lookup"><span data-stu-id="b1281-272">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="b1281-273">如果您想使用客戶金鑰 Exchange Online 與 Skype for Business，您需要的權限授與使用金鑰保存庫代表 Exchange Online 與 Skype for Business 的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b1281-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="b1281-274">同樣地，如果您想使用客戶金鑰 SharePoint Online 和 OneDrive for Business，您需要新增使用金鑰保存庫代表 SharePoint Online 和 OneDrive for Business 的 Office 365 的權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="b1281-275">若要將權限授與 Office 365，執行**組 AzureRmKeyVaultAccessPolicy**指令程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="b1281-275">To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="b1281-276">其中：</span><span class="sxs-lookup"><span data-stu-id="b1281-276">Where:</span></span>
    
  - <span data-ttu-id="b1281-277">*vaultname*是您建立金鑰保存庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1281-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="b1281-278">Exchange Online 和商務用 Skype，取代與*Office 365 appID*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="b1281-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="b1281-279">若是 SharePoint Online 和商務用 OneDrive，取代與*Office 365 appID*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="b1281-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="b1281-280">範例： 設定 Exchange Online 和商務用 Skype 的權限：</span><span class="sxs-lookup"><span data-stu-id="b1281-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="b1281-281">範例： 設定 SharePoint Online 和商務用 OneDrive 的權限</span><span class="sxs-lookup"><span data-stu-id="b1281-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="b1281-282">啟用，並確認虛刪除上您金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="b1281-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="b1281-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-283"></span></span>

<span data-ttu-id="b1281-284">當您可以快速復原您的金鑰時，您的可能性會較經驗延伸的服務中斷因為意外或惡意刪除索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b1281-284">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="b1281-285">您要啟用此設定，稱為 「 虛刪除時，您才能使用您的金鑰使用客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-285">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="b1281-286">啟用虛刪除，可讓您要刪除的 90 天內復原機碼或保存庫，而不必從備份還原。</span><span class="sxs-lookup"><span data-stu-id="b1281-286">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="b1281-287">若要啟用虛刪除您金鑰保存庫，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b1281-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="b1281-288">登入您使用 Windows Powershell 的 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1281-288">Log in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="b1281-289">如需相關指示，請參閱[登入 Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="b1281-289">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="b1281-290">執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b1281-290">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet.</span></span> <span data-ttu-id="b1281-291">在這個範例中， *vaultname*是您要為其啟用虛刪除金鑰保存庫的名稱：</span><span class="sxs-lookup"><span data-stu-id="b1281-291">In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="b1281-292">確認虛刪除執行**Get AzureRmKeyVault**指令程式時，已針對金鑰保存庫。</span><span class="sxs-lookup"><span data-stu-id="b1281-292">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet.</span></span> <span data-ttu-id="b1281-293">虛刪除的設定是否正確的金鑰保存庫，虛刪除已啟用？屬性會傳回**True**值：</span><span class="sxs-lookup"><span data-stu-id="b1281-293">If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="b1281-294">索引鍵新增至每個金鑰保存庫是藉由建立或匯入金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="b1281-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-295"></span></span>

<span data-ttu-id="b1281-296">有兩種方式可將機碼新增至 Azure 金鑰保存庫;您可以直接在金鑰保存庫中建立機碼，或您可以匯入金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-296">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="b1281-297">直接在金鑰保存庫中建立機碼時，若為較複雜的方法，匯入金鑰可讓您總控制如何產生金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-297">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="b1281-298">若要直接在您金鑰保存庫中建立機碼，執行[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="b1281-299">其中：</span><span class="sxs-lookup"><span data-stu-id="b1281-299">Where:</span></span>
  
-  <span data-ttu-id="b1281-300">*vaultname*是您要建立的機碼金鑰保存庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1281-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="b1281-301">*keyname*是您要給新的金鑰的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1281-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b1281-302">使用類似的命名慣例，上面所述的金鑰保存庫名稱機碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="b1281-303">如此一來，在 [顯示機碼名稱的工具，字串自我描述。</span><span class="sxs-lookup"><span data-stu-id="b1281-303">This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="b1281-304">如果您想要保護 HSM 索引鍵，請確定您指定**HSM**作為_目的地_參數值，否則指定**軟體**。</span><span class="sxs-lookup"><span data-stu-id="b1281-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="b1281-305">For example,</span><span class="sxs-lookup"><span data-stu-id="b1281-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="b1281-306">若要直接將您金鑰保存庫，匯入金鑰，您需要有 Thales nShield 硬體安全性模組。</span><span class="sxs-lookup"><span data-stu-id="b1281-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="b1281-307">有些組織偏好使用這個方法可以建立其機碼，與此 provenance 方法也會提供下列：</span><span class="sxs-lookup"><span data-stu-id="b1281-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="b1281-308">用於匯入工具組包含從 Thales 金鑰 Exchange 機碼 (KEK) 是用來加密您產生的機碼不是可匯出的證明，並產生 Thales 已生產正版 HSM 內。</span><span class="sxs-lookup"><span data-stu-id="b1281-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="b1281-309">工具組包含從 Azure Key Vault 安全性世界也已產生上生產 Thales 正版 HSM Thales 證明。</span><span class="sxs-lookup"><span data-stu-id="b1281-309">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="b1281-310">此證明能就能確信您 Microsoft 也使用正版 Thales 硬體。</span><span class="sxs-lookup"><span data-stu-id="b1281-310">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="b1281-311">請與您安全性群組來決定是否需要上述 attestations。</span><span class="sxs-lookup"><span data-stu-id="b1281-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="b1281-312">建立主要內部部署，然後匯入您金鑰保存庫的詳細步驟，請參閱[如何產生，並且傳送 HSM 保護 Azure Key Vault 機碼](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。</span><span class="sxs-lookup"><span data-stu-id="b1281-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="b1281-313">若要在每個金鑰保存庫中建立的機碼中使用 Azure 的指示。</span><span class="sxs-lookup"><span data-stu-id="b1281-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="b1281-314">請檢查您的金鑰的復原層級</span><span class="sxs-lookup"><span data-stu-id="b1281-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="b1281-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-315"></span></span>

<span data-ttu-id="b1281-316">Office 365 需要 Azure Key Vault 訂閱設為不會取消和使用客戶金鑰的機碼已啟用的虛刪除。</span><span class="sxs-lookup"><span data-stu-id="b1281-316">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="b1281-317">您可以透過查看 [您的機碼中的 [復原層級加以確認。</span><span class="sxs-lookup"><span data-stu-id="b1281-317">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="b1281-318">若要檢查的金鑰，請在 Azure PowerShell 復原層級執行 Get AzureKeyVaultKey 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="b1281-319">如果_復原層級_屬性可傳回的值為**復原 + ProtectedSubscription**以外的任何項目，您必須以檢閱本主題，並確認您是否已遵循所有訂閱置於 [不要取消] 清單中的步驟和您必須在每個您金鑰保存庫上啟用的虛刪除。</span><span class="sxs-lookup"><span data-stu-id="b1281-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="b1281-320">備份的 Azure 金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="b1281-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="b1281-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-321"></span></span>

<span data-ttu-id="b1281-322">緊接在建立或變更索引鍵，以執行備份，然後儲存的備份，線上和離線複本。</span><span class="sxs-lookup"><span data-stu-id="b1281-322">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="b1281-323">離線複本應該不連接到任何網路時，例如實體安全或商業儲存體設備中。</span><span class="sxs-lookup"><span data-stu-id="b1281-323">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="b1281-324">至少一份備份應該儲存在發生災害時可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="b1281-324">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="b1281-325">備份 blob 是唯一的還原金鑰內容應該 Key Vault 機碼會永久移除或否則呈現 [無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="b1281-325">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="b1281-326">按鍵的 Azure Key Vault 外部，且匯入至 Azure Key Vault 切勿做為備份，因為若要使用金鑰的客戶金鑰所需的中繼資料與外部索引鍵不存在。</span><span class="sxs-lookup"><span data-stu-id="b1281-326">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="b1281-327">僅備份採取從 Azure 金鑰保存庫可用於還原作業，使用客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-327">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="b1281-328">因此，它是不可或缺的 Azure Key Vault 備份進行後金鑰已上傳或建立。</span><span class="sxs-lookup"><span data-stu-id="b1281-328">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="b1281-329">若要建立 Azure Key Vault 機碼的備份，執行[備份 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="b1281-330">請確定您的輸出檔使用後置`.backup`。</span><span class="sxs-lookup"><span data-stu-id="b1281-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="b1281-331">此指令程式所產生的輸出檔進行加密，並不能使用外部 Azure 金鑰保存庫。</span><span class="sxs-lookup"><span data-stu-id="b1281-331">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="b1281-332">可以從中執行備份的 Azure 訂用帳戶，才能還原備份。</span><span class="sxs-lookup"><span data-stu-id="b1281-332">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="b1281-333">對於輸出檔案中，選擇 [儲藏室名稱和機碼名稱的組合。</span><span class="sxs-lookup"><span data-stu-id="b1281-333">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="b1281-334">這樣會使檔案名稱自我描述。</span><span class="sxs-lookup"><span data-stu-id="b1281-334">This will make the file name self-describing.</span></span> <span data-ttu-id="b1281-335">它也能確保備份的檔案名稱執行動作不會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="b1281-335">It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="b1281-336">例如：</span><span class="sxs-lookup"><span data-stu-id="b1281-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="b1281-337">驗證 Azure Key Vault 組態設定</span><span class="sxs-lookup"><span data-stu-id="b1281-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="b1281-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-338"></span></span>

<span data-ttu-id="b1281-339">執行 DEP 中使用機碼之前的驗證是選擇性作業，但強烈建議。</span><span class="sxs-lookup"><span data-stu-id="b1281-339">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="b1281-340">特別是，如果您使用的步驟來設定您的機碼和保存庫以外，本主題中所述，您應該先驗證您的 Azure Key Vault 資源的健康狀況，再設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-340">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="b1281-341">若要確認您的金鑰已啟用的 get、 wrapKey，以及 unwrapKey 作業：</span><span class="sxs-lookup"><span data-stu-id="b1281-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="b1281-342">執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="b1281-343">在輸出中，尋找適當的存取原則和 Exchange Online 的身分識別 (GUID) 或 SharePoint Online 的身分識別 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="b1281-343">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="b1281-344">所有三個以上的權限必須都顯示權限] 之下，機碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-344">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="b1281-345">如果存取原則設定不正確，請執行組 AzureRmKeyVaultAccessPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="b1281-346">例如，針對 Exchange Online 和商務用 Skype:</span><span class="sxs-lookup"><span data-stu-id="b1281-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="b1281-347">例如，對於 SharePoint Online 和商務用 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="b1281-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="b1281-348">若要確認您執行[Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)指令程式，如下所示的機碼未設定到期日：</span><span class="sxs-lookup"><span data-stu-id="b1281-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="b1281-349">客戶金鑰無法使用過期的索引鍵，並嘗試使用過期的索引鍵的作業會失敗，但可能會造成服務中斷。</span><span class="sxs-lookup"><span data-stu-id="b1281-349">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="b1281-350">我們強烈建議使用客戶金鑰與金鑰沒有到期日。</span><span class="sxs-lookup"><span data-stu-id="b1281-350">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="b1281-351">到期日，一旦設定，不能移除，但是可加以變更至不同的日期。</span><span class="sxs-lookup"><span data-stu-id="b1281-351">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="b1281-352">如果機碼必須使用已設定到期日，請將到期值變更為 12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="b1281-352">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="b1281-353">包含到期日的機碼設為日期以外 12/31/9999 不會通過 Office 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="b1281-353">Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="b1281-354">若要變更已設定為 12/31/9999 以外的任何數值的到期日，執行[組 AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="b1281-355">不在您使用客戶金鑰的加密金鑰設定到期日。</span><span class="sxs-lookup"><span data-stu-id="b1281-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="b1281-356">取得每一個 Azure Key Vault 機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="b1281-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="b1281-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-357"></span></span>

<span data-ttu-id="b1281-358">一旦您已完成設定您金鑰保存庫 Azure 中的所有步驟，並新增您的金鑰，請執行下列命令，以取得每個金鑰保存庫中的索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="b1281-358">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="b1281-359">您將需要使用這些 Uri，當您建立及更新版本中，指派每個 DEP 因此儲存此資訊在安全的地方。</span><span class="sxs-lookup"><span data-stu-id="b1281-359">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="b1281-360">請記得執行此命令一次的每個金鑰保存庫。</span><span class="sxs-lookup"><span data-stu-id="b1281-360">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="b1281-361">在 Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b1281-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b1281-362">Office 365： 客戶金鑰設定 Exchange Online 和商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b1281-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="b1281-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-363"></span></span>

<span data-ttu-id="b1281-364">開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。</span><span class="sxs-lookup"><span data-stu-id="b1281-364">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="b1281-365">如需資訊，請參閱[Azure 金鑰保存庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)。</span><span class="sxs-lookup"><span data-stu-id="b1281-365">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="b1281-366">若要設定 Exchange Online 和商務用 Skype 的客戶金鑰，您必須透過遠端連線到 Exchange Online 使用 Windows PowerShell 執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="b1281-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="b1281-367">建立資料加密原則 (DEP) 以用於 Exchange Online 與 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1281-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="b1281-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-368"></span></span>

<span data-ttu-id="b1281-369">DEP 是一組儲存在 Azure 金鑰保存庫中的機碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="b1281-369">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="b1281-370">您可以指派 DEP 至 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-370">You assign a DEP to a mailbox in Office 365.</span></span> <span data-ttu-id="b1281-371">Office 365 然後會使用該原則中所識別的金鑰來加密信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-371">Office 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="b1281-372">若要建立 DEP，您需要您稍早取得 Key Vault Uri。</span><span class="sxs-lookup"><span data-stu-id="b1281-372">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="b1281-373">如需相關指示，請參閱[Obtain 每一個 Azure Key Vault 機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="b1281-373">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="b1281-374">請記住 ！</span><span class="sxs-lookup"><span data-stu-id="b1281-374">Remember!</span></span> <span data-ttu-id="b1281-375">當您建立 DEP 時，您會指定位於兩個不同的 Azure 金鑰保存庫中的兩個索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b1281-375">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="b1281-376">請確定這些機碼位於兩個不同的 Azure 區域，以確保異地備援。</span><span class="sxs-lookup"><span data-stu-id="b1281-376">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b1281-377">若要建立 DEP，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b1281-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="b1281-378">在您的本機電腦上使用公司或學校帳戶具有 Office 365 組織中，開啟 Windows PowerShell 並執行下列命令[連接至 Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)的全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="b1281-379">在 [Windows PowerShell 認證要求] 對話方塊中，輸入您的工作或學校帳戶資訊、 按一下 [**確定**]，然後輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="b1281-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="b1281-380">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b1281-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="b1281-381">若要建立 DEP，使用新 DataEncryptionPolicy 指令程式輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="b1281-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="b1281-382">其中：</span><span class="sxs-lookup"><span data-stu-id="b1281-382">Where:</span></span>
    
   -  <span data-ttu-id="b1281-383">*PolicyName*是您想要用於此原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1281-383">*PolicyName*  is the name you want to use for the policy.</span></span> <span data-ttu-id="b1281-384">名稱不可包含空格。</span><span class="sxs-lookup"><span data-stu-id="b1281-384">Names cannot contain spaces.</span></span> <span data-ttu-id="b1281-385">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="b1281-385">For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="b1281-386">*PolicyDescription*是可協助您記住原則是針對原則的使用者易記描述。</span><span class="sxs-lookup"><span data-stu-id="b1281-386">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="b1281-387">您可以在描述中包含空格。</span><span class="sxs-lookup"><span data-stu-id="b1281-387">You can include spaces in the description.</span></span> <span data-ttu-id="b1281-388">例如，根機碼 USA 和其領域中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-388">For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="b1281-389">*KeyVaultURI1*是原則中的第一個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="b1281-389">*KeyVaultURI1*  is the URI for the first key in the policy.</span></span> <span data-ttu-id="b1281-390">例如 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="b1281-390">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="b1281-391">*KeyVaultURI2*是原則中的第二個機碼的 URI。</span><span class="sxs-lookup"><span data-stu-id="b1281-391">*KeyVaultURI2*  is the URI for the second key in the policy.</span></span> <span data-ttu-id="b1281-392">例如 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。</span><span class="sxs-lookup"><span data-stu-id="b1281-392">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="b1281-393">分隔兩個 Uri 以逗號和空格。</span><span class="sxs-lookup"><span data-stu-id="b1281-393">Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="b1281-394">範例：</span><span class="sxs-lookup"><span data-stu-id="b1281-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="b1281-395">將 DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="b1281-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="b1281-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-396"></span></span>

<span data-ttu-id="b1281-397">使用 Set-mailbox 指令程式，將 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-397">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="b1281-398">一旦您指派原則時，Office 365 加密，您可以信箱與相依性中所指定的金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-398">Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="b1281-399">其中*MailboxIdParameter*指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-399">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="b1281-400">如需將 Set-mailbox cmdlet 的詳細資訊，請參閱[Set-mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1281-400">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="b1281-401">驗證信箱加密</span><span class="sxs-lookup"><span data-stu-id="b1281-401">Validate mailbox encryption</span></span>
<span data-ttu-id="b1281-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-402"></span></span>

<span data-ttu-id="b1281-403">加密的信箱可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="b1281-403">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="b1281-404">第一次原則指派] 中，針對信箱也之前必須完成從一個資料庫移至另一個服務可以加密信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-404">For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="b1281-405">我們建議您等候 72 小時，再嘗試驗證加密之後變更 DEP 或第一次您指派 DEP 到信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-405">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="b1281-406">使用 Get-mailboxstatistics 指令程式來決定是否信箱已加密。</span><span class="sxs-lookup"><span data-stu-id="b1281-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="b1281-407">如果信箱尚未加密，IsEncrypted 屬性會傳回的值 **，則為 true**如果信箱已加密和**false**值。</span><span class="sxs-lookup"><span data-stu-id="b1281-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="b1281-408">完成信箱移動的時間取決於您所指派的第一次，DEP 的信箱數目，以及信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="b1281-408">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="b1281-409">如果信箱已不加密您指派 DEP 的時間從一週後，請使用 New-moverequest 指令程式起始未加密的信箱的信箱移動。</span><span class="sxs-lookup"><span data-stu-id="b1281-409">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="b1281-410">Office 365： 設定 SharePoint Online 和商務用 OneDrive 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="b1281-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-411"></span></span>

<span data-ttu-id="b1281-412">開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。</span><span class="sxs-lookup"><span data-stu-id="b1281-412">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="b1281-413">如需資訊，請參閱[Azure 金鑰保存庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)。</span><span class="sxs-lookup"><span data-stu-id="b1281-413">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="b1281-414">若要設定客戶金鑰的 SharePoint Online 和商務用 OneDrive，您必須透過遠端連線到 SharePoint Online Windows powershell 執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="b1281-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="b1281-415">建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置</span><span class="sxs-lookup"><span data-stu-id="b1281-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="b1281-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-416"></span></span>

<span data-ttu-id="b1281-417">DEP 是一組儲存在 Azure 金鑰保存庫中的機碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="b1281-417">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="b1281-418">您可以將 DEP 套用至所有您在一個地理位置，也稱為 「 地理位置的資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-418">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="b1281-419">如果您使用 Office 365 的多地理位置功能 （目前處於預覽） 時，您可以建立一個 DEP 每個地理位置。</span><span class="sxs-lookup"><span data-stu-id="b1281-419">If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo.</span></span> <span data-ttu-id="b1281-420">如果您不使用多地理位置，您可以在 Office 365 中建立一個 DEP，以用於 SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="b1281-420">If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="b1281-421">Office 365 然後會使用 DEP 中所識別的金鑰來加密的地理位置中的資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-421">Office 365 will then use the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="b1281-422">若要建立 DEP，您需要您稍早取得 Key Vault Uri。</span><span class="sxs-lookup"><span data-stu-id="b1281-422">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="b1281-423">如需相關指示，請參閱[Obtain 每一個 Azure Key Vault 機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="b1281-423">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="b1281-424">請記住 ！</span><span class="sxs-lookup"><span data-stu-id="b1281-424">Remember!</span></span> <span data-ttu-id="b1281-425">當您建立 DEP 時，您會指定位於兩個不同的 Azure 金鑰保存庫中的兩個索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b1281-425">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="b1281-426">請確定這些機碼位於兩個不同的 Azure 區域，以確保異地備援。</span><span class="sxs-lookup"><span data-stu-id="b1281-426">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b1281-427">若要建立 DEP，您需要使用 Windows PowerShell 從遠端連線至 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="b1281-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="b1281-428">在您的本機電腦上使用公司或學校帳戶具有 Office 365 組織中，[連線到 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)的全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="b1281-429">在 Microsoft SharePoint Online 管理命令介面中，執行[註冊 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="b1281-430">當您註冊 DEP 時，加密會開始於地理位置中的資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-430">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="b1281-431">這可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="b1281-431">This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="b1281-432">驗證群組網站、 小組網站和商務用 OneDrive 的加密</span><span class="sxs-lookup"><span data-stu-id="b1281-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="b1281-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-433"></span></span>

<span data-ttu-id="b1281-434">您可以檢查的加密狀態，藉由執行 Get SPODataEncryptionPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="b1281-435">此 cmdlet 的輸出包含：</span><span class="sxs-lookup"><span data-stu-id="b1281-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="b1281-436">主索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="b1281-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="b1281-437">第二個機碼的 URI。</span><span class="sxs-lookup"><span data-stu-id="b1281-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="b1281-438">地理加密狀態。</span><span class="sxs-lookup"><span data-stu-id="b1281-438">The encryption status for the geo.</span></span> <span data-ttu-id="b1281-439">可能的狀態包括：</span><span class="sxs-lookup"><span data-stu-id="b1281-439">Possible states include:</span></span>
    
  - <span data-ttu-id="b1281-440">**未註冊：** 客戶金鑰加密尚未套用。</span><span class="sxs-lookup"><span data-stu-id="b1281-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="b1281-441">**註冊：** 已套用客戶金鑰加密及加密正在您的檔案。</span><span class="sxs-lookup"><span data-stu-id="b1281-441">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="b1281-442">如果您地理位置是在此狀態下，您將也會顯示資訊上，讓您可以監視加密進度百分比的地理位置中的網站都已完成。</span><span class="sxs-lookup"><span data-stu-id="b1281-442">If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="b1281-443">**註冊：** 已套用客戶金鑰加密，並已加密的所有網站中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="b1281-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="b1281-444">**循環：** 索引鍵 roll 正在進行中。</span><span class="sxs-lookup"><span data-stu-id="b1281-444">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="b1281-445">如果您地理位置是在此狀態下，您將也會顯示資訊上百分比的網站都已完成金鑰 roll 作業，以便您可以監視進度。</span><span class="sxs-lookup"><span data-stu-id="b1281-445">If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="b1281-446">管理 office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="b1281-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-447"></span></span>

<span data-ttu-id="b1281-448">您的 Office 365 設定客戶金鑰之後，您可以執行下列的其他管理工作。</span><span class="sxs-lookup"><span data-stu-id="b1281-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="b1281-449">還原 Azure Key Vault 機碼</span><span class="sxs-lookup"><span data-stu-id="b1281-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="b1281-450">循環或旋轉的機碼中使用客戶金鑰的 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b1281-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="b1281-451">管理金鑰保存庫的權限</span><span class="sxs-lookup"><span data-stu-id="b1281-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="b1281-452">決定指派給信箱 DEP</span><span class="sxs-lookup"><span data-stu-id="b1281-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="b1281-453">還原 Azure Key Vault 機碼</span><span class="sxs-lookup"><span data-stu-id="b1281-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="b1281-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-454"></span></span>

<span data-ttu-id="b1281-455">之前執行還原，請使用虛刪除所提供的復原功能。</span><span class="sxs-lookup"><span data-stu-id="b1281-455">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="b1281-456">當您使用客戶金鑰的所有索引鍵所需已啟用的虛刪除。</span><span class="sxs-lookup"><span data-stu-id="b1281-456">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="b1281-457">虛刪除 bot 資源回收筒，並允許復原 90 天，而不需要還原。</span><span class="sxs-lookup"><span data-stu-id="b1281-457">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="b1281-458">在特殊或不尋常的情況，例如，如果金鑰或金鑰保存庫將會遺失時，應該只需要還原。</span><span class="sxs-lookup"><span data-stu-id="b1281-458">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="b1281-459">如果您必須使用客戶金鑰還原金鑰使用 Azure PowerShell 中執行還原 AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-459">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="b1281-460">例如：</span><span class="sxs-lookup"><span data-stu-id="b1281-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="b1281-461">如果在金鑰保存庫中已經存在具有相同名稱的索引鍵，將會失敗的還原作業。</span><span class="sxs-lookup"><span data-stu-id="b1281-461">If a key with the same name already exists in the key vault, the restore operation will fail.</span></span> <span data-ttu-id="b1281-462">還原 AzureKeyVaultKey 還原所有的主要版本和所有的中繼資料，包括機碼名稱機碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-462">Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="b1281-463">循環或旋轉的機碼中使用客戶金鑰的 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b1281-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="b1281-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-464"></span></span>

<span data-ttu-id="b1281-465">循環機碼，則不需要透過任一 Azure Key Vault 或客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-465">Rolling keys is not required by either Azure Key Vault or by Customer Key.</span></span> <span data-ttu-id="b1281-466">此外，使用 HSM 保護的索引鍵是幾乎不可能危害。</span><span class="sxs-lookup"><span data-stu-id="b1281-466">In addition, keys that are protected with an HSM are virtually impossible to compromise.</span></span> <span data-ttu-id="b1281-467">即使根機碼所擁有的惡意的動作項目中沒有可行的情況下使用它來解密資料，因為只有 Office 365 程式碼知道如何使用它的方法。</span><span class="sxs-lookup"><span data-stu-id="b1281-467">Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it.</span></span> <span data-ttu-id="b1281-468">不過，循環機碼是由支援客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-468">However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b1281-469">僅將清除技術原因存在或規範需求規定您必須回復索引鍵時使用客戶金鑰加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-469">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key.</span></span> <span data-ttu-id="b1281-470">此外，請勿刪除或已與原則相關聯的任何索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b1281-470">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="b1281-471">當您還原您的機碼，有將內容加密與先前的機碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-471">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="b1281-472">例如，當作用中信箱將會重新加密常見問題，非使用中，中斷連線，並已停用信箱可能仍將加密與先前的機碼之中。</span><span class="sxs-lookup"><span data-stu-id="b1281-472">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="b1281-473">SharePoint Online 執行備份的內容進行還原和復原，因此有可能仍會使用較舊的機碼的封存的內容。</span><span class="sxs-lookup"><span data-stu-id="b1281-473">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span> <br/> <span data-ttu-id="b1281-474">若要確保您的資料安全，SharePoint Online 可讓要進行一次不超過一個金鑰復原作業。</span><span class="sxs-lookup"><span data-stu-id="b1281-474">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time.</span></span> <span data-ttu-id="b1281-475">如果您想要將這兩個機碼金鑰保存庫中，您需要稍候的第一項重要 roll 作業完全完成。</span><span class="sxs-lookup"><span data-stu-id="b1281-475">If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete.</span></span> <span data-ttu-id="b1281-476">我們建議在不同的時間間隔，錯開金鑰 roll 作業，所以這不是此問題:。</span><span class="sxs-lookup"><span data-stu-id="b1281-476">Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="b1281-477">當您還原金鑰時，您要求新版本的現有的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b1281-477">When you roll a key, you are requesting a new version of an existing key.</span></span> <span data-ttu-id="b1281-478">若要要求新版本的現有的索引鍵，您可以使用相同的指令程式，[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)，具有相同的語法，用來在第一時間建立的機碼。</span><span class="sxs-lookup"><span data-stu-id="b1281-478">In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="b1281-479">例如：</span><span class="sxs-lookup"><span data-stu-id="b1281-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="b1281-480">在這個範例中，因為已經名為**Contoso-O365EX-NA-VaultA1-Key001**機碼存在於**Contoso O365EX-NA VaultA1**儲藏室，將會建立新的主要版本。</span><span class="sxs-lookup"><span data-stu-id="b1281-480">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created.</span></span> <span data-ttu-id="b1281-481">此作業會新增新的主要版本。</span><span class="sxs-lookup"><span data-stu-id="b1281-481">The operation adds a new key version.</span></span> <span data-ttu-id="b1281-482">這項作業會保留重要舊版中的索引鍵的版本歷程記錄，以便仍可解密先前使用該金鑰加密的資料。</span><span class="sxs-lookup"><span data-stu-id="b1281-482">This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted.</span></span> <span data-ttu-id="b1281-483">當您完成循環 DEP 相關聯的任何按鍵時，您必須執行其他的指令程式，以確保客戶金鑰會開始使用新的金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-483">Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="b1281-484">啟用 Exchange Online 和商務用 Skype 之後您將旋轉或 Azure 金鑰保存庫中的機碼，使用新的金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="b1281-485">當您展開任一 DEP 相關聯的 Azure Key Vault 機碼搭配 Exchange Online 與 Skype for Business，您必須執行下列命令，以更新 DEP 及啟用 Office 365，若要開始使用新的金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="b1281-486">以指示要用於新的金鑰加密中執行組 DataEncryptionPolicy 指令程式，如下所示的 Office 365 信箱的客戶金鑰：</span><span class="sxs-lookup"><span data-stu-id="b1281-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="b1281-487">48 小時內，使用此原則加密作用中信箱將會變成與更新的索引鍵關聯。</span><span class="sxs-lookup"><span data-stu-id="b1281-487">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key.</span></span> <span data-ttu-id="b1281-488">使用 < <b0>Determine DEP 指派給信箱</b0>的步驟，檢查信箱 DataEncryptionPolicyID 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="b1281-488">Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox.</span></span> <span data-ttu-id="b1281-489">一旦套用更新的機碼，將會變更此屬性的值。</span><span class="sxs-lookup"><span data-stu-id="b1281-489">The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="b1281-490">啟用 SharePoint Online 和商務用 OneDrive 之後您將旋轉或 Azure 金鑰保存庫中的機碼，使用新的金鑰</span><span class="sxs-lookup"><span data-stu-id="b1281-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="b1281-491">當您展開任一 DEP 相關聯的 Azure Key Vault 機碼搭配 SharePoint Online 和 OneDrive for Business，您必須執行[更新 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx)指令程式來更新 DEP，並啟用 Office 365，若要開始使用新的金鑰。</span><span class="sxs-lookup"><span data-stu-id="b1281-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="b1281-492">這會啟動 SharePoint Online 和商務用 OneDrive 的重要 roll 作業。</span><span class="sxs-lookup"><span data-stu-id="b1281-492">This will start the key roll operation for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="b1281-493">此巨集指令不即時運算]。</span><span class="sxs-lookup"><span data-stu-id="b1281-493">This action is not immediate.</span></span> <span data-ttu-id="b1281-494">若要查看機碼的復原作業的進度，執行 Get SPODataEncryptionPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1281-494">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="b1281-495">管理金鑰保存庫的權限</span><span class="sxs-lookup"><span data-stu-id="b1281-495">Manage key vault permissions</span></span>
<span data-ttu-id="b1281-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-496"></span></span>

<span data-ttu-id="b1281-497">多個 cmdlet 可供使用，可讓您檢視，如有必要，移除金鑰保存庫的權限。</span><span class="sxs-lookup"><span data-stu-id="b1281-497">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="b1281-498">您可能需要移除權限，例如，當員工離開小組。</span><span class="sxs-lookup"><span data-stu-id="b1281-498">You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="b1281-499">若要檢視金鑰保存庫的權限，請執行 Get AzureRmKeyVault 指令程式：</span><span class="sxs-lookup"><span data-stu-id="b1281-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="b1281-500">例如：</span><span class="sxs-lookup"><span data-stu-id="b1281-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="b1281-501">若要移除系統管理員權限，請執行移除 AzureRmKeyVaultAccessPolicy 指令程式：</span><span class="sxs-lookup"><span data-stu-id="b1281-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="b1281-502">例如：</span><span class="sxs-lookup"><span data-stu-id="b1281-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="b1281-503">決定指派給信箱 DEP</span><span class="sxs-lookup"><span data-stu-id="b1281-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="b1281-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="b1281-504"></span></span>

<span data-ttu-id="b1281-505">若要判斷 DEP 指派給信箱，請使用 Get-mailboxstatistics 指令程式。</span><span class="sxs-lookup"><span data-stu-id="b1281-505">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="b1281-506">此 cmdlet 會傳回的唯一識別碼 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="b1281-506">The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="b1281-507">其中*GeneralMailboxOrMailUserIdParameter*指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1281-507">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="b1281-508">如需 Get-mailboxstatistics 指令程式的詳細資訊，請參閱[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1281-508">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="b1281-509">使用 GUID 來找出信箱執行下列 cmdlet 來指派 DEP 的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="b1281-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="b1281-510">*GUID*是上一個步驟中的 Get-mailboxstatistics 指令程式所傳回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b1281-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

