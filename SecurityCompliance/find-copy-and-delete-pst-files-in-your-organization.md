---
title: 使用 PST 收集工具來尋找、 複製及刪除您的組織中的 PST 檔案
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: 使用 Microsoft PST 收集工具來搜尋組織的網路，以取得散佈整個組織的 PST 檔案的詳細目錄。 尋找 PST 檔案之後，您可以使用 PST 收集工具來複製它們在一個中央位置，以便您可以匯入到 Office 365。
ms.openlocfilehash: 87e13ec8a4c58f848ac2ff7a430a7532942ece74
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255337"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>使用 PST 收集工具來尋找、 複製及刪除您的組織中的 PST 檔案

> [!IMPORTANT]
> 本文所述的 PST 收集工具不支援任何 Microsoft 標準支援程式或服務。 以提供工具，不做任何種類。 Microsoft 進一步不作任何默示的擔保，包括，但不限於任何默示擔保售或適合特定用途。 與您保持承擔使用或效能工具和文件的風險。 事件無法在 Microsoft、 其作者或任何其他參與建立、 實際執行環境或傳遞的工具對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的工具或文件。

您可以使用 Microsoft PST 收集工具來搜尋您的組織網路的 PST 檔案。 此工具可協助您取得散佈整個組織的 PST 檔案的詳細目錄。 尋找 PST 檔案之後，您可以使用 PST 收集工具來複製它們在一個中央位置。 在單一位置有 Pst 然後可讓您匯入至 Exchange Online 信箱 （或單一 Exchange Online 信箱），其中您可以再套用豐富的 Office 365 中的符合性功能。 這包括將 Pst 匯入至使用者的封存信箱，搜尋在您使用匯入 eDiscovery 搜尋工具，使用 eDiscovery 保留郵件的 PST 檔案中的特定郵件的保留和 Office 365 保留原則，以及管理生命週期使用通訊這些訊息的循環記錄管理功能在 Exchange Online。 您確信您收集到的 PST 檔案都已成功匯入到 Office 365 之後，您可以使用此工具從其原始位置加以刪除，在您網路上。 
  
您可以使用 PST 收集工具進行的另一件事是防止使用者建立新的 PST 檔案或變更您尋找您的網路的現有 PST 檔案。 這些 「 區塊 」 功能可讓您尋找、 收集和已知的一組 PST 檔案匯入 Office 365 和防止未來激增貴組織中的 PST 檔案。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST 收集工具的運作方式

以下是使用 PST 收集工具來尋找、 控制、 收集和刪除您的組織中的 PST 檔案的程序的簡要概觀。
  
