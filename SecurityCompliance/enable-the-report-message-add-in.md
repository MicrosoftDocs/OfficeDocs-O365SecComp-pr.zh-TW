---
title: 啟用報告訊息增益集
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/26/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 瞭解如何針對個別使用者或整個組織啟用 Outlook 和 Outlook 網頁版的報告訊息增益集。
ms.openlocfilehash: d74772502f5ffd7e274574075604c2fc0c235f30
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077949"
---
# <a name="enable-the-report-message-add-in"></a>啟用報告訊息增益集

> [!NOTE]
> Outlook 和 outlook 網頁版的報告郵件增益集與[Outlook 垃圾郵件篩選器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)並不完全相同, 不過這兩者都可以用來將電子郵件標示為垃圾郵件, 而非垃圾郵件或網路釣魚企圖。 不同之處在于 Outlook 和 outlook 網頁版的報告訊息增益集會通知 Microsoft 有關 misclassified 電子郵件, 而 Outlook 垃圾郵件篩選器則是用來組織使用者信箱中的電子郵件訊息。 

## <a name="overview"></a>概觀

Outlook 和 Outlook 網頁版的報告訊息增益集可讓使用者輕鬆地向 Microsoft 及其子公司報告 misclassified 電子郵件, 以進行分析。 Microsoft 會使用這些提交來改善電子郵件保護技術的效能。 此外, 如果您的組織使用的是[Office 365 高級威脅防護計畫 1](office-365-atp.md)或[計畫 2](office-365-ti.md), 則報告郵件增益集會為貴組織的安全小組提供有用的資訊, 供您用來檢查及更新安全性原則。 

例如, 假設使用者將大量的郵件報告為網路釣魚。 [[安全性] 儀表板](security-dashboard.md)和其他報表中的此資訊。 您組織的安全小組可以使用此資訊, 表示可能需要更新反網路釣魚原則。 或者, 如果人員使用報告郵件增益集來報告大量以垃圾郵件表示為非垃圾郵件的郵件, 您組織的安全小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。 

報告郵件增益集可與您的 Office 365 訂閱及下列產品搭配使用:
 - Outlook 網頁版
 - Outlook 2013 SP1
 - Outlook 2016
 - Mac 版 Outlook 2016
 - Office 365 專業增強版隨附的 Outlook

您現有的網頁瀏覽器應該足以讓報告訊息增益集正常運作;不過, 如果您注意到增益集無法使用或無法如預期般運作, 請嘗試使用不同的瀏覽器。
  
