---
title: 從受限制的使用者入口網站中移除使用者之後傳送的垃圾郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果使用者持續傳送電子郵件從 Office 365 歸類為垃圾郵件，他們將會傳送任何更多的郵件限制。
ms.openlocfilehash: c775887ecfa136bd638d0b76050c7882a6219ae4
ms.sourcegitcommit: f86383dcb9c52352661d51b22617f1809445beaa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/14/2019
ms.locfileid: "30573517"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>從受限制的使用者入口網站中移除使用者之後傳送的垃圾郵件

如果使用者持續傳送電子郵件從 Office 365 歸類為垃圾郵件，他們會被限制傳送輸出任何更多的郵件。 使用者會列在 [為不正確的輸出寄件者的服務，並將會收到未傳遞回報 (NDR) 表示：

- 無法傳遞郵件，因為未辨識為有效的寄件者。 最常見原因是您的電子郵件地址可疑的傳送垃圾郵件，且不再具有允許傳送組織以外的郵件。 請連絡您的電子郵件系統管理員以尋求協助。 遠端伺服器傳回 550 5.1.8 拒絕存取，不正確的輸出寄件者 」

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

預估完成時間：5 分鐘
  
您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要哪些權限，請參閱 「 反垃圾郵件中的項目[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題。

您也可以透過遠端 PowerShell 執行下列程序。 使用 Get-BlockedSenderAddress 指令程式來取得受限的使用者和移除 BlockedSenderAddress 若要移除限制的清單。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>移除封鎖的 Office 365 電子郵件帳戶的限制

在您完成在 Office 365 安全性 & 合規性中心 (SCC) 此工作。 如需詳細資訊 SCC [[移至 Office 365 安全性 & 合規性中心](go-to-the-securitycompliance-center.md)]。 您必須是在**組織管理**」 或 「**安全性系統管理員**角色群組中，才能執行這些功能。 如需詳細資訊 SCC 角色群組的 [[移至 Office 365 安全性 & 合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)]。

1. 使用公司或學校帳戶具有 Office 365 全域系統管理員權限，登入 Office 365 安全與規範中心和在左側清單中，展開 [**威脅管理**，選擇 [**檢閱**，，然後選擇 [**限制使用者**。
    
    > [!TIP]
    > 若要直接前往**受限的使用者**」 （前身為重要訊息中心） 安全性&amp;合規性中心，使用下列 URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此頁面將包含已封鎖而無法傳送郵件給組織外的使用者清單。  尋找您想要移除限制上，然後按一下**解除封鎖**使用者。

3. 飛出視窗就會進入其傳送屬於受限帳戶的相關詳細資料。 您應經過建議，以確定您採取適當的動作，以防帳戶實際上入侵。 按 [**下一步**完成。

4. 下一個畫面中有建議，以協助防範未來的危害。 啟用多重要素驗證 (MFA) 和變更密碼是很好的防護。 按一下 **[解除封鎖使用者**完成。

5. 按一下 [ **]** 確認變更。

    > [!NOTE]
    > 可能需要 30 分鐘，限制會移除前。 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>確定發生這種情況時，會收到通知系統管理員

租用戶系統管理員也會收到警告指出受限已傳送任何其他輸出的郵件使用者。 它是預設警示，會提供給所有承租人，而列在 SCC 警示原則] 頁面上，標題為 「 限制使用者無法傳送電子郵件 」。 請移至[Office 365 安全性 & 合規性中心中的警示原則](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)如需詳細資訊的警示。

## <a name="for-more-information"></a>相關資訊

[回應遭入侵電子郵件帳戶](responding-to-a-compromised-email-account.md)

[了解使用者傳送電子郵件警示限制](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md)

[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)
