---
title: Office 365 雲端 App 安全性的網路流量記錄與資料來源
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 雲端應用程式安全性適用於從各種提供者的網頁流量記錄。閱讀本篇文章以深入了解網頁流量記錄和支援的 Office 365 雲端應用程式安全性的資料來源。
ms.openlocfilehash: 67246ded0e3d39c81b5b906f753b91298309d1d8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218103"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性的網路流量記錄與資料來源
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
  
您可以使用 Office 365 雲端應用程式安全性的各種 web 流量記錄檔與資料來源。不過，您的網頁流量記錄檔必須包含特定資訊和格式設定特定的方式，讓他們可搭配 Office 365 雲端應用程式安全性應用程式探索報告與雲端探索儀表板。使用本文做參考指南 web 流量記錄檔和您將與 Office 365 雲端應用程式安全性搭配使用的資料來源。
  
> [!NOTE]
> 您必須是以存取安全性的全域管理員、 安全性管理員或安全性讀者&amp;規範中心與 Office 365 雲端應用程式安全性入口網站。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="web-traffic-log-requirements"></a>Web 流量記錄檔需求

使用 office 365 雲端應用程式安全性使用資料可協助您了解哪些應用程式人員在組織中您 web 流量記錄檔中。更多詳細資料所包含的記錄檔，更好的可視性需要使用者活動。
  
下列各節將列出必要的屬性及正確地使用 Office 365 雲端應用程式安全性您 web 流量記錄檔的額外需求。

### <a name="attributes"></a>屬性

Office 365 雲端應用程式安全性無法顯示或分析您的網頁流量記錄檔中未含的屬性。例如，Cisco ASA 防火牆的標準記錄格式沒有每個交易、 username 或目標 URL (僅限目標 IP) 上傳的位元組的數目。因此，這些屬性都不會顯示在雲端探索資料與可見性的雲端應用程式僅限於。Cisco ASA 防火牆資訊層級必須設定為 6。 

您的網頁流量記錄檔應包含下列屬性：

- 異動的日期
- 來源 IP
- 來源使用者 （強烈建議使用）
- 目的地 IP 位址
- 目的地 URL （建議使用;Url 提供的雲端應用程式偵測較高的正確性比 IP 位址）
- 總資料量 （建議使用，資料資訊為高價值）
- 數量上傳或下載的資料 （建議使用，提供前瞻相關雲端應用程式的使用模式）
- （允許或封鎖） 所採取的動作

### <a name="additional-requirements"></a>其他需求 

除了包括本文稍早所列的屬性、 web 流量記錄檔應符合下列需求：

- 必須支援的記錄檔的資料來源。
- 使用記錄檔的格式必須符合標準格式。當檔案上傳時、 應用程式探索會確認此。
- 事件記錄檔中的必須發生不得超過 90 天以上。
- 記錄檔必須包含可以分析的網路活動的輸出流量資訊。
  
## <a name="data-attributes-for-different-vendors"></a>不同的廠商資料屬性

下表摘要說明從不同的廠商的網頁流量記錄檔中的資訊。**請務必洽詢您的廠商的最新資訊。**


|                 資料來源                  |    目標應用程式 URL    |    目標應用程式 IP     |       使用者名稱       |      來源 IP       |    總流量     |    上傳的位元組    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          無          |          否          |
|                  藍色外覆                   | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  檢查點                  |          否          | <strong>是</strong> |          無          | <strong>是</strong> |          無          |          否          |
|              Cisco ASA (Syslog)              |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          |
|           Cisco 與火力 ASA           | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Cisco FWSM                  |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          |
|              Cisco Ironport WSA              | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Cisco Meraki                 | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> |          無          |          否          |
|           Clavister NGFW (Syslog)            | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                SonicWall (前身為 Dell)                | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|            數位藝術 i 篩選             | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Fortigate                   |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Juniper SRX                  |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Juniper SSG                  |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  McAfee SWG                  | <strong>是</strong> |          無          |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    MS TMG                    | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|              Palo Alto 網路              |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    Sophos                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          無          |
|                Squid （一般）                | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> |
|                Squid （原生）                | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> |
| Websense-調查的詳細資料報告 (CSV) | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|    Websense-網際網路活動記錄檔 (CEF)    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                   Zscaler                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>支援的廠商防火牆及 proxy

