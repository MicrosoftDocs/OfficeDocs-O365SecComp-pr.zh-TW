---
title: 將 PST 檔案匯入至 Office 365 的常見問題集
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '常見問題集的系統管理員如何使用 Office 365 匯入服務 organizaiton 的 PST 檔案匯入到 Office 365 信箱。 '
ms.openlocfilehash: 69767353a574336351b01fdc42a9c6117c5c31ed
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255431"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="25c6f-103">將 PST 檔案匯入至 Office 365 的常見問題集</span><span class="sxs-lookup"><span data-stu-id="25c6f-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="25c6f-104">**本文適用於系統管理員。您想要將 PST 檔案匯入您自己的信箱？請參閱[匯入電子郵件、 連絡人及行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="25c6f-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="25c6f-105">以下是一些常見問題大量匯入 PST 檔案複製到 Office 365 信箱來使用 Office 365 匯入服務。</span><span class="sxs-lookup"><span data-stu-id="25c6f-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="25c6f-106">如需如何匯入 PST 檔案的詳細資訊，請參閱 < <b0>Overview of 匯入 PST 檔案複製到 Office 365</b0>。</span><span class="sxs-lookup"><span data-stu-id="25c6f-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="25c6f-107">使用網路上傳將 PST 檔案匯入</span><span class="sxs-lookup"><span data-stu-id="25c6f-107">Using network upload to import PST files</span></span>

<span data-ttu-id="25c6f-108">如需逐步指示，請參閱 <<c0>使用網路上傳至 Office 365 的 PST 檔案匯入。</span><span class="sxs-lookup"><span data-stu-id="25c6f-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="25c6f-109">**查看的權限，才能在 Office 365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="25c6f-110">您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 將 PST 檔案匯入 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="25c6f-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="25c6f-111">根據預設，此角色不指派給任何角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="25c6f-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="25c6f-112">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="25c6f-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="25c6f-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="25c6f-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="25c6f-114">如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="25c6f-115">此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：</span><span class="sxs-lookup"><span data-stu-id="25c6f-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="25c6f-116">您必須獲指派 「 郵件收件者角色在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="25c6f-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="25c6f-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span><span class="sxs-lookup"><span data-stu-id="25c6f-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="25c6f-118">Or</span><span class="sxs-lookup"><span data-stu-id="25c6f-118">Or</span></span>
    
- <span data-ttu-id="25c6f-119">您必須是 Office 365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="25c6f-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="25c6f-120">請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。</span><span class="sxs-lookup"><span data-stu-id="25c6f-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="25c6f-121">若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。</span><span class="sxs-lookup"><span data-stu-id="25c6f-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="25c6f-122">**所在可用的網路上傳？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="25c6f-123">在美國、 加拿大、 巴西、 英國、 法國、 歐洲、 印度、 東亞、 東南亞 （日本）、 大韓民國和澳洲網路上傳是目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="25c6f-123">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="25c6f-124">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="25c6f-124">Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="25c6f-125">**What is the pricing for importing PST files by using network upload?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="25c6f-126">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="25c6f-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="25c6f-127">這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在 Microsoft 365 系統管理中心中完成的匯入工作的檔案清單中。</span><span class="sxs-lookup"><span data-stu-id="25c6f-127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="25c6f-128">雖然匯入工作仍可能會列在 [**匯入資料到 Office 365** ] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。</span><span class="sxs-lookup"><span data-stu-id="25c6f-128">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="25c6f-129">**What version of the PST file format is supported for importing to Office 365?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="25c6f-130">There are two versions of the PST file format: ANSI and Unicode.</span><span class="sxs-lookup"><span data-stu-id="25c6f-130">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="25c6f-131">We recommend importing files that use the Unicode PST file format.</span><span class="sxs-lookup"><span data-stu-id="25c6f-131">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="25c6f-132">不過，使用 ANSI PST 檔案格式，例如使用雙位元組字元的語言的檔案集 (DBCS)，也可匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="25c6f-132">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="25c6f-133">如需匯入 ANSI PST 檔案的詳細資訊，請參閱 <<c0>使用網路上傳至匯入組織的 PST 檔案複製到 Office 365中的步驟 4。</span><span class="sxs-lookup"><span data-stu-id="25c6f-133">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="25c6f-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span><span class="sxs-lookup"><span data-stu-id="25c6f-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="25c6f-135">**我將我的 PST 檔案上傳至 Azure 存放區域之後，多久他們保持在 Azure 中在被刪除之前？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="25c6f-136">當您使用網路上傳方法匯入 PST 檔案時，您將它們上載至名為**ingestiondata**Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="25c6f-136">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="25c6f-137">如果沒有匯入工作進行中**匯入**] 頁面上中有安全性 & 合規性中心），然後在 Azure 中的 [ **ingestiondata** ] 容器中的所有 PST 檔案會都刪除 30 天後安全性 & 中建立的最新的匯入工作合規性中心。</span><span class="sxs-lookup"><span data-stu-id="25c6f-137">If there are no import jobs in progress on the **Import** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="25c6f-138">這也表示您必須建立新的匯入工作安全性 & （所述步驟 5 中的網路上傳指示） 的合規性中心中的將 PST 檔案上傳至 Azure 的 30 天內。</span><span class="sxs-lookup"><span data-stu-id="25c6f-138">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="25c6f-139">這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在安全性 & 合規性中心中完成的匯入工作的檔案清單中。</span><span class="sxs-lookup"><span data-stu-id="25c6f-139">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="25c6f-140">雖然匯入工作仍可能會列在 [安全性 & 合規性中心的 [**匯入**] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。</span><span class="sxs-lookup"><span data-stu-id="25c6f-140">Although an import job might still be listed on the **Import** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="25c6f-141">**PST 檔案匯入至信箱需要多久的時間？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="25c6f-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization.</span><span class="sxs-lookup"><span data-stu-id="25c6f-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization.</span></span> <span data-ttu-id="25c6f-143">PST 檔案複製到 Azure 的儲存區之後，匯入 PST 檔案至 Office 365 信箱至少 24 GB 每日的速率。</span><span class="sxs-lookup"><span data-stu-id="25c6f-143">After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="25c6f-144">如果此工資率不符合您的需求，您可以考慮將電子郵件資料移轉到 Office 365 的其他方法。</span><span class="sxs-lookup"><span data-stu-id="25c6f-144">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="25c6f-145">如需詳細資訊，請參閱[將移轉至 Office 365 的多個電子郵件帳戶](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-145">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="25c6f-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span><span class="sxs-lookup"><span data-stu-id="25c6f-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="25c6f-147">同樣地，如果多個 PST 檔案匯入到同一個信箱，他們會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="25c6f-147">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="25c6f-148">**Is there a message size limit when importing PST files?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="25c6f-149">是。</span><span class="sxs-lookup"><span data-stu-id="25c6f-149">Yes.</span></span> <span data-ttu-id="25c6f-150">如果 PST 檔案包含大於 150 MB 的信箱項目，將匯入程序期間略過項目。</span><span class="sxs-lookup"><span data-stu-id="25c6f-150">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="25c6f-151">**是郵件內容，例如當郵件已傳送或接收的收件者及其他屬性，當 PST 檔案匯入到 Office 365 信箱時保留清單？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="25c6f-152">是。</span><span class="sxs-lookup"><span data-stu-id="25c6f-152">Yes.</span></span> <span data-ttu-id="25c6f-153">在匯入程序期間不變更原始郵件中繼資料。</span><span class="sxs-lookup"><span data-stu-id="25c6f-153">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="25c6f-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="25c6f-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="25c6f-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="25c6f-158">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="25c6f-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="25c6f-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="25c6f-160">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="25c6f-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="25c6f-161">**可以使用網路上傳將 PST 檔案匯入 Exchange Online 中公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="25c6f-162">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="25c6f-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="25c6f-163">使用磁碟機運送將 PST 檔案匯入</span><span class="sxs-lookup"><span data-stu-id="25c6f-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="25c6f-164">如需逐步指示，請參閱[使用磁碟機運送來匯入 PST 檔案複製到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="25c6f-165">**查看的權限，才能在 Office 365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="25c6f-166">您必須被指派信箱匯入匯出角色將 PST 檔案匯入 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="25c6f-166">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="25c6f-167">根據預設，此角色不指派給任何角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="25c6f-167">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="25c6f-168">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="25c6f-168">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="25c6f-169">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="25c6f-169">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="25c6f-170">如需詳細資訊，請參閱 「 將角色新增至角色群組 」 或 「 建立角色群組 > 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-170">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="25c6f-171">此外，若要建立匯入工作安全性 & 合規性中心中，下列其中一項必須為真：</span><span class="sxs-lookup"><span data-stu-id="25c6f-171">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="25c6f-172">您必須獲指派 「 郵件收件者角色在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="25c6f-172">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="25c6f-173">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span><span class="sxs-lookup"><span data-stu-id="25c6f-173">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="25c6f-174">Or</span><span class="sxs-lookup"><span data-stu-id="25c6f-174">Or</span></span>
    
- <span data-ttu-id="25c6f-175">您必須是 Office 365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="25c6f-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="25c6f-176">請考慮在 Exchange Online 中，特別適用於將 PST 檔案匯入至 Office 365 中建立新的角色群組。</span><span class="sxs-lookup"><span data-stu-id="25c6f-176">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="25c6f-177">若要匯入 PST 檔案所需的權限的最低層級，將 「 信箱匯入匯出 」 和 「 郵件收件者角色指派給新的角色群組，並再新增成員。</span><span class="sxs-lookup"><span data-stu-id="25c6f-177">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="25c6f-178">**其中磁碟機運送可用？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="25c6f-179">磁碟機運送位於目前無法使用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 東亞、 東南亞 （日本）、 大韓民國和澳洲。</span><span class="sxs-lookup"><span data-stu-id="25c6f-179">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="25c6f-180">Drive shipping will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="25c6f-180">Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="25c6f-181">**What commercial licensing agreements support drive shipping?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="25c6f-182">磁碟機運送將 PST 檔案匯入 Office 365 可透過 Microsoft Enterprise Agreement (EA)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-182">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="25c6f-183">磁碟機運送無法透過 Microsoft 產品和服務合約 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-183">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="25c6f-184">**使用磁碟機運送將 PST 檔案匯入 Office 365 價格是什麼？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="25c6f-185">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span><span class="sxs-lookup"><span data-stu-id="25c6f-185">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="25c6f-186">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span><span class="sxs-lookup"><span data-stu-id="25c6f-186">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="25c6f-187">You can work with a partner to pay the import fee.</span><span class="sxs-lookup"><span data-stu-id="25c6f-187">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="25c6f-188">如需尋找合作夥伴的詳細資訊，請參閱[尋找您的 Office 365 合作夥伴或轉銷商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-188">For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="25c6f-189">**What kind of hard drives are supported for drive shipping?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="25c6f-190">僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 英吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="25c6f-190">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="25c6f-191">You can use hard drives up to 10 TB.</span><span class="sxs-lookup"><span data-stu-id="25c6f-191">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="25c6f-192">對於匯入工作，將會處理只有第一個資料磁碟區在硬碟上。</span><span class="sxs-lookup"><span data-stu-id="25c6f-192">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="25c6f-193">The data volume must be formatted with NTFS.</span><span class="sxs-lookup"><span data-stu-id="25c6f-193">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="25c6f-194">當將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加 2.5 或 3.5 英吋 SATA II/III 連接器或外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 英吋 SATA II/III USB 介面卡，您可以附加。</span><span class="sxs-lookup"><span data-stu-id="25c6f-194">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="25c6f-195">Office 365 匯入服務不支援外部硬碟隨附內建的 USB 介面卡。</span><span class="sxs-lookup"><span data-stu-id="25c6f-195">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="25c6f-196">Additionally, the disk inside the casing of an external hard drive can't be used.</span><span class="sxs-lookup"><span data-stu-id="25c6f-196">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="25c6f-197">Please don't ship external hard drives.</span><span class="sxs-lookup"><span data-stu-id="25c6f-197">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="25c6f-198">**How many hard drives can I ship for a single import job?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="25c6f-199">You can ship a maximum of 10 hard drives for a single import job.</span><span class="sxs-lookup"><span data-stu-id="25c6f-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="25c6f-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="25c6f-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="25c6f-203">**我的硬碟送達 Microsoft 資料中心之後，多久需要若要將 「 我的 PST 檔案上傳至 Azure？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="25c6f-204">您的硬碟機接收的 Microsoft 資料中心之後，它需要 7 到 10 個工作天來將 PST 檔案上傳至您的組織的 Microsoft Azure 存放區域之間。</span><span class="sxs-lookup"><span data-stu-id="25c6f-204">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization.</span></span> <span data-ttu-id="25c6f-205">將上傳的 PST 檔案至名為**ingestiondata**的 Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="25c6f-205">The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="25c6f-206">**PST 檔案匯入至信箱需要多久的時間？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="25c6f-207">PST 檔案上傳至 Azure 存放區域後，Office 365 會分析 （以安全無虞的方式） 的 PST 檔案中的資料來識別的項目並包含在 PST 檔案中的不同郵件類型的保留期限。</span><span class="sxs-lookup"><span data-stu-id="25c6f-207">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="25c6f-208">完成這項分析時，您必須匯入 PST 檔案中的所有資料的選項，或設定篩選器，以控制哪些資料取得匯入。</span><span class="sxs-lookup"><span data-stu-id="25c6f-208">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="25c6f-209">啟動匯入工作之後，匯入 PST 檔案至 Office 365 信箱至少 24 GB 每日的速率。</span><span class="sxs-lookup"><span data-stu-id="25c6f-209">After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="25c6f-210">如果此工資率不符合您的需求，您可能會考慮其他方法來匯入至 Office 365 的電子郵件資料。</span><span class="sxs-lookup"><span data-stu-id="25c6f-210">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="25c6f-211">如需詳細資訊，請參閱[將移轉至 Office 365 的多個電子郵件帳戶](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="25c6f-211">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="25c6f-212">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span><span class="sxs-lookup"><span data-stu-id="25c6f-212">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="25c6f-213">同樣地，如果多個 PST 檔案匯入到同一個信箱，他們會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="25c6f-213">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="25c6f-214">**Microsoft 將我的 PST 檔案上傳至 Azure 之後，多久他們保持在 Azure 中在被刪除之前？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="25c6f-215">Azure 儲存體位置中所有的 PST 檔案，為您的組織 （在 blob 容器中名為**ingestiondata** ），會刪除最新的匯入工作在安全性 & 合規性中心的 [**匯入**] 頁面上建立後的 30 天。</span><span class="sxs-lookup"><span data-stu-id="25c6f-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="25c6f-216">這也表示 PST 檔案會從 Azure 存放區域刪除之後，它們不再顯示在安全性 & 合規性中心中完成的匯入工作的檔案清單中。</span><span class="sxs-lookup"><span data-stu-id="25c6f-216">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="25c6f-217">雖然匯入工作仍可能會列在 [安全性 & 合規性中心的 [**匯入**] 頁面上，檢視較舊的匯入工作的詳細資料時，可能會空白的 PST 檔案清單。</span><span class="sxs-lookup"><span data-stu-id="25c6f-217">Although an import job might still be listed on the **Import** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="25c6f-218">**What version of the PST file format is supported for importing to Office 365?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="25c6f-219">There are two versions of the PST file format: ANSI and Unicode.</span><span class="sxs-lookup"><span data-stu-id="25c6f-219">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="25c6f-220">We recommend importing files that use the Unicode PST file format.</span><span class="sxs-lookup"><span data-stu-id="25c6f-220">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="25c6f-221">不過，使用 ANSI PST 檔案格式，例如使用雙位元組字元的語言的檔案集 (DBCS)，也可匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="25c6f-221">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="25c6f-222">如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁碟機運送來匯入 PST 檔案複製到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="25c6f-222">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="25c6f-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span><span class="sxs-lookup"><span data-stu-id="25c6f-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="25c6f-224">**Is there a message size limit when importing PST files?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="25c6f-225">是。</span><span class="sxs-lookup"><span data-stu-id="25c6f-225">Yes.</span></span> <span data-ttu-id="25c6f-226">如果 PST 檔案包含大於 150 MB 的信箱項目，將匯入程序期間略過項目。</span><span class="sxs-lookup"><span data-stu-id="25c6f-226">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="25c6f-227">**是郵件內容，例如當郵件已傳送或接收的收件者及其他屬性，當 PST 檔案匯入到 Office 365 信箱時保留清單？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="25c6f-228">是。</span><span class="sxs-lookup"><span data-stu-id="25c6f-228">Yes.</span></span> <span data-ttu-id="25c6f-229">在匯入程序期間不變更原始郵件中繼資料</span><span class="sxs-lookup"><span data-stu-id="25c6f-229">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="25c6f-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="25c6f-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="25c6f-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="25c6f-234">Yes, this capability is now available.</span><span class="sxs-lookup"><span data-stu-id="25c6f-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="25c6f-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="25c6f-236">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="25c6f-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="25c6f-237">**可以使用磁碟機運送將 PST 檔案匯入 Exchange Online 中公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="25c6f-238">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="25c6f-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="25c6f-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="25c6f-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="25c6f-242">**Microsoft 可以切割我而不是傳送給我的硬碟？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="25c6f-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="25c6f-245">**寄回支援哪些快遞服務？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="25c6f-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="25c6f-248">**傳回的運費成本為何？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="25c6f-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="25c6f-252">**可以使用自訂 courier 傳送服務，例如 FedEx 自訂傳送，運送硬碟給 Microsoft 嗎？**</span><span class="sxs-lookup"><span data-stu-id="25c6f-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="25c6f-253">是。</span><span class="sxs-lookup"><span data-stu-id="25c6f-253">Yes.</span></span>
  
 <span data-ttu-id="25c6f-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span><span class="sxs-lookup"><span data-stu-id="25c6f-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="25c6f-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
