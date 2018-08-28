---
title: Exchange Online Protection IP 位址
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: 下列的 Microsoft 資料中心 IP 位址所使用的 Microsoft Exchange Online Protection (EOP) 傳送電子郵件、 時接收電子郵件、 或 Exchange Online Protection 入口網站及管理服務。為了傳送和接收來自 EOP 的郵件或使用管理服務，請確定您的網路允許來自這些 IP 位址的連線。
ms.openlocfilehash: 853b64410969fcc2f3c9ef238d2e9f4a4bb36e7b
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230005"
---
# <a name="exchange-online-protection-ip-addresses"></a>Exchange Online Protection IP 位址

下列的 Microsoft 資料中心 IP 位址所使用的 Microsoft Exchange Online Protection (EOP) 傳送電子郵件、 時接收電子郵件、 或 Exchange Online Protection 入口網站及管理服務。為了傳送和接收來自 EOP 的郵件或使用管理服務，請確定您的網路允許來自這些 IP 位址的連線。
 
> [!NOTE]
> Microsoft 已開發 rest web 服務 IP 位址及 FQDN 此頁面上的項目。此新服務可協助您設定及更新例如防火牆及 proxy 伺服器的網路周邊裝置。您可以下載端點、 清單或特定變更的目前版本的清單。XML 文件、 RSS 摘要、 和 IP 位址及 FQDN 此頁面上的項目最後會取代此服務。若要嘗試取出這個新的服務，請移至[Web 服務](https://support.office.com/article/managing-office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#webservice)。 
 
## <a name="eop-ip-address-ranges"></a>EOP IP 位址範圍

||||
|:-----|:-----|:-----|
|**IPv4 位址範圍** <br/> |**IPv6 位址範圍** <br/> |
| 23.103.132.0/22 | 2a01:111:f400:7 c 00:: / 54 |
| 23.103.136.0/21 | 2a01:111:f400:fc00:: / 54 |
| 23.103.144.0/20 | 2a01:111:f403:: / 48 |
| 23.103.198.0/23 |  |
| 23.103.200.0/22 |  |
| 40.92.0.0/14 |  |
| 40.107.0.0/17 |  |
| 52.100.0.0/14 |  |
| 52.238.78.88/32 |  |
| 65.55.88.0/24 |  |
| 65.55.169.0/24 |  |
| 94.245.120.64/26 |  |
| 104.47.0.0/17 |  |
| 157.55.234.0/24 |  |
| 157.56.110.0/23 |  |
| 157.56.112.0/24 |  |
| 207.46.100.0/24 |  |
| 207.46.163.0/24 |  |
| 213.199.154.0/24 |  |
| 213.199.180.128/26 |  |
| 216.32.180.0/23 |  |
||||
 
> [!IMPORTANT]
> 這裡所提供的 IP 位址範圍僅適用於轉送到客戶連接器。IP 位址清單的變更極少，且會傳達事先。若要確認您的業務合作夥伴、 智慧主機，或透過服務的已發佈的 IP 位址的內部部署環境路由傳送的郵件，您必須設定正確連接器路由傳送至每個目的地。如需連接器的詳細資訊，請參閱[決定其連接器使用](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。 可以隨著時間變更本主題中的 IP 位址。記錄的所有 IP 位址已新增、 變更，或在過去一年中已被取代，請參閱[EOP IP 位址的變更通知](change-notification-for-eop-ip-addresses.md)。 
 
如需 Microsoft Office 365 所用之 IP 位址的詳細資訊，請參閱 [Office 365 URL 和 IP 位址範圍](https://go.microsoft.com/fwlink/p/?LinkId=324165)。
 
## <a name="ip-ranges-by-region"></a>依地區的 IP 範圍

Exchange Online Protection 路由郵件同時又不遵守我們客戶我們合約義務最有效率的方式。與此記住，以下 EOP 端點是目前的地區 IPv4 範圍 ； 清單不過，這些 IP 位址可能會換頁的通知，以支援容量及效率的 EOP 中的另一個函數不重新佈建。在郵件將這些事件流程仍根據我們合約責任，我們將有所變更之後，及時更新端點這個清單來進行我們適合。這次我們不的 Office 365 的其他部分維持區域的端點清單。
 
||||
|:-----|:-----|:-----|
|**美洲地區** <br/> |**EMEA** <br/> |**APAC** <br/> |
| 23.103.132.0/22 | 23.103.132.0/22 |23.103.136.0/21 |
| 23.103.136.0/21 | 23.103.144.0/22 |23.103.152.0/22 |
| 23.103.148.0/22 | 40.92.0.0/18 |40.92.128.0/17 |
| 23.103.152.0/21 | 40.93.0.0/18 |40.93.128.0/17 |
| 23.103.156.0/22 | 40.94.0.0/18 |40.94.128.0/17 |
| 23.103.198.0/24 | 40.95.0.0/18 |40.95.128.0/17 |
| 23.103.200.0/22 | 40.107.0.0/18 |52.100.128.0/17 |
| 40.92.64.0/18 | 52.100.0.0/18 |52.101.128.0/17 |
| 40.93.64.0/18 | 52.101.0.0/18 |52.102.128.0/17 |
| 40.94.64.0/18 | 52.102.0.0/18 |52.103.128.0/17 |
| 40.95.64.0/18 | 52.103.0.0/18 |65.55.88.0/24 |
| 40.107.64.0/18 | 94.245.120.64/27 |104.47.64.0/18 |
| 52.100.64.0/18 | 104.47.0.0/19 |2a01:111:f400:7 c 00:: / 54 |
| 52.101.64.0/18 | 157.55.234.0/24 |  |
| 52.102.64.0/18 | 157.56.112.0/24 | |
| 52.103.64.0/18 | 213.199.154.0/24 | |
| 65.55.169.0/24 | 213.199.180.128/26 | |
| 104.47.32.0/19 | 2a01:111:f400:7e00:: / 56 | |
| 157.56.110.0/23 | 2a01:111:f400:fe00:: / 56 | |
| 207.46.100.0/24 |  | |
| 207.46.163.0/24 |  | |
| 216.32.180.0/23 |  | |
| 2a01:111:f400:7 c 00:: / 54 |  | |
||||

