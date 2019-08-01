---
title: 在 Office 365 中的系統提交
ms.author: brwilcox
author: briwilcox
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何送出可能有害的郵件、 Url 和檔案給 Microsoft。
ms.openlocfilehash: 2e0bee0dd0a1ccc39d92ea9e175fc7fb10a5b6d3
ms.sourcegitcommit: 73d4cbcf7389935a04d2e451903ef14ebb38e096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643904"
---
# <a name="admin-submissions-in-office-365"></a>在 Office 365 中的系統提交

系統管理員現在可以傳送電子郵件掃描由 Microsoft Office 365 中使用的檔案或網路郵件 ID、 Url 和檔案。 更新送出資料] 區段中仍然會包含使用者所報告的郵件，並可供所有客戶使用 EOP。

當您提交的電子郵件時，您會收到郵件中的可能已允許內送電子郵件到您的租用戶，任何原則的相關資訊以及檢查任何 Url 和附件。 可能已允許郵件的原則包含個別使用者的安全寄件者清單，以及您在租用戶層級原則，例如 ETR 規則。 


## <a name="how-to-submit-content"></a>如何提交的內容

若要提交給 Microsoft 的內容按一下最左側的 [送出資料] 頁面上的 [**新的送出**] 按鈕。 頁面右側彈出式視窗會顯示送出任一電子郵件、 URL，或檔案的選項。 

### <a name="email"></a>電子郵件
![電子郵件送出範例](media/submission-flyout-email.PNG)
1. 若要提交的電子郵件，選取 [**電子郵件**和指定**網路郵件識別碼**的電子郵件或電子郵件檔案上傳。 

2. 指定您想要執行原則檢查的收件者。 原則檢查會決定電子郵件是否略過掃描由於使用者或租用戶層級原則。 

3. 指定是否電子郵件應被封鎖與否。 如果應該已封鎖電子郵件，指定如果它應該已封鎖為垃圾郵件、 網路釣魚或惡意程式碼。 如果您不確定哪種類型可能是，使用您的最佳 judgement。  

* 如果由於原則提交時略過篩選，您會看到該原則的相關資訊。

* 如果因為一或多個原則不略過篩選，將會在幾分鐘的時間內完成掃描。 在 [狀態] 連結，即可看到提交的其他資訊。 這包括原則檢查和掃描 verdict 的結果。 請注意這不會透過 Office 365 ATP 完整篩選堆疊一次執行電子郵件，但會執行部分重新掃描郵件、 URL 或檔案的某些屬性為基礎。 

4. 按一下 [**提交**] 按鈕。

### <a name="url"></a>URL
![電子郵件送出範例](media/submission-url-flyout.png)
1. 若要提交 URL 從彈出式視窗中選取**URL** 。 輸入完整的 URL 包括通訊協定 (**https://**)。 

* 如果您選取**應被篩選**，請指定 URL 如果是網路釣魚或惡意程式碼。

2. 按一下 [**提交**] 按鈕。 


### <a name="file"></a>檔案
![電子郵件送出範例](media/submission-file-flyout.PNG)
1. 提交從彈出式檔案選取**檔案**並上傳檔案至您想要掃描。 

2. 按一下 [**提交**] 按鈕。


## <a name="related-topics"></a>相關主題

[Office 365 進階的威脅保護計劃 2](office-365-ti.md)
  
[防範 Office 365 中的威脅](protect-against-threats.md)
  
[檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)
  
