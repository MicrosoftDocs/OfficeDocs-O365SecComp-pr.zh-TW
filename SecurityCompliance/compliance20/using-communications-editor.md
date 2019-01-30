---
title: 使用溝通編輯器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607569"
---
# <a name="using-the-communications-editor"></a>使用通訊編輯器
當您定義入口網站內容的內容、 法律保留通知和相關的 reminders 呈報，您可以運用通訊編輯器來設定的格式和動態自訂您的內容。

## <a name="rich-text-editor"></a>Rtf 編輯器 

通訊編輯器可讓使用者自訂使用編輯器選項的文字。例如，使用者可以變更字型類型、 建立項目符號清單、 醒目提示內容及其他。 

<<include screenshot>>

## <a name="merge-field-variables"></a>合併欄位變數

您可以運用電子郵件合併變數將通訊本文中嵌入自訂的 okay 屬性從通訊編輯器。傳送至 okay、 時就會以對應的欄位填入合併功能變數。例如時傳送到 okay John Smith，合併功能變數 [Okay 名稱] 將轉譯與對應的名稱。 

您可以使用電子郵件合併列印欄位選取 [請 rtf 編輯器控制項上方的**合併列印欄位**圖示。版面配置區將會加入根據關閉使用者的資料指標的位置。 

### <a name="list-of-merge-field-variables"></a>合併列印欄位變數清單
| 欄位名稱                  | 欄位的詳細資訊 | 
| :------------------- | :-------------------: |
| 顯示名稱  | Okay 的名字與姓氏 | 
| 認可連結                 | 記錄每個 okay 認可的自訂的連結                 |
| 入口網站的連結     | 自訂的連結 okay 規範入口網站                 |
| 發出主管人員                   | 指定發行主管電子郵件地址                   |
| 發行日期                   | 請注意已發出 (UTC) 的日期              |