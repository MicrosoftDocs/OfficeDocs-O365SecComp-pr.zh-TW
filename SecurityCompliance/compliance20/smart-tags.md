---
title: 設定律師-委託人權限偵測進階電子文件中的智慧標籤
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
description: ''
ms.openlocfilehash: 5310acad1aa1bc2e01cbabee69dd7bb38084bd9a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153965"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a>設定 ML 輔助檢閱進階電子文件中的智慧標籤

進階電子文件中的機器學習功能原本用意是為了讓文件上的決策程序更有效率。 智慧標籤是可將機器學習到的記錄決策的功能： 標記和標記群組。 當您建立的智慧標籤群組時，然後對應至群組 ML 模型的決策也會顯示在-線環繞，具有可協助您] 群組中的標記，請參閱在資訊中的列，它們依內容相關性成為最有意義。

## <a name="how-to-set-up-a-smart-tag-group"></a>如何設定的智慧標籤群組

1. 在 [檢閱設定，請移至**管理檢閱組** -> **管理標記**。

2. 按一下 [**新增標籤群組**旁的下拉式]，然後選取 [**新增智慧標籤群組**。

3. 選取您想要對應至這個群組的模型。 這會建立標籤] 區段中，N 子系標記，其中 N 是可能輸出模型的數目。 比方說，律師-委託人權限偵測模型有兩個可能的輸出的特殊權限和特殊權限;選取此模型會建立兩個的子系標記中檢閱設定，每個對應至下列其中一個可能的輸出。

4. 請重新命名標記群組和標記，請參閱填滿。

## <a name="how-to-use-a-smart-tag-group"></a>如何使用智慧標籤的群組

檢閱文件時, 模型的結果將會公開旁的適當的標籤值。 比方說，如果您有一個智慧標籤群組的設定律師-委託人權限偵測和您檢閱模型已決定文件可能特殊權限，您會看到的原因，適當的標籤旁。 請務必注意，不會自動套用標籤;如不管您的目的，標記內的智慧標籤群組法案就像一般的標記，不同之處在於公開模型的結果旁邊適當時機。