---
title: 資料外洩防護和 Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/26/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 您現在可以將 DLP 原則套用至 Microsoft 小組聊天和通道。 閱讀本篇文章以深入了解其運作方式。
ms.openlocfilehash: 712729972942d98afb5b3898ad357114ce1a6bae
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33367218"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>資料外洩防護和 Microsoft Teams

## <a name="overview-of-dlp-for-microsoft-teams"></a>DLP 對於 Microsoft Teams 概觀

最近，已擴充[資料外洩防護](data-loss-prevention-policies.md)(DLP) 功能，以包括 Microsoft Teams。 如果您的組織有 DLP，現在您可以定義共用 Microsoft Teams 通道或聊天室工作階段中的敏感資訊時，防止人員的原則。 以下是此保護的運作方式的一些範例：

- **範例 1： 保護郵件中的敏感資訊**。 假設有人嘗試來賓 （外部使用者） 與共用小組聊天或通道中的敏感資訊。 如果您有 DLP 原則定義要避免這種情況時，會刪除具有機密資訊傳送給外部使用者的郵件。 發生這種情況自動，並在秒內，根據您的 DLP 原則的設定方式。

- **範例 2： 保護文件中的敏感資訊**。 假設有人嘗試與 Microsoft Teams 通道或聊天室中的來賓共用文件和文件包含敏感資訊。 如果您有 DLP 原則定義要避免這種情況，這些使用者不會開啟文件。 請注意，在此情況下，您的 DLP 原則必須包括 SharePoint 和 OneDrive 設為就地保護的順序。

## <a name="policy-tips-help-educate-users"></a>原則提示協助教育使用者

類似於 DLP [Exchange、 Outlook 和 outlook 網頁版](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint 和 OneDrive for Business 網站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)以及[Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)中的運作方式，原則提示時出現巨集指令與 DLP 原則的衝突。 以下是範例的原則提示：

![Teams 中的已封鎖的郵件通知](media/dlp-teams-blockedmessage-notification.png)

在此情況下，寄件者會嘗試共用 Microsoft Teams 通道中社會安全號碼。 **我可以做什麼？** 連結會開啟一個對話方塊，提供解決問題，寄件者的選項。 請注意，在此情況下，寄件者可以選擇覆寫原則，或通知系統管理員檢視並加以解決。

![解決封鎖郵件的選項](media/dlp-teams-blockedmessage-possibleactions.png)

