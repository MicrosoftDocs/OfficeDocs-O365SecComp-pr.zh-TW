---
title: 敏感資訊類型在找什麼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含 80 準備好讓您能夠使用 DLP 原則中的敏感資訊類型。本主題列出所有的這些機密資訊類型及顯示新的 DLP 原則會尋找時被每個類型。
ms.openlocfilehash: 2e59b322730ca7fa828a685ed3a80c48ebdbbfd8
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972355"
---
# <a name="what-the-sensitive-information-types-look-for"></a>敏感資訊類型在找什麼

Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題列出所有的這些機密資訊類型及顯示新的 DLP 原則會尋找時被每個類型。敏感資訊類型定義由可藉由規則運算式或函數的模式。此外，例如關鍵字和總和檢查碼佐證性證據可用來識別敏感資訊類型。信賴等級和鄰近性也會用於評估程序。
  
## <a name="aba-routing-number"></a>阿拉巴馬州路由號碼

### <a name="format"></a>格式

可採用格式化或未格式化模式的 9 位數

### <a name="pattern"></a>模式

格式化：
- 以 0、1、2、3、6、7 或 8 開頭的四位數
- 一個連字號
- 四位數
- 一個連字號
- 一個數字

未格式化： 9 連續的數字開頭為 0、 1、 2、 3、 6、 7 或 8 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_aba_routing 找到符合模式的內容。
- 找到來自於 Keyword_ABA_Routing 的關鍵字。

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

- aba
- 
aba #
- 
aba routing #
- 
aba routing number
- 
aba#
- 
abarouting#
- 
aba number
- 
abaroutingnumber
- 
american bank association routing #
- 
american bank association routing number
- 
americanbankassociationrouting#
- 
americanbankassociationroutingnumber
- 
bank routing number
- 
bankrouting#
- 
bankroutingnumber
- 
routing transit number
- 
RTN
 
   
## <a name="argentina-national-identity-dni-number"></a>阿根廷國民識別 (DNI) 碼

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

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_argentina_national_id 會找出符合模式的內容。
- 從 Keyword_argentina_national_id 關鍵字是找到。

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

- Argentina National Identity number
 
- 身分識別 
- 識別國民身分識別卡 
- DNI
 
- NIC 的人員國民登錄 
- Documento Nacional de Identidad
 
- Registro Nacional de las Personas
 
- Identidad
 
- Identificación
 
   
## <a name="australia-bank-account-number"></a>澳洲銀行帳戶號碼

### <a name="format"></a>格式

包含或不含銀行代號的 6-10 位數

### <a name="pattern"></a>模式

帳戶號碼為 6-10 位數。澳洲銀行狀態分支號碼：
- 三位數 
- 一個連字號 
- 三位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。
- 找到來自於 Keyword_australia_bank_account_number 的關鍵字。
- 規則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。
- 找到來自於 Keyword_australia_bank_account_number 的關鍵字。

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

- swift bank code
- 
correspondent bank
- 
base currency
- 
usa account
- 
holder address
- 
bank address
- 
information account
- 
fund transfers
- 
bank charges
- 
bank details
- 
banking information
- 
full names
- 

iaea

   
## <a name="australia-drivers-license-number"></a>澳洲駕照編號

### <a name="format"></a>格式

九個字母和數字

### <a name="pattern"></a>模式

九個字母和數字： 

- 兩個數字或字母 (不區分大小寫) 
- 兩位數 
- 五個數字或字母 (不區分大小寫)

OR

- 1-2 選用字母 (不區分大小寫) 
- 4-9 位數

OR

- 九個數字或字母 (不區分大小寫)

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_australia_drivers_license_number 的關鍵字。
- 找不到來自於 Keyword_australia_drivers_license_number_exclusions 的關鍵字。

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

- international driving permits
- 
australian automobile association
- 
sydney nsw
- 
international driving permit
- DriverLicence
- DriverLicences
- 驅動程式 Lic
- Driver Licence

- Driver Licences

- DriversLic
- DriversLicence
- DriversLicences
- 發行的驅動程式 Lic
- 發行的驅動程式 Lics
- 發行的驅動程式授權
- 發行的驅動程式授權
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
- Driver's Licence

- Driver's Licences

- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- 
Driver Lics#

- 授權 # 驅動程式
- 授權 # 驅動程式
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- 發行的驅動程式 Lic #
- 發行的驅動程式 Lics #
- 授權 # 驅動程式
- 授權 # 驅動程式
- Driver'Lic#

- Driver'Lics#

- Driver'Licence#

- Driver'Licences#

- Driver' Lic#

- Driver' Lics#

- 驅動程式 ' 授權 #
- 驅動程式 ' 授權 #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#

- Driver's Lics#

- 駕授權 #
- 駕授權 # 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- 驅動程式授權
- 驅動程式授權
- 執照
- DriversLicenses
- 發行的驅動程式授權
- 發行的驅動程式授權
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
- 授權 # 驅動程式
- 授權 # 驅動程式
- 執照 #
- DriversLicenses #
- 授權 # 驅動程式
- 授權 # 驅動程式
- Driver'License#

- Driver'Licenses#

- Driver' License#

- Driver' Licenses#

- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#

- 

Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>澳洲醫療帳戶號碼

### <a name="format"></a>格式

10-11 位數

### <a name="pattern"></a>模式

10-11 位數：
- 第一個數字在 2-6 的範圍內
- 第九個數字是檢查碼
- 第十個數字是簽發碼
- 第十一個數字 (選用) 是個人碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：
- 函數 Func_australian_medical_account_number 找到符合模式的內容。
- 找到來自於 Keyword_Australia_Medical_Account_Number 的關鍵字。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
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

- bank account details
- 
medicare payments
- 
mortgage account
- 
bank payments
- 
information branch
- 
credit card loan
- 
department of human services
- 本機服務
- 

medicare

   
## <a name="australia-passport-number"></a>澳洲護照號碼

### <a name="format"></a>格式

字母後尾隨七位數

### <a name="pattern"></a>模式

一個字母 (不區分大小寫) 後尾隨七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_australia_passport_number 找到符合模式的內容。
- 從 Keyword_passport 或 Keyword_australia_passport_number 關鍵字是找到。

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

- Passport Number
- 
Passport No
- Passport#

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- 
パスポート ＃
 
- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport#

- Passeport#

- PasseportNon
- Passeportn °


#### <a name="keywordaustraliapassportnumber"></a>Keyword_australia_passport_number

- passport
- 
passport details
- 
immigration and citizenship
- 
commonwealth of australia
- 
department of immigration
- 
residential address
- 
department of immigration and citizenship
- visa

- 
national identity card
- 護照號碼
- 
travel document
- 

issuing authority
   
## <a name="australia-tax-file-number"></a>澳洲稅籍編號

### <a name="format"></a>格式

8-9 位數

### <a name="pattern"></a>模式

通常會有如下空格的 8-9 位數：
- 三位數 
- 一個選用空格 
- 三位數 
- 一個選用空格 
- 2-3 位數，最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_australian_tax_file_number 找到符合模式的內容。
- 找不到來自於 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。
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

- australian business number
- 
marginal tax rate
- 
medicare levy
- 
portfolio number
- 
service veterans
- 
withholding tax
- 
individual tax return
- 

tax file number

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
   
## <a name="belgium-national-number"></a>比利時國民編碼

### <a name="format"></a>格式

11 位數加上分隔符號

### <a name="pattern"></a>模式

11 位數加上分隔符號：
- 六位數加上兩個句點組合成 YY.MM.DD 的格式代表出生日期  
- 一個連字號 
- 三個連續數字 (奇數男生，偶數女生)  
- 句點  
- 兩位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_belgium_national_number 會找出符合模式的內容。
- 從 Keyword_belgium_national_number 關鍵字是找到。
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

- Identity
- Registration
- Identification 
- ID 
- Identiteitskaart
- Registratie nummer 
 
- Identificatie nummer
 
- Identiteit
- Registratie
- Identificatie

 
- Carte d’identité
 
- numéro d'immatriculation
- numéro d'identification
- 
identité
 
- inscription
 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>巴西 CPF 碼

### <a name="format"></a>格式

11 位數包含檢查碼，可格式化或未格式化

### <a name="pattern"></a>模式

格式化：
- 三位數 
- 句點  
- 三位數 
- 句點  
- 三位數 
- 一個連字號 
- 兩位數的檢查碼

未格式化：
- 11 位數，最後二位數是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_brazil_cpf 會找出符合模式的內容。
- 從 Keyword_brazil_cpf 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_brazil_cpf 會找出符合模式的內容。
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
- Identification
- Registration
- Revenue
- Cadastro de Pessoas Físicas
 
- Imposto
 
- Identificação
 
- Inscrição
 
- Receita

 
   
## <a name="brazil-legal-entity-number-cnpj"></a>巴西法律實體號碼 (CNPJ)

### <a name="format"></a>格式

14 位數包含登記碼、分支碼和檢查碼加上分隔符號

### <a name="pattern"></a>模式
14 位數，加上分隔符號：
- 兩位數 
- 句點  
- 三位數 
- 句點  
- 三位數 (此前 8 位數為登記碼)  
- 一個正斜線 
- 四位數分支碼  
- 一個連字號 
- 兩位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_brazil_cnpj 會找出符合模式的內容。
- 從 Keyword_brazil_cnpj 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_brazil_cnpj 會找出符合模式的內容。
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
- CNPJ-MF
 
