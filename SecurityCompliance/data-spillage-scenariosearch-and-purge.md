---
title: 電子文件探索解決方案系列資料外洩案例-搜尋及清除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 Office 365 電子文件探索與搜尋工具來管理與貴組織中的資料外洩事件回應。
ms.openlocfilehash: 50078e3f22ede8a1af2a252a7a6f75710534c062
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000146"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>eDiscovery solution 解決方案系列： 資料外洩案例-搜尋及清除

 **什麼是資料外洩，以及您要為什麼應該注意？** 機密文件發行到未受信任的環境時的資料外洩。 偵測到的資料外洩事件時，務必快速評估的大小和位置的外洩，檢查使用者活動周圍，並再從系統永久清除 spilled 的資料。 
  
## <a name="data-spillage-scenario"></a>資料外洩案例

您是在 contoso 公司的潛在客戶資訊安全性長。 會通知您的資料外洩的情況下，其中員工不知情的情況下高度機密文件與多個人員共用透過電子郵件。 您想要快速評估者接收到這份文件內部和外部。 識別之後，您想要與其他現場檢閱，並再永久移除 Office 365 資料共用案例所發現的錯誤。 調查完成後，您想要與任何供日後參考永久移除和其他案例的詳細資料的辨識項產生報告。
  
### <a name="scope-of-this-article"></a>本文討論範圍

