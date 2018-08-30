---
title: 將 eDiscovery 權限指派至 OneDrive for Business 網站
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: 您可以使用 SharePoint Online 中的 eDiscovery 中心來搜尋特定關鍵字、 敏感資訊及其他搜尋條件的組織中所有 OneDrive for Business 的網站。在組織中的每位使用者為其 OneDrive for Business 網站，位於名為網站集合的擁有人https://domain-my.sharepoint.com。根據預設，Office 365 全域管理員或規範管理員無法使用 SharePoint Online 中的 eDiscovery 中心搜尋任何 OneDrive for Business 的網站。若要搜尋 OneDrive for Business 網站、 系統管理員或規範經理必須是該 OneDrive for Business 網站的網站集合管理員。
ms.openlocfilehash: 48f84dfe21f0f99913ba2c27123d6c0e1f8bc03f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526775"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a><span data-ttu-id="51707-106">將 eDiscovery 權限指派至 OneDrive for Business 網站</span><span class="sxs-lookup"><span data-stu-id="51707-106">Assign eDiscovery permissions to OneDrive for Business sites</span></span>

<span data-ttu-id="51707-p102">您可以使用 SharePoint Online 中的 eDiscovery 中心來搜尋特定關鍵字、 敏感資訊及其他搜尋條件的組織中所有 OneDrive for Business 的網站。在組織中的每位使用者為其 OneDrive for Business 網站，位於名為網站集合的擁有人https://domain-my.sharepoint.com。根據預設，Office 365 全域管理員或規範管理員無法使用 SharePoint Online 中的 eDiscovery 中心搜尋任何 OneDrive for Business 的網站。若要搜尋 OneDrive for Business 網站、 系統管理員或規範經理必須是該 OneDrive for Business 網站的網站集合管理員。</span><span class="sxs-lookup"><span data-stu-id="51707-p102">You can use the eDiscovery Center in SharePoint Online to search all OneDrive for Business sites in your organization for certain keywords, sensitive information, and other search criteria. Each user in your organization is the owner of their OneDrive for Business site, which is located in the site collection named https://domain-my.sharepoint.com. By default, an Office 365 global administrator or compliance manager can't use the eDiscovery Center in SharePoint Online to search any OneDrive for Business sites. To search a OneDrive for Business site, administrators or compliance managers must be a site collection administrator for that OneDrive for Business site.</span></span> 
  
<span data-ttu-id="51707-111">本文會引導您完成讓系統管理員或法務經理每一個 OneDrive for Business 網站的網站集合管理員在組織中的步驟。</span><span class="sxs-lookup"><span data-stu-id="51707-111">This article guides you through the steps to make an administrator or compliance manager a site collection administrator for every OneDrive for Business site in your organization.</span></span> 
  
