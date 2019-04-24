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
description: 輕鬆地找出您將您的實際辦公室 IP 位址，例如使用 Office 365 雲端 App 安全性中的 IP 位址設定您可以設定群組的 IP 位址範圍。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254854"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
輕鬆地找出您將您的實際辦公室 IP 位址，例如使用 Office 365 雲端 App 安全性中的 IP 位址設定您可以設定群組的 IP 位址範圍。 定義這些範圍可讓您標記，並加以分類，則您可以使用標記並顯示及調查來自訂您的活動的記錄檔及警示的類別。
  
每個群組的 IP 範圍可以與標記的名稱，您選擇，然後將標記可分類根據預設清單的 IP 類別 （例如 Corporate、 系統管理、 Risky 和 VPN） 標記。 支援 IPv4 和 IPv6 位址。
  
> [!NOTE]
> 您必須是全域系統管理員或安全性系統管理員才能執行本文中的程序。 若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>若要設定 Office 365 雲端 App 安全性中的 IP 位址範圍

1. 以全域管理員或安全性管理員中，移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。
    
2. 在右上角] 頁面上，按一下 [**設定** \> **IP 位址範圍**。<br>![在 O365 雲端 App 安全性中，選擇 [設定，以存取您的系統和資料設定](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. 按一下 [新增] 按鈕，這類似於加上加號 ( **+**)。
    
4. 在 [**新的 IP 位址範圍**] 視窗中，指定下列值： 
    
|**欄位或清單**|**要執行的動作**|
|:-----|:-----|
|**Name** <br/> |使用此欄位來管理您的 IP 位址範圍和設定。 （您無法看到此活動記錄檔中的值）。  <br/> |
|**IP 位址範圍** <br/> |指定的範圍，使用網路前置詞表示法 （也稱為 CIDR 標記法）。 例如，192.168.1.0/27 包含值 192.168.1.0 透過 192.168.1.31 （含） 之間的範圍。  <br/> |
|**位置**和**註冊 ISP** <br/> |指定的位置和網際網路服務提供者 (ISP) 的 IP 位址範圍。 這會覆寫公用的欄位定義的地址，這是很有用的情況下，例如 IP 位址是，會被視為公開在愛爾蘭，但實際上是在美國  <br/> |
|**標記** <br/> |使用標籤來命名您的 IP 位址的群組。 （不同於 [名稱] 欄位中，您會看到標記活動記錄檔中）。輸入單字或片語，您想要使用標籤。 您可以新增多個標記為您想針對每個 IP 位址範圍。 如果您已經設定標記，並想要加入這個 IP 位址範圍，請從目前的標記，開始輸入時的清單中選擇。  <br/> |
|**類別** <br/> | 將類別指派給您的標記若要更容易辨識來自特定 IP 位址的活動。 選擇 [從下列選項：  <br/> **系統管理**所有您系統管理員的 IP 位址。  <br/> **雲端提供者**您的 proxy 在雲端中的 IP 位址。  <br/> **公司**所有的 IP 位址在您的內部網路、 您的分支辦公室和 Wi-fi 漫遊地址。  <br/> **風險**您認為無法風險，例如可疑的 IP 位址您任何 IP 位址所見在過去，競爭對手網路中的 IP 位址等等。 根據預設，有風險的類別包含兩個 IP 標記：**匿名 proxy**和**Tor** <br/> **VPN**您的遠端工作者使用任何 IP 位址。  <br/> |
   
7. 選擇 [**儲存**]。
    
設定您的 IP 位址範圍之後，請記住，只有日後事件受到這些變更。
  
## <a name="next-steps"></a>後續步驟

- [活動原則和警訊](activity-policies-and-alerts.md)
    
- [異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [將 SIEM 伺服器整合](integrate-your-siem-server-with-office-365-cas.md)
    
- [檢閱並對 Office 365 雲端 App 安全性中的警示採取動作](review-office-365-cas-alerts.md)
    

