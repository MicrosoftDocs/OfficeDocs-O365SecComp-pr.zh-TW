---
title: 使用網路上傳將 RMS 加密的 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: 了解如何使用網路上傳至 RMS 加密 PST 檔案匯入 Office 365 中的使用者信箱。
ms.openlocfilehash: 8f08b17b5b975316afaf9545d5ba42057f35deca
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296576"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a><span data-ttu-id="c4500-103">使用網路上傳將 RMS 加密的 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="c4500-103">Use network upload to import RMS-encrypted PST files to Office 365</span></span>

<span data-ttu-id="c4500-104">**本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span><span class="sxs-lookup"><span data-stu-id="c4500-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="c4500-p101">使用網路上傳至 PST 檔案匯入使用者信箱的選項和匯入 Office 365 服務。網路上傳表示您上載 PST 檔案中 Microsoft cloud 暫時存放區。則 Office 365 匯入服務會複製 PST 檔案存放區從目標使用者信箱。匯入服務的新功能可讓您之前在其上傳並儲存在 Microsoft cloud 加密 PST 檔案。當他們正在匯入至使用者信箱這些檔案都會未加密。</span><span class="sxs-lookup"><span data-stu-id="c4500-p101">Use the network upload option and the Office 365 Import service to import PST files to user mailboxes. Network upload means that you upload the PST files a temporary storage area in the Microsoft cloud. Then the Office 365 Import service copies the PST files from the storage area to the target user mailboxes. A new feature of the Import service lets you encrypt your PST files before they are uploaded and stored on the Microsoft cloud. These files will be un-encrypted when they're imported to user mailboxes.</span></span> 
  
