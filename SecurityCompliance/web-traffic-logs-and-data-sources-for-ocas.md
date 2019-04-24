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
description: Office 365 雲端 App 安全性適用於從各種提供者的 web 流量記錄檔。 閱讀本篇文章以深入了解網頁流量記錄檔和 Office 365 雲端 App 安全性支援資料來源。
ms.openlocfilehash: 67246ded0e3d39c81b5b906f753b91298309d1d8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266848"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性的網路流量記錄與資料來源
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
  
您可以使用 Office 365 雲端 App 安全性各種 web 流量記錄檔與資料來源。 不過，web 流量記錄檔必須包含特定資訊，並格式化以特定方式，讓他們將會使用 Office 365 雲端 App 安全性 app 探索報表及雲端探索儀表板。 使用本文做為參考指南 web 流量記錄檔以及您要使用與 Office 365 雲端 App 安全性的資料來源。
  
> [!NOTE]
> 您必須是全域系統管理員、 安全性系統管理員或安全性讀取者存取安全性&amp;規範中心和 Office 365 雲端 App 安全性的入口網站。 請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="web-traffic-log-requirements"></a>Web 流量記錄檔需求

使用 office 365 雲端 App 安全性使用資料可協助您了解哪些應用程式人員在組織中您 web 流量記錄檔中。 包含在記錄檔，但使用者活動的較佳可見度您有更多詳細資料。
  
下列各節將列出必要的屬性及其他需求才能正確地與 Office 365 雲端 App 安全性您網站的流量記錄。

### <a name="attributes"></a>屬性

Office 365 雲端 App 安全性無法顯示或分析 web 流量記錄檔中未包含的屬性。 Cisco ASA 防火牆的標準的記錄檔格式，例如沒有每個交易、 使用者名稱或目標 URL (僅限目標 IP) 上傳的位元組的數。 因此，這些屬性不會顯示在雲端探索資料，並查看雲端應用程式僅限於。 Cisco ASA 防火牆資訊層級必須設定為 6。 

您網站的流量記錄應包含下列屬性：

- 交易日期
- 來源 IP
- 來源使用者 （強烈建議）
- 目的地 IP 位址
- 目的地 URL （建議使用;Url 提供更高的佳精確度，雲端應用程式偵測比 IP 位址）
- 總資料量 （建議使用，資料的資訊是極其重要）
- 數量上傳或下載的資料 （建議使用，可提供見解有關雲端應用程式的使用模式）
- （允許或封鎖） 採取的動作

### <a name="additional-requirements"></a>其他需求 

除了包括本文稍早所列的屬性，您網站的流量記錄應符合下列需求：

- 必須支援記錄檔的資料來源。
- 使用記錄檔的格式必須符合標準格式。 當檔案上傳時，應用程式探索會確認這。
- 事件記錄檔中的必須已發生不超過 90 天。
- 記錄檔必須包含您可以分析網路活動的輸出流量資訊。
  
## <a name="data-attributes-for-different-vendors"></a>不同廠商使用的資料屬性

下表摘要說明各種廠商的 web 流量記錄檔中的資訊。 **請務必洽詢您的廠商的最新的資訊。**


|                 資料來源                  |    目標應用程式 URL    |    目標應用程式 IP     |       使用者名稱       |      來源 IP       |    總流量     |    上傳的位元組    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          否          |          否          |
|                  藍色外覆                   | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  檢查點                  |          否          | <strong>是</strong> |          無          | <strong>是</strong> |          否          |          否          |
|              Cisco ASA (Syslog)              |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          |
|           Cisco 與火力 ASA           | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Cisco FWSM                  |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          |
|              Cisco Ironport WSA              | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Cisco Meraki                 | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> |          否          |          否          |
|           Clavister NGFW (Syslog)            | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                SonicWall (先前稱為 Dell)                | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|            數位藝術 i 篩選             | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Fortigate                   |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Juniper SRX                  |          否          | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Juniper SSG                  |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  McAfee SWG                  | <strong>是</strong> |          否          |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    MS TMG                    | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|              Palo 琴奧圖網路              |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    Sophos                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          無          |
|                Squid （普遍）                | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> |
|                Squid （原生）                | <strong>是</strong> |          無          | <strong>是</strong> | <strong>是</strong> |          無          | <strong>是</strong> |
| Websense-調查的詳細資料報告 (CSV) | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|    Websense-網際網路活動記錄檔 (CEF)    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                   Zscaler                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>支援的廠商防火牆和 proxy