本文件提供如何永久移除訊息從 Office 365，以便它不是可存取或復原清單中的指示。 若要刪除的郵件，並使其可復原已刪除的項目保留期間到期之前，請參閱[搜尋並刪除 Office 365 組織中的電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>工作流程以管理資料外洩事件

以下是如何管理資料外洩事件：

![步驟 8 工作流程以管理資料外洩事件](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[（選用）步驟 1： 管理誰可以存取這種情況，並且設定合規性界限](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步驟 2： 建立 eDiscovery 案例](#step-2-create-an-ediscovery-case)<br/>
[步驟 3： 搜尋 spilled 資料](#step-3-search-for-the-spilled-data)<br/>
[步驟 4： 檢閱及驗證案例所發現的錯誤](#step-4-review-and-validate-case-findings)<br/>
[步驟 5： 使用郵件追蹤記錄檔以檢查如何溢出資料共用](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步驟 6： 準備信箱](#step-6-prepare-the-mailboxes)<br/>
[步驟 7： 永久刪除 spilled 的資料](#step-7-permanently-delete-the-spilled-data)<br/>
[步驟 8： 驗證、 提供證明刪除和稽核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>瞭解在您開始之前的事項

- 當信箱處於保留狀態時，直到保留期間到期或釋放保留已刪除的郵件會保留在 [可復原的項目] 資料夾。 [步驟 6](#step-6-prepare-the-mailboxes)說明如何從信箱移除保留。 移除保留之前，先檢查與您的記錄管理或法務部門。 您的組織可能會有一個原則來定義是否要保留的信箱上或資料外洩事件會優先採用。 
    
- 若要控制哪些使用者信箱資料外洩調查可以搜尋及管理誰可以存取這種情況，您可以設定合規性界限，並建立自訂角色群組，其在[步驟 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)中所述。 若要這麼做，您必須是 「 組織管理 」 角色群組的成員，或是獲指派 「 角色管理角色。 如果您或在組織中的系統管理員已設定合規性界限，您可以略過步驟 1。
    
- 若要建立案例，您必須是 eDiscovery 管理員角色群組的成員或是已指派案例管理角色自訂角色群組的成員。 如果您不是成員，要求將[您](assign-ediscovery-permissions.md)新增至 「 eDiscovery 管理員 」 角色群組的 Office 365 系統管理員。
    
- 若要刪除溢出至貴組織的資料，您需要在 Exchange Online PowerShell 中使用[Search-mailbox DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)命令。 此外，若要使用*DeleteContent*參數，您也必須是 Exchange Online 中已被指派信箱匯入匯出角色的角色群組的成員。 請參閱[管理角色群組](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)的 「 新增角色至角色群組 」 一節。
    
- 若要搜尋的 Office 365 稽核記錄 eDiscovery 活動在步驟 8 中，必須被開啟稽核為您的組織。 您可以搜尋過去 90 天內所執行的活動。 若要深入了解如何啟用及使用的稽核，請參閱[稽核資料外洩調查程序](#auditing-the-data-spillage-investigation-process)] 區段中的步驟 8。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>（選用）步驟 1： 管理誰可以存取這種情況，並且設定合規性界限

根據您組織的作法是，您需要控制可以存取用來調查資料外洩事件，並設定合規性界限的 eDiscovery 案例。 若要這麼做最簡單的方法是安全性 & 合規性中心中的現有角色群組成員身分加入現場，然後將角色群組新增為 eDiscovery 案例的成員。 如需內建的 eDiscovery 角色群組及如何將成員新增至 eDiscovery 案例的資訊，請參閱[指派 eDiscovery 權限](assign-ediscovery-permissions.md)。
  
您也可以建立新的角色群組，配合貴組織的需求。 例如，您可能想存取及共同作業的資料外洩的所有案例的組織中的資料外洩現場群組。 您可以建立的 「 資料外洩調查 」 角色群組、 指派適當的角色 （匯出、 RMS 解密、 檢閱、 預覽、 符合性搜尋和案例管理），將資料外洩現場新增至角色群組，然後再新增資料外洩 eDiscovery 案例的成員身分的角色群組。 如需如何執行這項操作的詳細指示，請參閱[設定 Office 365 中電子文件探索調查的合規性界限](set-up-compliance-boundaries.md)。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步驟 2： 建立 eDiscovery 案例

EDiscovery 案例提供有效的方法來管理您的資料外洩調查。 您可以將成員新增至您在步驟 1 建立的角色群組、 將該角色群組新增為新的 eDiscovery 案例，成員執行反覆執行搜尋來尋找 spilled 的資料、 共用、 追蹤的情況下，狀態報表匯出，然後參考回 c 的詳細資料如有需要 ase。 請考慮建立用於 [資料外洩事件的 eDiscovery 案例的命名慣例，並提供詳細資訊，讓您可以找出並參照在未來有必要，您可以在案例名稱和描述。
  
若要建立新的案例，您可以在安全性與合規性中心使用 eDiscovery。 請參閱 < <b0>eDiscovery 案例</b0>中的 「 建立新的案例 」。
  
## <a name="step-3-search-for-the-spilled-data"></a>步驟 3： 搜尋 spilled 資料

既然您已建立案例與受管理的存取，您可以使用這種情況來重複搜尋來尋找 spilled 的資料，並識別包含 spilled 的資料的信箱。 您會使用相同的搜尋查詢您用來找出電子郵件訊息] 來刪除這些相同的郵件，在[步驟 7](#step-7-permanently-delete-the-spilled-data)。
  
若要建立 eDiscovery 案例相關聯的內容搜尋，請參閱[eDiscovery 案例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的 「 建立和執行與案例相關聯的內容搜尋 」。
  
 **重要：** 您在搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。 例如，如果您搜尋包含社會安全號碼與您的文件使用 it 為搜尋關鍵字，您必須刪除之後，避免發生外洩的查詢。 請參閱 < 在步驟 8 中的 [<b0>刪除搜尋查詢</b0>。 
  
## <a name="step-4-review-and-validate-case-findings"></a>步驟 4： 檢閱及驗證案例所發現的錯誤

建立 「 內容搜尋之後，您需要檢閱及驗證搜尋結果，並確認，它們只能包含必須刪除電子郵件訊息。 在內容搜尋中，您可以預覽隨機取樣的 1000 封電子郵件，而無須匯出搜尋結果，以避免進一步的資料外洩。 您可以閱讀有關預覽限制在[內容搜尋的限制](limits-for-content-search.md)。
  
如果您有超過 1000 個信箱或 100 個以上的電子郵件訊息每個要檢閱的信箱，您可以分成多個搜尋中的首次搜尋，使用其他關鍵字或條件，例如日期範圍或寄件者/收件者和檢閱每個搜尋的結果個別。 請確定記下您刪除[步驟 7](#step-7-permanently-delete-the-spilled-data)中的郵件時所使用的所有搜尋查詢。

如果 custodian 或使用者指派 Office 36 E5 授權，您可以檢查一次使用 Office 365 進階電子文件探索的最多 10000 個搜尋結果。 如果有 10000 個以上的電子郵件，若要檢閱，您可以除以日期範圍的搜尋查詢和搜尋結果會依日期排序個別檢閱每個搜尋結果。 在進階電子文件，可以標記使用**標籤做為**功能預覽] 面板中的搜尋結果，並依您所標示的標籤篩選搜尋結果。 當您與次要的檢閱者共同作業時，這是很有幫助。 進階電子文件，例如光學字元辨識、 電子郵件執行緒，和預測撰寫程式碼中使用其他分析工具可以快速處理程序和檢閱千分位的郵件，並加上標籤的進一步檢閱。 請參閱 <<c0>快速設定 Office 365 進階電子文件探索。

當您找出電子郵件訊息包含溢出資料時，請檢查來決定是否它已外部共用郵件的收件者。 若要進一步的追蹤一則訊息，您可以收集寄件者資訊和日期範圍讓您可以在[步驟 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)中將會說明使用郵件追蹤記錄檔。

Afer 您驗證過的搜尋結果，您可能想要與他人共用您的發現次要檢閱。 您指派給此情況下步驟 1 中的人員可以檢閱 eDiscovery 和進階電子文件中的案例內容，並核准案例所發現的錯誤。 您也可以產生報表不含匯出實際內容。 您也可以使用這個相同的報告，以刪除，在[步驟 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)中所述的證明。
  
 **若要產生統計的報告：**
  
1. 移至 eDiscovery 案例中，在 [**搜尋**] 頁面上，按一下您想要產生報告的搜尋。 
    
2. 在彈出式頁面上，按一下 [**更多 > 匯出報告**。
 
      匯出報告頁面隨即顯示。

    ![選取搜尋]，然後按一下 [更多 > 彈出式頁面上的 [匯出] 報告](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 選取 [**所有項目，包括具有無法辨識的格式，已加密，或因為其他原因而未建立索引**，然後按一下 [**產生報表**。

4. 在 eDiscovery 案例中，按一下 [**匯出**至顯示匯出工作的清單。 您可能需要按一下 [更新清單，以顯示您剛剛建立的匯出工作的 [**重新整理**。

5. 按一下匯出工作，，然後按一下 [**下載**報告在彈出式頁面。
 
    ![在 [匯出] 頁面上，按一下 [匯出]，然後按一下 [「 下載報告 」](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

**匯出摘要**報告中包含結果與搜尋結果的大小找到的位置的數目。 您可以使用此比較之後刪除產生報告，並提供為刪除的證明。 **結果**報告中包含的搜尋結果中，包括主旨、 寄件者、 收件者，如果已讀取電子郵件、 日期和每個郵件的大小更詳細的摘要。 如果任何詳細資料此報告中包含實際 spilled 的資料，請務必調查完成後，永久刪除 Results.csv 檔案。

如需匯出報告的詳細資訊，請參閱[匯出內容搜尋報告](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步驟 5： 使用郵件追蹤記錄檔以檢查如何溢出資料共用

若要進一步調查如果共用溢出資料的電子郵件，您可以選擇性地查詢郵件追蹤記錄的寄件者資訊與您在步驟 4 中所收集的日期範圍資訊。 請注意，郵件追蹤的保留期間是 30 天的即時資料及 90 天的歷史資料。
  
您可以在安全性與合規性中心中使用郵件追蹤，或使用 Exchange Online PowerShell 中的相對應的 cmdlet。 請務必注意訊息追蹤並不提供完整的適當保證上所傳回的資料完整性。 如需使用郵件追蹤的詳細資訊，請參閱： 
  
- [安全性與合規性中心內的訊息追蹤](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [在安全性 & 合規性中心中新的郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>步驟 6： 準備信箱

檢閱並驗證搜尋結果包含必須刪除的郵件之後，您需要收集受影響的信箱，以使用步驟 7 中，當您執行**搜尋信箱 DeleteContent**命令的電子郵件地址的清單。 您可能要準備信箱，才能永久刪除電子郵件訊息，根據是否包含 spilled 的資料，或如果任何這些信箱上保留的信箱上啟用單一項目復原。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>取得與溢出資料的信箱地址的清單

有兩種方式來收集與溢出資料信箱的電子郵件地址清單。

**選項 1： 取得溢出資料的信箱地址的清單**

1. 開啟 eDiscovery 案例，請移至 [**搜尋**] 頁面上，選取適當的內容搜尋。 
    
2. 在彈出式頁面上，按一下 [**檢視結果**。
    
3. 在**個別的結果**] 下拉式清單中，按一下 [**搜尋統計資料**。
    
4. 在 [**類型**] 下拉式清單中，按一下**上方的位置**。
    
    ![取得包含在搜尋統計資料中的頂端位置] 頁面上的搜尋結果的信箱清單](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    包含搜尋結果的信箱清單隨即顯示。 也會顯示的每個信箱中符合搜尋查詢的項目數。
    
5. 複製資訊清單中並將它儲存到檔案或按一下 [**下載**下載至 CSV 檔案的資訊。 
    
**選項 2： 取得信箱位置，從 [匯出] 報告**

在[步驟 4](#step-4-review-and-validate-case-findings)中開啟您下載匯出摘要報告。 在報表中第一欄中，每個信箱的電子郵件地址會列在 [**位置**] 下。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>準備信箱，因此您可以刪除 spilled 的資料

如果已啟用單一項目復原，或信箱會處於暫止，永久刪除 （清除） 郵件仍會保留在 [可復原的項目] 資料夾。 因此您可以清除溢出資料之前，您需要檢查的現有的信箱組態和停用單一項目復原並移除任何保留或 Office 365 保留原則。 請記住，您可以準備一個信箱一次，然後在不同的信箱上執行相同的命令或建立 PowerShell 指令碼，以準備在同一時間的多個信箱。

- 請參閱 「 步驟 1： 收集信箱的相關資訊 」 中如需如何檢查是否啟用單一項目復原或如果信箱會處於暫止，或將它指派給指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)保留原則。 
    
- 請參閱 「 步驟 2： 準備信箱 」 中停用單一項目復原相關的指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)。 
    
- 請參閱 「 步驟 3： 從信箱移除所有保留 」 中[刪除項目在資料夾上的雲端式信箱的保留可復原項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)如需如何從信箱都移除保留或保留原則的指示。 

- 請參閱 「 步驟 4： 移除延遲保留狀態的信箱從 」 中移除暫留時信箱後移除任何類型的保留延遲保留的相關指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox)。
    
 **重要：** 移除保留或保留原則之前，先檢查與您的記錄管理或法務部門。 您的組織可能會有一個原則來定義是否要保留的信箱上或資料外洩事件會優先採用。 
  
請務必確認 spilled 的資料已永久刪除之後還原至先前設定的信箱。 請參閱[步驟 7](#step-7-permanently-delete-the-spilled-data)中的詳細資料。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步驟 7： 永久刪除 spilled 的資料

使用您收集並準備步驟 6 和已建立並精簡在步驟 3 以找出電子郵件訊息包含 spilled 的資料的搜尋查詢中的信箱位置，您現在可以永久刪除 spilled 的資料。 如先前所述，您必須獲指派 「 信箱匯入匯出角色在 Exchange Online 來刪除郵件使用下列程序。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554) (機器翻譯)。
    
2. 執行下列命令：
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. 重新執行前述命令包含 spilled 的資料，來取代 Identity 參數值; 每個信箱例如：

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
如先前所述，您也可以建立[powershell 指令碼](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)，並執行對信箱的清單，讓指令碼會刪除每個信箱中的 spilled 的資料。
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步驟 8： 驗證、 提供證明刪除和稽核

工作流程管理資料外洩事件的最後一個步驟是確認 spilled 的資料已永久移除信箱移至 [eDiscovery 案例，並重新執行相同的搜尋查詢，用來刪除該資料，確認沒有結果 ar傳回的 e。 確認 spilled 的資料已永久移除之後，您可以匯出報告，並將它 （以及在原始報告） 包含做為刪除的證明。 然後您就可以[關閉這種情況](ediscovery-cases.md#optional-step-9-close-a-case)，可讓您如果在未來參照至它重新開啟。 此外，您也可以還原信箱其先前的狀態，刪除用來尋找 spilled 的資料，並搜尋稽核記錄的工作會管理資料外洩事件時執行搜尋查詢。 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>還原成原來的狀態的信箱

如果您變更任何信箱中的組態步驟 6，以準備之前 spilled 的資料已刪除的信箱，必須將它們還原成原來的狀態。 請參閱 「 步驟 6： 將回復到之前的狀態的信箱 」 中[刪除項目在資料夾上的雲端式信箱的保留可復原項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)。
  
### <a name="deleting-the-search-query"></a>刪除搜尋查詢

如果您建立及使用步驟 3 中的搜尋查詢中的關鍵字包含部分或所有實際 spilled 資料，您應該刪除搜尋查詢，以避免進一步的資料外洩。
  
1. 在安全性與合規性中心]，開啟 eDiscovery 案例、 移至 [**搜尋**] 頁面上，並選取適當的內容搜尋。
    
2. 在彈出式頁面上，按一下 [**刪除**]。

    ![選取搜尋]，然後按一下 [延伸] 頁面上的 [刪除](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>稽核資料外洩調查程序

您可以搜尋 eDiscovery 活動期間調查已執行的 Office 365 稽核記錄檔。 您也可以搜尋稽核記錄檔若要傳回在您執行**搜尋信箱 DeleteContent**命令，以刪除 spilled 的資料時所建立的稽核記錄。 如需詳細資訊，請參閱：

- [搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)

- [在稽核記錄中搜尋電子文件探索活動](search-for-ediscovery-activities-in-the-audit-log.md)

- 請參閱 「 稽核活動-Exchange 系統管理員稽核記錄 」 一節中[搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md#audited-activities)如何與執行指令程式在 Exchange Online 的稽核記錄搜尋的相關指引。
  