<span data-ttu-id="51707-112">請參閱如需本文，包括修改在步驟 3 中移除使用者為網站集合管理員的 OneDrive for Business 的網站中的指令碼中使用指令碼的提示[的詳細資訊](#more-information)] 區段。</span><span class="sxs-lookup"><span data-stu-id="51707-112">See the [More information](#more-information) section for tips about using the script in this article, including revising the script in Step 3 to remove a user as a site collection administrator from OneDrive for Business sites.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="51707-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="51707-113">Before you begin</span></span>

- <span data-ttu-id="51707-p103">安裝 SharePoint Online 管理命令介面。資訊，請參閱[設定 SharePoint Online 管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)。</span><span class="sxs-lookup"><span data-stu-id="51707-p103">Install the SharePoint Online Management Shell. For information, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span></span>
    
- <span data-ttu-id="51707-116">步驟 3 中您想要為網站集合管理員的使用者指派給您組織中的商務網站的任何 OneDrive 每的次執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="51707-116">Run the script in Step 3 each time you want to assign a user as a site collection administrator to any OneDrive for Business sites in your organization.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="51707-p104">系統管理員或法務 manager 身為網站集合管理員的 OneDrive for Business 網站可以開啟使用者的 OneDrive for Business 文件庫和執行為擁有者相同的工作。請務必控制及監視尚未指派之 eDiscovery 的權限至 OneDrive 針對在組織中的商務網站。</span><span class="sxs-lookup"><span data-stu-id="51707-p104">An administrator or compliance manager who is a site collection administrator for OneDrive for Business sites can open users' OneDrive for Business document libraries and perform the same tasks as the owner. It's important to control and monitor who has been assigned eDiscovery permissions to OneDrive for Business sites in your organization.</span></span> 
  
- <span data-ttu-id="51707-p105">本文中提供的指令碼範例不支援任何 Microsoft 標準支援程式或服務底下。指令碼範例會為 IS 提供不含任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="51707-p105">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a><span data-ttu-id="51707-124">步驟 1： 收集所有 OneDrive for Business 的網站的清單</span><span class="sxs-lookup"><span data-stu-id="51707-124">Step 1: Collect a list of all OneDrive for Business sites</span></span>

<span data-ttu-id="51707-p106">第一個步驟是在組織中建立的所有 OneDrive for Business 的網站清單。指示，請參閱[建立您的組織中的所有 OneDrive 位置的清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此指令碼會建立包含的所有 OneDrive 網站清單的文字檔案。您在步驟 3 中執行的指令碼會將指定的使用者作為網站集合管理員指派給每個 OneDrive for Business 網站會在此步驟中建立的文字檔案中所列。顯示下列文字會提供範例應該用來格式化此檔案中的網站清單的方式。視您可以移除此檔案的網站。</span><span class="sxs-lookup"><span data-stu-id="51707-p106">The first step is to create a list of all OneDrive for Business sites in your organization. For instructions, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. The script that you run in Step 3 assigns a specified user as a site collection administrator to each OneDrive for Business site listed in the text file that's created in this step. The following text provides an example of how the list of sites in this file should be formatted. You can remove sites from this file if necessary.</span></span>

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a><span data-ttu-id="51707-131">步驟 2： 連線至組織的 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="51707-131">Step 2: Connect SharePoint Online Management Shell to your organization</span></span>

1. <span data-ttu-id="51707-132">在您的本機電腦上，開啟 SharePoint Online 管理命令介面，執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="51707-132">On your local computer, open the SharePoint Online Management Shell, and run the following command:</span></span>

    ```
    $credentials = Get-Credential
    ```

2. <span data-ttu-id="51707-133">在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入 Office 365 全域管理員帳戶的使用者名稱和密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51707-133">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global administrator account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="51707-134">執行下列程式碼將命令介面連線至您的 SharePoint Online 組織：</span><span class="sxs-lookup"><span data-stu-id="51707-134">Run the following command to connect the Shell to your SharePoint Online organization:</span></span>
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. <span data-ttu-id="51707-135">若要確認您已連線至 SharePoint Online 組織，執行下列命令以取得貴組織中所有網站的清單：</span><span class="sxs-lookup"><span data-stu-id="51707-135">To verify that you are connected to your SharePoint Online organization, run the following command to get a list of all the sites in your organization:</span></span>
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a><span data-ttu-id="51707-136">步驟 3：指派使用者為 OneDrive for Business 網站的網站集合管理員</span><span class="sxs-lookup"><span data-stu-id="51707-136">Step 3: Assign a user as a site collection administrator to OneDrive for Business sites</span></span>

<span data-ttu-id="51707-p107">下一步是執行指令碼會將指定的使用者指派為中每一個 OneDrive for Business 網站在組織中的網站集合管理員。此指令碼使用您在步驟 1 中建立的商務網站 OneDrive 的清單。先前所述，您必須執行此指令碼每次您要為網站集合管理員指派使用者至 OneDrive for Business 的網站。</span><span class="sxs-lookup"><span data-stu-id="51707-p107">The next step is to run a script that assigns a specified user as a site collection administrator in every OneDrive for Business site in your organization. This script uses the list of OneDrive for Business sites that you created in Step 1. As previously stated, you have to run this script each time that you want to assign a user as a site collection administrator to OneDrive for Business sites.</span></span>
  
1. <span data-ttu-id="51707-p108">儲存下列文字至文字檔。例如，您可以儲存至名為 OD4BAssignSCA.txt 的檔案。</span><span class="sxs-lookup"><span data-stu-id="51707-p108">Save the following text to a text file. For example, you could save it to a file named OD4BAssignSCA.txt.</span></span>

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. <span data-ttu-id="51707-p109">編輯下列變數中的指令碼檔案開頭並使用專屬於貴組織的資訊。下列範例假設您組織的網域名稱是 contoso.onmicrosoft.com。請務必環繞含有雙引號變數的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="51707-p109">Edit the following variables in the beginning of the script file, and use information that's specific to your organization. The following examples assume that the domain name of your organization is contoso.onmicrosoft.com. Be sure to surround the values for the variables with double-quotation marks (" ").</span></span>
    
    - <span data-ttu-id="51707-145">**$AdminURI** -這會指定之 URI 的 SharePoint Online 的管理服務，例如`"https://contoso-admin.sharepoint.com"`。</span><span class="sxs-lookup"><span data-stu-id="51707-145">**$AdminURI** - This specifies the URI for your SharePoint Online admin service, for example,  `"https://contoso-admin.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="51707-146">**$AdminAccount** -這會指定全域管理員帳戶的 Office 365 組織，例如`"admin@contoso.onmicrosoft.com"`。</span><span class="sxs-lookup"><span data-stu-id="51707-146">**$AdminAccount** - This specifies a global administrator account in your Office 365 organization, for example,  `"admin@contoso.onmicrosoft.com"`.</span></span>
    
    - <span data-ttu-id="51707-147">**$eDiscoveryUser** -這會指定系統管理員的使用者帳戶或規範 manager 將被指派為每個 OneDrive for Business 網站組織中的網站集合管理員例如`"annb@contoso.onmicrosoft.com"`。</span><span class="sxs-lookup"><span data-stu-id="51707-147">**$eDiscoveryUser** - This specifies the user account of an administrator or compliance manager who will be assigned as a site collection administrator for every OneDrive for Business site in your organization, for example,  `"annb@contoso.onmicrosoft.com"`.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="51707-148">變更 **$eDiscoveryUser**變數所指定的使用者帳戶並重新執行指令碼，以指派不同的使用者作為網站集合管理員 OneDrive for Business **$MySiteListFile**變數所指定的網站。</span><span class="sxs-lookup"><span data-stu-id="51707-148">Change the user account specified by the **$eDiscoveryUser** variable and re-run the script to assign a different user as a site collection administrator to the OneDrive for Business sites that are specified by the **$MySiteListFile** variable.</span></span> 
  
    - <span data-ttu-id="51707-p110">**$MySitePrefix**這會指定您組織的我的網站網域的 URL。這是例如包含所有 OneDrive for Business 網站組織中的網域`"https://contoso-my.sharepoint.com"`。</span><span class="sxs-lookup"><span data-stu-id="51707-p110">**$MySitePrefix**This specifies the URL for your organization's MySite domain. This is the domain that contains all the OneDrive for Business sites in your organization, for example,  `"https://contoso-my.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="51707-p111">**$MySiteListFile**這會指定您在步驟 1 中建立的文字檔案的完整路徑。這個檔案包含您的組織中的商務網站的 OneDrive 清單例如`'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`。請務必環繞單一引號的此變數的值 (' ')。請注意您應該指定您在步驟 1 中儲存到文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="51707-p111">**$MySiteListFile**This specifies the full path of the text file that you created in Step 1. This file contains a list of OneDrive for Business sites in your organization, for example,  `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Be sure to surround the value for this variable with single-quotation marks (' '). Note that you should specify the location that you saved the text file to in Step 1.</span></span>
    
3. <span data-ttu-id="51707-p112">變更檔名尾碼為 .ps1，將文字檔儲存為 PowerShell 指令碼檔案。例如，儲存 OD4BAssignSCA.txt 檔案為 OD4BAssignSCA.ps1。</span><span class="sxs-lookup"><span data-stu-id="51707-p112">Save the text file as a PowerShell script file by changing the file name suffix to .ps1. For example, save the file OD4BAssignSCA.txt as OD4BAssignSCA.ps1.</span></span>
    
4. <span data-ttu-id="51707-157">在 SharePoint Online 管理命令介面中，移至前一步驟建立之 PowerShell 指令碼的所在資料夾，然後執行指令碼，例如：</span><span class="sxs-lookup"><span data-stu-id="51707-157">In SharePoint Online Management Shell, go to the folder that contains the PowerShell script that you created in the previous step, and then run the script, for example:</span></span>
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    <span data-ttu-id="51707-p113">系統會提示您輸入指令碼中所指定的系統管理員帳戶的密碼。如果指令碼執行成功，郵件`"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"`會顯示每個 OneDrive for Business 網站 **$MySiteListFile**所指定輸入檔案中所列出的。</span><span class="sxs-lookup"><span data-stu-id="51707-p113">You will be prompted to enter the password for the administrator account that you specified in the script. If the script runs successfully, the message `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` is displayed for each OneDrive for Business site that's listed in the input file specified by **$MySiteListFile**.</span></span>

## <a name="more-information"></a><span data-ttu-id="51707-160">其他資訊</span><span class="sxs-lookup"><span data-stu-id="51707-160">More information</span></span>

- <span data-ttu-id="51707-p114">您在步驟 3 中執行的指令碼使用**組 SPOUser**指令程式將指定的使用者作為網站集合管理員指派給每個 OneDrive for Business 傳回會列在 **$MySiteListFile**變數所指定的檔案。如果您有很大的組織使用千分位的使用者，請考慮下列 cmdlet 以方便管理指派的 eDiscovery 權限。</span><span class="sxs-lookup"><span data-stu-id="51707-p114">The script that you ran in Step 3 uses the **Set-SPOUser** cmdlet to assign the specified user as a site collection administrator to every OneDrive for Business that's listed in the file specified by the **$MySiteListFile** variable. If you have a very large organization with thousands of users, consider doing the following to make it easier to manage assigning eDiscovery permissions.</span></span> 
    
  - <span data-ttu-id="51707-163">編輯您在該清單所在 of OneDrive for Business 的網站，使其包含的網站使用者的使用中的法律案例相關的步驟 1 中建立的檔案。</span><span class="sxs-lookup"><span data-stu-id="51707-163">Edit the file that you created in Step 1 that contains the list of OneDrive for Business sites so that it includes only the sites for users are that are involved in active legal cases.</span></span>
    
  - <span data-ttu-id="51707-p115">將權限指派給不超過 2500 OneDrive for Business 網站每日。例如，假設您組織中有 10000 OneDrive for Business 的網站。您無法在收集所有網站的步驟 1 中建立清單。然後您可以使用該檔案來建立四個各含 2500 使用者的檔案。在第一天中，您會先 2500 OneDrive for Business 網站指派權限的步驟 3 中執行指令碼。第二個的日期，您將接著 2500 onedrive for Business 網站執行指令碼等等。</span><span class="sxs-lookup"><span data-stu-id="51707-p115">Assign permissions to no more than 2,500 OneDrive for Business sites per day. For example, let's say you have 10,000 OneDrive for Business sites in your organization. You could create the list in Step 1 to collect all the sites. Then you could use that file to create four files that each contain 2,500 users. On the first day, you would run the script in Step 3 to assign permissions to the first 2,500 OneDrive for Business sites. On the second day, you would run the script for the next 2,500 OneDrive for Business sites, and so on.</span></span>
    
- <span data-ttu-id="51707-p116">保留記錄的 OneDrive for Business 已指派 eDiscovery 權限和指派為網站集合管理員之使用者的網站。例如指派權限之後，您可以儲存包含清單的 OneDrive for Business 網站的文字檔案並將一條線新增至其識別被指派為網站集合管理員的使用者。</span><span class="sxs-lookup"><span data-stu-id="51707-p116">Keep a record of the OneDrive for Business sites that were assigned eDiscovery permissions and the user who is assigned as the site collection administrator. For example, after you assign permissions, you can save the text file that contains the list of OneDrive for Business sites and add a line to it that identifies the user who is assigned as the site collection administrator.</span></span>
    
- <span data-ttu-id="51707-p117">使用者可以檢視其 OneDrive for Business 網站的網站集合 administators 清單。因為使用者自己 OneDrive for Business 網站的網站集合管理員，他們可以移除網站集合管理員。請考慮下列 cmdlet 以減輕移除指定 eDiscovery 權限給 OneDrive for Business 的網站之使用者的使用者的機會。</span><span class="sxs-lookup"><span data-stu-id="51707-p117">Users can view the list of site collection administators for their OneDrive for Business site. Because users are site collection administrator for their own OneDrive for Business site, they can remove site collection administrators. Consider doing the following to mitigate the chance of users removing the user who is assigned eDiscovery permissions to OneDrive for Business sites.</span></span>
    
  - <span data-ttu-id="51707-175">通訊的 eDiscovery 及規範用途法務已指派為網站集合管理員 OneDrive 貴組織中的商務網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="51707-175">Communicate to users that for eDiscovery and compliance purposes, a compliance officer has been assigned as a site collection administrator to OneDrive for Business sites in your organization.</span></span>
    
  - <span data-ttu-id="51707-176">重新執行指令碼步驟 3 中，如有必要，將使用者重新指派為網站集合管理員的 OneDrive for Business 的網站。</span><span class="sxs-lookup"><span data-stu-id="51707-176">Re-run the script in Step 3, if necessary, to re-assign a user as the site collection administrator for OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="51707-p118">您也可以使用您在步驟 3 中執行的指令碼為網站集合管理員移除使用者的 OneDrive for Business 的網站。若要移除的使用者作為網站集合管理員，您必須從變更 （鄰近的指令碼的結尾） 的下列命令：</span><span class="sxs-lookup"><span data-stu-id="51707-p118">You can also use the script that you ran in Step 3 to remove a user as the site collection administrator from OneDrive for Business sites. To remove a user as a site collection administrator, you have to change the following command (near the end of the script) from:</span></span> 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    <span data-ttu-id="51707-179">變更為：</span><span class="sxs-lookup"><span data-stu-id="51707-179">to:</span></span>
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    <span data-ttu-id="51707-180">您也可以將指令碼中的這一行：</span><span class="sxs-lookup"><span data-stu-id="51707-180">You can also change the following line in the script from:</span></span>

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    <span data-ttu-id="51707-181">變更為：</span><span class="sxs-lookup"><span data-stu-id="51707-181">to:</span></span>
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    <span data-ttu-id="51707-182">進行這些變更後，使用不同的名稱，例如 OD4BRemoveSCA.ps1、 儲存指令碼，然後用它來移除使用者作為網站集合管理員群組中的 OneDrive 商務網站。</span><span class="sxs-lookup"><span data-stu-id="51707-182">After you make these changes, save the script with a different name, such as OD4BRemoveSCA.ps1, and then use it to remove a user as a site collection administrator from a group of OneDrive for Business sites.</span></span>
