---
title: 敏感性資訊類型所尋找的項目
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全性中的資料遺失防護 (DLP)&amp;合規性中心包含可供您在 DLP 原則中使用的 80 種敏感資訊類型。 本主題列出所有的這些敏感資訊類型，並顯示 DLP 原則看起來當它偵測到每個類型。
ms.openlocfilehash: d161435c75149183289cfbfd6abe79d55e371e31
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266869"
---
# <a name="what-the-sensitive-information-types-look-for"></a>敏感性資訊類型所尋找的項目

Office 365 安全性中的資料遺失防護 (DLP)&amp;合規性中心包含許多可供您可以使用 DLP 原則中的敏感資訊類型。 本主題列出所有的這些敏感資訊類型，並顯示 DLP 原則看起來當它偵測到每個類型。 敏感資訊類型是由能夠識別規則運算式或函數的模式所定義。 此外，例如關鍵字和總和檢查碼佐證性證據可以用來識別敏感資訊類型。 信賴等級和接近性也會用於評估程序。
  
## <a name="aba-routing-number"></a>阿拉巴馬州路由號碼

### <a name="format"></a>格式

這可能是採用格式化或未格式化模式的 9 位數

### <a name="pattern"></a>模式

格式：
- 以 0、 1、 2、 3、 6、 7 或 8 開頭的四位數
- 連字號
- 四位數
- 連字號
- 數字

未格式化： 9 個連續數字以 0、 1、 2、 3、 6、 7 或 8 開頭 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_aba_routing 找到符合模式的內容。
- 找不到來自 Keyword_ABA_Routing 的關鍵字。

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>關鍵字

#### <a name="keywordabarouting"></a>Keyword_ABA_Routing

- 阿拉巴馬州銀行
- 阿拉巴馬州銀行 #
- 阿拉巴馬州銀行路由 #
- 阿拉巴馬州銀行路由號碼
- 阿拉巴馬州銀行 #
- abarouting #
- 阿拉巴馬州銀行號碼
- abaroutingnumber
- 美國銀行關聯路由 #
- 美國銀行關聯路由號碼
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- 銀行路由號碼
- bankrouting #
- bankroutingnumber
- 路由傳輸數目
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>阿根廷國民識別 （dni） 碼數目

### <a name="format"></a>格式

以句點分隔的八位數

### <a name="pattern"></a>模式

八位數：
- 兩位數
- 句點
- 三位數
- 句點
- 三位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_argentina_national_id 找到符合模式的內容。
- 找不到來自 Keyword_argentina_national_id 的關鍵字。

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordargentinanationalid"></a>Keyword_argentina_national_id

- 阿根廷國民識別數字 
- 身分識別 
- Identification 國民身分證 
- DNI 
- NIC 國民身分登錄的人員 
- Documento Nacional de Identidad 
- Registro Nacional de 美國的人物代表 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>澳洲銀行帳戶號碼

### <a name="format"></a>格式

包含或不含銀行代號的 6-10 位數

### <a name="pattern"></a>模式

帳戶號碼為 6-10 位數。
澳洲銀行代號：
- 三位數 
- 連字號 
- 三位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。.
- 找不到來自 Keyword_australia_bank_account_number 的關鍵字。
- 規則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。.
- 找不到來自 Keyword_australia_bank_account_number 的關鍵字。

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordaustraliabankaccountnumber"></a>Keyword_australia_bank_account_number

- swift 銀行代碼
- 對應的銀行
- 基底的貨幣
- usa 帳戶
- 持有者地址
- 銀行地址
- 資訊的帳戶
- 基金傳輸
- 銀行費用
- 銀行詳細資料
- 銀行業資訊
- 完整名稱
- iaea

   
## <a name="australia-drivers-license-number"></a>澳洲駕照編號

### <a name="format"></a>格式

九個字母和數字

### <a name="pattern"></a>模式

九個字母和數字： 

- 兩個數字或字母 （不區分大小寫） 
- 兩位數 
- 五個數字或字母 （不區分大小寫）

或

- 1-2 選用字母 （不區分大小寫） 
- 4-9 位數

或

- 九個數字或字母 （不區分大小寫）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。
- 找不到來自 Keyword_australia_drivers_license_number 的關鍵字。
- 找不到來自 Keyword_australia_drivers_license_number_exclusions 的關鍵字。

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordaustraliadriverslicensenumber"></a>Keyword_australia_drivers_license_number

- 國際主導許可
- 澳洲汽車關聯
- 國際主導允許
- DriverLicence
- DriverLicences
- 驅動程式 Lic
- 驅動程式授權
- 驅動程式授權
- DriversLic
- DriversLicence
- DriversLicences
- 驅動程式 Lic
- 驅動程式 Lics
- 驅動程式授權
- 驅動程式授權
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- 驅動程式 ' Lic
- 驅動程式 ' Lics
- 驅動程式 ' 授權
- 驅動程式 ' 授權
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- 駕 Lic
- 駕 Lics
- 驅動程式的授權
- 驅動程式的授權
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- 驅動程式 Lic #
- 驅動程式 Lics #
- 驅動程式授權 #
- 驅動程式授權 #
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- 驅動程式 Lic #
- 驅動程式 Lics #
- 驅動程式授權 #
- 驅動程式授權 #
- Driver'Lic #
- Driver'Lics #
- Driver'Licence #
- Driver'Licences #
- 驅動程式 ' Lic #
- 驅動程式 ' Lics #
- 驅動程式 ' 授權 #
- 驅動程式 ' 授權 #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- 駕 Lic #
- 駕 Lics #
- 驅動程式的授權 #
- 驅動程式的授權 # 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- 驅動程式授權
- 驅動程式授權
- 執照
- DriversLicenses
- 驅動程式授權
- 驅動程式授權
- Driver'License
- Driver'Licenses
- 驅動程式 ' 授權
- 驅動程式 ' 授權
- Driver'sLicense
- Driver'sLicenses
- 駕照
- 驅動程式的授權
- DriverLicense #
- DriverLicenses #
- 驅動程式授權 #
- 驅動程式授權 #
- 執照 #
- DriversLicenses #
- 驅動程式授權 #
- 驅動程式授權 #
- Driver'License #
- Driver'Licenses #
- 驅動程式 ' 授權 #
- 驅動程式 ' 授權 #
- Driver'sLicense #
- Driver'sLicenses #
- 驅動程式的授權 #
- 驅動程式的授權 #
   
## <a name="australia-medical-account-number"></a>澳洲醫療帳戶號碼

### <a name="format"></a>格式

10-11 位數

### <a name="pattern"></a>模式

10-11 位數：
- 第一個數字是 2-6 的範圍內
- 第九個數字是檢查碼
- 第十個數字是簽發碼
- 第十一個數字 （選擇性） 是個人碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_australian_medical_account_number 找到符合模式的內容。
- 找不到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_australian_medical_account_number 找到符合模式的內容。
- 總和檢查碼通過。

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordaustraliamedicalaccountnumber"></a>Keyword_Australia_Medical_Account_Number

- 銀行帳戶詳細資料
- medicare 付款
- 抵押帳戶
- 銀行付款
- 資訊分支
- 信用卡貸款
- 人力服務部門
- 本機服務
- medicare

   
## <a name="australia-passport-number"></a>澳洲護照號碼

### <a name="format"></a>格式

字母後尾隨七位數

### <a name="pattern"></a>模式

尾隨七位數字母 （不區分大小寫）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_australia_passport_number 找到符合模式的內容。
- 找不到來自 Keyword_passport 或 Keyword_australia_passport_number 的關鍵字。

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordpassport"></a>Keyword_passport

- 護照號碼
- Passport 否
- Passport #
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート # 
- Numéro de passeport
- Passeport n °
- Passeport 非
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keywordaustraliapassportnumber"></a>Keyword_australia_passport_number

- passport
- passport 詳細資料
- immigration 和公民
- 澳大利亞聯邦
- immigration 的部門
- 住家地址
- immigration 和公民的部門
- visa
- 國民身分證
- 護照號碼
- 出差的文件
- 授權單位
   
## <a name="australia-tax-file-number"></a>澳洲稅務檔案編號

### <a name="format"></a>格式

8-9 位數

### <a name="pattern"></a>模式

8-9 位數，通常會有空格，如下所示：
- 三位數 
- 一個選用空格 
- 三位數 
- 一個選用空格 
- 2-3 位數，最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_australian_tax_file_number 找到符合模式的內容。
- 找不到來自 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。
- 總和檢查碼通過。

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordaustraliataxfilenumber"></a>Keyword_Australia_Tax_File_Number

- 澳洲商務號碼
- 臨界稅率
- medicare 募集
- 組合數
- 服務老手
- 扣繳稅
- 個別的稅務傳回
- 稅務檔案編號

#### <a name="keywordnumberexclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999

## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 驗證金鑰

### <a name="format"></a>格式

將字串 「 DocumentDb 」 後面接著字元和下列模式中所述的字串。

### <a name="pattern"></a>模式

- 將字串 「 DocumentDb 」
- 3-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 大於符號 (>)、 等號 （=）、 引號 （"） 或單引號 （'）
- 或的任何組合 86 較低的大寫字母、 數字，轉寄斜線 （/） 或加上加號 （+）
- 兩個等號 （=）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 資料庫連接字串和 Azure SQL 連線字串

### <a name="format"></a>格式

字串 「 伺服器 」、 「 伺服器 」 或 「 資料來源 」 後面加上字元和下列，模式中所述的字串包含字串 「 cloudapp.azure。<!--no-hyperlink-->com 」 或者 「 cloudapp.azure。<!--no-hyperlink-->net 」 或者 「 database.windows。<!--no-hyperlink-->net 」 及 「 密碼 」 或 「 密碼 」 或 「 pwd 」 的字串。

### <a name="pattern"></a>模式

- 字串 「 伺服器 」、 「 伺服器 」 或者 「 資料來源 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 cloudapp.azure。<!--no-hyperlink-->com 」、 「 cloudapp.azure。<!--no-hyperlink-->net 」，或者 「 database.windows。<!--no-hyperlink-->net 」
- 1-300 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 字串 「 密碼 」、 「 密碼 」 或者 「 pwd 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 不是以分號 （;） 的一或多個字元的引號 （"） 或單引號 （'）
- 分號 （;）、 引號 （"） 或單引號 （'）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT 連接字串

### <a name="format"></a>格式

將字串 「 主機名稱 」 後面加上字元和下方，模式中所述的字串包含字串 「 azure 裝置。<!--no-hyperlink-->net 」 和 「 SharedAccessKey 」。

