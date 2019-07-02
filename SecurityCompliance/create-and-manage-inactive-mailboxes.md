---
title: 在 Office 365 中建立和管理非使用中的信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
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
description: 您可以在 Office 365 中建立非使用中的信箱, 方法是將保留或 Office 365 保留原則套用至信箱, 然後刪除對應的 Office 365 使用者帳戶。 非使用中信箱中的專案會保留在已套用至非使用中的保留或保留原則的持續時間。 若要永久刪除非使用中的信箱, 只需移除保留原則或保留原則。
ms.openlocfilehash: ca6fc5b579b6974ce89db14d318a6dc5a50f3f5c
ms.sourcegitcommit: eed9fb363c939168e4bc49698bb34038a54433db
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913074"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>在 Office 365 中建立和管理非使用中的信箱

Office 365 讓您可以保留已刪除信箱的內容。 這項功能稱為[非](inactive-mailboxes-in-office-365.md)使用中信箱。 非使用中的信箱可讓您在離開貴組織後, 保留先前員工的電子郵件。 在刪除對應的 Office 365 使用者帳戶之前, 當訴訟暫止或 Office 365 保留原則 (在 Office 365 或 Microsoft 365 的安全性和合規性中心建立) 中, 信箱便會變成非使用中狀態。 非使用中信箱的內容會保留在信箱停用之前的保留期間內。 這可讓系統管理員、合規性監察官和記錄管理員使用內容搜尋來搜尋並匯出非使用中信箱的內容。 非作用中的信箱無法接收電子郵件，也不會顯示於貴組織的共用通訊錄或其他清單中。
  
> [!NOTE]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 若要讓信箱成為非使用中信箱, 必須指派 Exchange Online Plan 2 授權, 讓訴訟暫止或 Office 365 保留原則可以套用至信箱, 然後再將其刪除。 Exchange Online Plan 2 授權是 Office 365 企業版 E3 和 E5 訂閱的一部分。 如果信箱已被指派 Exchange Online Plan 1 或 Exchange Online Kiosk 授權 (分別是 Office 365 E1 和 F1 訂閱的一部分), 您必須將其指派給個別的 Exchange Online 封存授權, 以便保留可以套用至信箱 before 它會被刪除。 如需詳細資訊, 請參閱[Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153)封存。
    
- 刪除對應的 Office 365 使用者帳戶之後, 就可以使用與已刪除的 Exchange Online 信箱相關聯的授權。 然後, 您可以[將這些授權指派給其他使用者](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。 
    
- 如果訴訟暫止或 Office 365 保留原則 (設定為保留或保留, 然後刪除內容) 未在刪除信箱之前套用至信箱, 則不會保留或探索信箱的內容。 不過, 刪除的信箱可在30天內復原, 但如果未復原, 則會在30天后永久刪除信箱及其內容。
    
- 如需訴訟暫止的詳細資訊, 請參閱[就地保留和訴訟資料暫](https://go.microsoft.com/fwlink/p/?LinkId=846124)留。 如需 Office 365 保留原則的詳細資訊, 請參閱[office 365 中的保留原則概述](retention-policies.md)。
  
## <a name="create-an-inactive-mailbox"></a>建立非使用中的信箱

使信箱成為非使用中的信箱包括兩個步驟: 1) 將信箱設為訴訟暫止, 或套用 Office 365 保留原則給 it, 2) 刪除信箱或對應的 Office 365 使用者帳戶。 信箱停用之後, 會保留其內容, 直到移除保留或保留原則為止。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>步驟 1: 將信箱設為訴訟暫止或套用 Office 365 保留原則

將信箱設為訴訟暫止或套用 Office 365 保留原則 (設定為保留或保留, 然後刪除內容) 時, 會保留信箱中的內容, 再將其刪除。 這兩種類型的保留會保留所有信箱內容, 包括已刪除的專案和已修改專案的原始版本。 刪除和修改的專案會保留在非使用中的信箱中指定的期間, 或在您移除已套用至非使用中信箱的保留原則之前, 永久刪除非使用中的信箱。
  
如果已在信箱上進行保留, 或 Office 365 保留原則已套用至信箱, 則您必須做的就是刪除步驟2中所述的對應 Office 365 使用者帳戶。
  
如需將信箱設為訴訟暫止或套用 Office 365 保留原則的逐步程式, 請參閱:
  
- [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Office 365 中的保留原則概述](retention-policies.md)
    
> [!NOTE]
> 針對訴訟保留和 Office 365 保留原則, 您可以建立無限期保留或以時間為基礎的保留原則。 在無限期保留中, 非使用中信箱的內容會永遠保留, 或直到移除保留或變更保留期間為止。 移除保留或保留原則之後 (假設信箱已刪除超過30天之前), 非使用中的信箱會標示為永久刪除, 且信箱的內容將不再保留或被探索。 在 [時間型保留] 或 [Office 365 保留原則] 中, 您可以指定保留的持續時間。 此持續時間視個別項目而定，會從接收或建立信箱項目的日期開始計算。 信箱專案的保留到期, 而且該專案移至或位於非使用中信箱的 [可復原的專案] 資料夾中時, 該專案會永久刪除 (清除) 從非使用中信箱的已刪除專案保留期間到期。 
  
### <a name="step-2-delete-the-mailbox"></a>步驟 2：刪除信箱

