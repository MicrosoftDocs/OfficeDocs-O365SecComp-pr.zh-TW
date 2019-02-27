---
title: 建立及管理 Office 365 中的非使用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 您可以建立 Office 365 中的非使用中的信箱將保留或 Office 365 保留原則套用至信箱並再將其刪除對應的 Office 365 使用者帳戶。保留或保留原則套用至其已進行非使用中之前的期間，會保留不在作用中的信箱中的項目。若要永久刪除非作用中的信箱，只是移除保留或保留原則。
ms.openlocfilehash: 1f5d0aa01e9688aaa5955b9721dded9b85afdfba
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295516"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>建立及管理 Office 365 中的非使用中信箱

Office 365 可以讓您保留已刪除信箱的內容。此功能會呼叫[不在作用中的信箱](inactive-mailboxes-in-office-365.md)。非使用中信箱可讓您保留先前的員工電子郵件之後他們離開貴組織。訴訟暫止狀態或 Office 365 保留原則時信箱會變成非作用中 (建立 Office 365 安全性&amp;規範中心) 對應的 Office 365 使用者帳戶會在刪除之前會套用至信箱。不在作用中信箱的內容會保留它進行非使用中之前被指定信箱的保留期間。這可讓系統管理員、 法務人員及記錄經理可以使用內容的搜尋安全性&amp;規範中心來搜尋並匯出非使用中信箱的內容。非使用中信箱無法接收電子郵件及未出現在您的組織共用的通訊錄或其他清單。
  
