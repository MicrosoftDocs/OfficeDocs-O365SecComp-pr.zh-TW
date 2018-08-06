---
title: 大量抱怨層級值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
description: 大量此刻會傳送模式、 內容建立和清單取得作法而有所不同。有些是很好的大量此刻傳送想要其訂閱者的相關內容的郵件。這些訊息產生一些客訴由收件者。其他大量此刻來路不明的傳送訊息密切類似垃圾郵件和收件者從產生許多客訴。為了區別這些類型的大量此刻，來自大量此刻郵件指派給大量抱怨層級 (BCL) 評等。產生客訴是 BCL 評等介於 1 到 9 根據方式可能大量郵件處理程式而定。具有分級 BCL 9 的寄件者是 BCL 3 的分級則是可能性來產生許多客訴可能產生許多客訴從收件者]。Microsoft 識別大宗郵件，並決定適當的 BCL 使用內部及協力廠商的來源。此評等會公開在 X-Microsoft 反垃圾郵件標頭中的每封郵件。如需此郵件標頭的詳細資訊，請參閱反垃圾郵件郵件標頭。
ms.openlocfilehash: adf179ba4a309f2ed22275179013b576888960c6
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026260"
---
# <a name="bulk-complaint-level-values"></a>大量抱怨層級值

大量此刻會傳送模式、 內容建立和清單取得作法而有所不同。有些是很好的大量此刻傳送想要其訂閱者的相關內容的郵件。這些訊息產生一些客訴由收件者。其他大量此刻來路不明的傳送訊息密切類似垃圾郵件和收件者從產生許多客訴。為了區別這些類型的大量此刻，來自大量此刻郵件指派給大量抱怨層級 (BCL) 評等。產生客訴是 BCL 評等介於 1 到 9 根據方式可能大量郵件處理程式而定。具有分級 BCL 9 的寄件者是 BCL 3 的分級則是可能性來產生許多客訴可能產生許多客訴從收件者]。Microsoft 識別大宗郵件，並決定適當的 BCL 使用內部及協力廠商的來源。此評等會公開在**X-Microsoft 反垃圾郵件**標頭中的每封郵件。如需此郵件標頭的詳細資訊，請參閱[反垃圾郵件郵件標頭](anti-spam-message-headers.md)。 
  
您可以使用 BCL 值來設定所需的層級大量篩選您的組織需要遵循[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)中的步驟。
  
更多 BCL 值新增，且會包含以下未來。下表列出並說明目前正在使用中的 BCL 值。
  
|||
|:-----|:-----|
|**BCL 值** <br/> |**描述** <br/> |
|0  <br/> |郵件不是從大量寄件者。  <br/> |
|1，2 3  <br/> |郵件是從產生一些客訴大量寄件者。  <br/> |
|4、 5、 6、 7  <br/> |郵件是來自大量寄件者所產生的抱怨混合數字。  <br/> |
|8、 9  <br/> |郵件是來自大量寄件者所產生的抱怨高數量  <br/> |
   

