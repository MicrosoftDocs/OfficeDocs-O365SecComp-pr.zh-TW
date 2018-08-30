---
title: 監督報告
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: 使用以查看哪些電子郵件需要規範檢閱監督報表以及誰應該執行它。
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526351"
---
# <a name="supervision-reports"></a>監督報告

監督原則定義其組織中的通訊需要規範、 檢閱及誰可以執行這些檢閱 （英文）。若要查看檢閱活動層級原則和檢閱者使用監督報告。每個原則，您也可以檢閱活動的目前狀態檢視 live 的統計資料。[解更多關於監督原則](configure-supervision-policies.md)。 
  
> [!NOTE]
> 使用監督原則您的組織需要的 Office 365 E5 訂閱。如果您不具有該對應並想要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
您可以使用監督報告：
  
- 確認您的原則運作如您預期。 
    
- 深入了解多少電子郵件會被識別出供檢閱。
    
- 了解如何許多電子郵件不相容與哪些已通過檢閱。這項資訊可協助您決定是否要調整成您的原則或變更檢閱者的數目。
    
## <a name="view-the-supervision-report"></a>檢視監督報告

1. 登入[安全性&amp;規範中心](https://protection.office.com/)使用 Office 365 組織中的檢視監督報告的權限的管理帳戶的認證。 
    
2. 移至 [**報表** \> **儀表板**。您會看見的監督報告 widget 及其他報告具有存取權。
    
3. 按一下 [以開啟 [詳細資料報告] 頁面上的**監督**widget。 
    
> [!NOTE]
> 如果您不可以存取 [**報告**] 頁面上，核取您正在監督檢閱角色群組的成員，[讓組織中可用的監督](configure-supervision-policies.md#SRavailable)所述。要包含在此角色群組可讓您建立及管理監督原則並執行報表。 
  
## <a name="how-to-use-the-report"></a>如何使用報告

當監督原則識別檢閱的電子郵件時、 電子郵件會傳遞至檢閱者監督資料夾中 Outlook 和 Outlook web app。這份報告會列出每個原則的名稱及通訊數目檢閱程序中的每一階段。
  
使用報告：
  
- 檢視資料的所有或特定的原則。
    
- 檢視資料標籤類型分組 （例如符合標準、 Questionable 等等）、 檢閱者或訊息類型。
    
- 將資料匯出為 CSV 檔案。
    
- 篩選根據檢閱活動日期、 標記類型、 檢閱、 郵件類型的資料。
    
以下是分解您可能會看到 [**標記類型**] 欄中的值。 
  
|**標記類型**|**其意思**|
|:-----|:-----|
|不檢閱  <br/> |尚未檢視的電子郵件數目。這些電子郵件送交檢閱者監督 Outlook 資料夾中的檢閱。  <br/> |
|相容  <br/> |檢閱並標示為相容的電子郵件數目。需要進一步的動作。  <br/> |
|問題  <br/> |檢閱並標示問題的電子郵件數目。這可以做為標幟 ；其他檢閱者可協助檢查電子郵件是否需要將正在調查規範。  <br/> |
|非相容 （使用中）  <br/> |非相容的目前調查檢閱者的電子郵件數目。  <br/> |
|非相容 （解析）  <br/> |檢閱者調查並解決非相容電子郵件數目。  <br/> |
   
## <a name="more-details"></a>更多詳細資料

- 監督原則必須先佈建才會出現在此報告。
    
- 如果會刪除原則，仍會顯示歷程資料。不過，它們指定為 「 非存在原則、"並**匯出**函數無法使用。 
    
- 如果報表沒有預設顯示的任何資料，則可能是因為目前的日期範圍沒有顯示任何資料。在下列情況下，使用**篩選器**控制項變更的日期範圍。 
    

