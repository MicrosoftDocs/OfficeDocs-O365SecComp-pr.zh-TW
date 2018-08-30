---
title: 建立 DLP 原則來保護具有 FCI 或其他內容的文件
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: 1b9e3c6c-4308-4a20-b11e-c37b8013e177
description: 許多組織已識別及分類敏感資訊是使用分類屬性在 Windows Server 檔案分類基礎結構 (FCI)、 SharePoint 中的文件屬性或文件屬性中的程序套用的協力廠商系統。如果此說明您的組織，您可以建立的 DLP 原則可辨識屬性已由 Windows Server FCI 或其他系統，套用至文件以便 DLP 原則可以在 Office 文件與特定 FCI 或其他強制執行 Office 365 中屬性的值。
ms.openlocfilehash: 057cdad981249e39d6f39f231d8d60ab977e717a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013687"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>建立 DLP 原則來保護具有 FCI 或其他內容的文件

在 Office 365 中，您可以使用資料外洩防護 (DLP) 原則來識別、監視和保護敏感資訊。許多組織都已有其程序，可使用 Windows Server 檔案分類基礎結構 (FCI) 中的分類屬性、SharePoint 中的文件屬性或協力廠商系統所套用的文件屬性，來識別和分類敏感資訊。如果您的組織也是如此，您可以在 Office 365 中建立 DLP 原則來辨識由 Windows Server FCI 或其他系統已套用至文件的屬性，讓 DLP 原則可以強制執行於使用特定 FCI 或其他屬性值的 Office 文件上。
  