### <a name="pattern"></a>模式

- 將字串 「 主機名稱 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 azure 裝置。<!--no-hyperlink-->net 」
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 SharedAccessKey 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 或的任何組合 43 較低的大寫字母、 數字，轉寄斜線 （/） 或加上加號 （+）
- 等號 （=）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Azure 發佈設定密碼

### <a name="format"></a>格式

將字串 「 userpwd = 」 後面接著英數字元的字串。

### <a name="pattern"></a>模式

- 將字串 「 userpwd = 」
- 60 小寫字母或數字的任何組合
- 引號 （"）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。


```
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Azure 意指快取的連接字串

### <a name="format"></a>格式

將字串 「 redis.cache.windows。<!--no-hyperlink-->net"後面加上字元和下方，模式中所述的字串包含字串 「 密碼 」 或 「 pwd 」。

### <a name="pattern"></a>模式

- 將字串 「 redis.cache.windows。<!--no-hyperlink-->net 」
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 字串 「 密碼 」 或者 「 pwd 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 43 較低或大寫字母、 數字的字元的任何組合反斜線 （/），或加上加號 （+）
- 等號 （=）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>格式

將字串 「 簽章 」 後面加上字元和下列模式中所述的字串。

### <a name="pattern"></a>模式

- 將字串 「 簽章 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 較低或小寫字母、 數字或百分比符號 （%） 的 43-53 字元之間的任何組合
- 將字串 「 %3d 」
- 不是較低的大寫字母、 數字或百分比符號 （%） 的任何字元

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 服務匯流排連接字串

### <a name="format"></a>格式

將字串 「 端點 」 後面加上字元和下方，模式中所述的字串包含字串 「 servicebus.windows。<!--no-hyperlink-->net 」 和 「 SharedAccesKey 」。

### <a name="pattern"></a>模式

- 將字串 「 端點 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 servicebus.windows。<!--no-hyperlink-->net 」
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 SharedAccessKey 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 43 較低或大寫字母、 數字的字元的任何組合反斜線 （/），或加上加號 （+）
- 等號 （=）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Azure 儲存體帳戶金鑰

### <a name="format"></a>格式

將字串 「 DefaultEndpointsProtocol"後面加上字元和下方，模式中所述的字串包含字串 「 AccountKey 」 中。

### <a name="pattern"></a>模式

- 將字串 「 DefaultEndpointsProtocol 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 AccountKey 」
- 0-2 空白字元
- 等號 （=）
- 0-2 空白字元
- 較低或大寫字母、 數字，86 個字元的任何組合反斜線 （/），或加上加號 （+）
- 兩個等號 （=）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。
- 規則運算式 CEP_AzureEmulatorStorageAccountFilter**不**尋找符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepazureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Azure 儲存體帳戶金鑰 （一般）

### <a name="format"></a>格式

或的任何組合 86 較低的大寫字母、 數字，正斜線 （/），加上加號 （+），前面或後面跟著字元下列模式中所述。

### <a name="pattern"></a>模式

- 0-1 的大於符號 (>)、 單引號 （'）、 等號 （=）、 引號 （"） 或數字符號 （#）
- 較低層或大寫 86 個字元的任何組合字母、 數字，正斜線 （/），或加上加號 （+）
- 兩個等號 （=）


### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a>比利時國民編碼

### <a name="format"></a>格式

11 位數加上分隔符號

### <a name="pattern"></a>模式

11 位數加上分隔符號：
- 六位數和兩個句點 yy： 通話的格式。公釐。DD 的出生日期 
- 連字號 
- 三個連續數字 （奇數男生，偶數女生） 
- 句點 
- 兩位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_belgium_national_number 找到符合模式的內容。
- 找不到來自 Keyword_belgium_national_number 的關鍵字。
- 總和檢查碼通過。

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordbelgiumnationalnumber"></a>Keyword_belgium_national_number

- 身分識別
- 註冊
- 識別 
- 識別碼 
- Identiteitskaart
- Registratie nummer 
- Identificatie nummer 
- Identiteit
- Registratie
- Identificatie 
- 相關 d'identité 
- numéro d'immatriculation
- numéro d'identification
- identité 
- 碑文 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>巴西 Cpf 碼

### <a name="format"></a>格式

11 位數包含檢查碼且可格式化或未格式化

### <a name="pattern"></a>模式

格式：
- 三位數 
- 句點 
- 三位數 
- 句點 
- 三位數 
- 連字號 
- 兩位數的檢查碼

格式化：
- 11 位數，最後二位數所在位置，請檢查位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_brazil_cpf 找到符合模式的內容。
- 找不到來自 Keyword_brazil_cpf 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_brazil_cpf 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordbrazilcpf"></a>Keyword_brazil_cpf

- CPF
- 識別
- 註冊
- 收益
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 
   
## <a name="brazil-legal-entity-number-cnpj"></a>巴西法律實體號碼 (CNPJ)

### <a name="format"></a>格式

14 位數包含登記碼、 分支碼和檢查碼加上分隔符號

### <a name="pattern"></a>模式
14 位數，加上分隔符號：
- 兩位數 
- 句點 
- 三位數 
- 句點 
- 三位數 （此前 8 位數為登記碼） 
- 一個正斜線 
- 四位數分支碼 
- 連字號 
- 兩位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_brazil_cnpj 找到符合模式的內容。
- 找不到來自 Keyword_brazil_cnpj 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_brazil_cnpj 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordbrazilcnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ MF 
- 法律實體的登錄，國際電話 
- 納稅人登錄 
- 法律實體 
- 法律實體 
- 註冊狀態 
- 商務版 
- Company
- CNPJ 
- Cadastro Nacional 斯坦 Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- Empresa 
   
## <a name="brazil-national-id-card-rg"></a>巴西國民身分證 (RG)

### <a name="format"></a>格式

Registro Geral （舊格式）： 九位數

Registro de Identidade (RIC) （新格式）： 11 位數

### <a name="pattern"></a>模式

Registro Geral （舊格式）：
- 兩位數 
- 句點 
- 三位數 
- 句點 
- 三位數 
- 連字號 
- 一位數是檢查碼

Registro de Identidade (RIC) （新格式）：
- 10 位數 
- 連字號 
- 一位數是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_brazil_rg 找到符合模式的內容。
- 找不到來自 Keyword_brazil_rg 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_brazil_rg 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordbrazilrg"></a>Keyword_brazil_rg

Cédula de identidade 身分證證 número de rregistro registro de Iidentidade registro geral RG （此關鍵字是區分大小寫） RIC （此關鍵字是區分大小寫） 
   
## <a name="canada-bank-account-number"></a>加拿大銀行帳戶號碼

### <a name="format"></a>格式

7 或 12 位數

### <a name="pattern"></a>模式

加拿大銀行帳戶號碼是 7 或 12 位數。

加拿大銀行帳戶交換號碼是：
- 五位數 
- 連字號 
- 三位數或
- 零"0" 
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 找不到來自 Keyword_canada_bank_account_number 的關鍵字。
- 規則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 找不到來自 Keyword_canada_bank_account_number 的關鍵字。

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordcanadabankaccountnumber"></a>Keyword_canada_bank_account_number

- 加拿大節省債券
- 加拿大收益機構
- 加拿大金融機構
- 直接儲放表單
- 加拿大公民
- 法律代表
- 公證人類似公開
- oaths 的專員
- 子系照護權益
- 萬用子照護
- 加拿大子稅務權益
- 收入稅務權益
- 協調的銷售稅務
- 社會保險號碼
- 收入稅務退款
- 子系稅務權益
- 就付款
- 機構數目
- 儲放要求
- 銀行業資訊
- 直接儲放
   
## <a name="canada-drivers-license-number"></a>加拿大駕照編號

### <a name="format"></a>格式

省分而異

### <a name="pattern"></a>模式

不同模式 Alberta、 不列顛哥倫比亞、 Manitoba、 New Brunswick、 Newfoundland/Labrador、 Nova Scotia、 安大略省、 Prince Edward 島、 Quebec 和薩克其萬

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_ [province_name] _drivers_license_name 的關鍵字。
- 找不到來自 Keyword_canada_drivers_license 的關鍵字。

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordprovincenamedriverslicensename"></a>於 Keyword_ [province_name] _drivers_license_name

- 省分縮寫，例如 AB
- 省分名稱，例如 Alberta

#### <a name="keywordcanadadriverslicense"></a>Keyword_canada_drivers_license

- DL
- 通訊群組清單
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- 驅動程式 Lic
- 驅動程式 Lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- 執照
- DriversLicenses
- 驅動程式 Lic
- 驅動程式 Lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- 驅動程式 ' Lic
- 驅動程式 ' Lics
- 驅動程式 ' 授權
- 驅動程式 ' 授權
- 驅動程式 ' 授權
- 驅動程式 ' 授權
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- 駕 Lic
- 駕 Lics
- 駕照
- 驅動程式的授權
- 驅動程式的授權
- 驅動程式的授權
- Permis de Conduire
- id
- 識別碼
- idcard 數目
- idcard 數字
- idcard #
- idcard #s
- idcard 卡
- idcard 卡
- idcard
- 識別碼
- 識別數字
- 識別 #
- 識別 #s
- 識別卡
- 識別卡
- 識別 
- DL #
- DL # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- 驅動程式 Lic #
- 驅動程式 Lics # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- DriversLic # 
- DriversLics # 
- 執照 # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- 驅動程式 Lic # 
- 驅動程式 Lics # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver'Licence # 
- Driver'Licences # 
- 驅動程式 ' Lic # 
- 驅動程式 ' Lics # 
- 驅動程式 ' 授權 # 
- 驅動程式 ' 授權 # 
- 驅動程式 ' 授權 # 
- 驅動程式 ' 授權 # 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- 駕 Lic # 
- 駕 Lics # 
- 驅動程式的授權 # 
- 驅動程式的授權 # 
- 驅動程式的授權 # 
- 驅動程式的授權 # 
- Permis de Conduire # 
- 識別碼 # 
- 識別碼 # 
- idcard 卡 # 
- idcard 卡 # 
- idcard # 
- 識別卡 # 
- 識別卡 # 
- 識別 # 
   
## <a name="canada-health-service-number"></a>加拿大健保號碼

### <a name="format"></a>格式

10 位數

### <a name="pattern"></a>模式

10 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_canada_health_service_number 找到符合模式的內容。
- 找不到來自 Keyword_canada_health_service_number 的關鍵字。

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordcanadahealthservicenumber"></a>Keyword_canada_health_service_number

- 個人健康數目
- 病患資訊
- 健康服務
- speciality 服務
- 汽車意外
- 病患醫院
- psychiatrist
- 工作者補償
- disability
      
## <a name="canada-passport-number"></a>加拿大護照號碼

### <a name="format"></a>格式

兩個大寫字母後尾隨六位數

### <a name="pattern"></a>模式

兩個大寫字母後尾隨六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_canada_passport_number 找到符合模式的內容。
- 找到來自於 Keyword_canada_passport_number 或 Keyword_passport 的關鍵字。

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordcanadapassportnumber"></a>Keyword_canada_passport_number

- 加拿大公民
- 加拿大護照
- passport 應用程式
- passport 相片
- 認證轉譯器
- 加拿大公民
- 處理時間
- 更新應用程式

#### <a name="keywordpassport"></a>Keyword_passport

- 護照號碼
- Passport 否
- Passport #
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート #
- Numéro de passeport
- Passeport n °
- Passeport 非
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>加拿大個人健康身分識別號碼 (PHIN)

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 規則運算式 Regex_canada_phin 找到符合模式的內容。
找到來自於 Keyword_canada_phin 或 keyword_canada_provinces 的關鍵字，至少有兩個關鍵字..

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordcanadaphin"></a>於 Keyword_canada_phin

- 社會保險號碼
- 健康資訊法案
- 收入稅務資訊
- 馬健康情況
- 健康情況註冊
- 解決方法購買
- 權益合格
- 個人健康情況
- 電源的律師
- 登記號碼
- 個人健康數目
- 從業員推薦
- 同等重要專業版
- 病患推薦
- 健康狀況和同等重要

#### <a name="keywordcanadaprovinces"></a>Keyword_canada_provinces 的關鍵字

- 努勒維特
- 魁北克
- 西北地區
- 安大略省
- 不列顛哥倫比亞
- Alberta
- 薩克其萬
- 馬
- Yukon
- 紐芬蘭和 Labrador
- New Brunswick
- 斯科
- Prince Edward Island
- 加拿大
   
## <a name="canada-social-insurance-number"></a>加拿大社會保險號碼

### <a name="format"></a>格式

使用選擇性連字號或空格的九位數

### <a name="pattern"></a>模式

格式：
- 三位數 
- 連字號或空格 
- 三位數 
- 連字號或空格 
- 三位數

未格式化： 九位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_canadian_sin 找到符合模式的內容。
- 至少兩個以下的任意組合：
    - 找不到來自 Keyword_sin 的關鍵字。
    - 找不到來自 Keyword_sin_collaborative 的關鍵字。
    - 函數 Func_eu_date 找到正確日期格式的日期。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_unformatted_canadian_sin 找到符合模式的內容。
- 找不到來自 Keyword_sin 的關鍵字。
- 總和檢查碼通過。

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsin"></a>Keyword_sin

- sin 
- 社會保險 
- numero d'assurance sociale 
- 贖罪 
- ssn 
- ssn 
- 社會安全 
- numero d'assurance 社交 
- 國家識別碼 
- 國民身分證 
- sin # 
- soc 集 
- 社交集 

#### <a name="keywordsincollaborative"></a>Keyword_sin_collaborative

- 駕照 
- 驅動程式授權 
- 驅動程式的授權 
- 驅動程式授權 
- DOB 
- 出生日期 
- 生日 
- 出生日期 
   
## <a name="chile-identity-card-number"></a>智利身分證號碼

### <a name="format"></a>格式

7-8 位數加上分隔符號檢查碼或字母

### <a name="pattern"></a>模式

7-8 位數加上分隔符號：
- 1-2 位數 
- 句點 
- 三位數 
- 句點 
- 三位數 
- 一條虛線 
- 一個數字或字母 （不區分大小寫） 這是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_chile_id_card 找到符合模式的內容。
- 找不到來自 Keyword_chile_id_card 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_chile_id_card 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordchileidcard"></a>Keyword_chile_id_card

- 國家識別碼 
- 身分證 
- 識別碼 
- 識別 
- Rol Único Nacional 
- 執行 
- Rol Único Tributario 
- 墨守成規 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>中國居民身分證 (PRC) 號碼

### <a name="format"></a>格式

18 位數

### <a name="pattern"></a>模式

18 位數：
- 六位數的地址代碼 
- Yyyymmdd 格式的八位數，代表出生日期 
- 三位數的序碼 
- 一位數是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_china_resident_id 找到符合模式的內容。
- 找不到來自 Keyword_china_resident_id 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_china_resident_id 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

### <a name="keywordchinaresidentid"></a>Keyword_china_resident_id

- 居民身分證 
- 中國 
- 國民身分識別卡 
- 身份证 
- 居民身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民身份證
- 鑑定 
   
## <a name="credit-card-number"></a>信用卡號碼

### <a name="format"></a>格式

16 位數，可格式化或未格式化 (dddddddddddddddd)，且必須通過 Luhn 測試。

### <a name="pattern"></a>模式

偵測全球，包括 Visa、 Mastercard、 Discover Card、 JCB、 American Express、 禮品卡和大來卡所有主要品牌的非常複雜且健全的模式。

### <a name="checksum"></a>總和檢查碼

是，Luhn 總和檢查碼

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_credit_card 找到符合模式的內容。
- 下列其中一項為真：
    - 找不到來自 Keyword_cc_verification 的關鍵字。
    - 找不到來自 Keyword_cc_name 的關鍵字。
    - 函數 Func_expiration_date 找到正確日期格式的日期。
- 總和檢查碼通過。

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_credit_card 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordccverification"></a>Keyword_cc_verification

- 卡片驗證
- 卡識別碼
- cvn 驗證
- cid
- cvc2
- cvv2
- pin 碼區塊
- 安全性驗證碼
- 安全號碼
- 安全性沒有
- 此問題： 數字
- 發出否
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod。 sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod。 seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód。 segurança
- cod。 seguranca cod。 segurança
- cód。 seguranca
- cód segurança
- cod seguranca cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- 資料 scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- 資料 de expiração
- 資料 de expiracao
- 資料長破折號 que expira
- validade
- 勇氣
- vencimento
- Venc 

#### <a name="keywordccname"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- Visa
- mastercard
- 主圖形卡
- mc 
- mastercards
- 主圖形卡
- 大來卡
- diners 俱樂部
- dinersclub
- 探索卡
- discovercard
- 探索卡
- JCB
- 日文卡機構
- 相關表示
- carteblanche
- 信用卡
- cc #
- cc # 中：
- 到期日
- exp 日期
- 到期日
- 日期 d'expiration
- 日期 d'exp
- 日期到期
- 銀行卡
- bankcard
- 證號碼
- 卡片 num
- cardnumber
- cardnumbers
- 卡號碼
- 信用卡
- 信用卡
- creditcards
- ccn
- 持卡人
- 持卡人
- 卡片持有者
- cardholders
- 檢查卡
- checkcard
- 檢查卡
- checkcards
- 轉帳卡
- debitcard
- 轉帳卡
- debitcards
- atm 卡
- atmcard
- atm 卡
- atmcards
- enroute
- en-us 路由
- 卡類型
- 相關 bancaire
- 相關 de crédit
- 相關 de 信用
- numéro de 相關
- numero de 相關
- nº de la 相關
- nº de 相關
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr 
- kartennummer
- kreditkartennummer
- kreditkarten nummer
- carta di credito
- carta credito
- carta
- n carta
- 編號。 carta
- 編號 carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- 無。 de tarjeta
- 沒有 de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta 沒有
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número 不要 cartão
- numero 不要 cartão 
- número 不要 cartao
- numero 不要 cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº 不要 cartão
- nº 不要 cartao
- nº。 請勿 cartão
- 沒有執行 cartão
- 沒有執行 cartao
- 無。 請勿 cartão
- 無。 請勿 cartao 
   
## <a name="croatia-identity-card-number"></a>克羅埃西亞身分證號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_croatia_id_card 找到符合模式的內容。
- 找不到來自 Keyword_croatia_id_card 的關鍵字。

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordcroatiaidcard"></a>Keyword_croatia_id_card

- 克羅埃西亞身分證
- Osobna iskaznica

   
## <a name="croatia-personal-identification-oib-number"></a>克羅埃西亞個人識別 (OIB) 碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數：
- 10 位數 
- 最後一個數字是檢查碼國際資料交換的目的，字母 HR 新增前面十一個數字。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_croatia_oib_number 找到符合模式的內容。
- 找不到來自 Keyword_croatia_oib_number 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_croatia_oib_number 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordcroatiaoibnumber"></a>Keyword_croatia_oib_number

- 個人識別碼
- Osobni identifikacijski broj 
- OIB 碼 

   
## <a name="czech-personal-identity-number"></a>捷克個人身分識別號碼

### <a name="format"></a>格式

具有選用的九位數正斜線 （舊格式） 搭配選用的 10 位數正斜線 （新格式）

### <a name="pattern"></a>模式

九位數 （舊格式）：
- 九位數

或

- 代表出生日期的六位數
- 一個正斜線
- 三位數

10 位數 （新格式）：
- 10 位數

或

- 代表出生日期的六位數
- 一個正斜線 
- 四個位數最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_czech_id_card 找到符合模式的內容。
找不到來自 Keyword_czech_id_card 的關鍵字。
總和檢查碼通過。

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字

- 捷克個人身分識別號碼
- Rodné číslo
   
## <a name="denmark-personal-identification-number"></a>丹麥個人識別碼

### <a name="format"></a>格式

10 位數包含連字號

### <a name="pattern"></a>模式

10 位數：
- DDMMYY 格式的六位數的出生日期 
- 連字號 
- 四個位數最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 規則運算式 Regex_denmark_id 找到符合模式的內容。
找不到來自 Keyword_denmark_id 的關鍵字。
總和檢查碼通過。

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyworddenmarkid"></a>Keyword_denmark_id

- 個人識別碼
- CPR
- Det Centrale Personregister
- Personnummer
   
## <a name="drug-enforcement-agency-dea-number"></a>藥物管理局 (DEA) 編號

### <a name="format"></a>格式

兩個字母後尾隨七位數

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 一個字母 （不區分大小寫） 從這組可能的字母： abcdefghjklmnprstux，此為註冊者代碼 
- 一個字母 （不區分大小寫），也就是註冊者姓氏的第一個字母 
- 七位數，最後一個數是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_dea_number 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

   
## <a name="eu-debit-card-number"></a>歐盟轉帳卡號碼

### <a name="format"></a>格式

16 位數

### <a name="pattern"></a>模式

非常複雜且健全的模式

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_eu_debit_card 找到符合模式的內容。
- 至少下列一種為真：
    - 找不到來自 Keyword_eu_debit_card 的關鍵字。
    - 找不到來自 Keyword_card_terms_dict 的關鍵字。
    - 找不到來自 Keyword_card_security_terms_dict 的關鍵字。
    - 找不到來自 Keyword_card_expiration_terms_dict 的關鍵字。
    - 函數 Func_expiration_date 找到正確日期格式的日期。
- 總和檢查碼通過。

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordeudebitcard"></a>Keyword_eu_debit_card

- 帳戶號碼 
- 證號碼 
- 卡否。 
- 安全號碼 
- cc # 

#### <a name="keywordcardtermsdict"></a>Keyword_card_terms_dict

- acct 芳鄰 
- acct num 
- acct 沒有 
- american express 
- americanexpress 
- americano 濃縮咖啡 
- amex 
- atm 卡 
- atm 卡 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- 銀行卡 
- bankkaart 
- 持卡人 
- 卡片持有者 
- 卡片 num 
- 證號碼 
- 卡號碼 
- 卡類型 
- cardano numerico 
- 持卡人 
- cardholders 
- cardnumber 
- cardnumbers 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- 相關 bancaire 
- 相關表示 
- 相關 bleue 
- 相關 de 信用 
- 相關 de crédit 
- 相關 di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- 檢查卡 
- 檢查卡 
- checkcard
- checkcards 
- chequekaart 
- cirrus 
- cirrus-edc-大師 
- controlekaart 
- controlekaarten 
- 信用卡 
- 信用卡 
- 信用卡 
- creditcards 
- debetkaart 
- debetkaarten 
- 轉帳卡 
- 轉帳卡 
- debitcard 
- debitcards 
- debito automatico 
- diners 俱樂部 
- dinersclub 
- 探索 
- 探索卡 
- 探索卡 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- 歐洲轉帳卡 
- hoofdkaart 
- hoofdkaarten 
- 在 [viaggio 
- 日文卡機構 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- 大師 
- 主圖形卡 
- 主圖形卡 
- mastercard 
- mastercards 
- mc 
- 先生現金 
- n carta 
- carta 
- 沒有 de tarjeta 
- 沒有執行 cartao 
- 沒有執行 cartão 
- 無。 de tarjeta 
- 無。 請勿 cartao 
- 無。 請勿 cartão 
- 編號 carta 
- 編號。 carta 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de 相關 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero 不要 cartao 
- numero 不要 cartão 
- numéro de 相關 
- nº carta 
- nº de 相關 
- nº de la 相關 
- nº de tarjeta 
- nº 不要 cartao 
- nº 不要 cartão 
- nº。 請勿 cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número 不要 cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- solo 
- supporti di scheda 
- supporto di scheda 
- 切換 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta 沒有
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v 工資 
- v 工資 
- visa 
- visa 加上 
- visa 電 
- visto 
- visum 
- vpay   

#### <a name="keywordcardsecuritytermsdict"></a>Keyword_card_security_terms_dict

- 卡識別碼
- 卡片驗證 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- cod。 seg 
- cod。 seguranca 
- cod。 segurança 
- cod。 sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- 密碼 
- cryptogramme 
- cv2 
- cvc 
- cvc2 
- cvn 驗證 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód。 seguranca 
- cód。 segurança 
- código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft 編號 uit 
- 發出否 
- 此問題： 數字 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- 無。 dell'edizione 
- 無。 di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin 碼區塊 
- prufziffer 
- prüfziffer 
- 安全性驗證碼 
- 安全性沒有 
- 安全號碼 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid 編號 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keywordcardexpirationtermsdict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- 資料 de expiracao 
- 資料 de expiração 
- 資料 del exp 
- 資料 di exp 
- 資料 di scadenza 
- 資料長破折號 que expira 
- 資料 scad 
- 資料 scadenza 
- 日期 de validité 
- 材料 afloop 
- 材料 van exp 
- de afloop 
- espira 
- espira 
- exp 日期 
- exp 材料 
- 到期日 
- 到期 
- 到期 
- 到期 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- 勇氣 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 
   
## <a name="eu-drivers-license-number"></a>歐盟駕照編號

若要深入了解，請參閱 <<c0>歐盟駕駛執照號碼敏感資訊類型。
  
## <a name="eu-national-identification-number"></a>歐盟國家識別碼

若要深入了解，請參閱 <<c0>歐盟國家識別碼號碼敏感資訊類型。
  
## <a name="eu-passport-number"></a>歐盟護照號碼

若要深入了解，請參閱 <<c0>歐盟護照號碼敏感資訊類型。
  
## <a name="eu-social-security-number-or-equivalent-id"></a>歐盟社會安全號碼或對等項目識別碼

若要了解更多，請參閱[歐盟社會安全號碼或對等識別碼敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。
  
## <a name="eu-tax-identification-number"></a>歐盟稅務識別碼

若要深入了解，請參閱 <<c0>歐盟稅務識別號碼敏感資訊類型。
  
## <a name="finland-national-id"></a>芬蘭國民身分證

### <a name="format"></a>格式

六位數加上字元，指出世紀加上三位數加上檢查碼

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 格式的六位數，格式為 DDMMYY，專屬於出生日期 
- 世紀標記 (可以是 '-'、 '+' 或 'a') 
- 三位數個人識別碼 
- 數字或字母 （不區分大小寫） 這是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_finnish_national_id 找到符合模式的內容。
- 找不到來自 Keyword_finnish_national_id 的關鍵字。
- 總和檢查碼通過。

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

- Keyword_finnish_national_id
- Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>芬蘭護照號碼

格式的九個字母和數字模式組合九個字母和數字的組合： 兩個字母 （不區分大小寫） 七位數總和檢查碼否定義 DLP 原則是 75%以內，則已偵測到此敏感資訊類型的如果、 內接近性是 300 個字元： 規則運算式 Regex_finland_passport_number 找到符合模式的內容。
找不到來自 Keyword_finland_passport_number 的關鍵字。
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity>
關鍵字 Keyword_finland_passport_number Passport Passi
   
## <a name="france-drivers-license-number"></a>法國駕照編號

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

12 位數驗證以忽略類似模式，例如法國電話號碼

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_french_drivers_license 找到符合模式的內容。
- 至少下列一種為真：
- 找不到來自 Keyword_french_drivers_license 的關鍵字。
- 函數 Func_eu_date 找到正確日期格式的日期。

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordfrenchdriverslicense"></a>Keyword_french_drivers_license

- 驅動程式授權
- 驅動程式授權
- driving 授權
- 主導授權
- permis de conduire
- 授權數目
- 駕照號碼
- 授權數字
- 照編號

## <a name="france-national-id-card-cni"></a>法國國民身分證 (CNI)

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

12 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_france_cni 找到符合模式的內容。

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無
   
## <a name="france-passport-number"></a>法國護照號碼

### <a name="format"></a>格式

九個數字和字母

### <a name="pattern"></a>模式

九個數字和字母：
- 兩位數 
- 兩個字母 （不區分大小寫） 
- 五位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_fr_passport 找到符合模式的內容。
- 找不到來自 Keyword_passport 的關鍵字。

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordpassport"></a>Keyword_passport

- 護照號碼
- Passport 否
- Passport #
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート # 
- Numéro de passeport
- Passeport n °
- Passeport 非
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee"></a>法國社會安全號碼 (INSEE)

### <a name="format"></a>格式

15 位數

### <a name="pattern"></a>模式

必須符合兩個模式之一：
- 13 位數後尾隨尾隨兩位數的空間<br/>
或
- 15 個連續數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。
- 找不到來自 Keyword_fr_insee 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。
- 找不到來自 Keyword_fr_insee 的關鍵字。
- 總和檢查碼通過。

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordfrinsee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- 國民身分證
- 國民身分識別
- numéro d'identité
- 沒有 d'identité
- 無。 d'identité
- numero d'identite
- 沒有 d'identite
- 無。 d'identite
- 社會安全號碼
- 社會安全的程式碼
- 社會保險號碼
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le 程式碼 de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- 程式碼 sécu 
   
## <a name="german-drivers-license-number"></a>德國駕照編號

### <a name="format"></a>格式

11 個數字和字母的組合

### <a name="pattern"></a>模式

11 個數字和字母 （不區分大小寫）：
- 數字或字母 
- 兩位數 
- 六個數字或字母 
- 數字 
- 數字或字母

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_german_drivers_license 找到符合模式的內容。
- 至少下列一種為真：
    - 找不到來自 Keyword_german_drivers_license_number 的關鍵字。
    - 找不到來自 Keyword_german_drivers_license_collaborative 的關鍵字。
    - 找不到來自 Keyword_german_drivers_license 的關鍵字。
- 總和檢查碼通過。

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordgermandriverslicensenumber"></a>Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein-編號
- Fuhrerschein-編號
- Fuehrerschein-編號 
- Führerschein-Klasse 
- Fuhrerschein-Klasse 
- Fuehrerschein-Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein-編號 
- Fuhrerschein-編號 
- Fuehrerschein-編號 
- Führerschein-Klasse 
- Fuhrerschein-Klasse 
- Fuehrerschein-Klasse 
- DL 
- 通訊群組清單
- Driv Lic 
- Driv Licen 
- Driv 授權
- Driv 授權 
- Driv 授權 
- Driv 授權 
- Driv Lic 
- 驅動程式 Licen 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式 Lic 
- 驅動程式 Licen 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式授權 
- 駕 Lic 
- 駕 Licen 
- 駕照 
- 驅動程式的授權 
- 驅動程式的授權 
- 驅動程式的授權 
- 主導 Lic 
- 主導 Licen 
- 主導授權 
- 主導授權 
- Driving 授權 
- Driving 授權

#### <a name="keywordgermandriverslicensecollaborative"></a>Keyword_german_drivers_license_collaborative

- 編號 Führerschein 
- 編號 Fuhrerschein 
- 編號 Fuehrerschein 
- 否 Führerschein 
- 否 Fuhrerschein 
- 否 Fuehrerschein 
- N Führerschein 
- N Fuhrerschein 
- N Fuehrerschein
- 編號 Führerschein 
- 編號 Fuhrerschein 
- 編號 Fuehrerschein 
- 否 Führerschein 
- 否 Fuhrerschein 
- 否 Fuehrerschein 
- N Führerschein 
- N Fuhrerschein 
- N Fuehrerschein 

#### <a name="keywordgermandriverslicense"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
   
## <a name="german-passport-number"></a>德國護照號碼

### <a name="format"></a>格式

10 個數字或字母

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 第一個字元是數字或字母 （C、 F、 G、 H、 J、 K） 
- 三位數 
- 五個數字或字母 (C、 H、 J-N、 P、 R、 T、 V Z) 
- 數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_german_passport 找到符合模式的內容。
- 找不到來自五個關鍵字清單任一的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_german_passport_data 找到符合模式的內容。
- 找不到來自五個關鍵字清單任一的關鍵字。
- 總和檢查碼通過。

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordgermanpassport"></a>Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- passport
- 護照

#### <a name="keywordgermanpassportcollaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keywordgermanpassportnumber"></a>Keyword_german_passport_number

無法對 Reisepass 編號 Reisepass

#### <a name="keywordgermanpassport1"></a>Keyword_german_passport1

Reisepass 編號

#### <a name="keywordgermanpassport2"></a>Keyword_german_passport2

bnationalit.t
   
## <a name="germany-identity-card-number"></a>德國身分證號碼

### <a name="format"></a>格式

自從 2010 年 1 年 11 月： 九個字母和數字

從 1 1987 年 31 October 2010: 10 位數

### <a name="pattern"></a>模式

自從 1 年 11 月 2010 年：
- 一個字母 （不區分大小寫） 
- 八位數

從 1 1987 年 31 October 2010:
- 10 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_germany_id_card 找到符合模式的內容。
- 找不到來自 Keyword_germany_id_card 的關鍵字。

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordgermanyidcard"></a>Keyword_germany_id_card

- 身分證
- 識別碼
- 識別
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>希臘國民身分證

### <a name="format"></a>格式

7-8 個字母和數字加上破折號的組合

### <a name="pattern"></a>模式

七個字母和數字 （舊格式）︰
- 一個字母 （希臘文的任何字母） 
- 一條虛線 
- 六位數

八個字母和數字 （新格式）︰
- 其大寫字元，就會發生在希臘文與拉丁文字母 (ABEZHIKMNOPTYX) 中的兩個字母 
- 一條虛線 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_greece_id_card 找到符合模式的內容。
- 找不到來自 Keyword_greece_id_card 的關鍵字。

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordgreeceidcard"></a>Keyword_greece_id_card

- 希臘文身分證
- Tautotita
- ΔΕΛΤΊΟ ΑΣΤΥΝΟΜΙΚΉΣ ΤΑΥΤΌΤΗΤΑΣ
- ΤΑΥΤΌΤΗΤΑ
   
## <a name="hong-kong-identity-card-hkid-number"></a>香港身分證 (HKID) 號碼

### <a name="format"></a>格式

8-9 個字母和數字加上選擇性括住的最後一個字元的組合

### <a name="pattern"></a>模式

8-9 個字母的組合：
- 1-2 個字母 （不區分大小寫） 
- 六位數 
- 最後一個字元 （任何數字或字母 A），也就是檢查碼 （選擇性） 括住括號。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_hong_kong_id_card 找到符合模式的內容。
- 找不到來自 Keyword_hong_kong_id_card 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_hong_kong_id_card 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordhongkongidcard"></a>Keyword_hong_kong_id_card

- 香港身分證
- HKIDC
- 證
- 身分證
- hk 身分證
- 香港識別碼
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
   
## <a name="india-permanent-account-number-pan"></a>印度永久帳戶號碼 (PAN)

### <a name="format"></a>格式

10 個字母或四位數

### <a name="pattern"></a>模式

10 個字母或數字：
- 五個字母 （不區分大小寫） 
- 四位數 
- 這是一個字母檢查碼的字母

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_india_permanent_account_number 找到符合模式的內容。
- 找不到來自 Keyword_india_permanent_account_number 的關鍵字。
- 總和檢查碼通過。

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordindiapermanentaccountnumber"></a>Keyword_india_permanent_account_number

- 永久帳戶號碼 
- PAN 
   
## <a name="india-unique-identification-aadhaar-number"></a>印度唯一識別 （aadhaar） 碼數字

### <a name="format"></a>格式

12 位數包含選擇性空格或破折號

### <a name="pattern"></a>模式

12 位數：
- 四位數 
- 選擇性空格或破折號 
- 四位數 
- 選擇性空格或破折號 
- 最後一位數是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_india_aadhaar 找到符合模式的內容。
找不到來自 Keyword_india_aadhar 的關鍵字。
總和檢查碼通過。
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_india_aadhaar 找到符合模式的內容。
總和檢查碼通過。
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity>

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordindiaaadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>印尼身分識 (Ktp) 號碼

### <a name="format"></a>格式

16 位數包含選擇性句點

### <a name="pattern"></a>模式

16 位數：
- 二位數省代碼 
- 句點 （選擇性） 
- 二位數攝政或城市代碼 
- 二位數次行政區代碼 
- 句點 （選擇性） 
- DDMMYY 格式的六位數的出生日期 
- 句點 （選擇性） 
- 四位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_indonesia_id_card 找到符合模式的內容。
- 找不到來自 Keyword_indonesia_id_card 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_indonesia_id_card 找到符合模式的內容。

```
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordindonesiaidcard"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>國際銀行帳號 (IBAN)

