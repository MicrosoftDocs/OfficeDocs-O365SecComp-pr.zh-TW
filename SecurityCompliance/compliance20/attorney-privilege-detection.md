---
title: 設定律師-委託人進階電子文件中的權限偵測
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
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
ms.openlocfilehash: 6838203a500a4fe600d8186a4b848beed0730665
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835063"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a>設定進階電子文件中的設定律師-委託人權限偵測 （預覽）

任何探索程序的檢閱部分主要且愈長寬檢閱特殊權限的內容。 進階電子文件提供 AI 型偵測您的案例中的特殊權限內容，讓您能進行此程序更有效率。 此功能目前是 beta，eDiscovery 系統管理員已加入至使用該功能。

## <a name="how-does-it-work"></a>它如何運作？

使用功能開啟，當您分析案例中設定檢閱，透過律師-委託人權限偵測模型執行的所有文件。 模型會查看兩件事：

- 內容： ML 模型會決定要在本質法律文件的內容的可能性。

- 參與者： 律師租用戶的使用者上傳清單時，該模型比較至判斷文件是否有至少一個律師參與者清單對文件的參與者。
模型會輸出每個文件，這些元件會檢閱集合內的可搜尋的三個值：

- 內容分數： 正在性質中法律文件的可能性 （介於 0 和 1 之間的分數）

- 具有律師： True 是表示如果參與者中找到其中一個 [上傳的律師] 清單中，則為 false 否則或者沒有任何律師清單。

-  可能特殊權限： True 是表示如果內容分數超出臨界值，或具有律師參與者，則為 false 否則。

## <a name="opting-into-attorney-client-privilege-detection"></a>設定律師-委託人權限偵測到選擇

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a>步驟 1： 選擇加入到律師-委託人權限偵測 (eDiscovery 系統管理員)

設定律師-委託人權限偵測時的預覽功能，因為您 eDiscovery 系統管理員必須選擇要讓此功能可在您的情況下。

- 移至 「 設定實驗功能 」 的進階電子文件] 頁面

- 按一下 「 管理律師-委託人特權偵測 」。

- 按一下切換以開啟該功能。

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>步驟 2： 上傳律師 （選用） 的清單

為了充分利用律師-委託人權限偵測我們建議您為公司提供的電子郵件地址律師或合法的人物代表工作清單。 清單應該不標頭的 CSV，每行一個電子郵件地址。

## <a name="leveraging-attorney-client-privilege-detection"></a>利用律師-委託人權限偵測 

### <a name="step-1-analyze-a-review-set"></a>步驟 1： 分析檢閱設定

當您分析您檢閱設定時，也將會執行律師-委託人權限偵測。 若要深入了解分析檢閱集中的資料，請參閱[中檢閱設定進階 eDiscovery 中分析資料](analyzing-data-in-review-set.md)。

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>步驟 2： 建立律師-委託人權限偵測模型的智慧標籤群組

您可以使用律師-委託人權限偵測的結果檢閱程序中的主要方法是使用智慧標籤群組。 智慧標籤群組採取 ML 模型的結果，並顯示模型中內嵌標記旁的結果，讓您輕鬆地耗用模型的結果，其中相關，與檢閱程序中使用標記，如同任何其他標記您的標記面板中。

- 在 「 管理標籤 」 中，按一下 [在 「 新增智慧標籤區段 」。

- 選取 「 律師-委託人權限偵測 」。 您會看到的已建立標記群組和兩個標記，對應至在模型中的可能結果。

- 請重新命名標記群組和標記，視您檢閱。

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a>步驟 3： 使用 [智慧標籤] 群組的權限檢閱

當您檢閱文件中，如果模型已決定文件可能特殊權限時，對應的智慧標籤會公開結果：

- 如果文件有可能是法律性質的內容，對應的智慧標籤旁邊會出現 「 法律內容 」 標籤。

- 如果文件上傳的律師清單中找到的參與者，對應的智慧標籤旁邊會出現 「 律師 」 標籤。