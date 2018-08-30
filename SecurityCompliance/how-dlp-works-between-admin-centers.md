---
title: DLP 安全性之間的運作方式&amp;規範中心及 Exchange 系統管理中心
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解如何在 [安全性] 中的 DLP&amp;規範中心可以與 Exchange 系統管理中心的 DLP 和傳輸規則搭配使用。
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527030"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>DLP 安全性之間的運作方式&amp;規範中心及 Exchange 系統管理中心

在 Office 365 中，您可以建立兩個不同的管理中心中的資料遺失防護 (DLP) 原則：
  
- 在**安全性&amp;規範中心**，您可以建立單一 DLP 原則可協助保護 SharePoint、 OneDrive 及 Exchange 中的內容。請儘可能我們建議您建立的 DLP 原則。如需詳細資訊，請參閱[安全性 DLP&amp;規範中心](data-loss-prevention-policies.md)。
    
- 在**Exchange 系統管理中心**中，您可以建立 DLP 原則可協助保護只能在 Exchange 中的內容。此原則可以使用 Exchange 傳輸規則，所以有更多選項特定來處理郵件。如需詳細資訊，請參閱[在 Exchange 系統管理中心的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。
    
DLP 原則建立這些系統中心運作並排-本主題說明如何。
  
![安全性和規範中心 」 及 Exchange 系統管理中心中的 DLP 頁面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>如何安全性 DLP&amp;規範中心搭配 Exchange 系統管理中心的 DLP 和傳輸規則

在 [安全性] 中建立的 DLP 原則之後&amp;規範中心、 原則會部署至所有包含在原則中的位置。如果原則包含 Exchange Online，將原則那里已同步處理及完全以相同方式來建立在 Exchange 系統管理中心的 DLP 原則強制執行。 
  
如果您已在 Exchange 系統管理中心中建立 DLP 原則，這些原則會繼續運作並排您在 [安全性] 中建立的電子郵件的任何原則&amp;規範中心。但是請注意在 Exchange 系統管理中心中建立的規則優先採用。首先，處理所有 Exchange 傳輸規則和 DLP 規則的安全性的然後&amp;都處理規範中心。
  
這表示：
  
- Exchange 傳輸規則封鎖的郵件將不會取得安全性中建立的 DLP 規則掃描&amp;規範中心。
    
- 如果 Exchange 傳輸規則會修改訊息會使其符合 DLP 原則中安全性的方式&amp;規範中心-例如新增外部使用者-則 DLP 規則會偵測這並強制執行原則所需。
    
安全性附註使用"停止處理"巨集指令的 Exchange 傳輸規則不會影響 DLP 處理的規則而且&amp;規範中心-將仍處理它們。
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>原則提示安全性&amp;規範中心與 Exchange 系統管理中心的比較

原則提示可以搭配使用其中一個與 DLP 原則及郵件流程規則建立在 Exchange 系統管理中心，或在 [安全性] 中建立的 DLP 原則&amp;規範中心，但不可同時。這是因為這些原則會儲存在不同的位置，但只能從單一位置可繪製原則提示。
  
如果您已在 Exchange 系統管理中心，任何您在 [安全性設定的原則提示設定原則提示&amp;規範中心就不會出現在網路上的 Outlook 和 Outlook 2013 及更新版本直到您關閉在 Exchange 系統管理中心中的提示使用者。這可確保您目前的 Exchange 傳輸規則會繼續運作直到您選擇切換至 [安全性]&amp;規範中心。
  
請注意，雖然只從單一位置可繪製原則提示的電子郵件通知一律傳送，即使您使用 DLP 原則這兩種安全性&amp;規範中心及 Exchange 系統管理中心。
  

