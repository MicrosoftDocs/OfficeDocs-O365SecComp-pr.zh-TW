---
title: Set up Information Rights Management (IRM) in SharePoint admin center
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: 了解如何使用 SharePoint Online IRM 透過 Microsoft Azure Active Directory Rights Management Services (RMS) 來保護 SharePoint 清單和文件庫。
ms.openlocfilehash: a5ac2cf5f33f3957e4cf17660461ad2d719d7c83
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217703"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center

在 SharePoint Online、 IRM 保護套用至清單和文件庫層級的檔案。您的組織可以使用 IRM 保護之前，您必須先設定版權管理。IRM 依賴 Azure 加密及指派流量限制的資訊保護 Azure 版權管理服務。某些 Office 365 計劃包括 Azure Rights Management，但非全部。如需了解，請先閱讀[如何 Office 應用程式及服務支援 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>開啟使用 SharePoint 管理中心的 IRM 服務

您的組織可以 IRM 保護的 SharePoint 清單和文件庫之前，您必須先啟動貴組織的版權管理服務。若要了解如何查看[啟動 Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service)。您必須使用工時或學校的帳戶已啟用的版權管理服務的 Office 365 全域管理員權限。否則您不能與 SharePoint Online 中使用 IRM 功能。
  
啟動之後版權管理服務，登入 SharePoint 系統管理中心來開啟 IRM。
  
1. 以全域管理員或 SharePoint 系統管理員身分登入 Office 365。
    
2. 選取左上方的應用程式啟動器圖示![Office 365 中的應用程式啟動器圖示](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然後選擇 [系統管理員]**** 以開啟 Office 365 系統管理中心。(如果您沒有看到 [系統管理員] 圖格，就表示您沒有貴組織中的 Office 365 系統管理員權限。) 
    
3. 在左窗格中，選擇 [ **Admin 中心** \> **SharePoint**。
    
4. 在左窗格中，選擇 [**設定**]。
    
5. 在 [**資訊版權管理 (IRM)** ] 區段中選擇 [**使用您的設定中指定的 IRM 服務**，然後選擇 [**重新整理 IRM 設定**。重新整理 IRM 設定之後，您組織中的人員即可開始使用 IRM 其 SharePoint 清單和文件庫中。不過，若要這樣做選項可能需要一小時出現在文件庫設定及清單設定。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM 啟用 SharePoint 文件庫和清單
<a name="__toc220831191"> </a>

在重新整理 IRM 設定之後, 網站擁有人可以 IRM 保護其 SharePoint 清單和文件庫。如需詳細資訊，請參閱[適用於資訊版權管理至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
當網站擁有者的清單或文件庫啟用 IRM 時，他們可以保護所有支援的檔案類型清單或文件庫中。當文件庫啟用 IRM 時，版權管理會套用於所有的文件庫中的檔案。當您啟用 IRM 的清單時，版權管理只適用於清單項目不實際的清單項目附加的檔案。
  
當人員下載中啟用 IRM 的清單或文件庫的檔案時，以便只授權的人員可檢視它們加密檔案。每個受版權管理檔案也包含會限制在檢視之檔案的人員的發行授權。一般限制包括唯讀屬性，停用的文字，防止人員從儲存的本機複本，並防止人員列印檔案複製進行檔案。可讀取的 IRM 支援的檔案類型的用戶端程式受版權管理檔案內使用的發行授權強制執行這些限制。這是如何受版權管理檔案會保留在其保護即使下載。若要在清單或文件庫啟用 IRM，請參閱[適用於資訊版權管理至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
您無法建立或編輯文件中啟用 IRM 的文件庫使用 Office Online。而是一次的某個人可以下載並編輯 IRM 加密的檔案。使用存回及取出管理*的共同撰寫*、 或製作跨多個使用者。 
  
當您從受 IRM 保護之文件庫下載 PDF 檔案時，Office 365 建立受保護的 PDF 檔案。將不會變更檔案的副檔名，但在受保護的檔案。若要檢視此檔案您需要 Azure 資訊保護檢視器中，完整的 Azure 資訊保護用戶端，或另一個應用程式支援檢視受保護的 PDF 檔案。 
  
SharePoint Online 支援下列檔案類型的加密：
  
- PDF
    
- 下列的 Microsoft Office 程式 97-2003年檔案格式： Word、 Excel 及 PowerPoint
    
- Office Open XML 格式的下列的 Microsoft Office 程式： Word、 Excel 及 PowerPoint
    
- XML Paper Specification (XPS) 格式
    
## <a name="next-steps"></a>後續步驟
<a name="__toc220831191"> </a>

一旦您已啟用 IRM 的 SharePoint Online，便可以開始將版權管理套用至清單和文件庫。資訊，請參閱[適用於資訊版權管理至清單或文件庫](apply-irm-to-a-list-or-library.md)。
  
新的 OneDrive sync 用戶端 windows 現在也支援同步處理受 IRM 保護的 SharePoint 文件庫和 OneDrive 位置 （只要程式庫的 IRM 設定不設為過期文件的存取權限）。如需詳細資訊，或要開始部署新的同步處理用戶端，請參閱 ＜ [Deploy Windows 新 OneDrive sync 用戶端](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)。
  
[回到頁首](set-up-irm-in-sp-admin-center.md#__top)
  

