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
# <a name="bulk-import-external-contacts-to-exchange-online"></a>大量匯入外部連絡人至 Exchange Online

**本文適用於系統管理員。您試圖匯入連絡人至您自己的信箱？請參閱[將連絡人匯入至 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
您的公司在 Exchange Online 中有大量您想要包含在共用的通訊錄 」 （也稱為全域通訊清單） 中的現有商務連絡人嗎？ 您要將外部連絡人新增為成員的通訊群組，如同您可以使用使用者貴公司內嗎？ 如果這樣，您可以使用 Exchange Online PowerShell 和 CSV （逗點分隔值） 檔案大量匯入外部連絡人 Exchange Online。 它是一個三步驟程序：
  
[步驟 1： 建立 CSV 檔案包含外部連絡人的相關資訊](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[步驟 2： 使用 PowerShell 建立外部連絡人](#step-2-create-the-external-contacts-with-powershell) 

[步驟 3： 將資訊新增至外部連絡人的屬性](#step-3-add-information-to-the-properties-of-the-external-contacts)

完成這些步驟來匯入連絡人之後，您可以執行這些額外的工作：
  
- [新增多個外部連絡人](#add-more-external-contacts)
  
- [隱藏共用的通訊錄中的外部連絡人](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>步驟 1： 建立 CSV 檔案包含外部連絡人的相關資訊

第一個步驟是建立 CSV 檔案，包含每個您想要匯入 Exchange Online 的外部連絡人的相關資訊。 
  
1. 將下列文字複製到 [記事本] 中的文字檔案並將其儲存到您的桌面為 CSV 檔使用.csv; 檔名尾碼例如，ExternalContacts.csv。
    
    > [!TIP]
    > 如果您的語言包含特殊字元 （例如**å**、 **ä**和瑞典文中的**文字，ö** ） 儲存 CSV 檔案以 utf-8 或其他 Unicode 編碼方式] 當您將檔案儲存在 [記事本]。 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    在第一列或標題列，在 CSV 檔列出屬性的匯入 Exchange Online 時所能使用的連絡人。 每個屬性名稱皆以逗號分隔。 標題列底下的每個資料列代表匯入單一外部連絡人的屬性值。 
    
    > [!NOTE]
    > 此文字會包含範例資料，您可以刪除。 但不刪除或變更第一個 （標題） 列。 它包含的所有外部連絡人屬性。 
  
2. 若要編輯的 CSV 檔案，因為它是更容易使用 Excel 編輯 CSV 檔案的 Microsoft Excel 中開啟 CSV 檔案。
    
3. 建立您想要匯入 Exchange Online 每個連絡人的資料列。 填入越多越好的儲存格。 這項資訊會顯示在每個連絡人的共用的通訊錄中。 
    
    > [!IMPORTANT]
    >  下列屬性 （也就是標頭列中的前四個項目），才能建立外部連絡人和必須填入 CSV 檔案中： **ExternalEmailAddress**、**名稱**、**名字**、**姓氏**。 您在步驟 2 中執行的 PowerShell 命令將會使用這些屬性的值來建立連絡人。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>步驟 2： 使用 PowerShell 建立外部連絡人

下一個步驟是使用您在步驟 1 建立的 CSV 檔案並 PowerShell 來大量匯入至 Exchange Online 的 CSV 檔案中所列的外部連絡人。 
  
1.  將 PowerShell 連線到 Exchange Online 組織。 如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。 請務必的使用者名稱和密碼使用 Office 365 全域系統管理員帳戶，當您連線至 Exchange Online PowerShell。 
    
2. 您將 PowerShell 連線到 Exchange Online 之後，請移至 [桌面] 資料夾，您在步驟 1; 儲存 CSV 檔案的所在例如`C:\Users\Administrator\desktop`。
    
3. 執行下列命令，以建立外部連絡人：

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    可能需要建立的新連絡人時，根據多少匯入一段時間。 命令完成時執行，PowerShell 會顯示所建立的新連絡人的清單。 
    
4. 若要檢視新的外部連絡人，請移至 Exchange 系統管理中心 (EAC) 中，，然後按一下 [**收件者** \> **連絡人**。 
    
    > [!TIP]
    > 如需連線至 EAC 中的指示，請參閱[Exchange 系統管理中心在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197)。 
  
5. 如有必要，請按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新清單，並查看已匯入外部連絡人。 
    
    匯入的連絡人會出現在 Outlook 和 outlook 網頁版中共用的通訊錄中。
    
    > [!NOTE]
    > 您也可以檢視 Microsoft 365 系統管理中心中的連絡人，移至 [**使用者** \> **連絡人**。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>步驟 3： 將資訊新增至外部連絡人的屬性

您在步驟 2 中執行命令之後，建立外部連絡人，但它們不包含任何連絡人] 或 [組織資訊，也就是從最大的 CSV 檔案中的儲存格的資訊。 這是因為當您建立新的外部連絡人時，會填入必要的屬性。 如果您不需要填入 CSV 檔案中的所有資訊，沒關係。 如果找不到，它不會加入。
  
1.  將 PowerShell 連線到 Exchange Online 組織。 如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
2. 移至您在步驟 1; 儲存 CSV 檔案的所在的桌面資料夾例如`C:\Users\Administrator\desktop`。
    
3. 執行下列兩個命令，以從 CSV 檔案中加入您在步驟 2 中建立外部連絡人的其他屬性。
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_參數可能會有問題。 如果 CSV 檔案中的儲存格是空白的您會收到錯誤，並沒有任何一個屬性的資訊會新增至連絡人。 如果您不需要指定主管，然後只刪除` -Manager $_.Manager `從舊的 PowerShell 命令。 
  
    同樣地，它可能需要更新的連絡人時，根據多少您匯入在步驟 1 中一段時間。 
    
4. 若要確認內容已新增至連絡人： 
    
1. In the EAC, go to **Recipients** \> **Contacts**.
    
2. 按一下連絡人，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)以顯示連絡人的內容。 
    
這就對了！ 使用者可以看到連絡人通訊錄 Outlook 中的其他資訊和網頁型 Outlook。
  
## <a name="add-more-external-contacts"></a>新增多個外部連絡人

您可以重複步驟 1 到步驟 3，將新的外部連絡人新增在 Exchange Online。 您或貴公司中的使用者只可以加入新的資料列中新的連絡人的 CSV 檔案。 然後您可以從建立，並將資訊新增至新的連絡人的 [步驟 2 和步驟 3 執行 PowerShell 命令。
  
> [!NOTE]
> 當您執行命令，以建立新的連絡人時，您可能會得到錯誤，指出先前已建立的連絡人存在。 但是建立任何新的連絡人新增至 CSV 檔案。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>隱藏共用地址 book> 從外部連絡人

某些公司可能會使用外部連絡人，只讓他們可以新增為通訊群組的成員。 在此案例中，他們可能會想要隱藏共用的通訊錄中的外部連絡人。 方法如下：
  
1.  將 PowerShell 連線到 Exchange Online 組織。 如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
2. 若要隱藏單一外部連絡人，請執行下列命令。
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    例如，若要從共用的通訊錄中隱藏 Pilar Pinilla，執行此命令：

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. 若要隱藏共用的通訊錄中的所有外部連絡人，請執行下列命令：

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

隱藏這些之後，外部連絡人不會顯示在共用的通訊錄中，但您可以仍將其新增為通訊群組的成員。
