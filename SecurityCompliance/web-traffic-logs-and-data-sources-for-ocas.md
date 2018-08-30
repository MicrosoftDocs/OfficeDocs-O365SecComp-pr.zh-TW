---
title: Office 365 雲端 App 安全性的網路流量記錄與資料來源
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 雲端應用程式安全性適用於從各種提供者的網頁流量記錄。閱讀本篇文章以深入了解網頁流量記錄和支援的 Office 365 雲端應用程式安全性的資料來源。
ms.openlocfilehash: 09b0358e0d8b9a6ed59393d8771237f7eaf8bb98
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526848"
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
  
下表列出的需求及您可正常使用 Office 365 雲端應用程式安全性的網頁流量記錄所需的屬性：
  
|**屬性**|**其他需求 **|
|:-----|:-----|
| 異動的日期  <br/>  來源 IP  <br/>  來源使用者 （建議）  <br/>  目的地 IP 位址  <br/>  目的地 URL (建議使用： Url 提供的雲端應用程式偵測較高的正確性比 IP 位址)  <br/>  總 （建議使用） 的資料量  <br/>  數量上傳或下載的資料 (建議使用： 提供關於雲端前瞻應用程式的使用模式)  <br/>  （允許或封鎖） 所採取的動作  <br/> | 必須支援的記錄檔的資料來源。  <br/>  使用記錄檔的格式必須符合標準格式。當檔案上傳時、 應用程式探索會確認此。  <br/>  事件記錄檔中的必須發生不得超過 90 天以上。  <br/>  記錄檔必須包含可以分析的網路活動的輸出流量資訊。  <br/> |
   
如果屬性不會載入的記錄檔中包含，Office 365 雲端應用程式安全性無法顯示或分析您的資訊。例如，Cisco ASA 防火牆的標準記錄格式不包含每個交易、 username 或目標 URL (僅限目標 IP) 上傳位元組數量。由於這項資訊不是 Cisco 記錄檔中，Office 365 雲端應用程式安全性將不會包含它時分析您的組織的網路流量。
  
> [!NOTE]
> 某些類型的防火牆，您必須設定的資訊層級的網頁流量記錄檔放到包含必要的屬性。例如，Cisco ASA 防火牆資訊層級必須設為 6。請務必確認組織防火牆已設為您的網頁流量記錄檔中傳遞正確的資訊。 
  
## <a name="data-attributes-for-different-vendors"></a>不同的廠商資料屬性
<a name="BKMK_LogAndData"> </a>

下表摘要說明從不同的廠商的網頁流量記錄檔中的資訊。**請務必洽詢您的廠商的最新資訊。**
  
|**資料來源**|**目標應用程式 URL**|**目標應用程式 IP**|**Username**|**來源 IP**|**總流量**|**上傳的位元組**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Barracuda  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |無  <br/> |否  <br/> |
|藍色外覆  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|檢查點  <br/> |否  <br/> |**是** <br/> |無  <br/> |**是** <br/> |無  <br/> |否  <br/> |
|Cisco ASA  <br/> |否  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |無  <br/> |
|Cisco FWSM  <br/> |否  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |無  <br/> |
|Cisco Ironport WSA  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Cisco Meraki  <br/> |**是** <br/> |**是** <br/> |無  <br/> |**是** <br/> |無  <br/> |否  <br/> |
|Clavister NGFW (Syslog)  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Dell SonicWall  <br/> |**是** <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Fortigate  <br/> |否  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Juniper SRX  <br/> |否  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Juniper SSG  <br/> |否  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|McAfee SWG  <br/> |**是** <br/> |無  <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Meraki (Cisco)  <br/> |**是** <br/> |**是** <br/> |無  <br/> |**是** <br/> |無  <br/> |否  <br/> |
|Microsoft Threat Management Gateway  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Palo Alto 網路  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Sophos  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |無  <br/> |
|Squid （一般）  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |無  <br/> |**是** <br/> |
|Squid （原生）  <br/> |**是** <br/> |無  <br/> |**是** <br/> |**是** <br/> |無  <br/> |**是** <br/> |
|Websense-調查的詳細資料報告 (CSV)  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Websense-網際網路活動記錄檔 (CEF)  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Zscaler  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>支援的廠商防火牆及 proxy
<a name="BKMK_Supported"> </a>

Office 365 雲端應用程式安全性支援下列防火牆及 proxy。
  
- Barracuda-Web 應用程式防火牆 (W3C)
    
- 藍色外覆 Proxy 個儲存-存取記錄檔 (W3C)
    
- 檢查點
    
- Cisco ASA 防火牆 （請注意您必須設定的資訊層級為 6）
    
- Cisco IronPort WSA
    
- Cisco ScanSafe
    
- Cisco Merkai-Url 記錄檔
    
- Dell Sonicwall
    
- Fortinet Fortigate
    
- Juniper SRX
    
- Juniper SSG
    
- McAfee 安全網路閘道
    
- Microsoft Forefront Threat Management Gateway (W3C)
    
- Palo Alto 數列防火牆
    
- Sophos 個儲存
    
- Sophos Cyberoam
    
- Squid （一般）
    
- Squid （原生）
    
- Websense-Web 安全性解決方案-調查的詳細資料報告 (CSV)
    
- Websense-Web 安全性解決方案-網際網路活動記錄檔 (CEF)
    
- Zscaler
    
> [!NOTE]
> 如果您想要使用的資料來源此處不包含在內，您可以要求它要新增至應用程式探索。若要這樣做，當您建立報表時，選取**其他****資料**來源。然後輸入您嘗試將上傳的資料來源的名稱。我們將檢閱記錄檔，並且可讓您知道若我們要新增的記錄類型的支援。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>疑難排解記錄檔上傳時的錯誤

上傳 web 流量記錄檔之後，請檢查控管記錄檔以查看 [是否未發生任何錯誤。如果沒有錯誤，使用下表中的資訊來解決這些錯誤。
  
|**錯誤**|**描述**|**解決方案**|
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
    

