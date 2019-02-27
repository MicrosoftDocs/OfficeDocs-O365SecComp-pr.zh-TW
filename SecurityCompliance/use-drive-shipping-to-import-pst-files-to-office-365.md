---
title: 使用的磁碟機傳送至您的組織 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '系統管理員： 了解如何將大量匯入您的組織至 Office 365 信箱的 PST 檔案複製到硬碟的 PST 檔案，然後將其傳送給 Microsoft。 '
ms.openlocfilehash: 0e902df03628711d8ccdaaf1fd42153eba1e1623
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296816"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="c06a1-103">使用的磁碟機傳送至您的組織 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="c06a1-103">Use drive shipping to import your organization PST files to Office 365</span></span>

<span data-ttu-id="c06a1-104">**本文適用於系統管理員。您嘗試 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span><span class="sxs-lookup"><span data-stu-id="c06a1-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="c06a1-p101">使用匯入 Office 365 服務及傳送至大量匯入至使用者信箱的 PST 檔案的磁碟機。傳送表示您將 PST 檔案複製到硬碟機，並將實體隨附給 Microsoft 的磁碟機的磁碟機。當 Microsoft 收到您的硬碟時，資料中心人員會將複製資料從硬碟到 Microsoft 雲端儲存區。然後您必須有機會修剪 PST 資料實際上所匯入至目標信箱設定控制哪些資料取得匯入的篩選。當您啟動匯入工作後，匯入服務匯入 PST 資料存放區從使用者信箱。使用的磁碟機傳送至 PST 檔案匯入使用者的信箱為貴組織的電子郵件移轉至 Office 365 的其中一個方法。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p101">Use the Office 365 Import service and drive shipping to bulk-import PST files to user mailboxes. Drive shipping means that you copy the PST files to a hard disk drive and then physically ship the drive to Microsoft. When Microsoft receives your hard drive, data center personnel will copy the data from the hard drive to a storage area in the Microsoft cloud. Then you have the opportunity to trim the PST data that's actually imported to the target mailboxes by setting filters that control what data gets imported. After you start the import job, the Import service imports the PST data from the storage area to user mailboxes. Using drive shipping to import PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
  
