---
標題: 「 啟用或停用 Office 365 中的安全提示"ms.author: krowley 作者： kccross manager: laurawi ms.date: 2018/12/05 ms.audience: Admin ms.topic： 文章 ms.service: o365 管理 localization_priority: Normal search.appverid: 
- MET150 ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7 ms.collection:
    - M365 安全性合規性描述: 「 告訴 Office 365 和 EOP 系統管理員如何啟用及停用電子郵件訊息中的安全提示。 」
---

# <a name="enable-or-disable-safety-tips-in-office-365"></a>啟用或停用 Office 365 中的安全提示

Exchange Online Protection (EOP) 新增，或傳送的電子郵件的戳記，safety 提示。 如果郵件已標示為垃圾郵件由 Office 365 中，如果郵件包含可疑的網路釣魚詐騙，例如某個項目或外部影像有這些安全提示提供快速、 視覺化的方式，來判斷郵件是否安全，從收件者驗證寄件者已封鎖。 Office 365 與獨立式 EOP 系統管理員可以編輯若要啟用或停用安全提示顯示於 Outlook 和其他桌面電子郵件用戶端中的電子郵件的垃圾郵件原則設定。 
  
Office 365 組織的預設啟用安全提示，並建議您保留加以啟用，以協助抵禦垃圾郵件和網路釣魚攻擊。 您無法停用 outlook 網頁版安全提示。
  
若要查看範例，以及了解安全提示中顯示的資訊，請參閱[安全提示在 Office 365 中的電子郵件訊息中。](safety-tips-in-office-365.md)
  
本主題內容：
  
- [若要啟用或停用安全提示使用 Office 365 安全性&amp;合規性中心](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [若要啟用或停用安全提示，藉由使用 PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>若要啟用或停用安全提示使用 Office 365 安全性&amp;合規性中心
<a name="SandCCsafetytip"> </a>

1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 以公司或學校帳戶登入 Office 365。
    
3. 選擇 [**威脅管理** \> **原則**。 
    
4. 在 [**原則**] 頁面上，選擇 [**反垃圾郵件**]。
    
    ![這個螢幕擷取畫面顯示如何取得反垃圾郵件設定] 頁面上，安全性&amp;合規性中心。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. 在 [**反垃圾郵件設定**] 頁面上選擇 [**自訂**] 索引標籤。 
    
    ![這個螢幕擷取畫面顯示 [自訂] 索引標籤的位置上反垃圾郵件設定] 頁面上，安全性&amp;合規性中心。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. 如有必要，選擇 [開啟自訂設定的**自訂設定**參數。 如果自訂設定參數設為**關閉**，您無法修改垃圾郵件篩選原則。
    
    ![這個螢幕擷取畫面顯示自訂的反垃圾郵件篩選原則設定為關閉。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. 展開您要修改]，然後選擇 [**編輯原則**的垃圾郵件原則。 例如，選擇**預設垃圾郵件篩選原則**旁的向下箭號。 或者，如果您想，您可以選擇 [**新增原則**建立新的原則。
    
8. 展開 [**垃圾郵件] 和 [大量**動作]。 
    
9. 若要啟用安全提示，[**安全提示**，請**在 [上**] 核取方塊。 若要停用安全提示，請清除 [**上**] 核取方塊。 
    
10. 選擇 [**儲存**]。
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>若要啟用或停用安全提示，藉由使用 PowerShell
<a name="pshellsafetytip"> </a>

系統管理員可以使用 Exchange Online PowerShell，啟用或停用安全提示。 使用 Set-hostedcontentfilterpolicy 指令程式來啟用或停用垃圾郵件篩選原則中的安全提示。
  
1. 連線至 Exchange Online PowerShell (機器翻譯)。 如需資訊，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
2. 執行 Set-hostedcontentfilterpolicy 指令程式來啟用或停用安全提示：
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

其中：
    
  -  *原則名稱*是您想要修改，例如**預設**原則的名稱。
    
  -  `$true`啟用安全的祕訣垃圾郵件篩選原則。 
    
  -  `$false`停用垃圾郵件篩選器原則的安全提示。 
    
    例如，若要停用預設垃圾郵件篩選器原則的安全提示，請執行下列命令：
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

如需有關此 cmdlet 的詳細資訊，請參閱 < <b0>Set-hostedcontentfilterpolicy</b0>。
    
## <a name="still-need-help"></a>仍需要協助嗎？
<a name="pshellsafetytip"> </a>

如果您停用安全提示，卻仍看到它們在您的電子郵件中，請檢查下列事項：
  
- 您無法停用 outlook 網頁版安全提示。 請嘗試在另一個用戶端，例如 Outlook 中檢視相同的電子郵件。
    
- 安全提示都預設為每一個使用 EOP 的人員，這包括具有 Office 365 的人。 若要停用安全提示從出現在 [電子郵件，您必須予以停用使用垃圾郵件篩選原則，如本主題所述。 一旦您已設定的原則，請確定已啟用。 啟用垃圾郵件篩選原則的詳細資訊，請參閱[設定垃圾郵件篩選原則](https://technet.microsoft.com/library/jj200684.aspx)。
    
如需更多，以便抵禦垃圾郵件和網路釣魚方法，請參閱 < <b0>Office 365 電子郵件反垃圾郵件保護</b0>。
  

