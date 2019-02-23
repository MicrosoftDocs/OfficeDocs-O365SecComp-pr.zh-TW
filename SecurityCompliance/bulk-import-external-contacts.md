---
title: Exchange online 大量匯入外部連絡人
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 了解如何系統管理員可以使用 Exchange Online PowerShell 及 CSV 檔案大量匯入全域通訊清單的外部連絡人。
ms.openlocfilehash: a38565d5cbff61a954914bf156fb1bac0814c815
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215913"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="3bca3-103">Exchange online 大量匯入外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="3bca3-104">**本文適用於系統管理員。您嘗試連絡人匯入到您自己的信箱吗？請參閱[匯入 Outlook 連絡人](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="3bca3-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="3bca3-p101">貴公司 Exchange Online 中有許多您想要包含在共用的通訊錄 （也稱為全域通訊清單） 中的現有商務連絡人嗎？您是否要將外部連絡人加入為成員的通訊群組，就像您可以使用使用者公司內部吗？若如此，您可以使用 Exchange Online PowerShell 和 CSV （逗點分隔值） 檔案以大量匯入外部連絡人 Exchange Online。它是三個步驟的程序：</span><span class="sxs-lookup"><span data-stu-id="3bca3-p101">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online? Do you want to add external contacts as members of distribution groups, just like you can with users inside your company? If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online. It's a three-step process:</span></span>
  
[<span data-ttu-id="3bca3-109">步驟 1： 建立包含外部連絡人的相關資訊的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="3bca3-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="3bca3-110">步驟 2： 使用 PowerShell 建立外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="3bca3-111">步驟 3： 將資訊新增至外部連絡人的屬性</span><span class="sxs-lookup"><span data-stu-id="3bca3-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="3bca3-112">完成下列步驟來匯入連絡人之後，您可以執行這些額外的工作：</span><span class="sxs-lookup"><span data-stu-id="3bca3-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="3bca3-113">新增多個外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-113">Add more external contacts</span></span>](bulk-import-external-contacts.md#AddMore)
  
- [<span data-ttu-id="3bca3-114">隱藏共用的通訊錄中的外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-114">Hide external contacts from the shared address book</span></span>](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="3bca3-115">步驟 1： 建立包含外部連絡人的相關資訊的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="3bca3-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="3bca3-116">第一個步驟是建立包含您想要匯入 Exchange Online 每個外部連絡人的相關資訊的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="3bca3-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="3bca3-117">將下列文字複製到 [記事本] 中的文字檔案並將其儲存到您的桌面為 CSV 檔案使用.csv; filename 尾碼例如，ExternalContacts.csv。</span><span class="sxs-lookup"><span data-stu-id="3bca3-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3bca3-118">如果您的語言包含特殊字元 （例如**å**、 **ä**、 及瑞典文中的**ö** ） 儲存 CSV 檔案以 utf-8 或其他 Unicode 編碼方式將檔案儲存在 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="3bca3-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="3bca3-p102">第一列或欄位名稱] 列的 CSV 檔案列出可用於匯入 Exchange Online 時的連絡人的屬性。每個屬性名稱是以逗號分隔。標頭列] 下方的每一個資料列代表匯入單一外部連絡人的屬性值。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p102">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online. Each property name is separated by a comma. Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3bca3-p103">此文字包含範例資料，您可以刪除。但不刪除或變更第一個 （標題） 列。包含的所有外部連絡人的屬性。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p103">This text includes sample data, which you can delete. But don't delete or change the first (header) row. It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="3bca3-125">若要編輯的 CSV 檔案很容易編輯 CSV 檔案中使用 Excel 的 Microsoft Excel 中開啟的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="3bca3-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="3bca3-p104">建立您想要匯入 Exchange Online 每位連絡人的資料列。填入數量儘可能的儲存格。這項資訊將會顯示在共用的通訊錄每位連絡人。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p104">Create a row for each contact that you want to import to Exchange Online. Populate as many of the cells as possible. This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="3bca3-p105">下列屬性 （亦即標題列中的前四個項目） 所建立的外部連絡人與必須填入 CSV 檔中： **ExternalEmailAddress**、**名稱**、**名字**、**姓氏**。您在步驟 2 中執行的 PowerShell 命令將會使用這些屬性的值來建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p105">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="3bca3-131">步驟 2： 使用 PowerShell 建立外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="3bca3-132">下一個步驟是使用您在步驟 1 中建立 CSV 檔案和 PowerShell 大量匯入至 Exchange Online 的 CSV 檔案中所列的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="3bca3-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="3bca3-p106">將 PowerShell 連線到 Exchange Online 組織。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。請務必使用的使用者名稱和密碼您的 Office 365 全域管理員帳戶連線至 Exchange Online PowerShell 時。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p106">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="3bca3-136">將 PowerShell 連線至 Exchange Online 後，移至 [桌面] 資料夾在步驟 1; 中所儲存的 CSV 檔案的位置例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="3bca3-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="3bca3-137">執行下列命令來建立外部連絡人：</span><span class="sxs-lookup"><span data-stu-id="3bca3-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="3bca3-p107">可能需要建立新的連絡人，根據多少您正在匯入一段。此命令完成時執行，PowerShell 會顯示所建立的新連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p107">It might take a while to create the new contacts, depending on how many you're importing. When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="3bca3-140">若要檢視新的外部連絡人，請移至 Exchange 系統管理中心 (EAC) 和 [**收件者** \> **連絡人**。</span><span class="sxs-lookup"><span data-stu-id="3bca3-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3bca3-141">連線至 EAC 中的指示，請參閱[Exchange admin 中心在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197)。</span><span class="sxs-lookup"><span data-stu-id="3bca3-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="3bca3-142">若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)更新清單，然後查看已匯入外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="3bca3-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="3bca3-143">匯入的連絡人會出現在 Outlook 和 Outlook web 上共用的通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="3bca3-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3bca3-144">您也可以檢視 Office 365 系統管理中心的連絡人，移至**使用者** \> **連絡人**。</span><span class="sxs-lookup"><span data-stu-id="3bca3-144">You can also view the contacts in the Office 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="3bca3-145">步驟 3： 將資訊新增至外部連絡人的屬性</span><span class="sxs-lookup"><span data-stu-id="3bca3-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="3bca3-p108">您在步驟 2 中執行此命令後，建立外部連絡人，但它們不含任何連絡人或組織資訊，這是從 CSV 檔案中的儲存格的最高的資訊。這是因為當您建立新的外部連絡人時，會填入必要的屬性。如果，擔心您不需要填入 CSV 檔案中的所有資訊。如果不存在，它將不會加入。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p108">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file. This is because when you create new external contacts, only the required properties are populated. Don't worry if you don't have all the information populated in the CSV file. If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="3bca3-p109">將 PowerShell 連線到 Exchange Online 組織。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p109">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="3bca3-152">移至 [桌面] 資料夾在步驟 1; 中所儲存的 CSV 檔案的位置例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="3bca3-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="3bca3-153">執行下列兩個命令，以將其他屬性從 CSV 檔案新增至您在步驟 2 中建立外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="3bca3-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="3bca3-p110">_Manager_參數可能有問題。如果 CSV 檔案中的儲存格為空白，您會收到的錯誤和無屬性資訊將新增至連絡人。如果您不需要指定 manager，然後只刪除` -Manager $_.Manager `從舊的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p110">The  _Manager_ parameter might be problematic. If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact. If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="3bca3-157">同樣地，可能需要一段時間來更新根據多少您匯入在步驟 1 中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="3bca3-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="3bca3-158">若要確認已加入到連絡人的屬性：</span><span class="sxs-lookup"><span data-stu-id="3bca3-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="3bca3-159">在 EAC 中，移至 [**收件者** \> **連絡人**。</span><span class="sxs-lookup"><span data-stu-id="3bca3-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="3bca3-160">按一下 [連絡人] 和 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)來顯示連絡人的屬性。</span><span class="sxs-lookup"><span data-stu-id="3bca3-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="3bca3-p111">這是它 ！使用者可以查看連絡人的 Outlook 通訊錄中的其他資訊和網路上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p111">That's it! Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="3bca3-163">新增多個外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-163">Add more external contacts</span></span>

