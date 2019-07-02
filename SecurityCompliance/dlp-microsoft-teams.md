---
title: 資料遺失防護和 Microsoft 小組
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/01/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 您現在可以將 DLP 原則套用至 Microsoft 團隊聊天和管道。 請閱讀本文以深入瞭解其運作方式。
ms.openlocfilehash: 3792fd6919749510ea20d4ff84b0249b16165a9f
ms.sourcegitcommit: cc1b0281fa594cbb7c09f3e419df21aec9557831
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417395"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="bcf60-104">資料遺失防護和 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="bcf60-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="bcf60-105">最近將資料遺失防護功能新增至 Microsoft 小組的 Office 365 E5 和 Office 365 高級規範。</span><span class="sxs-lookup"><span data-stu-id="bcf60-105">Data loss prevention capabilities were recently added to Microsoft Teams in Office 365 E5 and Office 365 Advanced Compliance.</span></span> <span data-ttu-id="bcf60-106">若要深入瞭解功能可用性, 請參閱[office 365 服務說明: office 365 安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="bcf60-106">To learn more about feature availability, see [Office 365 Service Descriptions: Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="bcf60-107">適用于 Microsoft 小組的 DLP 概述</span><span class="sxs-lookup"><span data-stu-id="bcf60-107">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="bcf60-108">最近,[資料遺失防護](data-loss-prevention-policies.md)(DLP) 功能已擴充為包含 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="bcf60-108">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams.</span></span> <span data-ttu-id="bcf60-109">如果您的組織有 DLP, 您現在可以定義原則, 以防止人員在 Microsoft 小組通道或聊天會話中共用敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf60-109">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="bcf60-110">以下是此保護運作方式的一些範例:</span><span class="sxs-lookup"><span data-stu-id="bcf60-110">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="bcf60-111">**範例 1: 保護郵件中的敏感資訊**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-111">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="bcf60-112">假設有人嘗試與客人 (外部使用者) 共用小組聊天或管道中的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf60-112">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="bcf60-113">如果您已定義 DLP 原則以防止發生這種情況, 則會刪除具有傳送給外部使用者之敏感資訊的郵件。</span><span class="sxs-lookup"><span data-stu-id="bcf60-113">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="bcf60-114">這會根據 DLP 原則的設定方式, 自動在幾秒內進行。</span><span class="sxs-lookup"><span data-stu-id="bcf60-114">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcf60-115">當使用者與在小組和管道中擁有[來賓存取](https://docs.microsoft.com/MicrosoftTeams/guest-access)權的使用者共用, 以及在會議和交談會話中有[外部存取](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)權的使用者時, DLP for Microsoft 團隊會封鎖敏感內容。</span><span class="sxs-lookup"><span data-stu-id="bcf60-115">DLP for Microsoft Teams blocks sensitive content when shared with users who have [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels, and with users who have [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <span data-ttu-id="bcf60-116">如果您[與商務用 Skype 搭配使用 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), 請記住, DLP for 團隊不會封鎖互通性或同盟交談會話中的郵件。</span><span class="sxs-lookup"><span data-stu-id="bcf60-116">If you are using [Microsoft Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), keep in mind that DLP for Teams does not block messages in interop or federated chat sessions.</span></span>

- <span data-ttu-id="bcf60-117">**範例 2: 保護檔中的敏感資訊**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-117">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="bcf60-118">假設有人嘗試與 Microsoft 小組頻道或聊天中的客人共用檔, 而且檔包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf60-118">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="bcf60-119">如果您已定義 DLP 原則以防止發生這種情況, 則不會對這些使用者開啟檔。</span><span class="sxs-lookup"><span data-stu-id="bcf60-119">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="bcf60-120">請注意, 在這種情況下, 您的 DLP 原則必須包含 SharePoint 和 OneDrive, 才可進行保護。</span><span class="sxs-lookup"><span data-stu-id="bcf60-120">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="bcf60-121">(這是在 Microsoft 團隊中顯示的 DLP for SharePoint 的範例。)</span><span class="sxs-lookup"><span data-stu-id="bcf60-121">(This is an example of DLP for SharePoint that shows up in Microsoft Teams.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="bcf60-122">原則提示有助於教育使用者</span><span class="sxs-lookup"><span data-stu-id="bcf60-122">Policy tips help educate users</span></span>

<span data-ttu-id="bcf60-123">與 DLP 在[Exchange、outlook 和 outlook 網頁](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)版、 [SharePoint 和商務用 OneDrive 網站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)及[Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)的運作方式類似, 當動作與 DLP 原則衝突時, 就會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="bcf60-123">Similar to how DLP works in [Exchange, Outlook, and Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint and OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="bcf60-124">以下是原則提示的範例:</span><span class="sxs-lookup"><span data-stu-id="bcf60-124">Here's an example of a policy tip:</span></span>

![小組中的封鎖訊息通知](media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="bcf60-126">在這種情況下, 寄件者嘗試在 Microsoft 小組通道中共用社交安全性號碼。</span><span class="sxs-lookup"><span data-stu-id="bcf60-126">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="bcf60-127">**我可以做什麼？** link 開啟對話方塊, 為寄件者提供解決問題的選項。</span><span class="sxs-lookup"><span data-stu-id="bcf60-127">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="bcf60-128">請注意, 在此情況下, 寄件者可以選擇覆寫原則, 或通知系統管理員檢查並解決。</span><span class="sxs-lookup"><span data-stu-id="bcf60-128">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![解決被封鎖郵件的選項](media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="bcf60-130">在您的組織中, 您可以選擇是否允許使用者覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="bcf60-130">In your organization, you can choose whether to allow users to override a DLP policy, or not.</span></span> <span data-ttu-id="bcf60-131">而且, 當您設定 DLP 原則時, 您可以使用預設原則提示, 或為您的組織[自訂原則提示](#to-customize-policy-tips)。</span><span class="sxs-lookup"><span data-stu-id="bcf60-131">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span> 

<span data-ttu-id="bcf60-132">回到我們的範例中, 寄件者在小組頻道中共用社交安全性號碼, 以下是收件者看到的內容:</span><span class="sxs-lookup"><span data-stu-id="bcf60-132">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![郵件被封鎖](media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="bcf60-134">[**這是什麼？** ] 連結會開啟有關 DLP 原則的[文章](data-loss-prevention-policies.md), 協助說明郵件被封鎖的原因。</span><span class="sxs-lookup"><span data-stu-id="bcf60-134">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="bcf60-135">自訂原則提示</span><span class="sxs-lookup"><span data-stu-id="bcf60-135">To customize policy tips</span></span>

<span data-ttu-id="bcf60-136">若要執行此工作, 您必須被指派有權編輯 DLP 原則的角色。</span><span class="sxs-lookup"><span data-stu-id="bcf60-136">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="bcf60-137">若要深入瞭解, 請參閱[許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="bcf60-137">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="bcf60-138">移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="bcf60-138">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="bcf60-139">選擇 [**資料遺失防護** > **原則**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-139">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="bcf60-140">選取原則, 然後按一下 [**原則設定**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-140">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="bcf60-141">請建立新的規則, 或編輯原則的現有規則。</span><span class="sxs-lookup"><span data-stu-id="bcf60-141">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![編輯原則的規則](media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="bcf60-143">在 [**使用者通知**] 索引標籤上, 選取 **[自訂電子郵件文字**] 和/或 **[自訂原則提示文字**選項]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-143">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="bcf60-144">![自訂使用者通知和原則提示](media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-144">![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="bcf60-145">指定您要用於電子郵件通知和/或原則提示的文字, 然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-145">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span> 

7. <span data-ttu-id="bcf60-146">在 [**原則設定**] 索引標籤上, 選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-146">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="bcf60-147">允許大約一小時的時間讓您的變更透過您的資料中心來運作, 並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bcf60-147">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="bcf60-148">將 Microsoft 團隊新增為現有 DLP 原則的位置</span><span class="sxs-lookup"><span data-stu-id="bcf60-148">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="bcf60-149">若要執行此工作, 您必須被指派有權編輯 DLP 原則的角色。</span><span class="sxs-lookup"><span data-stu-id="bcf60-149">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="bcf60-150">若要深入瞭解, 請參閱[許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="bcf60-150">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="bcf60-151">移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="bcf60-151">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="bcf60-152">選擇 [**資料遺失防護** > **原則**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-152">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="bcf60-153">選取原則, 並查看 [**位置**] 底下的值。</span><span class="sxs-lookup"><span data-stu-id="bcf60-153">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="bcf60-154">如果您看到**小組聊天和通道訊息**, 就是所有設定。</span><span class="sxs-lookup"><span data-stu-id="bcf60-154">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="bcf60-155">如果您沒有, 請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-155">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="bcf60-156">![現有原則的位置](media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-156">![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="bcf60-157">在 [**狀態**] 欄中, 針對**小組聊天和通道訊息**開啟原則。</span><span class="sxs-lookup"><span data-stu-id="bcf60-157">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="bcf60-158">![適用于團隊聊天和管道的 DLP](media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-158">![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="bcf60-159">保留所有帳戶的預設設定, 或指定要包含或排除的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bcf60-159">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="bcf60-160">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcf60-160">Click **Save**.</span></span>

<span data-ttu-id="bcf60-161">允許大約一小時的時間讓您的變更透過您的資料中心來運作, 並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bcf60-161">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="bcf60-162">為 Microsoft 團隊定義新的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bcf60-162">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="bcf60-163">若要執行此工作, 您必須被指派有權編輯 DLP 原則的角色。</span><span class="sxs-lookup"><span data-stu-id="bcf60-163">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="bcf60-164">若要深入瞭解, 請參閱[許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="bcf60-164">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="bcf60-165">移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="bcf60-165">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="bcf60-166">選擇 [**資料遺失防護** > **原則** > **+ 建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-166">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span> 

3. <span data-ttu-id="bcf60-167">選擇[範本](data-loss-prevention-policies.md#dlp-policy-templates), 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-167">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="bcf60-168">在我們的範例中, 我們選擇美國個人身分識別資訊資料範本。</span><span class="sxs-lookup"><span data-stu-id="bcf60-168">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="bcf60-169">![DLP 原則的隱私權範本](media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-169">![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="bcf60-170">在 [**命名您的原則**] 索引標籤上, 指定原則的名稱和描述, 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-170">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span> 

5. <span data-ttu-id="bcf60-171">在 [**選擇位置**] 索引標籤上, 保留 [所有位置] 的預設設定, 或選取 [**讓我選擇特定位置**], 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-171">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="bcf60-172">如果您選擇選擇 [特定位置], 請選取 DLP 原則的位置, 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-172">If you opted to choose specific locations, select the locations for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="bcf60-173">![DLP 原則位置](media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-173">![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="bcf60-174">如果您想要確定包含機密資訊的檔未適當地共用, 請確定**SharePoint 網站**和**OneDrive 帳戶**已開啟, 以及**小組聊天和通道訊息**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-174">If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>
<br/>

6. <span data-ttu-id="bcf60-175">在 [**原則設定**] 索引標籤的 [**自訂您要保護的內容類型**] 下, 保留預設的簡單設定, 或選擇 [**使用高級設定**], 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-175">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="bcf60-176">如果您選擇 [高級設定], 您可以建立或編輯原則的規則。</span><span class="sxs-lookup"><span data-stu-id="bcf60-176">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="bcf60-177">(若要取得這一點的說明, 請參閱[簡易設定與高級設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。)</span><span class="sxs-lookup"><span data-stu-id="bcf60-177">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="bcf60-178">在 [**原則設定**] 索引標籤的 [如果偵測到**敏感資訊, 您要執行什麼？**] 下, 複查設定。</span><span class="sxs-lookup"><span data-stu-id="bcf60-178">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="bcf60-179">(您可以在這裡選擇保留預設[原則提示和電子郵件通知](use-notifications-and-policy-tips.md), 或加以自訂)。</span><span class="sxs-lookup"><span data-stu-id="bcf60-179">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="bcf60-180">![使用秘訣和通知的 DLP 原則設定](media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-180">![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="bcf60-181">當您完成審閱或編輯設定時, 請選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-181">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="bcf60-182">在 [**原則設定**] 索引標籤的 [**您想要先開啟原則或測試內容嗎？**] 下, 選擇是否要開啟原則、[先測試](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)或保留 [關閉], 然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bcf60-182">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="bcf60-183">![指定是否要開啟原則](media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="bcf60-183">![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="bcf60-184">在 [**檢查您的設定**] 索引標籤上, 檢查新原則的設定。</span><span class="sxs-lookup"><span data-stu-id="bcf60-184">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="bcf60-185">選擇 [**編輯**] 進行變更。</span><span class="sxs-lookup"><span data-stu-id="bcf60-185">Choose **Edit** to make changes.</span></span> <span data-ttu-id="bcf60-186">完成後, 請選擇 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="bcf60-186">When you're finished, choose **Create**.</span></span> 

<span data-ttu-id="bcf60-187">針對您的新原則, 允許大約一小時的時間, 透過您的資料中心來進行, 並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bcf60-187">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bcf60-188">相關文章</span><span class="sxs-lookup"><span data-stu-id="bcf60-188">Related articles</span></span>

[<span data-ttu-id="bcf60-189">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="bcf60-189">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="bcf60-190">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="bcf60-190">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
