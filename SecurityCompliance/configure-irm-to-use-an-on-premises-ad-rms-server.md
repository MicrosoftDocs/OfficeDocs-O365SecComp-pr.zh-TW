---
title: 將 IRM 設定為使用內部部署 AD RMS 伺服器
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: 本主題示範如何設定 IRM 以使用 AD RMS 伺服器。
ms.openlocfilehash: 19d353dc8aa0e02b564616aacdde31c0fffa0483
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215254"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>將 IRM 設定為使用內部部署 AD RMS 伺服器
  
用於內部部署、 資訊版權管理 (IRM) 設定 Exchange Online 中使用 Active Directory Rights Management Services (AD RMS)、 Windows Server 2008 和較新版本的資訊保護技術。IRM 保護套用至電子郵件將 AD RMS 權限原則範本套用至電子郵件訊息。權限附加郵件本身使保護發生線上及離線和內部與外部組織的防火牆。
  
本主題顯示如何設定 IRM 以使用 AD RMS 伺服器。如需使用 Azure Active Directory 與 Azure 版權管理 Office 365 郵件加密的新功能資訊，請參閱[Office 365 郵件加密常見問題集](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。
  
若要深入了解 Exchange Online 中的 IRM，請參閱 [Exchange Online 的資訊版權管理](information-rights-management-in-exchange-online.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 完成此工作的預估時間：30 分鐘
    
- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的「資訊版權管理」項目。 
    
- AD RMS 伺服器必須執行 Windows Server 2008 或更新版本。如需如何部署 AD RMS 的詳細資料，請參閱[安裝 AD RMS 叢集](https://go.microsoft.com/fwlink/?LinkId=210873)。
    
- 如需如何安裝及設定 Windows PowerShell 及連線到服務的詳細資料，請參閱[使用遠端 PowerShell 連線到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="how-do-you-do-this"></a>該怎麼做？
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>步驟 1：使用 AD RMS 主控台從 AD RMS 伺服器匯出信任的發行網域 (TPD)

第一個步驟是將信任的發行網域 (TPD) 從內部部署 AD RMS 伺服器匯出至 XML 檔案。TPD 含有以下使用 RMS 功能所需的設定： 
  
- 用於簽署憑證和授權及予以加密的伺服器授權人憑證
    
- 用於授權和發行的 URL
    
- 以 TPD 特定的 SLC 建立的 AD RMS 權限原則範本
    
當您匯入 TPD 時，它就會由 Exchange Online 儲存並保護。
  
1. 開啟 Active Directory Rights Management Services 主控台，然後展開 AD RMS 叢集。
    
2. 在主控台樹狀目錄中，展開 **[信任原則]**，然後按一下 **[信任的發行網域]**。
    
3. 在結果窗格中，選取您想要匯出之網域的憑證。
    
4. 在 **[動作]** 窗格中按一下 **[匯出信任的發行網域]**。
    
5. 在 **[發行網域檔案]** 方塊中按一下 **[另存新檔]**，將檔案儲存至本機電腦上的特定位置。輸入檔案名稱並且務必指定  `.xml` 副檔名，然後按一下 **[儲存]**。
    
6. 在 **[密碼]** 和 **[確認密碼]** 方塊中，輸入將用來加密信任發行網域檔案的強式密碼。當您將 TPD 匯入雲端架構電子郵件組織時，就必須指定這個密碼。 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>步驟 2： 使用 Exchange 管理命令介面將 TPD 匯入 Exchange Online

將 TPD 匯出至 XML 檔案之後，您就必須將它匯入 Exchange Online。匯入 TPD 時，也會一併匯入組織的 AD RMS 範本。匯入第一個 TPD 時，它會成為雲端架構組織的預設 TPD。如果您匯入了其他 TPD，可以使用 **Default** 參數，讓它成為提供給使用者的預設 TPD。 
  
若要匯入 TPD，請在 Windows PowerShell 中執行下列命令：
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

您可以在 Active Directory Rights Management Services 主控台中取得  _ExtranetLicensingUrl_ 和  _IntranetLicensingUrl_ 參數的值。請在主控台樹狀目錄中選取 AD RMS 叢集。授權 URL 就會顯示在結果窗格中。當內容必須解密以及 Exchange Online 必須判斷要使用的 TPD 時，電子郵件用戶端就會使用這些 URL。 
  
當您執行此命令時，系統會提示您輸入密碼。請輸入您從 AD RMS 伺服器匯出 TPD 時所指定的密碼。
  
例如，下列命令會使用您從 AD RMS 伺服器匯出並儲存至系統管理員帳戶桌面的 XML 檔案來匯入名為 Exported TPD 的 TPD。Name 參數是用來指定 TPD 的名稱。
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

如需詳細的語法及參數資訊，請參閱 [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)。
  
#### <a name="how-do-you-know-this-step-worked"></a>如何才能了解此步驟是否正常運作？

若要確認您是否已成功匯入 TPD，請執行 **Get-RMSTrustedPublishingDomain** 指令程式以擷取 Exchange Online 組織中的 TPD。如需詳細資料，請參閱 [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx) 中的範例。
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>步驟 3： 使用 Exchange 管理命令介面來發佈 AD RMS 權限原則範本

匯入 TPD 之後，您必須確保分散式 AD RMS 權限原則範本。分散式的範本看至網頁 （前身為 Outlook Web App） 使用者，然後以電子郵件訊息套用範本上的 Outlook。
  
若要傳回預設 TPD 包含的所有範本清單，請執行下列命令：
  
```
Get-RMSTemplate -Type All | fl
```

如果_Type_參數的值是`Archived`、 範本不是可讓使用者看到。僅限分散式的範本預設 TPD 都可以在 web 上的 Outlook。
  
若要發佈範本，請執行下列命令：
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

例如，下列命令會匯入 Company Confidential 範本。
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

如需詳細的語法及參數資訊，請參閱 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 與 [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)。
  
 **不要轉寄範本**
  
當您將預設 TPD 從內部部署組織匯入 Exchange Online 時，會匯入名為 **[不要轉寄]** 的 AD RMS 權限原則範本。根據預設，當您匯入預設 TPD 時，系統會發佈此範本。但是，您無法使用 **Set-RMSTemplate** 指令程式來修改 **[不要轉寄]** 範本。 
  
當 **[不要轉寄]** 範本套用至郵件時，只有郵件中所列的收件者才能讀取郵件。此外，收件者無法進行下列作業： 
  
- 將郵件轉寄給其他人員。
    
- 複製郵件的內容。
    
- 列印郵件。
    
> [!IMPORTANT]
> **[不要轉寄]** 範本無法防止使用者透過協力廠商螢幕擷取程式複製郵件中的資訊，也無法防止使用者手動抄錄資訊。 
  
您可以在內部部署組織中的 AD RMS 伺服器上建立其他 AD RMS 權限原則範本，以符合您的 IRM 保護需求。如果您建立了其他 AD RMS 權限原則範本，就必須再次從內部部署 AD RMS 伺服器匯出 TPD，然後在雲端架構電子郵件組織中重新整理 TPD。 
  
#### <a name="how-do-you-know-this-step-worked"></a>如何才能了解此步驟是否正常運作？

若要確認您是否已成功發佈 AD RMS 權限原則範本，請執行 **Get-RMSTemplate** 指令程式以檢查範本的內容。如需詳細資料，請參閱 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 中的範例。
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>步驟 4： 使用 Exchange 管理命令介面來啟用 IRM

匯入 TPD 並發佈 AD RMS 權限原則範本之後，請執行以下命令以針對雲端架構電子郵件組織啟用 IRM。
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

如需詳細的語法及參數資訊，請參閱 [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)。
  
#### <a name="how-do-you-know-this-step-worked"></a>如何才能了解此步驟是否正常運作？

若要確認您是否已成功啟用 IRM，請執行 [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) 指令程式以檢查 Exchange Online 組織中的 IRM 組態。 
  
## <a name="how-do-you-know-this-task-worked"></a>如何才能了解此工作是否正常運作？
<a name="sectionSection2"> </a>

若要確認您是否已成功匯入 TPD 並啟用 IRM，請執行下列動作：
  
- 使用 **Test-IRMConfiguration** 指令程式來測試 IRM 功能。如需詳細資訊，請參閱 [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx) 中的「範例 1」。
    
- 撰寫新郵件在網路上的 Outlook 和 IRM 保護其選取 [**設定權限**從延伸功能表選項 (![更多選項] 圖示](media/ITPro-EAC-MoreOptionsIcon.gif))。
    

