---
title: 在高級 eDiscovery 中設定智慧標籤
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 智慧標籤可讓您在閱讀高級 eDiscovery 案例中的內容時套用機器學習功能。 使用智慧標籤群組來顯示機器學習偵測模型的結果, 例如「律師-用戶端」許可權模型。
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703826"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>在高級 eDiscovery 中設定智慧標籤

Advanced eDiscovery 中的機器學習 (ML) 功能, 可協助您在審閱集中檢查案例檔時, 讓決策程式更有效率。 智慧標籤是在記錄決策時所要採用的 ML 功能: 在審閱期間為檔加上標籤。 當您建立智慧標籤群組時, 如果您與智慧標籤群組相關聯的 ML 模型產生的決策, 就會與標記群組中的標籤一起顯示。 當您檢查特定檔時, 這有助於將 ML 結果資訊即時顯示。

## <a name="how-to-set-up-a-smart-tag-group"></a>如何設定智慧標籤群組

1. 在 [審閱集] 中, 按一下 [**管理審閱集**], 然後按一下 [**管理標記**]。

2. 按一下 [**新增標記群組**], 然後選取 [**新增智慧標籤群組**]。

3. 選取您想要與標籤群組建立關聯的 ML 模型。
    
   這會建立標記群組和*N*子標記, 其中*N*是模型的可能輸出數目。 例如, 「[律師-用戶端」的許可權偵測模型](attorney-privilege-detection.md)有兩個可能的輸出: 

   - **正值**–用於標記包含律師費-用戶端許可權內容的檔。
   
   - **負值**–用來標記不含律師費-用戶端許可權內容的檔。
    
    如果您選取此模型, 就會建立含有兩個子標記的標籤群組 (一個名為**正值**的子標記, 另一個名為**負數**) 做為審閱集。 在此範例中, 每個子標籤都對應至「律師-用戶端」許可權偵測模型的其中一個可能輸出。

4. 您可以選擇性地重新命名標記群組和子標記。 例如, 您可以將**正值**標籤重新命名為 [**特權**], 而 [**負**] 標記則不會有任何**許可權**。

## <a name="how-to-use-smart-tags"></a>如何使用智慧標籤

審閱檔時, 會在適當的子標記旁顯示模型的結果。 例如, 如果您有一個適用于律師-用戶端許可權偵測的智慧標籤群組, 並查看可能有許可權的檔, 則結論的原因會顯示在適當的標記旁。 請務必注意, 標記不會自動套用至檔。 檢閱者會決定如何標記檔。