### <a name="format"></a>格式

國碼/地區碼 （兩個字母） 加上檢查碼 （兩位數） 再加上 bban （最多 30 個字元）

### <a name="pattern"></a>模式

模式必須包含下列各項：

- 兩個字母的國碼/地區碼
- 兩位數檢查碼 （後面接著一個選用空格） 
- 1-7 組四字母或數字 （可以以空格分隔）
- 1-3 個字母或數字

每個國家/地區的格式是稍有不同。 IBAN 敏感資訊類型涵蓋這些 60 國家/地區：

ad、 ae、 al，在亞利桑那州，ba，是，bg、 bh、 頻道、 cr、 cy、 cz、 de、 粗、 執行、 卻、 es、 wi-fi、 於、 fr、 gb、 ge、 gi、 gl、 /gr、 hr、 hu，ie，il，是，它、 kw、 kz、 lb、 li、 lt、 lu、 lv，mc md、 我、 mk、 mr、 細明體、 記憶nl、 [否] pl、 pt、 ro、 rs、 sa、 se、 si、 sk、 sm、 tn、.msnavedit-linkcell、 vg

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_iban 找到符合模式的內容。
- 總和檢查碼通過。

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

   
## <a name="ip-address"></a>IP 位址

### <a name="format"></a>格式

