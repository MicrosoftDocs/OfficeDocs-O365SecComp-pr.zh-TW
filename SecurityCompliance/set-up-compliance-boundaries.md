---
title: 設定 Office 365 中電子文件探索調查的合規性界限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 若要建立 Office 365 組織內控制 eDiscovery 管理員可搜尋的使用者內容位置的邏輯界限使用規範界限。規範界限使用搜尋篩選 （也稱為的規範安全性篩選） 若要控制哪些信箱、 SharePoint 網站的權限，並可由特定使用者搜尋 OneDrive 帳戶。
ms.openlocfilehash: 2bebd29fa7701ba07aae7170142263aeaec5569e
ms.sourcegitcommit: c7264f3a6a97f1ff544544e2c722e7825e265fa1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2018
ms.locfileid: "26299237"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>設定 Office 365 中電子文件探索調查的合規性界限

規範界限建立 Office 365 組織內控制的使用者內容位置 （例如信箱、 SharePoint 網站及 OneDrive 帳戶） eDiscovery 管理員可搜尋的邏輯界限。此外，規範界限控制人員可以存取用來管理法律、 人力資源或其他調查組織中的 eDiscovery 案例。規範界限需要通常是必要必須遵守地理退敵軍和法規、 多重民公司及政府，通常會分成不同案件。在 Office 365，您符合規範界限說明執行時這些需求的內容搜尋與管理 eDiscovery 案例與調查。
  
我們用於範例會在下圖說明規範界限的運作方式。
  
