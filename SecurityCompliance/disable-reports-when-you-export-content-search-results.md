---
title: 當您將 Office 365 安全性的內容的搜尋結果匯出停用報告&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 編輯 Windows 登錄本機電腦上的 Office 365 安全性匯出內容的搜尋結果時停用報告&amp;Comliance 中心。停用這些報告可加速下載時間及儲存的磁碟空間。
ms.openlocfilehash: 0be2be18eaccb618a49e1b58a5c0e53d0a339d1e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213473"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>當您將 Office 365 安全性的內容的搜尋結果匯出停用報告&amp;規範中心

當您使用 Office 365 eDiscovery 匯出工具匯出其結果的安全性內容搜尋&amp;規範中心工具自動建立並匯出包含匯出內容的其他資訊的兩個報表。這些報告是 Results.csv 檔案和 Manifest.xml 檔 （請參閱本主題中針對這些報告的詳細描述的[常見問題集需停用匯出報告](#frequently-asked-questions-about-disabling-export-reports)」 一節）。因為這些檔案可能會很大，您可加速下載時間並儲存由防止這些檔案所匯出的磁碟空間。您可以變更您用來匯出搜尋結果的電腦上的 Windows 登錄。如果您想要包含於稍後的報告，您可以編輯登錄設定。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>建立停用匯出報告的登錄設定

您將使用來匯出內容的搜尋結果的電腦上執行下列程序。
  
1. 如果已開啟，關閉 Office 365 eDiscovery 匯出工具。
    
2. 執行下列一或兩個以下步驟，哪些匯出報告視您要停用。
    
    - **Results.csv**
    
      使用.reg; filename 尾碼將下列文字儲存至 Windows 登錄檔案例如，DisableResultsCsv.reg。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      使用.reg; filename 尾碼將下列文字儲存至 Windows 登錄檔案例如，DisableManifestXml.reg。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. 在 Windows 檔案總管中，按一下 [或按兩下您在先前步驟中建立.reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。 
    
5. 出現提示時若要繼續，按一下 [**是**]。
    
    登錄編輯程式中會顯示訊息，設定已順利新增至登錄。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>編輯若要重新啟用匯出報告的登錄設定

如果您停用 Results.csv 和 Manifest.xml 報告在先前程序中建立.reg 檔案，您可以編輯這些重新啟用報表以便與搜尋結果匯出的檔案。同樣地，您將使用來匯出內容的搜尋結果的電腦上執行下列程序。
  
1. 如果已開啟，關閉 Office 365 eDiscovery 匯出工具。
    
2. 編輯一或兩個您在前一程序中建立.reg 編輯檔案。
    
    - **Results.csv**
    
        開啟 [記事本] 中的 DisableResultsCsv.reg 檔案變更值`False`至`True`，然後儲存檔案。例如，編輯檔案之後，它看起來類似：
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        開啟 [記事本] 中的 DisableManifestXml.reg 檔案變更值`False`至`True`，然後儲存檔案。例如，編輯檔案之後，它看起來類似：
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. 在 Windows 檔案總管中，按一下 [或按兩下您在上一個步驟中編輯.reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 **[是]** 以讓 [登錄編輯程式中進行變更。 
    
5. 出現提示時若要繼續，按一下 [**是**]。
    
    登錄編輯程式中會顯示訊息，設定已順利新增至登錄。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>停用匯出報表相關的常見問題集
<a name="faqs"> </a>

 **Results.csv 和 Manifest.xml 報表有哪些？**
  
Results.csv 和 Manifest.xml 檔案包含已匯出的內容的其他資訊。
  
- 包含每個項目下載 （英文） 做為自訂的搜尋結果的相關資訊**Results.csv** Excel 文件。為電子郵件、 結果記錄檔包含每個郵件的資訊包括： 
    
  - 來源信箱中訊息的位置 (包括訊息位於主要或封存信箱)。
    
  - 送出或收到郵件的日期。
    
  - 郵件的主旨行。
    
  - 郵件的寄件者和收件者。
    
  - 郵件是否重複的郵件如果您啟用重複資料刪除匯出搜尋結果時。重複的郵件會識別將郵件當做重複的**父項目識別碼**] 欄中有一個值。**父項目識別碼**] 欄中的值是已匯出之郵件的 [**項目 DocumentId** ] 欄中的值相同。 
    
    文件從 SharePoint 和 OneDrive for Business 網站的結果記錄檔包含每個文件的資訊包括：
    
  - 文件的 URL。
    
  - 文件庫所在之網站集合的 URL。
    
  - 上次修改文件的日期。
    
  - (位於結果記錄檔中的 [主旨] 欄) 的文件名稱。
    
- **Manifest.xml**資訊清單檔案 （以 XML 格式），其中包含搜尋結果中包含每個項目的相關資訊。在此報告中的資訊是 Results.csv 報表相同，但它的格式指定所電子探索參照模型 (EDRM)。如需 EDRM 的詳細資訊，請移至[https://www.edrm.net](https://www.edrm.net)。
    
 **何時應該使用停用匯出這些報告？**
  
您的特定需求而定。許多組織不需要搜尋結果的其他資訊並不需要這些報告。
  
 **若要這樣做上有必須哪些電腦？**
  
 您必須在執行 Office 365 eDiscovery 匯出工具的任何本機電腦的登錄設定變更。 
  
 **變更此設定後，我必須重新啟動電腦吗？**
  
否，您不需要重新啟動電腦。但如果執行 Office 365 eDiscovery 匯出工具，來關閉再重新啟動它之後變更登錄設定。
  
 **沒有取得編輯現有的登錄機碼或沒有取得建立新的金鑰吗？**
  
新的登錄機碼會建立第一次執行您在本主題中的程序中建立的.reg 檔案。然後設定編輯每次您變更並重新執行.reg 編輯檔案。