#### <a name="ipv4"></a>IPv4:
帳戶版格式化 （句點） 和未格式化 （無句點） 之 IPv4 位址的複雜模式

#### <a name="ipv6"></a>IPv6:
哪一個帳戶表示格式化 IPv6 號碼 （其中包含冒號） 的複雜模式

### <a name="pattern"></a>模式

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

對於 IPv6 為 DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到來自 Keyword_ipaddress 的關鍵字。

DLP 原則是 95%以內，已偵測到此敏感資訊類型的對於 IPv4，如果鄰近性是 300 個字元：
- 規則運算式 Regex_ipv4_address 找到符合模式的內容。
- 找不到來自 Keyword_ipaddress 的關鍵字。

對於 IPv6 為 DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到來自 Keyword_ipaddress 的關鍵字。

```
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordipaddress"></a>Keyword_ipaddress

- IP （此關鍵字是區分大小寫）
- ip 位址 
- ip 位址
- 網際網路通訊協定
- IP כתובת ה 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>國際分類的治療法 （ICD-10-公分）

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 找不到來自 Dictionary_icd_10_cm 的關鍵字。

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

關鍵字

任何字詞從 Dictionary_icd_10_cm 關鍵字字典，這根據[治療法的國際分類、 十分之一修訂，臨床修改 （ICD-10-公分）](https://go.microsoft.com/fwlink/?linkid=852604)。 此類型只會尋找該字詞，不保險代碼。

   
## <a name="international-classification-of-diseases-icd-9-cm"></a>國際分類的治療法 （ICD-9-公分）

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 找不到來自 Dictionary_icd_9_cm 的關鍵字。

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

任何字詞從 Dictionary_icd_9_cm 關鍵字字典，這根據[治療法的國際分類、 二十九個修訂，臨床修改 （ICD-9-公分）](https://go.microsoft.com/fwlink/?linkid=852605)。 此類型只會尋找該字詞，不保險代碼。
   
## <a name="ireland-personal-public-service-pps-number"></a>愛爾蘭個人公用服務 (PPS) 號碼

### <a name="format"></a>格式

舊格式 （直到 2012 年 31):
- 七位數後尾隨 1-2 個字母 

新格式 (1 Jan 2013 年):
- 七位數後尾隨兩個字母

### <a name="pattern"></a>模式

舊格式 （直到 2012 年 31):
- 七位數 
- 1-2 個字母 （不區分大小寫） 

新格式 (1 Jan 2013 年):
- 七位數 
- 字母 （不區分大小寫） 這是一個字母檢查碼 
- 字母"A"或者"H"（不區分大小寫）

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_ireland_pps 找到符合模式的內容。
- 下列其中一項為真：
    - 找不到來自 Keyword_ireland_pps 的關鍵字。
    - 函數 Func_eu_date 找到正確日期格式的日期。
- 總和檢查碼通過。

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_ireland_pps 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordirelandpps"></a>Keyword_ireland_pps

- 個人公用服務號碼 
- PPS 數目 
- PPS Num 
- PPS [否]。 
- PPS # 
- PPS # 
- PPSN 
- 公用服務卡 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh。 PSP 
- PSP 
   
## <a name="israel-bank-account-number"></a>以色列銀行帳戶號碼

### <a name="format"></a>格式

13 位數

### <a name="pattern"></a>模式

格式：
- 兩位數 
- 一條虛線 
- 三位數 
- 一條虛線 
- 八位數

格式化：
- 13 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_israel_bank_account_number 找到符合模式的內容。
- 找不到來自 Keyword_israel_bank_account_number 的關鍵字。

```
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordisraelbankaccountnumber"></a>Keyword_israel_bank_account_number

