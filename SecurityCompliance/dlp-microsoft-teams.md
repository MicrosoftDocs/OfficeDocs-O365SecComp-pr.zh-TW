---
title: 資料外洩防護和 Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/26/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 您現在可以將 DLP 原則套用至 Microsoft 小組聊天和通道。 閱讀本篇文章以深入了解其運作方式。
ms.openlocfilehash: 712729972942d98afb5b3898ad357114ce1a6bae
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33367218"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="767e0-104">資料外洩防護和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="767e0-104">Data loss prevention and Microsoft Teams</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="767e0-105">DLP 對於 Microsoft Teams 概觀</span><span class="sxs-lookup"><span data-stu-id="767e0-105">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="767e0-106">最近，已擴充[資料外洩防護](data-loss-prevention-policies.md)(DLP) 功能，以包括 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="767e0-106">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams.</span></span> <span data-ttu-id="767e0-107">如果您的組織有 DLP，現在您可以定義共用 Microsoft Teams 通道或聊天室工作階段中的敏感資訊時，防止人員的原則。</span><span class="sxs-lookup"><span data-stu-id="767e0-107">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="767e0-108">以下是此保護的運作方式的一些範例：</span><span class="sxs-lookup"><span data-stu-id="767e0-108">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="767e0-109">**範例 1： 保護郵件中的敏感資訊**。</span><span class="sxs-lookup"><span data-stu-id="767e0-109">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="767e0-110">假設有人嘗試來賓 （外部使用者） 與共用小組聊天或通道中的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="767e0-110">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="767e0-111">如果您有 DLP 原則定義要避免這種情況時，會刪除具有機密資訊傳送給外部使用者的郵件。</span><span class="sxs-lookup"><span data-stu-id="767e0-111">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="767e0-112">發生這種情況自動，並在秒內，根據您的 DLP 原則的設定方式。</span><span class="sxs-lookup"><span data-stu-id="767e0-112">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

- <span data-ttu-id="767e0-113">**範例 2： 保護文件中的敏感資訊**。</span><span class="sxs-lookup"><span data-stu-id="767e0-113">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="767e0-114">假設有人嘗試與 Microsoft Teams 通道或聊天室中的來賓共用文件和文件包含敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="767e0-114">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="767e0-115">如果您有 DLP 原則定義要避免這種情況，這些使用者不會開啟文件。</span><span class="sxs-lookup"><span data-stu-id="767e0-115">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="767e0-116">請注意，在此情況下，您的 DLP 原則必須包括 SharePoint 和 OneDrive 設為就地保護的順序。</span><span class="sxs-lookup"><span data-stu-id="767e0-116">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="767e0-117">原則提示協助教育使用者</span><span class="sxs-lookup"><span data-stu-id="767e0-117">Policy tips help educate users</span></span>

