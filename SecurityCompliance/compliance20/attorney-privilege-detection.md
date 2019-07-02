---
title: 在高級 eDiscovery 中設定律師-用戶端許可權偵測
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 加入宣告並使用律師-用戶端許可權偵測模型, 以在檢查高級 eDiscovery 案例中的內容時, 使用具有許可權內容的機器學習式偵測。
ms.openlocfilehash: 16a6a215484c35d20fbe071cac033133270b7ea6
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703860"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>在高級 eDiscovery 中設定律師-用戶端許可權偵測

任何 eDiscovery 程式的審查階段的主要和成本高的層面, 就是檢查檔中的許可權內容。 高級 eDiscovery 提供電腦對許可權內容的瞭解式偵測, 讓此程式的效率更高。 這項功能稱為「*律師-用戶端許可權偵測*」。

> [!NOTE]
> 您必須先選擇「律師-用戶端」的許可權偵測模型, 才能使用它。 請參閱[步驟 1](#step-1-opt-in-to-attorney-client-privilege-detection)以取得相關指示。

## <a name="how-does-it-work"></a>它如何運作？

一旦啟用律師-用戶端許可權偵測, 當您分析考核集中[的資料](analyzing-data-in-review-set.md)時, 律師-用戶端的許可權偵測模型將會處理審閱集中的所有檔。 模型會尋找兩件事:

- 許可權內容–模型使用機器學習來判斷檔中包含法律的內容的可能性。

- 參與者–作為設定律師-用戶端許可權偵測的一部分, 您必須提交您組織的律師清單。 然後, 模型會將檔的參與者與律師清單進行比較, 以判斷檔是否至少有一個律師參與者。

模型會為每個檔產生下列三個屬性:

- **AttorneyClientPrivilegeScore** –檔本質上為法律的可能性。分數的值介於**0**和**1**之間。

- **HasAttorney** –如果其中一個檔參與者列出于律師清單, 則此屬性會設為**true** 。否則, 值為**false**。 如果您的組織未上傳律師清單, 則此值也會設為**false** 。

- **IsPrivilege** –如果**AttorneyClientPrivilegeScore**的值高於臨界值*或*檔有律師參與者, 則此屬性會設定為**true** 。否則, 此值會設為**false**。

這些屬性 (及其對應值) 會新增至審閱集中檔的檔案中繼資料中, 如下列螢幕擷取畫面所示:

![律師-檔案中繼資料中顯示的用戶端許可權屬性](../media/AeDAttorneyClientPrivilegeMetadata.png)

這三個屬性也可在檢查集中搜尋。 如需詳細資訊, 請參閱[查詢評審集中的資料](review-set-search.md)。

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>設定律師-用戶端許可權偵測模型

若要啟用律師-用戶端許可權偵測模型, 您的組織必須加入宣告, 然後上傳律師清單。

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a>步驟 1: 加入宣告律師-用戶端許可權偵測

如先前所述, 律師-用戶端許可權偵測模型是在預覽中。 因此, 在您組織 eDiscovery 系統管理員中的人員 (eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組成員), 必須選擇將模型提供給您的高級 eDiscovery 案例。

1. 在安全性 & 合規性中心內, 移至**eDiscovery > Advanced ediscovery**。

2. 在 [**高級 eDiscovery** ] 首頁上, 按一下 [**設定**] 磚中的 [設定**實驗的功能**]。

   ![按一下 [設定實驗功能]](../media/AeDExperimentalFeatures.png)

3. 在 [**實驗功能**] 索引標籤上, 按一下 [**管理律師-用戶端許可權] 設定**。

4. 在 [**律師-用戶端許可權**] 飛入頁面上, 按一下切換以開啟功能, 然後按一下 [**儲存**]。

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>步驟 2: 上傳律師清單 (選用)

若要充分利用律師用戶端的許可權偵測模型, 並使用先前所述的**** **授權或可能的特權**偵測結果, 建議您上傳為您的組織運作的律師和法務人員。 

若要上傳律師清單以供授權者-用戶端的許可權偵測模型使用:

1. 建立 .csv 檔案 (不含標題列), 並將每個適當人員的電子郵件地址新增到個別的一行。 將此檔案儲存到本機電腦。

2. 在 [ **Advanced eDiscovery** ] 首頁上, 按一下 [**設定**] 磚中的 [設定**實驗功能**], 然後按一下 [**管理律師-用戶端許可權] 設定**。

   隨即會顯示 [**律師-用戶端許可權**] 頁面, 並開啟 [**律師-用戶端許可權偵測**] 切換功能。

   ![律師-用戶端許可權飛出頁面](../media/AeDUploadAttorneyList.png)

3. 按一下 **[流覽]** , 然後尋找並選取您在步驟1中建立的 .csv 檔案。

4. 按一下 [**儲存**] 以上傳律師清單。

## <a name="use-the-attorney-client-privilege-detection-model"></a>使用律師-用戶端許可權偵測模型

請遵循本節中的步驟, 針對審閱集中的檔使用律師-用戶端許可權偵測。

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>步驟 1: 建立具有律師-用戶端許可權偵測模型的智慧標籤群組

在您的審查程式中查看律師-用戶端許可權偵測結果的其中一個主要方式, 就是使用智慧標籤群組。 智慧標籤群組會指出律師費-用戶端許可權偵測的結果, 並在智慧標籤群組中的標記旁邊以行顯示結果。 這可讓您在檔審閱期間快速找出可能具有特權的檔。 此外, 您也可以使用智慧標籤群組中的標記, 將檔標記為 [有許可權] 或 [非特權]。 如需有關智慧標籤的詳細資訊, 請參閱[在高級 eDiscovery 中設定智慧標籤](smart-tags.md)。

1. 在包含您在步驟1中分析之檔的審閱集中, 按一下 [**管理審閱集**], 然後按一下 [**管理標記**]。
 
2. 在 [**標記**] 下, 按一下 [**新增群組**] 旁的下拉式清單, 然後按一下 [**新增智慧標籤群組**]。

   ![按一下 [新增智慧標籤群組]](../media/AeDCreateSmartTag.png)

3. 在 [**選擇智慧標籤的模型**] 頁面上, 按一下 [在**律師-用戶端許可權**] 旁的 [**選取**]。

   隨即會顯示名為「**律師-用戶端」許可權**的標記群組。 它包含兩個名為**正值**和**負值**的子標記, 這會對應至模型產生的可能結果。

   ![律師-用戶端許可權智慧標籤群組](../media/AeDAttorneyClientSmartTagGroup.png)

3. 請視需要重新命名標記群組和標記。 例如, 您可以將**肯定**的重新命名為 [**許可權**] 和 [**否定**] 不需要的**許可權**。

### <a name="step-2-analyze-a-review-set"></a>步驟 2: 分析審閱集

當您分析審閱集中的檔時, 也會執行律師-用戶端許可權偵測模型, 以及對應的屬性 (說明[其運作方式](#how-does-it-work)) 將新增至審閱集中的每一份檔。 如需分析 [查看] 集中資料的詳細資訊, 請參閱[在高級 eDiscovery 中分析審閱集中的資料](analyzing-data-in-review-set.md)。

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>步驟 3: 使用智慧標籤群組以查看許可權內容

在分析檢查集並設定智慧標籤之後, 下一步是審閱檔。 如果模型判定檔有可能有許可權, 則 [**標記] 面板**中對應的智慧標籤將會指出由「律師-用戶端」許可權偵測所產生的下列結果:

- 如果檔中有可能是合法的內容, 則標籤的**合法內容**會顯示在對應的智慧標籤旁 (在此例中為預設的**正數**標記)。

- 如果檔有在您組織的律師清單中找到的參與者, 則標籤**律師**會顯示在對應的智慧標籤旁 (在此情況下, 也是預設的**正**標籤)。

- 如果檔中的內容可能是合法的,*且*在律師清單中找到了參與者, 則會顯示**法律內容**和**律師**標籤。 

如果模型決定檔不包含具有法律性質的內容, 或未包含律師清單中的參與者, 則 [標記] 面板中都不會顯示任何標籤。

例如, 下列螢幕擷取畫面顯示兩份檔;第一個專案包含合法的內容, 並有在律師清單中找到的參與者。第二個不包含任何一種, 因此不會顯示任何標籤。

![含律師和法律內容標籤的檔](../media/AeDTaggingPanelLegalContentAttorney.png)

![不含任何標籤的檔](../media/AeDTaggingPanelNegative.png)

檢查檔是否包含許可權內容之後, 您可以使用適當的標記來標記檔。