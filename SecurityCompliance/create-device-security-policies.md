---
title: 建立及部署裝置安全性原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/9/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewDevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: d310f556-8bfb-497b-9bd7-fe3c36ea2fd6
description: '步驟來建立及部署安全性原則行動裝置管理的 Office 365 可協助保護免於未經授權存取 Office 365 組織的資訊。 '
ms.openlocfilehash: ab1fc1960a3e55eb3080dde7df0ec742c58b2cc7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272068"
---
# <a name="create-and-deploy-device-security-policies"></a>建立及部署裝置安全性原則

您可以使用行動裝置管理 Office 365 建立協助保護免於未經授權存取您的組織資訊在 Office 365 的安全性原則。您可以將原則套用至任何的行動裝置，其中裝置的使用者具有適用的 Office 365 授權和已註冊 Office 365 中 MDM 裝置在組織中。
  
## <a name="before-you-begin"></a>開始之前

- 了解裝置、 行動裝置應用程式和 Office 365 MDM 支援的安全性設定。請參閱[office 365 的行動裝置管理功能](capabilities-of-mobile-device-management.md)。
    
- 建立包含您想要部署的原則的 Office 365 使用者的安全性群組與使用者您可能會想要排除在所封鎖的 Office 365 的存取。建議您為組織部署新的原則之前，測試將原則部署至少數使用者。您可以建立並使用包含剛自行或小型數字 Office 365 的使用者可以測試之原則的安全性群組。若要深入了解安全性群組，請參閱[建立、 編輯或刪除安全性群組](https://go.microsoft.com/fwlink/p/?LinkId=518555)。
    
- **重要：** 您可以建立行動裝置原則之前，您必須啟動及設定 MDM for Office 365。請參閱[office 365 的行動裝置管理的概觀](overview-of-mdm.md)。
    
- 若要建立及部署 Office 365 中的行動裝置管理原則，您必須是 Office 365 全域管理]。請參閱[中的 Office 365 安全性權限&amp;規範中心](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1)。
    
- 在部署原則之前，可讓您知道 MDM 的裝置註冊 Office 365 的潛在影響的組織。根據您如何設定原則，不相容的裝置存取 Office 365 也會遭到封鎖，並刪除資料，包括已安裝應用程式、 照片和註冊的裝置上的個人資訊。
    
