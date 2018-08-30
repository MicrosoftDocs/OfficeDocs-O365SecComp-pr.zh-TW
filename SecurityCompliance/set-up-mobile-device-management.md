---
title: 設定設定行動裝置管理 (MDM) in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: Office 365 內建的行動裝置管理可協助您保護及管理使用者的行動裝置 Iphone、 Ipad、 Androids、 like 及 Windows 電話。若要開始，請遵循下列步驟啟動及設定 Office 365 的行動裝置管理。
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272358"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a>設定設定行動裝置管理 (MDM) in Office 365

內建行動裝置管理 (MDM) for Office 365 可協助您保護及管理使用者的行動裝置 Iphone、 Ipad、 Androids、 like 及 Windows 電話。您可以建立和管理裝置安全性原則、 遠端裝置，並檢視裝置詳細的報告。
  
有問題嗎？我們已放入一起[協助地址的一般問題解答常見問題集](frequently-asked-questions-about-mdm.md)。請注意您無法使用[協力廠商： 優惠委派管理](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)來管理行動裝置管理 Office 365。 
  
裝置管理屬於安全性&amp;規範中心讓您需要那里前往開始進行的 MDM 安裝程式。
  
若要設定行動裝置管理的 Office 365 您需要：
  
1. [啟動 [行動裝置管理服務](#activate-the-mobile-device-management-service)  
2. [設定行動裝置管理](#set-up-mobile-device-management)
3. [請確定使用者註冊其裝置](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a>啟動 [行動裝置管理服務

1. 以您的工作或學校帳戶登入 Office 365。 
    
2. 移至 [[安全性&amp;規範中心](https://protection.office.com)。
    
3. 瀏覽至 [**資料外洩防護** \> **裝置管理**並按一下 [**我們開始吧**開始進行的啟用程序。 
    
    ![針對 Office 365 設定行動裝置管理](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. 我們建立預設的安全性原則來幫助您開始。更新] 頁面上的安全性原則名稱] 和 [**啟動安裝程式**。
    
    ![設定行動裝置管理安全性原則](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. 您會看見顯示進度設定服務的 [安裝] 畫面。
    
    ![MDM 安裝進度](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> 您也可以找到**MDM 安裝程式**透過搜尋。在 Office 365 系統管理中心\>**首頁**] 索引標籤類型的行動裝置管理的**搜尋**方塊中。>![搜尋系統管理中心中的行動裝置管理](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)
  
它可以花一些時間來啟動的 Office 365 的行動裝置管理，但其完成時，將會收到電子郵件的說明所採取的下一個步驟。
  
## <a name="set-up-mobile-device-management"></a>設定行動裝置管理

準備好服務時，請完成下列四個步驟以完成安裝程式。您可能需要在 [安全性]**裝置管理**] 頁面上的 [[管理設定](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx)&amp;規範中心來查看下列設定值。 
  
![設定行動裝置管理必要和建議的步驟](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a>步驟 1： MDM （必要） 設定網域

如果您不需要與 Office 365 相關聯的自訂網域或您不管理 Windows 裝置，您可以略過這一節。否則，您需要新增在 DNS 主機的網域的 DNS 記錄。如果您已設定您的網域與 Office 365 的一部分已經、 新增記錄您正在所有設定。新增記錄之後，Office 365 的使用者在組織中使用自訂網域的電子郵件地址與其 Windows 裝置登入已重新導向至在 MDM 中註冊 Office 365。
  
需要協助設定記錄吗？尋找網域註冊機構中所提供[的 Office 365 管理 DNS 記錄時建立 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)中的清單並選取要移至 [建立 DNS 記錄的逐步說明的登錄程式名稱。使用這些指示來新增下列兩個記錄： 
  
|**主機名稱**|**記錄類型**|**地址**|**TTL**|
|:-----|:-----|:-----|:-----|
|EnterpriseEnrollment  <br/> |CNAME  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |3600  <br/> |
|EnterpriseRegistration  <br/> |CNAME  <br/> |EnterpriseRegistration.windows.net  <br/> |3600  <br/> |
   
新增兩個記錄之後，回到安全性&amp;規範中心及瀏覽至 [**裝置管理** \> **管理設定**以完成下一個步驟。 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>步驟 2： （必要） Configure iOS 裝置 APNs 憑證

若要管理 iPad 和 Iphone iOS 裝置，您需要建立 APNs 憑證。
  
若要這樣做，遵循的步驟**設定**連結上的**行動裝置管理] 頁面上的安裝程式**。
  
1. **Configure iOS 裝置 APNs 憑證**] 旁邊選取 [**設定**]。
    
2. 選取 [**下載 CSR 檔案**並儲存至兩者的憑證簽署要求將記住您電腦上。 
    
    ![安裝 APN 憑證] 對話方塊](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. 選取 [**下一步**]。
    
4. 建立 APN 憑證。
    
  - 選取 [ **Apple APNS 入口網站**來開啟 Apple 推入憑證入口網站。 
    
    ![使用選取的 Apple APNS 入口網站安裝 APN 通知 cert 對話方塊](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - 使用 Apple ID 登入
    
    > [!IMPORTANT]
    > 使用 Apple 識別碼即使管理帳戶的使用者離開會與您的組織中保留電子郵件帳戶相關聯的公司。因為您需要該是時候來更新憑證時所使用的相同識別碼儲存此識別碼。 
  
  - 選取 [**建立憑證**並接受**使用規定**。
    
  - **瀏覽**至您下載到您的電腦從 Office 365 和選取 [**上傳**的憑證簽署要求。
    
  - **下載**建立 Apple 推入憑證入口網站到您的電腦 APN 憑證。 
    
    > [!TIP]
    > 如果您無法下載憑證，重新整理瀏覽器。 
  
5. 前往 Office 365 並選取 [**下一步**取得**上傳 APNS 憑證**] 頁面。 
    
6. 瀏覽至您下載從 Apple 推入憑證入口網站的 APN 憑證。
    
    ![按一下 [瀏覽] 按鈕選取 APNS cert 從 Apple 下載](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. 選取 [**完成**]。
    
新增 APN 憑證之後，回到安全性&amp;規範中心及瀏覽至 [**裝置管理** \> **管理設定**以完成下一個步驟。 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>步驟 3： 多重要素驗證設定 （建議使用）

如果您沒有看到 [**建議步驟**的多重要素驗證 (MFA)，您可以略過這一節。如果列出此選項，我們建議您在 Office 365 註冊程序的行動裝置管理安全性 Azure AD 入口網站中開啟 MFA。它會依預設已關閉。
  
MFA 可協助保護安全登入 Office 365 的行動裝置註冊需要驗證第二個表單。使用者所需確認電話、 文字訊息或應用程式通知使用者的行動裝置上正確地輸入工作的帳戶密碼之後。他們只可以註冊使用者的裝置後完成這第二種形式的驗證。使用者的裝置會在行動裝置管理註冊 Office 365 後，使用者可以存取 Office 365 資源與剛其工作的帳戶。
  
旁**設定多重要素驗證**，請選取 [**設定**]。若要了解如何在 Azure AD 入口網站中開啟 MFA，請參閱[設定多重要素驗證](https://go.microsoft.com/fwlink/p/?LinkId=519255)。
  
設定 「 MFA 之後，回到安全性&amp;規範中心及瀏覽至 [**裝置管理** \> **管理設定**以完成下一個步驟。 
  
### <a name="step-4-recommended-manage-device-security-policies"></a>步驟 4： （建議使用） 管理裝置安全性原則

下一步是建立及部署可協助保護您的 Office 365 組織資料的裝置安全性原則。例如，您可以協助防止資料遺失如果使用者藉由建立原則來鎖定裝置 5 分鐘的閒置時間後失去使用者的裝置和裝置 3 登入失敗之後清除。
  
在**安全性&amp;規範中心**、 移至 [**安全性原則** \> **裝置安全性原則**建立裝置安全性原則和存取規則。 
  
![新增裝置安全性原則](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
如需如何建立新原則的逐步指示，請參閱[建立及部署裝置安全性原則](create-device-security-policies.md)。
  
> [!TIP]
>  當您建立新的原則時，您可能會想要將原則設定為允許存取和報告原則違規使用者的裝置不符合原則是。這可讓您查看多少行動裝置會受到而封鎖存取 Office 365 的原則。> 每個人都部署在組織中的新原則之前，建議您測試少數使用者所使用的裝置上。> 此外，部署原則之前，可讓您知道 MDM 的裝置註冊 Office 365 的潛在影響的組織。根據您如何設定原則，存取 Office 365 可能會遭到封鎖不遵守其 （非相容裝置） 裝置。非相容裝置也可能必須安裝的應用程式、 相片和其註冊的裝置，可能會刪除如果清除裝置時的其他個人資訊。更多資訊： [Office 365 的行動裝置](wipe-a-mobile-device.md)。 
  
## <a name="make-sure-users-enroll-their-devices"></a>請確定使用者註冊其裝置

您已建立及部署的行動裝置管理原則之後，裝置原則可套用至您組織中的每個授權的 Office 365 使用者將會在的下次登入 Office 365 從使用者的行動裝置時收到註冊訊息。他們必須完成註冊並啟用步驟他們才能存取 Office 365 電子郵件和文件。請參閱[註冊您的公司或學校的行動裝置](enroll-your-mobile-device.md)。
  
> [!IMPORTANT]
> 如果使用者的偏好的語言不受支援的註冊程序，使用者可能會收到另一種語言註冊通知和其行動裝置上的步驟。並非所有語言都支援的 Office 365 中目前都支援的行動裝置上的註冊程序。 
  
Android 或 iOS 裝置使用的使用者，才能安裝的公司入口網站應用程式註冊程序的一部分。
  
## <a name="related-topics"></a>相關主題

[行動裝置管理功能](capabilities-of-mobile-device-management.md)
  
[建立及部署裝置安全性原則](create-device-security-policies.md)
  

