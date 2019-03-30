---
title: 設定 Office 365 中電子文件探索調查的合規性界限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合規性界限來建立 Office 365 組織內控制電子文件探索管理員可搜尋的使用者內容位置的邏輯界限。 合規性界限使用搜尋權限篩選 （也稱為的法規安全性篩選器） 來控制哪些信箱、 SharePoint 網站，並可搜尋特定使用者的 OneDrive 帳戶。
ms.openlocfilehash: dc1cf770ab015ece5212d5257f1807596e0e36c7
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001086"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>設定 Office 365 中電子文件探索調查的合規性界限

合規性界限建立 Office 365 組織內控制的使用者內容位置 （例如信箱、 SharePoint 網站與 OneDrive 帳戶） 電子文件探索管理員可搜尋的邏輯界限。 此外，合規性界限控制可以存取用來管理法律、 人力資源或組織內其他調查的 eDiscovery 案例。 合規性界限的需求，通常會需要必須遵守地理退敵軍與法規，多重民族企業與政府，通常可分為不同的行政機關。 在 Office 365、 合規性界限協助您符合這些需求時執行內容搜尋和使用 eDiscovery 案例的管理調查。
  
我們將使用下列圖例中的範例，說明合規性界限的運作方式。
  
![合規性界限組成搜尋權限篩選器控制項存取行政機關和系統管理員角色群組 eDisocovery 的情況下，控制存取](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
在這個範例中，Contoso LTD 是 Fourth Coffee 和 Coho Winery 的兩個子公司所組成的 Office 365 組織。 業務需要，eDiscovery 管理員中和現場只能搜尋 Exchange 信箱、 OneDrive 帳戶，以及 SharePoint 網站中其機構。 此外，eDiscovery 主管和現場僅能看到中的 eDiscovery 案例中其 agency，以及它們只能存取他們所隸屬的情況。 以下是合規性界限如何符合這些需求。
  
- 篩選內容搜尋控制項中的功能可以搜尋 eDiscovery 主管和現場的內容位置搜尋權限。 這表示 eDiscovery 主管和現場 Fourth Coffee 機構中的只能搜尋內容位置中的 Fourth Coffee 子公司。 Coho Winery 子公司套用相同的限制。
    
    角色群組的控制可以看到安全性 & 合規性中心中的 eDiscovery 案例。 這表示，eDiscovery 主管和現場只能看到其機構中的 eDiscovery 案例。
    
- 角色群組也會控制誰可以指派至 eDiscovery 案例的成員。 這表示 eDiscovery 主管和現場可以只將成員指派給他們彼此之間是成員的情況下。
    
以下是設定合規性界限的程序：
  
[步驟 1： 識別來定義貴機構使用者屬性](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步驟 2： 將歸檔與 Microsoft 支援服務以同步處理至 OneDrive 帳戶的使用者屬性](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步驟 3： 建立每個代理程式的角色群組](#step-3-create-a-role-group-for-each-agency)

[步驟 4： 建立搜尋權限篩選器來強制執行的合規性界限](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步驟 5： 建立內機構調查的 eDiscovery 案例](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步驟 1： 識別來定義貴機構使用者屬性

第一個步驟是選擇要使用的 Azure Active Directory 屬性將會定義您行政機關。 此屬性會用來建立限制 eDiscovery 搜尋的權限篩選來搜尋使用者獲指派此屬性的特定值的內容位置的管理員。 例如，假設 Contoso 決定要使用的**部門**屬性。 為 Fourth Coffee 子公司中使用者的此屬性的值會是`FourthCoffee`和 Coho Winery 子公司中的使用者的值會是`CohoWinery`。 在 [步驟 4 中，您將使用此`attribute:value`以限制使用者對 (例如，*部門： FourthCoffee* ) 內容電子文件探索管理員可搜尋的位置。 
  
以下是您可以使用合規性界限的 Azure Active Directory 使用者屬性的清單：
  
- Company
    
- CustomAttribute1-CustomAttribute15
    
- 部門
    
- 辦公室
    
雖然多個使用者屬性可用，尤其是針對 Exchange 信箱，上面所列的屬性是目前支援 OneDrive 是唯一的。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步驟 2： 將歸檔與 Microsoft 支援服務以同步處理至 OneDrive 帳戶的使用者屬性

下一步是檔案同步處理您選擇在步驟 1 中所有 OneDrive 帳戶中組織的 Azure Active Directory 屬性與 Microsoft 支援服務要求。 此同步處理發生時，屬性 （和其值） 後您選擇在步驟 1 中將會對應至名為 SharePoint 中的隱藏 managed 屬性`ComplianceAttribute`。 您將使用這個屬性來建立搜尋權限篩選器的步驟 4 中的 OneDrive。
  
當您將要求提交給 Microsoft 支援服務時，請包含下列資訊：
  
- Office 365 組織的預設網域名稱
    
- Azure Active Directory 屬性 （從步驟 1) 的名稱
    
- 下列的標題或支援要求的用途的描述: 「 啟用 OneDrive 的商務同步處理與 Azure Active Directory 的法規安全性篩選器 」。 這有助於將要求路由傳送至 Office 365 電子文件探索工程團隊會實作要求者。
    
工程變更，而且屬性同步至 OneDrive 之後，Microsoft 支援服務會傳送給您在進行變更的組建編號和預估的部署日期。 請注意，在部署程序通常需要 4-6 週後您提交支援要求。
  
 **重要：** 在部署變更之前，您可以完成步驟 3 到步驟 5。 但執行內容搜尋不會傳回文件從 OneDrive 網站部署變更之後，直到搜尋權限篩選器中指定。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步驟 3： 建立每個代理程式的角色群組

下一步是建立安全性 & 會符合貴機構的合規性中心中的角色群組。 我們建議您複製內建的 eDiscovery Managers 群組、 新增適當的成員，以及移除角色，可能無法適用於您的需求來建立新的角色群組。 如需 eDiscovery 相關角色的詳細資訊，請參閱[指派 Office 365 安全性 & 合規性中心中的 eDiscovery 權限](assign-ediscovery-permissions.md)。
  
若要建立的角色群組，移至安全性 & 合規性中心中的 [**權限**] 頁面上，將會使用合規性界限和 eDiscovery 案例來管理調查每個代理程式中建立的每個小組的角色群組。 
  
使用 Contoso 合規性界限案例中，需要建立四個角色群組，並適當成員新增至每個。
  
- Fourth Coffee eDiscovery 管理員
    
- Fourth Coffee 現場
    
- Coho Winery eDiscovery 管理員
    
- Coho Winery 現場
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步驟 4： 建立搜尋權限篩選器來強制執行的合規性界限

您已建立的每個代理程式的角色群組之後下, 一步是建立關聯至其特定的機構每個角色群組的搜尋權限篩選器，並定義本身的合規性界限。 您需要建立一個每個代理程式的搜尋權限篩選器。 如需建立安全性權限篩選器的詳細資訊，請參閱 <<c0>設定的權限篩選內容搜尋。
  
以下是用來建立搜尋權限的篩選器，用於合規性界限的語法。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
以下是在命令中每個參數的描述：
  
-  `FilterName`對指定的篩選器的名稱。 將用於使用說明或識別篩選機構的名稱。 
    
-  `Users`-指定使用者或群組，取得此篩選器套用至他們所執行的內容搜尋動作。 合規性界限，此參數會指定您要建立的篩選器代理的角色群組 （您在步驟 3 中建立）。 請注意這是多重值參數，因此您可以包含一或多個角色群組，以逗號隔開。 
    
-  `Filters`-指定篩選的搜尋準則。 合規性界限，您將定義下列篩選器。 每個會套用到使用者的內容位置。 
    
  -  `Mailbox`對指定的角色群組定義中的信箱`Users`參數可以搜尋。 合規性界限*ComplianceAttribute*是您在步驟 1 中識別之相同屬性， *AttributeValue*指定機構。 此篩選允許只搜尋特定的機構; 中的 [信箱角色群組的成員例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。 
    
  -  `Site`對指定的角色群組定義中的 OneDrive 帳戶`Users`參數可以搜尋。 OneDrive 篩選時，使用實際字串`ComplianceAttribute`;這會對應至相同的屬性，您在步驟 1 中識別的同步處理至您在步驟 2; 提交支援要求因為 OneDrive 帳戶 *AttributeValue*指定機構。 此篩選器可讓角色群組，以只搜尋特定的機構; 中的 [OneDrive 帳戶的成員例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。
    
  -  `Site_Path`對指定的角色群組定義中的 SharePoint 網站`Users`參數可以搜尋。 *SharePointURL*指定網站中的角色群組的成員可以搜尋; 機構例如，`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`對指定篩選套用至符合性搜尋動作的類型。 例如，`-Action Search`中定義的角色群組的成員時，則只會套用篩選器`Users`參數執行內容搜尋。 在此例中匯出搜尋結果時，就不會套用篩選器。 合規性界限，使用`-Action All`讓篩選套用至所有的搜尋動作。 
    
    如需內容搜尋動作的清單，請參閱 <<c0>設定的權限篩選內容搜尋中的 「 New-compliancesecurityfilter 」 一節。
    
以下是會建立為支援 contoso 公司的合規性界限案例的兩個搜尋的權限篩選器的範例。
  
 **Fourth Coffee**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Coho Winery**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>步驟 5： 建立內機構調查的 eDiscovery 案例

最後一個步驟是在安全性 & 合規性中心中建立新的 eDiscovery 案例，然後將新增角色群組，您在步驟 3 中建立 — 為案例的成員。 這會導致使用合規性界限的兩個重要特性：
  
- 只有新增至案例的角色群組的成員能夠查看及存取安全性 & 合規性中心中的情況。 例如，如果 Fourth Coffee 現場角色群組是案例的唯一成員，然後 Fourth Coffee eDiscovery 管理員角色群組 （或任何其他角色群組的成員） 的成員無法看到或存取這種情況。
    
- 當案例指派給角色群組的成員執行與案例相關聯的搜尋時，他們將只能搜尋其機構 （這由所定義您在步驟 4 中建立搜尋權限篩選器。） 內的內容位置


若要建立新的案例，並指派成員：
    
1. 移至安全性 & 合規性中心中的 [ **eDiscovery** ] 頁面上，並建立新的案例。 
    
2. 在清單中的 eDiscovery 案例，按一下您剛才建立的大小寫名稱。
    
3. 在 [**管理此情況下**彈出式視窗] 頁面的 [**管理角色群組**，按一下 [![加入圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新增**。
    
    ![將角色群組新增為 eDiscovery 案例成員](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色群組的清單中，選取下列其中一個您在步驟 3 中建立的角色群組，並按一下 [**新增**]。
    
5. 在 [**管理此情況下**彈出式視窗以儲存變更，按一下 [**儲存**]。 

## <a name="compliance-boundary-limitations"></a>合規性界限限制

管理 eDiscovery 案例] 和 [合規性界限的調查，使用時，請記住下列限制。
  
- 在建立和執行內容搜尋，您可以選取您機構外的內容位置。 不過，因為搜尋權限篩選器，而這些位置的內容將不會包含在搜尋結果中。
    
- 合規性界限不適用於 eDiscovery 案例中的保留。 這表示一個機構中的 eDiscovery 管理員可以在不同的機構保留的使用者。 不過，如果 「 eDiscovery 管理員 」 搜尋已處於保留狀態的使用者內容的位置，則強制合規性界限。 這表示電子文件探索管理員不會是無法搜尋使用者的內容位置，即使它們我們能夠將使用者放入保留。
    
    此外，保留統計資料將只會套用至機構中的內容位置。
    
- 搜尋的權限篩選器不會套用到 Exchange 公用資料夾。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>搜尋和匯出在多地理位置環境中的內容

搜尋的權限篩選器也可讓您控制會匯出的路由傳送內容，以及[SharePoint 多地理位置環境](https://go.microsoft.com/fwlink/?linkid=860840)中搜尋內容位置時，就可以搜尋哪些資料中心。
  
- **匯出搜尋結果**-您可以從 Exchange 信箱、 SharePoint 網站與 OneDrive 帳戶從特定的資料中心匯出搜尋結果。 這表示您可以指定將會從匯出搜尋結果的資料中心位置。

    將**區域**參數用於**New-compliancesecurityfilter**或**Set-compliancesecurityfilter** cmdlet 來建立或變更匯出，將透過路由傳送的資料中心。
  
    |**參數值**|**資料中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美地區 （實際資料中心是在美國）  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN <br/> |加拿大
    
- **路由傳送內容搜尋**-您可以將 SharePoint 網站與 OneDrive 帳戶的內容搜尋路由傳送到衛星資料中心。 這表示您可以指定將會執行搜尋的資料中心位置。
    
    使用下列**區域**參數值的值來控制哪些搜尋 SharePoint 網站與 OneDrive 位置時，將會執行中的內容搜尋的資料中心。 請注意，下表也會顯示的資料中心匯出都會透過路由傳送。 
  
    |**參數值**|**匯出資料中心路由位置**|
    |:-----|:-----|
    |NAM  <br/> |與我們連絡  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN  <br/> |與我們連絡  <br/> |
    |AUS  <br/> |亞太地區  <br/> |
    |KOR  <br/> |組織的預設資料中心  <br/> |
    |GBR  <br/> |歐洲  <br/> |
    |JPN  <br/> |亞太地區  <br/> |
    |IND  <br/> |亞太地區  <br/> |
    |LAM  <br/> |與我們連絡  <br/> |
   
> [!NOTE]
> 如果您沒有指定的搜尋權限篩選器的**區域**參數，將搜尋組織的預設 SharePoint 區域，然後搜尋結果匯出至最接近的資料中心。 
  
以下是建立搜尋的合規性界限的權限篩選器時，使用**Region**參數的範例。 這假設 Fourth Coffee 子公司位於 「 北美地區 」，且 Coho Winery Europe。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
保留記住時搜尋和匯出中的下列事項多地理位置環境中的內容。
  
- **Region**參數並不會控制 Exchange 信箱; 的搜尋當您搜尋信箱時，便會搜尋所有的資料中心。 若要限制可搜尋的哪些 Exchange 信箱的範圍，請使用時建立或變更的搜尋權限篩選器的**篩選器**參數。 
    
- 如果它是所需的 eDiscovery 搜尋跨多個 SharePoint 區域的管理員，您需要建立不同的使用者帳戶的電子文件探索管理員可以使用搜尋權限篩選器來指定備用區域中：SharePoint 網站或 OneDrive 帳戶有位於。
    
- 當您搜尋 SharePoint 和 OneDrive 中的內容， **Region**參數會指示任一種主要的搜尋或衛星位置電子文件探索管理員將會進行電子文件探索調查的位置。 如果 eDiscovery 管理員 」 搜尋中搜尋權限篩選器所指定的地區外的 SharePoint 和 OneDrive 網站，將會不傳回任何搜尋結果。 
    
- 匯出搜尋結果時, （包括 Exchange、 Skype for Business，SharePoint、 OneDrive 及其他 Office 365 服務，您可以使用 「 內容搜尋 」 工具來搜尋） 的所有內容位置的內容就會上傳到 Azure 的儲存位置**區域**參數所指定的資料中心。 這可協助組織保持在合規性內不允許匯出受控制的框線之間的內容。 如果沒有區域指定搜尋的權限篩選器中，內容是上傳到組織的預設區域。 
    
- 您可以編輯現有的搜尋權限篩選器來新增或變更區域藉由執行下列命令：

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>常見問題集

 **誰可以建立及管理搜尋的權限篩選器 （使用 New-compliancesecurityfilter 和 Set-compliancesecurityfilter cmdlet）？**
  
若要建立、 檢視及修改搜尋權限篩選器，您必須是安全性 & 合規性中心中 「 組織管理角色群組的成員。
  
 **如果 eDiscovery 管理員指派給多個角色群組跨越多個行政機關，如何在搜尋一個機構中的內容或其他？**
  
電子文件探索管理員可以將參數新增至其搜尋查詢，會限制搜尋至特定的機構。 例如，如果組織具有指定在**CustomAttribute10**屬性，來區分行政機關，他們可以附加下列至其搜尋查詢以搜尋特定的機構中信箱和 OneDrive 帳戶： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **如果屬性做為搜尋權限篩選器中的規範屬性的值已變更發生什麼情況？**
  
花費最多可為 3 天來強制執行的合規性界限，如果在篩選中使用屬性的值已變更的搜尋權限篩選器。 例如，在 Contoso 案例假設 Fourth Coffee 機構中的使用者會被轉接至 Coho Winery 機構。 因此，使用者物件上的**部門**屬性值會從*FourthCoffee*變更為*CohoWinery* 。 在此情況下，Fourth Coffee eDiscovery 和投資者會針對該使用者的設定之後屬性變更為 3 天取得搜尋結果。 同樣地，它將會需要最多 3 天前 Coho Winery eDiscovery 管理員和現場會取得使用者的搜尋結果。 
  
 **電子文件探索管理員可以看到兩個不同的合規性界限的內容？**
  
是。 這可以經由將使用者新增至角色群組，有兩個行政機關看得到。
  
 **搜尋 eDiscovery 案件保留、 Office 365 保留原則，或 DLP 權限篩選器的運作？**
  
否，不是在這個階段
  
 **如果指定其中要匯出的內容，但我沒有該區域中的 SharePoint 組織控制項的區域，我仍然可以搜尋 SharePoint？**
  
如果您的組織中不存在搜尋權限篩選器中指定的區域，可供搜尋的預設區域。
  
 **可以在組織中建立搜尋權限篩選器的最大數目為何？**
  
沒有任何限制可以在組織中建立搜尋權限篩選器的數目。 不過，有 100 個以上的搜尋權限篩選器時，會影響搜尋效能。 若要保留組織中搜尋的權限篩選數目，盡可能的小，建立篩選器，將規則的 Exchange、 SharePoint 和 OneDrive 合併成單一搜尋權限篩選器儘。
