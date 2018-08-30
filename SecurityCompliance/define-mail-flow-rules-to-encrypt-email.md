---
title: 定義加密 Office 365 中的電子郵件的郵件流程規則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 身為 Office 365 全域管理員，您可以建立郵件流程規則來啟用 Office 365 郵件加密 (OME)。您可以加密所有外寄電子郵件並從內部訊息或回覆加密郵件傳送自組織移除加密。
ms.openlocfilehash: 06668f29e69c885adb8c67d723efe42b4a4aa166
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526416"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>定義加密 Office 365 中的電子郵件的郵件流程規則

身為 Office 365 全域管理員，您可以建立郵件流程規則，也稱為傳輸規則，以協助保護您傳送和接收的電子郵件訊息。您可以設定加密所有外寄電子郵件並從加密的郵件來自組織內或回覆加密郵件傳送自組織移除加密的規則。您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online 的 Windows PowerShell cmdlet 建立這些規則。除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。
  
如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則以確保其繼續在新環境中運作。此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您需要更新現有的郵件流程規則。否則，您的使用者會繼續接收加密的郵件而不是新的且相當順暢 OME 經驗會使用先前的 HTML 附件格式。如果您尚未設定 OME 尚未，請參閱[Set up 新建置上方的 Azure 資訊保護的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)資訊。 
  
如需元件構成郵件流程規則與郵件流程規則運作的方式，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)。如需搭配 Azure 資訊保護的郵件流程規則如何運作的其他資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。
  
## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>建立郵件流程規則來加密電子郵件使用的新 OME 功能

您可以定義可使用 EAC 觸發新 OME 功能的郵件加密的郵件流程規則。
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a>若要建立可加密電子郵件使用的新 OME 功能使用 EAC 的規則

1. 在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 選擇 [**管理**] 磚。 
    
3. 在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。
    
