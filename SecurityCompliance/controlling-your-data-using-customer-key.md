---
title: 使用客戶金鑰控制 Office 365 中的資料
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: 了解如何設定客戶金鑰 for Office 365 的 Exchange Online、 Skype Business、 SharePoint Online 和 OneDrive for Business。與客戶金鑰您控制您組織的加密金鑰及使用方式來加密的 Microsoft 資料中心的靜態資料的 Office 365，則設定。
ms.openlocfilehash: c4a59af49efad3bb8539b6c83b9ad9fd1c2d1f43
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723250"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="2eb21-104">使用客戶金鑰控制 Office 365 中的資料</span><span class="sxs-lookup"><span data-stu-id="2eb21-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="2eb21-p102">與客戶金鑰您控制組織的加密金鑰並使用這些加密 Microsoft 資料中心的靜態資料的 Office 365，則設定。靜態資料包括從 Exchange Online 和 Skype 會儲存在信箱和 SharePoint Online 中儲存的檔案中的企業版及 OneDrive for Business 的資料。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="2eb21-p103">您必須設定 Azure 才可以使用 Office 365 的客戶機碼。本主題說明您必須遵循以建立並設定必要的 Azure 資源的步驟，然後步驟安裝 Office 365 中的客戶索引鍵設定。Azure 安裝程式完成之後，您可以決定哪個原則，與因此哪些機碼，將指派給信箱與您組織中的檔案。信箱與檔案的未指派的原則將會使用加密原則控制及管理 microsoft。客戶機碼的詳細資訊或的一般概觀，請參閱[Office 365 常見問題集的客戶機碼](service-encryption-with-customer-key-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2eb21-p104">我們強烈建議您遵循此主題中的最佳作法。這些被呼叫所佔的**提示**以及**重要**。客戶機碼可讓您控制其範圍可大為整個組織的根加密金鑰。這表示與這些機碼所產生的錯誤造成廣泛的影響，而且可能會造成服務中斷或無法挽回的資料損失。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="2eb21-116">開始之前客戶機碼設定</span><span class="sxs-lookup"><span data-stu-id="2eb21-116">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="2eb21-117"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-117"></span></span>

<span data-ttu-id="2eb21-p105">您開始之前，請確認您具有適當的授權您的組織。在 Office 365 中的客戶機碼是 Office 365 E5 或進階規範 SKU 中提供。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="2eb21-p106">然後，了解的概念和本主題中的程序，您應該檢閱[Azure 機碼存放庫](https://azure.microsoft.com/en-us/documentation/services/key-vault/)的文件。此外，熟悉使用 Azure，例如[租用戶](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)中的條款。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="2eb21-122">若要提供意見反應客戶金鑰，包括文件，將您的想法、 建議和觀點 （英文） 傳送至 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="2eb21-122">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="2eb21-123">設定 Office 365 的客戶機碼的概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="2eb21-123">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="2eb21-124"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-124"></span></span>

<span data-ttu-id="2eb21-p107">若要設定客戶機碼所完成這些工作。本主題的其餘部分提供詳細的說明每一項工作或取出程序中的每個步驟的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="2eb21-127">**在 Azure 和 Microsoft FastTrack：**</span><span class="sxs-lookup"><span data-stu-id="2eb21-127">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="2eb21-p108">您將透過遠端連線到 Azure PowerShell 完成大部分的這些工作。為了獲得最佳結果，使用版本 4.4.0 或更新版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="2eb21-130">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="2eb21-130">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="2eb21-131">註冊使用的必要項目保留期間的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="2eb21-131">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="2eb21-132">註冊可能需要一至五個工作天。</span><span class="sxs-lookup"><span data-stu-id="2eb21-132">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="2eb21-133">送出要求啟用 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="2eb21-133">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="2eb21-p109">一旦您已經建立兩個新的 Azure 訂閱，您將需要適當的客戶金鑰優惠要求送出完成裝載於 Microsoft FastTrack 入口網站的 web 表單。**FastTrack 小組不會提供客戶機碼。只允許您送出表單，並協助客戶鍵追蹤相關提供我們使用 FastTrack 入口網站的 office**。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. **The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="2eb21-p110">一旦您已送出客戶金鑰產品項目、 Microsoft 檢閱您的要求，並通知您時可以繼續進行安裝工作的其餘部分。此程序可能需要最多可以有五個工作天。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="2eb21-138">在每一個訂閱中建立 premium Azure 機碼存放庫</span><span class="sxs-lookup"><span data-stu-id="2eb21-138">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="2eb21-139">權限指派給每個主要的存放庫</span><span class="sxs-lookup"><span data-stu-id="2eb21-139">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="2eb21-140">啟用，然後確認可以在您的主要保存庫虛刪除</span><span class="sxs-lookup"><span data-stu-id="2eb21-140">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="2eb21-141">索引鍵新增至每個主要存放庫是藉由建立或匯入金鑰</span><span class="sxs-lookup"><span data-stu-id="2eb21-141">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="2eb21-142">檢查您的機碼的復原層級</span><span class="sxs-lookup"><span data-stu-id="2eb21-142">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="2eb21-143">備份 Azure 的主要存放庫</span><span class="sxs-lookup"><span data-stu-id="2eb21-143">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="2eb21-144">驗證 Azure 機碼存放庫組態設定</span><span class="sxs-lookup"><span data-stu-id="2eb21-144">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="2eb21-145">取得每個 Azure 機碼存放庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="2eb21-145">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="2eb21-146">**在 Office 365：**</span><span class="sxs-lookup"><span data-stu-id="2eb21-146">**In Office 365:**</span></span>
  
<span data-ttu-id="2eb21-147">Exchange Online 和 Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="2eb21-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="2eb21-148">建立用於資料加密原則 (DEP) 與 Exchange Online 和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2eb21-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="2eb21-149">DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="2eb21-149">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="2eb21-150">驗證信箱加密</span><span class="sxs-lookup"><span data-stu-id="2eb21-150">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="2eb21-151">SharePoint Online 和 OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="2eb21-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="2eb21-152">建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置</span><span class="sxs-lookup"><span data-stu-id="2eb21-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="2eb21-153">驗證的群組網站和小組網站、 OneDrive for Business 的加密</span><span class="sxs-lookup"><span data-stu-id="2eb21-153">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="2eb21-154">Azure 機碼存放庫和 Microsoft FastTrack 客戶機碼中完成工作</span><span class="sxs-lookup"><span data-stu-id="2eb21-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="2eb21-155"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-155"></span></span>

<span data-ttu-id="2eb21-p111">若要設定 Office 365 的客戶金鑰完成 Azure 機碼存放庫中的這些工作。您必須完成下列步驟，不論是否您想要設定客戶機碼的 Exchange Online 和 Skype 商務或 SharePoint Online 以及 OneDrive for Business 或 Office 365 中的所有受支援服務。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="2eb21-158">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="2eb21-158">Create two new Azure subscriptions</span></span>
<span data-ttu-id="2eb21-159"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-159"></span></span>

<span data-ttu-id="2eb21-p112">兩個 Azure 訂閱所需的客戶機碼。最佳作法是 Microsoft 建議您與客戶機碼建立新的 Azure 訂閱使用。Azure 機碼存放庫機碼僅可以授權中相同的 Azure Active Directory (AAD) 租用戶的應用程式，您必須建立新的訂閱使用相同的 Azure AD 租用戶搭配 Office 365 組織要指派 DEPs。例如，使用您在 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶。如需詳細步驟，請參閱[註冊為組織的 Azure](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2eb21-p113">客戶金鑰需要兩個機碼針對每個資料加密原則 (DEP)。若要達到此目的，您必須建立兩個 Azure 訂閱。最佳作法是 Microsoft 建議您必須在每一個訂閱中設定一個金鑰貴組織的個別成員。此外，這些 Azure 訂閱應該只用於 Office 365 的管理加密金鑰。這會保護您的組織以防您運算子的其中一個意外、 刻意，或惡意刪除或否則 mismanages 他們是負責的按鍵。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="2eb21-p114">我們建議您設定新的 Azure 訂閱只用於與客戶金鑰管理 Azure 機碼存放庫資源使用。有不受實用的 Azure 您可以為您的組織建立的訂閱數限制。遵循這些最佳作法將最小化人工錯誤的影響同時協助管理客戶機碼所使用的資源。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="2eb21-173">送出要求啟用 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="2eb21-173">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="2eb21-174"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-174"></span></span>

<span data-ttu-id="2eb21-p115">一旦您已經完成的 Azure 的步驟，您將需要產品項目中提交要求[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。一旦您已送出要求透過 FastTrack 的入口網站、 Microsoft 驗證 Azure 機碼存放庫組態資料與連絡人您所提供的資訊。您在貴組織的授權主管有關產品項目表單所做的選擇是要徑和所需完成的客戶金鑰註冊。您在表單中選取您組織的主管會用來確保撤銷並終結客戶索引鍵資料加密原則搭配使用的所有按鍵任何要求的確實性。您需要執行一次此步驟才能啟用 Exchange Online 和 Skype 的商務涵蓋範圍與第二次啟動客戶機碼的 SharePoint Online 和 OneDrive for Business 的客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="2eb21-180">若要送出產品啟用客戶金鑰項目，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2eb21-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="2eb21-181">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶登入[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-181">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="2eb21-182">一旦您的登入，瀏覽至**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="2eb21-182">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="2eb21-183">選擇**提供**，並查看目前提供的清單。</span><span class="sxs-lookup"><span data-stu-id="2eb21-183">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="2eb21-184">選擇**了解更多**的產品套用至您的項目：</span><span class="sxs-lookup"><span data-stu-id="2eb21-184">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="2eb21-185">**Exchange Online 和 Skype for Business:\*\*\*\*Exchange 的客戶金鑰**優惠上選擇 [**了解更多**]。</span><span class="sxs-lookup"><span data-stu-id="2eb21-185">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="2eb21-186">**SharePoint Online 和 OneDrive for Business:** 選擇**更了解**在**SharePoint 和 OneDrive for Business 的客戶金鑰**產品項目。</span><span class="sxs-lookup"><span data-stu-id="2eb21-186">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="2eb21-187">**提供詳細資料**] 索引標籤上選擇 [**建立要求**。</span><span class="sxs-lookup"><span data-stu-id="2eb21-187">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="2eb21-p116">填寫所有適用的詳細資訊與產品項目表單上要求的資訊。請特別注意您組織的哪些主管的選擇您要授權核准永久並指出損毀的加密金鑰及資料。一旦您已經完成表單，選擇 [**送出**]。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="2eb21-191">此程序可能需要最多可以有五個工作天後已經被 Microsoft 通知您的要求。</span><span class="sxs-lookup"><span data-stu-id="2eb21-191">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="2eb21-192">繼續前往下列必要項目保留期間] 區段。</span><span class="sxs-lookup"><span data-stu-id="2eb21-192">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="2eb21-193">註冊使用的必要項目保留期間的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="2eb21-193">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="2eb21-194"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-194"></span></span>

<span data-ttu-id="2eb21-p117">暫時性或永久性的遺失根加密金鑰可以是非常中斷或甚至是災難性服務作業，而且可能會導致資料遺失。此原因的客戶金鑰搭配使用的資源需要強式保護。客戶金鑰搭配使用的所有 Azure 資源提供保護機制以外的預設設定。Azure 訂閱可以標記或登錄會防止即時和冒用取消的方式。這被稱為註冊的必要項目保留期間。為必要項目保留期間註冊 Azure 訂閱所需的步驟需要與 Office 365 小組共同作業。此程序可能需要一至五個工作天。先前，這是有時稱為 「 無法取消"。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="2eb21-203">再連絡 Office 365 小組，您必須執行下列步驟每個 Azure 訂閱搭配客戶機碼：</span><span class="sxs-lookup"><span data-stu-id="2eb21-203">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="2eb21-p118">登入您使用 Azure PowerShell 的 Azure 訂閱。指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="2eb21-206">執行登錄 AzureRmProviderFeature cmdlet 以註冊您的訂閱若要使用的必要項目保留期間。</span><span class="sxs-lookup"><span data-stu-id="2eb21-206">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="2eb21-p119">請連絡 Microsoft 以已完成的程序。SharePoint 和 OneDrive for Business 小組、 連絡[spock@microsoft.com](mailto:spock@microsoft.com)。Exchange Online 與 Skype for Business，請連絡[exock@microsoft.com](mailto:exock@microsoft.com)。服務層級協議 (SLA) 完成此程序的五個工作天後 Microsoft 通知 （並之後驗證） 的已註冊您的訂閱若要使用的必要項目保留期間。在您的電子郵件中包括下列：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="2eb21-212">**主旨**： 客戶金鑰\<*您的租用戶完整網域名稱*\></span><span class="sxs-lookup"><span data-stu-id="2eb21-212">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="2eb21-213">**內文**： 要具有必要項目保留期間完成的訂閱識別碼。</span><span class="sxs-lookup"><span data-stu-id="2eb21-213">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="2eb21-214">一旦您會收到通知 microsoft 註冊已完成，確認您註冊的狀態執行 Get AzureRmProviderFeature 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2eb21-214">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="2eb21-215">檢查**登錄 State**屬性取得 AzureRmProviderFeature 指令程式會傳回的值為**Registered**，執行下列命令以完成程序：</span><span class="sxs-lookup"><span data-stu-id="2eb21-215">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="2eb21-216">在每一個訂閱中建立 premium Azure 機碼存放庫</span><span class="sxs-lookup"><span data-stu-id="2eb21-216">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="2eb21-217"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-217"></span></span>

<span data-ttu-id="2eb21-218">中[快速入門 Azure 機碼存放庫](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)，這會引導您安裝並啟動 PowerShell 的 windows Azure、 連線至您的 Azure 訂閱、 建立資源群組，及建立主要存放庫中所記載的步驟來建立主要存放庫資源群組。</span><span class="sxs-lookup"><span data-stu-id="2eb21-218">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="2eb21-p120">當您建立主要存放庫時，您必須選擇 SKU： 標準版或 Premium。標準 SKU 允許以使用-有無硬體安全性模組 (HSM) 金鑰保護-軟體保護 Azure 機碼存放庫機碼並 Premium SKU 允許 Hsm 用於金鑰儲藏室機碼的保護。客戶金鑰接受主要保存庫使用任一 SKU，但是 Microsoft 強烈建議您使用僅限 Premium SKU。使用任一類型的機碼的作業成本是相同，因此成本中唯一的不同是每月每個 HSM 保護索引鍵的成本。如需詳細資訊，請參閱[定價機碼存放庫](https://azure.microsoft.com/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2eb21-224">用於實際執行資料的 Premium SKU 主要保存庫和 HSM 受保護的機碼並僅可用於標準 SKU 主要保存庫和機碼為了測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="2eb21-224">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="2eb21-p121">每個 Office 365 服務用以客戶機碼，建立主要存放庫中每個您所建立的兩個 Azure 訂閱。例如 Exchange Online 與 Skype 僅商務或 SharePoint Online 和 OneDrive for Business 僅，您會建立只能有一組的保存庫。若要啟用 Exchange Online 和 SharePoint Online 客戶金鑰，您會建立兩個配對的主要保存庫。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="2eb21-p122">使用主要保存庫，以反映您將關聯將保存庫 DEP 的預定的用法的命名慣例。請參閱下方的命名慣例建議最佳作法一節。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="2eb21-p123">建立每個資料加密原則保存庫個別、 配對集。Exchange Online 的資料加密原則範圍是選擇您將原則指派給信箱時。信箱可以有一個原則指派，而您可以建立多達了大約 50 個原則。SharePoint Online 的原則範圍是所有地理位置或地理位置中組織內的資料。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="2eb21-p124">主要保存庫的建立也需要 Azure 資源群組，請的建立自主要保存庫需要儲存容量 （雖然很小） 和機碼存放庫記錄，如果啟用，也會產生儲存的資料。最佳作法是 Microsoft 建議使用不同的系統管理員管理每個資源] 群組中，以使用系統管理員將管理相關的所有客戶機碼資源的一組對齊管理。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2eb21-p125">若要提高可用性，您重要保存庫應該在您的 Office 365 服務接近的地區。例如，如果您的 Exchange Online 組織位於 「 北美地區 」，置於您重要保存庫 「 北美地區 」。如果您的 Exchange Online 組織位於歐洲、 置於 Europe 您重要保存庫。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="2eb21-p126">使用主要保存庫，常見的前置詞，包括使用的縮寫和主要儲藏室和機碼的範圍 (例如，如 Contoso SharePoint service 將保存庫所在的 「 北美地區 」，可能兩個名稱為 Contoso O365SP-NA VaultA1 和Contoso-O365SP-NA-VaultA2。存放庫名稱為全域唯一字串，內 Azure，所以您可能需要以防其他 Azure 客戶同時已經宣告所要的名稱會嘗試變化的您想要的名稱。年 7 月 2017年存放庫名稱無法變更，所以最佳作法是已安裝的書寫的計畫和確認正確地執行計劃時使用的第二個的人員。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="2eb21-p127">請儘可能建立您保存庫非配對地區中。成對的 Azure 區域 （英文） 提供服務的失敗網域間的高可用性。因此，區域的配對可以是視為彼此的備份區域。這表示放在一個區域中的 Azure 資源自動取得容錯透過成對的區域。基於此選擇兩個保存庫所在的區域是只有兩個區域的可用性總共正在使用的配對的表示 DEP 中所使用的區域。大部分的地理位置只有兩個區域，讓它尚未可能選取非配對區域 （英文）。請儘可能選擇用於 DEP 將兩個保存庫中非成對的兩個地區這可藉由總共四個區域的可用性而獲益。如需詳細資訊，請參閱[商務持續力和災害復原 (BCDR)： Azure 配對區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)區域成對的目前清單。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="2eb21-251">權限指派給每個主要的存放庫</span><span class="sxs-lookup"><span data-stu-id="2eb21-251">Assign permissions to each key vault</span></span>
<span data-ttu-id="2eb21-252"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-252"></span></span>

<span data-ttu-id="2eb21-p128">每個主要的存放庫，您必須定義三個不同的實作根據客戶機碼權限。例如，您將需要定義一組權限的下列各項：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="2eb21-p129">**機碼存放庫系統管理員**將執行的主要的儲藏室日常管理您的組織。這些工作包括備份、 建立、 取得、 匯入] 清單中，並還原。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2eb21-p130">指派給主要儲藏室系統管理員的權限集不包括權限可以刪除索引鍵。這是刻意及重要的作法。刪除加密金鑰不通常是，由於所以永久執行終結資料。最佳作法是不要不授與此權限主要儲藏室系統管理員預設。而此齊備的重要儲藏室參與者並只將其指派給短期為基礎的系統管理員瞭解後果清楚了解之後。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="2eb21-p131">若要將這些權限指派給 Office 365 組織中的使用者，登入您使用 Azure PowerShell 的 Azure 訂閱。指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="2eb21-264">執行設定 AzureRmKeyVaultAccessPolicy 指令程式來指派必要權限。</span><span class="sxs-lookup"><span data-stu-id="2eb21-264">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="2eb21-265">例如：</span><span class="sxs-lookup"><span data-stu-id="2eb21-265">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="2eb21-p132">**機碼存放庫參與者**可以變更 Azure 機碼存放庫的權限本身擷取。您需要變更這些權限如下員工離開或加入您的小組，或在極罕見的情況下的按鍵地窖管理員合法需要刪除或還原金鑰的權限。這組重要儲藏室參與者必須被授與您主要的存放庫的**參與者**角色的設定。您可以使用 Azure 資源管理員指派此角色。如需詳細步驟，請參閱[Use Role-Based 存取控制來管理 Azure 訂閱資源的存取權](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。建立訂閱的系統管理員存取此隱含，以及指派給參與者角色的其他管理員的能力。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="2eb21-p133">如果您想要使用與 Exchange Online 和 Skype 的客戶金鑰 for Business，您需要使用 Exchange Online 和 Skype 代表鍵儲藏室 for Business 的 Office 365 授與權限。同樣地，如果您想要使用客戶金鑰 SharePoint Online 以及 OneDrive for Business，您需要新增使用主要儲藏室代表 SharePoint Online 和 OneDrive for Business 的 Office 365 的權限。若要授與權限至 Office 365、 執行**組 AzureRmKeyVaultAccessPolicy**指令程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="2eb21-275">其中：</span><span class="sxs-lookup"><span data-stu-id="2eb21-275">Where:</span></span>
    
  - <span data-ttu-id="2eb21-276">*vaultname*是您建立主要存放庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="2eb21-276">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="2eb21-277">Exchange Online 與 Skype for Business，取代與*Office 365 應用程式識別碼*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="2eb21-277">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="2eb21-278">SharePoint Online 和 OneDrive for Business，將與*Office 365 應用程式識別碼*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="2eb21-278">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="2eb21-279">範例： 設定 Exchange Online 和 Skype for Business 的權限：</span><span class="sxs-lookup"><span data-stu-id="2eb21-279">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="2eb21-280">範例： 設定 SharePoint Online 和 OneDrive for Business 的權限</span><span class="sxs-lookup"><span data-stu-id="2eb21-280">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="2eb21-281">啟用，然後確認可以在您的主要保存庫虛刪除</span><span class="sxs-lookup"><span data-stu-id="2eb21-281">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="2eb21-282"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-282"></span></span>

<span data-ttu-id="2eb21-p134">當您可以快速地復原您的機碼時，就可能無法體驗擴充的服務中斷因為意外或惡意刪除機碼。您必須啟用此設定，稱為柔刪除，才可以使用您的金鑰與客戶機碼。啟用軟體刪除可讓您不必從備份中還原刪除的 90 天內復原機碼或保存庫。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="2eb21-286">若要啟用軟體刪除上您重要保存庫，完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2eb21-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="2eb21-p135">登入您使用 Windows Powershell 的 Azure 訂閱。指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="2eb21-p136">執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault)指令程式。在這個範例中， *vaultname*是您要為其啟用虛刪除主要存放庫的名稱：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="2eb21-p137">確認虛刪除已針對重要儲藏室執行**Get AzureRmKeyVault**指令程式。虛刪除的設定是否正確的主要儲藏室、 虛刪除已啟用吗？屬性會傳回**True**的值：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="2eb21-293">索引鍵新增至每個主要存放庫是藉由建立或匯入金鑰</span><span class="sxs-lookup"><span data-stu-id="2eb21-293">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="2eb21-294"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-294"></span></span>

<span data-ttu-id="2eb21-p138">有兩種方式將機碼新增至 Azure 機碼存放庫 ；您可以直接在機碼存放庫中建立機碼或您可以匯入金鑰。直接在機碼存放庫中建立機碼是較不複雜的方法，而匯入金鑰可讓您控制如何產生金鑰總數。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="2eb21-297">若要直接在您主要的存放庫中建立機碼，如下執行[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)指令程式：</span><span class="sxs-lookup"><span data-stu-id="2eb21-297">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="2eb21-298">其中：</span><span class="sxs-lookup"><span data-stu-id="2eb21-298">Where:</span></span>
  
-  <span data-ttu-id="2eb21-299">*vaultname*是您要建立的機碼主要存放庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="2eb21-299">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="2eb21-300">*keyname*是您要給新機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="2eb21-300">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="2eb21-p139">如前文所述的重要保存庫使用類似的命名慣例機碼的名稱。如此一來，顯示機碼名稱的工具，在字串自我描述。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="2eb21-303">如果您想要保護 HSM 鍵，請確定您指定**HSM**為_目的地_參數值，否則指定**軟體**。</span><span class="sxs-lookup"><span data-stu-id="2eb21-303">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="2eb21-304">例如，</span><span class="sxs-lookup"><span data-stu-id="2eb21-304">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="2eb21-305">若要直接將您主要的存放庫，匯入金鑰，您需要有 Thales nShield 硬體安全性模組。</span><span class="sxs-lookup"><span data-stu-id="2eb21-305">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="2eb21-306">有些組織偏好這種方法來建立其機碼，與此 provenance 方法也會提供下列：</span><span class="sxs-lookup"><span data-stu-id="2eb21-306">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="2eb21-307">用於匯入工具集包括從 Thales 金鑰 Exchange 索引鍵 (KEK) 用來加密您產生的金鑰不是可匯出的審查及產生內已由 Thales 生產正版 HSM。</span><span class="sxs-lookup"><span data-stu-id="2eb21-307">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="2eb21-p140">工具集包含從 Thales Azure 機碼存放庫安全性 world 也已產生在生產由 Thales 正版 HSM 審查。此審查證明您 Microsoft 也使用正版 Thales 硬體。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="2eb21-p141">檢查與您決定是否需要上述 attestations 的安全性群組。建立主要內部部署和匯入到您的主要存放庫的詳細步驟，請參閱[如何產生及傳輸 HSM 保護 Azure 機碼存放庫的機碼](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。使用 Azure 指示每一個主要的存放庫中建立機碼。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="2eb21-313">檢查您的機碼的復原層級</span><span class="sxs-lookup"><span data-stu-id="2eb21-313">Check the recovery level of your keys</span></span>
<span data-ttu-id="2eb21-314"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-314"></span></span>

<span data-ttu-id="2eb21-p142">Office 365 需要 Azure 機碼存放庫訂閱設為不要取消及客戶機碼所使用的按鍵已啟用的虛刪除。您可以透過查看 [您的機碼中的 [復原層級加以確認。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="2eb21-317">若要檢查 Azure PowerShell 中的索引鍵的復原層級，如下所示執行 Get AzureKeyVaultKey 指令程式：</span><span class="sxs-lookup"><span data-stu-id="2eb21-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="2eb21-318">如果_復原層級_屬性會傳回**發生無法復原 + ProtectedSubscription**值以外，您必須以檢閱本主題，並確定您已遵循所有訂閱置於 [不要取消清單中的步驟及您必須在每個您重要保存庫上啟用的虛刪除。</span><span class="sxs-lookup"><span data-stu-id="2eb21-318">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="2eb21-319">備份 Azure 的主要存放庫</span><span class="sxs-lookup"><span data-stu-id="2eb21-319">Backup Azure Key Vault</span></span>
<span data-ttu-id="2eb21-320"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-320"></span></span>

<span data-ttu-id="2eb21-p143">緊接在建立或任何變更機碼，執行備份與儲存區的線上及離線的備份複本。離線複本應該不會連線至任何網路，例如在實體安全或商業儲存設備。備份至少一個複本應儲存在會在發生災害時可以存取的位置。備份 blob 是應該金鑰儲藏室機碼是永久移除或否則呈現 [無法正常運作還原主要材料的唯一方法。外部 Azure 機碼存放庫，且已匯入至 Azure 機碼存放庫的機碼不能限定備份因為具有外部索引鍵不存在的中繼資料時所需的客戶使用按鍵的按鍵。僅取自 Azure 機碼存放庫的備份可搭配還原作業的客戶機碼。因此，很重要的 Azure 機碼存放庫備份進行之後金鑰已上傳或建立。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="2eb21-328">若要建立 Azure 機碼存放庫機碼的備份，以下列方式執行[備份 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2eb21-328">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="2eb21-329">請確定您的輸出檔案使用尾碼`.backup`。</span><span class="sxs-lookup"><span data-stu-id="2eb21-329">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="2eb21-p144">此指令程式所產生的輸出檔案加密，而且不能使用外部 Azure 機碼存放庫。可以只以拍攝備份時的 Azure 訂閱還原備份。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="2eb21-p145">輸出檔，選擇您的存放庫名稱和機碼名稱的組合。這會使檔案名稱自我描述。它也會確保備份的檔案名稱執行動作不會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="2eb21-335">例如：</span><span class="sxs-lookup"><span data-stu-id="2eb21-335">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="2eb21-336">驗證 Azure 機碼存放庫組態設定</span><span class="sxs-lookup"><span data-stu-id="2eb21-336">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="2eb21-337"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-337"></span></span>

<span data-ttu-id="2eb21-p146">執行驗證之前使用機碼中 DEP 是選擇性的但強烈建議。特別是，如果您使用步驟來設定您的機碼和保存庫本主題所述的錯誤以外，您應該驗證 Azure 機碼存放庫資源的健康狀況之前設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="2eb21-340">若要確認您的機碼已啟用 get、 wrapKey，以及 unwrapKey 作業：</span><span class="sxs-lookup"><span data-stu-id="2eb21-340">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="2eb21-341">執行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2eb21-341">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="2eb21-p147">在輸出中尋找適當的存取原則與 Exchange Online 的身分識別 (GUID) 或 SharePoint Online 的身分識別 (GUID)。所有三個以上的權限必須是底下都顯示的權限機碼。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="2eb21-344">如果存取原則設定不正確，請執行組 AzureRmKeyVaultAccessPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2eb21-344">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="2eb21-345">例如，用於 Exchange Online 和 Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="2eb21-345">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="2eb21-346">例如，用於 SharePoint Online 和 OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="2eb21-346">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="2eb21-347">若要確認到期沒有為您執行[Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)指令程式，如下所示的機碼設定：</span><span class="sxs-lookup"><span data-stu-id="2eb21-347">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="2eb21-p148">過期的索引鍵不能使用客戶金鑰並嘗試使用過期的索引鍵的作業會失敗，並可能造成服務中斷。我們強烈建議客戶金鑰搭配使用的按鍵沒有到期。設定，則無法移除，但可以變更為不同的日期之後到期日期。如果金鑰必須使用已到期設定到期日值變更為 12/31/9999。除了比 12/31/9999 不會將 Office 365 驗證傳遞機碼以到期設定日期。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="2eb21-353">若要變更已設定為 12/31/9999 以外的任何數值到期，以下列方式執行[組 AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2eb21-353">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="2eb21-354">不在您使用與客戶機碼的加密金鑰設定到期日。</span><span class="sxs-lookup"><span data-stu-id="2eb21-354">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="2eb21-355">取得每個 Azure 機碼存放庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="2eb21-355">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="2eb21-356"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-356"></span></span>

<span data-ttu-id="2eb21-p149">一次完成設定您的主要保存庫 Azure 中的所有步驟並新增機碼，執行下列命令以取得每個主要的存放庫中的機碼的 URI。您將需要使用這些 Uri 當您建立及更新版本、 指派每個 DEP 因此請儲存此資訊安全的位置。請記得執行此命令一次的每個主要的存放庫。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="2eb21-360">在 Azure PowerShell：</span><span class="sxs-lookup"><span data-stu-id="2eb21-360">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="2eb21-361">Office 365： 設定 Exchange Online 和 Skype for Business 的客戶機碼</span><span class="sxs-lookup"><span data-stu-id="2eb21-361">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="2eb21-362"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-362"></span></span>

<span data-ttu-id="2eb21-p150">開始之前，請確定您已完成工作所需設定 「 Azure 機碼存放庫。請參閱[在 Azure 機碼存放庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)的資訊。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="2eb21-365">若要設定客戶機碼的 Exchange Online 和 Skype for Business，必須從遠端連線至 Exchange Online 使用 Windows PowerShell 來執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="2eb21-365">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="2eb21-366">建立用於資料加密原則 (DEP) 與 Exchange Online 和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2eb21-366">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="2eb21-367"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-367"></span></span>

<span data-ttu-id="2eb21-p151">DEP 是一組儲存在 Azure 機碼存放庫中的機碼的相關聯。您可以指派 DEP 給 Office 365 中的信箱。Office 365 接著會使用該原則中所識別的按鍵來加密信箱。若要建立 DEP，您需要您稍早取得金鑰儲藏室 Uri。請參閱指示[取得每個 Azure 機碼存放庫機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="2eb21-p152">請記得 ！當您建立 DEP 時，您會指定兩個位於兩個不同的 Azure 金鑰保存庫中的索引鍵。請確定這些機碼位於兩個不同的 Azure 區域以確保地理冗餘。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="2eb21-376">若要建立 DEP 請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2eb21-376">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="2eb21-377">在您的本機電腦上使用的工作或學校 Office 365 組織中開啟 Windows PowerShell 並執行下列命令的 [[連線至 Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)中具有全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="2eb21-377">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="2eb21-378">在 Windows PowerShell 認證要求] 對話方塊中，輸入您的工作或學校帳戶資訊、 按一下 [**確定**] 並再輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="2eb21-378">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="2eb21-379">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="2eb21-379">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="2eb21-380">若要建立 DEP，使用新增 DataEncryptionPolicy 指令程式輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="2eb21-380">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="2eb21-381">其中：</span><span class="sxs-lookup"><span data-stu-id="2eb21-381">Where:</span></span>
    
   -  <span data-ttu-id="2eb21-p153">*Policyname 就*是您想要使用之原則的名稱。名稱不得包含空格。例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="2eb21-p154">*PolicyDescription*是可協助您記住此原則會針對原則的使用者易記描述。您可以在 [描述包含空格。例如，根中 USA 和其領域之信箱的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="2eb21-p155">*KeyVaultURI1*是原則中的第一個索引鍵的 URI。例如， https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="2eb21-p156">*KeyVaultURI2*是原則中的第二個機碼的 URI。例如， https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。分隔兩個逗號及空間 Uri。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="2eb21-393">範例：</span><span class="sxs-lookup"><span data-stu-id="2eb21-393">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="2eb21-394">DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="2eb21-394">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="2eb21-395"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-395"></span></span>

<span data-ttu-id="2eb21-p157">使用 Set-mailbox 指令程式將 DEP 指派給信箱。Office 365 一旦您指派原則時，可以使用 DEP 中指定的金鑰加密信箱</span><span class="sxs-lookup"><span data-stu-id="2eb21-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="2eb21-p158">其中*MailboxIdParameter*會指定信箱。如需 Set-mailbox 指令程式的詳細資訊，請參閱[Set-mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="2eb21-400">驗證信箱加密</span><span class="sxs-lookup"><span data-stu-id="2eb21-400">Validate mailbox encryption</span></span>
<span data-ttu-id="2eb21-401"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-401"></span></span>

<span data-ttu-id="2eb21-p159">加密信箱可能需要一些時間。第一次原則指派、 信箱也之前必須完成從一個資料庫移動至另一個服務可以加密信箱。我們建議您等待 72 小時嘗試之後變更 DEP 或第一次您 DEP 信箱指派驗證加密之前。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="2eb21-405">使用 Get-mailboxstatistics 指令程式來決定是否加密信箱。</span><span class="sxs-lookup"><span data-stu-id="2eb21-405">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="2eb21-406">如果未加密之信箱 IsEncrypted 屬性會傳回的值**則為 true**如果加密信箱及的值為**false** 。</span><span class="sxs-lookup"><span data-stu-id="2eb21-406">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="2eb21-p160">完成信箱移動的時間取決於您將指派 DEP 第一次的信箱數目時的信箱大小。如果尚未從一週後加密信箱指派 DEP、 使用 New-moverequest 指令程式起始之未加密的信箱的信箱移動。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="2eb21-409">Office 365： 設定 SharePoint Online 和 OneDrive for Business 的客戶機碼</span><span class="sxs-lookup"><span data-stu-id="2eb21-409">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="2eb21-410"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-410"></span></span>

<span data-ttu-id="2eb21-p161">開始之前，請確定您已完成工作所需設定 「 Azure 機碼存放庫。請參閱[在 Azure 機碼存放庫和 Microsoft FastTrack 客戶機碼中的完成工作](controlling-your-data-using-customer-key.md#AzureSteps)的資訊。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="2eb21-413">若要設定客戶機碼的 SharePoint Online 和 OneDrive for Business，必須從遠端連線至 SharePoint Online Windows powershell 來執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="2eb21-413">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="2eb21-414">建立資料加密原則 (DEP) 每個 SharePoint Online 和 OneDrive for Business 地理位置</span><span class="sxs-lookup"><span data-stu-id="2eb21-414">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="2eb21-415"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-415"></span></span>

<span data-ttu-id="2eb21-p162">DEP 是一組儲存在 Azure 機碼存放庫中的機碼的相關聯。您可以將 DEP 套用至所有的單一地理位置，也稱為 「 地理位置資料。如果您使用 Office 365 的多重地理位置功能 （目前 Preview) 中，您可以建立一個 DEP 個別地理位置。如果您不使用多個地理位置，您可以在 Office 365 中建立一個 DEP 搭配 SharePoint Online 和 OneDrive for Business。Office 365 接著會使用 DEP 中所識別的按鍵來加密您的地理位置中的資料。若要建立 DEP，您需要您稍早取得金鑰儲藏室 Uri。請參閱指示[取得每個 Azure 機碼存放庫機碼的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="2eb21-p163">請記得 ！當您建立 DEP 時，您會指定兩個位於兩個不同的 Azure 金鑰保存庫中的索引鍵。請確定這些機碼位於兩個不同的 Azure 區域以確保地理冗餘。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="2eb21-426">若要建立 DEP，您需要使用 Windows PowerShell 遠端連接至 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="2eb21-426">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="2eb21-427">在您的本機電腦上使用的工作或學校 Office 365 組織中[連線至 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)中具有全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="2eb21-427">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="2eb21-428">Microsoft SharePoint Online 管理命令介面中，執行[註冊 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2eb21-428">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="2eb21-p164">當您註冊 DEP 時，地理位置中的資料在上一開始會加密。這可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="2eb21-431">驗證的群組網站和小組網站、 OneDrive for Business 的加密</span><span class="sxs-lookup"><span data-stu-id="2eb21-431">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="2eb21-432"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-432"></span></span>

<span data-ttu-id="2eb21-433">您可以檢查的加密狀態執行 Get SPODataEncryptionPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2eb21-433">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="2eb21-434">此 cmdlet 的輸出包含：</span><span class="sxs-lookup"><span data-stu-id="2eb21-434">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="2eb21-435">主索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="2eb21-435">The URI of the primary key.</span></span>
    
- <span data-ttu-id="2eb21-436">次要機碼的 URI。</span><span class="sxs-lookup"><span data-stu-id="2eb21-436">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="2eb21-p165">地理位置加密狀態。狀態可能包括：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="2eb21-439">**取消登錄：** 尚未套用客戶金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="2eb21-439">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="2eb21-p166">**登錄：** 已套用客戶金鑰加密及加密正在您的檔案。如果您地理位置是在此狀態下，您將也會顯示資訊上以便您可以監視加密進度何種百分比地理位置中的網站皆已完成。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="2eb21-442">**登錄：** 套用客戶金鑰加密和已加密的所有網站中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="2eb21-442">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="2eb21-p167">**循環：** 主要 roll 正在進行中。如果您地理位置是在此狀態下，您將也會顯示資訊上何種百分比的網站，讓您可以監視進度完成的主要聯播 （英文） 作業。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="2eb21-445">管理 office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="2eb21-445">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="2eb21-446"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-446"></span></span>

<span data-ttu-id="2eb21-447">您針對 Office 365 設定客戶金鑰之後，您可以執行下列其他管理工作。</span><span class="sxs-lookup"><span data-stu-id="2eb21-447">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="2eb21-448">還原 Azure 機碼存放庫機碼</span><span class="sxs-lookup"><span data-stu-id="2eb21-448">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="2eb21-449">啟用或旋轉和客戶金鑰使用 Azure 機碼存放庫中的索引鍵</span><span class="sxs-lookup"><span data-stu-id="2eb21-449">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="2eb21-450">管理主要存放庫的權限</span><span class="sxs-lookup"><span data-stu-id="2eb21-450">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="2eb21-451">決定指派給信箱 DEP</span><span class="sxs-lookup"><span data-stu-id="2eb21-451">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="2eb21-452">還原 Azure 機碼存放庫機碼</span><span class="sxs-lookup"><span data-stu-id="2eb21-452">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="2eb21-453"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-453"></span></span>

<span data-ttu-id="2eb21-p168">在執行還原、 之前使用虛刪除所提供的復原功能。客戶金鑰搭配使用的所有索引鍵所需已啟用的虛刪除。虛刪除 bot 資源回收筒，並允許復原多達 90 天而不需要還原。超重度或不尋常的情況，例如金鑰或金鑰儲藏室中斷時應該只需要還原。如果您必須使用客戶金鑰還原金鑰使用 Azure PowerShell 中執行還原 AzureKeyVaultKey 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="2eb21-459">例如：</span><span class="sxs-lookup"><span data-stu-id="2eb21-459">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="2eb21-p169">如果主要存放庫中已經存在具有相同名稱的機碼，將會失敗的還原作業。還原 AzureKeyVaultKey 還原所有的主要版本和所有中繼資料包括機碼名稱的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="2eb21-462">啟用或旋轉和客戶金鑰使用 Azure 機碼存放庫中的索引鍵</span><span class="sxs-lookup"><span data-stu-id="2eb21-462">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="2eb21-463"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-463"></span></span>

<span data-ttu-id="2eb21-p170">啟用機碼不需要透過其中一個 Azure 機碼存放庫或客戶機碼。此外，使用 HSM 受到保護的機碼是幾乎很難危害。即使根機碼所擁有的惡意動作項目中沒有使用解密的資料，因為只有 Office 365 的程式碼知道如何使用它的任何可行的方法。不過，啟用金鑰客戶鍵所支援。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2eb21-p171">僅能復原清除技術原因存在於或規範需求以指定您必須將索引鍵時與客戶金鑰一起使用的加密金鑰。此外，不要刪除任何按鍵或已與原則產生關聯。當您首次機碼、 有將內容加密與先前的符號。例如時使用中的信箱，將會重新加密常見問題，不在作用中已中斷連線，但已停用信箱仍可能會加密與先前的符號。SharePoint Online 執行備份的內容還原及復原用途，因此仍可能使用較舊的機碼封存的內容。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="2eb21-p172">若要確保資料的安全，SharePoint Online 會允許設為正在進行一次不超過一個索引鍵首次作業。如果您想要在主要儲藏室彙兩者的機碼，則需要等待第一項重要聯播 （英文） 作業完全完成。我們建議是在不同的時間間隔錯開主要聯播 （英文） 作業使這不是發生問題。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="2eb21-p173">當您首次金鑰時，您要求的現有的索引鍵的新版本。若要要求新版本的現有的索引鍵、 您可以使用同一個指令程式[新增 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)，具有相同的語法您用以最初建立的機碼。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="2eb21-478">例如：</span><span class="sxs-lookup"><span data-stu-id="2eb21-478">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="2eb21-p174">在這個範例中，由於金鑰名為**Contoso-O365EX-NA-VaultA1-Key001**已經存在於**Contoso O365EX-NA VaultA1**存放庫將會建立新的主要版本。作業將新的主要版本。這項作業會保留主要索引鍵的版本歷程記錄中的舊版使仍進行解密先前與該金鑰加密資料。一旦您完成啟用關聯 DEP 任意鍵，接著您必須執行額外的指令程式來確保客戶金鑰一開始會使用新金鑰。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="2eb21-483">啟用 Exchange Online 和 Skype for Business 首次或旋轉 Azure 機碼存放庫中的機碼之後使用新的金鑰</span><span class="sxs-lookup"><span data-stu-id="2eb21-483">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="2eb21-484">當您首次任一 DEP 相關聯的 Azure 機碼存放庫按鍵搭配 Exchange Online 和 Skype for Business，您必須執行下列命令來更新 DEP 並啟用 Office 365 開始使用新的金鑰。</span><span class="sxs-lookup"><span data-stu-id="2eb21-484">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="2eb21-485">若要指示客戶機碼，以使用新的金鑰來加密 Office 365 中的信箱，如下所示執行組 DataEncryptionPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2eb21-485">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="2eb21-p175">48 小時內使用此原則加密的作用中信箱會成為與更新的索引鍵關聯。使用 ＜ [Determine DEP 指派給信箱](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)的步驟來查看信箱的 DataEncryptionPolicyID 屬性的值。此屬性的值會變更之後已套用更新的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="2eb21-489">讓 SharePoint Online 和 OneDrive for Business，以使用新的金鑰後您首次或旋轉 Azure 機碼存放庫中的機碼</span><span class="sxs-lookup"><span data-stu-id="2eb21-489">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="2eb21-490">當您首次任一 DEP 相關聯的 Azure 機碼存放庫按鍵用於 SharePoint Online 和 OneDrive for Business，您必須執行[更新 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx)指令程式來更新 DEP 並啟用 Office 365 開始使用新的金鑰。</span><span class="sxs-lookup"><span data-stu-id="2eb21-490">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="2eb21-p176">這會啟動 SharePoint Online 和 OneDrive for Business 的重要聯播 （英文） 作業。無法立即此巨集指令。若要查看機碼的首次作業的進度，以下列方式執行 Get SPODataEncryptionPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2eb21-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="2eb21-494">管理主要存放庫的權限</span><span class="sxs-lookup"><span data-stu-id="2eb21-494">Manage key vault permissions</span></span>
<span data-ttu-id="2eb21-495"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-495"></span></span>

<span data-ttu-id="2eb21-p177">現已提供數個 cmdlet 可讓您檢視和必要的話，移除重要的存放庫的權限。您可能需要移除權限，例如員工離開小組。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="2eb21-498">若要檢視主要存放庫的權限，請執行 Get AzureRmKeyVault cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2eb21-498">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="2eb21-499">例如：</span><span class="sxs-lookup"><span data-stu-id="2eb21-499">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="2eb21-500">若要移除的管理員權限，執行移除 AzureRmKeyVaultAccessPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2eb21-500">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="2eb21-501">例如：</span><span class="sxs-lookup"><span data-stu-id="2eb21-501">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="2eb21-502">決定指派給信箱 DEP</span><span class="sxs-lookup"><span data-stu-id="2eb21-502">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="2eb21-503"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="2eb21-503"></span></span>

<span data-ttu-id="2eb21-p178">若要判斷指派給信箱 DEP，請使用 Get-mailboxstatistics 指令程式。此指令程式會傳回的唯一識別碼 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="2eb21-p179">其中*GeneralMailboxOrMailUserIdParameter*會指定信箱。如需 Get-mailboxstatistics 指令程式的詳細資訊，請參閱[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2eb21-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="2eb21-508">使用 GUID 來找出對其執行下列指令程式來指派信箱 DEP 的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="2eb21-508">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="2eb21-509">其中*的 GUID*是 Get-mailboxstatistics 指令程式在上一個步驟中所傳回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="2eb21-509">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