- National Registry of Legal Entities
 
- Taxpayers Registry
 
- Legal entity
 
- Legal entities
 
- Registration Status
 
- Business
 
- Company
- CNPJ
 
- Cadastro Nacional da Pessoa Jurídica
 
- Cadastro Geral de Contribuintes
 
- CGC
 
- Pessoa jurídica
 
- Pessoas jurídicas
 
- Situação cadastral
 
- Inscrição
 
- Empresa
 
   
## <a name="brazil-national-id-card-rg"></a>	巴西國民身分證 (RG)

### <a name="format"></a>格式

Registro Geral （舊格式）： 9 的數字

Registro de Identidade (RIC) （新格式）： 11 位數

### <a name="pattern"></a>模式

Registro Geral (舊格式)：
- 兩位數 
- 句點  
- 三位數 
- 句點  
- 三位數 
- 一個連字號 
- 一位數的檢查碼

Registro de Identidade (RIC) （新格式）：
- 10 位數  
- 一個連字號 
- 一位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_brazil_rg 會找出符合模式的內容。
- 從 Keyword_brazil_rg 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_brazil_rg 會找出符合模式的內容。
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

Cédula de identidade 識別卡國家識別碼 número de rregistro registro de Iidentidade registro geral FEA-RG-APP-NO-VERSION （這個關鍵字是區分大小寫） RIC （這個關鍵字是區分大小寫） 
   
## <a name="canada-bank-account-number"></a>加拿大銀行帳戶號碼

### <a name="format"></a>格式

7 或 12 位數

### <a name="pattern"></a>模式

加拿大銀行帳戶號碼是 7 位數或 12 位數。

加拿大銀行帳戶交換號碼是：
- 五位數 
- 一個連字號 
- 三個數字或
- 一個零 "0" 
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 找到來自於 Keyword_canada_bank_account_number 的關鍵字。
- 規則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 找到來自於 Keyword_canada_bank_account_number 的關鍵字。

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

- canada savings bonds
- 
canada revenue agency
- 
canadian financial institution
- 
direct deposit form
- 
canadian citizen
- 
legal representative
- 
notary public
- 
commissioner for oaths
- 
child care benefit
- 
universal child care
- 
canada child tax benefit
- 
income tax benefit
- 
harmonized sales tax
- social insurance number
- 
income tax refund
- 
child tax benefit
- 
territorial payments
- 
institution number
- 
deposit request
- 
banking information
- 

direct deposit
   
## <a name="canada-drivers-license-number"></a>加拿大駕照編號

### <a name="format"></a>格式

隨省分而不同

### <a name="pattern"></a>模式

Alberta、British Columbia、Manitoba、New Brunswick、Newfoundland/Labrador、Nova Scotia、Ontario、Prince Edward Island、Quebec 和 Saskatchewan 各有不同模式

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_[province_name]_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_[province_name]_drivers_license_name 的關鍵字。
- 找到來自於 Keyword_canada_drivers_license 的關鍵字。

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

#### <a name="keywordprovincenamedriverslicensename"></a>Keyword_[province_name]_drivers_license_name

- 省分縮寫，例如 AB
- 
省分名稱，例如 Alberta

#### <a name="keywordcanadadriverslicense"></a>Keyword_canada_drivers_license

- DL
- DLS
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
- Driver Licence

- Driver Licences

- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- 執照
- DriversLicenses
- 發行的驅動程式 Lic
- 發行的驅動程式 Lics
- 發行的驅動程式授權
- 發行的驅動程式授權
- 發行的驅動程式授權
- 發行的驅動程式授權
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
- Driver's Licence

- Driver's Licences

- Permis de Conduire
- id
- 識別碼
- 
idcard number
- 
idcard numbers
- 
idcard #
- 
idcard #s
- idcard 卡片
- idcard 卡
- idcard
- identification number

- identification numbers

- identification #

- 
identification #s
- 識別卡
- 識別卡
- 
identification
 
- DL#
- 
DLS#
 
- CDL#
 
- CDLS#
 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- 
Driver Lics#
 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- DriversLic # 
- DriversLics # 
- 執照 # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- 發行的驅動程式 Lic # 
- 發行的驅動程式 Lics # 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- Driver'Lic#
 
- Driver'Lics#
 
- Driver'License#
 
- Driver'Licenses#
 
- Driver'Licence#
 
- Driver'Licences#
 
- Driver' Lic#
 
- Driver' Lics#
 
- Driver' License#
 
- Driver' Licenses#
 
- 驅動程式 ' 授權 # 
- 驅動程式 ' 授權 # 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic#
 
- Driver's Lics#
 
- Driver's License#
 
- Driver's Licenses#
 
- 駕授權 # 
- 駕授權 # 
- Permis de Conduire # 
- 識別碼 # 
- id # 
- idcard card#
 
- idcard cards#
 
- idcard#
 
- identification card#
 
- identification cards#
 
- identification#
 
   
## <a name="canada-health-service-number"></a>加拿大國家健保號碼

### <a name="format"></a>格式

10 位數

### <a name="pattern"></a>模式

10 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_canada_health_service_number 找到符合模式的內容。
- 找到來自於 Keyword_canada_health_service_number 的關鍵字。

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

- personal health number
- 
patient information
- 狀況服務
- 
speciality services
- 
automobile accident
- 
patient hospital
- 
psychiatrist
- 
workers compensation
- 
disability
      
## <a name="canada-passport-number"></a>加拿大護照號碼

### <a name="format"></a>格式

兩個大寫字母後尾隨六位數

### <a name="pattern"></a>模式

兩個大寫字母後尾隨六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_canada_passport_number 找到符合模式的內容。
- 從 Keyword_canada_passport_number 或 Keyword_passport 關鍵字是找到。

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

- canadian citizenship
- 
canadian passport
- 
passport application
- 
passport photos
- 
certified translator
- 
canadian citizens
- 
processing times
- 

renewal application

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport#

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- パスポート ＃

- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport#

- Passeport#

- PasseportNon
- 

Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>加拿大個人健康身分識別碼 (PHIN)

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 規則運算式 Regex_canada_phin 會找出符合模式的內容。找到至少兩種關鍵字 Keyword_canada_phin 或 Keyword_canada_provinces.

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

#### <a name="keywordcanadaphin"></a>Keyword_canada_phin

- social insurance number
- 
health information act
- 
income tax information
- 
manitoba health
- 
health registration
- 
prescription purchases
- 
benefit eligibility
- 
personal health
- 
power of attorney
- 
registration number
- personal health number
- 
practitioner referral
- 
wellness professional
- 
patient referral
- 

health and wellness

#### <a name="keywordcanadaprovinces"></a>Keyword_canada_provinces

- Nunavut
- 
Quebec
- 
Northwest Territories
- 
Ontario
- 
British Columbia
- 
Alberta
- 
Saskatchewan
- 
Manitoba
- 
Yukon
- 
Newfoundland and Labrador
- 
New Brunswick
- 
Nova Scotia
- 
Prince Edward Island
- 加拿大
   
## <a name="canada-social-insurance-number"></a>加拿大社會保險號碼

### <a name="format"></a>格式

具有選用連字號或空格的 9 位數

### <a name="pattern"></a>模式

格式化：
- 三位數 
- 一個連字號或空格 
- 三位數 
- 一個連字號或空格 
- 三位數

未格式化： 9 的數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_canadian_sin 找到符合模式的內容。
- 至少下列兩項的任意組合：
    - 找到來自於 Keyword_sin 的關鍵字。
    - 找到來自於 Keyword_sin_collaborative 的關鍵字。
    - 函數 Func_eu_date 找到正確日期格式的日期。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_unformatted_canadian_sin 找到符合模式的內容。
- 找到來自於 Keyword_sin 的關鍵字。
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
- social insurance
 
- numero d'assurance sociale
 
- sins
 
- ssn 
- ssns 
- 社會安全 
- numero d'assurance social
 
- 國家識別碼 
- 
national id 
- sin#
 
- soc ins
 
- social ins
 

#### <a name="keywordsincollaborative"></a>Keyword_sin_collaborative

- 駕照 
- 發行的驅動程式授權 
- 驅動程式的授權 
- drivers licence 
- DOB
 
- 出生日期 
- 生日  
- Date of Birth
 
   
## <a name="chile-identity-card-number"></a>	智利身分證號碼

### <a name="format"></a>格式

7-8 的數字加上分隔符號] 核取數字或字母

### <a name="pattern"></a>模式

7-8 位數加上分隔符號：
- 1-2 位數 
- 句點  
- 三位數 
- 句點  
- 三位數 
- 一個破折號 
- 一位數或字母 (不區分大小寫) 的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_chile_id_card 會找出符合模式的內容。
- 從 Keyword_chile_id_card 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_chile_id_card 會找出符合模式的內容。
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

- National Identification Number
 
- Identity card 
- ID 
- Identification 
- Rol Único Nacional
 
- 執行 
- Rol Único Tributario
 
- RUT
 
