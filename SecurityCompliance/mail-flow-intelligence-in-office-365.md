---
title: Office 365 中的郵件流程智慧
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: '一般而言，您使用連接器來路由傳送訊息從 Office 365 組織內部的郵件環境。您可能也使用連接器來路由郵件來自 Office 365 協力廠商組織。Office 365 無法傳送連接器透過這些訊息，當他們正在排入佇列 Office 365 中。 '
ms.openlocfilehash: 495d73524afb3ab3a34fd2f1f5f4cd747481f9d8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027620"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Office 365 中的郵件流程智慧
  
一般而言，您使用連接器來路由傳送訊息從 Office 365 組織內部的郵件環境。您可能也使用連接器來路由郵件來自 Office 365 協力廠商組織。Office 365 無法傳送連接器透過這些訊息，當他們正在排入佇列 Office 365 中。Office 365 會繼續重試每封郵件的傳遞 48 小時。48 小時之後已排入佇列的郵件將過期，及訊息將會傳回給原始寄件者的未傳遞回報 （也稱為 NDR 或彈跳訊息）。
  
Office 365 中將會產生錯誤時無法使用連接器來傳遞訊息。最常見的錯誤和其解決方案本主題所述。透過連接器傳送的郵件無法傳遞佇列和通知錯誤統稱稱為 「 郵件流程智慧。
  
 **目錄**
  
