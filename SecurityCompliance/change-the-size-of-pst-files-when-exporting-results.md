---
title: 匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以變更下載到您的電腦時匯出 eDiscovery 搜尋結果的 PST 檔案的預設大小。
ms.openlocfilehash: 8a956091f29ec1b564d3194c7e3ca2680fdeb564
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214623"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小

當您使用 Office 365 eDiscovery 匯出工具來匯出 eDiscovery 搜尋的電子郵件結果從不同的 Microsoft eDiscovery 工具時，可以匯出的 PST 檔案的預設大小為 10 GB。如果您想要變更此預設大小，您可以編輯您用來匯出搜尋結果的電腦上的 Windows 登錄。若要執行這項作業的其中一個原因是讓 PST 檔案可符合抽取式媒體、 這類 DVD、 光碟片或的 USB 磁碟機上。 
  
> [!NOTE]
>  Office 365 eDiscovery 匯出工具來匯出搜尋結果時使用 Office 365 安全性內容搜尋&amp;規範中心、 Exchange Online 中的就地 eDiscovery 和 SharePoint Online 中的 eDiscovery 中心。 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>建立匯出 eDiscovery 搜尋結果時變更 PST 檔案大小的登錄設定

您將使用的 eDiscovery 搜尋結果匯出之電腦上執行下列程序。
  
1. 如果已開啟，關閉 Office 365 eDiscovery 匯出工具。 
    
2. 使用.reg; filename 尾碼將下列文字儲存到視窗登錄檔案例如，PstExportSize.reg。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    在範例中，與上述`PstSizeLimitInBytes`值設為 1,073,741,824 位元組或約 1 GB。以下是一些其他範例值`PstSizeLimitInBytes`設定。 
    
    |**大小以 GB 為 (1tb)**|**大小 （位元組）**|
    |:-----|:-----|
    |.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 變更`PstSizeLimitInBytes`PST 檔案時您匯出搜尋結果，然後儲存檔案的所需的最大大小的值。 
    
4. 在 Windows 檔案總管中，按一下 [或按兩下您在先前步驟中建立.reg 檔案。
    
5. 在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。 
    
6. 出現提示時若要繼續，按一下 [**是**]。
    
    登錄編輯程式中會顯示訊息，設定已順利新增至登錄。
    
7. 您可以重複執行步驟 3-6，以變更的值`PstSizeLimitInBytes`登錄設定。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>關於匯出 eDiscovery 搜尋結果時變更 PST 檔案的預設大小的常見問題集

 **為什麼要選擇是預設的大小為 10 GB？**
  
10 GB 的預設大小根據客戶意見反應;10 GB 會是內容的很好的平衡之間最佳單一 PST 以及檔案損毀的最小機會量。
  
 **我應該增加或減少 PST 檔案的預設大小吗？**
  
客戶通常會降低大小限制，讓他們可以實際隨附其組織中的其他位置的抽取式媒體上能容納的搜尋結果。我們不建議您在因為 PST 檔案大於 10 GB 可能已損毀問題增加預設大小。
  
 **若要這樣做上有必須哪些電腦？**
  
您需要變更執行 Office 365 eDiscovery 匯出工具任何本機電腦上的登錄設定。
  
 **變更此設定後，我必須重新啟動電腦吗？**
  
否，您不需要重新啟動電腦。但如果執行 Office 365 eDiscovery 匯出工具，您必須關閉並重新啟動它之後變更此設定。
  
 **沒有取得編輯現有的登錄機碼或沒有取得建立新的金鑰吗？**
  
新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。然後設定編輯每次您變更並重新執行.reg 編輯檔案。