- Cédula de Identidad
 
- Número De Identificación Nacional
 
- Tarjeta de identificación
 
- Identificación
 
   
## <a name="china-resident-identity-card-prc-number"></a>	中國居民身分證 (PRC) 號碼

### <a name="format"></a>格式

18 位數

### <a name="pattern"></a>模式

18 位數：
- 六位數的地址代碼  
- YYYYMMDD 格式的八位數，代表出生日期  
- 三位數的序碼  
- 一位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_china_resident_id 會找出符合模式的內容。
- 從 Keyword_china_resident_id 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_china_resident_id 會找出符合模式的內容。
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

- Resident Identity Card
 
- PRC
 
- National Identification Card
 
- 身份证  
- 居民 身份证  
- 居民身份证
 
- 鉴定

 
- 身分證  
- 居民 身份證
- 鑑定  
   
## <a name="credit-card-number"></a>信用卡號

### <a name="format"></a>格式

這可設為 16 個位數或格式化 (dddddddddddddddd) 和必須通過 Luhn 測試。

### <a name="pattern"></a>模式

非常複雜且健全的模式，會偵測全球所有主要品牌的卡片，包括 Visa、MasterCard、Discover Card、JCB、American Express、禮品卡和大來卡。

### <a name="checksum"></a>總和檢查碼

是，Luhn 總和檢查碼

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_credit_card 找到符合模式的內容。
- 下列其中一項為真：
    - 找到來自於 Keyword_cc_verification 的關鍵字。
    - 找到來自於 Keyword_cc_name 的關鍵字。
    - 函數 Func_expiration_date 找到正確日期格式的日期。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
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

- card verification
- card identification number
- cvn

- cid

- cvc2
- cvv2
- pin block

- security code

- security number

- security no

- issue number

- issue no

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

- cod. sicurezza

- cod sicurezza
- 
n autorizzazione
- código

- codigo

- cod. seg

- cod seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca

- cód. segurança

- cod。seguranca cod。segurança
- cód. seguranca

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

- data scad

- fecha de expiracion

- fecha de venc

- vencimiento

- válido hasta

- valido hasta

- vto

- data de expiração

- data de expiracao

- data em que expira

- validade

- valor

- vencimento

- Venc 

#### <a name="keywordccname"></a>Keyword_cc_name

- amex
- 
american express
- americanexpress

- 因為撰寫
- mastercard

- master card

- 
mc
 
- mastercards
- 
master cards
- 大來卡
- diners club

- dinersclub

- discover card

- discovercard

- discover cards

- JCB
- japanese card bureau

- carte blanche

- carteblanche

- credit card

- [副本] #
- [副本] # 中：
- 
expiration date
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card

- 
bankcard
- card number

- card num

- cardnumber

- cardnumbers

- card numbers

- creditcard

- credit cards

- creditcards

- ccn

- card holder

- cardholder

- card holders

- cardholders

- check card

- checkcard

- check cards

- checkcards

- debit card

- debitcard

- debit cards

- debitcards

- atm card

- atmcard

- atm cards

- atmcards

- 
enroute
- 
en route
- card type

- carte bancaire

- carte de crédit

- carte de credit

- numéro de carte

- numero de carte

- nº de la carte

- nº de carte

- kreditkarte

- karte

- karteninhaber

- karteninhabers
- kreditkarteninhaber

- kreditkarteninstitut

- kreditkartentyp

- eigentümername

- 
kartennr
 
- kartennummer
- 
kreditkartennummer
- kreditkarten nummer
- carta di credito

- carta credito

- carta
- n carta
- nr. carta

- 編號 carta
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta

- no. de tarjeta

- 沒有 de tarjeta
- numero de tarjeta

- número de tarjeta

- tarjeta no

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

- 
número do cartão
- 
numero do cartão
 
- número do cartao
- 
numero do cartao
- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- nº 不要 cartão
- nº do cartao

- nº. do cartão

- 沒有執行 cartão
- 沒有執行 cartao
- no. do cartão

- 
no. do cartao
 
   
## <a name="croatia-identity-card-number"></a>	克羅埃西亞身分證號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_croatia_id_card 會找出符合模式的內容。
- 從 Keyword_croatia_id_card 關鍵字是找到。

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

- Croatian identity card
- Osobna iskaznica

   
## <a name="croatia-personal-identification-oib-number"></a>	克羅埃西亞個人識別 (OIB) 碼

### <a name="format"></a>格式

10 位數

### <a name="pattern"></a>模式

10 位數：
- DDMMYY 格式的六位數，代表出生日期 
- 四位數，最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_croatia_oib_number 會找出符合模式的內容。
- 從 Keyword_croatia_oib_number 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_croatia_oib_number 會找出符合模式的內容。
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

- Personal Identification Number
- Osobni identifikacijski broj
 
- OIB
 

   
## <a name="czech-national-identity-card-number"></a>	捷克國民身分證號碼

### <a name="format"></a>格式

10 位數包含正斜線

### <a name="pattern"></a>模式

10 位數：
- 六位數的出生日期 
- 一個正斜線 
- 四位數，最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%有信心它已偵測到這種類型的機密資訊時，300 個字元的距離： 函數 Func_czech_id_card 會找出符合模式的內容。從 Keyword_czech_id_card 關鍵字是找到。總和檢查碼會傳遞。

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a>關鍵字

- Keyword_czech_id_card
- Czech national identity card
- Občanský průka
   
## <a name="denmark-personal-identification-number"></a>	丹麥個人識別碼

### <a name="format"></a>格式

10 位數包含連字號

### <a name="pattern"></a>模式

10 位數：
- DDMMYY 格式的六位數，代表出生日期  
- 一個連字號 
- 四位數，最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 規則運算式 Regex_denmark_id 會找出符合模式的內容。從 Keyword_denmark_id 關鍵字是找到。總和檢查碼會傳遞。

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

- Personal Identification Number
- CPR
- Det Centrale Personregister
- Personnummer
   
## <a name="drug-enforcement-agency-dea-number"></a>藥物執法機構 (DEA) 編號

### <a name="format"></a>格式

兩個字母後尾隨七位數

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 這組可能的字母中的一個字母 (不區分大小寫)：abcdefghjklmnprstux，此為註冊者代碼 
- 一個字母 (不區分大小寫)，此為註冊者姓氏的第一個字母 
- 七位數，最後一個數字是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
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

   
## <a name="eu-debit-card-number"></a>歐盟轉帳卡卡號

### <a name="format"></a>格式

16 位數

### <a name="pattern"></a>模式

非常複雜且健全的模式

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_eu_debit_card 找到符合模式的內容。
- 下列至少一項為真：
    - 找到來自於 Keyword_eu_debit_card 的關鍵字。
    - 找到來自於 Keyword_card_terms_dict 的關鍵字。
    - 找到來自於 Keyword_card_security_terms_dict 的關鍵字。
    - 找到來自於 Keyword_card_expiration_terms_dict 的關鍵字。
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
- card number
 
- card no.
 
- security number
 
- [副本] # 

#### <a name="keywordcardtermsdict"></a>Keyword_card_terms_dict

- acct nbr
 
- acct num
 
- acct no
 
- american express
 
- americanexpress
 
- americano espresso
 
- amex 
- atm card
 
- atm cards
 
- atm kaart
 
- atmcard
 
- atmcards
 
- atmkaart
 
- atmkaarten
 
- bancontact
 
- bank card
 
- bankkaart
 
- card holder
 
- card holders
 
- card num
 
- card number
 
- card numbers
 
- card type
 
- cardano numerico
 
- cardholder
 
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
 
- carte bancaire
 
- carte blanche
 
- carte bleue
 
- carte de credit
 
- carte de crédit
 
- carte di credito
 
- carteblanche
 
- cartão de credito
 
- cartão de crédito
 
- cartão de debito
 
- cartão de débito
 
- cb
 
- ccn
 
- check card
 
- check cards
 
- checkcard

- checkcards
 
- chequekaart
 
- cirrus
 
- cirrus-edc-maestro
 
- controlekaart
 
- controlekaarten
 
- credit card
 
- credit cards
 
- creditcard
 
- creditcards
 
- debetkaart
 
- debetkaarten
 
- debit card
 
- debit cards
 
- debitcard
 
- debitcards
 
- debito automatico
 
- diners club
 
- dinersclub
 
- 探索 
- discover card
 
- discover cards
 
- discovercard
 
- discovercards
 
- débito automático
- 
edc
 
- eigentümername
 
- european debit card
 
- hoofdkaart
 
- hoofdkaarten
 
- in viaggio
 
- japanese card bureau
 
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
- 
kartennr
 
- kartennummer 
- kreditkarte
 
- kreditkarten nummer 
- kreditkarteninhaber
 
- kreditkarteninstitut
 
- kreditkartennummer
 
- kreditkartentyp
 
- maestro
 
- master card
 
- master cards
 
- mastercard
 
- mastercards 
- mc 
- mister cash
 
- n carta 
- carta 
- 沒有 de tarjeta 
- 沒有執行 cartao 
- 沒有執行 cartão 
- no. de tarjeta
 
- no. do cartao
 
- no. do cartão
 
- 編號 carta 
- nr. carta
 
- numeri di scheda
 
