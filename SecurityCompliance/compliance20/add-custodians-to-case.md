---
title: 新增 custodians 至進階電子文件 （預覽） 案例
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fe208f4a9f7927d8481d5c6ec8b901baafb98626
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455295"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>新增 custodians 至進階電子文件 （預覽） 案例

使用進階電子文件 （預覽），您可以利用內建 custodian 管理工具，來調整您的工作流程管理 custodians 和識別案例中的相關、 custodial 資料來源周圍。 當您新增 custodian 時，系統可以自動辨識，和就地保留在其主要 Exchange 信箱和 OneDrive for Business 網站。 當您進行您探索，您可能也從抽出及對應其他信箱或網站，custodian 存取過去或小組中 custodian 是今天的成員。

若要新增及管理 custodians 在進階電子文件 （預覽） 安全性 & 合規性中心內的情況下使用下列工作流程。 

![Custodian 管理] 索引標籤](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a>步驟 1： 找出潛在 custodians

第一個步驟是以識別您專家的適當 custodians。 若要新增 custodians 案例，您必須是成員的 eDiscovery 管理員或 eDiscovery 管理員 」 角色群組。   

![識別潛在 Custodians](../media/AddCustodianStep1.png)

若要將 custodians 新增至現有的進階電子文件 （預覽） 案例：

1. 從 [**進階電子文件 （預覽）** ] 頁面上，移至您的案例。
 
2. 選取案例之後，請移至 [ **Custodians** ] 索引標籤，然後按一下 [ **+ 新增 Custodian**。 
 
3. 選擇您想要新增至案例 custodians。 您可以啟動搜尋並從貴組織的 Azure Active Directory 選取使用者的輸入。
 
4. 您已完成的 custodians 清單之後，按 [**下一**開始用來識別潛在的資料來源。 
  
## <a name="optional-step-2-select-custodian-data-sources"></a>（選用）步驟 2： 選取 [custodian 資料來源

Custodians 新增至案例之後，您可以利用 Office 365，以協助您識別並保存 custodian 主要資料來源。 此工作流程的下一個步驟是選取步驟 1 中所指定 custodians 所擁有的資料來源。 

![選取 [Custodial 資料來源](../media/AddCustodianStep2.png)

若要找出 custodian 資料來源： 

1. 針對每個 custodian 中，選取**Exchange** ，如果您想要自動識別，並新增 custodian 主要 Exchange 信箱系統。 
 
2. 每個 custodian 中，選取 [ **OneDrive**如果您想要自動識別，並新增 custodian 主要 OneDrive URL 的系統。 

    進行您的選擇之後, 他們系統會自動嘗試找出資料來源，並將其新增至您的案例。
 
4. 按 [**下一步**開始將其他資料來源對應至您 custodian。

## <a name="optional-step-3-map-additional-data-sources"></a>（選用）步驟 3： 將其他資料來源對應

根據您的情況下，您可能還想要新增給定的 custodian 可能是在過去，使用的信箱群組其中 custodian 目前成員，或網站 custodian，必須在過去的存取權。 除了主要 custodian 資料來源，您可以將其他 Office 365 的資料來源新增至 custodian，或利用 Office 365，可協助您識別也可能相關的資料來源。 

![將其他資料來源對應](../media/AddCustodianStep3.PNG)

若要將信箱、 網站或小組對應至特定 custodian:
1. 選取 [**新增**若要將內容的位置，例如信箱、 網站和小組，指派給特定 custodian。 

2. 在彈出式視窗中，指定下列設定：![對應的資料來源](../media/AddCustodianStep4.PNG)
  -  **Exchange 信箱**-按一下 [**選擇使用者、 群組或小組**，然後再按一下 [**選擇使用者、 群組或小組**。 若要指定要指派給所選 custodian 的信箱，請使用 [搜尋] 方塊來尋找使用者信箱和通訊群組。 您也可以針對 Office 365 群組或 Microsoft 小組指派相關聯的信箱。 選取使用者、 群組、 小組] 核取方塊，按一下 [**選擇**，然後按一下 [**完成**。

        > [!NOTE]
        > 當您按一下 [選擇使用者、 群組或小組來指定信箱時，會顯示信箱選擇器是空的。 這項設計的目的是提升效能。 若要將人員新增至這份清單中，輸入的名稱 （3 個字元的最少） 在 [搜尋] 方塊中。
     
     - **SharePoint 網站**-按一下 [**選擇網站**]，然後按一下 [**選擇網站**再次指定其他的 SharePoint 和 OneDrive for Business 網站，您可能會想要指派給所選 custodian。 您也可以新增 SharePoint 網站的 URL 的 Office 365 群組或 Microsoft 小組。 輸入您想要指派每個網站的 URL。 按一下 [**選擇**，然後按一下 [**完成**。
     - **Microsoft Teams** – 按一下 [**選擇小組**，然後按一下 [**選擇小組**再次以檢視 Microsoft 小組群組 custodian 是今天成員的清單。 選取您想要新增至您 custodian Teams。 一旦選取，系統會自動識別相關聯的 [SharePoint 網站] 及 [群組信箱相關聯的 Microsoft Team & 選取。 按一下 [**選擇**，然後按一下 [**完成**。
        
      > [!NOTE]
      > 若要新增其他的 Microsoft Teams，您需要分別新增的信箱和 SharePoint 網站如上所示。

完成對應您的來源之後，您可以檢視您剛新增 custodians 信箱總數、 網站及 microsoft Teams。 當您完成相關的資料來源的特定 custodian 時，將會維護此對應，而且延伸至 eDiscovery 收集、 處理及檢閱工作流程。 

## <a name="optional-step-4-place-custodians-on-hold"></a>（選用）步驟 4： 就地 custodians 上保留

![就地保留](../media/AddCustodianStep5.PNG)

您已完成的 custodians 和您想要新增至您案例的資料來源之後，您可以選擇性地放置部分或所有在您 custodians 保留。 當您保留上放置 custodian 時，對應至該使用者的內容會保留直到您放開 custodian 從這種情況，或直到您刪除保留。 在某些情況下，您可能想要將 custodians 新增至案例中，而不將其置於保留狀態。 

若要將所選 custodians 與資料來源上的保留：

1. 驗證 custodian 選項，然後選取要就地保留每個 custodian] 核取方塊。 Custodian 處於保留狀態之後，就會自動建立包含所有 custodial 來源 custodian 保留原則。 如果選項不會檢查，custodian，而且不是選取資料來源會新增至案例，但將不會保留內容。

2. 移至 [**保留**] 索引標籤，然後選取 [ **Custodian 保留原則**。 

3. 按一下 [**編輯**] 以檢視所有選取的 custodian 資料來源。

   