<span data-ttu-id="c06a1-111">若要使用的磁碟機傳送至 PST 檔案匯入 Office 365 信箱所需的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="c06a1-111">Here are the steps required to use drive shipping to import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="c06a1-112">步驟 1： 下載安全儲存機碼和 PST 匯入工具</span><span class="sxs-lookup"><span data-stu-id="c06a1-112">Step 1: Download the secure storage key and PST Import tool</span></span>](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[<span data-ttu-id="c06a1-113">步驟 2： 將 PST 檔案複製到硬碟</span><span class="sxs-lookup"><span data-stu-id="c06a1-113">Step 2: Copy the PST files to the hard drive</span></span>](#step-2-copy-the-pst-files-to-the-hard-drive)

[<span data-ttu-id="c06a1-114">步驟 3： 建立 PST 匯入對應檔案</span><span class="sxs-lookup"><span data-stu-id="c06a1-114">Step 3: Create the PST Import mapping file</span></span>](#step-3-create-the-pst-import-mapping-file)

[<span data-ttu-id="c06a1-115">步驟 4：在 Office 365 中建立 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="c06a1-115">Step 4: Create a PST Import job in Office 365</span></span>](#step-4-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="c06a1-116">步驟 5：運送硬碟給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c06a1-116">Step 5: Ship the hard drive to Microsoft</span></span>](#step-5-ship-the-hard-drive-to-microsoft)

[<span data-ttu-id="c06a1-117">步驟 6： 篩選資料並開始 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="c06a1-117">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> <span data-ttu-id="c06a1-p102">您必須執行步驟 1 一次向下載入安全儲存金鑰及匯入工具。您執行這些步驟之後，請遵循步驟 2 到步驟 6 的每當您想要運送硬碟給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p102">You have to perform Step 1 once to down load the secure storage key and the import tool. After you perform these steps, follow Step 2 through Step 6 each time you want to ship a hard drive to Microsoft.</span></span> 
  
<span data-ttu-id="c06a1-120">針對常詢問過關於使用傳送至 PST 檔案匯入 Office 365，請參閱[使用傳送至 PST 檔匯入的磁碟機的常見問題集](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)的磁碟機的問題。</span><span class="sxs-lookup"><span data-stu-id="c06a1-120">For frequently asked questions about using drive shipping to import PST files to Office 365, see [FAQs for using drive shipping to import PST files](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c06a1-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="c06a1-121">Before you begin</span></span>

- <span data-ttu-id="c06a1-p103">您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後再將自己的成員身分或者。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="c06a1-127">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="c06a1-127">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="c06a1-p104">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="c06a1-130">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-130">Or</span></span>
    
  - <span data-ttu-id="c06a1-131">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="c06a1-131">You have to be a global administrator in your Office 365 organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c06a1-p105">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="c06a1-p106">您要儲存您想要複製到硬碟上的檔案伺服器或組織中的共用的資料夾的 PST 檔案。步驟 2 中您用來執行 「 Azure 匯入 / 匯出工具 (WAImportExport.exe)，會將複製的 PST 檔案，這個檔案伺服器上儲存或共用資料夾至硬碟。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p106">You need to store the PST files that you want to copy to a hard drive on a file server or shared folder in your organization. In Step 2, you'll run the Azure Import Export tool (WAImportExport.exe) that will copy the PST files that are stored on this file server or shared folder to the hard drive.</span></span>
    
- <span data-ttu-id="c06a1-p107">僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。您可以使用硬碟最多 10 TB。匯入的工作會處理在硬碟上的只有第一個資料量。資料磁碟區必須以 NTFS 格式化。時將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加或 2.5 或 3.5 英吋 SATA II/III 連接器或您可以附加外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 吋 SATA II/III USB 介面卡。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p107">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c06a1-p108">內建的 USB 介面卡隨附的外部硬碟不支援的 Office 365 匯入服務。此外，不能使用的磁碟內外部的硬碟磁碟機的大小寫。請不要隨附外部硬碟。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p108">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
- <span data-ttu-id="c06a1-p109">硬碟複製至 PST 檔案必須使用 BitLocker 加密。您在步驟 2 中執行 WAImportExport.exe 工具可協助您設定 BitLocker。它也會產生 BitLocker 加密金鑰的 Microsoft 資料中心人員會用來存取的磁碟機上傳至 Microsoft 雲端中的 [Azure 存放區] 區域的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p109">The hard drive that you copy the PST files to must be encrypted with BitLocker. The WAImportExport.exe tool that you run in Step 2 will help you set up BitLocker. It also generates a BitLocker encryption key that Microsoft data center personnel will use to access the drive to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="c06a1-p110">透過 Microsoft Enterprise Agreement (EA) 使用的磁碟機傳送。磁碟機傳送無法透過 Microsoft 產品和服務合約 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p110">Drive shipping is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
    
- <span data-ttu-id="c06a1-p111">PST 檔案匯入 Office 365 信箱使用的磁碟機傳送的成本是 $2 USD 每 GB 的資料。例如，如果您隨附包含 1000 GB (1 TB) 的 PST 檔案的硬碟，成本是 $2000 USD。您可以使用合作夥伴支付匯入費用。如需尋找協力廠商的資訊，請參閱[尋找 Office 365 協力廠商或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p111">The cost to import PST files to Office 365 mailboxes using drive shipping is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
    
- <span data-ttu-id="c06a1-153">您或貴組織必須擁有 FedEx 或 DHL 的帳戶。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-153">You or your organization must have an account with FedEx or DHL.</span></span>
    
  - <span data-ttu-id="c06a1-154">在美國、 巴西、 和歐洲的組織必須擁有 FedEx 帳戶。</span><span class="sxs-lookup"><span data-stu-id="c06a1-154">Organizations in the United States, Brazil, and Europe must have FedEx accounts.</span></span>
    
  - <span data-ttu-id="c06a1-155">在東亞、 東南亞洲 （日本）、 共和國的韓國及澳洲的組織必須擁有 DHL 帳戶。</span><span class="sxs-lookup"><span data-stu-id="c06a1-155">Organizations in East Asia, Southeast Asia, Japan, Republic of Korea, and Australia must have DHL accounts.</span></span>
    
    <span data-ttu-id="c06a1-156">Microsoft 會使用此帳戶來將硬碟送回給您 (以及計費)。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-156">Microsoft will use (and charge) this account to return the hard drive back to you.</span></span>
    
- <span data-ttu-id="c06a1-p112">運送給 Microsoft 的硬碟，可能必須跨越國境。在這種情況下，您必須負責確保硬碟機和它所包含的資料，會根據相關的法律匯入和/或匯出。運送硬碟之前，請向您的顧問確認磁碟機及資料可以合法的運送到指定的 Microsoft 資料中心。這是為了確保它及時送達 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p112">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the identified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
    
- <span data-ttu-id="c06a1-p113">此程序包括複製並儲存的安全認證儲存機碼和 BitLocker 加密金鑰。請務必採取預防措施像您會保護密碼或其他安全性相關的資訊保護這些機碼。例如，您可能會將其儲存至受密碼保護 Microsoft Word 文件或將其儲存至已加密的 USB 磁碟機。請參閱[的詳細資訊](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)] 區段中的這些機碼的範例。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p113">This procedure involves copying and saving a secure storage key and a BitLocker encryption key. Be sure to take precautions to protect these keys like you would protect passwords or other security-related information. For example, you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for an example of these keys.</span></span> 
    
- <span data-ttu-id="c06a1-p114">PST 檔案匯入至 Office 365 信箱之後，為信箱設定保留功能會開啟無限期的持續期間。這表示將不會處理在您關閉保留功能或設定要關閉保留日期之前中指派給信箱的保留原則。為什麼這麼做這？如果舊匯入至信箱的郵件，則它們可能會永久刪除 （清除） 因為其保留期間已過期為基礎之信箱的保留設定。將信箱設定保留功能將會讓信箱擁有者時間來管理這些新匯入訊息或讓您變更信箱的保留設定的時間。請參閱如需管理保留功能的建議[的詳細資訊](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)] 區段。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p114">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="c06a1-p115">根據預設，可以接收的 Office 365 信箱的最大郵件大小為 35 MB。那是因為信箱的*MaxReceiveSize*屬性的預設值設定為 35 MB。不過，限制的最大郵件的接收大小 Office 365 中為 150 MB。如此若您匯入 PST 檔案包含大於 35 MB，我們會自動將目標信箱上*MaxReceiveSize*屬性的值變更為 150 MB 的匯入 Office 365 服務的項目。這可讓郵件最多可 150 MB 要匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p115">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c06a1-176">若要找出郵件的接收大小的信箱，您可以執行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。</span><span class="sxs-lookup"><span data-stu-id="c06a1-176">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 
  
- <span data-ttu-id="c06a1-p116">您可以將 PST 檔案匯入 Office 365 中的非使用中信箱。您執行此動作以指定在非使用中信箱的 GUID `Mailbox` PST 匯入對應檔案中的參數。請參閱[步驟 3： 建立 PST 匯入對應檔案](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p116">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 
    
- <span data-ttu-id="c06a1-p117">在 Exchange 混合部署中，您可以 PST 檔案匯入雲端式封存信箱的主要信箱位於內部部署的使用者。您這麼做依照 PST 匯入對應檔案中的下列：</span><span class="sxs-lookup"><span data-stu-id="c06a1-p117">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="c06a1-182">指定使用者的內部部署信箱中的電子郵件地址`Mailbox`參數。</span><span class="sxs-lookup"><span data-stu-id="c06a1-182">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="c06a1-183">指定**TRUE**值`IsArchive`參數。</span><span class="sxs-lookup"><span data-stu-id="c06a1-183">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="c06a1-184">請參閱[步驟 3： 建立 PST 匯入對應檔案](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-184">See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a><span data-ttu-id="c06a1-185">步驟 1： 下載安全儲存機碼和 PST 匯入工具</span><span class="sxs-lookup"><span data-stu-id="c06a1-185">Step 1: Download the secure storage key and PST Import tool</span></span>

<span data-ttu-id="c06a1-186">第一個步驟是下載的安全認證儲存金鑰及工具，而且您要用以步驟 2 中複製到硬碟的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-186">The first step is to download the secure storage key and the tool and that you will use in Step 2 to copy PST files to the hard drive.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c06a1-p118">您必須使用 Azure 匯入/匯出工具版本 1 (WAimportExportV1) 若要使用的磁碟機傳送方法成功匯入 PST 檔案。第 2 版的 Azure 匯入/匯出工具不支援和使用它會導致不正確地準備匯入工作硬碟。請務必下載 Azure 匯入/匯出工具的安全性&amp;規範中心遵循此步驟中的程序。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p118">You have to use Azure Import/Export tool version 1 (WAimportExportV1) to successfully import PST files by using the drive shipping method. Version 2 of the Azure Import/Export tool isn't supported and using it will result in incorrectly preparing the hard drive for the import job. Be sure to download the Azure Import/Export tool from the Security &amp; Compliance Center by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="c06a1-190">移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c06a1-190">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c06a1-191">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-191">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c06a1-192">之前所述，您必須被指派存取安全性 [**匯入**] 頁面上的適當權限&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="c06a1-192">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
3. <span data-ttu-id="c06a1-193">在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-193">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="c06a1-p119">在 [匯入工作精靈] 中，輸入 PST 匯入工作名稱，並再按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p119">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="c06a1-197">在 [**選擇匯入工作類型**] 頁面上按一下 [**傳送至我們實體位置的硬碟機**並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-197">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![按一下 [傳送至我們建立傳送匯入工作的磁碟機的實體位置的硬碟機](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="c06a1-199">在 [**匯入資料**] 頁面上執行下列兩件事：</span><span class="sxs-lookup"><span data-stu-id="c06a1-199">On the **Import data** page, do the following two things:</span></span> 
    
    ![複製的安全認證儲存金鑰並下載 Azure 匯入 / 匯出工具在匯入資料] 頁面](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    <span data-ttu-id="c06a1-p120">a.在步驟 2 中，按一下 [**複製的安全認證儲存索引鍵**。顯示儲存金鑰後，按一下 [**複製到剪貼簿**然後將其貼並將其儲存至檔案，讓您可以稍後存取。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p120">a. In step 2, click **Copy the secure storage key**. After the storage key is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="c06a1-p121">b.在步驟 3、 下載及安裝 Azure 匯入/匯出 （版本 1） 工具**下載 Azure 匯入/匯出工具**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p121">b. In step 3, **Download the Azure Import/Export tool** to download and install the Azure Import/Export (version 1) tool.</span></span>
    
    - <span data-ttu-id="c06a1-206">在快顯視窗中，按一下 [**儲存** \> WaImportExportV1.zip 檔案儲存到資料夾本機電腦上的 [**另存為**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-206">In the pop-up window, click **Save** \> **Save as** to save the WaImportExportV1.zip file to a folder on your local computer.</span></span> 
    
    - <span data-ttu-id="c06a1-207">解壓縮 WaImportExportV1.zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-207">Extract the WaImportExportV1.zip file.</span></span>
    
7. <span data-ttu-id="c06a1-208">按一下 [**取消**] 以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="c06a1-208">Click **Cancel** to close the wizard.</span></span> 
    
    <span data-ttu-id="c06a1-209">您將會回到 [**匯入**] 頁面上的 [安全性]&amp;規範中心當您在步驟 4 中建立匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-209">You'll come back to the **Import** page in the Security &amp; Compliance Center when you create the import job in Step 4.</span></span> 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a><span data-ttu-id="c06a1-210">步驟 2： 將 PST 檔案複製到硬碟</span><span class="sxs-lookup"><span data-stu-id="c06a1-210">Step 2: Copy the PST files to the hard drive</span></span>

<span data-ttu-id="c06a1-p122">下一個步驟是使用 WAImportExport.exe 工具來將 PST 檔案複製到硬碟。這項工具硬碟與 BitLocker 會加密、 將 Pst 複製到硬碟，並建立日誌檔案儲存複本的程序的相關資訊。若要完成此步驟，PST 檔案必須位於檔案共用或組織中的檔案伺服器。這就是所謂的下列程序中的來源目錄。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p122">The next step is to use the WAImportExport.exe tool to copy PST files to the hard drive. This tool encrypts the hard drive with BitLocker, copies the PSTs to the hard drive, and creates a journal file that stores information about the copy process. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c06a1-p123">硬碟的第一次執行 WAImportExport.exe 工具之後，您必須使用不同的語法每個之後的時間。此語法會說明此程序可將 PST 檔案複製到硬碟的步驟 4 中。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p123">After you run the WAImportExport.exe tool the first time for a hard drive, you have to use a different syntax each time after that. This syntax is explained in step 4 of this procedure to copy PST files to the hard drive.</span></span> 
  
1. <span data-ttu-id="c06a1-217">在您的本機電腦上開啟 [命令提示字元]。</span><span class="sxs-lookup"><span data-stu-id="c06a1-217">Open a Command Prompt on your local computer.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c06a1-p124">如果您以系統管理員身分執行命令提示字元 (當您開啟時選取「以系統管理員身分執行」)，在命令提示字元視窗中，將顯示錯誤訊息。這可以協助您進行關於執行 WAImportExport.exe 工具問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p124">If you run the command prompt as an administrator (by selecting "Run as administrator" when you open it) error messages will be displayed in the command prompt window. This can help you troubleshoot problems running the WAImportExport.exe tool.</span></span> 
  
2. <span data-ttu-id="c06a1-220">移至您在步驟 1 中安裝 WAImportExport.exe 工具的目錄。</span><span class="sxs-lookup"><span data-stu-id="c06a1-220">Go to the directory where you installed the WAImportExport.exe tool in Step 1.</span></span>
    
3. <span data-ttu-id="c06a1-221">首次執行下列命令，您會使用 WAImportExport.exe 來將 PST 檔案複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="c06a1-221">Run the following command the first time that you use the WAImportExport.exe to copy PST files to a hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    <span data-ttu-id="c06a1-222">下表說明了參數與其需要的值。</span><span class="sxs-lookup"><span data-stu-id="c06a1-222">The following table describes the parameters and their required values.</span></span>
    
    |<span data-ttu-id="c06a1-223">**參數**</span><span class="sxs-lookup"><span data-stu-id="c06a1-223">**Parameter**</span></span>|<span data-ttu-id="c06a1-224">**描述**</span><span class="sxs-lookup"><span data-stu-id="c06a1-224">**Description**</span></span>|<span data-ttu-id="c06a1-225">**範例**</span><span class="sxs-lookup"><span data-stu-id="c06a1-225">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/j:` <br/> |<span data-ttu-id="c06a1-p125">指定日誌檔的名稱。此檔案會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。您送交給 Microsoft 的每個硬碟都必須有一個日誌檔案。每次您執行 WAImportTool.exe，將 PST 檔案複製到硬碟時，資訊都將會附加到該磁碟機的日誌檔。 
</span><span class="sxs-lookup"><span data-stu-id="c06a1-p125">Specifies the name of the journal file. This file is saved to the same folder where the WAImportExport.exe tool is located. Each hard drive you ship to Microsoft must have one journal file. Every time you run the WAImportTool.exe to copy PST files to a hard drive, information will be appended to the journal file for that drive.</span></span>  <br/> <span data-ttu-id="c06a1-230">Microsoft 資料中心人員將使用中的資訊的日誌檔案與您在步驟 4 中建立匯入工作相關聯的硬碟並將 PST 檔案上傳至 Microsoft 雲端中的 [Azure 存放區] 區域。</span><span class="sxs-lookup"><span data-stu-id="c06a1-230">Microsoft data center personnel will use the information in the journal file to associate the hard drive with the import job that you create in Step 4, and to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |<span data-ttu-id="c06a1-231">指定當硬碟連接至本機電腦時的磁碟機代號。</span><span class="sxs-lookup"><span data-stu-id="c06a1-231">Specifies the drive letter of the hard drive when it's connected to your local computer.</span></span>  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |<span data-ttu-id="c06a1-p126">指定複製工作階段的名稱。工作階段的定義是每次執行 WAImportExport.exe 工具，將檔案複製到硬碟的動作。PST 檔案會複製到資料夾，該資料夾是以此參數所指定的工作階段名稱來命名。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-p126">Specifies the name of the copy session. A session is defined as each time you run the WAImportExport.exe tool to copy files to the hard drive. The PST files are copied to a folder named with the session name specified by this parameter.</span></span>  <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |<span data-ttu-id="c06a1-p127">指定包含要複製工作階段期間的 PST 檔案在組織中的來源目錄。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p127">Specifies the source directory in your organization that contains the PST files that will be copied during the session. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |<span data-ttu-id="c06a1-p128">在 Azure 的存放區] 區域中 Pst 要上傳 Microsoft cloud 指定目的地目錄。您必須使用值`ingestiondata/`。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p128">Specifies the destination directory in the Azure storage area in the Microsoft cloud where the PSTs will be uploaded. You must use the value  `ingestiondata/`. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/> <span data-ttu-id="c06a1-p129">（選用） 您也可以新增其他檔案路徑為此參數的值。例如，您可以使用在硬碟上 （轉換成的 URL 格式），來源目錄中指定的檔案路徑`/srcdir:`參數。例如，`\\FILESERVER01\PSTs`變更為`FILESERVER01/PSTs`。在此例中，您仍必須包含`ingestiondata`中的檔案路徑。在此範例中的值是`/dstdir:`參數就是`"ingestiondata/FILESERVER01/PSTs"`。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p129">Optionally, you can also add an additional file path to the value of this parameter. For example, you can use the file path of the source directory on the hard drive (converted to a URL format) , which is specified in the  `/srcdir:` parameter. For example,  `\\FILESERVER01\PSTs` is changed to  `FILESERVER01/PSTs`. In this case, you still must include  `ingestiondata` in the file path. So in this example, the value for the  `/dstdir:` parameter would be  `"ingestiondata/FILESERVER01/PSTs"`.  </span></span><br/> <span data-ttu-id="c06a1-245">若要新增其他檔案路徑的其中一個原因是如果您必須具有相同的檔名的 Pst 檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-245">One reason to add the additional file path is if you have PSTs files with the same filename.</span></span>  <br/> <span data-ttu-id="c06a1-p130">> [!NOTE]如果您包括選用 pathname >、 PST 檔案上傳至 Azure 儲存區域後的命名空間將會包含路徑名稱及 PST 檔案名稱 ；例如， `FILESERVER01/PSTs/annb.pst`。如果您未包含路徑名稱、 命名空間是僅限 PST 檔案名稱 ；例如`annb.pst`。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p130">> [!NOTE]> If you include the optional pathname, the namespace for a PST file after it's uploaded to the Azure storage area will include the pathname and the name of the PST file; for example,  `FILESERVER01/PSTs/annb.pst`. If you don't include a pathname, the namespace is only the PST filename; for example  `annb.pst`.</span></span>           | `/dstdir:"ingestiondata/"` <br/> <span data-ttu-id="c06a1-248">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-248">Or</span></span>  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |<span data-ttu-id="c06a1-p131">在步驟 1 中指定您取得儲存帳戶機碼。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p131">Specifies the storage account key that you obtained in Step 1. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此參數會開啟硬碟的 BitLocker。首次執行 WAImportExport.exe 工具時需要此參數。  <br/> <span data-ttu-id="c06a1-p133">BitLocker 加密金鑰複製到日誌檔案和記錄檔會建立如果您使用`/logfile:`參數。如先前所述的日誌檔案會儲存到 WAImportExport.exe 工具所在的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p133">The BitLocker encryption key is copied to the journal file and the log file that is created if you use the  `/logfile:` parameter. As previously explained, the journal file is saved to the same folder where the WAImportExport.exe tool is located.  </span></span><br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |<span data-ttu-id="c06a1-p134">此選用參數會指定儲存記錄檔的資料夾。如果未指定，記錄檔會儲存至相同 WAImportExport.exe 工具所在的資料夾。請務必環繞雙引號使用此參數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p134">This optional parameter specifies a folder to save log files to. If not specified, the log files are save to the same folder where the WAImportExport.exe tool is located. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    <span data-ttu-id="c06a1-258">這是 WAImportExport.exe 工具針對各個參數使用實際值的語法範例︰</span><span class="sxs-lookup"><span data-stu-id="c06a1-258">Here's an example of the syntax for the WAImportExport.exe tool using actual values for each parameter:</span></span>
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    <span data-ttu-id="c06a1-p135">在您執行命令後，便會顯示 PST 檔案複製到硬碟進度的狀態訊息。最終狀態訊息會顯示已成功複製的檔案總數。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-p135">After you run the command, status messages are displayed that show the progress of copying the PST files to the hard drive. A final status message shows the total number of files that were successfully copied.</span></span>
    
4. <span data-ttu-id="c06a1-261">以後每次您執行 WAImportExport.ext 工具，將 PST 檔案複製到相同的硬碟時，都要執行此命令。</span><span class="sxs-lookup"><span data-stu-id="c06a1-261">Run this command each subsequent time you run the WAImportExport.ext tool to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    <span data-ttu-id="c06a1-262">這是以後執行工作階段，將 PST 檔案複製到相同的硬碟時的語法範例。  </span><span class="sxs-lookup"><span data-stu-id="c06a1-262">Here's an example of the syntax for running subsequent sessions to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a><span data-ttu-id="c06a1-263">步驟 3： 建立 PST 匯入對應檔案</span><span class="sxs-lookup"><span data-stu-id="c06a1-263">Step 3: Create the PST Import mapping file</span></span>

<span data-ttu-id="c06a1-p136">匯入服務 Microsoft 資料中心人員上傳至 Azure 的存放區從硬碟 PST 檔案之後，將會是以逗號分隔值 (CSV) 檔案，指定哪些使用者信箱 PST PST 匯入對應檔案中使用的資訊檔案會以匯入。當您建立 PST 匯入工作，會送出這個的 CSV 檔案中的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p136">After Microsoft data center personnel upload the PST files from the hard drive to the Azure storage area, the Import service will use the information in the PST Import mapping file, which is a comma separated value (CSV) file, that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="c06a1-266">[下載 PST 匯入對應檔案的複本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-266">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="c06a1-p137">開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p137">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    <span data-ttu-id="c06a1-p138">第一列或欄位名稱] 列的 CSV 檔案列出要使用 PST 匯入服務至 PST 檔案匯入使用者信箱的參數。每個參數名稱是以逗號分隔。標頭列] 下方的每一個資料列代表將 PST 檔案匯入特定信箱的參數值。您將需要一列的每個 PST 檔案複製到硬碟。請務必對應檔案中的版面配置區資料取代實際資料。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p138">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that was copied to the hard drive. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c06a1-275">不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。</span><span class="sxs-lookup"><span data-stu-id="c06a1-275">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="c06a1-276">使用下列表格的資訊，將所需的資訊填入 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-276">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="c06a1-277">**參數**</span><span class="sxs-lookup"><span data-stu-id="c06a1-277">**Parameter**</span></span>|<span data-ttu-id="c06a1-278">**描述**</span><span class="sxs-lookup"><span data-stu-id="c06a1-278">**Description**</span></span>|<span data-ttu-id="c06a1-279">**範例**</span><span class="sxs-lookup"><span data-stu-id="c06a1-279">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="c06a1-p139">指定要匯入資料至 Office 365 服務。若要匯入 PST 檔案至使用者信箱，請使用`Exchange`。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p139">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> | <span data-ttu-id="c06a1-282">PST 檔案會複製到運送硬碟時向 Microsoft Azure 儲存區域中指定的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="c06a1-282">Specifies the folder location in the Azure storage area that PST files will be copied to when the hard drive is shipped to Microsoft.</span></span>  <br/>  <span data-ttu-id="c06a1-283">您新增此資料行中的 CSV 檔案取決於內容中所指定的`/dstdir:`先前步驟中的參數。</span><span class="sxs-lookup"><span data-stu-id="c06a1-283">What you add in this column in the CSV file depends on what you specified in for the  `/dstdir:` parameter in the previous step.</span></span>  <br/>  <span data-ttu-id="c06a1-284">如果您是使用`/dstdir:"ingestiondata/"`，然後將此參數保留空白 CSV 檔案中。</span><span class="sxs-lookup"><span data-stu-id="c06a1-284">If you used  `/dstdir:"ingestiondata/"`, then leave this parameter blank in the CSV file.</span></span>  <br/>  <span data-ttu-id="c06a1-p140">如果您包含的值選用 pathname`/dstdir:`參數 (例如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`，然後使用 CSV 檔案中的此參數 （不包括"ingestiondata"） 的路徑名稱。此參數的值是區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p140">If you included an optional pathname for the value of the  `/dstdir:` parameter (for example,  `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, then use that pathname (not including "ingestiondata") for this parameter in the CSV file. The value for this parameter is case sensitive.  </span></span><br/>  <span data-ttu-id="c06a1-p141">無論如何，*不*包含"ingestiondata"中的值`FilePath`參數。將此參數保留空白，或指定的選用路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p141">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter. Leave this parameter blank or specify only the optional pathname.  </span></span><br/> <span data-ttu-id="c06a1-p142">> [!IMPORTANT]> 大小寫的檔案路徑名稱必須是相同的案例中所指定`/dstdir:`先前步驟中的參數。例如，如果您是使用`"ingestiondata/FILESERVER01/PSTs"`子資料夾名稱在先前步驟中，但接著會使用`fileserver01/psts`中`FilePath`CSV 檔中的參數，將會失敗 PST 檔案匯入。請務必在兩個執行個體中使用相同的大小寫。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p142">> [!IMPORTANT]>  The case for the file path name must be the same case that you specified in the  `/dstdir:` parameter in the previous step . For example, if you used  `"ingestiondata/FILESERVER01/PSTs"` for the subfolder name in the previous step, but then used  `fileserver01/psts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="c06a1-292">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c06a1-292">(leave blank)</span></span>  <br/> <span data-ttu-id="c06a1-293">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-293">Or</span></span>  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="c06a1-p143">指定要匯入至使用者信箱的 PST 檔案的名稱。此參數的值是區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p143">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="c06a1-p144">> [!IMPORTANT]> CSV 檔案中的 PST 檔案名稱的大小寫必須是已上傳至步驟 2 中的 Azure 儲存位置的 PST 檔案相同。例如，如果您使用`annb.pst`中`Name`參數中的 CSV 檔案，但實際的 PST 檔案的名稱是`AnnB.pst`，該 PST 檔案匯入就會失敗。請務必 PST CSV 檔案中的名稱會使用為實際的 PST 檔案的大小寫相同。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p144">> [!IMPORTANT]> The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="c06a1-p145">會指定 PST 檔案將會匯入至信箱的電子郵件地址。請注意您無法指定公用資料夾因為 PST 匯入服務不支援將 PST 檔案匯入的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p145">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="c06a1-p146">匯入 PST 檔案至不在作用中的信箱，您必須指定此參數的信箱 GUID。若要取得這個 GUID，請執行下列 PowerShell 命令 in Exchange Online：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="c06a1-p146">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span></span> <br/> <span data-ttu-id="c06a1-p147">> [!NOTE]> 在某些情況下，您可能會有多個信箱使用同一個電子郵件地址，其中一個信箱不在作用中信箱和其他信箱位於虛刪除 （或非使用中） 的狀態。在下列情況下，您必須指定信箱的信箱來唯一地識別要匯入至 PST 檔案的信箱 GUID。若要取得這個作用中信箱的 GUID，請執行下列 PowerShell 命令： `Get-Mailbox <identity of active mailbox> | FL Guid`。若要取得虛刪除 （或非使用中） 的信箱的 GUID，請執行下列命令： `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p147">> [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="c06a1-307">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-307">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="c06a1-p148">指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="c06a1-p148">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="c06a1-310">**FALSE**將 PST 檔案匯入使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-310">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="c06a1-p149">**True 是表示**將 PST 檔案匯入使用者的封存信箱。本範例假設[已啟用使用者的封存信箱](enable-archive-mailboxes.md)。如果您將這個參數設定為`TRUE`和未啟用使用者的封存信箱、 匯入的使用者將會失敗。請注意，如果匯入失敗的一位使用者 (因為其封存未啟用且此屬性設為`TRUE`)，將不會影響其他使用者匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p149">**TRUE** Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="c06a1-315">如果您將此參數保留空白，PST 檔案匯入使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-315">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="c06a1-316">**附註：** 匯入 PST 檔案到雲端式封存信箱的主要信箱位於內部部署的使用者，剛指定`TRUE`為此參數指定使用者的內部部署信箱的電子郵件地址`Mailbox`參數。</span><span class="sxs-lookup"><span data-stu-id="c06a1-316">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="c06a1-317">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-317">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="c06a1-318">指定要匯入 PST 檔案的信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="c06a1-318">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="c06a1-319">如果您將此參數保留空白，PST 會匯入至名為的**匯入**位於信箱 （相同層級 [收件匣] 資料夾和其他預設信箱資料夾） 的根層級的新資料夾。</span><span class="sxs-lookup"><span data-stu-id="c06a1-319">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="c06a1-320">如果您指定`/`、 PST 檔案中的項目會被匯入直接在使用者的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c06a1-320">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="c06a1-p150">如果您指定`/<foldername>`、 PST 檔案中的項目將會匯入至名為資料夾\*\<foldername\> \* 。例如，如果您使用`/ImportedPst`、 項目會匯入至名為**ImportedPst**的資料夾。這個資料夾會位於 [收件匣] 資料夾相同層級的使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p150">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/> |<span data-ttu-id="c06a1-324">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c06a1-324">(leave blank)</span></span>  <br/> <span data-ttu-id="c06a1-325">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-325">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="c06a1-326">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-326">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="c06a1-p151">此選用參數會指定要用於匯入 PST 檔案中的 ANSI 檔案格式的字碼頁的數值。此參數用於從中文、 日文及韓文 (CJK) 的組織中匯入 PST 檔案，因為這些語言通常使用雙位元組字元集 (DBCS) 的字元編碼。如果此參數不用來匯入 PST 檔案的信箱資料夾名稱使用 DBCS 的語言，則他們正在匯入後通常被混亂資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p151">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/> <span data-ttu-id="c06a1-330">如需使用此參數，請參閱[程式碼頁面識別碼](https://go.microsoft.com/fwlink/p/?LinkId=328514)支援值的清單。</span><span class="sxs-lookup"><span data-stu-id="c06a1-330">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <span data-ttu-id="c06a1-p152">> [!NOTE]> 如先前所述，這是選用的參數與您沒有包含 CSV 檔案中。或者您可以將它包含並將此值保留空白的一或多個資料列。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p152">> [!NOTE]> As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="c06a1-333">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c06a1-333">(leave blank)</span></span>  <br/> <span data-ttu-id="c06a1-334">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-334">Or</span></span>  <br/>  <span data-ttu-id="c06a1-335">`932`（這是程式碼] 頁面上的識別碼 ANSI/OEM 日文）</span><span class="sxs-lookup"><span data-stu-id="c06a1-335">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="c06a1-336">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-336">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c06a1-337">不適用</span><span class="sxs-lookup"><span data-stu-id="c06a1-337">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="c06a1-338">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-338">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c06a1-339">不適用</span><span class="sxs-lookup"><span data-stu-id="c06a1-339">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="c06a1-340">針對 PST 匯入，請將此參數保留空白。 </span><span class="sxs-lookup"><span data-stu-id="c06a1-340">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c06a1-341">不適用</span><span class="sxs-lookup"><span data-stu-id="c06a1-341">Not applicable</span></span>  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="c06a1-342">步驟 4：在 Office 365 中建立 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="c06a1-342">Step 4: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="c06a1-p153">下一步是建立 Office 365 中的匯入服務中的 PST 匯入工作。如先前所述，您會將提交您在步驟 3 中建立之 PST 匯入對應檔案。建立新的工作之後，匯入服務將使用中的資訊之對應檔案匯入 PST 檔案至指定的使用者信箱後 PST 檔案從硬碟複製到 Azure 儲存區與您建立並啟動匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p153">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 3. After you create the new job, the Import service will use the information in the mapping file to import the PST files to the specified user mailbox after the PST files are copied from the hard drive to the Azure storage area and you create and start the import job.</span></span>
  
1. <span data-ttu-id="c06a1-346">移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c06a1-346">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c06a1-347">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管**] 和 [**匯入**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-347">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="c06a1-348">在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-348">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c06a1-349">之前所述，您必須被指派存取安全性 [**匯入**] 頁面上的適當權限&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="c06a1-349">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
4. <span data-ttu-id="c06a1-p154">輸入 PST 匯入工作、 名稱，然後按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p154">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="c06a1-353">在 [**選擇匯入工作類型**] 頁面上按一下 [**傳送至我們實體位置的硬碟機**並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-353">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![按一下 [傳送至我們建立傳送匯入工作的磁碟機的實體位置的硬碟機](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="c06a1-355">在步驟 6 中，按一下 [**我準備好 「 我的硬碟與存取所需的磁碟機日誌檔案**而且**我有對應檔案的存取權**] 核取方塊中，並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-355">In step 6, click the **I've prepared my hard drives and have access to the necessary drive journal files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![按一下 [步驟 6 中兩個核取方塊](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. <span data-ttu-id="c06a1-p155">在**選取的磁碟機檔案**] 頁面上按一下 [**選取磁碟機檔案**，並前往 WAImportExport.exe 工具所在的相同資料夾。步驟 2 中建立的日誌檔案複製到此資料夾。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p155">On the **Select the drive file** page, click **Select drive file**, and then go to the same folder where the WAImportExport.exe tool is located. The journal file that was created in Step 2 was copied to this folder.</span></span>
    
    ![按一下 [選取磁碟機的檔案送出時執行 WAImportExport.exe 工具所建立的日誌檔案](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. <span data-ttu-id="c06a1-360">選取的日誌檔案 ；例如， `PSTHDD1.jrn`。</span><span class="sxs-lookup"><span data-stu-id="c06a1-360">Select the journal file; for example, `PSTHDD1.jrn`.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c06a1-361">您在步驟 2 中執行 WAImportExport.exe 工具時所指定的日誌檔案名稱`/j:`參數。</span><span class="sxs-lookup"><span data-stu-id="c06a1-361">When you ran the WAImportExport.exe tool in Step 2, the name of the journal file was specified by the  `/j:` parameter.</span></span> 
  
9. <span data-ttu-id="c06a1-362">磁碟機檔案的名稱會出現 [**磁碟機的檔案名稱**後，按一下 [**驗證**] 檢查您的磁碟機的檔案有錯誤。</span><span class="sxs-lookup"><span data-stu-id="c06a1-362">After the name of the drive file appears under **Drive file name**, click **Validate** to check your drive file for errors.</span></span> 
    
    ![按一下 [驗證來驗證您所選取的磁碟機檔案](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    <span data-ttu-id="c06a1-p156">磁碟機檔案具有建立 PST 匯入工作成功驗證。請注意會成功驗證之後的檔案名稱變更為綠色。如果驗證失敗，請按一下 [**檢視記錄檔]** 連結。會開啟錯誤訊息的資訊為何無法將檔案驗證錯誤報告。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p156">The drive file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message with information about why the file failed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c06a1-368">您必須新增及驗證每個硬碟您向 Microsoft 隨附的日誌檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-368">You must add and validate a journal file for each hard drive you ship to Microsoft.</span></span> 
  
10. <span data-ttu-id="c06a1-369">之後新增及驗證每個硬碟將隨附給 Microsoft 的日誌檔案，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="c06a1-369">After adding and validating a journal file for each hard drive that you'll ship to Microsoft, click **Next**.</span></span>
    
11. <span data-ttu-id="c06a1-370">按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**選取對應的檔案**送出您在步驟 3 中建立之 PST 匯入對應檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-370">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Select mapping file** to submit the PST Import mapping file that you created in Step 3.</span></span> 
    
    ![按一下 [選取對應檔案送出 CSV 檔案所建立之匯入工作](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. <span data-ttu-id="c06a1-372">CSV 名稱之後檔案會出現 [**對應檔案名稱**、 按一下 [**驗證**] 檢查 CSV 檔中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="c06a1-372">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![按一下 [驗證] 檢查錯誤的 CSV 檔案](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="c06a1-p157">CSV 檔案具有建立 PST 匯入工作成功驗證。請注意會成功驗證之後的檔案名稱變更為綠色。如果驗證失敗，請按一下 [**檢視記錄檔]** 連結。將開啟驗證錯誤報告失敗的檔案中的每一列的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p157">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
13. <span data-ttu-id="c06a1-378">PST 對應檔案已成功驗證之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="c06a1-378">After the PST mapping file is successfully validated, click **Next**.</span></span>
    
14. <span data-ttu-id="c06a1-379">在**提供連絡人資訊**] 頁面上，請在適用的方塊中輸入連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-379">On the **Provide contact information** page, type your contact information in the applicable boxes.</span></span> 
    
    <span data-ttu-id="c06a1-p158">請注意會顯示您出貨至您硬碟的 Microsoft 位置的地址。這個位址會自動產生取決於您的 Office 365 資料中心位置。將此位址複製到檔案或取得螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p158">Note that the address for the Microsoft location that you will ship your hard drives to is displayed. This address is auto-generated based on your Office 365 data center location. Copy this address to a file or take a screenshot.</span></span>
    
15. <span data-ttu-id="c06a1-383">閱讀條款和條件文件、 [核取方塊，和 [**儲存**] 以送出匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-383">Read the terms and conditions document, click the checkbox, and then click **Save** to submit the import job.</span></span> 
    
    <span data-ttu-id="c06a1-384">匯入工作成功建立，狀態] 頁面上會顯示說明傳送程序的磁碟機的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="c06a1-384">When the import job is successfully created, a status page is displayed that explains the next steps of the drive shipping process.</span></span>
    
16. <span data-ttu-id="c06a1-p159">在 [**匯入**] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以顯示新的磁碟機傳送匯入工作清單中的匯入工作。請注意狀態會設為**等候追蹤數目**。您也可以按一下 [匯入工作，以顯示狀態彈出式] 頁面，其中包含有關匯入工作的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p159">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to displayed the new drive shipping import job in the list of import jobs. Note that the status is set to **Waiting for tracking number**. You can also click the import job to display the status flyout page, which contains more detailed information about the import job.</span></span>
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a><span data-ttu-id="c06a1-388">步驟 5：運送硬碟給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c06a1-388">Step 5: Ship the hard drive to Microsoft</span></span>

<span data-ttu-id="c06a1-p160">下一步是隨附向 Microsoft、 硬碟及再提供物料追蹤數及傳回物料資訊之磁碟機傳送工作。由 Microsoft 接收磁碟機之後，它需要資料的 7 到 10 商務天之間中心人員將 PST 檔案上傳至您的組織的 Azure 儲存區。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p160">The next step is to ship the hard drive to Microsoft, and then provide the tracking number for the shipment and return shipment information for the drive shipping job. After the drive is received by Microsoft, it will take between 7 and 10 business days for data center personnel to upload your PST files to the Azure storage area for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c06a1-p161">如果您沒有提供追蹤號碼並傳回物料資訊建立匯入工作的 14 天內，將過期匯入工作。如果發生這種情況，您必須建立新的磁碟機傳送匯入工作 (請參閱[步驟 4： 在 Office 365 中建立 PST 匯入工作](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) 並重新提交的磁碟機和 PST 匯入對應檔案。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p161">If you don't provide the tracking number and return shipment information within 14 days of creating the import job, the import job will be expired. If this happens, you'll have to create a new drive shipping import job (see [Step 4: Create a PST Import job in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) and re-submit the drive file and the PST import mapping file.</span></span> 
  
### <a name="ship-the-hard-drive"></a><span data-ttu-id="c06a1-393">運送硬碟</span><span class="sxs-lookup"><span data-stu-id="c06a1-393">Ship the hard drive</span></span>

<span data-ttu-id="c06a1-394">當您運送硬碟給 Microsoft 時，請記住下列事項︰</span><span class="sxs-lookup"><span data-stu-id="c06a1-394">Keep the following things in mind when you ship hard drives to Microsoft:</span></span>
  
- <span data-ttu-id="c06a1-395">未隨附的 SATA-USB 配接器;您只能有隨附的硬碟。</span><span class="sxs-lookup"><span data-stu-id="c06a1-395">Don't ship the SATA-to-USB adapter; you only have to ship the hard drive.</span></span>
    
- <span data-ttu-id="c06a1-396">請妥善包裝硬碟；例如，使用防靜電包裝袋或氣泡紙包裝。</span><span class="sxs-lookup"><span data-stu-id="c06a1-396">Package the hard drive properly; for example, use an anti-static bag or bubble wrap.</span></span>
    
- <span data-ttu-id="c06a1-397">使用您所選擇的出貨承運業者運送硬碟給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c06a1-397">Use a delivery carrier of your choice to ship the hard drive to Microsoft.</span></span>
    
- <span data-ttu-id="c06a1-p162">傳送至您在步驟 4 中建立匯入工作時所顯示的 Microsoft 位置的地址硬碟。請務必在傳送至地址中包含"Office 365 匯入服務 」。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p162">Ship the hard drive to the address for the Microsoft location that was displayed when you created the import job in Step 4. Be sure to include "Office 365 Import Service" in the ship-to address.</span></span>
    
- <span data-ttu-id="c06a1-p163">在您運送硬碟後，請務必寫下出貨承運業者的名稱及追蹤號碼。在下一個步驟中您將提供這些資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p163">After you ship the hard drive, be sure to write down the name of the delivery carrier and the tracking number. You'll provide these in the next step.</span></span>
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a><span data-ttu-id="c06a1-402">輸入追蹤號碼，以及其他的送貨資訊</span><span class="sxs-lookup"><span data-stu-id="c06a1-402">Enter the tracking number and other shipping information</span></span>

<span data-ttu-id="c06a1-403">在您運送硬碟給 Microsoft 之後，請在 [匯入] 服務頁面完成下列程序。</span><span class="sxs-lookup"><span data-stu-id="c06a1-403">After you've shipped the hard drive to Microsoft, complete the following procedure on the Import service page.</span></span>
  
1. <span data-ttu-id="c06a1-404">移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c06a1-404">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c06a1-405">在左窗格中，按一下 [**資料控管**和 [**匯入**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-405">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="c06a1-406">在 [**匯入**] 頁面上按一下 [您要輸入的追蹤號碼的磁碟機物料的工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-406">On the **Import** page, click the job for the drive shipment that you want to enter the tracking number for.</span></span> 
    
4. <span data-ttu-id="c06a1-407">在 [狀態彈出式] 頁面上按一下 [**輸入追蹤數字**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-407">On the status flyout page, click **Enter tracking number**.</span></span>
    
5. <span data-ttu-id="c06a1-408">請提供下列的送貨資訊︰</span><span class="sxs-lookup"><span data-stu-id="c06a1-408">Provide the following shipping information:</span></span>
    
1. <span data-ttu-id="c06a1-409">**傳遞電信業者**輸入您用以隨附硬碟向 Microsoft 傳送電信業者的名稱。</span><span class="sxs-lookup"><span data-stu-id="c06a1-409">**Delivery carrier** Type the name of the delivery carrier that you used to ship the hard drive to Microsoft.</span></span> 
    
2. <span data-ttu-id="c06a1-410">**追蹤數目**輸入硬碟物料的追蹤號碼。</span><span class="sxs-lookup"><span data-stu-id="c06a1-410">**Tracking number** Type the tracking number for the hard drive shipment.</span></span> 
    
3. <span data-ttu-id="c06a1-p164">**傳回電信業者帳戶號碼**輸入您的組織帳戶號碼列於下**傳回電信業者**電信業者。Microsoft 會使用 （以及計費） 這個帳戶在您的硬碟隨附給您。請注意在美國和歐洲、 的組織必須具有 FedEx 的帳戶。亞洲與其餘的世界的組織必須具有 DHL 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p164">**Return carrier account number** Type your organization's account number for the carrier that listed under **Return carrier**. Microsoft will use (and charge) this account to ship your hard drive back to you. Note that organizations in the USA and Europe, must have an account with FedEx. Organizations in Asia and the rest of the world, must have an account with DHL.</span></span>
    
6. <span data-ttu-id="c06a1-415">按一下 **[儲存]** 以儲存此資訊供匯入工作使用。</span><span class="sxs-lookup"><span data-stu-id="c06a1-415">Click **Save** to save this information for the import job.</span></span> 
    
    <span data-ttu-id="c06a1-p165">在 [**匯入**] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**以更新的磁碟機傳送匯入工作的資訊。請注意狀態現在已設為**傳送過程中磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p165">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the information for your drive shipping import job. Notice that status is now set to **Drives in transit**.</span></span>

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="c06a1-418">步驟 6： 篩選資料並開始 PST 匯入工作</span><span class="sxs-lookup"><span data-stu-id="c06a1-418">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="c06a1-p166">由 Microsoft 接收硬碟機之後，請在 [**匯入**] 頁面的匯入工作的狀態會變更為**磁碟機已接收之**。資料中心人員會使用日誌檔案中的資訊來將 PST 檔案上傳至您的組織的 Azure 儲存區。此時狀態會變更為 [**匯入為正在進行中**。先前所述，它將會接收到您的硬碟上傳 PST 檔案後 7 到 10 商務天之間。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p166">After your hard drive is received by Microsoft, the status for the import job on the **Import** page will change to **Drives received**. Data center personnel will use the information in the journal file to upload your PST files to the Azure storage area for your organization. At this point, the status will change to **Import in-progress**. As previously stated, it will take between 7 to 10 business days after receiving your hard drive to upload the PST files.</span></span>
  
<span data-ttu-id="c06a1-p167">PST 檔案上傳至 Azure 之後，狀態會變更為**進行中的分析**。這表示 Office 365 分析 （在安全及安全的方式） PST 檔案中的資料以識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。分析已完成且資料已準備好要匯入、 匯入工作的狀態會變更為**分析已完成**。此時，您可選擇匯入 PST 檔案中所包含的所有資料或可以修剪匯入藉由設定控制哪些資料取得匯入的篩選器的資料。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p167">After PST files are uploaded to Azure, the status is changed to **Analysis in progress**. This indicates that Office 365 is analyzing the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, the status for the import job is changed to **Analysis completed**. At this point, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="c06a1-427">移至 [[https://protection.office.com](https://protection.office.com)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c06a1-427">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c06a1-428">在左窗格中，按一下 [**資料控管** > **匯入**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-428">In the left pane, click **Data governance** > **Import**.</span></span>
    
3. <span data-ttu-id="c06a1-429">在 [**匯入**] 頁面上按一下 [**準備好要匯入 Office 365**您在步驟 4 中建立之匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-429">On the **Import** page, click **Ready to import to Office 365** for the import job that you created in Step 4.</span></span> 
    
    ![按一下 [匯入至 Office 365 所建立的匯入工作旁的準備](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="c06a1-431">飛入] 頁面會顯示與 PST 檔案的相關資訊及匯入工作的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-431">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="c06a1-432">按一下 [**匯入至 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-432">Click **Import to Office 365**.</span></span>
    
5. <span data-ttu-id="c06a1-p168">會顯示 [**篩選資料**] 頁面。包含資料前瞻產生分析的 PST 檔案上執行的 Office 365，包括資料的保留天數的相關資訊。此時，您必須以篩選要匯入或匯入所有的資料時的資料選項。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p168">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![您可以修剪 PST 檔案中的資料或將其所有匯入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. <span data-ttu-id="c06a1-437">執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c06a1-437">Do one of the following:</span></span>
    
    <span data-ttu-id="c06a1-p169">a.以修剪您匯入的資料，按一下 [**是，我要匯入之前加以篩選**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p169">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="c06a1-440">如需篩選 PST 檔案中的資料，並再啟動匯入工作的詳細逐步指示，請參閱[篩選資料匯入至 Office 365 的 PST 檔案時](filter-data-when-importing-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-440">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="c06a1-441">或</span><span class="sxs-lookup"><span data-stu-id="c06a1-441">Or</span></span>
    
    <span data-ttu-id="c06a1-p170">b.匯入 PST 檔案中的所有資料，請按一下 [**否，我要匯都入每個項目，** 然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p170">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
7. <span data-ttu-id="c06a1-444">如果您選擇要匯入的所有資料，請按一下 [啟動匯都入工作都**匯都入資料**]。</span><span class="sxs-lookup"><span data-stu-id="c06a1-444">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="c06a1-p171">匯入工作的狀態會顯示在 [**匯入**] 頁面。按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [**狀態**] 欄中的狀態資訊的 [**重新整理**。按一下匯入工作顯示狀態彈出式] 頁面上，以顯示每個要匯入的 PST 檔案的狀態資訊。如果匯入即完成 PST 檔案匯入至使用者信箱，會變更狀態為 [**已完成**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p171">The status of the import job is displayed on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported. When the import is complete and PST files have been imported to user mailboxes, the status will be changed to **Completed**.</span></span>

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="c06a1-449">檢視清單中的 PST 檔案上傳至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c06a1-449">View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="c06a1-p172">您可以安裝及使用 Microsoft Azure 儲存在檔案總管 （這是免費，開放原始碼工具） 來檢視我們要上載 （由 Microsoft 資料中心人員） 您組織的 Azure 儲存區 PST 檔案的清單。您可以執行此作業以驗證從您傳送給 Microsoft 的硬碟磁碟機的 PST 檔案已成功上傳至 Azure 儲存區。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p172">You can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that we're uploaded (by Microsoft data center personnel) to the Azure storage area for your organization. You can do this to verify that PST files from the hard drives that you sent to Microsoft were successfully uploaded to the Azure storage area.</span></span>
  
<span data-ttu-id="c06a1-452">Microsoft Azure 儲存在檔案總管處於預覽。</span><span class="sxs-lookup"><span data-stu-id="c06a1-452">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
 <span data-ttu-id="c06a1-p173">**重要：** 您無法使用 Azure 儲存在檔案總管上傳或修改 PST 檔案。將 PST 檔案匯入 Office 365 唯一支援的方法是使用 AzCopy。此外，您無法刪除您已上傳至 Azure blob 的 PST 檔案。如果您嘗試刪除 PST 檔案，將會收到有關不會察覺必要的權限的錯誤。請注意 Azure 儲存區域會自動刪除所有 PST 檔案。如果沒有匯入中的工作進度，則中的所有 PST 檔案 \* \* ingestiondata \* \* 容器會刪除 30 天後所建立的最新的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p173">**Important:** You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the \*\* ingestiondata \*\* container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="c06a1-459">若要安裝 Azure 儲存在檔案總管並連線至 Azure 儲存區：</span><span class="sxs-lookup"><span data-stu-id="c06a1-459">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="c06a1-p174">請執行下列步驟來取得您的組織共用存取簽章 (SAS) URL。此 URL 會在 Microsoft 雲端組織及 SAS 金鑰 Azure 儲存位置的網路 URL 的組合。此機碼提供存取您的組織 Azure 儲存位置的必要權限。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p174">Perform the following steps to get the Shared Access Signature (SAS) URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and an SAS key. This key provides you with the necessary permissions to access your organization's Azure storage location.</span></span>
    
1. <span data-ttu-id="c06a1-463">移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c06a1-463">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c06a1-464">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-464">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
3. <span data-ttu-id="c06a1-465">在 [**匯入**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增匯入工作**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-465">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="c06a1-p175">在 [匯入工作精靈] 中，輸入 PST 匯入工作名稱，並再按 [**下一步**。使用小寫字母、 數字、 連字號及底線。您無法使用大寫字母的文字或使用者名稱包含空格。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p175">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="c06a1-469">在 [**選擇匯入工作類型**] 頁面上按一下 [**上傳資料**並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-469">On the **Choose import job type** page, click **Upload your data** and then click **Next**.</span></span>
    
6. <span data-ttu-id="c06a1-470">在步驟 2 中，按一下 [**顯示網路上傳 SAS URL**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-470">In step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="c06a1-p176">顯示 URL 後，將其複製並將其儲存至檔案。請務必複製整個 URL。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p176">After the URL is displayed, copy it and save it to a file. Be sure to copy the entire URL.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c06a1-p177">請務必採取預防措施保護 SAS URL。這可以存取您的組織的 Azure 儲存區所使用的任何人。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p177">Be sure to take precautions to protect the SAS URL. This can be used by anyone to access the Azure storage area for your organization.</span></span> 
  
8. <span data-ttu-id="c06a1-475">按一下 [**取消**] 關閉匯入工作精靈]。</span><span class="sxs-lookup"><span data-stu-id="c06a1-475">Click **Cancel** to close the import job wizard.</span></span> 
    
2. <span data-ttu-id="c06a1-476">下載並安裝[Microsoft Azure 儲存檔案總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-476">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
3. <span data-ttu-id="c06a1-477">啟動 Microsoft Azure 儲存在檔案總管、 以滑鼠右鍵按一下左窗格中的**存放區的帳戶**和 [**連線至 Azure 存放區**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-477">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![以滑鼠右鍵按一下 [儲存的帳戶，然後按一下 [連線至 Azure 存放區](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. <span data-ttu-id="c06a1-479">按一下 [**使用存取共用簽章 (SAS) URI 或連線字串**再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-479">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
5. <span data-ttu-id="c06a1-480">按一下 [**使用 SAS URI**、 在步驟 1 中以底下**URI**] 方塊中貼上您取得 SAS URL 並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-480">Click **Use a SAS URI**, paste the SAS URL that you obtained in step 1 in to in the box under **URI**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c06a1-481">在 [**連線摘要**] 頁面上您可以檢閱連線資訊，並再按一下 [**連線**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-481">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="c06a1-p178">開啟**ingestiondata**容器;包含從您的硬碟的 PST 檔案。[**存放區的帳戶**位於**ingestiondata**容器\> **(SAS-Attached Services)** \> **Blob 容器**。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p178">The **ingestiondata** container is opened; it contains the PST files from your hard drive. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span>
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. <span data-ttu-id="c06a1-p179">使用 Microsoft Azure 儲存在檔案總管完成作業後，用滑鼠右鍵按一下**ingestiondata**，並再按一下 [**卸離**中斷與 Azure 儲存區的連線。否則，您會收到錯誤的下次您嘗試附加。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p179">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a><span data-ttu-id="c06a1-488">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="c06a1-488">Troubleshooting tips</span></span>
<span data-ttu-id="c06a1-489"><a name="troubleshootingtips"> </a></span><span class="sxs-lookup"><span data-stu-id="c06a1-489"></span></span>

- <span data-ttu-id="c06a1-p180">**匯入工作失敗 PST 匯入 CSV 對應檔案中的錯誤因會發生什麼事？** 如果因為對應檔案中的錯誤而失敗匯入工作，您不需要重新隨附硬碟向 Microsoft 才可建立新的匯入工作。那是因為 PST 檔案從您提交硬碟的磁碟機傳送匯入工作已上傳至您的組織的 Azure 儲存區。在此例中您剛才已修正錯誤 PST 匯入 CSV 對應檔，然後建立新的 「 網路上傳"匯入工作並送出修訂的 CSV 對應檔案。若要建立並啟動新的網路上傳匯入工作，請參閱[步驟 5： Office 365 中建立 PST 匯入工作](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步驟 6： 篩選資料並開始 PST 匯入工作](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主題中的 「 使用網路上傳至 PST 檔案匯入 Office 365。 」</span><span class="sxs-lookup"><span data-stu-id="c06a1-p180">**What happens if the import job fails because of errors in the PST Import CSV mapping file?** If an import job fails because of errors in the mapping file, you don't have to re-ship the hard drive to Microsoft in order to create a new import job. That's because the PST files from the hard drive that you submitted for the drive shipping import job have already been uploaded to the Azure storage area for your organization. In this case, you just have to fix the errors in the PST Import CSV mapping file, and then create a new "network upload" import job and submit the revised CSV mapping file. To create and start a new network upload import job, see [Step 5: Create a PST Import job in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) and [Step 6: Filter data and start the PST Import job](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) in the topic "Use network upload to import PST files to Office 365."</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c06a1-p181">若要協助您疑難排解 PST 匯入 CSV 對應檔案、 使用[Azure 儲存檔案總管](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具來檢視已上傳至 Azure 儲存區的 PST 檔案從您的硬碟**ingestiondata**容器中的資料夾結構。對應檔案錯誤通常是 FilePath 參數值，不正確所造成。此參數會指定在 Azure 的存放區] 區域中 PST 檔案的位置。請參閱[步驟 3](#step-3-create-the-pst-import-mapping-file)中的表格中 FilePath 參數的描述。如先前所述，在 Azure 的存放區] 區域中的 PST 檔案的位置所指定`/dstdir:`您在[步驟 2](#step-2-copy-the-pst-files-to-the-hard-drive)中執行 WAImportExport.exe 工具時的參數。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p181">To help you troubleshoot the PST Import CSV mapping file, use the [Azure Storage Explorer](#view-a-list-of-the-pst-files-uploaded-to-office-365) tool to view the folder structure in the **ingestiondata** container for the PST files from your hard drive that were uploaded to the Azure storage area. Mapping file errors are typically caused by an incorrect value in the FilePath parameter. This parameter specifies the location of a PST file in the Azure storage area. See the description of the FilePath parameter in table in [Step 3](#step-3-create-the-pst-import-mapping-file). As previously explained, the location of PST files in the Azure storage area was specified by the  `/dstdir:` parameter when you ran the WAImportExport.exe tool in [Step 2](#step-2-copy-the-pst-files-to-the-hard-drive).</span></span> 
  

  
## <a name="more-information"></a><span data-ttu-id="c06a1-500">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c06a1-500">More information</span></span>

- <span data-ttu-id="c06a1-p182">磁碟機傳送是有效的方式大量的封存訊息資料匯入 Office 365 善用可用來在組織的符合性功能。封存的資料匯入至使用者信箱後，您可以：</span><span class="sxs-lookup"><span data-stu-id="c06a1-p182">Drive shipping is an effective way to import large amounts of archival messaging data to Office 365 to take advantage of the compliance features that are available to your organization. After archival data is imported to user mailboxes, you can:</span></span>
    
  - <span data-ttu-id="c06a1-503">啟用[封存信箱](enable-archive-mailboxes.md)與[自動展開封存](enable-unlimited-archiving.md)的資料提供使用者其他信箱的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c06a1-503">Enable [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space for the data.</span></span> 
    
  - <span data-ttu-id="c06a1-504">將信箱資料的保留[訴訟暫止狀態](https://go.microsoft.com/fwlink/?linkid=856286)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-504">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data.</span></span> 
    
  - <span data-ttu-id="c06a1-505">使用 Microsoft [eDiscovery 工具](search-for-content.md)來搜尋資料。</span><span class="sxs-lookup"><span data-stu-id="c06a1-505">Use Microsoft [eDiscovery tools](search-for-content.md) to search the data.</span></span> 
    
  - <span data-ttu-id="c06a1-506">適用於[Office 365 的保留原則](retention-policies.md)控制之資料的保留期限及要採取的保留期間到期後的動作。</span><span class="sxs-lookup"><span data-stu-id="c06a1-506">Apply [Office 365 retention policies](retention-policies.md) to control how long the data is retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="c06a1-507">[Office 365 稽核記錄](search-the-audit-log-in-security-and-compliance.md)的搜尋與此資料相關的事件。</span><span class="sxs-lookup"><span data-stu-id="c06a1-507">Search the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for events related to this data.</span></span> 
    
  - <span data-ttu-id="c06a1-508">將資料匯入[非使用中信箱](create-and-manage-inactive-mailboxes.md)的規範目的封存資料。</span><span class="sxs-lookup"><span data-stu-id="c06a1-508">Import data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="c06a1-509">保護[資料遺失](data-loss-prevention-policies.md)您組織中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="c06a1-509">Protect your organization against [data loss](data-loss-prevention-policies.md) of sensitive information.</span></span> 
    
- <span data-ttu-id="c06a1-p183">以下是安全存放裝置帳戶金鑰和 BitLocker 加密金鑰的範例。此範例也會包含您要複製 PST 檔案到硬碟，所執行的 WAImportExport.exe 命令的語法。請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p183">Here's an example of the secure storage account key and a BitLocker encryption key. This example also contains the syntax for the WAImportExport.exe command that you run to copy PST files to a hard drive. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- <span data-ttu-id="c06a1-p184">如先前所述的 Office 365 匯入服務會開啟設定 （無限期的持續時間） 之後 PST 檔案匯入至信箱的保留。這表示*RentionHoldEnabled*屬性設為`True`以便將不會處理指派給信箱的保留原則。這可讓管理新匯入訊息來防止刪除或封存原則中刪除或封存舊郵件的信箱擁有者時間。以下是一些以管理此保留所能採取的步驟：</span><span class="sxs-lookup"><span data-stu-id="c06a1-p184">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="c06a1-p185">後段特定時間內，您就可以關閉保留功能來執行`Set-Mailbox -RetentionHoldEnabled $false`命令。指示，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/p/?LinkId=544749)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p185">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="c06a1-p186">您可以設定保留功能，讓一些日期未來關閉。您執行這項作業執行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假設今天的日期是 2016 年 7 月 1，而且您想關閉在 30 天保留功能，您會執行下列命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此案例中，您會保留*RentionHoldEnabled*屬性設為*True* 。如需詳細資訊，請參閱[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p186">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="c06a1-p187">您可以變更使較舊的項目匯入的將不會立即刪除或移至使用者的封存信箱指派給信箱的保留原則的設定。例如，您無法延長刪除或封存原則指派給信箱的保留時間。在此案例中，您會關閉信箱保留之後變更此保留原則的設定。如需詳細資訊，請參閱 ＜ [Set up Office 365 組織中信箱的封存及刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c06a1-p187">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
    

  