Office 365 雲端應用程式安全性支援下列防火牆及 proxy。
  
- Barracuda-Web 應用程式防火牆 (W3C)  
- 藍色外覆 Proxy 個儲存-存取記錄檔 (W3C)
- 檢查點
- Cisco ASA 防火牆 （確定的資訊層級設為 6）
- Cisco 與火力 ASA   
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Merkai-Url 記錄檔
- Clavister NGFW (Syslog)
- 數位藝術 i 篩選
- Fortinet Fortigate
- iboss Secure Cloud 閘道
- Juniper SRX
- Juniper SSG
- McAfee 安全網路閘道
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto 數列防火牆
- Sonicwall (前身為 Dell)   
- Sophos 個儲存
- Sophos XG
- Sophos Cyberoam
- Squid （一般）
- Squid （原生）
- Websense-Web 安全性解決方案-調查的詳細資料報告 (CSV)
- Websense-Web 安全性解決方案-網際網路活動記錄檔 (CEF)
- Zscaler
    
> [!NOTE]
> 如果您想要使用的資料來源此處不包含在內，您可以要求它要新增至應用程式探索。若要這樣做，當您建立報表時，選取**其他****資料**來源。然後輸入您嘗試將上傳的資料來源的名稱。我們將檢閱記錄檔，並且可讓您知道若我們要新增的記錄類型的支援。或者，您可以[定義自訂剖析器](https://docs.microsoft.com/cloud-app-security/custom-log-parser)符合您的格式。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>疑難排解記錄檔上傳時的錯誤

上傳 web 流量記錄檔之後，請檢查控管記錄檔以查看 [是否未發生任何錯誤。如果沒有錯誤，使用下表中的資訊來解決這些錯誤。
  
|**錯誤**|**描述**|**登入時會顯示一個對話方塊，內含下列敘述︰Lync 無法針對您的登入地址確認伺服器是否可信任。**|
|:-----|:-----|:-----|
|不支援的檔案類型  <br/> |上傳的檔案不是有效的記錄檔。例如，圖像檔案。  <br/> |上傳的文字、 zip 或 gzip 直接從您的防火牆或 proxy 匯出的檔案。  <br/> |
|內部錯誤  <br/> |內部資源已偵測到失敗。  <br/> |按一下 [重新執行工作的 [**重試**]。  <br/> |
|記錄檔格式不符合  <br/> |您上傳的記錄檔格式不符合此資料來源的預期的記錄格式。  <br/> |
確認記錄檔未損毀。比較且符合 [上傳] 頁面上顯示的範例格式的記錄檔案格式。 |
|交易會超過 90 天  <br/> |所有交易超過 90 天與因此要忽略。  <br/> |匯出與最近的事件的新記錄檔並重新上傳。  <br/> |
|目錄中的雲端應用程式沒有交易  <br/> |沒有任何可識別的雲端應用程式的交易記錄檔中找到。  <br/> |確認記錄檔包含的輸出流量資訊。  <br/> |
|不支援的記錄類型  <br/> |當您選取 [**資料來源 = 其他 （不支援）**、 不剖析記錄檔。而傳送給[Microsoft 雲端應用程式安全性](https://aka.ms/whatiscas)技術小組的檢閱。<br/> |[Microsoft 雲端應用程式安全性](https://aka.ms/whatiscas)技術小組建立專用的剖析器每個資料來源。已經支援最常用的資料來源。不支援的資料來源上傳、 時它是檢閱並新增至的潛在的新資料來源剖析器清單。<br/> 當新剖析器新增到 「 功能時、 通知隨附於 Microsoft 雲端應用程式安全性版本資訊。  <br/> |
   
## <a name="next-steps"></a>後續步驟

- [檢閱並採取行動提醒](review-office-365-cas-alerts.md)
    
- [建立應用程式探索報告](create-app-discovery-reports-in-ocas.md)
    
- [檢閱應用程式探索偵測](review-app-discovery-findings-in-ocas.md)
    
- [檢閱 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)
    

