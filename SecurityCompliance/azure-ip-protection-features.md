---
title: Azure 資訊保護全面部署至現有的 Office 365 租用戶中保護功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
description: 若要協助保護您的資訊、 啟動年 7 月 2018年所有 Azure 資訊保護合格的租用戶的初始步驟會有中 Azure 資訊保護保護功能預設開啟。在 Azure 資訊保護的保護功能已前身為版權管理或 Azure RMS 的 Office 365 中。如果您的組織有辦公室 E3 服務計劃或更高的服務計劃您現在會取得標題開始時我們導入這些功能保護透過 Azure 資訊保護的資訊。
ms.openlocfilehash: be0200da3032dccbcf54e67f3bdfbac800b65526
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526483"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Azure 資訊保護全面部署至現有的 Office 365 租用戶中保護功能

若要協助保護您的資訊、 啟動年 7 月 2018年所有 Azure 資訊保護合格的租用戶的初始步驟會有中 Azure 資訊保護保護功能預設開啟。在 Azure 資訊保護的保護功能已前身為版權管理或 Azure RMS 的 Office 365 中。如果您的組織有辦公室 E3 服務計劃或更高的服務計劃您現在會取得標題開始時我們導入這些功能保護透過 Azure 資訊保護的資訊。
  
## <a name="changes-beginning-july-1-2018"></a>2018 年 7 月 1，開始進行的變更

啟動 2018 年 7 月 1 Microsoft 會在 Azure 資訊保護的保護功能的啟用所有 Office 365 租用戶具有其中一個訂閱方案：
  
- Office 365 郵件加密被提供 Office 365 E3 和 E5、 Microsoft E3 和 E5、 Office 365 A1、 A3 和 A5、 與 Office 365 G3 及 G5 的一部分。您不需要以接收新的保護功能由 Azure 資訊保護提供額外的授權。 
    
- 您也可以新增 Azure 資訊保護計劃 1 的下列計劃以接收新的 Office 365 郵件加密功能： Exchange Online 計劃 1、 Exchange Online 計劃 2、 Office 365 F1、 Office 365 商務 Essentials、 Office 365 企業進階版或Office 365 企業版 E1。
    
- 從 Office 365 郵件加密而且可以享有每位使用者必須被授權功能所涵蓋。
    
- 完整清單請參閱[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)Office 365 郵件加密。 
    
租用戶系統管理員可以檢查 Office 365 系統管理員入口網站中的保護狀態。 
  
![這個螢幕擷取畫面顯示 Office 365 中的權限管理已啟動。](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>為什麼我們會進行這項變更？

Office 365 郵件加密如何運用 Azure 資訊保護保護功能。在 Office 365 郵件加密的最近改良功能和以 Microsoft 365 中的資訊保護我們更廣泛投資的心形，我們會使其成為開啟並使用我們保護功能，以在過去，加密的組織更容易技術已設定很難。開啟的 Azure 資訊保護在預設的保護功能，您可以快速開始來保護機密資料。
  
## <a name="does-this-impact-me"></a>這影響我沒有吗？

如果您的 Office 365 組織已購買合格的 Office 365 授權，您的租用戶會影響由這項變更。
  
 **重要 ！** 如果您在內部部署環境中使用 Active Directory Rights Management Services (AD RMS)，您必須選擇延展這項變更立即或之前我們導入此變更下一個 30 天內移轉至 Azure 資訊保護。如需如何選擇延展、 本文稍後的看到 「 使用 AD RMS、 如何選擇 out? 」 的資訊。如果您偏好移轉，請參閱[從 AD RMS 移轉至 Azure 資訊保護。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>可以使用 Azure 資訊保護與 Active Directory Rights Management Services (AD RMS) 吗？

[否]。不支援的部署案例。不考慮其他的選擇加入延展步驟，某些電腦可能會自動啟動 [使用 Azure Rights Management service 和也連線到 AD RMS 叢集。此案例不支援與因此請務必退出這項變更之前我們導入這些新功能下一個 30 天內有不可靠的結果。如需如何選擇延展、 本文稍後的看到 「 使用 AD RMS、 如何選擇 out? 」 的資訊。如果您偏好移轉，請參閱[從 AD RMS 移轉至 Azure 資訊保護。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>如何知道是否我正在使用 AD RMS？

使用這些指示從[準備 Azure Rights Management 也有 Active Directory Rights Management Services (AD RMS) 時的環境](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)檢查是否您已部署 AD RMS： 
  
1. 雖然是選擇性的大部分的 AD RMS 部署將發佈的服務連線點 (SCP) 至 Active Directory 網域的電腦可以探索 AD RMS 叢集。 
  
使用 ADSI Edit 查看您是否已在 Active Directory 中發佈 SCP： CN = Configuration [伺服器名稱]、 CN = Services，CN = RightsManagementServices，CN = SCP
    
2. 如果您不使用 SCP，連線到 AD RMS 叢集的 Windows 電腦必須設定用戶端服務探索或授權的重新導向做為使用 Windows 登錄： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation 或 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
如需這些登錄設定的詳細資訊，請參閱[使用 Windows 登錄的啟用用戶端服務探索](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)和[重新導向 」 授權伺服器的流量](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>使用 AD RMS how do I 退出？

若要選擇退出即將來臨的變更，完成下列步驟：
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段並連線至 Exchange Online。指示，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。
    
2. 執行 Set-irmconfiguration 指令程式使用下列語法：
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>可什麼我預期之後進行這項變更？

這啟用後，提供您尚未會選擇加入，您可以開始使用新版的 Office 365 郵件加密的已在[Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)即已宣佈以及使用 Azure 資訊的加密和保護功能保護。 
  
![螢幕擷取畫面顯示 OME 保護網路上的 Outlook 中的郵件。](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
如需新的增強功能的詳細資訊，請參閱[Office 365 郵件加密](ome.md)。
  