![規範界限組成搜尋權限篩選控制存取行政機關和系統管理員角色群組 eDisocovery 的情況下的控制存取](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
在本例中為 Contoso LTD 是 Office 365 組織所組成的兩個子公司 Fourth Coffee 和 Coho Winery。公司需要的 eDiscovery 管理員中及現場只能搜尋 Exchange 信箱、 OneDrive 帳戶及 SharePoint 網站中其機構。此外，eDiscovery 管理員及現場只能看到中的 eDiscovery 案例中其 agency，並只可以存取它們的成員的情況。以下是規範界限如何符合這些需求。
  
- 篩選內容搜尋控制項中的功能 eDiscovery 管理員及現場可搜尋的內容位置搜尋的權限。這表示 eDiscovery 管理員及現場 Fourth Coffee 機構中的只能搜尋的內容位置中 Fourth Coffee 子公司。Coho Winery 子公司套用相同的限制。
    
    角色群組控制可以看到 Office 365 安全性的 eDiscovery 案例&amp;規範中心。這表示 eDiscovery 管理員及現場只可以看到其機構中的 eDiscovery 案例。
    
- 角色群組也會控制誰可將成員指派至 eDiscovery 案例。這表示 eDiscovery 管理員及現場可以只將成員指派給他們本身是成員的情況下。
    
以下是設定規範界限的程序：
  
[步驟 1： 識別使用者屬性以定義您的行政機關](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步驟 2： 檔案要求 Microsoft 技術支援人員以同步處理至 OneDrive 帳戶的使用者屬性](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步驟 3： 建立角色群組的每個機構](#step-3-create-a-role-group-for-each-agency)

[步驟 4： 建立搜尋權限篩選器來強制執行規範界限](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步驟 5： 建立內機構調查的 eDiscovery 案例](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步驟 1： 識別使用者屬性以定義您的行政機關

第一個步驟是定義在行政機關選擇要使用的 Azure Active Directory 屬性。此屬性會用來建立限制 eDiscovery 搜尋的權限篩選來搜尋使用者對其指派特定的值為此屬性的內容位置的管理員。例如，假設 Contoso 決定要使用的**部門**屬性。Fourth Coffee 子公司中使用者的這個屬性的值就是`FourthCoffee`和 Coho Winery 子公司中使用者的值就是`CohoWinery`。在步驟 4 中，您將使用此`attribute:value`限制使用者對 (例如*部門： FourthCoffee* ) 內容 eDiscovery 管理員可搜尋的位置。 
  
以下是您可以使用規範界限的 Azure Active Directory 使用者屬性的清單：
  
- Company
    
- CountryCode
    
- CustomAttribute1-CustomAttribute15
    
- 部門
    
- 辦公室
    
雖然多個使用者屬性可供，特別是 Exchange 信箱，以上所列的屬性是目前支援的 OneDrive 的唯一錯誤。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步驟 2： 檔案要求 Microsoft 技術支援人員以同步處理至 OneDrive 帳戶的使用者屬性

下一步是檔案同步處理您選擇在步驟 1 中所有 OneDrive 帳戶在組織中的 Azure Active Directory 屬性與 Microsoft 支援要求。此同步處理發生屬性 （和其值） 後您在步驟 1 中選擇要對應至名為 SharePoint 中隱藏的 managed 屬性`ComplianceAttribute`。您將使用此屬性來建立步驟 4 中的 OneDrive 搜尋權限篩選。
  
當您要求提交至 Microsoft 支援包括下列資訊：
  
- Office 365 組織的預設網域名稱
    
- Azure Active Directory 屬性 （從步驟 1) 的名稱
    
- 下列的標題或支援要求的用途說明:"啟用 OneDrive for 商務同步處理與 Azure Active Directory 的規範安全性篩選"。這有助於路由要求傳送到 Office 365 eDiscovery 工程小組人員實作要求。
    
工程變更並屬性已同步處理至 OneDrive 之後，Microsoft 技術支援人員會傳送給您在進行變更的組建編號與估計的部署日期。請注意部署程序通常會 4-6 週後支援將要求送出。
  
 **重要：** 您可以在部署變更之前完成步驟 3 到步驟 5。但是執行內容的搜尋不會傳回文件從之後部署變更指定直到搜尋權限篩選器中的 OneDrive 網站。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步驟 3： 建立角色群組的每個機構

下一步是建立 Office 365 安全性角色群組&amp;將您的行政機關最符合的規範中心。我們建議您建立新的角色群組的方式將複製的內建的 eDiscovery 管理員群組新增適當的成員，移除角色可能不會套用至您的需求。如需 eDiscovery 相關的角色的詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
  
若要建立角色群組，請前往 [安全性**權限**] 頁面上&amp;規範中心及中會使用規範界限和 eDiscovery 案例來管理調查每個機構建立每個小組角色群組。 
  
使用 Contoso 規範界限案例，需要建立四個角色群組和適當的成員新增至每個。
  
- Fourth Coffee eDiscovery 管理員
    
- Fourth Coffee 現場
    
- Coho Winery eDiscovery 管理員
    
- Coho Winery 現場
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步驟 4： 建立搜尋權限篩選器來強制執行規範界限
<a name="step4"> </a>

您已建立的每個機構的角色群組之後下, 一步是建立關聯至其特定機構的每個角色群組搜尋的權限篩選及定義的規範界限本身擷取。您需要建立一個搜尋權限篩選的每個機構。如需建立安全性權限篩選器的詳細資訊，請參閱 ＜ [Configure 權限的內容搜尋篩選](permissions-filtering-for-content-search.md)。
  
用來建立規範界限用於搜尋的權限篩選語法如下所示。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
以下是在命令中的每個參數的描述：
  
-  `FilterName`-指定篩選的名稱。將用於使用說明或識別篩選機構的名稱。 
    
-  `Users`-指定使用者或群組取得此篩選器套用至他們所執行的內容搜尋動作。規範界限此參數會指定您建立的篩選器機構的角色群組 （您在步驟 3 中建立）。請注意此多重值參數讓您可以包含一或多個以逗號分隔的角色群組。 
    
-  `Filters`-指定篩選條件的搜尋準則。規範界限中，您將會定義下列篩選器。每一個適用於使用者的內容位置。 
    
  -  `Mailbox`-指定中所定義的角色群組的信箱`Users`參數可搜尋。規範界限*ComplianceAttribute*是您在步驟 1 中識別之相同屬性並*AttributeValue*指定機構。此篩選允許只在特定的機構 ； 搜尋之信箱的角色群組的成員例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。 
    
  -  `Site`-指定角色群組中所定義的 OneDrive 帳戶`Users`參數可搜尋。使用 OneDrive 篩選器的實際字串`ComplianceAttribute`;這會對應至您在步驟 1 中識別和同步處理至 OneDrive 帳戶是您在步驟 2; 送出的支援要求的相同屬性 *AttributeValue*指定機構。此篩選允許只在特定的機構 ； 搜尋 OneDrive 帳戶的角色群組的成員例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。
    
  -  `Site_Path`-指定角色群組中所定義的 SharePoint 網站`Users`參數可搜尋。*SharePointURL*指定網站中的角色群組的成員可以搜尋 ； 機構例如，`Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`-指定篩選條件套用到規範搜尋動作的類型。例如，`-Action Search`就只會套用篩選器時中所定義的角色群組的成員`Users`參數執行內容的搜尋。在此例中匯出搜尋結果時不會套用篩選。規範界限使用`-Action All`所以篩選條件套用到所有搜尋動作。 
    
    內容搜尋動作的清單，請參閱[設定權限的內容搜尋篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)"New-ComplianceSecurityFilter 」 一節。
    
以下是範例會建立為支援 Contoso 規範界限案例的兩個搜尋權限篩選器。
  
 **Fourth Coffee**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Coho Winery**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>步驟 5： 建立內機構調查的 eDiscovery 案例

最後一個步驟是在 [安全性] 中建立新的 eDiscovery 案例&amp;規範中心然後新增角色群組 — 您在步驟 3 中建立 — 為大小寫的成員。這會產生使用規範界限的兩個重要特性：
  
- 僅新增至案例的角色群組的成員能看到並存取安全性案例&amp;規範中心。例如，如果案例的唯一成員 Fourth Coffee 現場角色群組，然後 Fourth Coffee eDiscovery 管理員角色群組 （或其他任何角色群組的成員） 的成員不會能夠請參閱或存取大小寫。
    
- 指派給案例的角色群組的成員執行與案例相關聯的搜尋時所將只能夠搜尋其機構 （這由定義您在步驟 4 中建立的搜尋權限篩選。） 內的內容位置


若要建立新案例並指派成員：
    
1. 移至 [ **eDiscovery** ] 頁面上的 [安全性]&amp;規範中心並建立新的案例。 
    
2. 在清單中的 eDiscovery 的情況下，按一下您剛建立的大小寫的名稱。
    
3. [**管理角色群組**、 [**管理此例中**彈出式] 頁面中按一下 [![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新增]**。
    
    ![新增 eDiscovery 案例的成員身分的角色群組](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色群組的清單中，選取您在步驟 3 中建立的角色群組的其中一個並按一下 [**新增**]。
    
5. 按一下 [**管理此例中**彈出式以儲存變更上的 [**儲存**]。 

## <a name="compliance-boundary-limitations"></a>規範界限限制

管理 eDiscovery 案例和規範界限的使用調查時，請記住下列限制。
  
- 當建立和執行內容搜尋時，您可以選取您機構外的內容位置。不過，搜尋權限篩選，因此將不會包含從這些位置內容搜尋結果中。
    
- 規範界限不適用於保留 eDiscovery 案例中。這表示一個機構中的 eDiscovery 管理員可以將使用者放入保留不同機構。不過，規範界限將強制執行如果 eDiscovery 管理員會搜尋已處於保留狀態的使用者內容的位置。這表示 eDiscovery 管理員將不會是無法搜尋使用者的內容位置、 即使交易能夠將使用者放入保留。
    
    此外，保留統計資料會僅適用於機構中的內容位置。
    
- 搜尋的權限篩選不會套用到 Exchange 公用資料夾。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>搜尋和匯出多個地理位置環境中的內容

搜尋的權限篩選也可讓您控制會匯出的路由傳送的內容及搜尋[SharePoint 多重地理位置環境](https://go.microsoft.com/fwlink/?linkid=860840)中的 SharePoint 網站及 OneDrive 帳戶時可搜尋的資料中心：
  
- 從特定的資料中心匯出搜尋結果。這表示您可以指定資料中心的位置搜尋結果將會從匯出。
    
- 路由 SharePoint 網站及 OneDrive 帳戶的搜尋衛星資料中心。這表示您可以指定能執行搜尋的資料中心位置。
    
用於**Region**參數**新增 ComplianceSecurityFilter**或**組 ComplianceSecurityFilter** cmdlet 建立或變更匯出將轉接到哪一個資料中心。
  
|**參數值**|**資料中心位置**|
|:-----|:-----|
|NAM  <br/> |北美地區 （實際資料中心有實際在美國）  <br/> |
|EUR  <br/> |歐洲  <br/> |
|APC  <br/> |亞太地區  <br/> |
|CAN <br/> |加拿大
   
同樣地，您可以使用下列**區域**的參數值的值來控制內容搜尋搜尋 SharePoint 及 OneDrive 位置時所執行的哪些資料中心。請注意，如下表也會顯示匯出將轉接到哪一個資料中心。 
  
|**參數值**|**資料中心匯出路由的位置**|
|:-----|:-----|
|NAM  <br/> |US  <br/> |
|EUR  <br/> |歐洲  <br/> |
|APC  <br/> |亞太地區  <br/> |
|CAN  <br/> |US  <br/> |
|AUS  <br/> |亞太地區  <br/> |
|KOR  <br/> |組織的預設資料中心  <br/> |
|GBR  <br/> |歐洲  <br/> |
|JPN  <br/> |亞太地區  <br/> |
|尋找  <br/> |亞太地區  <br/> |
|LAM  <br/> |US  <br/> |
   
 **附註：** 如果您沒有指定搜尋的權限篩選 Region 參數，拼寫須符合組織的預設 SharePoint 區域，然後搜尋結果匯出至最接近的資料中心。 
  
以下是範例使用 **-地區**參數建立規範界限搜尋 」 權限篩選器時。這是假設 Fourth Coffee 子公司位於 「 北美地區 」 與 Coho Winery 處於 Europe。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
保留下列項目在搜尋時記住和匯出多個地理位置環境中的 [內容。
  
- **Region**參數不會控制 Exchange 信箱 ； 的搜尋搜尋信箱時將會搜尋所有的資料中心。若要限制可搜尋的哪些 Exchange 信箱的範圍，請使用**篩選**參數建立或變更搜尋權限篩選時。 
    
- 如果時所需的 eDiscovery 來搜尋跨多個 SharePoint 區域的管理員，您需要搜尋權限篩選以指定的備用區域中可用的管理員建立不同的使用者帳戶該的 ediscovery （英文） 位置SharePoint 網站或 OneDrive 帳戶位於。
    
- 搜尋 SharePoint 和 OneDrive 中的內容、 時**Region**參數會指示搜尋以其中一個主要或附屬 eDiscovery 管理員會對執行 eDiscovery 調查的位置。如果 eDiscovery 管理員搜尋中搜尋的權限篩選指定的區域外部的 SharePoint 和 OneDrive 網站，會不傳回任何搜尋結果。 
    
- 從所有內容的位置 （包括 Exchange、 Skype Business、 SharePoint、 onedrive 及其他 Office 365 服務，您可以使用 「 內容搜尋工具來搜尋） 的內容匯出搜尋結果時, 將上傳至在 Azure 的儲存位置**區域**參數所指定的資料中心。這可幫助組織內規範保持不允許匯出控制框線之間的內容。如果搜尋權限篩選器中指定無區域，則內容已上傳至組織的預設區域。 
    
- 您可以編輯現有的搜尋權限篩選條件新增或變更區域中執行下列命令：

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>常見問題集

 **誰可以建立及管理搜尋的權限篩選 （使用 New ComplianceSecurityFilter 和設定 ComplianceSecurityFilter cmdlet）？**
  
若要建立、 檢視及修改搜尋權限篩選，您必須是安全性組織管理角色群組的成員&amp;規範中心。
  
 **如果 eDiscovery 管理員指派給多個角色群組跨多個行政機關，如何搜尋時一個機構中的內容或其他？**
  
EDiscovery 管理員可以將參數加入至特定機構會限制搜尋其搜尋查詢。例如，如果組織具有指定**CustomAttribute10**屬性來區分行政機關，他們可以附加下列至其搜尋查詢，以搜尋特定的機構中信箱和 OneDrive 帳戶： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **如果會做為搜尋權限篩選器中的規範屬性的屬性值變更發生什麼情況？**
  
延長最多可搜尋的權限篩選強制規範界限如果在篩選中使用的屬性值變更為 3 天。例如，Contoso 的案例中假設 Fourth Coffee 機構中的使用者會轉接到 Coho Winery 機構。因此，使用者物件上的**部門**屬性的值會從*FourthCoffee*變更為*CohoWinery* 。在此情況下，Fourth Coffee eDiscovery 及投資者會針對該使用者的設定屬性有所變更之後為 3 天取得搜尋結果。同樣地，需要最多為 3 天前 Coho Winery eDiscovery 管理員及現場將使用者取得搜尋結果。 
  
 **EDiscovery 管理員可以看到兩個獨立的規範界限的內容吗？**
  
[是]。這可以完成將使用者新增至角色群組具有兩個行政機關看得到。
  
 **搜尋的權限篩選 eDiscovery 案件保留、 Office 365 的保留原則或 DLP 吗？**
  
否，未在此階段
  
 **如果我指定一個區域，其中會匯出內容，但我沒有該區域中的 SharePoint 組織的控制項，可以使用仍搜尋 SharePoint？**
  
如果指定搜尋的權限篩選器中的區域不存在您組織中，將可搜尋的預設區域。
  
 **什麼是搜尋權限篩選器可以在組織中建立的最大數目？**
  
沒有可建立在組織中的搜尋權限篩選數目受限制。但如有 100 個以上的搜尋權限篩選將會影響搜尋效能。若要在組織中的搜尋權限篩選數目維持盡可能的小，建立的 Exchange、 SharePoint 及 OneDrive 的規則合併成單一搜尋權限篩選盡可能的篩選器。
