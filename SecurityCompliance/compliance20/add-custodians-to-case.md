---
title: 將 custodians 新增至進階的 eDiscovery （預覽） 案例
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c36e0a2228db042d50361460e2e22f13556e8715
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218213"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>將 custodians 新增至進階的 eDiscovery （預覽） 案例

使用進階的 eDiscovery （預覽），您可以運用協調繞管理 custodians 和相關、 custodial 資料來源的案例中用來識別您工作流程內建 okay 管理工具。當您新增 okay 時，系統可以自動識別、 和就地保留在其主要 Exchange 信箱和 OneDrive 商務網站。當您進行您探索，也可能會從抽出和對應其他信箱或網站確認 okay 存取過去或小組中 okay 是今天的成員。

新增及管理 custodians 安全性 & 規範中心內的進階的 eDiscovery （預覽） 案例中使用下列工作流程。 

## <a name="step-1-identify-potential-custodians"></a>步驟 1： 識別潛在 custodians

第一個步驟是以識別您專家的適當 custodians。若要新增 custodians 案例，您必須是 eDiscovery 管理員的成員或 eDiscovery 系統管理員角色群組。   

若要將 custodians 新增至現有的進階的 eDiscovery （預覽） 案例：

1. 從 [**進階的 eDiscovery （預覽）** ] 頁面上，移至您的案例。
 
2. 選取案例之後，請移至 [ **Custodians** ] 索引標籤並按一下 [ **+ 新增 Okay**。 
 
3. 選擇您想要新增至案例 custodians。您可以搜尋並從您的組織 Azure Active Directory 選取的使用者輸入來啟動。
 
4. 您已完成的 custodians 清單之後，按 [**下一**開始用來識別潛在的資料來源。 
   
## <a name="optional-step-2-select-custodian-data-sources"></a>（選用）步驟 2： 選取 okay 資料來源

新增 custodians 案例之後，您可以運用 Office 365 可協助您識別並保留主要 okay 資料來源。此工作流程的下一個步驟是選取步驟 1 中所指定 custodians 所擁有的資料來源。 

識別 okay 資料來源： 

1. 針對每個 okay 中，選取 [ **Exchange**如果您想要自動找出並新增 okay 主要 Exchange 信箱的系統。 
 
2. 針對每個 okay、 選取**OneDrive**如果您想要自動找出並新增 okay 主要 OneDrive URL 系統。 

    您是否已進行您的選擇之後, 這些系統將會自動嘗試找出的資料來源並將其新增至您的案例。
 
4. 按 [**下一**開始將其他資料來源對應至您 okay。

## <a name="optional-step-3-map-additional-data-sources"></a>（選用）步驟 3： 將對應其他資料來源

根據您的案例中，可能也想要新增給定的 okay 可能已經使用過去的信箱群組的 okay 那過去其中 okay 目前成員或網站。除了主要 okay 資料來源而言，您可以為 okay 新增其他 Office 365 的資料來源或利用 Office 365 可協助您識別也可能相關的資料來源。 

若要將信箱、 網站或小組對應至特定 okay：

1. 選取要指派給特定 okay 的信箱、 網站和小組類似的內容位置**更新**。 

2. 彈出式中指定下列項目：
   
  -  **Exchange 信箱**-[**選擇使用者、 群組或小組**和 [**選擇使用者、 群組或小組**一次。若要指定要指派給所選 okay 信箱，使用 [搜尋] 方塊中尋找使用者信箱和通訊群組。您也可以針對 Office 365 群組或 Microsoft 小組指派關聯的信箱。選取使用者、 群組、 小組] 核取方塊、 按一下 [**選擇**] 和 [**完成**。

      > [!NOTE]
      > 當您按一下 [選擇使用者、 群組或小組來指定信箱時，會顯示信箱選擇是空的。這是由設計，以提升效能。若要將人員新增至這份清單中，輸入的名稱 （至少要有 3 個字元） 在 [搜尋] 方塊中。
     
   - **SharePoint 網站**-按一下 [**選擇的網站**] 和 [一次可指定您想要指派給所選 okay 商務網站其他 SharePoint 及 OneDrive 的**選擇網站**。您也可以針對 Office 365 群組或 Microsoft 小組新增 SharePoint 網站的 URL。輸入您要指派每個網站的 URL。按一下 [**選擇**] 和 [**完成**。
   - **Microsoft 小組**– 按一下 [**選擇 [小組**] 和 [**選擇小組**再次若要檢視清單中的 Microsoft 小組群組 okay 是今天的成員。選取您想要新增至您 okay 小組。一旦選取，系統會自動識別 & 選取相關聯的 [SharePoint 網站] 和 [群組信箱相關聯的 Microsoft 小組。按一下 [**選擇**] 和 [**完成**。
        
      > [!NOTE]
      > 若要新增其他的 Microsoft 小組，您必須分別新增信箱和 SharePoint 網站上面所示。

完成對應您的來源之後，您可以檢視您剛新增 custodians 信箱總數、 網站及小組。當您已完成相關之資料來源的特定 okay 時，此對應會維護及延伸至 eDiscovery 集合、 處理和檢閱工作流程。 

## <a name="optional-step-4-place-custodians-on-hold"></a>（選用）步驟 4： 就地保留在 custodians

 您已完成的 custodians 與您想要新增至您案例的資料來源之後，您可以選擇性地放置某些或您 custodians 上的所有保留。當您保留上放置 okay 時，對應至該使用者的內容會保留直到您放開 okay 從案例或直到您刪除保留。在某些情況下，可能會想要新增 custodians 案例而不將其置於保留。 

若要放置在所選 custodians 與資料來源上的保留：

1. 確認 okay 選項，然後選取每個 okay 置於保留的核取方塊。一旦 okay 處於保留狀態，將會自動建立包含所有 custodial 來源 okay 保留原則。如果未選取這個選項，okay & 選取資料來源會新增至案例但不是會保留內容。

2. 移至 [**保留**] 索引標籤並選取**Okay 保留原則**。 

3. 按一下 [**編輯**] 以檢視所有選取的 okay 資料來源。
