---
title: 敏感資訊類型在找什麼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含 80 準備好讓您能夠使用 DLP 原則中的敏感資訊類型。本主題列出所有的這些機密資訊類型及顯示新的 DLP 原則會尋找時被每個類型。
ms.openlocfilehash: 4b083f80e02c80053b63ee897b2515a4505c16d9
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194734"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="d3c7c-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-104">What the sensitive information types look for</span></span>

<span data-ttu-id="d3c7c-p102">Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題列出所有的這些機密資訊類型及顯示新的 DLP 原則會尋找時被每個類型。敏感資訊類型定義由可藉由規則運算式或函數的模式。此外，例如關鍵字和總和檢查碼佐證性證據可用來識別敏感資訊類型。信賴等級和鄰近性也會用於評估程序。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="d3c7c-110">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-111">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-111">Format</span></span>

<span data-ttu-id="d3c7c-112">可採用格式化或未格式化模式的 9 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-113">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-113">Pattern</span></span>

<span data-ttu-id="d3c7c-114">格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-114">Formatted:</span></span>
- <span data-ttu-id="d3c7c-115">以 0、1、2、3、6、7 或 8 開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="d3c7c-116">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-116">A hyphen</span></span>
- <span data-ttu-id="d3c7c-117">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-117">Four digits</span></span>
- <span data-ttu-id="d3c7c-118">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-118">A hyphen</span></span>
- <span data-ttu-id="d3c7c-119">一個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-119">A digit</span></span>

<span data-ttu-id="d3c7c-120">未格式化： 9 連續的數字開頭為 0、 1、 2、 3、 6、 7 或 8</span><span class="sxs-lookup"><span data-stu-id="d3c7c-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="d3c7c-121">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-121">Checksum</span></span>

<span data-ttu-id="d3c7c-122">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-123">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-123">Definition</span></span>

<span data-ttu-id="d3c7c-124">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-126">找到來自於 Keyword_ABA_Routing 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="d3c7c-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="d3c7c-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="d3c7c-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="d3c7c-129">aba</span><span class="sxs-lookup"><span data-stu-id="d3c7c-129">aba</span></span>
- <span data-ttu-id="d3c7c-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-130">aba #</span></span>
- <span data-ttu-id="d3c7c-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-131">aba routing #</span></span>
- <span data-ttu-id="d3c7c-132">
aba routing number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-132">aba routing number</span></span>
- <span data-ttu-id="d3c7c-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-133">aba#</span></span>
- <span data-ttu-id="d3c7c-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-134">abarouting#</span></span>
- <span data-ttu-id="d3c7c-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-135">aba number</span></span>
- <span data-ttu-id="d3c7c-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d3c7c-136">abaroutingnumber</span></span>
- <span data-ttu-id="d3c7c-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-137">american bank association routing #</span></span>
- <span data-ttu-id="d3c7c-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-138">american bank association routing number</span></span>
- <span data-ttu-id="d3c7c-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="d3c7c-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d3c7c-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="d3c7c-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-141">bank routing number</span></span>
- <span data-ttu-id="d3c7c-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-142">bankrouting#</span></span>
- <span data-ttu-id="d3c7c-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d3c7c-143">bankroutingnumber</span></span>
- <span data-ttu-id="d3c7c-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-144">routing transit number</span></span>
- <span data-ttu-id="d3c7c-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="d3c7c-146">阿根廷國民識別 (DNI) 碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-147">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-147">Format</span></span>

<span data-ttu-id="d3c7c-148">以句點分隔的八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-149">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-149">Pattern</span></span>

<span data-ttu-id="d3c7c-150">八位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-150">Eight digits:</span></span>
- <span data-ttu-id="d3c7c-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-151">Two digits</span></span>
- <span data-ttu-id="d3c7c-152">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-152">A period</span></span>
- <span data-ttu-id="d3c7c-153">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-153">Three digits</span></span>
- <span data-ttu-id="d3c7c-154">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-154">A period</span></span>
- <span data-ttu-id="d3c7c-155">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-156">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-156">Checksum</span></span>

<span data-ttu-id="d3c7c-157">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-158">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-158">Definition</span></span>

<span data-ttu-id="d3c7c-159">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-160">規則運算式 Regex_argentina_national_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-161">從 Keyword_argentina_national_id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="d3c7c-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="d3c7c-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="d3c7c-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="d3c7c-165">Identity</span></span> 
- <span data-ttu-id="d3c7c-166">識別國民身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="d3c7c-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-167">DNI</span></span> 
- <span data-ttu-id="d3c7c-168">NIC 的人員國民登錄</span><span class="sxs-lookup"><span data-stu-id="d3c7c-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="d3c7c-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="d3c7c-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="d3c7c-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-171">Identidad</span></span> 
- <span data-ttu-id="d3c7c-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="d3c7c-173">澳洲銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-174">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-174">Format</span></span>

<span data-ttu-id="d3c7c-175">包含或不含銀行代號的 6-10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-176">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-176">Pattern</span></span>

<span data-ttu-id="d3c7c-p103">帳戶號碼為 6-10 位數。澳洲銀行狀態分支號碼：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="d3c7c-179">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-179">Three digits</span></span> 
- <span data-ttu-id="d3c7c-180">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-180">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-181">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-182">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-182">Checksum</span></span>

<span data-ttu-id="d3c7c-183">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-184">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-184">Definition</span></span>

<span data-ttu-id="d3c7c-185">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-186">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="d3c7c-187">找到來自於 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="d3c7c-188">規則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="d3c7c-189">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-190">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="d3c7c-191">找到來自於 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="d3c7c-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="d3c7c-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="d3c7c-194">swift bank code</span></span>
- <span data-ttu-id="d3c7c-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="d3c7c-195">correspondent bank</span></span>
- <span data-ttu-id="d3c7c-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="d3c7c-196">base currency</span></span>
- <span data-ttu-id="d3c7c-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="d3c7c-197">usa account</span></span>
- <span data-ttu-id="d3c7c-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="d3c7c-198">holder address</span></span>
- <span data-ttu-id="d3c7c-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="d3c7c-199">bank address</span></span>
- <span data-ttu-id="d3c7c-200">
information account</span><span class="sxs-lookup"><span data-stu-id="d3c7c-200">information account</span></span>
- <span data-ttu-id="d3c7c-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="d3c7c-201">fund transfers</span></span>
- <span data-ttu-id="d3c7c-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="d3c7c-202">bank charges</span></span>
- <span data-ttu-id="d3c7c-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="d3c7c-203">bank details</span></span>
- <span data-ttu-id="d3c7c-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="d3c7c-204">banking information</span></span>
- <span data-ttu-id="d3c7c-205">
full names</span><span class="sxs-lookup"><span data-stu-id="d3c7c-205">full names</span></span>
- <span data-ttu-id="d3c7c-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="d3c7c-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="d3c7c-207">澳洲駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-208">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-208">Format</span></span>

<span data-ttu-id="d3c7c-209">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-210">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-210">Pattern</span></span>

<span data-ttu-id="d3c7c-211">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="d3c7c-212">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-213">Two digits</span></span> 
- <span data-ttu-id="d3c7c-214">五個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="d3c7c-215">OR</span><span class="sxs-lookup"><span data-stu-id="d3c7c-215">OR</span></span>

- <span data-ttu-id="d3c7c-216">1-2 選用字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-217">4-9 digits</span></span>

<span data-ttu-id="d3c7c-218">OR</span><span class="sxs-lookup"><span data-stu-id="d3c7c-218">OR</span></span>

- <span data-ttu-id="d3c7c-219">九個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-220">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-220">Checksum</span></span>

<span data-ttu-id="d3c7c-221">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-222">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-222">Definition</span></span>

<span data-ttu-id="d3c7c-223">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-224">規則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-225">找到來自於 Keyword_australia_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="d3c7c-226">找不到來自於 Keyword_australia_drivers_license_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="d3c7c-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="d3c7c-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="d3c7c-229">international driving permits</span></span>
- <span data-ttu-id="d3c7c-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="d3c7c-230">australian automobile association</span></span>
- <span data-ttu-id="d3c7c-231">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-231">international driving permit</span></span>
- <span data-ttu-id="d3c7c-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-232">DriverLicence</span></span>
- <span data-ttu-id="d3c7c-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-233">DriverLicences</span></span>
- <span data-ttu-id="d3c7c-234">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-234">Driver Lic</span></span>
- <span data-ttu-id="d3c7c-235">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-235">Driver Licence</span></span>
- <span data-ttu-id="d3c7c-236">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-236">Driver Licences</span></span>
- <span data-ttu-id="d3c7c-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-237">DriversLic</span></span>
- <span data-ttu-id="d3c7c-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-238">DriversLicence</span></span>
- <span data-ttu-id="d3c7c-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-239">DriversLicences</span></span>
- <span data-ttu-id="d3c7c-240">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-240">Drivers Lic</span></span>
- <span data-ttu-id="d3c7c-241">發行的驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-241">Drivers Lics</span></span>
- <span data-ttu-id="d3c7c-242">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-242">Drivers Licence</span></span>
- <span data-ttu-id="d3c7c-243">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-243">Drivers Licences</span></span>
- <span data-ttu-id="d3c7c-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-244">Driver'Lic</span></span>
- <span data-ttu-id="d3c7c-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-245">Driver'Lics</span></span>
- <span data-ttu-id="d3c7c-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-246">Driver'Licence</span></span>
- <span data-ttu-id="d3c7c-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-247">Driver'Licences</span></span>
- <span data-ttu-id="d3c7c-248">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-248">Driver' Lic</span></span>
- <span data-ttu-id="d3c7c-249">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-249">Driver' Lics</span></span>
- <span data-ttu-id="d3c7c-250">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-250">Driver' Licence</span></span>
- <span data-ttu-id="d3c7c-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-251">Driver' Licences</span></span>
- <span data-ttu-id="d3c7c-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-252">Driver'sLic</span></span>
- <span data-ttu-id="d3c7c-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-253">Driver'sLics</span></span>
- <span data-ttu-id="d3c7c-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-254">Driver'sLicence</span></span>
- <span data-ttu-id="d3c7c-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-255">Driver'sLicences</span></span>
- <span data-ttu-id="d3c7c-256">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-256">Driver's Lic</span></span>
- <span data-ttu-id="d3c7c-257">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-257">Driver's Lics</span></span>
- <span data-ttu-id="d3c7c-258">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-258">Driver's Licence</span></span>
- <span data-ttu-id="d3c7c-259">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-259">Driver's Licences</span></span>
- <span data-ttu-id="d3c7c-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-260">DriverLic#</span></span>
- <span data-ttu-id="d3c7c-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-261">DriverLics#</span></span>
- <span data-ttu-id="d3c7c-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-262">DriverLicence#</span></span>
- <span data-ttu-id="d3c7c-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-263">DriverLicences#</span></span>
- <span data-ttu-id="d3c7c-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-264">Driver Lic#</span></span>
- <span data-ttu-id="d3c7c-265">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-265">Driver Lics#</span></span>
- <span data-ttu-id="d3c7c-266">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-266">Driver Licence#</span></span>
- <span data-ttu-id="d3c7c-267">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-267">Driver Licences#</span></span>
- <span data-ttu-id="d3c7c-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-268">DriversLic#</span></span>
- <span data-ttu-id="d3c7c-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-269">DriversLics#</span></span>
- <span data-ttu-id="d3c7c-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-270">DriversLicence#</span></span>
- <span data-ttu-id="d3c7c-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-271">DriversLicences#</span></span>
- <span data-ttu-id="d3c7c-272">發行的驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-272">Drivers Lic#</span></span>
- <span data-ttu-id="d3c7c-273">發行的驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-273">Drivers Lics#</span></span>
- <span data-ttu-id="d3c7c-274">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-274">Drivers Licence#</span></span>
- <span data-ttu-id="d3c7c-275">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-275">Drivers Licences#</span></span>
- <span data-ttu-id="d3c7c-276">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-276">Driver'Lic#</span></span>
- <span data-ttu-id="d3c7c-277">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-277">Driver'Lics#</span></span>
- <span data-ttu-id="d3c7c-278">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-278">Driver'Licence#</span></span>
- <span data-ttu-id="d3c7c-279">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-279">Driver'Licences#</span></span>
- <span data-ttu-id="d3c7c-280">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-280">Driver' Lic#</span></span>
- <span data-ttu-id="d3c7c-281">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-281">Driver' Lics#</span></span>
- <span data-ttu-id="d3c7c-282">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-282">Driver' Licence#</span></span>
- <span data-ttu-id="d3c7c-283">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-283">Driver' Licences#</span></span>
- <span data-ttu-id="d3c7c-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-284">Driver'sLic#</span></span>
- <span data-ttu-id="d3c7c-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-285">Driver'sLics#</span></span>
- <span data-ttu-id="d3c7c-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-286">Driver'sLicence#</span></span>
- <span data-ttu-id="d3c7c-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-287">Driver'sLicences#</span></span>
- <span data-ttu-id="d3c7c-288">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-288">Driver's Lic#</span></span>
- <span data-ttu-id="d3c7c-289">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-289">Driver's Lics#</span></span>
- <span data-ttu-id="d3c7c-290">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-290">Driver's Licence#</span></span>
- <span data-ttu-id="d3c7c-291">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="d3c7c-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="d3c7c-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="d3c7c-293">aaa</span><span class="sxs-lookup"><span data-stu-id="d3c7c-293">aaa</span></span>
- <span data-ttu-id="d3c7c-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d3c7c-294">DriverLicense</span></span>
- <span data-ttu-id="d3c7c-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-295">DriverLicenses</span></span>
- <span data-ttu-id="d3c7c-296">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-296">Driver License</span></span>
- <span data-ttu-id="d3c7c-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-297">Driver Licenses</span></span>
- <span data-ttu-id="d3c7c-298">執照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-298">DriversLicense</span></span>
- <span data-ttu-id="d3c7c-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-299">DriversLicenses</span></span>
- <span data-ttu-id="d3c7c-300">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-300">Drivers License</span></span>
- <span data-ttu-id="d3c7c-301">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-301">Drivers Licenses</span></span>
- <span data-ttu-id="d3c7c-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d3c7c-302">Driver'License</span></span>
- <span data-ttu-id="d3c7c-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-303">Driver'Licenses</span></span>
- <span data-ttu-id="d3c7c-304">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-304">Driver' License</span></span>
- <span data-ttu-id="d3c7c-305">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-305">Driver' Licenses</span></span>
- <span data-ttu-id="d3c7c-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d3c7c-306">Driver'sLicense</span></span>
- <span data-ttu-id="d3c7c-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-307">Driver'sLicenses</span></span>
- <span data-ttu-id="d3c7c-308">駕照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-308">Driver's License</span></span>
- <span data-ttu-id="d3c7c-309">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-309">Driver's Licenses</span></span>
- <span data-ttu-id="d3c7c-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-310">DriverLicense#</span></span>
- <span data-ttu-id="d3c7c-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-311">DriverLicenses#</span></span>
- <span data-ttu-id="d3c7c-312">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-312">Driver License#</span></span>
- <span data-ttu-id="d3c7c-313">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-313">Driver Licenses#</span></span>
- <span data-ttu-id="d3c7c-314">執照 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-314">DriversLicense#</span></span>
- <span data-ttu-id="d3c7c-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-315">DriversLicenses#</span></span>
- <span data-ttu-id="d3c7c-316">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-316">Drivers License#</span></span>
- <span data-ttu-id="d3c7c-317">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-317">Drivers Licenses#</span></span>
- <span data-ttu-id="d3c7c-318">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-318">Driver'License#</span></span>
- <span data-ttu-id="d3c7c-319">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-319">Driver'Licenses#</span></span>
- <span data-ttu-id="d3c7c-320">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-320">Driver' License#</span></span>
- <span data-ttu-id="d3c7c-321">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-321">Driver' Licenses#</span></span>
- <span data-ttu-id="d3c7c-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-322">Driver'sLicense#</span></span>
- <span data-ttu-id="d3c7c-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="d3c7c-324">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-324">Driver's License#</span></span>
- <span data-ttu-id="d3c7c-325">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="d3c7c-326">澳洲醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-327">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-327">Format</span></span>

<span data-ttu-id="d3c7c-328">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-329">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-329">Pattern</span></span>

<span data-ttu-id="d3c7c-330">10-11 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-330">10-11 digits:</span></span>
- <span data-ttu-id="d3c7c-331">第一個數字在 2-6 的範圍內</span><span class="sxs-lookup"><span data-stu-id="d3c7c-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="d3c7c-332">第九個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="d3c7c-333">第十個數字是簽發碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="d3c7c-334">第十一個數字 (選用) 是個人碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-335">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-335">Checksum</span></span>

<span data-ttu-id="d3c7c-336">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-337">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-337">Definition</span></span>

<span data-ttu-id="d3c7c-338">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-339">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-340">找到來自於 Keyword_Australia_Medical_Account_Number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="d3c7c-341">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-341">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-342">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-343">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-344">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="d3c7c-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="d3c7c-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="d3c7c-347">bank account details</span></span>
- <span data-ttu-id="d3c7c-348">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="d3c7c-348">medicare payments</span></span>
- <span data-ttu-id="d3c7c-349">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="d3c7c-349">mortgage account</span></span>
- <span data-ttu-id="d3c7c-350">
bank payments</span><span class="sxs-lookup"><span data-stu-id="d3c7c-350">bank payments</span></span>
- <span data-ttu-id="d3c7c-351">
information branch</span><span class="sxs-lookup"><span data-stu-id="d3c7c-351">information branch</span></span>
- <span data-ttu-id="d3c7c-352">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="d3c7c-352">credit card loan</span></span>
- <span data-ttu-id="d3c7c-353">
department of human services</span><span class="sxs-lookup"><span data-stu-id="d3c7c-353">department of human services</span></span>
- <span data-ttu-id="d3c7c-354">本機服務</span><span class="sxs-lookup"><span data-stu-id="d3c7c-354">local service</span></span>
- <span data-ttu-id="d3c7c-355">

medicare</span><span class="sxs-lookup"><span data-stu-id="d3c7c-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="d3c7c-356">澳洲護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-357">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-357">Format</span></span>

<span data-ttu-id="d3c7c-358">字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-359">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-359">Pattern</span></span>

<span data-ttu-id="d3c7c-360">一個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-361">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-361">Checksum</span></span>

<span data-ttu-id="d3c7c-362">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-363">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-363">Definition</span></span>

<span data-ttu-id="d3c7c-364">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-365">規則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-366">從 Keyword_passport 或 Keyword_australia_passport_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="d3c7c-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-368">Keyword_passport</span></span>

- <span data-ttu-id="d3c7c-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-369">Passport Number</span></span>
- <span data-ttu-id="d3c7c-370">
Passport No</span><span class="sxs-lookup"><span data-stu-id="d3c7c-370">Passport No</span></span>
- <span data-ttu-id="d3c7c-371">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-371">Passport #</span></span>
- <span data-ttu-id="d3c7c-372">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-372">Passport#</span></span>
- <span data-ttu-id="d3c7c-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-373">PassportID</span></span>
- <span data-ttu-id="d3c7c-374">Passportno
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-374">Passportno</span></span>
- <span data-ttu-id="d3c7c-375">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-375">passportnumber</span></span>
- <span data-ttu-id="d3c7c-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="d3c7c-376">パスポート</span></span>
- <span data-ttu-id="d3c7c-377">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-377">パスポート番号</span></span>
- <span data-ttu-id="d3c7c-378">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-378">パスポートのNum</span></span>
- <span data-ttu-id="d3c7c-379">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-379">パスポート ＃</span></span> 
- <span data-ttu-id="d3c7c-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-380">Numéro de passeport</span></span>
- <span data-ttu-id="d3c7c-381">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-381">Passeport n °</span></span>
- <span data-ttu-id="d3c7c-382">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-382">Passeport Non</span></span>
- <span data-ttu-id="d3c7c-383">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-383">Passeport #</span></span>
- <span data-ttu-id="d3c7c-384">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-384">Passeport#</span></span>
- <span data-ttu-id="d3c7c-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d3c7c-385">PasseportNon</span></span>
- <span data-ttu-id="d3c7c-386">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="d3c7c-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="d3c7c-388">passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-388">passport</span></span>
- <span data-ttu-id="d3c7c-389">
passport details</span><span class="sxs-lookup"><span data-stu-id="d3c7c-389">passport details</span></span>
- <span data-ttu-id="d3c7c-390">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="d3c7c-390">immigration and citizenship</span></span>
- <span data-ttu-id="d3c7c-391">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="d3c7c-391">commonwealth of australia</span></span>
- <span data-ttu-id="d3c7c-392">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="d3c7c-392">department of immigration</span></span>
- <span data-ttu-id="d3c7c-393">
residential address</span><span class="sxs-lookup"><span data-stu-id="d3c7c-393">residential address</span></span>
- <span data-ttu-id="d3c7c-394">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="d3c7c-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="d3c7c-395">visa
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-395">visa</span></span>
- <span data-ttu-id="d3c7c-396">
national identity card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-396">national identity card</span></span>
- <span data-ttu-id="d3c7c-397">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-397">passport number</span></span>
- <span data-ttu-id="d3c7c-398">
travel document</span><span class="sxs-lookup"><span data-stu-id="d3c7c-398">travel document</span></span>
- <span data-ttu-id="d3c7c-399">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="d3c7c-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="d3c7c-400">澳洲稅籍編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-401">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-401">Format</span></span>

<span data-ttu-id="d3c7c-402">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-403">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-403">Pattern</span></span>

<span data-ttu-id="d3c7c-404">通常會有如下空格的 8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="d3c7c-405">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-405">Three digits</span></span> 
- <span data-ttu-id="d3c7c-406">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-406">An optional space</span></span> 
- <span data-ttu-id="d3c7c-407">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-407">Three digits</span></span> 
- <span data-ttu-id="d3c7c-408">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-408">An optional space</span></span> 
- <span data-ttu-id="d3c7c-409">2-3 位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-410">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-410">Checksum</span></span>

<span data-ttu-id="d3c7c-411">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-412">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-412">Definition</span></span>

<span data-ttu-id="d3c7c-413">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-414">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-415">找不到來自於 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="d3c7c-416">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="d3c7c-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="d3c7c-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-419">australian business number</span></span>
- <span data-ttu-id="d3c7c-420">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="d3c7c-420">marginal tax rate</span></span>
- <span data-ttu-id="d3c7c-421">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="d3c7c-421">medicare levy</span></span>
- <span data-ttu-id="d3c7c-422">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-422">portfolio number</span></span>
- <span data-ttu-id="d3c7c-423">
service veterans</span><span class="sxs-lookup"><span data-stu-id="d3c7c-423">service veterans</span></span>
- <span data-ttu-id="d3c7c-424">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="d3c7c-424">withholding tax</span></span>
- <span data-ttu-id="d3c7c-425">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="d3c7c-425">individual tax return</span></span>
- <span data-ttu-id="d3c7c-426">

tax file number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="d3c7c-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="d3c7c-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="d3c7c-428">00000000</span><span class="sxs-lookup"><span data-stu-id="d3c7c-428">00000000</span></span>
- <span data-ttu-id="d3c7c-429">11111111</span><span class="sxs-lookup"><span data-stu-id="d3c7c-429">11111111</span></span>
- <span data-ttu-id="d3c7c-430">22222222</span><span class="sxs-lookup"><span data-stu-id="d3c7c-430">22222222</span></span>
- <span data-ttu-id="d3c7c-431">33333333</span><span class="sxs-lookup"><span data-stu-id="d3c7c-431">33333333</span></span>
- <span data-ttu-id="d3c7c-432">44444444</span><span class="sxs-lookup"><span data-stu-id="d3c7c-432">44444444</span></span>
- <span data-ttu-id="d3c7c-433">55555555</span><span class="sxs-lookup"><span data-stu-id="d3c7c-433">55555555</span></span>
- <span data-ttu-id="d3c7c-434">66666666</span><span class="sxs-lookup"><span data-stu-id="d3c7c-434">66666666</span></span>
- <span data-ttu-id="d3c7c-435">77777777</span><span class="sxs-lookup"><span data-stu-id="d3c7c-435">77777777</span></span>
- <span data-ttu-id="d3c7c-436">88888888</span><span class="sxs-lookup"><span data-stu-id="d3c7c-436">88888888</span></span>
- <span data-ttu-id="d3c7c-437">99999999</span><span class="sxs-lookup"><span data-stu-id="d3c7c-437">99999999</span></span>
- <span data-ttu-id="d3c7c-438">000000000</span><span class="sxs-lookup"><span data-stu-id="d3c7c-438">000000000</span></span>
- <span data-ttu-id="d3c7c-439">111111111</span><span class="sxs-lookup"><span data-stu-id="d3c7c-439">111111111</span></span>
- <span data-ttu-id="d3c7c-440">222222222</span><span class="sxs-lookup"><span data-stu-id="d3c7c-440">222222222</span></span>
- <span data-ttu-id="d3c7c-441">333333333</span><span class="sxs-lookup"><span data-stu-id="d3c7c-441">333333333</span></span>
- <span data-ttu-id="d3c7c-442">444444444</span><span class="sxs-lookup"><span data-stu-id="d3c7c-442">444444444</span></span>
- <span data-ttu-id="d3c7c-443">555555555</span><span class="sxs-lookup"><span data-stu-id="d3c7c-443">555555555</span></span>
- <span data-ttu-id="d3c7c-444">666666666</span><span class="sxs-lookup"><span data-stu-id="d3c7c-444">666666666</span></span>
- <span data-ttu-id="d3c7c-445">777777777</span><span class="sxs-lookup"><span data-stu-id="d3c7c-445">777777777</span></span>
- <span data-ttu-id="d3c7c-446">888888888</span><span class="sxs-lookup"><span data-stu-id="d3c7c-446">888888888</span></span>
- <span data-ttu-id="d3c7c-447">999999999</span><span class="sxs-lookup"><span data-stu-id="d3c7c-447">999999999</span></span>
- <span data-ttu-id="d3c7c-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="d3c7c-448">0000000000</span></span>
- <span data-ttu-id="d3c7c-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="d3c7c-449">1111111111</span></span>
- <span data-ttu-id="d3c7c-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="d3c7c-450">2222222222</span></span>
- <span data-ttu-id="d3c7c-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="d3c7c-451">3333333333</span></span>
- <span data-ttu-id="d3c7c-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="d3c7c-452">4444444444</span></span>
- <span data-ttu-id="d3c7c-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="d3c7c-453">5555555555</span></span>
- <span data-ttu-id="d3c7c-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="d3c7c-454">6666666666</span></span>
- <span data-ttu-id="d3c7c-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="d3c7c-455">7777777777</span></span>
- <span data-ttu-id="d3c7c-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="d3c7c-456">8888888888</span></span>
- <span data-ttu-id="d3c7c-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="d3c7c-457">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="d3c7c-458">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-458">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-459">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-459">Format</span></span>

<span data-ttu-id="d3c7c-460">11 位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-460">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-461">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-461">Pattern</span></span>

<span data-ttu-id="d3c7c-462">11 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-462">11 digits plus delimiters:</span></span>
- <span data-ttu-id="d3c7c-463">六位數加上兩個句點組合成 YY.MM.DD 的格式代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-463">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="d3c7c-464">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-464">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-465">三個連續數字 (奇數男生，偶數女生) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-465">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="d3c7c-466">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-466">A period</span></span> 
- <span data-ttu-id="d3c7c-467">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-467">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-468">Checksum</span></span>

<span data-ttu-id="d3c7c-469">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-469">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-470">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-470">Definition</span></span>

<span data-ttu-id="d3c7c-471">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-472">函數 Func_belgium_national_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-472">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-473">從 Keyword_belgium_national_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-473">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="d3c7c-474">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-474">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-475">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-475">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="d3c7c-476">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-476">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="d3c7c-477">Identity</span><span class="sxs-lookup"><span data-stu-id="d3c7c-477">Identity</span></span>
- <span data-ttu-id="d3c7c-478">Registration</span><span class="sxs-lookup"><span data-stu-id="d3c7c-478">Registration</span></span>
- <span data-ttu-id="d3c7c-479">Identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-479">Identification</span></span> 
- <span data-ttu-id="d3c7c-480">ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-480">ID</span></span> 
- <span data-ttu-id="d3c7c-481">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="d3c7c-481">Identiteitskaart</span></span>
- <span data-ttu-id="d3c7c-482">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-482">Registratie nummer</span></span> 
- <span data-ttu-id="d3c7c-483">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-483">Identificatie nummer</span></span> 
- <span data-ttu-id="d3c7c-484">Identiteit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-484">Identiteit</span></span>
- <span data-ttu-id="d3c7c-485">Registratie</span><span class="sxs-lookup"><span data-stu-id="d3c7c-485">Registratie</span></span>
- <span data-ttu-id="d3c7c-486">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-486">Identificatie</span></span> 
- <span data-ttu-id="d3c7c-487">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-487">Carte d’identité</span></span> 
- <span data-ttu-id="d3c7c-488">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="d3c7c-488">numéro d'immatriculation</span></span>
- <span data-ttu-id="d3c7c-489">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-489">numéro d'identification</span></span>
- <span data-ttu-id="d3c7c-490">
identité
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-490">identité</span></span> 
- <span data-ttu-id="d3c7c-491">inscription
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-491">inscription</span></span> 
- <span data-ttu-id="d3c7c-492">Identifikation</span><span class="sxs-lookup"><span data-stu-id="d3c7c-492">Identifikation</span></span>
- <span data-ttu-id="d3c7c-493">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="d3c7c-493">Identifizierung</span></span>
- <span data-ttu-id="d3c7c-494">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-494">Identifikationsnummer</span></span>
- <span data-ttu-id="d3c7c-495">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="d3c7c-495">Personalausweis</span></span>
- <span data-ttu-id="d3c7c-496">Registrierung</span><span class="sxs-lookup"><span data-stu-id="d3c7c-496">Registrierung</span></span>
- <span data-ttu-id="d3c7c-497">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-497">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="d3c7c-498">巴西 CPF 碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-498">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-499">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-499">Format</span></span>

<span data-ttu-id="d3c7c-500">11 位數包含檢查碼，可格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="d3c7c-500">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-501">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-501">Pattern</span></span>

<span data-ttu-id="d3c7c-502">格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-502">Formatted:</span></span>
- <span data-ttu-id="d3c7c-503">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-503">Three digits</span></span> 
- <span data-ttu-id="d3c7c-504">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-504">A period</span></span> 
- <span data-ttu-id="d3c7c-505">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-505">Three digits</span></span> 
- <span data-ttu-id="d3c7c-506">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-506">A period</span></span> 
- <span data-ttu-id="d3c7c-507">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-507">Three digits</span></span> 
- <span data-ttu-id="d3c7c-508">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-508">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-509">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-509">Two digits which are check digits</span></span>