在信箱處於保留狀態或套用 Office 365 保留原則之後, 下一步是刪除信箱。 刪除信箱的最佳方法, 就是在 Microsoft 365 系統管理中心刪除對應的 Office 365 使用者帳戶。 如需刪除 Office 365 使用者帳戶的詳細資訊, 請參閱[刪除組織中的使用者](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)。
  
> [!NOTE]
> 您也可以在 Exchange Online PowerShell 中使用**移除信箱**Cmdlet 來刪除信箱。 如需詳細資訊, 請參閱[刪除或還原 Exchange Online 中的使用者信箱](https://go.microsoft.com/fwlink/?linkid=856287)。 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>查看非使用中信箱的清單

若要在您的組織中查看非使用中信箱的清單:
  
1. 移至[https://protection.office.com](https://protection.office.com) , 並使用 Office 365 組織中的系統管理員帳號憑證來登入。 
    
2. 按一下 [**資料** > 控管**保留**]。
    
3. 在 [**保留**] 頁面上****![, 按一下 [其他](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)導覽列省略號], 然後按一下 [非使用中**信箱**]。
    
    ![在 [保留] 頁面上, 按一下 [更多], 然後按一下 [非使用中的信箱] 以顯示非使用中信箱](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    [**非**使用中信箱] 頁面隨即顯示。 請注意, 會顯示您組織中的非使用中信箱總數。 
    
    ![顯示組織中所有非使用中信箱的清單](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
或者, 您可以在 Exchange Online PowerShell 中執行下列命令, 以顯示非使用中信箱的清單。

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

您可以按一下![[匯出搜尋結果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)圖示**匯出**], 以查看或下載包含組織中非使用中信箱之其他資訊的 CSV 檔案。 
  
您也可以執行下列命令, 將非使用中信箱和其他資訊的清單匯出至 CSV 檔案。 在此範例中, 會在目前目錄中建立 CSV 檔案。

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> 非使用中的信箱可能會有與使用中使用者信箱相同的 SMTP 位址。 在這種情況下, **DistinguishedName**或**ExchangeGuid**屬性的值可以用來唯一識別非使用中的信箱。 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜尋並匯出非使用中信箱的內容

您可以使用安全性 & 規範中心的內容搜尋工具, 來存取非使用中信箱的內容。 在搜尋非使用中的信箱時，您可以建立關鍵字搜尋查詢以搜尋特定項目，也可以傳回非使用中信箱的完整內容。 您可以預覽搜尋結果, 或將搜尋結果匯出至 Outlook 資料 (PST) 檔案或個別的電子郵件。 如需搜尋信箱及匯出搜尋結果的逐步程式, 請參閱下列主題:
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [匯出內容搜尋結果](export-search-results.md)
    
以下是搜尋非使用中信箱時, 需注意的事項。
  
- 如果內容搜尋包含使用者信箱, 且該信箱變為非使用中, 則當您重新執行搜尋之後, 內容搜尋會繼續搜尋非使用中的信箱。
    
- 在某些情況下, 使用者可能會有使用中的信箱, 以及具有相同 SMTP 位址的非使用中信箱。 在這種情況下, 只會搜尋您選取作為內容搜尋位置的特定信箱。 換句話說, 如果您將使用者的信箱新增至搜尋, 就無法假設會搜尋其作用中和非使用中的信箱;只會搜尋您明確新增至搜尋的信箱。
    
- 強烈建議您避免使用相同 SMTP 位址的主動信箱和非使用中信箱。 如果您需要重複使用目前指派給非使用中信箱的 SMTP 位址, 建議您復原非使用中的信箱, 或將非使用中信箱的內容還原至使用中信箱 (或封存使用中信箱), 然後刪除非使用中信箱。
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>變更非作用中信箱的保留持續時間

信箱成為非使用中信箱之後, 您可以變更保留期間或套用至非使用中信箱的 Office 365 保留原則。 如需逐步程式, 請參閱[在 Office 365 中變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。
  
## <a name="recover-an-inactive-mailbox"></a>復原非作用中的信箱

如果離職員工回到您的組織, 或雇用新的員工對已離開員工的工作責任採取行動, 您可以復原非使用中信箱的內容。 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 如需逐步程式及復原非使用中信箱時所發生的詳細資訊, 請參閱[在 Office 365 復原非使用中的信箱](recover-an-inactive-mailbox.md)。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>將非使用中信箱的內容還原至另一個信箱

如果另一位員工承擔離職員工的工作責任, 或其他人需要存取非使用中信箱的內容, 您可以將非使用中信箱的內容還原 (或合併) 到現有信箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 非使用中的信箱仍可使用 eDiscovery 來搜尋, 其內容可以還原至另一個信箱, 也可以在日後復原或刪除。 如需逐步程式, 請參閱[在 Office 365 中還原非使用中的信箱](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>刪除非作用中的信箱

如果您不再需要保留非使用中信箱的內容, 您可以移除保留或移除套用至非使用中信箱的 Office 365 保留原則, 永久刪除非使用中的信箱。 如果信箱已刪除超過30天, 則信箱將在您移除保留後標示為永久刪除, 且信箱將無法復原。 如果信箱已在過去30天內刪除, 您仍然可以在移除保留或保留原則後, 復原信箱。 如需移除保留或 Office 365 保留原則以永久刪除非使用中信箱的逐步程式, 請參閱[刪除 Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)。