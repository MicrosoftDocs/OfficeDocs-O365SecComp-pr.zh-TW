---
title: 在 Office 365 中設定連接器來封存 LinkedIn 資料 (預覽)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 系統管理員可以設定一個原生連接器，以將資料從 LinkedIn 公司頁面匯入到 Office 365。 這可讓您在 Office 365 中封存來自第三方資料來源的資料，使得您可使用法務保存措施、內容搜尋和保留原則之類的合規性功能來管理您組織的第三方資料。
ms.openlocfilehash: 618cef7c0208378179d41a94f4a274a0bddadee9
ms.sourcegitcommit: ecc823c2a4f1465114cf1d3a4630e31c47779ddc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "35079377"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a><span data-ttu-id="10b89-104">在 Office 365 中設定連接器來封存 LinkedIn 資料 (預覽)</span><span class="sxs-lookup"><span data-stu-id="10b89-104">Set up a connector to archive LinkedIn data in Office 365 (Preview)</span></span>

<span data-ttu-id="10b89-105">在 Office 365 中封存來自 LinkedIn 公司頁面資料的連接器功能目前處於預覽階段。</span><span class="sxs-lookup"><span data-stu-id="10b89-105">The connector feature to archive data from LinkedIn Company pages in Office 365 is in Preview.</span></span>

<span data-ttu-id="10b89-106">在安全性與 Office 365 合規性中心使用原生連接器來匯入並保存來自 LinkedIn 公司頁面的資料。</span><span class="sxs-lookup"><span data-stu-id="10b89-106">Use a native connector in the Security & Compliance Center in Office 365 to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="10b89-107">安裝和設定連接器之後，連接器會每 24 小時連線到特定的 LinkedIn 公司頁面中帳戶一次。</span><span class="sxs-lookup"><span data-stu-id="10b89-107">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="10b89-108">連接器會將張貼至公司頁面的訊息轉換為電子郵件訊息，然後在 Office 365 中將這些項目匯入至信箱。</span><span class="sxs-lookup"><span data-stu-id="10b89-108">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="10b89-109">將 LinkedIn 公司頁面資料儲存在信箱之後，您可以將訴訟資料暫留、內容搜尋、就地封存、稽核與 Office 365 保留原則之類的 Office 365 合規性功能套用至 LinkedIn 資料。</span><span class="sxs-lookup"><span data-stu-id="10b89-109">After the LinkedIn Company page data is stored in a mailbox, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="10b89-110">例如，您可以使用內容搜尋來搜尋這些項目，或是在進階電子文件探索案例中將儲存空間信箱與監管人建立關聯。</span><span class="sxs-lookup"><span data-stu-id="10b89-110">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="10b89-111">在 Office 365 中建立連接器以匯入和封存 LinkedIn 資料，可協助組織保持符合政府與法規政策的規範。</span><span class="sxs-lookup"><span data-stu-id="10b89-111">Creating a connector to import and archive LinkedIn data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="10b89-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="10b89-112">Before you begin</span></span>

- <span data-ttu-id="10b89-113">您的組織必須同意讓 Office 365 匯入服務存取組織的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="10b89-113">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="10b89-114">若要同意這項要求，請移至[本頁](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)使用 Office 365 全域系統管理員認證登入，然後接受要求。</span><span class="sxs-lookup"><span data-stu-id="10b89-114">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="10b89-115">建立 LinkedIn 公司頁面連接器的使用者，必須獲指派 Exchange Online 中的信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="10b89-115">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="10b89-116">這是存取安全性與合規性中心的**封存第三方資料**頁面所需。</span><span class="sxs-lookup"><span data-stu-id="10b89-116">This is required to access the **Archive third-party data** page in the Security & Compliance Center.</span></span> <span data-ttu-id="10b89-117">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="10b89-117">By default, this role isn't assigned to any role group in ExchangeOnline.</span></span> <span data-ttu-id="10b89-118">您可以在 Exchange Online 中將「信箱匯入匯出」角色新增至「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="10b89-118">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="10b89-119">或者您可以建立角色群組、指派「信箱匯入匯出」角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="10b89-119">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="10b89-120">如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」文章中的[建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)小節。</span><span class="sxs-lookup"><span data-stu-id="10b89-120">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="10b89-121">您必須具備 LinkedIn 使用者帳戶登入認證 (電子郵件地址或電話號碼和密碼)，該帳號是您想要封存的 LinkedIn 公司頁面的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="10b89-121">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="10b89-122">您可以使用這些認證在設定連接器時登入 LinkedIn。</span><span class="sxs-lookup"><span data-stu-id="10b89-122">You use these credentials to sign in to LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="10b89-123">建立 LinkedIn 連接器</span><span class="sxs-lookup"><span data-stu-id="10b89-123">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="10b89-124">移至 <https://protection.office.com>，按一下 [資料控管] \> [匯入]\*\*\*\*，然後按一下 [封存第三方資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-124">Go to <https://protection.office.com> and then click **Data governance \> Import** and then click **Archive third-party data**.</span></span>

