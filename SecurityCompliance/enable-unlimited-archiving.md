---
title: 啟用 Office 365-說明系統中沒有限制之封存
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 系統管理員： 了解如何啟用自動展開 Office 365，您的使用者與不受限制的存放區提供其 Exchange Online 信箱的封存。您可以啟用自動展開封存為整個組織或只是特定的使用者。
ms.openlocfilehash: 823e4ed0049e7a28a6c97c4045fb75987f43db5f
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782150"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="023f5-104">啟用 Office 365-說明系統中沒有限制之封存</span><span class="sxs-lookup"><span data-stu-id="023f5-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="023f5-p102">您可以使用 Office 365 中的 「 Exchange Online 的自動展開封存 」 功能以啟用封存信箱的無限制的儲存空間。自動展開封存開啟時，會自動新增額外儲存空間至使用者的封存信箱時加以式升級的儲存限制。結果是不受限制的信箱儲存容量。您可以開啟自動展開封存的組織中所有人或只是特定的使用者。如需關於自動展開封存，請參閱[Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="023f5-p102">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes. When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit. The result is unlimited mailbox storage capacity. You can turn on auto-expanding archiving for everyone in your organization or just for specific users. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="023f5-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="023f5-110">Before you begin</span></span>

- <span data-ttu-id="023f5-p103">您必須是 Office 365 組織或組織管理角色群組成員 Exchange Online 組織中的啟用整個組織或特定使用者自動展開封存的全域管理員。或者，您必須是已指派啟用自動展開封存特定使用者的郵件收件者角色的角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="023f5-p103">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users. Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="023f5-p104">使用者的封存信箱具有您可以啟用自動展開封存之前予以啟用。使用者必須具有啟用封存信箱的 Exchange Online 計劃 2 授權。如果使用者已指派 Exchange Online 計劃 1 授權，則您必須將它們指派不同 Exchange Online 封存授權啟用封存信箱。請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="023f5-p104">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving. A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox. If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox. See [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="023f5-p105">您也可以使用 PowerShell 啟用封存信箱。請參閱[的詳細資訊](#more-information)] 區段中的可用來啟用您組織中的所有使用者的封存信箱的 PowerShell 命令的範例。</span><span class="sxs-lookup"><span data-stu-id="023f5-p105">You can also use PowerShell to enable archive mailboxes. See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="023f5-p106">自動展開封存也支援共用的信箱。若要啟用共用信箱的封存，Exchange Online 計劃 2 授權或 Exchange Online 計劃 1 授權來搭配 Exchange Online 封存的授權，則需要。</span><span class="sxs-lookup"><span data-stu-id="023f5-p106">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="023f5-p107">您無法使用 Exchange 系統管理中心或安全性&amp;規範中心以啟用自動展開封存。您必須使用 Exchange Online PowerShell。若要連線至 Exchange Online 組織使用遠端 PowerShell，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="023f5-p107">You can't use the Exchange admin center or the Security &amp; Compliance Center to enable auto-expanding archiving. You have to use Exchange Online PowerShell. To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="023f5-124">啟用整個組織的自動展開封存</span><span class="sxs-lookup"><span data-stu-id="023f5-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="023f5-p108">您可以啟用自動展開整個組織的封存。您開啟之後，自動展開封存將會啟用現有使用者信箱以及所建立的新使用者信箱。當您建立新使用者信箱時，請務必讓自動展開的封存功能可讓新的使用者信箱的運作啟用使用者的主要封存信箱。</span><span class="sxs-lookup"><span data-stu-id="023f5-p108">You can enable auto-expanding archiving for your entire organization. After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created. When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="023f5-128">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="023f5-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="023f5-129">若要啟用整個組織的自動展開封存 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="023f5-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="023f5-130">啟用自動展開特定使用者的封存</span><span class="sxs-lookup"><span data-stu-id="023f5-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="023f5-p109">而非啟用自動展開您組織中每個使用者的封存，您可以僅啟用它對特定使用者。因為只有一些使用者可能會有非常大的封存儲存區需要您可能會這麼做。</span><span class="sxs-lookup"><span data-stu-id="023f5-p109">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users. You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="023f5-133">當您啟用自動展開特定使用者的封存時，也會進行下列兩種組態變更：</span><span class="sxs-lookup"><span data-stu-id="023f5-133">When you enable auto-expanding archiving for a specific user, the following two configurations changes are also made:</span></span>
  
- <span data-ttu-id="023f5-p110">使用者的主要封存信箱儲存配額會增加 10 GB （從 100 GB，以 110 GB)。封存警告配額也增加 10 GB （從 100 gb 的 90 GB)。</span><span class="sxs-lookup"><span data-stu-id="023f5-p110">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB). The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="023f5-p111">在使用者的主要信箱 [可復原的項目] 資料夾的存放區配額會增加 10 GB （也從 100 GB，以 110 GB)。可復原的項目警告配額也增加 10 GB （從 100 gb 的 90 GB)。這些變更適用於僅限中的信箱上保留或會指派給 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="023f5-p111">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB). The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB). These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="023f5-p112">此額外的空間新增至防止任何儲存空間可能發生的問題之前自動展開封存已佈建。請注意該額外儲存空間*不是*新增當您啟用整個組織前一節所述的自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="023f5-p112">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned. Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="023f5-141">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="023f5-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="023f5-p113">若要啟用自動展開封存特定使用者的 Exchange Online PowerShell 中執行下列命令。如先前所述，您可以開啟自動展開該使用者的封存之前必須啟用使用者的封存信箱 （主要封存）。</span><span class="sxs-lookup"><span data-stu-id="023f5-p113">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user. As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="023f5-p114">在 Exchange 混合部署中，您無法使用**Enable-mailbox AutoExpandingArchive**命令來啟用自動展開封存特定主要信箱位於內部部署使用者和其封存信箱不在雲端架構。若要啟用自動展開 Exchange 混合部署中的雲端式封存信箱的封存，您必須執行**Set-organizationconfig AutoExpandingArchive**命令在 Exchange Online PowerShell 來啟用自動展開的封存整個組織。如果使用者的主要和封存信箱都雲端，您可以啟用自動展開該特定使用者的封存使用**Enable-mailbox AutoExpandingArchive**命令。</span><span class="sxs-lookup"><span data-stu-id="023f5-p114">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based. To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization. If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="023f5-147">確認已啟用 [自動展開封存</span><span class="sxs-lookup"><span data-stu-id="023f5-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="023f5-148">若要確認您的組織會啟用自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="023f5-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="023f5-149">值為`True`表示已為組織啟用 [自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="023f5-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="023f5-150">若要確認自動展開封存為特定使用者啟用，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="023f5-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="023f5-151">值為`True`表示已為使用者啟用 [自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="023f5-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="023f5-152">您啟用自動展開封存之後請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="023f5-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="023f5-p115">如果您執行**Set-organizationconfig AutoExpandingArchive**命令，以啟用自動展開您的組織封存時，您不需要執行個別信箱**啟用信箱 AutoExpandingArchive** 。請注意執行**Set-organizationconfig**指令程式來啟用自動展開封存的組織不會變更使用者信箱上的*AutoExpandingArchiveEnabled*屬性`True`。</span><span class="sxs-lookup"><span data-stu-id="023f5-p115">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes. Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="023f5-p116">同樣地，您啟用自動展開封存時，不變更*ArchiveQuota*和*ArchiveWarningQuota*信箱屬性的值。事實上，當您啟用使用者信箱的自動展開封存和*AutoExpandingArchiveEnabled*屬性設為`True`、 *ArchiveQuota*和*ArchiveWarningQuota*屬性只會略過。以下是這些信箱屬性的範例之後自動展開封存啟用使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="023f5-p116">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving. In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored. Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![在您啟用自動展開封存之後會略過 ArchiveQuota 和 ArchiveWarningQuota 屬性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="023f5-159">其他資訊</span><span class="sxs-lookup"><span data-stu-id="023f5-159">More information</span></span>