> [!NOTE]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 若要停用信箱，它必須被指派 Exchange Online 計劃 2 授權使訴訟暫止狀態或 Office 365 保留原則可套用至信箱會在刪除之前。Exchange Online 計劃 2 授權是 Office 365 企業版 E3 和 E5 訂閱的一部分。如果信箱指派 Exchange Online 計劃 1 授權 （這是 Office 365 企業版 E1 訂閱的一部分），您必須將使保留可套用至信箱會在刪除之前將其指派不同的 Exchange Online 封存授權。如需詳細資訊，請參閱[Exchange Online 封存](https://go.microsoft.com/fwlink/p/?LinkId=286153)。
    
- 刪除對應的 Office 365 使用者帳戶之後將可以使用 [刪除的 Exchange Online 信箱相關聯的授權。然後您可以[指派給 Office 365 中的商務使用者的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)給另一個使用者。 
    
- 如果訴訟暫止狀態或 Office 365 保留原則不套用到信箱會在刪除之前內容不會是信箱的保留或可供搜尋。不過，刪除排程、 30 天內可復原已刪除的信箱但信箱和其內容會永久刪除 30 天後如果它不復原。
    
- 如需訴訟暫止狀態的詳細資訊，請參閱[就地保留和訴訟暫止狀態](https://go.microsoft.com/fwlink/p/?LinkId=846124)。如需關於 Office 365 安全性的保留原則&amp;規範中心，請參閱[Overview of Office 365 中的保留原則](retention-policies.md)。
  
## <a name="create-an-inactive-mailbox"></a>建立非使用中信箱

讓信箱不在作用中包含兩個步驟： 1） 將放置信箱訴訟暫止狀態或 Office 365 保留原則套用到其中，和 2） 刪除信箱或相對應的 Office 365 使用者帳戶。不在作用中信箱後，直到移除保留或保留原則將會保留其內容。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>步驟 1： 將信箱置於訴訟暫止狀態或適用於 Office 365 保留原則

訴訟暫止狀態將信箱設定或套用 Office 365 保留原則會在刪除之前會保留信箱中的內容。這兩種類型的保留會保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。已刪除及修改過的項目會保留在非使用中的信箱在指定的期間內或直到您永久刪除非使用中信箱移除套用至非使用中信箱的保留或保留原則。
  
如果保留已處於信箱或 Office 365 保留原則已套用到信箱，則您只需要是步驟 2 所述刪除對應的 Office 365 使用者帳戶。
  
將信箱設定訴訟暫止狀態或將 Office 365 保留原則套用的逐步程序，請參閱：
  
- [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Office 365 中的保留原則的概觀](retention-policies.md)
    
> [!NOTE]
> 訴訟保留與 Office 365 的保留原則，您可以建立無限期保留或在時間型保留。在無限期保留，不在作用中信箱的內容將永久，保留或直到移除保留或直到變更保留持續時間。保留或保留原則移除 （假設信箱已遭刪除超過 30 天） 後，將目標記為要永久刪除非使用中信箱和信箱的內容不再是保留或可供搜尋。時間型保留或 Office 365 保留原則，您會指定保留的期限。此持續時間是每個項目和信箱項目所接收或建立日期開始。保留信箱項目到期以及該項目移至或非使用中的信箱中的可復原的項目] 資料夾位於之後，此項目會永久刪除 （清除） 從非使用中信箱後刪除項目保留期間到期。 
  
### <a name="step-2-delete-the-mailbox"></a>步驟 2：刪除信箱

信箱處於保留狀態或 Office 365 保留原則套用至其之後下, 一步是以刪除信箱。若要刪除信箱的最佳方式是要刪除對應的 Office 365 使用者帳戶在 Office 365 系統管理中心。刪除 Office 365 使用者帳戶的相關資訊，請參閱[刪除您組織中的使用者](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)。
  
> [!NOTE]
> 您也可以在 Exchange Online PowerShell 中使用**Remove-mailbox**指令程式刪除信箱。如需詳細資訊，請參閱[刪除或還原使用者信箱在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287)。 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>檢視非使用中信箱的清單


若要檢視您組織中的非使用中信箱的清單：
  
1. 移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。 
    
2. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> * * 保留 * *。
    
3. 在 [**保留**] 頁面上按一下 [**更多**![導覽列省略符號](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)，然後按一下 [**非使用中的信箱**。
    
    ![在 [保留] 頁面上，按一下 [更多及 [非使用中信箱移轉至顯示不在作用中信箱的清單](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    會顯示 [**非使用中信箱**] 頁面。請注意顯示組織中不在作用中的信箱總數。 
    
    ![會顯示您組織中的所有非使用中信箱的清單](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
或者，您可以執行下列命令在 Exchange Online PowerShell 來顯示不在作用中信箱的清單。

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

您可以按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**匯出**檢視或下載 CSV 檔案包含您組織中不在作用中信箱的其他資訊。 
  
您也可以執行下列命令以將非使用中信箱的清單和其他資訊匯出至 CSV 檔案。在這個範例中，目前目錄中建立 CSV 檔案。

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> 有可能不在作用中的信箱可能會有相同的 SMTP 地址為作用中使用者信箱。在此例中**DistinguishedName**或**ExchangeGuid**屬性的值可以用來唯一地識別非使用中的信箱。 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜尋並匯出非使用中信箱的內容

您可以使用 「 內容搜尋工具安全性存取非使用中信箱的內容&amp;規範中心。當您搜尋非使用中的信箱時，您可以建立關鍵字搜尋查詢，搜尋特定的項目或您可以傳回非使用中信箱的完整內容。您可以預覽搜尋結果或將搜尋結果匯出至 Outlook 資料 (PST) 檔案或以個別的電子郵件訊息方式。搜尋信箱及匯出搜尋結果的逐步程序，請參閱下列主題：
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心](export-search-results.md)
    
以下是搜尋非使用中信箱時請牢記的一些事項。
  
- 如果內容搜尋包含使用者信箱，該信箱再進行非使用中內容的搜尋會繼續搜尋不在作用中的信箱時變成非使用中之後重新執行搜尋。
    
- 在某些情況下，使用者可能會有作用中的信箱，而非使用中的信箱具有相同的 SMTP 地址。在此例中，只選取作為內容的搜尋位置的特定信箱拼寫須符合。換句話說，如果您將使用者的信箱新增到搜尋，您不能假設其作用中且非使用中的信箱拼寫須符合;要搜尋的明確新增到搜尋的信箱。
    
- 我們強烈建議您避免擁有作用中信箱和非使用中的信箱使用相同的 SMTP 地址。如果您需要重複使用的目前指派給非使用中信箱的 SMTP 位址，我們建議您復原非使用中的信箱或非使用中信箱的內容還原至作用中的信箱 （或 [作用中信箱的封存），然後刪除非使用中的信箱。
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>變更非使用中信箱的保留期間

進行不在作用中信箱之後，您可以變更保留或 Office 365 保留原則套用至非使用中信箱的工期。如需逐步程序，請參閱 ＜ [Change Office 365 中不在作用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。
  
## <a name="recover-an-inactive-mailbox"></a>復原非使用中的信箱

如果先前的員工會傳回您組織中，或將新的員工雇用採取 departed 員工的工作職責，您可以復原不在作用中信箱的內容。當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。它會復原之後，非使用中的信箱不存在。逐步程序及詳細資訊發生問題時復原不在作用中的信箱，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>還原至另一個信箱不在作用中信箱的內容

如果另一位員工採用在先前的員工、 工作職責或另一個人需要存取非使用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。當您還原非使用中信箱內容複製到另一個信箱。非使用中的信箱，則會保留與會維持不在作用中的信箱。非使用中信箱仍可搜尋使用 eDiscovery、 其內容可以還原至另一個信箱或復原或刪除日後。如需逐步程序，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>刪除非使用中的信箱

如果您不再需要保留非使用中信箱的內容，您可以永久刪除非使用中信箱移除保留或移除 Office 365 保留原則套用至非使用中的信箱。如果信箱已遭刪除超過 30 天，信箱加以標示為永久刪除之後移除保留與信箱會變成無法修復。如果在過去 30 天內刪除信箱，則您仍可以復原信箱之後移除保留或保留原則。逐步程序移除保留或要永久刪除非作用中信箱的 Office 365 保留原則，請參閱[刪除非作用中的信箱在 Office 365 中](delete-an-inactive-mailbox.md)。