- 銀行帳戶號碼 
- 銀行帳戶 
- 帳戶號碼 
- מספר חשבון בנק 
   
## <a name="israel-national-id"></a>以色列國民身分證

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_israeli_national_id_number 找到符合模式的內容。
- 找不到來自 Keyword_Israel_National_ID 的關鍵字。
- 總和檢查碼通過。

```
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordisraelnationalid"></a>Keyword_Israel_National_ID

- מספר זהות 
- 身分證號碼
   
## <a name="italy-drivers-license-number"></a>義大利駕照編號

### <a name="format"></a>格式

10 個字母和數字的組合

### <a name="pattern"></a>模式

- 10 個字母和數字的組合：
- 一個字母 （不區分大小寫） 
- 字母"A"或者"V"（不區分大小寫） 
- 七個字母 （不區分大小寫）、 數字或底線字元 
- 一個字母 （不區分大小寫）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。
- 找不到來自 Keyword_italy_drivers_license_number 的關鍵字。

```
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyworditalydriverslicensenumber"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 
   
## <a name="japan-bank-account-number"></a>日本銀行帳戶號碼

### <a name="format"></a>格式

7 或 8 位數

### <a name="pattern"></a>模式

銀行帳戶號碼：
- 7 或 8 位數
- 銀行帳戶分行代碼：
- 四位數 
- 一個空格或破折號 （選擇性） 
- 三位數