![PST 收集工具程序的概觀](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[步驟 1： 找出您的網路上的 PST 檔案](#step-1-find-pst-files-on-your-network)**-當您執行工具以找出 PST 檔案時，您指定的位置，例如包含用戶端和伺服器電腦的 Active Directory 物件的組織單位。 您也可以搜尋特定電腦或網路檔案共用。 當您執行工具時，在目標電腦上安裝 「 輕量級 」 的集合代理程式。 此代理程式搜尋 PST 檔案的目標電腦，並再將資訊傳送回 PST 收集工具會在找到任何 PST 檔案的相關。 此工具會建立包含在指定的位置中找到的 PST 檔案的相關資訊的記錄檔。 當您在稍後步驟中執行工具時，會使用這些檔案。 
    
2. **[（選用） 步驟 2： 控制 PST 檔案的存取](#optional-step-2-control-access-to-pst-files)**-工具使用防止使用者建立或變更的 PST 檔案的設定來建立群組原則物件 (GPO)。 這個 GPO 會套用至您的網域中每一個使用者。 此選用的步驟可協助您 「 鎖定 「 找不到在步驟 1 中，以便您可以收集、 匯入，並予以刪除，而不需要建立新的 PST 檔案的 PST 檔案或變更現有 PST 檔案。 
    
3. **[步驟 3： 將 PST 檔案複製到集合的位置](#step-3-copy-the-pst-files-to-a-collection-location)**-這可讓您收集在一個位置的 PST 檔案，以便您可以匯入至 Exchange Online 信箱在步驟 4 中使用 Office 365 匯入服務。 當您執行此工具中的 「 收集 」 模式時，每個集合代理程式會複製入集合位置安裝代理程式的目標電腦的 PST 檔案。 
    
4. **[步驟 4: PST 檔案匯入 Office 365](#step-4-import-the-pst-files-to-office-365)** -您已複製的 PST 檔案至一個位置之後，就可以匯入到 Exchange Online 信箱。 
    
5. **[步驟 5： 刪除您的網路找到的 PST 檔案](#step-5-delete-the-pst-files-found-on-your-network)**-之後 PST 檔案變成您找到並收集都已匯入至 Office 365 中的 Exchange Online 信箱，您可以使用 PST 收集工具從原始位置刪除 PST 檔案其中它們步驟 1 中找到。 

## <a name="before-you-begin"></a>開始之前

- 請遵循下列步驟下載到本機電腦的 PST 收集工具。 
    
    1. [下載 PST 收集工具](https://aka.ms/pstcollectiontool)。
    
    2. 在快顯視窗中，按一下 [**儲存** \> PSTCollectionTool.zip 檔案儲存至資料夾，在本機電腦上的 [**另存為**。 
    
    3. 解壓縮到資料夾 PSTCollectionTool.zip 檔案在本機電腦;預設資料夾名稱是 PSTCollectionTool。
    
- 若要執行 PST 收集工具 （尋找、 封鎖、 複製、 或刪除） 的任何模式中，您必須是 Active Directory 網域中 Domain Administrators 群組的成員。 

## <a name="step-1-find-pst-files-on-your-network"></a>步驟 1： 找出您的網路上的 PST 檔案

第一步是執行 PST 收集工具來尋找組織中的 PST 檔案。 您可以使用此工具來搜尋下列類型的位置。 
  
- 在內部部署 Active Directory 網域中的組織單位 (Ou)。 此工具會搜尋所包含的所有機器所指定 OU 中。 
    
- 用戶端和伺服器電腦。 此工具會搜尋指定的機器。 
    
- 網路檔案共用。 此工具會搜尋指定的網路檔案共用。 
    
請參閱 < 的描述<b0></b0>用於每個位置類型語法的範例如下列程序中的資料表中的參數。 
  
> [!IMPORTANT]
> 您必須執行尋找模式的 PST 收集工具才能執行其他動作，例如封鎖、 收集，或刪除 PST 檔案。 
  
1. 在本機電腦上開啟命令提示字元 （以系統管理員身分執行）。
    
2. 移至 PSTCollectionTool 資料夾 （或您解壓縮 PSTCollectionTool.zip 檔案的資料夾）。
    
3. 變更至 DataCollectorMaster 目錄。
    
4. 執行下列命令，以尋找 PST 檔案中指定的位置。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    下表說明參數和其所需的值，當您執行 DataCollectorMaster.exe 命令來尋找 PST 檔案。 
    
    |參數 * * *|****描述****|範例 * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋資料的類型。 目前，您可以使用 PST 收集工具來搜尋的 PST 檔案。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定將會執行此工具的作業類型。 使用值`Find`來尋找 PST 檔案中指定的位置。 請注意此工具可以尋找及取得 Outlook 和 PST 檔案中連線至 Outlook 設定檔的已開啟的 PST 檔案的相關資訊。  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |會指定 PST 收集工作的名稱。 當您執行 PST 收集工具來封鎖、 收集和刪除，當您執行工具以找出 PST 檔案時所找到的 PST 檔案時，您會使用這個相同的工作名稱。 工作名稱也會加入至記錄檔、 設定檔名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | 會指定要搜尋的 PST 檔案的一或多個位置。 如果您指定多個位置，請使用分號 （;）若要分隔個別的位置。 請務必個別的值，此參數與雙引號括住 ("")。  <br/><br/>   以下是必要的 identity 值格式類型的您可以搜尋的位置。  <br/><br/>        **Ou**來識別 Ou; 使用辨別名稱 (DN)例如：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]您不能指定內建的電腦容器的 > (例如，CN = 電腦，DC = contoso，DC = com") 因為它不是組織單位。<br/> <br/> **機器**-DN 或完整的網域名稱 (FQDN) 來識別您的網路; 上的用戶端和伺服器機器例如：  <br/>  DN:`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  Or  <br/>  FQDN:`"FILESERVER01.contoso.com"` <br/><br/>  **網路檔案共用**用 UNC 名稱來識別網路檔案共用;例如，`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |指定記錄檔會複製到的資料夾。 如果資料夾不存在，則會加以建立當您執行此工具。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |指定.xml 組態檔會複製到的資料夾。 此檔案包含執行工具時找到每個 PST 檔案的相關資訊。 若要複製的 PST 檔案所找到的步驟 3 中執行工具時，將會使用此檔案。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |此選用參數會指定在尋找作業期間略過的位置。 您可以排除特定的 Ou，機器，以及網路檔案共用。 例如，您無法排除機器，例如設定為 SQL server （或其他類型的應用程式伺服器） 的電腦、 使用者沒有存取權。 如果您指定要排除的多個位置，請使用分號 （;）若要分隔個別的位置。 請務必個別的值，此參數與雙引號括住 ("")。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |此選用參數可讓您在現有 PST 收集工作的尋找模式中執行此工具。 當您使用`ForceRestart`切換，請從先前的尋找作業的結果工作將會被捨棄，而此工具會重新掃描的指定的位置，建立新的記錄檔和設定檔。  <br/> | `-ForceRestart` <br/> |
   
    以下是針對各個參數使用實際值的 DataCollectorMaster.exe 命令的語法範例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    您執行命令之後，詳細的狀態郵件會顯示 [顯示在指定的位置尋找 PST 檔案的進度。 在一段時間之後, 的最終狀態郵件會顯示 PST 檔案中所找到的總數、 是否已完成之工作，以及若發生任何錯誤。 相同的狀態郵件會複製到.log 檔案。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>在尋找模式中執行 DataCollectorMaster.exe 的結果

成功執行 PST 收集工具尋找模式之後，建立並儲存在所指定的資料夾中的下列檔案`LogLocation`和`ConfigurationLocation`參數。 
  
- **\<工作名稱\>_尋找_\<DateTimeStamp\>.log** -記錄檔會包含已顯示狀態訊息。 在所指定的資料夾中建立此檔案`LogLocation`參數。 
    
- **\<工作名稱\>_尋找_\<DateTimeStamp\>.csv** -CSV 檔案包含找不到每個 PST 檔案的資料列。 每個 PST 的資訊包含 PST 檔案已找到，PST 檔案的完整檔案路徑位置]、 [擁有者的 PST 檔案和大小 （kb) 的 PST 檔案的電腦。 在所指定的資料夾中建立此檔案`LogLocation`參數。 
    
    > [!TIP]
    > 使用 Excel 中的 [自動加總] 工具，來計算所有 CSV 檔案中列出的 PST 檔案的總大小 （以 kb 為單位）。 然後您可以使用轉換 [小算盤] 若要轉換的總大小 (mb) 或 (gb)。 
  
- **\<工作名稱\>_尋找_\<DateTimeStamp\>.xml** -XML 檔案包含的資訊如下參數的值，當您執行工具，以尋找模式時使用。 此檔案也包含找不到每個 PST 檔案的相關資訊。 當您重新執行 [相同的工具工作區塊，以收集，或找不到的刪除 PST 檔案執行，會使用此檔案中的資料。 在所指定的資料夾中建立此檔案`ConfigurationLocation`參數。 
    
    > [!IMPORTANT]
    > 不要重新命名、 變更或移動此檔案。 當您重新執行工具在區塊、 複製、 或刪除模式相同的工作會使用 PST 收集工具。 

## <a name="optional-step-2-control-access-to-pst-files"></a>（選用）步驟 2： 控制 PST 檔案的存取權

此選用的步驟屬性可讓您 「 鎖定 「 找不到在步驟 1 中，讓您可以收集與已知的一組 PST 檔案匯入 Office 365 的 PST 檔案。 當您執行 PST 收集工具的 [封鎖模式時，會發生下列情形： 
  
- 此工具會建立群組原則物件 (GPO) 名為*PST 流量控制項*。 這個 GPO 連結至您的網域，並套用至組織中所有已驗證的使用者。 
    
- PST 流量控制項 GPO 貴組織中的機器上建立的登錄設定。 根據您使用的參數，您可以建立登錄設定防止使用者建立新的 PST 檔案及登錄設定防止使用者變更現有 PST 檔案。
    
> [!NOTE]
> 為您的組織太中斷控制存取 PST 檔案時，您可以考慮跳過此步驟，以及執行步驟 3 將 PST 檔案複製到一個集中的位置。 然後您可以重複步驟 1 相同的工作 (使用`ForceRestart`參數) 來尋找其他之後您將 Pst 檔案複製到集合的位置所建立的 Pst 檔案。 如果找不到新的 PST 檔案，您可以將其複製到集合的位置。 當您使用`ForceRestart`參數，當您重新執行工具以尋找模式，工作先前的尋找作業的結果將會被捨棄，此工具會重新掃描的指定的位置。 

若要封鎖 PST 檔案的存取權：

1. 在本機電腦上開啟命令提示字元 （以系統管理員身分執行）。
    
2. 前往您下載 PST 收集工具所在的目錄。
    
3. 執行下列命令，以封鎖在步驟 1 中找到的 PST 檔案的存取。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    下表說明參數和其所需的值，當您執行 DataCollectorMaster.exe 命令，以封鎖建立，以及變更的 PST 檔案。 
    
    |參數 * * *|****描述****|範例 * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋資料的類型。 目前，您可以使用 PST 收集工具來搜尋的 PST 檔案。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定將會執行此工具的作業類型。 使用值`Block`以防止使用者建立新的 PST 檔案，並對現有 PST 檔案的變更。  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |指定現有 PST 收集工作的名稱。 您必須使用此您在步驟 1 中尋找模式中執行此工具時所用的相同工作名稱。 此工作名稱也會新增至封鎖模式執行工具時建立記錄檔的名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |會指定資料夾包含.xml 組態檔中尋找模式執行工具時所建立。 使用您用於步驟 1 中的這個參數的值相同。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定將會封鎖作業的記錄檔複製到的資料夾。 這是選擇性的參數。 如果您未包含它，記錄檔會複製到您下載 PST 收集工具所在的資料夾。 請考慮使用相同的記錄位置，讓所有的記錄檔會儲存在相同的資料夾，在步驟 1 中尋找模式中執行此工具時所用。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |使用此參數來防止使用者變更 PST 檔案。 當您使用此參數時，會建立下列登錄項目： `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` ，且 [資料] 值設為 1。 這個登錄設定建立您的組織中的機器上封鎖模式中執行 PST 收集工具時建立的 GPO。  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |使用此參數可防止使用者建立新的 PST 檔案、 開啟將 PST 檔案匯入至 Outlook，並從 Outlook 匯出的 PST 檔案。 當您使用此參數時，會建立下列登錄項目： `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` ，且 [資料] 值設為 1。 這個登錄設定建立您的組織中的機器上封鎖模式中執行 PST 收集工具時建立的 GPO。  <br/> | `-BlockNewFiles` <br/> |
   
    以下是針對各個參數使用實際值的 DataCollectorMaster.exe 命令的語法範例：

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    系統會提示您確認您想要封鎖新的 PST 檔案或變更現有 PST 檔案。 確認您想要繼續，而且命令執行成功後，會顯示訊息，指出已建立新的 GPO，名為 「 PST 流量控制項 」。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>步驟 3： 將 PST 檔案複製到集合的位置

下一步是將複製的 PST 檔案，找到時尋找模式中執行 PST 收集工具。 這可讓您收集在一個位置的 PST 檔案，以便您可以稍後再匯入到 Office 365。 將 PST 檔案複製到集合位置之前，請考慮決定所需的儲存空間總量。 您可以使用來計算所有的 PST 檔案的總大小的步驟 1 中所建立的 CSV 檔案。
  
> [!NOTE]
> 在您的 PST 檔案匯入至 Office 365，並從其原始位置刪除這些之後，您可能想要刪除您在此步驟中複製到集合位置。 
  
1. 在本機電腦上開啟命令提示字元 （以系統管理員身分執行）。
    
2. 前往您下載 PST 收集工具所在的目錄。
    
3. 執行下列命令，以將 PST 檔案複製到指定的位置。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表說明參數和其所需的值，當您執行 DataCollectorMaster.exe 命令，以將 PST 檔案複製。 
    
    |參數 * * *|****描述****|範例 * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋資料的類型。 目前，您可以使用 PST 收集工具來搜尋的 PST 檔案。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定將會執行此工具的作業類型。 使用值`Collect`以複製 PST 檔案，找不到當您執行工具，以尋找模式。 請注意，此工具可以將 PST 檔案複製，在 Outlook 中開啟，然後複製已連線至 Outlook 設定檔的 PST 檔案。  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |指定現有 PST 收集工作的名稱。 您必須使用此您在步驟 1 中尋找模式中執行此工具時所用的相同工作名稱。 此工作名稱也會加入至收集模式中執行此工具時建立記錄檔的名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |使用相同的值所用`Locations`在步驟 1 中的參數。 如果您想要重新執行工具，從其在步驟 5 中的來源位置中刪除的 PST 檔案，以收集模式執行工具時，您必須包含此參數。  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |指定包含.xml 組態檔中尋找模式執行工具時所建立的資料夾。 使用您用於步驟 1 中的這個參數的值相同。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |指定您要複製的 PST 檔案的集合位置。 您可以將檔案複製到檔案伺服器、 網路檔案共用或硬碟。 位置必須存在之前以收集模式執行此工具。 工具不會建立該位置，並將傳回的錯誤訊息不存在。  <br/> 此外，您具有寫入權限給此參數所指定的集合位置。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |指定記錄檔收集模式會複製到的資料夾。 這是選擇性的參數。 如果您未包含它，記錄檔會複製到您下載 PST 收集工具所在的資料夾。 請考慮使用相同的記錄位置，讓所有的記錄檔會儲存在相同的資料夾，在步驟 1 中尋找模式中執行此工具時所用。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此選用參數可讓您重新執行工具在現有 PST 收集工作集合模式。 如果您先前在收集模式中，執行此工具，但再執行此工具中尋找模式與`ForceRestart`切換至重新掃描的 PST 檔案的位置，您可以使用此參數，重新執行工具以集合模式，並重新將複製沒有找到時的 PST 檔案您重新掃描的位置。 當使用`ForceRestart`參數集合模式，此工具會忽略任何先前集合作業，並嘗試將 PST 檔案複製從頭。  <br/> | `-ForceRestart` <br/> |
   
    以下是語法的 DataCollectorMaster.exe 工具針對各個參數使用實際值範例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    執行此命令之後，詳細的狀態郵件會顯示 [顯示進度收集找不到在步驟 1 中的 PST 檔案。 在一段時間之後, 的最終狀態郵件會顯示是否發生任何錯誤和記錄檔複製到的位置。 相同的狀態郵件會複製到.log 檔案。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>收集模式中執行 DataCollectorMaster.exe 的結果

收集模式中成功執行 DataCollectorMaster.exe 之後，建立並儲存在所指定的資料夾中的下列檔案`LogLocation`和`ConfigurationLocation`參數。 
  
- **\<工作名稱\>_收集_\<DateTimeStamp\>.log** -記錄檔會包含已顯示狀態訊息。 在所指定的資料夾中建立此檔案`LogLocation`參數。 
    
- **\<工作名稱\>_收集_\<DateTimeStamp\>.xml** -XML 檔案只包含其中所使用的工具已執行收集模式中的參數值的相關資訊。 當您執行時使用此檔案中的資料重新執行 DataCollectorMaster.exe 工具，以刪除 PST 檔案;請參閱 「[步驟 5](#step-5-delete-the-pst-files-found-on-your-network)。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>步驟 4： 將 PST 檔案匯入 Office 365

您已收集在步驟 1 中找到的 PST 檔案之後下, 一步是匯入到 Office 365 中的信箱。 為組件或匯入程序，您必須建立包含您想要匯入每個 PST 檔案的資料列的 CSV 對應檔案。 每一列中的資訊會指定 PST 檔案名稱，使用者的電子郵件地址，而且您是否要將 PST 檔案匯入至使用者的主要信箱還是封存信箱。 使用中的資訊**工作名稱\>_找到_\<DateTimeStamp.csv**檔案 （步驟中建立） 1 可協助您建立 CSV 對應檔案。 
  
將 PST 檔案匯入 Office 365 的逐步指示，請參閱下列主題：
  
- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>步驟 5： 刪除您網路上找到的 PST 檔案

您找到並收集的 PST 檔案匯入至 Office 365 中的 Exchange Online 信箱之後，您可以使用 PST 收集工具從他們找到在步驟 1 中的原始來源位置中刪除的 PST 檔案。 
  
1. 在本機電腦上開啟命令提示字元 （以系統管理員身分執行）。
    
2. 前往您下載 PST 收集工具所在的目錄。
    
3. 執行下列命令，以刪除 PST 檔案。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表說明參數和其所需的值，當您執行 DataCollectorMaster.exe 命令，以刪除 PST 檔案。 
    
    |參數 * * *|****描述****|範例 * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋資料的類型。 目前，您可以使用 PST 收集工具來搜尋的 PST 檔案。 ![空格字元](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定將會執行此工具的作業類型。 使用值`Delete`若要刪除 PST 檔案，找不到當您執行工具，以尋找模式。  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |指定現有 PST 收集工作的名稱。 您必須使用此尋找模式和步驟 1] 和 [步驟 3 中的收集模式中執行此工具時所用的相同工作名稱。 此工作名稱也會加入至刪除模式執行工具時建立記錄檔的名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定包含.xml 組態檔中收集模式執行工具時所建立的資料夾。 使用此參數在步驟 3 中所用的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定將會刪除模式的記錄檔複製到的資料夾。 這是選擇性的參數。 如果您未包含它，記錄檔會複製到您下載 PST 收集工具所在的資料夾。 請考慮使用相同的記錄位置，讓所有的記錄檔會儲存在相同的資料夾，在 [尋找] 和 [步驟 1] 和 [步驟 3 中的收集模式中執行此工具時所用。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此選用參數可讓您重新執行工具在現有 PST 收集工作刪除模式。 如果您先前在 「 刪除 」 模式中執行此工具，但再執行此工具中尋找模式與`ForceRestart`切換至重新掃描的 PST 檔案的位置，您可以使用此參數，重新執行工具以刪除模式，並刪除沒有找到時的 PST 檔案您重新 scanned 位置。 當使用`ForceRestart`參數刪除模式，此工具會忽略任何先前的刪除作業，並嘗試再次刪除 PST 檔案。  <br/> | `-ForceRestart` <br/> 

    以下是語法的 DataCollectorMaster.exe 工具針對各個參數使用實際值範例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    執行此命令之後，詳細的狀態郵件會顯示 [顯示進度刪除，在步驟 1 中發現並收集在步驟 3 中的 PST 檔案。 在一段時間之後, 的最終狀態郵件會顯示是否發生任何錯誤和記錄檔複製到的位置。 相同的狀態郵件會複製到.log 檔案。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>刪除 」 模式中執行 DataCollectorMaster.exe 的結果

成功執行 DataCollectorMaster.exe 刪除模式之後，建立和儲存在所指定的資料夾中的下列檔案`LogLocation`和`ConfigurationLocation`參數。 
  
- **\<工作名稱\>_刪除_\<DateTimeStamp\>.log** -記錄檔會包含已顯示狀態訊息。 在所指定的資料夾中建立此檔案`LogLocation`參數。 
    
- **\<工作名稱\>_刪除_\<DateTimeStamp\>.xml** -XML 檔案只包含其中所使用的工具已執行刪除模式的參數值的相關資訊。 它也會列出每個已刪除的 PST 檔案的名稱及檔案路徑。 在所指定的資料夾中建立此檔案`ConfigurationLocation`參數。 
