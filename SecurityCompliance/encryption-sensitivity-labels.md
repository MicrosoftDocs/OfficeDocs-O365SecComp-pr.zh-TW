---
title: 使用敏感度標籤中的加密來限制內容的存取
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 10/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。敏感度標籤可以使用加密來保護內容。
ms.openlocfilehash: fff787e980b7dbbfea227734bb6caad0985cf158
ms.sourcegitcommit: 77c50332c3dbb026f47da3ac2534198202d9ef64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2018
ms.locfileid: "25842602"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a><span data-ttu-id="21154-104">使用敏感度標籤中的加密來限制內容的存取</span><span class="sxs-lookup"><span data-stu-id="21154-104">Restrict access to content by using encryption in sensitivity labels</span></span>

<span data-ttu-id="21154-p102">當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。例如，使用敏感度標籤的加密設定，您可以保護內容，以便：</span><span class="sxs-lookup"><span data-stu-id="21154-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="21154-107">僅您組織內的使用者才能開啟機密文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="21154-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="21154-108">僅行銷部門中的使用者才能編輯和列印促銷公告文件或電子郵件，而您組織中的所有其他使用者則只能讀取它。</span><span class="sxs-lookup"><span data-stu-id="21154-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="21154-109">使用者無法轉寄電子郵件，或從中複製包含內部組織相關消息的資訊。</span><span class="sxs-lookup"><span data-stu-id="21154-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="21154-110">在指定日期之後，無法開啟傳送給商業夥伴的目前價格清單。</span><span class="sxs-lookup"><span data-stu-id="21154-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="21154-111">加密文件或電子郵件時，內容的存取會受到限制，以便：</span><span class="sxs-lookup"><span data-stu-id="21154-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="21154-112">只有標籤加密設定授權的使用者才能將其解密。</span><span class="sxs-lookup"><span data-stu-id="21154-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="21154-113">即使檔案重新命名，無論其位於您組織內部或外部，仍保持加密狀態。</span><span class="sxs-lookup"><span data-stu-id="21154-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="21154-114">同時靜態加密 (例如，在 OneDrive 帳戶中) 及傳輸中加密 (例如，已傳送的電子郵件)。</span><span class="sxs-lookup"><span data-stu-id="21154-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="21154-115">可在 [Office 365 安全性與合規性中心] > [**標籤**] 頁面 > [**敏感度**] 索引標籤 > [**建立標籤**] 中使用加密設定。</span><span class="sxs-lookup"><span data-stu-id="21154-115">The encryption settings are available in the Office 365 Security & Compliance Center > **Labels** page > **Sensitivity** tab > **Create a label**.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="21154-116">加密的運作方式</span><span class="sxs-lookup"><span data-stu-id="21154-116">How encryption works</span></span>

