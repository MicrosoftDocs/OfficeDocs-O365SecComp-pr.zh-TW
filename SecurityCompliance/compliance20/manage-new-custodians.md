---
title: 管理進階的 eDiscovery （預覽） 案例中的 custodians
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
ms.openlocfilehash: 95a1bcbbc279ad4e476fc479e701b0f8a921c83b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295676"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a>管理進階的 eDiscovery （預覽） 案例中的 custodians

[Custodians] 索引標籤包含案例中的所有 custodians 可排序的清單。Custodians 新增至案例之後，Azure Active Directory 中會自動收集有關每個 okay 的詳細資料。

## <a name="viewing-custodian-details"></a>檢視 okay 詳細資料

含有 okay 詳細資料彈出式] 頁面隨即顯示之後將 okay 新增至案例並從 [ **Custodians** ] 索引標籤上的清單中加以選取。從這裡，您可以檢視該 okay 相關的所有詳細資料。彈出式頁面包含下列欄位：

- 連絡人資訊

  - **顯示名稱**： okay 顯示在通訊錄中的名稱。這通常是 okay 名字、 中間的初始和最後一個名稱的組合。
  - **郵件/SMTP**: okay，例如 jeff@contoso.onmicrosoft.com 的 SMTP 位址。  
  - **標題**： okay 的職稱。
  - **部門**： 部門 okay 運作方式的名稱。
  - **Manager**: okay 的管理員。指定的管理員將會收到此 okay 任何呈報通訊。
  
- 位置資訊

  - **縣/市**： okay 所在位置的城市。
  - **狀態**： 位置的省或市 okay 地址。
  - **國家 （地區）**： 在其中 okay 位於; 國家/地區例如，"US"或者"英國"。
  - **Office**： 業務的 okay 就地的辦公室位置。

- 案例資訊

  - **保留狀態**： 指出是否 okay 具有已處於保留狀態。 
  - **通訊狀態**： 指出 okay 是否已發行的保留通知。如果已核發給 okay 請注意，這將會標示為*已發佈*。如果 okay 不已發行的通知，然後將此狀態*解除發佈*。 
  - **狀態**： okay 內大小寫的狀態。這是*Active* okay 時仍在保留案例。已從案例移除 okay 則及其狀態會變更為*發行*。 

- 處理狀態

  - **編製索引狀態**： 指出深層索引工作的狀態。  
  - **編製索引上次更新時間**： 指出的最後一個觸發深層索引工作 datestamp。
  - **資料來源**： 顯示的信箱、 網站和小組已選取的 okay 計數。

## <a name="updating-a-custodian"></a>更新 okay

隨著您案例的進度，您可能會發現可能有其他資料來源相關的特定 okay & 您的案例。在其他情況下，可能會想要移除特定資料來源的檢閱和視為不相關。

若要更新 okay 及選取的資料來源：

1. 從**eDiscovery > 進階的 eDiscovery (Preview)** 中選取現有的案例。
  
2. 情況下，按一下 [ **Custodians**索引標籤。
  
3. 從清單中選取 custodian(s) 並按一下 [**編輯來源**。
  
4. 依序按一下 [**選擇資料來源**中更新 Exchange 和 OneDrive 位置的選項。
  
5. 新增或移除小組、 SharePoint、 或 Exchange 信箱對應使用者按一下以**選取其他資料來源**。如需您可以將對應的資料來源以 okay 的方式的詳細資訊，請參閱 ＜ [Add custodians 案例](add-custodians-to-case.md)。
  
6. 若要更新之 okay 持有狀態，按一下 [ **custodial 就地保留**，並啟用或停用 custodians 保留。

> [!TIP]
> 您可以選取多個 custodians 執行大量動作，像重新編製索引、 釋放，或編輯 custodians 一組。

## <a name="resolving-custodian-processing-errors"></a>協助您解決 okay 處理錯誤

大部分的法律工作流程的 custodians 新增針對特定的調查之後, 會搜尋之使用者的資料子集。因為大型檔案大小或可能損毀、 custodians 的資料來源中的某些項目可能是部分編製索引。使用 「 進階的 eDiscovery （預覽） 深層索引 」 功能，這些部分已編製索引的項目可以是自動在於重新編目，並重新編製索引隨選這些項目。 

當 okay 加入至案例時，自己的資料將會自動為"deep 編製索引 」，讓使用者能夠部分保留這些編製索引而不需要下載、 修復及重新執行搜尋 Office 365 外部的進行中的項目。案例的技術支援週期期間的使用者可能會修復項目或新增新的資料來源的特定 okay。這可能需要更新 Okay 索引。 

若要觸發重新索引程序，以地址部分編製索引的項目：

1. 移至**eDiscovery > 進階的 eDiscovery （預覽）** 並選取現有的案例。

2. 在案例中，按一下 [ **Custodians] 索引標籤**。 

3. 選取需要重新編製索引，custodian(s) 然後再按一下 [彈出式頁面上的 [**更新索引**。

4. 按一下連結**Custodians** ] 索引標籤上的 [**編製索引工作狀態**] 欄中檢查 okay 索引的狀態。  

5. 也可以在 [**工作**] 索引標籤上追蹤重新索引程序的狀態。

如需重新索引及補救部分已編製索引項目的詳細資訊，請參閱[修正處理錯誤](processing-data-for-case.md)。

## <a name="releasing-a-custodian-from-a-case"></a>釋放 okay 從案例

Okay 發行情況其中關閉案例、 okay 不再下義務来保留內容的案例中，或當 okay 已被視為不會再是相關內容為特定案例。 

如果已發佈的保留通知後釋放 okay 版本通知將會傳送至 okay。此外，也會移除對應到發行的 custodians 任何 custodial 保留。

如果 okay 被指定無訊息保留其已不發出任何合法持有通知，將會移除對應到發行的 custodians 任何 custodial 保留。  

若要發行 okay: 

1.  移至 [ **Custodians** ] 索引標籤。

2.  從清單中選取 okay 並按一下**版本 custodians**彈出式頁面上。

    Okay **Custodians** ] 索引標籤上的狀態設為**發行**和**保留狀態**彈出式] 頁面上會變更為**非使用中**。 

> [!TIP]
> Okay 可能同時也會參與數個合法持有不僅。當 okay 發行從案例時，不會影響 [保留] 及 [其他不僅不同的通知。

## <a name="related-information"></a>相關資訊

 - [處理資料時發生補救錯誤](error-remediation.md) 
- [使用通訊](managing-custodian-communications.md)
