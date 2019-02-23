---
title: 使用網路上傳至您的組織 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 系統管理員： 了解如何使用網路上傳至大量匯入至 Office 365 中的使用者信箱的多個 PST 檔案。
ms.openlocfilehash: a92217ad4126851a042b3492614aaa35ef215f61
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223602"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="e5da6-103">使用網路上傳至您的組織 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5da6-103">Use network upload to import your organization PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="e5da6-p101">本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span><span class="sxs-lookup"><span data-stu-id="e5da6-p101">This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>
  
<span data-ttu-id="e5da6-p102">以下是使用網路上傳至大量匯入至 Office 365 信箱的多個 PST 檔案所需的逐步指示。如需使用網路上傳大量匯入至 Office 365 信箱的 PST 檔案，請參閱[使用匯入 PST 檔案的網路上傳的常見問題集](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)的常見問題集問題。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p102">Here are the step-by-step instructions required to use network upload to bulk-import multiple PST files to Office 365 mailboxes. For frequently asked questions about using network upload to bulk-import PST files to Office 365 mailboxes, see [FAQs for using network upload to import PST files](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).</span></span>
  
[<span data-ttu-id="e5da6-109">步驟 1： 複製 SAS URL 並安裝 Azure AzCopy</span><span class="sxs-lookup"><span data-stu-id="e5da6-109">Step 1: Copy the SAS URL and install Azure AzCopy</span></span>](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[<span data-ttu-id="e5da6-110">步驟 2： 將 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5da6-110">Step 2: Upload your PST files to Office 365</span></span>](#step-2-upload-your-pst-files-to-office-365)

[<span data-ttu-id="e5da6-111">（選用）步驟 3： 檢視清單中的 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5da6-111">(Optional) Step 3: View a list of the PST files uploaded to Office 365</span></span>](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[<span data-ttu-id="e5da6-112">步驟 4： 建立 PST 匯入對應檔案</span><span class="sxs-lookup"><span data-stu-id="e5da6-112">Step 4: Create the PST Import mapping file</span></span>](#step-4-create-the-pst-import-mapping-file)

[<span data-ttu-id="e5da6-113">步驟 5：在 Office 365 中建立 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="e5da6-113">Step 5: Create a PST Import job in Office 365</span></span>](#step-5-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="e5da6-114">步驟 6： 篩選資料並開始 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="e5da6-114">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)

<span data-ttu-id="e5da6-p103">請注意您必須執行一次只能步驟 1 至 PST 檔案匯入 Office 365 信箱。您執行這些步驟之後，請遵循步驟 2 到步驟 6 每一個您想要上傳並匯入 PST 檔案的批次的時間。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p103">Note that you have to perform Step 1 only once to import PST files to Office 365 mailboxes. After you perform these steps, follow Step 2 through Step 6 each time you want to upload and import a batch of PST files.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e5da6-117">開始之前</span><span class="sxs-lookup"><span data-stu-id="e5da6-117">Before you begin</span></span>
  
- <span data-ttu-id="e5da6-p104">您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後再將自己的成員身分或者。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p104">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="e5da6-123">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="e5da6-123">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="e5da6-p105">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p105">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="e5da6-126">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-126">Or</span></span>
    
  - <span data-ttu-id="e5da6-127">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="e5da6-127">You have to be a global administrator in your Office 365 organization.</span></span>
    
  > [!TIP]
    > <span data-ttu-id="e5da6-p106">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p106">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="e5da6-p107">將 PST 檔案匯入 Office 365 唯一支援的方法是使用 Azure AzCopy 工具，如本主題所述。您無法使用 Azure 儲存在檔案總管 PST 檔案上傳直接至 Azure 儲存區。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p107">The only supported method for importing PST files to Office 365 is to use the Azure AzCopy tool, as described in this topic. You can't use the Azure Storage Explorer to upload PST files directly to the Azure storage area.</span></span>
    
- <span data-ttu-id="e5da6-p108">您要儲存您想要匯入 Office 365 上的檔案伺服器或組織中的共用的資料夾的 PST 檔案。在步驟 2 中，您將執行 Azure AzCopy 工具將上傳儲存此檔案伺服器上或共用資料夾至 Office 365 的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p108">You need to store the PST files that you want to import to Office 365 on a file server or shared folder in your organization. In Step 2, you'll run the Azure AzCopy tool that will upload the PST files that are stored on this file server or shared folder to Office 365.</span></span>
    
- <span data-ttu-id="e5da6-p109">此程序包括複製並儲存一份包含便捷鍵的 URL。此資訊的使用中上傳您的 PST 檔案的步驟 2 和步驟 3 中若要檢視的上傳至 Office 365 的 PST 檔案清單。請務必採取預防措施像您會保護密碼或其他安全性相關的資訊保護此 URL。例如您可能會將其儲存至受密碼保護 Microsoft Word 文件或已加密的 USB 磁碟機。請參閱[的詳細資訊](#more-information)] 區段中的此範例會合併的 URL 及索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p109">This procedure involves copying and saving a copy of a URL that contains an access key. This information will be used in Step 2 to upload your PST files, and in Step 3 if you want to view a list of the PST files uploaded to Office 365. Be sure to take precautions to protect this URL like you would protect passwords or other security-related information. For example you might save it to a password-protected Microsoft Word document or to an encrypted USB drive. See the [More information](#more-information) section for an example of this combined URL and key.</span></span> 
    
- <span data-ttu-id="e5da6-p110">您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。您執行此動作以指定在非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。請參閱步驟 4 如本主題中的 [**說明**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p110">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See Step 4 on the **Instructions** tab in this topic for information.</span></span> 
    
- <span data-ttu-id="e5da6-p111">在 Exchange 混合部署中，您可以 PST 檔案匯入雲端式封存信箱的主要信箱位於內部部署的使用者。您這麼做依照 PST 匯入對應檔案中的下列：</span><span class="sxs-lookup"><span data-stu-id="e5da6-p111">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="e5da6-144">指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。</span><span class="sxs-lookup"><span data-stu-id="e5da6-144">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="e5da6-145">指定**TRUE**值`IsArchive`參數。</span><span class="sxs-lookup"><span data-stu-id="e5da6-145">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="e5da6-146">如需詳細資訊，請參閱[步驟 4](#step-4-create-the-pst-import-mapping-file) 。</span><span class="sxs-lookup"><span data-stu-id="e5da6-146">See [Step 4](#step-4-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="e5da6-p112">PST 檔案匯入至 Office 365 信箱之後，為信箱設定保留功能會開啟無限期的持續期間。這表示將不會處理在您關閉保留功能或設定要關閉保留日期之前中指派給信箱的保留原則。為什麼這麼做這？如果舊匯入至信箱的郵件，則它們可能會永久刪除 （清除） 因為其保留期間已過期為基礎之信箱的保留設定。將信箱設定保留功能將會讓信箱擁有者時間來管理這些新匯入訊息或讓您變更信箱的保留設定的時間。請參閱本主題中針對有關管理保留功能的建議的**詳細資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p112">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the **More info** tab in this topic for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="e5da6-p113">根據預設，可以接收的 Office 365 信箱的最大郵件大小為 35 MB。那是因為信箱的*MaxReceiveSize*屬性的預設值設定為 35 MB。不過，限制的最大郵件的接收大小 Office 365 中為 150 MB。如此若您匯入 PST 檔案包含大於 35 MB，我們會自動將目標信箱上*MaxReceiveSize*屬性的值變更為 150 MB 的匯入 Office 365 服務的項目。這可讓郵件最多可 150 MB 要匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p113">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="e5da6-158">若要找出郵件的接收大小的信箱，您可以執行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。</span><span class="sxs-lookup"><span data-stu-id="e5da6-158">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a><span data-ttu-id="e5da6-159">步驟 1： 複製 SAS URL 並安裝 Azure AzCopy</span><span class="sxs-lookup"><span data-stu-id="e5da6-159">Step 1: Copy the SAS URL and install Azure AzCopy</span></span>

<span data-ttu-id="e5da6-p114">第一個步驟是下載並安裝 Azure AzCopy 工具，這是您用來執行步驟 2 中 PST 檔案上傳至 Office 365 的工具。您也將您的組織複製 SAS URL。此 URL 會在 Microsoft 雲端組織和共用存取簽章 (SAS) 金鑰 Azure 儲存位置的網路 URL 的組合。此機碼提供 PST 檔案上傳至 Azure 儲存位置的必要權限。請務必採取預防措施保護 SAS URL。它是唯一的您的組織並將用於在步驟 2。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p114">The first step is to download and install the Azure AzCopy tool, which is the tool that you'll run in Step 2 to upload PST files to Office 365. You'll also copy the SAS URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and a Shared Access Signature (SAS) key. This key provides you with the necessary permissions to upload PST files to your Azure storage location. Be sure to take precautions to protect the SAS URL. It's unique to your organization and will be used in Step 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5da6-166">匯入 PST 檔案使用網路上傳方法，建議您依照下列程序中的步驟 6b 可以下載的 Azure AzCopy 的版本。</span><span class="sxs-lookup"><span data-stu-id="e5da6-166">To import PST files using the network upload method, we recommend that you use the version of Azure AzCopy that can be downloaded in step 6b in the following procedure.</span></span>
  
1. <span data-ttu-id="e5da6-167">移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="e5da6-167">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="e5da6-168">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-168">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5da6-p115">您必須被指派存取安全性 [**匯入**] 頁面上的適當權限&amp;規範中心。請參閱 ＜**開始之前**] 區段中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p115">You have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center. See the **Before you begin** section for more information.</span></span> 
    
3. <span data-ttu-id="e5da6-171">在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-171">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    <span data-ttu-id="e5da6-172">匯入工作精靈] 會顯示。</span><span class="sxs-lookup"><span data-stu-id="e5da6-172">The import job wizard is displayed.</span></span>
    
4. <span data-ttu-id="e5da6-p116">輸入 PST 匯入工作、 名稱，然後按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p116">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="e5da6-176">在**您要上傳或隨附的資料吗？** 頁面、 按一下 [**上傳資料**然後再按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-176">On the **Do you want to upload or ship data?** page, click **Upload your data** and then click **Next**.</span></span>
    
    ![按一下 [上傳您若要建立網路上傳的資料匯入工作](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. <span data-ttu-id="e5da6-178">在 [**匯入資料**] 頁面上執行下列兩件事：</span><span class="sxs-lookup"><span data-stu-id="e5da6-178">On the **Import data** page, do the following two things:</span></span> 
    
    ![複製 SAS URL 並下載 [匯入資料] 頁面上的 [Azure AzCopy 工具](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    <span data-ttu-id="e5da6-p117">a.在步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。顯示 SAS URL 後，按一下 [**複製到剪貼簿**然後將其貼並將其儲存至檔案，讓您可以稍後存取。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p117">a. In step 2, click **Show network upload SAS URL**. After the SAS URL is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="e5da6-p118">b.在步驟 3 中，按一下 [**下載 Azure AzCopy**下載並安裝 Azure AzCopy 工具。在快顯視窗中，按一下 [**執行**] 表示安裝 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p118">b. In step 3, click **Download Azure AzCopy** to download and install the Azure AzCopy tool. In the pop-up window, click **Run** to install AzCopy.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e5da6-186">您可以 [**匯入資料**] 頁面上保持在開啟狀態 （以防您需要再次複製 SAS URL） 或按一下 [**取消**] 以關閉它。</span><span class="sxs-lookup"><span data-stu-id="e5da6-186">You can leave the **Import data** page open (in case you need to copy the SAS URL again) or click **Cancel** to close it.</span></span> 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a><span data-ttu-id="e5da6-187">步驟 2： 將 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5da6-187">Step 2: Upload your PST files to Office 365</span></span>

<span data-ttu-id="e5da6-p119">現在您已經準備好要用以 AzCopy.exe 工具 PST 檔案上傳至 Office 365。這項工具上傳並將其儲存在 Microsoft 雲端 Azure 的儲存位置。如先前所述 Azure 儲存位置的上傳至 PST 檔案位於同一個地區 Office 365 組織所在的 Microsoft 資料中心。若要完成此步驟，PST 檔案必須位於檔案共用或組織中的檔案伺服器。這就是所謂的下列程序中的來源目錄。每次執行 AzCopy 工具，您可以指定不同的來源目錄。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p119">Now you're ready to use the AzCopy.exe tool to upload PST files to Office 365. This tool uploads and stores them in an Azure storage location in the Microsoft cloud. As previously explained, the Azure storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure. Each time you run the AzCopy tool, you can specify a different source directory.</span></span> 
  
1. <span data-ttu-id="e5da6-194">在您的本機電腦上開啟 [命令提示字元]。</span><span class="sxs-lookup"><span data-stu-id="e5da6-194">Open a Command Prompt on your local computer.</span></span>
    
2. <span data-ttu-id="e5da6-p120">移至目錄您在步驟 1 安裝 AzCopy.exe 工具。如果您安裝此工具預設位置中，移至`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p120">Go to the directory where you installed the AzCopy.exe tool in Step 1. If you installed the tool in the default location, go to `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.</span></span>
    
3. <span data-ttu-id="e5da6-197">執行下列命令以將 PST 檔案上傳至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e5da6-197">Run the following command to upload the PST files to Office 365.</span></span>

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    <span data-ttu-id="e5da6-p121">下表說明參數和其所需的值。請注意您在上一個步驟是取得此資訊可用值為這些參數。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p121">The following table describes the parameters and their required values. Note that the information you obtained in the previous step is used in the values for these parameters.</span></span>
    
    |<span data-ttu-id="e5da6-200">**參數**</span><span class="sxs-lookup"><span data-stu-id="e5da6-200">**Parameter**</span></span>|<span data-ttu-id="e5da6-201">**描述**</span><span class="sxs-lookup"><span data-stu-id="e5da6-201">**Description**</span></span>|<span data-ttu-id="e5da6-202">**範例**</span><span class="sxs-lookup"><span data-stu-id="e5da6-202">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |<span data-ttu-id="e5da6-203">指定包含要上傳至 Office 365 的 PST 檔案在組織中的來源目錄。</span><span class="sxs-lookup"><span data-stu-id="e5da6-203">Specifies the source directory in your organization that contains the PST files that will be uploaded to Office 365.</span></span>  <br/> <span data-ttu-id="e5da6-204">請務必使用雙引號 (" ") 括住此參數的值。</span><span class="sxs-lookup"><span data-stu-id="e5da6-204">Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |<span data-ttu-id="e5da6-205">在步驟 1 中指定您取得 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="e5da6-205">Specifies the SAS URL that you obtained in Step 1.</span></span>  <br/> <span data-ttu-id="e5da6-206">請務必使用雙引號 (" ") 括住此參數的值。</span><span class="sxs-lookup"><span data-stu-id="e5da6-206">Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> <span data-ttu-id="e5da6-p122">**提示：**（選用）您可以在 Azure 的儲存位置上傳至 PST 檔案中指定的子資料夾。您執行方法是新增 SAS URL 中的子資料夾位置 （之後"ingestiondata")。第一個範例不會指定子資料夾;這表示 Pst 將可上傳到根目錄 （名為*ingestiondata* ） 的 Azure 儲存位置。第二個範例 Azure 儲存位置的根目錄中的上傳至 （名為*PSTFiles* ） 的子資料夾的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p122">**Tip:** (Optional) You can specify a subfolder in the Azure storage location to upload the PST files to. You do this by adding a subfolder location (after "ingestiondata") in the SAS URL. The first example doesn't specify a subfolder; that means the PSTs will be uploaded to the root (named  *ingestiondata*  ) of the Azure storage location. The second example uploads the PST files to a subfolder (named  *PSTFiles*  ) in the root of the Azure storage location.  </span></span><br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> <span data-ttu-id="e5da6-211">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-211">Or</span></span>  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |<span data-ttu-id="e5da6-p123">將詳細狀態訊息輸出到記錄檔。根據預設，在 %LocalAppData%\Microsoft\Azure\AzCopy 中，詳細資訊記錄檔的名稱為 AzCopyVerbose.log。如果您在此選項中指定現有檔案位置，詳細資訊記錄檔會附加至該檔案。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p123">Outputs verbose status messages into a log file. By default, the verbose log file is named AzCopyVerbose.log in %LocalAppData%\Microsoft\Azure\AzCopy. If you specify an existing file location for this option, the verbose log will be appended to that file.</span></span>  <br/> <span data-ttu-id="e5da6-215">請務必使用雙引號 (" ") 括住此參數的值。</span><span class="sxs-lookup"><span data-stu-id="e5da6-215">Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |<span data-ttu-id="e5da6-216">使 AzCopy 工具會將位於所指定的來源目錄中的子資料夾中的 Pst 檔案複製此選用參數會指定遞迴模式`/Source:`參數。</span><span class="sxs-lookup"><span data-stu-id="e5da6-216">This optional switch specifies the recursive mode so that the AzCopy tool will copy PSTs files that are located in subfolders in the source directory that is specified by the  `/Source:` parameter.</span></span>  <br/> <span data-ttu-id="e5da6-p124">**附註：** 如果加上此參數，在子資料夾中的 PST 檔案不同的檔案路徑名稱中有 Azure 的儲存位置之後他們正在上傳。您必須在您在步驟 4 中建立 CSV 檔案中指定的實際檔案路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p124">**Note:** If you include this switch, PST files in subfolders will have a different file pathname in the Azure storage location after they're uploaded. You'll have to specify the exact file pathname in the CSV file that you create in Step 4.  </span></span><br/> | `/S` <br/> |
    | `/Y` <br/> |<span data-ttu-id="e5da6-p125">此必要的參數可讓唯寫 SAS 權杖使用當您將 PST 檔案上傳至 Azure 儲存位置。您在步驟 1 中取得 SAS URL (並指定在`/Dest:`參數) 是唯寫 SAS URL，這是您必須包含此參數的原因。請注意唯寫 SAS URL 將無法防止您使用 Azure 儲存在檔案總管檢視 PST 檔案上傳至 Azure 儲存位置的清單。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p125">This required switch allows the use of write-only SAS tokens when you upload the PST files to the Azure storage location. The SAS URL you obtained in step 1 (and specified in  `/Dest:` parameter) is a write-only SAS URL, which is why you must include this switch. Note that a write-only SAS URL will not prevent you from using the Azure Storage Explorer to view a list of the PST files uploaded to the Azure storage location.  </span></span><br/> | `/Y` <br/> |
   
<span data-ttu-id="e5da6-222">這是 AzCopy.exe 工具針對各個參數使用實際值的語法範例︰</span><span class="sxs-lookup"><span data-stu-id="e5da6-222">Here's an example of the syntax for the AzCopy.exe tool using actual values for each parameter:</span></span>
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

<span data-ttu-id="e5da6-p126">在您執行命令後，便會顯示 PST 檔案上傳進度的狀態訊息。最終狀態訊息會顯示已成功上傳的檔案總數。 </span><span class="sxs-lookup"><span data-stu-id="e5da6-p126">After you run the command, status messages are displayed that show the progress of uploading the PST files. A final status message shows the total number of files that were successfully uploaded.</span></span>

> [!TIP]
> <span data-ttu-id="e5da6-p127">您已順利執行 AzCopy.exe 命令並確認所有參數正確都無誤後，命令列語法到您複製資訊相同 （安全） 檔案的複本儲存您取得在步驟 1 中。然後您可以命令複製並貼入此命令提示字元中每一個您想要執行 AzCopy.exe 工具至 PST 檔案上傳至 Office 365 的時間。您可能必須變更的唯一值是針對該組`/Source:`參數。這取決於 PST 檔案的所在位置的來源目錄。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p127">After you successfully run the AzCopy.exe command and verify that all the parameters are correct, save a copy of the command line syntax to the same (secured) file where you copied the information you obtained in Step 1. Then you can copy and paste this command in a Command Prompt each time that you want to run the AzCopy.exe tool to upload PST files to Office 365. The only value you might have to change are the ones for the  `/Source:` parameter. This depends on the source directory where the PST files are located.</span></span>

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="e5da6-229">（選用）步驟 3： 檢視清單中的 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5da6-229">(Optional) Step 3: View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="e5da6-p128">為選用的步驟，您可以安裝及使用 Microsoft Azure 儲存在檔案總管 （這是免費，開放原始碼工具） 來檢視您已上傳至 Azure blob PST 檔案的清單。為達成此目的兩種很好的原因有：</span><span class="sxs-lookup"><span data-stu-id="e5da6-p128">As an optional step, you can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that you've uploaded to the Azure blob. There are two good reasons to do this:</span></span>
  
- <span data-ttu-id="e5da6-232">確認 PST 檔案從共用的資料夾或檔案伺服器在組織中的已成功上傳至 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="e5da6-232">Verify that PST files from the shared folder or file server in your organization were successfully uploaded to the Azure blob.</span></span>
    
- <span data-ttu-id="e5da6-p129">確認每個 PST 檔案上傳至 Azure blob 的檔案名稱 （和子資料夾 pathname 如果包含一個）。當您建立對應檔案中的下一個步驟因為您有指定的資料夾路徑名稱和每個 PST 檔案的檔案名稱 PST，這是很有幫助。確認這些名稱可以協助降低您 PST 對應檔案中的潛在錯誤。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p129">Verify the filename (and the subfolder pathname if you included one) for each PST file uploaded to the Azure blob. This is really helpful when you're creating the PST mapping file in the next step because you have to specify both the folder pathname and filename for each PST file. Verifying these names can help reduce potential errors in your PST mapping file.</span></span>
    
<span data-ttu-id="e5da6-236">Microsoft Azure 儲存在檔案總管處於預覽。</span><span class="sxs-lookup"><span data-stu-id="e5da6-236">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5da6-p130">您無法使用 Azure 儲存在檔案總管上傳或修改 PST 檔案。將 PST 檔案匯入 Office 365 唯一支援的方法是使用 AzCopy。此外，您無法刪除您已上傳至 Azure blob 的 PST 檔案。如果您嘗試刪除 PST 檔案，將會收到有關不會察覺必要的權限的錯誤。請注意 Azure 儲存區域會自動刪除所有 PST 檔案。如果有任何匯入工作進行，然後所有 PST 檔案中的 [ **ingestiondata** ] 容器中會不刪除 30 天後所建立的最新的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p130">You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.</span></span>
  
<span data-ttu-id="e5da6-243">若要安裝 Azure 儲存在檔案總管並連線至 Azure 儲存區：</span><span class="sxs-lookup"><span data-stu-id="e5da6-243">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="e5da6-244">下載並安裝[Microsoft Azure 儲存檔案總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-244">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
2. <span data-ttu-id="e5da6-245">啟動 Microsoft Azure 儲存在檔案總管、 以滑鼠右鍵按一下左窗格中的**存放區的帳戶**和 [**連線至 Azure 存放區**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-245">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![以滑鼠右鍵按一下 [儲存的帳戶，然後按一下 [連線至 Azure 存放區](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. <span data-ttu-id="e5da6-247">按一下 [**使用存取共用簽章 (SAS) URI 或連線字串**再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-247">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
4. <span data-ttu-id="e5da6-248">按一下 [**使用 SAS URI**、 在步驟 1 中所取得 SAS URL 貼入底下**URI**] 方塊並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-248">Click **Use a SAS URI**, paste the SAS URL that you obtained in Step 1 into the box under **URI**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="e5da6-249">在 [**連線摘要**] 頁面上您可以檢閱連線資訊，並再按一下 [**連線**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-249">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="e5da6-p131">開啟**ingestiondata**容器;包含您在步驟 2 中上傳的 PST 檔案。[**存放區的帳戶**位於**ingestiondata**容器\> **(SAS-Attached Services)** \> **Blob 容器**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p131">The **ingestiondata** container is opened; it contains the PST files that you uploaded in Step 2. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span> 
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. <span data-ttu-id="e5da6-p132">使用 Microsoft Azure 儲存在檔案總管完成作業後，用滑鼠右鍵按一下**ingestiondata**，並再按一下 [**卸離**中斷與 Azure 儲存區的連線。否則，您會收到錯誤的下次您嘗試附加。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p132">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a><span data-ttu-id="e5da6-256">步驟 4： 建立 PST 匯入對應檔案</span><span class="sxs-lookup"><span data-stu-id="e5da6-256">Step 4: Create the PST Import mapping file</span></span>

<span data-ttu-id="e5da6-p133">Azure 儲存位置的 Office 365 組織已上載的 PST 檔案之後下, 一步是建立逗點分隔值 (CSV) 檔案，指定 PST 檔案會以匯入的使用者信箱。當您建立 PST 匯入工作，將送出這個的 CSV 檔案中的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p133">After the PST files have been uploaded to the Azure storage location for your Office 365 organization, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to. You'll submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="e5da6-259">[下載 PST 匯入對應檔案的複本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-259">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="e5da6-p134">開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p134">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    <span data-ttu-id="e5da6-p135">第一列或欄位名稱] 列的 CSV 檔案列出要使用 PST 匯入服務至 PST 檔案匯入使用者信箱的參數。每個參數名稱是以逗號分隔。標頭列] 下方的每一個資料列代表將 PST 檔案匯入特定信箱的參數值。您將需要一列的每一個您想要匯入使用者信箱的 PST 檔案。請務必對應檔案中的版面配置區資料取代實際資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p135">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that you want to import to a user mailbox. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

   <span data-ttu-id="e5da6-268">**附註：** 並不會變更標題列，包括 SharePoint 參數 ； 中的任何項目這些都會被忽略 PST 匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="e5da6-268">**Note:** Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 

 3. <span data-ttu-id="e5da6-269">使用下列表格的資訊，將所需的資訊填入 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="e5da6-269">Use the information in the following table to populate the CSV file with the required information.</span></span>


    |<span data-ttu-id="e5da6-270">**參數**</span><span class="sxs-lookup"><span data-stu-id="e5da6-270">**Parameter**</span></span>|<span data-ttu-id="e5da6-271">**描述**</span><span class="sxs-lookup"><span data-stu-id="e5da6-271">**Description**</span></span>|<span data-ttu-id="e5da6-272">**範例**</span><span class="sxs-lookup"><span data-stu-id="e5da6-272">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="e5da6-p136">指定要匯入資料至 Office 365 服務。若要匯入 PST 檔案至使用者信箱，請使用`Exchange`。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p136">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> |<span data-ttu-id="e5da6-275">在 Azure 的儲存位置上傳至 PST 檔案步驟 2 中的指定的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="e5da6-275">Specifies the folder location in the Azure storage location that you uploaded the PST files to in Step 2.</span></span>  <br/> <span data-ttu-id="e5da6-p137">如果您沒有加入選用的子資料夾名稱中 SAS URL 中`/Dest:`參數在步驟 2 中，將此參數保留空白 CSV 檔案中。如果您加入子資料夾名稱，會將它指定這個參數中 （請參閱第二個範例）。此參數的值是區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p137">If you didn't include an optional subfolder name in the SAS URL in the  `/Dest:` parameter in Step 2, leave this parameter blank in the CSV file. If you included a subfolder name, specify it in this parameter (see the second example). The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="e5da6-279">無論如何，*不*包含"ingestiondata"中的值`FilePath`參數。</span><span class="sxs-lookup"><span data-stu-id="e5da6-279">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter.</span></span>  <br/><br/> <span data-ttu-id="e5da6-p138">**重要：** 大小寫的檔案路徑名稱必須是所用如果 SAS URL 中包含的選用子資料夾名稱的大小寫相同`/Dest:`步驟 2 中的參數。例如，如果您是使用`PSTFiles`的子資料夾名稱步驟 2 中，然後使用`pstfiles`中`FilePath`CSV 檔中的參數，將會失敗 PST 檔案匯入。請務必在兩個執行個體中使用相同的大小寫。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p138">**Important:** The case for the file path name must be the same as the case you used if you included an optional subfolder name in the SAS URL in the  `/Dest:` parameter in Step 2. For example, if you used  `PSTFiles` for the subfolder name in Step 2 and then use  `pstfiles` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.  </span></span><br/> |<span data-ttu-id="e5da6-283">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="e5da6-283">(leave blank)</span></span>  <br/> <span data-ttu-id="e5da6-284">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-284">Or</span></span>  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |<span data-ttu-id="e5da6-p139">指定要匯入至使用者信箱的 PST 檔案的名稱。此參數的值是區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p139">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <br/><span data-ttu-id="e5da6-p140">**重要：** CSV 檔案中的 PST 檔案名稱的大小寫必須已上傳至步驟 2 中的 Azure 儲存位置的 PST 檔案相同。例如，如果您使用`annb.pst`中`Name`參數中的 CSV 檔案，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入就會失敗。請務必 PST CSV 檔案中的名稱會使用為實際的 PST 檔案的大小寫相同。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p140">**Important:** The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.  </span></span><br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="e5da6-p141">會指定 PST 檔案將會匯入至信箱的電子郵件地址。請注意您無法指定公用資料夾因為 PST 匯入服務不支援將 PST 檔案匯入的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p141">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="e5da6-p142">匯入 PST 檔案至不在作用中的信箱，您必須指定此參數的信箱 GUID。若要取得這個 GUID，請執行下列 PowerShell 命令 in Exchange Online：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="e5da6-p142">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span></span> <br/> <br/><span data-ttu-id="e5da6-p143">**附註：** 在某些情況下，您可能會有多個信箱使用同一個電子郵件地址，其中一個信箱不在作用中信箱和其他信箱位於虛刪除 （或非使用中） 的狀態。在下列情況下，您必須指定信箱的信箱來唯一地識別要匯入至 PST 檔案的信箱 GUID。若要取得這個作用中信箱的 GUID，請執行下列 PowerShell 命令： `Get-Mailbox <identity of active mailbox> | FL Guid`。若要取得虛刪除 （或非使用中） 的信箱的 GUID，請執行此命令`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p143">**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  </span></span><br/> | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="e5da6-298">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-298">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="e5da6-p144">指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="e5da6-p144">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/><br/><span data-ttu-id="e5da6-301">**FALSE** -將 PST 檔案匯入使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-301">**FALSE** - Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="e5da6-p145">**True 是表示**-將 PST 檔案匯入使用者的封存信箱。本範例假設[已啟用使用者的封存信箱](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p145">**TRUE** - Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). </span></span><br/><br/><span data-ttu-id="e5da6-p146">如果您將這個參數設定為`TRUE`和未啟用使用者的封存信箱、 匯入的使用者將會失敗。請注意，如果匯入失敗的一位使用者 (因為其封存未啟用且此屬性設為`TRUE`)，將不會影響其他使用者匯入工作。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p146">If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="e5da6-306">如果您將此參數保留空白，PST 檔案匯入使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-306">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <br/><span data-ttu-id="e5da6-307">**附註：** 匯入 PST 檔案到雲端式封存信箱的主要信箱位於內部部署的使用者，剛指定`TRUE`為此參數指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。</span><span class="sxs-lookup"><span data-stu-id="e5da6-307">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="e5da6-308">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-308">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="e5da6-309">指定要匯入 PST 檔案的信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="e5da6-309">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="e5da6-310">如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於信箱 （相同層級 [收件匣] 資料夾和其他預設信箱資料夾） 的根層級的新資料夾。</span><span class="sxs-lookup"><span data-stu-id="e5da6-310">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="e5da6-311">如果您指定`/`、 PST 檔案中的項目會被匯入直接在使用者的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e5da6-311">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/><br/>  <span data-ttu-id="e5da6-p147">如果您指定`/<foldername>`、 PST 檔案中的項目將會匯入至名為資料夾\*\<foldername\> \* 。例如，如果您使用`/ImportedPst`、 項目會匯入至名為**ImportedPst**的資料夾。這個資料夾會位於 [收件匣] 資料夾相同層級的使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p147">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/><br/> <span data-ttu-id="e5da6-315">**提示：** 請考慮執行一些測試批次到實驗這個參數讓您可以決定要匯入至 Pst 檔案的最佳資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="e5da6-315">**Tip:** Consider running a few test batches to experiment with this parameter so you can determine the best folder location to import PSTs files to.</span></span>  <br/> |<span data-ttu-id="e5da6-316">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="e5da6-316">(leave blank)</span></span>  <br/> <span data-ttu-id="e5da6-317">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-317">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="e5da6-318">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-318">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="e5da6-p148">此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數值。此參數用於從中文、 日文及韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常使用雙位元組字元集 (DBCS) 的字元編碼。如果此參數不用來匯入 PST 檔案的信箱資料夾名稱使用 DBCS 的語言，則他們正在匯入後通常被混亂資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p148">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/><br/> <span data-ttu-id="e5da6-322">如需使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)支援值的清單。</span><span class="sxs-lookup"><span data-stu-id="e5da6-322">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <br/><span data-ttu-id="e5da6-p149">**附註：** 如先前另有說明，這是選用的參數與您沒有包含 CSV 檔案中。或者您可以將它包含並將此值保留空白的一或多個資料列。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p149">**Note:** As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.  </span></span><br/> |<span data-ttu-id="e5da6-325">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="e5da6-325">(leave blank)</span></span>  <br/> <span data-ttu-id="e5da6-326">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-326">Or</span></span>  <br/>  <span data-ttu-id="e5da6-327">`932`（這是程式碼] 頁面上的識別碼 ANSI/OEM 日文）</span><span class="sxs-lookup"><span data-stu-id="e5da6-327">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="e5da6-328">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="e5da6-328">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="e5da6-329">不適用</span><span class="sxs-lookup"><span data-stu-id="e5da6-329">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="e5da6-330">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="e5da6-330">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="e5da6-331">不適用</span><span class="sxs-lookup"><span data-stu-id="e5da6-331">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="e5da6-332">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="e5da6-332">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="e5da6-333">不適用</span><span class="sxs-lookup"><span data-stu-id="e5da6-333">Not applicable</span></span>  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="e5da6-334">步驟 5：在 Office 365 中建立 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="e5da6-334">Step 5: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="e5da6-p150">下一步是建立 Office 365 中的匯入服務中的 PST 匯入工作。如先前所述，您會將提交您在步驟 4 中建立之 PST 匯入對應檔案。建立新的工作之後，Office 365 分析 PST 檔案中的資料，然後您機會來篩選實際取得匯入至信箱 PST 匯入對應檔案中指定的資料 （請參閱[步驟 6](#step-6-filter-data-and-start-the-pst-import-job)）。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p150">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 4. After you create the new job, Office 365 analyzes the data in the PST files and then gives you an opportunity to filter the data that actually gets imported to the mailboxes specified in the PST import mapping file (see [Step 6](#step-6-filter-data-and-start-the-pst-import-job)).</span></span>
  
1. <span data-ttu-id="e5da6-338">移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="e5da6-338">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="e5da6-339">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管**] 和 [**匯入**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-339">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="e5da6-340">在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-340">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    <span data-ttu-id="e5da6-p151">**附註：** 您必須被指派適當的權限來存取 [**匯入**] 頁面上的 [安全性]&amp;規範中心以建立新的匯入工作。請參閱 ＜**開始之前**] 區段中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p151">**Note:** You have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center to create a new import job. See the **Before you begin** section for more information.</span></span> 
    
4. <span data-ttu-id="e5da6-p152">輸入 PST 匯入工作、 名稱，然後按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p152">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="e5da6-346">在**您要上傳或隨附的資料吗？** 頁面、 按一下 [**上傳資料**然後再按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-346">On the **Do you want to upload or ship data?** page, click **Upload your data** and then click **Next**.</span></span>
    
    ![按一下 [上傳您若要建立網路上傳的資料匯入工作](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. <span data-ttu-id="e5da6-348">在步驟 4 中**匯入資料**] 頁面上，按一下 [ **I 完成上傳我檔案\*\*\*\*我有對應檔案的存取權**的核取方塊，，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-348">In step 4 on the **Import data** page, click the **I'm done uploading my files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![按一下 [步驟 4 中兩個核取方塊](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. <span data-ttu-id="e5da6-350">在 [**選取對應檔案**] 頁面上按一下 [**選取對應檔案**送出您在步驟 4 中建立之 PST 匯入對應檔案。</span><span class="sxs-lookup"><span data-stu-id="e5da6-350">On the **Select the mapping file** page, click **Select mapping file** to submit the PST Import mapping file that you created in Step 4.</span></span> 
    
    ![按一下 [選取對應檔案送出 CSV 檔案所建立之匯入工作](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. <span data-ttu-id="e5da6-352">CSV 名稱之後檔案會出現 [**對應檔案名稱**、 按一下 [**驗證**] 檢查 CSV 檔中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="e5da6-352">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![按一下 [驗證] 檢查錯誤的 CSV 檔案](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="e5da6-p153">CSV 檔案具有建立 PST 匯入工作成功驗證。請注意會成功驗證之後的檔案名稱變更為綠色。如果驗證失敗，請按一下 [**檢視記錄檔]** 連結。將開啟驗證錯誤報告失敗的檔案中的每一列的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p153">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
9. <span data-ttu-id="e5da6-358">PST 對應檔案已成功驗證之後，閱讀條款和條件文件，並再按一下 [核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e5da6-358">After the PST mapping file is successfully validated, read the terms and conditions document, and then click the checkbox.</span></span>
    
10. <span data-ttu-id="e5da6-359">按一下 [**儲存**] 以送出工作及 [**關閉**之後已成功建立的工作。</span><span class="sxs-lookup"><span data-stu-id="e5da6-359">Click **Save** to submit the job, and then click **Close** after the job is successfully created.</span></span> 
    
    <span data-ttu-id="e5da6-360">顯示狀態彈出式] 頁面上，**進行中的分析**的狀態及新的匯入工作會顯示在 [**匯入**] 頁面上的清單中。</span><span class="sxs-lookup"><span data-stu-id="e5da6-360">A status flyout page is displayed, with a status of **Analysis in progress** and the new import job is displayed in the list on the **Import** page.</span></span> 
    
11. <span data-ttu-id="e5da6-p154">按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [**狀態**] 欄中的狀態資訊。分析完成且資料已準備好要匯入、 狀態會變更為**分析已完成**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p154">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the status information that's displayed in the **Status** column. When the analysis is complete and the data is ready to be imported, the status is changed to **Analysis completed**.</span></span>
    
    <span data-ttu-id="e5da6-363">您可以按一下 [匯入工作，以顯示狀態彈出式] 頁面，其中包含的每個對應檔案中所列的 PST 檔案匯入工作等狀態的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="e5da6-363">You can click the import job to display the status flyout page, which contains more detailed information about the import job such as the status of each PST file listed in the mapping file.</span></span>
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="e5da6-364">步驟 6： 篩選資料並開始 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="e5da6-364">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="e5da6-p155">您在步驟 5 中建立匯入工作之後，Office 365 以方式分析 PST 檔案中的資料 （安全且安全的方式） 所識別的項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成分析，且資料已準備好要匯入，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p155">After you create the import job in Step 5, Office 365 analyzes the data in the PST files (in a safe and secure manner) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="e5da6-367">在 [安全性] 的 [**匯入**] 頁面上&amp;規範中心，按一下 [**準備好要匯入 Office 365**在步驟 5 中所建立的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="e5da6-367">On the **Import** page in the Security &amp; Compliance Center, click **Ready to import to Office 365** for the import job that you created in Step 5.</span></span> 
    
    ![按一下 [匯入至 Office 365 所建立的匯入工作旁的準備](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="e5da6-369">飛入] 頁面會顯示與 PST 檔案的相關資訊及匯入工作的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="e5da6-369">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
2. <span data-ttu-id="e5da6-370">在 [彈出式] 頁面上按一下 [**匯入至 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-370">On the flyout page, click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="e5da6-p156">會顯示 [**篩選資料**] 頁面。包含資料前瞻產生分析的 PST 檔案上執行的 Office 365，包括資料的保留天數的相關資訊。此時，您必須以篩選要匯入或匯入所有的資料時的資料選項。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p156">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![您可以修剪 PST 檔案中的資料或將其所有匯入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. <span data-ttu-id="e5da6-375">執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e5da6-375">Do one of the following:</span></span>
    
    <span data-ttu-id="e5da6-p157">a.以修剪您匯入的資料，按一下 [**是，我要匯入之前加以篩選**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p157">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="e5da6-378">如需篩選 PST 檔案中的資料，並再啟動匯入工作的詳細逐步指示，請參閱[篩選資料匯入至 Office 365 的 PST 檔案時](filter-data-when-importing-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-378">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="e5da6-379">或</span><span class="sxs-lookup"><span data-stu-id="e5da6-379">Or</span></span>
    
    <span data-ttu-id="e5da6-p158">b.匯入 PST 檔案中的所有資料，請按一下 [**否，我要匯都入每個項目，** 然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p158">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
4. <span data-ttu-id="e5da6-382">如果您選擇要匯入的所有資料，請按一下 [啟動匯都入工作都**匯都入資料**]。</span><span class="sxs-lookup"><span data-stu-id="e5da6-382">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="e5da6-p159">匯入工作的狀態會顯示在 [**匯入**] 頁面。按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [**狀態**] 欄中的狀態資訊的 [**重新整理**。按一下匯入工作顯示狀態彈出式] 頁面上，以顯示每個要匯入的 PST 檔案的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p159">The status of the import job is display on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported.</span></span> 

## <a name="how-the-import-process-works"></a><span data-ttu-id="e5da6-386">匯入程序的運作方式</span><span class="sxs-lookup"><span data-stu-id="e5da6-386">How the import process works</span></span>
  
<span data-ttu-id="e5da6-p160">您可以使用網路上傳選項及匯入 Office 365 服務以大量匯入至使用者信箱的 PST 檔案。網路上傳表示您上載 PST 檔案中 Microsoft cloud 暫時存放區。則 Office 365 匯入服務會複製 PST 檔案存放區從目標使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p160">You can use the network upload option and the Office 365 Import service to bulk-import PST files to user mailboxes. Network upload means that you upload the PST files a temporary storage area in the Microsoft cloud. Then the Office 365 Import service copies the PST files from the storage area to the target user mailboxes.</span></span>
  
<span data-ttu-id="e5da6-390">以下是圖與 PST 檔案匯入 Office 365 中的信箱的網路上傳程序的描述。</span><span class="sxs-lookup"><span data-stu-id="e5da6-390">Here's an illustration and description of the network upload process to import PST files to mailboxes in Office 365.</span></span>
  
![工作流程的網路上傳至 PST 檔案匯入 Office 365 的程序](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. <span data-ttu-id="e5da6-p161">**下載 PST 匯入工具和關鍵私人 Azure 儲存位置**-第一個步驟是下載 Azure AzCopy 命令列工具及便捷鍵用來將 PST 檔案上傳至 Microsoft 雲端 Azure 的儲存位置。您可以取得這些 Office 365 安全性 [**匯入**] 頁面中&amp;規範中心。索引鍵 （稱為安全存取簽章 (SAS) 金鑰、 可提供必要的權限至 PST 檔案上傳至私人及保護 Azure 儲存位置。此存取索引鍵是唯一的您的組織和協助防止 PST 檔案的未經授權的存取他們正在上傳至 Microsoft cloud 之後。請注意將 PST 檔案匯入 Office 365 不需要有不同的 Azure 訂閱貴組織。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p161">**Download the PST import tool and key to private Azure storage location** - The first step is to download the Azure AzCopy command-line tool and an access key used to upload the PST files to an Azure storage location in the Microsoft cloud . You obtain these from the **Import** page in the Office 365 Security &amp; Compliance Center. The key (called a secure access signature (SAS) key, provides you with the necessary permissions to upload PST files to a private and secure Azure storage location. This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud. Note that importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="e5da6-p162">使用 AzCopy.exe 工具 （在步驟 1 中下載） 上傳並儲存在位於相同的區域 Microsoft 資料中心 Azure 儲存位置的 PST 檔案**上傳至 Azure 儲存位置的 PST 檔案**-下一步是其中您的 Office 365組織所在。若要將其上傳，您想要匯入 Office 365 的 PST 檔案必須位於檔案共用或組織中的檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p162">**Upload the PST files to the Azure storage location** - The next step is to use the AzCopy.exe tool (downloaded in step 1) to upload and store your PST files in an Azure storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located. To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    <span data-ttu-id="e5da6-399">請注意您可以檢視他們正在上傳至 Azure 儲存位置之後的 PST 檔案的清單執行選用步驟。</span><span class="sxs-lookup"><span data-stu-id="e5da6-399">Note that there's an optional step that you can perform to view the list of PST files after they're uploaded to the Azure storage location.</span></span>
    
3. <span data-ttu-id="e5da6-p163">**建立 PST 匯入對應檔案**-以 Azure 儲存位置已上載的 PST 檔案之後下, 一步是建立指定哪些使用者信箱的 PST 檔案將是以，請注意可以是 PST 檔案匯入的以逗號分隔的值 (CSV) 檔案 匯入使用者的主要信箱或封存信箱。匯入 Office 365 服務會使用 CSV 檔案中的資訊來匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p163">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure storage location, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to, note that a PST file can be imported to a user's primary mailbox or their archive mailbox. The Office 365 Import service will use the information in the CSV file to import the PST files.</span></span>
    
4. <span data-ttu-id="e5da6-p164">**建立 PST 匯入工作**-下一個步驟是在 [安全性] 的 [**匯入**] 頁面上建立 PST 匯入工作&amp;規範中心並送出在上一個步驟中建立之 PST 匯入對應檔案。建立匯入工作之後，Office 365 分析 PST 檔案中的資料並再讓您在設定控制哪些資料實際取得匯入至信箱 PST 匯入對應檔案中指定的篩選器。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p164">**Create a PST import job** - The next step is to create a PST import job on the **Import** page in the Security &amp; Compliance Center and submit the PST import mapping file created in the previous step. After you create the import job, Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
5. <span data-ttu-id="e5da6-p165">**篩選所要匯入至信箱的 PST 資料**-建立並啟動匯入工作之後，Office 365 分析 PST 檔案中的資料 （安全地和安全地） 所識別的項目及 PST 檔案中包含的不同郵件類型的保留時間下限.完成分析，且資料已準備好要匯入，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p165">**Filter the PST data that will be imported to mailboxes** - After the import job is created and started, Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
    
6. <span data-ttu-id="e5da6-p166">**啟動 PST 匯入工作**-開始匯入工作之後，Office 365 資訊檔案中使用 PST 匯入對應從他 Azure 儲存位置的 Pst 檔案匯入至使用者信箱。在 [安全性] 的 [**匯入**] 頁面上會顯示狀態資訊 （包括要匯入每個 PST 檔案的相關資訊） 匯入工作&amp;規範中心。匯入工作完成時，設置**完成**之工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p166">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure storage location to user mailboxes. Status information about the import job (including information about each PST file being imported) is displayed on the **Import** page in the Security &amp; Compliance Center. When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="e5da6-409">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e5da6-409">More information</span></span>

- <span data-ttu-id="e5da6-410">為什麼要選擇 PST 檔案匯入 Office 365？</span><span class="sxs-lookup"><span data-stu-id="e5da6-410">Why import PST files to Office 365?</span></span>
    
  - <span data-ttu-id="e5da6-411">是您的組織封存訊息資料匯入 Office 365 的好方法。</span><span class="sxs-lookup"><span data-stu-id="e5da6-411">It's a good way to import your organization's archival messaging data to Office 365.</span></span>
    
  - <span data-ttu-id="e5da6-412">資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-412">The data is available to the user from all devices because it's stored in the cloud.</span></span>
    
  - <span data-ttu-id="e5da6-p167">可讓您從您所匯入 PST 檔案套用到資料的 Office 365 的符合性功能協助組織的地址規範需求。這包括：</span><span class="sxs-lookup"><span data-stu-id="e5da6-p167">It helps address compliance needs of your organization by letting you apply Office 365 compliance features to the data from the PST files that you imported. This includes:</span></span>
    
  - <span data-ttu-id="e5da6-415">啟用[封存信箱](enable-archive-mailboxes.md)並提供使用者其他信箱的儲存空間來儲存您所匯入資料的 [[自動展開封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-415">Enabling [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space to store the data that you imported.</span></span> 
    
  - <span data-ttu-id="e5da6-416">進行信箱您所匯入資料的保留 [[訴訟暫止狀態](https://go.microsoft.com/fwlink/?linkid=856286)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-416">Placing mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data that you imported.</span></span> 
    
  - <span data-ttu-id="e5da6-417">使用 Microsoft [eDiscovery 工具](search-for-content.md)來搜尋您匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-417">Using Microsoft [eDiscovery tools](search-for-content.md) to search the data that you imported.</span></span> 
    
  - <span data-ttu-id="e5da6-418">使用[Office 365 的保留原則](retention-policies.md)以控制的保留期限您匯入的資料，以及要採取的保留期間到期後的動作。</span><span class="sxs-lookup"><span data-stu-id="e5da6-418">Using [Office 365 retention policies](retention-policies.md) to control how long the data that you imported will be retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="e5da6-419">搜尋[Office 365 稽核記錄](search-the-audit-log-in-security-and-compliance.md)的信箱相關的事件會影響您匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-419">Searching the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for mailbox-related events that affect the data that you imported.</span></span> 
    
  - <span data-ttu-id="e5da6-420">將資料匯入[非使用中信箱](create-and-manage-inactive-mailboxes.md)的規範目的封存資料。</span><span class="sxs-lookup"><span data-stu-id="e5da6-420">Importing data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="e5da6-421">若要防止機密資料流失貴組織的內部使用[的資料外洩防護原則](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e5da6-421">Using [data loss prevention policies](data-loss-prevention-policies.md) to prevent sensitive data from leaking outside your organization.</span></span> 
  
- <span data-ttu-id="e5da6-p168">以下是範例取得在步驟 1 中的共用存取簽章 (SAS) URL。這個範例也會包含命令執行 AzCopy.exe 工具 PST 檔案上傳至 Office 365 的語法。請務必採取預防措施就像您會保護密碼或其他安全性相關的資訊保護 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="e5da6-p168">Here's an example of the Shared Access Signature (SAS) URL that's obtained in Step 1. This example also contains the syntax for the command that you run in the AzCopy.exe tool to upload PST files to Office 365. Be sure to take precautions to protect the SAS URL just like you would protect passwords or other security-related information.</span></span>

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  **True** so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the **Set-Mailbox -RetentionHoldEnabled $false** command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 8/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
