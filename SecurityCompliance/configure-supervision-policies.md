---
title: 為您的組織設定監督原則
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 設定監督檢閱原則以擷取員工通訊供檢閱。
ms.openlocfilehash: a919d65f5c0967a44ac12b7e02d477dac2113704
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527430"
---
# <a name="configure-supervision-policies-for-your-organization"></a>為您的組織設定監督原則

使用監督原則來擷取由內部或外部檢閱者檢查 「 員工通訊。
  
> [!NOTE]
> 使用監督原則您的組織需要的 Office 365 E5 訂閱。如果您不具有該對應並想要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
請遵循下列步驟來設定和 Office 365 組織中使用監督： 
  
- [設定群組的監督](configure-supervision-policies.md#exampledist)
    
    在您開始使用監督之前，請決定誰將其通訊檢閱和誰可以執行這些檢閱 （英文）。如果您想要開始使用少數使用者看到監督的運作方式，您可以略過現在群組設定。
    
- [在組織中讓監督](configure-supervision-policies.md#SRavailable)
    
    新增您自己監督檢閱角色群組讓您可以設定原則。已指派給此角色的任何人可以存取下**資料管理**安全性的**監督**頁面&amp;規範中心。 
    
- [設定的監督原則](configure-supervision-policies.md#setupsuper)
    
    您將建立安全性的監督原則&amp;規範中心。這些原則定義的通訊會受到組織中的檢閱和指定誰應該執行檢閱 （英文）。通訊包含電子郵件時 （例如 Facebook、 Twitter、 等） 的第 3 廠商平台通訊
    
- [使用 Outlook web app 檢閱監督原則所識別的通訊](configure-supervision-policies.md#UseOutlook)
    
    監督增益集可以讓檢閱者存取 Outlook web app 右邊的監督功能，讓他們可以評估並將每個項目。即將推出的桌面的 Outlook 版本支援。
    
- **執行監督報告**
    
    若要查看檢閱活動層級原則和檢閱者使用監督報告。每個原則，您也可以檢閱活動的目前狀態檢視 live 的統計資料。如需詳細資訊，請參閱[監督報告](supervision-reports.md)。
    
## <a name="set-up-groups-for-supervision"></a>設定群組的監督
<a name="exampledist"> </a>

 當您建立監督原則時，您將決定誰會有檢閱其通訊及誰可以執行這些檢閱 （英文）。在原則中，您將使用電子郵件地址來識別的個人或群組的人員。若要簡化您的安裝程式，建立人員有其檢閱的通訊群組和人員將檢閱這些通訊群組。如果您使用的群組，您可能需要數個 — 例如，如果您想要監視的人員、 兩個不同的群組之間的通訊，或者您想要指定無法移至要指導的群組。如需此的運作方式的詳細資訊，請參閱[範例通訊群組](configure-supervision-policies.md#GroupExample)。 
  
若要管理組織中的群組內或之間的通訊、 設定通訊群組在 Exchange 系統管理中心 (移至 [**收件者** \> **群組**)。如需設定通訊群組的詳細資訊，請參閱[管理通訊群組](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> 您也可以使用動態通訊群組或安全性群組的監督若您偏好。若要協助您決定是否這些更適合您組織需求，請參閱[管理擁有郵件功能的安全性群組](http://go.microsoft.com/fwlink/?LinkId=627033)及[管理動態通訊群組](http://go.microsoft.com/fwlink/?LinkId=627058)。 
  
### <a name="example-distribution-groups"></a>通訊群組範例
<a name="GroupExample"> </a>

此範例會包含已針對名為 Contoso 財務國際財務組織設定的通訊群組。 
  
在 Contoso Financial International 中，必須抽樣監管美國境內各代理人間的通訊。不過，不需要監管該群組內的法務人員。在此範例中，我們可以建立下列群組：
  
|**設定此通訊群組**|**群組地址 (別名)**|**描述**|
|:-----|:-----|:-----|
|所有美國代理人  <br/> |US_Brokers@Contoso.com  <br/> |此群組包含於 Contoso 任職，所有位於美國的代理人的電子郵件地址。  <br/> |
|所有美國法務人員  <br/> |US_Compliance@Contoso.com  <br/> |此群組包含所有的美國型法務人員合作 Contoso 的電子郵件地址。因為此群組的所有美國型經紀人子集，您可用於此別名免除法務人員從監督原則。  <br/> |
   
[監督原則設定](configure-supervision-policies.md#setupsuper)] 區段中會說明如何使用這些群組，當您設定的原則。 
  
## <a name="make-supervision-available-in-your-organization"></a>在組織中讓監督
<a name="SRavailable"> </a>

在 [安全性] 進行**監督**可作為功能表選項&amp;規範中心，您必須指派監督檢閱系統管理員角色。 
  
為達成此目的，您也可以新增您自己做監督檢閱角色群組的成員，或您可以建立新的角色群組。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>新增成員至監督檢閱角色群組

1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。 
    
2. 安全性&amp;規範中心，請移至 [**權限**。
    
3. 選取 [**監督檢閱**角色群組，然後按一下 [編輯] 圖示。 
    
4. 在 [**成員**] 區段中，新增您想要管理您的組織的監督的人員。 
    
### <a name="create-a-new-role-group"></a>建立新的角色群組

1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。 
    
2. 安全性&amp;規範中心移至 [**權限**] 和 [新增] ( **+**)。
    
3. 在 [**角色**] 區段中，按一下 [新增] ( **+**) 和**監督檢閱管理員**下的捲軸。將此角色新增至角色群組。
    
4. 在 [**成員**] 區段中，新增您想要管理您的組織的監督的人員。 
    
如需有關角色群組和權限的詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="set-up-a-supervision-policy"></a>設定的監督原則
<a name="setupsuper"> </a>

> [!IMPORTANT]
> 之前建立的監督原則，您必須先移除任何現有的監督檢閱原則。 
  
1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。 
    
2. 安全性&amp;規範管理中心，移至按一下 [**資料控管** \> **監督**。
    
    > [!NOTE]
    > 舊版的功能可能會顯示在左導覽中做為**監督檢閱 （淘汰很快）**。此版本將推出已被取代的和移除。呼叫**監督**的新版本需要其位置。 
  
3. 按一下 [**建立**，然後遵循精靈來設定下列原則的頁面。 
    
### <a name="policy-name-and-description"></a>原則名稱與描述

輸入名稱與您的原則的描述。基於範例中，我們將命名原則 Contoso 美國經紀人。
  
### <a name="choose-users-to-supervise"></a>選擇 [管理使用者

- 在 [ **Supervise 這些使用者或群組**] 方塊中，選擇 [使用者或群組您想来管理其通訊。如果為 Contoso 美國經紀人堅持與我們的範例，我們將會選擇群組 US_Brokers@Contoso.com 此處。 
    
- 如果您選擇以管理群組，您可以使用 [**排除這些使用者**] 方塊中選擇免除監督時群組的成員。使用的範例，我們將排除的群組 US_Compliance@Contoso.com 此處。 
    
### <a name="choose-communications-to-review"></a>選擇 [可供檢閱的通訊
<a name="CommsToReview"> </a>

根據預設，**方向是**條件會顯示，且無法移除。如果您想要的範圍 （例如僅檢閱含有特定單字或片語的內容） 進一步的檢閱，按一下 [**新增條件**。您可以在必要時指定多個條件。
  
您選擇的條件將套用通訊 (從 Facebook 或投寄箱 like) 您組織中的電子郵件和第 3 廠商來源。如需 Office 365 組織將匯入第 3 廠商通訊的詳細資訊，請參閱[Office 365 中的封存與協力廠商資料](https://technet.microsoft.com/EN-US/library/mt621583.aspx)。
  
下表說明更多關於每一項條件。
  
|**條件**|**如何使用此條件**|
|:-----|:-----|
|指示如下  <br/> |選擇**輸入**檢閱就會傳送**至**管理**從**人員選擇的人員不包含在原則中的通訊。  <br/> 如果您想要檢閱通訊所選擇**輸出****寄件者選擇管理人員*** * 以 * * 不包含在原則中的人員。  <br/> 選擇**內部**通訊傳送**之間**檢閱您指定的人員原則中。  <br/> |
|郵件包含任何這些字詞  <br/> 郵件包含任何這些字詞  <br/> |若要將原則套用包含或排除在郵件中特定單字或片語時，輸入每個單字或片語分列一行。您輸入的文字的每一行會分別套用 （僅需一個的這些行必須套用適用於將原則套用至郵件）。如需輸入單字或片語的詳細資訊，請參閱 [下一步] 區段中[比對字與詞至電子郵件或附件](configure-supervision-policies.md#Matchwords)。<br/> |
|附件中包含任何這些字詞  <br/> 附件包含任何這些字詞  <br/> |若要將原則套用包含或排除在郵件附件 （例如 Word 文件） 中特定單字或片語時，輸入每個單字或片語分列一行。您輸入的文字的每一行會分別套用 （僅限一行必須套用適用於將原則套用至附件）。如需輸入單字或片語的詳細資訊，請參閱 [下一步] 區段中[比對字與詞至電子郵件或附件](configure-supervision-policies.md#Matchwords)。<br/> |
|附件是任何這些檔案類型  <br/> 附件為 none 這些檔案類型  <br/> |若要管理包括或排除特定類型的附件的通訊，請輸入副檔名 （例如.exe 或.pdf）。如果您想要包含或排除多個副檔名，輸入這些在個別行上。只有一個附件副檔名必須套用之原則的相符。  <br/> |
|郵件大小大於  <br/> 郵件大小大於不  <br/> |若要檢閱根據特定大小的郵件，請使用這些條件來指定一則訊息可以隨時檢閱之前的最大值或最小大小。例如，如果您指定**的郵件大小大於** \> **1.0 MB**，所有郵件 1.01 MB 且更大會遵循檢閱。您可以選擇位元組、 kb、 （mb） 或 gb 此情況。<br/> |
|附件為大於  <br/> 附件是不大於  <br/> |若要檢閱其附件的大小為基礎的郵件，請指定附件的最大值或最小大小可以是之前郵件和其附件會受到檢閱。例如，如果您指定**附件大於** \> **2.0 MB**附件的所有郵件 2.01 MB 及移轉會遵循檢閱。您可以選擇位元組、 kb、 （mb） 或 gb 此情況。<br/> |
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>對電子郵件或附件比對單字和字詞
<a name="Matchwords"> </a>

您輸入的文字的每一行會分別套用 （僅限一行必須套用適用於電子郵件或附件套用原則條件）。例如，我們使用條件、**郵件包含任何這些字詞**，關鍵字"也"及"內部貿易"在個別行上。原則會套用到任何包含"也"一字或片語"內部貿易"的訊息。僅有一個這些單字或片語的必須發生以套用此原則條件。在訊息或附件中的文字必須完全符合您的輸入。
  
#### <a name="entering-multiple-conditions"></a>輸入多個條件
<a name="Matchwords"> </a>

如果您輸入多個條件、 Office 365 使用的所有條件一起決定何時要將原則套用至通訊項目。當您設定多個條件時，他們必須所有符合將原則套用，除非您輸入的例外狀況。例如，假設您需要建立如果郵件包含單字"貿易"且大於 2 MB 應套用原則。不過，如果郵件也包含單字"Contoso 財務的已核准 」，應該不會套用原則。因此，在此例中的三種條件就是，如下所示： 
  
- **郵件包含任何這些字詞**、 使用關鍵字"貿易"
    
- **郵件大小大於**，以值 2 MB
    
- **郵件包含不含這些字**、 使用關鍵字"Contoso 財務小組的已核准 」。
    
### <a name="specify-percentage-to-review"></a>指定要檢閱百分比
<a name="CommsToReview"> </a>

如果您想要減少可供檢閱的內容量，指定百分比。我們隨機將選取的內容量從總符合您所選擇的條件。如果您想檢閱者的所有項目，請輸入**100%**。
  
### <a name="choose-reviewers"></a>選擇 [檢閱者
<a name="CommsToReview"> </a>

使用者和群組您選擇要用以監督應用程式 Outlook web app 中檢查傳回依此原則的通訊。您可以在內部或外部檢閱者的包含電子郵件地址。 
  
### <a name="review-your-settings"></a>檢閱您的設定
<a name="CommsToReview"> </a>

在完成所有章節的監督原則後，檢閱您的設定和 [**完成**] 以儲存您的原則。可能需要幾個小時開始捕捉 communications 原則。監督將供檢閱的所有通訊都傳遞到檢閱者可以存取 Outlook web app 中的共用資料夾。 
  
## <a name="use-outlook-web-app-to-review-communications-identified-by-a-supervision-policy"></a>使用 Outlook web app 檢閱監督原則所識別的通訊
<a name="UseOutlook"> </a>

檢閱者將會使用監督增益集的 Outlook web app 檢閱通訊。增益集會自動安裝 Outlook web app 中所指定之原則的所有檢閱者的。即將推出的桌面的 Outlook 版本支援。
  
 **檢閱在 Outlook web app 中的通訊**
  
1. 在 Outlook web app 中，依序展開 [**監督-\<原則名稱\>** 資料夾。 
    
2. 在**\<原則名稱\>** 子資料夾、 檢閱者將會看到該監督原則所識別的所有通訊。 
    
    ![監督增益集在 Outlook web app 顯示所選取的監督原則子資料夾](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. 開啟檢閱並按一下 [**監督**增益集的項目。 
    
4. 使用增益集將分類為**符合標準**、**非符合標準**、 **Questionable**或**已解決**的項目。您是否已分類項目之後，將會移至相對應的子資料夾下**\<原則名稱\>** 資料夾。 
    

