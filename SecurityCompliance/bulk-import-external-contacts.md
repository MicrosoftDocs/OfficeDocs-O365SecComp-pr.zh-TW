---
title: 大量匯入外部連絡人至 Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 了解如何系統管理員可以使用 Exchange Online PowerShell 和 CSV 檔案大量匯入外部連絡人至全域通訊清單。
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152205"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="b1684-103">大量匯入外部連絡人至 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1684-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="b1684-104">**本文適用於系統管理員。您試圖匯入連絡人至您自己的信箱？請參閱[將連絡人匯入至 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="b1684-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="b1684-105">您的公司在 Exchange Online 中有大量您想要包含在共用的通訊錄 」 （也稱為全域通訊清單） 中的現有商務連絡人嗎？</span><span class="sxs-lookup"><span data-stu-id="b1684-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="b1684-106">您要將外部連絡人新增為成員的通訊群組，如同您可以使用使用者貴公司內嗎？</span><span class="sxs-lookup"><span data-stu-id="b1684-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="b1684-107">如果這樣，您可以使用 Exchange Online PowerShell 和 CSV （逗點分隔值） 檔案大量匯入外部連絡人 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b1684-107">If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="b1684-108">它是一個三步驟程序：</span><span class="sxs-lookup"><span data-stu-id="b1684-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="b1684-109">步驟 1： 建立 CSV 檔案包含外部連絡人的相關資訊</span><span class="sxs-lookup"><span data-stu-id="b1684-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="b1684-110">步驟 2： 使用 PowerShell 建立外部連絡人</span><span class="sxs-lookup"><span data-stu-id="b1684-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="b1684-111">步驟 3： 將資訊新增至外部連絡人的屬性</span><span class="sxs-lookup"><span data-stu-id="b1684-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="b1684-112">完成這些步驟來匯入連絡人之後，您可以執行這些額外的工作：</span><span class="sxs-lookup"><span data-stu-id="b1684-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="b1684-113">新增多個外部連絡人</span><span class="sxs-lookup"><span data-stu-id="b1684-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="b1684-114">隱藏共用的通訊錄中的外部連絡人</span><span class="sxs-lookup"><span data-stu-id="b1684-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="b1684-115">步驟 1： 建立 CSV 檔案包含外部連絡人的相關資訊</span><span class="sxs-lookup"><span data-stu-id="b1684-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="b1684-116">第一個步驟是建立 CSV 檔案，包含每個您想要匯入 Exchange Online 的外部連絡人的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b1684-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="b1684-117">將下列文字複製到 [記事本] 中的文字檔案並將其儲存到您的桌面為 CSV 檔使用.csv; 檔名尾碼例如，ExternalContacts.csv。</span><span class="sxs-lookup"><span data-stu-id="b1684-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b1684-118">如果您的語言包含特殊字元 （例如**å**、 **ä**和瑞典文中的**文字，ö** ） 儲存 CSV 檔案以 utf-8 或其他 Unicode 編碼方式] 當您將檔案儲存在 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="b1684-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="b1684-119">在第一列或標題列，在 CSV 檔列出屬性的匯入 Exchange Online 時所能使用的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b1684-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="b1684-120">每個屬性名稱皆以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="b1684-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="b1684-121">標題列底下的每個資料列代表匯入單一外部連絡人的屬性值。</span><span class="sxs-lookup"><span data-stu-id="b1684-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b1684-122">此文字會包含範例資料，您可以刪除。</span><span class="sxs-lookup"><span data-stu-id="b1684-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="b1684-123">但不刪除或變更第一個 （標題） 列。</span><span class="sxs-lookup"><span data-stu-id="b1684-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="b1684-124">它包含的所有外部連絡人屬性。</span><span class="sxs-lookup"><span data-stu-id="b1684-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="b1684-125">若要編輯的 CSV 檔案，因為它是更容易使用 Excel 編輯 CSV 檔案的 Microsoft Excel 中開啟 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b1684-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="b1684-126">建立您想要匯入 Exchange Online 每個連絡人的資料列。</span><span class="sxs-lookup"><span data-stu-id="b1684-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="b1684-127">填入越多越好的儲存格。</span><span class="sxs-lookup"><span data-stu-id="b1684-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="b1684-128">這項資訊會顯示在每個連絡人的共用的通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="b1684-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="b1684-129">下列屬性 （也就是標頭列中的前四個項目），才能建立外部連絡人和必須填入 CSV 檔案中： **ExternalEmailAddress**、**名稱**、**名字**、**姓氏**。</span><span class="sxs-lookup"><span data-stu-id="b1684-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="b1684-130">您在步驟 2 中執行的 PowerShell 命令將會使用這些屬性的值來建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="b1684-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="b1684-131">步驟 2： 使用 PowerShell 建立外部連絡人</span><span class="sxs-lookup"><span data-stu-id="b1684-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="b1684-132">下一個步驟是使用您在步驟 1 建立的 CSV 檔案並 PowerShell 來大量匯入至 Exchange Online 的 CSV 檔案中所列的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="b1684-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="b1684-133">將 PowerShell 連線到 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="b1684-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="b1684-134">如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="b1684-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="b1684-135">請務必的使用者名稱和密碼使用 Office 365 全域系統管理員帳戶，當您連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1684-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="b1684-136">您將 PowerShell 連線到 Exchange Online 之後，請移至 [桌面] 資料夾，您在步驟 1; 儲存 CSV 檔案的所在例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="b1684-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="b1684-137">執行下列命令，以建立外部連絡人：</span><span class="sxs-lookup"><span data-stu-id="b1684-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="b1684-138">可能需要建立的新連絡人時，根據多少匯入一段時間。</span><span class="sxs-lookup"><span data-stu-id="b1684-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="b1684-139">命令完成時執行，PowerShell 會顯示所建立的新連絡人的清單。</span><span class="sxs-lookup"><span data-stu-id="b1684-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="b1684-140">若要檢視新的外部連絡人，請移至 Exchange 系統管理中心 (EAC) 中，，然後按一下 [**收件者** \> **連絡人**。</span><span class="sxs-lookup"><span data-stu-id="b1684-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b1684-141">如需連線至 EAC 中的指示，請參閱[Exchange 系統管理中心在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197)。</span><span class="sxs-lookup"><span data-stu-id="b1684-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="b1684-142">如有必要，請按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新清單，並查看已匯入外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="b1684-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="b1684-143">匯入的連絡人會出現在 Outlook 和 outlook 網頁版中共用的通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="b1684-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b1684-144">您也可以檢視 Microsoft 365 系統管理中心中的連絡人，移至 [**使用者** \> **連絡人**。</span><span class="sxs-lookup"><span data-stu-id="b1684-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="b1684-145">步驟 3： 將資訊新增至外部連絡人的屬性</span><span class="sxs-lookup"><span data-stu-id="b1684-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="b1684-146">您在步驟 2 中執行命令之後，建立外部連絡人，但它們不包含任何連絡人] 或 [組織資訊，也就是從最大的 CSV 檔案中的儲存格的資訊。</span><span class="sxs-lookup"><span data-stu-id="b1684-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file.</span></span> <span data-ttu-id="b1684-147">這是因為當您建立新的外部連絡人時，會填入必要的屬性。</span><span class="sxs-lookup"><span data-stu-id="b1684-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="b1684-148">如果您不需要填入 CSV 檔案中的所有資訊，沒關係。</span><span class="sxs-lookup"><span data-stu-id="b1684-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="b1684-149">如果找不到，它不會加入。</span><span class="sxs-lookup"><span data-stu-id="b1684-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="b1684-150">將 PowerShell 連線到 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="b1684-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="b1684-151">如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="b1684-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="b1684-152">移至您在步驟 1; 儲存 CSV 檔案的所在的桌面資料夾例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="b1684-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="b1684-153">執行下列兩個命令，以從 CSV 檔案中加入您在步驟 2 中建立外部連絡人的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="b1684-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="b1684-154">_Manager_參數可能會有問題。</span><span class="sxs-lookup"><span data-stu-id="b1684-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="b1684-155">如果 CSV 檔案中的儲存格是空白的您會收到錯誤，並沒有任何一個屬性的資訊會新增至連絡人。</span><span class="sxs-lookup"><span data-stu-id="b1684-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="b1684-156">如果您不需要指定主管，然後只刪除` -Manager $_.Manager `從舊的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="b1684-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="b1684-157">同樣地，它可能需要更新的連絡人時，根據多少您匯入在步驟 1 中一段時間。</span><span class="sxs-lookup"><span data-stu-id="b1684-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="b1684-158">若要確認內容已新增至連絡人：</span><span class="sxs-lookup"><span data-stu-id="b1684-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="b1684-159">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="b1684-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="b1684-160">按一下連絡人，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)以顯示連絡人的內容。</span><span class="sxs-lookup"><span data-stu-id="b1684-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="b1684-161">這就對了！</span><span class="sxs-lookup"><span data-stu-id="b1684-161">That's it!</span></span> <span data-ttu-id="b1684-162">使用者可以看到連絡人通訊錄 Outlook 中的其他資訊和網頁型 Outlook。</span><span class="sxs-lookup"><span data-stu-id="b1684-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="b1684-163">新增多個外部連絡人</span><span class="sxs-lookup"><span data-stu-id="b1684-163">Add more external contacts</span></span>

