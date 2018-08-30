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
ms.openlocfilehash: 064606085363ba9de972511642993277451c8ce3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527127"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="c49b6-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="c49b6-104">What the sensitive information types look for</span></span>

<span data-ttu-id="c49b6-p102">Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題列出所有的這些機密資訊類型及顯示新的 DLP 原則會尋找時被每個類型。敏感資訊類型定義由可藉由規則運算式或函數的模式。此外，例如關鍵字和總和檢查碼佐證性證據可用來識別敏感資訊類型。信賴等級和鄰近性也會用於評估程序。</span><span class="sxs-lookup"><span data-stu-id="c49b6-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="c49b6-110">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-111">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-111">Format</span></span>

<span data-ttu-id="c49b6-112">可採用格式化或未格式化模式的 9 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-113">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-113">Pattern</span></span>

<span data-ttu-id="c49b6-114">格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-114">Formatted:</span></span>
- <span data-ttu-id="c49b6-115">以 0、1、2、3、6、7 或 8 開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="c49b6-116">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-116">A hyphen</span></span>
- <span data-ttu-id="c49b6-117">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-117">Four digits</span></span>
- <span data-ttu-id="c49b6-118">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-118">A hyphen</span></span>
- <span data-ttu-id="c49b6-119">一個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-119">A digit</span></span>

<span data-ttu-id="c49b6-120">未格式化： 9 連續的數字開頭為 0、 1、 2、 3、 6、 7 或 8</span><span class="sxs-lookup"><span data-stu-id="c49b6-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="c49b6-121">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-121">Checksum</span></span>

<span data-ttu-id="c49b6-122">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-123">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-123">Definition</span></span>

<span data-ttu-id="c49b6-124">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-126">找到來自於 Keyword_ABA_Routing 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="c49b6-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="c49b6-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="c49b6-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="c49b6-129">aba</span><span class="sxs-lookup"><span data-stu-id="c49b6-129">aba</span></span>
- <span data-ttu-id="c49b6-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="c49b6-130">aba #</span></span>
- <span data-ttu-id="c49b6-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="c49b6-131">aba routing #</span></span>
- <span data-ttu-id="c49b6-132">
aba routing number</span><span class="sxs-lookup"><span data-stu-id="c49b6-132">aba routing number</span></span>
- <span data-ttu-id="c49b6-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="c49b6-133">aba#</span></span>
- <span data-ttu-id="c49b6-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="c49b6-134">abarouting#</span></span>
- <span data-ttu-id="c49b6-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="c49b6-135">aba number</span></span>
- <span data-ttu-id="c49b6-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="c49b6-136">abaroutingnumber</span></span>
- <span data-ttu-id="c49b6-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="c49b6-137">american bank association routing #</span></span>
- <span data-ttu-id="c49b6-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="c49b6-138">american bank association routing number</span></span>
- <span data-ttu-id="c49b6-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="c49b6-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="c49b6-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="c49b6-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="c49b6-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="c49b6-141">bank routing number</span></span>
- <span data-ttu-id="c49b6-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="c49b6-142">bankrouting#</span></span>
- <span data-ttu-id="c49b6-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="c49b6-143">bankroutingnumber</span></span>
- <span data-ttu-id="c49b6-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="c49b6-144">routing transit number</span></span>
- <span data-ttu-id="c49b6-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="c49b6-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="c49b6-146">阿根廷國民識別 (DNI) 碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-147">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-147">Format</span></span>

<span data-ttu-id="c49b6-148">以句點分隔的八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-149">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-149">Pattern</span></span>

<span data-ttu-id="c49b6-150">八位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-150">Eight digits:</span></span>
- <span data-ttu-id="c49b6-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-151">Two digits</span></span>
- <span data-ttu-id="c49b6-152">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-152">A period</span></span>
- <span data-ttu-id="c49b6-153">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-153">Three digits</span></span>
- <span data-ttu-id="c49b6-154">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-154">A period</span></span>
- <span data-ttu-id="c49b6-155">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-156">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-156">Checksum</span></span>

<span data-ttu-id="c49b6-157">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-158">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-158">Definition</span></span>

<span data-ttu-id="c49b6-159">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-160">規則運算式 Regex_argentina_national_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-161">從 Keyword_argentina_national_id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="c49b6-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="c49b6-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="c49b6-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="c49b6-165">Identity</span></span> 
- <span data-ttu-id="c49b6-166">識別國民身分識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="c49b6-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="c49b6-167">DNI</span></span> 
- <span data-ttu-id="c49b6-168">NIC 的人員國民登錄</span><span class="sxs-lookup"><span data-stu-id="c49b6-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="c49b6-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="c49b6-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="c49b6-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="c49b6-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="c49b6-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="c49b6-171">Identidad</span></span> 
- <span data-ttu-id="c49b6-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="c49b6-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="c49b6-173">澳洲銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-174">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-174">Format</span></span>

<span data-ttu-id="c49b6-175">包含或不含銀行代號的 6-10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-176">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-176">Pattern</span></span>

<span data-ttu-id="c49b6-p103">帳戶號碼為 6-10 位數。澳洲銀行狀態分支號碼：</span><span class="sxs-lookup"><span data-stu-id="c49b6-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="c49b6-179">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-179">Three digits</span></span> 
- <span data-ttu-id="c49b6-180">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-180">A hyphen</span></span> 
- <span data-ttu-id="c49b6-181">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-182">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-182">Checksum</span></span>

<span data-ttu-id="c49b6-183">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-184">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-184">Definition</span></span>

<span data-ttu-id="c49b6-185">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-186">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="c49b6-187">找到來自於 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="c49b6-188">規則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="c49b6-189">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-190">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="c49b6-191">找到來自於 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="c49b6-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="c49b6-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="c49b6-194">swift bank code</span></span>
- <span data-ttu-id="c49b6-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="c49b6-195">correspondent bank</span></span>
- <span data-ttu-id="c49b6-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="c49b6-196">base currency</span></span>
- <span data-ttu-id="c49b6-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="c49b6-197">usa account</span></span>
- <span data-ttu-id="c49b6-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="c49b6-198">holder address</span></span>
- <span data-ttu-id="c49b6-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="c49b6-199">bank address</span></span>
- <span data-ttu-id="c49b6-200">
information account</span><span class="sxs-lookup"><span data-stu-id="c49b6-200">information account</span></span>
- <span data-ttu-id="c49b6-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="c49b6-201">fund transfers</span></span>
- <span data-ttu-id="c49b6-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="c49b6-202">bank charges</span></span>
- <span data-ttu-id="c49b6-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="c49b6-203">bank details</span></span>
- <span data-ttu-id="c49b6-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="c49b6-204">banking information</span></span>
- <span data-ttu-id="c49b6-205">
full names</span><span class="sxs-lookup"><span data-stu-id="c49b6-205">full names</span></span>
- <span data-ttu-id="c49b6-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="c49b6-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="c49b6-207">澳洲駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-208">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-208">Format</span></span>

<span data-ttu-id="c49b6-209">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-210">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-210">Pattern</span></span>

<span data-ttu-id="c49b6-211">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="c49b6-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="c49b6-212">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-213">Two digits</span></span> 
- <span data-ttu-id="c49b6-214">五個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="c49b6-215">OR</span><span class="sxs-lookup"><span data-stu-id="c49b6-215">OR</span></span>

- <span data-ttu-id="c49b6-216">1-2 選用字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-217">4-9 digits</span></span>

<span data-ttu-id="c49b6-218">OR</span><span class="sxs-lookup"><span data-stu-id="c49b6-218">OR</span></span>

- <span data-ttu-id="c49b6-219">九個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-220">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-220">Checksum</span></span>

<span data-ttu-id="c49b6-221">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-222">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-222">Definition</span></span>

<span data-ttu-id="c49b6-223">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-224">規則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-225">找到來自於 Keyword_australia_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="c49b6-226">找不到來自於 Keyword_australia_drivers_license_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="c49b6-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="c49b6-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="c49b6-229">international driving permits</span></span>
- <span data-ttu-id="c49b6-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="c49b6-230">australian automobile association</span></span>
- <span data-ttu-id="c49b6-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="c49b6-231">sydney nsw</span></span>
- <span data-ttu-id="c49b6-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="c49b6-232">international driving permit</span></span>
- <span data-ttu-id="c49b6-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="c49b6-233">DriverLicence</span></span>
- <span data-ttu-id="c49b6-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="c49b6-234">DriverLicences</span></span>
- <span data-ttu-id="c49b6-235">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-235">Driver Lic</span></span>
- <span data-ttu-id="c49b6-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-236">Driver Licence</span></span>
- <span data-ttu-id="c49b6-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-237">Driver Licences</span></span>
- <span data-ttu-id="c49b6-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-238">DriversLic</span></span>
- <span data-ttu-id="c49b6-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="c49b6-239">DriversLicence</span></span>
- <span data-ttu-id="c49b6-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="c49b6-240">DriversLicences</span></span>
- <span data-ttu-id="c49b6-241">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-241">Drivers Lic</span></span>
- <span data-ttu-id="c49b6-242">發行的驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-242">Drivers Lics</span></span>
- <span data-ttu-id="c49b6-243">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-243">Drivers Licence</span></span>
- <span data-ttu-id="c49b6-244">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-244">Drivers Licences</span></span>
- <span data-ttu-id="c49b6-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-245">Driver'Lic</span></span>
- <span data-ttu-id="c49b6-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-246">Driver'Lics</span></span>
- <span data-ttu-id="c49b6-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="c49b6-247">Driver'Licence</span></span>
- <span data-ttu-id="c49b6-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="c49b6-248">Driver'Licences</span></span>
- <span data-ttu-id="c49b6-249">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-249">Driver' Lic</span></span>
- <span data-ttu-id="c49b6-250">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-250">Driver' Lics</span></span>
- <span data-ttu-id="c49b6-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-251">Driver' Licence</span></span>
- <span data-ttu-id="c49b6-252">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-252">Driver' Licences</span></span>
- <span data-ttu-id="c49b6-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-253">Driver'sLic</span></span>
- <span data-ttu-id="c49b6-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-254">Driver'sLics</span></span>
- <span data-ttu-id="c49b6-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="c49b6-255">Driver'sLicence</span></span>
- <span data-ttu-id="c49b6-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="c49b6-256">Driver'sLicences</span></span>
- <span data-ttu-id="c49b6-257">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-257">Driver's Lic</span></span>
- <span data-ttu-id="c49b6-258">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-258">Driver's Lics</span></span>
- <span data-ttu-id="c49b6-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-259">Driver's Licence</span></span>
- <span data-ttu-id="c49b6-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-260">Driver's Licences</span></span>
- <span data-ttu-id="c49b6-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-261">DriverLic#</span></span>
- <span data-ttu-id="c49b6-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-262">DriverLics#</span></span>
- <span data-ttu-id="c49b6-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="c49b6-263">DriverLicence#</span></span>
- <span data-ttu-id="c49b6-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="c49b6-264">DriverLicences#</span></span>
- <span data-ttu-id="c49b6-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="c49b6-265">Driver Lic#</span></span>
- <span data-ttu-id="c49b6-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-266">Driver Lics#</span></span>
- <span data-ttu-id="c49b6-267">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-267">Driver Licence#</span></span>
- <span data-ttu-id="c49b6-268">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-268">Driver Licences#</span></span>
- <span data-ttu-id="c49b6-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-269">DriversLic#</span></span>
- <span data-ttu-id="c49b6-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-270">DriversLics#</span></span>
- <span data-ttu-id="c49b6-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="c49b6-271">DriversLicence#</span></span>
- <span data-ttu-id="c49b6-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="c49b6-272">DriversLicences#</span></span>
- <span data-ttu-id="c49b6-273">發行的驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-273">Drivers Lic#</span></span>
- <span data-ttu-id="c49b6-274">發行的驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-274">Drivers Lics#</span></span>
- <span data-ttu-id="c49b6-275">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-275">Drivers Licence#</span></span>
- <span data-ttu-id="c49b6-276">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-276">Drivers Licences#</span></span>
- <span data-ttu-id="c49b6-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-277">Driver'Lic#</span></span>
- <span data-ttu-id="c49b6-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-278">Driver'Lics#</span></span>
- <span data-ttu-id="c49b6-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-279">Driver'Licence#</span></span>
- <span data-ttu-id="c49b6-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-280">Driver'Licences#</span></span>
- <span data-ttu-id="c49b6-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-281">Driver' Lic#</span></span>
- <span data-ttu-id="c49b6-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-282">Driver' Lics#</span></span>
- <span data-ttu-id="c49b6-283">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-283">Driver' Licence#</span></span>
- <span data-ttu-id="c49b6-284">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-284">Driver' Licences#</span></span>
- <span data-ttu-id="c49b6-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-285">Driver'sLic#</span></span>
- <span data-ttu-id="c49b6-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-286">Driver'sLics#</span></span>
- <span data-ttu-id="c49b6-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="c49b6-287">Driver'sLicence#</span></span>
- <span data-ttu-id="c49b6-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="c49b6-288">Driver'sLicences#</span></span>
- <span data-ttu-id="c49b6-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-289">Driver's Lic#</span></span>
- <span data-ttu-id="c49b6-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-290">Driver's Lics#</span></span>
- <span data-ttu-id="c49b6-291">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-291">Driver's Licence#</span></span>
- <span data-ttu-id="c49b6-292">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="c49b6-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="c49b6-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="c49b6-294">aaa</span><span class="sxs-lookup"><span data-stu-id="c49b6-294">aaa</span></span>
- <span data-ttu-id="c49b6-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="c49b6-295">DriverLicense</span></span>
- <span data-ttu-id="c49b6-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-296">DriverLicenses</span></span>
- <span data-ttu-id="c49b6-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-297">Driver License</span></span>
- <span data-ttu-id="c49b6-298">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-298">Driver Licenses</span></span>
- <span data-ttu-id="c49b6-299">執照</span><span class="sxs-lookup"><span data-stu-id="c49b6-299">DriversLicense</span></span>
- <span data-ttu-id="c49b6-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-300">DriversLicenses</span></span>
- <span data-ttu-id="c49b6-301">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-301">Drivers License</span></span>
- <span data-ttu-id="c49b6-302">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-302">Drivers Licenses</span></span>
- <span data-ttu-id="c49b6-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="c49b6-303">Driver'License</span></span>
- <span data-ttu-id="c49b6-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-304">Driver'Licenses</span></span>
- <span data-ttu-id="c49b6-305">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-305">Driver' License</span></span>
- <span data-ttu-id="c49b6-306">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-306">Driver' Licenses</span></span>
- <span data-ttu-id="c49b6-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="c49b6-307">Driver'sLicense</span></span>
- <span data-ttu-id="c49b6-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-308">Driver'sLicenses</span></span>
- <span data-ttu-id="c49b6-309">駕照</span><span class="sxs-lookup"><span data-stu-id="c49b6-309">Driver's License</span></span>
- <span data-ttu-id="c49b6-310">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-310">Driver's Licenses</span></span>
- <span data-ttu-id="c49b6-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="c49b6-311">DriverLicense#</span></span>
- <span data-ttu-id="c49b6-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-312">DriverLicenses#</span></span>
- <span data-ttu-id="c49b6-313">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-313">Driver License#</span></span>
- <span data-ttu-id="c49b6-314">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-314">Driver Licenses#</span></span>
- <span data-ttu-id="c49b6-315">執照 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-315">DriversLicense#</span></span>
- <span data-ttu-id="c49b6-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-316">DriversLicenses#</span></span>
- <span data-ttu-id="c49b6-317">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-317">Drivers License#</span></span>
- <span data-ttu-id="c49b6-318">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-318">Drivers Licenses#</span></span>
- <span data-ttu-id="c49b6-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-319">Driver'License#</span></span>
- <span data-ttu-id="c49b6-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-320">Driver'Licenses#</span></span>
- <span data-ttu-id="c49b6-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-321">Driver' License#</span></span>
- <span data-ttu-id="c49b6-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-322">Driver' Licenses#</span></span>
- <span data-ttu-id="c49b6-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="c49b6-323">Driver'sLicense#</span></span>
- <span data-ttu-id="c49b6-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="c49b6-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-325">Driver's License#</span></span>
- <span data-ttu-id="c49b6-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="c49b6-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="c49b6-327">澳洲醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-328">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-328">Format</span></span>

<span data-ttu-id="c49b6-329">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-330">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-330">Pattern</span></span>

<span data-ttu-id="c49b6-331">10-11 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-331">10-11 digits:</span></span>
- <span data-ttu-id="c49b6-332">第一個數字在 2-6 的範圍內</span><span class="sxs-lookup"><span data-stu-id="c49b6-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="c49b6-333">第九個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="c49b6-334">第十個數字是簽發碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="c49b6-335">第十一個數字 (選用) 是個人碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-336">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-336">Checksum</span></span>

<span data-ttu-id="c49b6-337">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-338">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-338">Definition</span></span>

<span data-ttu-id="c49b6-339">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-340">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-341">找到來自於 Keyword_Australia_Medical_Account_Number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="c49b6-342">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-342">The checksum passes.</span></span>

<span data-ttu-id="c49b6-343">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-344">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-345">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-346">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="c49b6-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="c49b6-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="c49b6-348">bank account details</span></span>
- <span data-ttu-id="c49b6-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="c49b6-349">medicare payments</span></span>
- <span data-ttu-id="c49b6-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="c49b6-350">mortgage account</span></span>
- <span data-ttu-id="c49b6-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="c49b6-351">bank payments</span></span>
- <span data-ttu-id="c49b6-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="c49b6-352">information branch</span></span>
- <span data-ttu-id="c49b6-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="c49b6-353">credit card loan</span></span>
- <span data-ttu-id="c49b6-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="c49b6-354">department of human services</span></span>
- <span data-ttu-id="c49b6-355">本機服務</span><span class="sxs-lookup"><span data-stu-id="c49b6-355">local service</span></span>
- <span data-ttu-id="c49b6-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="c49b6-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="c49b6-357">澳洲護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-358">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-358">Format</span></span>

<span data-ttu-id="c49b6-359">字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-360">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-360">Pattern</span></span>

<span data-ttu-id="c49b6-361">一個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-362">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-362">Checksum</span></span>

<span data-ttu-id="c49b6-363">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-364">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-364">Definition</span></span>

<span data-ttu-id="c49b6-365">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-366">規則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-367">從 Keyword_passport 或 Keyword_australia_passport_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-368">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="c49b6-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-369">Keyword_passport</span></span>

- <span data-ttu-id="c49b6-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-370">Passport Number</span></span>
- <span data-ttu-id="c49b6-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="c49b6-371">Passport No</span></span>
- <span data-ttu-id="c49b6-372">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-372">Passport #</span></span>
- <span data-ttu-id="c49b6-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-373">Passport#</span></span>
- <span data-ttu-id="c49b6-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="c49b6-374">PassportID</span></span>
- <span data-ttu-id="c49b6-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="c49b6-375">Passportno</span></span>
- <span data-ttu-id="c49b6-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-376">passportnumber</span></span>
- <span data-ttu-id="c49b6-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="c49b6-377">パスポート</span></span>
- <span data-ttu-id="c49b6-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-378">パスポート番号</span></span>
- <span data-ttu-id="c49b6-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-379">パスポートのNum</span></span>
- <span data-ttu-id="c49b6-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-380">パスポート ＃</span></span> 
- <span data-ttu-id="c49b6-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="c49b6-381">Numéro de passeport</span></span>
- <span data-ttu-id="c49b6-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="c49b6-382">Passeport n °</span></span>
- <span data-ttu-id="c49b6-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="c49b6-383">Passeport Non</span></span>
- <span data-ttu-id="c49b6-384">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-384">Passeport #</span></span>
- <span data-ttu-id="c49b6-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-385">Passeport#</span></span>
- <span data-ttu-id="c49b6-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="c49b6-386">PasseportNon</span></span>
- <span data-ttu-id="c49b6-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="c49b6-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="c49b6-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="c49b6-389">passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-389">passport</span></span>
- <span data-ttu-id="c49b6-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="c49b6-390">passport details</span></span>
- <span data-ttu-id="c49b6-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="c49b6-391">immigration and citizenship</span></span>
- <span data-ttu-id="c49b6-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="c49b6-392">commonwealth of australia</span></span>
- <span data-ttu-id="c49b6-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="c49b6-393">department of immigration</span></span>
- <span data-ttu-id="c49b6-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="c49b6-394">residential address</span></span>
- <span data-ttu-id="c49b6-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="c49b6-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="c49b6-396">visa
</span><span class="sxs-lookup"><span data-stu-id="c49b6-396">visa</span></span>
- <span data-ttu-id="c49b6-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="c49b6-397">national identity card</span></span>
- <span data-ttu-id="c49b6-398">護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-398">passport number</span></span>
- <span data-ttu-id="c49b6-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="c49b6-399">travel document</span></span>
- <span data-ttu-id="c49b6-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="c49b6-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="c49b6-401">澳洲稅籍編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-402">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-402">Format</span></span>

<span data-ttu-id="c49b6-403">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-404">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-404">Pattern</span></span>

<span data-ttu-id="c49b6-405">通常會有如下空格的 8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="c49b6-406">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-406">Three digits</span></span> 
- <span data-ttu-id="c49b6-407">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-407">An optional space</span></span> 
- <span data-ttu-id="c49b6-408">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-408">Three digits</span></span> 
- <span data-ttu-id="c49b6-409">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-409">An optional space</span></span> 
- <span data-ttu-id="c49b6-410">2-3 位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-411">Checksum</span></span>

<span data-ttu-id="c49b6-412">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-413">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-413">Definition</span></span>

<span data-ttu-id="c49b6-414">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-415">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-416">找不到來自於 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="c49b6-417">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-418">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="c49b6-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="c49b6-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="c49b6-420">australian business number</span></span>
- <span data-ttu-id="c49b6-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="c49b6-421">marginal tax rate</span></span>
- <span data-ttu-id="c49b6-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="c49b6-422">medicare levy</span></span>
- <span data-ttu-id="c49b6-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="c49b6-423">portfolio number</span></span>
- <span data-ttu-id="c49b6-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="c49b6-424">service veterans</span></span>
- <span data-ttu-id="c49b6-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="c49b6-425">withholding tax</span></span>
- <span data-ttu-id="c49b6-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="c49b6-426">individual tax return</span></span>
- <span data-ttu-id="c49b6-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="c49b6-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="c49b6-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="c49b6-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="c49b6-429">00000000</span><span class="sxs-lookup"><span data-stu-id="c49b6-429">00000000</span></span>
- <span data-ttu-id="c49b6-430">11111111</span><span class="sxs-lookup"><span data-stu-id="c49b6-430">11111111</span></span>
- <span data-ttu-id="c49b6-431">22222222</span><span class="sxs-lookup"><span data-stu-id="c49b6-431">22222222</span></span>
- <span data-ttu-id="c49b6-432">33333333</span><span class="sxs-lookup"><span data-stu-id="c49b6-432">33333333</span></span>
- <span data-ttu-id="c49b6-433">44444444</span><span class="sxs-lookup"><span data-stu-id="c49b6-433">44444444</span></span>
- <span data-ttu-id="c49b6-434">55555555</span><span class="sxs-lookup"><span data-stu-id="c49b6-434">55555555</span></span>
- <span data-ttu-id="c49b6-435">66666666</span><span class="sxs-lookup"><span data-stu-id="c49b6-435">66666666</span></span>
- <span data-ttu-id="c49b6-436">77777777</span><span class="sxs-lookup"><span data-stu-id="c49b6-436">77777777</span></span>
- <span data-ttu-id="c49b6-437">88888888</span><span class="sxs-lookup"><span data-stu-id="c49b6-437">88888888</span></span>
- <span data-ttu-id="c49b6-438">99999999</span><span class="sxs-lookup"><span data-stu-id="c49b6-438">99999999</span></span>
- <span data-ttu-id="c49b6-439">000000000</span><span class="sxs-lookup"><span data-stu-id="c49b6-439">000000000</span></span>
- <span data-ttu-id="c49b6-440">111111111</span><span class="sxs-lookup"><span data-stu-id="c49b6-440">111111111</span></span>
- <span data-ttu-id="c49b6-441">222222222</span><span class="sxs-lookup"><span data-stu-id="c49b6-441">222222222</span></span>
- <span data-ttu-id="c49b6-442">333333333</span><span class="sxs-lookup"><span data-stu-id="c49b6-442">333333333</span></span>
- <span data-ttu-id="c49b6-443">444444444</span><span class="sxs-lookup"><span data-stu-id="c49b6-443">444444444</span></span>
- <span data-ttu-id="c49b6-444">555555555</span><span class="sxs-lookup"><span data-stu-id="c49b6-444">555555555</span></span>
- <span data-ttu-id="c49b6-445">666666666</span><span class="sxs-lookup"><span data-stu-id="c49b6-445">666666666</span></span>
- <span data-ttu-id="c49b6-446">777777777</span><span class="sxs-lookup"><span data-stu-id="c49b6-446">777777777</span></span>
- <span data-ttu-id="c49b6-447">888888888</span><span class="sxs-lookup"><span data-stu-id="c49b6-447">888888888</span></span>
- <span data-ttu-id="c49b6-448">999999999</span><span class="sxs-lookup"><span data-stu-id="c49b6-448">999999999</span></span>
- <span data-ttu-id="c49b6-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="c49b6-449">0000000000</span></span>
- <span data-ttu-id="c49b6-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="c49b6-450">1111111111</span></span>
- <span data-ttu-id="c49b6-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="c49b6-451">2222222222</span></span>
- <span data-ttu-id="c49b6-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="c49b6-452">3333333333</span></span>
- <span data-ttu-id="c49b6-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="c49b6-453">4444444444</span></span>
- <span data-ttu-id="c49b6-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="c49b6-454">5555555555</span></span>
- <span data-ttu-id="c49b6-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="c49b6-455">6666666666</span></span>
- <span data-ttu-id="c49b6-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="c49b6-456">7777777777</span></span>
- <span data-ttu-id="c49b6-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="c49b6-457">8888888888</span></span>
- <span data-ttu-id="c49b6-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="c49b6-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="c49b6-459">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-460">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-460">Format</span></span>

