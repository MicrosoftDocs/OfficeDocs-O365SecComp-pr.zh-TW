---
title: 資料遺失防護和 Microsoft 小組
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/01/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 您現在可以將 DLP 原則套用至 Microsoft 團隊聊天和管道。 請閱讀本文以深入瞭解其運作方式。
ms.openlocfilehash: 3792fd6919749510ea20d4ff84b0249b16165a9f
ms.sourcegitcommit: cc1b0281fa594cbb7c09f3e419df21aec9557831
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417395"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>資料遺失防護和 Microsoft 小組

> [!NOTE]
> 最近將資料遺失防護功能新增至 Microsoft 小組的 Office 365 E5 和 Office 365 高級規範。 若要深入瞭解功能可用性, 請參閱[office 365 服務說明: office 365 安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。

## <a name="overview-of-dlp-for-microsoft-teams"></a>適用于 Microsoft 小組的 DLP 概述

最近,[資料遺失防護](data-loss-prevention-policies.md)(DLP) 功能已擴充為包含 Microsoft 團隊。 如果您的組織有 DLP, 您現在可以定義原則, 以防止人員在 Microsoft 小組通道或聊天會話中共用敏感資訊。 以下是此保護運作方式的一些範例:

- **範例 1: 保護郵件中的敏感資訊**。 假設有人嘗試與客人 (外部使用者) 共用小組聊天或管道中的敏感資訊。 如果您已定義 DLP 原則以防止發生這種情況, 則會刪除具有傳送給外部使用者之敏感資訊的郵件。 這會根據 DLP 原則的設定方式, 自動在幾秒內進行。

    > [!NOTE]
    > 當使用者與在小組和管道中擁有[來賓存取](https://docs.microsoft.com/MicrosoftTeams/guest-access)權的使用者共用, 以及在會議和交談會話中有[外部存取](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)權的使用者時, DLP for Microsoft 團隊會封鎖敏感內容。 如果您[與商務用 Skype 搭配使用 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), 請記住, DLP for 團隊不會封鎖互通性或同盟交談會話中的郵件。

- **範例 2: 保護檔中的敏感資訊**。 假設有人嘗試與 Microsoft 小組頻道或聊天中的客人共用檔, 而且檔包含機密資訊。 如果您已定義 DLP 原則以防止發生這種情況, 則不會對這些使用者開啟檔。 請注意, 在這種情況下, 您的 DLP 原則必須包含 SharePoint 和 OneDrive, 才可進行保護。 (這是在 Microsoft 團隊中顯示的 DLP for SharePoint 的範例。)

## <a name="policy-tips-help-educate-users"></a>原則提示有助於教育使用者

與 DLP 在[Exchange、outlook 和 outlook 網頁](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)版、 [SharePoint 和商務用 OneDrive 網站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)及[Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)的運作方式類似, 當動作與 DLP 原則衝突時, 就會顯示原則提示。 以下是原則提示的範例:

![小組中的封鎖訊息通知](media/dlp-teams-blockedmessage-notification.png)

在這種情況下, 寄件者嘗試在 Microsoft 小組通道中共用社交安全性號碼。 **我可以做什麼？** link 開啟對話方塊, 為寄件者提供解決問題的選項。 請注意, 在此情況下, 寄件者可以選擇覆寫原則, 或通知系統管理員檢查並解決。

![解決被封鎖郵件的選項](media/dlp-teams-blockedmessage-possibleactions.png)

在您的組織中, 您可以選擇是否允許使用者覆寫 DLP 原則。 而且, 當您設定 DLP 原則時, 您可以使用預設原則提示, 或為您的組織[自訂原則提示](#to-customize-policy-tips)。 

回到我們的範例中, 寄件者在小組頻道中共用社交安全性號碼, 以下是收件者看到的內容:

![郵件被封鎖](media/dlp-teams-blockedmessage-notification-to-user.png)

[**這是什麼？** ] 連結會開啟有關 DLP 原則的[文章](data-loss-prevention-policies.md), 協助說明郵件被封鎖的原因。

### <a name="to-customize-policy-tips"></a>自訂原則提示

若要執行此工作, 您必須被指派有權編輯 DLP 原則的角色。 若要深入瞭解, 請參閱[許可權](data-loss-prevention-policies.md#permissions)。

1. 移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com)) 並登入。

2. 選擇 [**資料遺失防護** > **原則**]。 

3. 選取原則, 然後按一下 [**原則設定**] 旁的 [**編輯**]。

4. 請建立新的規則, 或編輯原則的現有規則。<br/>![編輯原則的規則](media/dlp-teams-editrule.png)<br/>

5. 在 [**使用者通知**] 索引標籤上, 選取 **[自訂電子郵件文字**] 和/或 **[自訂原則提示文字**選項]。<br/>![自訂使用者通知和原則提示](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 指定您要用於電子郵件通知和/或原則提示的文字, 然後選擇 [**儲存**]。 

7. 在 [**原則設定**] 索引標籤上, 選擇 [**儲存**]。

允許大約一小時的時間讓您的變更透過您的資料中心來運作, 並同步處理至使用者帳戶。
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>將 Microsoft 團隊新增為現有 DLP 原則的位置

若要執行此工作, 您必須被指派有權編輯 DLP 原則的角色。 若要深入瞭解, 請參閱[許可權](data-loss-prevention-policies.md#permissions)。

1. 移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com)) 並登入。

2. 選擇 [**資料遺失防護** > **原則**]。 

3. 選取原則, 並查看 [**位置**] 底下的值。 如果您看到**小組聊天和通道訊息**, 就是所有設定。 如果您沒有, 請按一下 [**編輯**]。<br/>![現有原則的位置](media/dlp-teams-editexistingpolicy.png)<br/>

4. 在 [**狀態**] 欄中, 針對**小組聊天和通道訊息**開啟原則。<br/>![適用于團隊聊天和管道的 DLP](media/dlp-teams-addteamschatschannels.png)<br/>

5. 保留所有帳戶的預設設定, 或指定要包含或排除的帳戶。

6. 按一下 [儲存]****。

允許大約一小時的時間讓您的變更透過您的資料中心來運作, 並同步處理至使用者帳戶。

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>為 Microsoft 團隊定義新的 DLP 原則

若要執行此工作, 您必須被指派有權編輯 DLP 原則的角色。 若要深入瞭解, 請參閱[許可權](data-loss-prevention-policies.md#permissions)。

1. 移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com)) 並登入。

2. 選擇 [**資料遺失防護** > **原則** > **+ 建立原則**]。 

3. 選擇[範本](data-loss-prevention-policies.md#dlp-policy-templates), 然後選擇 [**下一步]**。<br/>在我們的範例中, 我們選擇美國個人身分識別資訊資料範本。<br/>![DLP 原則的隱私權範本](media/dlp-teams-createnewpolicy-template.png)<br/>

4. 在 [**命名您的原則**] 索引標籤上, 指定原則的名稱和描述, 然後選擇 [**下一步]**。 

5. 在 [**選擇位置**] 索引標籤上, 保留 [所有位置] 的預設設定, 或選取 [**讓我選擇特定位置**], 然後選擇 [**下一步]**。<br/>如果您選擇選擇 [特定位置], 請選取 DLP 原則的位置, 然後選擇 [**下一步]**。<br/>![DLP 原則位置](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > 如果您想要確定包含機密資訊的檔未適當地共用, 請確定**SharePoint 網站**和**OneDrive 帳戶**已開啟, 以及**小組聊天和通道訊息**。
<br/>

6. 在 [**原則設定**] 索引標籤的 [**自訂您要保護的內容類型**] 下, 保留預設的簡單設定, 或選擇 [**使用高級設定**], 然後選擇 [**下一步]**。 如果您選擇 [高級設定], 您可以建立或編輯原則的規則。 (若要取得這一點的說明, 請參閱[簡易設定與高級設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。)

7.  在 [**原則設定**] 索引標籤的 [如果偵測到**敏感資訊, 您要執行什麼？**] 下, 複查設定。 (您可以在這裡選擇保留預設[原則提示和電子郵件通知](use-notifications-and-policy-tips.md), 或加以自訂)。<br/>![使用秘訣和通知的 DLP 原則設定](media/dlp-teams-policysettings-tipsemails.png)<br/>當您完成審閱或編輯設定時, 請選擇 **[下一步]**。

8. 在 [**原則設定**] 索引標籤的 [**您想要先開啟原則或測試內容嗎？**] 下, 選擇是否要開啟原則、[先測試](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)或保留 [關閉], 然後選擇 **[下一步]**。<br/>![指定是否要開啟原則](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. 在 [**檢查您的設定**] 索引標籤上, 檢查新原則的設定。 選擇 [**編輯**] 進行變更。 完成後, 請選擇 [**建立**]。 

針對您的新原則, 允許大約一小時的時間, 透過您的資料中心來進行, 並同步處理至使用者帳戶。

## <a name="related-articles"></a>相關文章

[建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)

[針對 DLP 原則傳送電子郵件通知並顯示原則提示](use-notifications-and-policy-tips.md)
