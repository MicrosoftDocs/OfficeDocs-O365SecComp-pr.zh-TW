---
title: 重試內容搜尋以解決錯誤的內容位置
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 重試] 按鈕可用於解決有內容位置錯誤的內容搜尋。
ms.openlocfilehash: 0fdc11593fec42e1f9f9b76fbbb408d9c16fd183
ms.sourcegitcommit: d5f841744b716fcf368c670009b61441f5a5eed2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2018
ms.locfileid: "27210180"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>重試內容搜尋以解決錯誤的內容位置

當您可以使用在 Office 365 安全性和規範中心] 中的內容搜尋來搜尋超大 （例如搜尋 100000 信箱或其他單一內容搜尋功能） 的信箱數目時，您可能會得到類似下列的搜尋錯誤：

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

這些錯誤 （錯誤代碼 CS008 009 和 CS012 002） 指出內容搜尋失敗來搜尋特定的內容位置 ；在此範例中未搜尋兩個信箱。這些錯誤會顯示在 [狀態的詳細資訊彈出式] 頁面上之內容的搜尋。

## <a name="cause-of-content-location-errors"></a>內容位置錯誤的原因

搜尋的信箱數目，搜尋會分散於數以千計之 Microsoft 資料中心中的伺服器。在任何時候的特定伺服器可能是在重新開機狀態或收件人容錯移轉備援副本的程序。在下列情況下擷取資料的內容的搜尋要求將會逾時。在上述範例中，錯誤失敗的信箱已搜尋逾時的結果。

## <a name="resolving-content-location-errors"></a>協助您解決內容位置錯誤

在不同伺服器上的類似錯誤通常會產生重新啟動搜尋。而不重新啟動搜尋，按一下 [搜尋結果頁面頂端會顯示 [**重試**] 按鈕。

![按一下 [重試] 按鈕以解決內容位置錯誤](media/retrycontentsearch3.png)

這會導致重試僅針對失敗的信箱搜尋。當您重試搜尋時，會保留已順利傳回的結果。

## <a name="tips-to-avoid-content-location-errors"></a>若要避免內容位置錯誤的秘訣

以下是一些除了原因的內容位置錯誤和一些秘訣可協助您搜尋大量信箱時加以避免。

- 所搜尋的信箱可能會因為使用者活動忙碌。在此例中的搜尋服務可能節流本身防止信箱變成無法使用。若要避免此問題，請嘗試執行搜尋期間非上班時間。

- 搜尋查詢可能會從信箱太多內容擷取。請儘可能嘗試使用關鍵字、 日期範圍和搜尋條件來縮小搜尋範圍。

- 太多的關鍵字或當您建立搜尋查詢使用的[關鍵字] 清單中](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)的關鍵字詞。當您執行搜尋查詢使用關鍵字] 清單中時，基本上執行服務的每一列的個別搜尋關鍵字清單中，讓可產生統計資料。如果您在搜尋查詢中使用關鍵字] 清單中，最小化] 的 [關鍵字] 清單中的列數或分成較小的清單中的數字的關鍵字，並建立不同的搜尋為每個關鍵字清單。

  > [!NOTE]
  > 若要協助減少大型關鍵字清單所導致的問題，現在是限制最大值為 20 列在 [關鍵字] 清單中的搜尋查詢。

- 太多搜尋相同的信箱上正在執行在同一時間。請儘可能嘗試在任何一個信箱上一次執行一個搜尋。

- 在單一搜尋中搜尋太多的信箱。搜尋非常大的信箱數目時會增加的內容位置錯誤的機率。請儘可能嘗試執行多個搜尋，讓每個搜尋組織中包含信箱的子集。

- 必要的維護信箱上執行。雖然此原因可能會發生常，等待一點時後接收內容位置錯誤，然後重試搜尋。