在您組織中，您可以選擇是否要允許使用者覆寫 DLP 原則，或不。 和，當您設定 DLP 原則時，您可以為您的組織使用的預設原則提示，或[自訂原則提示](#to-customize-policy-tips)。 

回到我們的範例，其中寄件者會共用中的小組通道，此處的社會安全號碼哪些收件者鋸：

![封鎖的郵件](media/dlp-teams-blockedmessage-notification-to-user.png)

**這是什麼？** 連結會開啟 [DLP 原則，這有助於說明為什麼已封鎖郵件的相關[文章](data-loss-prevention-policies.md)。

### <a name="to-customize-policy-tips"></a>若要自訂原則提示

若要執行這項工作，您必須獲指派的角色具有 [編輯 DLP 原則的權限。 若要深入了解，請參閱 <<c0>權限。

1. 移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。

2. 選擇 [**資料外洩防護** > **原則**。 

3. 選取原則，並旁**原則設定**，選擇 [**編輯**]。

4. 建立新規則，或編輯現有的原則規則。<br/>![編輯原則的規則](media/dlp-teams-editrule.png)<br/>

5. 在 [**使用者通知**] 索引標籤上選取 [**自訂電子郵件的文字**及/或**自訂原則提示文字**選項。<br/>![自訂使用者通知和原則提示](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 指定您想要用於電子郵件通知及/或原則提示的文字，然後選擇 [**儲存**。 

7. 在 [**原則設定**] 索引標籤中，選擇 [**儲存**]。

可讓您變更其透過您的資料中心和同步處理至使用者帳戶的方式運作大約一小時。
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>新增 Microsoft Teams 為現有的 DLP 原則的位置

若要執行這項工作，您必須獲指派的角色具有 [編輯 DLP 原則的權限。 若要深入了解，請參閱 <<c0>權限。

1. 移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。

2. 選擇 [**資料外洩防護** > **原則**。 

3. 選取原則]，然後查看 [**位置**] 下的值。 如果您看到**小組聊天和通道訊息**，就會是完成設定。 如果不這麼做，請按一下 [**編輯**]。<br/>![現有的原則的位置](media/dlp-teams-editexistingpolicy.png)<br/>

4. 在 [**狀態**] 欄中，開啟原則**小組聊天和通道訊息**。<br/>![DLP 小組聊天和通道](media/dlp-teams-addteamschatschannels.png)<br/>

5. 保留預設設定的所有帳戶，或指定要包含或排除哪一個帳戶。

6. 按一下 [儲存]****。

可讓您變更其透過您的資料中心和同步處理至使用者帳戶的方式運作大約一小時。

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>對於 Microsoft Teams 定義新的 DLP 原則

若要執行這項工作，您必須獲指派的角色具有 [編輯 DLP 原則的權限。 若要深入了解，請參閱 <<c0>權限。

1. 移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。

2. 選擇 [**資料外洩防護** > **原則** > **+ 建立原則**。 

3. 選擇[範本](data-loss-prevention-policies.md#dlp-policy-templates)，然後再選擇 [**下一步**。<br/>在我們的範例中，我們會選擇美國個人識別資訊的資料範本。<br/>![隱私權 DLP 原則範本](media/dlp-teams-createnewpolicy-template.png)<br/>

4. 在 [**您的原則名稱**] 索引標籤上指定的名稱和描述原則] 中，然後選擇 [**下一步**。 

5. 在 [**選擇位置**] 索引標籤中，保留預設設定的所有位置，或選取 [**讓我選擇特定位置**，，然後選擇**下一步**。<br/>如果您選擇選擇特定位置，選取您的 DLP 原則的位置，然後選擇 [**下一步**。<br/>![DLP 原則的位置](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > 如果您想要確定包含敏感資訊的文件不不當共用，請確定**SharePoint 網站**與**OneDrive 帳戶**已開啟，以及**小組聊天和通道訊息**。
<br/>

6. 在**原則設定**] 索引標籤的 [**自訂您要保護的內容類型**，簡單的設定，保留預設值或選擇**使用進階設定**]，然後選擇 [**下一步**。 如果您選擇 [進階的設定，您可以建立或編輯原則的規則。 （若要取得此問題的協助，請參閱[和進階設定比較簡單的設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)）。

7.  在 [**原則設定**] 索引標籤上 [**您想要執行動作如果偵測到機密資訊？**，檢閱設定。 （在這裡是您可以選擇保留預設[原則提示和電子郵件通知](use-notifications-and-policy-tips.md)，或加以自訂）。<br/>![秘訣與通知的 DLP 原則設定](media/dlp-teams-policysettings-tipsemails.png)<br/>當您完成檢閱或編輯設定時，選擇 [**下一步**]。

8. 在 [**原則設定**] 索引標籤上 [**您要開啟第一個原則或測試內容？**，選擇是否要開啟原則，[先進行測試](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)，或將它關閉，現在保存，然後選擇 [**下一步**。<br/>![指定是否要開啟原則](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. 在 [**檢閱您的設定**] 索引標籤中，檢閱您的新原則的設定。 選擇 [**編輯**] 以進行變更。 當您完成時，選擇 [**建立**]。 

允許大約一小時的您新的原則，以其透過您的資料中心和同步處理至使用者帳戶的方式運作。

## <a name="related-articles"></a>相關文章

[建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)

[針對 DLP 原則傳送電子郵件通知並顯示原則提示](use-notifications-and-policy-tips.md)