- <span data-ttu-id="023f5-p117">您也可以使用 PowerShell 啟用封存信箱。例如，您可以執行下列命令在 Exchange Online PowerShell 啟用封存信箱不已啟用的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="023f5-p117">You can also use PowerShell to enable archive mailboxes. For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="023f5-p118">您開啟自動展開您的組織或特定使用者的封存之後，封存信箱 （包括可復原的項目] 資料夾） 達到 90 GB 時的封存信箱會轉換為自動展開封存。可能很多達 30 天的額外儲存空間來佈建。</span><span class="sxs-lookup"><span data-stu-id="023f5-p118">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB. It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="023f5-164">您開啟自動展開封存後，它不能已關閉。</span><span class="sxs-lookup"><span data-stu-id="023f5-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="023f5-p119">自動展開封存支援具有內部部署主要信箱的使用者的 Exchange 混合部署中的雲端式封存信箱。但是，自動展開封存啟用雲端式封存信箱後，您無法關閉-委員會回內部部署 Exchange 組織的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="023f5-p119">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox. However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span>
    
- <span data-ttu-id="023f5-167">使用者可以存取封存信箱中的其他儲存區中的項目使用的 Outlook 用戶端的清單，請參閱"Outlook 需求存取自動展開封存中的項目 」 一節中[的不受限制的概觀 （英文） 封存 Office 365 中](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span><span class="sxs-lookup"><span data-stu-id="023f5-167">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="023f5-p120">如先前所述，10 GB 新增至使用者的主要封存信箱儲存配額 （以及可復原的項目] 資料夾至信箱時保留） 當您執行的命令會**啟用信箱 AutoExpandingArchive** 。這會提供額外儲存空間之前的自動展開儲存空間佈建 （這可能需要最多 30 天）。當您執行**Set-organizationconfig AutoExpandingArchive**啟用自動展開您的組織中所有信箱的封存時未加上此額外儲存空間空格。如果您啟用自動展開封存整個組織中，但需要新增額外的 10 GB 的特定使用者的儲存空間，您可以**啟用信箱 AutoExpandingArchive**上執行命令的信箱。請注意您會收到錯誤預警已經啟用自動展開封存，但其他的儲存空間新增至信箱。</span><span class="sxs-lookup"><span data-stu-id="023f5-p120">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command. This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days). This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization. If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox. Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 