![圖表顯示 Office 365 及外部的分類系統](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
例如您的組織可能會使用 Windows Server FCI 使用社會安全編號，例如的個人識別資訊 (PII) 來識別文件，然後用來分類藉由設定**個人身分資訊**以**高**、**中等**、**低**、**公用**或**不 PII**屬性會根據類型和文件中找到的 PII 次數。在 Office 365 中，您可以建立的 DLP 原則識別該屬性設定為 **[高**] 和 [**中等**特定值的文件，然後採取動作例如封鎖存取這些檔案。將相同的原則可以有另一個採用不同的動作如果屬性設定為 [**低**，例如傳送的電子郵件通知的規則。如此一來，在 Office 365 中的 DLP 會與 Windows Server FCI 整合並可協助保護 Office 文件上傳或共用 Office 365 的 Windows Server 為基礎的檔案伺服器。
  
DLP 原則只會尋找特定的屬性名稱/值組。可以使用任何文件屬性，只要有 SharePoint 搜尋的對應的 managed 的屬性的屬性。例如 SharePoint 網站集合可能會使用名為必要欄位名為**客戶****來回報表**內容類型。每當人員會建立來回報表，他們必須輸入客戶名稱。此屬性的名稱/值組也可用於 DLP 原則 — 例如，如果您要封鎖外部使用者的文件時也能存取 「**客戶**」 欄位包含**Contoso**規則。
  
請注意是否您想要將您的 DLP 原則套用至特定的 Office 365 標籤的內容，您應該不遵循的步驟。而是了解如何[使用做為條件 DLP 原則中的標籤](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。
  
## <a name="before-you-create-the-dlp-policy"></a>建立 DLP 原則之前

您可以使用 Windows Server FCI 屬性或其他屬性中的 DLP 原則之前，您需要在 SharePoint 管理中心內建立的 managed 的屬性。以下是為何。
  
範例
  
這是很重要的，因為 Office 365 中的 DLP 會使用搜尋編目程式來識別和分類網站上的敏感資訊，然後將此敏感資訊儲存在搜尋索引的安全區域。當您將文件上傳至 Office 365 時，SharePoint 會根據文件屬性自動建立編目屬性。但若要在 DLP 原則中使用 FCI 或其他屬性，該編目屬性必須對應至 Managed 屬性，使具有該屬性的內容保留在索引中。
  
如需有關搜尋和 managed 的屬性的詳細資訊，請參閱 ＜ [Manage SharePoint Online 中的搜尋結構描述](http://go.microsoft.com/fwlink/p/?LinkID=627454)。
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>步驟 1：將具有所需屬性的文件上傳至 Office 365

您必須先將上傳文件與您想要參考在 DLP 原則的屬性。Office 365 會偵測屬性，並自動從其建立編目的屬性。在下一個步驟中，您將建立的 managed 的屬性，然後將 managed 的屬性對應至此編目屬性。
  
### <a name="step-2-create-a-managed-property"></a>步驟 2：建立 Managed 屬性

1. 登入 Office 365 系統管理中心。
    
2. 在左導覽列中，選擇 [ **Admin 中心** \> **SharePoint**。您現在是在 SharePoint 系統管理中心。
    
3. 在左導覽列中，選擇 [**搜尋**\>在 [**搜尋管理**] 頁面上\>**管理搜尋結構描述**。
    
    ![SharePoint 系統管理中心的搜尋管理頁面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. 在 [ **Managed 屬性**] 頁面上\>**新增 Managed 屬性**。
    
    ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. 輸入屬性的名稱和描述。此名稱將會出現在您的 DLP 原則中。
    
6. **類型**，選擇 [**文字**]。 
    
7. 在 [**主要特性**、 選取**設定為可查詢**及**Retrievable**。
    
8. [**對應至編目屬性** \> **新增對應**。
    
9. 在 [**編目屬性選取項目**] 對話方塊中\>尋找和選取編目的屬性對應至 Windows Server FCI 屬性或 DLP 原則中要使用其他屬性\> **[確定]**。
    
    ![選取編目屬性對話方塊](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. 在頁面底部\> **[確定]**。
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>建立使用 FCI 屬性或其他屬性的 DLP 原則

在這個範例中，組織已在其 Windows Server 為基礎的檔案伺服器 ； 使用 FCI尤其他們所使用且可能的值為**High**、**中等**、**低**、**公用**和**不 PII**名為**個人身分資訊**之 FCI 分類屬性。現在要利用 Office 365 中其 DLP 原則中的其現有 FCI 分類。
  
首先，他們可以依照前述步驟在 SharePoint Online 中建立 Managed 屬性，而此屬性會對應至自動從 FCI 屬性建立的編目屬性。
  
接下來，他們建立這兩個規則同時使用**文件摘要資訊包含任何這些值**的條件 DLP 原則：
  
- **FCI PII 的內容-高]、 [設定一般**如果 FCI 分類屬性**個人身分資訊**等於**高**或**中等**並與組織外部人員共用文件的第一個規則限制存取文件。 
    
- **FCI PII 內容-低**第二個規則傳送通知給 FCI 分類屬性**個人身分資訊**等於**低**及文件的文件擁有者與組織外部人員共用。 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>使用 PowerShell 建立 DLP 原則

請注意**文件摘要資訊包含任何這些值**的條件為暫時無法提供的安全性 UI 中&amp;規範中心，但您仍然可以使用這種情況使用 PowerShell。您可以使用`New\Set\Get-DlpCompliancePolicy`指令程式來使用 DLP 原則，並使用`New\Set\Get-DlpComplianceRule`cmdlet 搭配`ContentPropertyContainsWords`參數來新增**文件摘要資訊包含任何這些值**的條件。
  
如需這些 cmdlet 的詳細資訊，請參閱[Office 365 安全性&amp;規範中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。
  
1. [連線至 Office 365 安全性&amp;規範中心使用遠端 PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用建立原則`New-DlpCompliancePolicy`。
    
    以下是建立套用至所有位置的 DLP 原則的 PowerShell 範例。
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. 建立使用上述兩個規則`New-DlpComplianceRule`，其中一項規則是**低**值，而其他規則是 [**高**] 和 [**中等**值。 
    
    以下是建立這兩個規則的 PowerShell 範例。請注意屬性名稱/值組會以雙引號括住，而且屬性名稱可以指定多個值以任何空格，以逗號分隔類似`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    請注意 Windows Server FCI 包含許多內建的屬性，包括在這個範例中所用的**個人識別資訊**。每個屬性的可能值可以是不同的每一個組織。**高**、**中等**和**低**值在這裡使用的僅限範例。您的組織，您可以檢視其可能的值與 Windows Server FCI 分類屬性在 Windows Server 為基礎的檔案伺服器上的檔案伺服器資源管理員。如需詳細資訊，請參閱 ＜ [Create 分類屬性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。
    
完成後，您的原則應該有兩個同時使用**文件摘要資訊包含任何這些值**條件的新規則。請注意此條件可將不會出現在 UI 中上述其他條件、 動作和設定將會出現。 
  
一項規則封鎖的存取權其中**個人身分資訊**屬性等於**高**或**中等**的內容。第二個規則傳送其中**個人身分資訊**屬性等於**低**內容的通知。
  
![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>建立 DLP 原則之後

執行前文各節中的步驟會建立快速地將偵測的 DLP 原則內容與該屬性，但只有在 （使內容編製索引） 新上傳的內容，或如果的內容舊但剛編輯 （以便將內容重新編製索引）.
  
若要在所有位置偵測具有該屬性的內容，您可以手動要求您的文件庫、網站或網站集合重新編製索引，使 DLP 原則可辨識具有該屬性的所有內容。在 SharePoint Online 中，內容會根據已定義的編目排程自動編目。編目程式會提取在上次編目後有所變更的內容，並更新索引。如果您在下一次排程的編目之前需要以 DLP 原則保護內容，您可以執行這些步驟。
  
> [!CAUTION]
> 重新編製索引的網站可能會造成巨大負載搜尋系統上。不要重新編製索引網站除非您的案例絕對需要。 
  
如需詳細資訊，請參閱[手動要求編目及重新編製索引的文件庫或清單的網站](http://go.microsoft.com/fwlink/p/?LinkID=627457)。
  
### <a name="re-index-a-site-optional"></a>為網站重新編製索引 (選用)

1. 在網站上，選擇 [**設定**（在右上方的齒輪圖示） \> **網站設定**。
    
2. 在 [**搜尋**] 下選擇**搜尋與離線可用性** \> **網站重新編製索引**。
    
## <a name="more-information"></a>其他資訊

- [資料外洩防護原則概觀](data-loss-prevention-policies.md)
    
- [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)
    
- [針對 DLP 原則傳送通知並顯示原則提示](use-notifications-and-policy-tips.md)
    
- [DLP 原則範本包含哪些內容](what-the-dlp-policy-templates-include.md)
    
- [敏感資訊類型詳細目錄](what-the-sensitive-information-types-look-for.md)
    