- numero carta
 
- numero de cartao
 
- numero de carte
 
- numero de cartão
 
- numero de tarjeta

- numero della carta
 
- numero di carta
 
- numero di scheda
 
- numero do cartao
 
- numero do cartão
 
- numéro de carte
 
- nº carta
 
- nº de carte
 
- nº de la carte
 
- nº de tarjeta
 
- nº do cartao
 
- nº 不要 cartão 
- nº. do cartão
 
- número de cartao
 
- número de cartão
 
- número de tarjeta
 
- número do cartao 
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
 
- 參數 
- tarjeta atm
 
- tarjeta credito
 
- tarjeta de atm
 
- tarjeta de credito
 
- tarjeta de debito
 
- tarjeta debito
 
- tarjeta no

- tarjetahabiente
 
- tipo della scheda
 
- ufficio giapponese della 
- scheda
 
- v pay
 
- v 工資 
- visa
 
- visa plus
 
- visa electron
 
- visto
 
- visum
 
- vpay
   

#### <a name="keywordcardsecuritytermsdict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica
 
- cid
 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- cod. seg
 
- cod. seguranca
 
- cod. segurança
 
- cod. sicurezza
 
- codice di sicurezza
 
- codice di verifica
 
- codigo
 
- codigo de seguranca
 
- codigo de segurança
 
- crittogramma
 
- cryptogram
 
- cryptogramme
 
- cv2 
- cvc
 
- cvc2 
- cvn
 
- cvv
 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca
 
- cód. segurança
 
- código
 
- código de seguranca
 
- código de segurança
 
- de kaart controle
 
- geeft nr uit
 
- issue no
 
- issue number
 
- kaartidentificatienummer
 
- kreditkartenprufnummer
 
- kreditkartenprüfnummer
 
- kwestieaantal
 
- no. dell'edizione
 
- no. di sicurezza
 
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
 
- pin block
 
- prufziffer
 
- prüfziffer
 
- security code
 
- security no
 
- security number
 
- sicherheits kode
 
- sicherheitscode
 
- sicherheitsnummer
 
- speldblok
 
- veiligheid nr
 
- veiligheidsaantal
 
- veiligheidscode
 
- veiligheidsnummer
 
- verfalldatum
 

#### <a name="keywordcardexpirationtermsdict"></a>Keyword_card_expiration_terms_dict

- ablauf
 
- data de expiracao
 
- data de expiração
 
- data del exp
 
- data di exp
 
- data di scadenza
 
- data em que expira
 
- data scad
 
- data scadenza
 
- date de validité
 
- datum afloop
 
- datum van exp
 
- de afloop
 
- espira
 
- espira
 
- exp date
 
- exp datum
 
- 到期日 
- expire
 
- expires
 
- expiry
 
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
 
- valor
 
- venc
 
- vencimento
 
- vencimiento
 
- verloopt
 
- vervaldag
 
- vervaldatum
 
- vto
 
- válido hasta
 
   
## <a name="eu-drivers-license-number"></a>歐盟駕照編號

若要深入了解，請參閱[歐盟駕照編號敏感資訊類型](eu-driver-s-license-number.md)。
  
## <a name="eu-national-identification-number"></a>歐盟國家識別碼

若要深入了解，請參閱[國家識別碼歐盟敏感資訊類型](eu-national-identification-number.md)。
  
## <a name="eu-passport-number"></a>歐盟護照號碼

若要深入了解，請參閱[歐盟護照號碼敏感資訊類型](eu-passport-number.md)。
  
## <a name="eu-social-security-number-or-equivalent-id"></a>歐盟社會安全號碼或對等資格識別碼