<span data-ttu-id="d3c7c-510">未格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-510">Unformatted:</span></span>
- <span data-ttu-id="d3c7c-511">11 位數，最後二位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-511">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-512">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-512">Checksum</span></span>

<span data-ttu-id="d3c7c-513">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-514">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-514">Definition</span></span>

<span data-ttu-id="d3c7c-515">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-515">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-516">函數 Func_brazil_cpf 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-516">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-517">從 Keyword_brazil_cpf 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-517">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="d3c7c-518">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-518">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-519">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-519">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-520">函數 Func_brazil_cpf 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-520">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-521">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-521">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-522">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-522">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="d3c7c-523">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="d3c7c-523">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="d3c7c-524">CPF</span><span class="sxs-lookup"><span data-stu-id="d3c7c-524">CPF</span></span>
- <span data-ttu-id="d3c7c-525">Identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-525">Identification</span></span>
- <span data-ttu-id="d3c7c-526">Registration</span><span class="sxs-lookup"><span data-stu-id="d3c7c-526">Registration</span></span>
- <span data-ttu-id="d3c7c-527">Revenue</span><span class="sxs-lookup"><span data-stu-id="d3c7c-527">Revenue</span></span>
- <span data-ttu-id="d3c7c-528">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-528">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="d3c7c-529">Imposto
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-529">Imposto</span></span> 
- <span data-ttu-id="d3c7c-530">Identificação
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-530">Identificação</span></span> 
- <span data-ttu-id="d3c7c-531">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-531">Inscrição</span></span> 
- <span data-ttu-id="d3c7c-532">Receita

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-532">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="d3c7c-533">巴西法律實體號碼 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-533">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-534">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-534">Format</span></span>

<span data-ttu-id="d3c7c-535">14 位數包含登記碼、分支碼和檢查碼加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-535">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-536">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-536">Pattern</span></span>
<span data-ttu-id="d3c7c-537">14 位數，加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-537">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="d3c7c-538">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-538">Two digits</span></span> 
- <span data-ttu-id="d3c7c-539">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-539">A period</span></span> 
- <span data-ttu-id="d3c7c-540">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-540">Three digits</span></span> 
- <span data-ttu-id="d3c7c-541">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-541">A period</span></span> 
- <span data-ttu-id="d3c7c-542">三位數 (此前 8 位數為登記碼) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-542">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="d3c7c-543">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="d3c7c-543">A forward slash</span></span> 
- <span data-ttu-id="d3c7c-544">四位數分支碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-544">Four-digit branch number</span></span> 
- <span data-ttu-id="d3c7c-545">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-545">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-546">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-546">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-547">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-547">Checksum</span></span>

<span data-ttu-id="d3c7c-548">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-549">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-549">Definition</span></span>

<span data-ttu-id="d3c7c-550">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-551">函數 Func_brazil_cnpj 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-551">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-552">從 Keyword_brazil_cnpj 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-552">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="d3c7c-553">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-553">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-554">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-554">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-555">函數 Func_brazil_cnpj 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-555">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-556">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-556">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-557">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-557">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="d3c7c-558">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="d3c7c-558">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="d3c7c-559">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-559">CNPJ</span></span> 
- <span data-ttu-id="d3c7c-560">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="d3c7c-560">CNPJ/MF</span></span> 
- <span data-ttu-id="d3c7c-561">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-561">CNPJ-MF</span></span> 
- <span data-ttu-id="d3c7c-562">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-562">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="d3c7c-563">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-563">Taxpayers Registry</span></span> 
- <span data-ttu-id="d3c7c-564">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-564">Legal entity</span></span> 
- <span data-ttu-id="d3c7c-565">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-565">Legal entities</span></span> 
- <span data-ttu-id="d3c7c-566">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-566">Registration Status</span></span> 
- <span data-ttu-id="d3c7c-567">Business
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-567">Business</span></span> 
- <span data-ttu-id="d3c7c-568">Company</span><span class="sxs-lookup"><span data-stu-id="d3c7c-568">Company</span></span>
- <span data-ttu-id="d3c7c-569">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-569">CNPJ</span></span> 
- <span data-ttu-id="d3c7c-570">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-570">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="d3c7c-571">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-571">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="d3c7c-572">CGC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-572">CGC</span></span> 
- <span data-ttu-id="d3c7c-573">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-573">Pessoa jurídica</span></span> 
- <span data-ttu-id="d3c7c-574">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-574">Pessoas jurídicas</span></span> 
- <span data-ttu-id="d3c7c-575">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-575">Situação cadastral</span></span> 
- <span data-ttu-id="d3c7c-576">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-576">Inscrição</span></span> 
- <span data-ttu-id="d3c7c-577">Empresa
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-577">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="d3c7c-578">	巴西國民身分證 (RG)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-578">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-579">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-579">Format</span></span>

<span data-ttu-id="d3c7c-580">Registro Geral （舊格式）： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-580">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="d3c7c-581">Registro de Identidade (RIC) （新格式）： 11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-581">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-582">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-582">Pattern</span></span>

<span data-ttu-id="d3c7c-583">Registro Geral (舊格式)：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-583">Registro Geral (old format):</span></span>
- <span data-ttu-id="d3c7c-584">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-584">Two digits</span></span> 
- <span data-ttu-id="d3c7c-585">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-585">A period</span></span> 
- <span data-ttu-id="d3c7c-586">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-586">Three digits</span></span> 
- <span data-ttu-id="d3c7c-587">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-587">A period</span></span> 
- <span data-ttu-id="d3c7c-588">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-588">Three digits</span></span> 
- <span data-ttu-id="d3c7c-589">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-589">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-590">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-590">One digit which is a check digit</span></span>

<span data-ttu-id="d3c7c-591">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-591">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="d3c7c-592">10 位數 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-592">10 digits</span></span> 
- <span data-ttu-id="d3c7c-593">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-593">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-594">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-594">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-595">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-595">Checksum</span></span>

<span data-ttu-id="d3c7c-596">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-596">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-597">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-597">Definition</span></span>

<span data-ttu-id="d3c7c-598">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-598">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-599">函數 Func_brazil_rg 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-599">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-600">從 Keyword_brazil_rg 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-600">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="d3c7c-601">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-601">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-602">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-602">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-603">函數 Func_brazil_rg 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-603">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-604">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-604">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-605">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-605">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="d3c7c-606">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="d3c7c-606">Keyword_brazil_rg</span></span>

<span data-ttu-id="d3c7c-607">Cédula de identidade 識別卡國家識別碼 número de rregistro registro de Iidentidade registro geral FEA-RG-APP-NO-VERSION （這個關鍵字是區分大小寫） RIC （這個關鍵字是區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-607">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="d3c7c-608">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-608">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-609">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-609">Format</span></span>

<span data-ttu-id="d3c7c-610">7 或 12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-610">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-611">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-611">Pattern</span></span>

<span data-ttu-id="d3c7c-612">加拿大銀行帳戶號碼是 7 位數或 12 位數。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-612">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="d3c7c-613">加拿大銀行帳戶交換號碼是：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-613">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="d3c7c-614">五位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-614">Five digits</span></span> 
- <span data-ttu-id="d3c7c-615">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-615">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-616">三個數字或</span><span class="sxs-lookup"><span data-stu-id="d3c7c-616">Three digits OR</span></span>
- <span data-ttu-id="d3c7c-617">一個零 "0"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-617">A zero "0"</span></span> 
- <span data-ttu-id="d3c7c-618">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-618">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-619">Checksum</span></span>

<span data-ttu-id="d3c7c-620">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-620">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-621">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-621">Definition</span></span>

<span data-ttu-id="d3c7c-622">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-622">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-623">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-623">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-624">找到來自於 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-624">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="d3c7c-625">規則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-625">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="d3c7c-626">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-627">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-627">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-628">找到來自於 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-628">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-629">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-629">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="d3c7c-630">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-630">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="d3c7c-631">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="d3c7c-631">canada savings bonds</span></span>
- <span data-ttu-id="d3c7c-632">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="d3c7c-632">canada revenue agency</span></span>
- <span data-ttu-id="d3c7c-633">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="d3c7c-633">canadian financial institution</span></span>
- <span data-ttu-id="d3c7c-634">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="d3c7c-634">direct deposit form</span></span>
- <span data-ttu-id="d3c7c-635">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="d3c7c-635">canadian citizen</span></span>
- <span data-ttu-id="d3c7c-636">
legal representative</span><span class="sxs-lookup"><span data-stu-id="d3c7c-636">legal representative</span></span>
- <span data-ttu-id="d3c7c-637">
notary public</span><span class="sxs-lookup"><span data-stu-id="d3c7c-637">notary public</span></span>
- <span data-ttu-id="d3c7c-638">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="d3c7c-638">commissioner for oaths</span></span>
- <span data-ttu-id="d3c7c-639">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-639">child care benefit</span></span>
- <span data-ttu-id="d3c7c-640">
universal child care</span><span class="sxs-lookup"><span data-stu-id="d3c7c-640">universal child care</span></span>
- <span data-ttu-id="d3c7c-641">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-641">canada child tax benefit</span></span>
- <span data-ttu-id="d3c7c-642">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-642">income tax benefit</span></span>
- <span data-ttu-id="d3c7c-643">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="d3c7c-643">harmonized sales tax</span></span>
- <span data-ttu-id="d3c7c-644">social insurance number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-644">social insurance number</span></span>
- <span data-ttu-id="d3c7c-645">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="d3c7c-645">income tax refund</span></span>
- <span data-ttu-id="d3c7c-646">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-646">child tax benefit</span></span>
- <span data-ttu-id="d3c7c-647">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="d3c7c-647">territorial payments</span></span>
- <span data-ttu-id="d3c7c-648">
institution number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-648">institution number</span></span>
- <span data-ttu-id="d3c7c-649">
deposit request</span><span class="sxs-lookup"><span data-stu-id="d3c7c-649">deposit request</span></span>
- <span data-ttu-id="d3c7c-650">
banking information</span><span class="sxs-lookup"><span data-stu-id="d3c7c-650">banking information</span></span>
- <span data-ttu-id="d3c7c-651">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="d3c7c-651">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="d3c7c-652">加拿大駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-652">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-653">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-653">Format</span></span>

<span data-ttu-id="d3c7c-654">隨省分而不同</span><span class="sxs-lookup"><span data-stu-id="d3c7c-654">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-655">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-655">Pattern</span></span>

<span data-ttu-id="d3c7c-656">Alberta、British Columbia、Manitoba、New Brunswick、Newfoundland/Labrador、Nova Scotia、Ontario、Prince Edward Island、Quebec 和 Saskatchewan 各有不同模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-656">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-657">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-657">Checksum</span></span>

<span data-ttu-id="d3c7c-658">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-658">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-659">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-659">Definition</span></span>

<span data-ttu-id="d3c7c-660">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-660">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-661">函數 Func_[province_name]_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-661">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-662">找到來自於 Keyword_[province_name]_drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-662">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d3c7c-663">找到來自於 Keyword_canada_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-663">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-664">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-664">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="d3c7c-665">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="d3c7c-665">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="d3c7c-666">省分縮寫，例如 AB</span><span class="sxs-lookup"><span data-stu-id="d3c7c-666">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="d3c7c-667">
省分名稱，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-667">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="d3c7c-668">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d3c7c-668">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="d3c7c-669">DL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-669">DL</span></span>
- <span data-ttu-id="d3c7c-670">DLS</span><span class="sxs-lookup"><span data-stu-id="d3c7c-670">DLS</span></span>
- <span data-ttu-id="d3c7c-671">CDL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-671">CDL</span></span>
- <span data-ttu-id="d3c7c-672">CDLS</span><span class="sxs-lookup"><span data-stu-id="d3c7c-672">CDLS</span></span>
- <span data-ttu-id="d3c7c-673">DriverLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-673">DriverLic</span></span>
- <span data-ttu-id="d3c7c-674">DriverLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-674">DriverLics</span></span>
- <span data-ttu-id="d3c7c-675">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d3c7c-675">DriverLicense</span></span>
- <span data-ttu-id="d3c7c-676">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-676">DriverLicenses</span></span>
- <span data-ttu-id="d3c7c-677">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-677">DriverLicence</span></span>
- <span data-ttu-id="d3c7c-678">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-678">DriverLicences</span></span>
- <span data-ttu-id="d3c7c-679">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-679">Driver Lic</span></span>
- <span data-ttu-id="d3c7c-680">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-680">Driver Lics</span></span>
- <span data-ttu-id="d3c7c-681">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-681">Driver License</span></span>
- <span data-ttu-id="d3c7c-682">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-682">Driver Licenses</span></span>
- <span data-ttu-id="d3c7c-683">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-683">Driver Licence</span></span>
- <span data-ttu-id="d3c7c-684">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-684">Driver Licences</span></span>
- <span data-ttu-id="d3c7c-685">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-685">DriversLic</span></span>
- <span data-ttu-id="d3c7c-686">DriversLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-686">DriversLics</span></span>
- <span data-ttu-id="d3c7c-687">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-687">DriversLicence</span></span>
- <span data-ttu-id="d3c7c-688">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-688">DriversLicences</span></span>
- <span data-ttu-id="d3c7c-689">執照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-689">DriversLicense</span></span>
- <span data-ttu-id="d3c7c-690">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-690">DriversLicenses</span></span>
- <span data-ttu-id="d3c7c-691">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-691">Drivers Lic</span></span>
- <span data-ttu-id="d3c7c-692">發行的驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-692">Drivers Lics</span></span>
- <span data-ttu-id="d3c7c-693">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-693">Drivers License</span></span>
- <span data-ttu-id="d3c7c-694">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-694">Drivers Licenses</span></span>
- <span data-ttu-id="d3c7c-695">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-695">Drivers Licence</span></span>
- <span data-ttu-id="d3c7c-696">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-696">Drivers Licences</span></span>
- <span data-ttu-id="d3c7c-697">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-697">Driver'Lic</span></span>
- <span data-ttu-id="d3c7c-698">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-698">Driver'Lics</span></span>
- <span data-ttu-id="d3c7c-699">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d3c7c-699">Driver'License</span></span>
- <span data-ttu-id="d3c7c-700">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-700">Driver'Licenses</span></span>
- <span data-ttu-id="d3c7c-701">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-701">Driver'Licence</span></span>
- <span data-ttu-id="d3c7c-702">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-702">Driver'Licences</span></span>
- <span data-ttu-id="d3c7c-703">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-703">Driver' Lic</span></span>
- <span data-ttu-id="d3c7c-704">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-704">Driver' Lics</span></span>
- <span data-ttu-id="d3c7c-705">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-705">Driver' License</span></span>
- <span data-ttu-id="d3c7c-706">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-706">Driver' Licenses</span></span>
- <span data-ttu-id="d3c7c-707">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-707">Driver' Licence</span></span>
- <span data-ttu-id="d3c7c-708">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-708">Driver' Licences</span></span>
- <span data-ttu-id="d3c7c-709">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-709">Driver'sLic</span></span>
- <span data-ttu-id="d3c7c-710">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-710">Driver'sLics</span></span>
- <span data-ttu-id="d3c7c-711">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d3c7c-711">Driver'sLicense</span></span>
- <span data-ttu-id="d3c7c-712">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-712">Driver'sLicenses</span></span>
- <span data-ttu-id="d3c7c-713">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-713">Driver'sLicence</span></span>
- <span data-ttu-id="d3c7c-714">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-714">Driver'sLicences</span></span>
- <span data-ttu-id="d3c7c-715">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-715">Driver's Lic</span></span>
- <span data-ttu-id="d3c7c-716">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-716">Driver's Lics</span></span>
- <span data-ttu-id="d3c7c-717">駕照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-717">Driver's License</span></span>
- <span data-ttu-id="d3c7c-718">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-718">Driver's Licenses</span></span>
- <span data-ttu-id="d3c7c-719">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-719">Driver's Licence</span></span>
- <span data-ttu-id="d3c7c-720">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-720">Driver's Licences</span></span>
- <span data-ttu-id="d3c7c-721">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="d3c7c-721">Permis de Conduire</span></span>
- <span data-ttu-id="d3c7c-722">id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-722">id</span></span>
- <span data-ttu-id="d3c7c-723">識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-723">ids</span></span>
- <span data-ttu-id="d3c7c-724">
idcard number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-724">idcard number</span></span>
- <span data-ttu-id="d3c7c-725">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="d3c7c-725">idcard numbers</span></span>
- <span data-ttu-id="d3c7c-726">
idcard #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-726">idcard #</span></span>
- <span data-ttu-id="d3c7c-727">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="d3c7c-727">idcard #s</span></span>
- <span data-ttu-id="d3c7c-728">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="d3c7c-728">idcard card</span></span>
- <span data-ttu-id="d3c7c-729">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-729">idcard cards</span></span>
- <span data-ttu-id="d3c7c-730">idcard</span><span class="sxs-lookup"><span data-stu-id="d3c7c-730">idcard</span></span>
- <span data-ttu-id="d3c7c-731">identification number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-731">identification number</span></span>
- <span data-ttu-id="d3c7c-732">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-732">identification numbers</span></span>
- <span data-ttu-id="d3c7c-733">identification #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-733">identification #</span></span>
- <span data-ttu-id="d3c7c-734">
identification #s</span><span class="sxs-lookup"><span data-stu-id="d3c7c-734">identification #s</span></span>
- <span data-ttu-id="d3c7c-735">識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-735">identification card</span></span>
- <span data-ttu-id="d3c7c-736">識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-736">identification cards</span></span>
- <span data-ttu-id="d3c7c-737">
identification
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-737">identification</span></span> 
- <span data-ttu-id="d3c7c-738">DL#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-738">DL#</span></span>
- <span data-ttu-id="d3c7c-739">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-739">DLS#</span></span> 
- <span data-ttu-id="d3c7c-740">CDL#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-740">CDL#</span></span> 
- <span data-ttu-id="d3c7c-741">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-741">CDLS#</span></span> 
- <span data-ttu-id="d3c7c-742">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-742">DriverLic#</span></span> 
- <span data-ttu-id="d3c7c-743">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-743">DriverLics#</span></span> 
- <span data-ttu-id="d3c7c-744">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-744">DriverLicense#</span></span> 
- <span data-ttu-id="d3c7c-745">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-745">DriverLicenses#</span></span> 
- <span data-ttu-id="d3c7c-746">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-746">DriverLicence#</span></span> 
- <span data-ttu-id="d3c7c-747">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-747">DriverLicences#</span></span> 
- <span data-ttu-id="d3c7c-748">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-748">Driver Lic#</span></span>
- <span data-ttu-id="d3c7c-749">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-749">Driver Lics#</span></span> 
- <span data-ttu-id="d3c7c-750">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-750">Driver License#</span></span> 
- <span data-ttu-id="d3c7c-751">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-751">Driver Licenses#</span></span> 
- <span data-ttu-id="d3c7c-752">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-752">Driver License#</span></span> 
- <span data-ttu-id="d3c7c-753">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-753">Driver Licences#</span></span> 
- <span data-ttu-id="d3c7c-754">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-754">DriversLic#</span></span> 
- <span data-ttu-id="d3c7c-755">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-755">DriversLics#</span></span> 
- <span data-ttu-id="d3c7c-756">執照 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-756">DriversLicense#</span></span> 
- <span data-ttu-id="d3c7c-757">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-757">DriversLicenses#</span></span> 
- <span data-ttu-id="d3c7c-758">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-758">DriversLicence#</span></span> 
- <span data-ttu-id="d3c7c-759">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-759">DriversLicences#</span></span> 
- <span data-ttu-id="d3c7c-760">發行的驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-760">Drivers Lic#</span></span> 
- <span data-ttu-id="d3c7c-761">發行的驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-761">Drivers Lics#</span></span> 
- <span data-ttu-id="d3c7c-762">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-762">Drivers License#</span></span> 
- <span data-ttu-id="d3c7c-763">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-763">Drivers Licenses#</span></span> 
- <span data-ttu-id="d3c7c-764">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-764">Drivers Licence#</span></span> 
- <span data-ttu-id="d3c7c-765">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-765">Drivers Licences#</span></span> 
- <span data-ttu-id="d3c7c-766">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-766">Driver'Lic#</span></span> 
- <span data-ttu-id="d3c7c-767">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-767">Driver'Lics#</span></span> 
- <span data-ttu-id="d3c7c-768">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-768">Driver'License#</span></span> 
- <span data-ttu-id="d3c7c-769">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-769">Driver'Licenses#</span></span> 
- <span data-ttu-id="d3c7c-770">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-770">Driver'Licence#</span></span> 
- <span data-ttu-id="d3c7c-771">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-771">Driver'Licences#</span></span> 
- <span data-ttu-id="d3c7c-772">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-772">Driver' Lic#</span></span> 
- <span data-ttu-id="d3c7c-773">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-773">Driver' Lics#</span></span> 
- <span data-ttu-id="d3c7c-774">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-774">Driver' License#</span></span> 
- <span data-ttu-id="d3c7c-775">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-775">Driver' Licenses#</span></span> 
- <span data-ttu-id="d3c7c-776">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-776">Driver' Licence#</span></span> 
- <span data-ttu-id="d3c7c-777">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-777">Driver' Licences#</span></span> 
- <span data-ttu-id="d3c7c-778">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-778">Driver'sLic#</span></span> 
- <span data-ttu-id="d3c7c-779">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-779">Driver'sLics#</span></span> 
- <span data-ttu-id="d3c7c-780">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-780">Driver'sLicense#</span></span> 
- <span data-ttu-id="d3c7c-781">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-781">Driver'sLicenses#</span></span> 
- <span data-ttu-id="d3c7c-782">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-782">Driver'sLicence#</span></span> 
- <span data-ttu-id="d3c7c-783">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-783">Driver'sLicences#</span></span> 
- <span data-ttu-id="d3c7c-784">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-784">Driver's Lic#</span></span> 
- <span data-ttu-id="d3c7c-785">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-785">Driver's Lics#</span></span> 
- <span data-ttu-id="d3c7c-786">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-786">Driver's License#</span></span> 
- <span data-ttu-id="d3c7c-787">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-787">Driver's Licenses#</span></span> 
- <span data-ttu-id="d3c7c-788">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-788">Driver's Licence#</span></span> 
- <span data-ttu-id="d3c7c-789">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-789">Driver's Licences#</span></span> 
- <span data-ttu-id="d3c7c-790">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-790">Permis de Conduire#</span></span> 
- <span data-ttu-id="d3c7c-791">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-791">id#</span></span> 
- <span data-ttu-id="d3c7c-792">id #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-792">ids#</span></span> 
- <span data-ttu-id="d3c7c-793">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-793">idcard card#</span></span> 
- <span data-ttu-id="d3c7c-794">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-794">idcard cards#</span></span> 
- <span data-ttu-id="d3c7c-795">idcard#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-795">idcard#</span></span> 
- <span data-ttu-id="d3c7c-796">identification card#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-796">identification card#</span></span> 
- <span data-ttu-id="d3c7c-797">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-797">identification cards#</span></span> 
- <span data-ttu-id="d3c7c-798">identification#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-798">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="d3c7c-799">加拿大國家健保號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-799">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-800">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-800">Format</span></span>

<span data-ttu-id="d3c7c-801">10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-801">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-802">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-802">Pattern</span></span>

<span data-ttu-id="d3c7c-803">10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-803">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-804">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-804">Checksum</span></span>

<span data-ttu-id="d3c7c-805">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-805">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-806">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-806">Definition</span></span>

<span data-ttu-id="d3c7c-807">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-807">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-808">規則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-808">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-809">找到來自於 Keyword_canada_health_service_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-809">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-810">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-810">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="d3c7c-811">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-811">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="d3c7c-812">personal health number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-812">personal health number</span></span>
- <span data-ttu-id="d3c7c-813">
patient information</span><span class="sxs-lookup"><span data-stu-id="d3c7c-813">patient information</span></span>
- <span data-ttu-id="d3c7c-814">狀況服務</span><span class="sxs-lookup"><span data-stu-id="d3c7c-814">health services</span></span>
- <span data-ttu-id="d3c7c-815">
speciality services</span><span class="sxs-lookup"><span data-stu-id="d3c7c-815">speciality services</span></span>
- <span data-ttu-id="d3c7c-816">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="d3c7c-816">automobile accident</span></span>
- <span data-ttu-id="d3c7c-817">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="d3c7c-817">patient hospital</span></span>
- <span data-ttu-id="d3c7c-818">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="d3c7c-818">psychiatrist</span></span>
- <span data-ttu-id="d3c7c-819">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="d3c7c-819">workers compensation</span></span>
- <span data-ttu-id="d3c7c-820">
disability</span><span class="sxs-lookup"><span data-stu-id="d3c7c-820">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="d3c7c-821">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-821">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-822">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-822">Format</span></span>

<span data-ttu-id="d3c7c-823">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-823">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-824">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-824">Pattern</span></span>

<span data-ttu-id="d3c7c-825">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-825">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-826">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-826">Checksum</span></span>

<span data-ttu-id="d3c7c-827">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-827">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-828">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-828">Definition</span></span>

<span data-ttu-id="d3c7c-829">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-829">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-830">規則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-830">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-831">從 Keyword_canada_passport_number 或 Keyword_passport 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-831">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-832">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-832">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="d3c7c-833">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-833">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="d3c7c-834">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="d3c7c-834">canadian citizenship</span></span>
- <span data-ttu-id="d3c7c-835">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-835">canadian passport</span></span>
- <span data-ttu-id="d3c7c-836">
passport application</span><span class="sxs-lookup"><span data-stu-id="d3c7c-836">passport application</span></span>
- <span data-ttu-id="d3c7c-837">
passport photos</span><span class="sxs-lookup"><span data-stu-id="d3c7c-837">passport photos</span></span>
- <span data-ttu-id="d3c7c-838">
certified translator</span><span class="sxs-lookup"><span data-stu-id="d3c7c-838">certified translator</span></span>
- <span data-ttu-id="d3c7c-839">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="d3c7c-839">canadian citizens</span></span>
- <span data-ttu-id="d3c7c-840">
processing times</span><span class="sxs-lookup"><span data-stu-id="d3c7c-840">processing times</span></span>
- <span data-ttu-id="d3c7c-841">

renewal application</span><span class="sxs-lookup"><span data-stu-id="d3c7c-841">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="d3c7c-842">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-842">Keyword_passport</span></span>

- <span data-ttu-id="d3c7c-843">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-843">Passport Number</span></span>
- <span data-ttu-id="d3c7c-844">
Passport No</span><span class="sxs-lookup"><span data-stu-id="d3c7c-844">Passport No</span></span>
- <span data-ttu-id="d3c7c-845">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-845">Passport #</span></span>
- <span data-ttu-id="d3c7c-846">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-846">Passport#</span></span>
- <span data-ttu-id="d3c7c-847">PassportID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-847">PassportID</span></span>
- <span data-ttu-id="d3c7c-848">Passportno
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-848">Passportno</span></span>
- <span data-ttu-id="d3c7c-849">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-849">passportnumber</span></span>
- <span data-ttu-id="d3c7c-850">パスポート</span><span class="sxs-lookup"><span data-stu-id="d3c7c-850">パスポート</span></span>
- <span data-ttu-id="d3c7c-851">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-851">パスポート番号</span></span>
- <span data-ttu-id="d3c7c-852">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-852">パスポートのNum</span></span>
- <span data-ttu-id="d3c7c-853">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-853">パスポート＃</span></span>
- <span data-ttu-id="d3c7c-854">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-854">Numéro de passeport</span></span>
- <span data-ttu-id="d3c7c-855">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-855">Passeport n °</span></span>
- <span data-ttu-id="d3c7c-856">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-856">Passeport Non</span></span>
- <span data-ttu-id="d3c7c-857">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-857">Passeport #</span></span>
- <span data-ttu-id="d3c7c-858">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-858">Passeport#</span></span>
- <span data-ttu-id="d3c7c-859">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d3c7c-859">PasseportNon</span></span>
- <span data-ttu-id="d3c7c-860">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-860">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="d3c7c-861">加拿大個人健康身分識別碼 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-861">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-862">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-862">Format</span></span>

<span data-ttu-id="d3c7c-863">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-863">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-864">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-864">Pattern</span></span>

<span data-ttu-id="d3c7c-865">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-865">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-866">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-866">Checksum</span></span>

<span data-ttu-id="d3c7c-867">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-867">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-868">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-868">Definition</span></span>

<span data-ttu-id="d3c7c-p104">DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 規則運算式 Regex_canada_phin 會找出符合模式的內容。找到至少兩種關鍵字 Keyword_canada_phin 或 Keyword_canada_provinces.</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-871">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-871">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="d3c7c-872">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="d3c7c-872">Keyword_canada_phin</span></span>

- <span data-ttu-id="d3c7c-873">social insurance number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-873">social insurance number</span></span>
- <span data-ttu-id="d3c7c-874">
health information act</span><span class="sxs-lookup"><span data-stu-id="d3c7c-874">health information act</span></span>
- <span data-ttu-id="d3c7c-875">
income tax information</span><span class="sxs-lookup"><span data-stu-id="d3c7c-875">income tax information</span></span>
- <span data-ttu-id="d3c7c-876">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="d3c7c-876">manitoba health</span></span>
- <span data-ttu-id="d3c7c-877">
health registration</span><span class="sxs-lookup"><span data-stu-id="d3c7c-877">health registration</span></span>
- <span data-ttu-id="d3c7c-878">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="d3c7c-878">prescription purchases</span></span>
- <span data-ttu-id="d3c7c-879">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="d3c7c-879">benefit eligibility</span></span>
- <span data-ttu-id="d3c7c-880">
personal health</span><span class="sxs-lookup"><span data-stu-id="d3c7c-880">personal health</span></span>
- <span data-ttu-id="d3c7c-881">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="d3c7c-881">power of attorney</span></span>
- <span data-ttu-id="d3c7c-882">
registration number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-882">registration number</span></span>
- <span data-ttu-id="d3c7c-883">personal health number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-883">personal health number</span></span>
- <span data-ttu-id="d3c7c-884">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="d3c7c-884">practitioner referral</span></span>
- <span data-ttu-id="d3c7c-885">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="d3c7c-885">wellness professional</span></span>
- <span data-ttu-id="d3c7c-886">
patient referral</span><span class="sxs-lookup"><span data-stu-id="d3c7c-886">patient referral</span></span>
- <span data-ttu-id="d3c7c-887">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="d3c7c-887">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="d3c7c-888">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="d3c7c-888">Keyword_canada_provinces</span></span>