<span data-ttu-id="767e0-118">類似於 DLP [Exchange、 Outlook 和 outlook 網頁版](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint 和 OneDrive for Business 網站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)以及[Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)中的運作方式，原則提示時出現巨集指令與 DLP 原則的衝突。</span><span class="sxs-lookup"><span data-stu-id="767e0-118">Similar to how DLP works in [Exchange, Outlook, and Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint and OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="767e0-119">以下是範例的原則提示：</span><span class="sxs-lookup"><span data-stu-id="767e0-119">Here's an example of a policy tip:</span></span>

![Teams 中的已封鎖的郵件通知](media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="767e0-121">在此情況下，寄件者會嘗試共用 Microsoft Teams 通道中社會安全號碼。</span><span class="sxs-lookup"><span data-stu-id="767e0-121">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="767e0-122">**我可以做什麼？** 連結會開啟一個對話方塊，提供解決問題，寄件者的選項。</span><span class="sxs-lookup"><span data-stu-id="767e0-122">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="767e0-123">請注意，在此情況下，寄件者可以選擇覆寫原則，或通知系統管理員檢視並加以解決。</span><span class="sxs-lookup"><span data-stu-id="767e0-123">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![解決封鎖郵件的選項](media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="767e0-125">在您組織中，您可以選擇是否要允許使用者覆寫 DLP 原則，或不。</span><span class="sxs-lookup"><span data-stu-id="767e0-125">In your organization, you can choose whether to allow users to override a DLP policy, or not.</span></span> <span data-ttu-id="767e0-126">和，當您設定 DLP 原則時，您可以為您的組織使用的預設原則提示，或[自訂原則提示](#to-customize-policy-tips)。</span><span class="sxs-lookup"><span data-stu-id="767e0-126">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span> 

<span data-ttu-id="767e0-127">回到我們的範例，其中寄件者會共用中的小組通道，此處的社會安全號碼哪些收件者鋸：</span><span class="sxs-lookup"><span data-stu-id="767e0-127">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![封鎖的郵件](media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="767e0-129">**這是什麼？** 連結會開啟 [DLP 原則，這有助於說明為什麼已封鎖郵件的相關[文章](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="767e0-129">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="767e0-130">若要自訂原則提示</span><span class="sxs-lookup"><span data-stu-id="767e0-130">To customize policy tips</span></span>

<span data-ttu-id="767e0-131">若要執行這項工作，您必須獲指派的角色具有 [編輯 DLP 原則的權限。</span><span class="sxs-lookup"><span data-stu-id="767e0-131">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="767e0-132">若要深入了解，請參閱 <<c0>權限。</span><span class="sxs-lookup"><span data-stu-id="767e0-132">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="767e0-133">移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="767e0-133">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="767e0-134">選擇 [**資料外洩防護** > **原則**。</span><span class="sxs-lookup"><span data-stu-id="767e0-134">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="767e0-135">選取原則，並旁**原則設定**，選擇 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="767e0-135">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="767e0-136">建立新規則，或編輯現有的原則規則。</span><span class="sxs-lookup"><span data-stu-id="767e0-136">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![編輯原則的規則](media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="767e0-138">在 [**使用者通知**] 索引標籤上選取 [**自訂電子郵件的文字**及/或**自訂原則提示文字**選項。</span><span class="sxs-lookup"><span data-stu-id="767e0-138">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="767e0-139">![自訂使用者通知和原則提示](media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-139">![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="767e0-140">指定您想要用於電子郵件通知及/或原則提示的文字，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="767e0-140">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span> 

7. <span data-ttu-id="767e0-141">在 [**原則設定**] 索引標籤中，選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="767e0-141">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="767e0-142">可讓您變更其透過您的資料中心和同步處理至使用者帳戶的方式運作大約一小時。</span><span class="sxs-lookup"><span data-stu-id="767e0-142">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="767e0-143">新增 Microsoft Teams 為現有的 DLP 原則的位置</span><span class="sxs-lookup"><span data-stu-id="767e0-143">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="767e0-144">若要執行這項工作，您必須獲指派的角色具有 [編輯 DLP 原則的權限。</span><span class="sxs-lookup"><span data-stu-id="767e0-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="767e0-145">若要深入了解，請參閱 <<c0>權限。</span><span class="sxs-lookup"><span data-stu-id="767e0-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="767e0-146">移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="767e0-146">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="767e0-147">選擇 [**資料外洩防護** > **原則**。</span><span class="sxs-lookup"><span data-stu-id="767e0-147">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="767e0-148">選取原則]，然後查看 [**位置**] 下的值。</span><span class="sxs-lookup"><span data-stu-id="767e0-148">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="767e0-149">如果您看到**小組聊天和通道訊息**，就會是完成設定。</span><span class="sxs-lookup"><span data-stu-id="767e0-149">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="767e0-150">如果不這麼做，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="767e0-150">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="767e0-151">![現有的原則的位置](media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-151">![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="767e0-152">在 [**狀態**] 欄中，開啟原則**小組聊天和通道訊息**。</span><span class="sxs-lookup"><span data-stu-id="767e0-152">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="767e0-153">![DLP 小組聊天和通道](media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-153">![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="767e0-154">保留預設設定的所有帳戶，或指定要包含或排除哪一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="767e0-154">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="767e0-155">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="767e0-155">Click **Save**.</span></span>

<span data-ttu-id="767e0-156">可讓您變更其透過您的資料中心和同步處理至使用者帳戶的方式運作大約一小時。</span><span class="sxs-lookup"><span data-stu-id="767e0-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="767e0-157">對於 Microsoft Teams 定義新的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="767e0-157">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="767e0-158">若要執行這項工作，您必須獲指派的角色具有 [編輯 DLP 原則的權限。</span><span class="sxs-lookup"><span data-stu-id="767e0-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="767e0-159">若要深入了解，請參閱 <<c0>權限。</span><span class="sxs-lookup"><span data-stu-id="767e0-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="767e0-160">移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="767e0-160">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="767e0-161">選擇 [**資料外洩防護** > **原則** > **+ 建立原則**。</span><span class="sxs-lookup"><span data-stu-id="767e0-161">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span> 

3. <span data-ttu-id="767e0-162">選擇[範本](data-loss-prevention-policies.md#dlp-policy-templates)，然後再選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="767e0-162">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="767e0-163">在我們的範例中，我們會選擇美國個人識別資訊的資料範本。</span><span class="sxs-lookup"><span data-stu-id="767e0-163">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="767e0-164">![隱私權 DLP 原則範本](media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-164">![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="767e0-165">在 [**您的原則名稱**] 索引標籤上指定的名稱和描述原則] 中，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="767e0-165">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span> 

5. <span data-ttu-id="767e0-166">在 [**選擇位置**] 索引標籤中，保留預設設定的所有位置，或選取 [**讓我選擇特定位置**，，然後選擇**下一步**。</span><span class="sxs-lookup"><span data-stu-id="767e0-166">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="767e0-167">如果您選擇選擇特定位置，選取您的 DLP 原則的位置，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="767e0-167">If you opted to choose specific locations, select the locations for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="767e0-168">![DLP 原則的位置](media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-168">![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="767e0-169">如果您想要確定包含敏感資訊的文件不不當共用，請確定**SharePoint 網站**與**OneDrive 帳戶**已開啟，以及**小組聊天和通道訊息**。</span><span class="sxs-lookup"><span data-stu-id="767e0-169">If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>
<br/>

6. <span data-ttu-id="767e0-170">在**原則設定**] 索引標籤的 [**自訂您要保護的內容類型**，簡單的設定，保留預設值或選擇**使用進階設定**]，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="767e0-170">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="767e0-171">如果您選擇 [進階的設定，您可以建立或編輯原則的規則。</span><span class="sxs-lookup"><span data-stu-id="767e0-171">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="767e0-172">（若要取得此問題的協助，請參閱[和進階設定比較簡單的設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)）。</span><span class="sxs-lookup"><span data-stu-id="767e0-172">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="767e0-173">在 [**原則設定**] 索引標籤上 [**您想要執行動作如果偵測到機密資訊？**，檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="767e0-173">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="767e0-174">（在這裡是您可以選擇保留預設[原則提示和電子郵件通知](use-notifications-and-policy-tips.md)，或加以自訂）。</span><span class="sxs-lookup"><span data-stu-id="767e0-174">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="767e0-175">![秘訣與通知的 DLP 原則設定](media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-175">![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="767e0-176">當您完成檢閱或編輯設定時，選擇 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="767e0-176">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="767e0-177">在 [**原則設定**] 索引標籤上 [**您要開啟第一個原則或測試內容？**，選擇是否要開啟原則，[先進行測試](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)，或將它關閉，現在保存，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="767e0-177">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="767e0-178">![指定是否要開啟原則](media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="767e0-178">![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="767e0-179">在 [**檢閱您的設定**] 索引標籤中，檢閱您的新原則的設定。</span><span class="sxs-lookup"><span data-stu-id="767e0-179">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="767e0-180">選擇 [**編輯**] 以進行變更。</span><span class="sxs-lookup"><span data-stu-id="767e0-180">Choose **Edit** to make changes.</span></span> <span data-ttu-id="767e0-181">當您完成時，選擇 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="767e0-181">When you're finished, choose **Create**.</span></span> 

<span data-ttu-id="767e0-182">允許大約一小時的您新的原則，以其透過您的資料中心和同步處理至使用者帳戶的方式運作。</span><span class="sxs-lookup"><span data-stu-id="767e0-182">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="767e0-183">相關文章</span><span class="sxs-lookup"><span data-stu-id="767e0-183">Related articles</span></span>

[<span data-ttu-id="767e0-184">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="767e0-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="767e0-185">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="767e0-185">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