如果您是個人使用者, 您可以[為自己啟用報告訊息增益集](#get-the-report-message-add-in-for-yourself)。 
  
如果您是 Office 365 全域系統管理員或 Exchange Online 系統管理員, 而且已將 Exchange 設定為使用 OAuth 驗證, 您可以[為您的組織啟用報告訊息增益集](#get-and-enable-the-report-message-add-in-for-your-organization)。 您現在可以透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)來使用報告訊息增益集。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>取得自己的報告訊息增益集

1. 在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)中, 搜尋[報告訊息增益集](https://appsource.microsoft.com/product/office/wa104381180)。
    
2. 選擇 [**立即取得**]。<br/>![報告訊息-立即取得](media/ReportMessageGETITNOW.png)<br/> 
    
3. 回顧使用條款和隱私權原則。 然後選擇 [**繼續**]。 
    
4. 使用您的工作或學校帳戶 (供商務用) 或您的 Microsoft 帳戶 (供個人使用) 登入 Office 365。
    
安裝並啟用增益集之後, 您會看到下列圖示: 

- 在 Outlook 中, 圖示如下所示: <br/> ![報告 Outlook 的郵件增益集圖示](media/OutlookReportMessageIcon.png)<br/>
- 在網頁版 Outlook (先前稱為 Outlook Web App) 中, 圖示看起來像這樣:<br/>![網頁上的 Outlook 報告訊息增益集圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 下一步, 瞭解如何[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>取得並啟用組織的報告訊息增益集

> [!IMPORTANT]
> 您必須是 Office 365 全域管理員或 Exchange Online 系統管理員, 才可完成此工作。 此外, 必須將 Exchange 設定為使用 OAuth 驗證來深入瞭解, 請參閱[exchange 需求 (增益集的集中式部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。 

1. 移至 Microsoft 365 系統管理中心的 [服務] [ [& 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![新 Microsoft 365 系統管理中心的 [服務和增益集] 頁面](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. 選擇 [ **+ 部署增益集**]。<br/>![選擇 [部署增益集]](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. 在 [**新增增益集**] 畫面中, 查看資訊, 然後選擇 [**下一步]**。<br/>![新的增益集詳細資料](media/NewAddInScreen1.png)<br/>
    
4. 選取 **[我想要從 Office 存放區新增增益集**], 然後選擇 [**下一步]**。<br/>![我想要新增增益集](media/NewAddInScreen2.png)<br/> 
    
5. 搜尋**報告訊息**, 並在結果清單中的**報告訊息增益集**旁, 選擇 [**新增**]。<br/>![搜尋報告訊息, 然後選擇 [新增]](media/NewAddInScreen3.png)<br/>
    
6. 在 [**報告訊息**] 畫面上, 查看資訊, 然後選擇 [**下一步]**。<br/>![報告訊息詳細資料](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. 指定 Outlook 的使用者預設設定, 然後選擇 [**下一步]**。<br/>![報告郵件的預設設定 Outlook](media/ReportMessageOptionsScreen5.png)<br/>

8. 指定誰可以取得報表郵件增益集, 然後選擇 [**儲存**]。 <br/>![誰可以取得報表訊息增益集](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> 建議[您設定規則, 以取得使用者所報告之電子](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)郵件的副本。

根據您在設定增益集時所選取的專案 (上述步驟 7-8), 您組織中的人員將會有可用的[報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。 您組織中的人員會看到下列圖示: 

- 在 Outlook 中, 圖示如下所示: <br/> ![報告 Outlook 的郵件增益集圖示](media/OutlookReportMessageIcon.png)<br/>
- 在網頁版 Outlook 中, 圖示看起來像這樣:<br/>![網頁上的 Outlook 報告訊息增益集圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 當您通知使用者有關報告訊息增益集時, 請包含[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>設定規則以取得使用者所報告的電子郵件的副本

> [!IMPORTANT]
> 您必須是 Exchange Online 系統管理員, 才可執行此工作。
  
您可以設定規則, 以取得組織中使用者所報告之電子郵件的副本。 您可以在下載並啟用組織的報告訊息增益集之後執行此動作。
  
1. 在 Exchange 系統管理中心中, 選擇 [**郵件流程** \> **規則**]。 
    
2. 選擇**+** \> [**建立新規則**]。 
    
3. 在 [**名稱**] 方塊中, 輸入名稱, 例如 [送出]。
    
4. 在 [**將此規則**套用至] 清單中, 選擇 [**收件者位址包含 ...**]。 
    
5. 在 [**指定字詞或片語**] 畫面中`junk@office365.microsoft.com` , `phish@office365.microsoft.com`新增和, 然後選擇 **[確定]**。<br/>![指定規則的垃圾郵件和網路釣魚電子郵件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. 在 [**執行下列**動作 ...] 清單中, 選擇 [**密件副本郵件為 ...**]。 
    
7. 新增全域管理員、安全性系統管理員和/或安全性讀者, 其應該會收到每個人員向 Microsoft 報告的電子郵件的副本, 然後選擇 **[確定]**。<br/>![新增全域或安全性系統管理員以接收每個報告的郵件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. 選取 [**使用嚴重性層級來審核這個規則**], 然後選擇 [**中**]。 
    
9. 在 **[選擇此規則的模式]** 下, 選擇 [**強制**]。<br/>![設定規則以取得每個報告的郵件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. 選擇 [**儲存**]。 
    
使用此規則時, 每當組織中的人員使用報告訊息增益集來報告電子郵件訊息時, 您的全域系統管理員、安全性管理員和/或安全性讀取者都會收到該郵件的複本。 此資訊可讓您設定或調整原則, 例如[Office 365 ATP 安全連結](atp-safe-links.md)原則或[反垃圾郵件](anti-spam-protection.md)設定。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>瞭解如何使用報告訊息增益集

請參閱[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>檢查或編輯報告郵件增益集的設定

您可以在 [[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上, 查看及編輯 [報告郵件] 增益集的預設設定。 

> [!IMPORTANT]
> 您必須是 Office 365 全域管理員或 Exchange Online 系統管理員, 才可完成此工作。
    
1. 移至 Microsoft 365 系統管理中心的 [服務] [ [& 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![新 Microsoft 365 系統管理中心的 [服務和增益集] 頁面](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. 尋找並選取 [報告訊息] 增益集。<br/>![尋找並選取報告郵件增益集](media/FindReportMessageAddIn.png)<br/> 
    
3. 在 [報告訊息] 畫面上, 視需要查看和編輯您組織的設定。<br/>![報告郵件增益集的設定](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a>相關主題

[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[在安全性&amp;與合規性中心中查看電子郵件安全性報告](view-email-security-reports.md)

[查看 Office 365 的報告高級威脅防護](view-reports-for-atp.md)

[在安全性&amp;與合規性中心使用 Explorer](use-explorer-in-security-and-compliance.md)
  