如需了解，請參閱[歐盟社會安全號碼或對等識別碼敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。
  
## <a name="eu-tax-identification-number"></a>歐盟稅識別碼

若要深入了解，請參閱[歐盟稅識別碼敏感資訊類型](eu-tax-identification-number.md)。
  
## <a name="finland-national-id"></a>芬蘭國民身分證

### <a name="format"></a>格式

六位數加上一個指出世紀的字元，再加上三位數和一個檢查碼

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 六位數的格式為 DDMMYY，此為出生日期 
- 世紀標記 ('-'、'+' 或 'a') 
- 三位數個人識別碼 
- 一個做為檢查碼的數字或字母 (不區分大小寫)

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_finnish_national_id 找到符合模式的內容。
- 找到來自於 Keyword_finnish_national_id 的關鍵字。
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
- 

Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>芬蘭護照號碼

格式化九個字母和數字模式組合的九個字母和數字的組合： 兩個字母 （不區分大小寫） 七位數總和檢查碼沒有定義 DLP 原則是 75%健全的如果它是已偵測這種敏感資訊類型、 兩者之間300 個字元的鄰近： 規則運算式 Regex_finland_passport_number 會找出符合模式的內容。從 Keyword_finland_passport_number 關鍵字是找到。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
</Entity>關鍵字 Keyword_finland_passport_number Passport Passi
   
## <a name="france-drivers-license-number"></a>法國駕照編號

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

可驗證以忽略類似模式 (例如法國電話號碼) 的 12 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_french_drivers_license 找到符合模式的內容。
- 下列至少一項為真：
- 找到來自於 Keyword_french_drivers_license 的關鍵字。
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

- drivers licence
- 
drivers license
- driving licence

- 主導授權
- 
permis de conduire
- 
licence number
- 
license number
- 
licence numbers
- 

license numbers

## <a name="france-national-id-card-cni"></a>法國國民身分證 (CNI)

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

12 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
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
- 兩個字母 (不區分大小寫) 
- 五位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_fr_passport 找到符合模式的內容。
- 找到來自於 Keyword_passport 的關鍵字。

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

- Passport Number
- 
Passport No
- Passport#

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- 
パスポート ＃
 
- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport#

- Passeport#

- PasseportNon
- 

Passeportn °

      
## <a name="france-social-security-number-insee"></a>法國社會安全號碼 (INSEE)

### <a name="format"></a>格式

15 位數

### <a name="pattern"></a>模式

必須符合兩個模式之一：
- 後面接著空格後面接著兩個位數字的數字 13<br/>
或
- 15 個連續數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：
- Func_french_insee 或 Func_fr_insee 函數會找出符合模式的內容。
- 找到來自於 Keyword_fr_insee 的關鍵字。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- Func_french_insee 或 Func_fr_insee 函數會找出符合模式的內容。
- 找不到來自於 Keyword_fr_insee 的關鍵字。
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
- 
securité sociale
- 
securite sociale
- 
national id
- 
national identification
- 
numéro d'identité
- 沒有 d'identité
- 
no. d'identité
- 
numero d'identite
- 沒有 d'identite
- 
no. d'identite
- social security number

- 
social security code
- social insurance number
- 
le numéro d'identification nationale
- 
d'identité nationale
- 
numéro de sécurité sociale
- 
le code de la sécurité sociale
- 
numéro d'assurance sociale
- 
numéro de sécu
- 
code sécu
 
   
## <a name="german-drivers-license-number"></a>德國駕照編號

### <a name="format"></a>格式

11 個數字和字母的組合

### <a name="pattern"></a>模式

11 個數字和字母 (不區分大小寫)：
- 一個數字或字母 
- 兩位數 
- 六個數字或字母 
- 一個數字 
- 一個數字或字母

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_german_drivers_license 找到符合模式的內容。
- 下列至少一項為真：
    - 找到來自於 Keyword_german_drivers_license_number 的關鍵字。
    - 找到來自於 Keyword_german_drivers_license_collaborative 的關鍵字。
    - 找到來自於 Keyword_german_drivers_license 的關鍵字。
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
- 
Fuhrerschein
- Fuehrerschein
- 
Führerscheinnummer
- 
Fuhrerscheinnummer
- 
Fuehrerscheinnummer
- 
Führerschein-
 
- Fuhrerschein-
 
- Fuehrerschein-
 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr

- Fuhrerschein- Nr

- Fuehrerschein- Nr
 
- Führerschein- Klasse
 
- Fuhrerschein- Klasse
 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr
 
- Fuhrerschein- Nr
 
- Fuehrerschein- Nr
 
- Führerschein- Klasse
 
- Fuhrerschein- Klasse
 
- Fuehrerschein- Klasse 
- DL 
- DLS
- 
Driv Lic
 
- Driv Licen
 
- Driv License
- 
Driv Licenses
 
- Driv Licence
 
- Driv Licences
 
- Driv Lic
 
- Driver Licen
 
- 驅動程式授權 
- 驅動程式授權 
- Driver Licence
 
- Driver Licences
 
- 發行的驅動程式 Lic 
- 發行的驅動程式 Licen 
- 發行的驅動程式授權 
- 發行的驅動程式授權 
- 發行的驅動程式授權 
- 發行的驅動程式授權 
- 駕 Lic 
- Driver's Licen
 
- 駕照 
- 驅動程式的授權 
- Driver's Licence
 
- Driver's Licences
 
- Driving Lic
 
- Driving Licen
 
- Driving License
 
- Driving Licenses
 
- Driving Licence

 
- Driving Licences

#### <a name="keywordgermandriverslicensecollaborative"></a>Keyword_german_drivers_license_collaborative

- 
Nr-Führerschein
 
- Nr-Fuhrerschein
 
- Nr-Fuehrerschein
 
- No-Führerschein
 
- No-Fuhrerschein
 
- No-Fuehrerschein
 
- N-Führerschein
 
- N-Fuhrerschein
 
- N-Fuehrerschein
- 
Nr-Führerschein
 
- Nr-Fuhrerschein
 
- Nr-Fuehrerschein
 
- No-Führerschein
 
- No-Fuhrerschein
 
- No-Fuehrerschein
 
- N-Führerschein
 
- N-Fuhrerschein
 
- N-Fuehrerschein 

#### <a name="keywordgermandriverslicense"></a>Keyword_german_drivers_license

- ausstellungsdatum
- 
ausstellungsort
- 
ausstellende behöde
- 
ausstellende behorde
- 

ausstellende behoerde
   
## <a name="german-passport-number"></a>德國護照號碼

### <a name="format"></a>格式

10 個數字或字母

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 第一個字元是一個數字或 C、F、G、H、J、K 之中的一個字母 
- 三位數 
- 5 個數字或 C、H、J-N、P、R、T、V-Z 之中的字母 
- 一個數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_german_passport 找到符合模式的內容。
- 找到五個關鍵字清單任一者中的關鍵字。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_german_passport_data 找到符合模式的內容。
- 找到五個關鍵字清單任一者中的關鍵字。
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
- 
reisepasse
- 
reisepassnummer
- passport
- 

passports

#### <a name="keywordgermanpassportcollaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- 
ausstellungsort

#### <a name="keywordgermanpassportnumber"></a>Keyword_german_passport_number

否-Reisepass 編號 Reisepass

#### <a name="keywordgermanpassport1"></a>Keyword_german_passport1

Reisepass-Nr


#### <a name="keywordgermanpassport2"></a>Keyword_german_passport2

bnationalit.t
   
## <a name="germany-identity-card-number"></a>德國身分證號碼

### <a name="format"></a>格式

1 年 11 月 2010年自： 九個字母和數字

從 1 年 4 月 1987 直到 31 年 10 月 2010年: 10 位數

### <a name="pattern"></a>模式

自從 2010 年 11 月 1 日：
- 一個字母 (不區分大小寫) 
- 八位數

從 1 年 4 月 1987 31 年 10 月 2010年之前：
- 10 位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
- 規則運算式 Regex_germany_id_card 會找出符合模式的內容。
- 從 Keyword_germany_id_card 關鍵字是找到。

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

- Identity Card
- ID
- Identification
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>希臘國民身分證

### <a name="format"></a>格式

7-8 個字母和數字加上破折號的組合

### <a name="pattern"></a>模式

七個字母和數字 (舊格式)︰
- 一個字母 (希臘文字母的任何字母)  
- 一個破折號 
- 六位數

八個字母和數字 (新格式)︰
- 在希臘文與拉丁文字母中皆有大寫形態的兩個字母 (ABEZHIKMNOPTYX)  
- 一個破折號 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_greece_id_card 會找出符合模式的內容。
- 從 Keyword_greece_id_card 關鍵字是找到。

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

- Greek identity Card
- Tautotita
- Δελτίο αστυνομικής ταυτότητας
- Ταυτότητα
   
## <a name="hong-kong-identity-card-hkid-number"></a>香港身分證 (HKID) 號碼

### <a name="format"></a>格式

8-9 個字母和數字，加上選擇性括住的最後一個字元的組合

### <a name="pattern"></a>模式

8-9 個字母的組合：
- 1-2 個字母 (不區分大小寫)  
- 六位數 
- 最後一個字元 (任何數字或字母 A)，是檢查碼且可選擇性加上前後括號。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_hong_kong_id_card 會找出符合模式的內容。
- 從 Keyword_hong_kong_id_card 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
- 函數 Func_hong_kong_id_card 會找出符合模式的內容。
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

- Hong Kong Identity Card
- HKID
- ID card
- 香港身份證
 
- 香港永久性居民身份證
 
   
## <a name="india-permanent-account-number-pan"></a>印度永久帳戶號碼 (PAN)

### <a name="format"></a>格式

10 個字母或數字

### <a name="pattern"></a>模式

10 個字母或數字：
- 五個字母 (不區分大小寫) 
- 四位數 
- 一個做為字母檢查碼的字母

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_india_permanent_account_number 會找出符合模式的內容。
- 從 Keyword_india_permanent_account_number 關鍵字是找到。
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

- Permanent Account Number
 
- PAN
 
   
## <a name="india-unique-identification-aadhaar-number"></a>印度唯一識別 (Aadhaar) 碼

### <a name="format"></a>格式

12 位數包含選擇性空格或破折號

### <a name="pattern"></a>模式

12 位數：
- 四位數 
- 一個選擇性空格或破折號  
- 四位數 
- 一個選擇性空格或破折號  
- 最後一位數是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則是 85%有信心它已偵測到這種類型的機密資訊時，300 個字元的距離： 函數 Func_india_aadhaar 會找出符合模式的內容。從 Keyword_india_aadhar 關鍵字是找到。總和檢查碼會傳遞。DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 函數 Func_india_aadhaar 會找出符合模式的內容。總和檢查碼會傳遞。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity>

### <a name="keywords"></a>關鍵字
   
#### <a name="keywordindiaaadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>印尼身分識 (KTP) 號碼

### <a name="format"></a>格式

16 位數包含選擇性句點

### <a name="pattern"></a>模式

16 位數：
- 二位數省代碼  
- 句點 (選擇性)  
- 二位數攝政或城市代碼  
- 二位數次行政區代碼  
- 句點 (選擇性)  
- DDMMYY 格式的六位數，代表出生日期  
- 句點 (選擇性)  
- 四位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_indonesia_id_card 會找出符合模式的內容。
- 從 Keyword_indonesia_id_card 關鍵字是找到。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_indonesia_id_card 會找出符合模式的內容。

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

國家/地區碼 （兩個字母） 加號 plus bban 數 （最多 30 個字元） 檢查位數 （兩個位數）

### <a name="pattern"></a>模式

模式必須包含下列各項：

- 雙字母國家/地區碼
- 兩個核取位數 （後面選用的空間） 
- 1-7 群組的四個字母或數字 （可以以空格）
- 1-3 個字母或數字

每個國家/地區的格式是稍有不同。IBAN 敏感資訊類型涵蓋下列 60 國家/地區：

ad、 ae、 al，在亞利桑那州、 ba、 是、 bg、 bh、 頻道、 cr、 cy、 cz、 de、 粗、 執行、 ee、 es、 wi-fi、 於、 fr、 gb、 ge、 gi、 gl、 /gr、 hr、 hu、 ie、 芝加哥，它、 kw、 kz、 lb、 li、 lt、 lu、 lv mc md、 我、 mk、 mr、 明、 mu、 nl、 [否] pl、 pt、 ro、 rs、 sa、 se、 si、 sk、 sm、 tn、 tr、 vg

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
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

#### <a name="ipv4"></a>IPv4：
表示格式化 (句點) 和未格式化 (無句點) 之 IPv4 位址的複雜模式

#### <a name="ipv6"></a>IPv6：
表示格式化 IPv6 號碼 (其中包含冒號) 的複雜模式

### <a name="pattern"></a>模式

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

對於 IPv6，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到來自於 Keyword_ipaddress 的關鍵字。

對於 IPv4，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：
- 規則運算式 Regex_ipv4_address 找到符合模式的內容。
- 找到來自於 Keyword_ipaddress 的關鍵字。

對於 IPv6，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：
- 規則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到來自於 Keyword_ipaddress 的關鍵字。

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

- IP (此關鍵字區分大小寫)
- ip address
 
- ip addresses
- internet protocol
- 
IP-כתובת ה
 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>國際分類的治療法 （ICD-10-公分）

### <a name="format"></a>格式

字典

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 從 Dictionary_icd_10_cm 關鍵字是找到。

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

關鍵字

任何字詞的 Dictionary_icd_10_cm 關鍵字字典，這根據[國際分類的治療法、 十分之一修訂、 臨床修改 （ICD-10-公分）](https://go.microsoft.com/fwlink/?linkid=852604)。此類型只會尋找詞不保險代碼。

   
## <a name="international-classification-of-diseases-icd-9-cm"></a>國際分類的治療法 （ICD-9-公分）

### <a name="format"></a>格式

字典

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 從 Dictionary_icd_9_cm 關鍵字是找到。

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

任何字詞的 Dictionary_icd_9_cm 關鍵字字典，這根據[國際分類的治療法、 二十九修訂、 臨床修改 （ICD-9-公分）](https://go.microsoft.com/fwlink/?linkid=852605)。此類型只會尋找詞不保險代碼。
   
## <a name="ireland-personal-public-service-pps-number"></a>愛爾蘭個人公用服務 (PPS) 號碼

### <a name="format"></a>格式

（直到 31 Dec 2012) 的舊格式：
- 七位數後尾隨 1-2 個字母  

新的格式 (1 Jan 2013 及之後)：
- 七位數後尾隨二個字母

### <a name="pattern"></a>模式

（直到 31 Dec 2012) 的舊格式：
- 七位數 
- 1-2 個字母 (不區分大小寫)  

新的格式 (1 Jan 2013 及之後)：
- 七位數 
- 一個字母 (不區分大小寫)，是一個字母檢查碼  
- 字母 "A" 或 "H" (不區分大小寫)

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_ireland_pps 會找出符合模式的內容。
- 下列其中一項為真：
    - 從 Keyword_ireland_pps 關鍵字是找到。
    - 函數 Func_eu_date 找到正確日期格式的日期。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
- 函數 Func_ireland_pps 會找出符合模式的內容。
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

- Personal Public Service Number 
 
- PPS Number
 
- PPS Num
 
- PPS No.
 
- PPS #
 
- PPS#
 
- PPSN
 
- Public Services Card
 
- Uimhir Phearsanta Seirbhíse Poiblí
 
- Uimh.PSP
 
- PSP
 
   
## <a name="israel-bank-account-number"></a>以色列銀行帳戶號碼

### <a name="format"></a>格式

13 位數

### <a name="pattern"></a>模式

格式化：
- 兩位數 
- 一個破折號 
- 三位數 
- 一個破折號 
- 八位數

未格式化：
- 13 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_israel_bank_account_number 找到符合模式的內容。
- 找到來自於 Keyword_israel_bank_account_number 的關鍵字。

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

- Bank Account Number
 
- Bank Account
 
- Account Number
 
- מספר חשבון בנק
 
   
## <a name="israel-national-id"></a>以色列國家識別碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_israeli_national_id_number 找到符合模式的內容。
- 找到來自於 Keyword_Israel_National_ID 的關鍵字。
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
 
- 國門身分證號碼
   
## <a name="italy-drivers-license-number"></a>義大利駕照編號

### <a name="format"></a>格式

10 個字母和數字的組合

### <a name="pattern"></a>模式

- 10 個字母和數字的組合：
- 一個字母 (不區分大小寫) 
- 字母 "A" 或 "V" (不區分大小寫) 
- 七個字母 (不區分大小寫)、數字或底線字元 
- 一個字母 (不區分大小寫)

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_italy_drivers_license_number 的關鍵字。

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
 
   
## <a name="japan-bank-account-number"></a>日本銀行帳號

### <a name="format"></a>格式

7 或 8 位數

### <a name="pattern"></a>模式

銀行帳戶號碼：
- 7 或 8 位數
- 銀行帳戶分行代碼：
- 四位數 
- 一個空格或連字號 (選用) 
- 三位數

總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 找到來自於 Keyword_jp_bank_account 的關鍵字。
- 下列其中一項為真：
- 函數 Func_jp_bank_account_branch_code 找到符合模式的內容。
- 找到來自於 Keyword_jp_bank_branch_code 的關鍵字。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 找到來自於 Keyword_jp_bank_account 的關鍵字。

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

- Checking Account Number
 
- Checking Account
 
- Checking Account #
 
- Checking Acct Number
 
- Checking Acct #
 
- Checking Acct No.
 
- Checking Account No.
 
- Bank Account Number
 
- Bank Account
 
- Bank Account #
 
- Bank Acct Number
 
- Bank Acct #
 
- Bank Acct No.
 
- Bank Account No.
 
- Savings Account Number
 
- 節約帳戶 
- Savings Account #
 
- Savings Acct Number
 
- Savings Acct #
 
- Savings Acct No.
 
- Savings Account No.
 
- Debit Account Number
 
- Debit Account
 
- Debit Account #
 
- Debit Acct Number
 
- Debit Acct #
 
- Debit Acct No.
 
- Debit Account No.
 
- 口座番号を当座預金口座の確認
 
- ＃アカウントの確認、勘定番号の確認
 
- ＃勘定の確認
 
- 勘定番号の確認
 
- 口座番号の確認
 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃
 
- 銀行の勘定番号
 
- 銀行のacct＃
 
- 銀行の勘定いいえ
 
- 銀行口座番号
- 
普通預金口座番号
 
- 預金口座
 
- 貯蓄口座＃
 
- 貯蓄勘定の数
 
- 貯蓄勘定＃
 
- 貯蓄勘定番号
 
- 普通預金口座番号
 
- 引き落とし口座番号
 
- 口座番号 
- 口座番号＃
 
- デビットのacct番号
 
- デビット勘定＃
 
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

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_jp_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_jp_drivers_license_number 的關鍵字。

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

- dl#
 
- DL # 
- dl # 
- DL # 
- 驅動程式授權 
- 驅動程式授權 
- 發行的驅動程式授權 
- 駕照 
- 發行的驅動程式授權 
- 驅動程式的授權 
- driving licence
 
- lic # 
- LIC # 
- lics#
 
- 狀態識別碼 
- state identification
 
- state identification number
 
- 低所得国＃
 
- 免許証
 
- 状態ID
- 
状態の識別
 
- 状態の識別番号
 
- 運転免許
 
- 運転免許証
 
- 運転免許証番号
 
   
## <a name="japan-passport-number"></a>日本護照號碼

### <a name="format"></a>格式

兩個字母後尾隨七位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後尾隨七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_jp_passport 找到符合模式的內容。
- 找到來自於 Keyword_jp_passport 的關鍵字。

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
 
- パスポート ＃
 
   
## <a name="japan-resident-registration-number"></a>日本常駐居民登記號碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_jp_resident_registration_number 找到符合模式的內容。
- 找到來自於 Keyword_jp_resident_registration_number 的關鍵字。

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

- Resident Registration Number
- Resident Register Number
 
- Residents Basic Registry Number
 
- Resident Registration No.
 
- Resident Register No.
 
- Residents Basic Registry No.
 
- Basic Resident Register No.
 
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
- 一個連字號 (選用) 
- 6 位數或
- 7-12 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_jp_sin 找到符合模式的內容。
- 找到來自於 Keyword_jp_sin 的關鍵字。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_jp_sin_pre_1997 找到符合模式的內容。
- 找到來自於 Keyword_jp_sin 的關鍵字。

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

- Social Insurance No.
 
- Social Insurance Num
 
- Social Insurance Number
 
- 社会保険のテンキー
 
- 社会保険番号
 
   
## <a name="malaysia-id-card-number"></a>馬來西亞身分證號碼

### <a name="format"></a>格式

12 位數包含選擇性連字號

### <a name="pattern"></a>模式

12 位數：
- YYMMDD 格式的六位數，代表出生日期  
- 一個破折號 (選擇性) 
- 兩個字母的出生地代碼  
- 一個破折號 (選擇性) 
- 三個隨機的數字  
- 一位數性別代碼

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_malaysia_id_card_number 會找出符合模式的內容。
- 從 Keyword_malaysia_id_card_number 關鍵字是找到。

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

- MyKad 
- Identity Card 
- 識別碼卡片 
- 識別卡 
- Digital Application Card
 
- Kad Akuan Diri
 
- Kad Aplikasi Digital
 
   
## <a name="netherlands-citizens-service-bsn-number"></a>荷蘭公民服務 (BSN) 號碼

### <a name="format"></a>格式

8-9 位數包含選擇性空格

### <a name="pattern"></a>模式

8-9 位數：
- 三位數 
- 一個空格 (選用) 
- 三位數 
- 一個空格 (選用) 
- 2-3 位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_netherlands_bsn 會找出符合模式的內容。
- 從 Keyword_netherlands_bsn 關鍵字是找到。
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

- Citizen service number
 
- BSN

 
- Burgerservicenummer
 
- Sofinummer
 
- Persoonsgebonden nummer
 
- Persoonsnummer
    

   
## <a name="new-zealand-ministry-of-health-number"></a>紐西蘭衛生部編號

### <a name="format"></a>格式

三個字母、一個空格 (選用) 和四位數

### <a name="pattern"></a>模式

三個字母空格 （選擇性） 四位數 （不區分大小寫）

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。
- 找到來自於 Keyword_nz_terms 的關鍵字。
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
 
- 紐西蘭 
- 狀況良好 
- treatment
 
   
## <a name="norway-identification-number"></a>挪威識別碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數：
- DDMMYY 格式的六位數，代表出生日期  
- 三位數個人識別碼  
- 二位數檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_norway_id_number 會找出符合模式的內容。
- 從 Keyword_norway_id_number 關鍵字是找到。
- 總和檢查碼通過。
- 如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_norway_id_numbe 會找出符合模式的內容。
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

- Personal identification number
- Norwegian ID Number
- ID Number
- Identification
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-id-number"></a>菲律賓統一多用途身分證號碼

### <a name="format"></a>格式

以連字號分隔的 12 位數

### <a name="pattern"></a>模式

12 位數：
- 四位數 
- 一個連字號 
- 七位數 
- 一個連字號 
- 一個數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_philippines_unified_id 會找出符合模式的內容。
- 從 Keyword_philippines_id 關鍵字是找到。

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

- Unified Multi-Purpose ID
 
- UMID
 
- Identity Card 
- Pinag-isang Multi-Layunin ID
   
## <a name="poland-identity-card"></a>波蘭身分證明卡

### <a name="format"></a>格式

三個字母和六位數

### <a name="pattern"></a>模式

三個字母 (不區分大小寫) 後尾隨六位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 函數 Func_polish_national_id 會找出符合模式的內容。從 Keyword_polish_national_id_passport_number 關鍵字是找到。總和檢查碼會傳遞。

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

- Nazwa i nr dowodu tożsamości
 
- Dowód Tożsamości
 
- dow. os.
 

   
## <a name="poland-national-id-pesel"></a>波蘭國民身分證 (PESEL)

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 個連續數字

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_pesel_identification_number 找到符合模式的內容。
- 找到來自於 Keyword_pesel_identification_number 的關鍵字。
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

- Nr PESEL
- PESEL   

   
## <a name="poland-passport"></a>波蘭護照

### <a name="format"></a>格式

兩個字母和七位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後尾隨七位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_polish_passport_number 找到符合模式的內容。
- 找到來自於 Keyword_polish_national_id_passport_number 的關鍵字。
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

- Nazwa i nr dowodu tożsamości
 
- Dowód Tożsamości
 
- dow. os.
 

   
## <a name="portugal-citizen-card-number"></a>葡萄牙公民證號碼

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_portugal_citizen_card 會找出符合模式的內容。
- 從 Keyword_portugal_citizen_card 關鍵字是找到。

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

- Citizen Card
- National ID Card
- CC
- Cartão de Cidadão
- Bilhete de Identidade
   
## <a name="saudi-arabia-national-id"></a>沙烏地阿拉伯國民身分證號

### <a name="format"></a>格式

10 位數

### <a name="pattern"></a>模式

10 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。
- 找到來自於 Keyword_saudi_arabia_national_id 的關鍵字。

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

- Identification Card
 
- I card number
 
- 識別碼 
- الوطنية الهوية بطاقة رقم
 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡國民登記身分證 (NRIC) 號碼

### <a name="format"></a>格式

九個字母和數字

### <a name="pattern"></a>模式

- 九個字母和數字：
- 字母 "F"、"G"、"S" 或 "T" (不區分大小寫)  
- 七位數 
- 一個字母檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 規則運算式 Regex_singapore_nric 會找出符合模式的內容。
- 從 Keyword_singapore_nric 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_singapore_nric 會找出符合模式的內容。
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

- National Registration Identity Card
 
- Identity Card Number
 
- NRIC
 
- IC
 
- Foreign Identification Number
 
- FIN
 
- 身份证  
- 身份證
 
   
## <a name="south-africa-identification-number"></a>南非身分證號碼

### <a name="format"></a>格式

可以包含空格的 13 位數

### <a name="pattern"></a>模式

13 位數：
- YYMMDD 格式的六位數，代表出生日期  
- 四位數 
- 一位數公民指標  
- 數字 "8" 或 "9"  
- 一位數總和檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_south_africa_identification_number 會找出符合模式的內容。
- 從 Keyword_south_africa_identification_number 關鍵字是找到。
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

- Identity card
- ID
- Identification 
   
## <a name="south-korea-resident-registration-number"></a>南韓居民登記號碼

### <a name="format"></a>格式

13 位數包含連字號

### <a name="pattern"></a>模式

13 位數：
- YYMMDD 格式的六位數，代表出生日期  
- 一個連字號 
- 由世紀與性別判定的一位數  
- 四位數出生地區碼  
- 一位數，用來區分前幾碼皆相同的人員  
- 檢查碼。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_south_korea_resident_number 會找出符合模式的內容。
- 從 Keyword_south_korea_resident_number 關鍵字是找到。
- 總和檢查碼通過。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_south_korea_resident_number 會找出符合模式的內容。
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

第 11 12 位數：
- 兩位數 
- 一個正斜線 (選用) 
- 7-8 位數 
- 一個正斜線 (選用) 
- 兩位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
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
   
## <a name="sweden-national-id"></a>瑞典國民身分證號

### <a name="format"></a>格式

10 或 12 位數和一個選用分隔符號

### <a name="pattern"></a>模式

10 或 12 位數和一個選用分隔符號：
- 2-4 位數 (選用) 
- 採用日期格式 YYMMDD 的六位數 
- 分隔符號 "-" 或 "+" (選用)，加上
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
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

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_sweden_passport_number 找到符合模式的內容。
- 下列其中一項為真：
    - 找到來自於 Keyword_passport 的關鍵字。
    - 找到來自於 Keyword_sweden_passport 的關鍵字。

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

- visa requirements
 
- Alien Registration Card
 
- Schengen visas
 
- Schengen visa
 
- Visa Processing
 
- Visa Type
 
- Single Entry
 
- Multiple Entry
 
- G3 Processing Fees

 

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number 
- 
Passport No 
- Passport#
 
- Passport#
 
- PassportID 
- Passportno
 
- passportnumber
 
- パスポート 
- パスポート番号
 
- パスポートのNum
 
- パスポート ＃
 
- Numéro de passeport 
- 
Passeport n ° 
- Passeport Non
 
- Passeport#
 
- Passeport#
 
- PasseportNon 
- Passeportn °
 
   
## <a name="swift-code"></a>SWIFT 代碼

### <a name="format"></a>格式

四個字母後尾隨 5-31 個字母或數字

### <a name="pattern"></a>模式

四個字母後尾隨 5-31 個字母或數字：
- 四字母銀行代碼 (不區分大小寫) 
- 一個選用空格 
- 4-28 個字母或數字 (基本銀行帳戶號碼 (BBAN)) 
- 一個選用空格 
- 1-3 個字母或數字 (BBAN 的其餘部分)

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_swift 找到符合模式的內容。
- 找到來自於 Keyword_swift 的關鍵字。

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

- international organization for standardization 9362
 
- iso 9362
 
- iso9362 
- swift\# 
- swiftcode
 
- swiftnumber
 
- swiftroutingnumber
 
- swift code
 
- swift number #
 
- swift routing number
 
- bic number
 
- bic code
 
- bic\# 
- bic\# 
- bank identifier code
 
- 標準化9362 
- 迅速＃
 
- SWIFTコード
 
- SWIFT番号
 
- 迅速なルーティング番号
 
- BIC番号
 
- BICコード
 
- 銀行識別コードのための国際組織
 
- Organisation internationale de normalisation 9362
 
- rapide\# 
- code SWIFT
 
- le numéro de swift
 
- swift numéro d'acheminement
 
- le numéro BIC
 
- \#BIC 
- code identificateur de banque
 
   
## <a name="taiwan-national-id"></a>台灣身分證

### <a name="format"></a>格式

一個字母 後尾隨九位數

### <a name="pattern"></a>模式

一個字母 後尾隨九位數：
- 一個字母 (英文、不區分大小寫) 
- 數字 "1" 或 "2" 
- 八位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_taiwanese_national_id 找到符合模式的內容。
- 找到來自於 Keyword_taiwanese_national_id 的關鍵字。
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
   
## <a name="taiwan-passport-number"></a>	台灣護照號碼

### <a name="format"></a>格式

- 生物特徵護照號碼： 9 的數字
- 非生物特徵護照號碼： 9 的數字

### <a name="pattern"></a>模式
生物特徵護照號碼：
- 數字 "3"  
- 八位數

非生物特徵護照號碼：
- 九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_taiwan_passport 會找出符合模式的內容。
- 從 Keyword_taiwan_passport 關鍵字是找到。

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
- Passport 無 
- Passport Num
 
- Passport#
 
- 护照
 
- 中華民國護照
 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan Resident Certificate (ARC/TARC) Number

### <a name="format"></a>格式

10 個字母和數字

### <a name="pattern"></a>模式

10 個字母和數字：
- 兩個字母 (不區分大小寫) 
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_taiwan_resident_certificate 會找出符合模式的內容。
- 從 Keyword_taiwan_resident_certificate 關鍵字是找到。

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

- Resident Certificate
 
- 常駐居民登記 Cert 
- Resident Cert.
 
- 識別卡 
- Alien Resident Certificate
 
- ARC
 
- Taiwan Area Resident Certificate
 
- TARC
 
- 居留證
 
- 外僑居留證
 
- 台灣地區居留證
 
   
## <a name="uk-drivers-license-number"></a>英國駕照號碼

### <a name="format"></a>格式

18 個指定格式的字母和數字的組合

### <a name="pattern"></a>模式

18 個字母和數字：
- 五個字母 (不區分大小寫) 或取代字母的數字 "9" 
- 一個數字 
- 以日期格式 DDMMY 表示出生日期的五位數 
- 兩個字母 (不區分大小寫) 或取代字母的數字 "9" 
- 五位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_uk_drivers_license 找到符合模式的內容。
- 找到來自於 Keyword_uk_drivers_license 的關鍵字。
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
 
- light vans
 
- quadbikes
 
- motor cars
 
- 125cc 
- sidecar
 
- tricycles
 
- motorcycles
 
- photocard licence
 
- learner drivers
 
- licence holder
 
- licence holders
 
- driving licences
 
- driving licence
 
- dual control car
 
   
## <a name="uk-electoral-roll-number"></a>英國選民名冊編號

### <a name="format"></a>格式

兩個字母後尾隨 1-4 位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後尾隨 1-4 個數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_uk_electoral 找到符合模式的內容。
- 找到來自於 Keyword_uk_electoral 的關鍵字。

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

- council nomination
 
- nomination form
 
- electoral register

 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>英國國民健保服務編號

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

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_uk_nhs_number 找到符合模式的內容。
- 下列其中一項為真：
    - 找到來自於 Keyword_uk_nhs_number 的關鍵字。
    - 找到來自於 Keyword_uk_nhs_number1 的關鍵字。
    - 找到來自於 Keyword_uk_nhs_number_dob 的關鍵字。
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

- national health service
 
- nhs
 
- health services authority

 
- health authority

#### <a name="keyworduknhsnumber1"></a>Keyword_uk_nhs_number1

- patient id
 
- patient identification
 
- patient no

 
- patient number

#### <a name="keyworduknhsnumberdob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB
 
- D.O.B 
- Date of Birth
 
- Birth Date
 
   
## <a name="uk-national-insurance-number-nino"></a>英國國民保險編號 (NINO)

### <a name="format"></a>格式

7 個字元或空格或虛線隔開的 9 字元

### <a name="pattern"></a>模式

兩個可能的模式：

- 兩個字母 (有效 NINOs 只使用某些字元在此模式會驗證 ； 這個前置詞不區分大小寫)
- 六位數
- ''，'B' 'C' 或鎖 ' （例如首碼僅某些字元中允許尾碼; 不區分大小寫）

或

- 兩個字母
- 一個空格或連字號
- 兩位數
- 一個空格或連字號
- 兩位數
- 一個空格或連字號
- 兩位數
- 一個空格或連字號
- ''，'B' 'C' 或鎖 '

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_uk_nino 找到符合模式的內容。
- 找到來自於 Keyword_uk_nino 的關鍵字。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_uk_nino 找到符合模式的內容。
- 找不到來自於 Keyword_uk_nino 的關鍵字。

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

- national insurance number
 
- national insurance contributions
 
- protection act
 
- insurance
 
- social security number
 
- insurance application
 
- medical application
 
- social insurance
 
- medical attention
 
- 社會安全 
- great britain
 
- insurance
    
   
## <a name="us--uk-passport-number"></a>美國 / 英國護照號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_usa_uk_passport 找到符合模式的內容。
- 找到來自於 Keyword_passport 的關鍵字。

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

- Passport Number 
- 
Passport No 
- Passport#
 
- Passport#
 
- PassportID 
- Passportno
 
- passportnumber
 
- パスポート 
- パスポート番号
 
- パスポートのNum
 
- パスポート ＃
 
- Numéro de passeport 
- 
Passeport n ° 
- Passeport Non
 
- Passeport#
 
- Passeport#
 
- PasseportNon 
- Passeportn °
 
   
## <a name="us-bank-account-number"></a>美國銀行帳號

### <a name="format"></a>格式

8-17 位數

### <a name="pattern"></a>模式

8-17 個連續數字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 規則運算式 Regex_usa_bank_account_number 找到符合模式的內容。
- 找到來自於 Keyword_usa_Bank_Account 的關鍵字。

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

- Checking Account Number
 
- Checking Account
 
- Checking Account #
 
- Checking Acct Number
 
- Checking Acct #
 
- Checking Acct No.
 
- Checking Account No.
 
- Bank Account Number
 
- Bank Account #
 
- Bank Acct Number
 
- Bank Acct #
 
- Bank Acct No.
 
- Bank Account No.
 
- Savings Account Number
 
- Savings Account.
 
- Savings Account #
 
- Savings Acct Number
 
- Savings Acct #
 
- Savings Acct No.
 
- Savings Account No.
 
- Debit Account Number
 
- Debit Account
 
- Debit Account #
 
- Debit Acct Number
 
- Debit Acct #
 
- Debit Acct No.
 
- Debit Account No.
 
   
## <a name="us-drivers-license-number"></a>美國駕照號碼

### <a name="format"></a>格式

隨州別不同

### <a name="pattern"></a>模式

隨州別不同 -- 以紐約州為例：
- 9 的數字格式像是 ddd ddd ddd 會比對。
- 將不會符合 ddddddddd 類似的九個位數。

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_[state_name]_drivers_license_name 的關鍵字。
- 從 Keyword_us_drivers_license 關鍵字是找到。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自於 Keyword_[state_name]_drivers_license_name 的關鍵字。
- 找到來自於 Keyword_us_drivers_license_abbreviations 的關鍵字。
- 找不到來自於 Keyword_us_drivers_license 的關鍵字。

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
- DLS 
- CDL 
- CDLS 
- ID 
- 識別碼 
- DL# 
- 
DLS#
 
- CDL#
 
- CDLS#
 
- ID#
- 
IDs#
 
- 識別碼 
- ID numbers
 
- LIC 
- LIC#
 

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
- 發行的驅動程式 Lic 
- 發行的驅動程式 Lics 
- 發行的驅動程式授權 
- 發行的驅動程式授權 
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
- identification number
 
- identification numbers
 
- identification #
 
- 識別碼卡片 
- 識別碼卡 
- 識別卡 
- 識別卡 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- 
Driver Lics#
 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- DriversLic # 
- DriversLics # 
- 執照 # 
- DriversLicenses # 
- 發行的驅動程式 Lic # 
- 發行的驅動程式 Lics # 
- 授權 # 驅動程式 
- 授權 # 驅動程式 
- Driver'Lic#
 
- Driver'Lics#
 
- Driver'License#
 
- Driver'Licenses#
 
- Driver' Lic#
 
- Driver' Lics#
 
- Driver' License#
 
- Driver' Licenses#
 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic#
 
- Driver's Lics#
 
- Driver's License#
 
- Driver's Licenses#
 
- 識別碼卡片 # 
- id cards#
 
- identification card#
 
- identification cards#
 


#### <a name="keywordstatenamedriverslicensename"></a>Keyword_[state_name]_drivers_license_name

- 州別縮寫 (例如 "NY")
 
- 州名稱 (例如 "New York")
    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>美國個別納稅人身分識別碼 (ITIN)

### <a name="format"></a>格式

以 "9" 開頭且第四個數字是 "7" 或 "8" 的九位數，可選擇加上空格或連字號

### <a name="pattern"></a>模式

格式化：
- 數字 "9" 
- 兩位數 
- 一個空格或連字號 
- 一個 "7" 或 "8" 
- 一個數字 
- 一個空格或連字號 
- 四位數

未格式化：
- 數字 "9" 
- 兩位數 
- 一個 "7" 或 "8" 
- 五位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_formatted_itin 找到符合模式的內容。
- 下列至少一項為真：
    - 找到來自於 Keyword_itin 的關鍵字。
    - 函數 Func_us_address 找到正確日期格式的地址。
    - 函數 Func_us_date 找到正確日期格式的日期。
    - 找到來自於 Keyword_itin_collaborative 的關鍵字。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_unformatted_itin 找到符合模式的內容。
- 下列至少一項為真：
    - 找到來自於 Keyword_itin_collaborative 的關鍵字。
    - 函數 Func_us_address 找到正確日期格式的地址。
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
 
- tax id
 
- tax identification
 
- itin
 
- ssn 
- tin
 
- 社會安全 
- tax payer
 
- itins
 
- taxid

 
- individual taxpayer
 

#### <a name="keyworditincollaborative"></a>Keyword_itin_collaborative

- License 
- DL 
- DOB
 
- 出生日期 
- 生日  
- Date of Birth
 
   
## <a name="us-social-security-number-ssn"></a>美國社會安全編號 (SSN)

### <a name="format"></a>格式

9 位數，可採用格式化或未格式化模式

> [!NOTE]
> SSN 發出 mid 2011 之前，是否具有強式格式設定其中某些部分的數字必須落在有效特定範圍 （但沒有具總和檢查碼）。

### <a name="pattern"></a>模式

四個不同的模式 SSNs 尋找四個函數：
- Func_ssn 都會尋找 SSNs 之前 2011年強式格式格式為虛線或空格 (ddd-dd-dddd OR ddd dd dddd)
- Func_unformatted_ssn 都會尋找 SSNs 之前 2011年強式的格式以未格式化為九個連續的數字 (ddddddddd)
- Func_randomized_formatted_ssn 都會以虛線或空格 (ddd-dd-dddd OR ddd dd dddd) 格式化的張貼 2011 SSNs
- Func_randomized_unformatted_ssn 會尋找已格式化為九個連續的數字 (ddddddddd) 的文章 2011 SSNs

### <a name="checksum"></a>總和檢查碼

否


### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
- 函數 Func_ssn 找到符合模式的內容。
- 找到來自於 Keyword_ssn 的關鍵字。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
- 函數 Func_unformatted_ssn 會找出符合模式的內容。
- 找到來自於 Keyword_ssn 的關鍵字。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
- 函數 Func_randomized_formatted_ssn 找到符合模式的內容。
- 找到來自於 Keyword_ssn 的關鍵字。
- 函數 Func_ssn 找不到符合模式的內容。

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 55%：
- 函數 Func_randomized_unformatted_ssn 找到符合模式的內容。
- 找到來自於 Keyword_ssn 的關鍵字。
- 函數 Func_unformatted_ssn 找不到符合模式的內容。

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

- Social Security
 
- Social Security#
 
- Soc Sec
 
- SSN 
- SSNS
 
- SSN#
 
- SS#
 
- SSID
 
   

