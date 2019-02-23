---
title: eDiscovery 解決方案數列的資料 spillage 案例-搜尋和清除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 Office 365 eDiscovery 及搜尋工具來管理，並在組織中建立資料 spillage 事件回應。
ms.openlocfilehash: 0da49dfbe8104d89a1abf4a14adce51ec0ef25f1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219423"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>eDiscovery 解決方案系列： 資料 spillage 案例-搜尋和清除

 **資料 spillage 及不可您不知吗？** 機密文件發行至不受信任的環境時資料 spillage。當偵測到資料 spillage 事件時，務必快速評估的大小及位置的 spillage、 檢查周圍、 使用者活動及則從系統永久清除 spilled 的資料。 
  
## <a name="data-spillage-scenario"></a>資料 spillage 案例

您是在 contoso 公司負責人資訊安全主管。您要得知其中員工不知情的情況下高度機密文件與多人共用透過電子郵件資料 spillage 情況。您想要快速評估者接收到此文件內部及外部。之後，您想與其他現場，檢閱，然後從 Office 365 永久移除資料共用案例研究結果。將正在調查完成後，您想要與任何供未來參照永久移除與其他案例的詳細資料證據產生報告。
  
### <a name="scope-of-this-article"></a>本文的範圍

本文件提供如何將永久移除郵件來自 Office 365，讓它不是可存取或可復原清單中的指示。若要刪除一則訊息並使其可復原已刪除的項目保留期間到期之前，請參閱[Search for 和 Office 365 組織中的刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>工作流程以管理資料 spillage 事件

以下是如何管理資料 spillage 事件：

![管理資料 spillage 事件的步驟 8 工作流程](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[（選用）步驟 1： 管理人員可以存取案例和設定規範界限](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步驟 2： 建立 eDiscovery 案例](#step-2-create-an-ediscovery-case)<br/>
[步驟 3： 搜尋 spilled 資料](#step-3-search-for-the-spilled-data)<br/>
[步驟 4： 檢閱並驗證案例研究結果](#step-4-review-and-validate-case-findings)<br/>
[步驟 5： 使用郵件追蹤記錄檔以檢查如何溢出資料的形式共用](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步驟 6： 準備信箱](#step-6-prepare-the-mailboxes)<br/>
[步驟 7： 永久刪除 spilled 的資料](#step-7-permanently-delete-the-spilled-data)<br/>
[步驟 8： 驗證、 提供證明刪除，及稽核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>須知事項開始之前

- 當信箱處於 [保留時] 直到保留期間到期或保留已刪除的郵件會維持可復原的項目] 資料夾中。[步驟 6](#step-6-prepare-the-mailboxes)說明如何從信箱移除保留。記錄管理或法務部門檢查之前先移除保留。您的組織可能已定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。 
    
- 若要控制哪些使用者信箱資料 spillage 調查可以搜尋並管理人員可以存取案例，您可以設定規範界限及建立自訂角色群組，在[步驟 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)中所述。為達成此目的，您必須是 「 組織管理角色群組的成員或角色的管理角色指派。如果您或在組織中的系統管理員已經有設定規範界限，您可以略過步驟 1。
    
- 若要建立案例，您必須是 「 eDiscovery 管理員角色群組的成員或是已指派的案例管理角色自訂角色群組的成員。如果您不是成員，要求 Office 365 管理員[將您新增至 eDiscovery 管理員角色群組](assign-ediscovery-permissions.md)。
    
- 若要刪除溢出至您的組織的資料，您需要在 Exchange Online PowerShell 中使用[Search-mailbox DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)命令。此外，若要使用*DeleteContent*參數，您也必須是 Exchange Online 中有指派的信箱匯入 / 匯出 」 角色的角色群組的成員。請參閱[管理角色群組](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)的 「 將角色新增至角色群組 」 一節。
    
- 若要在步驟 8 中搜尋 Office 365 稽核記錄檔 eDiscovery 活動，稽核必須開啟您的組織。您可搜尋過去 90 天內所執行的活動。若要深入了解如何啟用及使用稽核，請參閱[稽核資料 spillage 調查程序](#auditing-the-data-spillage-investigation-process)] 區段中的步驟 8。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>（選用）步驟 1： 管理人員可以存取案例和設定規範界限

隨您組織的作法是，您必須控制可存取用來建立資料 spillage 事件的調查並設定規範界限 eDiscovery 案例的人員。執行這項作業的最簡單方式是 Office 365 安全性 & 規範中心中的現有角色群組成員身分加入現場並再新增 eDiscovery 案例的成員身分的角色群組。內建的 eDiscovery 角色群組以及如何將成員新增至 eDiscovery 案例的相關資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
  
您也可以建立新的角色群組的對齊您組織的需求。例如，您可能會想存取及進行共同作業的所有資料 spillage 案例組織中的資料 spillage 現場群組。您可以這麼做建立"資料 Spillage 調查 」 角色群組、 指派適當的角色 （匯出、 RMS 解密、 檢閱、 Preview、 規範搜尋及案例管理）、 資料 spillage 現場新增至角色群組，然後將資料 spillage eDiscovery 案例的成員身分的角色群組。請參閱[Set up Office 365 中的 eDiscovery 調查的規範界限](set-up-compliance-boundaries.md)如何執行這項作業的詳細指示。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步驟 2： 建立 eDiscovery 案例

EDiscovery 案例提供有效的方法來管理您的資料 spillage 調查。您可以將成員新增至您在步驟 1 中建立的角色群組、 角色群組新增新的 eDiscovery 案例的成員身分執行反覆執行搜尋以尋找 spilled 的資料、 將共用、 追蹤的情況下，狀態報表匯出以及然後參照回 c 的詳細資訊如果需要，ase。請考慮建立用於資料 spillage 事件、 eDiscovery 案例的命名慣例及提供方式，儘可能案例名稱與描述，讓您可以找出並參照未來如有必要的資訊。
  
若要建立新的案例，您可以使用 eDiscovery 安全性&amp;規範中心。請參閱[Office 365 安全性 & 規範中心中的 eDiscovery 案例](ediscovery-cases.md#step-2-create-a-new-case)中的 「 建立新的案例 」。
  
## <a name="step-3-search-for-the-spilled-data"></a>步驟 3： 搜尋 spilled 資料

既然您已經建立案例和受管理的存取，您可以使用反覆搜尋來尋找 spilled 的資料並找出包含 spilled 的資料之信箱的大小寫。您將會使用您用來找出要刪除那些相同的郵件在[步驟 7](#step-7-permanently-delete-the-spilled-data)中的電子郵件訊息的同一個搜尋查詢。
  
若要建立內容的搜尋相關聯的 eDiscovery 案例，請參閱[Office 365 安全性 & 規範中心中的 eDiscovery 案例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的 「 建立和執行與案例相關聯之內容的搜尋 」。
  
 **重要：** 搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。例如，如果搜尋文件包含社會安全號碼與您使用 it 如搜尋關鍵字，您必須刪除事後以避免進一步 spillage 查詢。請參閱在步驟 8 中的 [[刪除的搜尋查詢](#deleting-the-search-query)。 
  
## <a name="step-4-review-and-validate-case-findings"></a>步驟 4： 檢閱並驗證案例研究結果

建立內容的搜尋之後，您需要檢閱並驗證搜尋結果並確認其包含只的必須刪除電子郵件。在內容搜尋，您可預覽 1000 封電子郵件隨機取樣不含匯出搜尋結果，以避免進一步資料 spillage。您可以閱讀更多關於在預覽限制[Limits for Office 365 安全性內容搜尋&amp;規範中心](limits-for-content-search.md)。
  
如果您有超過 1000 個信箱或超過 100 封電子郵件訊息每個可供檢閱的信箱，您可以使用其他關鍵字或日期範圍或寄件者/收件者的條件將首次搜尋分割成多個搜尋並檢閱每個搜尋結果個別。請務必注意下時刪除訊息在[步驟 7](#step-7-permanently-delete-the-spilled-data)中的所使用的所有搜尋查詢。

如果 okay 或使用者指派 Office 36 E5 授權，您可以檢查一次使用 Office 365 進階 eDiscovery 的最多 10000 個搜尋結果。檢閱 10000 個以上的電子郵件訊息時，您可以除以日期範圍的搜尋查詢和搜尋結果會依日期排序個別檢閱每個搜尋結果。進階 ediscovery 可以標記 [預覽] 面板中使用**標籤設為**功能的搜尋結果，而您所標示的標籤來篩選搜尋結果。當您與次要檢閱者共同作業將很有用。進階 eDiscovery，例如光學字元辨識、 電子郵件超執行緒，以及預測撰寫程式碼中使用其他分析工具您可以快速處理及檢閱數千個郵件並加以標記供進一步檢閱。請參閱[Office 365 進階 ediscovery 快速設定](quick-setup-for-advanced-ediscovery.md)。

當您尋找電子郵件訊息內含溢出資料時，請檢查要判斷是否它的形式共用外部之郵件的收件者。若要進一步追蹤訊息，您可以收集寄件者資訊和日期範圍讓您可以在[步驟 5 中](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)有相關描述使用郵件追蹤記錄檔。

確認搜尋結果的 Afer，可能會想要次要檢閱與其他人共用您發現項目。您指派給在步驟 1 中的大小寫的人員可以檢閱 eDiscovery 及進階的 eDiscovery 案件內容及核准案例研究結果。您也可以產生報表不含匯出實際內容。您也可以使用這個相同的報告為刪除，在[步驟 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)中所述的概念。
  
 **若要產生統計的報告：**
  
1. 移至 eDiscovery 案例中，在 [**搜尋**] 頁面上，按一下 [搜尋想要產生的報告。 
    
2. 按一下 [彈出式] 索引標籤的 [**更多 > 匯出報告**]。
 
      會顯示 [匯出報告] 頁面。

    ![選取搜尋]，然後按一下 [更多 > 彈出式] 頁面上的匯出報告](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 選取**所有項目，包括類有無法辨認的格式來加密或未編製索引的其他原因**，然後按一下 [**產生報表**。

4. 在 eDiscovery 案例中，按一下 [要顯示的匯出工作清單的 [**匯出**]。您必須按一下 [更新以顯示您剛才建立的匯出工作清單的 [**重新整理**。

5. 按一下匯出工作，並再按一下 [**下載**報告彈出式] 頁面上。
 
    ![在 [匯出] 頁面上按一下匯出] 和 ["下載報告"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

**匯出的摘要**報告包含位置找到結果與大小的搜尋結果數目。您可以使用這比較刪除之後所產生的報表，並提供以證明刪除。**結果**報告包含更詳細的摘要的搜尋結果，包括主旨、 寄件者、 收件者，如果已讀取的電子郵件、 日期和每個郵件的大小。如果這份報告的詳細資料的任何包含該實際 spilled 的資料，請務必將正在調查完成時永久刪除 Results.csv 檔案。

如需匯出報告的詳細資訊，請參閱[匯出內容搜尋報告](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步驟 5： 使用郵件追蹤記錄檔以檢查如何溢出資料的形式共用

如果溢出資料的電子郵件的形式共用的進一步調查，您可以選擇性地查詢郵件追蹤記錄檔的寄件者資訊與您在步驟 4 中所收集的日期範圍資訊。請注意目的保留期間的郵件追蹤 30 天的即時資料及 90 天的歷程資料。
  
您可以使用安全性 & 規範中心中的郵件追蹤或使用對應 cmdlet 在 Exchange Online PowerShell。請務必注意郵件追蹤並不提供完整保證在傳回的資料完整性。如需使用郵件追蹤的詳細資訊，請參閱： 
  
- [郵件追蹤的 Office 365 安全性&amp;規範中心](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [新的 Message Trace in Office 365 安全性&amp;規範中心](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>步驟 6： 準備信箱

檢閱並驗證的搜尋結果包含必須要刪除的郵件之後，您需要收集受影響信箱時您執行**搜尋信箱 DeleteContent**命令在步驟 7 中使用的電子郵件地址清單。您也可以準備才能永久刪除電子郵件訊息根據是否包含 spilled 的資料或任何這些信箱位於音樂信箱上啟用單一項目復原的信箱。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>要取得的信箱溢出資料的地址清單

有兩種方式來收集溢出資料的信箱的電子郵件地址清單。

**做法 1： 取得信箱溢出資料的地址清單**

1. 開啟 eDiscovery 案例、 移至 [**搜尋**] 頁面並選取適當的內容搜尋。 
    
2. 在 [彈出式] 頁面上按一下 [**檢視結果**。
    
3. 在**個別的結果**] 下拉式清單中，按一下 [**搜尋統計資料**。
    
4. 在 [**類型**] 下拉式清單中，按一下 [**上方的位置**。
    
    ![取得包含在搜尋統計資料上方的位置] 頁面上的搜尋結果的信箱的清單](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    會顯示包含搜尋結果的信箱的清單。也會顯示每個信箱中比對搜尋查詢的項目數。
    
5. 複製清單中的資訊並將它儲存到檔案或按一下 [**下載**下載至 CSV 檔案的資訊。 
    
**選項 2： 取得信箱位置從匯出報告**

在 [[步驟 4](#step-4-review-and-validate-case-findings)中開啟您下載匯出摘要報告。在報表中第一欄中，每個信箱的電子郵件地址會列於 [**位置**] 下。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>準備讓您可以刪除 spilled 的資料的信箱

如果已啟用單一項目復原或信箱處於保留狀態，永久刪除 （清除） 的訊息將會保留在可復原的項目] 資料夾中。如此可清除溢出資料之前，需要檢查現有的信箱設定和停用單一項目復原，並且移除任何保留或 Office 365 保留原則。請記住您可以準備一次一個信箱，然後在不同的信箱上執行相同的命令或建立 PowerShell 指令碼以準備在同一時間的多個信箱。

- 請參閱 「 步驟 1： 收集信箱的相關資訊 」 中如需如何檢查是否啟用單一項目復原或如果信箱處於保留或指派給的指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)保留原則。 
    
- 請參閱 「 步驟 2： 準備信箱"中如需停用單一項目復原指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)。 
    
- 請參閱 「 步驟 3： 從信箱移除所有保留"中如需如何從信箱都移除保留或保留原則的指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)。 

- 請參閱 「 步驟 4： 延遲保留從信箱移除 」 中移除後移除任何類型的保留信箱處於延遲保留的相關指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox)。
    
 **重要：** 記錄管理或法務部門檢查之前先移除保留或保留原則。您的組織可能會有定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。 
  
請務必確認已永久刪除 spilled 的資料之後還原至先前的設定的信箱。請參閱在[步驟 7](#step-7-permanently-delete-the-spilled-data)中的詳細資料。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步驟 7： 永久刪除 spilled 的資料

收集並準備步驟 6 和建立及精簡尋找包含 spilled 的資料的電子郵件訊息的步驟 3 中的搜尋查詢中的信箱位置，您可以使用現在永久刪除 spilled 的資料。如先前所述，您必須獲指派信箱匯入 / 匯出角色在 Exchange Online 從中刪除郵件使用下列程序。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554) (機器翻譯)。
    
2. 執行下列命令：
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. 重新執行上述命令包含 spilled 的資料、 所取代的 Identity 參數值 ； 每個信箱例如：

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
先前所述，您也可以建立[powershell 指令碼](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)並執行對信箱的清單，讓指令碼會刪除每個信箱中的 spilled 的資料。
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步驟 8： 驗證、 提供證明刪除，及稽核

管理資料 spillage 事件的工作流程的最後一個步驟是驗證 spilled 的資料已永久移除從信箱移至 eDiscovery 案例並重新執行相同的搜尋查詢用來不刪除任何結果 ar，確認該資料傳回 e。您確認已永久移除 spilled 的資料之後，您可以將報表匯出並包括其 （搭配原始的報表） 以證明刪除。然後您可以[關閉案例](ediscovery-cases.md#optional-step-9-close-a-case)，可讓您如果未來參照它重新開啟。此外，您也可以還原信箱以其先前的狀態，刪除用來尋找 spilled 的資料，並搜尋稽核記錄的工作會管理資料 spillage 事件時執行搜尋查詢。 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>回復至其先前狀態的信箱

如果您變更任何信箱中的設定步驟 6，以準備信箱已刪除的 spilled 的資料之前，您必須將它們還原先前的狀態。請參閱 「 步驟 6： 還原成先前狀態的信箱 」 中[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)。
  
### <a name="deleting-the-search-query"></a>刪除搜尋查詢

如果您建立及使用步驟 3 中的搜尋查詢中的關鍵字包含部分或所有實際 spilled 資料，您應該刪除搜尋查詢以避免進一步資料 spillage。
  
1. 在安全性 & 規範中心開啟 eDiscovery 案例、 移至 [**搜尋**] 頁面上，並選取適當的內容搜尋。
    
2. 在 [彈出式] 頁面上按一下 [**刪除**]。

    ![選取搜尋] 和 [彈出式] 頁面上 [刪除](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>稽核資料 spillage 調查程序

您可以搜尋期間將正在調查所執行的 eDiscovery 活動的 Office 365 稽核記錄。您也可以搜尋稽核記錄，以傳回在您執行**搜尋信箱 DeleteContent**命令刪除 spilled 的資料時所建立的稽核記錄。如需詳細資訊，請參閱：

- [在 Office 365 安全與規範中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)

- [搜尋 Office 365 稽核記錄中的 eDiscovery 活動](search-for-ediscovery-activities-in-the-audit-log.md)

- 請參閱"稽核活動-Exchange 管理員稽核記錄 」 一節中的[搜尋稽核登入 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)如需如何執行 Exchange Online 中的 cmdlet 與相關的稽核記錄搜尋的指引。
  

