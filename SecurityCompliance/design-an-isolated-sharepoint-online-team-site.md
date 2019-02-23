---
title: 設計獨立的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 摘要： 透過隔離的 SharePoint Online 小組網站的設計程序的步驟。
ms.openlocfilehash: 09748fcc22a4a48efc4346ff75a225db612a0ef4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216153"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>設計獨立的 SharePoint Online 小組網站

 **摘要：** 逐步解說隔離的 SharePoint Online 小組網站的設計程序的步驟。
  
本文會引導您完成建立隔離的 SharePoint Online 小組網站之前，您必須進行的重要的設計決策。
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>階段 1： 決定您的 SharePoint 群組和權限層級

每個預設的 SharePoint Online 小組網站被建立具有下列 SharePoint 群組：
  
- \<網站 name> 成員
    
- \<網站 name> 訪客
    
- \<網站 name> 擁有者
    
這些群組是不同 Office 365 和 Azure Active Directory (AD) 群組和指派資源的權限之網站的基礎。
  
會決定 SharePoint 群組的成員可以執行網站中的特定權限集是權限等級。SharePoint Online 小組網站的預設有三個權限層級： 編輯、 讀取、 及完全控制。下表顯示預設相互關聯之 SharePoint 群組及指派權限層級：
  
|**SharePoint 群組**|**權限等級**|
|:-----|:-----|
|\<網站 name> 成員  <br/> |編輯  <br/> |
|\<網站 name> 訪客  <br/> |讀取  <br/> |
|\<網站 name> 擁有者  <br/> |完全控制  <br/> |
   
 **最佳作法：** 您可以建立其他 SharePoint 群組與權限等級。不過，我們建議您隔離的 SharePoint Online 網站使用的預設 SharePoint 群組和權限層級。
  
以下是預設 SharePoint 群組與權限等級。
  
![SharePoint Online 網站的預設 SharePoint 群組和權限等級。](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>階段 2： 指派給使用者的存取群組與權限

您可以指派給使用者的權限新增其使用者帳戶或 Office 365 或 Azure AD 群組是所屬的使用者帳戶至 SharePoint 群組的成員。新增之後，Office 365 使用者帳戶，其直接或間接透過 Office 365 或 Azure AD 的群組成員資格，指派給關聯的 SharePoint 群組的權限層級。
  
使用預設 SharePoint 群組作為範例：
  
- 成員**\<網站 name> 成員**SharePoint 群組，其中可能包含使用者帳戶和群組，已指派的**編輯**權限層級
    
- 成員**\<網站 name> 訪客**SharePoint 群組，其中可能包含使用者帳戶和群組，已指派**讀取**權限等級
    
- 成員**\<網站 name> 擁有者**SharePoint 群組，其中可能包含使用者帳戶和群組，已指派的**完全控制**」 權限層級
    
 **最佳作法：** 雖然您可以透過管理權限的個別使用者帳戶，我們建議您使用單一 Azure AD] 群組中，而稱為 access] 群組中。這可透過在 [存取] 群組的成員資格的權限管理簡化而不是每個 SharePoint 群組管理清單的使用者帳戶。
  
Office 365 的 azure AD 群組是 Office 365 群組與不同。Azure AD 群組會出現在**安全性**其**型別**組與 Office 系統管理中心和不具有電子郵件地址。您可以管理 azure AD 群組內：
  
- Windows Server Active Directory (AD)
    
    這些是在您的內部部署 Windows Server AD 基礎結構中建立及同步處理至 Office 365 訂閱的群組。在 Office 系統管理中心，這些群組會有**與 active directory Synched****狀態**。
    
- Office 365
    
    這些是透過 Office 系統管理中心、 Azure 入口網站，或使用 Microsoft PowerShell 已建立的群組。在 Office 系統管理中心，這些群組會有**雲端**的**狀態**。
    
 **最佳作法：** 如果您使用 Windows Server AD 的內部使用者和群組管理與 Windows Server AD 同步處理與您的 Office 365 訂閱執行。
  
