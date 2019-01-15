---
title: 搜尋並刪除您的 Office 365 組織-Admin 說明中的電子郵件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用搜尋並清除 Office 365 安全性功能&amp;規範中心來搜尋並刪除您組織中所有信箱的電子郵件訊息。
ms.openlocfilehash: 82ba38ef2c3c8c6b78743a4b2263dde0ef3a5b48
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015015"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>搜尋並刪除您的 Office 365 組織-Admin 說明中的電子郵件

**本文適用於系統管理員。您試圖尋找您想要刪除的信箱中的項目請參閱[尋找訊息或具有立即搜尋的項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
您可以使用 Office 365 中的 「 內容搜尋功能來搜尋並在組織中刪除所有信箱的電子郵件訊息。這可協助您尋找及移除潛在有害或高風險的電子郵件，例如：
  
- 包含危險附件或病毒的郵件
    
- 網路釣魚郵件
    
- 包含敏感資料的郵件
    
> [!CAUTION]
> 搜尋和清除是強大功能，可讓任何人指派刪除您組織中信箱的電子郵件訊息的必要權限。 
  
## <a name="before-you-begin"></a>開始之前

- 若要建立並執行內容的搜尋，您必須是**eDiscovery 管理員**角色群組的成員或**規範搜尋**管理角色指派。若要刪除的郵件，您必須是 「**組織管理**角色群組的成員或**搜尋和清除**管理角色指派。如需將使用者新增至角色群組，請參閱[授與使用者存取 Office 365 安全性&amp;規範中心](grant-access-to-the-security-and-compliance-center.md)。
    
- 您必須使用安全性&amp;規範中心 PowerShell 来刪除的郵件。請參閱[Step 2](#step-2-connect-to-security-amp-compliance-center-powershell)的連線方式的相關指示。
    
- 每個信箱的 10 個項目最多可以一次移除。搜尋並移除郵件的功能為了要事件回應工具，因為此限制可協助確保從信箱快速地移除訊息。此功能並未清除 [使用者信箱適用對象。若要刪除超過 10 個項目，您可以使用**Search-mailbox DeleteContent**命令在 Exchange Online PowerShell。請參閱[搜尋和刪除郵件-Admin 說明](search-for-and-delete-messagesadmin-help.md)。
    
- 內容搜尋您可以刪除項目中的搜尋並清除巨集指令中的信箱數目上限為 50000。如果內容搜尋 （您在[步驟 1](#step-1-create-a-content-search-to-find-the-message-to-delete)中建立） 有超過 50000 個來源信箱，將會失敗的清除動作 （您在步驟 3 中建立）。請參閱[的詳細資訊](#more-information)] 區段中的提示上執行搜尋並清除超過 50000 個信箱上的作業。 
    
- 本文中的程序只可以用來刪除 Exchange Online 信箱和公用資料夾中的項目。您無法使用它來刪除內容 SharePoint 或 OneDrive for Business 的網站。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>步驟 1：建立內容搜尋來尋找要刪除的郵件

第一個步驟是建立及執行內容的搜尋來尋找您想要移除您組織中信箱的郵件。您可以使用 [安全性] 來建立搜尋&amp;規範中心或執行**新增 ComplianceSearch**和**開始 ComplianceSearch**指令程式。[步驟 3](#step-3-delete-the-message)中執行**新增 ComplianceSearchAction**指令程式將會刪除符合此搜尋查詢的郵件。如需建立內容的搜尋及設定搜尋查詢，請參閱下列主題： 
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> 您在此步驟中建立的內容搜尋中搜尋的內容位置不能包含 SharePoint 或 OneDrive for Business 的網站。您可以將用於電子郵件訊息內容搜尋中包含只信箱與公用資料夾。如果內容搜尋包含網站，將會收到錯誤步驟 3 中執行**新增 ComplianceSearchAction**指令程式時。 
  
### <a name="tips-for-finding-messages-to-remove"></a>尋找要移除的郵件的提示

搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：
  
- 如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。 
    
- 如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。 
    
- 如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。 
    
- 預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。
    
- 使用搜尋評估統計資料 (搜尋安全性的詳細資料窗格中顯示&amp;規範中心或使用[Get ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)指令程式來) 若要取得的結果總數計數。 
    
以下是尋找可疑電子郵件訊息的兩個查詢範例。
  
- 此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- 此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security-amp-compliance-center-powershell"></a>步驟 2： 連線至安全性&amp;規範中心 PowerShell

下一步是連線至安全性&amp;貴組織的規範中心 PowerShell。如需逐步說明，請參閱[連線至 Office 365 安全性&amp;規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
如果您的 Office 365 帳戶使用多重要素驗證 (MFA) 或同盟的驗證，則無法使用指示先前在連線至安全性主題中&amp;規範中心 PowerShell。但是，請參閱主題中的指示[連線至 Office 365 安全性&amp;規範中心 PowerShell 使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)。
  
## <a name="step-3-delete-the-message"></a>步驟 3： 刪除郵件

您已建立並精簡內容搜尋以傳回您想要移除並連接到安全性訊息之後&amp;規範中心 PowerShell 中的最後一個步驟是執行**新增 ComplianceSearchAction** cmdlet 來刪除郵件。您可以虛或硬-刪除郵件。虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾及保留，直到刪除項目保留期間到期為止。硬碟已刪除的郵件標記為永久移除從信箱並將會永久移除受管理的資料夾助理員處理此信箱的下一次。如果信箱啟用單一項目復原，則硬碟已刪除的項目將永久移除後刪除項目保留期間到期。如果信箱處於保留狀態，刪除的郵件會保留項目的保留期間到期直到或從信箱移除保留為止。
  
在下列範例中，此命令將會虛刪除名為"移除網路釣魚 Message"的內容搜尋所傳回的搜尋結果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```
在下列範例中，命令會完全刪除名為"移除網路釣魚 Message"的內容搜尋所傳回的搜尋結果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

*SearchName*參數所指定的搜尋是您在步驟 1 中建立內容搜尋。 

硬碟-刪除"移除網路釣魚訊息 「 內容搜尋傳回的項目，則會執行此命令：

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```
  
如需詳細資訊，請參閱[新增 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。
  

## <a name="more-information"></a>詳細資訊

- **如何取得的搜尋狀態及移除作業嗎？**

    執行**Get ComplianceSearchAction**以取得刪除作業狀態。請注意當您執行**新增 ComplianceSearchAction**指令程式時所建立的物件名為使用此格式： `<name of Content Search>_Purge`。 
    
- **刪除郵件之後會發生什麼事？**

   使用已刪除的訊息`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令移至 [清除] 資料夾，且無法供使用者存取。將郵件移至 [清除] 資料夾之後，郵件會保留已刪除的項目保留期間的持續期間如果單一項目復原已啟用信箱。（Office 365 的單一項目復原預設會啟用時建立新的信箱。）刪除項目保留期間到期後，標記為永久刪除郵件，並將來自 Office 365 清除信箱由受管理的資料夾助理員處理下一次。 

   如果您使用`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令郵件會移到使用者的 [可復原的項目] 資料夾中的 [刪除] 資料夾。它不是立即清除來自 Office 365。使用者可以設定信箱已刪除的項目保留期間為基礎的持續期間復原刪除的郵件] 資料夾中的郵件。此保留期間到期 （或如果使用者清除前的郵件會到期後），郵件移至 [清除] 資料夾，並不會再使用者存取。一次 [清除] 資料夾中郵件會保留已刪除的項目保留期間如果單一項目復原已啟用信箱的信箱設定為基礎的工期。（Office 365 的單一項目復原預設會啟用時建立新的信箱。）刪除項目保留期間到期後，標記為永久刪除郵件，並將來自 Office 365 清除信箱由受管理的資料夾助理員處理下一次。 
    
- **如果您必須刪除超過 50000 個信箱的郵件吗？**

    先前所述，您可以執行搜尋，並清除最大值為 50000 信箱上的作業。如果您有執行搜尋並清除超過 50000 個信箱上的作業，請考慮建立暫存搜尋權限篩選就會降低會小於 50000 信箱搜尋的信箱數目。例如，如果您的組織會包含不同部門、 states 或國家的信箱，您可以建立根據其中這些信箱来搜尋的內容信箱的子集您組織中的信箱搜尋的權限篩選器。建立搜尋權限篩選之後，您會建立 （在步驟 1 中所述） 搜尋，然後刪除郵件 （步驟 3 中所述）。然後您可以編輯的篩選來搜尋並清除一組不同的信箱中的郵件。如需建立搜尋權限篩選器的詳細資訊，請參閱 ＜ [Configure 權限的內容搜尋篩選](permissions-filtering-for-content-search.md)。
    
- **將會刪除包含在搜尋結果中編製索引的項目吗？**

    否，' 新增 ComplianceSearchAction-Purge 命令不會刪除編製索引的項目。 
    
- **如果從已處於就地保留或訴訟暫止狀態或指派給 Office 365 保留原則的信箱刪除郵件發生什麼情況？**

    郵件已清除，並移至 [清除資料夾之後，郵件會保留直到保留期間到期。若無限制保留持續時間，則會保留項目，直到移除保留或變更的保留期間。
    
- **為什麼要選擇搜尋及移除這些分散不同的安全性與規範中心角色群組的工作流程？**

    如先前所述人員有 eDiscovery 管理員角色群組的成員或來搜尋信箱的規範搜尋管理角色指派。若要刪除的郵件，人員必須是 「 組織管理角色群組的成員或搜尋和清除管理角色指派。這可讓控制項誰可在組織中搜尋信箱和誰可以刪除郵件。 