<span data-ttu-id="3bca3-p112">您可以重複執行步驟 1 到步驟 3 新增新的外部連絡人在 Exchange Online。您或公司內的使用者只可以新增新的資料列中的新連絡人的 CSV 檔案。然後您可以從建立及將資訊新增至新的連絡人的 [步驟 2 和步驟 3 執行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p112">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online. You or users in your company can just add a new row in the CSV file for the new contact. Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bca3-p113">當您執行命令以建立新連絡人時，您可能會收到預警先前已建立的連絡人所存在的錯誤。而是建立任何新的連絡人加入至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p113">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist. But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="3bca3-169">隱藏共用的位址 book> 從外部連絡人</span><span class="sxs-lookup"><span data-stu-id="3bca3-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="3bca3-p114">有些公司可能會使用外部連絡人只能讓他們可以新增為通訊群組的成員。在此案例中，它們可能會想要隱藏共用的通訊錄中的外部連絡人。以下是如何：</span><span class="sxs-lookup"><span data-stu-id="3bca3-p114">Some companies may use external contacts only so they can be added as members of distribution groups. In this scenario, they may want to hide external contacts from the shared address book. Here's how:</span></span>
  
1.  <span data-ttu-id="3bca3-p115">將 PowerShell 連線到 Exchange Online 組織。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="3bca3-p115">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="3bca3-175">若要隱藏單一外部連絡人，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="3bca3-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="3bca3-176">例如，若要隱藏共用的通訊錄中的 Pilar Pinilla，執行此命令：</span><span class="sxs-lookup"><span data-stu-id="3bca3-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="3bca3-177">若要隱藏共用的通訊錄中的所有外部連絡人，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3bca3-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="3bca3-178">隱藏它們之後，外部連絡人未出現在共用的通訊錄，但您還是可以加入其為通訊群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3bca3-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