<span data-ttu-id="c49b6-461">11 位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="c49b6-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-462">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-462">Pattern</span></span>

<span data-ttu-id="c49b6-463">11 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="c49b6-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="c49b6-464">六位數加上兩個句點組合成 YY.MM.DD 的格式代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="c49b6-465">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-465">A hyphen</span></span> 
- <span data-ttu-id="c49b6-466">三個連續數字 (奇數男生，偶數女生) </span><span class="sxs-lookup"><span data-stu-id="c49b6-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="c49b6-467">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-467">A period</span></span> 
- <span data-ttu-id="c49b6-468">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-469">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-469">Checksum</span></span>

<span data-ttu-id="c49b6-470">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-471">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-471">Definition</span></span>

<span data-ttu-id="c49b6-472">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-473">函數 Func_belgium_national_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-474">從 Keyword_belgium_national_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="c49b6-475">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-476">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="c49b6-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="c49b6-478">Identity</span><span class="sxs-lookup"><span data-stu-id="c49b6-478">Identity</span></span>
- <span data-ttu-id="c49b6-479">Registration</span><span class="sxs-lookup"><span data-stu-id="c49b6-479">Registration</span></span>
- <span data-ttu-id="c49b6-480">Identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-480">Identification</span></span> 
- <span data-ttu-id="c49b6-481">ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-481">ID</span></span> 
- <span data-ttu-id="c49b6-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="c49b6-482">Identiteitskaart</span></span>
- <span data-ttu-id="c49b6-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="c49b6-483">Registratie nummer</span></span> 
- <span data-ttu-id="c49b6-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-484">Identificatie nummer</span></span> 
- <span data-ttu-id="c49b6-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="c49b6-485">Identiteit</span></span>
- <span data-ttu-id="c49b6-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="c49b6-486">Registratie</span></span>
- <span data-ttu-id="c49b6-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="c49b6-487">Identificatie</span></span> 
- <span data-ttu-id="c49b6-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="c49b6-488">Carte d’identité</span></span> 
- <span data-ttu-id="c49b6-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="c49b6-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="c49b6-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-490">numéro d'identification</span></span>
- <span data-ttu-id="c49b6-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="c49b6-491">identité</span></span> 
- <span data-ttu-id="c49b6-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="c49b6-492">inscription</span></span> 
- <span data-ttu-id="c49b6-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="c49b6-493">Identifikation</span></span>
- <span data-ttu-id="c49b6-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="c49b6-494">Identifizierung</span></span>
- <span data-ttu-id="c49b6-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-495">Identifikationsnummer</span></span>
- <span data-ttu-id="c49b6-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="c49b6-496">Personalausweis</span></span>
- <span data-ttu-id="c49b6-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="c49b6-497">Registrierung</span></span>
- <span data-ttu-id="c49b6-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="c49b6-499">巴西 CPF 碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-500">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-500">Format</span></span>

<span data-ttu-id="c49b6-501">11 位數包含檢查碼，可格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="c49b6-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-502">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-502">Pattern</span></span>

<span data-ttu-id="c49b6-503">格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-503">Formatted:</span></span>
- <span data-ttu-id="c49b6-504">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-504">Three digits</span></span> 
- <span data-ttu-id="c49b6-505">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-505">A period</span></span> 
- <span data-ttu-id="c49b6-506">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-506">Three digits</span></span> 
- <span data-ttu-id="c49b6-507">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-507">A period</span></span> 
- <span data-ttu-id="c49b6-508">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-508">Three digits</span></span> 
- <span data-ttu-id="c49b6-509">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-509">A hyphen</span></span> 
- <span data-ttu-id="c49b6-510">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-510">Two digits which are check digits</span></span>

<span data-ttu-id="c49b6-511">未格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-511">Unformatted:</span></span>
- <span data-ttu-id="c49b6-512">11 位數，最後二位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-513">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-513">Checksum</span></span>

<span data-ttu-id="c49b6-514">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-515">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-515">Definition</span></span>

<span data-ttu-id="c49b6-516">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-517">函數 Func_brazil_cpf 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-518">從 Keyword_brazil_cpf 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="c49b6-519">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-519">The checksum passes.</span></span>

<span data-ttu-id="c49b6-520">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-521">函數 Func_brazil_cpf 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-522">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-523">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="c49b6-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="c49b6-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="c49b6-525">CPF</span><span class="sxs-lookup"><span data-stu-id="c49b6-525">CPF</span></span>
- <span data-ttu-id="c49b6-526">Identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-526">Identification</span></span>
- <span data-ttu-id="c49b6-527">Registration</span><span class="sxs-lookup"><span data-stu-id="c49b6-527">Registration</span></span>
- <span data-ttu-id="c49b6-528">Revenue</span><span class="sxs-lookup"><span data-stu-id="c49b6-528">Revenue</span></span>
- <span data-ttu-id="c49b6-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="c49b6-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="c49b6-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="c49b6-530">Imposto</span></span> 
- <span data-ttu-id="c49b6-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="c49b6-531">Identificação</span></span> 
- <span data-ttu-id="c49b6-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="c49b6-532">Inscrição</span></span> 
- <span data-ttu-id="c49b6-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="c49b6-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="c49b6-534">巴西法律實體號碼 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="c49b6-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-535">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-535">Format</span></span>

<span data-ttu-id="c49b6-536">14 位數包含登記碼、分支碼和檢查碼加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="c49b6-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-537">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-537">Pattern</span></span>
<span data-ttu-id="c49b6-538">14 位數，加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="c49b6-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="c49b6-539">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-539">Two digits</span></span> 
- <span data-ttu-id="c49b6-540">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-540">A period</span></span> 
- <span data-ttu-id="c49b6-541">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-541">Three digits</span></span> 
- <span data-ttu-id="c49b6-542">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-542">A period</span></span> 
- <span data-ttu-id="c49b6-543">三位數 (此前 8 位數為登記碼) </span><span class="sxs-lookup"><span data-stu-id="c49b6-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="c49b6-544">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="c49b6-544">A forward slash</span></span> 
- <span data-ttu-id="c49b6-545">四位數分支碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-545">Four-digit branch number</span></span> 
- <span data-ttu-id="c49b6-546">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-546">A hyphen</span></span> 
- <span data-ttu-id="c49b6-547">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-548">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-548">Checksum</span></span>

<span data-ttu-id="c49b6-549">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-550">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-550">Definition</span></span>

<span data-ttu-id="c49b6-551">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-552">函數 Func_brazil_cnpj 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-553">從 Keyword_brazil_cnpj 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="c49b6-554">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-554">The checksum passes.</span></span>

<span data-ttu-id="c49b6-555">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-556">函數 Func_brazil_cnpj 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-557">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-558">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="c49b6-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="c49b6-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="c49b6-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="c49b6-560">CNPJ</span></span> 
- <span data-ttu-id="c49b6-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="c49b6-561">CNPJ/MF</span></span> 
- <span data-ttu-id="c49b6-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="c49b6-562">CNPJ-MF</span></span> 
- <span data-ttu-id="c49b6-563">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="c49b6-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="c49b6-564">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="c49b6-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="c49b6-565">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="c49b6-565">Legal entity</span></span> 
- <span data-ttu-id="c49b6-566">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="c49b6-566">Legal entities</span></span> 
- <span data-ttu-id="c49b6-567">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="c49b6-567">Registration Status</span></span> 
- <span data-ttu-id="c49b6-568">Business
</span><span class="sxs-lookup"><span data-stu-id="c49b6-568">Business</span></span> 
- <span data-ttu-id="c49b6-569">Company</span><span class="sxs-lookup"><span data-stu-id="c49b6-569">Company</span></span>
- <span data-ttu-id="c49b6-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="c49b6-570">CNPJ</span></span> 
- <span data-ttu-id="c49b6-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="c49b6-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="c49b6-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="c49b6-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="c49b6-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-573">CGC</span></span> 
- <span data-ttu-id="c49b6-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="c49b6-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="c49b6-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="c49b6-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="c49b6-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="c49b6-576">Situação cadastral</span></span> 
- <span data-ttu-id="c49b6-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="c49b6-577">Inscrição</span></span> 
- <span data-ttu-id="c49b6-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="c49b6-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="c49b6-579">	巴西國民身分證 (RG)</span><span class="sxs-lookup"><span data-stu-id="c49b6-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-580">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-580">Format</span></span>

<span data-ttu-id="c49b6-581">Registro Geral （舊格式）： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="c49b6-582">Registro de Identidade (RIC) （新格式）： 11 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-583">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-583">Pattern</span></span>

<span data-ttu-id="c49b6-584">Registro Geral (舊格式)：</span><span class="sxs-lookup"><span data-stu-id="c49b6-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="c49b6-585">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-585">Two digits</span></span> 
- <span data-ttu-id="c49b6-586">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-586">A period</span></span> 
- <span data-ttu-id="c49b6-587">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-587">Three digits</span></span> 
- <span data-ttu-id="c49b6-588">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-588">A period</span></span> 
- <span data-ttu-id="c49b6-589">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-589">Three digits</span></span> 
- <span data-ttu-id="c49b6-590">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-590">A hyphen</span></span> 
- <span data-ttu-id="c49b6-591">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-591">One digit which is a check digit</span></span>

<span data-ttu-id="c49b6-592">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="c49b6-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="c49b6-593">10 位數 </span><span class="sxs-lookup"><span data-stu-id="c49b6-593">10 digits</span></span> 
- <span data-ttu-id="c49b6-594">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-594">A hyphen</span></span> 
- <span data-ttu-id="c49b6-595">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-596">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-596">Checksum</span></span>

<span data-ttu-id="c49b6-597">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-598">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-598">Definition</span></span>

<span data-ttu-id="c49b6-599">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-600">函數 Func_brazil_rg 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-601">從 Keyword_brazil_rg 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="c49b6-602">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-602">The checksum passes.</span></span>

<span data-ttu-id="c49b6-603">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-604">函數 Func_brazil_rg 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-605">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-606">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="c49b6-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="c49b6-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="c49b6-608">Cédula de identidade 識別卡國家識別碼 número de rregistro registro de Iidentidade registro geral FEA-RG-APP-NO-VERSION （這個關鍵字是區分大小寫） RIC （這個關鍵字是區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c49b6-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="c49b6-609">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-610">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-610">Format</span></span>

<span data-ttu-id="c49b6-611">7 或 12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-612">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-612">Pattern</span></span>

<span data-ttu-id="c49b6-613">加拿大銀行帳戶號碼是 7 位數或 12 位數。</span><span class="sxs-lookup"><span data-stu-id="c49b6-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="c49b6-614">加拿大銀行帳戶交換號碼是：</span><span class="sxs-lookup"><span data-stu-id="c49b6-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="c49b6-615">五位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-615">Five digits</span></span> 
- <span data-ttu-id="c49b6-616">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-616">A hyphen</span></span> 
- <span data-ttu-id="c49b6-617">三個數字或</span><span class="sxs-lookup"><span data-stu-id="c49b6-617">Three digits OR</span></span>
- <span data-ttu-id="c49b6-618">一個零 "0"</span><span class="sxs-lookup"><span data-stu-id="c49b6-618">A zero "0"</span></span> 
- <span data-ttu-id="c49b6-619">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-620">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-620">Checksum</span></span>

<span data-ttu-id="c49b6-621">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-622">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-622">Definition</span></span>

<span data-ttu-id="c49b6-623">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-624">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-625">找到來自於 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="c49b6-626">規則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="c49b6-627">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-628">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-629">找到來自於 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-630">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="c49b6-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="c49b6-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="c49b6-632">canada savings bonds</span></span>
- <span data-ttu-id="c49b6-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="c49b6-633">canada revenue agency</span></span>
- <span data-ttu-id="c49b6-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="c49b6-634">canadian financial institution</span></span>
- <span data-ttu-id="c49b6-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="c49b6-635">direct deposit form</span></span>
- <span data-ttu-id="c49b6-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="c49b6-636">canadian citizen</span></span>
- <span data-ttu-id="c49b6-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="c49b6-637">legal representative</span></span>
- <span data-ttu-id="c49b6-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="c49b6-638">notary public</span></span>
- <span data-ttu-id="c49b6-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="c49b6-639">commissioner for oaths</span></span>
- <span data-ttu-id="c49b6-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="c49b6-640">child care benefit</span></span>
- <span data-ttu-id="c49b6-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="c49b6-641">universal child care</span></span>
- <span data-ttu-id="c49b6-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="c49b6-642">canada child tax benefit</span></span>
- <span data-ttu-id="c49b6-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="c49b6-643">income tax benefit</span></span>
- <span data-ttu-id="c49b6-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="c49b6-644">harmonized sales tax</span></span>
- <span data-ttu-id="c49b6-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="c49b6-645">social insurance number</span></span>
- <span data-ttu-id="c49b6-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="c49b6-646">income tax refund</span></span>
- <span data-ttu-id="c49b6-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="c49b6-647">child tax benefit</span></span>
- <span data-ttu-id="c49b6-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="c49b6-648">territorial payments</span></span>
- <span data-ttu-id="c49b6-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="c49b6-649">institution number</span></span>
- <span data-ttu-id="c49b6-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="c49b6-650">deposit request</span></span>
- <span data-ttu-id="c49b6-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="c49b6-651">banking information</span></span>
- <span data-ttu-id="c49b6-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="c49b6-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="c49b6-653">加拿大駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-654">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-654">Format</span></span>

<span data-ttu-id="c49b6-655">隨省分而不同</span><span class="sxs-lookup"><span data-stu-id="c49b6-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-656">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-656">Pattern</span></span>

<span data-ttu-id="c49b6-657">Alberta、British Columbia、Manitoba、New Brunswick、Newfoundland/Labrador、Nova Scotia、Ontario、Prince Edward Island、Quebec 和 Saskatchewan 各有不同模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-658">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-658">Checksum</span></span>

<span data-ttu-id="c49b6-659">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-660">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-660">Definition</span></span>

<span data-ttu-id="c49b6-661">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-662">函數 Func_[province_name]_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-663">找到來自於 Keyword_[province_name]_drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="c49b6-664">找到來自於 Keyword_canada_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-665">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="c49b6-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="c49b6-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="c49b6-667">省分縮寫，例如 AB</span><span class="sxs-lookup"><span data-stu-id="c49b6-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="c49b6-668">
省分名稱，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="c49b6-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="c49b6-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="c49b6-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="c49b6-670">DL</span><span class="sxs-lookup"><span data-stu-id="c49b6-670">DL</span></span>
- <span data-ttu-id="c49b6-671">DLS</span><span class="sxs-lookup"><span data-stu-id="c49b6-671">DLS</span></span>
- <span data-ttu-id="c49b6-672">CDL</span><span class="sxs-lookup"><span data-stu-id="c49b6-672">CDL</span></span>
- <span data-ttu-id="c49b6-673">CDLS</span><span class="sxs-lookup"><span data-stu-id="c49b6-673">CDLS</span></span>
- <span data-ttu-id="c49b6-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-674">DriverLic</span></span>
- <span data-ttu-id="c49b6-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-675">DriverLics</span></span>
- <span data-ttu-id="c49b6-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="c49b6-676">DriverLicense</span></span>
- <span data-ttu-id="c49b6-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-677">DriverLicenses</span></span>
- <span data-ttu-id="c49b6-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="c49b6-678">DriverLicence</span></span>
- <span data-ttu-id="c49b6-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="c49b6-679">DriverLicences</span></span>
- <span data-ttu-id="c49b6-680">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-680">Driver Lic</span></span>
- <span data-ttu-id="c49b6-681">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-681">Driver Lics</span></span>
- <span data-ttu-id="c49b6-682">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-682">Driver License</span></span>
- <span data-ttu-id="c49b6-683">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-683">Driver Licenses</span></span>
- <span data-ttu-id="c49b6-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-684">Driver Licence</span></span>
- <span data-ttu-id="c49b6-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-685">Driver Licences</span></span>
- <span data-ttu-id="c49b6-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-686">DriversLic</span></span>
- <span data-ttu-id="c49b6-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-687">DriversLics</span></span>
- <span data-ttu-id="c49b6-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="c49b6-688">DriversLicence</span></span>
- <span data-ttu-id="c49b6-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="c49b6-689">DriversLicences</span></span>
- <span data-ttu-id="c49b6-690">執照</span><span class="sxs-lookup"><span data-stu-id="c49b6-690">DriversLicense</span></span>
- <span data-ttu-id="c49b6-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-691">DriversLicenses</span></span>
- <span data-ttu-id="c49b6-692">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-692">Drivers Lic</span></span>
- <span data-ttu-id="c49b6-693">發行的驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-693">Drivers Lics</span></span>
- <span data-ttu-id="c49b6-694">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-694">Drivers License</span></span>
- <span data-ttu-id="c49b6-695">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-695">Drivers Licenses</span></span>
- <span data-ttu-id="c49b6-696">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-696">Drivers Licence</span></span>
- <span data-ttu-id="c49b6-697">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-697">Drivers Licences</span></span>
- <span data-ttu-id="c49b6-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-698">Driver'Lic</span></span>
- <span data-ttu-id="c49b6-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-699">Driver'Lics</span></span>
- <span data-ttu-id="c49b6-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="c49b6-700">Driver'License</span></span>
- <span data-ttu-id="c49b6-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-701">Driver'Licenses</span></span>
- <span data-ttu-id="c49b6-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="c49b6-702">Driver'Licence</span></span>
- <span data-ttu-id="c49b6-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="c49b6-703">Driver'Licences</span></span>
- <span data-ttu-id="c49b6-704">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-704">Driver' Lic</span></span>
- <span data-ttu-id="c49b6-705">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-705">Driver' Lics</span></span>
- <span data-ttu-id="c49b6-706">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-706">Driver' License</span></span>
- <span data-ttu-id="c49b6-707">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-707">Driver' Licenses</span></span>
- <span data-ttu-id="c49b6-708">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-708">Driver' Licence</span></span>
- <span data-ttu-id="c49b6-709">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-709">Driver' Licences</span></span>
- <span data-ttu-id="c49b6-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-710">Driver'sLic</span></span>
- <span data-ttu-id="c49b6-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-711">Driver'sLics</span></span>
- <span data-ttu-id="c49b6-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="c49b6-712">Driver'sLicense</span></span>
- <span data-ttu-id="c49b6-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-713">Driver'sLicenses</span></span>
- <span data-ttu-id="c49b6-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="c49b6-714">Driver'sLicence</span></span>
- <span data-ttu-id="c49b6-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="c49b6-715">Driver'sLicences</span></span>
- <span data-ttu-id="c49b6-716">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-716">Driver's Lic</span></span>
- <span data-ttu-id="c49b6-717">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-717">Driver's Lics</span></span>
- <span data-ttu-id="c49b6-718">駕照</span><span class="sxs-lookup"><span data-stu-id="c49b6-718">Driver's License</span></span>
- <span data-ttu-id="c49b6-719">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-719">Driver's Licenses</span></span>
- <span data-ttu-id="c49b6-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-720">Driver's Licence</span></span>
- <span data-ttu-id="c49b6-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-721">Driver's Licences</span></span>
- <span data-ttu-id="c49b6-722">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="c49b6-722">Permis de Conduire</span></span>
- <span data-ttu-id="c49b6-723">id</span><span class="sxs-lookup"><span data-stu-id="c49b6-723">id</span></span>
- <span data-ttu-id="c49b6-724">識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-724">ids</span></span>
- <span data-ttu-id="c49b6-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="c49b6-725">idcard number</span></span>
- <span data-ttu-id="c49b6-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="c49b6-726">idcard numbers</span></span>
- <span data-ttu-id="c49b6-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="c49b6-727">idcard #</span></span>
- <span data-ttu-id="c49b6-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="c49b6-728">idcard #s</span></span>
- <span data-ttu-id="c49b6-729">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="c49b6-729">idcard card</span></span>
- <span data-ttu-id="c49b6-730">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-730">idcard cards</span></span>
- <span data-ttu-id="c49b6-731">idcard</span><span class="sxs-lookup"><span data-stu-id="c49b6-731">idcard</span></span>
- <span data-ttu-id="c49b6-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-732">identification number</span></span>
- <span data-ttu-id="c49b6-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-733">identification numbers</span></span>
- <span data-ttu-id="c49b6-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-734">identification #</span></span>
- <span data-ttu-id="c49b6-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="c49b6-735">identification #s</span></span>
- <span data-ttu-id="c49b6-736">識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-736">identification card</span></span>
- <span data-ttu-id="c49b6-737">識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-737">identification cards</span></span>
- <span data-ttu-id="c49b6-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="c49b6-738">identification</span></span> 
- <span data-ttu-id="c49b6-739">DL#</span><span class="sxs-lookup"><span data-stu-id="c49b6-739">DL#</span></span>
- <span data-ttu-id="c49b6-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-740">DLS#</span></span> 
- <span data-ttu-id="c49b6-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-741">CDL#</span></span> 
- <span data-ttu-id="c49b6-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-742">CDLS#</span></span> 
- <span data-ttu-id="c49b6-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-743">DriverLic#</span></span> 
- <span data-ttu-id="c49b6-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-744">DriverLics#</span></span> 
- <span data-ttu-id="c49b6-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="c49b6-745">DriverLicense#</span></span> 
- <span data-ttu-id="c49b6-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-746">DriverLicenses#</span></span> 
- <span data-ttu-id="c49b6-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="c49b6-747">DriverLicence#</span></span> 
- <span data-ttu-id="c49b6-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="c49b6-748">DriverLicences#</span></span> 
- <span data-ttu-id="c49b6-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="c49b6-749">Driver Lic#</span></span>
- <span data-ttu-id="c49b6-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-750">Driver Lics#</span></span> 
- <span data-ttu-id="c49b6-751">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-751">Driver License#</span></span> 
- <span data-ttu-id="c49b6-752">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-752">Driver Licenses#</span></span> 
- <span data-ttu-id="c49b6-753">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-753">Driver License#</span></span> 
- <span data-ttu-id="c49b6-754">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-754">Driver Licences#</span></span> 
- <span data-ttu-id="c49b6-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-755">DriversLic#</span></span> 
- <span data-ttu-id="c49b6-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-756">DriversLics#</span></span> 
- <span data-ttu-id="c49b6-757">執照 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-757">DriversLicense#</span></span> 
- <span data-ttu-id="c49b6-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-758">DriversLicenses#</span></span> 
- <span data-ttu-id="c49b6-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="c49b6-759">DriversLicence#</span></span> 
- <span data-ttu-id="c49b6-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="c49b6-760">DriversLicences#</span></span> 
- <span data-ttu-id="c49b6-761">發行的驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-761">Drivers Lic#</span></span> 
- <span data-ttu-id="c49b6-762">發行的驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-762">Drivers Lics#</span></span> 
- <span data-ttu-id="c49b6-763">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-763">Drivers License#</span></span> 
- <span data-ttu-id="c49b6-764">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="c49b6-765">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-765">Drivers Licence#</span></span> 
- <span data-ttu-id="c49b6-766">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-766">Drivers Licences#</span></span> 
- <span data-ttu-id="c49b6-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-767">Driver'Lic#</span></span> 
- <span data-ttu-id="c49b6-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-768">Driver'Lics#</span></span> 
- <span data-ttu-id="c49b6-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-769">Driver'License#</span></span> 
- <span data-ttu-id="c49b6-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="c49b6-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-771">Driver'Licence#</span></span> 
- <span data-ttu-id="c49b6-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-772">Driver'Licences#</span></span> 
- <span data-ttu-id="c49b6-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-773">Driver' Lic#</span></span> 
- <span data-ttu-id="c49b6-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-774">Driver' Lics#</span></span> 
- <span data-ttu-id="c49b6-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-775">Driver' License#</span></span> 
- <span data-ttu-id="c49b6-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="c49b6-777">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-777">Driver' Licence#</span></span> 
- <span data-ttu-id="c49b6-778">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-778">Driver' Licences#</span></span> 
- <span data-ttu-id="c49b6-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-779">Driver'sLic#</span></span> 
- <span data-ttu-id="c49b6-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-780">Driver'sLics#</span></span> 
- <span data-ttu-id="c49b6-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="c49b6-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="c49b6-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="c49b6-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="c49b6-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="c49b6-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="c49b6-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="c49b6-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-785">Driver's Lic#</span></span> 
- <span data-ttu-id="c49b6-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-786">Driver's Lics#</span></span> 
- <span data-ttu-id="c49b6-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-787">Driver's License#</span></span> 
- <span data-ttu-id="c49b6-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="c49b6-789">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-789">Driver's Licence#</span></span> 
- <span data-ttu-id="c49b6-790">駕授權 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-790">Driver's Licences#</span></span> 
- <span data-ttu-id="c49b6-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="c49b6-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="c49b6-792">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-792">id#</span></span> 
- <span data-ttu-id="c49b6-793">id #</span><span class="sxs-lookup"><span data-stu-id="c49b6-793">ids#</span></span> 
- <span data-ttu-id="c49b6-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-794">idcard card#</span></span> 
- <span data-ttu-id="c49b6-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-795">idcard cards#</span></span> 
- <span data-ttu-id="c49b6-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-796">idcard#</span></span> 
- <span data-ttu-id="c49b6-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-797">identification card#</span></span> 
- <span data-ttu-id="c49b6-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-798">identification cards#</span></span> 
- <span data-ttu-id="c49b6-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="c49b6-800">加拿大國家健保號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-801">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-801">Format</span></span>

<span data-ttu-id="c49b6-802">10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-803">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-803">Pattern</span></span>

<span data-ttu-id="c49b6-804">10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-805">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-805">Checksum</span></span>

<span data-ttu-id="c49b6-806">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-807">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-807">Definition</span></span>