<span data-ttu-id="c4500-110">加密和 PST 檔案匯入 Office 365 信箱所需的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="c4500-110">Here are the steps required to encrypt and import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="c4500-111">步驟 1：為 PST 匯入設定 Azure Rights Management </span><span class="sxs-lookup"><span data-stu-id="c4500-111">Step 1: Set up Azure Rights Management for PST Import</span></span>](#step-1-set-up-azure-rights-management-for-pst-import)

[<span data-ttu-id="c4500-112">步驟 2：為 PST 匯入產生加密金鑰</span><span class="sxs-lookup"><span data-stu-id="c4500-112">Step 2: Generate an encryption key for PST Import</span></span>](#step-2-generate-an-encryption-key-for-pst-import)

[<span data-ttu-id="c4500-113">步驟 3： 取得 RMS 租用戶識別碼和授權的 URL</span><span class="sxs-lookup"><span data-stu-id="c4500-113">Step 3: Obtain RMS tenant ID and licensing URL</span></span>](#step-3-obtain-rms-tenant-id-and-licensing-url)

[<span data-ttu-id="c4500-114">步驟 4： 下載 PST 匯入工具並複製 SAS URL</span><span class="sxs-lookup"><span data-stu-id="c4500-114">Step 4: Download the PST Import tools and copy the SAS URL</span></span>](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[<span data-ttu-id="c4500-115">步驟 5： 加密和您 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c4500-115">Step 5: Encrypt and upload your PST files to Office 365</span></span>](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[<span data-ttu-id="c4500-116">（選用）步驟 6： 檢視清單中的 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c4500-116">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[<span data-ttu-id="c4500-117">步驟 7： 建立 PST 匯入對應檔案</span><span class="sxs-lookup"><span data-stu-id="c4500-117">Step 7: Create the PST Import mapping file</span></span>](#step-7-create-the-pst-import-mapping-file)

[<span data-ttu-id="c4500-118">步驟 8：在 Office 365 中建立 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="c4500-118">Step 8: Create a PST Import job in Office 365</span></span>](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> <span data-ttu-id="c4500-p102">您必須執行步驟 1 到步驟 4 只有一次安裝及設定您的組織來加密及 PST 檔案匯入 Office 365 信箱。您執行這些步驟之後，請遵循步驟 5 到步驟 8 每一個您想要加密、 上傳及匯入 PST 檔案的批次的時間。</span><span class="sxs-lookup"><span data-stu-id="c4500-p102">You have to perform Step 1 through Step 4 only once to set up and configure your organization to encrypt and import PST files to Office 365 mailboxes. After you perform these steps, follow Step 5 through Step 8 each time you want to encrypt, upload, and import a batch of PST files.</span></span> 
  
<span data-ttu-id="c4500-121">如需將資料匯入 Office 365 的詳細資訊，請參閱 ＜ [Overview of 匯入至 Office 365 貴組織 PST 檔案](importing-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c4500-121">For more information about importing data to Office 365, see [Overview of importing your organization PST files to Office 365](importing-pst-files-to-office-365.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c4500-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="c4500-122">Before you begin</span></span>

- <span data-ttu-id="c4500-p103">您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後再將自己的成員身分或者。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="c4500-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="c4500-128">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="c4500-128">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="c4500-p104">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="c4500-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="c4500-131">或</span><span class="sxs-lookup"><span data-stu-id="c4500-131">Or</span></span>
    
  - <span data-ttu-id="c4500-132">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="c4500-132">You have to be a global administrator in your Office 365 organization.</span></span>
    
  > [!TIP]
  > <span data-ttu-id="c4500-p105">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="c4500-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="c4500-p106">您要儲存您想要匯入 Office 365 上的檔案伺服器或組織中的共用的資料夾的 PST 檔案。在步驟 5 中，您用來執行 Office 365 ImportTool，由其將會加密並上傳儲存此檔案伺服器上或共用資料夾至 Office 365 的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-p106">You need to store the PST files that you want to import to Office 365 on a file server or shared folder in your organization. In Step 5, you'll run the Office 365 ImportTool, which will encrypt and upload the PST files that are stored on this file server or shared folder to Office 365.</span></span>
    
- <span data-ttu-id="c4500-p107">此程序包括複製並儲存加密金鑰、 儲存機碼和識別機碼和 Url 的數字的複本。此資訊會用於加密和上傳 PST 檔案之步驟 5。請務必採取預防措施來保護這些剛剛像您會保護密碼或其他安全性相關資訊。例如您可能會將其儲存至受密碼保護 Microsoft Word 文件或將其儲存至已加密的 USB 磁碟機。請參閱[的詳細資訊](#more-information)] 區段中的下列機碼、 識別碼、 及 Url 的範例。</span><span class="sxs-lookup"><span data-stu-id="c4500-p107">This procedure involves copying and saving a copy of an encryption key, a storage key, and a number of identification keys and URLs. This information will be used in Step 5 to encrypt and upload your PST files. Be sure to take precautions to protect these just like you would protect passwords or other security-related information. For example you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](#more-information) section for an example of these keys, IDs, and URLs.</span></span> 
    
- <span data-ttu-id="c4500-p108">您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。您執行此動作以指定在非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。如需詳細資訊，請參閱[步驟 7](#step-7-create-the-pst-import-mapping-file) 。</span><span class="sxs-lookup"><span data-stu-id="c4500-p108">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="c4500-p109">在 Exchange 混合部署中，您可以 PST 檔案匯入雲端式封存信箱的主要信箱位於內部部署的使用者。您這麼做依照 PST 匯入對應檔案中的下列：</span><span class="sxs-lookup"><span data-stu-id="c4500-p109">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="c4500-147">指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。</span><span class="sxs-lookup"><span data-stu-id="c4500-147">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="c4500-148">指定**TRUE**值`IsArchive`參數。</span><span class="sxs-lookup"><span data-stu-id="c4500-148">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="c4500-149">如需詳細資訊，請參閱[步驟 7](#step-7-create-the-pst-import-mapping-file) 。</span><span class="sxs-lookup"><span data-stu-id="c4500-149">See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="c4500-p110">PST 檔案匯入至 Office 365 信箱之後，為信箱設定保留功能會開啟無限期的持續期間。這表示將不會處理在您關閉保留功能或設定要關閉保留日期之前中指派給信箱的保留原則。為什麼這麼做這？如果舊匯入至信箱的郵件，則它們可能會永久刪除 （清除） 因為其保留期間已過期為基礎之信箱的保留設定。將信箱設定保留功能將會讓信箱擁有者時間來管理這些新匯入訊息或讓您變更信箱的保留設定的時間。請參閱如需管理保留功能的建議[的詳細資訊](#more-information)] 區段。</span><span class="sxs-lookup"><span data-stu-id="c4500-p110">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](#more-information) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="c4500-156">如果您不需要加密 PST 檔案您將其上傳至 Office 365 之前，請參閱[使用網路上傳至匯入至 Office 365 的 PST 檔案](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="c4500-156">If you don't need to encrypt your PST files before you upload them to Office 365, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
    
- <span data-ttu-id="c4500-157">如需使用網路上傳至 PST 檔案匯入 Office 365 常見問題集問題，請參閱 ＜[常見問題集匯入至 Office 365 的 PST 檔案](faqimporting-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c4500-157">For frequently asked questions about using network upload to import PST files to Office 365, see [FAQ about importing PST files to Office 365](faqimporting-pst-files-to-office-365.md).</span></span>
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a><span data-ttu-id="c4500-158">步驟 1：為 PST 匯入設定 Azure Rights Management </span><span class="sxs-lookup"><span data-stu-id="c4500-158">Step 1: Set up Azure Rights Management for PST Import</span></span>

<span data-ttu-id="c4500-p111">PST 匯入使用 Office 365 的 Azure 版權管理 (Azure RMS) 服務所提供的加密功能。這可讓您將它們上載到 Office 365 之前加密 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-p111">PST Import uses the encryption functionality provided by the Azure Rights Management (Azure RMS) service in Office 365. This lets you to encrypt PST files before uploading them to Office 365.</span></span> 
  
<span data-ttu-id="c4500-161">設定 Azure RMS PST 匯入包含三個步驟：</span><span class="sxs-lookup"><span data-stu-id="c4500-161">Configuring Azure RMS for PST Import consists of three steps:</span></span>
  
- [<span data-ttu-id="c4500-162">啟動 Azure RMS</span><span class="sxs-lookup"><span data-stu-id="c4500-162">Activating Azure RMS</span></span>](#activate-azure-rms)
    
- [<span data-ttu-id="c4500-163">設定 RMS in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c4500-163">Configuring RMS in Exchange Online</span></span>](#configure-rms-in-exchange-online)
    
- [<span data-ttu-id="c4500-164">安裝 Active Directory RMS 用戶端</span><span class="sxs-lookup"><span data-stu-id="c4500-164">Installing the Active Directory RMS Client</span></span>](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a><span data-ttu-id="c4500-165">啟動 Azure RMS</span><span class="sxs-lookup"><span data-stu-id="c4500-165">Activating Azure RMS</span></span>

<span data-ttu-id="c4500-p112">Azure RMS 已停用根據預設，但寄件者或組織中的其他系統管理員可能已啟動它。遵循指示安裝並啟動 Azure DRM[啟動 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) 。</span><span class="sxs-lookup"><span data-stu-id="c4500-p112">Azure RMS is disabled by default, but you or another administrator in your organization might have activated it. Follow instructions on [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) to install and activate Azure DRM.</span></span>
  
### <a name="configuring-rms-in-exchange-online"></a><span data-ttu-id="c4500-168">設定 RMS in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c4500-168">Configuring RMS in Exchange Online</span></span>

<span data-ttu-id="c4500-p113">您已啟動版權管理服務之後下, 一步是設定在 Exchange Online 使用 Azure RMS 設定資訊版權管理 (IRM)。如需詳細資訊，請參閱 ＜[設定 IRM 以使用 Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816)。</span><span class="sxs-lookup"><span data-stu-id="c4500-p113">After you've activated the Rights Management service, the next step is to set up Information Rights Management (IRM) in Exchange Online to use Azure RMS. For more information, see [Configure IRM to use Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).</span></span>
  
1. <span data-ttu-id="c4500-171">[連線至 Exchange Online 使用遠端 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 )。</span><span class="sxs-lookup"><span data-stu-id="c4500-171">[Connect to Exchange Online using Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).</span></span>
    
2. <span data-ttu-id="c4500-172">執行下列命令來設定 RMS 金鑰共用 URL。</span><span class="sxs-lookup"><span data-stu-id="c4500-172">Run the following command to set the RMS key sharing URL.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    <span data-ttu-id="c4500-173">請根據貴組織的所在位置，透過下表來判斷正確的 RMS 金鑰共用位置。</span><span class="sxs-lookup"><span data-stu-id="c4500-173">Use the following table to determine the correct RMS key sharing location for the location of your organization.</span></span>
    
    |<span data-ttu-id="c4500-174">**位置**</span><span class="sxs-lookup"><span data-stu-id="c4500-174">**Location**</span></span>|<span data-ttu-id="c4500-175">**RMS 金鑰共用位置**</span><span class="sxs-lookup"><span data-stu-id="c4500-175">**RMS key sharing location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c4500-176">北美</span><span class="sxs-lookup"><span data-stu-id="c4500-176">North America</span></span>  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="c4500-177">歐盟</span><span class="sxs-lookup"><span data-stu-id="c4500-177">European Union</span></span>  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="c4500-178">亞洲</span><span class="sxs-lookup"><span data-stu-id="c4500-178">Asia</span></span>  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="c4500-179">南美洲</span><span class="sxs-lookup"><span data-stu-id="c4500-179">South America</span></span>  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="c4500-180">Office 365 for Government (政府社群雲端)</span><span class="sxs-lookup"><span data-stu-id="c4500-180">Office 365 for Government (Government Community Cloud)</span></span>  <br/> | <span data-ttu-id="c4500-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c4500-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span></span> <br/> |
   
    > [!NOTE]
    > <span data-ttu-id="c4500-182"><sup>1</sup>只有已購買 Office 365 for Government Sku （政府社群雲端） 的客戶應該使用此 RMS 金鑰共用位置。</span><span class="sxs-lookup"><span data-stu-id="c4500-182"><sup>1</sup> Only customers who have purchased Office 365 for Government SKUs (Government Community Cloud) should use this RMS key sharing location.</span></span> 
  
    <span data-ttu-id="c4500-183">例如，此命令會設定 RMS Online 金鑰共用位置在 Exchange Online 客戶位於 「 北美地區 」 的。</span><span class="sxs-lookup"><span data-stu-id="c4500-183">For example, this command configures the RMS Online key sharing location in Exchange Online for a customer located in North America.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. <span data-ttu-id="c4500-184">執行下列命令以從 RMS Online 的受信任的發行網域 (TPD) 匯入 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="c4500-184">Run the following command to import a Trusted Publishing Domain (TPD) from RMS Online to your Office 365 organization.</span></span> 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    <span data-ttu-id="c4500-185">TPD 包含在組織中使用 RMS 功能所需的設定，其包括加密 PST 檔案。 </span><span class="sxs-lookup"><span data-stu-id="c4500-185">A TPD contains the settings needed to use RMS features in your organization, including encrypting PST files.</span></span> 
    
4. <span data-ttu-id="c4500-186">執行下列命令以針對 Office 365 組織啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c4500-186">Run the following command to enable IRM for your Office 365 organization.</span></span>
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a><span data-ttu-id="c4500-187">安裝 Active Directory RMS 用戶端</span><span class="sxs-lookup"><span data-stu-id="c4500-187">Installing the Active Directory RMS Client</span></span>

<span data-ttu-id="c4500-p114">本節中的最後一個步驟是下載 Rights Management Services (RMS) 用戶端 2.1。此軟體可協助保護 Azure RMS 存取並保護通過使用 Azure 您安裝的應用程式在您將用來加密和上傳步驟 5 中的 PST 檔案的相同電腦上的 RMS 用戶端的資訊。</span><span class="sxs-lookup"><span data-stu-id="c4500-p114">The last step in this section is to download the Rights Management Services (RMS) Client 2.1. This software helps protect access to Azure RMS and protects information flowing through applications that use Azure RMS. Install the RMS client on the same computer that you'll use to encrypt and upload PST files in Step 5.</span></span> 
  
1. <span data-ttu-id="c4500-191">下載[Rights Management Service 用戶端 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)。</span><span class="sxs-lookup"><span data-stu-id="c4500-191">Download [Rights Management Service Client 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).</span></span>
    
2. <span data-ttu-id="c4500-192">執行 Active Directory Rights Management Service Client 2.1 精靈來安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="c4500-192">Run the Active Directory Rights Management Service Client 2.1 wizard to install the client.</span></span>

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a><span data-ttu-id="c4500-193">步驟 2：為 PST 匯入產生加密金鑰</span><span class="sxs-lookup"><span data-stu-id="c4500-193">Step 2: Generate an encryption key for PST Import</span></span>

<span data-ttu-id="c4500-p115">您已設定 「 Azure RMS 之後下, 一步是產生會用來加密您上傳到 Office 365 的 PST 檔案的加密金鑰 （稱為 「 對稱的索引鍵）。您將做為服務主要 Azure Active Directory 中新增 PST 匯入服務來執行這項作業。將此應用程式以服務主要名稱會允許您將上傳時直接與 Azure Active Directory 進行驗證 PST 匯入 service 加密的 Azure 儲存位置中之步驟 5 的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-p115">After you've set up Azure RMS, the next step is to generate an encryption key (called a symmetric key) that will be used to encrypt the PST files that you upload to Office 365. You'll do this by adding the PST Import service as a service principal in Azure Active Directory. Adding this application as a service principal will allow the PST Import service to authenticate directly with Azure Active Directory when you upload encrypted the PST files to the Azure storage location in Step 5.</span></span>
  
1. <span data-ttu-id="c4500-197">啟動 Windows powershell 的 Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="c4500-197">Start the Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c4500-198">執行下列命令來連接 Microsoft Online Service。</span><span class="sxs-lookup"><span data-stu-id="c4500-198">Run the following command to connect to the Microsoft Online service.</span></span>
    
    ```
    Connect-MsolService
    ```

3. <span data-ttu-id="c4500-199">輸入 Office 365 組織中系統管理員帳戶的認證並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c4500-199">Enter the credentials for an administrator account in your Office 365 organization, and then click **OK**.</span></span>
    
4. <span data-ttu-id="c4500-p116">執行下列命令來產生加密金鑰 (稱為對稱金鑰)。您將以透過建立新 PST 加密主體的方式進行。</span><span class="sxs-lookup"><span data-stu-id="c4500-p116">Run the following command to generate an encryption key (call a symmetric key). You'll do this by creating a new PST Encryption Principal.</span></span>
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    <span data-ttu-id="c4500-202">系統會顯示新 PST 加密主體的對稱金鑰以及屬性。</span><span class="sxs-lookup"><span data-stu-id="c4500-202">The system displays the symmetric key and the properties for the new PST Encryption Principal.</span></span>
    
    ![複製並儲存所顯示的對稱金鑰](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. <span data-ttu-id="c4500-p117">將對稱金鑰複製到文字檔案或 Word 檔案中。如先前所述，請確定已採取相關預防措施來保護此檔案。因為對稱金鑰僅會顯示這一次，所以您可以考慮擷取此視窗的螢幕擷取畫面，然後將其儲存至相同檔案中。 </span><span class="sxs-lookup"><span data-stu-id="c4500-p117">Copy the symmetric key to a text or Word file. As previously stated, be sure to take precautions to protect this file. Because this is the only time that the symmetric key is displayed, you might also consider taking a screenshot of this window and saving it to the same file.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="c4500-p118">在您建立 PST 加密主體後，將無法使用 **Get-MsolServicePrincipal** 指令程式來擷取對稱金鑰。這就是儲存金鑰為何如此重要的原因。</span><span class="sxs-lookup"><span data-stu-id="c4500-p118">After you create the PST Encryption Principal, you won't be able to retrieve the symmetric key by using the **Get-MsolServicePrincipal** cmdlet. That's why it's important to save the key.</span></span> 
  
<span data-ttu-id="c4500-p119">開啟並連線至 Microsoft Online 服務保留 Azure Active Directory 的 Windows PowerShell 模組。您將在此視窗的下一個步驟中執行的命令。</span><span class="sxs-lookup"><span data-stu-id="c4500-p119">Keep the Azure Active Directory Module for Windows PowerShell open and connected to the Microsoft Online service. You'll run a command in this window in the next step.</span></span>

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a><span data-ttu-id="c4500-211">步驟 3： 取得 RMS 租用戶識別碼和授權的 URL</span><span class="sxs-lookup"><span data-stu-id="c4500-211">Step 3: Obtain RMS tenant ID and licensing URL</span></span>

<span data-ttu-id="c4500-p120">下一個步驟是取得租用戶識別碼和 Azure RMS 服務組織的授權的位置 URL。複製並將此資訊儲存至相同檔案包含從步驟 2 對稱的索引鍵。識別碼和 URL 將用於在步驟 5 來加密 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-p120">The next step is to obtain the tenant ID and licensing location URL for the Azure RMS service for your organization. Copy and save this information to the same file that contains the symmetric key from Step 2. The ID and URL will be used in Step 5 to encrypt your PST files.</span></span>
  
1. <span data-ttu-id="c4500-215">Azure Active Directory 模組 （這連線至 Microsoft Online 服務） 的 Windows powershell 中執行下列命令來連線到 Office 365 組織中的 Azure RMS 服務。</span><span class="sxs-lookup"><span data-stu-id="c4500-215">In the Azure Active Directory Module for Windows PowerShell (which is connected to the Microsoft Online service), run the following command to connect to the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Connect-AadrmService 
    ```

2. <span data-ttu-id="c4500-216">輸入您的 Office 365 組織中系統管理員帳戶的認證並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c4500-216">Enter the credentials for an administrator account in your Office 365 organization and then click **OK**.</span></span>
    
3. <span data-ttu-id="c4500-217">執行下列命令以顯示 Office 365 組織租用戶識別碼 Azure RMS 服務。</span><span class="sxs-lookup"><span data-stu-id="c4500-217">Run the following command to display the tenant ID for the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    <span data-ttu-id="c4500-218">複製並儲存的值`BPOSId`屬性。</span><span class="sxs-lookup"><span data-stu-id="c4500-218">Copy and save the value for the  `BPOSId` property.</span></span> 
    
4. <span data-ttu-id="c4500-219">執行下列命令以顯示 Azure RMS 服務授權的位置。</span><span class="sxs-lookup"><span data-stu-id="c4500-219">Run the following command to display the licensing location for your Azure RMS service.</span></span>
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    <span data-ttu-id="c4500-220">複製並儲存的值`LicensingIntranetDistributionPointUrl`屬性。</span><span class="sxs-lookup"><span data-stu-id="c4500-220">Copy and save the value for the  `LicensingIntranetDistributionPointUrl` property.</span></span> 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a><span data-ttu-id="c4500-221">步驟 4： 下載 PST 匯入工具並複製 SAS URL</span><span class="sxs-lookup"><span data-stu-id="c4500-221">Step 4: Download the PST Import tools and copy the SAS URL</span></span>

<span data-ttu-id="c4500-p121">現在您已設定 Azure RMS 並取得必要加密 PST 檔案的識別碼下, 一步是下載並安裝到 Office 365 的工具，將會執行在步驟 5 中加密及上傳 PST 檔案。這些工具的 Azure AzCopy 工具與 Office 365 資料加密工具。您也將您的組織複製 SAS URL。此 URL 會在 Microsoft 雲端組織和共用存取簽章 (SAS) 金鑰 Azure 儲存位置的網路 URL 的組合。此機碼提供 PST 檔案上傳至 Azure 儲存位置的必要權限。將它儲存到同一個檔案您是否已在步驟 2 和步驟 3 中複製的其他資訊。先前所述，請以保護 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="c4500-p121">Now that you've configured Azure RMS and obtained the IDs necessary to encrypt PST files, the next step is to download and install the tools that you will run in Step 5 to encrypt and upload PST files to Office 365. These tools are the Azure AzCopy tool and the Office 365 Data Encryption tool. You'll also copy the SAS URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and a Shared Access Signature (SAS) key. This key provides you with the necessary permissions to upload PST files to your Azure storage location. Save it to the same file that you've copied the other information to in Step 2 and Step 3. As previously stated, take precautions to protect the SAS URL.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c4500-p122">您必須使用 Azure AzCopy 5.0 版成功 PST 檔案上傳至 Azure 儲存位置。較新版本的 AzCopy 工具不支援將 PST 檔案匯入 Office 365。請務必 AzCopy 工具從**上傳檔案透過網路**頁面下載遵循此步驟中的程序。</span><span class="sxs-lookup"><span data-stu-id="c4500-p122">You have to use Azure AzCopy version 5.0 to successfully upload PST files to the Azure storage location. Newer versions of the AzCopy tool aren't supported for importing PST files to Office 365. Be sure to download the AzCopy tool from the **Upload files over the network** page by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="c4500-232">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c4500-232">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c4500-233">登入 Office 365 使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c4500-233">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="c4500-234">在左窗格中，按一下 [**資料控管**和 [**匯入**。</span><span class="sxs-lookup"><span data-stu-id="c4500-234">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="c4500-235">在 [**匯入**] 頁面上，按一下 [**移至 [匯入服務**。</span><span class="sxs-lookup"><span data-stu-id="c4500-235">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="c4500-236">在 [ **Office 365 的匯入資料**] 頁面上按一下 [**新增工作**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**上傳的電子郵件 （PST 檔案）**。</span><span class="sxs-lookup"><span data-stu-id="c4500-236">On the **Import data to Office 365** page, click **New job** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="c4500-237">按一下 [**上傳檔案透過網路**] 頁面的 [步驟 2 中的 [**顯示網路上傳 SAS URL**]。</span><span class="sxs-lookup"><span data-stu-id="c4500-237">On the **Upload files over the network** page, in step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="c4500-p123">顯示 URL 後，將其複製並將它儲存在您儲存其他按鍵的檔案。請務必複製整個 URL。</span><span class="sxs-lookup"><span data-stu-id="c4500-p123">After the URL is displayed, copy it and save it in the file where you saved the other keys. Be sure to copy the entire URL.</span></span> 
    
8. <span data-ttu-id="c4500-240">在步驟 3 中，按一下 [**下載 Azure AzCopy 工具**下載並安裝 Azure AzCopy 工具。</span><span class="sxs-lookup"><span data-stu-id="c4500-240">In step 3, click **Download the Azure AzCopy tool** to download and install the Azure AzCopy tool.</span></span> 
    
9. <span data-ttu-id="c4500-241">在快顯視窗中，按一下 [安裝 Azure AzCopy 工具的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="c4500-241">In the pop-up window, click **Run** to install the Azure AzCopy tool.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="c4500-p124">請務必在預設位置是安裝 Azure AzCopy 工具`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`的電腦上執行 64 位元 Windows。那是因為當您在步驟 5 中執行 O365ImportTool.exe，它會尋找在此位置的 AzCopy 工具。</span><span class="sxs-lookup"><span data-stu-id="c4500-p124">Be sure to install the Azure AzCopy tool in the default location, which is `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` on a computer running 64-bit Windows. That's because when you run the O365ImportTool.exe in Step 5, it looks for the AzCopy tool in this location.</span></span> 
  
10. <span data-ttu-id="c4500-244">您已安裝 Azure AzCopy 工具之後，按一下 [**下載 Office 365 資料加密及匯入工具**。</span><span class="sxs-lookup"><span data-stu-id="c4500-244">After you've installed the Azure AzCopy tool, click **Download the Office 365 Data Encryption and Import tool**.</span></span>
    
11. <span data-ttu-id="c4500-245">在快顯視窗中，按一下 [**儲存** \> O365ImportTool.zip 檔案儲存到資料夾本機電腦上的 [**另存為**。</span><span class="sxs-lookup"><span data-stu-id="c4500-245">In the pop-up window, click **Save** \> **Save as** to save the O365ImportTool.zip file to a folder on your local computer.</span></span> 
    
12. <span data-ttu-id="c4500-246">解壓縮 O365ImportTool.zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-246">Extract the O365ImportTool.zip file.</span></span>
    
13. <span data-ttu-id="c4500-247">按一下 [**取消**] 關閉 [**上傳檔案透過網路**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4500-247">Click **Cancel** to close the **Upload files over the network** page.</span></span> 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a><span data-ttu-id="c4500-248">步驟 5： 加密和您 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c4500-248">Step 5: Encrypt and upload your PST files to Office 365</span></span>

<span data-ttu-id="c4500-p125">完成步驟 1 到步驟 4 之後，即可使用 O365ImportTool.exe 工具來加密和 PST 檔案上傳至 Office 365。這項工具會加密 PST 檔案，然後上傳並將其儲存在 Microsoft 雲端 Azure 的儲存位置。若要完成此步驟，PST 檔案必須位於檔案共用或組織中的檔案伺服器。這就是所謂的下列程序中的來源目錄。每次執行 O365ImportTool.exe 工具，您將可以指定不同的來源目錄。</span><span class="sxs-lookup"><span data-stu-id="c4500-p125">After you have completed Step 1 through Step 4, you're ready to use the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. This tool encrypts your PST files and then uploads and stores them in an Azure storage location in the Microsoft cloud. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure. Each time you run the O365ImportTool.exe tool, you'll can specify a different source directory.</span></span> 
  
1. <span data-ttu-id="c4500-254">在您的本機電腦上開啟 [命令提示字元]。</span><span class="sxs-lookup"><span data-stu-id="c4500-254">Open a Command Prompt on your local computer.</span></span>
    
2. <span data-ttu-id="c4500-255">移至您在步驟 4 中安裝 O365ImportTool.exe 工具的目錄。</span><span class="sxs-lookup"><span data-stu-id="c4500-255">Go to the directory where you installed the O365ImportTool.exe tool in Step 4.</span></span>
    
3. <span data-ttu-id="c4500-256">執行下列命令來加密和 PST 檔案上傳至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c4500-256">Run the following command to encrypt and upload PST files to Office 365.</span></span>
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    <span data-ttu-id="c4500-p126">下表說明了參數與其需要的值。請注意，您在先前步驟中所取得的資訊，會在這些參數內的值中使用。</span><span class="sxs-lookup"><span data-stu-id="c4500-p126">The following table describes the parameters and their required values. Note that the information you obtained in the previous steps is used in the values for these parameters.</span></span>
    
    |<span data-ttu-id="c4500-259">**參數**</span><span class="sxs-lookup"><span data-stu-id="c4500-259">**Parameter**</span></span>|<span data-ttu-id="c4500-260">**描述**</span><span class="sxs-lookup"><span data-stu-id="c4500-260">**Description**</span></span>|<span data-ttu-id="c4500-261">**範例**</span><span class="sxs-lookup"><span data-stu-id="c4500-261">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |<span data-ttu-id="c4500-262">指定包含要上傳至 Office 365 的 PST 檔案在組織中的來源目錄。</span><span class="sxs-lookup"><span data-stu-id="c4500-262">Specifies the source directory in your organization that contains the PST files that will be uploaded to Office 365.</span></span>  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |<span data-ttu-id="c4500-p127">指定授權 Azure RMS 服務的位置。使用的值`LicensingIntranetDistributionPointUrl`您在步驟 3 中取得的屬性。請務必環繞雙引號使用此參數的值 ("")</span><span class="sxs-lookup"><span data-stu-id="c4500-p127">Specifies the licensing location for your Azure RMS service. Use the value of the  `LicensingIntranetDistributionPointUrl` property that you obtained in Step 3. Be sure to surround the value of this parameter with double-quotation marks (" ")  </span></span><br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |<span data-ttu-id="c4500-p128">指定 Azure RMS 組織的識別碼。使用的值`BPOSId`您在步驟 3 中取得的屬性。</span><span class="sxs-lookup"><span data-stu-id="c4500-p128">Specifies the identity of your Azure RMS organization. Use the value of the  `BPOSId` property that you obtained in Step 3.  </span></span><br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |<span data-ttu-id="c4500-p129">步驟 2 中指定所取得的對稱金鑰。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c4500-p129">Specifies the symmetric key that you obtained in Step 2. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |<span data-ttu-id="c4500-p130">會指定是否將 PST 檔案上傳透過網路或隨附其硬碟上。此值`upload`指出您已透過網路上載的檔案。此值`drive`表示您要傳送 Pst 硬碟上。</span><span class="sxs-lookup"><span data-stu-id="c4500-p130">Specifies whether you upload PST files over the network or ship them on a hard drive. The value  `upload` indicates that you are uploading the files over the network. The value  `drive` indicates that you are shipping the PSTs on a hard drive.  </span></span><br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |<span data-ttu-id="c4500-p131">在 Office 365 PST 檔案要上傳至 ； 指定目的地這是您的組織 Azure 儲存位置。此參數的值是由您在步驟 4 中複製 SAS URL 中的網路上傳 URL 所組成。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c4500-p131">Specifies the destination in Office 365 where your PST files will be uploaded to; this is the Azure storage location for your organization. The value for this parameter consists of the network upload URL from the SAS URL that you copied in Step 4. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/><br/> <span data-ttu-id="c4500-p132">**提示：**（選用）您可以在 Azure 的儲存位置上傳至的加密的 PST 檔案中指定的子資料夾。您執行方法是在網路上傳 URL 中新增子資料夾位置 （之後"ingestiondata")。第一個範例不會指定子資料夾;這表示 Pst 將可上傳到根目錄 （名為*ingestiondata* ） 的 Azure 儲存位置。第二個範例 Azure 儲存位置中的上傳至 （名為*EncryptedPSTs* ） 的子資料夾的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-p132">**Tip:** (Optional) You can specify a subfolder in the Azure storage location to upload the encrypted PST files to. You do this by adding a subfolder location (after "ingestiondata") in the network upload URL. The first example doesn't specify a subfolder; that means the PSTs will be uploaded to the root (named  *ingestiondata*  ) of the Azure storage location. The second example uploads the PST files to a subfolder (named  *EncryptedPSTs*  ) in the Azure storage location.</span></span>           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> <span data-ttu-id="c4500-280">或</span><span class="sxs-lookup"><span data-stu-id="c4500-280">Or</span></span>  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |<span data-ttu-id="c4500-p133">會指定您組織的 SAS 索引鍵。此參數的值是由 SAS 金鑰與您在步驟 4 中複製 SAS URL 所組成。請注意 SAS 機碼中的第一個字元為問號 ("？")。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c4500-p133">Specifies the SAS key for you organization. The value for this parameter consists of the SAS key from the SAS URL that you copied in Step 4. Note that first character in the SAS key is a question mark ("?"). Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |<span data-ttu-id="c4500-285">使 O365ImportTool.exe 工具會將位於所指定的來源目錄中的子資料夾中的 Pst 檔案複製此選用參數會指定遞迴模式`/srcdir:`參數。</span><span class="sxs-lookup"><span data-stu-id="c4500-285">This optional switch specifies the recursive mode so that the O365ImportTool.exe tool will copy PSTs files that are located in subfolders in the source directory that is specified by the  `/srcdir:` parameter.</span></span>  <br/><br/> <span data-ttu-id="c4500-p134">**附註：** 如果加上此參數，在子資料夾中的 PST 檔案不同的檔案路徑名稱中有 Azure 的儲存位置之後他們正在上傳。您必須在您在步驟 7 中建立 CSV 檔案中指定的實際檔案路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="c4500-p134">**Note:** If you include this switch, PST files in subfolders will have a different file pathname in the Azure storage location after they're uploaded. You'll have to specify the exact file pathname in the CSV file that you create in Step 7.</span></span>           | `/recurse` <br/> |
   
    <span data-ttu-id="c4500-288">這是 O365ImportTool.exe 工具針對各個參數使用實際值的語法範例︰</span><span class="sxs-lookup"><span data-stu-id="c4500-288">Here's an example of the syntax for the O365ImportTool.exe tool using actual values for each parameter:</span></span>
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    <span data-ttu-id="c4500-p135">在您執行命令後，便會顯示 PST 檔案加密及上傳進度的狀態訊息。最終狀態訊息會顯示已成功加密及上傳的檔案總數。 </span><span class="sxs-lookup"><span data-stu-id="c4500-p135">After you run the command, status messages are displayed that show the progress of encrypting and uploading the PST files. A final status message shows the total number of files that were successfully encrypted and uploaded.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c4500-p136">您已順利執行 O365ImportTool.exe 命令並確認所有參數正確都無誤後，命令列語法到您複製資訊相同 （安全） 檔案的複本儲存您在取得上述步驟。然後您可以命令複製並貼入此命令提示字元中每一個您想要執行 O365ImportTool.exe 工具來加密和 PST 檔案上傳至 Office 365 的時間。您可能必須變更的唯一值是針對該組`/srcdir:`和`/upload-dest:`參數。</span><span class="sxs-lookup"><span data-stu-id="c4500-p136">After you successfully run the O365ImportTool.exe command and verify that all the parameters are correct, save a copy of the command line syntax to the same (secured) file where you copied the information you obtained in the previous steps. Then you can copy and paste this command in a Command Prompt each time that you want to run the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. The only values you might have to change are the ones for the  `/srcdir:` and  `/upload-dest:` parameters.</span></span> 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="c4500-294">（選用）步驟 6： 檢視清單中的 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c4500-294">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="c4500-p137">為選用的步驟，您可以安裝及使用 Microsoft Azure 儲存在檔案總管 （這是免費，開放原始碼工具） 來檢視您已上傳至 Azure blob PST 檔案的清單。為達成此目的三種很好的原因有：</span><span class="sxs-lookup"><span data-stu-id="c4500-p137">As an optional step, you can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that you've uploaded to the Azure blob. There are three good reasons to do this:</span></span>
  
- <span data-ttu-id="c4500-297">確認 PST 檔案從共用的資料夾或檔案伺服器在組織中的已成功上傳至 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="c4500-297">Verify that PST files from the shared folder or file server in your organization were successfully uploaded to the Azure blob.</span></span>

- <span data-ttu-id="c4500-p138">確認已加密的 PST 檔案。加密的 PST 檔案有`.pfile`附加至 PST 檔案名稱 ； 的副檔名例如， `pilarp.pst.pfile`。</span><span class="sxs-lookup"><span data-stu-id="c4500-p138">Verify that the PST files are encrypted. Encrypted PST files have a  `.pfile` extension appended to the PST filename; for example,  `pilarp.pst.pfile`.</span></span>
    
- <span data-ttu-id="c4500-p139">確認每個 PST 檔案上傳至 Azure blob 的檔案名稱 （和子資料夾 pathname 如果包含一個）。當您建立對應檔案中的下一個步驟因為您有指定的資料夾路徑名稱和每個 PST 檔案的檔案名稱 PST，這是很有幫助。確認這些名稱可以協助降低您 PST 對應檔案中的潛在錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4500-p139">Verify the filename (and the subfolder pathname if you included one) for each PST file uploaded to the Azure blob. This is really helpful when you're creating the PST mapping file in the next step because you have to specify both the folder pathname and filename for each PST file. Verifying these names can help reduce potential errors in your PST mapping file.</span></span>
    
<span data-ttu-id="c4500-303">Microsoft Azure 儲存在檔案總管處於預覽。</span><span class="sxs-lookup"><span data-stu-id="c4500-303">The Microsoft Azure Storage Explorer is in Preview.</span></span> 
  
 > [!IMPORTANT]
>  <span data-ttu-id="c4500-p140">您無法使用 Azure 儲存在檔案總管上傳或修改 PST 檔案。將 PST 檔案匯入 Office 365 唯一支援的方法是使用 AzCopy。此外，您無法刪除您已上傳至 Azure blob 的 PST 檔案。如果您嘗試刪除 PST 檔案，將會收到有關不會察覺必要的權限的錯誤。請注意 Azure 儲存區域會自動刪除所有 PST 檔案。如果有任何匯入工作進行，然後所有 PST 檔案中的 [ **ingestiondata** ] 容器中會不刪除 30 天後所建立的最新的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c4500-p140">You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="c4500-310">若要安裝 Azure 儲存在檔案總管並連線至 Azure 儲存區：</span><span class="sxs-lookup"><span data-stu-id="c4500-310">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="c4500-311">下載並安裝[Microsoft Azure 儲存檔案總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="c4500-311">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
2. <span data-ttu-id="c4500-312">啟動 Microsoft Azure 儲存在檔案總管、 以滑鼠右鍵按一下左窗格中的**存放區的帳戶**和 [**連線至 Azure 存放區**。</span><span class="sxs-lookup"><span data-stu-id="c4500-312">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span> 
    
    ![以滑鼠右鍵按一下 [儲存的帳戶，然後按一下 [連線至 Azure 存放區](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. <span data-ttu-id="c4500-314">在 [**連接到 Azure 存放區**] 下方，在步驟 4 中貼上您取得 SAS URL] 和 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4500-314">In the box under **Connect to Azure storage**, paste the SAS URL that you obtained in Step 4, and then click **Next**.</span></span> 
    
    ![在連接至 Azure 存放區] 頁面上的方塊中貼上 SAS URL](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. <span data-ttu-id="c4500-316">在 [**連線摘要**] 頁面上您可以檢閱連線資訊，並再按一下 [**連線**。</span><span class="sxs-lookup"><span data-stu-id="c4500-316">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span> 
    
5. <span data-ttu-id="c4500-317">[**存放區的帳戶**] 下展開 **(服務 SAS)** ] 節點，然後展開**Blob 容器**] 節點。</span><span class="sxs-lookup"><span data-stu-id="c4500-317">Under **Storage Accounts**, expand the **(Service SAS)** node, and then expand the **Blob Containers** node.</span></span> 
    
6. <span data-ttu-id="c4500-318">以滑鼠右鍵按一下**ingestiondata**，並再按一下 [**開啟 Blob 容器編輯器**。</span><span class="sxs-lookup"><span data-stu-id="c4500-318">Right-click **ingestiondata**, and then click **Open Blob Container Editor**.</span></span>
    
    ![以滑鼠右鍵按一下 ingestiondata，然後按一下 [開啟 Blob 容器編輯器]](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    <span data-ttu-id="c4500-320">會顯示 Azure 存放區] 區域中，您在步驟 5 中上傳的 PST 檔案的清單。</span><span class="sxs-lookup"><span data-stu-id="c4500-320">The Azure storage area, with a list of the PST files that you uploaded in Step 5 is displayed.</span></span>
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. <span data-ttu-id="c4500-p141">使用 Microsoft Azure 儲存在檔案總管完成作業後，用滑鼠右鍵按一下**ingestiondata**，並再按一下 [**卸離**中斷與 Azure 儲存區的連線。否則，您會收到錯誤的下次您嘗試附加。</span><span class="sxs-lookup"><span data-stu-id="c4500-p141">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a><span data-ttu-id="c4500-325">步驟 7： 建立 PST 匯入對應檔案</span><span class="sxs-lookup"><span data-stu-id="c4500-325">Step 7: Create the PST Import mapping file</span></span>

<span data-ttu-id="c4500-p142">PST 檔案已加密及上傳至 Office 365 組織 Azure 儲存位置之後下, 一步是建立逗點分隔值 (CSV) 檔案，指定 PST 檔案會以匯入的使用者信箱。當您建立 PST 匯入工作，會送出這個的 CSV 檔案中的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="c4500-p142">After the PST files have been encrypted and uploaded to the Azure storage location for your Office 365 organization, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="c4500-328">[下載 PST 匯入對應檔案的複本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="c4500-328">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span> 
    
2. <span data-ttu-id="c4500-p143">開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。</span><span class="sxs-lookup"><span data-stu-id="c4500-p143">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    <span data-ttu-id="c4500-p144">第一列或欄位名稱] 列的 CSV 檔案列出要使用 PST 匯入服務至 PST 檔案匯入使用者信箱的參數。每個參數名稱是以逗號分隔。標頭列] 下方的每一個資料列代表將 PST 檔案匯入特定信箱的參數值。您將需要一列的每一個您想要匯入使用者信箱的 PST 檔案。請務必對應檔案中的版面配置區資料取代實際資料。</span><span class="sxs-lookup"><span data-stu-id="c4500-p144">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that you want to import to a user mailbox. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4500-337">不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。</span><span class="sxs-lookup"><span data-stu-id="c4500-337">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="c4500-338">使用下列表格的資訊，將所需的資訊填入 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-338">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="c4500-339">**參數**</span><span class="sxs-lookup"><span data-stu-id="c4500-339">**Parameter**</span></span>|<span data-ttu-id="c4500-340">**描述**</span><span class="sxs-lookup"><span data-stu-id="c4500-340">**Description**</span></span>|<span data-ttu-id="c4500-341">**範例**</span><span class="sxs-lookup"><span data-stu-id="c4500-341">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="c4500-p145">指定要匯入資料至 Office 365 服務。若要匯入 PST 檔案至使用者信箱，請使用`Exchange`。</span><span class="sxs-lookup"><span data-stu-id="c4500-p145">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> |<span data-ttu-id="c4500-344">在 Azure 的儲存位置上傳至 PST 檔案中之步驟 5 中指定的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="c4500-344">Specifies the folder location in the Azure storage location that you uploaded the PST files to in Step 5.</span></span>  <br/>  <span data-ttu-id="c4500-p146">如果您沒有加入選用的子資料夾名稱中的網路 URL 中`/upload-dest:`參數在步驟 5 中，將此參數保留空白 CSV 檔案中。如果在包含子資料夾名稱，請將它指定這個參數中。此參數的值是區分大小寫。無論如何，*不*包含"ingestiondata"中的值`FilePath`參數。</span><span class="sxs-lookup"><span data-stu-id="c4500-p146">If you didn't include an optional subfolder name in the network URL in the  `/upload-dest:` parameter in Step 5, leave this parameter blank in the CSV file. If you included a subfolder name, specify it in this parameter. The value for this parameter is case sensitive. Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter.  </span></span><br/> <br/><span data-ttu-id="c4500-p147">**重要：** 大小寫的檔案路徑名稱必須是所用如果 SAS URL 中包含的選用子資料夾名稱相同案例`/upload-dest:`在步驟 5 中的參數。例如，如果您是使用`EncryptedPSTs`的子資料夾名稱在步驟 5 中，然後使用`encryptedpsts`中`FilePath`CSV 檔中的參數，將會失敗 PST 檔案匯入。請務必在兩個執行個體中使用相同的大小寫。</span><span class="sxs-lookup"><span data-stu-id="c4500-p147">**Important:** The case for the file path name must be the same case that you used if you included an optional subfolder name in the SAS URL in the  `/upload-dest:` parameter in Step 5. For example, if you used  `EncryptedPSTs` for the subfolder name in Step 5 and then use  `encryptedpsts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="c4500-352">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c4500-352">(leave blank)</span></span>  <br/> <span data-ttu-id="c4500-353">或</span><span class="sxs-lookup"><span data-stu-id="c4500-353">Or</span></span>  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="c4500-p148">指定要匯入至使用者信箱的 PST 檔案的名稱。此參數的值是區分大小寫。因為加密 PST 檔案上傳至 Azure 儲存位置、`.pfile`副檔名新增至 PST 檔案名稱。您必須新增`.pfile`延伸模組名稱的 PST 檔案 CSV 檔案中。</span><span class="sxs-lookup"><span data-stu-id="c4500-p148">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive. Because the PST files that are uploaded to the Azure storage location are encrypted, a  `.pfile` extension is added to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file.  </span></span><br/><br/> <span data-ttu-id="c4500-p149">**重要：** CSV 檔案中的 PST 檔案名稱的大小寫必須已上傳至 Azure 儲存位置中之步驟 5 的 PST 檔案相同。例如，如果您使用`annb.pst.pfile`中`Name`參數中的 CSV 檔案，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入就會失敗。請務必 PST CSV 檔案中的名稱會使用為實際的 PST 檔案的大小寫相同。</span><span class="sxs-lookup"><span data-stu-id="c4500-p149">**Important:** The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 5. For example, if you use  `annb.pst.pfile` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="c4500-361">指定將匯入 PST 檔案的信箱電子郵件地址。 </span><span class="sxs-lookup"><span data-stu-id="c4500-361">Specifies the email address of the mailbox that the PST file will be imported to.</span></span>  <br/> <span data-ttu-id="c4500-p150">匯入 PST 檔案至不在作用中的信箱，您必須指定此參數的信箱 GUID。若要取得這個 GUID，請執行下列 PowerShell 命令 in Exchange Online：`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="c4500-p150">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  `Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid`</span></span> <br/><br/> <span data-ttu-id="c4500-p151">**附註：** 在某些情況下，您可能會有多個信箱使用同一個電子郵件地址，其中一個信箱不在作用中信箱和其他信箱位於虛刪除 （或非使用中） 的狀態。在下列情況下，您有指定信箱的信箱來唯一地識別要匯入至 PST 檔案的信箱 GUID。若要取得這個作用中信箱的 GUID，請執行下列 PowerShell 命令： `Get-Mailbox - <identity of active mailbox> | FL Guid`。若要取得虛刪除 （或非使用中） 的信箱的 GUID，請執行此命令`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="c4500-p151">**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox - <identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="c4500-368">或</span><span class="sxs-lookup"><span data-stu-id="c4500-368">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="c4500-p152">指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="c4500-p152">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="c4500-371">**FALSE**將 PST 檔案匯入使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="c4500-371">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="c4500-372">**True 是表示**將 PST 檔案匯入使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="c4500-372">**TRUE** Imports the PST file to the user's archive mailbox.</span></span>  <br/>  <span data-ttu-id="c4500-373">如果您將此參數保留空白，PST 檔案匯入使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="c4500-373">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/><br/> <span data-ttu-id="c4500-374">**附註：** 匯入 PST 檔案到雲端式封存信箱的主要信箱位於內部部署的使用者，只要指定此參數 **，則為 TRUE** ，並指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。</span><span class="sxs-lookup"><span data-stu-id="c4500-374">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify **TRUE** for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>           | `FALSE` <br/> <span data-ttu-id="c4500-375">或</span><span class="sxs-lookup"><span data-stu-id="c4500-375">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="c4500-376">指定要匯入 PST 檔案的信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4500-376">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="c4500-377">如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於信箱 （相同層級 [收件匣] 資料夾和其他預設信箱資料夾） 的根層級的新資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4500-377">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="c4500-378">如果您指定`/`、 PST 檔案中的項目會被匯入直接在使用者的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4500-378">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="c4500-p153">如果您指定`/<foldername>`、 PST 檔案中的項目將會匯入至名為子資料夾\*\<foldername\> \* 。例如，如果您是使用`/ImportedPst`、 項目會匯入至名為**ImportedPst**子資料夾。這個子資料夾會位於使用者的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4500-p153">If you specify  `/<foldername>`, items in the PST file will be imported to a subfolder named  *\<foldername\>*  . For example, if you used  `/ImportedPst`, items would be imported to a subfolder named **ImportedPst**. This subfolder will be located in the user's Inbox folder.  </span></span><br/><br/> <span data-ttu-id="c4500-382">**提示：** 請考慮執行一些測試批次到實驗這個參數讓您可以決定要匯入至 Pst 檔案的最佳資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="c4500-382">**Tip:** Consider running a few test batches to experiment with this parameter so you can determine the best folder location to import PSTs files to.</span></span>           |<span data-ttu-id="c4500-383">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c4500-383">(leave blank)</span></span>  <br/> <span data-ttu-id="c4500-384">或</span><span class="sxs-lookup"><span data-stu-id="c4500-384">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="c4500-385">或</span><span class="sxs-lookup"><span data-stu-id="c4500-385">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="c4500-p154">此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數值。此參數用於從中文、 日文及韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常使用雙位元組字元集 (DBCS) 的字元編碼。如果此參數不用來匯入 PST 檔案的信箱資料夾名稱使用 DBCS 的語言，則他們正在匯入後通常被混亂資料夾名稱。如需使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)支援值的清單。</span><span class="sxs-lookup"><span data-stu-id="c4500-p154">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported. For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  </span></span><br/><br/> <span data-ttu-id="c4500-p155">**附註：** 如先前另有說明，這是選用的參數與您沒有包含 CSV 檔案中。或者您可以將它包含並將此值保留空白的一或多個資料列。</span><span class="sxs-lookup"><span data-stu-id="c4500-p155">**Note:** As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="c4500-392">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c4500-392">(leave blank)</span></span>  <br/> <span data-ttu-id="c4500-393">或</span><span class="sxs-lookup"><span data-stu-id="c4500-393">Or</span></span>  <br/>  <span data-ttu-id="c4500-394">`932`（這是程式碼] 頁面上的識別碼 ANSI/OEM 日文）</span><span class="sxs-lookup"><span data-stu-id="c4500-394">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="c4500-395">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="c4500-395">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c4500-396">不適用</span><span class="sxs-lookup"><span data-stu-id="c4500-396">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="c4500-397">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="c4500-397">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c4500-398">不適用</span><span class="sxs-lookup"><span data-stu-id="c4500-398">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="c4500-399">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="c4500-399">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c4500-400">不適用</span><span class="sxs-lookup"><span data-stu-id="c4500-400">Not applicable</span></span>  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="c4500-401">步驟 8：在 Office 365 中建立 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="c4500-401">Step 8: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="c4500-p156">最後一個步驟是在 Office 365 中的匯入服務中建立 PST 匯入工作。如先前所述，您會將提交您在步驟 7 中建立之 PST 匯入對應檔案。匯入服務建立新的工作之後，將會解除對應檔案中使用的資訊層加密和 （您所上傳到步驟 5 中的 Office 365） PST 檔案匯入指定的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="c4500-p156">The last step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 7. After you create the new job, the Import service will use the information in the mapping file to un-encrypt and import the PST files (that you uploaded to Office 365 in Step 5) to the specified user mailbox.</span></span> 
  
1. <span data-ttu-id="c4500-405">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c4500-405">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c4500-406">登入 Office 365 使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c4500-406">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="c4500-407">在左窗格中，按一下 [**資料控管**和 [**匯入**。</span><span class="sxs-lookup"><span data-stu-id="c4500-407">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="c4500-408">在 [**匯入**] 頁面上，按一下 [**移至 [匯入服務**。</span><span class="sxs-lookup"><span data-stu-id="c4500-408">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="c4500-409">在 [ **Office 365 的匯入資料**] 頁面上按一下 [**新增工作**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**上傳的電子郵件 （PST 檔案）**。</span><span class="sxs-lookup"><span data-stu-id="c4500-409">On the **Import data to Office 365** page, click **New job**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="c4500-410">在 [**上傳檔案透過網路**] 頁面上，按一下 [ **I 完成上傳我檔案\*\*\*\*我有對應檔案的存取權**的核取方塊，，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4500-410">On the **Upload files over the network** page, click the **I'm done uploading my files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span> 
    
7. <span data-ttu-id="c4500-411">輸入 PST 匯入工作、 名稱，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4500-411">Type a name for the PST Import job, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c4500-412">按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)選取您在步驟 7 中建立的對應 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4500-412">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to select the PST Mapping file that you created in Step 7.</span></span> 
    
9. <span data-ttu-id="c4500-413">CSV 檔案的名稱會出現在清單之後，加以選取並再按一下 [**驗證**] 檢查 CSV 檔中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4500-413">After the name of the CSV file appears in the list, select it and then click **Validate** to check your CSV file for errors.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c4500-p157">為舊清楚，加密的 PST 檔案時，`.pfile`副檔名會附加至 PST 檔案名稱。您必須新增`.pfile`延伸模組名稱的 PST 檔案 CSV 檔案中。如果您未驗證的 CSV 檔案將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c4500-p157">As previous explained, when the PST files are encrypted, a  `.pfile` extension is appended to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file. If you don't, the validation of the CSV file will fail.</span></span> 
  
    <span data-ttu-id="c4500-p158">CSV 檔案具有建立 PST 匯入工作成功驗證。如果驗證失敗，請按一下 [**狀態**] 欄中的**無效**的連結。將開啟的 PST 匯入對應檔案的複本失敗的檔案中的每一列的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="c4500-p158">The CSV file has to be successfully validated to create a PST Import job. If the validation fails, click the **Invalid** link in the **Status** column. A copy of your PST Import mapping file is opened, with a error message for each row in the file that failed.</span></span> 
    
10. <span data-ttu-id="c4500-420">當 PST 對應檔案驗證成功時，請檢閱條款和條件文件，然後按一下 [核取方塊]。</span><span class="sxs-lookup"><span data-stu-id="c4500-420">When the PST mapping file is successfully validated, read the terms and conditions document, and then click the checkbox.</span></span>
    
11. <span data-ttu-id="c4500-421">按一下 [**完成**] 以送出工作。</span><span class="sxs-lookup"><span data-stu-id="c4500-421">Click **Finish** to submit the job.</span></span> 
    
    <span data-ttu-id="c4500-422">此工作會顯示在**Office 365 的匯入資料**] 頁面上的 PST 匯入工作清單中。</span><span class="sxs-lookup"><span data-stu-id="c4500-422">The job is displayed in the list of PST Import jobs on the **Import data to Office 365** page.</span></span> 
    
12. <span data-ttu-id="c4500-423">選取此工作，按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中顯示狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="c4500-423">Select the job and click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the status information that's displayed in the details pane.</span></span> 
    
13. <span data-ttu-id="c4500-424">在 [詳細資料] 窗格中，按一下 [**檢視詳細資料]** 以取得最新狀態的選取工作]。</span><span class="sxs-lookup"><span data-stu-id="c4500-424">In the details pane, click **View details** to get the latest status for the selected job.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="c4500-425">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c4500-425">More information</span></span>

- <span data-ttu-id="c4500-426">為什麼要選擇 PST 檔案匯入 Office 365？</span><span class="sxs-lookup"><span data-stu-id="c4500-426">Why import PST files to Office 365?</span></span>
    
  - <span data-ttu-id="c4500-427">它是一個好方法來將組織的電子郵件移轉至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c4500-427">It's a good way to migrate your organization's email to Office 365.</span></span>
    
  - <span data-ttu-id="c4500-428">它可讓您透過下列方式協助解決組織的法務遵循需求︰</span><span class="sxs-lookup"><span data-stu-id="c4500-428">It helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="c4500-429">啟用封存信箱以提供使用者額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c4500-429">Enable archive mailboxes to give users additional mailbox storage space.</span></span>
    
  - <span data-ttu-id="c4500-430">保存信箱以保留內容。</span><span class="sxs-lookup"><span data-stu-id="c4500-430">Place mailboxes on hold to preserve content.</span></span>
    
  - <span data-ttu-id="c4500-431">使用 Microsoft eDiscovery 工具來搜尋信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="c4500-431">Use Microsoft eDiscovery tools to search for content in mailboxes.</span></span>
    
  - <span data-ttu-id="c4500-432">使用保留原則來控制信箱內容要保留多久。</span><span class="sxs-lookup"><span data-stu-id="c4500-432">Use retention policies to control how long mailbox content is retained.</span></span>
    
  - <span data-ttu-id="c4500-433">搜尋 Office 365 信箱相關的事件稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c4500-433">Search the Office 365 audit log for mailbox-related events.</span></span>
    
  - <span data-ttu-id="c4500-p159">它可協助防止資料遺失。Office 365 信箱將會匯入的 PST 檔案繼承 Exchange Online 的高可用性的功能而非儲存在使用者電腦上的資料。</span><span class="sxs-lookup"><span data-stu-id="c4500-p159">It helps protect against data loss. PST files that are imported to Office 365 mailboxes inherit the high availability features of Exchange Online, as opposed to storing the data on a user's computer.</span></span>
    
  - <span data-ttu-id="c4500-436">資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。</span><span class="sxs-lookup"><span data-stu-id="c4500-436">The data is available to the user from all devices because it's stored in the cloud.</span></span>
    
- <span data-ttu-id="c4500-p160">以下是範例金鑰、 識別碼、 及取得步驟 2、 3 及 4 中的 Url。此範例也會包含您執行在 O365ImportTool.exe 工具來加密及上傳 PST 檔案至 Office 365 的命令語法。請務必採取預防措施來保護這些剛剛像您會保護密碼或其他安全性相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c4500-p160">Here's an example of the keys, IDs, and URLs that are obtained in Steps 2, 3, and 4. This example also contains the syntax for the command that you run in the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- <span data-ttu-id="c4500-p161">如先前所述的 Office 365 匯入服務會開啟設定 （無限期的持續時間） 之後 PST 檔案匯入至信箱的保留。這表示*RentionHoldEnabled*屬性設為`True`以便將不會處理指派給信箱的保留原則。這可讓管理新匯入訊息來防止刪除或封存原則中刪除或封存舊郵件的信箱擁有者時間。以下是一些以管理此保留所能採取的步驟：</span><span class="sxs-lookup"><span data-stu-id="c4500-p161">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="c4500-p162">後段特定時間內，您就可以關閉保留功能來執行`Set-Mailbox -RetentionHoldEnabled $false`命令。指示，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/p/?LinkId=544749)。</span><span class="sxs-lookup"><span data-stu-id="c4500-p162">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="c4500-p163">您可以設定保留功能，讓一些日期未來關閉。您執行這項作業執行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假設今天的日期是 2016 年 7 月 1，而且您想關閉在 30 天保留功能，您會執行下列命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此案例中，您會將保留*RentionHoldEnabled*屬性設定為`True`。如需詳細資訊，請參閱[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。</span><span class="sxs-lookup"><span data-stu-id="c4500-p163">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to `True`. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="c4500-p164">您可以變更使較舊的項目匯入的將不會立即刪除或移至使用者的封存信箱指派給信箱的保留原則的設定。例如，您無法延長刪除或封存原則指派給信箱的保留時間。在此案例中，您會關閉信箱保留之後變更此保留原則的設定。如需詳細資訊，請參閱 ＜ [Set up Office 365 組織中信箱的封存及刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c4500-p164">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
