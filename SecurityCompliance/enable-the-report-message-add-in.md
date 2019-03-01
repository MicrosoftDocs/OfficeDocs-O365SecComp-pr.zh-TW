---
title: 啟用報告訊息增益集
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何啟用報告訊息增益集以進行 Outlook 和 Outlook 個別使用者的 web 應用程式或整個組織。
ms.openlocfilehash: c184b7ac1baef297d65e6e93e4e7a085920d87b0
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341424"
---
# <a name="enable-the-report-message-add-in"></a>啟用報告訊息增益集

## <a name="overview"></a>概觀

報告訊息增益集以進行 Outlook 和網頁型 Outlook 讓人員能輕鬆地報告誤分類電子郵件是否安全或惡意，Microsoft 並分析其關係企業。Microsoft 使用這些提交來改善電子郵件保護技術的有效性。此外，如果您的組織使用[Office 365 進階威脅防護](office-365-atp.md)或[Office 365 威脅情報](office-365-ti.md)，報告訊息增益集提供有用的資訊可用於檢視並更新與貴組織的安全性小組安全性原則。 

例如，假設人員會回報為網路釣魚郵件許多。[安全性儀表板](security-dashboard.md)和其他報表中此資訊表面。貴組織的安全性小組可以使用這項資訊作為反網路釣魚原則可能需要更新指示。或者，如果人員所報告的郵件已標示為垃圾郵件為不是垃圾郵件報告訊息增益集使用很多，貴組織的安全性小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。 

報告訊息增益集的運作方式與您的 Office 365 訂閱和下列產品：
 - Outlook 網頁版
 - Outlook 2013 SP1
 - Outlook 2016
 - Mac 版 Outlook 2016
 - 隨附於 Office 365 專業增強版的 outlook

> [!NOTE]
> 報告訊息增益集以進行 Outlook 和 outlook 網頁版並不完全相同的動作為[Outlook 垃圾郵件篩選器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)中，雖然兩者都可以用來將電子郵件標示為垃圾郵件、 非垃圾郵件或網路釣魚嘗試。報告訊息增益集以進行 Outlook 和 outlook 網頁版通知 Microsoft 有關誤分類電子郵件，而 Outlook 垃圾郵件篩選器用來將組織中使用者信箱的電子郵件。 
  
