---
title: 大量抱怨層級值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 大量郵件寄件者在其傳送模式、 內容建立，與清單取得作法差異。 有些是很好的大量郵件寄件者傳送原本到其訂閱者的相關內容的郵件。 這些訊息會產生一些抱怨收件者。 其他大量郵件寄件者傳送仔細看起來像垃圾郵件和收件者產生許多抱怨的來路不明的郵件。 若要區分這些類型的大量郵件寄件者，來自大量郵件寄件者的郵件會指派大量抱怨層級 (BCL) 分級。 BCL 分級介於 1 到 9 根據方式可能會大量郵件寄件者是產生抱怨。 寄件者已分級為 BCL 9 是可能會從收件者產生許多抱怨，而分級為 BCL 3 不太可能會產生許多抱怨。 Microsoft 會使用內部和協力廠商來源，以找出大量郵件，並決定適當的 BCL。 此分級會公開在 X-Microsoft 反垃圾郵件標頭中的每一封郵件。 如需有關此訊息標頭的詳細資訊，請參閱 < 反垃圾郵件郵件標頭。
ms.openlocfilehash: e6d639098adc8c29b09b186ff72e38c5f5ac4e81
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243814"
---
# <a name="bulk-complaint-level-values"></a>大量抱怨層級值

大量郵件寄件者在其傳送模式、 內容建立，與清單取得作法差異。 有些是很好的大量郵件寄件者傳送原本到其訂閱者的相關內容的郵件。 這些訊息會產生一些抱怨收件者。 其他大量郵件寄件者傳送仔細看起來像垃圾郵件和收件者產生許多抱怨的來路不明的郵件。 若要區分這些類型的大量郵件寄件者，來自大量郵件寄件者的郵件會指派大量抱怨層級 (BCL) 分級。 BCL 分級介於 1 到 9 根據方式可能會大量郵件寄件者是產生抱怨。 寄件者已分級為 BCL 9 是可能會從收件者產生許多抱怨，而分級為 BCL 3 不太可能會產生許多抱怨。 Microsoft 會使用內部和協力廠商來源，以找出大量郵件，並決定適當的 BCL。 此分級會公開在**X-Microsoft 反垃圾郵件**標頭中的每一封郵件。 如需有關此訊息標頭的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。 
  
您可以使用 BCL 值來設定所需的層級，大量篩選您的組織需要遵循的步驟中[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。
  
多個 BCL 值新增，並將會包含以下在未來。 下表列出並說明目前正在使用中的 BCL 值。
  
|||
|:-----|:-----|
|**BCL 值** <br/> |**描述** <br/> |
|0  <br/> |郵件不是來自大量寄件者。  <br/> |
|1、 2、 3  <br/> |郵件是來自會產生一些抱怨大量寄件者。  <br/> |
|4、 5、 6、 7  <br/> |郵件是來自大量寄件者所產生的抱怨混合數字。  <br/> |
|8, 9  <br/> |郵件是來自會產生大量抱怨的大量寄件者  <br/> |
   

