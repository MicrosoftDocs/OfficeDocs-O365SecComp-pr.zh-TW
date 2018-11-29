---
title: Office 365 雲端應用程式安全性的新功能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 11/28/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: 請參閱 Office 365 雲端應用程式安全性的新功能
ms.openlocfilehash: a3ca4504d80cbb39b51ecbcf3a5165bc5139e07c
ms.sourcegitcommit: bf628da123a89d9422e8cff02165b1e2d35dfe12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26872011"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a><span data-ttu-id="a7ccf-103">Office 365 雲端應用程式安全性的新功能</span><span class="sxs-lookup"><span data-stu-id="a7ccf-103">What is new in Office 365 Cloud App Security</span></span>

<span data-ttu-id="a7ccf-104">**摘要**請閱讀本篇文章以取得 Office 365 雲端應用程式安全性 （前身為 Office 365 進階安全性管理），這由[Microsoft 雲端應用程式安全性](https://aka.ms/whatiscas)提供更新及新功能的快速概觀。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-104">**Summary** Read this article to get a quick overview of updates and new features in Office 365 Cloud App Security (formerly known as Office 365 Advanced Security Management), which is powered by [Microsoft Cloud App Security](https://aka.ms/whatiscas).</span></span>
  
<span data-ttu-id="a7ccf-p101">＞ 本文已更新頻率，新增或改良功能時。Office 365 雲端應用程式的安全性更新發行約兩週後 Microsoft 雲端應用程式的安全性更新並不是所有的 Microsoft 雲端應用程式的安全性更新套用至 Office 365 雲端應用程式安全性。此外，新功能可能需要一週或更多 Office 365 雲端應用程式安全性環境中顯示其發行日期之後。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p101">This article is updated frequently, as features are added or improved. Office 365 Cloud App Security updates are released approximately two weeks after Microsoft Cloud App Security updates, and not all Microsoft Cloud App Security updates apply to Office 365 Cloud App Security. In addition, new features might take a week or more after their release date to show up in your Office 365 Cloud App Security environment.</span></span>

## <a name="office-365-cloud-app-security-release-136"></a><span data-ttu-id="a7ccf-108">Office 365 雲端應用程式安全性版本 136</span><span class="sxs-lookup"><span data-stu-id="a7ccf-108">Office 365 Cloud App Security release 136</span></span>

<span data-ttu-id="a7ccf-109">*發行 2018 年 11 月 25*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-109">*Released November 25, 2018*</span></span>

<span data-ttu-id="a7ccf-110">在**下列[版本 136 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-110">**Following [Microsoft Cloud App Security release 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:</span></span>

- <span data-ttu-id="a7ccf-p102">**雲端探索更新**自訂記錄剖析器已增強為可支援其他及更複雜的網頁流量記錄格式。為屬於下列增強功能的使用者現在可以輸入 headerless CSV 記錄檔的自訂頁首的機碼值檔案使用特殊的分隔字元、 Syslog 檔案格式及其他程序。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p102">**Cloud Discovery updates** The custom log parser was enhanced to support additional and more complex web traffic logs formats. As part of these enhancements users can now input custom headers for headerless CSV log files, use special delimiters for key-value files, process Syslog file format, and more.</span></span>

- <span data-ttu-id="a7ccf-p103">**新異常偵測原則： 可疑的收件匣操作規則**此原則設定檔環境與觸發程序提醒時可疑刪除或移動郵件或資料夾的規則設定在使用者的收件匣。這可能表示危害使用者帳戶，該郵件會被刻意隱藏，及信箱會被用來散佈垃圾郵件或惡意程式碼在組織中。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p103">**New anomaly detection policy: Suspicious inbox manipulation rules** This policy profiles your environment and triggers alerts when suspicious rules that delete or move messages or folders are set on a user's inbox. This may indicate that the user’s account is compromised, that messages are being intentionally hidden, and that the mailbox is being used to distribute spam or malware in your organization.</span></span>

- <span data-ttu-id="a7ccf-p104">**支援的應用程式的權限原則中的群組**雲端應用程式安全性現在讓您能夠更細部定義應用程式的權限原則根據授權之應用程式之使用者的群組成員資格。例如，系統管理員可以決定設定如果他們尋求高的權限授與權限的使用者是管理員群組的成員才會撤銷不尋常的應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p104">**Support for groups in app permission policies** Cloud App Security now gives you the ability to define app permission policies more granularly, based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the administrators group.</span></span>


## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a><span data-ttu-id="a7ccf-117">Office 365 雲端應用程式安全性釋放 133、 134，以及 135</span><span class="sxs-lookup"><span data-stu-id="a7ccf-117">Office 365 Cloud App Security releases 133, 134, and 135</span></span>

<span data-ttu-id="a7ccf-118">*發行的年 10 月-年 11 月、 2018*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-118">*Released in October-November, 2018*</span></span>

<span data-ttu-id="a7ccf-119">在**下列[133、 134，以及 135 版本 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-119">**Following [Microsoft Cloud App Security release 133, 134, and 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:</span></span>

- <span data-ttu-id="a7ccf-120">**新的異常偵測原則**會逐漸推出：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-120">**New anomaly detection policies** are rolling out gradually:</span></span>
    
    - <span data-ttu-id="a7ccf-121">新的**資料 exfiltration unsanctioned 應用程式**原則會自動啟用至使用者或 IP 位址所使用的應用程式未執行的格式類似於嘗試 exfiltrate 資訊從您的組織活動 sanctioned 時提出警示。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-121">The new **Data exfiltration to unsanctioned apps** policy is automatically enabled to alert you when a user or IP address uses an app that isn't sanctioned to perform an activity that resembles an attempt to exfiltrate information from your organization.</span></span>
    
    - <span data-ttu-id="a7ccf-122">新的**多個刪除 VM 活動**原則設定檔環境及當使用者在相對於基線您組織中的單一工作階段中刪除多個 Vm 觸發提醒。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-122">The new **Multiple delete VM activities** policy profiles your environment and triggers alerts when users delete multiple VMs in a single session, relative to the baseline in your organization.</span></span>

- <span data-ttu-id="a7ccf-123">**雲端探索支援 i 篩選**雲端應用程式安全性雲端探索功能現在已增強 i 篩選 syslog 剖析的支援。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-123">**Cloud Discovery support for i-Filter** The Cloud App Security Cloud Discovery feature now has enhanced support for the i-Filter syslog parser.</span></span>


## <a name="office-365-cloud-app-security-release-131"></a><span data-ttu-id="a7ccf-124">Office 365 雲端應用程式安全性版本 131</span><span class="sxs-lookup"><span data-stu-id="a7ccf-124">Office 365 Cloud App Security release 131</span></span>

<span data-ttu-id="a7ccf-125">*發行 2018 年 9 月 16*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-125">*Released September 16, 2018*</span></span>

<span data-ttu-id="a7ccf-126">在**下列[版本 131 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-126">**Following [Microsoft Cloud App Security release 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:</span></span>

- <span data-ttu-id="a7ccf-p105">**自動撤消 risky OAuth 應用程式的權限**您現在可以控制哪些 OAuth 應用程式為使用者可存取、 撤銷 OAuth office 的應用程式的應用程式權限。建立應用程式的權限原則時，您現在可以設定撤消應用程式的權限原則。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p105">**Automatically revoke permissions on risky OAuth apps** You can now control which OAuth apps your users have access to, by revoking app permission for OAuth apps on Office. When creating an App permission policy, you can now set the policy to revoke an app’s permission.</span></span>

- <span data-ttu-id="a7ccf-129">**雲端探索其他內建剖析器支援**雲端探索現在也支援 Forcepoint Web 安全性雲端記錄格式。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-129">**Cloud Discovery additional built-in parser supported** Cloud Discovery now supports the Forcepoint Web Security Cloud log format.</span></span>

  
## <a name="office-365-cloud-app-security-release-130"></a><span data-ttu-id="a7ccf-130">Office 365 雲端應用程式安全性版本 130</span><span class="sxs-lookup"><span data-stu-id="a7ccf-130">Office 365 Cloud App Security release 130</span></span>

<span data-ttu-id="a7ccf-131">*發行 2018 年 9 月 5、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-131">*Released September 5, 2018*</span></span>

<span data-ttu-id="a7ccf-132">在**下列[版本 130 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-132">**Following [Microsoft Cloud App Security release 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:</span></span>

- <span data-ttu-id="a7ccf-p106">**新的功能表列**若要提供更一致的管理經驗 Microsoft 365 產品並可讓您更輕鬆地樞紐之間的 Microsoft 安全性方案、 雲端應用程式安全性入口網站的功能表列已移至螢幕左邊。此一致的瀏覽體驗可幫助您的方式放置自行時移動到另一個 Microsoft 安全性入口網站。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p106">**New menu bar** To provide a more consistent admin experience across Microsoft 365 products, and to enable you to pivot more easily between Microsoft security solutions, the Cloud App Security portal menu bar has moved to the left side of the screen. This consistent navigation experience helps you orient yourself when moving from one Microsoft security portal to another.</span></span><br/><span data-ttu-id="a7ccf-135">![Office 雲端應用程式安全性的功能表列](media/OCAS-MenuBar.png)</span><span class="sxs-lookup"><span data-stu-id="a7ccf-135">![Menu bar in Office Cloud App Security](media/OCAS-MenuBar.png)</span></span><br/>

- <span data-ttu-id="a7ccf-p107">**影響 OAuth app 分數**您現在可以傳送意見是否有發現似乎惡意您組織中的 OAuth 應用程式的雲端應用程式安全性小組意見反應。此新功能可讓您是我們安全性社群的一部分並加強 OAuth app 風險分數與分析。如需詳細資訊請參閱 ＜[管理應用程式權限](manage-app-permissions-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p107">**Impact OAuth app score** You can now send the Cloud App Security team feedback to let us know if there’s an OAuth app discovered in your organization that seems malicious. This new feature enables you to be part of our security community and enhance OAuth app risk score and analysis. For more information see [Manage app permissions](manage-app-permissions-in-ocas.md).</span></span>

- <span data-ttu-id="a7ccf-139">**新雲端探索剖析器**雲端探索剖析器現在支援 iboss Secure Cloud 閘道和 Sophos XG。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-139">**New Cloud Discovery parsers** The Cloud Discovery parsers now support iboss Secure Cloud Gateway and Sophos XG.</span></span>


## <a name="office-365-cloud-app-security-release-128"></a><span data-ttu-id="a7ccf-140">Office 365 雲端應用程式安全性版本 128</span><span class="sxs-lookup"><span data-stu-id="a7ccf-140">Office 365 Cloud App Security release 128</span></span>

<span data-ttu-id="a7ccf-141">*發行 2018 年 8 月 5、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-141">*Released August 5, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-142">在**下列[版本 128 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-142">**Following [Microsoft Cloud App Security release 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p108">**跨多個應用程式的應用程式權限**對於已授予應用程式權限的應用程式，您可以立即禁止或核准多個應用程式中的單一動作。例如，您可以檢閱已授與權限由您組織中使用者、 選取您想要禁止、 的所有應用程式，然後按一下 [要撤銷權限授與所有同意禁止應用程式的所有應用程式並將不再允許授與這些應用程式的權限的使用者。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p108">**App permissions across multiple apps** For apps that have been granted app permissions, you can now ban or approve multiple apps in a single action. For example, you can review all the apps that have been granted permission by users in your organization, select all the apps you want to ban, and then click ban apps to revoke all consent granted and will no longer allow users to grant permission to those apps.</span></span> 
    
- <span data-ttu-id="a7ccf-p109">**新增建議的查詢： GDPR 就緒**沒有可讓您識別探索到的應用程式的已準備好 GDPR 建議新的查詢。GDPR 最近已變成安全性管理員的最高優先順序。此查詢可協助您輕鬆地識別應用程式的已準備好，GDPR 並降低所評估的應用程式不風險的威脅。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p109">**New suggested query: GDPR ready** There is a new suggested query to enable you to identify discovered apps that are GDPR ready. GDPR has recently became a top priority for security admins. This query helps you easily identify apps that are GDPR ready, and mitigate threat by assessing the risk of the apps that aren't.</span></span> 
    
## <a name="office-365-cloud-app-security-release-126"></a><span data-ttu-id="a7ccf-148">Office 365 雲端應用程式安全性版本 126</span><span class="sxs-lookup"><span data-stu-id="a7ccf-148">Office 365 Cloud App Security release 126</span></span>

<span data-ttu-id="a7ccf-149">*發行 2018 年 7 月 7、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-149">*Released July 7, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-150">在**下列[版本 126 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-150">**Following [Microsoft Cloud App Security release 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p110">**自動修復可疑的活動**您現在可以設定自動修復動作可疑異常偵測原則所觸發的工作階段。此增強功能可讓您能夠立即當缺口發生提醒與自動套用控管動作，例如暫停使用者。如需詳細資訊，請參閱[Office 365 雲端應用程式安全性異常偵測原則](anomaly-detection-policies-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p110">**Automated remediation for suspicious activities** You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and apply governance actions automatically, such as suspend user. For more information, see [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).</span></span>
    
- <span data-ttu-id="a7ccf-p111">**自動偵測 risky OAuth 應用程式**連線至您的環境的 OAuth 應用程式現有調查，以及 Office 365 雲端應用程式安全性現在可讓您設定讓您知道 OAuth 應用程式時符合特定準則的自動化的通知。例如，您可自動警示應用程式時需要較高的權限層級且已超過 50 個使用者授權。如需詳細資訊，請參閱[管理使用 Office 365 雲端應用程式安全性的應用程式權限](manage-app-permissions-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p111">**Automated detection of risky OAuth Apps** In addition to the existing investigate of OAuth apps connected to your environment, Office 365 Cloud App Security now allows you to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [Manage app permissions using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
    
- <span data-ttu-id="a7ccf-p112">**受管理的安全性服務提供者管理 (MSSP) 支援**Office 365 雲端應用程式安全性現在提供較佳的管理經驗 MSSPs，並可讓您設定外部合作夥伴與任何目前無法在 Office 365 雲端應用程式安全性角色的系統管理員身分。此外，使用多個承租人的存取權限的系統管理員可以立即輕鬆樞紐分析租用戶之間。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p112">**Managed Security Service Provider management (MSSP) support** Office 365 Cloud App Security now provides a better management experience to MSSPs, and allows you to configure external partners as administrators with any of the roles currently available in Office 365 Cloud App Security. In addition, Administrators with access rights to more than one tenant can now easily pivot between the tenants.</span></span> 
    
## <a name="office-365-cloud-app-security-release-124"></a><span data-ttu-id="a7ccf-159">Office 365 雲端應用程式安全性版本 124</span><span class="sxs-lookup"><span data-stu-id="a7ccf-159">Office 365 Cloud App Security release 124</span></span>

<span data-ttu-id="a7ccf-160">*發行 2018 年 6 月 10，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-160">*Released June 10, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-161">在**下列[版本 124 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-161">**Following [Microsoft Cloud App Security release 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p113">**範圍內部署**企業組織細部可以決定哪些使用者來監視及保護根據群組成員資格。此功能可讓您選取其活動將不會顯示為任何受保護的應用程式的使用者。設定監視的範圍是特別適合規範及授權。某些規範要求也許您避免監控當地法規由於某些國家/地區的使用者。然後您可以監視較少使用者保持在 Office 365 雲端應用程式安全性授權的限制內。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p113">**Scoped deployments** Enterprise organizations can granularly determine which users to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. Scoped monitoring is especially useful for compliance and licensing. Some compliance regulations necessitate that you refrain from monitoring users from certain countries due to local regulations. And, you can monitor fewer users to stay within the limits of your Office 365 Cloud App Security licenses.</span></span> 
    
- <span data-ttu-id="a7ccf-p114">**新的電子郵件伺服器**Office 365 雲端應用程式安全性電子郵件伺服器已變更，並使用不同的 IP 位址範圍。若要確定您可以取得通知，請將新的 IP 位址新增至反垃圾郵件 whitelist。自訂其通知的組織，雲端應用程式安全性會啟用這讓您使用 MailChimp、 協力廠商電子郵件服務。郵件伺服器 IP 位址及啟用使用 MailChimp 指示的清單，請參閱[網路需求 （Microsoft 雲端應用程式安全性）](https://docs.microsoft.com/cloud-app-security/network-requirements)和[郵件設定 （Microsoft 雲端應用程式安全性）](https://docs.microsoft.com/cloud-app-security/mail-settings)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p114">**New email server** The email server for Office 365 Cloud App Security has changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam whitelist. For organizations who customize their notifications, Cloud App Security enables this for you using MailChimp, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) and [Mail settings (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).</span></span>
    
## <a name="office-365-cloud-app-security-release-121"></a><span data-ttu-id="a7ccf-171">Office 365 雲端應用程式安全性版本 121</span><span class="sxs-lookup"><span data-stu-id="a7ccf-171">Office 365 Cloud App Security release 121</span></span>

<span data-ttu-id="a7ccf-172">*發行 2018 年 5 月 6、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-172">*Released May 6, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-173">在**下列[版本 121 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-173">**Following [Microsoft Cloud App Security release 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p115">**異常偵測原則增強功能**。Office 365 雲端應用程式安全性的異常偵測原則包含兩種新逐漸推出的威脅偵測已改善：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p115">**Anomaly detection policy improvements**. Office 365 Cloud App Security's anomaly detection policies have been improved to include two new types of threat detection that are gradually rolling out:</span></span> 
    
  - <span data-ttu-id="a7ccf-p116">**Ransomware 活動。** Ransomware 偵測功能已使用讓您更完整的涵蓋範圍針對複雜的 ransomware 攻擊異常偵測進行擴充。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p116">**Ransomware activity.** Ransomware detection capabilities are extended with anomaly detection to give you more comprehensive coverage against sophisticated ransomware attacks.</span></span> 
    
  - <span data-ttu-id="a7ccf-p117">**終止使用者活動。** 終止使用者活動可讓您要監視之人員可能會有已取消佈建從公司的應用程式，但誰可能仍終止的使用者帳戶具有特定公司資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p117">**Terminated user activity.** Terminated user activity enables you to monitor the accounts of terminated users who may have been de-provisioned from corporate applications, but who might still have access to certain corporate resources.</span></span> 
    
    <span data-ttu-id="a7ccf-180">若要檢視您[異常偵測原則](anomaly-detection-policies-in-ocas.md)中，在 Office 365 雲端應用程式安全性入口網站中，選擇 [**控制項**] \> **原則**。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-180">To view your [Anomaly detection policies](anomaly-detection-policies-in-ocas.md), in the Office 365 Cloud App Security portal, choose **Control** \> **Policies**.</span></span>
    
## <a name="office-365-cloud-app-security-release-120"></a><span data-ttu-id="a7ccf-181">Office 365 雲端應用程式安全性版本 120</span><span class="sxs-lookup"><span data-stu-id="a7ccf-181">Office 365 Cloud App Security release 120</span></span>

<span data-ttu-id="a7ccf-182">*發行 2018 年 4 月 22，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-182">*Released April 22, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-183">在**下列[版本 120 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-183">**Following [Microsoft Cloud App Security release 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p118">**為使用者活動的內部應用程式**。Office 365 和 Azure Active Directory (Azure AD)，我們會立即逐漸推出偵測內部應用程式為使用者帳戶活動的 Office 365 和 Azure AD 應用程式 （內部和外部） 所執行的功能。這可讓您建立原則來提醒您如果應用程式執行未預期和未經授權的活動。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p118">**Internal applications as user activities**. For Office 365 and Azure Active Directory (Azure AD), we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies to alert you if an application performs unexpected and unauthorized activities.</span></span> 
    
- <span data-ttu-id="a7ccf-p119">**匯出應用程式的權限清單中的多個欄位**。應用程式的權限清單匯出至 csv，例如發行者、 其他欄位時的權限層級和社群的使用方式是以協助的規範與調查有關的程序。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p119">**More fields in app permissions list export**. When exporting an app permissions list to csv, additional fields such as publisher, permissions level and community usage are included to assist with the compliance and investigation process.</span></span> 
    
## <a name="office-365-cloud-app-security-release-119"></a><span data-ttu-id="a7ccf-189">Office 365 雲端應用程式安全性版本 119</span><span class="sxs-lookup"><span data-stu-id="a7ccf-189">Office 365 Cloud App Security release 119</span></span>

<span data-ttu-id="a7ccf-190">*發行 2018 April 1，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-190">*Released April 1, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-191">在**下列[版本 119 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-191">**Following [Microsoft Cloud App Security release 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p120">**雲端探索的改善**。雲端探索提供讓更容易以檢視有關 Office 365 的使用狀況詳細資料和其他應用程式上的使用者和 IP 位址的詳細資訊。若要深入了解，請參閱[Office 365 雲端應用程式安全性檢閱應用程式探索偵測](review-app-discovery-findings-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p120">**Improvements to Cloud Discovery**. The Cloud Discovery provides more information about top users and IP addresses, making it easier to view usage details about Office 365 and other apps. To learn more, see [Review app discovery findings in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).</span></span>
    
    ![已更新雲端探索儀表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a><span data-ttu-id="a7ccf-196">Office 365 雲端應用程式安全性版本 118</span><span class="sxs-lookup"><span data-stu-id="a7ccf-196">Office 365 Cloud App Security release 118</span></span>

<span data-ttu-id="a7ccf-197">*發行 2018 年 3 月 18，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-197">*Released March 18, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-198">在**下列[版本 118 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-198">**Following [Microsoft Cloud App Security release 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p121">**Barracuda 支援**。雲端探索現在也支援 Barracuda F 系列防火牆和 Barracuda F 系列防火牆 web 記錄資料流。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p121">**Barracuda support**. Cloud Discovery now supports Barracuda F Series firewalls and Barracuda F-Series firewall web log streaming.</span></span> 
    
## <a name="office-365-cloud-app-security-release-117"></a><span data-ttu-id="a7ccf-201">Office 365 雲端應用程式安全性版本 117</span><span class="sxs-lookup"><span data-stu-id="a7ccf-201">Office 365 Cloud App Security release 117</span></span>

<span data-ttu-id="a7ccf-202">*發行 2018 年 3 月 6、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-202">*Released March 6, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-203">在**下列[版本 117 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-203">**Following [Microsoft Cloud App Security release 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p122">**i 篩選支援**。雲端探索現在也支援 i 篩選。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p122">**i-FILTER support**. Cloud Discovery now supports i-FILTER.</span></span> 
    
## <a name="office-365-cloud-app-security-release-116"></a><span data-ttu-id="a7ccf-206">Office 365 雲端應用程式安全性版本 116</span><span class="sxs-lookup"><span data-stu-id="a7ccf-206">Office 365 Cloud App Security release 116</span></span>

<span data-ttu-id="a7ccf-207">*發行 2018 年 2 月 18，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-207">*Released February 18, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-208">在**下列[版本 116 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-208">**Following [Microsoft Cloud App Security release 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p123">**異常偵測原則增強功能**。異常偵測原則中包括無法運用旅行活動可疑的 IP 位址從新案例型偵測與已增強了 Office 365 雲端應用程式安全性及多失敗的登入嘗試。自動啟用了新的原則，整個雲端環境提供的方塊 （英文） 威脅偵測。此外，新的原則會公開 Office 365 雲端應用程式安全性偵測引擎，可協助加速調查程序，包含持續威脅的詳細資料。若要深入了解，請參閱 Microsoft 雲端應用程式安全性，[取得即時行為上有無分析和異常偵測](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p123">**Anomaly detection policy enhancements**. Anomaly detection polices in Office 365 Cloud App Security were enhanced with new scenario-based detections including impossible travel, activity from a suspicious IP address and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Office 365 Cloud App Security detection engine, which can help speed up the investigation process and contain ongoing threats. To learn more, see the Microsoft Cloud App Security article, [Get instantaneous behavioral analytics and anomaly detection](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).</span></span>
    
- <span data-ttu-id="a7ccf-p124">**檢查點格式的記錄剖析器支援**。雲端探索記錄剖析器現在支援兩個額外的檢查點格式： XML 及 KPC。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p124">**Log parser support for Checkpoint formats**. The Cloud Discovery log parsers now support two additional Checkpoint formats: XML, and KPC.</span></span> 
    
## <a name="office-365-cloud-app-security-release-114"></a><span data-ttu-id="a7ccf-216">Office 365 雲端應用程式安全性版本 114</span><span class="sxs-lookup"><span data-stu-id="a7ccf-216">Office 365 Cloud App Security release 114</span></span>

<span data-ttu-id="a7ccf-217">*發行 2018 年 1 月 21，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-217">*Released January 21, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-218">在**下列[版本的 Microsoft 雲端應用程式安全性 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-218">**Following [Microsoft Cloud App Security release 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p125">**服務狀態**。您現在可以檢查目前的 Office 365 雲端應用程式安全性服務狀態移至**協助** \> **系統狀態**。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p125">**Service status**. You can now check the current Office 365 Cloud App Security service status by going to **Help** \> **System status**.</span></span> 
    
    ![按一下 [說明]\>檢視系統健康狀態的系統狀態](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- <span data-ttu-id="a7ccf-p126">**活動記錄檔的自訂查詢**。開始版本 114、 建立並儲存自訂查詢活動記錄檔中的功能已啟用逐步。自訂查詢可讓您建立可重複使用的深入了解調查的篩選範本。此外，建議的查詢已新增至提供的方塊 （英文） 調查範本來篩選您的活動及探索到的應用程式。建議的查詢包含自訂的篩選器以使用弱式加密，以及安全性風險識別如模擬活動、 管理員活動、 risky 非相容的雲端儲存應用程式、 企業應用程式的風險。使用建議的查詢當做起點、 依需要修改這些，然後將其儲存為新的查詢。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p126">**Custom queries for Activity log**. Beginning in version 114, the ability to create and save custom queries in the Activity log is rolling out gradually. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, suggested queries have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. Suggested queries include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. Use the suggested queries as a starting point, modify them as needed, and then save them as a new query.</span></span> 
    
## <a name="office-365-cloud-app-security-release-113"></a><span data-ttu-id="a7ccf-228">Office 365 雲端應用程式安全性版本 113</span><span class="sxs-lookup"><span data-stu-id="a7ccf-228">Office 365 Cloud App Security release 113</span></span>

<span data-ttu-id="a7ccf-229">*發行 2018 年 1 月 8、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-229">*Released January 8, 2018*</span></span> 
  
<span data-ttu-id="a7ccf-230">在**下列[版本 113 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-230">**Following [Microsoft Cloud App Security release 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p127">**記錄剖析器支援一般的格式**。雲端探索記錄剖析器現在則支援下列一般格式： LEEF、 CEF、 及 W3C。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p127">**Log parser support for generic formats**. The Cloud Discovery log parsers now support the following generic formats: LEEF, CEF, and W3C.</span></span> 
    
## <a name="office-365-cloud-app-security-release-112"></a><span data-ttu-id="a7ccf-233">Office 365 雲端應用程式安全性版本 112</span><span class="sxs-lookup"><span data-stu-id="a7ccf-233">Office 365 Cloud App Security release 112</span></span>

<span data-ttu-id="a7ccf-234">*發行 2017 年 12 月 24、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-234">*Released December 24, 2017*</span></span> 
  
<span data-ttu-id="a7ccf-235">在**下列[版本 112 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-235">**Following [Microsoft Cloud App Security release 112](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p128">**相關的獨到抽屜**。活動記錄檔中您現在已可存取相關的獨到抽屜按一下使用者名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p128">**Relevant insight drawer**. In the Activity log, you can now access the relevant insight drawer by clicking on a user name or IP address.</span></span> 
    
    ![按一下 [使用者名稱或 IP 位址來查看相關洞察力抽屜活動記錄檔中。](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- <span data-ttu-id="a7ccf-p129">**能夠檢視按一下多項活動**。在相關的獨到抽屜中，您可以按一下以檢視在所選活動的 48 小時內執行的所有活動的時鐘圖示。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p129">**Ability to view more activities with a click**. In the relevant insight drawer, you can click the clock icon to view all activities performed within 48 hours of a selected activity.</span></span> 
    
    ![在相關的見解抽屜中，您可以按一下 [查看所選活動的 48 小時內執行的活動的時鐘圖示](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- <span data-ttu-id="a7ccf-p130">**Juniper SRX 記錄剖析器增強功能**。改良功能已對 Juniper SRX 雲端探索記錄剖析器。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p130">**Log parser improvements for Juniper SRX**. Improvements were made to the Cloud Discovery log parser for Juniper SRX.</span></span> 
    
## <a name="office-365-cloud-app-security-release-111"></a><span data-ttu-id="a7ccf-244">Office 365 雲端應用程式安全性版本 111</span><span class="sxs-lookup"><span data-stu-id="a7ccf-244">Office 365 Cloud App Security release 111</span></span>

<span data-ttu-id="a7ccf-245">*發行 2017 年 12 月 10，*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-245">*Released December 10, 2017*</span></span> 
  
<span data-ttu-id="a7ccf-246">在**下列[版本 111 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-246">**Following [Microsoft Cloud App Security release 111](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p131">**時間篩選器增強功能**。時間篩選現在容易使用。若要存取時間篩選，檢視，例如活動記錄檔、 原則、 提醒、 使用 [進階] 檢視中的選擇 [篩選器的清單中的**日期**。然後選擇一個選項，例如之前、 之後，或在之間套用時間篩選。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p131">**Time filter improvements**. Time filters are now easier to use. To access a time filter, in a view, such as Activity log, Policies, Alerts, using the Advanced view, choose **Date** in the list of filters. Then choose an option, such as before, after, or in between to apply the time filter.</span></span> 
    
    ![使用日期篩選器來檢視資訊之前、 之後，或傳來的日期。](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## <a name="office-365-cloud-app-security-release-110"></a><span data-ttu-id="a7ccf-252">Office 365 雲端應用程式安全性版本 110</span><span class="sxs-lookup"><span data-stu-id="a7ccf-252">Office 365 Cloud App Security release 110</span></span>

<span data-ttu-id="a7ccf-253">*發行 2017 年 11 月 26*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-253">*Released November 26, 2017*</span></span> 
  
<span data-ttu-id="a7ccf-254">在**下列[版本 110 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-254">**Following [Microsoft Cloud App Security release 110](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p132">**現在通常可用的 SIEM 伺服器整合**。您的 SIEM 伺服器連線至 Office 365 雲端應用程式安全性。您可以立即傳送提醒與活動自動選擇的 SIEM 伺服器 SIEM 代理程式進行設定。請參閱[整合您 SIEM 的伺服器與 Office 365 雲端應用程式安全性](integrate-your-siem-server-with-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p132">**SIEM server integration now generally available**. Connect your SIEM server to Office 365 Cloud App Security. You can now send alerts and activities automatically to your SIEM server of choice by configuring SIEM Agents. See [Integrate your SIEM server with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
    
- <span data-ttu-id="a7ccf-p133">**更輕鬆地說明內容的存取**權。使用新的問號的右上角中，您現在已可存取 Office 365 雲端應用程式安全性入口網站的頁面中的 [從的說明內容。每個連結是即時線上、 採取了您所需要的資訊、 根據你所在的頁面。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p133">**Easier access to help content**. Using the new question mark in the upper right corner, you can now access the help content from within the pages of the Office 365 Cloud App Security portal. Each link is context-sensitive, taking you to the information you need, based on the page you're on.</span></span> 
    
- <span data-ttu-id="a7ccf-p134">**傳送意見反應**。使用笑臉中的右上角，可以從 Office 365 雲端應用程式安全性入口網站的每一頁立即傳送意見反應。這可讓您回報錯誤、 要求的新功能並直接與 Office 365 雲端應用程式安全性小組共用您的功能。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p134">**Send us feedback**. Using the smiley face in the upper right corner, you can now send feedback from every page of the Office 365 Cloud App Security portal. This enables you to report bugs, request new features and share your experience directly with the Office 365 Cloud App Security team.</span></span> 
    
## <a name="office-365-cloud-app-security-release-102"></a><span data-ttu-id="a7ccf-265">Office 365 雲端應用程式安全性版本 102</span><span class="sxs-lookup"><span data-stu-id="a7ccf-265">Office 365 Cloud App Security release 102</span></span>

<span data-ttu-id="a7ccf-266">*發行 2017 年 8 月 13、*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-266">*Released August 13, 2017*</span></span> 
  
<span data-ttu-id="a7ccf-267">在**下列[版本 102 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-267">**Following [Microsoft Cloud App Security release 102](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p135">**新的使用者將正在調查動作**啟用的向下鑽研新增層級至使用者調查。調查] 索引標籤上您可以將滑鼠指標移入活動、 user 或帳戶並將其套用做為篩選條件，並從該處，您可以檢視相關的活動或事件。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p135">**New user investigation actions** enable an added level of drill-down to user investigations. On an Investigate page, you can hover on an activity, user, or account and apply it as a filter, and from there, you can view related activities or events.</span></span> 
    
## <a name="office-365-cloud-app-security-release-100"></a><span data-ttu-id="a7ccf-270">Office 365 雲端應用程式安全性版本 100</span><span class="sxs-lookup"><span data-stu-id="a7ccf-270">Office 365 Cloud App Security release 100</span></span>

<span data-ttu-id="a7ccf-271">*發行 2017 年 7 月 17*</span><span class="sxs-lookup"><span data-stu-id="a7ccf-271">*Released July 17, 2017*</span></span> 
  
<span data-ttu-id="a7ccf-272">在**下列[版本 100 Microsoft 雲端應用程式安全性](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-272">**Following [Microsoft Cloud App Security release 100](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**:</span></span> 
  
- <span data-ttu-id="a7ccf-p136">**安全性副檔名**為新的儀表板其中您可以集中管理所有安全性延伸模組的 Office 365 雲端應用程式安全性，包括 API 權杖和 SIEM 代理程式。若要檢視安全性 extensions 儀表板，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p136">**Security extensions** is a new dashboard where you can centrally manage all your security extensions for Office 365 Cloud App Security, including API tokens and SIEM agents. To view the Security extensions dashboard, follow these steps:</span></span> 
    
1. <span data-ttu-id="a7ccf-p137">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p137">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="a7ccf-277">移至 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-277">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="a7ccf-278">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-278">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全性&amp;規範中心選擇提醒\>管理進階提醒\>移至 [進階安全性管理](media/9792b121-9cd4-4faa-a6e0-81cfab4bf2f2.png)
  
4. <span data-ttu-id="a7ccf-280">選擇 [**設定** \> **安全性延伸模組**。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-280">Choose **Settings** \> **Security extensions**.</span></span>
    
    ![在 ASM 入口網站中選擇 [設定\>安全性延伸模組](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- <span data-ttu-id="a7ccf-p138">**剖析的改善**。剖析機制雲端探索記錄檔中所做的改良。內部錯誤是大幅可能發生的。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p138">**Improved parsing**. Improvements were made in the Cloud Discovery log parsing mechanism. Internal errors are significantly less likely to occur.</span></span> 
    
- <span data-ttu-id="a7ccf-p139">**預期記錄格式**。雲端探索記錄檔的預期的記錄檔格式現在提供範例 Syslog 格式和 FTP 格式。</span><span class="sxs-lookup"><span data-stu-id="a7ccf-p139">**Expected log formats**. The expected log format for Cloud Discovery logs now provides examples for both Syslog format and FTP format.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="a7ccf-287">相關主題</span><span class="sxs-lookup"><span data-stu-id="a7ccf-287">Related topics</span></span>

[<span data-ttu-id="a7ccf-288">Office 365 雲端應用程式安全性說明內容</span><span class="sxs-lookup"><span data-stu-id="a7ccf-288">Office 365 Cloud App Security help content</span></span>](office-365-cas-help.md)
  
[<span data-ttu-id="a7ccf-289">推出 Office 365 雲端 App 安全性後的使用活動</span><span class="sxs-lookup"><span data-stu-id="a7ccf-289">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
  
[<span data-ttu-id="a7ccf-290">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="a7ccf-290">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

