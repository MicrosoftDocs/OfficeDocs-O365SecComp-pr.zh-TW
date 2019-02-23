---
title: 將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 輕鬆地識別設定之 IP 位址的實際辦公室 IP 位址，例如您將使用 Office 365 雲端應用程式安全性您可以設定群組的 IP 位址範圍。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220443"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
輕鬆地識別設定之 IP 位址的實際辦公室 IP 位址，例如您將使用 Office 365 雲端應用程式安全性您可以設定群組的 IP 位址範圍。定義這些範圍可讓您標記及分類 （英文），然後您可使用標記和自訂您的活動的記錄檔及提醒的類別會顯示與調查。
  
IP 範圍的每個群組可以標記使用您選擇，然後將標記可以會歸類根據 IP 類別 （例如 Corporate、 系統管理、 Risky、 和 VPN） 的預設清單的標籤名稱。支援 IPv4 和 IPv6 位址。
  
> [!NOTE]
> 您必須是執行本文中的程序的全域管理員或安全性管理員。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>若要設定 IP 位址範圍新增 Office 365 雲端應用程式安全性

1. 以全域管理員或安全性管理員中，移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。
    
2. 在右上角] 頁面上，按一下 [**設定** \> **IP 位址範圍**。<br>![在 O365 雲端應用程式安全性]，選擇 [設定來存取您的系統和資料的設定](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. 按一下加號的格式類似於 [新增] 按鈕 ( **+**)。
    
4. 在 [**新的 IP 位址範圍**] 視窗中，指定下列值： 
    
|**欄位或清單**|**該怎麼辦**|
|:-----|:-----|
|**名稱** <br/> |使用此欄位來管理您的 IP 位址範圍與設定。（您將不會看到此值活動記錄檔中的）。  <br/> |
|**IP 位址範圍** <br/> |指定的範圍會使用網路首碼標記法 （也稱為 CIDR 表示法）。例如，192.168.1.0/27 包含值 192.168.1.0 透過 192.168.1.31 （含） 的範圍。  <br/> |
|**位置**和**登錄 ISP** <br/> |指定 IP 位址範圍的位置和網際網路服務提供者 (ISP)。這會覆寫公用欄位定義的地址，這是有用的情況下，例如 IP 位址是，會被視為公開在愛爾蘭但實際上是在美國  <br/> |
|**標籤** <br/> |使用標籤來命名您的 IP 位址的群組。（不同於 [名稱] 欄位中，您會看到標記活動記錄檔中。）輸入的單字或片語想要使用的標籤。您可以新增任意數量的標記為您想要為每個 IP 位址範圍。如果您已經設定標籤並想要新增此 IP 位址範圍，請從目前的標記顯示當您開始輸入的清單中選擇。  <br/> |
|**類別** <br/> | 將類別指派給您標記以方便辨識來自特定 IP 位址的活動。選擇 [從下列選項：<br/> **系統管理**所有您的系統管理員的 IP 位址。  <br/> **雲端提供者**您為雲端中的 proxy IP 位址。  <br/> **公司**所有的 IP 位址在內部網路、 您分公司、 和 Wi-fi 漫遊地址。  <br/> **risky**您考慮要 risky，例如可疑的 IP 位址您任何 IP 位址所見過去、 競爭者的網路中的 IP 位址等等。根據預設，Risky 類別包含兩個 IP 標記：**匿名 proxy**和**Tor** <br/> **VPN**您的遠端工作者使用任何 IP 位址。  <br/> |
   
7. 選擇 [**儲存**]。
    
設定您的 IP 位址範圍之後，請記住僅未來事件受到這些變更。
  
## <a name="next-steps"></a>後續步驟

- [活動原則及提醒](activity-policies-and-alerts.md)
    
- [異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [整合 SIEM server](integrate-your-siem-server-with-office-365-cas.md)
    
- [檢閱並對 Office 365 雲端 App 安全性中的警示採取動作](review-office-365-cas-alerts.md)
    

