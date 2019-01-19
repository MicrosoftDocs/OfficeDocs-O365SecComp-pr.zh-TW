---
title: 啟用報告訊息增益集
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: 了解如何啟用報表訊息增益集 Outlook 和 Outlook web 針對個別使用者或整個組織。
ms.openlocfilehash: 013145813e8feb3e7389f6248ee26195c1df3d08
ms.sourcegitcommit: 1169a5759b9c2336fbc89d4651daf29e556f62fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2019
ms.locfileid: "28727867"
---
# <a name="enable-the-report-message-add-in"></a>啟用報告訊息增益集

## <a name="overview"></a>概觀

報告訊息的增益集 Outlook 和 Outlook web 上的啟用人員輕鬆地回報被歸類電子郵件是否安全或惡意、 Microsoft 及分析及其子公司。Microsoft 使用這些送出改善電子郵件保護技術的有效性。此外，如果您的組織會使用[Office 365 進階威脅保護](office-365-atp.md)或[Office 365 威脅智慧](office-365-ti.md)、 報告郵件增益集提供實用的資訊可用於檢閱及更新您的組織安全性小組安全性原則。 

例如，假設人員會報告為網路釣魚許多的郵件。此資訊以循[安全性儀表板](security-dashboard.md)和其他報表中。貴組織的安全性小組可以使用這項資訊以反網路釣魚原則可能需要更新的指示。或者，如果人員所報告的郵件已標示為垃圾郵件郵件不是垃圾郵件報告增益集使用許多組織的安全性小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。 

報告郵件增益集的運作方式與您的 Office 365 訂閱及下列產品：
 - Outlook 網頁版
 - Outlook 2013 SP1
 - Outlook 2016
 - Mac 版 Outlook 2016
 - Office 365 ProPlus 所含的 outlook

> [!NOTE]
> 報告訊息的增益集 Outlook 和 Outlook web 上的是不完全相同兩回事[Outlook 垃圾郵件篩選](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)，但兩者都可以用來將電子郵件標示為垃圾郵件、 未垃圾郵件或網路釣魚嘗試。報告訊息的增益集 Outlook 和 Outlook web 上的而 Outlook 垃圾郵件篩選工具用來將組織中使用者信箱的電子郵件會被歸類電子郵件的相關通知 Microsoft。 
  