總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 找不到來自 Keyword_jp_bank_account 的關鍵字。
- 下列其中一項為真：
- 函數 Func_jp_bank_account_branch_code 找到符合模式的內容。
- 找不到來自 Keyword_jp_bank_branch_code 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 找不到來自 Keyword_jp_bank_account 的關鍵字。

```
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordjpbankaccount"></a>Keyword_jp_bank_account

- 檢查帳戶號碼 
- 檢查帳戶 
- 檢查帳戶 # 
- 檢查 Acct 數目 
- 檢查 Acct # 
- 檢查 Acct [否]。 
- 檢查帳戶 [否]。 
- 銀行帳戶號碼 
- 銀行帳戶 
- 銀行帳戶 # 
- 銀行帳戶號碼 
- 銀行 Acct # 
- 銀行 Acct [否]。 
- 銀行帳戶 [否]。 
- 節省帳戶號碼 
- 存款帳戶 
- 節省帳戶 # 
- 節省 Acct 數目 
- 節省 Acct # 
- 節省 Acct [否]。 
- 存款帳戶 [否]。 
- 轉帳帳戶號碼 
- 轉帳帳戶 
- 借方帳戶 # 
- 轉帳 Acct 號碼 
- 借方 Acct # 
- 轉帳 Acct [否]。 
- 轉帳帳戶 [否]。 
- 口座番号を当座預金口座の確認 
- # アカウントの確認、勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座 # 
- 銀行の勘定番号 
- 銀行のacct # 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座 # 
- 貯蓄勘定の数 
- 貯蓄勘定 # 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号 # 
- デビットのacct番号 
- デビット勘定 # 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keywordjpbankbranchcode"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>日本駕照編號

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

12 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_drivers_license_number 找到符合模式的內容。
- 找不到來自 Keyword_jp_drivers_license_number 的關鍵字。

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordjpdriverslicensenumber"></a>Keyword_jp_drivers_license_number

- dl # 
- DL # 
- dl # 
- DL # 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式授權 
- 駕照 
- 驅動程式授權 
- 驅動程式的授權 
- driving 授權 
- lic # 
- LIC # 
- lics # 
- 狀態識別碼 
- 狀態識別碼 
- 狀態識別碼 
- 低所得国 # 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>日本護照號碼

### <a name="format"></a>格式

兩個字母後尾隨七位數

### <a name="pattern"></a>模式

兩個字母 （不區分大小寫） 尾隨七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_passport 找到符合模式的內容。
- 找不到來自 Keyword_jp_passport 的關鍵字。

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordjppassport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート # 
   
## <a name="japan-resident-registration-number"></a>日本常駐居民登記號碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_resident_registration_number 找到符合模式的內容。
- 找不到來自 Keyword_jp_resident_registration_number 的關鍵字。

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordjpresidentregistrationnumber"></a>Keyword_jp_resident_registration_number

- 常駐居民登記號碼
- 駐留註冊數目 
- 居民基本登錄數目 
- 居民登記 [否]。 
- 駐留註冊 [否]。 
- 居民基本登錄 [否]。 
- 基本居民註冊 [否]。 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>日本社會保險號碼 (SIN)

### <a name="format"></a>格式

7-12 位數

### <a name="pattern"></a>模式

7-12 位數：
- 四位數 
- 連字號 （選用） 
- 六位數或
- 7-12 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_sin 找到符合模式的內容。
- 找不到來自 Keyword_jp_sin 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_jp_sin_pre_1997 找到符合模式的內容。
- 找不到來自 Keyword_jp_sin 的關鍵字。

```
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordjpsin"></a>Keyword_jp_sin

- 社會保險 [否]。 
- 社會保險 Num 
- 社會保險號碼 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="japanese-residence-card-number"></a>日文居住地證號碼

### <a name="format"></a>格式

12 個字母和數字

### <a name="pattern"></a>模式

12 個字母和數字：
- 兩個字母 （不區分大小寫）
- 八位數 
- 兩個字母 （不區分大小寫）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_jp_residence_card_number 找到符合模式的內容。
- 找不到來自 Keyword_jp_residence_card_number 的關鍵字。

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordjpresidencecardnumber"></a>Keyword_jp_residence_card_number

- 居住地證號碼
- 居住地卡否
- 居住地卡 #
- 在留カード番号
   
## <a name="malaysia-id-card-number"></a>馬來西亞身分證號碼

### <a name="format"></a>格式

12 位數包含選擇性連字號

### <a name="pattern"></a>模式

12 位數：
- YYMMDD 格式的六位數的出生日期 
- 一個破折號 （選擇性） 
- 雙字母的出生地代碼 
- 一個破折號 （選擇性） 
- 三個隨機的數字 
- 一位數性別代碼

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。
- 找不到來自 Keyword_malaysia_id_card_number 的關鍵字。

```
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordmalaysiaidcardnumber"></a>Keyword_malaysia_id_card_number

- 數位應用程式卡
- 我 /c
- 我 /c 沒有
- ic
- ic 沒有
- 證
- 識別卡
- 身分證
- k/p
- k/p 沒有
- kad akuan diri
- kad aplikasi 數位
- kad pengenalan 馬來西亞
- kp
- kp 沒有
- mykad
- mykas
- mykid
- mypr
- mytentera
- 馬來西亞身分證
- 馬來西亞身分證
- nric
- 個人識別卡
   
## <a name="netherlands-citizens-service-bsn-number"></a>荷蘭公民服務 (BSN) 號碼

### <a name="format"></a>格式

8-9 位數包含選擇性空格

### <a name="pattern"></a>模式

8-9 位數：
- 三位數 
- 一個空格 （選用） 
- 三位數 
- 一個空格 （選用） 
- 2-3 位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_netherlands_bsn 找到符合模式的內容。
- 找不到來自 Keyword_netherlands_bsn 的關鍵字。
- 函數 Func_eu_date2 找到正確日期格式的日期。
- 總和檢查碼通過。

```
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordnetherlandsbsn"></a>Keyword_netherlands_bsn

- 公民健保號碼 
- BSN 
- Burgerservicenummer 
- Sofinummer 
- Persoonsgebonden nummer 
- Persoonsnummer    

   
## <a name="new-zealand-ministry-of-health-number"></a>紐西蘭衛生部編號

### <a name="format"></a>格式

三個字母、 一個空格 （選用） 和四位數

### <a name="pattern"></a>模式

三個字母 （不區分大小寫） 的空間 （選用） 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。
- 找不到來自 Keyword_nz_terms 的關鍵字。
- 總和檢查碼通過。

```
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

關鍵字

Keyword_nz_terms

- NHI 
- JPRatingExplicitAllowed 
- 健康情況 
- 處理方式 
   
## <a name="norway-identification-number"></a>挪威識別碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數：
- DDMMYY 格式的六位數的出生日期 
- 三位數個人識別碼 
- 二位數檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_norway_id_number 找到符合模式的內容。
- 找不到來自 Keyword_norway_id_number 的關鍵字。
- 總和檢查碼通過。
- DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_norway_id_numbe 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordnorwayidnumber"></a>Keyword_norway_id_number

- 個人識別碼
- 挪威文識別碼
- 識別碼號碼
- 識別
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-id-number"></a>菲律賓統一多用途 ID 號碼

### <a name="format"></a>格式

以連字號分隔的 12 位數

### <a name="pattern"></a>模式

12 位數：
- 四位數 
- 連字號 
- 七位數 
- 連字號 
- 一位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_philippines_unified_id 找到符合模式的內容。
- 找不到來自 Keyword_philippines_id 的關鍵字。

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordphilippinesid"></a>Keyword_philippines_id

- 統一多用途識別碼 
- UMID 
- 身分證 
- Pinag isang 多 Layunin 識別碼
   
## <a name="poland-identity-card"></a>波蘭身分證明卡

### <a name="format"></a>格式

三個字母和六位數

### <a name="pattern"></a>模式

三個字母 （不區分大小寫） 尾隨六位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_polish_national_id 找到符合模式的內容。
找不到來自 Keyword_polish_national_id_passport_number 的關鍵字。
總和檢查碼通過。

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordpolishnationalidpassportnumber"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- 數目 dowodu osobistego
- Nazwa 我數目 dowodu osobistego
- Nazwa 我編號 dowodu osobistego
- Nazwa 我編號 dowodu tożsamości
- Dowód Tożsamości
- dow。 os。

   
## <a name="poland-national-id-pesel"></a>波蘭國民身分證 (PESEL)

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 個連續數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_pesel_identification_number 找到符合模式的內容。
- 找不到來自 Keyword_pesel_identification_number 的關鍵字。
- 總和檢查碼通過。

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordpeselidentificationnumber"></a>Keyword_pesel_identification_number

- 編號 PESEL
- PESEL   

   
## <a name="poland-passport"></a>波蘭護照

### <a name="format"></a>格式

兩個字母和七位數

### <a name="pattern"></a>模式

兩個字母 （不區分大小寫） 尾隨七位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_polish_passport_number 找到符合模式的內容。
- 找不到來自 Keyword_polish_national_id_passport_number 的關鍵字。
- 總和檢查碼通過。

```
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordpolishnationalidpassportnumber"></a>Keyword_polish_national_id_passport_number

- 數目 paszportu
- 編號。 Paszportu
- Paszport

   
## <a name="portugal-citizen-card-number"></a>葡萄牙公民證號碼

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_portugal_citizen_card 找到符合模式的內容。
- 找不到來自 Keyword_portugal_citizen_card 的關鍵字。

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordportugalcitizencard"></a>Keyword_portugal_citizen_card

- 公民證
- 國民身分證
- 副本
- Cartão de Cidadão
- Bilhete de Identidade
   
