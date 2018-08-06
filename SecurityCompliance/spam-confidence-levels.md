---
title: 垃圾郵件信賴等級
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: 當電子郵件訊息會通過垃圾郵件篩選其指派的垃圾郵件計分。該分數會對應到個別的垃圾郵件信賴等級 (SCL) 為與 X 標頭中加上戳記。服務採取動作時取決於的 scl 垃圾郵件信賴解譯的訊息。下表來篩選和預設採取的動作是針對每個評等的內送郵件上解譯不同 SCL 評等。
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026280"
---
# <a name="spam-confidence-levels"></a>垃圾郵件信賴等級

當電子郵件訊息會通過垃圾郵件篩選其指派的垃圾郵件計分。該分數會對應到個別的垃圾郵件信賴等級 (SCL) 為與 X 標頭中加上戳記。服務採取動作時取決於的 scl 垃圾郵件信賴解譯的訊息。下表來篩選和預設採取的動作是針對每個評等的內送郵件上解譯不同 SCL 評等。
  
|**Scl**|**垃圾郵件信賴解譯**|**將預設動作**|
|:-----|:-----|:-----|
|-1  <br/> |非垃圾郵件來自 [安全的寄件者、 安全的收件者或安全列出 IP 位址 （信任的合作夥伴）  <br/> |將郵件傳遞至收件者的收件匣。  <br/> |
|0、 1  <br/> |非垃圾郵件因為已掃描郵件，並決定要全新  <br/> |將郵件傳遞至收件者的收件匣。  <br/> |
|5、 6  <br/> | 垃圾郵件  <br/> |將郵件傳遞至收件者的垃圾郵件] 資料夾。  <br/> |
|7，8 9  <br/> |高度信賴垃圾郵件  <br/> |將郵件傳遞至收件者的垃圾郵件] 資料夾。  <br/> |
   
> [!TIP]
> 服務未設定 SCL 評等的 2、 3、 4、 7 和 8。5 或 6 的 scl 會被視為可疑的垃圾郵件，這是某些較不是比 scl 為 9、 會視為某些垃圾郵件的垃圾郵件。垃圾郵件和高信賴垃圾郵件的不同動作可以透過您在 Exchange 系統管理中心中的內容篩選原則設定。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。您也可以設定與特定條件相符使用傳輸規則[使用郵件流程規則將郵件中的垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)中所述的郵件的 scl。如果您使用的傳輸規則來設定 SCL 7、 8 或 9 的訊息會視為高信賴垃圾郵件。 
  
||
|:-----|
|![LinkedIn Learning 的短圖示](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。 |
   