<span data-ttu-id="b1684-164">您可以重複步驟 1 到步驟 3，將新的外部連絡人新增在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b1684-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="b1684-165">您或貴公司中的使用者只可以加入新的資料列中新的連絡人的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b1684-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="b1684-166">然後您可以從建立，並將資訊新增至新的連絡人的 [步驟 2 和步驟 3 執行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="b1684-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1684-167">當您執行命令，以建立新的連絡人時，您可能會得到錯誤，指出先前已建立的連絡人存在。</span><span class="sxs-lookup"><span data-stu-id="b1684-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="b1684-168">但是建立任何新的連絡人新增至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b1684-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="b1684-169">隱藏共用地址 book> 從外部連絡人</span><span class="sxs-lookup"><span data-stu-id="b1684-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="b1684-170">某些公司可能會使用外部連絡人，只讓他們可以新增為通訊群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b1684-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="b1684-171">在此案例中，他們可能會想要隱藏共用的通訊錄中的外部連絡人。</span><span class="sxs-lookup"><span data-stu-id="b1684-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="b1684-172">方法如下：</span><span class="sxs-lookup"><span data-stu-id="b1684-172">Here's how:</span></span>
  
1.  <span data-ttu-id="b1684-173">將 PowerShell 連線到 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="b1684-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="b1684-174">如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="b1684-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="b1684-175">若要隱藏單一外部連絡人，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b1684-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="b1684-176">例如，若要從共用的通訊錄中隱藏 Pilar Pinilla，執行此命令：</span><span class="sxs-lookup"><span data-stu-id="b1684-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="b1684-177">若要隱藏共用的通訊錄中的所有外部連絡人，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b1684-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="b1684-178">隱藏這些之後，外部連絡人不會顯示在共用的通訊錄中，但您可以仍將其新增為通訊群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b1684-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
