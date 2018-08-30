---
title: Office 365 進階電子文件探索中的標記與相關性訓練
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: '了解標記的步驟，然後與訓練樣本的 40 檔案搭配使用 Office 365 進階 eDiscovery 相關性訓練階段。  '
ms.openlocfilehash: 90272452c8c1317957e542eba07bc43722f9c0e9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526788"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a>Office 365 進階電子文件探索中的標記與相關性訓練

> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主題說明使用進階的 eDiscovery 相關性訓練單元的程序。 
  
評估完成進階 eDiscovery 中與您輸入的相關性訓練階段後，40 檔案的訓練範例是帶入標記 [標籤] 索引標籤。 
  
## <a name="performing-relevance-training"></a>執行相關性訓練

1. 在**相關性\>標籤**] 索引標籤，[標記] 窗格中顯示作者的左的窗格和檔案會顯示在範例中的預設值、 標記一次一個。 
    
    ![相關性標籤面板](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    在 [**標籤**] 索引標籤會顯示檔案的顯示名稱。這可能是路徑、 電子郵件主旨、 標題或使用者定義的名稱。以滑鼠右鍵按一下檔案的路徑可以複製識別碼、 檔案路徑或文字路徑。 
    
    標記檔案範例數 （在左邊窗格的最頂端）、 目前顯示的檔案不在 （右窗格的底端），此範例中的總檔案的數目及目前總數 （t 底部的範例中的標記檔案的統計資料顯示 [**標籤**] 索引標籤會靠左窗格）、 其變更為您標記檔案。這適用於任何相關性標記完成，評估、 訓練、 Catch-up，或測試。 
    
    在 [檔案] 檢視中的列上方檔案顯示圖示表示註解、 標記和系列檔案存在。
    
2. 決定檔案的相關性案件問題和標記檔案使用 [標記] 選項圖示按鈕或鍵盤快速鍵，如下表所示：
    
| |
|**標記] 選項**|**描述**|**鍵盤快速鍵**|**多個問題-大量標籤鍵盤快速鍵**|
|:-----|:-----|:-----|:-----|
|R  <br/> |相關  <br/> |Z  <br/> |Shift + Z  <br/> |
|編號  <br/> |不相關  <br/> |X  <br/> |Shift + X  <br/> |
|略過  <br/> |略過  <br/> |C  <br/> |Shift + A  <br/> |
   
  - 當多個問題後標記一個問題存在檔案選取項目移至下一個問題 （如果有的話）。 
    
  - 反白顯示關鍵字時由系統管理員或案例的管理員定義的關鍵字 (相關性安裝\>醒目提示的關鍵字)，將會顯示 （在指定的色彩） 來協助識別同時標記相關的檔案。如果關鍵字都有雙底線，可以按下顯示的關鍵字描述的工具提示。 
    
    （選用) 在 [**標籤**] 索引標籤按一下 [**標記設定**來設定下列選項： 
    
    ![相關性標籤設定](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **大量 tag**： 使用此選項可以選取 [**全部**設定選取的檔案的所有問題 （覆寫已標記問題） 的標籤或選取 [將剩餘的無標記問題套用標記的**其餘部分**指派多個問題的檔案。所選取的選項會維持作用中的這個使用者的情況下直到變更該使用者的所有 （設定為每位使用者的所有使用者的情況下）。 
    
  - **自動標記**： 選取此核取方塊設定為 Not 的其他問題的檔案相關之後單一相關標記。
    
  - **自動換頁**： 選取此核取方塊將顯示的檔案選取項目移至下一個檔案時標記的最後一筆或僅無標記的問題。 
    
    跳過的檔案不會被視為相關性訓練與計分用途的相關性。
    
3. 任意文字註解相關聯的檔案，可以檢視及編輯透過在左的窗格中的下拉式清單中的 [**註解**] 選項。（選用） 
    
4. 可以檢視標記的指導方針的左的窗格下拉式清單中選取 [**標記準則**] 選項。 
    
5. 在完成 [標記] 清單中的所有檔案並準備好可計算結果之後，按一下 [**計算**]。會顯示 [**追蹤**] 索引標籤。 
    
## <a name="working-with-the-sample-files-list"></a>使用範例檔案清單

範例檔案清單可讓您檢視訓練範例中的檔案清單以及一或多個檔案上執行各種巨集指令。在 [**相關性** \> **標籤**] 索引標籤，**範例檔案**左邊的窗格會顯示範例檔案處理評估、 訓練、 Catch-up、 與不一致的程序的清單。 
  
1. 在**相關性\>標籤**] 索引標籤中選取左的窗格下拉式清單中的範例檔案。在左窗格中列出的範例檔案。 
    
    ![相關性標籤範例檔案清單](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. 輸入或選取其 [**範例**或**檔案**] 方塊中所選取的特定範例或檔案數字。 
    
  -   - 檔案序號會列在左欄的**標籤**] 索引標籤上顯示的檔案清單。按一下標題，將檔案的原始顯示的順序會傳回其原始的順序。 
    
  - 按一下 [檔案] 列上的 [在右窗格中顯示其內容。
    
  - 瀏覽之間使用較低的功能表列選項的目前範例中的檔案。此外，瀏覽的鍵盤快速鍵可用：
    
    若要瀏覽範例中的第一個檔案： Shift + Ctrl +\<
    
    若要瀏覽至 [範例中的前一個檔案： Shift +\<
    
    若要瀏覽範例中的下一個檔案： Shift +\>
    
    若要瀏覽至最後一個範例中的檔案： Shift + Ctrl +\>
    
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解評估的相關性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記及評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定所得的結果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