如果您是個別使用者，您還可以[讓報表訊息的增益集自己](#get-the-report-message-add-in-for-yourself)。 
  
如果您是 Office 365 全域管理員或 Exchange Online 管理員，而 Exchange 設定為使用 OAuth 驗證，您可以[啟用報表訊息增益集的組織](#get-and-enable-the-report-message-add-in-for-your-organization)。報告郵件增益集現在已可透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>您要報告郵件取得增益集

1. 在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)、 搜尋[報告郵件增益集](https://appsource.microsoft.com/product/office/wa104381180)。
    
2. 選擇 [**取得 IT 現在**。<br/>![報告訊息-立即取得](media/ReportMessageGETITNOW.png)<br/> 
    
3. 檢閱使用及隱私權原則的字詞。然後選擇 [**繼續]**。 
    
4. 登入 Office 365 中，使用您的工作或學校帳戶 （供商務使用） 或 Microsoft 帳戶 （適用於個人使用）。
    
增益集已安裝並啟用之後，您會看到下列圖示： 

- 在 Outlook 中，圖示外觀類似如下： <br/> ![報告郵件增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- 在 Outlook Web App （或 [網路上的 Outlook） 圖示外觀類似如下：<br/>![Outlook 郵件報告增益集的 web 圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 下一個步驟中，以了解如何[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>取得並啟用報表訊息增益集的組織

> [!IMPORTANT]
> 您必須是 Office 365 全域管理員或 Exchange Online 管理員，才可完成此工作。另外，Exchange 必須設定為使用 OAuth 驗證來深入了解，請參閱[Exchange 需求 （增益集的集中式部署）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。 

1. 前往 Microsoft 365 系統管理中心[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![在新的 Microsoft 365 系統管理中心服務與增益集] 頁面上](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. 選擇 [ **+ 部署增益集**。<br/>![選擇部署增益集](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. 在**新增益集**] 畫面上，檢閱資訊，並再選擇 [**下一步**。<br/>![新的增益集詳細資料](media/NewAddInScreen1.png)<br/>
    
4. 選取 [**我想要新增增益集來自 Office 市集**、，然後選擇 [**下一步**。<br/>![我想要新增新增益集](media/NewAddInScreen2.png)<br/> 
    
5. 搜尋**報表訊息**，並的結果旁的**報表訊息增益集**清單中，選擇 [**新增]**。<br/>![搜尋報告的郵件，然後選擇 [新增]](media/NewAddInScreen3.png)<br/>
    
6. 在**報表訊息**] 畫面上，檢閱資訊，然後選擇 [**下一步**。<br/>![報告郵件詳細資料](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. 指定 Outlook 使用者預設設定，然後選擇 [**下一步**。<br/>![報告 for Outlook 訊息預設設定](media/ReportMessageOptionsScreen5.png)<br/>

8. 指定誰取得報表訊息增益集] 中，然後選擇 [**儲存**。 <br/>![誰可以取得報表訊息增益集](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> 建議您[設定要取得一份報告的使用者的電子郵件的規則](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。

根據您選取的項目設定時的增益集 (步驟 7-8 上方)、 人員在組織中的有[報表訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)提供。在組織中的人員會看到下列圖示： 

- 在 Outlook 中，圖示外觀類似如下： <br/> ![報告郵件增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- 在 Outlook Web App （或 [網路上的 Outlook） 圖示外觀類似如下：<br/>![在 [網頁報表訊息增益集] 圖示上的 outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 當您通知使用者有關郵件報告增益集時，包含要[使用的報表訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>若要取得一份報告的使用者的電子郵件設定的規則

> [!IMPORTANT]
> 您必須是 Exchange Online 管理員，才能執行這項工作。
  
您可以設定以取得一份報告的組織中使用者的電子郵件的規則。下載並啟用的報告訊息增益集組織之後，您可以這麼做。
  
1. 在 Exchange 系統管理中心中，選擇 [**郵件流程** \> **規則**。 
    
2. 選擇 [ **+** \> **建立新的規則**。 
    
3. 在 [**名稱**] 方塊中輸入名稱，例如送出。
    
4. **如果套用此規則**] 清單中選擇 [**收件者的地址包含...**]。 
    
5. 在 [**指定單字或片語**] 畫面中，新增`junk@office365.microsoft.com`和`phish@office365.microsoft.com`，然後選擇 **[確定]**。<br/>![指定之規則的垃圾郵件] 及 [phish 電子郵件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. 在**執行下列動作...** ] 清單中，選擇 [ **[密件副本郵件到...**。 
    
7. 新增全域管理員、 安全性管理員及/或安全性讀者應該接收人員向 Microsoft 報告每個電子郵件訊息的複本並再選擇 **[確定]**。<br/>![新增全域或安全性管理員接收每個報告的郵件的複本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. 選取 [**此規則使用嚴重性層級的稽核**，然後選擇 [**中等**。 
    
9. [**選擇此規則模式**] 下選擇 [**強制執行**。<br/>![設定規則，以取得每個報告的郵件的複本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. 選擇 [**儲存**]。 
    
與備妥此規則，每當您組織中某人報告電子郵件訊息的報告訊息 」 增益集，使用您全域管理員、 安全性管理員及/或安全性讀取者會收到該郵件的複本。這項資訊可讓您設定或調整原則，例如[Office 365 ATP 安全連結](atp-safe-links.md)原則或[反垃圾郵件](anti-spam-protection.md)設定。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用報告郵件增益集

請參閱[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>檢閱或編輯報表訊息增益集設定

您可以檢閱並編輯報表訊息增益集在[服務 & 增益集] 頁面上](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)的預設設定。 

> [!IMPORTANT]
> 您必須是 Office 365 全域管理員或 Exchange Online 管理員，才可完成此工作。
    
1. 前往 Microsoft 365 系統管理中心[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![在新的 Microsoft 365 系統管理中心服務與增益集] 頁面上](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. 尋找並選取 [郵件報告增益集。<br/>![尋找並選取 [郵件報告增益集](media/FindReportMessageAddIn.png)<br/> 
    
3. 在報表訊息] 畫面上，檢閱並編輯設定最適合您的組織。<br/>![設定報表訊息增益集 (英文）](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a>相關主題

[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心](view-email-security-reports.md)

[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)

[使用瀏覽器安全性&amp;規範中心](use-explorer-in-security-and-compliance.md)
  

