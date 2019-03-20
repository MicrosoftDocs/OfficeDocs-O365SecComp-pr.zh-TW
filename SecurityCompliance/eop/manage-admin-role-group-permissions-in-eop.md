---
title: 管理 EOP 中的系統管理員角色群組權限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 系統管理中心 (EAC)，讓使用者成為角色群組的成員，以為他們指派可用以執行特定管理工作的權限。您也可以使用 EAC 從角色群組中移除使用者。
ms.openlocfilehash: aed32c8a9224bc60ef3e4a1ac9be9d797e61bda8
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693422"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>管理 EOP 中的系統管理員角色群組權限
  
在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 系統管理中心 (EAC)，讓使用者成為角色群組的成員，以為他們指派可用以執行特定管理工作的權限。您也可以使用 EAC 從角色群組中移除使用者。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 預估完成時間：5-10 分鐘
    
- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題中的「使用者、連絡人及角色群組」項目。 
    
- Office 365 中的某些權限會對映至 EOP 系統管理員角色群組權限。如需詳細資訊，請參閱[指派管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=286708)中＜我的 Office 365 權限會延伸至哪些服務＞一節中的「Exchange Online 中的角色」欄。
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="what-do-you-want-to-do"></a>您要執行的工作

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>使用 EAC 將成員指派給系統管理員角色群組

1. 在 EAC 中，瀏覽至 [**權限** \> **系統管理員角色**]，按一下您想要新增的使用者或使用者，角色群組，然後按一下 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)。
    
2. 在 [成員] 下，按一下 **[新增]**![加入圖示](../media/ITPro-EAC-AddIcon.gif)。[選取成員] 視窗將會出現。
    
3. 搜尋您要新增的使用者，或是從清單中加以選取。
    
4. 選好要新增的使用者後，按一下 **[新增]**，然後按一下 **[確定]**。[選取成員] 視窗便會關閉。
    
5. 您會看到使用者已新增至 **[成員]** 窗格。按一下 **[儲存]**。
    
    > [!NOTE]
    > 使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>使用 EAC 從系統管理員角色群組中移除成員

1. 在 EAC 中，瀏覽至 [**權限** \> **系統管理員角色**]，按一下您想要移除使用者或使用者的角色群組，然後按一下 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)。
    
2. 在 [成員] 下，選取您要移除的使用者，然後按一下 **[移除]**![[移除] 圖示](../media/ITPro-EAC-RemoveIcon.gif)。
    
3. 按一下 **[儲存]**，以儲存角色群組的變更，並回到 **[系統管理員角色]** 頁面。若要確認您是否已成功從系統管理員角色群組中移除使用者，請確定在所選角色群組的詳細資料窗格中，[成員] 下已看不到該成員。 
    
    > [!NOTE]
    > 使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。 
  
## <a name="for-more-information"></a>相關資訊

[EOP 中的功能權限](feature-permissions-in-eop.md)
  