Office 365 雲端 App 安全性支援下列的防火牆和 proxy。
  
- Barracuda-Web 應用程式防火牆 (W3C)  
- 藍色外覆 Proxy 個儲存-存取記錄檔 (W3C)
- 檢查點
- Cisco ASA 防火牆 （請確定資訊層級設為 6）
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
- McAfee 安全 Web 閘道
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo 琴奧圖數列防火牆
- Sonicwall (先前稱為 Dell)   
- Sophos 個儲存
- Sophos XG
- Sophos Cyberoam
- Squid （普遍）
- Squid （原生）
- Websense-Web 安全性解決方案-調查的詳細資料報告 (CSV)
- Websense-Web 安全性解決方案-網際網路活動記錄檔 (CEF)
- Zscaler
    
> [!NOTE]
> 如果您想要使用的資料來源不是包含在這裡，您可以要求就會加入至應用程式探索。 若要這麼做，請建立報告時，選取**其他****資料**來源。 然後輸入您想要上傳的資料來源的名稱。 我們將檢閱記錄檔，並可讓您知道如果我們新增該記錄類型的支援。 或者，您可以[定義自訂剖析器](https://docs.microsoft.com/cloud-app-security/custom-log-parser)符合您的格式。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>疑難排解時記錄檔上傳錯誤

上傳 web 流量記錄檔之後，請檢查控管記錄檔若要查看是否發生任何錯誤。 如果有錯誤，請使用下表中的資訊，若要解決這些錯誤。
  
|**Error**|**描述**|**解決方案**|
|:-----|:-----|:-----|
|不支援的檔案類型  <br/> |上傳的檔案不是有效的記錄檔。 例如，圖像檔案。  <br/> |上傳的文字、 zip 或 gzip 直接從您的防火牆或 proxy 匯出的檔案。  <br/> |
|內部錯誤  <br/> |偵測到內部資源失敗。  <br/> |按一下 [重新執行工作的 [**重試**]。  <br/> |
|記錄檔格式不符合  <br/> |您上傳記錄格式不符合此資料來源的預期的記錄檔格式。  <br/> |
確認記錄檔未損毀。 比較，且符合要顯示在 [上傳] 頁面的範例格式的記錄檔案格式。 |
|異動已超過 90 天  <br/> |所有交易超過 90 天，因此會被略過。  <br/> |匯出的最近事件的新記錄檔，並重新上傳。  <br/> |
|沒有交易在目錄中的雲端應用程式  <br/> |沒有任何可辨識的雲端應用程式的交易記錄檔中找到。  <br/> |確認記錄檔包含的輸出流量資訊。  <br/> |
|不支援的記錄類型  <br/> |當您選取 [**的資料來源 = 其他 （不支援）**，無法剖析記錄檔。 相反地，它會傳送給[Microsoft Cloud App Security](https://aka.ms/whatiscas)技術團隊的檢閱。  <br/> |[Microsoft Cloud App Security](https://aka.ms/whatiscas)技術小組會建置專用的剖析器，每個資料來源。 已支援最常用的資料來源。 當不支援的資料來源上傳時，它會檢閱，並且新增至清單中的潛在的新資料來源剖析器。  <br/> 當新的剖析器加入功能時，通知隨附於 Microsoft Cloud App Security 版本資訊。  <br/> |
   
## <a name="next-steps"></a>後續步驟

- [檢閱並採取相應動作提醒](review-office-365-cas-alerts.md)
    
- [建立 app 探索報表](create-app-discovery-reports-in-ocas.md)
    
- [檢閱應用程式探索結果](review-app-discovery-findings-in-ocas.md)
    
- [Office 365 雲端 App 安全性，檢閱您的使用率活動](utilization-activities-for-ocas.md)
    

