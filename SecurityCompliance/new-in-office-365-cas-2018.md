---
title: What's new in Office 365 雲端 App 安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 請參閱什麼發行期間 2018 for Office 365 雲端 App 安全性
ms.openlocfilehash: 986fb64eedf8184e7835d1fec41845fde13b294b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263147"
---
# <a name="office-365-cloud-app-security-updates-during-2018"></a>在 2018年期間更新的 office 365 雲端 App 安全性

## <a name="office-365-cloud-app-security-release-138"></a>Office 365 雲端 App 安全性版本 138

*發行 2018 年 12 月 23 日*

**下列[Microsoft Cloud App Security 釋出 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **使用 windows Docker 自動記錄上傳**Cloud App Security 現在可支援自動記錄上傳適用於 Windows 10 ([Fall Creators Update](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)和更新版本) 和 Windows Server ([版本 1709年](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709)和更新版本) 使用 Docker Windows 上。 請參閱[這篇文章](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows)以了解更多與設定 Docker。  

- **Microsoft Flow 整合**與[Microsoft Flow](https://docs.microsoft.com/flow/getting-started)提供自訂警示的自動化和協調流程 playbooks 現在整合 cloud App Security。 請參閱[這篇文章](https://docs.microsoft.com/cloud-app-security/flow-integration)以了解更多及設定 Microsoft Flow 整合。 

## <a name="office-365-cloud-app-security-release-137"></a>Office 365 雲端 App 安全性版本 137

*2018 年 12 月 8 日發行*

**下列[Microsoft Cloud App Security 釋出 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **新增支援 Dynamics**Cloud App Security 現在包含 Office 365 稽核記錄中皆受到支援的 Microsoft Dynamics 活動的支援。 

- **設定新的術語組分 ！** 以方便識別已變更的應用程式的權限功能的名稱-它現在稱為 OAuth 應用程式。 

## <a name="office-365-cloud-app-security-release-136"></a>Office 365 雲端 App 安全性版本 136

*2018 年 11 月 25 日發行*

**下列[Microsoft Cloud App Security 釋出 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **雲端探索更新**自訂記錄剖析器已增強，可支援其他和更複雜的 web 流量記錄檔的格式。 隨著一部分這些增強功能的使用者現在可以輸入 headerless CSV 檔的自訂標頭，機碼值檔案使用特殊的分隔符號，Syslog 檔案格式及其他處理程序。

- **新的異常偵測原則： 可疑的收件匣操作規則**刪除或移動郵件或資料夾的可疑規則設定使用者的收件匣時，此原則設定檔您的環境和會觸發警示。 這表示可能危害使用者帳戶，該郵件正在刻意隱藏的和信箱會被用來發佈垃圾郵件或貴組織中的惡意程式碼。

- **支援的應用程式的權限原則中的群組**Cloud App Security 現在讓您能夠更細微地定義應用程式的權限原則根據授權的應用程式的使用者的群組成員資格。 例如，系統管理員可以決定要設定的原則，如果他們要求高的權限，授與權限的使用者是管理員群組的成員，才會撤銷另類應用程式。

## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Office 365 雲端 App 安全性放開 133、 134，以及 135

*於 10 月 11 月發行 2018*

**下列[Microsoft Cloud App Security 發行 133、 134，以及 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- **新的異常偵測原則**會逐漸推出：
    
    - 新的**資料 exfiltration unsanctioned 應用程式**原則會自動啟用的使用者或 IP 位址使用的應用程式不是.若要執行的格式類似於嘗試 exfiltrate 資訊從您的組織活動時提醒您。
    
    - 新的**多個刪除 VM 活動**原則設定檔您的環境，並會觸發警示，當使用者在單一工作階段，相對於基線貴組織中刪除多個 Vm。

- **雲端探索支援 i 篩選器**雲端 App 安全性雲端探索功能現在已增強 i 篩選 syslog 剖析器的支援。

## <a name="office-365-cloud-app-security-release-131"></a>Office 365 雲端 App 安全性版本 131

*發行 2018 年 9 月 16 日*

**下列[Microsoft Cloud App Security 釋出 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **自動撤銷風險 OAuth 應用程式的權限**您現在可以控制哪些 OAuth 應用程式使用者可以存取，利用撤銷 Office 上的 OAuth 應用程式的應用程式權限。 建立應用程式的權限原則時，您現在可以設定要撤銷應用程式的權限的原則。

- **雲端探索其他內建剖析器支援**雲端探索現在可支援 Forcepoint Web 安全性雲端記錄格式。
  
## <a name="office-365-cloud-app-security-release-130"></a>Office 365 雲端 App 安全性版本 130

*2018 年 9 月 5 日發行*

**下列[Microsoft Cloud App Security 釋出 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **新的功能表列**若要跨 Microsoft 365 的產品，提供更一致的管理經驗，並可讓您更輕鬆地樞紐之間 Microsoft 安全性解決方案，Cloud App Security 入口網站的功能表列已移至螢幕的左側。 此一致的瀏覽體驗可幫助您會引導您自己從一個 Microsoft 安全性入口網站移至另一個時。<br/>![Office 雲端 App 安全性中的功能表列](media/OCAS-MenuBar.png)<br/>

- **影響 OAuth app 分數**您現在可以傳送，讓我們知道是否有發現似乎惡意您組織中的 OAuth 應用程式的 Cloud App Security 小組意見反應。 這項新功能可讓您是我們安全性社群的一部分，而且增強 OAuth 應用程式的風險分數及分析。 如需詳細資訊，請參閱[管理 OAuth 應用程式](manage-app-permissions-in-ocas.md)。

- **新的雲端探索剖析器**雲端探索剖析器現在則支援 iboss Secure Cloud 閘道與 Sophos XG。

## <a name="office-365-cloud-app-security-release-128"></a>Office 365 雲端 App 安全性版本 128

*2018 年 8 月 5 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **跨多個應用程式的 OAuth 應用程式**OAuth 應用程式，您可以現在禁止或核准單一動作中的多個應用程式。 例如，您可以檢閱所有的應用程式具有已授與權限由使用者在組織中，選取您要禁止，所有應用程式，然後按一下 [若要撤銷授與所有同意的郵件應用程式，並將不再允許這些應用程式的權限授與使用者。 若要深入了解，請參閱 <<c0>使用 Office 365 雲端 App 安全性管理 OAuth 應用程式。 
    
- **新增建議的查詢： 可供 GDPR 的雲端應用程式**沒有新的建議的查詢，可讓您識別已發現已準備好 GDPR 的應用程式。 您可能已經知道，GDPR 最近已變成首要安全性系統管理員。 此查詢可協助您輕鬆地找出已準備好，GDPR 的應用程式，並藉由評估不的應用程式的風險降低威脅。 若要使用新的查詢，在**雲端探索**儀表板的 [ **Discovered 應用程式**] 索引標籤中，選擇 [**查詢** > **GDPR 準備雲端應用程式**。<br/>![GDPR 準備雲端應用程式查詢](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 雲端 App 安全性版本 126

*2018 年 7 月 7 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **自動化修復可疑的活動**您現在可以設定自動修復動作的異常偵測原則所觸發的可疑活動。 這個增強功能可讓您立即發生外洩時，便會通知和自動套用控管動作，例如暫停使用者。 如需詳細資訊，請參閱[Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)。
    
- **自動化偵測有風險的 OAuth 應用程式**除了 OAuth 應用程式連線至您的環境現有調查，Office 365 雲端 App 安全性現在可讓您設定，讓您知道 OAuth 應用程式時符合特定準則的自動化的通知。 例如，您可自動警示應用程式時，需要高的權限等級，且已獲授權 50 個以上的使用者。 如需詳細資訊，請參閱 <<c0>使用 Office 365 雲端 App 安全性管理 OAuth 應用程式。
    
- **受管理的安全性服務提供者管理 (MSSP) 支援**Office 365 雲端 App 安全性現在 MSSPs，以提供較佳的管理經驗，並可讓您將外部合作夥伴設定為與任何 Office 365 雲端 App 安全性中目前可用的角色的系統管理員。 此外，多個租用戶的存取權限的系統管理員可以立即輕鬆樞紐分析租用戶之間。 
    
## <a name="office-365-cloud-app-security-release-124"></a>Office 365 雲端 App 安全性版本 124

*2018 年 6 月 10 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **範圍部署**企業組織可以進行細緻決定哪些使用者監視和保護根據群組成員資格。 這項功能可讓您選取其活動不會顯示任何受保護的應用程式的使用者。 設定監視的範圍是特別有用的規範與授權。 有些合規性法規也許您避免監視當地法規由於某些國家/地區的使用者。 然後您可以監視較少的使用者，若要保持在您的 Office 365 雲端 App 安全性授權的上下限範圍內。 
    
- **新的電子郵件伺服器**Office 365 雲端 App 安全性的電子郵件伺服器已變更，並使用不同的 IP 位址範圍。 若要確保您可以取得通知，將新的 IP 位址新增至您的反垃圾郵件 whitelist。 針對自訂其通知的組織，Cloud App Security 可讓這讓您使用 mailchimp 代表，協力廠商電子郵件服務。 郵件伺服器 IP 位址，並啟用： 使用 mailchimp 代表指示的清單，請參閱[網路需求 (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements)和[郵件設定 (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings)。
    
## <a name="office-365-cloud-app-security-release-121"></a>Office 365 雲端 App 安全性版本 121

*2018 年 5 月 6 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **異常偵測原則增強功能**。 Office 365 雲端 App 安全性的異常偵測原則已經過改良加入逐漸推出的威脅偵測新兩種： 
    
  - **勒索軟體活動。** 勒索軟體偵測功能是為了讓您更廣泛的涵蓋範圍，複雜勒索軟體攻擊的異常偵測與擴充。 
    
  - **終止使用者活動。** 終止使用者活動可讓您監視的人員可能已經取消佈建從公司的應用程式，但誰可能仍會終止使用者帳戶可以存取特定公司資源。 
    
    若要檢視您[的異常偵測原則](anomaly-detection-policies-in-ocas.md)中，在 Office 365 雲端 App 安全性入口網站中，選擇 [**控制項** \> **原則**。
    
## <a name="office-365-cloud-app-security-release-120"></a>Office 365 雲端 App 安全性版本 120

*2018 年 4 月 22 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **為使用者活動的內部應用程式**。 Office 365 和 Azure Active Directory (Azure AD)，我們已現在會逐漸推出能夠偵測內部應用程式為 Office 365 和 Azure AD 應用程式 （內部和外部） 所執行的使用者帳戶活動。 這可讓您建立原則，如果應用程式執行預期或未經授權的活動時提醒您。 
    
- **匯出 OAuth 應用程式清單中的多個欄位**。 OAuth 應用程式] 清單匯出為 csv，例如發行者，其他欄位時的權限層級和社群的使用狀況會包含協助您的合規性和調查程序。 
    
## <a name="office-365-cloud-app-security-release-119"></a>Office 365 雲端 App 安全性版本 119

*2018 年 4 月 1 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **雲端探索的增強功能**。 雲端探索提供主要使用者和 IP 位址的詳細資訊，使其更容易進行 Office 365 的相關資訊的檢視使用狀況詳細資料和其他應用程式。 若要深入了解，請參閱 < <b0>Office 365 雲端 App 安全性中的檢閱應用程式探索結果</b0>。
    
    ![已更新，在雲端探索儀表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Office 365 雲端 App 安全性版本 118

*2018 年 3 月 18 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Barracuda 支援**。 雲端探索現在可支援 Barracuda F 數列防火牆和 Barracuda F 數列防火牆 web 記錄資料流。 
    
## <a name="office-365-cloud-app-security-release-117"></a>Office 365 雲端 App 安全性版本 117

*2018 年 3 月 6 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **i 篩選器支援**。 雲端探索現在可支援 i 篩選器。 
    
## <a name="office-365-cloud-app-security-release-116"></a>Office 365 雲端 App 安全性版本 116

*2018 年 2 月 18 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **異常偵測原則增強功能**。 異常偵測原則在 Office 365 雲端 App 安全性已增強功能包括無法旅行社，從可疑的 IP 位址的活動新案例型偵測和多個失敗的登入。 自動啟用了新的原則，提供雲端環境之間的方塊出威脅偵測。 此外，新的原則會公開從 Office 365 雲端 App 安全性偵測引擎，可以協助加速調查的程序，並包含持續威脅的更多資料。 若要深入了解，請參閱 Microsoft Cloud App Security，[取得顯現行為分析和異常偵測](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)。
    
- **記錄檢查點格式的剖析器支援**。 雲端探索記錄剖析器現在則支援兩個額外的檢查點格式： XML，而且 KPC。 
    
## <a name="office-365-cloud-app-security-release-114"></a>Office 365 雲端 App 安全性版本 114

*2018 年 1 月 21 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **服務狀態**。 您現在可以檢查目前的 Office 365 雲端 App 安全性服務狀態移至 [**協助** \> **系統狀態**。 
    
    ![按一下 [說明]\>系統狀態] 以檢視系統健康狀態](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **活動記錄檔的自訂查詢**。 從開始版本 114，能夠建立及儲存活動記錄檔中的自訂查詢推行逐漸。 自訂查詢可讓您建立可重複使用的深層探討調查的篩選範本。 此外，建議的查詢已新增至提供的方塊出調查範本來篩選您的活動，並探索應用程式。 建議的查詢包含自訂篩選，以識別例如模擬活動、 系統管理員活動、 風險不相容的雲端儲存應用程式、 企業應用程式的風險與弱式的加密，以及安全性風險。 使用建議的查詢做為起點，視需要修改，然後將其儲存為新的查詢。 
    
## <a name="office-365-cloud-app-security-release-113"></a>Office 365 雲端 App 安全性版本 113

*2018 年 1 月 8 日發行* 
  
**下列[Microsoft Cloud App Security 釋出 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **記錄剖析器支援泛型格式**。 雲端探索記錄剖析器現在則支援下列的一般格式： LEEF、 CEF，以及 W3C。 

## <a name="related-topics"></a>相關主題

[What's new in Office 365 雲端 App 安全性](new-in-office-365-cas.md)

<b0>請參閱 < 2017年更新 Office 365 雲端 App 安全性</b0>
    
[推出 Office 365 雲端 App 安全性後的使用活動](utilization-activities-for-ocas.md)