## <a name="saudi-arabia-national-id"></a>沙烏地阿拉伯國民身分證

### <a name="format"></a>格式

10 位數

### <a name="pattern"></a>模式

10 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。
- 找不到來自 Keyword_saudi_arabia_national_id 的關鍵字。

```
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsaudiarabianationalid"></a>Keyword_saudi_arabia_national_id

- 識別卡 
- 我介面卡數目 
- 識別碼 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡國民登記身分證 (NRIC) 號碼

### <a name="format"></a>格式

九個字母和數字

### <a name="pattern"></a>模式

- 九個字母和數字：
- 字母"F"、"G"、"S"或"T"（不區分大小寫） 
- 七位數 
- 一個字母檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_singapore_nric 找到符合模式的內容。
- 找不到來自 Keyword_singapore_nric 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_singapore_nric 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordsingaporenric"></a>Keyword_singapore_nric

- 國民登記身分證 
- 身分證號碼 
- NRIC 
- IC 
- 外部識別碼 
- FIN 
- 身份证 
- 身份證 
   
## <a name="south-africa-identification-number"></a>南非識別碼

### <a name="format"></a>格式

可以包含空格的 13 位數

### <a name="pattern"></a>模式

13 位數：
- YYMMDD 格式的六位數的出生日期 
- 四位數 
- 一位數公民指標 
- 數字"8"或"9" 
- 一位數總和檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_south_africa_identification_number 找到符合模式的內容。
- 找不到來自 Keyword_south_africa_identification_number 的關鍵字。
- 總和檢查碼通過。

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordsouthafricaidentificationnumber"></a>Keyword_south_africa_identification_number

- 身分證
- 識別碼
- 識別 
   
## <a name="south-korea-resident-registration-number"></a>南韓居民登記號碼

### <a name="format"></a>格式

13 位數包含連字號

### <a name="pattern"></a>模式

13 位數：
- YYMMDD 格式的六位數的出生日期 
- 連字號 
- 由世紀與性別判定的一位數 
- 四位數出生地區碼 
- 一位數，用來區分其前幾碼皆相同的人員 
- 檢查碼。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_south_korea_resident_number 找到符合模式的內容。
- 找不到來自 Keyword_south_korea_resident_number 的關鍵字。
- 總和檢查碼通過。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_south_korea_resident_number 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordsouthkorearesidentnumber"></a>Keyword_south_korea_resident_number

- 國民身分證 
- 公民登記號碼 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호
   
## <a name="spain-social-security-number-ssn"></a>西班牙社會安全號碼 (SSN)

### <a name="format"></a>格式

11-12 位數

### <a name="pattern"></a>模式

11-12 位數：
- 兩位數 
- 正斜線 （選用） 
- 7-8 位數 
- 正斜線 （選用） 
- 兩位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_spanish_social_security_number 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

## <a name="sql-server-connection-string"></a>SQL Server 連線字串

### <a name="format"></a>格式

字串 「 使用者 Id 」、 「 使用者 ID 」、 「 uid 」 或 「 使用者識別碼 」 後面跟著字元和下列模式中所述的字串。

### <a name="pattern"></a>模式

- 字串 「 使用者 Id 」、 「 使用者 ID 」、 「 uid 」 或者 「 UserId 」
- 1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合
- 將字串 「 密碼 」 或 「 pwd 」 不的小寫字母前面 「 pwd 」
- 等號 （=）
- 任何不錢幣符號 （$）、 百分比符號 （%），大於符號 (>) 符號字元 (@)、 引號 （"）、 分號 （;）、 左大括弧 ([]) 或左大括弧 （{}）
- 不是以分號 （;） 的 7-128 個字元的任何組合反斜線 （/） 或雙引號 （"）
- 分號 （;）或引號 （"）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。
- 從 CEP_GlobalFilter 關鍵字**不**找到。
- 規則運算式 CEP_PasswordPlaceHolder**不**尋找符合模式的內容。
- 規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。

```
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cepglobalfilter"></a>CEP_GlobalFilter

- 某些密碼
- somepassword
- secretPassword
- 範例

#### <a name="ceppasswordplaceholder"></a>CEP_PasswordPlaceHolder

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- Password 或 pwd 後面接著 0-2 空格，等號 （=）、 0-2 空格，並星號 （*）-或-
- Password 或 pwd 後面加上：
    - 等號 （=）
    - 小於符號 (<)
    - 1-200 的字元上方-或小寫字母、 數字、 星號 （*）、 連字號 （-）、 底線 (_) 或空白字元的任意組合
    - 大於符號 (>)

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。

- contoso
- fabrikam
- northwind
- 沙箱化
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s int。<!--no-hyperlink-->net

## <a name="sweden-national-id"></a>瑞典國民身分證號

### <a name="format"></a>格式

10 或 12 位數和一個選用分隔符號

### <a name="pattern"></a>模式

10 或 12 位數和一個選用分隔符號：
- 2-4 位數 （選用） 
- 格式 YYMMDD 的六位數，日期 
- 分隔符號"-"或"+"（選用），再加上
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_swedish_national_identifier 找到符合模式的內容。
- 總和檢查碼通過。

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

否
   
## <a name="sweden-passport-number"></a>瑞典護照號碼

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_sweden_passport_number 找到符合模式的內容。
- 下列其中一項為真：
    - 找不到來自 Keyword_passport 的關鍵字。
    - 找不到來自 Keyword_sweden_passport 的關鍵字。

```
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordswedenpassport"></a>Keyword_sweden_passport

- visa 需求 
- 外星註冊卡 
- Schengen 簽證 
- Schengen visa 
- Visa 處理 
- Visa 類型 
- 單一項目 
- 多個項目 
- G3 處理費用 

#### <a name="keywordpassport"></a>Keyword_passport

- 護照號碼 
- Passport 否 
- Passport # 
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート # 
- Numéro de passeport 
- Passeport n ° 
- Passeport 非 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 
   
## <a name="swift-code"></a>SWIFT 代碼

### <a name="format"></a>格式

四個字母後尾隨 5-31 個字母或數字

### <a name="pattern"></a>模式

四個字母後尾隨 5-31 個字母或數字：
- 四字母銀行代碼 （不區分大小寫） 
- 一個選用空格 
- 4-28 個字母或數字 (基本銀行帳戶號碼 (BBAN)) 
- 一個選用空格 
- 1-3 個字母或數字 （BBAN 的其餘部分）

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_swift 找到符合模式的內容。
- 找不到來自 Keyword_swift 的關鍵字。

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordswift"></a>Keyword_swift

- 國際標準 9362 組織 
- iso 9362 
- iso9362 
- swift\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift 代碼 
- swift 號碼 # 
- swift 路由號碼 
- bic 數目 
- bic 程式碼 
- bic\# 
- bic\# 
- 銀行識別碼程式碼 
- 標準化9362 
- 迅速 # 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- 組織 internationale de normalisation 9362 
- rapide\# 
- SWIFT 代碼 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \#BIC 
- 程式碼 identificateur de banque 
   
## <a name="taiwan-national-id"></a>台灣國家識別碼

### <a name="format"></a>格式

一個字母 （英文） 尾隨九位數

### <a name="pattern"></a>模式

一個字母 （英文） 尾隨九位數：
- 一個字母 （以英文、 不區分大小寫） 
- 數字"1"或"2" 
- 八位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_taiwanese_national_id 找到符合模式的內容。
- 找不到來自 Keyword_taiwanese_national_id 的關鍵字。
- 總和檢查碼通過。

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordtaiwanesenationalid"></a>Keyword_taiwanese_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>台灣護照號碼

### <a name="format"></a>格式

- 生物識別護照號碼： 九位數
- 非生物識別護照號碼： 九位數

### <a name="pattern"></a>模式
生物識別護照號碼：
- 數字"3" 
- 八位數

非生物識別護照號碼：
- 九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_taiwan_passport 找到符合模式的內容。
- 找不到來自 Keyword_taiwan_passport 的關鍵字。

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordtaiwanpassport"></a>Keyword_taiwan_passport

- 中華民國護照號碼 
- 護照號碼 
- Passport 沒有 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>台灣居民憑證 (ARC/TARC) 號碼

### <a name="format"></a>格式

10 個字母和數字

### <a name="pattern"></a>模式

10 個字母和數字：
- 兩個字母 （不區分大小寫） 
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。
- 找不到來自 Keyword_taiwan_resident_certificate 的關鍵字。

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordtaiwanresidentcertificate"></a>Keyword_taiwan_resident_certificate

- 內建的憑證 
- 駐留 Cert 
- 內建的憑證。 
- 識別卡 
- 外星居民憑證 
- 弧線 
- 台灣區域居民憑證 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>泰文母體識別程式碼

### <a name="format"></a>格式

13 位數

### <a name="pattern"></a>模式

13 位數：
- 第一個數字不是 0 或 9 
- 12 位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_Thai_Citizen_Id 找到符合模式的內容。
- 找不到來自 Keyword_Thai_Citizen_Id 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_Thai_Citizen_Id 找到符合模式的內容。

```
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordthaicitizenid"></a>Keyword_Thai_Citizen_Id

- 識別碼號碼
- 識別碼
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>土耳其文的國家識別碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_Turkish_National_Id 找到符合模式的內容。
- 找不到來自 Keyword_Turkish_National_Id 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_Turkish_National_Id 找到符合模式的內容。

```
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordturkishnationalid"></a>Keyword_Turkish_National_Id

- 繁體中文 Kimlik 否
- 繁體中文 Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık 沒有

## <a name="uk-drivers-license-number"></a>英國 駕照編號

### <a name="format"></a>格式

18 個字母和數字中指定之格式的組合

### <a name="pattern"></a>模式

18 個字母和數字：
- 五個字母 （不區分大小寫） 或取代字母的數字"9" 
- 一位數 
- 五位數的日期格式 ddmmy 表示出生日期 
- 兩個字母 （不區分大小寫） 或取代字母的數字"9" 
- 五位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_uk_drivers_license 找到符合模式的內容。
- 找不到來自 Keyword_uk_drivers_license 的關鍵字。
- 總和檢查碼通過。

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordukdriverslicense"></a>Keyword_uk_drivers_license

- DVLA 
- 淺 van 能夠 
- quadbikes 
- 馬達車輛 
- 125cc 
- sidecar 
- tricycles 
- 機車 
- photocard 授權 
- 學習者單元驅動程式 
- 授權持有者 
- 授權持有者 
- driving 授權 
- driving 授權 
- 雙重控制汽車 
   
## <a name="uk-electoral-roll-number"></a>英國 Electoral Roll 數目

### <a name="format"></a>格式

兩個字母後尾隨 1-4 位數

### <a name="pattern"></a>模式

兩個字母 （不區分大小寫） 尾隨 1-4 個數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_uk_electoral 找到符合模式的內容。
- 找不到來自 Keyword_uk_electoral 的關鍵字。

```
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordukelectoral"></a>Keyword_uk_electoral

