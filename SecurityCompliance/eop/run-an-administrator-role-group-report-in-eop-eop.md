---
title: '執行 EOP 中的系統管理員角色群組報告 '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 當系統管理員在系統管理員角色群組新增或移除成員時，Microsoft Exchange Online Protection (EOP) 會記錄每次發生的事件。
ms.openlocfilehash: 5004851ec08afba7fcb26cbaefbe18f8c14e629a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153045"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>執行 EOP 中的系統管理員角色群組報告 

 當系統管理員在系統管理員角色群組新增或移除成員時，Microsoft Exchange Online Protection (EOP) 會記錄每次發生的事件。當您在 Exchange 系統管理中心執行系統管理員角色群組報告時，項目會顯示為搜尋結果，並包括受影響的角色群組、變更角色群組成員資格的人員和時間，以及做了什麼成員資格更新。使用此報告可監視指派給組織使用者的系統管理權限變更。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 預估完成時間：2 分鐘
    
- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題的「報告」一節。 
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>使用 EAC 執行系統管理員角色群組報告

執行系統管理員角色群組報告，以尋找在特定時間範圍內，對您組織中管理角色群組所進行的變更。
  
1. 在 EAC 中，瀏覽至 **[相符性管理]** \> **[稽核]**，然後選擇 **[執行系統管理員角色群組報告]**。
    
2. 選擇 **[開始日期]** 和 **[結束日期]**。依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。
    
3. 若要檢視特定角色群組的變更，請按一下 **[選取角色群組]**。在後續的對話方塊中選取一或多個角色群組，然後按一下 **[確定]**。您也可以將欄位留白，以尋找所有變更的角色群組。
    
4. Click **Search**.
    
如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。
  
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。
  
## <a name="monitor-changes-to-role-group-membership"></a>監視角色群組成員資格的變更

在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。
  
若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目： 
  
 **27.01.13 16:43:00 AM**
  
 **Administrator**
  
 **Updated members:Administrator;annb,florencef;pilarp**
  
 **06.02.13 10:09 AM**
  
 **Administrator**
  
 **Updated members:Administrator;annb;florencef;pilarp;tonip**
  
 **19.02.13 14:12:00 AM**
  
 **Administrator**
  
 **Updated members:Administrator;annb;florencef;tonip**
  
在此範例中，系統管理員使用者帳戶做了以下變更：
  
- 他在 06.02.13 新增使用者 tonip。
    
- 他在 19.02.13 移除使用者 pilarp。
    

