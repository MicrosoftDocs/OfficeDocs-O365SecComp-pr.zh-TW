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
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何將能辨識和回應 Office 365 的入侵的電子郵件帳戶
ms.openlocfilehash: 6692c63d6cf349af3f3debea10251880d8d1e16c
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223402"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>對於 Office 365 遭入侵電子郵件帳戶的回覆

**摘要**了解如何辨識與回應中 Office 365 的入侵的電子郵件帳戶。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>什麼是 Office 365 危害電子郵件帳戶？
存取 Office 365 信箱、 資料及其他服務、 控制透過認證，例如使用者名稱及密碼或 PIN。當某人以外的預定使用者竊取所需的認證時，會視為竊的認證遭到洩漏。與這些攻擊者可以原始的使用者身分登入，並執行非法動作。使用竊的認證，請攻擊者可以存取使用者的 Office 365 信箱、 SharePoint 資料夾或檔案在使用者的 OneDrive。一個巨集指令一般呈現為原始使用者的電子郵件傳送給內部和外部組織的收件者攻擊。當攻擊者電子郵件電子郵件資料給外部收件者時，這會呼叫資料 exfiltration。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>徵狀之洩漏的 Office 365 電子郵件帳戶
使用者可能會注意到並報告在 Office 365 信箱不尋常的活動。以下為部分常見徵狀：
- 可疑的活動，例如遺失或已刪除的電子郵件。
- 其他使用者可能會收到電子郵件從洩漏的帳戶沒有對應的寄件者**傳送的項目**] 資料夾中現有的電子郵件。
- 未預期的使用者或系統管理員所建立的收件匣規則的目前狀態。這些規則可能會自動轉寄未知的地址的電子郵件或將其移至的**註解**、**垃圾郵件**或**RSS 訂閱**的資料夾。
- 全域通訊清單中，可能會變更使用者的顯示名稱。
- 使用者的信箱會禁止傳送電子郵件。
- 在 Microsoft Outlook 或 Outlook web （前身為 Outlook Web App） 上的寄件備份或刪除的郵件資料夾包含一般駭客入侵帳戶訊息，例如"I 倫敦、 傳送 money 中前"。
- 已更新不尋常的設定檔的變更，例如名稱、 電話號碼或的郵遞區號。
- 不尋常的認證的變更，例如多項的密碼變更是必要的。
- 最近新增郵件轉寄。
- 最近新增不尋常的簽章，例如假銀行業簽章或解決方法藥物簽章。

如果使用者回報任何上述徵狀，您應該執行進一步調查。Office 365 安全性 & 規範中心和 Azure 入口網站提供工具來協助您調查的使用者帳戶的懷疑可能遭到洩漏活動。
- Office 365 整合稽核記錄檔中安全性 & 規範中心-檢閱可疑帳戶的所有活動篩選的日期範圍跨越來自可疑活動發生為目前日期之前的結果。不要在搜尋期間篩選活動。
- 使用 Azure AD 登入記錄檔和其他 Azure AD 入口網站中可用的風險報告。檢查這些資料行中的值：
    - 檢閱 IP 位址
    - 登入位置
    - 登入時間
    - 登入成功或失敗

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>如何保護及還原至可疑的電子郵件函數危害 Office 365 帳戶和信箱

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使您已經下列存取您的帳戶後，攻擊者可能會有新增後門項目可讓攻擊者能夠繼續帳戶的控制權。

您必須執行所有下列步驟來重新存取您的帳戶以確保不會繼續 hijacker 搭配成效更快控制您的帳戶。下列步驟可協助您移除 hijacker 可能已新增至您的帳戶的任何後門項目。您執行這些步驟之後，建議您執行以確定您的電腦不危害病毒掃描。

### <a name="step-1-reset-the-users-password"></a>步驟 1 重設使用者密碼
> [!WARNING]
> 當攻擊者仍有權存取信箱此時請不要預定使用者透過電子郵件傳送的新密碼。

