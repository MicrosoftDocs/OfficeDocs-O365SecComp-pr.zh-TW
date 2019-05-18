---
title: Azure 資訊保護推行至現有的 Office 365 租用戶中的保護功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: 若要協助保護您的資訊，所有的 Azure 資訊保護合格租用戶開始 2018 年 7 月的初始步驟會有 Azure 資訊保護中的保護功能預設開啟。 Azure 資訊保護中的保護功能已前身為權限管理或 Azure RMS 的 Office 365 中。 如果您的組織有辦公室 E3 服務計劃或更高的服務計劃現在就會開始保護透過 Azure 資訊保護的資訊，當我們推行這些功能。
ms.openlocfilehash: f7c5126ddf1a15dde147e724ceced34d95eef185
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152225"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Azure 資訊保護推行至現有的 Office 365 租用戶中的保護功能

若要協助保護您的資訊，所有的 Azure 資訊保護合格租用戶開始 2018 年 7 月的初始步驟會有 Azure 資訊保護中的保護功能預設開啟。 Azure 資訊保護中的保護功能已前身為權限管理或 Azure RMS 的 Office 365 中。 如果您的組織有辦公室 E3 服務計劃或更高的服務計劃現在就會開始保護透過 Azure 資訊保護的資訊，當我們推行這些功能。
  
## <a name="changes-beginning-july-1-2018"></a>從 2018 年 7 月 1 日開始的變更

啟動 2018 年 7 月 1 日，Microsoft 將會啟用保護功能，在 [Azure 資訊保護所有 Office 365 租用戶具有下列其中一個下列訂閱計劃取得：
  
- Office 365 郵件加密被提供 Office 365 E3 和 E5、 Microsoft E3 和 E5、 Office 365 A1、 A3 和 A5，與 Office 365 G3 和 G5 的一部分。 您不需要額外的授權，以接收由 Azure 資訊保護提供的新保護功能。 
    
- 您也可以新增 Azure 資訊保護方案 1 於下列計劃以接收新的 Office 365 郵件加密功能： Exchange Online Plan 1 Exchange Online Plan 2、 Office 365 F1、 Office 365 商務基本版、 Office 365 商務進階版，或Office 365 企業版 E1。
    
- 從 Office 365 郵件加密優點每位使用者需要功能線所涵蓋的授權。
    
- 完整清單請參閱[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)Office 365 郵件加密。 
    
租用戶系統管理員可以檢查 Office 365 系統管理員入口網站中的保護狀態。 
  
![螢幕擷取畫面，顯示 Office 365 中的權限管理會在啟動。](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>為什麼我們要讓這項變更？

Office 365 郵件加密利用 Azure 資訊保護中的保護功能。 Office 365 郵件加密的最新改進功能和 Microsoft 365 中的資訊保護我們更廣泛投資的核心，我們會使其成為開啟並使用我們的保護功能，以在過去，加密的組織更容易技術已經容易設定。 藉由在預設情況下的 [Azure 資訊保護中的保護功能，您可以快速開始來保護機密資料。
  
## <a name="does-this-impact-me"></a>沒有這會影響我？

如果您的 Office 365 組織已購買合格的 Office 365 授權，然後您的租用戶將會受到此變更。
  
 **重要 ！** 如果您使用 Active Directory Rights Management Services (AD RMS) 內部部署環境中，您必須選擇不使用這項變更立即或之前我們推出此變更下一個 30 天內，將移轉至 Azure 資訊保護。 如需如何選擇不使用，請參閱 「 使用 AD RMS，如何執行我退出？ 」 本文稍後。 如果您想要移轉，請參閱[從 AD RMS 移轉至 Azure 資訊保護。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>可以使用 Azure 資訊保護與 Active Directory Rights Management Services (AD RMS)？

否。 這不是支援的部署案例。 不採取額外的擴充加入確認程序的步驟，某些電腦可能會自動開始使用 Azure 版權管理服務，並同時連線到 AD RMS 叢集。 此案例不支援，且不可靠的結果，因此請務必退出這項變更 30 天內之前我們推行這些新功能。 如需如何選擇不使用，請參閱 「 使用 AD RMS，如何執行我退出？ 」 本文稍後。 如果您想要移轉，請參閱[從 AD RMS 移轉至 Azure 資訊保護。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>如何知道我是否使用 AD RMS？

若要檢查是否您已部署 AD RMS 使用這些指示[準備環境的 Azure Rights Management 時也有 Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) : 
  
1. 雖然選擇性的大部分的 AD RMS 部署發佈的服務連線點 (SCP) 至 Active Directory，讓網域電腦可探索的 AD RMS 叢集。 
  
使用 adsi 編輯器] 若要查看您是否已在 Active Directory 中發佈 SCP: CN = Configuration [伺服器名稱] 中，CN = Services，CN = RightsManagementServices，CN = SCP
    
2. 如果您不使用 SCP，連線至 AD RMS 叢集的 Windows 電腦必須設定用戶端服務探索或授權的重新導向透過 Windows 登錄中： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation 或 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
如需這些登錄設定的詳細資訊，請參閱[使用 Windows 登錄中啟用用戶端服務探索](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)和[重新導向 」 授權伺服器的流量](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>使用 AD RMS，如何執行我退出嗎？

若要選擇退出即將到來的變更，完成下列步驟：
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
2. 執行 Set-irmconfiguration 指令程式使用下列語法：
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>項目可以預期之後進行此項變更？

一旦啟用這項功能，提供您未選擇，就可以開始使用新版的 Office 365 郵件加密宣告於[Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)並利用 Azure 資訊的加密和保護功能保護。 
  
![螢幕擷取畫面顯示 OME 受保護的網頁型 Outlook 中的郵件。](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
如需有關新的增強功能的詳細資訊，請參閱 < <b0>Office 365 郵件加密</b0>。
  