- <span data-ttu-id="d3c7c-889">Nunavut</span><span class="sxs-lookup"><span data-stu-id="d3c7c-889">Nunavut</span></span>
- <span data-ttu-id="d3c7c-890">
Quebec</span><span class="sxs-lookup"><span data-stu-id="d3c7c-890">Quebec</span></span>
- <span data-ttu-id="d3c7c-891">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="d3c7c-891">Northwest Territories</span></span>
- <span data-ttu-id="d3c7c-892">
Ontario</span><span class="sxs-lookup"><span data-stu-id="d3c7c-892">Ontario</span></span>
- <span data-ttu-id="d3c7c-893">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="d3c7c-893">British Columbia</span></span>
- <span data-ttu-id="d3c7c-894">
Alberta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-894">Alberta</span></span>
- <span data-ttu-id="d3c7c-895">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="d3c7c-895">Saskatchewan</span></span>
- <span data-ttu-id="d3c7c-896">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="d3c7c-896">Manitoba</span></span>
- <span data-ttu-id="d3c7c-897">
Yukon</span><span class="sxs-lookup"><span data-stu-id="d3c7c-897">Yukon</span></span>
- <span data-ttu-id="d3c7c-898">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="d3c7c-898">Newfoundland and Labrador</span></span>
- <span data-ttu-id="d3c7c-899">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="d3c7c-899">New Brunswick</span></span>
- <span data-ttu-id="d3c7c-900">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="d3c7c-900">Nova Scotia</span></span>
- <span data-ttu-id="d3c7c-901">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="d3c7c-901">Prince Edward Island</span></span>
- <span data-ttu-id="d3c7c-902">加拿大</span><span class="sxs-lookup"><span data-stu-id="d3c7c-902">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="d3c7c-903">加拿大社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-903">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-904">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-904">Format</span></span>

<span data-ttu-id="d3c7c-905">具有選用連字號或空格的 9 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-905">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-906">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-906">Pattern</span></span>

<span data-ttu-id="d3c7c-907">格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-907">Formatted:</span></span>
- <span data-ttu-id="d3c7c-908">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-908">Three digits</span></span> 
- <span data-ttu-id="d3c7c-909">一個連字號或空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-909">A hyphen or space</span></span> 
- <span data-ttu-id="d3c7c-910">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-910">Three digits</span></span> 
- <span data-ttu-id="d3c7c-911">一個連字號或空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-911">A hyphen or space</span></span> 
- <span data-ttu-id="d3c7c-912">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-912">Three digits</span></span>

<span data-ttu-id="d3c7c-913">未格式化： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-913">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-914">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-914">Checksum</span></span>

<span data-ttu-id="d3c7c-915">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-915">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-916">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-916">Definition</span></span>

<span data-ttu-id="d3c7c-917">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-917">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-918">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-918">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-919">至少下列兩項的任意組合：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-919">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="d3c7c-920">找到來自於 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-920">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="d3c7c-921">找到來自於 Keyword_sin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-921">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="d3c7c-922">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-922">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d3c7c-923">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-923">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-924">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-924">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-925">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-925">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-926">找到來自於 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-926">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="d3c7c-927">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-927">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-928">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-928">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="d3c7c-929">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="d3c7c-929">Keyword_sin</span></span>

- <span data-ttu-id="d3c7c-930">sin</span><span class="sxs-lookup"><span data-stu-id="d3c7c-930">sin</span></span> 
- <span data-ttu-id="d3c7c-931">social insurance
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-931">social insurance</span></span> 
- <span data-ttu-id="d3c7c-932">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-932">numero d'assurance sociale</span></span> 
- <span data-ttu-id="d3c7c-933">sins
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-933">sins</span></span> 
- <span data-ttu-id="d3c7c-934">ssn</span><span class="sxs-lookup"><span data-stu-id="d3c7c-934">ssn</span></span> 
- <span data-ttu-id="d3c7c-935">ssns</span><span class="sxs-lookup"><span data-stu-id="d3c7c-935">ssns</span></span> 
- <span data-ttu-id="d3c7c-936">社會安全</span><span class="sxs-lookup"><span data-stu-id="d3c7c-936">social security</span></span> 
- <span data-ttu-id="d3c7c-937">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-937">numero d'assurance social</span></span> 
- <span data-ttu-id="d3c7c-938">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-938">national identification number</span></span> 
- <span data-ttu-id="d3c7c-939">
national id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-939">national id</span></span> 
- <span data-ttu-id="d3c7c-940">sin#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-940">sin#</span></span> 
- <span data-ttu-id="d3c7c-941">soc ins
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-941">soc ins</span></span> 
- <span data-ttu-id="d3c7c-942">social ins
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-942">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="d3c7c-943">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="d3c7c-943">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="d3c7c-944">駕照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-944">driver's license</span></span> 
- <span data-ttu-id="d3c7c-945">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-945">drivers license</span></span> 
- <span data-ttu-id="d3c7c-946">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-946">driver's licence</span></span> 
- <span data-ttu-id="d3c7c-947">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-947">drivers licence</span></span> 
- <span data-ttu-id="d3c7c-948">DOB
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-948">DOB</span></span> 
- <span data-ttu-id="d3c7c-949">出生日期</span><span class="sxs-lookup"><span data-stu-id="d3c7c-949">Birthdate</span></span> 
- <span data-ttu-id="d3c7c-950">生日 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-950">Birthday</span></span> 
- <span data-ttu-id="d3c7c-951">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-951">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="d3c7c-952">	智利身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-952">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-953">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-953">Format</span></span>

<span data-ttu-id="d3c7c-954">7-8 的數字加上分隔符號] 核取數字或字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-954">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-955">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-955">Pattern</span></span>

<span data-ttu-id="d3c7c-956">7-8 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-956">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="d3c7c-957">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-957">1-2 digits</span></span> 
- <span data-ttu-id="d3c7c-958">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-958">A period</span></span> 
- <span data-ttu-id="d3c7c-959">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-959">Three digits</span></span> 
- <span data-ttu-id="d3c7c-960">句點 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-960">A period</span></span> 
- <span data-ttu-id="d3c7c-961">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-961">Three digits</span></span> 
- <span data-ttu-id="d3c7c-962">一個破折號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-962">A dash</span></span> 
- <span data-ttu-id="d3c7c-963">一位數或字母 (不區分大小寫) 的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-963">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-964">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-964">Checksum</span></span>

<span data-ttu-id="d3c7c-965">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-966">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-966">Definition</span></span>

<span data-ttu-id="d3c7c-967">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-967">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-968">函數 Func_chile_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-968">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-969">從 Keyword_chile_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-969">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="d3c7c-970">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-970">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-971">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-971">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-972">函數 Func_chile_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-972">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-973">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-973">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-974">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-974">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="d3c7c-975">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-975">Keyword_chile_id_card</span></span>

- <span data-ttu-id="d3c7c-976">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-976">National Identification Number</span></span> 
- <span data-ttu-id="d3c7c-977">Identity card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-977">Identity card</span></span> 
- <span data-ttu-id="d3c7c-978">ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-978">ID</span></span> 
- <span data-ttu-id="d3c7c-979">Identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-979">Identification</span></span> 
- <span data-ttu-id="d3c7c-980">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-980">Rol Único Nacional</span></span> 
- <span data-ttu-id="d3c7c-981">執行</span><span class="sxs-lookup"><span data-stu-id="d3c7c-981">RUN</span></span> 
- <span data-ttu-id="d3c7c-982">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-982">Rol Único Tributario</span></span> 
- <span data-ttu-id="d3c7c-983">RUT
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-983">RUT</span></span> 
- <span data-ttu-id="d3c7c-984">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-984">Cédula de Identidad</span></span> 
- <span data-ttu-id="d3c7c-985">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-985">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="d3c7c-986">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-986">Tarjeta de identificación</span></span> 
- <span data-ttu-id="d3c7c-987">Identificación
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-987">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="d3c7c-988">	中國居民身分證 (PRC) 號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-988">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-989">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-989">Format</span></span>

<span data-ttu-id="d3c7c-990">18 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-990">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-991">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-991">Pattern</span></span>

<span data-ttu-id="d3c7c-992">18 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-992">18 digits:</span></span>
- <span data-ttu-id="d3c7c-993">六位數的地址代碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-993">Six digits which are an address code</span></span> 
- <span data-ttu-id="d3c7c-994">YYYYMMDD 格式的八位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-994">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-995">三位數的序碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-995">Three digits which are an order code</span></span> 
- <span data-ttu-id="d3c7c-996">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-996">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-997">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-997">Checksum</span></span>

<span data-ttu-id="d3c7c-998">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-998">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-999">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-999">Definition</span></span>

<span data-ttu-id="d3c7c-1000">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1000">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1001">函數 Func_china_resident_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1001">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1002">從 Keyword_china_resident_id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1002">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="d3c7c-1003">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1003">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-1004">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1005">函數 Func_china_resident_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1005">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1006">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1006">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1007">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1007">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="d3c7c-1008">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1008">Keyword_china_resident_id</span></span>

- <span data-ttu-id="d3c7c-1009">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1009">Resident Identity Card</span></span> 
- <span data-ttu-id="d3c7c-1010">PRC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1010">PRC</span></span> 
- <span data-ttu-id="d3c7c-1011">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1011">National Identification Card</span></span> 
- <span data-ttu-id="d3c7c-1012">身份证 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-1012">身份证</span></span> 
- <span data-ttu-id="d3c7c-1013">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-1013">居民 身份证</span></span> 
- <span data-ttu-id="d3c7c-1014">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1014">居民身份证</span></span> 
- <span data-ttu-id="d3c7c-1015">鉴定

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1015">鉴定</span></span> 
- <span data-ttu-id="d3c7c-1016">身分證 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-1016">身分證</span></span> 
- <span data-ttu-id="d3c7c-1017">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1017">居民 身份證</span></span>
- <span data-ttu-id="d3c7c-1018">鑑定 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-1018">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="d3c7c-1019">信用卡號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1019">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1020">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1020">Format</span></span>

<span data-ttu-id="d3c7c-1021">這可設為 16 個位數或格式化 (dddddddddddddddd) 和必須通過 Luhn 測試。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1021">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1022">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1022">Pattern</span></span>

<span data-ttu-id="d3c7c-1023">非常複雜且健全的模式，會偵測全球所有主要品牌的卡片，包括 Visa、MasterCard、Discover Card、JCB、American Express、禮品卡和大來卡。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1023">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1024">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1024">Checksum</span></span>

<span data-ttu-id="d3c7c-1025">是，Luhn 總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1025">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1026">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1026">Definition</span></span>

<span data-ttu-id="d3c7c-1027">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1027">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1028">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1028">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1029">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1029">One of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-1030">找到來自於 Keyword_cc_verification 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1030">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="d3c7c-1031">找到來自於 Keyword_cc_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1031">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="d3c7c-1032">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1032">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d3c7c-1033">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1033">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-1034">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1034">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1035">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1035">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1036">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1036">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1037">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1037">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="d3c7c-1038">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1038">Keyword_cc_verification</span></span>

- <span data-ttu-id="d3c7c-1039">card verification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1039">card verification</span></span>
- <span data-ttu-id="d3c7c-1040">card identification number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1040">card identification number</span></span>
- <span data-ttu-id="d3c7c-1041">cvn
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1041">cvn</span></span>
- <span data-ttu-id="d3c7c-1042">cid
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1042">cid</span></span>
- <span data-ttu-id="d3c7c-1043">cvc2</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1043">cvc2</span></span>
- <span data-ttu-id="d3c7c-1044">cvv2</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1044">cvv2</span></span>
- <span data-ttu-id="d3c7c-1045">pin block
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1045">pin block</span></span>
- <span data-ttu-id="d3c7c-1046">security code
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1046">security code</span></span>
- <span data-ttu-id="d3c7c-1047">security number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1047">security number</span></span>
- <span data-ttu-id="d3c7c-1048">security no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1048">security no</span></span>
- <span data-ttu-id="d3c7c-1049">issue number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1049">issue number</span></span>
- <span data-ttu-id="d3c7c-1050">issue no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1050">issue no</span></span>
- <span data-ttu-id="d3c7c-1051">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1051">cryptogramme</span></span>
- <span data-ttu-id="d3c7c-1052">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1052">numéro de sécurité</span></span>
- <span data-ttu-id="d3c7c-1053">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1053">numero de securite</span></span>
- <span data-ttu-id="d3c7c-1054">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1054">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="d3c7c-1055">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1055">kreditkartenprufnummer</span></span>
- <span data-ttu-id="d3c7c-1056">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1056">prüfziffer</span></span>
- <span data-ttu-id="d3c7c-1057">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1057">prufziffer</span></span>
- <span data-ttu-id="d3c7c-1058">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1058">sicherheits Kode</span></span>
- <span data-ttu-id="d3c7c-1059">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1059">sicherheitscode</span></span>
- <span data-ttu-id="d3c7c-1060">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1060">sicherheitsnummer</span></span>
- <span data-ttu-id="d3c7c-1061">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1061">verfalldatum</span></span>
- <span data-ttu-id="d3c7c-1062">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1062">codice di verifica</span></span>
- <span data-ttu-id="d3c7c-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p105">cod. sicurezza</span></span>
- <span data-ttu-id="d3c7c-1065">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1065">cod sicurezza</span></span>
- <span data-ttu-id="d3c7c-1066">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1066">n autorizzazione</span></span>
- <span data-ttu-id="d3c7c-1067">código
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1067">código</span></span>
- <span data-ttu-id="d3c7c-1068">codigo
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1068">codigo</span></span>
- <span data-ttu-id="d3c7c-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p106">cod. seg</span></span>
- <span data-ttu-id="d3c7c-1071">cod seg</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1071">cod seg</span></span>
- <span data-ttu-id="d3c7c-1072">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1072">código de segurança</span></span>
- <span data-ttu-id="d3c7c-1073">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1073">codigo de seguranca</span></span>
- <span data-ttu-id="d3c7c-1074">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1074">codigo de segurança</span></span>
- <span data-ttu-id="d3c7c-1075">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1075">código de seguranca</span></span>
- <span data-ttu-id="d3c7c-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p107">cód. segurança</span></span>
- <span data-ttu-id="d3c7c-p108">cod。seguranca cod。segurança</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="d3c7c-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p109">cód. seguranca</span></span>
- <span data-ttu-id="d3c7c-1083">cód segurança</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1083">cód segurança</span></span>
- <span data-ttu-id="d3c7c-1084">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1084">cod seguranca cod segurança</span></span>
- <span data-ttu-id="d3c7c-1085">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1085">cód seguranca</span></span>
- <span data-ttu-id="d3c7c-1086">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1086">número de verificação</span></span>
- <span data-ttu-id="d3c7c-1087">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1087">numero de verificacao</span></span>
- <span data-ttu-id="d3c7c-1088">ablauf
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1088">ablauf</span></span>
- <span data-ttu-id="d3c7c-1089">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1089">gültig bis</span></span>
- <span data-ttu-id="d3c7c-1090">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1090">gültigkeitsdatum</span></span>
- <span data-ttu-id="d3c7c-1091">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1091">gultig bis</span></span>
- <span data-ttu-id="d3c7c-1092">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1092">gultigkeitsdatum</span></span>
- <span data-ttu-id="d3c7c-1093">scadenza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1093">scadenza</span></span>
- <span data-ttu-id="d3c7c-1094">data scad
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1094">data scad</span></span>
- <span data-ttu-id="d3c7c-1095">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1095">fecha de expiracion</span></span>
- <span data-ttu-id="d3c7c-1096">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1096">fecha de venc</span></span>
- <span data-ttu-id="d3c7c-1097">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1097">vencimiento</span></span>
- <span data-ttu-id="d3c7c-1098">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1098">válido hasta</span></span>
- <span data-ttu-id="d3c7c-1099">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1099">valido hasta</span></span>
- <span data-ttu-id="d3c7c-1100">vto
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1100">vto</span></span>
- <span data-ttu-id="d3c7c-1101">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1101">data de expiração</span></span>
- <span data-ttu-id="d3c7c-1102">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1102">data de expiracao</span></span>
- <span data-ttu-id="d3c7c-1103">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1103">data em que expira</span></span>
- <span data-ttu-id="d3c7c-1104">validade
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1104">validade</span></span>
- <span data-ttu-id="d3c7c-1105">valor
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1105">valor</span></span>
- <span data-ttu-id="d3c7c-1106">vencimento
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1106">vencimento</span></span>
- <span data-ttu-id="d3c7c-1107">Venc</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1107">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="d3c7c-1108">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1108">Keyword_cc_name</span></span>

- <span data-ttu-id="d3c7c-1109">amex</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1109">amex</span></span>
- <span data-ttu-id="d3c7c-1110">
american express</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1110">american express</span></span>
- <span data-ttu-id="d3c7c-1111">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1111">americanexpress</span></span>
- <span data-ttu-id="d3c7c-1112">因為撰寫</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1112">Visa</span></span>
- <span data-ttu-id="d3c7c-1113">mastercard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1113">mastercard</span></span>
- <span data-ttu-id="d3c7c-1114">master card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1114">master card</span></span>
- <span data-ttu-id="d3c7c-1115">
mc
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1115">mc</span></span> 
- <span data-ttu-id="d3c7c-1116">mastercards</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1116">mastercards</span></span>
- <span data-ttu-id="d3c7c-1117">
master cards</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1117">master cards</span></span>
- <span data-ttu-id="d3c7c-1118">大來卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1118">diner's Club</span></span>
- <span data-ttu-id="d3c7c-1119">diners club
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1119">diners club</span></span>
- <span data-ttu-id="d3c7c-1120">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1120">dinersclub</span></span>
- <span data-ttu-id="d3c7c-1121">discover card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1121">discover card</span></span>
- <span data-ttu-id="d3c7c-1122">discovercard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1122">discovercard</span></span>
- <span data-ttu-id="d3c7c-1123">discover cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1123">discover cards</span></span>
- <span data-ttu-id="d3c7c-1124">JCB</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1124">JCB</span></span>
- <span data-ttu-id="d3c7c-1125">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1125">japanese card bureau</span></span>
- <span data-ttu-id="d3c7c-1126">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1126">carte blanche</span></span>
- <span data-ttu-id="d3c7c-1127">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1127">carteblanche</span></span>
- <span data-ttu-id="d3c7c-1128">credit card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1128">credit card</span></span>
- <span data-ttu-id="d3c7c-1129">[副本] #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1129">cc#</span></span>
- <span data-ttu-id="d3c7c-1130">[副本] # 中：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1130">cc#:</span></span>
- <span data-ttu-id="d3c7c-1131">
expiration date</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1131">expiration date</span></span>
- <span data-ttu-id="d3c7c-1132">exp date
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1132">exp date</span></span>
- <span data-ttu-id="d3c7c-1133">
expiry date</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1133">expiry date</span></span>
- <span data-ttu-id="d3c7c-1134">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1134">date d’expiration</span></span>
- <span data-ttu-id="d3c7c-1135">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1135">date d'exp</span></span>
- <span data-ttu-id="d3c7c-1136">
date expiration</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1136">date expiration</span></span>
- <span data-ttu-id="d3c7c-1137">bank card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1137">bank card</span></span>
- <span data-ttu-id="d3c7c-1138">
bankcard</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1138">bankcard</span></span>
- <span data-ttu-id="d3c7c-1139">card number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1139">card number</span></span>
- <span data-ttu-id="d3c7c-1140">card num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1140">card num</span></span>
- <span data-ttu-id="d3c7c-1141">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1141">cardnumber</span></span>
- <span data-ttu-id="d3c7c-1142">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1142">cardnumbers</span></span>
- <span data-ttu-id="d3c7c-1143">card numbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1143">card numbers</span></span>
- <span data-ttu-id="d3c7c-1144">creditcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1144">creditcard</span></span>
- <span data-ttu-id="d3c7c-1145">credit cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1145">credit cards</span></span>
- <span data-ttu-id="d3c7c-1146">creditcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1146">creditcards</span></span>
- <span data-ttu-id="d3c7c-1147">ccn
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1147">ccn</span></span>
- <span data-ttu-id="d3c7c-1148">card holder
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1148">card holder</span></span>
- <span data-ttu-id="d3c7c-1149">cardholder
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1149">cardholder</span></span>
- <span data-ttu-id="d3c7c-1150">card holders
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1150">card holders</span></span>
- <span data-ttu-id="d3c7c-1151">cardholders
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1151">cardholders</span></span>
- <span data-ttu-id="d3c7c-1152">check card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1152">check card</span></span>
- <span data-ttu-id="d3c7c-1153">checkcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1153">checkcard</span></span>
- <span data-ttu-id="d3c7c-1154">check cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1154">check cards</span></span>
- <span data-ttu-id="d3c7c-1155">checkcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1155">checkcards</span></span>
- <span data-ttu-id="d3c7c-1156">debit card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1156">debit card</span></span>
- <span data-ttu-id="d3c7c-1157">debitcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1157">debitcard</span></span>
- <span data-ttu-id="d3c7c-1158">debit cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1158">debit cards</span></span>
- <span data-ttu-id="d3c7c-1159">debitcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1159">debitcards</span></span>
- <span data-ttu-id="d3c7c-1160">atm card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1160">atm card</span></span>
- <span data-ttu-id="d3c7c-1161">atmcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1161">atmcard</span></span>
- <span data-ttu-id="d3c7c-1162">atm cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1162">atm cards</span></span>
- <span data-ttu-id="d3c7c-1163">atmcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1163">atmcards</span></span>
- <span data-ttu-id="d3c7c-1164">
enroute</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1164">enroute</span></span>
- <span data-ttu-id="d3c7c-1165">
en route</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1165">en route</span></span>
- <span data-ttu-id="d3c7c-1166">card type
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1166">card type</span></span>
- <span data-ttu-id="d3c7c-1167">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1167">carte bancaire</span></span>
- <span data-ttu-id="d3c7c-1168">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1168">carte de crédit</span></span>
- <span data-ttu-id="d3c7c-1169">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1169">carte de credit</span></span>
- <span data-ttu-id="d3c7c-1170">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1170">numéro de carte</span></span>
- <span data-ttu-id="d3c7c-1171">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1171">numero de carte</span></span>
- <span data-ttu-id="d3c7c-1172">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1172">nº de la carte</span></span>
- <span data-ttu-id="d3c7c-1173">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1173">nº de carte</span></span>
- <span data-ttu-id="d3c7c-1174">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1174">kreditkarte</span></span>
- <span data-ttu-id="d3c7c-1175">karte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1175">karte</span></span>
- <span data-ttu-id="d3c7c-1176">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1176">karteninhaber</span></span>
- <span data-ttu-id="d3c7c-1177">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1177">karteninhabers</span></span>
- <span data-ttu-id="d3c7c-1178">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1178">kreditkarteninhaber</span></span>
- <span data-ttu-id="d3c7c-1179">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1179">kreditkarteninstitut</span></span>
- <span data-ttu-id="d3c7c-1180">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1180">kreditkartentyp</span></span>
- <span data-ttu-id="d3c7c-1181">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1181">eigentümername</span></span>
- <span data-ttu-id="d3c7c-1182">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1182">kartennr</span></span> 
- <span data-ttu-id="d3c7c-1183">kartennummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1183">kartennummer</span></span>
- <span data-ttu-id="d3c7c-1184">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1184">kreditkartennummer</span></span>
- <span data-ttu-id="d3c7c-1185">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1185">kreditkarten-nummer</span></span>
- <span data-ttu-id="d3c7c-1186">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1186">carta di credito</span></span>
- <span data-ttu-id="d3c7c-1187">carta credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1187">carta credito</span></span>
- <span data-ttu-id="d3c7c-1188">carta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1188">carta</span></span>
- <span data-ttu-id="d3c7c-1189">n carta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1189">n carta</span></span>
- <span data-ttu-id="d3c7c-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p110">nr. carta</span></span>
- <span data-ttu-id="d3c7c-1192">編號 carta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1192">nr carta</span></span>
- <span data-ttu-id="d3c7c-1193">numero carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1193">numero carta</span></span>
- <span data-ttu-id="d3c7c-1194">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1194">numero della carta</span></span>
- <span data-ttu-id="d3c7c-1195">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1195">numero di carta</span></span>
- <span data-ttu-id="d3c7c-1196">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1196">tarjeta credito</span></span>
- <span data-ttu-id="d3c7c-1197">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1197">tarjeta de credito</span></span>
- <span data-ttu-id="d3c7c-1198">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1198">tarjeta crédito</span></span>
- <span data-ttu-id="d3c7c-1199">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1199">tarjeta de crédito</span></span>
- <span data-ttu-id="d3c7c-1200">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1200">tarjeta de atm</span></span>
- <span data-ttu-id="d3c7c-1201">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1201">tarjeta atm</span></span>
- <span data-ttu-id="d3c7c-1202">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1202">tarjeta debito</span></span>
- <span data-ttu-id="d3c7c-1203">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1203">tarjeta de debito</span></span>
- <span data-ttu-id="d3c7c-1204">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1204">tarjeta débito</span></span>
- <span data-ttu-id="d3c7c-1205">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1205">tarjeta de débito</span></span>
- <span data-ttu-id="d3c7c-1206">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1206">nº de tarjeta</span></span>
- <span data-ttu-id="d3c7c-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p111">no. de tarjeta</span></span>
- <span data-ttu-id="d3c7c-1209">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1209">no de tarjeta</span></span>
- <span data-ttu-id="d3c7c-1210">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1210">numero de tarjeta</span></span>
- <span data-ttu-id="d3c7c-1211">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1211">número de tarjeta</span></span>
- <span data-ttu-id="d3c7c-1212">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1212">tarjeta no</span></span>
- <span data-ttu-id="d3c7c-1213">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1213">tarjetahabiente</span></span>
- <span data-ttu-id="d3c7c-1214">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1214">cartão de crédito</span></span>
- <span data-ttu-id="d3c7c-1215">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1215">cartão de credito</span></span>
- <span data-ttu-id="d3c7c-1216">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1216">cartao de crédito</span></span>
- <span data-ttu-id="d3c7c-1217">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1217">cartao de credito</span></span>
- <span data-ttu-id="d3c7c-1218">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1218">cartão de débito</span></span>
- <span data-ttu-id="d3c7c-1219">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1219">cartao de débito</span></span>
- <span data-ttu-id="d3c7c-1220">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1220">cartão de debito</span></span>
- <span data-ttu-id="d3c7c-1221">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1221">cartao de debito</span></span>
- <span data-ttu-id="d3c7c-1222">débito automático</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1222">débito automático</span></span>
- <span data-ttu-id="d3c7c-1223">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1223">debito automatico</span></span>
- <span data-ttu-id="d3c7c-1224">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1224">número do cartão</span></span>
- <span data-ttu-id="d3c7c-1225">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1225">numero do cartão</span></span> 
- <span data-ttu-id="d3c7c-1226">número do cartao</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1226">número do cartao</span></span>
- <span data-ttu-id="d3c7c-1227">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1227">numero do cartao</span></span>
- <span data-ttu-id="d3c7c-1228">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1228">número de cartão</span></span>
- <span data-ttu-id="d3c7c-1229">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1229">numero de cartão</span></span>
- <span data-ttu-id="d3c7c-1230">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1230">número de cartao</span></span>
- <span data-ttu-id="d3c7c-1231">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1231">numero de cartao</span></span>
- <span data-ttu-id="d3c7c-1232">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1232">nº do cartão</span></span>
- <span data-ttu-id="d3c7c-1233">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1233">nº do cartao</span></span>
- <span data-ttu-id="d3c7c-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p112">nº. do cartão</span></span>
- <span data-ttu-id="d3c7c-1236">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1236">no do cartão</span></span>
- <span data-ttu-id="d3c7c-1237">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1237">no do cartao</span></span>
- <span data-ttu-id="d3c7c-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p113">no. do cartão</span></span>
- <span data-ttu-id="d3c7c-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="d3c7c-1242">	克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1242">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1243">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1243">Format</span></span>

<span data-ttu-id="d3c7c-1244">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1245">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1245">Pattern</span></span>

<span data-ttu-id="d3c7c-1246">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1247">Checksum</span></span>

<span data-ttu-id="d3c7c-1248">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1248">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1249">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1249">Definition</span></span>

<span data-ttu-id="d3c7c-1250">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1251">函數 Func_croatia_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1251">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1252">從 Keyword_croatia_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1252">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1253">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="d3c7c-1254">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1254">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="d3c7c-1255">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1255">Croatian identity card</span></span>
- <span data-ttu-id="d3c7c-1256">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1256">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="d3c7c-1257">	克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1257">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1258">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1258">Format</span></span>

<span data-ttu-id="d3c7c-1259">11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1259">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1260">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1260">Pattern</span></span>

<span data-ttu-id="d3c7c-1261">11 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1261">11 digits:</span></span>
- <span data-ttu-id="d3c7c-1262">10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1262">10 digits</span></span> 
- <span data-ttu-id="d3c7c-1263">最後一個數字是基於的國際資料交換] 核取數字，字母 HR 會新增前面另外的數字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1263">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1264">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1264">Checksum</span></span>

<span data-ttu-id="d3c7c-1265">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1265">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1266">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1266">Definition</span></span>

<span data-ttu-id="d3c7c-1267">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1267">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1268">函數 Func_croatia_oib_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1268">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1269">從 Keyword_croatia_oib_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1269">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="d3c7c-1270">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1270">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-1271">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1272">函數 Func_croatia_oib_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1272">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1273">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1273">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1274">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1274">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="d3c7c-1275">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1275">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="d3c7c-1276">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1276">Personal Identification Number</span></span>
- <span data-ttu-id="d3c7c-1277">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1277">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="d3c7c-1278">OIB
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1278">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="d3c7c-1279">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1279">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1280">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1280">Format</span></span>

<span data-ttu-id="d3c7c-1281">使用選用的九個位數正斜線 （舊格式） 與選用的 10 位數字正斜線 （新格式）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1281">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1282">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1282">Pattern</span></span>

<span data-ttu-id="d3c7c-1283">九個位數 （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1283">Nine digits (old format):</span></span>
- <span data-ttu-id="d3c7c-1284">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1284">Nine digits</span></span>

<span data-ttu-id="d3c7c-1285">OR</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1285">OR</span></span>

- <span data-ttu-id="d3c7c-1286">代表出生日期的六個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1286">Six digits that represent date of birth</span></span>
- <span data-ttu-id="d3c7c-1287">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1287">A forward slash</span></span>
- <span data-ttu-id="d3c7c-1288">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1288">Three digits</span></span>

<span data-ttu-id="d3c7c-1289">10 位數 （新格式）：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1289">10 digits (new format):</span></span>
- <span data-ttu-id="d3c7c-1290">10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1290">10 digits</span></span>