<span data-ttu-id="c49b6-808">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-809">規則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-810">找到來自於 Keyword_canada_health_service_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-811">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="c49b6-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="c49b6-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="c49b6-813">personal health number</span></span>
- <span data-ttu-id="c49b6-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="c49b6-814">patient information</span></span>
- <span data-ttu-id="c49b6-815">狀況服務</span><span class="sxs-lookup"><span data-stu-id="c49b6-815">health services</span></span>
- <span data-ttu-id="c49b6-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="c49b6-816">speciality services</span></span>
- <span data-ttu-id="c49b6-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="c49b6-817">automobile accident</span></span>
- <span data-ttu-id="c49b6-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="c49b6-818">patient hospital</span></span>
- <span data-ttu-id="c49b6-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="c49b6-819">psychiatrist</span></span>
- <span data-ttu-id="c49b6-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="c49b6-820">workers compensation</span></span>
- <span data-ttu-id="c49b6-821">
disability</span><span class="sxs-lookup"><span data-stu-id="c49b6-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="c49b6-822">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-823">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-823">Format</span></span>

<span data-ttu-id="c49b6-824">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-825">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-825">Pattern</span></span>

<span data-ttu-id="c49b6-826">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-827">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-827">Checksum</span></span>

<span data-ttu-id="c49b6-828">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-829">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-829">Definition</span></span>

<span data-ttu-id="c49b6-830">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-831">規則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-832">從 Keyword_canada_passport_number 或 Keyword_passport 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-833">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="c49b6-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="c49b6-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="c49b6-835">canadian citizenship</span></span>
- <span data-ttu-id="c49b6-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-836">canadian passport</span></span>
- <span data-ttu-id="c49b6-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="c49b6-837">passport application</span></span>
- <span data-ttu-id="c49b6-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="c49b6-838">passport photos</span></span>
- <span data-ttu-id="c49b6-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="c49b6-839">certified translator</span></span>
- <span data-ttu-id="c49b6-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="c49b6-840">canadian citizens</span></span>
- <span data-ttu-id="c49b6-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="c49b6-841">processing times</span></span>
- <span data-ttu-id="c49b6-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="c49b6-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="c49b6-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-843">Keyword_passport</span></span>

- <span data-ttu-id="c49b6-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-844">Passport Number</span></span>
- <span data-ttu-id="c49b6-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="c49b6-845">Passport No</span></span>
- <span data-ttu-id="c49b6-846">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-846">Passport #</span></span>
- <span data-ttu-id="c49b6-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-847">Passport#</span></span>
- <span data-ttu-id="c49b6-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="c49b6-848">PassportID</span></span>
- <span data-ttu-id="c49b6-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="c49b6-849">Passportno</span></span>
- <span data-ttu-id="c49b6-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-850">passportnumber</span></span>
- <span data-ttu-id="c49b6-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="c49b6-851">パスポート</span></span>
- <span data-ttu-id="c49b6-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-852">パスポート番号</span></span>
- <span data-ttu-id="c49b6-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-853">パスポートのNum</span></span>
- <span data-ttu-id="c49b6-854">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-854">パスポート＃</span></span>
- <span data-ttu-id="c49b6-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="c49b6-855">Numéro de passeport</span></span>
- <span data-ttu-id="c49b6-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="c49b6-856">Passeport n °</span></span>
- <span data-ttu-id="c49b6-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="c49b6-857">Passeport Non</span></span>
- <span data-ttu-id="c49b6-858">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-858">Passeport #</span></span>
- <span data-ttu-id="c49b6-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-859">Passeport#</span></span>
- <span data-ttu-id="c49b6-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="c49b6-860">PasseportNon</span></span>
- <span data-ttu-id="c49b6-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="c49b6-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="c49b6-862">加拿大個人健康身分識別碼 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-863">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-863">Format</span></span>

<span data-ttu-id="c49b6-864">九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-865">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-865">Pattern</span></span>

<span data-ttu-id="c49b6-866">九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-867">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-867">Checksum</span></span>

<span data-ttu-id="c49b6-868">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-869">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-869">Definition</span></span>

<span data-ttu-id="c49b6-p104">DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 規則運算式 Regex_canada_phin 會找出符合模式的內容。找到至少兩種關鍵字 Keyword_canada_phin 或 Keyword_canada_provinces.</span><span class="sxs-lookup"><span data-stu-id="c49b6-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-872">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="c49b6-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="c49b6-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="c49b6-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="c49b6-874">social insurance number</span></span>
- <span data-ttu-id="c49b6-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="c49b6-875">health information act</span></span>
- <span data-ttu-id="c49b6-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="c49b6-876">income tax information</span></span>
- <span data-ttu-id="c49b6-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="c49b6-877">manitoba health</span></span>
- <span data-ttu-id="c49b6-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="c49b6-878">health registration</span></span>
- <span data-ttu-id="c49b6-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="c49b6-879">prescription purchases</span></span>
- <span data-ttu-id="c49b6-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="c49b6-880">benefit eligibility</span></span>
- <span data-ttu-id="c49b6-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="c49b6-881">personal health</span></span>
- <span data-ttu-id="c49b6-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="c49b6-882">power of attorney</span></span>
- <span data-ttu-id="c49b6-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="c49b6-883">registration number</span></span>
- <span data-ttu-id="c49b6-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="c49b6-884">personal health number</span></span>
- <span data-ttu-id="c49b6-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="c49b6-885">practitioner referral</span></span>
- <span data-ttu-id="c49b6-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="c49b6-886">wellness professional</span></span>
- <span data-ttu-id="c49b6-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="c49b6-887">patient referral</span></span>
- <span data-ttu-id="c49b6-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="c49b6-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="c49b6-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="c49b6-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="c49b6-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="c49b6-890">Nunavut</span></span>
- <span data-ttu-id="c49b6-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="c49b6-891">Quebec</span></span>
- <span data-ttu-id="c49b6-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="c49b6-892">Northwest Territories</span></span>
- <span data-ttu-id="c49b6-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="c49b6-893">Ontario</span></span>
- <span data-ttu-id="c49b6-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="c49b6-894">British Columbia</span></span>
- <span data-ttu-id="c49b6-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="c49b6-895">Alberta</span></span>
- <span data-ttu-id="c49b6-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="c49b6-896">Saskatchewan</span></span>
- <span data-ttu-id="c49b6-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="c49b6-897">Manitoba</span></span>
- <span data-ttu-id="c49b6-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="c49b6-898">Yukon</span></span>
- <span data-ttu-id="c49b6-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="c49b6-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="c49b6-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="c49b6-900">New Brunswick</span></span>
- <span data-ttu-id="c49b6-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="c49b6-901">Nova Scotia</span></span>
- <span data-ttu-id="c49b6-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="c49b6-902">Prince Edward Island</span></span>
- <span data-ttu-id="c49b6-903">加拿大</span><span class="sxs-lookup"><span data-stu-id="c49b6-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="c49b6-904">加拿大社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-905">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-905">Format</span></span>

<span data-ttu-id="c49b6-906">具有選用連字號或空格的 9 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-907">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-907">Pattern</span></span>

<span data-ttu-id="c49b6-908">格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-908">Formatted:</span></span>
- <span data-ttu-id="c49b6-909">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-909">Three digits</span></span> 
- <span data-ttu-id="c49b6-910">一個連字號或空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-910">A hyphen or space</span></span> 
- <span data-ttu-id="c49b6-911">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-911">Three digits</span></span> 
- <span data-ttu-id="c49b6-912">一個連字號或空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-912">A hyphen or space</span></span> 
- <span data-ttu-id="c49b6-913">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-913">Three digits</span></span>

<span data-ttu-id="c49b6-914">未格式化： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-915">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-915">Checksum</span></span>

<span data-ttu-id="c49b6-916">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-917">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-917">Definition</span></span>

<span data-ttu-id="c49b6-918">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-919">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-920">至少下列兩項的任意組合：</span><span class="sxs-lookup"><span data-stu-id="c49b6-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="c49b6-921">找到來自於 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="c49b6-922">找到來自於 Keyword_sin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="c49b6-923">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="c49b6-924">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-924">The checksum passes.</span></span>

<span data-ttu-id="c49b6-925">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-926">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-927">找到來自於 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="c49b6-928">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-929">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="c49b6-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="c49b6-930">Keyword_sin</span></span>

- <span data-ttu-id="c49b6-931">sin</span><span class="sxs-lookup"><span data-stu-id="c49b6-931">sin</span></span> 
- <span data-ttu-id="c49b6-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="c49b6-932">social insurance</span></span> 
- <span data-ttu-id="c49b6-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="c49b6-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="c49b6-934">sins
</span><span class="sxs-lookup"><span data-stu-id="c49b6-934">sins</span></span> 
- <span data-ttu-id="c49b6-935">ssn</span><span class="sxs-lookup"><span data-stu-id="c49b6-935">ssn</span></span> 
- <span data-ttu-id="c49b6-936">ssns</span><span class="sxs-lookup"><span data-stu-id="c49b6-936">ssns</span></span> 
- <span data-ttu-id="c49b6-937">社會安全</span><span class="sxs-lookup"><span data-stu-id="c49b6-937">social security</span></span> 
- <span data-ttu-id="c49b6-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="c49b6-938">numero d'assurance social</span></span> 
- <span data-ttu-id="c49b6-939">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-939">national identification number</span></span> 
- <span data-ttu-id="c49b6-940">
national id</span><span class="sxs-lookup"><span data-stu-id="c49b6-940">national id</span></span> 
- <span data-ttu-id="c49b6-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-941">sin#</span></span> 
- <span data-ttu-id="c49b6-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="c49b6-942">soc ins</span></span> 
- <span data-ttu-id="c49b6-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="c49b6-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="c49b6-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="c49b6-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="c49b6-945">駕照</span><span class="sxs-lookup"><span data-stu-id="c49b6-945">driver's license</span></span> 
- <span data-ttu-id="c49b6-946">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-946">drivers license</span></span> 
- <span data-ttu-id="c49b6-947">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-947">driver's licence</span></span> 
- <span data-ttu-id="c49b6-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c49b6-948">drivers licence</span></span> 
- <span data-ttu-id="c49b6-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="c49b6-949">DOB</span></span> 
- <span data-ttu-id="c49b6-950">出生日期</span><span class="sxs-lookup"><span data-stu-id="c49b6-950">Birthdate</span></span> 
- <span data-ttu-id="c49b6-951">生日 </span><span class="sxs-lookup"><span data-stu-id="c49b6-951">Birthday</span></span> 
- <span data-ttu-id="c49b6-952">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="c49b6-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="c49b6-953">	智利身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-954">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-954">Format</span></span>

<span data-ttu-id="c49b6-955">7-8 的數字加上分隔符號] 核取數字或字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-956">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-956">Pattern</span></span>

<span data-ttu-id="c49b6-957">7-8 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="c49b6-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="c49b6-958">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-958">1-2 digits</span></span> 
- <span data-ttu-id="c49b6-959">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-959">A period</span></span> 
- <span data-ttu-id="c49b6-960">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-960">Three digits</span></span> 
- <span data-ttu-id="c49b6-961">句點 </span><span class="sxs-lookup"><span data-stu-id="c49b6-961">A period</span></span> 
- <span data-ttu-id="c49b6-962">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-962">Three digits</span></span> 
- <span data-ttu-id="c49b6-963">一個破折號</span><span class="sxs-lookup"><span data-stu-id="c49b6-963">A dash</span></span> 
- <span data-ttu-id="c49b6-964">一位數或字母 (不區分大小寫) 的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-965">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-965">Checksum</span></span>

<span data-ttu-id="c49b6-966">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-967">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-967">Definition</span></span>

<span data-ttu-id="c49b6-968">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-969">函數 Func_chile_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-970">從 Keyword_chile_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="c49b6-971">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-971">The checksum passes.</span></span>

<span data-ttu-id="c49b6-972">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-973">函數 Func_chile_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-974">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-975">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="c49b6-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="c49b6-977">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-977">National Identification Number</span></span> 
- <span data-ttu-id="c49b6-978">Identity card</span><span class="sxs-lookup"><span data-stu-id="c49b6-978">Identity card</span></span> 
- <span data-ttu-id="c49b6-979">ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-979">ID</span></span> 
- <span data-ttu-id="c49b6-980">Identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-980">Identification</span></span> 
- <span data-ttu-id="c49b6-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="c49b6-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="c49b6-982">執行</span><span class="sxs-lookup"><span data-stu-id="c49b6-982">RUN</span></span> 
- <span data-ttu-id="c49b6-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="c49b6-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="c49b6-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="c49b6-984">RUT</span></span> 
- <span data-ttu-id="c49b6-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="c49b6-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="c49b6-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="c49b6-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="c49b6-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="c49b6-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="c49b6-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="c49b6-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="c49b6-989">	中國居民身分證 (PRC) 號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-990">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-990">Format</span></span>

<span data-ttu-id="c49b6-991">18 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-992">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-992">Pattern</span></span>

<span data-ttu-id="c49b6-993">18 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-993">18 digits:</span></span>
- <span data-ttu-id="c49b6-994">六位數的地址代碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="c49b6-995">YYYYMMDD 格式的八位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-996">三位數的序碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="c49b6-997">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-998">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-998">Checksum</span></span>

<span data-ttu-id="c49b6-999">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1000">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1000">Definition</span></span>

<span data-ttu-id="c49b6-1001">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1002">函數 Func_china_resident_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1003">從 Keyword_china_resident_id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="c49b6-1004">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1004">The checksum passes.</span></span>

<span data-ttu-id="c49b6-1005">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1006">函數 Func_china_resident_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1007">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1008">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="c49b6-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="c49b6-1010">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="c49b6-1011">PRC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1011">PRC</span></span> 
- <span data-ttu-id="c49b6-1012">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1012">National Identification Card</span></span> 
- <span data-ttu-id="c49b6-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="c49b6-1013">身份证</span></span> 
- <span data-ttu-id="c49b6-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="c49b6-1014">居民 身份证</span></span> 
- <span data-ttu-id="c49b6-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1015">居民身份证</span></span> 
- <span data-ttu-id="c49b6-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="c49b6-1016">鉴定</span></span> 
- <span data-ttu-id="c49b6-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="c49b6-1017">身分證</span></span> 
- <span data-ttu-id="c49b6-1018">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="c49b6-1018">居民 身份證</span></span>
- <span data-ttu-id="c49b6-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="c49b6-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="c49b6-1020">信用卡號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1021">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1021">Format</span></span>

<span data-ttu-id="c49b6-1022">這可設為 16 個位數或格式化 (dddddddddddddddd) 和必須通過 Luhn 測試。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1023">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1023">Pattern</span></span>

<span data-ttu-id="c49b6-1024">非常複雜且健全的模式，會偵測全球所有主要品牌的卡片，包括 Visa、MasterCard、Discover Card、JCB、American Express、禮品卡和大來卡。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1025">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1025">Checksum</span></span>

<span data-ttu-id="c49b6-1026">是，Luhn 總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1027">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1027">Definition</span></span>

<span data-ttu-id="c49b6-1028">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1029">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1030">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1030">One of the following is true:</span></span>
    - <span data-ttu-id="c49b6-1031">找到來自於 Keyword_cc_verification 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="c49b6-1032">找到來自於 Keyword_cc_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="c49b6-1033">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="c49b6-1034">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1034">The checksum passes.</span></span>

<span data-ttu-id="c49b6-1035">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1036">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1037">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1038">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="c49b6-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="c49b6-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="c49b6-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="c49b6-1040">card verification</span></span>
- <span data-ttu-id="c49b6-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1041">card identification number</span></span>
- <span data-ttu-id="c49b6-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1042">cvn</span></span>
- <span data-ttu-id="c49b6-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1043">cid</span></span>
- <span data-ttu-id="c49b6-1044">cvc2</span><span class="sxs-lookup"><span data-stu-id="c49b6-1044">cvc2</span></span>
- <span data-ttu-id="c49b6-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="c49b6-1045">cvv2</span></span>
- <span data-ttu-id="c49b6-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1046">pin block</span></span>
- <span data-ttu-id="c49b6-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1047">security code</span></span>
- <span data-ttu-id="c49b6-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1048">security number</span></span>
- <span data-ttu-id="c49b6-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1049">security no</span></span>
- <span data-ttu-id="c49b6-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1050">issue number</span></span>
- <span data-ttu-id="c49b6-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1051">issue no</span></span>
- <span data-ttu-id="c49b6-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1052">cryptogramme</span></span>
- <span data-ttu-id="c49b6-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1053">numéro de sécurité</span></span>
- <span data-ttu-id="c49b6-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1054">numero de securite</span></span>
- <span data-ttu-id="c49b6-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="c49b6-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="c49b6-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1057">prüfziffer</span></span>
- <span data-ttu-id="c49b6-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1058">prufziffer</span></span>
- <span data-ttu-id="c49b6-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="c49b6-1059">sicherheits Kode</span></span>
- <span data-ttu-id="c49b6-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1060">sicherheitscode</span></span>
- <span data-ttu-id="c49b6-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="c49b6-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1062">verfalldatum</span></span>
- <span data-ttu-id="c49b6-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1063">codice di verifica</span></span>
- <span data-ttu-id="c49b6-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p105">cod. sicurezza</span></span>
- <span data-ttu-id="c49b6-1066">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="c49b6-1066">cod sicurezza</span></span>
- <span data-ttu-id="c49b6-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c49b6-1067">n autorizzazione</span></span>
- <span data-ttu-id="c49b6-1068">código
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1068">código</span></span>
- <span data-ttu-id="c49b6-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1069">codigo</span></span>
- <span data-ttu-id="c49b6-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p106">cod. seg</span></span>
- <span data-ttu-id="c49b6-1072">cod seg</span><span class="sxs-lookup"><span data-stu-id="c49b6-1072">cod seg</span></span>
- <span data-ttu-id="c49b6-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1073">código de segurança</span></span>
- <span data-ttu-id="c49b6-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1074">codigo de seguranca</span></span>
- <span data-ttu-id="c49b6-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1075">codigo de segurança</span></span>
- <span data-ttu-id="c49b6-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1076">código de seguranca</span></span>
- <span data-ttu-id="c49b6-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p107">cód. segurança</span></span>
- <span data-ttu-id="c49b6-p108">cod。seguranca cod。segurança</span><span class="sxs-lookup"><span data-stu-id="c49b6-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="c49b6-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p109">cód. seguranca</span></span>
- <span data-ttu-id="c49b6-1084">cód segurança</span><span class="sxs-lookup"><span data-stu-id="c49b6-1084">cód segurança</span></span>
- <span data-ttu-id="c49b6-1085">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="c49b6-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="c49b6-1086">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="c49b6-1086">cód seguranca</span></span>
- <span data-ttu-id="c49b6-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1087">número de verificação</span></span>
- <span data-ttu-id="c49b6-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1088">numero de verificacao</span></span>
- <span data-ttu-id="c49b6-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1089">ablauf</span></span>
- <span data-ttu-id="c49b6-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1090">gültig bis</span></span>
- <span data-ttu-id="c49b6-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="c49b6-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1092">gultig bis</span></span>
- <span data-ttu-id="c49b6-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="c49b6-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1094">scadenza</span></span>
- <span data-ttu-id="c49b6-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1095">data scad</span></span>
- <span data-ttu-id="c49b6-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1096">fecha de expiracion</span></span>
- <span data-ttu-id="c49b6-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1097">fecha de venc</span></span>
- <span data-ttu-id="c49b6-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1098">vencimiento</span></span>
- <span data-ttu-id="c49b6-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1099">válido hasta</span></span>
- <span data-ttu-id="c49b6-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1100">valido hasta</span></span>
- <span data-ttu-id="c49b6-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1101">vto</span></span>
- <span data-ttu-id="c49b6-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1102">data de expiração</span></span>
- <span data-ttu-id="c49b6-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1103">data de expiracao</span></span>
- <span data-ttu-id="c49b6-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1104">data em que expira</span></span>
- <span data-ttu-id="c49b6-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1105">validade</span></span>
- <span data-ttu-id="c49b6-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1106">valor</span></span>
- <span data-ttu-id="c49b6-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1107">vencimento</span></span>
- <span data-ttu-id="c49b6-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="c49b6-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="c49b6-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="c49b6-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="c49b6-1110">amex</span><span class="sxs-lookup"><span data-stu-id="c49b6-1110">amex</span></span>
- <span data-ttu-id="c49b6-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="c49b6-1111">american express</span></span>
- <span data-ttu-id="c49b6-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1112">americanexpress</span></span>
- <span data-ttu-id="c49b6-1113">因為撰寫</span><span class="sxs-lookup"><span data-stu-id="c49b6-1113">Visa</span></span>
- <span data-ttu-id="c49b6-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1114">mastercard</span></span>
- <span data-ttu-id="c49b6-1115">master card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1115">master card</span></span>
- <span data-ttu-id="c49b6-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1116">mc</span></span> 
- <span data-ttu-id="c49b6-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="c49b6-1117">mastercards</span></span>
- <span data-ttu-id="c49b6-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="c49b6-1118">master cards</span></span>
- <span data-ttu-id="c49b6-1119">大來卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-1119">diner's Club</span></span>
- <span data-ttu-id="c49b6-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1120">diners club</span></span>
- <span data-ttu-id="c49b6-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1121">dinersclub</span></span>
- <span data-ttu-id="c49b6-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1122">discover card</span></span>
- <span data-ttu-id="c49b6-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1123">discovercard</span></span>
- <span data-ttu-id="c49b6-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1124">discover cards</span></span>
- <span data-ttu-id="c49b6-1125">JCB</span><span class="sxs-lookup"><span data-stu-id="c49b6-1125">JCB</span></span>
- <span data-ttu-id="c49b6-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1126">japanese card bureau</span></span>
- <span data-ttu-id="c49b6-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1127">carte blanche</span></span>
- <span data-ttu-id="c49b6-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1128">carteblanche</span></span>
- <span data-ttu-id="c49b6-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1129">credit card</span></span>
- <span data-ttu-id="c49b6-1130">[副本] #</span><span class="sxs-lookup"><span data-stu-id="c49b6-1130">cc#</span></span>
- <span data-ttu-id="c49b6-1131">[副本] # 中：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1131">cc#:</span></span>
- <span data-ttu-id="c49b6-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="c49b6-1132">expiration date</span></span>
- <span data-ttu-id="c49b6-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1133">exp date</span></span>
- <span data-ttu-id="c49b6-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="c49b6-1134">expiry date</span></span>
- <span data-ttu-id="c49b6-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="c49b6-1135">date d’expiration</span></span>
- <span data-ttu-id="c49b6-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="c49b6-1136">date d'exp</span></span>
- <span data-ttu-id="c49b6-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="c49b6-1137">date expiration</span></span>
- <span data-ttu-id="c49b6-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1138">bank card</span></span>
- <span data-ttu-id="c49b6-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="c49b6-1139">bankcard</span></span>
- <span data-ttu-id="c49b6-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1140">card number</span></span>
- <span data-ttu-id="c49b6-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1141">card num</span></span>
- <span data-ttu-id="c49b6-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1142">cardnumber</span></span>
- <span data-ttu-id="c49b6-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1143">cardnumbers</span></span>
- <span data-ttu-id="c49b6-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1144">card numbers</span></span>
- <span data-ttu-id="c49b6-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1145">creditcard</span></span>
- <span data-ttu-id="c49b6-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1146">credit cards</span></span>
- <span data-ttu-id="c49b6-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1147">creditcards</span></span>
- <span data-ttu-id="c49b6-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1148">ccn</span></span>
- <span data-ttu-id="c49b6-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1149">card holder</span></span>
- <span data-ttu-id="c49b6-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1150">cardholder</span></span>
- <span data-ttu-id="c49b6-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1151">card holders</span></span>
- <span data-ttu-id="c49b6-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1152">cardholders</span></span>
- <span data-ttu-id="c49b6-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1153">check card</span></span>
- <span data-ttu-id="c49b6-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1154">checkcard</span></span>
- <span data-ttu-id="c49b6-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1155">check cards</span></span>
- <span data-ttu-id="c49b6-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1156">checkcards</span></span>
- <span data-ttu-id="c49b6-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1157">debit card</span></span>
- <span data-ttu-id="c49b6-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1158">debitcard</span></span>
- <span data-ttu-id="c49b6-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1159">debit cards</span></span>
- <span data-ttu-id="c49b6-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1160">debitcards</span></span>
- <span data-ttu-id="c49b6-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1161">atm card</span></span>
- <span data-ttu-id="c49b6-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1162">atmcard</span></span>
- <span data-ttu-id="c49b6-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1163">atm cards</span></span>
- <span data-ttu-id="c49b6-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1164">atmcards</span></span>
- <span data-ttu-id="c49b6-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="c49b6-1165">enroute</span></span>
- <span data-ttu-id="c49b6-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="c49b6-1166">en route</span></span>
- <span data-ttu-id="c49b6-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1167">card type</span></span>
- <span data-ttu-id="c49b6-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1168">carte bancaire</span></span>
- <span data-ttu-id="c49b6-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1169">carte de crédit</span></span>
- <span data-ttu-id="c49b6-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1170">carte de credit</span></span>
- <span data-ttu-id="c49b6-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1171">numéro de carte</span></span>
- <span data-ttu-id="c49b6-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1172">numero de carte</span></span>
- <span data-ttu-id="c49b6-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1173">nº de la carte</span></span>
- <span data-ttu-id="c49b6-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1174">nº de carte</span></span>
- <span data-ttu-id="c49b6-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1175">kreditkarte</span></span>
- <span data-ttu-id="c49b6-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1176">karte</span></span>
- <span data-ttu-id="c49b6-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1177">karteninhaber</span></span>
- <span data-ttu-id="c49b6-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="c49b6-1178">karteninhabers</span></span>
- <span data-ttu-id="c49b6-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="c49b6-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="c49b6-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1181">kreditkartentyp</span></span>
- <span data-ttu-id="c49b6-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1182">eigentümername</span></span>
- <span data-ttu-id="c49b6-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1183">kartennr</span></span> 
- <span data-ttu-id="c49b6-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1184">kartennummer</span></span>
- <span data-ttu-id="c49b6-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1185">kreditkartennummer</span></span>
- <span data-ttu-id="c49b6-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="c49b6-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1187">carta di credito</span></span>
- <span data-ttu-id="c49b6-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1188">carta credito</span></span>
- <span data-ttu-id="c49b6-1189">carta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1189">carta</span></span>
- <span data-ttu-id="c49b6-1190">n carta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1190">n carta</span></span>
- <span data-ttu-id="c49b6-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p110">nr. carta</span></span>
- <span data-ttu-id="c49b6-1193">編號 carta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1193">nr carta</span></span>
- <span data-ttu-id="c49b6-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1194">numero carta</span></span>
- <span data-ttu-id="c49b6-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1195">numero della carta</span></span>
- <span data-ttu-id="c49b6-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1196">numero di carta</span></span>
- <span data-ttu-id="c49b6-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1197">tarjeta credito</span></span>
- <span data-ttu-id="c49b6-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1198">tarjeta de credito</span></span>
- <span data-ttu-id="c49b6-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="c49b6-1199">tarjeta crédito</span></span>
- <span data-ttu-id="c49b6-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="c49b6-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="c49b6-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1201">tarjeta de atm</span></span>
- <span data-ttu-id="c49b6-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1202">tarjeta atm</span></span>
- <span data-ttu-id="c49b6-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1203">tarjeta debito</span></span>
- <span data-ttu-id="c49b6-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1204">tarjeta de debito</span></span>
- <span data-ttu-id="c49b6-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="c49b6-1205">tarjeta débito</span></span>
- <span data-ttu-id="c49b6-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="c49b6-1206">tarjeta de débito</span></span>
- <span data-ttu-id="c49b6-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1207">nº de tarjeta</span></span>
- <span data-ttu-id="c49b6-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p111">no. de tarjeta</span></span>
- <span data-ttu-id="c49b6-1210">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1210">no de tarjeta</span></span>
- <span data-ttu-id="c49b6-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1211">numero de tarjeta</span></span>
- <span data-ttu-id="c49b6-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1212">número de tarjeta</span></span>
- <span data-ttu-id="c49b6-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1213">tarjeta no</span></span>
- <span data-ttu-id="c49b6-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1214">tarjetahabiente</span></span>
- <span data-ttu-id="c49b6-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1215">cartão de crédito</span></span>
- <span data-ttu-id="c49b6-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1216">cartão de credito</span></span>
- <span data-ttu-id="c49b6-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1217">cartao de crédito</span></span>
- <span data-ttu-id="c49b6-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1218">cartao de credito</span></span>
- <span data-ttu-id="c49b6-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1219">cartão de débito</span></span>
- <span data-ttu-id="c49b6-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1220">cartao de débito</span></span>
- <span data-ttu-id="c49b6-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1221">cartão de debito</span></span>
- <span data-ttu-id="c49b6-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1222">cartao de debito</span></span>
- <span data-ttu-id="c49b6-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="c49b6-1223">débito automático</span></span>
- <span data-ttu-id="c49b6-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1224">debito automatico</span></span>
- <span data-ttu-id="c49b6-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="c49b6-1225">número do cartão</span></span>
- <span data-ttu-id="c49b6-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1226">numero do cartão</span></span> 
- <span data-ttu-id="c49b6-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="c49b6-1227">número do cartao</span></span>
- <span data-ttu-id="c49b6-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="c49b6-1228">numero do cartao</span></span>
- <span data-ttu-id="c49b6-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1229">número de cartão</span></span>
- <span data-ttu-id="c49b6-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1230">numero de cartão</span></span>
- <span data-ttu-id="c49b6-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1231">número de cartao</span></span>
- <span data-ttu-id="c49b6-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1232">numero de cartao</span></span>
- <span data-ttu-id="c49b6-1233">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="c49b6-1233">nº do cartão</span></span>
- <span data-ttu-id="c49b6-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1234">nº do cartao</span></span>
- <span data-ttu-id="c49b6-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p112">nº. do cartão</span></span>
- <span data-ttu-id="c49b6-1237">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="c49b6-1237">no do cartão</span></span>
- <span data-ttu-id="c49b6-1238">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="c49b6-1238">no do cartao</span></span>
- <span data-ttu-id="c49b6-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p113">no. do cartão</span></span>
- <span data-ttu-id="c49b6-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="c49b6-1243">	克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1244">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1244">Format</span></span>

