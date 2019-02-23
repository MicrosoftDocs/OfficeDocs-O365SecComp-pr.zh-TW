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
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Exchange online 大量匯入外部連絡人

**本文適用於系統管理員。您嘗試連絡人匯入到您自己的信箱吗？請參閱[匯入 Outlook 連絡人](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
貴公司 Exchange Online 中有許多您想要包含在共用的通訊錄 （也稱為全域通訊清單） 中的現有商務連絡人嗎？您是否要將外部連絡人加入為成員的通訊群組，就像您可以使用使用者公司內部吗？若如此，您可以使用 Exchange Online PowerShell 和 CSV （逗點分隔值） 檔案以大量匯入外部連絡人 Exchange Online。它是三個步驟的程序：
  
[步驟 1： 建立包含外部連絡人的相關資訊的 CSV 檔案](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[步驟 2： 使用 PowerShell 建立外部連絡人](#step-2-create-the-external-contacts-with-powershell) 

[步驟 3： 將資訊新增至外部連絡人的屬性](#step-3-add-information-to-the-properties-of-the-external-contacts)

完成下列步驟來匯入連絡人之後，您可以執行這些額外的工作：
  
- [新增多個外部連絡人](bulk-import-external-contacts.md#AddMore)
  
- [隱藏共用的通訊錄中的外部連絡人](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>步驟 1： 建立包含外部連絡人的相關資訊的 CSV 檔案

第一個步驟是建立包含您想要匯入 Exchange Online 每個外部連絡人的相關資訊的 CSV 檔案。 
  
1. 將下列文字複製到 [記事本] 中的文字檔案並將其儲存到您的桌面為 CSV 檔案使用.csv; filename 尾碼例如，ExternalContacts.csv。
    
    > [!TIP]
    > 如果您的語言包含特殊字元 （例如**å**、 **ä**、 及瑞典文中的**ö** ） 儲存 CSV 檔案以 utf-8 或其他 Unicode 編碼方式將檔案儲存在 [記事本]。 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    第一列或欄位名稱] 列的 CSV 檔案列出可用於匯入 Exchange Online 時的連絡人的屬性。每個屬性名稱是以逗號分隔。標頭列] 下方的每一個資料列代表匯入單一外部連絡人的屬性值。 
    
    > [!NOTE]
    > 此文字包含範例資料，您可以刪除。但不刪除或變更第一個 （標題） 列。包含的所有外部連絡人的屬性。 
  
2. 若要編輯的 CSV 檔案很容易編輯 CSV 檔案中使用 Excel 的 Microsoft Excel 中開啟的 CSV 檔案。
    
3. 建立您想要匯入 Exchange Online 每位連絡人的資料列。填入數量儘可能的儲存格。這項資訊將會顯示在共用的通訊錄每位連絡人。 
    
    > [!IMPORTANT]
    >  下列屬性 （亦即標題列中的前四個項目） 所建立的外部連絡人與必須填入 CSV 檔中： **ExternalEmailAddress**、**名稱**、**名字**、**姓氏**。您在步驟 2 中執行的 PowerShell 命令將會使用這些屬性的值來建立連絡人。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>步驟 2： 使用 PowerShell 建立外部連絡人

下一個步驟是使用您在步驟 1 中建立 CSV 檔案和 PowerShell 大量匯入至 Exchange Online 的 CSV 檔案中所列的外部連絡人。 
  
1.  將 PowerShell 連線到 Exchange Online 組織。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。請務必使用的使用者名稱和密碼您的 Office 365 全域管理員帳戶連線至 Exchange Online PowerShell 時。 
    
2. 將 PowerShell 連線至 Exchange Online 後，移至 [桌面] 資料夾在步驟 1; 中所儲存的 CSV 檔案的位置例如`C:\Users\Administrator\desktop`。
    
3. 執行下列命令來建立外部連絡人：

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    可能需要建立新的連絡人，根據多少您正在匯入一段。此命令完成時執行，PowerShell 會顯示所建立的新連絡人清單。 
    
4. 若要檢視新的外部連絡人，請移至 Exchange 系統管理中心 (EAC) 和 [**收件者** \> **連絡人**。 
    
    > [!TIP]
    > 連線至 EAC 中的指示，請參閱[Exchange admin 中心在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197)。 
  
5. 若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)更新清單，然後查看已匯入外部連絡人。 
    
    匯入的連絡人會出現在 Outlook 和 Outlook web 上共用的通訊錄中。
    
    > [!NOTE]
    > 您也可以檢視 Office 365 系統管理中心的連絡人，移至**使用者** \> **連絡人**。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>步驟 3： 將資訊新增至外部連絡人的屬性

您在步驟 2 中執行此命令後，建立外部連絡人，但它們不含任何連絡人或組織資訊，這是從 CSV 檔案中的儲存格的最高的資訊。這是因為當您建立新的外部連絡人時，會填入必要的屬性。如果，擔心您不需要填入 CSV 檔案中的所有資訊。如果不存在，它將不會加入。
  
1.  將 PowerShell 連線到 Exchange Online 組織。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 移至 [桌面] 資料夾在步驟 1; 中所儲存的 CSV 檔案的位置例如`C:\Users\Administrator\desktop`。
    
3. 執行下列兩個命令，以將其他屬性從 CSV 檔案新增至您在步驟 2 中建立外部連絡人。
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_參數可能有問題。如果 CSV 檔案中的儲存格為空白，您會收到的錯誤和無屬性資訊將新增至連絡人。如果您不需要指定 manager，然後只刪除` -Manager $_.Manager `從舊的 PowerShell 命令。 
  
    同樣地，可能需要一段時間來更新根據多少您匯入在步驟 1 中的連絡人。 
    
4. 若要確認已加入到連絡人的屬性： 
    
1. 在 EAC 中，移至 [**收件者** \> **連絡人**。
    
2. 按一下 [連絡人] 和 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)來顯示連絡人的屬性。 
    
這是它 ！使用者可以查看連絡人的 Outlook 通訊錄中的其他資訊和網路上的 Outlook。
  
## <a name="add-more-external-contacts"></a>新增多個外部連絡人

您可以重複執行步驟 1 到步驟 3 新增新的外部連絡人在 Exchange Online。您或公司內的使用者只可以新增新的資料列中的新連絡人的 CSV 檔案。然後您可以從建立及將資訊新增至新的連絡人的 [步驟 2 和步驟 3 執行 PowerShell 命令。
  
> [!NOTE]
> 當您執行命令以建立新連絡人時，您可能會收到預警先前已建立的連絡人所存在的錯誤。而是建立任何新的連絡人加入至 CSV 檔案。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>隱藏共用的位址 book> 從外部連絡人

有些公司可能會使用外部連絡人只能讓他們可以新增為通訊群組的成員。在此案例中，它們可能會想要隱藏共用的通訊錄中的外部連絡人。以下是如何：
  
1.  將 PowerShell 連線到 Exchange Online 組織。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 若要隱藏單一外部連絡人，請執行下列命令。
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    例如，若要隱藏共用的通訊錄中的 Pilar Pinilla，執行此命令：

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. 若要隱藏共用的通訊錄中的所有外部連絡人，請執行下列命令：

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

隱藏它們之後，外部連絡人未出現在共用的通訊錄，但您還是可以加入其為通訊群組的成員。