<span data-ttu-id="d3c7c-1291">或</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1291">OR</span></span>

- <span data-ttu-id="d3c7c-1292">代表出生日期的六個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1292">Six digits that represent date of birth</span></span>
- <span data-ttu-id="d3c7c-1293">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1293">A forward slash</span></span> 
- <span data-ttu-id="d3c7c-1294">其中的最後一個數字是核取數字的四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1294">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1295">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1295">Checksum</span></span>

<span data-ttu-id="d3c7c-1296">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1296">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1297">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1297">Definition</span></span>

<span data-ttu-id="d3c7c-p115">DLP 原則是 85%有信心它已偵測到這種類型的機密資訊時，300 個字元的距離： 函數 Func_czech_id_card 會找出符合模式的內容。從 Keyword_czech_id_card 關鍵字是找到。總和檢查碼會傳遞。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="d3c7c-1301">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1301">Keywords</span></span>

- <span data-ttu-id="d3c7c-1302">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1302">czech personal identity number</span></span>
- <span data-ttu-id="d3c7c-1303">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1303">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="d3c7c-1304">	丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1304">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1305">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1305">Format</span></span>

<span data-ttu-id="d3c7c-1306">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1306">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1307">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1307">Pattern</span></span>

<span data-ttu-id="d3c7c-1308">10 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1308">10 digits:</span></span>
- <span data-ttu-id="d3c7c-1309">DDMMYY 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-1309">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-1310">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1310">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-1311">四位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1311">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1312">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1312">Checksum</span></span>

<span data-ttu-id="d3c7c-1313">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1314">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1314">Definition</span></span>

<span data-ttu-id="d3c7c-p116">DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 規則運算式 Regex_denmark_id 會找出符合模式的內容。從 Keyword_denmark_id 關鍵字是找到。總和檢查碼會傳遞。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1318">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1318">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="d3c7c-1319">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1319">Keyword_denmark_id</span></span>

- <span data-ttu-id="d3c7c-1320">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1320">Personal Identification Number</span></span>
- <span data-ttu-id="d3c7c-1321">CPR</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1321">CPR</span></span>
- <span data-ttu-id="d3c7c-1322">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1322">Det Centrale Personregister</span></span>
- <span data-ttu-id="d3c7c-1323">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1323">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="d3c7c-1324">藥物執法機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1324">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1325">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1325">Format</span></span>

<span data-ttu-id="d3c7c-1326">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1326">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1327">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1327">Pattern</span></span>

<span data-ttu-id="d3c7c-1328">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1328">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d3c7c-1329">這組可能的字母中的一個字母 (不區分大小寫)：abcdefghjklmnprstux，此為註冊者代碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1329">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="d3c7c-1330">一個字母 (不區分大小寫)，此為註冊者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1330">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="d3c7c-1331">七位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1331">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1332">Checksum</span></span>

<span data-ttu-id="d3c7c-1333">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1333">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1334">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1334">Definition</span></span>

<span data-ttu-id="d3c7c-1335">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1335">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1336">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1336">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1337">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1337">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1338">Keywords</span></span>

<span data-ttu-id="d3c7c-1339">無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1339">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="d3c7c-1340">歐盟轉帳卡卡號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1340">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1341">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1341">Format</span></span>

<span data-ttu-id="d3c7c-1342">16 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1342">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1343">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1343">Pattern</span></span>

<span data-ttu-id="d3c7c-1344">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1344">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1345">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1345">Checksum</span></span>

<span data-ttu-id="d3c7c-1346">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1346">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1347">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1347">Definition</span></span>

<span data-ttu-id="d3c7c-1348">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1348">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1349">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1349">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1350">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1350">At least one of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-1351">找到來自於 Keyword_eu_debit_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1351">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="d3c7c-1352">找到來自於 Keyword_card_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1352">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="d3c7c-1353">找到來自於 Keyword_card_security_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1353">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="d3c7c-1354">找到來自於 Keyword_card_expiration_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1354">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="d3c7c-1355">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1355">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d3c7c-1356">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1356">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1357">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1357">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="d3c7c-1358">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1358">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="d3c7c-1359">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1359">account number</span></span> 
- <span data-ttu-id="d3c7c-1360">card number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1360">card number</span></span> 
- <span data-ttu-id="d3c7c-1361">card no.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1361">card no.</span></span> 
- <span data-ttu-id="d3c7c-1362">security number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1362">security number</span></span> 
- <span data-ttu-id="d3c7c-1363">[副本] #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1363">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="d3c7c-1364">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1364">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="d3c7c-1365">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1365">acct nbr</span></span> 
- <span data-ttu-id="d3c7c-1366">acct num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1366">acct num</span></span> 
- <span data-ttu-id="d3c7c-1367">acct no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1367">acct no</span></span> 
- <span data-ttu-id="d3c7c-1368">american express
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1368">american express</span></span> 
- <span data-ttu-id="d3c7c-1369">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1369">americanexpress</span></span> 
- <span data-ttu-id="d3c7c-1370">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1370">americano espresso</span></span> 
- <span data-ttu-id="d3c7c-1371">amex</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1371">amex</span></span> 
- <span data-ttu-id="d3c7c-1372">atm card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1372">atm card</span></span> 
- <span data-ttu-id="d3c7c-1373">atm cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1373">atm cards</span></span> 
- <span data-ttu-id="d3c7c-1374">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1374">atm kaart</span></span> 
- <span data-ttu-id="d3c7c-1375">atmcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1375">atmcard</span></span> 
- <span data-ttu-id="d3c7c-1376">atmcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1376">atmcards</span></span> 
- <span data-ttu-id="d3c7c-1377">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1377">atmkaart</span></span> 
- <span data-ttu-id="d3c7c-1378">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1378">atmkaarten</span></span> 
- <span data-ttu-id="d3c7c-1379">bancontact
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1379">bancontact</span></span> 
- <span data-ttu-id="d3c7c-1380">bank card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1380">bank card</span></span> 
- <span data-ttu-id="d3c7c-1381">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1381">bankkaart</span></span> 
- <span data-ttu-id="d3c7c-1382">card holder
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1382">card holder</span></span> 
- <span data-ttu-id="d3c7c-1383">card holders
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1383">card holders</span></span> 
- <span data-ttu-id="d3c7c-1384">card num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1384">card num</span></span> 
- <span data-ttu-id="d3c7c-1385">card number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1385">card number</span></span> 
- <span data-ttu-id="d3c7c-1386">card numbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1386">card numbers</span></span> 
- <span data-ttu-id="d3c7c-1387">card type
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1387">card type</span></span> 
- <span data-ttu-id="d3c7c-1388">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1388">cardano numerico</span></span> 
- <span data-ttu-id="d3c7c-1389">cardholder
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1389">cardholder</span></span> 
- <span data-ttu-id="d3c7c-1390">cardholders
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1390">cardholders</span></span> 
- <span data-ttu-id="d3c7c-1391">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1391">cardnumber</span></span> 
- <span data-ttu-id="d3c7c-1392">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1392">cardnumbers</span></span> 
- <span data-ttu-id="d3c7c-1393">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1393">carta bianca</span></span> 
- <span data-ttu-id="d3c7c-1394">carta credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1394">carta credito</span></span> 
- <span data-ttu-id="d3c7c-1395">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1395">carta di credito</span></span> 
- <span data-ttu-id="d3c7c-1396">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1396">cartao de credito</span></span> 
- <span data-ttu-id="d3c7c-1397">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1397">cartao de crédito</span></span> 
- <span data-ttu-id="d3c7c-1398">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1398">cartao de debito</span></span> 
- <span data-ttu-id="d3c7c-1399">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1399">cartao de débito</span></span> 
- <span data-ttu-id="d3c7c-1400">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1400">carte bancaire</span></span> 
- <span data-ttu-id="d3c7c-1401">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1401">carte blanche</span></span> 
- <span data-ttu-id="d3c7c-1402">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1402">carte bleue</span></span> 
- <span data-ttu-id="d3c7c-1403">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1403">carte de credit</span></span> 
- <span data-ttu-id="d3c7c-1404">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1404">carte de crédit</span></span> 
- <span data-ttu-id="d3c7c-1405">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1405">carte di credito</span></span> 
- <span data-ttu-id="d3c7c-1406">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1406">carteblanche</span></span> 
- <span data-ttu-id="d3c7c-1407">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1407">cartão de credito</span></span> 
- <span data-ttu-id="d3c7c-1408">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1408">cartão de crédito</span></span> 
- <span data-ttu-id="d3c7c-1409">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1409">cartão de debito</span></span> 
- <span data-ttu-id="d3c7c-1410">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1410">cartão de débito</span></span> 
- <span data-ttu-id="d3c7c-1411">cb
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1411">cb</span></span> 
- <span data-ttu-id="d3c7c-1412">ccn
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1412">ccn</span></span> 
- <span data-ttu-id="d3c7c-1413">check card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1413">check card</span></span> 
- <span data-ttu-id="d3c7c-1414">check cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1414">check cards</span></span> 
- <span data-ttu-id="d3c7c-1415">checkcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1415">checkcard</span></span>
- <span data-ttu-id="d3c7c-1416">checkcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1416">checkcards</span></span> 
- <span data-ttu-id="d3c7c-1417">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1417">chequekaart</span></span> 
- <span data-ttu-id="d3c7c-1418">cirrus
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1418">cirrus</span></span> 
- <span data-ttu-id="d3c7c-1419">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1419">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="d3c7c-1420">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1420">controlekaart</span></span> 
- <span data-ttu-id="d3c7c-1421">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1421">controlekaarten</span></span> 
- <span data-ttu-id="d3c7c-1422">credit card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1422">credit card</span></span> 
- <span data-ttu-id="d3c7c-1423">credit cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1423">credit cards</span></span> 
- <span data-ttu-id="d3c7c-1424">creditcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1424">creditcard</span></span> 
- <span data-ttu-id="d3c7c-1425">creditcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1425">creditcards</span></span> 
- <span data-ttu-id="d3c7c-1426">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1426">debetkaart</span></span> 
- <span data-ttu-id="d3c7c-1427">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1427">debetkaarten</span></span> 
- <span data-ttu-id="d3c7c-1428">debit card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1428">debit card</span></span> 
- <span data-ttu-id="d3c7c-1429">debit cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1429">debit cards</span></span> 
- <span data-ttu-id="d3c7c-1430">debitcard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1430">debitcard</span></span> 
- <span data-ttu-id="d3c7c-1431">debitcards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1431">debitcards</span></span> 
- <span data-ttu-id="d3c7c-1432">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1432">debito automatico</span></span> 
- <span data-ttu-id="d3c7c-1433">diners club
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1433">diners club</span></span> 
- <span data-ttu-id="d3c7c-1434">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1434">dinersclub</span></span> 
- <span data-ttu-id="d3c7c-1435">探索</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1435">discover</span></span> 
- <span data-ttu-id="d3c7c-1436">discover card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1436">discover card</span></span> 
- <span data-ttu-id="d3c7c-1437">discover cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1437">discover cards</span></span> 
- <span data-ttu-id="d3c7c-1438">discovercard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1438">discovercard</span></span> 
- <span data-ttu-id="d3c7c-1439">discovercards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1439">discovercards</span></span> 
- <span data-ttu-id="d3c7c-1440">débito automático</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1440">débito automático</span></span>
- <span data-ttu-id="d3c7c-1441">
edc
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1441">edc</span></span> 
- <span data-ttu-id="d3c7c-1442">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1442">eigentümername</span></span> 
- <span data-ttu-id="d3c7c-1443">european debit card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1443">european debit card</span></span> 
- <span data-ttu-id="d3c7c-1444">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1444">hoofdkaart</span></span> 
- <span data-ttu-id="d3c7c-1445">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1445">hoofdkaarten</span></span> 
- <span data-ttu-id="d3c7c-1446">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1446">in viaggio</span></span> 
- <span data-ttu-id="d3c7c-1447">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1447">japanese card bureau</span></span> 
- <span data-ttu-id="d3c7c-1448">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1448">japanse kaartdienst</span></span> 
- <span data-ttu-id="d3c7c-1449">jcb
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1449">jcb</span></span> 
- <span data-ttu-id="d3c7c-1450">kaart
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1450">kaart</span></span> 
- <span data-ttu-id="d3c7c-1451">kaart num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1451">kaart num</span></span> 
- <span data-ttu-id="d3c7c-1452">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1452">kaartaantal</span></span> 
- <span data-ttu-id="d3c7c-1453">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1453">kaartaantallen</span></span> 
- <span data-ttu-id="d3c7c-1454">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1454">kaarthouder</span></span> 
- <span data-ttu-id="d3c7c-1455">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1455">kaarthouders</span></span> 
- <span data-ttu-id="d3c7c-1456">karte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1456">karte</span></span>  
- <span data-ttu-id="d3c7c-1457">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1457">karteninhaber</span></span> 
- <span data-ttu-id="d3c7c-1458">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1458">karteninhabers</span></span>
- <span data-ttu-id="d3c7c-1459">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1459">kartennr</span></span> 
- <span data-ttu-id="d3c7c-1460">kartennummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1460">kartennummer</span></span> 
- <span data-ttu-id="d3c7c-1461">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1461">kreditkarte</span></span> 
- <span data-ttu-id="d3c7c-1462">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1462">kreditkarten-nummer</span></span> 
- <span data-ttu-id="d3c7c-1463">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1463">kreditkarteninhaber</span></span> 
- <span data-ttu-id="d3c7c-1464">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1464">kreditkarteninstitut</span></span> 
- <span data-ttu-id="d3c7c-1465">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1465">kreditkartennummer</span></span> 
- <span data-ttu-id="d3c7c-1466">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1466">kreditkartentyp</span></span> 
- <span data-ttu-id="d3c7c-1467">maestro
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1467">maestro</span></span> 
- <span data-ttu-id="d3c7c-1468">master card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1468">master card</span></span> 
- <span data-ttu-id="d3c7c-1469">master cards
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1469">master cards</span></span> 
- <span data-ttu-id="d3c7c-1470">mastercard
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1470">mastercard</span></span> 
- <span data-ttu-id="d3c7c-1471">mastercards</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1471">mastercards</span></span> 
- <span data-ttu-id="d3c7c-1472">mc</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1472">mc</span></span> 
- <span data-ttu-id="d3c7c-1473">mister cash
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1473">mister cash</span></span> 
- <span data-ttu-id="d3c7c-1474">n carta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1474">n carta</span></span> 
- <span data-ttu-id="d3c7c-1475">carta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1475">carta</span></span> 
- <span data-ttu-id="d3c7c-1476">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1476">no de tarjeta</span></span> 
- <span data-ttu-id="d3c7c-1477">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1477">no do cartao</span></span> 
- <span data-ttu-id="d3c7c-1478">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1478">no do cartão</span></span> 
- <span data-ttu-id="d3c7c-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="d3c7c-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p118">no. do cartao</span></span> 
- <span data-ttu-id="d3c7c-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p119">no. do cartão</span></span> 
- <span data-ttu-id="d3c7c-1485">編號 carta</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1485">nr carta</span></span> 
- <span data-ttu-id="d3c7c-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p120">nr. carta</span></span> 
- <span data-ttu-id="d3c7c-1488">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1488">numeri di scheda</span></span> 
- <span data-ttu-id="d3c7c-1489">numero carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1489">numero carta</span></span> 
- <span data-ttu-id="d3c7c-1490">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1490">numero de cartao</span></span> 
- <span data-ttu-id="d3c7c-1491">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1491">numero de carte</span></span> 
- <span data-ttu-id="d3c7c-1492">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1492">numero de cartão</span></span> 
- <span data-ttu-id="d3c7c-1493">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1493">numero de tarjeta</span></span>
- <span data-ttu-id="d3c7c-1494">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1494">numero della carta</span></span> 
- <span data-ttu-id="d3c7c-1495">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1495">numero di carta</span></span> 
- <span data-ttu-id="d3c7c-1496">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1496">numero di scheda</span></span> 
- <span data-ttu-id="d3c7c-1497">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1497">numero do cartao</span></span> 
- <span data-ttu-id="d3c7c-1498">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1498">numero do cartão</span></span> 
- <span data-ttu-id="d3c7c-1499">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1499">numéro de carte</span></span> 
- <span data-ttu-id="d3c7c-1500">nº carta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1500">nº carta</span></span> 
- <span data-ttu-id="d3c7c-1501">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1501">nº de carte</span></span> 
- <span data-ttu-id="d3c7c-1502">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1502">nº de la carte</span></span> 
- <span data-ttu-id="d3c7c-1503">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1503">nº de tarjeta</span></span> 
- <span data-ttu-id="d3c7c-1504">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1504">nº do cartao</span></span> 
- <span data-ttu-id="d3c7c-1505">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1505">nº do cartão</span></span> 
- <span data-ttu-id="d3c7c-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p121">nº. do cartão</span></span> 
- <span data-ttu-id="d3c7c-1508">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1508">número de cartao</span></span> 
- <span data-ttu-id="d3c7c-1509">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1509">número de cartão</span></span> 
- <span data-ttu-id="d3c7c-1510">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1510">número de tarjeta</span></span> 
- <span data-ttu-id="d3c7c-1511">número do cartao</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1511">número do cartao</span></span> 
- <span data-ttu-id="d3c7c-1512">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1512">scheda dell'assegno</span></span> 
- <span data-ttu-id="d3c7c-1513">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1513">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="d3c7c-1514">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1514">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="d3c7c-1515">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1515">scheda della banca</span></span> 
- <span data-ttu-id="d3c7c-1516">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1516">scheda di controllo</span></span> 
- <span data-ttu-id="d3c7c-1517">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1517">scheda di debito</span></span> 
- <span data-ttu-id="d3c7c-1518">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1518">scheda matrice</span></span> 
- <span data-ttu-id="d3c7c-1519">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1519">schede dell'atmosfera</span></span> 
- <span data-ttu-id="d3c7c-1520">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1520">schede di controllo</span></span> 
- <span data-ttu-id="d3c7c-1521">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1521">schede di debito</span></span> 
- <span data-ttu-id="d3c7c-1522">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1522">schede matrici</span></span> 
- <span data-ttu-id="d3c7c-1523">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1523">scoprono la scheda</span></span> 
- <span data-ttu-id="d3c7c-1524">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1524">scoprono le schede</span></span> 
- <span data-ttu-id="d3c7c-1525">solo
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1525">solo</span></span> 
- <span data-ttu-id="d3c7c-1526">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1526">supporti di scheda</span></span> 
- <span data-ttu-id="d3c7c-1527">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1527">supporto di scheda</span></span> 
- <span data-ttu-id="d3c7c-1528">參數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1528">switch</span></span> 
- <span data-ttu-id="d3c7c-1529">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1529">tarjeta atm</span></span> 
- <span data-ttu-id="d3c7c-1530">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1530">tarjeta credito</span></span> 
- <span data-ttu-id="d3c7c-1531">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1531">tarjeta de atm</span></span> 
- <span data-ttu-id="d3c7c-1532">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1532">tarjeta de credito</span></span> 
- <span data-ttu-id="d3c7c-1533">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1533">tarjeta de debito</span></span> 
- <span data-ttu-id="d3c7c-1534">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1534">tarjeta debito</span></span> 
- <span data-ttu-id="d3c7c-1535">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1535">tarjeta no</span></span>
- <span data-ttu-id="d3c7c-1536">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1536">tarjetahabiente</span></span> 
- <span data-ttu-id="d3c7c-1537">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1537">tipo della scheda</span></span> 
- <span data-ttu-id="d3c7c-1538">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1538">ufficio giapponese della</span></span> 
- <span data-ttu-id="d3c7c-1539">scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1539">scheda</span></span> 
- <span data-ttu-id="d3c7c-1540">v pay
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1540">v pay</span></span> 
- <span data-ttu-id="d3c7c-1541">v 工資</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1541">v-pay</span></span> 
- <span data-ttu-id="d3c7c-1542">visa
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1542">visa</span></span> 
- <span data-ttu-id="d3c7c-1543">visa plus
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1543">visa plus</span></span> 
- <span data-ttu-id="d3c7c-1544">visa electron
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1544">visa electron</span></span> 
- <span data-ttu-id="d3c7c-1545">visto
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1545">visto</span></span> 
- <span data-ttu-id="d3c7c-1546">visum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1546">visum</span></span> 
- <span data-ttu-id="d3c7c-1547">vpay
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1547">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="d3c7c-1548">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1548">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="d3c7c-1549">card identification number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1549">card identification number</span></span>
- <span data-ttu-id="d3c7c-1550">card verification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1550">card verification</span></span> 
- <span data-ttu-id="d3c7c-1551">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1551">cardi la verifica</span></span> 
- <span data-ttu-id="d3c7c-1552">cid
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1552">cid</span></span> 
- <span data-ttu-id="d3c7c-1553">cod seg</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1553">cod seg</span></span> 
- <span data-ttu-id="d3c7c-1554">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1554">cod seguranca</span></span> 
- <span data-ttu-id="d3c7c-1555">cod segurança</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1555">cod segurança</span></span> 
- <span data-ttu-id="d3c7c-1556">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1556">cod sicurezza</span></span> 
- <span data-ttu-id="d3c7c-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p122">cod. seg</span></span> 
- <span data-ttu-id="d3c7c-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p123">cod. seguranca</span></span> 
- <span data-ttu-id="d3c7c-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p124">cod. segurança</span></span> 
- <span data-ttu-id="d3c7c-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="d3c7c-1565">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1565">codice di sicurezza</span></span> 
- <span data-ttu-id="d3c7c-1566">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1566">codice di verifica</span></span> 
- <span data-ttu-id="d3c7c-1567">codigo
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1567">codigo</span></span> 
- <span data-ttu-id="d3c7c-1568">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1568">codigo de seguranca</span></span> 
- <span data-ttu-id="d3c7c-1569">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1569">codigo de segurança</span></span> 
- <span data-ttu-id="d3c7c-1570">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1570">crittogramma</span></span> 
- <span data-ttu-id="d3c7c-1571">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1571">cryptogram</span></span> 
- <span data-ttu-id="d3c7c-1572">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1572">cryptogramme</span></span> 
- <span data-ttu-id="d3c7c-1573">cv2</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1573">cv2</span></span> 
- <span data-ttu-id="d3c7c-1574">cvc
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1574">cvc</span></span> 
- <span data-ttu-id="d3c7c-1575">cvc2</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1575">cvc2</span></span> 
- <span data-ttu-id="d3c7c-1576">cvn
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1576">cvn</span></span> 
- <span data-ttu-id="d3c7c-1577">cvv
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1577">cvv</span></span> 
- <span data-ttu-id="d3c7c-1578">cvv2</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1578">cvv2</span></span> 
- <span data-ttu-id="d3c7c-1579">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1579">cód seguranca</span></span> 
- <span data-ttu-id="d3c7c-1580">cód segurança</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1580">cód segurança</span></span> 
- <span data-ttu-id="d3c7c-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p126">cód. seguranca</span></span> 
- <span data-ttu-id="d3c7c-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p127">cód. segurança</span></span> 
- <span data-ttu-id="d3c7c-1585">código
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1585">código</span></span> 
- <span data-ttu-id="d3c7c-1586">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1586">código de seguranca</span></span> 
- <span data-ttu-id="d3c7c-1587">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1587">código de segurança</span></span> 
- <span data-ttu-id="d3c7c-1588">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1588">de kaart controle</span></span> 
- <span data-ttu-id="d3c7c-1589">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1589">geeft nr uit</span></span> 
- <span data-ttu-id="d3c7c-1590">issue no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1590">issue no</span></span> 
- <span data-ttu-id="d3c7c-1591">issue number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1591">issue number</span></span> 
- <span data-ttu-id="d3c7c-1592">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1592">kaartidentificatienummer</span></span> 
- <span data-ttu-id="d3c7c-1593">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1593">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="d3c7c-1594">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1594">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="d3c7c-1595">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1595">kwestieaantal</span></span> 
- <span data-ttu-id="d3c7c-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="d3c7c-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="d3c7c-1600">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1600">numero de securite</span></span> 
- <span data-ttu-id="d3c7c-1601">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1601">numero de verificacao</span></span> 
- <span data-ttu-id="d3c7c-1602">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1602">numero dell'edizione</span></span> 
- <span data-ttu-id="d3c7c-1603">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1603">numero di identificazione della</span></span> 
- <span data-ttu-id="d3c7c-1604">scheda
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1604">scheda</span></span> 
- <span data-ttu-id="d3c7c-1605">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1605">numero di sicurezza</span></span> 
- <span data-ttu-id="d3c7c-1606">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1606">numero van veiligheid</span></span> 
- <span data-ttu-id="d3c7c-1607">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1607">numéro de sécurité</span></span> 
- <span data-ttu-id="d3c7c-1608">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1608">nº autorizzazione</span></span> 
- <span data-ttu-id="d3c7c-1609">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1609">número de verificação</span></span> 
- <span data-ttu-id="d3c7c-1610">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1610">perno il blocco</span></span> 
- <span data-ttu-id="d3c7c-1611">pin block
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1611">pin block</span></span> 
- <span data-ttu-id="d3c7c-1612">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1612">prufziffer</span></span> 
- <span data-ttu-id="d3c7c-1613">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1613">prüfziffer</span></span> 
- <span data-ttu-id="d3c7c-1614">security code
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1614">security code</span></span> 
- <span data-ttu-id="d3c7c-1615">security no
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1615">security no</span></span> 
- <span data-ttu-id="d3c7c-1616">security number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1616">security number</span></span> 
- <span data-ttu-id="d3c7c-1617">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1617">sicherheits kode</span></span> 
- <span data-ttu-id="d3c7c-1618">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1618">sicherheitscode</span></span> 
- <span data-ttu-id="d3c7c-1619">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1619">sicherheitsnummer</span></span> 
- <span data-ttu-id="d3c7c-1620">speldblok
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1620">speldblok</span></span> 
- <span data-ttu-id="d3c7c-1621">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1621">veiligheid nr</span></span> 
- <span data-ttu-id="d3c7c-1622">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1622">veiligheidsaantal</span></span> 
- <span data-ttu-id="d3c7c-1623">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1623">veiligheidscode</span></span> 
- <span data-ttu-id="d3c7c-1624">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1624">veiligheidsnummer</span></span> 
- <span data-ttu-id="d3c7c-1625">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1625">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="d3c7c-1626">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1626">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="d3c7c-1627">ablauf
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1627">ablauf</span></span> 
- <span data-ttu-id="d3c7c-1628">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1628">data de expiracao</span></span> 
- <span data-ttu-id="d3c7c-1629">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1629">data de expiração</span></span> 
- <span data-ttu-id="d3c7c-1630">data del exp
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1630">data del exp</span></span> 
- <span data-ttu-id="d3c7c-1631">data di exp
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1631">data di exp</span></span> 
- <span data-ttu-id="d3c7c-1632">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1632">data di scadenza</span></span> 
- <span data-ttu-id="d3c7c-1633">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1633">data em que expira</span></span> 
- <span data-ttu-id="d3c7c-1634">data scad
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1634">data scad</span></span> 
- <span data-ttu-id="d3c7c-1635">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1635">data scadenza</span></span> 
- <span data-ttu-id="d3c7c-1636">date de validité
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1636">date de validité</span></span> 
- <span data-ttu-id="d3c7c-1637">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1637">datum afloop</span></span> 
- <span data-ttu-id="d3c7c-1638">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1638">datum van exp</span></span> 
- <span data-ttu-id="d3c7c-1639">de afloop
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1639">de afloop</span></span> 
- <span data-ttu-id="d3c7c-1640">espira
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1640">espira</span></span> 
- <span data-ttu-id="d3c7c-1641">espira
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1641">espira</span></span> 
- <span data-ttu-id="d3c7c-1642">exp date
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1642">exp date</span></span> 
- <span data-ttu-id="d3c7c-1643">exp datum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1643">exp datum</span></span> 
- <span data-ttu-id="d3c7c-1644">到期日</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1644">expiration</span></span> 
- <span data-ttu-id="d3c7c-1645">expire
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1645">expire</span></span> 
- <span data-ttu-id="d3c7c-1646">expires
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1646">expires</span></span> 
- <span data-ttu-id="d3c7c-1647">expiry
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1647">expiry</span></span> 
- <span data-ttu-id="d3c7c-1648">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1648">fecha de expiracion</span></span> 
- <span data-ttu-id="d3c7c-1649">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1649">fecha de venc</span></span> 
- <span data-ttu-id="d3c7c-1650">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1650">gultig bis</span></span> 
- <span data-ttu-id="d3c7c-1651">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1651">gultigkeitsdatum</span></span> 
- <span data-ttu-id="d3c7c-1652">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1652">gültig bis</span></span> 
- <span data-ttu-id="d3c7c-1653">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1653">gültigkeitsdatum</span></span> 
- <span data-ttu-id="d3c7c-1654">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1654">la scadenza</span></span> 
- <span data-ttu-id="d3c7c-1655">scadenza
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1655">scadenza</span></span> 
- <span data-ttu-id="d3c7c-1656">valable
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1656">valable</span></span> 
- <span data-ttu-id="d3c7c-1657">validade
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1657">validade</span></span> 
- <span data-ttu-id="d3c7c-1658">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1658">valido hasta</span></span> 
- <span data-ttu-id="d3c7c-1659">valor
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1659">valor</span></span> 
- <span data-ttu-id="d3c7c-1660">venc
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1660">venc</span></span> 
- <span data-ttu-id="d3c7c-1661">vencimento
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1661">vencimento</span></span> 
- <span data-ttu-id="d3c7c-1662">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1662">vencimiento</span></span> 
- <span data-ttu-id="d3c7c-1663">verloopt
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1663">verloopt</span></span> 
- <span data-ttu-id="d3c7c-1664">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1664">vervaldag</span></span> 
- <span data-ttu-id="d3c7c-1665">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1665">vervaldatum</span></span> 
- <span data-ttu-id="d3c7c-1666">vto
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1666">vto</span></span> 
- <span data-ttu-id="d3c7c-1667">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1667">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="d3c7c-1668">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1668">EU Driver's License Number</span></span>