<span data-ttu-id="c49b6-1245">九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1246">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1246">Pattern</span></span>

<span data-ttu-id="c49b6-1247">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1248">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1248">Checksum</span></span>

<span data-ttu-id="c49b6-1249">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1250">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1250">Definition</span></span>

<span data-ttu-id="c49b6-1251">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1252">函數 Func_croatia_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1253">從 Keyword_croatia_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1254">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="c49b6-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="c49b6-1256">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1256">Croatian identity card</span></span>
- <span data-ttu-id="c49b6-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="c49b6-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="c49b6-1258">	克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1259">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1259">Format</span></span>

<span data-ttu-id="c49b6-1260">10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1261">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1261">Pattern</span></span>

<span data-ttu-id="c49b6-1262">10 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1262">10 digits:</span></span>
- <span data-ttu-id="c49b6-1263">DDMMYY 格式的六位數，代表出生日期</span><span class="sxs-lookup"><span data-stu-id="c49b6-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-1264">四位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1265">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1265">Checksum</span></span>

<span data-ttu-id="c49b6-1266">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1267">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1267">Definition</span></span>

<span data-ttu-id="c49b6-1268">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1269">函數 Func_croatia_oib_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1270">從 Keyword_croatia_oib_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="c49b6-1271">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1271">The checksum passes.</span></span>

<span data-ttu-id="c49b6-1272">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1273">函數 Func_croatia_oib_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1274">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1275">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="c49b6-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="c49b6-1277">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1277">Personal Identification Number</span></span>
- <span data-ttu-id="c49b6-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="c49b6-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="c49b6-1280">	捷克國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1281">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1281">Format</span></span>

<span data-ttu-id="c49b6-1282">10 位數包含正斜線</span><span class="sxs-lookup"><span data-stu-id="c49b6-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1283">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1283">Pattern</span></span>

<span data-ttu-id="c49b6-1284">10 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1284">10 digits:</span></span>
- <span data-ttu-id="c49b6-1285">六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="c49b6-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-1286">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="c49b6-1286">A forward slash</span></span> 
- <span data-ttu-id="c49b6-1287">四位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1288">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1288">Checksum</span></span>

<span data-ttu-id="c49b6-1289">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1290">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1290">Definition</span></span>

<span data-ttu-id="c49b6-p115">DLP 原則是 85%有信心它已偵測到這種類型的機密資訊時，300 個字元的距離： 函數 Func_czech_id_card 會找出符合模式的內容。從 Keyword_czech_id_card 關鍵字是找到。總和檢查碼會傳遞。</span><span class="sxs-lookup"><span data-stu-id="c49b6-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="c49b6-1294">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1294">Keywords</span></span>

- <span data-ttu-id="c49b6-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="c49b6-1296">Czech national identity card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1296">Czech national identity card</span></span>
- <span data-ttu-id="c49b6-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="c49b6-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="c49b6-1298">	丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1299">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1299">Format</span></span>

<span data-ttu-id="c49b6-1300">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1301">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1301">Pattern</span></span>

<span data-ttu-id="c49b6-1302">10 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1302">10 digits:</span></span>
- <span data-ttu-id="c49b6-1303">DDMMYY 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-1304">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1304">A hyphen</span></span> 
- <span data-ttu-id="c49b6-1305">四位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1306">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1306">Checksum</span></span>

<span data-ttu-id="c49b6-1307">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1308">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1308">Definition</span></span>

<span data-ttu-id="c49b6-p116">DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 規則運算式 Regex_denmark_id 會找出符合模式的內容。從 Keyword_denmark_id 關鍵字是找到。總和檢查碼會傳遞。</span><span class="sxs-lookup"><span data-stu-id="c49b6-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1312">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="c49b6-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="c49b6-1314">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1314">Personal Identification Number</span></span>
- <span data-ttu-id="c49b6-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="c49b6-1315">CPR</span></span>
- <span data-ttu-id="c49b6-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="c49b6-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="c49b6-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="c49b6-1318">藥物執法機構 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1319">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1319">Format</span></span>

<span data-ttu-id="c49b6-1320">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1321">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1321">Pattern</span></span>

<span data-ttu-id="c49b6-1322">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="c49b6-1323">這組可能的字母中的一個字母 (不區分大小寫)：abcdefghjklmnprstux，此為註冊者代碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="c49b6-1324">一個字母 (不區分大小寫)，此為註冊者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="c49b6-1325">七位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1326">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1326">Checksum</span></span>

<span data-ttu-id="c49b6-1327">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1328">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1328">Definition</span></span>

<span data-ttu-id="c49b6-1329">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1330">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1331">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1332">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1332">Keywords</span></span>

<span data-ttu-id="c49b6-1333">無</span><span class="sxs-lookup"><span data-stu-id="c49b6-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="c49b6-1334">歐盟轉帳卡卡號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1335">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1335">Format</span></span>

<span data-ttu-id="c49b6-1336">16 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1337">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1337">Pattern</span></span>

<span data-ttu-id="c49b6-1338">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1339">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1339">Checksum</span></span>

<span data-ttu-id="c49b6-1340">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1341">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1341">Definition</span></span>

<span data-ttu-id="c49b6-1342">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1343">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1344">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="c49b6-1345">找到來自於 Keyword_eu_debit_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="c49b6-1346">找到來自於 Keyword_card_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="c49b6-1347">找到來自於 Keyword_card_security_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="c49b6-1348">找到來自於 Keyword_card_expiration_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="c49b6-1349">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="c49b6-1350">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1351">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="c49b6-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="c49b6-1353">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1353">account number</span></span> 
- <span data-ttu-id="c49b6-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1354">card number</span></span> 
- <span data-ttu-id="c49b6-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1355">card no.</span></span> 
- <span data-ttu-id="c49b6-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1356">security number</span></span> 
- <span data-ttu-id="c49b6-1357">[副本] #</span><span class="sxs-lookup"><span data-stu-id="c49b6-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="c49b6-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="c49b6-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="c49b6-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1359">acct nbr</span></span> 
- <span data-ttu-id="c49b6-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1360">acct num</span></span> 
- <span data-ttu-id="c49b6-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1361">acct no</span></span> 
- <span data-ttu-id="c49b6-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1362">american express</span></span> 
- <span data-ttu-id="c49b6-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1363">americanexpress</span></span> 
- <span data-ttu-id="c49b6-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1364">americano espresso</span></span> 
- <span data-ttu-id="c49b6-1365">amex</span><span class="sxs-lookup"><span data-stu-id="c49b6-1365">amex</span></span> 
- <span data-ttu-id="c49b6-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1366">atm card</span></span> 
- <span data-ttu-id="c49b6-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1367">atm cards</span></span> 
- <span data-ttu-id="c49b6-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1368">atm kaart</span></span> 
- <span data-ttu-id="c49b6-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1369">atmcard</span></span> 
- <span data-ttu-id="c49b6-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1370">atmcards</span></span> 
- <span data-ttu-id="c49b6-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1371">atmkaart</span></span> 
- <span data-ttu-id="c49b6-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1372">atmkaarten</span></span> 
- <span data-ttu-id="c49b6-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1373">bancontact</span></span> 
- <span data-ttu-id="c49b6-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1374">bank card</span></span> 
- <span data-ttu-id="c49b6-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1375">bankkaart</span></span> 
- <span data-ttu-id="c49b6-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1376">card holder</span></span> 
- <span data-ttu-id="c49b6-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1377">card holders</span></span> 
- <span data-ttu-id="c49b6-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1378">card num</span></span> 
- <span data-ttu-id="c49b6-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1379">card number</span></span> 
- <span data-ttu-id="c49b6-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1380">card numbers</span></span> 
- <span data-ttu-id="c49b6-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1381">card type</span></span> 
- <span data-ttu-id="c49b6-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1382">cardano numerico</span></span> 
- <span data-ttu-id="c49b6-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1383">cardholder</span></span> 
- <span data-ttu-id="c49b6-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1384">cardholders</span></span> 
- <span data-ttu-id="c49b6-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1385">cardnumber</span></span> 
- <span data-ttu-id="c49b6-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1386">cardnumbers</span></span> 
- <span data-ttu-id="c49b6-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1387">carta bianca</span></span> 
- <span data-ttu-id="c49b6-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1388">carta credito</span></span> 
- <span data-ttu-id="c49b6-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1389">carta di credito</span></span> 
- <span data-ttu-id="c49b6-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1390">cartao de credito</span></span> 
- <span data-ttu-id="c49b6-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1391">cartao de crédito</span></span> 
- <span data-ttu-id="c49b6-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1392">cartao de debito</span></span> 
- <span data-ttu-id="c49b6-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1393">cartao de débito</span></span> 
- <span data-ttu-id="c49b6-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1394">carte bancaire</span></span> 
- <span data-ttu-id="c49b6-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1395">carte blanche</span></span> 
- <span data-ttu-id="c49b6-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1396">carte bleue</span></span> 
- <span data-ttu-id="c49b6-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1397">carte de credit</span></span> 
- <span data-ttu-id="c49b6-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1398">carte de crédit</span></span> 
- <span data-ttu-id="c49b6-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1399">carte di credito</span></span> 
- <span data-ttu-id="c49b6-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1400">carteblanche</span></span> 
- <span data-ttu-id="c49b6-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1401">cartão de credito</span></span> 
- <span data-ttu-id="c49b6-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1402">cartão de crédito</span></span> 
- <span data-ttu-id="c49b6-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1403">cartão de debito</span></span> 
- <span data-ttu-id="c49b6-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1404">cartão de débito</span></span> 
- <span data-ttu-id="c49b6-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1405">cb</span></span> 
- <span data-ttu-id="c49b6-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1406">ccn</span></span> 
- <span data-ttu-id="c49b6-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1407">check card</span></span> 
- <span data-ttu-id="c49b6-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1408">check cards</span></span> 
- <span data-ttu-id="c49b6-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1409">checkcard</span></span>
- <span data-ttu-id="c49b6-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1410">checkcards</span></span> 
- <span data-ttu-id="c49b6-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1411">chequekaart</span></span> 
- <span data-ttu-id="c49b6-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1412">cirrus</span></span> 
- <span data-ttu-id="c49b6-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="c49b6-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1414">controlekaart</span></span> 
- <span data-ttu-id="c49b6-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1415">controlekaarten</span></span> 
- <span data-ttu-id="c49b6-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1416">credit card</span></span> 
- <span data-ttu-id="c49b6-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1417">credit cards</span></span> 
- <span data-ttu-id="c49b6-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1418">creditcard</span></span> 
- <span data-ttu-id="c49b6-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1419">creditcards</span></span> 
- <span data-ttu-id="c49b6-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1420">debetkaart</span></span> 
- <span data-ttu-id="c49b6-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1421">debetkaarten</span></span> 
- <span data-ttu-id="c49b6-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1422">debit card</span></span> 
- <span data-ttu-id="c49b6-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1423">debit cards</span></span> 
- <span data-ttu-id="c49b6-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1424">debitcard</span></span> 
- <span data-ttu-id="c49b6-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1425">debitcards</span></span> 
- <span data-ttu-id="c49b6-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1426">debito automatico</span></span> 
- <span data-ttu-id="c49b6-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1427">diners club</span></span> 
- <span data-ttu-id="c49b6-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1428">dinersclub</span></span> 
- <span data-ttu-id="c49b6-1429">探索</span><span class="sxs-lookup"><span data-stu-id="c49b6-1429">discover</span></span> 
- <span data-ttu-id="c49b6-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1430">discover card</span></span> 
- <span data-ttu-id="c49b6-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1431">discover cards</span></span> 
- <span data-ttu-id="c49b6-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1432">discovercard</span></span> 
- <span data-ttu-id="c49b6-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1433">discovercards</span></span> 
- <span data-ttu-id="c49b6-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="c49b6-1434">débito automático</span></span>
- <span data-ttu-id="c49b6-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1435">edc</span></span> 
- <span data-ttu-id="c49b6-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1436">eigentümername</span></span> 
- <span data-ttu-id="c49b6-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1437">european debit card</span></span> 
- <span data-ttu-id="c49b6-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1438">hoofdkaart</span></span> 
- <span data-ttu-id="c49b6-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="c49b6-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1440">in viaggio</span></span> 
- <span data-ttu-id="c49b6-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1441">japanese card bureau</span></span> 
- <span data-ttu-id="c49b6-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="c49b6-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1443">jcb</span></span> 
- <span data-ttu-id="c49b6-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1444">kaart</span></span> 
- <span data-ttu-id="c49b6-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1445">kaart num</span></span> 
- <span data-ttu-id="c49b6-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1446">kaartaantal</span></span> 
- <span data-ttu-id="c49b6-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1447">kaartaantallen</span></span> 
- <span data-ttu-id="c49b6-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1448">kaarthouder</span></span> 
- <span data-ttu-id="c49b6-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1449">kaarthouders</span></span> 
- <span data-ttu-id="c49b6-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1450">karte</span></span>  
- <span data-ttu-id="c49b6-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1451">karteninhaber</span></span> 
- <span data-ttu-id="c49b6-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="c49b6-1452">karteninhabers</span></span>
- <span data-ttu-id="c49b6-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1453">kartennr</span></span> 
- <span data-ttu-id="c49b6-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1454">kartennummer</span></span> 
- <span data-ttu-id="c49b6-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1455">kreditkarte</span></span> 
- <span data-ttu-id="c49b6-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="c49b6-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="c49b6-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="c49b6-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="c49b6-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="c49b6-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1461">maestro</span></span> 
- <span data-ttu-id="c49b6-1462">master card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1462">master card</span></span> 
- <span data-ttu-id="c49b6-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1463">master cards</span></span> 
- <span data-ttu-id="c49b6-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1464">mastercard</span></span> 
- <span data-ttu-id="c49b6-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="c49b6-1465">mastercards</span></span> 
- <span data-ttu-id="c49b6-1466">mc</span><span class="sxs-lookup"><span data-stu-id="c49b6-1466">mc</span></span> 
- <span data-ttu-id="c49b6-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1467">mister cash</span></span> 
- <span data-ttu-id="c49b6-1468">n carta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1468">n carta</span></span> 
- <span data-ttu-id="c49b6-1469">carta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1469">carta</span></span> 
- <span data-ttu-id="c49b6-1470">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1470">no de tarjeta</span></span> 
- <span data-ttu-id="c49b6-1471">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="c49b6-1471">no do cartao</span></span> 
- <span data-ttu-id="c49b6-1472">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="c49b6-1472">no do cartão</span></span> 
- <span data-ttu-id="c49b6-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="c49b6-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p118">no. do cartao</span></span> 
- <span data-ttu-id="c49b6-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p119">no. do cartão</span></span> 
- <span data-ttu-id="c49b6-1479">編號 carta</span><span class="sxs-lookup"><span data-stu-id="c49b6-1479">nr carta</span></span> 
- <span data-ttu-id="c49b6-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p120">nr. carta</span></span> 
- <span data-ttu-id="c49b6-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1482">numeri di scheda</span></span> 
- <span data-ttu-id="c49b6-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1483">numero carta</span></span> 
- <span data-ttu-id="c49b6-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1484">numero de cartao</span></span> 
- <span data-ttu-id="c49b6-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1485">numero de carte</span></span> 
- <span data-ttu-id="c49b6-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1486">numero de cartão</span></span> 
- <span data-ttu-id="c49b6-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1487">numero de tarjeta</span></span>
- <span data-ttu-id="c49b6-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1488">numero della carta</span></span> 
- <span data-ttu-id="c49b6-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1489">numero di carta</span></span> 
- <span data-ttu-id="c49b6-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1490">numero di scheda</span></span> 
- <span data-ttu-id="c49b6-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1491">numero do cartao</span></span> 
- <span data-ttu-id="c49b6-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1492">numero do cartão</span></span> 
- <span data-ttu-id="c49b6-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1493">numéro de carte</span></span> 
- <span data-ttu-id="c49b6-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1494">nº carta</span></span> 
- <span data-ttu-id="c49b6-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1495">nº de carte</span></span> 
- <span data-ttu-id="c49b6-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1496">nº de la carte</span></span> 
- <span data-ttu-id="c49b6-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="c49b6-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1498">nº do cartao</span></span> 
- <span data-ttu-id="c49b6-1499">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="c49b6-1499">nº do cartão</span></span> 
- <span data-ttu-id="c49b6-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p121">nº. do cartão</span></span> 
- <span data-ttu-id="c49b6-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1502">número de cartao</span></span> 
- <span data-ttu-id="c49b6-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1503">número de cartão</span></span> 
- <span data-ttu-id="c49b6-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1504">número de tarjeta</span></span> 
- <span data-ttu-id="c49b6-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="c49b6-1505">número do cartao</span></span> 
- <span data-ttu-id="c49b6-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="c49b6-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="c49b6-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="c49b6-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1509">scheda della banca</span></span> 
- <span data-ttu-id="c49b6-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1510">scheda di controllo</span></span> 
- <span data-ttu-id="c49b6-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1511">scheda di debito</span></span> 
- <span data-ttu-id="c49b6-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1512">scheda matrice</span></span> 
- <span data-ttu-id="c49b6-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="c49b6-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1514">schede di controllo</span></span> 
- <span data-ttu-id="c49b6-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1515">schede di debito</span></span> 
- <span data-ttu-id="c49b6-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1516">schede matrici</span></span> 
- <span data-ttu-id="c49b6-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="c49b6-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1518">scoprono le schede</span></span> 
- <span data-ttu-id="c49b6-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1519">solo</span></span> 
- <span data-ttu-id="c49b6-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1520">supporti di scheda</span></span> 
- <span data-ttu-id="c49b6-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1521">supporto di scheda</span></span> 
- <span data-ttu-id="c49b6-1522">參數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1522">switch</span></span> 
- <span data-ttu-id="c49b6-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1523">tarjeta atm</span></span> 
- <span data-ttu-id="c49b6-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1524">tarjeta credito</span></span> 
- <span data-ttu-id="c49b6-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="c49b6-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="c49b6-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="c49b6-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1528">tarjeta debito</span></span> 
- <span data-ttu-id="c49b6-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1529">tarjeta no</span></span>
- <span data-ttu-id="c49b6-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="c49b6-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1531">tipo della scheda</span></span> 
- <span data-ttu-id="c49b6-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="c49b6-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="c49b6-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1533">scheda</span></span> 
- <span data-ttu-id="c49b6-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1534">v pay</span></span> 
- <span data-ttu-id="c49b6-1535">v 工資</span><span class="sxs-lookup"><span data-stu-id="c49b6-1535">v-pay</span></span> 
- <span data-ttu-id="c49b6-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1536">visa</span></span> 
- <span data-ttu-id="c49b6-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1537">visa plus</span></span> 
- <span data-ttu-id="c49b6-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1538">visa electron</span></span> 
- <span data-ttu-id="c49b6-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1539">visto</span></span> 
- <span data-ttu-id="c49b6-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1540">visum</span></span> 
- <span data-ttu-id="c49b6-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="c49b6-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="c49b6-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="c49b6-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1543">card identification number</span></span>
- <span data-ttu-id="c49b6-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="c49b6-1544">card verification</span></span> 
- <span data-ttu-id="c49b6-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1545">cardi la verifica</span></span> 
- <span data-ttu-id="c49b6-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1546">cid</span></span> 
- <span data-ttu-id="c49b6-1547">cod seg</span><span class="sxs-lookup"><span data-stu-id="c49b6-1547">cod seg</span></span> 
- <span data-ttu-id="c49b6-1548">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="c49b6-1548">cod seguranca</span></span> 
- <span data-ttu-id="c49b6-1549">cod segurança</span><span class="sxs-lookup"><span data-stu-id="c49b6-1549">cod segurança</span></span> 
- <span data-ttu-id="c49b6-1550">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="c49b6-1550">cod sicurezza</span></span> 
- <span data-ttu-id="c49b6-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p122">cod. seg</span></span> 
- <span data-ttu-id="c49b6-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p123">cod. seguranca</span></span> 
- <span data-ttu-id="c49b6-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p124">cod. segurança</span></span> 
- <span data-ttu-id="c49b6-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="c49b6-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="c49b6-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1560">codice di verifica</span></span> 
- <span data-ttu-id="c49b6-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1561">codigo</span></span> 
- <span data-ttu-id="c49b6-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="c49b6-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1563">codigo de segurança</span></span> 
- <span data-ttu-id="c49b6-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1564">crittogramma</span></span> 
- <span data-ttu-id="c49b6-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1565">cryptogram</span></span> 
- <span data-ttu-id="c49b6-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1566">cryptogramme</span></span> 
- <span data-ttu-id="c49b6-1567">cv2</span><span class="sxs-lookup"><span data-stu-id="c49b6-1567">cv2</span></span> 
- <span data-ttu-id="c49b6-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1568">cvc</span></span> 
- <span data-ttu-id="c49b6-1569">cvc2</span><span class="sxs-lookup"><span data-stu-id="c49b6-1569">cvc2</span></span> 
- <span data-ttu-id="c49b6-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1570">cvn</span></span> 
- <span data-ttu-id="c49b6-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1571">cvv</span></span> 
- <span data-ttu-id="c49b6-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="c49b6-1572">cvv2</span></span> 
- <span data-ttu-id="c49b6-1573">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="c49b6-1573">cód seguranca</span></span> 
- <span data-ttu-id="c49b6-1574">cód segurança</span><span class="sxs-lookup"><span data-stu-id="c49b6-1574">cód segurança</span></span> 
- <span data-ttu-id="c49b6-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p126">cód. seguranca</span></span> 
- <span data-ttu-id="c49b6-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p127">cód. segurança</span></span> 
- <span data-ttu-id="c49b6-1579">código
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1579">código</span></span> 
- <span data-ttu-id="c49b6-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1580">código de seguranca</span></span> 
- <span data-ttu-id="c49b6-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1581">código de segurança</span></span> 
- <span data-ttu-id="c49b6-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1582">de kaart controle</span></span> 
- <span data-ttu-id="c49b6-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1583">geeft nr uit</span></span> 
- <span data-ttu-id="c49b6-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1584">issue no</span></span> 
- <span data-ttu-id="c49b6-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1585">issue number</span></span> 
- <span data-ttu-id="c49b6-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="c49b6-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="c49b6-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="c49b6-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1589">kwestieaantal</span></span> 
- <span data-ttu-id="c49b6-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="c49b6-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="c49b6-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1594">numero de securite</span></span> 
- <span data-ttu-id="c49b6-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1595">numero de verificacao</span></span> 
- <span data-ttu-id="c49b6-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="c49b6-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="c49b6-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="c49b6-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1598">scheda</span></span> 
- <span data-ttu-id="c49b6-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="c49b6-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="c49b6-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="c49b6-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="c49b6-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1603">número de verificação</span></span> 
- <span data-ttu-id="c49b6-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1604">perno il blocco</span></span> 
- <span data-ttu-id="c49b6-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1605">pin block</span></span> 
- <span data-ttu-id="c49b6-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1606">prufziffer</span></span> 
- <span data-ttu-id="c49b6-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1607">prüfziffer</span></span> 
- <span data-ttu-id="c49b6-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1608">security code</span></span> 
- <span data-ttu-id="c49b6-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1609">security no</span></span> 
- <span data-ttu-id="c49b6-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1610">security number</span></span> 
- <span data-ttu-id="c49b6-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1611">sicherheits kode</span></span> 
- <span data-ttu-id="c49b6-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1612">sicherheitscode</span></span> 
- <span data-ttu-id="c49b6-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="c49b6-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1614">speldblok</span></span> 
- <span data-ttu-id="c49b6-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1615">veiligheid nr</span></span> 
- <span data-ttu-id="c49b6-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="c49b6-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1617">veiligheidscode</span></span> 
- <span data-ttu-id="c49b6-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="c49b6-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="c49b6-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="c49b6-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="c49b6-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1621">ablauf</span></span> 
- <span data-ttu-id="c49b6-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1622">data de expiracao</span></span> 
- <span data-ttu-id="c49b6-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1623">data de expiração</span></span> 
- <span data-ttu-id="c49b6-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1624">data del exp</span></span> 
- <span data-ttu-id="c49b6-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1625">data di exp</span></span> 
- <span data-ttu-id="c49b6-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1626">data di scadenza</span></span> 
- <span data-ttu-id="c49b6-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1627">data em que expira</span></span> 
- <span data-ttu-id="c49b6-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1628">data scad</span></span> 
- <span data-ttu-id="c49b6-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1629">data scadenza</span></span> 
- <span data-ttu-id="c49b6-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1630">date de validité</span></span> 
- <span data-ttu-id="c49b6-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1631">datum afloop</span></span> 
- <span data-ttu-id="c49b6-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1632">datum van exp</span></span> 
- <span data-ttu-id="c49b6-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1633">de afloop</span></span> 
- <span data-ttu-id="c49b6-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1634">espira</span></span> 
- <span data-ttu-id="c49b6-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1635">espira</span></span> 
- <span data-ttu-id="c49b6-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1636">exp date</span></span> 
- <span data-ttu-id="c49b6-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1637">exp datum</span></span> 
- <span data-ttu-id="c49b6-1638">到期日</span><span class="sxs-lookup"><span data-stu-id="c49b6-1638">expiration</span></span> 
- <span data-ttu-id="c49b6-1639">expire
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1639">expire</span></span> 
- <span data-ttu-id="c49b6-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1640">expires</span></span> 
- <span data-ttu-id="c49b6-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1641">expiry</span></span> 
- <span data-ttu-id="c49b6-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="c49b6-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1643">fecha de venc</span></span> 
- <span data-ttu-id="c49b6-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1644">gultig bis</span></span> 
- <span data-ttu-id="c49b6-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="c49b6-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1646">gültig bis</span></span> 
- <span data-ttu-id="c49b6-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="c49b6-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1648">la scadenza</span></span> 
- <span data-ttu-id="c49b6-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1649">scadenza</span></span> 
- <span data-ttu-id="c49b6-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1650">valable</span></span> 
- <span data-ttu-id="c49b6-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1651">validade</span></span> 
- <span data-ttu-id="c49b6-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1652">valido hasta</span></span> 
- <span data-ttu-id="c49b6-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1653">valor</span></span> 
- <span data-ttu-id="c49b6-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1654">venc</span></span> 
- <span data-ttu-id="c49b6-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1655">vencimento</span></span> 
- <span data-ttu-id="c49b6-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1656">vencimiento</span></span> 
- <span data-ttu-id="c49b6-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1657">verloopt</span></span> 
- <span data-ttu-id="c49b6-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1658">vervaldag</span></span> 
- <span data-ttu-id="c49b6-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1659">vervaldatum</span></span> 
- <span data-ttu-id="c49b6-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1660">vto</span></span> 
- <span data-ttu-id="c49b6-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="c49b6-1662">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1662">EU Driver's License Number</span></span>

