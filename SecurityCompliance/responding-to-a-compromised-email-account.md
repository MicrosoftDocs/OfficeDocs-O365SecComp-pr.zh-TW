---
title: 對於 Office 365 遭入侵電子郵件帳戶的回覆
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何識別並回應中 Office 365 遭入侵電子郵件帳戶
ms.openlocfilehash: 3f64cd249a425cc098fc49f6e9bbbe1901c734de
ms.sourcegitcommit: 0a1ce1ac45672d1d98eb7dbcfd4f0179d9eb4509
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30412941"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>對於 Office 365 遭入侵電子郵件帳戶的回覆

**摘要**了解如何識別並回應中 Office 365 遭入侵電子郵件帳戶。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>什麼是 Office 365 入侵電子郵件帳戶？
存取 Office 365 信箱、 資料及其他服務，控制透過認證，例如使用者名稱和密碼或 pin 碼。 當某人非預期的使用者竊取這些認證時，被竊的認證會被視為遭到洩漏。 與其攻擊者可以為原始的使用者登入，並執行非法動作。
使用遭竊的認證，攻擊者可以存取使用者的 Office 365 信箱、 SharePoint 資料夾或使用者的 OneDrive 中的檔案。 常見的一個巨集指令會為原始的使用者傳送電子郵件給收件者同時組織內部和外部攻擊者。 當攻擊者電子郵件給外部收件者的資料時，這就稱為資料 exfiltration。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>徵狀遭入侵的 Office 365 電子郵件帳戶
使用者可能會注意到，並報告其 Office 365 信箱中的異常活動。 以下是部分常見徵狀：
- 可疑活動，例如遺失或已刪除的電子郵件。
- 其他使用者可能會收到沒有對應的電子郵件的寄件者的**寄件備份**] 資料夾中現有的電子郵件遭入侵的帳戶。
- 未預期的使用者或系統管理員所建立的收件匣規則的目前狀態。 這些規則可能會自動未知的地址將電子郵件轉寄或將它們移至 [**備忘稿**、**垃圾郵件**或**RSS 訂閱**] 資料夾。
- 全域通訊清單中，可能會變更使用者的顯示名稱。
- 使用者的信箱會封鎖而無法傳送電子郵件。
- 在 Microsoft Outlook 或網頁 （先前稱為 Outlook Web App） 中的寄件備份] 或 [刪除的項目資料夾包含常見的駭客入侵帳戶訊息，例如 「 我已經卡在倫敦，傳送金錢。 」
- 已更新不尋常的設定檔的變更，例如名稱、 電話號碼或的郵遞區號。
- 必須要有不尋常的認證變更，例如多項密碼變更。
- 近期新增郵件轉寄。
- 近期新增不尋常的簽章，例如假銀行業簽章或預防措施藥物簽章。

如果使用者回報任何上述徵狀，您應該執行進一步調查。 Office 365 安全性 & 規範中心和 Azure 入口網站提供的工具，以協助您調查的使用者帳戶，您懷疑可能遭到洩漏活動。
- Office 365 中的安全性 & 合規性中心-的統一稽核記錄來檢閱可疑帳戶的所有活動篩選日期範圍跨越從可疑的活動所發生的目前日期之前的結果。 不要在搜尋期間篩選活動。
- 使用 Azure AD 登入記錄檔和 Azure AD 入口網站中提供其他風險報表。 檢查這些資料行中的值：
    - 檢閱 IP 位址
    - 登入位置
    - 登入時間
    - 登入成功或失敗

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>如何保護及還原至可疑的電子郵件函數危害 Office 365 帳戶和信箱

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使您已下列存取您的帳戶之後，攻擊者可能已新增後門項目，可讓攻擊者能夠繼續帳戶的控制權。

您必須執行所有下列步驟，因為您帳戶的存取權以確保不會繼續 hijacker 好更快速地控制您的帳戶。 下列步驟可協助您移除任何 hijacker 可能已新增至您的帳戶的上一步門項目。 您執行這些步驟之後，我們建議您執行病毒掃描，以確定您的電腦未遭到盜用。

### <a name="step-1-reset-the-users-password"></a>步驟 1 重設使用者的密碼
> [!WARNING]
> 為攻擊者仍有權存取信箱此時請不要給預定透過電子郵件使用者傳送新密碼。

1. 人員遵循重設 Office 365 商務版密碼中的其他程序[系統管理員： 重設 Office 365 商務版密碼](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**附註：**
- 請確定已強式密碼，而且它包含大小寫字母、 至少一個數字和至少一個特殊字元。 
- 不要重複使用的前 5 的密碼。 即使密碼歷程記錄需求可讓您重複使用較新的密碼，您應該選取某個項目無法猜測攻擊者。
- 如果您的內部部署身分識別與 Office 365 同盟，您必須變更密碼內部，，然後您必須通知您的系統管理員的危害。

> [!TIP]
> 強烈建議您在才能避免遭到入侵，特別是針對具有系統管理權限的帳戶啟用多重要素驗證 (MFA)。  您可以深入[以下](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步驟 2 移除可疑的電子郵件轉寄地址
1. 開啟**Office 365 系統管理中心 > 作用中的使用者**。
2. 找出有問題的使用者帳戶，並依序展開 [**郵件設定**。
3. **電子郵件轉寄**，按一下 [**編輯**]。
4. 移除任何可疑的轉寄地址。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步驟 3 停用任何可疑的收件匣規則
1. 登入使用者的信箱使用網頁型 Outlook。
2. 按一下 [] 齒輪圖示，然後按一下 [**郵件**。
3. 按一下 [**收件匣與整理規則**，然後檢閱規則。
4. 停用或刪除可疑的規則。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步驟 4 解除封鎖傳送給郵件使用者
如果可疑遭入侵的信箱非法用來傳送垃圾郵件，很可能信箱已封鎖而無法傳送郵件。
1. 若要解除封鎖無法傳送郵件的信箱，請遵循中[移除使用者、 網域或 IP 位址從封鎖清單後傳送的垃圾郵件](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )的程序。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步驟 5 可省略： 封鎖從登入的使用者帳戶
> [!IMPORTANT]
> 您可以封鎖可疑洩漏的帳戶，您可以從簽章中直到您認為才能安全地重新啟用存取。

1. Go to the Office 365 admin center.
2. 在 Office 365 系統管理中心中，選取 [**使用者**]。
3. 選取您要封鎖的員工，然後選擇 [使用者] 窗格中的 [**登入狀態**] 旁的 [**編輯**
4. 在 [**登入狀態**] 窗格中，選擇 [**登入封鎖**，然後**儲存**。 
5. 在 Office 365 系統管理中心中，在左下角瀏覽窗格中，展開 [**系統管理中心**，選取 [ **Exchange]**。
6. 在 Exchange 系統管理中心中，瀏覽至 [**收件者 > 信箱**。
7. 選取使用者，使用者屬性] 頁面上的 [**行動裝置**] 中，按一下 [**停用 Exchange ActivcSync**並**停用裝置用 OWA**並回答 **[是]** 這兩種。
8. 在 [**電子郵件連線**、**停用**並回答 **[是]**。 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步驟 6 選用： 從所有系統管理角色群組中移除可疑洩漏的帳戶
> [!NOTE]
> 受保護的帳戶之後，就可以還原系統管理角色群組成員資格。

1. 登入 Office 365 系統管理中心以全域管理員帳戶，並開啟**作用中的使用者**。
2. 尋找可疑的危害帳戶及手動檢查看看是否有任何管理角色指派給帳戶。
3. 開啟**安全性 & 合規性中心**。
4. 按一下 [**權限**。
5. 以手動方式檢視角色群組，以查看可疑危害帳戶是否其中的任何成員。  如果是：。 按一下 [角色群組，然後按一下 [**編輯角色群組**。
    b. 按一下 [**選擇成員**和**編輯**以移除角色群組的使用者。
6. 開啟**Exchange 系統管理中心**
7. 按一下 [**權限**。
8. 以手動方式檢視角色群組，以查看可疑危害帳戶是否其中的任何成員。 如果是：。 按一下 [角色群組，然後按一下 [**編輯**]。
    b. 若要移除的角色群組的使用者使用 [**成員**] 區段。

### <a name="step-7-optional-additional-precautionary-steps"></a>步驟 7 可省略： 額外的預防步驟
1. 請務必確認您已傳送的項目。 您可能要通知您的連絡人清單上的人您的帳戶遭到盜用了。 攻擊者可能已要求他們金錢，詐騙，例如擱淺在不同的國家/地區中，且需要金錢，或攻擊者可能會將傳送給他們也挾套裝軟體病毒。
2. 任何其他服務，其備用電子郵件帳戶可能已遭入侵作為此 Exchange 帳戶。 首先，Office 365 訂用帳戶，執行下列步驟，然後再執行這些步驟的其他帳戶。
3. 請確定您的連絡人資訊，例如電話號碼及地址正確無誤。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>保護 Office 365 專業 cybersecurity 像
Office 365 訂閱隨附一組功能強大的安全性功能，可用來保護您的資料和您的使用者。  使用[Office 365 安全性藍圖： 前的 30 天、 前 90 天及過後](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法為保護您的 Office 365 租用戶。
- 若要在第一個 30 天內完成的工作。  這些有直接影響，而低影響您的使用者。
- 若要在 90 天內完成的工作。 這些較多要花時間規劃及實作，但是大幅改善您的安全性狀態。
- 超過 90 天。 這些增強功能建立您第一張 90 天的工作。

## <a name="see-also"></a>另請參閱：
- [Office 365 的安全性最佳做法](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊](detect-and-remediate-outlook-rules-forms-attack.md)
- [網際網路犯罪抱怨中心](http://www.ic3.gov/preventiontips.aspx)
- [證券與 Exchange 委員會 「 網路釣魚 「 詐騙](http://www.sec.gov/investor/pubs/phishing.htm)