<span data-ttu-id="d3c7c-1669">若要深入了解，請參閱[歐盟駕照編號敏感資訊類型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1669">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="d3c7c-1670">歐盟國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1670">EU National Identification Number</span></span>

<span data-ttu-id="d3c7c-1671">若要深入了解，請參閱[國家識別碼歐盟敏感資訊類型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1671">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="d3c7c-1672">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1672">EU Passport Number</span></span>

<span data-ttu-id="d3c7c-1673">若要深入了解，請參閱[歐盟護照號碼敏感資訊類型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1673">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="d3c7c-1674">歐盟社會安全號碼或對等資格識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1674">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="d3c7c-1675">如需了解，請參閱[歐盟社會安全號碼或對等識別碼敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1675">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="d3c7c-1676">歐盟稅識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1676">EU Tax Identification Number</span></span>

<span data-ttu-id="d3c7c-1677">若要深入了解，請參閱[歐盟稅識別碼敏感資訊類型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1677">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="d3c7c-1678">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1678">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1679">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1679">Format</span></span>

<span data-ttu-id="d3c7c-1680">六位數加上一個指出世紀的字元，再加上三位數和一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1680">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1681">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1681">Pattern</span></span>

<span data-ttu-id="d3c7c-1682">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1682">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d3c7c-1683">六位數的格式為 DDMMYY，此為出生日期</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1683">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="d3c7c-1684">世紀標記 ('-'、'+' 或 'a')</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1684">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="d3c7c-1685">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1685">Three-digit personal identification number</span></span> 
- <span data-ttu-id="d3c7c-1686">一個做為檢查碼的數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1686">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1687">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1687">Checksum</span></span>

<span data-ttu-id="d3c7c-1688">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1688">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1689">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1689">Definition</span></span>

<span data-ttu-id="d3c7c-1690">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1690">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1691">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1691">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1692">找到來自於 Keyword_finnish_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1692">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="d3c7c-1693">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1693">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1694">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1694">Keywords</span></span>

- <span data-ttu-id="d3c7c-1695">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1695">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="d3c7c-1696">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1696">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="d3c7c-1697">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1697">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="d3c7c-1698">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1698">Personbeteckning</span></span>
- <span data-ttu-id="d3c7c-1699">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1699">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="d3c7c-1700">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1700">Finland Passport Number</span></span>

<span data-ttu-id="d3c7c-p130">格式化九個字母和數字模式組合的九個字母和數字的組合： 兩個字母 （不區分大小寫） 七位數總和檢查碼沒有定義 DLP 原則是 75%健全的如果它是已偵測這種敏感資訊類型、 兩者之間300 個字元的鄰近： 規則運算式 Regex_finland_passport_number 會找出符合模式的內容。從 Keyword_finland_passport_number 關鍵字是找到。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
</Entity>關鍵字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="d3c7c-1705">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1705">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1706">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1706">Format</span></span>

<span data-ttu-id="d3c7c-1707">12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1707">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1708">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1708">Pattern</span></span>

<span data-ttu-id="d3c7c-1709">可驗證以忽略類似模式 (例如法國電話號碼) 的 12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1709">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1710">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1710">Checksum</span></span>

<span data-ttu-id="d3c7c-1711">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1711">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1712">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1712">Definition</span></span>

<span data-ttu-id="d3c7c-1713">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1713">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1714">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1714">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1715">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1715">At least one of the following is true:</span></span>
- <span data-ttu-id="d3c7c-1716">找到來自於 Keyword_french_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1716">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="d3c7c-1717">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1717">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1718">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1718">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="d3c7c-1719">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1719">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="d3c7c-1720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1720">drivers licence</span></span>
- <span data-ttu-id="d3c7c-1721">
drivers license</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1721">drivers license</span></span>
- <span data-ttu-id="d3c7c-1722">driving licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1722">driving licence</span></span>
- <span data-ttu-id="d3c7c-1723">主導授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1723">driving license</span></span>
- <span data-ttu-id="d3c7c-1724">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1724">permis de conduire</span></span>
- <span data-ttu-id="d3c7c-1725">
licence number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1725">licence number</span></span>
- <span data-ttu-id="d3c7c-1726">
license number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1726">license number</span></span>
- <span data-ttu-id="d3c7c-1727">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1727">licence numbers</span></span>
- <span data-ttu-id="d3c7c-1728">

license numbers</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1728">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="d3c7c-1729">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1729">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1730">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1730">Format</span></span>

<span data-ttu-id="d3c7c-1731">12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1731">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1732">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1732">Pattern</span></span>

<span data-ttu-id="d3c7c-1733">12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1733">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1734">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1734">Checksum</span></span>

<span data-ttu-id="d3c7c-1735">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1735">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1736">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1736">Definition</span></span>

<span data-ttu-id="d3c7c-1737">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1737">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1738">規則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1738">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1739">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1739">Keywords</span></span>

<span data-ttu-id="d3c7c-1740">無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1740">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="d3c7c-1741">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1741">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1742">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1742">Format</span></span>

<span data-ttu-id="d3c7c-1743">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1743">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1744">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1744">Pattern</span></span>

<span data-ttu-id="d3c7c-1745">九個數字和字母：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1745">Nine digits and letters:</span></span>
- <span data-ttu-id="d3c7c-1746">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1746">Two digits</span></span> 
- <span data-ttu-id="d3c7c-1747">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1747">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-1748">五位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1748">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1749">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1749">Checksum</span></span>

<span data-ttu-id="d3c7c-1750">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1750">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1751">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1751">Definition</span></span>

<span data-ttu-id="d3c7c-1752">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1752">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1753">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1753">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1754">找到來自於 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1754">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1755">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1755">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="d3c7c-1756">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1756">Keyword_passport</span></span>

- <span data-ttu-id="d3c7c-1757">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1757">Passport Number</span></span>
- <span data-ttu-id="d3c7c-1758">
Passport No</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1758">Passport No</span></span>
- <span data-ttu-id="d3c7c-1759">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1759">Passport #</span></span>
- <span data-ttu-id="d3c7c-1760">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1760">Passport#</span></span>
- <span data-ttu-id="d3c7c-1761">PassportID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1761">PassportID</span></span>
- <span data-ttu-id="d3c7c-1762">Passportno
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1762">Passportno</span></span>
- <span data-ttu-id="d3c7c-1763">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1763">passportnumber</span></span>
- <span data-ttu-id="d3c7c-1764">パスポート</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1764">パスポート</span></span>
- <span data-ttu-id="d3c7c-1765">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1765">パスポート番号</span></span>
- <span data-ttu-id="d3c7c-1766">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1766">パスポートのNum</span></span>
- <span data-ttu-id="d3c7c-1767">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1767">パスポート ＃</span></span> 
- <span data-ttu-id="d3c7c-1768">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1768">Numéro de passeport</span></span>
- <span data-ttu-id="d3c7c-1769">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1769">Passeport n °</span></span>
- <span data-ttu-id="d3c7c-1770">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1770">Passeport Non</span></span>
- <span data-ttu-id="d3c7c-1771">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1771">Passeport #</span></span>
- <span data-ttu-id="d3c7c-1772">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1772">Passeport#</span></span>
- <span data-ttu-id="d3c7c-1773">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1773">PasseportNon</span></span>
- <span data-ttu-id="d3c7c-1774">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1774">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="d3c7c-1775">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1775">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1776">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1776">Format</span></span>

<span data-ttu-id="d3c7c-1777">15 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1777">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1778">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1778">Pattern</span></span>

<span data-ttu-id="d3c7c-1779">必須符合兩個模式之一：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1779">Must match one of two patterns:</span></span>
- <span data-ttu-id="d3c7c-1780">後面接著空格後面接著兩個位數字的數字 13</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1780">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="d3c7c-1781">或</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1781">or</span></span>
- <span data-ttu-id="d3c7c-1782">15 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1782">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1783">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1783">Checksum</span></span>

<span data-ttu-id="d3c7c-1784">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1784">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1785">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1785">Definition</span></span>

<span data-ttu-id="d3c7c-1786">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1786">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1787">Func_french_insee 或 Func_fr_insee 函數會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1787">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1788">找到來自於 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1788">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="d3c7c-1789">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1789">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-1790">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1790">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1791">Func_french_insee 或 Func_fr_insee 函數會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1791">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1792">找不到來自於 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1792">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="d3c7c-1793">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1793">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1794">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1794">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="d3c7c-1795">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1795">Keyword_fr_insee</span></span>

- <span data-ttu-id="d3c7c-1796">insee</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1796">insee</span></span>
- <span data-ttu-id="d3c7c-1797">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1797">securité sociale</span></span>
- <span data-ttu-id="d3c7c-1798">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1798">securite sociale</span></span>
- <span data-ttu-id="d3c7c-1799">
national id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1799">national id</span></span>
- <span data-ttu-id="d3c7c-1800">
national identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1800">national identification</span></span>
- <span data-ttu-id="d3c7c-1801">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1801">numéro d'identité</span></span>
- <span data-ttu-id="d3c7c-1802">沒有 d'identité</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1802">no d'identité</span></span>
- <span data-ttu-id="d3c7c-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p131">no. d'identité</span></span>
- <span data-ttu-id="d3c7c-1805">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1805">numero d'identite</span></span>
- <span data-ttu-id="d3c7c-1806">沒有 d'identite</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1806">no d'identite</span></span>
- <span data-ttu-id="d3c7c-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p132">no. d'identite</span></span>
- <span data-ttu-id="d3c7c-1809">social security number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1809">social security number</span></span>
- <span data-ttu-id="d3c7c-1810">
social security code</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1810">social security code</span></span>
- <span data-ttu-id="d3c7c-1811">social insurance number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1811">social insurance number</span></span>
- <span data-ttu-id="d3c7c-1812">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1812">le numéro d'identification nationale</span></span>
- <span data-ttu-id="d3c7c-1813">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1813">d'identité nationale</span></span>
- <span data-ttu-id="d3c7c-1814">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1814">numéro de sécurité sociale</span></span>
- <span data-ttu-id="d3c7c-1815">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1815">le code de la sécurité sociale</span></span>
- <span data-ttu-id="d3c7c-1816">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1816">numéro d'assurance sociale</span></span>
- <span data-ttu-id="d3c7c-1817">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1817">numéro de sécu</span></span>
- <span data-ttu-id="d3c7c-1818">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1818">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="d3c7c-1819">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1819">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1820">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1820">Format</span></span>

<span data-ttu-id="d3c7c-1821">11 個數字和字母的組合</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1821">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1822">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1822">Pattern</span></span>

<span data-ttu-id="d3c7c-1823">11 個數字和字母 (不區分大小寫)：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1823">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="d3c7c-1824">一個數字或字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1824">A digit or letter</span></span> 
- <span data-ttu-id="d3c7c-1825">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1825">Two digits</span></span> 
- <span data-ttu-id="d3c7c-1826">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1826">Six digits or letters</span></span> 
- <span data-ttu-id="d3c7c-1827">一個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1827">A digit</span></span> 
- <span data-ttu-id="d3c7c-1828">一個數字或字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1828">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1829">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1829">Checksum</span></span>

<span data-ttu-id="d3c7c-1830">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1830">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1831">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1831">Definition</span></span>

<span data-ttu-id="d3c7c-1832">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1833">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1833">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1834">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1834">At least one of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-1835">找到來自於 Keyword_german_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1835">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="d3c7c-1836">找到來自於 Keyword_german_drivers_license_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1836">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="d3c7c-1837">找到來自於 Keyword_german_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1837">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="d3c7c-1838">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1838">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1839">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1839">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="d3c7c-1840">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1840">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="d3c7c-1841">Führerschein</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1841">Führerschein</span></span>
- <span data-ttu-id="d3c7c-1842">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1842">Fuhrerschein</span></span>
- <span data-ttu-id="d3c7c-1843">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1843">Fuehrerschein</span></span>
- <span data-ttu-id="d3c7c-1844">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1844">Führerscheinnummer</span></span>
- <span data-ttu-id="d3c7c-1845">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1845">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="d3c7c-1846">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1846">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="d3c7c-1847">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1847">Führerschein-</span></span> 
- <span data-ttu-id="d3c7c-1848">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1848">Fuhrerschein-</span></span> 
- <span data-ttu-id="d3c7c-1849">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1849">Fuehrerschein-</span></span> 
- <span data-ttu-id="d3c7c-1850">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1850">FührerscheinnummerNr</span></span>
- <span data-ttu-id="d3c7c-1851">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1851">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="d3c7c-1852">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1852">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="d3c7c-1853">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1853">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="d3c7c-1854">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1854">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="d3c7c-1855">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1855">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="d3c7c-1856">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1856">Führerschein- Nr</span></span>
- <span data-ttu-id="d3c7c-1857">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1857">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="d3c7c-1858">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1858">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="d3c7c-1859">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1859">Führerschein- Klasse</span></span> 
- <span data-ttu-id="d3c7c-1860">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1860">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="d3c7c-1861">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1861">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="d3c7c-1862">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1862">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="d3c7c-1863">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1863">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="d3c7c-1864">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1864">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="d3c7c-1865">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1865">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d3c7c-1866">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1866">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d3c7c-1867">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1867">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d3c7c-1868">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1868">Führerschein- Nr</span></span> 
- <span data-ttu-id="d3c7c-1869">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1869">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="d3c7c-1870">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1870">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="d3c7c-1871">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1871">Führerschein- Klasse</span></span> 
- <span data-ttu-id="d3c7c-1872">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1872">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="d3c7c-1873">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1873">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="d3c7c-1874">DL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1874">DL</span></span> 
- <span data-ttu-id="d3c7c-1875">DLS</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1875">DLS</span></span>
- <span data-ttu-id="d3c7c-1876">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1876">Driv Lic</span></span> 
- <span data-ttu-id="d3c7c-1877">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1877">Driv Licen</span></span> 
- <span data-ttu-id="d3c7c-1878">Driv License</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1878">Driv License</span></span>
- <span data-ttu-id="d3c7c-1879">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1879">Driv Licenses</span></span> 
- <span data-ttu-id="d3c7c-1880">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1880">Driv Licence</span></span> 
- <span data-ttu-id="d3c7c-1881">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1881">Driv Licences</span></span> 
- <span data-ttu-id="d3c7c-1882">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1882">Driv Lic</span></span> 
- <span data-ttu-id="d3c7c-1883">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1883">Driver Licen</span></span> 
- <span data-ttu-id="d3c7c-1884">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1884">Driver License</span></span> 
- <span data-ttu-id="d3c7c-1885">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1885">Driver Licenses</span></span> 
- <span data-ttu-id="d3c7c-1886">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1886">Driver Licence</span></span> 
- <span data-ttu-id="d3c7c-1887">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1887">Driver Licences</span></span> 
- <span data-ttu-id="d3c7c-1888">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1888">Drivers Lic</span></span> 
- <span data-ttu-id="d3c7c-1889">發行的驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1889">Drivers Licen</span></span> 
- <span data-ttu-id="d3c7c-1890">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1890">Drivers License</span></span> 
- <span data-ttu-id="d3c7c-1891">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1891">Drivers Licenses</span></span> 
- <span data-ttu-id="d3c7c-1892">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1892">Drivers Licence</span></span> 
- <span data-ttu-id="d3c7c-1893">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1893">Drivers Licences</span></span> 
- <span data-ttu-id="d3c7c-1894">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1894">Driver's Lic</span></span> 
- <span data-ttu-id="d3c7c-1895">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1895">Driver's Licen</span></span> 
- <span data-ttu-id="d3c7c-1896">駕照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1896">Driver's License</span></span> 
- <span data-ttu-id="d3c7c-1897">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1897">Driver's Licenses</span></span> 
- <span data-ttu-id="d3c7c-1898">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1898">Driver's Licence</span></span> 
- <span data-ttu-id="d3c7c-1899">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1899">Driver's Licences</span></span> 
- <span data-ttu-id="d3c7c-1900">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1900">Driving Lic</span></span> 
- <span data-ttu-id="d3c7c-1901">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1901">Driving Licen</span></span> 
- <span data-ttu-id="d3c7c-1902">Driving License
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1902">Driving License</span></span> 
- <span data-ttu-id="d3c7c-1903">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1903">Driving Licenses</span></span> 
- <span data-ttu-id="d3c7c-1904">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1904">Driving Licence</span></span> 
- <span data-ttu-id="d3c7c-1905">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1905">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="d3c7c-1906">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1906">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="d3c7c-1907">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1907">Nr-Führerschein</span></span> 
- <span data-ttu-id="d3c7c-1908">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1908">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="d3c7c-1909">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1909">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="d3c7c-1910">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1910">No-Führerschein</span></span> 
- <span data-ttu-id="d3c7c-1911">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1911">No-Fuhrerschein</span></span> 
- <span data-ttu-id="d3c7c-1912">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1912">No-Fuehrerschein</span></span> 
- <span data-ttu-id="d3c7c-1913">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1913">N-Führerschein</span></span> 
- <span data-ttu-id="d3c7c-1914">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1914">N-Fuhrerschein</span></span> 
- <span data-ttu-id="d3c7c-1915">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1915">N-Fuehrerschein</span></span>
- <span data-ttu-id="d3c7c-1916">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1916">Nr-Führerschein</span></span> 
- <span data-ttu-id="d3c7c-1917">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1917">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="d3c7c-1918">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1918">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="d3c7c-1919">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1919">No-Führerschein</span></span> 
- <span data-ttu-id="d3c7c-1920">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1920">No-Fuhrerschein</span></span> 
- <span data-ttu-id="d3c7c-1921">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1921">No-Fuehrerschein</span></span> 
- <span data-ttu-id="d3c7c-1922">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1922">N-Führerschein</span></span> 
- <span data-ttu-id="d3c7c-1923">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1923">N-Fuhrerschein</span></span> 
- <span data-ttu-id="d3c7c-1924">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1924">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="d3c7c-1925">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1925">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="d3c7c-1926">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1926">ausstellungsdatum</span></span>
- <span data-ttu-id="d3c7c-1927">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1927">ausstellungsort</span></span>
- <span data-ttu-id="d3c7c-1928">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1928">ausstellende behöde</span></span>
- <span data-ttu-id="d3c7c-1929">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1929">ausstellende behorde</span></span>
- <span data-ttu-id="d3c7c-1930">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1930">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="d3c7c-1931">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1931">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1932">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1932">Format</span></span>

<span data-ttu-id="d3c7c-1933">10 個數字或字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1933">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1934">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1934">Pattern</span></span>

<span data-ttu-id="d3c7c-1935">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1935">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d3c7c-1936">第一個字元是一個數字或 C、F、G、H、J、K 之中的一個字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1936">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="d3c7c-1937">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1937">Three digits</span></span> 
- <span data-ttu-id="d3c7c-1938">5 個數字或 C、H、J-N、P、R、T、V-Z 之中的字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1938">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="d3c7c-1939">一個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1939">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1940">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1940">Checksum</span></span>

<span data-ttu-id="d3c7c-1941">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1941">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1942">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1942">Definition</span></span>

<span data-ttu-id="d3c7c-1943">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1943">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1944">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1944">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1945">找到五個關鍵字清單任一者中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1945">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="d3c7c-1946">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1946">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-1947">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1947">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1948">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1948">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1949">找到五個關鍵字清單任一者中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1949">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="d3c7c-1950">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1950">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-1951">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1951">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="d3c7c-1952">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1952">Keyword_german_passport</span></span>

- <span data-ttu-id="d3c7c-1953">reisepass</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1953">reisepass</span></span>
- <span data-ttu-id="d3c7c-1954">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1954">reisepasse</span></span>
- <span data-ttu-id="d3c7c-1955">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1955">reisepassnummer</span></span>
- <span data-ttu-id="d3c7c-1956">passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1956">passport</span></span>
- <span data-ttu-id="d3c7c-1957">

passports</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1957">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="d3c7c-1958">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1958">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="d3c7c-1959">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1959">geburtsdatum</span></span>
- <span data-ttu-id="d3c7c-1960">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1960">ausstellungsdatum</span></span>
- <span data-ttu-id="d3c7c-1961">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1961">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="d3c7c-1962">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1962">Keyword_german_passport_number</span></span>

<span data-ttu-id="d3c7c-1963">否-Reisepass 編號 Reisepass</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1963">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="d3c7c-1964">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1964">Keyword_german_passport1</span></span>

<span data-ttu-id="d3c7c-1965">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1965">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="d3c7c-1966">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1966">Keyword_german_passport2</span></span>

<span data-ttu-id="d3c7c-1967">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1967">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="d3c7c-1968">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1968">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1969">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1969">Format</span></span>

<span data-ttu-id="d3c7c-1970">1 年 11 月 2010年自： 九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1970">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="d3c7c-1971">從 1 年 4 月 1987 直到 31 年 10 月 2010年: 10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1971">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1972">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1972">Pattern</span></span>

<span data-ttu-id="d3c7c-1973">自從 2010 年 11 月 1 日：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1973">Since 1 November 2010:</span></span>
- <span data-ttu-id="d3c7c-1974">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1974">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-1975">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1975">Eight digits</span></span>

<span data-ttu-id="d3c7c-1976">從 1 年 4 月 1987 31 年 10 月 2010年之前：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1976">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="d3c7c-1977">10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1977">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-1978">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1978">Checksum</span></span>

<span data-ttu-id="d3c7c-1979">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1979">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-1980">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1980">Definition</span></span>

<span data-ttu-id="d3c7c-1981">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1981">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-1982">規則運算式 Regex_germany_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1982">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-1983">從 Keyword_germany_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1983">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-1984">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1984">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="d3c7c-1985">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1985">Keyword_germany_id_card</span></span>

- <span data-ttu-id="d3c7c-1986">Identity Card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1986">Identity Card</span></span>
- <span data-ttu-id="d3c7c-1987">ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1987">ID</span></span>
- <span data-ttu-id="d3c7c-1988">Identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1988">Identification</span></span>
- <span data-ttu-id="d3c7c-1989">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1989">Personalausweis</span></span>
- <span data-ttu-id="d3c7c-1990">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1990">Identifizierungsnummer</span></span>
- <span data-ttu-id="d3c7c-1991">Ausweis</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1991">Ausweis</span></span>
- <span data-ttu-id="d3c7c-1992">Identifikation</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1992">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="d3c7c-1993">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1993">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-1994">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1994">Format</span></span>

<span data-ttu-id="d3c7c-1995">7-8 個字母和數字加上破折號的組合</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1995">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-1996">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1996">Pattern</span></span>

<span data-ttu-id="d3c7c-1997">七個字母和數字 (舊格式)︰</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1997">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="d3c7c-1998">一個字母 (希臘文字母的任何字母) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-1998">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="d3c7c-1999">一個破折號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-1999">A dash</span></span> 
- <span data-ttu-id="d3c7c-2000">六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2000">Six digits</span></span>

<span data-ttu-id="d3c7c-2001">八個字母和數字 (新格式)︰</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2001">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="d3c7c-2002">在希臘文與拉丁文字母中皆有大寫形態的兩個字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2002">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="d3c7c-2003">一個破折號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2003">A dash</span></span> 
- <span data-ttu-id="d3c7c-2004">六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2004">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2005">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2005">Checksum</span></span>

<span data-ttu-id="d3c7c-2006">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2006">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2007">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2007">Definition</span></span>

<span data-ttu-id="d3c7c-2008">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2008">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2009">規則運算式 Regex_greece_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2009">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2010">從 Keyword_greece_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2010">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2011">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2011">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="d3c7c-2012">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2012">Keyword_greece_id_card</span></span>

- <span data-ttu-id="d3c7c-2013">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2013">Greek identity Card</span></span>
- <span data-ttu-id="d3c7c-2014">Tautotita</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2014">Tautotita</span></span>
- <span data-ttu-id="d3c7c-2015">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2015">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="d3c7c-2016">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2016">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="d3c7c-2017">香港身分證 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2017">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2018">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2018">Format</span></span>

<span data-ttu-id="d3c7c-2019">8-9 個字母和數字，加上選擇性括住的最後一個字元的組合</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2019">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2020">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2020">Pattern</span></span>

<span data-ttu-id="d3c7c-2021">8-9 個字母的組合：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2021">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="d3c7c-2022">1-2 個字母 (不區分大小寫) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2022">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2023">六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2023">Six digits</span></span> 
- <span data-ttu-id="d3c7c-2024">最後一個字元 (任何數字或字母 A)，是檢查碼且可選擇性加上前後括號。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2024">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2025">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2025">Checksum</span></span>

<span data-ttu-id="d3c7c-2026">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2026">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2027">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2027">Definition</span></span>

<span data-ttu-id="d3c7c-2028">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2028">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2029">函數 Func_hong_kong_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2029">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2030">從 Keyword_hong_kong_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2030">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="d3c7c-2031">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2031">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-2032">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2032">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2033">函數 Func_hong_kong_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2033">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2034">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2034">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2035">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2035">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="d3c7c-2036">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2036">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="d3c7c-2037">香港特別行政區識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2037">hong kong identity card</span></span>
- <span data-ttu-id="d3c7c-2038">HKIDC</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2038">HKIDC</span></span>
- <span data-ttu-id="d3c7c-2039">識別碼卡片</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2039">id card</span></span>
- <span data-ttu-id="d3c7c-2040">identity card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2040">identity card</span></span>
- <span data-ttu-id="d3c7c-2041">hk 識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2041">hk identity card</span></span>
- <span data-ttu-id="d3c7c-2042">香港特別行政區識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2042">hong kong id</span></span>
- <span data-ttu-id="d3c7c-2043">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2043">香港身份證</span></span>
- <span data-ttu-id="d3c7c-2044">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2044">香港永久性居民身份證</span></span>
- <span data-ttu-id="d3c7c-2045">身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2045">身份證</span></span>
- <span data-ttu-id="d3c7c-2046">身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2046">身份証</span></span>
- <span data-ttu-id="d3c7c-2047">身分證 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2047">身分證</span></span>
- <span data-ttu-id="d3c7c-2048">身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2048">身分証</span></span>
- <span data-ttu-id="d3c7c-2049">香港身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2049">香港身份証</span></span>
- <span data-ttu-id="d3c7c-2050">香港身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2050">香港身分證</span></span>
- <span data-ttu-id="d3c7c-2051">香港身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2051">香港身分証</span></span>
- <span data-ttu-id="d3c7c-2052">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2052">香港身份證</span></span>
- <span data-ttu-id="d3c7c-2053">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2053">香港居民身份證</span></span>
- <span data-ttu-id="d3c7c-2054">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2054">香港居民身份証</span></span>
- <span data-ttu-id="d3c7c-2055">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2055">香港居民身分證</span></span>
- <span data-ttu-id="d3c7c-2056">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2056">香港居民身分証</span></span>
- <span data-ttu-id="d3c7c-2057">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2057">香港永久性居民身份証</span></span>
- <span data-ttu-id="d3c7c-2058">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2058">香港永久性居民身分證</span></span>
- <span data-ttu-id="d3c7c-2059">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2059">香港永久性居民身分証</span></span>
- <span data-ttu-id="d3c7c-2060">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2060">香港永久性居民身份證</span></span>
- <span data-ttu-id="d3c7c-2061">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2061">香港非永久性居民身份證</span></span>
- <span data-ttu-id="d3c7c-2062">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2062">香港非永久性居民身份証</span></span>
- <span data-ttu-id="d3c7c-2063">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2063">香港非永久性居民身分證</span></span>
- <span data-ttu-id="d3c7c-2064">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2064">香港非永久性居民身分証</span></span>
- <span data-ttu-id="d3c7c-2065">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2065">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="d3c7c-2066">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2066">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="d3c7c-2067">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2067">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="d3c7c-2068">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2068">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="d3c7c-2069">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2069">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="d3c7c-2070">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2070">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="d3c7c-2071">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2071">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="d3c7c-2072">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2072">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="d3c7c-2073">印度永久帳戶號碼 (PAN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2073">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2074">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2074">Format</span></span>

<span data-ttu-id="d3c7c-2075">10 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2075">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2076">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2076">Pattern</span></span>

<span data-ttu-id="d3c7c-2077">10 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2077">10 letters or digits:</span></span>
- <span data-ttu-id="d3c7c-2078">五個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2078">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2079">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2079">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2080">一個做為字母檢查碼的字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2080">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2081">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2081">Checksum</span></span>

<span data-ttu-id="d3c7c-2082">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2083">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2083">Definition</span></span>

<span data-ttu-id="d3c7c-2084">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2084">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2085">規則運算式 Regex_india_permanent_account_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2085">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2086">從 Keyword_india_permanent_account_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2086">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="d3c7c-2087">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2087">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2088">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2088">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="d3c7c-2089">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2089">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="d3c7c-2090">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2090">Permanent Account Number</span></span> 
- <span data-ttu-id="d3c7c-2091">PAN
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2091">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="d3c7c-2092">印度唯一識別 (Aadhaar) 碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2092">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2093">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2093">Format</span></span>

<span data-ttu-id="d3c7c-2094">12 位數包含選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2094">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2095">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2095">Pattern</span></span>

<span data-ttu-id="d3c7c-2096">12 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2096">12 digits:</span></span>
- <span data-ttu-id="d3c7c-2097">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2097">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2098">一個選擇性空格或破折號 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2098">An optional space or dash</span></span> 
- <span data-ttu-id="d3c7c-2099">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2099">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2100">一個選擇性空格或破折號 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2100">An optional space or dash</span></span> 
- <span data-ttu-id="d3c7c-2101">最後一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2101">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2102">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2102">Checksum</span></span>

<span data-ttu-id="d3c7c-2103">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2103">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2104">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2104">Definition</span></span>

<span data-ttu-id="d3c7c-p133">DLP 原則是 85%有信心它已偵測到這種類型的機密資訊時，300 個字元的距離： 函數 Func_india_aadhaar 會找出符合模式的內容。從 Keyword_india_aadhar 關鍵字是找到。總和檢查碼會傳遞。DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 函數 Func_india_aadhaar 會找出符合模式的內容。總和檢查碼會傳遞。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="d3c7c-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="d3c7c-2111">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2111">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="d3c7c-2112">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2112">Keyword_india_aadhar</span></span>
- <span data-ttu-id="d3c7c-2113">Aadhar</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2113">Aadhar</span></span>
- <span data-ttu-id="d3c7c-2114">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2114">Aadhaar</span></span>
- <span data-ttu-id="d3c7c-2115">UID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2115">UID</span></span>
- <span data-ttu-id="d3c7c-2116">आधार</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2116">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="d3c7c-2117">印尼身分識 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2117">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2118">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2118">Format</span></span>

<span data-ttu-id="d3c7c-2119">16 位數包含選擇性句點</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2119">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2120">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2120">Pattern</span></span>

<span data-ttu-id="d3c7c-2121">16 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2121">16 digits:</span></span>
- <span data-ttu-id="d3c7c-2122">二位數省代碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2122">Two-digit province code</span></span> 
- <span data-ttu-id="d3c7c-2123">句點 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2123">A period (optional)</span></span> 
- <span data-ttu-id="d3c7c-2124">二位數攝政或城市代碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2124">Two-digit regency or city code</span></span> 
- <span data-ttu-id="d3c7c-2125">二位數次行政區代碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2125">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="d3c7c-2126">句點 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2126">A period (optional)</span></span> 
- <span data-ttu-id="d3c7c-2127">DDMMYY 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2127">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-2128">句點 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2128">A period (optional)</span></span> 
- <span data-ttu-id="d3c7c-2129">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2129">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2130">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2130">Checksum</span></span>

<span data-ttu-id="d3c7c-2131">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2131">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2132">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2132">Definition</span></span>

<span data-ttu-id="d3c7c-2133">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2133">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2134">規則運算式 Regex_indonesia_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2134">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2135">從 Keyword_indonesia_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2135">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="d3c7c-2136">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2137">規則運算式 Regex_indonesia_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2137">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2138">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2138">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="d3c7c-2139">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2139">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="d3c7c-2140">KTP</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2140">KTP</span></span>
- <span data-ttu-id="d3c7c-2141">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2141">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="d3c7c-2142">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2142">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="d3c7c-2143">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2143">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2144">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2144">Format</span></span>

<span data-ttu-id="d3c7c-2145">國家/地區碼 （兩個字母） 加號 plus bban 數 （最多 30 個字元） 檢查位數 （兩個位數）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2145">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2146">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2146">Pattern</span></span>

<span data-ttu-id="d3c7c-2147">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2147">Pattern must include all of the following:</span></span>

- <span data-ttu-id="d3c7c-2148">雙字母國家/地區碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2148">Two-letter country code</span></span>
- <span data-ttu-id="d3c7c-2149">兩個核取位數 （後面選用的空間）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2149">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="d3c7c-2150">1-7 群組的四個字母或數字 （可以以空格）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2150">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="d3c7c-2151">1-3 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2151">1-3 letters or digits</span></span>

<span data-ttu-id="d3c7c-p134">每個國家/地區的格式是稍有不同。IBAN 敏感資訊類型涵蓋下列 60 國家/地區：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="d3c7c-2154">ad、 ae、 al，在亞利桑那州、 ba、 是、 bg、 bh、 頻道、 cr、 cy、 cz、 de、 粗、 執行、 ee、 es、 wi-fi、 於、 fr、 gb、 ge、 gi、 gl、 /gr、 hr、 hu、 ie、 芝加哥，它、 kw、 kz、 lb、 li、 lt、 lu、 lv mc md、 我、 mk、 mr、 明、 mu、 nl、 [否] pl、 pt、 ro、 rs、 sa、 se、 si、 sk、 sm、 tn、 tr、 vg</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2155">Checksum</span></span>

<span data-ttu-id="d3c7c-2156">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2156">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2157">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2157">Definition</span></span>

<span data-ttu-id="d3c7c-2158">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2158">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2159">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2159">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2160">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2160">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2161">Keywords</span></span>

<span data-ttu-id="d3c7c-2162">無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2162">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="d3c7c-2163">IP 位址</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2163">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2164">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2164">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="d3c7c-2165">IPv4：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2165">IPv4:</span></span>
<span data-ttu-id="d3c7c-2166">表示格式化 (句點) 和未格式化 (無句點) 之 IPv4 位址的複雜模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2166">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="d3c7c-2167">IPv6：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2167">IPv6:</span></span>
<span data-ttu-id="d3c7c-2168">表示格式化 IPv6 號碼 (其中包含冒號) 的複雜模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2168">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2169">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2169">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2170">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2170">Checksum</span></span>

<span data-ttu-id="d3c7c-2171">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2172">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2172">Definition</span></span>

<span data-ttu-id="d3c7c-2173">對於 IPv6，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2173">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2174">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2174">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2175">找不到來自於 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2175">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="d3c7c-2176">對於 IPv4，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2176">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2177">規則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2177">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2178">找到來自於 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2178">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="d3c7c-2179">對於 IPv6，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2179">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2180">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2180">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2181">找不到來自於 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2181">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2182">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2182">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="d3c7c-2183">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2183">Keyword_ipaddress</span></span>

- <span data-ttu-id="d3c7c-2184">IP (此關鍵字區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2184">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="d3c7c-2185">ip address
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2185">ip address</span></span> 
- <span data-ttu-id="d3c7c-2186">ip addresses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2186">ip addresses</span></span>
- <span data-ttu-id="d3c7c-2187">internet protocol</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2187">internet protocol</span></span>
- <span data-ttu-id="d3c7c-2188">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2188">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="d3c7c-2189">國際分類的治療法 （ICD-10-公分）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2189">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2190">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2190">Format</span></span>

<span data-ttu-id="d3c7c-2191">字典</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2191">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2192">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2192">Pattern</span></span>

<span data-ttu-id="d3c7c-2193">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2193">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2194">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2194">Checksum</span></span>

<span data-ttu-id="d3c7c-2195">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2195">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2196">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2196">Definition</span></span>

<span data-ttu-id="d3c7c-2197">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2197">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2198">從 Dictionary_icd_10_cm 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2198">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="d3c7c-2199">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2199">Keywords</span></span>

<span data-ttu-id="d3c7c-p135">任何字詞的 Dictionary_icd_10_cm 關鍵字字典，這根據[國際分類的治療法、 十分之一修訂、 臨床修改 （ICD-10-公分）](https://go.microsoft.com/fwlink/?linkid=852604)。此類型只會尋找詞不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="d3c7c-2202">國際分類的治療法 （ICD-9-公分）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2202">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2203">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2203">Format</span></span>

<span data-ttu-id="d3c7c-2204">字典</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2204">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2205">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2205">Pattern</span></span>

<span data-ttu-id="d3c7c-2206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2206">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2207">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2207">Checksum</span></span>

<span data-ttu-id="d3c7c-2208">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2208">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2209">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2209">Definition</span></span>

<span data-ttu-id="d3c7c-2210">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2210">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2211">從 Dictionary_icd_9_cm 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2211">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2212">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2212">Keywords</span></span>

<span data-ttu-id="d3c7c-p136">任何字詞的 Dictionary_icd_9_cm 關鍵字字典，這根據[國際分類的治療法、 二十九修訂、 臨床修改 （ICD-9-公分）](https://go.microsoft.com/fwlink/?linkid=852605)。此類型只會尋找詞不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="d3c7c-2215">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2215">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2216">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2216">Format</span></span>

<span data-ttu-id="d3c7c-2217">（直到 31 Dec 2012) 的舊格式：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2217">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="d3c7c-2218">七位數後尾隨 1-2 個字母 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2218">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="d3c7c-2219">新的格式 (1 Jan 2013 及之後)：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2219">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="d3c7c-2220">七位數後尾隨二個字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2220">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2221">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2221">Pattern</span></span>

<span data-ttu-id="d3c7c-2222">（直到 31 Dec 2012) 的舊格式：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2222">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="d3c7c-2223">七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2223">Seven digits</span></span> 
- <span data-ttu-id="d3c7c-2224">1-2 個字母 (不區分大小寫) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2224">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="d3c7c-2225">新的格式 (1 Jan 2013 及之後)：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2225">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="d3c7c-2226">七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2226">Seven digits</span></span> 
- <span data-ttu-id="d3c7c-2227">一個字母 (不區分大小寫)，是一個字母檢查碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2227">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="d3c7c-2228">字母 "A" 或 "H" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2228">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2229">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2229">Checksum</span></span>

<span data-ttu-id="d3c7c-2230">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2230">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2231">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2231">Definition</span></span>

<span data-ttu-id="d3c7c-2232">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2232">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2233">函數 Func_ireland_pps 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2233">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2234">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2234">One of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-2235">從 Keyword_ireland_pps 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2235">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="d3c7c-2236">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2236">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d3c7c-2237">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2237">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-2238">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2238">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2239">函數 Func_ireland_pps 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2239">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2240">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2240">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2241">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2241">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="d3c7c-2242">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2242">Keyword_ireland_pps</span></span>

- <span data-ttu-id="d3c7c-2243">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2243">Personal Public Service Number</span></span> 
- <span data-ttu-id="d3c7c-2244">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2244">PPS Number</span></span> 
- <span data-ttu-id="d3c7c-2245">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2245">PPS Num</span></span> 
- <span data-ttu-id="d3c7c-2246">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2246">PPS No.</span></span> 
- <span data-ttu-id="d3c7c-2247">PPS #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2247">PPS #</span></span> 
- <span data-ttu-id="d3c7c-2248">PPS#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2248">PPS#</span></span> 
- <span data-ttu-id="d3c7c-2249">PPSN
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2249">PPSN</span></span> 
- <span data-ttu-id="d3c7c-2250">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2250">Public Services Card</span></span> 
- <span data-ttu-id="d3c7c-2251">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2251">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="d3c7c-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="d3c7c-2254">PSP
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2254">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="d3c7c-2255">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2255">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2256">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2256">Format</span></span>

<span data-ttu-id="d3c7c-2257">13 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2257">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2258">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2258">Pattern</span></span>

<span data-ttu-id="d3c7c-2259">格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2259">Formatted:</span></span>
- <span data-ttu-id="d3c7c-2260">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2260">Two digits</span></span> 
- <span data-ttu-id="d3c7c-2261">一個破折號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2261">A dash</span></span> 
- <span data-ttu-id="d3c7c-2262">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2262">Three digits</span></span> 
- <span data-ttu-id="d3c7c-2263">一個破折號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2263">A dash</span></span> 
- <span data-ttu-id="d3c7c-2264">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2264">Eight digits</span></span>

<span data-ttu-id="d3c7c-2265">未格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2265">Unformatted:</span></span>
- <span data-ttu-id="d3c7c-2266">13 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2266">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2267">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2267">Checksum</span></span>

<span data-ttu-id="d3c7c-2268">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2269">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2269">Definition</span></span>

<span data-ttu-id="d3c7c-2270">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2271">規則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2271">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2272">找到來自於 Keyword_israel_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2272">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2273">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2273">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="d3c7c-2274">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2274">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="d3c7c-2275">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2275">Bank Account Number</span></span> 
- <span data-ttu-id="d3c7c-2276">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2276">Bank Account</span></span> 
- <span data-ttu-id="d3c7c-2277">Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2277">Account Number</span></span> 
- <span data-ttu-id="d3c7c-2278">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2278">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="d3c7c-2279">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2279">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2280">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2280">Format</span></span>

<span data-ttu-id="d3c7c-2281">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2281">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2282">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2282">Pattern</span></span>

<span data-ttu-id="d3c7c-2283">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2283">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2284">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2284">Checksum</span></span>

<span data-ttu-id="d3c7c-2285">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2285">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2286">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2286">Definition</span></span>

<span data-ttu-id="d3c7c-2287">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2288">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2288">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2289">找到來自於 Keyword_Israel_National_ID 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2289">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="d3c7c-2290">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2290">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2291">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2291">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="d3c7c-2292">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2292">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="d3c7c-2293">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2293">מספר זהות</span></span> 
- <span data-ttu-id="d3c7c-2294">國門身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2294">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="d3c7c-2295">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2295">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2296">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2296">Format</span></span>

<span data-ttu-id="d3c7c-2297">10 個字母和數字的組合</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2297">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2298">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2298">Pattern</span></span>

- <span data-ttu-id="d3c7c-2299">10 個字母和數字的組合：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2299">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="d3c7c-2300">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2300">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2301">字母 "A" 或 "V" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2301">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2302">七個字母 (不區分大小寫)、數字或底線字元</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2302">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="d3c7c-2303">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2303">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2304">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2304">Checksum</span></span>

<span data-ttu-id="d3c7c-2305">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2305">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2306">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2306">Definition</span></span>

<span data-ttu-id="d3c7c-2307">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2308">規則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2308">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2309">找到來自於 Keyword_italy_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2309">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2310">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2310">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="d3c7c-2311">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2311">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="d3c7c-2312">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2312">numero di patente di guida</span></span> 
- <span data-ttu-id="d3c7c-2313">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2313">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="d3c7c-2314">日本銀行帳號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2314">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2315">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2315">Format</span></span>

<span data-ttu-id="d3c7c-2316">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2316">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2317">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2317">Pattern</span></span>

<span data-ttu-id="d3c7c-2318">銀行帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2318">Bank account number:</span></span>
- <span data-ttu-id="d3c7c-2319">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2319">Seven or eight digits</span></span>
- <span data-ttu-id="d3c7c-2320">銀行帳戶分行代碼：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2320">Bank account branch code:</span></span>
- <span data-ttu-id="d3c7c-2321">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2321">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2322">一個空格或連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2322">A space or dash (optional)</span></span> 
- <span data-ttu-id="d3c7c-2323">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2323">Three digits</span></span>

<span data-ttu-id="d3c7c-2324">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2324">Checksum</span></span>

<span data-ttu-id="d3c7c-2325">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2325">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2326">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2326">Definition</span></span>

<span data-ttu-id="d3c7c-2327">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2327">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2328">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2328">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2329">找到來自於 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2329">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="d3c7c-2330">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2330">One of the following is true:</span></span>
- <span data-ttu-id="d3c7c-2331">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2331">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2332">找到來自於 Keyword_jp_bank_branch_code 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2332">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="d3c7c-2333">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2333">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2334">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2334">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2335">找到來自於 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2335">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2336">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2336">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="d3c7c-2337">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2337">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="d3c7c-2338">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2338">Checking Account Number</span></span> 
- <span data-ttu-id="d3c7c-2339">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2339">Checking Account</span></span> 
- <span data-ttu-id="d3c7c-2340">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2340">Checking Account #</span></span> 
- <span data-ttu-id="d3c7c-2341">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2341">Checking Acct Number</span></span> 
- <span data-ttu-id="d3c7c-2342">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2342">Checking Acct #</span></span> 
- <span data-ttu-id="d3c7c-2343">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2343">Checking Acct No.</span></span> 
- <span data-ttu-id="d3c7c-2344">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2344">Checking Account No.</span></span> 
- <span data-ttu-id="d3c7c-2345">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2345">Bank Account Number</span></span> 
- <span data-ttu-id="d3c7c-2346">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2346">Bank Account</span></span> 
- <span data-ttu-id="d3c7c-2347">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2347">Bank Account #</span></span> 
- <span data-ttu-id="d3c7c-2348">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2348">Bank Acct Number</span></span> 
- <span data-ttu-id="d3c7c-2349">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2349">Bank Acct #</span></span> 
- <span data-ttu-id="d3c7c-2350">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2350">Bank Acct No.</span></span> 
- <span data-ttu-id="d3c7c-2351">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2351">Bank Account No.</span></span> 
- <span data-ttu-id="d3c7c-2352">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2352">Savings Account Number</span></span> 
- <span data-ttu-id="d3c7c-2353">節約帳戶</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2353">Savings Account</span></span> 
- <span data-ttu-id="d3c7c-2354">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2354">Savings Account #</span></span> 
- <span data-ttu-id="d3c7c-2355">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2355">Savings Acct Number</span></span> 
- <span data-ttu-id="d3c7c-2356">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2356">Savings Acct #</span></span> 
- <span data-ttu-id="d3c7c-2357">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2357">Savings Acct No.</span></span> 
- <span data-ttu-id="d3c7c-2358">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2358">Savings Account No.</span></span> 
- <span data-ttu-id="d3c7c-2359">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2359">Debit Account Number</span></span> 
- <span data-ttu-id="d3c7c-2360">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2360">Debit Account</span></span> 
- <span data-ttu-id="d3c7c-2361">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2361">Debit Account #</span></span> 
- <span data-ttu-id="d3c7c-2362">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2362">Debit Acct Number</span></span> 
- <span data-ttu-id="d3c7c-2363">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2363">Debit Acct #</span></span> 
- <span data-ttu-id="d3c7c-2364">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2364">Debit Acct No.</span></span> 
- <span data-ttu-id="d3c7c-2365">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2365">Debit Account No.</span></span> 
- <span data-ttu-id="d3c7c-2366">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2366">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="d3c7c-2367">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2367">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="d3c7c-2368">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2368">＃勘定の確認</span></span> 
- <span data-ttu-id="d3c7c-2369">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2369">勘定番号の確認</span></span> 
- <span data-ttu-id="d3c7c-2370">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2370">口座番号の確認</span></span> 
- <span data-ttu-id="d3c7c-2371">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2371">銀行口座番号</span></span> 
- <span data-ttu-id="d3c7c-2372">銀行口座</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2372">銀行口座</span></span> 
- <span data-ttu-id="d3c7c-2373">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2373">銀行口座＃</span></span> 
- <span data-ttu-id="d3c7c-2374">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2374">銀行の勘定番号</span></span> 
- <span data-ttu-id="d3c7c-2375">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2375">銀行のacct＃</span></span> 
- <span data-ttu-id="d3c7c-2376">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2376">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="d3c7c-2377">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2377">銀行口座番号</span></span>
- <span data-ttu-id="d3c7c-2378">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2378">普通預金口座番号</span></span> 
- <span data-ttu-id="d3c7c-2379">預金口座
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2379">預金口座</span></span> 
- <span data-ttu-id="d3c7c-2380">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2380">貯蓄口座＃</span></span> 
- <span data-ttu-id="d3c7c-2381">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2381">貯蓄勘定の数</span></span> 
- <span data-ttu-id="d3c7c-2382">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2382">貯蓄勘定＃</span></span> 
- <span data-ttu-id="d3c7c-2383">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2383">貯蓄勘定番号</span></span> 
- <span data-ttu-id="d3c7c-2384">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2384">普通預金口座番号</span></span> 
- <span data-ttu-id="d3c7c-2385">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2385">引き落とし口座番号</span></span> 
- <span data-ttu-id="d3c7c-2386">口座番号</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2386">口座番号</span></span> 
- <span data-ttu-id="d3c7c-2387">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2387">口座番号＃</span></span> 
- <span data-ttu-id="d3c7c-2388">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2388">デビットのacct番号</span></span> 
- <span data-ttu-id="d3c7c-2389">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2389">デビット勘定＃</span></span> 
- <span data-ttu-id="d3c7c-2390">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2390">デビットACCTの番号</span></span> 
- <span data-ttu-id="d3c7c-2391">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2391">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="d3c7c-2392">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2392">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="d3c7c-2393">Otemachi</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2393">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="d3c7c-2394">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2394">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2395">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2395">Format</span></span>

<span data-ttu-id="d3c7c-2396">12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2396">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2397">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2397">Pattern</span></span>

<span data-ttu-id="d3c7c-2398">12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2398">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2399">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2399">Checksum</span></span>

<span data-ttu-id="d3c7c-2400">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2400">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2401">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2401">Definition</span></span>

<span data-ttu-id="d3c7c-2402">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2402">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2403">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2403">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2404">找到來自於 Keyword_jp_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2404">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2405">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2405">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="d3c7c-2406">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2406">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="d3c7c-2407">dl#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2407">dl#</span></span> 
- <span data-ttu-id="d3c7c-2408">DL #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2408">DL＃</span></span> 
- <span data-ttu-id="d3c7c-2409">dl #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2409">dls#</span></span> 
- <span data-ttu-id="d3c7c-2410">DL #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2410">DLS＃</span></span> 
- <span data-ttu-id="d3c7c-2411">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2411">driver license</span></span> 
- <span data-ttu-id="d3c7c-2412">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2412">driver licenses</span></span> 
- <span data-ttu-id="d3c7c-2413">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2413">drivers license</span></span> 
- <span data-ttu-id="d3c7c-2414">駕照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2414">driver's license</span></span> 
- <span data-ttu-id="d3c7c-2415">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2415">drivers licenses</span></span> 
- <span data-ttu-id="d3c7c-2416">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2416">driver's licenses</span></span> 
- <span data-ttu-id="d3c7c-2417">driving licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2417">driving licence</span></span> 
- <span data-ttu-id="d3c7c-2418">lic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2418">lic#</span></span> 
- <span data-ttu-id="d3c7c-2419">LIC #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2419">LIC＃</span></span> 
- <span data-ttu-id="d3c7c-2420">lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2420">lics#</span></span> 
- <span data-ttu-id="d3c7c-2421">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2421">state id</span></span> 
- <span data-ttu-id="d3c7c-2422">state identification
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2422">state identification</span></span> 
- <span data-ttu-id="d3c7c-2423">state identification number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2423">state identification number</span></span> 
- <span data-ttu-id="d3c7c-2424">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2424">低所得国＃</span></span> 
- <span data-ttu-id="d3c7c-2425">免許証
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2425">免許証</span></span> 
- <span data-ttu-id="d3c7c-2426">状態ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2426">状態ID</span></span>
- <span data-ttu-id="d3c7c-2427">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2427">状態の識別</span></span> 
- <span data-ttu-id="d3c7c-2428">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2428">状態の識別番号</span></span> 
- <span data-ttu-id="d3c7c-2429">運転免許
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2429">運転免許</span></span> 
- <span data-ttu-id="d3c7c-2430">運転免許証
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2430">運転免許証</span></span> 
- <span data-ttu-id="d3c7c-2431">運転免許証番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2431">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="d3c7c-2432">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2432">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2433">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2433">Format</span></span>

<span data-ttu-id="d3c7c-2434">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2434">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2435">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2435">Pattern</span></span>

<span data-ttu-id="d3c7c-2436">兩個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2436">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2437">Checksum</span></span>

<span data-ttu-id="d3c7c-2438">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2438">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2439">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2439">Definition</span></span>

<span data-ttu-id="d3c7c-2440">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2441">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2441">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2442">找到來自於 Keyword_jp_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2442">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2443">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="d3c7c-2444">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2444">Keyword_jp_passport</span></span>

- <span data-ttu-id="d3c7c-2445">パスポート
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2445">パスポート</span></span> 
- <span data-ttu-id="d3c7c-2446">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2446">パスポート番号</span></span> 
- <span data-ttu-id="d3c7c-2447">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2447">パスポートのNum</span></span> 
- <span data-ttu-id="d3c7c-2448">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2448">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="d3c7c-2449">日本常駐居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2449">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2450">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2450">Format</span></span>

<span data-ttu-id="d3c7c-2451">11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2451">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2452">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2452">Pattern</span></span>

<span data-ttu-id="d3c7c-2453">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2453">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2454">Checksum</span></span>

<span data-ttu-id="d3c7c-2455">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2455">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2456">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2456">Definition</span></span>

<span data-ttu-id="d3c7c-2457">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2458">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2458">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2459">找到來自於 Keyword_jp_resident_registration_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2459">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2460">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="d3c7c-2461">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2461">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="d3c7c-2462">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2462">Resident Registration Number</span></span>
- <span data-ttu-id="d3c7c-2463">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2463">Resident Register Number</span></span> 
- <span data-ttu-id="d3c7c-2464">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2464">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="d3c7c-2465">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2465">Resident Registration No.</span></span> 
- <span data-ttu-id="d3c7c-2466">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2466">Resident Register No.</span></span> 
- <span data-ttu-id="d3c7c-2467">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2467">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="d3c7c-2468">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2468">Basic Resident Register No.</span></span> 
- <span data-ttu-id="d3c7c-2469">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2469">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="d3c7c-2470">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2470">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="d3c7c-2471">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2471">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="d3c7c-2472">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2472">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="d3c7c-2473">日本社會保險號碼 (SIN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2473">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2474">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2474">Format</span></span>

<span data-ttu-id="d3c7c-2475">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2475">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2476">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2476">Pattern</span></span>

<span data-ttu-id="d3c7c-2477">7-12 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2477">7-12 digits:</span></span>
- <span data-ttu-id="d3c7c-2478">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2478">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2479">一個連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2479">A hyphen (optional)</span></span> 
- <span data-ttu-id="d3c7c-2480">6 位數或</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2480">Six digits OR</span></span>
- <span data-ttu-id="d3c7c-2481">7-12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2481">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2482">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2482">Checksum</span></span>

<span data-ttu-id="d3c7c-2483">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2483">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2484">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2484">Definition</span></span>

<span data-ttu-id="d3c7c-2485">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2485">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2486">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2486">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2487">找到來自於 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2487">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="d3c7c-2488">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2488">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2489">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2489">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2490">找到來自於 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2490">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2491">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2491">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="d3c7c-2492">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2492">Keyword_jp_sin</span></span>

- <span data-ttu-id="d3c7c-2493">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2493">Social Insurance No.</span></span> 
- <span data-ttu-id="d3c7c-2494">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2494">Social Insurance Num</span></span> 
- <span data-ttu-id="d3c7c-2495">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2495">Social Insurance Number</span></span> 
- <span data-ttu-id="d3c7c-2496">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2496">社会保険のテンキー</span></span> 
- <span data-ttu-id="d3c7c-2497">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2497">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="d3c7c-2498">日文我卡卡號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2498">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2499">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2499">Format</span></span>

<span data-ttu-id="d3c7c-2500">12 字母和數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2500">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2501">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2501">Pattern</span></span>

<span data-ttu-id="d3c7c-2502">12 字母和數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2502">12 letters and digits:</span></span>
- <span data-ttu-id="d3c7c-2503">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2503">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="d3c7c-2504">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2504">Eight digits</span></span> 
- <span data-ttu-id="d3c7c-2505">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2505">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2506">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2506">Checksum</span></span>

<span data-ttu-id="d3c7c-2507">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2507">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2508">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2508">Definition</span></span>

<span data-ttu-id="d3c7c-2509">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2509">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2510">規則運算式 Regex_jp_residence_card_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2510">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2511">從 Keyword_jp_residence_card_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2511">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2512">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="d3c7c-2513">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2513">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="d3c7c-2514">我卡卡號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2514">Residence card number</span></span>
- <span data-ttu-id="d3c7c-2515">我卡片否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2515">Residence card no</span></span>
- <span data-ttu-id="d3c7c-2516">我卡 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2516">Residence card #</span></span>
- <span data-ttu-id="d3c7c-2517">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2517">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="d3c7c-2518">馬來西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2518">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2519">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2519">Format</span></span>

<span data-ttu-id="d3c7c-2520">12 位數包含選擇性連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2520">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2521">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2521">Pattern</span></span>

<span data-ttu-id="d3c7c-2522">12 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2522">12 digits:</span></span>
- <span data-ttu-id="d3c7c-2523">YYMMDD 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2523">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-2524">一個破折號 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2524">A dash (optional)</span></span> 
- <span data-ttu-id="d3c7c-2525">兩個字母的出生地代碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2525">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="d3c7c-2526">一個破折號 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2526">A dash (optional)</span></span> 
- <span data-ttu-id="d3c7c-2527">三個隨機的數字 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2527">Three random digits</span></span> 
- <span data-ttu-id="d3c7c-2528">一位數性別代碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2528">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2529">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2529">Checksum</span></span>

<span data-ttu-id="d3c7c-2530">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2530">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2531">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2531">Definition</span></span>

<span data-ttu-id="d3c7c-2532">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2532">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2533">規則運算式 Regex_malaysia_id_card_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2533">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2534">從 Keyword_malaysia_id_card_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2534">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2535">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2535">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="d3c7c-2536">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2536">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="d3c7c-2537">數位應用程式卡片</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2537">digital application card</span></span>
- <span data-ttu-id="d3c7c-2538">i / c</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2538">i/c</span></span>
- <span data-ttu-id="d3c7c-2539">i / c 沒有</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2539">i/c no</span></span>
- <span data-ttu-id="d3c7c-2540">ic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2540">ic</span></span>
- <span data-ttu-id="d3c7c-2541">ic 無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2541">ic no</span></span>
- <span data-ttu-id="d3c7c-2542">識別碼卡片</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2542">id card</span></span>
- <span data-ttu-id="d3c7c-2543">識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2543">identification Card</span></span>
- <span data-ttu-id="d3c7c-2544">identity card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2544">identity card</span></span>
- <span data-ttu-id="d3c7c-2545">k/p</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2545">k/p</span></span>
- <span data-ttu-id="d3c7c-2546">k/p 無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2546">k/p no</span></span>
- <span data-ttu-id="d3c7c-2547">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2547">kad akuan diri</span></span>
- <span data-ttu-id="d3c7c-2548">kad aplikasi 數位</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2548">kad aplikasi digital</span></span>
- <span data-ttu-id="d3c7c-2549">kad pengenalan 馬來西亞</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2549">kad pengenalan malaysia</span></span>
- <span data-ttu-id="d3c7c-2550">kp</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2550">kp</span></span>
- <span data-ttu-id="d3c7c-2551">kp 沒有</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2551">kp no</span></span>
- <span data-ttu-id="d3c7c-2552">mykad</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2552">mykad</span></span>
- <span data-ttu-id="d3c7c-2553">mykas</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2553">mykas</span></span>
- <span data-ttu-id="d3c7c-2554">mykid</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2554">mykid</span></span>
- <span data-ttu-id="d3c7c-2555">mypr</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2555">mypr</span></span>
- <span data-ttu-id="d3c7c-2556">mytentera</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2556">mytentera</span></span>
- <span data-ttu-id="d3c7c-2557">馬來西亞識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2557">malaysia identity card</span></span>
- <span data-ttu-id="d3c7c-2558">德識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2558">malaysian identity card</span></span>
- <span data-ttu-id="d3c7c-2559">nric</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2559">nric</span></span>
- <span data-ttu-id="d3c7c-2560">個人識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2560">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="d3c7c-2561">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2561">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2562">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2562">Format</span></span>

<span data-ttu-id="d3c7c-2563">8-9 位數包含選擇性空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2563">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2564">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2564">Pattern</span></span>

<span data-ttu-id="d3c7c-2565">8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2565">8-9 digits:</span></span>
- <span data-ttu-id="d3c7c-2566">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2566">Three digits</span></span> 
- <span data-ttu-id="d3c7c-2567">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2567">A space (optional)</span></span> 
- <span data-ttu-id="d3c7c-2568">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2568">Three digits</span></span> 
- <span data-ttu-id="d3c7c-2569">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2569">A space (optional)</span></span> 
- <span data-ttu-id="d3c7c-2570">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2570">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2571">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2571">Checksum</span></span>

<span data-ttu-id="d3c7c-2572">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2573">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2573">Definition</span></span>

<span data-ttu-id="d3c7c-2574">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2574">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2575">函數 Func_netherlands_bsn 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2575">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2576">從 Keyword_netherlands_bsn 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2576">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="d3c7c-2577">函數 Func_eu_date2 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2577">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="d3c7c-2578">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2578">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2579">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2579">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="d3c7c-2580">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2580">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="d3c7c-2581">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2581">Citizen service number</span></span> 
- <span data-ttu-id="d3c7c-2582">BSN

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2582">BSN</span></span> 
- <span data-ttu-id="d3c7c-2583">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2583">Burgerservicenummer</span></span> 
- <span data-ttu-id="d3c7c-2584">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2584">Sofinummer</span></span> 
- <span data-ttu-id="d3c7c-2585">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2585">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="d3c7c-2586">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2586">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="d3c7c-2587">紐西蘭衛生部編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2587">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2588">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2588">Format</span></span>

<span data-ttu-id="d3c7c-2589">三個字母、一個空格 (選用) 和四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2589">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2590">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2590">Pattern</span></span>

<span data-ttu-id="d3c7c-2591">三個字母空格 （選擇性） 四位數 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2591">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2592">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2592">Checksum</span></span>

<span data-ttu-id="d3c7c-2593">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2593">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2594">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2594">Definition</span></span>

<span data-ttu-id="d3c7c-2595">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2596">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2596">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2597">找到來自於 Keyword_nz_terms 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2597">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="d3c7c-2598">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2598">The checksum passes.</span></span>

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

<span data-ttu-id="d3c7c-2599">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2599">Keywords</span></span>

<span data-ttu-id="d3c7c-2600">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2600">Keyword_nz_terms</span></span>

- <span data-ttu-id="d3c7c-2601">NHI
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2601">NHI</span></span> 
- <span data-ttu-id="d3c7c-2602">紐西蘭</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2602">New Zealand</span></span> 
- <span data-ttu-id="d3c7c-2603">健康情況</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2603">Health</span></span> 
- <span data-ttu-id="d3c7c-2604">treatment
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2604">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="d3c7c-2605">挪威識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2605">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2606">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2606">Format</span></span>

<span data-ttu-id="d3c7c-2607">11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2607">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2608">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2608">Pattern</span></span>

<span data-ttu-id="d3c7c-2609">11 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2609">11 digits:</span></span>
- <span data-ttu-id="d3c7c-2610">DDMMYY 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2610">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-2611">三位數個人識別碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2611">Three-digit individual number</span></span> 
- <span data-ttu-id="d3c7c-2612">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2612">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2613">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2613">Checksum</span></span>

<span data-ttu-id="d3c7c-2614">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2614">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2615">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2615">Definition</span></span>

<span data-ttu-id="d3c7c-2616">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2616">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2617">函數 Func_norway_id_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2617">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2618">從 Keyword_norway_id_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2618">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="d3c7c-2619">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2619">The checksum passes.</span></span>
- <span data-ttu-id="d3c7c-2620">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2621">函數 Func_norway_id_numbe 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2621">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2622">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2622">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2623">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2623">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="d3c7c-2624">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2624">Keyword_norway_id_number</span></span>

- <span data-ttu-id="d3c7c-2625">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2625">Personal identification number</span></span>
- <span data-ttu-id="d3c7c-2626">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2626">Norwegian ID Number</span></span>
- <span data-ttu-id="d3c7c-2627">ID Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2627">ID Number</span></span>
- <span data-ttu-id="d3c7c-2628">Identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2628">Identification</span></span>
- <span data-ttu-id="d3c7c-2629">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2629">Personnummer</span></span>
- <span data-ttu-id="d3c7c-2630">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2630">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="d3c7c-2631">菲律賓統一多用途身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2631">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2632">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2632">Format</span></span>

<span data-ttu-id="d3c7c-2633">以連字號分隔的 12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2633">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2634">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2634">Pattern</span></span>

<span data-ttu-id="d3c7c-2635">12 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2635">12 digits:</span></span>
- <span data-ttu-id="d3c7c-2636">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2636">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2637">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2637">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-2638">七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2638">Seven digits</span></span> 
- <span data-ttu-id="d3c7c-2639">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2639">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-2640">一個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2640">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2641">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2641">Checksum</span></span>

<span data-ttu-id="d3c7c-2642">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2642">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2643">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2643">Definition</span></span>

<span data-ttu-id="d3c7c-2644">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2644">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2645">規則運算式 Regex_philippines_unified_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2645">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2646">從 Keyword_philippines_id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2646">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2647">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2647">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="d3c7c-2648">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2648">Keyword_philippines_id</span></span>

- <span data-ttu-id="d3c7c-2649">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2649">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="d3c7c-2650">UMID
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2650">UMID</span></span> 
- <span data-ttu-id="d3c7c-2651">Identity Card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2651">Identity Card</span></span> 
- <span data-ttu-id="d3c7c-2652">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2652">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="d3c7c-2653">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2653">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2654">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2654">Format</span></span>

<span data-ttu-id="d3c7c-2655">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2655">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2656">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2656">Pattern</span></span>

<span data-ttu-id="d3c7c-2657">三個字母 (不區分大小寫) 後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2657">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2658">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2658">Checksum</span></span>

<span data-ttu-id="d3c7c-2659">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2659">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2660">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2660">Definition</span></span>

<span data-ttu-id="d3c7c-p138">DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 函數 Func_polish_national_id 會找出符合模式的內容。從 Keyword_polish_national_id_passport_number 關鍵字是找到。總和檢查碼會傳遞。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2664">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2664">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="d3c7c-2665">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2665">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="d3c7c-2666">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2666">Dowód osobisty</span></span>
- <span data-ttu-id="d3c7c-2667">數目 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2667">Numer dowodu osobistego</span></span>
- <span data-ttu-id="d3c7c-2668">Nazwa 我數目 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2668">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="d3c7c-2669">Nazwa 我編號 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2669">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="d3c7c-2670">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2670">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="d3c7c-2671">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2671">Dowód Tożsamości</span></span>
- <span data-ttu-id="d3c7c-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p139">dow. os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="d3c7c-2674">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2674">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2675">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2675">Format</span></span>

<span data-ttu-id="d3c7c-2676">11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2676">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2677">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2677">Pattern</span></span>

<span data-ttu-id="d3c7c-2678">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2678">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2679">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2679">Checksum</span></span>

<span data-ttu-id="d3c7c-2680">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2680">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2681">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2681">Definition</span></span>

<span data-ttu-id="d3c7c-2682">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2682">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2683">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2683">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2684">找到來自於 Keyword_pesel_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2684">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="d3c7c-2685">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2685">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2686">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2686">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="d3c7c-2687">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2687">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="d3c7c-2688">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2688">Nr PESEL</span></span>
- <span data-ttu-id="d3c7c-2689">PESEL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2689">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="d3c7c-2690">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2690">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2691">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2691">Format</span></span>

<span data-ttu-id="d3c7c-2692">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2692">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2693">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2693">Pattern</span></span>

<span data-ttu-id="d3c7c-2694">兩個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2694">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2695">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2695">Checksum</span></span>

<span data-ttu-id="d3c7c-2696">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2696">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2697">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2697">Definition</span></span>

<span data-ttu-id="d3c7c-2698">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2698">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2699">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2699">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2700">找到來自於 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2700">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="d3c7c-2701">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2701">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2702">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2702">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="d3c7c-2703">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2703">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="d3c7c-2704">數目 paszportu</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2704">Numer paszportu</span></span>
- <span data-ttu-id="d3c7c-p140">Paszportu 編號。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p140">Nr. Paszportu</span></span>
- <span data-ttu-id="d3c7c-2707">Paszport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2707">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="d3c7c-2708">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2708">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2709">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2709">Format</span></span>

<span data-ttu-id="d3c7c-2710">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2710">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2711">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2711">Pattern</span></span>

<span data-ttu-id="d3c7c-2712">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2712">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2713">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2713">Checksum</span></span>

<span data-ttu-id="d3c7c-2714">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2714">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2715">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2715">Definition</span></span>

<span data-ttu-id="d3c7c-2716">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2716">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2717">規則運算式 Regex_portugal_citizen_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2717">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2718">從 Keyword_portugal_citizen_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2718">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2719">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2719">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="d3c7c-2720">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2720">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="d3c7c-2721">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2721">Citizen Card</span></span>
- <span data-ttu-id="d3c7c-2722">National ID Card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2722">National ID Card</span></span>
- <span data-ttu-id="d3c7c-2723">CC</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2723">CC</span></span>
- <span data-ttu-id="d3c7c-2724">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2724">Cartão de Cidadão</span></span>
- <span data-ttu-id="d3c7c-2725">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2725">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="d3c7c-2726">沙烏地阿拉伯國民身分證號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2726">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2727">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2727">Format</span></span>

<span data-ttu-id="d3c7c-2728">10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2728">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2729">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2729">Pattern</span></span>

<span data-ttu-id="d3c7c-2730">10 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2730">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2731">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2731">Checksum</span></span>

<span data-ttu-id="d3c7c-2732">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2732">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2733">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2733">Definition</span></span>

<span data-ttu-id="d3c7c-2734">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2734">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2735">規則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2735">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2736">找到來自於 Keyword_saudi_arabia_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2736">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2737">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2737">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="d3c7c-2738">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2738">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="d3c7c-2739">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2739">Identification Card</span></span> 
- <span data-ttu-id="d3c7c-2740">I card number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2740">I card number</span></span> 
- <span data-ttu-id="d3c7c-2741">識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2741">ID number</span></span> 
- <span data-ttu-id="d3c7c-2742">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2742">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="d3c7c-2743">新加坡國民登記身分證 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2743">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2744">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2744">Format</span></span>

<span data-ttu-id="d3c7c-2745">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2745">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2746">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2746">Pattern</span></span>

- <span data-ttu-id="d3c7c-2747">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2747">Nine letters and digits:</span></span>
- <span data-ttu-id="d3c7c-2748">字母 "F"、"G"、"S" 或 "T" (不區分大小寫) </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2748">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2749">七位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2749">Seven digits</span></span> 
- <span data-ttu-id="d3c7c-2750">一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2750">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2751">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2751">Checksum</span></span>

<span data-ttu-id="d3c7c-2752">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2752">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2753">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2753">Definition</span></span>

<span data-ttu-id="d3c7c-2754">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2754">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2755">規則運算式 Regex_singapore_nric 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2755">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2756">從 Keyword_singapore_nric 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2756">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="d3c7c-2757">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2757">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-2758">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2758">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2759">規則運算式 Regex_singapore_nric 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2759">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2760">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2760">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2761">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2761">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="d3c7c-2762">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2762">Keyword_singapore_nric</span></span>

- <span data-ttu-id="d3c7c-2763">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2763">National Registration Identity Card</span></span> 
- <span data-ttu-id="d3c7c-2764">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2764">Identity Card Number</span></span> 
- <span data-ttu-id="d3c7c-2765">NRIC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2765">NRIC</span></span> 
- <span data-ttu-id="d3c7c-2766">IC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2766">IC</span></span> 
- <span data-ttu-id="d3c7c-2767">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2767">Foreign Identification Number</span></span> 
- <span data-ttu-id="d3c7c-2768">FIN
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2768">FIN</span></span> 
- <span data-ttu-id="d3c7c-2769">身份证 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2769">身份证</span></span> 
- <span data-ttu-id="d3c7c-2770">身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2770">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="d3c7c-2771">南非身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2771">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2772">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2772">Format</span></span>

<span data-ttu-id="d3c7c-2773">可以包含空格的 13 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2773">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2774">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2774">Pattern</span></span>

<span data-ttu-id="d3c7c-2775">13 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2775">13 digits:</span></span>
- <span data-ttu-id="d3c7c-2776">YYMMDD 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2776">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-2777">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2777">Four digits</span></span> 
- <span data-ttu-id="d3c7c-2778">一位數公民指標 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2778">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="d3c7c-2779">數字 "8" 或 "9" </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2779">The digit "8" or "9"</span></span> 
- <span data-ttu-id="d3c7c-2780">一位數總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2780">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2781">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2781">Checksum</span></span>

<span data-ttu-id="d3c7c-2782">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2782">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2783">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2783">Definition</span></span>

<span data-ttu-id="d3c7c-2784">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2785">函數 Func_south_africa_identification_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2785">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2786">從 Keyword_south_africa_identification_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2786">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="d3c7c-2787">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2787">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2788">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2788">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="d3c7c-2789">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2789">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="d3c7c-2790">Identity card</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2790">Identity card</span></span>
- <span data-ttu-id="d3c7c-2791">ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2791">ID</span></span>
- <span data-ttu-id="d3c7c-2792">Identification</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2792">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="d3c7c-2793">南韓居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2793">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2794">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2794">Format</span></span>

<span data-ttu-id="d3c7c-2795">13 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2795">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2796">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2796">Pattern</span></span>

<span data-ttu-id="d3c7c-2797">13 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2797">13 digits:</span></span>
- <span data-ttu-id="d3c7c-2798">YYMMDD 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2798">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d3c7c-2799">一個連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2799">A hyphen</span></span> 
- <span data-ttu-id="d3c7c-2800">由世紀與性別判定的一位數 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2800">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="d3c7c-2801">四位數出生地區碼 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2801">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="d3c7c-2802">一位數，用來區分前幾碼皆相同的人員 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2802">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="d3c7c-2803">檢查碼。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2803">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2804">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2804">Checksum</span></span>

<span data-ttu-id="d3c7c-2805">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2805">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2806">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2806">Definition</span></span>

<span data-ttu-id="d3c7c-2807">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2807">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2808">函數 Func_south_korea_resident_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2808">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2809">從 Keyword_south_korea_resident_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2809">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="d3c7c-2810">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2810">The checksum passes.</span></span>

<span data-ttu-id="d3c7c-2811">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2811">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2812">函數 Func_south_korea_resident_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2812">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2813">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2813">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2814">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2814">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="d3c7c-2815">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2815">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="d3c7c-2816">國民身分證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2816">National ID card</span></span> 
- <span data-ttu-id="d3c7c-2817">公民登記號碼
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2817">Citizen's Registration Number</span></span> 
- <span data-ttu-id="d3c7c-2818">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2818">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="d3c7c-2819">RRN
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2819">RRN</span></span> 
- <span data-ttu-id="d3c7c-2820">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2820">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="d3c7c-2821">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2821">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2822">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2822">Format</span></span>

<span data-ttu-id="d3c7c-2823">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2823">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2824">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2824">Pattern</span></span>

<span data-ttu-id="d3c7c-2825">第 11 12 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2825">11-12 digits:</span></span>
- <span data-ttu-id="d3c7c-2826">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2826">Two digits</span></span> 
- <span data-ttu-id="d3c7c-2827">一個正斜線 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2827">A forward slash (optional)</span></span> 
- <span data-ttu-id="d3c7c-2828">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2828">7-8 digits</span></span> 
- <span data-ttu-id="d3c7c-2829">一個正斜線 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2829">A forward slash (optional)</span></span> 
- <span data-ttu-id="d3c7c-2830">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2830">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2831">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2831">Checksum</span></span>

<span data-ttu-id="d3c7c-2832">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2832">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2833">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2833">Definition</span></span>

<span data-ttu-id="d3c7c-2834">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2834">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2835">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2835">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2836">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2836">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2837">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2837">Keywords</span></span>

<span data-ttu-id="d3c7c-2838">無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2838">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="d3c7c-2839">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2839">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2840">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2840">Format</span></span>

<span data-ttu-id="d3c7c-2841">10 或 12 位數和一個選用分隔符號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2841">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2842">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2842">Pattern</span></span>

<span data-ttu-id="d3c7c-2843">10 或 12 位數和一個選用分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2843">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="d3c7c-2844">2-4 位數 (選用)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2844">2-4 digits (optional)</span></span> 
- <span data-ttu-id="d3c7c-2845">採用日期格式 YYMMDD 的六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2845">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="d3c7c-2846">分隔符號 "-" 或 "+" (選用)，加上</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2846">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="d3c7c-2847">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2847">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2848">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2848">Checksum</span></span>

<span data-ttu-id="d3c7c-2849">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2849">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2850">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2850">Definition</span></span>

<span data-ttu-id="d3c7c-2851">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2851">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2852">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2852">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2853">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2853">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2854">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2854">Keywords</span></span>

<span data-ttu-id="d3c7c-2855">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2855">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="d3c7c-2856">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2856">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2857">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2857">Format</span></span>

<span data-ttu-id="d3c7c-2858">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2858">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2859">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2859">Pattern</span></span>

<span data-ttu-id="d3c7c-2860">八個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2860">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2861">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2861">Checksum</span></span>

<span data-ttu-id="d3c7c-2862">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2862">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2863">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2863">Definition</span></span>

<span data-ttu-id="d3c7c-2864">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2864">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2865">規則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2865">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2866">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2866">One of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-2867">找到來自於 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2867">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="d3c7c-2868">找到來自於 Keyword_sweden_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2868">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-2869">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2869">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="d3c7c-2870">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2870">Keyword_sweden_passport</span></span>

- <span data-ttu-id="d3c7c-2871">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2871">visa requirements</span></span> 
- <span data-ttu-id="d3c7c-2872">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2872">Alien Registration Card</span></span> 
- <span data-ttu-id="d3c7c-2873">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2873">Schengen visas</span></span> 
- <span data-ttu-id="d3c7c-2874">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2874">Schengen visa</span></span> 
- <span data-ttu-id="d3c7c-2875">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2875">Visa Processing</span></span> 
- <span data-ttu-id="d3c7c-2876">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2876">Visa Type</span></span> 
- <span data-ttu-id="d3c7c-2877">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2877">Single Entry</span></span> 
- <span data-ttu-id="d3c7c-2878">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2878">Multiple Entry</span></span> 
- <span data-ttu-id="d3c7c-2879">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2879">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="d3c7c-2880">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2880">Keyword_passport</span></span>

- <span data-ttu-id="d3c7c-2881">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2881">Passport Number</span></span> 
- <span data-ttu-id="d3c7c-2882">
Passport No</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2882">Passport No</span></span> 
- <span data-ttu-id="d3c7c-2883">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2883">Passport #</span></span> 
- <span data-ttu-id="d3c7c-2884">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2884">Passport#</span></span> 
- <span data-ttu-id="d3c7c-2885">PassportID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2885">PassportID</span></span> 
- <span data-ttu-id="d3c7c-2886">Passportno
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2886">Passportno</span></span> 
- <span data-ttu-id="d3c7c-2887">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2887">passportnumber</span></span> 
- <span data-ttu-id="d3c7c-2888">パスポート</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2888">パスポート</span></span> 
- <span data-ttu-id="d3c7c-2889">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2889">パスポート番号</span></span> 
- <span data-ttu-id="d3c7c-2890">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2890">パスポートのNum</span></span> 
- <span data-ttu-id="d3c7c-2891">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2891">パスポート＃</span></span> 
- <span data-ttu-id="d3c7c-2892">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2892">Numéro de passeport</span></span> 
- <span data-ttu-id="d3c7c-2893">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2893">Passeport n °</span></span> 
- <span data-ttu-id="d3c7c-2894">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2894">Passeport Non</span></span> 
- <span data-ttu-id="d3c7c-2895">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2895">Passeport #</span></span> 
- <span data-ttu-id="d3c7c-2896">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2896">Passeport#</span></span> 
- <span data-ttu-id="d3c7c-2897">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2897">PasseportNon</span></span> 
- <span data-ttu-id="d3c7c-2898">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2898">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="d3c7c-2899">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2899">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2900">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2900">Format</span></span>

<span data-ttu-id="d3c7c-2901">四個字母後尾隨 5-31 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2901">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2902">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2902">Pattern</span></span>

<span data-ttu-id="d3c7c-2903">四個字母後尾隨 5-31 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2903">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="d3c7c-2904">四字母銀行代碼 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2904">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2905">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2905">An optional space</span></span> 
- <span data-ttu-id="d3c7c-2906">4-28 個字母或數字 (基本銀行帳戶號碼 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2906">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="d3c7c-2907">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2907">An optional space</span></span> 
- <span data-ttu-id="d3c7c-2908">1-3 個字母或數字 (BBAN 的其餘部分)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2908">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2909">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2909">Checksum</span></span>

<span data-ttu-id="d3c7c-2910">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2910">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2911">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2911">Definition</span></span>

<span data-ttu-id="d3c7c-2912">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2913">規則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2913">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2914">找到來自於 Keyword_swift 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2914">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2915">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2915">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="d3c7c-2916">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2916">Keyword_swift</span></span>

- <span data-ttu-id="d3c7c-2917">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2917">international organization for standardization 9362</span></span> 
- <span data-ttu-id="d3c7c-2918">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2918">iso 9362</span></span> 
- <span data-ttu-id="d3c7c-2919">iso9362</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2919">iso9362</span></span> 
- <span data-ttu-id="d3c7c-2920">swift\#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2920">swift\#</span></span> 
- <span data-ttu-id="d3c7c-2921">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2921">swiftcode</span></span> 
- <span data-ttu-id="d3c7c-2922">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2922">swiftnumber</span></span> 
- <span data-ttu-id="d3c7c-2923">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2923">swiftroutingnumber</span></span> 
- <span data-ttu-id="d3c7c-2924">swift code
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2924">swift code</span></span> 
- <span data-ttu-id="d3c7c-2925">swift number #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2925">swift number #</span></span> 
- <span data-ttu-id="d3c7c-2926">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2926">swift routing number</span></span> 
- <span data-ttu-id="d3c7c-2927">bic number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2927">bic number</span></span> 
- <span data-ttu-id="d3c7c-2928">bic code
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2928">bic code</span></span> 
- <span data-ttu-id="d3c7c-2929">bic\#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2929">bic \#</span></span> 
- <span data-ttu-id="d3c7c-2930">bic\#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2930">bic\#</span></span> 
- <span data-ttu-id="d3c7c-2931">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2931">bank identifier code</span></span> 
- <span data-ttu-id="d3c7c-2932">標準化9362</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2932">標準化9362</span></span> 
- <span data-ttu-id="d3c7c-2933">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2933">迅速＃</span></span> 
- <span data-ttu-id="d3c7c-2934">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2934">SWIFTコード</span></span> 
- <span data-ttu-id="d3c7c-2935">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2935">SWIFT番号</span></span> 
- <span data-ttu-id="d3c7c-2936">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2936">迅速なルーティング番号</span></span> 
- <span data-ttu-id="d3c7c-2937">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2937">BIC番号</span></span> 
- <span data-ttu-id="d3c7c-2938">BICコード
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2938">BICコード</span></span> 
- <span data-ttu-id="d3c7c-2939">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2939">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="d3c7c-2940">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2940">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="d3c7c-2941">rapide\#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2941">rapide \#</span></span> 
- <span data-ttu-id="d3c7c-2942">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2942">code SWIFT</span></span> 
- <span data-ttu-id="d3c7c-2943">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2943">le numéro de swift</span></span> 
- <span data-ttu-id="d3c7c-2944">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2944">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="d3c7c-2945">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2945">le numéro BIC</span></span> 
- <span data-ttu-id="d3c7c-2946">\#BIC</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2946">\# BIC</span></span> 
- <span data-ttu-id="d3c7c-2947">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2947">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="d3c7c-2948">台灣身分證</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2948">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2949">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2949">Format</span></span>

<span data-ttu-id="d3c7c-2950">一個字母 後尾隨九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2950">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2951">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2951">Pattern</span></span>

<span data-ttu-id="d3c7c-2952">一個字母 後尾隨九位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2952">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="d3c7c-2953">一個字母 (英文、不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2953">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-2954">數字 "1" 或 "2"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2954">The digit "1" or "2"</span></span> 
- <span data-ttu-id="d3c7c-2955">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2955">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2956">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2956">Checksum</span></span>

<span data-ttu-id="d3c7c-2957">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2957">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2958">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2958">Definition</span></span>

<span data-ttu-id="d3c7c-2959">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2959">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2960">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2960">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2961">找到來自於 Keyword_taiwanese_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2961">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="d3c7c-2962">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2962">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2963">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2963">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="d3c7c-2964">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2964">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="d3c7c-2965">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2965">身份證字號</span></span> 
- <span data-ttu-id="d3c7c-2966">身份證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2966">身份證</span></span> 
- <span data-ttu-id="d3c7c-2967">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2967">身份證號碼</span></span> 
- <span data-ttu-id="d3c7c-2968">身份證號
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2968">身份證號</span></span> 
- <span data-ttu-id="d3c7c-2969">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2969">身分證字號</span></span> 
- <span data-ttu-id="d3c7c-2970">身分證 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2970">身分證</span></span> 
- <span data-ttu-id="d3c7c-2971">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2971">身分證號碼</span></span> 
- <span data-ttu-id="d3c7c-2972">身份證號
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2972">身份證號</span></span> 
- <span data-ttu-id="d3c7c-2973">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2973">身分證統一編號</span></span> 
- <span data-ttu-id="d3c7c-2974">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2974">國民身分證統一編號</span></span> 
- <span data-ttu-id="d3c7c-2975">簽名
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2975">簽名</span></span> 
- <span data-ttu-id="d3c7c-2976">蓋章
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2976">蓋章</span></span> 
- <span data-ttu-id="d3c7c-2977">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2977">簽名或蓋章</span></span> 
- <span data-ttu-id="d3c7c-2978">簽章</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2978">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="d3c7c-2979">	台灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2979">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-2980">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2980">Format</span></span>

- <span data-ttu-id="d3c7c-2981">生物特徵護照號碼： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2981">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="d3c7c-2982">非生物特徵護照號碼： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2982">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-2983">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2983">Pattern</span></span>
<span data-ttu-id="d3c7c-2984">生物特徵護照號碼：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2984">Biometric passport number:</span></span>
- <span data-ttu-id="d3c7c-2985">數字 "3" </span><span class="sxs-lookup"><span data-stu-id="d3c7c-2985">The digit "3"</span></span> 
- <span data-ttu-id="d3c7c-2986">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2986">Eight digits</span></span>

<span data-ttu-id="d3c7c-2987">非生物特徵護照號碼：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2987">Non-biometric passport number:</span></span>
- <span data-ttu-id="d3c7c-2988">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2988">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-2989">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2989">Checksum</span></span>

<span data-ttu-id="d3c7c-2990">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2990">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-2991">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2991">Definition</span></span>

<span data-ttu-id="d3c7c-2992">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2992">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-2993">規則運算式 Regex_taiwan_passport 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2993">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-2994">從 Keyword_taiwan_passport 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2994">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-2995">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2995">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="d3c7c-2996">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2996">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="d3c7c-2997">中華民國護照號碼
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2997">ROC passport number</span></span> 
- <span data-ttu-id="d3c7c-2998">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2998">Passport number</span></span> 
- <span data-ttu-id="d3c7c-2999">Passport 無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-2999">Passport no</span></span> 
- <span data-ttu-id="d3c7c-3000">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3000">Passport Num</span></span> 
- <span data-ttu-id="d3c7c-3001">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3001">Passport #</span></span> 
- <span data-ttu-id="d3c7c-3002">护照
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3002">护照</span></span> 
- <span data-ttu-id="d3c7c-3003">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3003">中華民國護照</span></span> 
- <span data-ttu-id="d3c7c-3004">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3004">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="d3c7c-3005">Taiwan Resident Certificate (ARC/TARC) Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3005">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3006">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3006">Format</span></span>

<span data-ttu-id="d3c7c-3007">10 個字母和數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3007">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3008">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3008">Pattern</span></span>

<span data-ttu-id="d3c7c-3009">10 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3009">10 letters and digits:</span></span>
- <span data-ttu-id="d3c7c-3010">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3010">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="d3c7c-3011">八位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3011">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3012">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3012">Checksum</span></span>

<span data-ttu-id="d3c7c-3013">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3013">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3014">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3014">Definition</span></span>

<span data-ttu-id="d3c7c-3015">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3015">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3016">規則運算式 Regex_taiwan_resident_certificate 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3016">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3017">從 Keyword_taiwan_resident_certificate 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3017">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-3018">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3018">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="d3c7c-3019">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3019">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="d3c7c-3020">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3020">Resident Certificate</span></span> 
- <span data-ttu-id="d3c7c-3021">常駐居民登記 Cert</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3021">Resident Cert</span></span> 
- <span data-ttu-id="d3c7c-3022">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3022">Resident Cert.</span></span> 
- <span data-ttu-id="d3c7c-3023">識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3023">Identification card</span></span> 
- <span data-ttu-id="d3c7c-3024">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3024">Alien Resident Certificate</span></span> 
- <span data-ttu-id="d3c7c-3025">ARC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3025">ARC</span></span> 
- <span data-ttu-id="d3c7c-3026">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3026">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="d3c7c-3027">TARC
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3027">TARC</span></span> 
- <span data-ttu-id="d3c7c-3028">居留證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3028">居留證</span></span> 
- <span data-ttu-id="d3c7c-3029">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3029">外僑居留證</span></span> 
- <span data-ttu-id="d3c7c-3030">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3030">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="d3c7c-3031">泰文母體識別程式碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3031">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3032">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3032">Format</span></span>

<span data-ttu-id="d3c7c-3033">13 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3033">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3034">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3034">Pattern</span></span>

<span data-ttu-id="d3c7c-3035">13 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3035">13 digits:</span></span>
- <span data-ttu-id="d3c7c-3036">第一個數字不是 0 或 9</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3036">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="d3c7c-3037">12 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3037">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3038">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3038">Checksum</span></span>

<span data-ttu-id="d3c7c-3039">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3040">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3040">Definition</span></span>

<span data-ttu-id="d3c7c-3041">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3042">函數 Func_Thai_Citizen_Id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3042">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3043">從 Keyword_Thai_Citizen_Id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3043">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="d3c7c-3044">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3044">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3045">函數 Func_Thai_Citizen_Id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3045">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3046">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3046">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="d3c7c-3047">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3047">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="d3c7c-3048">ID Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3048">ID Number</span></span>
- <span data-ttu-id="d3c7c-3049">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3049">Identification Number</span></span>
- <span data-ttu-id="d3c7c-3050">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3050">บัตรประชาชน</span></span>
- <span data-ttu-id="d3c7c-3051">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3051">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="d3c7c-3052">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3052">บัตรประชาชน</span></span>
- <span data-ttu-id="d3c7c-3053">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3053">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="d3c7c-3054">土耳其文的國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3054">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3055">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3055">Format</span></span>

<span data-ttu-id="d3c7c-3056">11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3056">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3057">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3057">Pattern</span></span>

<span data-ttu-id="d3c7c-3058">11 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3058">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3059">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3059">Checksum</span></span>

<span data-ttu-id="d3c7c-3060">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3061">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3061">Definition</span></span>

<span data-ttu-id="d3c7c-3062">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3063">函數 Func_Turkish_National_Id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3063">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3064">從 Keyword_Turkish_National_Id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3064">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="d3c7c-3065">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3065">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3066">函數 Func_Turkish_National_Id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3066">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3067">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3067">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="d3c7c-3068">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3068">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="d3c7c-3069">繁體中文 Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3069">TC Kimlik No</span></span>
- <span data-ttu-id="d3c7c-3070">繁體中文 Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3070">TC Kimlik numarası</span></span>
- <span data-ttu-id="d3c7c-3071">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3071">Vatandaşlık numarası</span></span>
- <span data-ttu-id="d3c7c-3072">Vatandaşlık 無</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3072">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="d3c7c-p141">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3075">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3075">Format</span></span>

<span data-ttu-id="d3c7c-3076">18 個指定格式的字母和數字的組合</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3076">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3077">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3077">Pattern</span></span>

<span data-ttu-id="d3c7c-3078">18 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3078">18 letters and digits:</span></span>
- <span data-ttu-id="d3c7c-3079">五個字母 (不區分大小寫) 或取代字母的數字 "9"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3079">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="d3c7c-3080">一個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3080">One digit</span></span> 
- <span data-ttu-id="d3c7c-3081">以日期格式 DDMMY 表示出生日期的五位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3081">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="d3c7c-3082">兩個字母 (不區分大小寫) 或取代字母的數字 "9"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3082">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="d3c7c-3083">五位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3083">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3084">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3084">Checksum</span></span>

<span data-ttu-id="d3c7c-3085">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3085">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3086">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3086">Definition</span></span>

<span data-ttu-id="d3c7c-3087">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3087">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3088">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3088">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3089">找到來自於 Keyword_uk_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3089">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="d3c7c-3090">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3090">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-3091">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3091">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="d3c7c-3092">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3092">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="d3c7c-3093">DVLA
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3093">DVLA</span></span> 
- <span data-ttu-id="d3c7c-3094">light vans
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3094">light vans</span></span> 
- <span data-ttu-id="d3c7c-3095">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3095">quadbikes</span></span> 
- <span data-ttu-id="d3c7c-3096">motor cars
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3096">motor cars</span></span> 
- <span data-ttu-id="d3c7c-3097">125cc</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3097">125cc</span></span> 
- <span data-ttu-id="d3c7c-3098">sidecar
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3098">sidecar</span></span> 
- <span data-ttu-id="d3c7c-3099">tricycles
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3099">tricycles</span></span> 
- <span data-ttu-id="d3c7c-3100">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3100">motorcycles</span></span> 
- <span data-ttu-id="d3c7c-3101">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3101">photocard licence</span></span> 
- <span data-ttu-id="d3c7c-3102">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3102">learner drivers</span></span> 
- <span data-ttu-id="d3c7c-3103">licence holder
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3103">licence holder</span></span> 
- <span data-ttu-id="d3c7c-3104">licence holders
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3104">licence holders</span></span> 
- <span data-ttu-id="d3c7c-3105">driving licences
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3105">driving licences</span></span> 
- <span data-ttu-id="d3c7c-3106">driving licence
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3106">driving licence</span></span> 
- <span data-ttu-id="d3c7c-3107">dual control car
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3107">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="d3c7c-p142">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3110">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3110">Format</span></span>

<span data-ttu-id="d3c7c-3111">兩個字母後尾隨 1-4 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3111">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3112">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3112">Pattern</span></span>

<span data-ttu-id="d3c7c-3113">兩個字母 (不區分大小寫) 後尾隨 1-4 個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3113">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3114">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3114">Checksum</span></span>

<span data-ttu-id="d3c7c-3115">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3115">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3116">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3116">Definition</span></span>

<span data-ttu-id="d3c7c-3117">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3118">規則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3118">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3119">找到來自於 Keyword_uk_electoral 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3119">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3120">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3120">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="d3c7c-3121">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3121">Keyword_uk_electoral</span></span>

- <span data-ttu-id="d3c7c-3122">council nomination
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3122">council nomination</span></span> 
- <span data-ttu-id="d3c7c-3123">nomination form
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3123">nomination form</span></span> 
- <span data-ttu-id="d3c7c-3124">electoral register

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3124">electoral register</span></span> 
- <span data-ttu-id="d3c7c-3125">electoral roll</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3125">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="d3c7c-p143">英國國民健保服務編號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3128">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3128">Format</span></span>

<span data-ttu-id="d3c7c-3129">以空格分隔的 10-17 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3129">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3130">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3130">Pattern</span></span>

<span data-ttu-id="d3c7c-3131">10-17 位數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3131">10-17 digits:</span></span>
- <span data-ttu-id="d3c7c-3132">3 或 10 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3132">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="d3c7c-3133">一個空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3133">A space</span></span> 
- <span data-ttu-id="d3c7c-3134">三位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3134">Three digits</span></span> 
- <span data-ttu-id="d3c7c-3135">一個空格</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3135">A space</span></span> 
- <span data-ttu-id="d3c7c-3136">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3136">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3137">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3137">Checksum</span></span>

<span data-ttu-id="d3c7c-3138">是</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3138">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3139">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3139">Definition</span></span>

<span data-ttu-id="d3c7c-3140">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3141">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3141">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3142">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3142">One of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-3143">找到來自於 Keyword_uk_nhs_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3143">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="d3c7c-3144">找到來自於 Keyword_uk_nhs_number1 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3144">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="d3c7c-3145">找到來自於 Keyword_uk_nhs_number_dob 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3145">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="d3c7c-3146">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3146">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3147">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3147">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="d3c7c-3148">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3148">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="d3c7c-3149">national health service
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3149">national health service</span></span> 
- <span data-ttu-id="d3c7c-3150">nhs
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3150">nhs</span></span> 
- <span data-ttu-id="d3c7c-3151">health services authority

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3151">health services authority</span></span> 
- <span data-ttu-id="d3c7c-3152">health authority</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3152">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="d3c7c-3153">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3153">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="d3c7c-3154">patient id
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3154">patient id</span></span> 
- <span data-ttu-id="d3c7c-3155">patient identification
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3155">patient identification</span></span> 
- <span data-ttu-id="d3c7c-3156">patient no

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3156">patient no</span></span> 
- <span data-ttu-id="d3c7c-3157">patient number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3157">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="d3c7c-3158">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3158">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="d3c7c-3159">GP</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3159">GP</span></span> 
- <span data-ttu-id="d3c7c-3160">DOB
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3160">DOB</span></span> 
- <span data-ttu-id="d3c7c-3161">D.O.B</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3161">D.O.B</span></span> 
- <span data-ttu-id="d3c7c-3162">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3162">Date of Birth</span></span> 
- <span data-ttu-id="d3c7c-3163">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3163">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="d3c7c-p144">英國國民保險編號 (NINO)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3166">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3166">Format</span></span>

<span data-ttu-id="d3c7c-3167">7 個字元或空格或虛線隔開的 9 字元</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3167">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3168">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3168">Pattern</span></span>

<span data-ttu-id="d3c7c-3169">兩個可能的模式：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3169">Two possible patterns:</span></span>

- <span data-ttu-id="d3c7c-3170">兩個字母 (有效 NINOs 只使用某些字元在此模式會驗證 ； 這個前置詞不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3170">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="d3c7c-3171">六位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3171">Six digits</span></span>
- <span data-ttu-id="d3c7c-3172">''，'B' 'C' 或鎖 ' （例如首碼僅某些字元中允許尾碼; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3172">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="d3c7c-3173">或</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3173">OR</span></span>

- <span data-ttu-id="d3c7c-3174">兩個字母</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3174">Two letters</span></span>
- <span data-ttu-id="d3c7c-3175">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3175">A space or dash</span></span>
- <span data-ttu-id="d3c7c-3176">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3176">Two digits</span></span>
- <span data-ttu-id="d3c7c-3177">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3177">A space or dash</span></span>
- <span data-ttu-id="d3c7c-3178">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3178">Two digits</span></span>
- <span data-ttu-id="d3c7c-3179">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3179">A space or dash</span></span>
- <span data-ttu-id="d3c7c-3180">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3180">Two digits</span></span>
- <span data-ttu-id="d3c7c-3181">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3181">A space or dash</span></span>
- <span data-ttu-id="d3c7c-3182">''，'B' 'C' 或鎖 '</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3182">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3183">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3183">Checksum</span></span>

<span data-ttu-id="d3c7c-3184">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3185">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3185">Definition</span></span>

<span data-ttu-id="d3c7c-3186">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3186">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3187">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3187">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3188">找到來自於 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3188">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="d3c7c-3189">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3190">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3190">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3191">找不到來自於 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3191">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3192">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="d3c7c-3193">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3193">Keyword_uk_nino</span></span>

- <span data-ttu-id="d3c7c-3194">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3194">national insurance number</span></span> 
- <span data-ttu-id="d3c7c-3195">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3195">national insurance contributions</span></span> 
- <span data-ttu-id="d3c7c-3196">protection act
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3196">protection act</span></span> 
- <span data-ttu-id="d3c7c-3197">insurance
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3197">insurance</span></span> 
- <span data-ttu-id="d3c7c-3198">social security number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3198">social security number</span></span> 
- <span data-ttu-id="d3c7c-3199">insurance application
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3199">insurance application</span></span> 
- <span data-ttu-id="d3c7c-3200">medical application
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3200">medical application</span></span> 
- <span data-ttu-id="d3c7c-3201">social insurance
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3201">social insurance</span></span> 
- <span data-ttu-id="d3c7c-3202">medical attention
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3202">medical attention</span></span> 
- <span data-ttu-id="d3c7c-3203">社會安全</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3203">social security</span></span> 
- <span data-ttu-id="d3c7c-3204">great britain
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3204">great britain</span></span> 
- <span data-ttu-id="d3c7c-3205">insurance
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3205">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="d3c7c-p145">美國 / 英國護照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3208">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3208">Format</span></span>

<span data-ttu-id="d3c7c-3209">九位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3209">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3210">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3210">Pattern</span></span>

<span data-ttu-id="d3c7c-3211">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3211">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3212">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3212">Checksum</span></span>

<span data-ttu-id="d3c7c-3213">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3213">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3214">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3214">Definition</span></span>

<span data-ttu-id="d3c7c-3215">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3215">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3216">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3216">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3217">找到來自於 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3217">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-3218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3218">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="d3c7c-3219">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3219">Keyword_passport</span></span>

- <span data-ttu-id="d3c7c-3220">Passport Number</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3220">Passport Number</span></span> 
- <span data-ttu-id="d3c7c-3221">
Passport No</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3221">Passport No</span></span> 
- <span data-ttu-id="d3c7c-3222">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3222">Passport #</span></span> 
- <span data-ttu-id="d3c7c-3223">Passport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3223">Passport#</span></span> 
- <span data-ttu-id="d3c7c-3224">PassportID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3224">PassportID</span></span> 
- <span data-ttu-id="d3c7c-3225">Passportno
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3225">Passportno</span></span> 
- <span data-ttu-id="d3c7c-3226">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3226">passportnumber</span></span> 
- <span data-ttu-id="d3c7c-3227">パスポート</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3227">パスポート</span></span> 
- <span data-ttu-id="d3c7c-3228">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3228">パスポート番号</span></span> 
- <span data-ttu-id="d3c7c-3229">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3229">パスポートのNum</span></span> 
- <span data-ttu-id="d3c7c-3230">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3230">パスポート＃</span></span> 
- <span data-ttu-id="d3c7c-3231">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3231">Numéro de passeport</span></span> 
- <span data-ttu-id="d3c7c-3232">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3232">Passeport n °</span></span> 
- <span data-ttu-id="d3c7c-3233">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3233">Passeport Non</span></span> 
- <span data-ttu-id="d3c7c-3234">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3234">Passeport #</span></span> 
- <span data-ttu-id="d3c7c-3235">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3235">Passeport#</span></span> 
- <span data-ttu-id="d3c7c-3236">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3236">PasseportNon</span></span> 
- <span data-ttu-id="d3c7c-3237">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3237">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="d3c7c-3238">美國銀行帳號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3238">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3239">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3239">Format</span></span>

<span data-ttu-id="d3c7c-3240">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3240">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3241">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3241">Pattern</span></span>

<span data-ttu-id="d3c7c-3242">8-17 個連續數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3242">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3243">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3243">Checksum</span></span>

<span data-ttu-id="d3c7c-3244">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3244">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3245">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3245">Definition</span></span>

<span data-ttu-id="d3c7c-3246">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3247">規則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3247">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3248">找到來自於 Keyword_usa_Bank_Account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3248">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d3c7c-3249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3249">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="d3c7c-3250">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3250">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="d3c7c-3251">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3251">Checking Account Number</span></span> 
- <span data-ttu-id="d3c7c-3252">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3252">Checking Account</span></span> 
- <span data-ttu-id="d3c7c-3253">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3253">Checking Account #</span></span> 
- <span data-ttu-id="d3c7c-3254">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3254">Checking Acct Number</span></span> 
- <span data-ttu-id="d3c7c-3255">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3255">Checking Acct #</span></span> 
- <span data-ttu-id="d3c7c-3256">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3256">Checking Acct No.</span></span> 
- <span data-ttu-id="d3c7c-3257">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3257">Checking Account No.</span></span> 
- <span data-ttu-id="d3c7c-3258">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3258">Bank Account Number</span></span> 
- <span data-ttu-id="d3c7c-3259">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3259">Bank Account #</span></span> 
- <span data-ttu-id="d3c7c-3260">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3260">Bank Acct Number</span></span> 
- <span data-ttu-id="d3c7c-3261">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3261">Bank Acct #</span></span> 
- <span data-ttu-id="d3c7c-3262">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3262">Bank Acct No.</span></span> 
- <span data-ttu-id="d3c7c-3263">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3263">Bank Account No.</span></span> 
- <span data-ttu-id="d3c7c-3264">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3264">Savings Account Number</span></span> 
- <span data-ttu-id="d3c7c-3265">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3265">Savings Account.</span></span> 
- <span data-ttu-id="d3c7c-3266">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3266">Savings Account #</span></span> 
- <span data-ttu-id="d3c7c-3267">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3267">Savings Acct Number</span></span> 
- <span data-ttu-id="d3c7c-3268">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3268">Savings Acct #</span></span> 
- <span data-ttu-id="d3c7c-3269">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3269">Savings Acct No.</span></span> 
- <span data-ttu-id="d3c7c-3270">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3270">Savings Account No.</span></span> 
- <span data-ttu-id="d3c7c-3271">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3271">Debit Account Number</span></span> 
- <span data-ttu-id="d3c7c-3272">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3272">Debit Account</span></span> 
- <span data-ttu-id="d3c7c-3273">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3273">Debit Account #</span></span> 
- <span data-ttu-id="d3c7c-3274">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3274">Debit Acct Number</span></span> 
- <span data-ttu-id="d3c7c-3275">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3275">Debit Acct #</span></span> 
- <span data-ttu-id="d3c7c-3276">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3276">Debit Acct No.</span></span> 
- <span data-ttu-id="d3c7c-3277">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3277">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="d3c7c-3278">美國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3278">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3279">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3279">Format</span></span>

<span data-ttu-id="d3c7c-3280">隨州別不同</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3280">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3281">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3281">Pattern</span></span>

<span data-ttu-id="d3c7c-3282">隨州別不同 -- 以紐約州為例：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3282">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="d3c7c-3283">9 的數字格式像是 ddd ddd ddd 會比對。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3283">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="d3c7c-3284">將不會符合 ddddddddd 類似的九個位數。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3284">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3285">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3285">Checksum</span></span>

<span data-ttu-id="d3c7c-3286">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3287">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3287">Definition</span></span>

<span data-ttu-id="d3c7c-3288">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3289">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3289">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3290">找到來自於 Keyword_[state_name]_drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3290">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d3c7c-3291">從 Keyword_us_drivers_license 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3291">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="d3c7c-3292">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3292">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3293">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3293">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3294">找到來自於 Keyword_[state_name]_drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3294">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d3c7c-3295">找到來自於 Keyword_us_drivers_license_abbreviations 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3295">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="d3c7c-3296">找不到來自於 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3296">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3297">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3297">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="d3c7c-3298">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3298">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="d3c7c-3299">DL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3299">DL</span></span> 
- <span data-ttu-id="d3c7c-3300">DLS</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3300">DLS</span></span> 
- <span data-ttu-id="d3c7c-3301">CDL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3301">CDL</span></span> 
- <span data-ttu-id="d3c7c-3302">CDLS</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3302">CDLS</span></span> 
- <span data-ttu-id="d3c7c-3303">ID</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3303">ID</span></span> 
- <span data-ttu-id="d3c7c-3304">識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3304">IDs</span></span> 
- <span data-ttu-id="d3c7c-3305">DL#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3305">DL#</span></span> 
- <span data-ttu-id="d3c7c-3306">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3306">DLS#</span></span> 
- <span data-ttu-id="d3c7c-3307">CDL#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3307">CDL#</span></span> 
- <span data-ttu-id="d3c7c-3308">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3308">CDLS#</span></span> 
- <span data-ttu-id="d3c7c-3309">ID#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3309">ID#</span></span>
- <span data-ttu-id="d3c7c-3310">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3310">IDs#</span></span> 
- <span data-ttu-id="d3c7c-3311">識別碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3311">ID number</span></span> 
- <span data-ttu-id="d3c7c-3312">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3312">ID numbers</span></span> 
- <span data-ttu-id="d3c7c-3313">LIC</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3313">LIC</span></span> 
- <span data-ttu-id="d3c7c-3314">LIC#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3314">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="d3c7c-3315">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3315">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="d3c7c-3316">DriverLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3316">DriverLic</span></span> 
- <span data-ttu-id="d3c7c-3317">DriverLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3317">DriverLics</span></span> 
- <span data-ttu-id="d3c7c-3318">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3318">DriverLicense</span></span> 
- <span data-ttu-id="d3c7c-3319">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3319">DriverLicenses</span></span> 
- <span data-ttu-id="d3c7c-3320">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3320">Driver Lic</span></span> 
- <span data-ttu-id="d3c7c-3321">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3321">Driver Lics</span></span> 
- <span data-ttu-id="d3c7c-3322">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3322">Driver License</span></span> 
- <span data-ttu-id="d3c7c-3323">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3323">Driver Licenses</span></span> 
- <span data-ttu-id="d3c7c-3324">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3324">DriversLic</span></span> 
- <span data-ttu-id="d3c7c-3325">DriversLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3325">DriversLics</span></span> 
- <span data-ttu-id="d3c7c-3326">執照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3326">DriversLicense</span></span> 
- <span data-ttu-id="d3c7c-3327">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3327">DriversLicenses</span></span> 
- <span data-ttu-id="d3c7c-3328">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3328">Drivers Lic</span></span> 
- <span data-ttu-id="d3c7c-3329">發行的驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3329">Drivers Lics</span></span> 
- <span data-ttu-id="d3c7c-3330">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3330">Drivers License</span></span> 
- <span data-ttu-id="d3c7c-3331">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3331">Drivers Licenses</span></span> 
- <span data-ttu-id="d3c7c-3332">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3332">Driver'Lic</span></span> 
- <span data-ttu-id="d3c7c-3333">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3333">Driver'Lics</span></span> 
- <span data-ttu-id="d3c7c-3334">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3334">Driver'License</span></span> 
- <span data-ttu-id="d3c7c-3335">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3335">Driver'Licenses</span></span> 
- <span data-ttu-id="d3c7c-3336">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3336">Driver' Lic</span></span> 
- <span data-ttu-id="d3c7c-3337">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3337">Driver' Lics</span></span> 
- <span data-ttu-id="d3c7c-3338">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3338">Driver' License</span></span> 
- <span data-ttu-id="d3c7c-3339">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3339">Driver' Licenses</span></span>
- <span data-ttu-id="d3c7c-3340">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3340">Driver'sLic</span></span> 
- <span data-ttu-id="d3c7c-3341">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3341">Driver'sLics</span></span> 
- <span data-ttu-id="d3c7c-3342">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3342">Driver'sLicense</span></span> 
- <span data-ttu-id="d3c7c-3343">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3343">Driver'sLicenses</span></span> 
- <span data-ttu-id="d3c7c-3344">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3344">Driver's Lic</span></span> 
- <span data-ttu-id="d3c7c-3345">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3345">Driver's Lics</span></span> 
- <span data-ttu-id="d3c7c-3346">駕照</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3346">Driver's License</span></span> 
- <span data-ttu-id="d3c7c-3347">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3347">Driver's Licenses</span></span> 
- <span data-ttu-id="d3c7c-3348">identification number
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3348">identification number</span></span> 
- <span data-ttu-id="d3c7c-3349">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3349">identification numbers</span></span> 
- <span data-ttu-id="d3c7c-3350">identification #
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3350">identification #</span></span> 
- <span data-ttu-id="d3c7c-3351">識別碼卡片</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3351">id card</span></span> 
- <span data-ttu-id="d3c7c-3352">識別碼卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3352">id cards</span></span> 
- <span data-ttu-id="d3c7c-3353">識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3353">identification card</span></span> 
- <span data-ttu-id="d3c7c-3354">識別卡</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3354">identification cards</span></span> 
- <span data-ttu-id="d3c7c-3355">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3355">DriverLic#</span></span> 
- <span data-ttu-id="d3c7c-3356">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3356">DriverLics#</span></span> 
- <span data-ttu-id="d3c7c-3357">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3357">DriverLicense#</span></span> 
- <span data-ttu-id="d3c7c-3358">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3358">DriverLicenses#</span></span> 
- <span data-ttu-id="d3c7c-3359">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3359">Driver Lic#</span></span> 
- <span data-ttu-id="d3c7c-3360">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3360">Driver Lics#</span></span> 
- <span data-ttu-id="d3c7c-3361">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3361">Driver License#</span></span> 
- <span data-ttu-id="d3c7c-3362">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3362">Driver Licenses#</span></span> 
- <span data-ttu-id="d3c7c-3363">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3363">DriversLic#</span></span> 
- <span data-ttu-id="d3c7c-3364">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3364">DriversLics#</span></span> 
- <span data-ttu-id="d3c7c-3365">執照 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3365">DriversLicense#</span></span> 
- <span data-ttu-id="d3c7c-3366">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3366">DriversLicenses#</span></span> 
- <span data-ttu-id="d3c7c-3367">發行的驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3367">Drivers Lic#</span></span> 
- <span data-ttu-id="d3c7c-3368">發行的驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3368">Drivers Lics#</span></span> 
- <span data-ttu-id="d3c7c-3369">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3369">Drivers License#</span></span> 
- <span data-ttu-id="d3c7c-3370">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3370">Drivers Licenses#</span></span> 
- <span data-ttu-id="d3c7c-3371">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3371">Driver'Lic#</span></span> 
- <span data-ttu-id="d3c7c-3372">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3372">Driver'Lics#</span></span> 
- <span data-ttu-id="d3c7c-3373">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3373">Driver'License#</span></span> 
- <span data-ttu-id="d3c7c-3374">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3374">Driver'Licenses#</span></span> 
- <span data-ttu-id="d3c7c-3375">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3375">Driver' Lic#</span></span> 
- <span data-ttu-id="d3c7c-3376">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3376">Driver' Lics#</span></span> 
- <span data-ttu-id="d3c7c-3377">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3377">Driver' License#</span></span> 
- <span data-ttu-id="d3c7c-3378">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3378">Driver' Licenses#</span></span> 
- <span data-ttu-id="d3c7c-3379">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3379">Driver'sLic#</span></span> 
- <span data-ttu-id="d3c7c-3380">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3380">Driver'sLics#</span></span> 
- <span data-ttu-id="d3c7c-3381">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3381">Driver'sLicense#</span></span> 
- <span data-ttu-id="d3c7c-3382">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3382">Driver'sLicenses#</span></span> 
- <span data-ttu-id="d3c7c-3383">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3383">Driver's Lic#</span></span> 
- <span data-ttu-id="d3c7c-3384">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3384">Driver's Lics#</span></span> 
- <span data-ttu-id="d3c7c-3385">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3385">Driver's License#</span></span> 
- <span data-ttu-id="d3c7c-3386">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3386">Driver's Licenses#</span></span> 
- <span data-ttu-id="d3c7c-3387">識別碼卡片 #</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3387">id card#</span></span> 
- <span data-ttu-id="d3c7c-3388">id cards#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3388">id cards#</span></span> 
- <span data-ttu-id="d3c7c-3389">identification card#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3389">identification card#</span></span> 
- <span data-ttu-id="d3c7c-3390">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3390">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="d3c7c-3391">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3391">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="d3c7c-3392">州別縮寫 (例如 "NY")
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3392">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="d3c7c-3393">州名稱 (例如 "New York")
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3393">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="d3c7c-3394">美國個別納稅人身分識別碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3394">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3395">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3395">Format</span></span>

<span data-ttu-id="d3c7c-3396">以 "9" 開頭且第四個數字是 "7" 或 "8" 的九位數，可選擇加上空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3396">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3397">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3397">Pattern</span></span>

<span data-ttu-id="d3c7c-3398">格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3398">Formatted:</span></span>
- <span data-ttu-id="d3c7c-3399">數字 "9"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3399">The digit "9"</span></span> 
- <span data-ttu-id="d3c7c-3400">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3400">Two digits</span></span> 
- <span data-ttu-id="d3c7c-3401">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3401">A space or dash</span></span> 
- <span data-ttu-id="d3c7c-3402">一個 "7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3402">A "7" or "8"</span></span> 
- <span data-ttu-id="d3c7c-3403">一個數字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3403">A digit</span></span> 
- <span data-ttu-id="d3c7c-3404">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3404">A space, or dash</span></span> 
- <span data-ttu-id="d3c7c-3405">四位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3405">Four digits</span></span>

<span data-ttu-id="d3c7c-3406">未格式化：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3406">Unformatted:</span></span>
- <span data-ttu-id="d3c7c-3407">數字 "9"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3407">The digit "9"</span></span> 
- <span data-ttu-id="d3c7c-3408">兩位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3408">Two digits</span></span> 
- <span data-ttu-id="d3c7c-3409">一個 "7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3409">A "7" or "8"</span></span> 
- <span data-ttu-id="d3c7c-3410">五位數</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3410">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3411">Checksum</span></span>

<span data-ttu-id="d3c7c-3412">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3412">No</span></span>

### <a name="definition"></a><span data-ttu-id="d3c7c-3413">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3413">Definition</span></span>

<span data-ttu-id="d3c7c-3414">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3415">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3415">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3416">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3416">At least one of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-3417">找到來自於 Keyword_itin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3417">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="d3c7c-3418">函數 Func_us_address 找到正確日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3418">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="d3c7c-3419">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3419">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="d3c7c-3420">找到來自於 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3420">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="d3c7c-3421">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3421">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3422">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3422">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3423">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3423">At least one of the following is true:</span></span>
    - <span data-ttu-id="d3c7c-3424">找到來自於 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3424">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="d3c7c-3425">函數 Func_us_address 找到正確日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3425">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="d3c7c-3426">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3426">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3427">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3427">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="d3c7c-3428">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3428">Keyword_itin</span></span>

- <span data-ttu-id="d3c7c-3429">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3429">taxpayer</span></span> 
- <span data-ttu-id="d3c7c-3430">tax id
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3430">tax id</span></span> 
- <span data-ttu-id="d3c7c-3431">tax identification
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3431">tax identification</span></span> 
- <span data-ttu-id="d3c7c-3432">itin
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3432">itin</span></span> 
- <span data-ttu-id="d3c7c-3433">ssn</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3433">ssn</span></span> 
- <span data-ttu-id="d3c7c-3434">tin
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3434">tin</span></span> 
- <span data-ttu-id="d3c7c-3435">社會安全</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3435">social security</span></span> 
- <span data-ttu-id="d3c7c-3436">tax payer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3436">tax payer</span></span> 
- <span data-ttu-id="d3c7c-3437">itins
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3437">itins</span></span> 
- <span data-ttu-id="d3c7c-3438">taxid

</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3438">taxid</span></span> 
- <span data-ttu-id="d3c7c-3439">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3439">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="d3c7c-3440">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3440">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="d3c7c-3441">License</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3441">License</span></span> 
- <span data-ttu-id="d3c7c-3442">DL</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3442">DL</span></span> 
- <span data-ttu-id="d3c7c-3443">DOB
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3443">DOB</span></span> 
- <span data-ttu-id="d3c7c-3444">出生日期</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3444">Birthdate</span></span> 
- <span data-ttu-id="d3c7c-3445">生日 </span><span class="sxs-lookup"><span data-stu-id="d3c7c-3445">Birthday</span></span> 
- <span data-ttu-id="d3c7c-3446">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3446">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="d3c7c-3447">美國社會安全編號 (SSN)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3447">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="d3c7c-3448">格式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3448">Format</span></span>

<span data-ttu-id="d3c7c-3449">9 位數，可採用格式化或未格式化模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3449">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="d3c7c-3450">SSN 發出 mid 2011 之前，是否具有強式格式設定其中某些部分的數字必須落在有效特定範圍 （但沒有具總和檢查碼）。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3450">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="d3c7c-3451">模式</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3451">Pattern</span></span>

<span data-ttu-id="d3c7c-3452">四個不同的模式 SSNs 尋找四個函數：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3452">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="d3c7c-3453">Func_ssn 都會尋找 SSNs 之前 2011年強式格式格式為虛線或空格 (ddd-dd-dddd OR ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3453">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="d3c7c-3454">Func_unformatted_ssn 都會尋找 SSNs 之前 2011年強式的格式以未格式化為九個連續的數字 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3454">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="d3c7c-3455">Func_randomized_formatted_ssn 都會以虛線或空格 (ddd-dd-dddd OR ddd dd dddd) 格式化的張貼 2011 SSNs</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3455">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="d3c7c-3456">Func_randomized_unformatted_ssn 會尋找已格式化為九個連續的數字 (ddddddddd) 的文章 2011 SSNs</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3456">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="d3c7c-3457">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3457">Checksum</span></span>

<span data-ttu-id="d3c7c-3458">否</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3458">No</span></span>


### <a name="definition"></a><span data-ttu-id="d3c7c-3459">定義</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3459">Definition</span></span>

<span data-ttu-id="d3c7c-3460">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3461">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3461">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3462">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3462">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="d3c7c-3463">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3464">函數 Func_unformatted_ssn 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3464">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3465">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3465">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="d3c7c-3466">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3467">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3467">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3468">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3468">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="d3c7c-3469">函數 Func_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3469">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="d3c7c-3470">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 55%：</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3470">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d3c7c-3471">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3471">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d3c7c-3472">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3472">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="d3c7c-3473">函數 Func_unformatted_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3473">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d3c7c-3474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3474">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="d3c7c-3475">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3475">Keyword_ssn</span></span>

- <span data-ttu-id="d3c7c-3476">Social Security
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3476">Social Security</span></span> 
- <span data-ttu-id="d3c7c-3477">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3477">Social Security#</span></span> 
- <span data-ttu-id="d3c7c-3478">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3478">Soc Sec</span></span> 
- <span data-ttu-id="d3c7c-3479">SSN</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3479">SSN</span></span> 
- <span data-ttu-id="d3c7c-3480">SSNS
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3480">SSNS</span></span> 
- <span data-ttu-id="d3c7c-3481">SSN#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3481">SSN#</span></span> 
- <span data-ttu-id="d3c7c-3482">SS#
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3482">SS#</span></span> 
- <span data-ttu-id="d3c7c-3483">SSID
</span><span class="sxs-lookup"><span data-stu-id="d3c7c-3483">SSID</span></span> 
   