<span data-ttu-id="c49b6-1663">若要深入了解，請參閱[歐盟駕照編號敏感資訊類型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="c49b6-1664">歐盟國家識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1664">EU National Identification Number</span></span>

<span data-ttu-id="c49b6-1665">若要深入了解，請參閱[國家識別碼歐盟敏感資訊類型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="c49b6-1666">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1666">EU Passport Number</span></span>

<span data-ttu-id="c49b6-1667">若要深入了解，請參閱[歐盟護照號碼敏感資訊類型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="c49b6-1668">歐盟社會安全號碼或對等資格識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="c49b6-1669">如需了解，請參閱[歐盟社會安全號碼或對等識別碼敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="c49b6-1670">歐盟稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="c49b6-1671">若要深入了解，請參閱[歐盟稅識別碼敏感資訊類型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="c49b6-1672">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="c49b6-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1673">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1673">Format</span></span>

<span data-ttu-id="c49b6-1674">六位數加上一個指出世紀的字元，再加上三位數和一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1675">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1675">Pattern</span></span>

<span data-ttu-id="c49b6-1676">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="c49b6-1677">六位數的格式為 DDMMYY，此為出生日期</span><span class="sxs-lookup"><span data-stu-id="c49b6-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="c49b6-1678">世紀標記 ('-'、'+' 或 'a')</span><span class="sxs-lookup"><span data-stu-id="c49b6-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="c49b6-1679">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="c49b6-1680">一個做為檢查碼的數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1681">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1681">Checksum</span></span>

<span data-ttu-id="c49b6-1682">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1683">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1683">Definition</span></span>

<span data-ttu-id="c49b6-1684">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1685">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1686">找到來自於 Keyword_finnish_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="c49b6-1687">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1688">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1688">Keywords</span></span>

- <span data-ttu-id="c49b6-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="c49b6-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="c49b6-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="c49b6-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="c49b6-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="c49b6-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="c49b6-1692">Personbeteckning</span></span>
- <span data-ttu-id="c49b6-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="c49b6-1694">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1694">Finland Passport Number</span></span>

<span data-ttu-id="c49b6-p130">格式化九個字母和數字模式組合的九個字母和數字的組合： 兩個字母 （不區分大小寫） 七位數總和檢查碼沒有定義 DLP 原則是 75%健全的如果它是已偵測這種敏感資訊類型、 兩者之間300 個字元的鄰近： 規則運算式 Regex_finland_passport_number 會找出符合模式的內容。從 Keyword_finland_passport_number 關鍵字是找到。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
</Entity>關鍵字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="c49b6-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="c49b6-1699">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1700">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1700">Format</span></span>

<span data-ttu-id="c49b6-1701">12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1702">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1702">Pattern</span></span>

<span data-ttu-id="c49b6-1703">可驗證以忽略類似模式 (例如法國電話號碼) 的 12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1704">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1704">Checksum</span></span>

<span data-ttu-id="c49b6-1705">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1706">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1706">Definition</span></span>

<span data-ttu-id="c49b6-1707">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1708">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1709">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="c49b6-1710">找到來自於 Keyword_french_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="c49b6-1711">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1712">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="c49b6-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="c49b6-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="c49b6-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c49b6-1714">drivers licence</span></span>
- <span data-ttu-id="c49b6-1715">
drivers license</span><span class="sxs-lookup"><span data-stu-id="c49b6-1715">drivers license</span></span>
- <span data-ttu-id="c49b6-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1716">driving licence</span></span>
- <span data-ttu-id="c49b6-1717">主導授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1717">driving license</span></span>
- <span data-ttu-id="c49b6-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="c49b6-1718">permis de conduire</span></span>
- <span data-ttu-id="c49b6-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1719">licence number</span></span>
- <span data-ttu-id="c49b6-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1720">license number</span></span>
- <span data-ttu-id="c49b6-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="c49b6-1721">licence numbers</span></span>
- <span data-ttu-id="c49b6-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="c49b6-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="c49b6-1723">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="c49b6-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1724">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1724">Format</span></span>

<span data-ttu-id="c49b6-1725">12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1726">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1726">Pattern</span></span>

<span data-ttu-id="c49b6-1727">12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1728">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1728">Checksum</span></span>

<span data-ttu-id="c49b6-1729">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1730">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1730">Definition</span></span>

<span data-ttu-id="c49b6-1731">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1732">規則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1733">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1733">Keywords</span></span>

<span data-ttu-id="c49b6-1734">無</span><span class="sxs-lookup"><span data-stu-id="c49b6-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="c49b6-1735">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1736">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1736">Format</span></span>

<span data-ttu-id="c49b6-1737">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1738">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1738">Pattern</span></span>

<span data-ttu-id="c49b6-1739">九個數字和字母：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="c49b6-1740">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1740">Two digits</span></span> 
- <span data-ttu-id="c49b6-1741">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-1742">五位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1743">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1743">Checksum</span></span>

<span data-ttu-id="c49b6-1744">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1745">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1745">Definition</span></span>

<span data-ttu-id="c49b6-1746">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1747">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1748">找到來自於 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1749">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="c49b6-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-1750">Keyword_passport</span></span>

- <span data-ttu-id="c49b6-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1751">Passport Number</span></span>
- <span data-ttu-id="c49b6-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="c49b6-1752">Passport No</span></span>
- <span data-ttu-id="c49b6-1753">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1753">Passport #</span></span>
- <span data-ttu-id="c49b6-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1754">Passport#</span></span>
- <span data-ttu-id="c49b6-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="c49b6-1755">PassportID</span></span>
- <span data-ttu-id="c49b6-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1756">Passportno</span></span>
- <span data-ttu-id="c49b6-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1757">passportnumber</span></span>
- <span data-ttu-id="c49b6-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="c49b6-1758">パスポート</span></span>
- <span data-ttu-id="c49b6-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1759">パスポート番号</span></span>
- <span data-ttu-id="c49b6-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1760">パスポートのNum</span></span>
- <span data-ttu-id="c49b6-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1761">パスポート ＃</span></span> 
- <span data-ttu-id="c49b6-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="c49b6-1762">Numéro de passeport</span></span>
- <span data-ttu-id="c49b6-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="c49b6-1763">Passeport n °</span></span>
- <span data-ttu-id="c49b6-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1764">Passeport Non</span></span>
- <span data-ttu-id="c49b6-1765">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1765">Passeport #</span></span>
- <span data-ttu-id="c49b6-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1766">Passeport#</span></span>
- <span data-ttu-id="c49b6-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="c49b6-1767">PasseportNon</span></span>
- <span data-ttu-id="c49b6-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="c49b6-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="c49b6-1769">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="c49b6-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1770">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1770">Format</span></span>

<span data-ttu-id="c49b6-1771">15 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1772">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1772">Pattern</span></span>

<span data-ttu-id="c49b6-1773">必須符合兩個模式之一：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="c49b6-1774">後面接著空格後面接著兩個位數字的數字 13</span><span class="sxs-lookup"><span data-stu-id="c49b6-1774">13 digits followed by a space followed by two digits</span></span></br>
<span data-ttu-id="c49b6-1775">或</span><span class="sxs-lookup"><span data-stu-id="c49b6-1775">or</span></span>
- <span data-ttu-id="c49b6-1776">15 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1777">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1777">Checksum</span></span>

<span data-ttu-id="c49b6-1778">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1779">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1779">Definition</span></span>

<span data-ttu-id="c49b6-1780">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1781">Func_french_insee 或 Func_fr_insee 函數會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1782">找到來自於 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="c49b6-1783">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1783">The checksum passes.</span></span>

<span data-ttu-id="c49b6-1784">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1785">Func_french_insee 或 Func_fr_insee 函數會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1786">找不到來自於 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="c49b6-1787">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1788">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="c49b6-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="c49b6-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="c49b6-1790">insee</span><span class="sxs-lookup"><span data-stu-id="c49b6-1790">insee</span></span>
- <span data-ttu-id="c49b6-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1791">securité sociale</span></span>
- <span data-ttu-id="c49b6-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1792">securite sociale</span></span>
- <span data-ttu-id="c49b6-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="c49b6-1793">national id</span></span>
- <span data-ttu-id="c49b6-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-1794">national identification</span></span>
- <span data-ttu-id="c49b6-1795">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="c49b6-1795">numéro d'identité</span></span>
- <span data-ttu-id="c49b6-1796">沒有 d'identité</span><span class="sxs-lookup"><span data-stu-id="c49b6-1796">no d'identité</span></span>
- <span data-ttu-id="c49b6-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="c49b6-p131">no. d'identité</span></span>
- <span data-ttu-id="c49b6-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="c49b6-1799">numero d'identite</span></span>
- <span data-ttu-id="c49b6-1800">沒有 d'identite</span><span class="sxs-lookup"><span data-stu-id="c49b6-1800">no d'identite</span></span>
- <span data-ttu-id="c49b6-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="c49b6-p132">no. d'identite</span></span>
- <span data-ttu-id="c49b6-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1803">social security number</span></span>
- <span data-ttu-id="c49b6-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="c49b6-1804">social security code</span></span>
- <span data-ttu-id="c49b6-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1805">social insurance number</span></span>
- <span data-ttu-id="c49b6-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="c49b6-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1807">d'identité nationale</span></span>
- <span data-ttu-id="c49b6-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="c49b6-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="c49b6-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="c49b6-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="c49b6-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="c49b6-1811">numéro de sécu</span></span>
- <span data-ttu-id="c49b6-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="c49b6-1813">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1814">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1814">Format</span></span>

<span data-ttu-id="c49b6-1815">11 個數字和字母的組合</span><span class="sxs-lookup"><span data-stu-id="c49b6-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1816">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1816">Pattern</span></span>

<span data-ttu-id="c49b6-1817">11 個數字和字母 (不區分大小寫)：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="c49b6-1818">一個數字或字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1818">A digit or letter</span></span> 
- <span data-ttu-id="c49b6-1819">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1819">Two digits</span></span> 
- <span data-ttu-id="c49b6-1820">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1820">Six digits or letters</span></span> 
- <span data-ttu-id="c49b6-1821">一個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1821">A digit</span></span> 
- <span data-ttu-id="c49b6-1822">一個數字或字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1823">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1823">Checksum</span></span>

<span data-ttu-id="c49b6-1824">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1825">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1825">Definition</span></span>

<span data-ttu-id="c49b6-1826">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1827">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1828">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="c49b6-1829">找到來自於 Keyword_german_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="c49b6-1830">找到來自於 Keyword_german_drivers_license_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="c49b6-1831">找到來自於 Keyword_german_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="c49b6-1832">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1833">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="c49b6-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="c49b6-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="c49b6-1835">Führerschein</span></span>
- <span data-ttu-id="c49b6-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="c49b6-1836">Fuhrerschein</span></span>
- <span data-ttu-id="c49b6-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="c49b6-1837">Fuehrerschein</span></span>
- <span data-ttu-id="c49b6-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="c49b6-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="c49b6-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="c49b6-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1841">Führerschein-</span></span> 
- <span data-ttu-id="c49b6-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="c49b6-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="c49b6-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="c49b6-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="c49b6-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="c49b6-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="c49b6-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="c49b6-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="c49b6-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="c49b6-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="c49b6-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="c49b6-1850">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="c49b6-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="c49b6-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="c49b6-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="c49b6-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="c49b6-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="c49b6-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="c49b6-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="c49b6-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="c49b6-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="c49b6-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="c49b6-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="c49b6-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="c49b6-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="c49b6-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="c49b6-1862">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="c49b6-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="c49b6-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="c49b6-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="c49b6-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="c49b6-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="c49b6-1868">DL</span><span class="sxs-lookup"><span data-stu-id="c49b6-1868">DL</span></span> 
- <span data-ttu-id="c49b6-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="c49b6-1869">DLS</span></span>
- <span data-ttu-id="c49b6-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1870">Driv Lic</span></span> 
- <span data-ttu-id="c49b6-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1871">Driv Licen</span></span> 
- <span data-ttu-id="c49b6-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="c49b6-1872">Driv License</span></span>
- <span data-ttu-id="c49b6-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1873">Driv Licenses</span></span> 
- <span data-ttu-id="c49b6-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1874">Driv Licence</span></span> 
- <span data-ttu-id="c49b6-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1875">Driv Licences</span></span> 
- <span data-ttu-id="c49b6-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1876">Driv Lic</span></span> 
- <span data-ttu-id="c49b6-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1877">Driver Licen</span></span> 
- <span data-ttu-id="c49b6-1878">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1878">Driver License</span></span> 
- <span data-ttu-id="c49b6-1879">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1879">Driver Licenses</span></span> 
- <span data-ttu-id="c49b6-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1880">Driver Licence</span></span> 
- <span data-ttu-id="c49b6-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1881">Driver Licences</span></span> 
- <span data-ttu-id="c49b6-1882">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-1882">Drivers Lic</span></span> 
- <span data-ttu-id="c49b6-1883">發行的驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="c49b6-1883">Drivers Licen</span></span> 
- <span data-ttu-id="c49b6-1884">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1884">Drivers License</span></span> 
- <span data-ttu-id="c49b6-1885">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="c49b6-1886">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1886">Drivers Licence</span></span> 
- <span data-ttu-id="c49b6-1887">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1887">Drivers Licences</span></span> 
- <span data-ttu-id="c49b6-1888">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-1888">Driver's Lic</span></span> 
- <span data-ttu-id="c49b6-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1889">Driver's Licen</span></span> 
- <span data-ttu-id="c49b6-1890">駕照</span><span class="sxs-lookup"><span data-stu-id="c49b6-1890">Driver's License</span></span> 
- <span data-ttu-id="c49b6-1891">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="c49b6-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1892">Driver's Licence</span></span> 
- <span data-ttu-id="c49b6-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1893">Driver's Licences</span></span> 
- <span data-ttu-id="c49b6-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1894">Driving Lic</span></span> 
- <span data-ttu-id="c49b6-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1895">Driving Licen</span></span> 
- <span data-ttu-id="c49b6-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1896">Driving License</span></span> 
- <span data-ttu-id="c49b6-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1897">Driving Licenses</span></span> 
- <span data-ttu-id="c49b6-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="c49b6-1898">Driving Licence</span></span> 
- <span data-ttu-id="c49b6-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="c49b6-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="c49b6-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="c49b6-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="c49b6-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="c49b6-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="c49b6-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="c49b6-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1904">No-Führerschein</span></span> 
- <span data-ttu-id="c49b6-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="c49b6-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="c49b6-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1907">N-Führerschein</span></span> 
- <span data-ttu-id="c49b6-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="c49b6-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="c49b6-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="c49b6-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="c49b6-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="c49b6-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="c49b6-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1913">No-Führerschein</span></span> 
- <span data-ttu-id="c49b6-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="c49b6-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="c49b6-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1916">N-Führerschein</span></span> 
- <span data-ttu-id="c49b6-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="c49b6-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="c49b6-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="c49b6-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="c49b6-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="c49b6-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="c49b6-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="c49b6-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="c49b6-1921">ausstellungsort</span></span>
- <span data-ttu-id="c49b6-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="c49b6-1922">ausstellende behöde</span></span>
- <span data-ttu-id="c49b6-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="c49b6-1923">ausstellende behorde</span></span>
- <span data-ttu-id="c49b6-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="c49b6-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="c49b6-1925">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1926">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1926">Format</span></span>

<span data-ttu-id="c49b6-1927">10 個數字或字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1928">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1928">Pattern</span></span>

<span data-ttu-id="c49b6-1929">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="c49b6-1930">第一個字元是一個數字或 C、F、G、H、J、K 之中的一個字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="c49b6-1931">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1931">Three digits</span></span> 
- <span data-ttu-id="c49b6-1932">5 個數字或 C、H、J-N、P、R、T、V-Z 之中的字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="c49b6-1933">一個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1934">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1934">Checksum</span></span>

<span data-ttu-id="c49b6-1935">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1936">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1936">Definition</span></span>

<span data-ttu-id="c49b6-1937">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1938">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1939">找到五個關鍵字清單任一者中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="c49b6-1940">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1940">The checksum passes.</span></span>

<span data-ttu-id="c49b6-1941">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1942">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1943">找到五個關鍵字清單任一者中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="c49b6-1944">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-1945">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="c49b6-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="c49b6-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="c49b6-1947">reisepass</span></span>
- <span data-ttu-id="c49b6-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="c49b6-1948">reisepasse</span></span>
- <span data-ttu-id="c49b6-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1949">reisepassnummer</span></span>
- <span data-ttu-id="c49b6-1950">passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-1950">passport</span></span>
- <span data-ttu-id="c49b6-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="c49b6-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="c49b6-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="c49b6-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="c49b6-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="c49b6-1953">geburtsdatum</span></span>
- <span data-ttu-id="c49b6-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="c49b6-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="c49b6-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="c49b6-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="c49b6-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="c49b6-1957">否-Reisepass 編號 Reisepass</span><span class="sxs-lookup"><span data-stu-id="c49b6-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="c49b6-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="c49b6-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="c49b6-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="c49b6-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="c49b6-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="c49b6-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="c49b6-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="c49b6-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="c49b6-1962">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1963">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1963">Format</span></span>

<span data-ttu-id="c49b6-1964">1 年 11 月 2010年自： 九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="c49b6-1965">從 1 年 4 月 1987 直到 31 年 10 月 2010年: 10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1966">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1966">Pattern</span></span>

<span data-ttu-id="c49b6-1967">自從 2010 年 11 月 1 日：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="c49b6-1968">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-1969">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1969">Eight digits</span></span>

<span data-ttu-id="c49b6-1970">從 1 年 4 月 1987 31 年 10 月 2010年之前：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="c49b6-1971">10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1972">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1972">Checksum</span></span>

<span data-ttu-id="c49b6-1973">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-1974">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-1974">Definition</span></span>

<span data-ttu-id="c49b6-1975">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-1976">規則運算式 Regex_germany_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-1977">從 Keyword_germany_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-1978">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="c49b6-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="c49b6-1980">Identity Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-1980">Identity Card</span></span>
- <span data-ttu-id="c49b6-1981">ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-1981">ID</span></span>
- <span data-ttu-id="c49b6-1982">Identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-1982">Identification</span></span>
- <span data-ttu-id="c49b6-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="c49b6-1983">Personalausweis</span></span>
- <span data-ttu-id="c49b6-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="c49b6-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="c49b6-1985">Ausweis</span></span>
- <span data-ttu-id="c49b6-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="c49b6-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="c49b6-1987">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="c49b6-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-1988">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1988">Format</span></span>

<span data-ttu-id="c49b6-1989">7-8 個字母和數字加上破折號的組合</span><span class="sxs-lookup"><span data-stu-id="c49b6-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-1990">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-1990">Pattern</span></span>

<span data-ttu-id="c49b6-1991">七個字母和數字 (舊格式)︰</span><span class="sxs-lookup"><span data-stu-id="c49b6-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="c49b6-1992">一個字母 (希臘文字母的任何字母) </span><span class="sxs-lookup"><span data-stu-id="c49b6-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="c49b6-1993">一個破折號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1993">A dash</span></span> 
- <span data-ttu-id="c49b6-1994">六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1994">Six digits</span></span>

<span data-ttu-id="c49b6-1995">八個字母和數字 (新格式)︰</span><span class="sxs-lookup"><span data-stu-id="c49b6-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="c49b6-1996">在希臘文與拉丁文字母中皆有大寫形態的兩個字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="c49b6-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="c49b6-1997">一個破折號</span><span class="sxs-lookup"><span data-stu-id="c49b6-1997">A dash</span></span> 
- <span data-ttu-id="c49b6-1998">六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-1999">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-1999">Checksum</span></span>

<span data-ttu-id="c49b6-2000">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2001">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2001">Definition</span></span>

<span data-ttu-id="c49b6-2002">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2003">規則運算式 Regex_greece_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2004">從 Keyword_greece_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2005">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="c49b6-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="c49b6-2007">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2007">Greek identity Card</span></span>
- <span data-ttu-id="c49b6-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="c49b6-2008">Tautotita</span></span>
- <span data-ttu-id="c49b6-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="c49b6-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="c49b6-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="c49b6-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="c49b6-2011">香港身分證 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2012">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2012">Format</span></span>

<span data-ttu-id="c49b6-2013">8-9 個字母和數字，加上選擇性括住的最後一個字元的組合</span><span class="sxs-lookup"><span data-stu-id="c49b6-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2014">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2014">Pattern</span></span>

<span data-ttu-id="c49b6-2015">8-9 個字母的組合：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="c49b6-2016">1-2 個字母 (不區分大小寫) </span><span class="sxs-lookup"><span data-stu-id="c49b6-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2017">六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2017">Six digits</span></span> 
- <span data-ttu-id="c49b6-2018">最後一個字元 (任何數字或字母 A)，是檢查碼且可選擇性加上前後括號。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2019">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2019">Checksum</span></span>

<span data-ttu-id="c49b6-2020">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2021">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2021">Definition</span></span>

<span data-ttu-id="c49b6-2022">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2023">函數 Func_hong_kong_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2024">從 Keyword_hong_kong_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="c49b6-2025">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2025">The checksum passes.</span></span>

<span data-ttu-id="c49b6-2026">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2027">函數 Func_hong_kong_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2028">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2029">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="c49b6-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="c49b6-2031">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="c49b6-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2032">HKID</span></span>
- <span data-ttu-id="c49b6-2033">ID card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2033">ID card</span></span>
- <span data-ttu-id="c49b6-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2034">香港身份證</span></span> 
- <span data-ttu-id="c49b6-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="c49b6-2036">印度永久帳戶號碼 (PAN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2037">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2037">Format</span></span>

<span data-ttu-id="c49b6-2038">10 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2039">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2039">Pattern</span></span>

<span data-ttu-id="c49b6-2040">10 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2040">10 letters or digits:</span></span>
- <span data-ttu-id="c49b6-2041">五個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2042">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2042">Four digits</span></span> 
- <span data-ttu-id="c49b6-2043">一個做為字母檢查碼的字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2044">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2044">Checksum</span></span>

<span data-ttu-id="c49b6-2045">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2046">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2046">Definition</span></span>

<span data-ttu-id="c49b6-2047">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2048">規則運算式 Regex_india_permanent_account_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2049">從 Keyword_india_permanent_account_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="c49b6-2050">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2051">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="c49b6-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="c49b6-2053">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="c49b6-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="c49b6-2055">印度唯一識別 (Aadhaar) 碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2056">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2056">Format</span></span>

<span data-ttu-id="c49b6-2057">12 位數包含選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2058">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2058">Pattern</span></span>

<span data-ttu-id="c49b6-2059">12 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2059">12 digits:</span></span>
- <span data-ttu-id="c49b6-2060">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2060">Four digits</span></span> 
- <span data-ttu-id="c49b6-2061">一個選擇性空格或破折號 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2061">An optional space or dash</span></span> 
- <span data-ttu-id="c49b6-2062">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2062">Four digits</span></span> 
- <span data-ttu-id="c49b6-2063">一個選擇性空格或破折號 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2063">An optional space or dash</span></span> 
- <span data-ttu-id="c49b6-2064">最後一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2065">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2065">Checksum</span></span>

<span data-ttu-id="c49b6-2066">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2067">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2067">Definition</span></span>

<span data-ttu-id="c49b6-p133">DLP 原則是 85%有信心它已偵測到這種類型的機密資訊時，300 個字元的距離： 函數 Func_india_aadhaar 會找出符合模式的內容。從 Keyword_india_aadhar 關鍵字是找到。總和檢查碼會傳遞。DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 函數 Func_india_aadhaar 會找出符合模式的內容。總和檢查碼會傳遞。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="c49b6-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="c49b6-2074">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="c49b6-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="c49b6-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="c49b6-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="c49b6-2076">Aadhar</span></span>
- <span data-ttu-id="c49b6-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="c49b6-2077">Aadhaar</span></span>
- <span data-ttu-id="c49b6-2078">UID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2078">UID</span></span>
- <span data-ttu-id="c49b6-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="c49b6-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="c49b6-2080">印尼身分識 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2081">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2081">Format</span></span>

<span data-ttu-id="c49b6-2082">16 位數包含選擇性句點</span><span class="sxs-lookup"><span data-stu-id="c49b6-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2083">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2083">Pattern</span></span>

<span data-ttu-id="c49b6-2084">16 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2084">16 digits:</span></span>
- <span data-ttu-id="c49b6-2085">二位數省代碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2085">Two-digit province code</span></span> 
- <span data-ttu-id="c49b6-2086">句點 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="c49b6-2086">A period (optional)</span></span> 
- <span data-ttu-id="c49b6-2087">二位數攝政或城市代碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="c49b6-2088">二位數次行政區代碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="c49b6-2089">句點 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="c49b6-2089">A period (optional)</span></span> 
- <span data-ttu-id="c49b6-2090">DDMMYY 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-2091">句點 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="c49b6-2091">A period (optional)</span></span> 
- <span data-ttu-id="c49b6-2092">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2093">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2093">Checksum</span></span>

<span data-ttu-id="c49b6-2094">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2095">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2095">Definition</span></span>

<span data-ttu-id="c49b6-2096">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2097">規則運算式 Regex_indonesia_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2098">從 Keyword_indonesia_id_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="c49b6-2099">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2100">規則運算式 Regex_indonesia_id_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2101">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="c49b6-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="c49b6-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="c49b6-2103">KTP</span></span>
- <span data-ttu-id="c49b6-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="c49b6-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="c49b6-2106">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2107">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2107">Format</span></span>

<span data-ttu-id="c49b6-2108">國家/地區碼 （兩個字母） 加號 plus bban 數 （最多 30 個字元） 檢查位數 （兩個位數）</span><span class="sxs-lookup"><span data-stu-id="c49b6-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2109">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2109">Pattern</span></span>

<span data-ttu-id="c49b6-2110">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="c49b6-2111">雙字母國家/地區碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2111">Two-letter country code</span></span>
- <span data-ttu-id="c49b6-2112">兩個核取位數 （後面選用的空間）</span><span class="sxs-lookup"><span data-stu-id="c49b6-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="c49b6-2113">1-7 群組的四個字母或數字 （可以以空格）</span><span class="sxs-lookup"><span data-stu-id="c49b6-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="c49b6-2114">1-3 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2114">1-3 letters or digits</span></span>

<span data-ttu-id="c49b6-p134">每個國家/地區的格式是稍有不同。IBAN 敏感資訊類型涵蓋下列 60 國家/地區：</span><span class="sxs-lookup"><span data-stu-id="c49b6-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="c49b6-2117">ad、 ae、 al，在亞利桑那州、 ba、 是、 bg、 bh、 頻道、 cr、 cy、 cz、 de、 粗、 執行、 ee、 es、 wi-fi、 於、 fr、 gb、 ge、 gi、 gl、 /gr、 hr、 hu、 ie、 芝加哥，它、 kw、 kz、 lb、 li、 lt、 lu、 lv mc md、 我、 mk、 mr、 明、 mu、 nl、 [否] pl、 pt、 ro、 rs、 sa、 se、 si、 sk、 sm、 tn、 tr、 vg</span><span class="sxs-lookup"><span data-stu-id="c49b6-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2118">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2118">Checksum</span></span>

<span data-ttu-id="c49b6-2119">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2120">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2120">Definition</span></span>

<span data-ttu-id="c49b6-2121">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2122">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2123">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2124">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2124">Keywords</span></span>

<span data-ttu-id="c49b6-2125">無</span><span class="sxs-lookup"><span data-stu-id="c49b6-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="c49b6-2126">IP 位址</span><span class="sxs-lookup"><span data-stu-id="c49b6-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2127">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="c49b6-2128">IPv4：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2128">IPv4:</span></span>
<span data-ttu-id="c49b6-2129">表示格式化 (句點) 和未格式化 (無句點) 之 IPv4 位址的複雜模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="c49b6-2130">IPv6：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2130">IPv6:</span></span>
<span data-ttu-id="c49b6-2131">表示格式化 IPv6 號碼 (其中包含冒號) 的複雜模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2132">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2133">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2133">Checksum</span></span>

<span data-ttu-id="c49b6-2134">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2135">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2135">Definition</span></span>

<span data-ttu-id="c49b6-2136">對於 IPv6，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2137">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2138">找不到來自於 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="c49b6-2139">對於 IPv4，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2140">規則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2141">找到來自於 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="c49b6-2142">對於 IPv6，如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 95%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2143">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2144">找不到來自於 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2145">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="c49b6-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="c49b6-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="c49b6-2147">IP (此關鍵字區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="c49b6-2148">ip address
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2148">ip address</span></span> 
- <span data-ttu-id="c49b6-2149">ip addresses</span><span class="sxs-lookup"><span data-stu-id="c49b6-2149">ip addresses</span></span>
- <span data-ttu-id="c49b6-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="c49b6-2150">internet protocol</span></span>
- <span data-ttu-id="c49b6-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="c49b6-2152">國際分類的治療法 （ICD-10-公分）</span><span class="sxs-lookup"><span data-stu-id="c49b6-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2153">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2153">Format</span></span>

<span data-ttu-id="c49b6-2154">字典</span><span class="sxs-lookup"><span data-stu-id="c49b6-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2155">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2155">Pattern</span></span>

<span data-ttu-id="c49b6-2156">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2157">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2157">Checksum</span></span>

<span data-ttu-id="c49b6-2158">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2159">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2159">Definition</span></span>

<span data-ttu-id="c49b6-2160">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2161">從 Dictionary_icd_10_cm 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="c49b6-2162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2162">Keywords</span></span>

<span data-ttu-id="c49b6-p135">任何字詞的 Dictionary_icd_10_cm 關鍵字字典，這根據[國際分類的治療法、 十分之一修訂、 臨床修改 （ICD-10-公分）](https://go.microsoft.com/fwlink/?linkid=852604)。此類型只會尋找詞不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="c49b6-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="c49b6-2165">國際分類的治療法 （ICD-9-公分）</span><span class="sxs-lookup"><span data-stu-id="c49b6-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2166">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2166">Format</span></span>

<span data-ttu-id="c49b6-2167">字典</span><span class="sxs-lookup"><span data-stu-id="c49b6-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2168">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2168">Pattern</span></span>

<span data-ttu-id="c49b6-2169">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2170">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2170">Checksum</span></span>

<span data-ttu-id="c49b6-2171">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2172">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2172">Definition</span></span>

<span data-ttu-id="c49b6-2173">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2174">從 Dictionary_icd_9_cm 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2175">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2175">Keywords</span></span>

<span data-ttu-id="c49b6-p136">任何字詞的 Dictionary_icd_9_cm 關鍵字字典，這根據[國際分類的治療法、 二十九修訂、 臨床修改 （ICD-9-公分）](https://go.microsoft.com/fwlink/?linkid=852605)。此類型只會尋找詞不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="c49b6-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="c49b6-2178">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2179">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2179">Format</span></span>

<span data-ttu-id="c49b6-2180">（直到 31 Dec 2012) 的舊格式：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="c49b6-2181">七位數後尾隨 1-2 個字母 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="c49b6-2182">新的格式 (1 Jan 2013 及之後)：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="c49b6-2183">七位數後尾隨二個字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2184">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2184">Pattern</span></span>

<span data-ttu-id="c49b6-2185">（直到 31 Dec 2012) 的舊格式：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="c49b6-2186">七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2186">Seven digits</span></span> 
- <span data-ttu-id="c49b6-2187">1-2 個字母 (不區分大小寫) </span><span class="sxs-lookup"><span data-stu-id="c49b6-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="c49b6-2188">新的格式 (1 Jan 2013 及之後)：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="c49b6-2189">七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2189">Seven digits</span></span> 
- <span data-ttu-id="c49b6-2190">一個字母 (不區分大小寫)，是一個字母檢查碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="c49b6-2191">字母 "A" 或 "H" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2192">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2192">Checksum</span></span>

<span data-ttu-id="c49b6-2193">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2194">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2194">Definition</span></span>

<span data-ttu-id="c49b6-2195">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2196">函數 Func_ireland_pps 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2197">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2197">One of the following is true:</span></span>
    - <span data-ttu-id="c49b6-2198">從 Keyword_ireland_pps 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="c49b6-2199">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="c49b6-2200">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2200">The checksum passes.</span></span>

<span data-ttu-id="c49b6-2201">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2202">函數 Func_ireland_pps 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2203">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2204">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="c49b6-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="c49b6-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="c49b6-2206">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="c49b6-2207">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2207">PPS Number</span></span> 
- <span data-ttu-id="c49b6-2208">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2208">PPS Num</span></span> 
- <span data-ttu-id="c49b6-2209">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2209">PPS No.</span></span> 
- <span data-ttu-id="c49b6-2210">PPS #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2210">PPS #</span></span> 
- <span data-ttu-id="c49b6-2211">PPS#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2211">PPS#</span></span> 
- <span data-ttu-id="c49b6-2212">PPSN
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2212">PPSN</span></span> 
- <span data-ttu-id="c49b6-2213">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2213">Public Services Card</span></span> 
- <span data-ttu-id="c49b6-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="c49b6-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="c49b6-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="c49b6-2218">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2219">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2219">Format</span></span>

<span data-ttu-id="c49b6-2220">13 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2221">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2221">Pattern</span></span>

<span data-ttu-id="c49b6-2222">格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2222">Formatted:</span></span>
- <span data-ttu-id="c49b6-2223">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2223">Two digits</span></span> 
- <span data-ttu-id="c49b6-2224">一個破折號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2224">A dash</span></span> 
- <span data-ttu-id="c49b6-2225">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2225">Three digits</span></span> 
- <span data-ttu-id="c49b6-2226">一個破折號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2226">A dash</span></span> 
- <span data-ttu-id="c49b6-2227">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2227">Eight digits</span></span>

<span data-ttu-id="c49b6-2228">未格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2228">Unformatted:</span></span>
- <span data-ttu-id="c49b6-2229">13 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2230">Checksum</span></span>

<span data-ttu-id="c49b6-2231">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2232">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2232">Definition</span></span>

<span data-ttu-id="c49b6-2233">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2234">規則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2235">找到來自於 Keyword_israel_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="c49b6-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="c49b6-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2238">Bank Account Number</span></span> 
- <span data-ttu-id="c49b6-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2239">Bank Account</span></span> 
- <span data-ttu-id="c49b6-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2240">Account Number</span></span> 
- <span data-ttu-id="c49b6-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="c49b6-2242">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2243">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2243">Format</span></span>

<span data-ttu-id="c49b6-2244">九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2245">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2245">Pattern</span></span>

<span data-ttu-id="c49b6-2246">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2247">Checksum</span></span>

<span data-ttu-id="c49b6-2248">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2249">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2249">Definition</span></span>

<span data-ttu-id="c49b6-2250">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2251">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2252">找到來自於 Keyword_Israel_National_ID 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="c49b6-2253">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2254">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="c49b6-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="c49b6-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2256">מספר זהות</span></span> 
- <span data-ttu-id="c49b6-2257">國門身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="c49b6-2258">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2259">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2259">Format</span></span>

<span data-ttu-id="c49b6-2260">10 個字母和數字的組合</span><span class="sxs-lookup"><span data-stu-id="c49b6-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2261">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2261">Pattern</span></span>

- <span data-ttu-id="c49b6-2262">10 個字母和數字的組合：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="c49b6-2263">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2264">字母 "A" 或 "V" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2265">七個字母 (不區分大小寫)、數字或底線字元</span><span class="sxs-lookup"><span data-stu-id="c49b6-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="c49b6-2266">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2267">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2267">Checksum</span></span>

<span data-ttu-id="c49b6-2268">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2269">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2269">Definition</span></span>

<span data-ttu-id="c49b6-2270">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2271">規則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2272">找到來自於 Keyword_italy_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2273">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="c49b6-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="c49b6-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="c49b6-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="c49b6-2277">日本銀行帳號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2278">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2278">Format</span></span>

<span data-ttu-id="c49b6-2279">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2280">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2280">Pattern</span></span>

<span data-ttu-id="c49b6-2281">銀行帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2281">Bank account number:</span></span>
- <span data-ttu-id="c49b6-2282">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2282">Seven or eight digits</span></span>
- <span data-ttu-id="c49b6-2283">銀行帳戶分行代碼：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2283">Bank account branch code:</span></span>
- <span data-ttu-id="c49b6-2284">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2284">Four digits</span></span> 
- <span data-ttu-id="c49b6-2285">一個空格或連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="c49b6-2286">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2286">Three digits</span></span>

<span data-ttu-id="c49b6-2287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2287">Checksum</span></span>

<span data-ttu-id="c49b6-2288">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2289">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2289">Definition</span></span>

<span data-ttu-id="c49b6-2290">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2291">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2292">找到來自於 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="c49b6-2293">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2293">One of the following is true:</span></span>
- <span data-ttu-id="c49b6-2294">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2295">找到來自於 Keyword_jp_bank_branch_code 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="c49b6-2296">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2297">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2298">找到來自於 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2299">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="c49b6-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="c49b6-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="c49b6-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2301">Checking Account Number</span></span> 
- <span data-ttu-id="c49b6-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2302">Checking Account</span></span> 
- <span data-ttu-id="c49b6-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2303">Checking Account #</span></span> 
- <span data-ttu-id="c49b6-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="c49b6-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2305">Checking Acct #</span></span> 
- <span data-ttu-id="c49b6-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="c49b6-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2307">Checking Account No.</span></span> 
- <span data-ttu-id="c49b6-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2308">Bank Account Number</span></span> 
- <span data-ttu-id="c49b6-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2309">Bank Account</span></span> 
- <span data-ttu-id="c49b6-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2310">Bank Account #</span></span> 
- <span data-ttu-id="c49b6-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="c49b6-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2312">Bank Acct #</span></span> 
- <span data-ttu-id="c49b6-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="c49b6-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2314">Bank Account No.</span></span> 
- <span data-ttu-id="c49b6-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2315">Savings Account Number</span></span> 
- <span data-ttu-id="c49b6-2316">節約帳戶</span><span class="sxs-lookup"><span data-stu-id="c49b6-2316">Savings Account</span></span> 
- <span data-ttu-id="c49b6-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2317">Savings Account #</span></span> 
- <span data-ttu-id="c49b6-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="c49b6-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2319">Savings Acct #</span></span> 
- <span data-ttu-id="c49b6-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="c49b6-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2321">Savings Account No.</span></span> 
- <span data-ttu-id="c49b6-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2322">Debit Account Number</span></span> 
- <span data-ttu-id="c49b6-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2323">Debit Account</span></span> 
- <span data-ttu-id="c49b6-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2324">Debit Account #</span></span> 
- <span data-ttu-id="c49b6-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="c49b6-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2326">Debit Acct #</span></span> 
- <span data-ttu-id="c49b6-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="c49b6-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2328">Debit Account No.</span></span> 
- <span data-ttu-id="c49b6-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="c49b6-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="c49b6-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="c49b6-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="c49b6-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2333">口座番号の確認</span></span> 
- <span data-ttu-id="c49b6-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="c49b6-2334">銀行口座番号</span></span> 
- <span data-ttu-id="c49b6-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="c49b6-2335">銀行口座</span></span> 
- <span data-ttu-id="c49b6-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2336">銀行口座＃</span></span> 
- <span data-ttu-id="c49b6-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="c49b6-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="c49b6-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="c49b6-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="c49b6-2340">銀行口座番号</span></span>
- <span data-ttu-id="c49b6-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="c49b6-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2342">預金口座</span></span> 
- <span data-ttu-id="c49b6-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="c49b6-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="c49b6-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="c49b6-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="c49b6-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="c49b6-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="c49b6-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="c49b6-2349">口座番号</span></span> 
- <span data-ttu-id="c49b6-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2350">口座番号＃</span></span> 
- <span data-ttu-id="c49b6-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="c49b6-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="c49b6-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="c49b6-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="c49b6-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="c49b6-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="c49b6-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="c49b6-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="c49b6-2357">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2358">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2358">Format</span></span>

<span data-ttu-id="c49b6-2359">12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2360">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2360">Pattern</span></span>

<span data-ttu-id="c49b6-2361">12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2362">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2362">Checksum</span></span>

<span data-ttu-id="c49b6-2363">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2364">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2364">Definition</span></span>

<span data-ttu-id="c49b6-2365">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2366">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2367">找到來自於 Keyword_jp_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2368">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="c49b6-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="c49b6-2370">dl#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2370">dl#</span></span> 
- <span data-ttu-id="c49b6-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="c49b6-2371">DL＃</span></span> 
- <span data-ttu-id="c49b6-2372">dl #</span><span class="sxs-lookup"><span data-stu-id="c49b6-2372">dls#</span></span> 
- <span data-ttu-id="c49b6-2373">DL #</span><span class="sxs-lookup"><span data-stu-id="c49b6-2373">DLS＃</span></span> 
- <span data-ttu-id="c49b6-2374">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-2374">driver license</span></span> 
- <span data-ttu-id="c49b6-2375">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-2375">driver licenses</span></span> 
- <span data-ttu-id="c49b6-2376">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-2376">drivers license</span></span> 
- <span data-ttu-id="c49b6-2377">駕照</span><span class="sxs-lookup"><span data-stu-id="c49b6-2377">driver's license</span></span> 
- <span data-ttu-id="c49b6-2378">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-2378">drivers licenses</span></span> 
- <span data-ttu-id="c49b6-2379">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-2379">driver's licenses</span></span> 
- <span data-ttu-id="c49b6-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2380">driving licence</span></span> 
- <span data-ttu-id="c49b6-2381">lic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-2381">lic#</span></span> 
- <span data-ttu-id="c49b6-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="c49b6-2382">LIC＃</span></span> 
- <span data-ttu-id="c49b6-2383">lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2383">lics#</span></span> 
- <span data-ttu-id="c49b6-2384">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2384">state id</span></span> 
- <span data-ttu-id="c49b6-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2385">state identification</span></span> 
- <span data-ttu-id="c49b6-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2386">state identification number</span></span> 
- <span data-ttu-id="c49b6-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2387">低所得国＃</span></span> 
- <span data-ttu-id="c49b6-2388">免許証
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2388">免許証</span></span> 
- <span data-ttu-id="c49b6-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2389">状態ID</span></span>
- <span data-ttu-id="c49b6-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2390">状態の識別</span></span> 
- <span data-ttu-id="c49b6-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2391">状態の識別番号</span></span> 
- <span data-ttu-id="c49b6-2392">運転免許
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2392">運転免許</span></span> 
- <span data-ttu-id="c49b6-2393">運転免許証
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2393">運転免許証</span></span> 
- <span data-ttu-id="c49b6-2394">運転免許証番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="c49b6-2395">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2396">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2396">Format</span></span>

<span data-ttu-id="c49b6-2397">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2398">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2398">Pattern</span></span>

<span data-ttu-id="c49b6-2399">兩個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2400">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2400">Checksum</span></span>

<span data-ttu-id="c49b6-2401">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2402">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2402">Definition</span></span>

<span data-ttu-id="c49b6-2403">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2404">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2405">找到來自於 Keyword_jp_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2406">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="c49b6-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="c49b6-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2408">パスポート</span></span> 
- <span data-ttu-id="c49b6-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2409">パスポート番号</span></span> 
- <span data-ttu-id="c49b6-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2410">パスポートのNum</span></span> 
- <span data-ttu-id="c49b6-2411">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="c49b6-2412">日本常駐居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2413">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2413">Format</span></span>

<span data-ttu-id="c49b6-2414">11 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2415">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2415">Pattern</span></span>

<span data-ttu-id="c49b6-2416">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2417">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2417">Checksum</span></span>

<span data-ttu-id="c49b6-2418">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2419">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2419">Definition</span></span>

<span data-ttu-id="c49b6-2420">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2421">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2422">找到來自於 Keyword_jp_resident_registration_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2423">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="c49b6-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="c49b6-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2425">Resident Registration Number</span></span>
- <span data-ttu-id="c49b6-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2426">Resident Register Number</span></span> 
- <span data-ttu-id="c49b6-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="c49b6-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="c49b6-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2429">Resident Register No.</span></span> 
- <span data-ttu-id="c49b6-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="c49b6-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="c49b6-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="c49b6-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="c49b6-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="c49b6-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="c49b6-2436">日本社會保險號碼 (SIN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2437">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2437">Format</span></span>

<span data-ttu-id="c49b6-2438">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2439">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2439">Pattern</span></span>

<span data-ttu-id="c49b6-2440">7-12 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2440">7-12 digits:</span></span>
- <span data-ttu-id="c49b6-2441">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2441">Four digits</span></span> 
- <span data-ttu-id="c49b6-2442">一個連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="c49b6-2443">6 位數或</span><span class="sxs-lookup"><span data-stu-id="c49b6-2443">Six digits OR</span></span>
- <span data-ttu-id="c49b6-2444">7-12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2445">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2445">Checksum</span></span>

<span data-ttu-id="c49b6-2446">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2447">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2447">Definition</span></span>

<span data-ttu-id="c49b6-2448">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2449">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2450">找到來自於 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="c49b6-2451">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2452">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2453">找到來自於 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2454">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="c49b6-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="c49b6-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="c49b6-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="c49b6-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="c49b6-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="c49b6-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="c49b6-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="c49b6-2461">馬來西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2462">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2462">Format</span></span>

<span data-ttu-id="c49b6-2463">12 位數包含選擇性連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2464">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2464">Pattern</span></span>

<span data-ttu-id="c49b6-2465">12 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2465">12 digits:</span></span>
- <span data-ttu-id="c49b6-2466">YYMMDD 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-2467">一個破折號 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2467">A dash (optional)</span></span> 
- <span data-ttu-id="c49b6-2468">兩個字母的出生地代碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="c49b6-2469">一個破折號 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2469">A dash (optional)</span></span> 
- <span data-ttu-id="c49b6-2470">三個隨機的數字 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2470">Three random digits</span></span> 
- <span data-ttu-id="c49b6-2471">一位數性別代碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2472">Checksum</span></span>

<span data-ttu-id="c49b6-2473">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2474">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2474">Definition</span></span>

<span data-ttu-id="c49b6-2475">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2476">規則運算式 Regex_malaysia_id_card_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2477">從 Keyword_malaysia_id_card_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="c49b6-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="c49b6-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="c49b6-2480">MyKad</span></span> 
- <span data-ttu-id="c49b6-2481">Identity Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2481">Identity Card</span></span> 
- <span data-ttu-id="c49b6-2482">識別碼卡片</span><span class="sxs-lookup"><span data-stu-id="c49b6-2482">ID Card</span></span> 
- <span data-ttu-id="c49b6-2483">識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-2483">Identification Card</span></span> 
- <span data-ttu-id="c49b6-2484">Digital Application Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2484">Digital Application Card</span></span> 
- <span data-ttu-id="c49b6-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="c49b6-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="c49b6-2487">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2488">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2488">Format</span></span>

<span data-ttu-id="c49b6-2489">8-9 位數包含選擇性空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2490">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2490">Pattern</span></span>

<span data-ttu-id="c49b6-2491">8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2491">8-9 digits:</span></span>
- <span data-ttu-id="c49b6-2492">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2492">Three digits</span></span> 
- <span data-ttu-id="c49b6-2493">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2493">A space (optional)</span></span> 
- <span data-ttu-id="c49b6-2494">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2494">Three digits</span></span> 
- <span data-ttu-id="c49b6-2495">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2495">A space (optional)</span></span> 
- <span data-ttu-id="c49b6-2496">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2497">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2497">Checksum</span></span>

<span data-ttu-id="c49b6-2498">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2499">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2499">Definition</span></span>

<span data-ttu-id="c49b6-2500">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2501">函數 Func_netherlands_bsn 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2502">從 Keyword_netherlands_bsn 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="c49b6-2503">函數 Func_eu_date2 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="c49b6-2504">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2505">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="c49b6-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="c49b6-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="c49b6-2507">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2507">Citizen service number</span></span> 
- <span data-ttu-id="c49b6-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="c49b6-2508">BSN</span></span> 
- <span data-ttu-id="c49b6-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="c49b6-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2510">Sofinummer</span></span> 
- <span data-ttu-id="c49b6-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="c49b6-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="c49b6-2513">紐西蘭衛生部編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2514">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2514">Format</span></span>

<span data-ttu-id="c49b6-2515">三個字母、一個空格 (選用) 和四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2516">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2516">Pattern</span></span>

<span data-ttu-id="c49b6-2517">三個字母空格 （選擇性） 四位數 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c49b6-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2518">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2518">Checksum</span></span>

<span data-ttu-id="c49b6-2519">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2520">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2520">Definition</span></span>

<span data-ttu-id="c49b6-2521">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2522">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2523">找到來自於 Keyword_nz_terms 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="c49b6-2524">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2524">The checksum passes.</span></span>

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

<span data-ttu-id="c49b6-2525">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2525">Keywords</span></span>

<span data-ttu-id="c49b6-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="c49b6-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="c49b6-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2527">NHI</span></span> 
- <span data-ttu-id="c49b6-2528">紐西蘭</span><span class="sxs-lookup"><span data-stu-id="c49b6-2528">New Zealand</span></span> 
- <span data-ttu-id="c49b6-2529">狀況良好</span><span class="sxs-lookup"><span data-stu-id="c49b6-2529">Health</span></span> 
- <span data-ttu-id="c49b6-2530">treatment
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="c49b6-2531">挪威識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2532">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2532">Format</span></span>

<span data-ttu-id="c49b6-2533">11 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2534">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2534">Pattern</span></span>

<span data-ttu-id="c49b6-2535">11 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2535">11 digits:</span></span>
- <span data-ttu-id="c49b6-2536">DDMMYY 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-2537">三位數個人識別碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="c49b6-2538">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2539">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2539">Checksum</span></span>

<span data-ttu-id="c49b6-2540">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2541">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2541">Definition</span></span>

<span data-ttu-id="c49b6-2542">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2543">函數 Func_norway_id_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2544">從 Keyword_norway_id_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="c49b6-2545">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2545">The checksum passes.</span></span>
- <span data-ttu-id="c49b6-2546">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2547">函數 Func_norway_id_numbe 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2548">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2549">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="c49b6-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="c49b6-2551">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2551">Personal identification number</span></span>
- <span data-ttu-id="c49b6-2552">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="c49b6-2553">ID Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2553">ID Number</span></span>
- <span data-ttu-id="c49b6-2554">Identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-2554">Identification</span></span>
- <span data-ttu-id="c49b6-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-2555">Personnummer</span></span>
- <span data-ttu-id="c49b6-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="c49b6-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="c49b6-2557">菲律賓統一多用途身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2558">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2558">Format</span></span>

<span data-ttu-id="c49b6-2559">以連字號分隔的 12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2560">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2560">Pattern</span></span>

<span data-ttu-id="c49b6-2561">12 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2561">12 digits:</span></span>
- <span data-ttu-id="c49b6-2562">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2562">Four digits</span></span> 
- <span data-ttu-id="c49b6-2563">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2563">A hyphen</span></span> 
- <span data-ttu-id="c49b6-2564">七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2564">Seven digits</span></span> 
- <span data-ttu-id="c49b6-2565">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2565">A hyphen</span></span> 
- <span data-ttu-id="c49b6-2566">一個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2567">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2567">Checksum</span></span>

<span data-ttu-id="c49b6-2568">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2569">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2569">Definition</span></span>

<span data-ttu-id="c49b6-2570">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2571">規則運算式 Regex_philippines_unified_id 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2572">從 Keyword_philippines_id 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2573">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="c49b6-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="c49b6-2575">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="c49b6-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2576">UMID</span></span> 
- <span data-ttu-id="c49b6-2577">Identity Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2577">Identity Card</span></span> 
- <span data-ttu-id="c49b6-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="c49b6-2579">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2580">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2580">Format</span></span>

<span data-ttu-id="c49b6-2581">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2582">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2582">Pattern</span></span>

<span data-ttu-id="c49b6-2583">三個字母 (不區分大小寫) 後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2584">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2584">Checksum</span></span>

<span data-ttu-id="c49b6-2585">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2586">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2586">Definition</span></span>

<span data-ttu-id="c49b6-p138">DLP 原則就是有信心它已偵測到這種敏感資訊類型的 75 %if，300 個字元的距離： 函數 Func_polish_national_id 會找出符合模式的內容。從 Keyword_polish_national_id_passport_number 關鍵字是找到。總和檢查碼會傳遞。</span><span class="sxs-lookup"><span data-stu-id="c49b6-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2590">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="c49b6-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="c49b6-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="c49b6-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="c49b6-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="c49b6-2596">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2597">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2597">Format</span></span>

<span data-ttu-id="c49b6-2598">11 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2599">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2599">Pattern</span></span>

<span data-ttu-id="c49b6-2600">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2601">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2601">Checksum</span></span>

<span data-ttu-id="c49b6-2602">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2603">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2603">Definition</span></span>

<span data-ttu-id="c49b6-2604">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2605">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2606">找到來自於 Keyword_pesel_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="c49b6-2607">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2608">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="c49b6-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="c49b6-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="c49b6-2610">Nr PESEL</span></span>
- <span data-ttu-id="c49b6-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="c49b6-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="c49b6-2612">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="c49b6-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2613">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2613">Format</span></span>

<span data-ttu-id="c49b6-2614">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2615">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2615">Pattern</span></span>

<span data-ttu-id="c49b6-2616">兩個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2617">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2617">Checksum</span></span>

<span data-ttu-id="c49b6-2618">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2619">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2619">Definition</span></span>

<span data-ttu-id="c49b6-2620">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2621">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2622">找到來自於 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="c49b6-2623">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2624">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="c49b6-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="c49b6-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="c49b6-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="c49b6-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="c49b6-2630">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2631">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2631">Format</span></span>

<span data-ttu-id="c49b6-2632">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2633">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2633">Pattern</span></span>

<span data-ttu-id="c49b6-2634">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2635">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2635">Checksum</span></span>

<span data-ttu-id="c49b6-2636">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2637">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2637">Definition</span></span>

<span data-ttu-id="c49b6-2638">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2639">規則運算式 Regex_portugal_citizen_card 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2640">從 Keyword_portugal_citizen_card 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2641">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="c49b6-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="c49b6-2643">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2643">Citizen Card</span></span>
- <span data-ttu-id="c49b6-2644">National ID Card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2644">National ID Card</span></span>
- <span data-ttu-id="c49b6-2645">CC</span><span class="sxs-lookup"><span data-stu-id="c49b6-2645">CC</span></span>
- <span data-ttu-id="c49b6-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="c49b6-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="c49b6-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="c49b6-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="c49b6-2648">沙烏地阿拉伯國民身分證號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2649">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2649">Format</span></span>

<span data-ttu-id="c49b6-2650">10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2651">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2651">Pattern</span></span>

<span data-ttu-id="c49b6-2652">10 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2653">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2653">Checksum</span></span>

<span data-ttu-id="c49b6-2654">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2655">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2655">Definition</span></span>

<span data-ttu-id="c49b6-2656">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2657">規則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2658">找到來自於 Keyword_saudi_arabia_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2659">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="c49b6-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="c49b6-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2661">Identification Card</span></span> 
- <span data-ttu-id="c49b6-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2662">I card number</span></span> 
- <span data-ttu-id="c49b6-2663">識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2663">ID number</span></span> 
- <span data-ttu-id="c49b6-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="c49b6-2665">新加坡國民登記身分證 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2666">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2666">Format</span></span>

<span data-ttu-id="c49b6-2667">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2668">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2668">Pattern</span></span>

- <span data-ttu-id="c49b6-2669">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="c49b6-2670">字母 "F"、"G"、"S" 或 "T" (不區分大小寫) </span><span class="sxs-lookup"><span data-stu-id="c49b6-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2671">七位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2671">Seven digits</span></span> 
- <span data-ttu-id="c49b6-2672">一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2673">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2673">Checksum</span></span>

<span data-ttu-id="c49b6-2674">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2675">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2675">Definition</span></span>

<span data-ttu-id="c49b6-2676">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2677">規則運算式 Regex_singapore_nric 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2678">從 Keyword_singapore_nric 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="c49b6-2679">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2679">The checksum passes.</span></span>

<span data-ttu-id="c49b6-2680">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2681">規則運算式 Regex_singapore_nric 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2682">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2683">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="c49b6-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="c49b6-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="c49b6-2685">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="c49b6-2686">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2686">Identity Card Number</span></span> 
- <span data-ttu-id="c49b6-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2687">NRIC</span></span> 
- <span data-ttu-id="c49b6-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2688">IC</span></span> 
- <span data-ttu-id="c49b6-2689">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="c49b6-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2690">FIN</span></span> 
- <span data-ttu-id="c49b6-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2691">身份证</span></span> 
- <span data-ttu-id="c49b6-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="c49b6-2693">南非身分證號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2694">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2694">Format</span></span>

<span data-ttu-id="c49b6-2695">可以包含空格的 13 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2696">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2696">Pattern</span></span>

<span data-ttu-id="c49b6-2697">13 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2697">13 digits:</span></span>
- <span data-ttu-id="c49b6-2698">YYMMDD 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-2699">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2699">Four digits</span></span> 
- <span data-ttu-id="c49b6-2700">一位數公民指標 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="c49b6-2701">數字 "8" 或 "9" </span><span class="sxs-lookup"><span data-stu-id="c49b6-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="c49b6-2702">一位數總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2703">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2703">Checksum</span></span>

<span data-ttu-id="c49b6-2704">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2705">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2705">Definition</span></span>

<span data-ttu-id="c49b6-2706">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2707">函數 Func_south_africa_identification_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2708">從 Keyword_south_africa_identification_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="c49b6-2709">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2710">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="c49b6-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="c49b6-2712">Identity card</span><span class="sxs-lookup"><span data-stu-id="c49b6-2712">Identity card</span></span>
- <span data-ttu-id="c49b6-2713">ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2713">ID</span></span>
- <span data-ttu-id="c49b6-2714">Identification</span><span class="sxs-lookup"><span data-stu-id="c49b6-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="c49b6-2715">南韓居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2716">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2716">Format</span></span>

<span data-ttu-id="c49b6-2717">13 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2718">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2718">Pattern</span></span>

<span data-ttu-id="c49b6-2719">13 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2719">13 digits:</span></span>
- <span data-ttu-id="c49b6-2720">YYMMDD 格式的六位數，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="c49b6-2721">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2721">A hyphen</span></span> 
- <span data-ttu-id="c49b6-2722">由世紀與性別判定的一位數 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="c49b6-2723">四位數出生地區碼 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="c49b6-2724">一位數，用來區分前幾碼皆相同的人員 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="c49b6-2725">檢查碼。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2726">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2726">Checksum</span></span>

<span data-ttu-id="c49b6-2727">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2728">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2728">Definition</span></span>

<span data-ttu-id="c49b6-2729">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2730">函數 Func_south_korea_resident_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2731">從 Keyword_south_korea_resident_number 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="c49b6-2732">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2732">The checksum passes.</span></span>

<span data-ttu-id="c49b6-2733">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2734">函數 Func_south_korea_resident_number 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2735">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2736">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="c49b6-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="c49b6-2738">國民身分證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2738">National ID card</span></span> 
- <span data-ttu-id="c49b6-2739">公民登記號碼
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="c49b6-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="c49b6-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2741">RRN</span></span> 
- <span data-ttu-id="c49b6-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="c49b6-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="c49b6-2743">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2744">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2744">Format</span></span>

<span data-ttu-id="c49b6-2745">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2746">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2746">Pattern</span></span>

<span data-ttu-id="c49b6-2747">第 11 12 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2747">11-12 digits:</span></span>
- <span data-ttu-id="c49b6-2748">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2748">Two digits</span></span> 
- <span data-ttu-id="c49b6-2749">一個正斜線 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="c49b6-2750">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2750">7-8 digits</span></span> 
- <span data-ttu-id="c49b6-2751">一個正斜線 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="c49b6-2752">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2753">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2753">Checksum</span></span>

<span data-ttu-id="c49b6-2754">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2755">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2755">Definition</span></span>

<span data-ttu-id="c49b6-2756">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2757">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2758">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2759">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2759">Keywords</span></span>

<span data-ttu-id="c49b6-2760">無</span><span class="sxs-lookup"><span data-stu-id="c49b6-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="c49b6-2761">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2762">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2762">Format</span></span>

<span data-ttu-id="c49b6-2763">10 或 12 位數和一個選用分隔符號</span><span class="sxs-lookup"><span data-stu-id="c49b6-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2764">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2764">Pattern</span></span>

<span data-ttu-id="c49b6-2765">10 或 12 位數和一個選用分隔符號：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="c49b6-2766">2-4 位數 (選用)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="c49b6-2767">採用日期格式 YYMMDD 的六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="c49b6-2768">分隔符號 "-" 或 "+" (選用)，加上</span><span class="sxs-lookup"><span data-stu-id="c49b6-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="c49b6-2769">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2770">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2770">Checksum</span></span>

<span data-ttu-id="c49b6-2771">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2772">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2772">Definition</span></span>

<span data-ttu-id="c49b6-2773">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2774">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2775">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2776">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2776">Keywords</span></span>

<span data-ttu-id="c49b6-2777">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="c49b6-2778">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2779">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2779">Format</span></span>

<span data-ttu-id="c49b6-2780">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2781">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2781">Pattern</span></span>

<span data-ttu-id="c49b6-2782">八個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2783">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2783">Checksum</span></span>

<span data-ttu-id="c49b6-2784">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2785">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2785">Definition</span></span>

<span data-ttu-id="c49b6-2786">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2787">規則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2788">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2788">One of the following is true:</span></span>
    - <span data-ttu-id="c49b6-2789">找到來自於 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="c49b6-2790">找到來自於 Keyword_sweden_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-2791">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="c49b6-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="c49b6-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2793">visa requirements</span></span> 
- <span data-ttu-id="c49b6-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="c49b6-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2795">Schengen visas</span></span> 
- <span data-ttu-id="c49b6-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2796">Schengen visa</span></span> 
- <span data-ttu-id="c49b6-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2797">Visa Processing</span></span> 
- <span data-ttu-id="c49b6-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2798">Visa Type</span></span> 
- <span data-ttu-id="c49b6-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2799">Single Entry</span></span> 
- <span data-ttu-id="c49b6-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2800">Multiple Entry</span></span> 
- <span data-ttu-id="c49b6-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="c49b6-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="c49b6-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-2802">Keyword_passport</span></span>

- <span data-ttu-id="c49b6-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2803">Passport Number</span></span> 
- <span data-ttu-id="c49b6-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="c49b6-2804">Passport No</span></span> 
- <span data-ttu-id="c49b6-2805">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2805">Passport #</span></span> 
- <span data-ttu-id="c49b6-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2806">Passport#</span></span> 
- <span data-ttu-id="c49b6-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="c49b6-2807">PassportID</span></span> 
- <span data-ttu-id="c49b6-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2808">Passportno</span></span> 
- <span data-ttu-id="c49b6-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2809">passportnumber</span></span> 
- <span data-ttu-id="c49b6-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="c49b6-2810">パスポート</span></span> 
- <span data-ttu-id="c49b6-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2811">パスポート番号</span></span> 
- <span data-ttu-id="c49b6-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2812">パスポートのNum</span></span> 
- <span data-ttu-id="c49b6-2813">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2813">パスポート＃</span></span> 
- <span data-ttu-id="c49b6-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="c49b6-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="c49b6-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="c49b6-2815">Passeport n °</span></span> 
- <span data-ttu-id="c49b6-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2816">Passeport Non</span></span> 
- <span data-ttu-id="c49b6-2817">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2817">Passeport #</span></span> 
- <span data-ttu-id="c49b6-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2818">Passeport#</span></span> 
- <span data-ttu-id="c49b6-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="c49b6-2819">PasseportNon</span></span> 
- <span data-ttu-id="c49b6-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="c49b6-2821">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2822">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2822">Format</span></span>

<span data-ttu-id="c49b6-2823">四個字母後尾隨 5-31 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2824">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2824">Pattern</span></span>

<span data-ttu-id="c49b6-2825">四個字母後尾隨 5-31 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="c49b6-2826">四字母銀行代碼 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2827">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-2827">An optional space</span></span> 
- <span data-ttu-id="c49b6-2828">4-28 個字母或數字 (基本銀行帳戶號碼 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="c49b6-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="c49b6-2829">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-2829">An optional space</span></span> 
- <span data-ttu-id="c49b6-2830">1-3 個字母或數字 (BBAN 的其餘部分)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2831">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2831">Checksum</span></span>

<span data-ttu-id="c49b6-2832">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2833">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2833">Definition</span></span>

<span data-ttu-id="c49b6-2834">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2835">規則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2836">找到來自於 Keyword_swift 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2837">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="c49b6-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="c49b6-2838">Keyword_swift</span></span>

- <span data-ttu-id="c49b6-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="c49b6-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2840">iso 9362</span></span> 
- <span data-ttu-id="c49b6-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="c49b6-2841">iso9362</span></span> 
- <span data-ttu-id="c49b6-2842">swift\#</span><span class="sxs-lookup"><span data-stu-id="c49b6-2842">swift\#</span></span> 
- <span data-ttu-id="c49b6-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2843">swiftcode</span></span> 
- <span data-ttu-id="c49b6-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2844">swiftnumber</span></span> 
- <span data-ttu-id="c49b6-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="c49b6-2846">swift code
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2846">swift code</span></span> 
- <span data-ttu-id="c49b6-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2847">swift number #</span></span> 
- <span data-ttu-id="c49b6-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2848">swift routing number</span></span> 
- <span data-ttu-id="c49b6-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2849">bic number</span></span> 
- <span data-ttu-id="c49b6-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2850">bic code</span></span> 
- <span data-ttu-id="c49b6-2851">bic\#</span><span class="sxs-lookup"><span data-stu-id="c49b6-2851">bic \#</span></span> 
- <span data-ttu-id="c49b6-2852">bic\#</span><span class="sxs-lookup"><span data-stu-id="c49b6-2852">bic\#</span></span> 
- <span data-ttu-id="c49b6-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2853">bank identifier code</span></span> 
- <span data-ttu-id="c49b6-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="c49b6-2854">標準化9362</span></span> 
- <span data-ttu-id="c49b6-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2855">迅速＃</span></span> 
- <span data-ttu-id="c49b6-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2856">SWIFTコード</span></span> 
- <span data-ttu-id="c49b6-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2857">SWIFT番号</span></span> 
- <span data-ttu-id="c49b6-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="c49b6-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2859">BIC番号</span></span> 
- <span data-ttu-id="c49b6-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2860">BICコード</span></span> 
- <span data-ttu-id="c49b6-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="c49b6-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="c49b6-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="c49b6-2863">rapide \#</span></span> 
- <span data-ttu-id="c49b6-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2864">code SWIFT</span></span> 
- <span data-ttu-id="c49b6-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2865">le numéro de swift</span></span> 
- <span data-ttu-id="c49b6-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="c49b6-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2867">le numéro BIC</span></span> 
- <span data-ttu-id="c49b6-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="c49b6-2868">\# BIC</span></span> 
- <span data-ttu-id="c49b6-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="c49b6-2870">台灣身分證</span><span class="sxs-lookup"><span data-stu-id="c49b6-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2871">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2871">Format</span></span>

<span data-ttu-id="c49b6-2872">一個字母 後尾隨九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2873">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2873">Pattern</span></span>

<span data-ttu-id="c49b6-2874">一個字母 後尾隨九位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="c49b6-2875">一個字母 (英文、不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2876">數字 "1" 或 "2"</span><span class="sxs-lookup"><span data-stu-id="c49b6-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="c49b6-2877">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2878">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2878">Checksum</span></span>

<span data-ttu-id="c49b6-2879">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2880">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2880">Definition</span></span>

<span data-ttu-id="c49b6-2881">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2882">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2883">找到來自於 Keyword_taiwanese_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="c49b6-2884">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2885">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="c49b6-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="c49b6-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="c49b6-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2887">身份證字號</span></span> 
- <span data-ttu-id="c49b6-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2888">身份證</span></span> 
- <span data-ttu-id="c49b6-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2889">身份證號碼</span></span> 
- <span data-ttu-id="c49b6-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2890">身份證號</span></span> 
- <span data-ttu-id="c49b6-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2891">身分證字號</span></span> 
- <span data-ttu-id="c49b6-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="c49b6-2892">身分證</span></span> 
- <span data-ttu-id="c49b6-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2893">身分證號碼</span></span> 
- <span data-ttu-id="c49b6-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2894">身份證號</span></span> 
- <span data-ttu-id="c49b6-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2895">身分證統一編號</span></span> 
- <span data-ttu-id="c49b6-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="c49b6-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2897">簽名</span></span> 
- <span data-ttu-id="c49b6-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2898">蓋章</span></span> 
- <span data-ttu-id="c49b6-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="c49b6-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="c49b6-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="c49b6-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="c49b6-2901">	台灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2902">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2902">Format</span></span>

- <span data-ttu-id="c49b6-2903">生物特徵護照號碼： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="c49b6-2904">非生物特徵護照號碼： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2905">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2905">Pattern</span></span>
<span data-ttu-id="c49b6-2906">生物特徵護照號碼：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2906">Biometric passport number:</span></span>
- <span data-ttu-id="c49b6-2907">數字 "3" </span><span class="sxs-lookup"><span data-stu-id="c49b6-2907">The digit "3"</span></span> 
- <span data-ttu-id="c49b6-2908">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2908">Eight digits</span></span>

<span data-ttu-id="c49b6-2909">非生物特徵護照號碼：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="c49b6-2910">九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2911">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2911">Checksum</span></span>

<span data-ttu-id="c49b6-2912">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2913">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2913">Definition</span></span>

<span data-ttu-id="c49b6-2914">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2915">規則運算式 Regex_taiwan_passport 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2916">從 Keyword_taiwan_passport 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2917">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="c49b6-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="c49b6-2919">中華民國護照號碼
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2919">ROC passport number</span></span> 
- <span data-ttu-id="c49b6-2920">護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2920">Passport number</span></span> 
- <span data-ttu-id="c49b6-2921">Passport 無</span><span class="sxs-lookup"><span data-stu-id="c49b6-2921">Passport no</span></span> 
- <span data-ttu-id="c49b6-2922">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2922">Passport Num</span></span> 
- <span data-ttu-id="c49b6-2923">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2923">Passport #</span></span> 
- <span data-ttu-id="c49b6-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2924">护照</span></span> 
- <span data-ttu-id="c49b6-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2925">中華民國護照</span></span> 
- <span data-ttu-id="c49b6-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="c49b6-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="c49b6-2927">Taiwan Resident Certificate (ARC/TARC) Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2928">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2928">Format</span></span>

<span data-ttu-id="c49b6-2929">10 個字母和數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2930">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2930">Pattern</span></span>

<span data-ttu-id="c49b6-2931">10 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2931">10 letters and digits:</span></span>
- <span data-ttu-id="c49b6-2932">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="c49b6-2933">八位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2934">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2934">Checksum</span></span>

<span data-ttu-id="c49b6-2935">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2936">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2936">Definition</span></span>

<span data-ttu-id="c49b6-2937">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2938">規則運算式 Regex_taiwan_resident_certificate 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2939">從 Keyword_taiwan_resident_certificate 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2940">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="c49b6-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="c49b6-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="c49b6-2942">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2942">Resident Certificate</span></span> 
- <span data-ttu-id="c49b6-2943">常駐居民登記 Cert</span><span class="sxs-lookup"><span data-stu-id="c49b6-2943">Resident Cert</span></span> 
- <span data-ttu-id="c49b6-2944">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2944">Resident Cert.</span></span> 
- <span data-ttu-id="c49b6-2945">識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-2945">Identification card</span></span> 
- <span data-ttu-id="c49b6-2946">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="c49b6-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2947">ARC</span></span> 
- <span data-ttu-id="c49b6-2948">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="c49b6-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2949">TARC</span></span> 
- <span data-ttu-id="c49b6-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2950">居留證</span></span> 
- <span data-ttu-id="c49b6-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2951">外僑居留證</span></span> 
- <span data-ttu-id="c49b6-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="c49b6-p141">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2955">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2955">Format</span></span>

<span data-ttu-id="c49b6-2956">18 個指定格式的字母和數字的組合</span><span class="sxs-lookup"><span data-stu-id="c49b6-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2957">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2957">Pattern</span></span>

<span data-ttu-id="c49b6-2958">18 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2958">18 letters and digits:</span></span>
- <span data-ttu-id="c49b6-2959">五個字母 (不區分大小寫) 或取代字母的數字 "9"</span><span class="sxs-lookup"><span data-stu-id="c49b6-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="c49b6-2960">一個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2960">One digit</span></span> 
- <span data-ttu-id="c49b6-2961">以日期格式 DDMMY 表示出生日期的五位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="c49b6-2962">兩個字母 (不區分大小寫) 或取代字母的數字 "9"</span><span class="sxs-lookup"><span data-stu-id="c49b6-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="c49b6-2963">五位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2964">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2964">Checksum</span></span>

<span data-ttu-id="c49b6-2965">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2966">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2966">Definition</span></span>

<span data-ttu-id="c49b6-2967">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2968">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2969">找到來自於 Keyword_uk_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="c49b6-2970">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-2971">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="c49b6-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="c49b6-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="c49b6-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2973">DVLA</span></span> 
- <span data-ttu-id="c49b6-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2974">light vans</span></span> 
- <span data-ttu-id="c49b6-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2975">quadbikes</span></span> 
- <span data-ttu-id="c49b6-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2976">motor cars</span></span> 
- <span data-ttu-id="c49b6-2977">125cc</span><span class="sxs-lookup"><span data-stu-id="c49b6-2977">125cc</span></span> 
- <span data-ttu-id="c49b6-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2978">sidecar</span></span> 
- <span data-ttu-id="c49b6-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2979">tricycles</span></span> 
- <span data-ttu-id="c49b6-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2980">motorcycles</span></span> 
- <span data-ttu-id="c49b6-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2981">photocard licence</span></span> 
- <span data-ttu-id="c49b6-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2982">learner drivers</span></span> 
- <span data-ttu-id="c49b6-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2983">licence holder</span></span> 
- <span data-ttu-id="c49b6-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2984">licence holders</span></span> 
- <span data-ttu-id="c49b6-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2985">driving licences</span></span> 
- <span data-ttu-id="c49b6-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2986">driving licence</span></span> 
- <span data-ttu-id="c49b6-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="c49b6-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="c49b6-p142">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-2990">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2990">Format</span></span>

<span data-ttu-id="c49b6-2991">兩個字母後尾隨 1-4 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-2992">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-2992">Pattern</span></span>

<span data-ttu-id="c49b6-2993">兩個字母 (不區分大小寫) 後尾隨 1-4 個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-2994">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-2994">Checksum</span></span>

<span data-ttu-id="c49b6-2995">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-2996">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-2996">Definition</span></span>

<span data-ttu-id="c49b6-2997">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-2998">規則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-2999">找到來自於 Keyword_uk_electoral 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-3000">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="c49b6-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="c49b6-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="c49b6-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3002">council nomination</span></span> 
- <span data-ttu-id="c49b6-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3003">nomination form</span></span> 
- <span data-ttu-id="c49b6-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="c49b6-3004">electoral register</span></span> 
- <span data-ttu-id="c49b6-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="c49b6-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="c49b6-p143">英國國民健保服務編號</span><span class="sxs-lookup"><span data-stu-id="c49b6-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3008">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3008">Format</span></span>

<span data-ttu-id="c49b6-3009">以空格分隔的 10-17 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3010">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3010">Pattern</span></span>

<span data-ttu-id="c49b6-3011">10-17 位數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3011">10-17 digits:</span></span>
- <span data-ttu-id="c49b6-3012">3 或 10 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="c49b6-3013">一個空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-3013">A space</span></span> 
- <span data-ttu-id="c49b6-3014">三位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3014">Three digits</span></span> 
- <span data-ttu-id="c49b6-3015">一個空格</span><span class="sxs-lookup"><span data-stu-id="c49b6-3015">A space</span></span> 
- <span data-ttu-id="c49b6-3016">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3017">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3017">Checksum</span></span>

<span data-ttu-id="c49b6-3018">是</span><span class="sxs-lookup"><span data-stu-id="c49b6-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-3019">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3019">Definition</span></span>

<span data-ttu-id="c49b6-3020">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3021">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3022">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3022">One of the following is true:</span></span>
    - <span data-ttu-id="c49b6-3023">找到來自於 Keyword_uk_nhs_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="c49b6-3024">找到來自於 Keyword_uk_nhs_number1 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="c49b6-3025">找到來自於 Keyword_uk_nhs_number_dob 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="c49b6-3026">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-3027">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="c49b6-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="c49b6-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="c49b6-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3029">national health service</span></span> 
- <span data-ttu-id="c49b6-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3030">nhs</span></span> 
- <span data-ttu-id="c49b6-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="c49b6-3031">health services authority</span></span> 
- <span data-ttu-id="c49b6-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="c49b6-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="c49b6-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="c49b6-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="c49b6-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3034">patient id</span></span> 
- <span data-ttu-id="c49b6-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3035">patient identification</span></span> 
- <span data-ttu-id="c49b6-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="c49b6-3036">patient no</span></span> 
- <span data-ttu-id="c49b6-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="c49b6-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="c49b6-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="c49b6-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="c49b6-3039">GP</span><span class="sxs-lookup"><span data-stu-id="c49b6-3039">GP</span></span> 
- <span data-ttu-id="c49b6-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3040">DOB</span></span> 
- <span data-ttu-id="c49b6-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="c49b6-3041">D.O.B</span></span> 
- <span data-ttu-id="c49b6-3042">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3042">Date of Birth</span></span> 
- <span data-ttu-id="c49b6-3043">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="c49b6-p144">英國國民保險編號 (NINO)</span><span class="sxs-lookup"><span data-stu-id="c49b6-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3046">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3046">Format</span></span>

<span data-ttu-id="c49b6-3047">7 個字元或空格或虛線隔開的 9 字元</span><span class="sxs-lookup"><span data-stu-id="c49b6-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3048">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3048">Pattern</span></span>

<span data-ttu-id="c49b6-3049">兩個可能的模式：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3049">Two possible patterns:</span></span>

- <span data-ttu-id="c49b6-3050">兩個字母 (有效 NINOs 只使用某些字元在此模式會驗證 ； 這個前置詞不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="c49b6-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="c49b6-3051">六位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3051">Six digits</span></span>
- <span data-ttu-id="c49b6-3052">''，'B' 'C' 或鎖 ' （例如首碼僅某些字元中允許尾碼; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c49b6-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="c49b6-3053">或</span><span class="sxs-lookup"><span data-stu-id="c49b6-3053">OR</span></span>

- <span data-ttu-id="c49b6-3054">兩個字母</span><span class="sxs-lookup"><span data-stu-id="c49b6-3054">Two letters</span></span>
- <span data-ttu-id="c49b6-3055">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3055">A space or dash</span></span>
- <span data-ttu-id="c49b6-3056">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3056">Two digits</span></span>
- <span data-ttu-id="c49b6-3057">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3057">A space or dash</span></span>
- <span data-ttu-id="c49b6-3058">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3058">Two digits</span></span>
- <span data-ttu-id="c49b6-3059">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3059">A space or dash</span></span>
- <span data-ttu-id="c49b6-3060">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3060">Two digits</span></span>
- <span data-ttu-id="c49b6-3061">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3061">A space or dash</span></span>
- <span data-ttu-id="c49b6-3062">''，'B' 'C' 或鎖 '</span><span class="sxs-lookup"><span data-stu-id="c49b6-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3063">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3063">Checksum</span></span>

<span data-ttu-id="c49b6-3064">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-3065">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3065">Definition</span></span>

<span data-ttu-id="c49b6-3066">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3067">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3068">找到來自於 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="c49b6-3069">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3070">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3071">找不到來自於 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-3072">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="c49b6-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="c49b6-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="c49b6-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3074">national insurance number</span></span> 
- <span data-ttu-id="c49b6-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3075">national insurance contributions</span></span> 
- <span data-ttu-id="c49b6-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3076">protection act</span></span> 
- <span data-ttu-id="c49b6-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3077">insurance</span></span> 
- <span data-ttu-id="c49b6-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3078">social security number</span></span> 
- <span data-ttu-id="c49b6-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3079">insurance application</span></span> 
- <span data-ttu-id="c49b6-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3080">medical application</span></span> 
- <span data-ttu-id="c49b6-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3081">social insurance</span></span> 
- <span data-ttu-id="c49b6-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3082">medical attention</span></span> 
- <span data-ttu-id="c49b6-3083">社會安全</span><span class="sxs-lookup"><span data-stu-id="c49b6-3083">social security</span></span> 
- <span data-ttu-id="c49b6-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3084">great britain</span></span> 
- <span data-ttu-id="c49b6-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="c49b6-p145">美國 / 英國護照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3088">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3088">Format</span></span>

<span data-ttu-id="c49b6-3089">九位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3090">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3090">Pattern</span></span>

<span data-ttu-id="c49b6-3091">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3092">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3092">Checksum</span></span>

<span data-ttu-id="c49b6-3093">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-3094">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3094">Definition</span></span>

<span data-ttu-id="c49b6-3095">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3096">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3097">找到來自於 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-3098">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="c49b6-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="c49b6-3099">Keyword_passport</span></span>

- <span data-ttu-id="c49b6-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c49b6-3100">Passport Number</span></span> 
- <span data-ttu-id="c49b6-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="c49b6-3101">Passport No</span></span> 
- <span data-ttu-id="c49b6-3102">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3102">Passport #</span></span> 
- <span data-ttu-id="c49b6-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3103">Passport#</span></span> 
- <span data-ttu-id="c49b6-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="c49b6-3104">PassportID</span></span> 
- <span data-ttu-id="c49b6-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3105">Passportno</span></span> 
- <span data-ttu-id="c49b6-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3106">passportnumber</span></span> 
- <span data-ttu-id="c49b6-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="c49b6-3107">パスポート</span></span> 
- <span data-ttu-id="c49b6-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3108">パスポート番号</span></span> 
- <span data-ttu-id="c49b6-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3109">パスポートのNum</span></span> 
- <span data-ttu-id="c49b6-3110">パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3110">パスポート＃</span></span> 
- <span data-ttu-id="c49b6-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="c49b6-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="c49b6-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="c49b6-3112">Passeport n °</span></span> 
- <span data-ttu-id="c49b6-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3113">Passeport Non</span></span> 
- <span data-ttu-id="c49b6-3114">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3114">Passeport #</span></span> 
- <span data-ttu-id="c49b6-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3115">Passeport#</span></span> 
- <span data-ttu-id="c49b6-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="c49b6-3116">PasseportNon</span></span> 
- <span data-ttu-id="c49b6-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="c49b6-3118">美國銀行帳號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3119">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3119">Format</span></span>

<span data-ttu-id="c49b6-3120">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3121">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3121">Pattern</span></span>

<span data-ttu-id="c49b6-3122">8-17 個連續數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3123">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3123">Checksum</span></span>

<span data-ttu-id="c49b6-3124">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-3125">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3125">Definition</span></span>

<span data-ttu-id="c49b6-3126">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3127">規則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3128">找到來自於 Keyword_usa_Bank_Account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c49b6-3129">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="c49b6-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="c49b6-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="c49b6-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3131">Checking Account Number</span></span> 
- <span data-ttu-id="c49b6-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3132">Checking Account</span></span> 
- <span data-ttu-id="c49b6-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3133">Checking Account #</span></span> 
- <span data-ttu-id="c49b6-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="c49b6-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3135">Checking Acct #</span></span> 
- <span data-ttu-id="c49b6-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="c49b6-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3137">Checking Account No.</span></span> 
- <span data-ttu-id="c49b6-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3138">Bank Account Number</span></span> 
- <span data-ttu-id="c49b6-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3139">Bank Account #</span></span> 
- <span data-ttu-id="c49b6-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="c49b6-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3141">Bank Acct #</span></span> 
- <span data-ttu-id="c49b6-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="c49b6-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3143">Bank Account No.</span></span> 
- <span data-ttu-id="c49b6-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3144">Savings Account Number</span></span> 
- <span data-ttu-id="c49b6-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3145">Savings Account.</span></span> 
- <span data-ttu-id="c49b6-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3146">Savings Account #</span></span> 
- <span data-ttu-id="c49b6-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="c49b6-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3148">Savings Acct #</span></span> 
- <span data-ttu-id="c49b6-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="c49b6-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3150">Savings Account No.</span></span> 
- <span data-ttu-id="c49b6-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3151">Debit Account Number</span></span> 
- <span data-ttu-id="c49b6-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3152">Debit Account</span></span> 
- <span data-ttu-id="c49b6-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3153">Debit Account #</span></span> 
- <span data-ttu-id="c49b6-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="c49b6-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3155">Debit Acct #</span></span> 
- <span data-ttu-id="c49b6-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="c49b6-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="c49b6-3158">美國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3159">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3159">Format</span></span>

<span data-ttu-id="c49b6-3160">隨州別不同</span><span class="sxs-lookup"><span data-stu-id="c49b6-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3161">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3161">Pattern</span></span>

<span data-ttu-id="c49b6-3162">隨州別不同 -- 以紐約州為例：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="c49b6-3163">9 的數字格式像是 ddd ddd ddd 會比對。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="c49b6-3164">將不會符合 ddddddddd 類似的九個位數。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3165">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3165">Checksum</span></span>

<span data-ttu-id="c49b6-3166">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-3167">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3167">Definition</span></span>

<span data-ttu-id="c49b6-3168">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3169">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3170">找到來自於 Keyword_[state_name]_drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="c49b6-3171">從 Keyword_us_drivers_license 關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="c49b6-3172">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3173">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3174">找到來自於 Keyword_[state_name]_drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="c49b6-3175">找到來自於 Keyword_us_drivers_license_abbreviations 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="c49b6-3176">找不到來自於 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-3177">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="c49b6-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="c49b6-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="c49b6-3179">DL</span><span class="sxs-lookup"><span data-stu-id="c49b6-3179">DL</span></span> 
- <span data-ttu-id="c49b6-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="c49b6-3180">DLS</span></span> 
- <span data-ttu-id="c49b6-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="c49b6-3181">CDL</span></span> 
- <span data-ttu-id="c49b6-3182">CDLS</span><span class="sxs-lookup"><span data-stu-id="c49b6-3182">CDLS</span></span> 
- <span data-ttu-id="c49b6-3183">ID</span><span class="sxs-lookup"><span data-stu-id="c49b6-3183">ID</span></span> 
- <span data-ttu-id="c49b6-3184">識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3184">IDs</span></span> 
- <span data-ttu-id="c49b6-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="c49b6-3185">DL#</span></span> 
- <span data-ttu-id="c49b6-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3186">DLS#</span></span> 
- <span data-ttu-id="c49b6-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3187">CDL#</span></span> 
- <span data-ttu-id="c49b6-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3188">CDLS#</span></span> 
- <span data-ttu-id="c49b6-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="c49b6-3189">ID#</span></span>
- <span data-ttu-id="c49b6-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3190">IDs#</span></span> 
- <span data-ttu-id="c49b6-3191">識別碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3191">ID number</span></span> 
- <span data-ttu-id="c49b6-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3192">ID numbers</span></span> 
- <span data-ttu-id="c49b6-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="c49b6-3193">LIC</span></span> 
- <span data-ttu-id="c49b6-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="c49b6-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="c49b6-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="c49b6-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3196">DriverLic</span></span> 
- <span data-ttu-id="c49b6-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3197">DriverLics</span></span> 
- <span data-ttu-id="c49b6-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="c49b6-3198">DriverLicense</span></span> 
- <span data-ttu-id="c49b6-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-3199">DriverLicenses</span></span> 
- <span data-ttu-id="c49b6-3200">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3200">Driver Lic</span></span> 
- <span data-ttu-id="c49b6-3201">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3201">Driver Lics</span></span> 
- <span data-ttu-id="c49b6-3202">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3202">Driver License</span></span> 
- <span data-ttu-id="c49b6-3203">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3203">Driver Licenses</span></span> 
- <span data-ttu-id="c49b6-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3204">DriversLic</span></span> 
- <span data-ttu-id="c49b6-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3205">DriversLics</span></span> 
- <span data-ttu-id="c49b6-3206">執照</span><span class="sxs-lookup"><span data-stu-id="c49b6-3206">DriversLicense</span></span> 
- <span data-ttu-id="c49b6-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-3207">DriversLicenses</span></span> 
- <span data-ttu-id="c49b6-3208">發行的驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3208">Drivers Lic</span></span> 
- <span data-ttu-id="c49b6-3209">發行的驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3209">Drivers Lics</span></span> 
- <span data-ttu-id="c49b6-3210">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3210">Drivers License</span></span> 
- <span data-ttu-id="c49b6-3211">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="c49b6-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3212">Driver'Lic</span></span> 
- <span data-ttu-id="c49b6-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3213">Driver'Lics</span></span> 
- <span data-ttu-id="c49b6-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="c49b6-3214">Driver'License</span></span> 
- <span data-ttu-id="c49b6-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="c49b6-3216">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3216">Driver' Lic</span></span> 
- <span data-ttu-id="c49b6-3217">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3217">Driver' Lics</span></span> 
- <span data-ttu-id="c49b6-3218">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3218">Driver' License</span></span> 
- <span data-ttu-id="c49b6-3219">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3219">Driver' Licenses</span></span>
- <span data-ttu-id="c49b6-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3220">Driver'sLic</span></span> 
- <span data-ttu-id="c49b6-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3221">Driver'sLics</span></span> 
- <span data-ttu-id="c49b6-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="c49b6-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="c49b6-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="c49b6-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="c49b6-3224">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="c49b6-3224">Driver's Lic</span></span> 
- <span data-ttu-id="c49b6-3225">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="c49b6-3225">Driver's Lics</span></span> 
- <span data-ttu-id="c49b6-3226">駕照</span><span class="sxs-lookup"><span data-stu-id="c49b6-3226">Driver's License</span></span> 
- <span data-ttu-id="c49b6-3227">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="c49b6-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="c49b6-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3228">identification number</span></span> 
- <span data-ttu-id="c49b6-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3229">identification numbers</span></span> 
- <span data-ttu-id="c49b6-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3230">identification #</span></span> 
- <span data-ttu-id="c49b6-3231">識別碼卡片</span><span class="sxs-lookup"><span data-stu-id="c49b6-3231">id card</span></span> 
- <span data-ttu-id="c49b6-3232">識別碼卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-3232">id cards</span></span> 
- <span data-ttu-id="c49b6-3233">識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-3233">identification card</span></span> 
- <span data-ttu-id="c49b6-3234">識別卡</span><span class="sxs-lookup"><span data-stu-id="c49b6-3234">identification cards</span></span> 
- <span data-ttu-id="c49b6-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3235">DriverLic#</span></span> 
- <span data-ttu-id="c49b6-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3236">DriverLics#</span></span> 
- <span data-ttu-id="c49b6-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3237">DriverLicense#</span></span> 
- <span data-ttu-id="c49b6-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="c49b6-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="c49b6-3239">Driver Lic#</span></span> 
- <span data-ttu-id="c49b6-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3240">Driver Lics#</span></span> 
- <span data-ttu-id="c49b6-3241">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3241">Driver License#</span></span> 
- <span data-ttu-id="c49b6-3242">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="c49b6-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3243">DriversLic#</span></span> 
- <span data-ttu-id="c49b6-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3244">DriversLics#</span></span> 
- <span data-ttu-id="c49b6-3245">執照 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3245">DriversLicense#</span></span> 
- <span data-ttu-id="c49b6-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="c49b6-3247">發行的驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="c49b6-3248">發行的驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="c49b6-3249">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3249">Drivers License#</span></span> 
- <span data-ttu-id="c49b6-3250">授權 # 驅動程式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="c49b6-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="c49b6-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="c49b6-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3253">Driver'License#</span></span> 
- <span data-ttu-id="c49b6-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="c49b6-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="c49b6-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="c49b6-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3257">Driver' License#</span></span> 
- <span data-ttu-id="c49b6-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="c49b6-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="c49b6-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="c49b6-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="c49b6-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="c49b6-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="c49b6-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="c49b6-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3265">Driver's License#</span></span> 
- <span data-ttu-id="c49b6-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="c49b6-3267">識別碼卡片 #</span><span class="sxs-lookup"><span data-stu-id="c49b6-3267">id card#</span></span> 
- <span data-ttu-id="c49b6-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3268">id cards#</span></span> 
- <span data-ttu-id="c49b6-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3269">identification card#</span></span> 
- <span data-ttu-id="c49b6-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="c49b6-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="c49b6-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="c49b6-3272">州別縮寫 (例如 "NY")
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="c49b6-3273">州名稱 (例如 "New York")
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="c49b6-3274">美國個別納稅人身分識別碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3275">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3275">Format</span></span>

<span data-ttu-id="c49b6-3276">以 "9" 開頭且第四個數字是 "7" 或 "8" 的九位數，可選擇加上空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3277">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3277">Pattern</span></span>

<span data-ttu-id="c49b6-3278">格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3278">Formatted:</span></span>
- <span data-ttu-id="c49b6-3279">數字 "9"</span><span class="sxs-lookup"><span data-stu-id="c49b6-3279">The digit "9"</span></span> 
- <span data-ttu-id="c49b6-3280">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3280">Two digits</span></span> 
- <span data-ttu-id="c49b6-3281">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3281">A space or dash</span></span> 
- <span data-ttu-id="c49b6-3282">一個 "7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="c49b6-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="c49b6-3283">一個數字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3283">A digit</span></span> 
- <span data-ttu-id="c49b6-3284">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="c49b6-3284">A space, or dash</span></span> 
- <span data-ttu-id="c49b6-3285">四位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3285">Four digits</span></span>

<span data-ttu-id="c49b6-3286">未格式化：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3286">Unformatted:</span></span>
- <span data-ttu-id="c49b6-3287">數字 "9"</span><span class="sxs-lookup"><span data-stu-id="c49b6-3287">The digit "9"</span></span> 
- <span data-ttu-id="c49b6-3288">兩位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3288">Two digits</span></span> 
- <span data-ttu-id="c49b6-3289">一個 "7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="c49b6-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="c49b6-3290">五位數</span><span class="sxs-lookup"><span data-stu-id="c49b6-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3291">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3291">Checksum</span></span>

<span data-ttu-id="c49b6-3292">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="c49b6-3293">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3293">Definition</span></span>

<span data-ttu-id="c49b6-3294">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3295">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3296">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="c49b6-3297">找到來自於 Keyword_itin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="c49b6-3298">函數 Func_us_address 找到正確日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="c49b6-3299">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="c49b6-3300">找到來自於 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="c49b6-3301">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3302">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3303">下列至少一項為真：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="c49b6-3304">找到來自於 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="c49b6-3305">函數 Func_us_address 找到正確日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="c49b6-3306">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-3307">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="c49b6-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="c49b6-3308">Keyword_itin</span></span>

- <span data-ttu-id="c49b6-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3309">taxpayer</span></span> 
- <span data-ttu-id="c49b6-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3310">tax id</span></span> 
- <span data-ttu-id="c49b6-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3311">tax identification</span></span> 
- <span data-ttu-id="c49b6-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3312">itin</span></span> 
- <span data-ttu-id="c49b6-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="c49b6-3313">ssn</span></span> 
- <span data-ttu-id="c49b6-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3314">tin</span></span> 
- <span data-ttu-id="c49b6-3315">社會安全</span><span class="sxs-lookup"><span data-stu-id="c49b6-3315">social security</span></span> 
- <span data-ttu-id="c49b6-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3316">tax payer</span></span> 
- <span data-ttu-id="c49b6-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3317">itins</span></span> 
- <span data-ttu-id="c49b6-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="c49b6-3318">taxid</span></span> 
- <span data-ttu-id="c49b6-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="c49b6-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="c49b6-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="c49b6-3321">License</span><span class="sxs-lookup"><span data-stu-id="c49b6-3321">License</span></span> 
- <span data-ttu-id="c49b6-3322">DL</span><span class="sxs-lookup"><span data-stu-id="c49b6-3322">DL</span></span> 
- <span data-ttu-id="c49b6-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3323">DOB</span></span> 
- <span data-ttu-id="c49b6-3324">出生日期</span><span class="sxs-lookup"><span data-stu-id="c49b6-3324">Birthdate</span></span> 
- <span data-ttu-id="c49b6-3325">生日 </span><span class="sxs-lookup"><span data-stu-id="c49b6-3325">Birthday</span></span> 
- <span data-ttu-id="c49b6-3326">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="c49b6-3327">美國社會安全編號 (SSN)</span><span class="sxs-lookup"><span data-stu-id="c49b6-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="c49b6-3328">格式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3328">Format</span></span>

<span data-ttu-id="c49b6-3329">9 位數，可採用格式化或未格式化模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="c49b6-3330">SSN 發出 mid 2011 之前，是否具有強式格式設定其中某些部分的數字必須落在有效特定範圍 （但沒有具總和檢查碼）。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="c49b6-3331">模式</span><span class="sxs-lookup"><span data-stu-id="c49b6-3331">Pattern</span></span>

<span data-ttu-id="c49b6-3332">四個不同的模式 SSNs 尋找四個函數：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="c49b6-3333">Func_ssn 都會尋找 SSNs 之前 2011年強式格式格式為虛線或空格 (ddd-dd-dddd OR ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="c49b6-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="c49b6-3334">Func_unformatted_ssn 都會尋找 SSNs 之前 2011年強式的格式以未格式化為九個連續的數字 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="c49b6-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="c49b6-3335">Func_randomized_formatted_ssn 都會以虛線或空格 (ddd-dd-dddd OR ddd dd dddd) 格式化的張貼 2011 SSNs</span><span class="sxs-lookup"><span data-stu-id="c49b6-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="c49b6-3336">Func_randomized_unformatted_ssn 會尋找已格式化為九個連續的數字 (ddddddddd) 的文章 2011 SSNs</span><span class="sxs-lookup"><span data-stu-id="c49b6-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="c49b6-3337">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c49b6-3337">Checksum</span></span>

<span data-ttu-id="c49b6-3338">否</span><span class="sxs-lookup"><span data-stu-id="c49b6-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="c49b6-3339">定義</span><span class="sxs-lookup"><span data-stu-id="c49b6-3339">Definition</span></span>

<span data-ttu-id="c49b6-3340">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3341">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3342">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="c49b6-3343">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3344">函數 Func_unformatted_ssn 會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3345">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="c49b6-3346">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3347">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3348">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="c49b6-3349">函數 Func_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="c49b6-3350">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 55%：</span><span class="sxs-lookup"><span data-stu-id="c49b6-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="c49b6-3351">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="c49b6-3352">找到來自於 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="c49b6-3353">函數 Func_unformatted_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c49b6-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="c49b6-3354">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c49b6-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="c49b6-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="c49b6-3355">Keyword_ssn</span></span>

- <span data-ttu-id="c49b6-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3356">Social Security</span></span> 
- <span data-ttu-id="c49b6-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3357">Social Security#</span></span> 
- <span data-ttu-id="c49b6-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3358">Soc Sec</span></span> 
- <span data-ttu-id="c49b6-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="c49b6-3359">SSN</span></span> 
- <span data-ttu-id="c49b6-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3360">SSNS</span></span> 
- <span data-ttu-id="c49b6-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3361">SSN#</span></span> 
- <span data-ttu-id="c49b6-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3362">SS#</span></span> 
- <span data-ttu-id="c49b6-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="c49b6-3363">SSID</span></span> 
   

