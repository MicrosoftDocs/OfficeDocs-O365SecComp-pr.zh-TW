---
title: 在 Office 365 進階電子文件探索中設定分析選項
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '請檢閱步驟來設定 Office 365 進階 eDiscovery，包括接近重複項目、 電子郵件執行緒及佈景主題中的分析程序的選項。  '
ms.openlocfilehash: 12bbe4043803c165a58adac80b72d03afd48adc7
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218223"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中設定分析選項

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在 [進階 eDiscovery 設定在執行分析的 [分析] 選項。
  
## <a name="set-analyze-options"></a>設定分析選項

開啟**準備\>分析** \> **安裝程式**。下列視窗會隨即顯示。
  
![設定分析選項](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **接近重複項目及電子郵件執行緒**如果您想要執行分析] 核取此方塊。預設會選取它。 
  
 **文件相似性**輸入 Near 重複的臨界值或接受預設值是 65%。 
  
 **佈景主題**核取此方塊可處理所有檔案並將佈景主題指派給他們。根據預設，不會選取此核取方塊。如果您想要執行處理的佈景主題中輸入下列選項。
  
- **佈景主題的最大數目**輸入或選取 [建立佈景主題數目的值。預設值為 200。 
    
    > [!NOTE]
    > 增加的佈景主題數目會影響效能，如一般化佈景主題的能力。佈景主題數目較高、 更細微它們。例如，如果 50 佈景主題的一組包含如"籃球、 Spurs、 Clippers、 Lakers"； 將佈景主題300 佈景主題可能會包含不同的佈景主題："Spurs"，"Clippers"，"Lakers"。如果您有無佈景主題的認知"籃球"並使用 ECA 這項功能，看不到佈景主題 」 籃球 」 可能是很有用。但是，如果處理有太多的佈景主題，您可能會永遠不會看到的字"籃球"並可能不知道該 Spurs 和 Clippers 是很好的籃球佈景主題可供檢閱，而不是移入的項目會開機並用於字形。 
  
- **建議佈景主題**您可以建議來控制處理的佈景主題的佈景主題文字。進階的 eDiscovery 將重心在這些建議的字詞與嘗試建立一或多個相關的佈景主題，根據"最高的佈景主題數目 」 設定。 
    
    例如，若建議的單字"computer"，且您指定作為"佈景主題的最大數目""2"，進階的 eDiscovery 會嘗試產生兩個單字"computer"與相關的佈景主題。佈景主題的兩個可能會是"電腦軟體"和"電腦 hardware"，例如。 
    
    ![新增建議的佈景主題](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 若要檢視、 新增或編輯建議的佈景主題，按一下 [**修改**]。
    
2. 在 [**建議追蹤佈景主題**] 面板中，按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)新增佈景主題的圖示。在 [**新增建議佈景主題**] 面板中，新增以逗號分隔的文字。 
    
3. 在**佈景主題數目**] 中選取一個值來決定進階的 eDiscovery 會嘗試將產生的 （預設值為 1 佈景主題套用） 這些字詞的佈景主題數目。
    
4. 按一下 [**儲存**]，然後關閉 [] 對話方塊。 
    
    > [!NOTE]
    > 佈景主題的總數包含建議的佈景主題。總建議的佈景主題不能超過總佈景主題。如果有許多的建議的佈景主題，相對於總佈景主題，只有幾個"小說"佈景主題會偵測出系統因為大部分的佈景主題將專用於建議的佈景主題。 
  
- **模式**從下拉式清單中選取**佈景主題**選項： 
    
  - **建立並套用模型**： 計算的模型檔案的線段的佈景主題，然後將它們之間的檔案。
    
  - **建立模型**： 從檔案的線段的佈景主題模型來計算。套用處理所得的餘數檔案已完成另外另一次。
    
  - **套用模型**： 此選項只會顯示是否先前建立及尚未套用模型。這會劃分為基礎的佈景主題檔案。
    
您也可以[設定搜尋時忽略的文字](set-ignore-text-in-advanced-ediscovery.md)，並[將分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)的分析。 
  
您已設定這些選項之後，按一下 [**分析**執行]。[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)的顯示。 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)