- [錯誤代碼： 450 4.4.312 DNS 查詢失敗](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [錯誤代碼： 450 4.4.315 連線逾時](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [錯誤代碼： 450 4.4.316 拒絕連線](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [錯誤代碼： 450 4.4.317 無法連線至遠端伺服器](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [錯誤代碼： 450 4.4.318 突然關閉連線](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [錯誤代碼： 450 4.7.320 憑證驗證失敗](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a>錯誤代碼： 450 4.4.312 DNS 查詢失敗
<a name="ErrorCode44312"> </a>

這個錯誤通常表示 Office 365 嘗試連線至智慧主機所指定的連接器，但 DNS 查詢以尋找智慧主機的 IP 位址失敗。針對這項錯誤的可能原因如下：
  
- 沒有問題與網域的 DNS 裝載服務 （維護您網域的代表性頁面的名稱伺服器的方）。
    
- 您的網域已最近過期，因此無法擷取 MX 記錄。
    
- 最近已變更您的網域的 MX 記錄，及 Office 365 的 DNS 伺服器仍有先前快取的 DNS 網域的資訊。
    
您需要修正的 DNS 問題的處理的 DNS 裝載服務。
  
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  
## <a name="error-code-450-44315-connection-timed-out"></a>錯誤代碼： 450 4.4.315 連線逾時
<a name="ErrorCode44315"> </a>

通常這表示 Office 365 無法連線至目的地郵件伺服器。錯誤詳細資料會說明問題。例如：
  
- 您內部部署郵件伺服器已離線。
    
- 中有錯誤的連接器智慧主機設定，讓 Office 365 嘗試連線至了錯誤的 IP 位址。
    
了解哪些案例適用於，並進行必要的修正。例如，如果郵件流程運作正確，且尚未變更連接器的設定，您需要檢查您的內部郵件環境如果伺服器已關閉，或者已有任何變更至您的網路基礎結構 （例如，您已變更的網際網路服務提供者，所以您現在有不同的 IP 位址）。
  
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  
## <a name="error-code-450-44316-connection-refused"></a>錯誤代碼： 450 4.4.316 拒絕連線
<a name="ErrorCode44316"> </a>

通常此錯誤表示 Office 365 時遇到的連線錯誤它嘗試連線至目的地郵件伺服器。這項錯誤的可能原因為您的防火牆會封鎖來自 Office 365 IP 位址的連線。或這項錯誤可能是根據設計如果您已完全移轉您的內部郵件至 Office 365 系統並關閉 [您的內部郵件環境。
  
- 如果您有內部部署環境中的信箱，您需要修改您的防火牆設定以允許 TCP 連接埠 25 上的 Office 365 IP 位址從連線到您的內部通訊的伺服器。如需 Office 365 IP 位址的清單，請參閱[Office 365 Url 和 IP 位址範圍](https://go.microsoft.com/fwlink/p/?linkid=228887)。
    
- 如果沒有多個郵件應該傳遞至內部部署環境中，按一下 [**立即修正**警示中讓 Office 365 可立即拒絕無效的收件者的郵件。這會降低超出您的組織配額無效收件者，這可能會影響正常的郵件傳遞的風險。或者，您可以使用下列指示以手動方式修正的問題： 
    
  - 停用或刪除來自 Office 365 的連接器至內部部署環境： Office 365 系統管理中心\>**系統中心** \> **Exchange** \> **郵件流程** \> **連接器**\>選取**從**值**Office 365**的連接器及**以**值**貴組織的電子郵件伺服器**。依序按一下 [**刪除**刪除連接器![刪除圖示](media/ITPro-EAC-DeleteIcon.png)，或按一下 [**編輯**停用連接線![編輯圖示](media/ITPro-EAC-EditIcon.png)及取消核取**加以開啟**。
    
  - 變更與內部具有相關聯的 Office 365 中公認的網域從**內部轉送**至**授權**的郵件環境。指示，請參閱[管理 Exchange Online 中公認的網域](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx)。
    
    **請注意**： 30 分鐘和一小時之間這些變更時間才會生效通常。在一個小時後確認不會再收到錯誤。
    
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>錯誤代碼： 450 4.4.317 無法連線至遠端伺服器
<a name="ErrorCode44317"> </a>

通常此錯誤表示 Office 365 連線至目的地郵件伺服器，但伺服器回應立即錯誤為或不符合的連線需求。錯誤詳細資料會說明問題。例如：
  
- 目的地訊息伺服器回應 「 無法使用服務 」 錯誤，指出伺服器無法與 Office 365 保持通訊。
    
- 若要要求 TLS] 設定連接器，但目的地郵件伺服器不支援 TLS。
    
確認您內部部署的憑證的 TLS 設定訊息伺服器及連接器上的 TLS 設定。
  
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>錯誤代碼： 450 4.4.318 突然關閉連線
<a name="ErrorCode44318"> </a>

這個錯誤通常表示 Office 365 與內部通訊發生問題郵件環境，因此已中斷連線。針對這項錯誤的可能原因如下：
  
- 防火牆使用 SMTP 封包檢查規則，這些規則未運作正常。
    
- 您內部部署郵件伺服器未運作正常 （例如服務擱置、 當機次數或低系統資源），會導致逾時時間的伺服器，並關閉 Office 365 的連線。
    
- 有內部部署環境與 Office 365 之間的網路問題。如果問題持續發生，請連絡您的網路小組來排除此問題。
    
了解哪些案例適用於，並進行必要的修正。
  
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  
## <a name="error-code-450-47320-certificate-validation-failed"></a>錯誤代碼： 450 4.7.320 憑證驗證失敗
<a name="ErrorCode47320"> </a>

通常此錯誤表示 Office 365 嘗試驗證目的地通訊伺服器的憑證時遭遇到錯誤。錯誤詳細資料會說明錯誤。例如：
  
- 憑證到期
    
- 憑證主旨不符
    
- 不再是有效的憑證
    
請在使 Office 365can 中已排入佇列的郵件傳遞修正憑證或連接器。
  
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  
## <a name="other-error-codes"></a>其他錯誤碼
<a name="sectionSection6"> </a>

Office 365 問題發生提供訊息給您的內部或協力廠商訊息伺服器。使用**目的地伺服器**資訊錯誤檢查您的環境的問題或修改連接器，如果有設定錯誤。 
  
如果錯誤是從協力廠商組織 （例如 3rd 廠商雲端服務提供者），您必須連絡您若要修正此問題的協力廠商。
  

