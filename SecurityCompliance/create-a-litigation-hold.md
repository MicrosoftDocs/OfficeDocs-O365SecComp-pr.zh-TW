---
title: 在 Office 365 中建立訴訟暫止狀態
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: aa78d12046108aa1f1b974f01c02ff923b99b97b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037956"
---
# <a name="create-a-litigation-hold-in-office-365"></a>在 Office 365 中建立訴訟暫止狀態

將信箱置於訴訟暫止狀態保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。您將使用者信箱置於訴訟暫止狀態，使用者的封存信箱中的內容 （如果已啟用） 是也會保留。當您建立保留時，您可以指定保留期間 （也稱為*時間型保留*） 使刪除及修改過的項目會在指定期間內保留與永久刪除信箱。您可以只會無限期保留內容或者 （稱為*無限保留*） 或直到訴訟暫止狀態已移除。如果您指定保留持續時間期間，它會計算日期接收郵件或建立信箱項目。 
  
以下是您建立訴訟暫止狀態時會發生什麼情況。
  
- 永久刪除之使用者的項目會保留在使用者的信箱 [可復原的項目] 資料夾中的保留期間。
    
- 會在使用者將從 [可復原的項目] 資料夾清除的項目都會保留的保留期間。
    
- 儲存配額可復原的項目] 資料夾是從 30 GB 增加為 110 GB。
    
- 在使用者的主要和封存信箱中的項目保留
    
## <a name="before-you-begin"></a>開始之前

- Exchange Online 的信箱置於訴訟暫止狀態，它必須被指派 Exchange Online 計劃 2 授權。如果信箱指派 Exchange Online 計劃 1 授權，您必須將其放入個別 Exchange Online 封存授權保留指派。
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>將信箱置於訴訟保留在 Office 365 系統管理中心

以下是置於訴訟暫止狀態使用 Office 365 系統管理中心信箱的步驟。

1. 移至 [https://portal.office.com/adminportal/home並使用您的全域管理員帳戶登入。
2. 按一下 [**使用者** > 的左的功能窗格中的**作用中使用者**。
3. 選取您想要置於訴訟保留其信箱的使用者。
4. 彈出式] 索引標籤上 [**郵件設定**] 和 [**訴訟暫止狀態**] 旁的 [**編輯**。
5. 在**訴訟暫止狀態**] 頁面上按一下 [開啟訴訟暫止狀態並完成會顯示下列選用設定切換：
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    a.**保留期間 （天）** -使用此方塊來建立時間型保留與指定信箱處於訴訟暫止狀態時，長保留信箱項目。信箱項目會接收或建立日期被計算持續時間。如果您保留此方塊空白，項目會保留無限期或直到移除保留為止。用於持續時間指定天數。
    
    b.**附註**-使用此方塊來通知的使用者他們的信箱處於訴訟暫止狀態。附註如果將會出現在使用者的信箱中的 [帳戶資訊] 頁面上所使用的 Outlook 2010 或更新版本。若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。
     
    c. **Web 頁面**-使用此方塊可將使用者導向至訴訟暫止狀態的詳細資訊的網站。如果其於使用 Outlook 2010 或更新版本上使用者的信箱中的 [帳戶資訊] 頁面上會出現此 URL。若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。
 
6. 按一下 [**儲存**] 以建立訴訟暫止狀態。

建立保留之後，在彈出式] 頁面上的信箱設定會顯示的訴訟暫止狀態在已開啟選取的使用者。

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

如需建立及管理訴訟保留及使用 Exchange Online PowerShell 大量建立訴訟保留的詳細資訊，請參閱[Place 在訴訟暫止狀態的信箱](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)。
