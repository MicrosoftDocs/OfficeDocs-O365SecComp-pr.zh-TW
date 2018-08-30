---
title: Office 365 進階電子文件探索中的測試相關性分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何使用 Office 365 進階在 eDiscovery 中的批次計算後的 [測試] 索引標籤來測試、 比較和驗證處理的整體品質。  '
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526772"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a>Office 365 進階電子文件探索中的測試相關性分析

> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
進階在 eDiscovery 中的 [測試] 索引標籤可讓您測試、 比較和驗證處理的整體品質。這些測試是批次計算後執行。由標記集合中的檔案、 專家進行最終的判斷關於是否已標記的每一個檔案實際案例相關。 
  
在單一與多問題的情況下，測試通常會執行每個問題。每個測試後可檢視結果並測試結果可以已修訂與指定之的範例測試檔案。
  
## <a name="testing-the-rest"></a>測試其餘部分

"測試 Rest"測試用來驗證挑選出決策，例如、 檢閱上方最後一個進階的 eDiscovery 結果為基礎的特定相關性截止分數的檔案。專家檢閱下用來評估在該集相關的檔案數目的選定截止分數檔案的範例。
  
這項測試會提供統計資料和檢閱設定及測試的比較 Rest 母體。檢閱一組的結果是指由相關性計算期間訓練。結果包含計算、 根據的設定與輸入的參數，例如：
  
- 測試範例的檔案數目的統計資料的範例及識別相關的檔案。 
    
- 檢閱設定與其餘部分，例如檔案數目的母體參數的表格式比較估計數目相關的檔案、 估計的豐富及尋找其他相關檔案的平均成本。成本設定可以由系統管理員設定的參數。
    
1. 開啟**相關性\>測試**] 索引標籤。 
    
2. 在 [**測試**] 索引標籤中按一下 [**新增測試**。**建立測試**] 對話方塊隨即出現，如下列範例所示。 
    
    ![相關性測試的其他結果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. **測試名稱**與**描述**] 中輸入名稱與描述。
    
4. 在 [**測試類型**] 清單中選取 [**測試其餘部分**
    
5. 在**問題 / 類別**清單中，選取問題名稱。 
    
6. 在**載入**] 清單中，選取負載。 
    
7. 在**讀取 %**、 接受預設值或選取截止相關性分數的值。 
    
8. 在**設定大小**，或接受預設值。請注意還原圖示會還原預設值。
    
9. 按一下 [**啟動標記**。產生測試範例。
    
10. 檢閱及標籤的檔案] 中的每個**相關性\>標籤**] 索引標籤和完成時，按一下 [**計算**。
    
11. 在 [測試] 索引標籤中，您可以按一下 [**檢視結果**查看測試結果。下圖顯示範例。 
    
    ![測試其他結果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
在如上圖**範例參數**] 區段中的表格包含標記的專家，範例中的檔案數目及相關的範例中找到的檔案數目的詳細資料。 
  
[**母體參數**] 區段中的表格包含的測試結果，包括檢閱組母體具有所選截止下方的分數檔案和"Rest"母群體的檔案與所選截止上方的分數。針對每個母群體，會顯示下列結果： 
  
- 包含具有讀取 %-所述的截止檔案
    
- 檔案總數 
    
- 估計的相關的檔案數目 
    
- 估計的豐富 
    
- 平均檢閱總成本的尋找其他相關檔案
    
## <a name="testing-the-slice"></a>測試扇形

「 測試扇形"測試執行測試類似"測試其餘"測試，但為檔案的區段設定相關性讀取 %所指定。
  
1. 開啟**相關性\>測試**] 索引標籤。 
    
2. 在 [**測試**] 索引標籤中按一下 [**新增測試**。**建立測試**對話方塊會顯示。 
    
3. **測試名稱**與**描述**] 中輸入資訊。
    
4. 在 [**測試類型**] 清單中選取 [**測試扇形**。
    
5. [**問題**] 清單中選取問題名稱。 
    
6. 在**載入**] 清單中，選取負載。 
    
7. **讀取 %之間**，接受預設低或高範圍值或選取值截止相關性分數。 
    
8. 在**設定大小**，請選取一個值或接受預設值。
    
    還原圖示會還原預設值。
    
9. 按一下 [**啟動標記**。產生測試範例。
    
10. 檢閱及標籤的檔案] 中的每個**相關性\>標籤**] 索引標籤和完成時，按一下 [**計算**。 
    
11. 在 [測試] 索引標籤中，您可以按一下 [**檢視結果**查看測試結果。 
    
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解評估的相關性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記及評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記及相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定所得的結果](decision-based-on-the-results-in-advanced-ediscovery.md)

