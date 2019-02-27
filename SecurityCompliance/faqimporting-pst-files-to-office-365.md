---
title: 關於將 PST 檔案匯入 Office 365 常見問題集
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
description: '常見問題集管理員需使用 Office 365 匯入服務 organizaiton 的 PST 檔案匯入 Office 365 信箱。 '
ms.openlocfilehash: bef9c9e80f4f4c8261e9c44ba201a978937e2841
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296876"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="8c9b3-103">關於將 PST 檔案匯入 Office 365 常見問題集</span><span class="sxs-lookup"><span data-stu-id="8c9b3-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="8c9b3-104">**本文適用於系統管理員。您是否要 PST 檔案匯入您自己的信箱吗？請參閱[匯入電子郵件、 連絡人和行事曆從 Outlook.pst 檔案](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="8c9b3-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="8c9b3-p101">以下是一些常見問題大量匯入至 Office 365 信箱的 PST 檔案中使用 Office 365 匯入服務。如需如何匯入 PST 檔案的詳細資訊，請參閱 ＜ [Overview of 匯入至 Office 365 的 PST 檔案](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p101">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes. For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="8c9b3-107">若要匯入 PST 檔案使用網路上傳</span><span class="sxs-lookup"><span data-stu-id="8c9b3-107">Using network upload to import PST files</span></span>

<span data-ttu-id="8c9b3-108">如需逐步說明，請參閱[使用網路上傳至匯入至 Office 365 的 PST 檔案](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="8c9b3-109">**不需要在 Office 365 匯入服務中建立匯入工作哪些權限？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="8c9b3-p102">您必須指派匯入匯出信箱角色的 Exchange Online 至 PST 檔案匯入 Office 365 信箱。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。或者您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後將自己或其他使用者新增為成員。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p102">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="8c9b3-115">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="8c9b3-115">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="8c9b3-p103">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p103">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="8c9b3-118">或</span><span class="sxs-lookup"><span data-stu-id="8c9b3-118">Or</span></span>
    
- <span data-ttu-id="8c9b3-119">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="8c9b3-p104">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p104">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="8c9b3-122">**哪裡可用的網路上傳？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="8c9b3-p105">網路上傳位於目前可用美國、 加拿大、 巴西、 英國、 法國、 歐洲、 印度、 中文、 東南亞洲 （日本）、 共和國的韓國及澳洲。網路上傳會提供多個地區中推出。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p105">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="8c9b3-125">**什麼是匯入 PST 檔案使用網路上傳定價？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="8c9b3-126">使用網路上傳匯入 PST 檔案是自由。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="8c9b3-p106">這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示在清單中的 Office 365 系統管理中心中完成的匯入工作的檔案。匯入工作仍可能會列在 [**匯入至 Office 365 的資料**] 頁面上，雖然 PST 檔案的清單可能空白時檢視較舊的匯入工作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p106">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="8c9b3-129">**將匯入 Office 365 支援 PST 檔案格式的版本？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="8c9b3-p107">有兩個版本的 PST 檔案格式： ANSI 與 Unicode。建議您匯入使用 Unicode PST 檔案格式的檔案。不過，使用 ANSI PST 檔案格式，例如語言之使用雙位元組字元的檔案 (DBCS)，也可匯入 Office 365。如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用網路上傳至匯入至 Office 365 組織的 PST 檔案](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步驟 4。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p107">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="8c9b3-134">此外，從 Outlook 2007 或更新版本的 PST 檔案可以匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="8c9b3-135">**我將 「 我的 PST 檔案上傳至 Azure 儲存區之後，時間是他們保持在 Azure 中刪除之前？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="8c9b3-p108">當您使用的網路上傳方法匯入 PST 檔案時，您將其上傳至名為**ingestiondata**Azure blob 容器。如果沒有匯入工作進行中在 [**匯入**] 頁面中有安全性&amp;規範中心)，然後在 Azure **ingestiondata**容器中的所有 PST 檔案會都刪除 30 天後安全性&amp;規範中心。這也表示您必須建立新的匯入工作安全性&amp;規範中心 （所述之步驟 5 中的網路上傳指示） 內 30 天的上傳 PST 檔案至 Azure。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p108">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="8c9b3-p109">這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示清單中的安全性完成的匯入工作的檔案&amp;規範中心。雖然匯入工作仍可能會列在 [**匯入**] 頁面上的 [安全性]&amp;規範中心 PST 檔案的清單可能會是空的較舊的匯入工作詳細資料檢視時。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p109">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="8c9b3-141">**PST 檔案匯入至信箱需要多久的時間？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="8c9b3-p110">它取決於您的網路容量，但它通常採用的每個 tb 的資料要上傳至您的組織的 Azure 儲存區的數個小時。PST 檔案複製到 Azure 儲存區之後，會 PST 檔案匯入到 Office 365 信箱至少 24 GB 的每日的速率。如果此速率不符合您的需求，您可能會考慮將電子郵件資料移轉至 Office 365 的其他方法。如需詳細資訊，請參閱 ＜[移轉至 Office 365 的多個電子郵件帳戶的方式](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p110">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="8c9b3-p111">如果不同的 PST 檔案匯入至不同的目標信箱、 匯入程序會發生平行;換句話說，每 PST/信箱對匯入同時。同樣地，如果多個 PST 檔案匯入至相同信箱，這些會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p111">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="8c9b3-148">**是否有將郵件大小限制時匯入 PST 檔案？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="8c9b3-p112">[是]。如果 PST 檔案包含大於 150 MB 的信箱項目，則會略過之項目的匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p112">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="8c9b3-151">**是郵件內容，例如郵件已傳送或接收的收件者和其他屬性，PST 檔案匯入至 Office 365 信箱時保留清單？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="8c9b3-p113">[是]。原始郵件中繼資料不匯入程序期間變更。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p113">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="8c9b3-154">**是否有限制 PST 檔案所要匯入信箱資料夾階層中的層級數目吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="8c9b3-p114">[是]。您不能有個巢狀資料夾 300 或多個層級的 PST 檔案匯入。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="8c9b3-157">**可以使用網路上傳至 PST 檔案匯入 Office 365 中的非使用中信箱吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="8c9b3-158">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8c9b3-159">**可以使用網路上傳至 PST 檔案匯入線上封存信箱在 Exchange 混合部署吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="8c9b3-160">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8c9b3-161">**可以使用網路上傳至 PST 檔案匯入 Exchange Online 中公用資料夾嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="8c9b3-162">否，您不能 PST 檔案匯入的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="8c9b3-163">若要匯入 PST 檔案中使用的磁碟機傳送</span><span class="sxs-lookup"><span data-stu-id="8c9b3-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="8c9b3-164">如需逐步說明，請參閱[使用傳送至匯入至 Office 365 的 PST 檔案的磁碟機](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="8c9b3-165">**不需要在 Office 365 匯入服務中建立匯入工作哪些權限？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="8c9b3-p115">您必須指派信箱匯入匯出至 PST 檔案匯入 Office 365 信箱角色。根據預設，此角色不被指派給任何角色群組在 Exchange Online。您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。或者您可以建立新的角色群組、 指派信箱匯入 / 匯出 」 角色，然後將自己或其他使用者新增為成員。如需詳細資訊，請參閱"新增至角色群組角色"或"建立角色群組 」 小節中[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p115">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="8c9b3-171">此外，若要建立匯入工作 Office 365 安全性&amp;規範中心其中一項必須成立：</span><span class="sxs-lookup"><span data-stu-id="8c9b3-171">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="8c9b3-p116">您必須具有 「 郵件收件者 」 角色在 Exchange Online。根據預設，此角色指派給 「 組織管理與收件者管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p116">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="8c9b3-174">或</span><span class="sxs-lookup"><span data-stu-id="8c9b3-174">Or</span></span>
    
- <span data-ttu-id="8c9b3-175">您必須是 Office 365 組織中的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="8c9b3-p117">請考慮在 Exchange Online 中的特別適合將 PST 檔案匯入 Office 365 中建立新的角色群組。匯入 PST 檔案、 將 [匯出信箱匯入] 與 [郵件收件者角色指派給新角色群組，並再將成員新增所需的權限最低層級。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p117">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="8c9b3-178">**其中磁碟機傳送可用？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="8c9b3-p118">磁碟機傳送位於目前可用美國、 加拿大、 巴西、 英國、 歐洲、 印度、 中文、 東南亞洲 （日本）、 共和國的韓國及澳洲。磁碟機傳送會提供多個地區中推出。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p118">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="8c9b3-181">**何種商業的授權合約支援的磁碟機傳送？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="8c9b3-p119">使用透過 Microsoft Enterprise Agreement (EA) 傳送至 PST 檔案匯入 Office 365 的磁碟機。磁碟機傳送無法透過 Microsoft 產品和服務合約 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p119">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="8c9b3-184">**什麼是使用傳送至 PST 檔案匯入 Office 365 的磁碟機的定價？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="8c9b3-p120">若要使用的磁碟機傳送至 PST 檔案匯入 Office 365 信箱成本是 $2 USD 每 GB 的資料。例如，如果您隨附包含 1000 GB (1 TB) 的 PST 檔案的硬碟，成本是 $2000 USD。您可以使用合作夥伴支付匯入費用。如需尋找協力廠商的資訊，請參閱[尋找 Office 365 協力廠商或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p120">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="8c9b3-189">**支援何種類型的硬碟的磁碟機傳送？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="8c9b3-p121">僅限 2.5 英吋固態磁碟機 (Ssd) 或 2.5 或 3.5 吋 SATA II/III 內部硬碟所支援的 Office 365 匯入服務搭配使用。您可以使用硬碟最多 10 TB。匯入的工作會處理在硬碟上的只有第一個資料量。資料磁碟區必須以 NTFS 格式化。時將資料複製到硬碟，您可以將其使用 2.5 英吋 SSD 直接附加或 2.5 或 3.5 英吋 SATA II/III 連接器或您可以附加外部使用外部 2.5 英吋 SSD 或 2.5 或 3.5 吋 SATA II/III USB 介面卡。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p121">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c9b3-p122">內建的 USB 介面卡隨附的外部硬碟不支援的 Office 365 匯入服務。此外，不能使用的磁碟內外部的硬碟磁碟機的大小寫。請不要隨附外部硬碟。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p122">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="8c9b3-198">**單一匯入工作可以隨附多少硬碟？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="8c9b3-199">您可以隨附最多 10 個硬碟的單一匯入工作。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="8c9b3-200">**我隨附我硬碟的磁碟機之後，沒有多少時間要取得之 Microsoft 資料中心？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="8c9b3-p123">取決於一些事項，例如 Microsoft 資料中心在接近和用以隨附您的硬碟 （例如下, 一步] 時差傳遞、 兩天傳遞或地上傳遞） 何種傳送選項。您可以使用大部分 shippers 追蹤數追蹤您傳送的狀態。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="8c9b3-203">**「 我的硬碟抵達 Microsoft 資料中心之後，沒有多少時間來我 PST 檔案上傳至 Azure？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="8c9b3-p124">您的硬碟接收於 Microsoft 資料中心之後，則需要 7 到 10 商務數天才能 PST 檔案上傳至您的組織的 Microsoft Azure 儲存區之間。PST 檔案將上傳至名為**ingestiondata**Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p124">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="8c9b3-206">**PST 檔案匯入至信箱需要多久的時間？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="8c9b3-p125">PST 檔案上傳至 Azure 儲存區之後，Office 365 以方式分析 PST 檔案中的資料 （安全且安全的方式） 來識別項目及 PST 檔案中包含的不同郵件類型的保留時間下限。完成這項分析時，您必須匯入 PST 檔案中的所有資料的選項或設定篩選器的控制哪些資料取得匯入。當您啟動匯入工作後，PST 檔案匯入至少 24 GB 每天率的 Office 365 信箱。如果此速率不符合您的需求，您可能會考慮將電子郵件資料匯入 Office 365 的其他方法。如需詳細資訊，請參閱 ＜[移轉至 Office 365 的多個電子郵件帳戶的方式](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p125">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="8c9b3-p126">如果不同的 PST 檔案匯入至不同的目標信箱、 匯入程序會發生平行;換句話說，每 PST/信箱對匯入同時。同樣地，如果多個 PST 檔案匯入至相同信箱，這些會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p126">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="8c9b3-214">**Microsoft 將 「 我的 PST 檔案上傳至 Azure 之後，時間是他們保持在 Azure 中刪除之前？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="8c9b3-215">所有 PST 檔案在 Azure 的儲存位置 （以名為**ingestiondata** blob container)，組織會都刪除在 [安全性] 的 [**匯入**] 頁面上建立的最新的匯入工作後的 30 天&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="8c9b3-p127">這也表示從 Azure 的存放區刪除 PST 檔案之後，他們正在不再顯示清單中的安全性完成的匯入工作的檔案&amp;規範中心。雖然匯入工作仍可能會列在 [**匯入**] 頁面上的 [安全性]&amp;規範中心 PST 檔案的清單可能會是空的較舊的匯入工作詳細資料檢視時。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="8c9b3-218">**將匯入 Office 365 支援 PST 檔案格式的版本？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="8c9b3-p128">有兩個版本的 PST 檔案格式： ANSI 與 Unicode。建議您匯入使用 Unicode PST 檔案格式的檔案。不過，使用 ANSI PST 檔案格式，例如語言之使用雙位元組字元的檔案 (DBCS)，也可匯入 Office 365。如需匯入 ANSI PST 檔案的詳細資訊，請參閱[使用傳送至匯入至 Office 365 的 PST 檔案的磁碟機](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p128">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="8c9b3-223">此外，從 Outlook 2007 或更新版本的 PST 檔案可以匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="8c9b3-224">**是否有將郵件大小限制時匯入 PST 檔案？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="8c9b3-p129">[是]。如果 PST 檔案包含大於 150 MB 的信箱項目，則會略過之項目的匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="8c9b3-227">**是郵件內容，例如郵件已傳送或接收的收件者和其他屬性，PST 檔案匯入至 Office 365 信箱時保留清單？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="8c9b3-p130">[是]。匯入程序期間未變更的原始郵件中繼資料</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p130">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="8c9b3-230">**是否有限制 PST 檔案所要匯入信箱資料夾階層中的層級數目吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="8c9b3-p131">[是]。您不能有個巢狀資料夾 300 或多個層級的 PST 檔案匯入。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="8c9b3-233">**可以使用的磁碟機傳送至 PST 檔案匯入 Office 365 中的非使用中信箱吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="8c9b3-234">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8c9b3-235">**可以使用的磁碟機傳送至 PST 檔案匯入線上封存信箱在 Exchange 混合部署吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="8c9b3-236">是，這項功能現在使用。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8c9b3-237">**可以使用的磁碟機傳送至 PST 檔案匯入 Exchange Online 中公用資料夾嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="8c9b3-238">否，您不能 PST 檔案匯入的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="8c9b3-239">**可以 Microsoft 清除我硬碟之前所隨附給我, 吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="8c9b3-p132">否，Microsoft 無法抹除之前傳送其返回客戶的硬碟。硬碟會以相同交易時收到 microsoft 的狀態傳回給您。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="8c9b3-242">**Microsoft 切割我硬碟，而非傳送給我可以吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="8c9b3-p133">否，Microsoft 無法終結您的硬碟。硬碟會以相同交易時收到 microsoft 的狀態傳回給您。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="8c9b3-245">**傳回傳送支援何種 courier 服務？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="8c9b3-p134">如果您是在美國和歐洲客戶，Microsoft 使用 FedEx 傳回您的硬碟。所有其他區域 （英文）、 Microsoft 使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="8c9b3-248">**傳回的運費成本為何？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="8c9b3-p135">會傳回運費成本而異，您接近 Microsoft 資料中心的傳送至您的硬碟。Microsoft 將 bill 您 FedEx 或 DHL 帳戶來傳回您的硬碟。傳回傳送的成本是您的責任。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="8c9b3-252">**可以使用自訂 courier 傳送服務，例如 FedEx 自訂傳送，以隨附我硬碟向 Microsoft 吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="8c9b3-253">是。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-253">Yes.</span></span>
  
 <span data-ttu-id="8c9b3-254">**如果我有隨附我硬碟至另一個國家/地區、 是否有我需要執行的任何項目吗？**</span><span class="sxs-lookup"><span data-stu-id="8c9b3-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="8c9b3-p136">您以 Microsoft 隨附的硬碟機可能必須跨多語系的框線。如果是這樣，則已負責確保該硬碟及它所包含的資料會匯入及/或匯出符合適用法。之前傳送的硬碟，請確認該磁碟機和資料可以法律上幫助將傳送到指定的 Microsoft 資料中心位顧問。這有助於確保它達到 Microsoft 及時。</span><span class="sxs-lookup"><span data-stu-id="8c9b3-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