2. <span data-ttu-id="10b89-125">在 [封存第三方資料]\*\*\*\* 頁面上，按一下 [新增連接器]\*\*\*\*，然後按一下 **LinkedIn**。</span><span class="sxs-lookup"><span data-stu-id="10b89-125">On the **Archive third-party data** page, click **Add a connector**, and then click **LinkedIn**.</span></span>

3. <span data-ttu-id="10b89-126">在 [服務條款]\*\*\*\* 頁面上，按一下 [接受]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-126">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="10b89-127">在 [使用 LinkedIn 登入]\*\*\*\* 頁面上，按一下 [使用 LinkedIn 登入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-127">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="10b89-128">LinkedIn 登入頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="10b89-128">The LinkedIn sign in page is displayed.</span></span>

   ![LinkedIn 登入頁面](media/LinkedInSigninPage.png)

5. <span data-ttu-id="10b89-130">在 LinkedIn 登入頁面上，輸入與您想要封存的公司頁面相關聯的 LinkedIn 帳戶的電子郵件地址 (或電話號碼) 和密碼，然後按一下 [登入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-130">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account that associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="10b89-131">精靈頁面隨即會顯示與您登入的帳戶相關聯的所有 LinkedIn 公司頁面的清單。</span><span class="sxs-lookup"><span data-stu-id="10b89-131">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="10b89-132">您只能針對一個公司頁面設定一個連接器。</span><span class="sxs-lookup"><span data-stu-id="10b89-132">A connector can only be configured for one company page.</span></span> <span data-ttu-id="10b89-133">如果您的組織有多個 LinkedIn 公司頁面，則必須為每個頁面建立一個連接器。</span><span class="sxs-lookup"><span data-stu-id="10b89-133">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![顯示 LinkedIn 公司頁面清單的頁面](media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="10b89-135">選取您要從中封存項目的公司頁面，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-135">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="10b89-136">在 [設定篩選器]\*\*\*\* 頁面上，您可以套用篩選器以開始匯入特定存留期的項目。</span><span class="sxs-lookup"><span data-stu-id="10b89-136">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="10b89-137">選取某個存留期，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-137">Select TemporaryUserDB, and then click Next.</span></span>

8. <span data-ttu-id="10b89-138">在 [設定儲存空間帳戶]\*\*\*\* 頁面上，輸入將匯入 LinkedIn 項目的目標 Office 365 信箱的電子郵件地址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10b89-138">On the **Set storage account** page, type the email address of an Office 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="10b89-139">項目會匯入至此信箱中的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10b89-139">Items are imported to the Inbox folder in this mailbox.</span></span>

9. <span data-ttu-id="10b89-140">檢閱連接器設定，然後按一下 [儲存]\*\*\*\* 來完成連接器設定。</span><span class="sxs-lookup"><span data-stu-id="10b89-140">Review the connector settings and then click **Save** to complete the connector setup.</span></span>

<span data-ttu-id="10b89-141">建立連接器之後，您可以返回 [封存第三方資料]\*\*\*\* 頁面來檢視新的連接器 (必要時按一下 [重新整理]\*\*\*\* 來更新連接器清單)。</span><span class="sxs-lookup"><span data-stu-id="10b89-141">After you create the connector, you can go back to the **Archive third-party data** page (click **Refresh** if necessary to update the list of connectors) a view the new connector.</span></span> <span data-ttu-id="10b89-142">[狀態]\*\*\*\* 欄中的值為**正在等待啟動**。</span><span class="sxs-lookup"><span data-stu-id="10b89-142">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="10b89-143">最多需要 24 小時的時間，才能開始初始匯入程序。</span><span class="sxs-lookup"><span data-stu-id="10b89-143">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="10b89-144">在連接器第一次執行並匯入 LinkedIn 項目後，連接器會每 24 小時執行一次，並匯入在過去 24 小時於 LinkedIn 公司頁面上建立的任何新項目。</span><span class="sxs-lookup"><span data-stu-id="10b89-144">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="10b89-145">若要檢視更多詳細資訊，請按一下 [封存第三方資料]\*\*\*\* 頁面上清單中的連接器，以顯示飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="10b89-145">To view more details, click the connector in the list on the **Archive third-party data** page to display the flyout page.</span></span> <span data-ttu-id="10b89-146">在 [狀態]\*\*\*\* 下，顯示的日期範圍會指出建立連接器時所選取的存留期篩選器。</span><span class="sxs-lookup"><span data-stu-id="10b89-146">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span> 

## <a name="more-information"></a><span data-ttu-id="10b89-147">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="10b89-147">More information</span></span>

- <span data-ttu-id="10b89-148">LinkedIn 項目會匯入到 Office 365 中儲存空間信箱的 [收件匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10b89-148">LinkedIn items are imported to the Inbox folder in the storage mailbox in Office 365.</span></span> <span data-ttu-id="10b89-149">這些項目會顯示為電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="10b89-149">They appear as email messages.</span></span> <span data-ttu-id="10b89-150">郵件的寄件者顯示名稱為 LinkedIn 公司頁面名稱。</span><span class="sxs-lookup"><span data-stu-id="10b89-150">The display name of the sender of the message is the name of the LinkedIn Company Page.</span></span> <span data-ttu-id="10b89-151">寄件者的實際的電子郵件地址是儲存信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="10b89-151">The actual email address of the sender is the email address of the storage mailbox.</span></span> <span data-ttu-id="10b89-152">也會將公司頁面的名稱附加至主旨行的前端。</span><span class="sxs-lookup"><span data-stu-id="10b89-152">The name of the company page is also pre-appended to the subject line.</span></span> 

- <span data-ttu-id="10b89-153">因為前述的行為，使用 Microsoft 電子文件探索工具來搜尋封存在 Office 365 中的 LinkedIn 項目時，您可以搜尋 `from` 或 `subject` 電子郵件內容。</span><span class="sxs-lookup"><span data-stu-id="10b89-153">Because of the previous behavior, you can search the `from` or `subject` email properties when using a Microsoft eDiscovery tool to search LinkedIn items that are archived in Office 365.</span></span> <span data-ttu-id="10b89-154">例如，如果公司頁面的名稱為「Contoso 公司頁面」，您可以在關鍵字搜尋查詢中使用下列其中一個 *property:value* 組：</span><span class="sxs-lookup"><span data-stu-id="10b89-154">For example if the name of the company page is "Contoso Company Page", then you can use one of the following *property:value* pairs in the keyword search query:</span></span>
   
   ```
   from:"Contoso Company Page"
   ```

    <span data-ttu-id="10b89-155">或者</span><span class="sxs-lookup"><span data-stu-id="10b89-155">Or</span></span>

   ```
   subject:"Contoso Company Page"
   ```

- <span data-ttu-id="10b89-156">為了讓您易於找出或管理匯入至 Office 365 的 LinkedIn 項目，信箱儲存空間的擁有者 (或獲指派 FullAccess 權限的任何人) 都可以設定收件匣規則，將來自 LinkedIn 公司頁面的項目移至特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="10b89-156">To make it easier to locate or manage LinkedIn items imported to Office 365, the owner of the storage mailbox (or anyone assigned the FullAccess permission) can set up an inbox rule to move the items from a LinkedIn Company Page to a specific folder.</span></span> <span data-ttu-id="10b89-157">如果儲存空間信箱會用來封存從不同第三方資料來源匯入的項目，則此方式會很有用。</span><span class="sxs-lookup"><span data-stu-id="10b89-157">This is helpful if the storage mailbox is used to archive items imported from different third-party data sources.</span></span> <span data-ttu-id="10b89-158">比方說，您可以建立收件匣規則，將主旨欄位中包含特定 LinkedIn 公司頁面名稱的所有項目移動至特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="10b89-158">For example, you can create an inbox rule that moves all items that contain the name of a specific LinkedIn Company Page in the subject field to a specific folder.</span></span>