如果您是個別使用者，您可以[啟用報告訊息增益集以進行自己](#get-the-report-message-add-in-for-yourself)。 
  
如果您是 Office 365 全域管理員或 Exchange Online 的系統管理員，而且 Exchange 設定為使用 OAuth 驗證，您可以[啟用報告訊息增益集以進行組織](#get-and-enable-the-report-message-add-in-for-your-organization)。報告訊息增益集目前已提供透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>取得報告訊息增益集自行

1. 在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)，搜尋[報告訊息增益集](https://appsource.microsoft.com/product/office/wa104381180)。
    
2. 選擇 [**取得現在 IT**。<br/>![報告訊息-立即取得](media/ReportMessageGETITNOW.png)<br/> 
    
3. 檢閱使用和隱私權原則中的條款。然後選擇 [**繼續]**。 
    
4. 登入 Office 365 中，使用您的工作或學校帳戶 （適用於商業用途） 或 Microsoft 帳戶 （供個人使用）。
    
增益集已安裝並啟用之後，您會看到下列圖示： 

- 在 Outlook 中，圖示看起來像這樣： <br/> ![報告訊息增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- 在 Outlook 中網頁 （原先稱為 Outlook Web App） 上，圖示看起來像這樣：<br/>![Outlook 網頁報告訊息增益集] 圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 下一個步驟中，以了解如何[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>取得並啟用報告訊息增益集為您的組織

> [!IMPORTANT]
> 您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員，才能完成此工作。此外，Exchange 必須設定為使用 OAuth 驗證來了解更多，請參閱[Exchange 需求 （的增益集的集中式部署）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。 

1. 移至 Microsoft 365 系統管理中心中的[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![服務與增益集] 頁面中新的 Microsoft 365 系統管理中心](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. 選擇 [ **+ 部署增益集**]。<br/>![選擇 [部署增益集](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. 在 [**新增益集**] 畫面中，請先檢閱資訊，，然後選擇 [**下一步**。<br/>![新的增益集詳細資料](media/NewAddInScreen1.png)<br/>
    
4. 選取 [**我想要將增益集從 Office 市集**，，然後選擇 [**下一步**。<br/>![我想要將新增益集](media/NewAddInScreen2.png)<br/> 
    
5. 搜尋**報告郵件**，並在旁的**報告訊息增益集**的結果清單中，選擇 [**新增]**。<br/>![搜尋報告的郵件，然後選擇 [新增]](media/NewAddInScreen3.png)<br/>
    
6. 在**報告郵件**畫面上，檢閱的詳細資訊，，然後選擇 [**下一步**。<br/>![報告訊息詳細資料](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. 指定 Outlook 使用者預設設定，然後選擇 [**下一步**。<br/>![報告適用於 Outlook 的郵件預設設定](media/ReportMessageOptionsScreen5.png)<br/>

8. 指定誰的報告訊息增益集] 中，然後選擇 [**儲存**。 <br/>![誰可以取得報告訊息增益集](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> 我們建議您[設定 「 可取得一份報告，讓使用者的電子郵件訊息的規則](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。

根據您選取的項目當您設定 「 增益集 (步驟 7-8 上方)，您組織中的人員會有[報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)可用。在您的組織中的人會看到下列圖示： 

- 在 Outlook 中，圖示看起來像這樣： <br/> ![報告訊息增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- 在 web 上 Outlook 中，圖示看起來像這樣：<br/>![Outlook Web 報告訊息增益集] 圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 當您通知使用者有關的報告訊息增益集時，包括[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>設定規則，以取得一份報告，讓使用者的電子郵件

> [!IMPORTANT]
> 您必須是 Exchange Online 系統管理員可執行此工作。
  
您可以設定規則，以取得一份報告的組織中使用者的電子郵件訊息。下載及組織啟用報告訊息增益集之後，您可以這麼做。
  
1. 在 Exchange 系統管理中心中，選擇 [**郵件流程** \> **規則**。 
    
2. 選擇 [ **+** \> **建立新的規則**。 
    
3. 在 [**名稱**] 方塊中，輸入名稱，例如提交。
    
4. 在 [**套用此規則情況**] 清單中，選擇 [**收件者的地址包含...**]。 
    
5. 在 [**指定單字或片語**] 畫面中，新增`junk@office365.microsoft.com`和`phish@office365.microsoft.com`，然後選擇 [**確定]**。<br/>![指定規則的垃圾郵件及釣魚程式電子郵件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. 在**執行下列動作...** ] 清單中，選擇 [ **[密件副本郵件到...**。 
    
7. 新增全域系統管理員、 安全性系統管理員和/或安全性讀取者應該接收人員回報給 Microsoft，每個電子郵件訊息的複本，然後選擇 [**確定]**。<br/>![新增的全域或安全性管理員，才能接收的每個報告的郵件複本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. 選取 [**此規則使用嚴重性層級的稽核**，然後選擇 [**中等**。 
    
9. 在 [**選擇此規則的模式**，選擇 [**強制執行**]。<br/>![設定規則，以取得每個報告的郵件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. 選擇 [**儲存**]。 
    
使用就地此規則，每當您的組織中的人員報告電子郵件訊息的報告訊息增益集，使用您全域系統管理員、 安全性系統管理員和/或安全性讀取者會收到該郵件的副本。這項資訊可以讓您設定或調整原則，例如[Office 365 ATP 安全連結](atp-safe-links.md)原則或您的[反垃圾郵件](anti-spam-protection.md)設定。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用報告訊息增益集

請參閱 <<c0>使用報告訊息增益集。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>檢視或編輯報告訊息增益集的設定

您可以檢閱並編輯報告訊息增益集[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上的預設設定。 

> [!IMPORTANT]
> 您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員，才能完成此工作。
    
1. 移至 Microsoft 365 系統管理中心中的[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![服務與增益集] 頁面中新的 Microsoft 365 系統管理中心](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. 尋找和選取的報告訊息增益集。<br/>![尋找和選取的報告訊息增益集](media/FindReportMessageAddIn.png)<br/> 
    
3. 報告郵件在畫面上，檢閱並編輯最適合貴組織的設定。<br/>![設定的報告訊息增益集](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a>相關主題

[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[檢視安全性中的電子郵件安全性報告&amp;合規性中心](view-email-security-reports.md)

[檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)

[使用檔案總管中的安全性&amp;合規性中心](use-explorer-in-security-and-compliance.md)
  