4. 在 EAC 中，移至 [**郵件流程** \> **規則** \> ![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)(**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。
    
5. 在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。
    
6. 在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com： 
    
    1. 在**套用此規則**，請選取 [**收件者**。
    
    2. 從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。 
    
        若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。
    
        輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。
    
7. 若要新增多個條件、 選擇 [**更多選項]** 然後選擇 [**新增條件**並從清單中選取。 
    
    例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。
    
8. 若要啟用加密使用新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存**]，然後選擇 **[確定]**。
    
    範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。
    
    您可以選擇**加入動作**如果您想要指定另一個巨集指令。 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a>更新現有的郵件流程規則來使用 EAC OME 的新功能

1. 在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 選擇 [**管理**] 磚。 
    
3. 在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。
    
4. 在 EAC 中，移至 [**郵件流程** \> **規則**。
    
5. 在郵件流程規則清單中，選取您想要使用的新 OME 功能，然後選擇 [修改的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)（**編輯**）。
    
6. 若要啟用加密使用新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存]** ，然後選擇 **[確定]**。
    
    範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。
    
    您可以選擇**加入動作**如果您想要指定另一個巨集指令。 
    
7. 從**執行下列動作**] 清單中移除任何指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。
    
8. 選擇 [**儲存**]。
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>不使用的新功能建立 Office 365 郵件加密的規則

若您尚未尚未移動 Office 365 組織到新的 OME 功能，可用於這些工作定義加密您的組織的郵件的郵件流程規則。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a>若要建立可加密電子郵件訊息的新 OME 功能不使用 EAC 的規則

1. 在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 選擇 [**管理**] 磚。 
    
3. 在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。
    
4. 在 EAC 中，移至 [**郵件流程** \> **規則** \> **+** (**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。
    
5. 在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。
    
6. 在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com： 
    
1. 在**套用此規則**，請選取 [**收件者**。
    
2. 從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。 
    
    若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。
    
    輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。
    
7. 若要新增多個條件、 選擇 [**更多選項]** 然後選取 [**新增條件**與從清單中選取。 
    
    例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。
    
8. 若要啟用加密沒有使用新的 OME 功能，**請執行下列操作**，請選取 [**修改郵件安全性** \> **套用 OME 的前一版**]，然後選擇 [**儲存**。
    
    如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。如果您想要立即設定 OME，您必須設定為使用新的 OME 功能。資訊，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支援的 OME 而的新功能的新部署的設定。
    
    您可以選擇**加入動作**如果您想要指定另一個巨集指令。 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>若要建立可加密電子郵件訊息的新 OME 功能不使用 Exchange Online 的 Windows PowerShell 規則

1. 使用本機電腦上的 Windows PowerShell 建立至 Exchange Online 的遠端 PowerShell 工作階段。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。
    
2. 使用**New-transportrule**指令程式來定義規則並將**ApplyOME**屬性設定為**true**。
    
    例如，若要要求必須加密所有電子郵件訊息傳送給 DrToniRamos@hotmail.com，請輸入：
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    在此範例中：
    
  - 新規則的名稱為"加密規則 Dr Toni Ramos"。
    
  - **-SentTo**參數會指定尋找收件者電子郵件訊息中的條件。您可以使用唯一識別收件者，例如電子郵件地址、 名稱、 辨別的名稱 (DN) 等的任何值。在這個範例中，收件者可識別的電子郵件地址"DrToniRamos@hotmail.com"。 
    
  - **-SentToScope**參數會指定條件所尋找的收件者的位置。在本例中為收件者的信箱在 hotmail 而不屬於 Office 365 組織，因此會使用"NotInOrganization"值。 
    
    如需詳細資訊條件您可以使用此指令程式的郵件流程規則上設定，請參閱[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>移除新 OME 功能不加密的電子郵件回覆的加密

當您的電子郵件使用者傳送加密的郵件時，那些郵件的收件者可以使用加密回覆與回應。您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不需要登入加密入口網站以進行檢視。您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。如果您不尚未使用新的 OME 功能，您可以僅解密其中一個從您的組織或組織內傳送訊息的回覆的郵件中傳送的郵件。您無法解密源自組織外的加密的郵件。
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a>若要建立移除新 OME 功能不使用 EAC 來加密的電子郵件回覆中加密的規則
<a name="DecryptruleEACNoNewOME"> </a>

1. 在網頁瀏覽器中使用的工作或學校了已授與管理員的權限，[登入 Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 選擇 [**管理**] 磚。 
    
3. 在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。
    
4. 在 EAC 中，移至 [**郵件流程** \> **規則** \> **+** (**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)。
    
5. 在 [**名稱**] 輸入規則名稱，例如 Remove encryption from incoming mail。
    
6. 在**套用此規則**選取的條件的郵件，例如**收件者位於**應該移除加密\>**在組織內**。
    
7. 在**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的舊版本中移除**。
    
8. 選取 **[儲存]**。
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>若要建立可移除新 OME 功能不使用 Exchange Online 的 Windows PowerShell 加密的電子郵件回覆中加密的規則
<a name="DecryptrulePShellNoNewOME"> </a>

1. 使用本機電腦上的 Windows PowerShell 建立至 Exchange Online 的遠端 PowerShell 工作階段。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。
    
2. 使用**New-transportrule**指令程式來定義規則並將**RemoveOME**屬性設定為**true**。
    
    例如，若要移除所有傳送給 Office 365 組織中的收件者的郵件加密，請輸入：
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    在此範例中：
    
  - 新規則的名稱為"Remove encryption from incoming mail"。
    
  - **-SentToScope**參數會指定條件所尋找的收件者的位置。在這個範例中，會使用"InOrganization"值會指出的： 
    
  - 收件者是信箱、 郵件使用者、 群組或擁有郵件功能在您的組織中的公用資料夾或
    
  - 收件者的電子郵件地址中公認的網域設定為授權網域] 或 [內部轉送網域，且郵件已傳送或接收透過未經過驗證的連線。
    
    如需詳細資訊條件您可以使用此指令程式的郵件流程規則上設定，請參閱[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。
    
## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)
  
[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)
  
[將商標新增至加密郵件](add-your-organization-brand-to-encrypted-messages.md)
  
[Exchange Online 中的郵件流程規則 (傳輸規則)](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[Exchange Online Protection 中的郵件流程規則 (傳輸規則)](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  

