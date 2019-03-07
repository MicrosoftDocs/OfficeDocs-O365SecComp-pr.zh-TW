---
title: 管理 custodians 進階電子文件 （預覽） 案例中
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
ms.openlocfilehash: 6a21240f71c64f244ee42c3d3a2ed9d75381edaa
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454935"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a>管理 custodians 進階電子文件 （預覽） 案例中

[Custodians] 索引標籤包含的情況下的所有 custodians 排序清單。 Custodians 新增至案例之後，從 Azure Active Directory 會自動收集有關每個 custodian 的詳細資料。

![管理 Custodians](../media/CustodianDetails.PNG)

## <a name="viewing-custodian-details"></a>檢視 custodian 詳細資料

之後您將 custodian 新增至案例及**Custodians** ] 索引標籤上，從清單中選取他們，會出現包含 custodian 詳細資料彈出式頁面。從這裡開始，您可以檢視該 custodian 與相關的所有詳細資料。 彈出式頁面包含下列欄位：

- 連絡人資訊

  - **顯示名稱**： custodian 顯示在通訊錄中的名稱。 這通常是 custodian 名字]、 [中間的初始和最後一個名稱的組合。
  - **郵件/SMTP**: custodian，例如 jeff@contoso.onmicrosoft.com 的 SMTP 位址。  
  - **標題**： custodian 的職稱。
  - **部門**： custodian 適用於部門的名稱。
  - **管理員**： custodian 的管理員。 指定的管理員會收到此 custodian 任何呈報通訊。
  
- 位置資訊

  - **縣/市**： custodian 所在的市/鎮。
  - **狀態**： 縣 / 市 custodian 的地址。
  - **國家/地區**： 於 custodian 所在; 國家/地區例如，「 美國 」 或者 「 英國 」。
  - **Office**： 商務版 custodian 就地的辦公室位置。

- 案例資訊

  - **保留狀態**： 指出是否 custodian 具有已處於保留狀態。 
  - **通訊狀態**： 指出 custodian 是否已經發出保留通知。 如果 custodian 已發出的通知，這會被標示為*已發佈*。 如果 custodian 已不發出通知，則此狀態將會是*未發佈*。 
  - **狀態**： 在 case custodian 的狀態。 如果 custodian 仍處於保留的情況下，這會是*作用中*。 如果從案例移除 custodian，其狀態會變更為*發行*。 

- 處理狀態

  - **編製索引狀態**： 指出深層索引工作的狀態。  
  - **編製索引上次更新時間**： 指出的深層索引工作最後觸發 datestamp。
  - **資料來源**： 顯示的信箱、 網站和小組 custodian 已選取的計數。

## <a name="editing-a-custodian"></a>編輯 custodian

隨著您案例的進度，您可能會發現可能有其他資料來源相關的特定 custodian & 您的案例。 在其他情況下，您可能想要移除特定資料來源的檢閱和視為不相關。

若要更新 custodian 及選取的資料來源：

1. 從**eDiscovery > 進階電子文件 （預覽）** 中選取現有的案例。
  
2. 在案例中，按一下 [ **Custodians** ] 索引標籤。
  
3. 從清單中選取 custodian(s)，然後按一下 [**編輯來源**。

    ![編輯資料來源](../media/EditCustodianDataSource.PNG)
  
4. 按一下 [**選擇資料來源**，更新 Exchange 和 OneDrive 位置的選項。
  
5. 新增或移除 microsoft Teams、 SharePoint 或 Exchange 信箱]，即可選取**其他資料來源**對應的使用者。 如需您可以將對應的資料來源到 custodian 的方式的詳細資訊，請參閱 < <b0>Add custodians 案例</b0>。
  
6. 若要更新的 custodian 持有狀態，按一下 [ **custodial 就地保留**，以及啟用或停用 custodians 保留。

> [!TIP]
> 您可以選取多個 custodians 來執行 [大量動作]，或重新編製索引，放開，編輯一群 custodians 等。

## <a name="resolving-custodian-processing-errors"></a>解決 custodian 處理錯誤

大部分合法的工作流程，即會為特定的調查，新增 custodians 之後會搜尋使用者的資料子集。 因為大型檔案的大小或可能損毀，custodians 的資料來源中的某些項目可能是已局部編製索引。 使用進階電子文件 （預覽） 深層索引功能，這些已局部編製索引的項目可進行自動修復重新編目和重新編製索引視需要這些項目。 

當 custodian 新增至案例時，其資料將會自動為 「 deep 編製索引 」 時，允許使用者離開這些已局部編製索引而不必下載、 修正，並重新執行搜尋 Office 365 以外的位置中的項目。 週期中的情況下，使用者可能修復項目，或指定 custodian 新增新的資料來源。 這可能需要更新 Custodian 索引。 

若要觸發地址重新編製索引程序已局部編製索引的項目：

1. 移至**eDiscovery > 進階電子文件 （預覽）** ，然後選取現有的案例。

2. 在案例中，按一下 [ **Custodians] 索引標籤**。 

3. 選取 [需要以重新建立索引，然後按一下 [custodian(s) ![更新索引](../media/UpdateIndex.PNG) 在彈出式頁面。

4. **Custodians** ] 索引標籤上的 [**編製索引工作狀態**] 欄中的連結，即可檢查 custodian 索引的狀態。  

5. 在 [**工作**] 索引標籤上也可以追蹤重新編製索引的程序的狀態。

如需重新編製索引和補救局部編製索引的項目的詳細資訊，請參閱[修正處理錯誤](processing-data-for-case.md)。

## <a name="releasing-a-custodian-from-a-case"></a>釋放 custodian 從案例

Custodian 發行的情況下其中關閉案例、 custodian 不再下義務以保留內容的情況下，或當 custodian 會被視為不會再是相關為特定案例。 

如果已發佈保留通知之後，您就會釋放 custodian，發行通知會傳送至 custodian。 此外，也會移除歸因於發行 custodians 任何 custodial 保留。

如果 custodian 已處於暫止無訊息狀態，其所未發出任何合法持有通知，然後將移除歸因於發行 custodians 任何 custodial 保留。  

若要發行 custodian: 

1.  移至 [ **Custodians** ] 索引標籤。

2.  從清單中選取 custodian，然後按一下 [ ![版本 Custodian](../media/ReleaseCustodian.PNG) 在彈出式頁面。

    Custodian **Custodians** ] 索引標籤上的狀態設為**已發行**並**保留狀態**的彈出式頁面變更為**非作用中**。 

> [!TIP]
> Custodian 可同時可能參與數個合法持有事件。 當 custodian 發行從案例時，不會影響保留和跨其他事件通知。

## <a name="related-information"></a>相關資訊

 - [處理資料時發生補救錯誤](error-remediation.md) 
- [使用通訊](managing-custodian-communications.md)
