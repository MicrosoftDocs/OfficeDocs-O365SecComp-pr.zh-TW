---
title: 匯出 eDiscovery 搜尋結果從 Office 365 時所增加的下載速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何設定 Windows 登錄，以增加資料輸送量下載搜尋結果時及搜尋資料從 Office 365 安全性&amp;規範中心與 Office 365 進階 eDiscovery。
ms.openlocfilehash: a23525ada1ef5f36bc7df4fc738c712e22243bc0
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295426"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>匯出 eDiscovery 搜尋結果從 Office 365 時所增加的下載速度

當您使用 Office 365 eDiscovery 匯出工具下載 Office 365 安全性內容的搜尋結果&amp;規範中心或下載資料從 Office 365 進階 eDiscovery，此工具會啟動並行匯出數目若要下載到本機電腦的資料的作業。根據預設，並行作業的數目設為您使用下載資料的電腦中的核心數 8 的次數。例如，如果您有雙核心電腦 （這表示一個晶片上的兩個集中處理單位），同時匯出作業的預設數為 16。若要增加的資料傳輸輸送量與提升並下載程序，您可以依您用以下載搜尋結果的電腦上設定 Windows 登錄設定增加並行作業數目。為了提升並下載程序，建議您開始使用設定為 24 並行作業。
  
如果您透過低頻寬網路下載搜尋結果，請增加此設定可能會造成負面影響。或者，您可以增加 （並行作業的數目上限為 512） 高頻寬網路中的多個 24 並行作業的設定。設定此登錄設定之後，您可能必須將它變更為找出最佳的並行環境作業數目。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>建立登錄設定來匯出資料時變更並行作業的數目

您將使用的安全性下載搜尋結果的電腦上執行下列程序&amp;規範中心或進階的 eDiscovery 的資料。
  
1. 如果已開啟，關閉 Office 365 eDiscovery 匯出工具。 
    
2. 使用.reg; filename 尾碼將下列文字儲存到視窗登錄檔案例如，ConcurrentOperations.reg。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    為舊清楚，建議您開始使用 24 並行作業，然後變更此設定可分別。
    
3. 在 Windows 檔案總管中，按一下 [或按兩下您在上一個步驟中建立.reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。 
    
5. 出現提示時若要繼續，按一下 [**是**]。
    
    登錄編輯程式中會顯示訊息，設定已順利新增至登錄。
    
6. 您可以重複執行步驟 2-5 變更的值`DownloadConcurrency`登錄設定。 
    
    > [!IMPORTANT]
    > 建立或變更之後`DownloadConcurrency`登錄設定，請務必建立新的匯出工作或重新啟動現有匯出工作的搜尋結果或要下載的資料。請參閱如需詳細資訊[的詳細資訊](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)] 區段。 
  
## <a name="more-information"></a>詳細資訊

- 新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。然後`DownloadConcurrency`登錄設定編輯每次您變更並重新執行.reg 編輯檔案。 
    
- Office 365 eDiscovery 匯出工具會使用[Azure AzCopy 公用程式](https://go.microsoft.com/fwlink/?linkid=849949)的安全性下載搜尋資料&amp;規範中心或進階的 eDiscovery。設定`DownloadConcurrency`登錄設定就類似於執行 AzCopy 公用程式時使用 **/NC**參數。所以的登錄設定`"DownloadConcurrency=24"`必須使用的參數值相同的效果`/NC:24`與 AzCopy 公用程式。 
    
- 如果您要停止匯出下載仍在建構中，然後將其重新 （嘗試再次下載搜尋結果）、 Office 365 eDiscovery 匯出工具將嘗試繼續執行相同的下載。如此，如果您啟動的下載 （英文）、 停止，並再變更`DownloadConcurrency`登錄設定，下載可能會失敗如果重新啟動 （依序按一下 [**下載匯出結果**)。這是因為匯出工具會嘗試將繼續先前下載 （英文） 使用因為您已變更的登錄設定不正確的設定。
    
    因此，之後變更`DownloadConcurrency`登錄設定，請先重新啟動匯出工作 （依序按一下 [**重新啟動匯出**) 中的 [安全性]&amp;規範中心。然後您可以下載匯出的結果。如需匯出搜尋結果和資料的詳細資訊，請參閱：
    
  - [從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心](export-search-results.md)
    
  - [在 Office 365 進階電子文件探索中匯出結果](export-results-in-advanced-ediscovery.md)
    