- 會議提名 
- 提名表單 
- 選舉註冊 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>英國 國民健保服務號碼

### <a name="format"></a>格式

以空格分隔的 10-17 位數

### <a name="pattern"></a>模式

10-17 位數：
- 3 或 10 位數 
- 一個空格 
- 三位數 
- 一個空格 
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_uk_nhs_number 找到符合模式的內容。
- 下列其中一項為真：
    - 找不到來自 Keyword_uk_nhs_number 的關鍵字。
    - 找不到來自 Keyword_uk_nhs_number1 的關鍵字。
    - 找不到來自 Keyword_uk_nhs_number_dob 的關鍵字。
- 總和檢查碼通過。

```
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyworduknhsnumber"></a>Keyword_uk_nhs_number

- 國民健保服務 
- nhs 
- 健康情況服務授權 
- 健康情況授權

#### <a name="keyworduknhsnumber1"></a>Keyword_uk_nhs_number1

- 病患識別碼 
- 病患識別碼 
- 病患否 
- 病患的數字

#### <a name="keyworduknhsnumberdob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D.O.B 
- 出生日期 
- 出生日期 
   
## <a name="uk-national-insurance-number-nino"></a>英國 國家保險號碼 (NINO)

### <a name="format"></a>格式

7 個字元或空格或連字號分隔的 9 個字元

### <a name="pattern"></a>模式

兩個可能的模式：

- 兩個字母 (有效 NINOs 中此前置詞，此模式會驗證; 使用僅限特定字元不區分大小寫)
- 六位數
- 可以是 'A'、 'B'、 'C'，或有 ' （例如前置詞，只有某些字元中允許之尾碼; 不區分大小寫）

或

- 兩個字母
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 可以是 'A'、 'B'、 'C'，或有 '

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_uk_nino 找到符合模式的內容。
- 找不到來自 Keyword_uk_nino 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_uk_nino 找到符合模式的內容。
- 找不到來自 Keyword_uk_nino 的關鍵字。

```
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyworduknino"></a>Keyword_uk_nino

- 國家保險號碼 
- 國家保險捐款 
- 保護法案 
- 保險 
- 社會安全號碼 
- 保險應用程式 
- 醫療應用程式 
- 社會保險 
- 醫療注意事項 
- 社會安全 
- 英國 
- 保險    
   
## <a name="us--uk-passport-number"></a>美國 / 英國 護照號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_usa_uk_passport 找到符合模式的內容。
- 找不到來自 Keyword_passport 的關鍵字。

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordpassport"></a>Keyword_passport

- 護照號碼 
- Passport 否 
- Passport # 
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート # 
- Numéro de passeport 
- Passeport n ° 
- Passeport 非 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 
   
## <a name="us-bank-account-number"></a>美國銀行帳戶號碼

### <a name="format"></a>格式

8-17 位數

### <a name="pattern"></a>模式

8-17 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 規則運算式 Regex_usa_bank_account_number 找到符合模式的內容。
- 找不到來自 Keyword_usa_Bank_Account 的關鍵字。

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordusabankaccount"></a>Keyword_usa_Bank_Account

- 檢查帳戶號碼 
- 檢查帳戶 
- 檢查帳戶 # 
- 檢查 Acct 數目 
- 檢查 Acct # 
- 檢查 Acct [否]。 
- 檢查帳戶 [否]。 
- 銀行帳戶號碼 
- 銀行帳戶 # 
- 銀行帳戶號碼 
- 銀行 Acct # 
- 銀行 Acct [否]。 
- 銀行帳戶 [否]。 
- 節省帳戶號碼 
- 省下的帳戶。 
- 節省帳戶 # 
- 節省 Acct 數目 
- 節省 Acct # 
- 節省 Acct [否]。 
- 存款帳戶 [否]。 
- 轉帳帳戶號碼 
- 轉帳帳戶 
- 借方帳戶 # 
- 轉帳 Acct 號碼 
- 借方 Acct # 
- 轉帳 Acct [否]。 
- 轉帳帳戶 [否]。 
   
## <a name="us-drivers-license-number"></a>美國駕駛執照號碼

### <a name="format"></a>格式

隨州別

### <a name="pattern"></a>模式

狀態-例如，紐約而定：
- 九位數格式化 like ddd ddd ddd 會比對。
- 不會符合 ddddddddd 類似的九位數。

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_ [state_name] _drivers_license_name 的關鍵字。
- 找不到來自 Keyword_us_drivers_license 的關鍵字。

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_ [state_name] _drivers_license_name 的關鍵字。
- 找不到來自 Keyword_us_drivers_license_abbreviations 的關鍵字。
- 找不到來自 Keyword_us_drivers_license 的關鍵字。

```
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordusdriverslicenseabbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- 通訊群組清單 
- CDL 
- CDLS 
- 識別碼 
- 識別碼 
- DL # 
- DL # 
- CDL # 
- CDLS # 
- 識別碼 #
- 識別碼 # 
- 識別碼 
- 識別碼號碼 
- LIC 
- LIC # 

#### <a name="keywordusdriverslicense"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- 驅動程式 Lic 
- 驅動程式 Lics 
- 驅動程式授權 
- 驅動程式授權 
- DriversLic 
- DriversLics 
- 執照 
- DriversLicenses 
- 驅動程式 Lic 
- 驅動程式 Lics 
- 驅動程式授權 
- 驅動程式授權 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- 驅動程式 ' Lic 
- 驅動程式 ' Lics 
- 驅動程式 ' 授權 
- 驅動程式 ' 授權
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- 駕 Lic 
- 駕 Lics 
- 駕照 
- 驅動程式的授權 
- 識別碼 
- 識別數字 
- 識別 # 
- 證 
- id 卡 
- 識別卡 
- 識別卡 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- 驅動程式 Lic # 
- 驅動程式 Lics # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- DriversLic # 
- DriversLics # 
- 執照 # 
- DriversLicenses # 
- 驅動程式 Lic # 
- 驅動程式 Lics # 
- 驅動程式授權 # 
- 驅動程式授權 # 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- 驅動程式 ' Lic # 
- 驅動程式 ' Lics # 
- 驅動程式 ' 授權 # 
- 驅動程式 ' 授權 # 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- 駕 Lic # 
- 駕 Lics # 
- 驅動程式的授權 # 
- 驅動程式的授權 # 
- 證 # 
- id 卡 # 
- 識別卡 # 
- 識別卡 # 


#### <a name="keywordstatenamedriverslicensename"></a>於 Keyword_ [state_name] _drivers_license_name

- 州別縮寫 (例如"NY") 
- 州名稱 (例如"New York")    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>美國個別 Taxpayer 識別號碼 (ITIN)

### <a name="format"></a>格式

九位數，以"9"開頭且包含"7"8"的第四個位數，可選擇加上空格或破折號

### <a name="pattern"></a>模式

格式：
- 數字"9" 
- 兩位數 
- 一個空格或破折號 
- "7"或者"8" 
- 數字 
- 一個空格或破折號 
- 四位數

格式化：
- 數字"9" 
- 兩位數 
- "7"或者"8" 
- 五位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_formatted_itin 找到符合模式的內容。
- 至少下列一種為真：
    - 找不到來自 Keyword_itin 的關鍵字。
    - 函數 Func_us_address 找到正確日期格式中的地址。
    - 函數 Func_us_date 找到正確日期格式的日期。
    - 找不到來自 Keyword_itin_collaborative 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_unformatted_itin 找到符合模式的內容。
- 至少下列一種為真：
    - 找不到來自 Keyword_itin_collaborative 的關鍵字。
    - 函數 Func_us_address 找到正確日期格式中的地址。
    - 函數 Func_us_date 找到正確日期格式的日期。

```
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyworditin"></a>Keyword_itin

- taxpayer 
- 稅務識別碼 
- 稅務識別碼 
- itin 
- ssn 
- 錫 
- 社會安全 
- 稅務付款者 
- itins 
- taxid 
- 個別 taxpayer 

#### <a name="keyworditincollaborative"></a>Keyword_itin_collaborative

- License 
- DL 
- DOB 
- 出生日期 
- 生日 
- 出生日期 
   
## <a name="us-social-security-number-ssn"></a>美國社會安全號碼 (SSN)

### <a name="format"></a>格式

9 位數，可採用格式化或未格式化模式

> [!NOTE]
> SSN 如果發出 mid 2011 之前，已增強式格式設定其中某些部分的數字必須落在有效特定範圍內 （但沒有任何總和檢查碼）。

### <a name="pattern"></a>模式

四個函數尋找 Ssn 四個不同的模式：
- Func_ssn 找到與預先 2011年強式的格式設定，以連字號或空格 (ddd ddd-dd-dddd 或 ddd dd dddd) 格式化 Ssn
- Func_unformatted_ssn 找尋找 Ssn 具有預先 2011年強式的格式設定，會以未格式化為九個連續數字 (ddddddddd)
- Func_randomized_formatted_ssn 找到以連字號或空格 (ddd ddd-dd-dddd 或 ddd dd dddd) 格式化的文章 2011 Ssn
- Func_randomized_unformatted_ssn 找到 post 2011 Ssn 所格式化為九個連續數字 (ddddddddd)

### <a name="checksum"></a>總和檢查碼

否


### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_ssn 找到符合模式的內容。
- 找不到來自 Keyword_ssn 的關鍵字。

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 func_unformatted_ssn 找找到符合模式的內容。
- 找不到來自 Keyword_ssn 的關鍵字。

DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_randomized_formatted_ssn 找到符合模式的內容。
- 找不到來自 Keyword_ssn 的關鍵字。
- 函數 func_ssn 找不到符合模式的內容。

DLP 原則是 55%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
- 函數 Func_randomized_unformatted_ssn 找到符合模式的內容。
- 找不到來自 Keyword_ssn 的關鍵字。
- 函數 func_unformatted_ssn 找不到符合模式的內容。

```
<!-- U.S. Social Security Number (SSN) -->
    <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordssn"></a>Keyword_ssn

- 社會安全 
- 社會安全 # 
- Soc Sec 
- SSN 
- SSN 
- SSN # 
- SS # 
- SSID 
   