> [!NOTE]
> Exchange ActiveSync 行動裝置信箱原則和裝置存取規則在 Exchange 系統管理中心中建立的原則和 MDM 中建立的 Office 365 的存取規則會覆寫。裝置在 MDM 中註冊 Office 365 之後，都會被忽略任何 Exchange ActiveSync 行動裝置信箱原則 」 或 「 裝置存取規則套用至裝置。若要深入了解 Exchange ActiveSync，請參閱[Exchange Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。 
  
## <a name="step-1-create-a-security-policy-and-deploy-to-a-test-group"></a>步驟 1： 建立安全性原則和部署至測試群組

您可以啟動之前，請確定已啟動並設定 Office 365 MDM。請參閱[概觀 （英文） 的行動裝置管理 Office 365](overview-of-mdm.md)的指示。 
  
1. 在 [安全性] 中的 Office 365 中&amp;規範管理中心，移至 [**資料外洩防護** \> **裝置安全性原則**。
    
    > [!NOTE]
    > 僅之後已啟動行動裝置管理**裝置安全性原則**會出現的功能表中。 
  
2. 選擇 [ **+ 建立原則**。
    
    ![建立裝置安全性原則] 下的 MDN 裝置原則](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
3. 指定新原則的**名稱**和**描述**，然後選擇 [**下一步**。
    
    ![設定裝置安全性原則的名稱](media/d382e845-4a7f-4f72-8a09-813ea4cbd0c4.png)
  
4. 在**您要在裝置上有哪些需求？** ] 頁面上，指定您想要套用至行動裝置在您的組織中的需求，然後選擇 [**下一步**。
    
    ![[設定] 頁面上的裝置安全性原則](media/186b3bd5-5e3d-4059-978f-94113111a8ca.png)
  
5. 在**您想要設定吗？** ] 頁面上，指定您想要套用至行動裝置在您的組織中任何其他需求，然後選擇 [**下一步**。
    
6. 在**您想要立即套用此原則吗？** ] 頁面上，並選擇 [ **]**，然後選擇 [ **+ 新增**。 
    
    ![新增原則](media/89ab7cab-1b7a-4c78-9aa6-3db7d7667f8e.png)
  
7. 選取 [將其部署至您的組織與然後選擇 [**新增**之前測試其原則的群組。
    
8. 選擇 [下一步]****。
    
9. 檢閱並確認新的裝置原則的詳細資訊，然後選擇**建立此原則**。
    
    ![選擇 [建立此原則以完成建立裝置原則](media/e410bcf3-8a36-44ed-9fea-00e742db06fb.png)
  
10. 按一下 [關閉]****。
    
原則可套用至每位使用者必須推送至使用者的裝置在下次登入 Office 365 使用使用者的行動裝置的原則。如果使用者尚未套用至使用者的行動裝置之前的原則，然後部署原則之後他們會得到通知包括[步驟註冊並啟動 Office 365 MDM](https://go.microsoft.com/fwlink/?LinkId=615272)其裝置上。直到完成註冊，存取權的電子郵件、 OneDrive 及其他服務將會受限。完成註冊使用 Intune 的公司入口網站應用程式之後，他們必須能夠使用的服務與原則將會套用至使用者的裝置。
  
## <a name="step-2-verify-your-policy-works"></a>步驟 2： 確認您的原則運作

您已建立的安全性原則之後，就應該檢查原則運作如預期般部署至組織之前。
  
1. 在 Office 365 中，移至**安全性&amp;規範中心** \> **資料外洩防護** \> **裝置管理**。
    
2. 在**Office 365 的行動裝置管理**] 頁面上，勾選 [已套用原則的使用者裝置的狀態。您可以篩選或排序的**所有**檢視所有的裝置或**封鎖**檢視封鎖的裝置。 
    
    ![檢視受 MDM 裝置](media/5c9fd069-b716-40d8-9b36-f9cfeae2139f.png)
  
3. 您也可以執行完整或選擇性的抹除裝置上。指示，請參閱[Office 365 的行動裝置](wipe-a-mobile-device.md)。
    
## <a name="step-3-deploy-a-policy-to-your-organization"></a>步驟 3： 部署至您的組織的原則

您已建立的行動裝置原則並確認其運作如預期般運作後，則會部署至您的組織。
  
1. 在 Office 365 中，移至**安全性&amp;規範中心** \> **資料外洩防護**\> **裝置安全性原則**。
    
2. 選取您想要部署的原則和選擇中的 [**編輯原則** \<_原則名稱_\>面板。  
    
3. 選取 **[部署]** 索引標籤。 
    
4. 在 [**部署**] 索引標籤中選擇 [**是**上方**選取下列其中一個或多個安全性群組且包含您要套用此原則的人員**] 與 [**新增**]。
    
  - 在 [**選取群組**] 面板中，您可以搜尋要新增的群組，您可以當做篩選依據別名或顯示名稱。您也可以從 [**群組**] 清單中新增的現有群組。 
    
    您可以新增要套用之原則的多個群組。
    
    選擇 [控制台] 之底部上的 [**新增**]。 
    
5. [**部署**] 索引標籤上選擇 [**儲存**]。 
    
    ![為組織部署 MDM 原則。](media/dc3e7fe5-201a-4e45-abe3-fc93e0b59028.png)
  
原則可套用至每位使用者必須推送至使用者的裝置在下次登入 Office 365 從使用者的行動裝置的原則。如果使用者尚未套用至使用者的行動裝置的原則，其將註冊並針對 MDM 啟動 Office 365 步驟[要取得其裝置上的通知](https://go.microsoft.com/fwlink/?LinkId=615272)。他們在註冊完成後，該原則會套用至使用者的裝置。 
  
## <a name="step-4-block-email-access-for-unsupported-devices"></a>步驟 4： 封鎖存取電子郵件不受支援的裝置

為了安全貴組織的資訊，您應封鎖不支援 MDM for Office 365 的行動裝置的 Office 365 電子郵件應用程式存取。請參閱[Office 365 的內建行動裝置管理功能](capabilities-of-mobile-device-management.md)所支援的裝置清單。若要執行這項作業： 
  
1. 移至 [安全性&amp;規範中心\>**資料外洩防護**\> **裝置安全性原則**。
    
2. 選取 [**管理整個組織的裝置存取設定**。
    
    ![移至 [規範中心\>裝置並按一下 [管理裝置存取設定連結。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. 若要封鎖不受支援的裝置，請選擇 [**封鎖**下**如果裝置不受支援的 Office 365 MDM 執行您想要允許或封鎖它無法使用 Exchange 帳戶以存取貴組織的電子郵件** \> **儲存**。
  
## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>步驟 5：選擇不要進行條件存取檢查的安全性群組

如果您不想某些人在他們的行動裝置上進行條件存取檢查，且您已經針對這些人建立一或多個安全性群組，請在此新增安全性群組。系統不會針對這些群組中的人，強制在他們支援的行動裝置上執行任何原則。
  
1. 移至 [安全性&amp;規範中心\>**資料外洩防護**\> **裝置安全性原則**。
    
2. 選取 [**管理整個組織的裝置存取設定**。
    
    ![移至 [規範中心\>裝置並按一下 [管理裝置存取設定連結。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. 選取 [**新增**] 以新增 [安全性] 群組具有您想要從要排除的使用者封鎖至 Office 365 的存取。當使用者已新增至這份清單中時，他們必須能夠存取 Office 365 電子郵件時使用不受支援的裝置。 
    
4. 選取您想要使用 [**選取群組**] 面板中的 [安全性] 群組。 
    
5. 選取 [名稱] 中，然後**新增** \> **儲存**。
    
6. 在**整個組織的裝置存取設定**] 面板中，選擇 [**儲存**]。
  
## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>安全性原則對於不同的裝置類型有何影響？

當您將原則套用至使用者裝置時，每個裝置所受到的影響會隨著裝置類型而有所不同。請參閱下表中的範例，瞭解原則對於不同裝置的影響。
  


|**安全性原則**|**Windows Phone 8.1 +**|**Android 4+**|**Samsung Knox**|**IOS 6 +**|**附註**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|需要加密備份  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |需要 IOS 加密備份。  <br/> |
|封鎖雲端備份  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |封鎖 Android 上的 Google 備份 (呈現灰色)、iOS 上的雲端備份。  <br/> |
|封鎖文件同步處理  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS：封鎖雲端中的文件。  <br/> |
|封鎖相片同步處理  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS (原生)：封鎖相片串流。  <br/> |
|封鎖螢幕擷取畫面  <br/> |✔  <br/> |X  <br/> |✔  <br/> |✔  <br/> |在嘗試時遭封鎖。  <br/> |
|封鎖視訊會議  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |FaceTime 在 iOS 上遭封鎖，Skype 或其他項目則否。  <br/> |
|封鎖診斷資料的傳送  <br/> |✖  <br/> |X  <br/> |✔  <br/> |✔  <br/> |在 Android 上封鎖 Google 當機報告的傳送。  <br/> |
|封鎖對應用程式市集的存取  <br/> |✔  <br/> |X  <br/> |✔  <br/> |✔  <br/> |應用程式市集圖示未出現在 Android 首頁上、在 Windows 上停用、在 iOS 上未顯示。  <br/> |
|應用程式市集需要密碼  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS：ITunes 購物需要密碼。  <br/> |
|封鎖卸除式存放裝置的連線  <br/> |✔  <br/> |X  <br/> |✔  <br/> |NA  <br/> |Android：SD 記憶卡在 [設定] 中會呈現為灰色，Windows 會通知使用者該處安裝的應用程式無法使用  <br/> |
|封鎖藍芽連線  <br/> |✔  <br/> |\*\*\*  <br/> |\*\*\*  <br/> |✖  <br/> |\*\*\*我們不能作為在 android （英文） 上的設定來停用 BlueTooth。我們停用需要 BlueTooth 的所有交易的而： 進階音訊通訊、 音訊/視訊遠端控制、 免手持裝置、 耳機、 電話簿存取及序列連接埠。使用任何以上時小型吐司訊息就會出現在頁面底部。  <br/> |
   
## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>當您刪除原則或從原則中移除使用者時，會發生什麼情況？

當您刪除原則或移除的原則已部署至群組中的使用者時，從使用者的裝置可能會移除原則設定、 Office 365 電子郵件設定檔及快取的電子郵件。請參閱下表來查看功能已移除對於不同的裝置類型：
  
|**移除的項目**|**Windows Phone 8.1 +**|**iOS 6 +**|**Android 4 + （包括 Samsung Knox）**|
|:-----|:-----|:-----|:-----|
|受管理的電子郵件設定檔\*  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|原則設定  <br/> |✔  <br/>           **[封鎖裝置傳送診斷資料]** 除外。 <br/> |✔  <br/> |✖  <br/> |
   
> [!NOTE]
> \*如果原則已部署選項與**受管理的電子郵件設定檔**] 選取受管理的電子郵件設定檔並於該設定檔將會從使用者的裝置刪除快取電子郵件。 
  
已移除的原則套用至每位使用者必須從使用者的裝置中移除使用者的行動裝置使用 MDM 檢查 Office 365 的下一次的原則。如果您要部署新的原則套用至這些使用者的裝置，其將提示您重新註冊 Office 365 的 [在 MDM。
  
您也可以[裝置](wipe-a-mobile-device.md)、 其中一個完全，或選擇性地清除之裝置的組織資訊。
  
## <a name="related-topics"></a>相關主題

[Office 365 的行動裝置管理概觀](overview-of-mdm.md)
  
[Office 365 的行動裝置管理功能](capabilities-of-mobile-device-management.md)
  