隔離 SharePoint Online 小組網站的建議的群組結構如下：
  
|**SharePoint 群組**|**Azure AD 式存取群組**|**權限等級**|
|:-----|:-----|:-----|
|\<網站 name> 成員  <br/> |\<網站 name> 成員  <br/> |編輯  <br/> |
|\<網站 name> 訪客  <br/> |\<網站 name> 檢視器  <br/> |讀取  <br/> |
|\<網站 name> 擁有者  <br/> |\<網站 name> 系統管理員  <br/> |完全控制  <br/> |
   
 **最佳作法：** 雖然您可以使用 Office 365 或 Azure AD 群組 SharePoint 群組的成員身分，我們建議您使用 Azure AD 群組。Azure AD 群組、 受管理的透過 Windows Server AD 或 Office 365 提供您更多彈性，可使用巢狀的群組來指派權限。
  
以下是預設值設定為使用 Azure AD 型的存取群組的 SharePoint 群組。
  
![使用存取群組作為預設 SharePoint Online 網站群組的成員。](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
設計的三種存取群組、 時請謹記下列事項：
  
- 應該有幾個成員只在**\<網站 name> Admins**存取群組，對應至少量的 SharePoint Online 系統管理員所管理小組網站。
    
- 大部分的網站成員位於**\<網站 name> 成員**或**\<網站 name> 檢視者**存取群組。因為網站中的成員**\<網站 name> 成員**存取群組已刪除或修改網站中的資源、 謹慎考慮其成員資格的能力。當有疑問，新增至該網站成員**\<網站 name> 檢視者**存取群組。
    
以下是範例中的 SharePoint 群組和名為 ProjectX 隔離網站的存取群組。
  
![為名為 ProjectX 的 SharePoint Online 網站使用存取群組的範例。](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>階段 3： 使用巢狀 Azure AD 群組

侷限於人員少數專案、 Azure AD 式存取群組新增至網站的 SharePoint 群組的單一層級適合大部分的情況。不過，如果您有大量的人員與這些人員的已經成員建立 Azure AD 群組，您可以更輕鬆地指派 SharePoint 權限使用巢狀的群組或包含其他群組成員的群組。
  
例如，您要建立隔離的 SharePoint online 小組網站的銷售、 行銷、 工程、 法律高階主管之間的共同作業及支援部門與這些部門已經自己群組以高階主管的使用者帳戶成員資格。而不是建立新的網站成員的新群組並放所有個別高階主管的使用者帳戶，將每個部門的現有 executive 群組置於新的群組。
  
 如果您要共用多個組織之間的 Office 365 訂閱，組織隔離網站群組成員資格的單一層級可能會不易管理因為大量的使用者帳戶。在此例中，您可以使用巢狀的每個組織的 Azure AD 群組包含在其組織中管理的權限的群組。
  
若要使用巢狀 Azure AD 群組：
  
1. 識別或建立將包含使用者帳戶並將適當的使用者帳戶新增為成員的 Azure AD 群組。
    
2. 建立將包含 「 Azure AD 群組並將這些群組新增為成員的容器 Azure AD 式存取群組。
    
3.  對於容器存取群組存取權的適當層級，識別 SharePoint 群組與對應的權限層級。
    
> [!NOTE]
> 您無法使用巢狀的 Office 365 群組。 
  
以下是巢狀的 Azure AD 的範例群組 ProjectX 成員存取群組。
  
![針對 ProjectX 網站之成員存取群組使用巢狀存取群組的範例。](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
因為參考資料、 工程和專案中的使用者帳戶的所有負責人小組都是設為網站成員、 將其 Azure AD 群組新增至 ProjectX 成員存取群組變得更容易。
  
## <a name="next-step"></a>後續步驟

當您準備好建立及設定在生產環境中隔離的網站時，請參閱 ＜ [Deploy 隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。
  
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。
  
[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)



