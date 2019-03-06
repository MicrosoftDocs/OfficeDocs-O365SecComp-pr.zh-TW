---
title: DLP 如何安全性 & 規範中心和 Exchange 系統管理中心之間工作
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解 DLP 安全性 & 合規性中心與 DLP 的運作方式，以及郵件流程規則 （傳輸規則） 中 Exchange 系統管理中心。
ms.openlocfilehash: 512d9e4c9d3181cbaec2d58faac4f95f649b78c8
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410678"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>DLP 如何安全性 & 規範中心和 Exchange 系統管理中心之間工作

在 Office 365 中，您可以建立兩個不同的系統管理中心中的資料遺失防護 (DLP) 原則：
  
- 在**安全性 & 合規性中心**中，您可以建立一個 DLP 原則來協助保護 SharePoint、 OneDrive 及 Exchange 中的內容。 可能的話，我們建議您建立的 DLP 原則。 如需詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的 DLP。
    
- 在**Exchange 系統管理中心**中，您可以建立 DLP 原則來協助保護只能在 Exchange 中的內容。 此原則可以使用 Exchange 郵件流程規則 （也稱為傳輸規則），使其具有更多選項特定處理電子郵件。 如需詳細資訊，請參閱 <<c0>在 Exchange 系統管理中心中的 DLP。
    
DLP 原則建立這些系統管理員中心運作並排-本主題說明如何。
  
![在安全性與規範中心和 Exchange 系統管理中心中的 DLP 頁面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>DLP 安全性 & 合規性中心與 Exchange 系統管理中心中的 DLP 和郵件流程規則的運作方式

安全性 & 合規性中心中建立 DLP 原則之後，原則會部署至所有包含的原則中的位置。 如果原則包含 Exchange Online 時，此原則便那里同步處理，並強制執行完全相同的方式與在 Exchange 系統管理中心中建立的 DLP 原則中。 
  
如果您已在 Exchange 系統管理中心中建立 DLP 原則，這些原則會繼續運作並排任何您建立安全性 & 合規性中心中的電子郵件的原則。 但是請注意，在 Exchange 系統管理中心中建立的規則優先順序。 所有的 Exchange 郵件流程規則會先處理，並接著處理從安全性 & 合規性中心的 DLP 規則。
  
這表示：
  
- Exchange 郵件流程規則封鎖的郵件不會取得安全性 & 合規性中心中建立的 DLP 規則所掃描。
    
- Exchange 郵件流程規則會修改郵件的方式，會使其符合安全性 & 合規性中心中的 DLP 原則-例如新增外部使用者-如果然後 DLP 規則會偵測這，並視需要強制執行原則。
    
也請注意，使用 「 停止處理 「 巨集指令的 Exchange 郵件流程規則不會影響安全性 & 合規性中心中的 DLP 規則處理-將仍處理它們。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>在 Exchange 系統管理中心與安全性 & 合規性中心中的原則提示

在 Exchange 系統管理中心中，建立郵件流程規則與 DLP 原則或安全性 & 合規性中心，但不能兩者同時建立的 DLP 原則，可以使用原則提示。 這是因為這些原則會儲存在不同的位置，但只能從單一位置繪製原則提示。
  
如果您已在 Exchange 系統管理中心中設定原則提示，您在合規性中心不會出現在 web 和 Outlook 2013 和更新版本直到您在 Outlook 中的使用者安全性 & 中設定任何原則提示就會關閉 Exchange 系統管理中心中的提示。 這可確保您目前的 Exchange 郵件流程規則會繼續處理之前，您選擇要切換至安全性 & 合規性中心。
  
請注意，雖然原則提示可以只從單一位置繪製，電子郵件通知一律傳送，即使您使用安全性 & 規範中心和 Exchange 系統管理中心中的 DLP 原則。
  