<span data-ttu-id="21154-p103">加密會使用 Azure Rights Management (Azure RMS)。Azure RMS 會使用加密、身分識別和授權原則。若要深入了解，請參閱[什麼是 Azure Rights Management？](https://docs.microsoft.com/zh-TW/azure/information-protection/what-is-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="21154-p103">Encryption uses Azure Rights Management (Azure RMS). Azure RMS uses encryption, identity, and authorization policies. To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/zh-TW/azure/information-protection/what-is-azure-rms)</span></span>

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a><span data-ttu-id="21154-120">如何開啟敏感度標籤的加密</span><span class="sxs-lookup"><span data-stu-id="21154-120">How to turn on encryption for a sensitivity label</span></span>

<span data-ttu-id="21154-p104">若要開始，只需將 [**加密**] 切換為 [**開啟**]，然後使用下列選項來控制誰可以存取此標套用至其中的電子郵件或文。您可以：</span><span class="sxs-lookup"><span data-stu-id="21154-p104">To begin, simply toggle **Encryption** to **On**, and then use the options below to control who can acess email or documents to which this label is applied. You can:</span></span>

1. <span data-ttu-id="21154-p105">**將加密同時套用至電子郵件和文件，或只套用至電子郵件。** 如果您選擇只套用至電子郵件，則將在 Outlook 中加密具有此標籤的訊息，但不會在其他應用程式 (例如 Word 或 PowerPoint) 中加密具有此標籤的文件。</span><span class="sxs-lookup"><span data-stu-id="21154-p105">**Apply encryption to both email and documents, or just email.** If you choose just email, messages with this label will be encrypted in Outlook, but documents with this label won't be encrypted in other apps, such as Word or PowerPoint.</span></span> 
2. <span data-ttu-id="21154-p106">在套用標籤之後**允許標籤內容的存取在特定日期或在特定天數之後到期**。在此之後，使用者將無法開啟標籤項目。如果您指定日期，則有效時間直到您的目前時區中該日期的午夜。</span><span class="sxs-lookup"><span data-stu-id="21154-p106">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone.</span></span> 
3. <span data-ttu-id="21154-p107">在套用標籤之後**允許離線存取**可為從不、一律或特定天數。如果您將離線存取限制為從不或天數，則達到該臨界值時，必須重新驗證使用者，並記錄其存取。如需詳細資訊，請參閱關於 Rights Management 使用授權的下一節。</span><span class="sxs-lookup"><span data-stu-id="21154-p107">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

![敏感度標籤的加密設定](media/Sensitivity_Encryption_settings_for_sensitivity_label.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="21154-132">用於離線存取的 Rights Management 使用授權</span><span class="sxs-lookup"><span data-stu-id="21154-132">Rights Management use license for offline access</span></span>

<span data-ttu-id="21154-p108">當使用者離線開啟受到敏感度標籤保護的文件或電子郵件時，該內容的 Azure Rights Management 使用授權會授與使用者。此使用授權是一種憑證，其中包含使用者對文件或電子郵件的使用權，以及用來加密內容的加密金鑰。使用授權也會包含到期日 (若已設定的話)，以及使用授權的有效期限。</span><span class="sxs-lookup"><span data-stu-id="21154-p108">When a user opens a document or email offline that’s been protected by a sensitivity label, an Azure Rights Management use license for that content is granted to the user. This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content. The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="21154-p109">如果未設定到期日，則租用戶的預設使用授權有效期間為 30 天。在這段期間，不會針對內容重新驗證或重新授權使用者。這可讓使用者在沒有網際網路連線的情況下繼續開啟受保護文件或電子郵件。 使用授權有效期間到期時，下次使用者存取受保護文件或電子郵件時，必須重新驗證和重新授權使用者。</span><span class="sxs-lookup"><span data-stu-id="21154-p109">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This lets the user continue to open the protected document or email without an Internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="21154-p110">除了重新驗證外，還會重新評估原則和使用者群組成員資格。這表示，如果上次使用者存取內容後，原則或群組成員資格發生變更，則這些使用者可能遇到相同的文件或電子郵件，卻有不同的存取結果。</span><span class="sxs-lookup"><span data-stu-id="21154-p110">In addition to reauthentication, the policy and user group membership is reevaluated. This means that users could experience different access results for the same document or email if there are changes in the policy or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="21154-142">若要了解如何變更預設 30 天設定，請參閱 [Rights Management 使用授權](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="21154-142">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

## <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="21154-143">將權限指派給特定使用者或群組</span><span class="sxs-lookup"><span data-stu-id="21154-143">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="21154-144">您可以將權限授與特定人員，以便只有他們可與標籤內容互動。</span><span class="sxs-lookup"><span data-stu-id="21154-144">You can grant permissions to specific people so that only they can interact with the labeled content.</span></span>

<span data-ttu-id="21154-145">作法是簡單的兩步驟程序：</span><span class="sxs-lookup"><span data-stu-id="21154-145">Doing so is a straightforward two-step process:</span></span>

1. <span data-ttu-id="21154-146">首先，新增將獲指派標籤內容之權限的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="21154-146">First you add users or groups that will be assigned permissions to the labeled content.</span></span>
2. <span data-ttu-id="21154-147">接著，選擇那些使用者對標籤內容具有的權限。</span><span class="sxs-lookup"><span data-stu-id="21154-147">Then you choose which permissions those users have for the labeled content.</span></span>

![將權限指派給使用者的選項](media/Sensitivity_Assign_permissions_settings.png)

### <a name="add-users-or-groups"></a><span data-ttu-id="21154-149">新增使用者或群組</span><span class="sxs-lookup"><span data-stu-id="21154-149">Add users or groups</span></span>

<span data-ttu-id="21154-150">指派權限時，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="21154-150">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="21154-p111">組織中的所有人 (所有租用戶成員)。此設定會排除來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="21154-p111">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="21154-153">任何特定使用者或啟用電子郵件功能的安全性群組、通訊群組、Office 365 群組或動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="21154-153">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="21154-154">組織外的任何電子郵件地址或網域，例如 gmail.com、hotmail.com 或 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="21154-154">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span>

<span data-ttu-id="21154-155">當您選擇所有租用戶成員或瀏覽目錄時，使用者或群組必須具有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="21154-155">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="21154-p112">最佳作法是使用群組，而非使用者。此策略可讓您保持更簡單的組態。</span><span class="sxs-lookup"><span data-stu-id="21154-p112">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

### <a name="choose-permissions"></a><span data-ttu-id="21154-158">選擇權限</span><span class="sxs-lookup"><span data-stu-id="21154-158">Choose permissions</span></span>

<span data-ttu-id="21154-159">當您選擇要對那些使用者或群組允許的權限時，您可以選取下列一項：</span><span class="sxs-lookup"><span data-stu-id="21154-159">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="21154-160">[預先定義的權限層級](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，其中有一組預設的權限，例如共同作者或檢閱者。</span><span class="sxs-lookup"><span data-stu-id="21154-160">A [predefined permissions level](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="21154-161">一組自訂的權限，您可在其中選擇任何您想要的權限。</span><span class="sxs-lookup"><span data-stu-id="21154-161">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="21154-162">如需每一個特定權限的詳細資訊，請參閱[使用權限和描述](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="21154-162">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![選擇預設或自訂權限的選項](media/Sensitivity_Choose_permissions_settings.png)

<span data-ttu-id="21154-p113">請注意，相同標籤可將不同的權限授與不同的使用者。例如，單一標籤可將某些使用者指派為檢閱者，並將不同的使用者指派為共同作者，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21154-p113">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown below.</span></span>

<span data-ttu-id="21154-p114">若要這麼做，請新增使用者或群組、將權限指派給他們，並儲存這些設定。然後，重複這些步驟，新增使用者並將權限指派給他們，每次儲存設定。您可以視需要經常執行此動作，為不同的使用者定義不同的權限。</span><span class="sxs-lookup"><span data-stu-id="21154-p114">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can do this as often as necessary, to define different permissions for different users.</span></span>

![具有不同權限的不同使用者](media/Sensitivity_Multiple_users_permissions.png)

### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="21154-170">Rights Management 簽發者 (套用敏感度標籤的使用者) 一律具有完全控制權</span><span class="sxs-lookup"><span data-stu-id="21154-170">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="21154-p115">敏感度標籤的加密會使用 Azure RMS。當使用者套用敏感度標籤，以使用 Azure RMS 保護文件或電子郵件時，該使用者就會變成該內容的 Rights Management 簽發者。</span><span class="sxs-lookup"><span data-stu-id="21154-p115">Encryption for a sensitivity label uses Azure RMS. When a user applies a sensitivity label to protect a document or email by using Azure RMS, that user becomes the Rights Management issuers for that content.</span></span>

<span data-ttu-id="21154-173">Rights Management 簽發者一律會被授與文件或電子郵件的完全控制權限，此外：</span><span class="sxs-lookup"><span data-stu-id="21154-173">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="21154-174">如果保護設定包括到期日，則 Rights Management 簽發者仍然可在該日期之後開啟和編輯文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="21154-174">If the protection settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="21154-175">Rights Management 簽發者一律可以離線存取文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="21154-175">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="21154-176">Rights Management 簽發者仍可以開啟撤銷後的文件。</span><span class="sxs-lookup"><span data-stu-id="21154-176">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="21154-177">如需詳細資訊，請參閱[Rights Management 簽發者和 Rights Management 擁有者](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="21154-177">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a><span data-ttu-id="21154-178">將加密內容儲存在 OneDrive 和 SharePoint 中</span><span class="sxs-lookup"><span data-stu-id="21154-178">Storing encrypted content in OneDrive and SharePoint</span></span>

<span data-ttu-id="21154-p116">請注意，當加密套用至 OneDrive 和 SharePoint 中儲存的檔案時，服務無法處理這些檔案的內容。這表示共同撰寫、電子文件探索、搜尋、Delve 和其他共同作業功能等這類功能無法運作。此外，資料外洩防護 (DLP) 原則只可使用中繼資料 (包括 Office 365 標籤)，但無法使用加密檔案的內容 (例如檔案內的信用卡號碼)。</span><span class="sxs-lookup"><span data-stu-id="21154-p116">Be aware that when Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files. Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. DLP policies can only work with the metadata (including Office 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>

<span data-ttu-id="21154-p117">這僅適用於 OneDrive 和 SharePoint 中儲存的內容。在 Exchange Online 中，傳輸規則會使用[進階使用者帳戶](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-super-users)，讓他們可以掃描加密內容，並強制執行 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="21154-p117">This applies only to content stored in OneDrive and SharePoint. In Exchange Online, transport rules use the [super user account](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-super-users) so that they can scan encrypted content and enforce DLP policies.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="21154-184">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="21154-184">Important prerequisites</span></span>

<span data-ttu-id="21154-185">在可以使用加密之前，您可能需要執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="21154-185">Before you can use encryption, you might need to perform these tasks.</span></span>

### <a name="activating-azure-rights-management"></a><span data-ttu-id="21154-186">啟動 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="21154-186">^^ Azure Rights Management</span></span>

<span data-ttu-id="21154-p118">若要使用敏感度標籤中的加密，需要在您的租用戶中啟動 Azure Rights Management 服務。在較新的租用戶中，此服務預設為開啟，但您可能需要手動啟動此服務。如需詳細資訊，請參閱[啟動 Azure Rights Management](https://docs.microsoft.com/zh-TW/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="21154-p118">To use encryption in sensitivity labels, the Azure Rights Management service needs to be activated in your tenant. In newer tenants, the service is on by default, but you might need to manually activate the service. For more information, see [Activating Azure Rights Management](https://docs.microsoft.com/zh-TW/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="21154-190">設定 Exchange 進行 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="21154-190">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="21154-p119">在使用者可在 Outlook 中套用標籤，以保護其電子郵件之前，不必設定 Exchange 進行 Azure 資訊保護。不過，直到設定 Exchange 進行 Azure 資訊保護前，您都無法取得使用 Azure Rights Management 保護與 Exchange 搭配的完整功能。</span><span class="sxs-lookup"><span data-stu-id="21154-p119">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="21154-193">例如，使用者無法在行動電話上檢視受保護的電子郵件，也無法在 Web 上使用 Outlook 這樣做，受保護的電子郵件無法編製索引進行搜尋，以及您無法設定 Exchange Online DLP 進行 Rights Management 保護。</span><span class="sxs-lookup"><span data-stu-id="21154-193">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="21154-194">若要確保 Exchange 可以支援這些額外情節，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="21154-194">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="21154-195">若為 Exchange Online，請參閱 [Exchange Online：IRM 設定](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-office365#exchange-online-irm-configuration)的指示。</span><span class="sxs-lookup"><span data-stu-id="21154-195">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-office365#exchange-online-irm-configuration).</span></span>
- <span data-ttu-id="21154-196">若為 Exchange 內部部署，您必須部署 [RMS 連接器和設定您的 Exchange Server](https://docs.microsoft.com/zh-TW/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="21154-196">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/zh-TW/azure/information-protection/deploy-rms-connector).</span></span> 