1. 請重設 Office 365 商務密碼執行某人的其他人的程序的[Admins： 重設 Office 365 商務密碼](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**附註：**
- 請確定密碼強式而且它包含小寫字母、 至少一個數字及至少一個特殊字元。 
- 不要重複使用任何上次五個的密碼。即使密碼歷程記錄需求可讓您重複使用最近的密碼，您應該選取的攻擊者無法猜測的某個項目。
- 如果您的內部識別同盟與 Office 365，您必須變更密碼內部，然後您必須通知您的危害的管理員。

> [!TIP]
> 強烈建議您啟用多重要素驗證 (MFA) 若要防止危害，特別適用於具有系統管理權限的帳戶。 您可以深入了解[以下](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步驟 2 移除可疑的電子郵件轉寄地址
1. 開啟**Office 365 系統管理中心 > 作用中使用者**。
2. 尋找有問題的使用者帳戶並依序展開 [**郵件設定**。
3. **電子郵件轉寄**，請按一下 [**編輯**]。
4. 移除任何可疑轉寄地址。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步驟 3 停用任何可疑的收件匣規則
1. 登入使用者的信箱使用網路上的 Outlook。
2. 齒輪圖示上按一下 [並按一下 [**郵件**]。
3. 按一下 [**收件匣及延伸的規則**並檢閱的規則。
4. 停用或刪除可疑的規則。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步驟 4 解除使用者傳送郵件
如果可疑洩漏的信箱用以非法垃圾電子郵件傳送，很可能信箱已被禁止傳送郵件。
1. 若要解除封鎖從傳送郵件的信箱，請遵循中[移除使用者、 網域或 IP 位址從封鎖清單之後傳送垃圾電子郵件](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )的程序。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步驟 5 選用： 封鎖從登入的使用者帳戶
> [!IMPORTANT]
> 您可以封鎖從登入直到您認為放心地重新啟用存取可疑入侵的帳戶。

1. 移至 Office 365 系統管理員中心。
2. 在 Office 365 系統管理中心中，選取 [**使用者**]。
3. 選取您要封鎖、 員工，然後選擇 [使用者] 窗格中的 [**登入狀態**] 旁的 [**編輯**
4. 在 [**登入狀態**] 窗格中，選擇 [**登入封鎖**，然後**儲存**。 
5. 在 Office 365 系統管理中心，左下功能窗格中，依序展開 [**管理中心**並選取 [ **Exchange**。
6. 在 Exchange 系統管理中心中，瀏覽至 [**收件者 > 信箱**。
7. 選取使用者、 使用者屬性] 頁面上的 [**行動裝置**，按一下 [**停用 Exchange ActivcSync**和**停用裝置的 OWA**和回答**皆**為兩者。
8. [**電子郵件連線**、**停用**和答覆 **[是]**。 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步驟 6 選用： 從所有系統管理角色群組中移除可疑洩漏的帳戶
> [!NOTE]
> 保護帳戶之後可以還原系統管理角色群組成員資格。

1. Office 365 系統管理中心以全域管理員帳戶登入並開啟 [**作用中使用者**。
2. 尋找可疑危害帳戶及手動檢查是否有任何系統管理角色指派給帳戶。
3. 開啟**安全性 & 規範中心**。
4. 按一下 [**權限**。
5. 手動檢閱查看如果可疑危害帳戶屬於其中的任何角色群組。 如果是： a 按一下角色群組並按一下 [**編輯角色群組**。 b.按一下 [**選擇成員**與**編輯**若要從角色群組移除使用者。
6. 開啟**Exchange 系統管理中心**
7. 按一下 [**權限**。
8. 手動檢閱查看如果可疑危害帳戶屬於其中的任何角色群組。如果是： a 按一下角色群組並按一下 [**編輯**]。 b.從角色群組移除使用者使用 [**成員**] 區段中。

### <a name="step-7-optional-additional-precautionary-steps"></a>步驟 7 選用： 其他預防步驟
1. 請確定您確認您已傳送的項目。您必須通知您的帳戶已危害的連絡人清單上的人員。攻擊者可能會有系統要求他們的 money、 詐騙、 例如擱淺在不同的國家/地區及所需 money，或攻擊者可能會將傳送給他們也劫持其電腦病毒。
2. 任何其他服務為其替代電子郵件帳戶已遭洩露用此 Exchange 帳戶。首先，執行下列步驟在 Office 365 訂閱，然後為其他帳戶執行這些步驟。
3. 請確定您的連絡人資訊，例如電話號碼和地址正確。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>安全 like cybersecurity 專業人員的 Office 365
您的 Office 365 訂閱隨附一組功能強大的安全性功能可用來保護您的資料與您的使用者。 使用[Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法保護您的 Office 365 租用戶。
- 若要完成工作前 30 天的工作。 這些包含立即影響且為 low 影響您的使用者。
- 若要完成 90 天的工作。這些需要規劃和實作但大幅改善了安全性狀態的更多時間。
- 超過 90 天。您在第一個 90 天工作建立這些增強功能。

## <a name="see-also"></a>另請參閱：
- [Office 365 的安全性最佳做法](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊](detect-and-remediate-outlook-rules-forms-attack.md)
- [網際網路犯罪抱怨中心](http://www.ic3.gov/preventiontips.aspx)
- [美國證券業 and Exchange 委員會"網路釣魚"詐騙](http://www.sec.gov/investor/pubs/phishing.htm)
