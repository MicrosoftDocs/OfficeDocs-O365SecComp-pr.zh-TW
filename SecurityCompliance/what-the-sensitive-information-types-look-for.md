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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全性中的資料遺失防護 (DLP)&amp;合規性中心包含可供您在 DLP 原則中使用的 80 種敏感資訊類型。 本主題列出所有的這些敏感資訊類型，並顯示 DLP 原則看起來當它偵測到每個類型。
ms.openlocfilehash: e9811b285e98a791570dc91e275cb5cead4f8bc9
ms.sourcegitcommit: 6e8e2b43a4bea31c1e835c5b050824651c6a0094
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537640"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="88180-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="88180-104">What the sensitive information types look for</span></span>

<span data-ttu-id="88180-105">Office 365 安全性中的資料遺失防護 (DLP)&amp;合規性中心包含許多可供您可以使用 DLP 原則中的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88180-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="88180-106">本主題列出所有的這些敏感資訊類型，並顯示 DLP 原則看起來當它偵測到每個類型。</span><span class="sxs-lookup"><span data-stu-id="88180-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="88180-107">敏感資訊類型是由能夠識別規則運算式或函數的模式所定義。</span><span class="sxs-lookup"><span data-stu-id="88180-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="88180-108">此外，例如關鍵字和總和檢查碼佐證性證據可以用來識別敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88180-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="88180-109">信賴等級和接近性也會用於評估程序。</span><span class="sxs-lookup"><span data-stu-id="88180-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="88180-110">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="88180-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-111">Format</span><span class="sxs-lookup"><span data-stu-id="88180-111">Format</span></span>

<span data-ttu-id="88180-112">這可能是採用格式化或未格式化模式的 9 位數</span><span class="sxs-lookup"><span data-stu-id="88180-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-113">模式</span><span class="sxs-lookup"><span data-stu-id="88180-113">Pattern</span></span>

<span data-ttu-id="88180-114">格式：</span><span class="sxs-lookup"><span data-stu-id="88180-114">Formatted:</span></span>
- <span data-ttu-id="88180-115">以 0、 1、 2、 3、 6、 7 或 8 開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="88180-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="88180-116">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-116">A hyphen</span></span>
- <span data-ttu-id="88180-117">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-117">Four digits</span></span>
- <span data-ttu-id="88180-118">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-118">A hyphen</span></span>
- <span data-ttu-id="88180-119">數字</span><span class="sxs-lookup"><span data-stu-id="88180-119">A digit</span></span>

<span data-ttu-id="88180-120">未格式化： 9 個連續數字以 0、 1、 2、 3、 6、 7 或 8 開頭</span><span class="sxs-lookup"><span data-stu-id="88180-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="88180-121">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-121">Checksum</span></span>

<span data-ttu-id="88180-122">否</span><span class="sxs-lookup"><span data-stu-id="88180-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-123">定義</span><span class="sxs-lookup"><span data-stu-id="88180-123">Definition</span></span>

<span data-ttu-id="88180-124">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-126">找不到來自 Keyword_ABA_Routing 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="88180-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="88180-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="88180-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="88180-129">阿拉巴馬州銀行</span><span class="sxs-lookup"><span data-stu-id="88180-129">aba</span></span>
- <span data-ttu-id="88180-130">阿拉巴馬州銀行 #</span><span class="sxs-lookup"><span data-stu-id="88180-130">aba #</span></span>
- <span data-ttu-id="88180-131">阿拉巴馬州銀行路由 #</span><span class="sxs-lookup"><span data-stu-id="88180-131">aba routing #</span></span>
- <span data-ttu-id="88180-132">阿拉巴馬州銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="88180-132">aba routing number</span></span>
- <span data-ttu-id="88180-133">阿拉巴馬州銀行 #</span><span class="sxs-lookup"><span data-stu-id="88180-133">aba#</span></span>
- <span data-ttu-id="88180-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="88180-134">abarouting#</span></span>
- <span data-ttu-id="88180-135">阿拉巴馬州銀行號碼</span><span class="sxs-lookup"><span data-stu-id="88180-135">aba number</span></span>
- <span data-ttu-id="88180-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="88180-136">abaroutingnumber</span></span>
- <span data-ttu-id="88180-137">美國銀行關聯路由 #</span><span class="sxs-lookup"><span data-stu-id="88180-137">american bank association routing #</span></span>
- <span data-ttu-id="88180-138">美國銀行關聯路由號碼</span><span class="sxs-lookup"><span data-stu-id="88180-138">american bank association routing number</span></span>
- <span data-ttu-id="88180-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="88180-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="88180-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="88180-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="88180-141">銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="88180-141">bank routing number</span></span>
- <span data-ttu-id="88180-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="88180-142">bankrouting#</span></span>
- <span data-ttu-id="88180-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="88180-143">bankroutingnumber</span></span>
- <span data-ttu-id="88180-144">路由傳輸數目</span><span class="sxs-lookup"><span data-stu-id="88180-144">routing transit number</span></span>
- <span data-ttu-id="88180-145">RTN</span><span class="sxs-lookup"><span data-stu-id="88180-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="88180-146">阿根廷國民識別 （dni） 碼數目</span><span class="sxs-lookup"><span data-stu-id="88180-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-147">Format</span><span class="sxs-lookup"><span data-stu-id="88180-147">Format</span></span>

<span data-ttu-id="88180-148">以句點分隔的八位數</span><span class="sxs-lookup"><span data-stu-id="88180-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-149">模式</span><span class="sxs-lookup"><span data-stu-id="88180-149">Pattern</span></span>

<span data-ttu-id="88180-150">八位數：</span><span class="sxs-lookup"><span data-stu-id="88180-150">Eight digits:</span></span>
- <span data-ttu-id="88180-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-151">Two digits</span></span>
- <span data-ttu-id="88180-152">句點</span><span class="sxs-lookup"><span data-stu-id="88180-152">A period</span></span>
- <span data-ttu-id="88180-153">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-153">Three digits</span></span>
- <span data-ttu-id="88180-154">句點</span><span class="sxs-lookup"><span data-stu-id="88180-154">A period</span></span>
- <span data-ttu-id="88180-155">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-156">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-156">Checksum</span></span>

<span data-ttu-id="88180-157">否</span><span class="sxs-lookup"><span data-stu-id="88180-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-158">定義</span><span class="sxs-lookup"><span data-stu-id="88180-158">Definition</span></span>

<span data-ttu-id="88180-159">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-160">規則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-161">找不到來自 Keyword_argentina_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="88180-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="88180-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="88180-164">阿根廷國民識別數字</span><span class="sxs-lookup"><span data-stu-id="88180-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="88180-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="88180-165">Identity</span></span> 
- <span data-ttu-id="88180-166">Identification 國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="88180-167">DNI</span><span class="sxs-lookup"><span data-stu-id="88180-167">DNI</span></span> 
- <span data-ttu-id="88180-168">NIC 國民身分登錄的人員</span><span class="sxs-lookup"><span data-stu-id="88180-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="88180-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="88180-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="88180-170">Registro Nacional de 美國的人物代表</span><span class="sxs-lookup"><span data-stu-id="88180-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="88180-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="88180-171">Identidad</span></span> 
- <span data-ttu-id="88180-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="88180-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="88180-173">澳洲銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-174">Format</span><span class="sxs-lookup"><span data-stu-id="88180-174">Format</span></span>

<span data-ttu-id="88180-175">包含或不含銀行代號的 6-10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-176">模式</span><span class="sxs-lookup"><span data-stu-id="88180-176">Pattern</span></span>

<span data-ttu-id="88180-177">帳戶號碼為 6-10 位數。</span><span class="sxs-lookup"><span data-stu-id="88180-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="88180-178">澳洲銀行代號：</span><span class="sxs-lookup"><span data-stu-id="88180-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="88180-179">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-179">Three digits</span></span> 
- <span data-ttu-id="88180-180">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-180">A hyphen</span></span> 
- <span data-ttu-id="88180-181">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-182">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-182">Checksum</span></span>

<span data-ttu-id="88180-183">否</span><span class="sxs-lookup"><span data-stu-id="88180-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-184">定義</span><span class="sxs-lookup"><span data-stu-id="88180-184">Definition</span></span>

<span data-ttu-id="88180-185">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-186">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。.</span><span class="sxs-lookup"><span data-stu-id="88180-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="88180-187">找不到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="88180-188">規則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="88180-189">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-190">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。.</span><span class="sxs-lookup"><span data-stu-id="88180-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="88180-191">找不到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="88180-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="88180-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="88180-194">swift 銀行代碼</span><span class="sxs-lookup"><span data-stu-id="88180-194">swift bank code</span></span>
- <span data-ttu-id="88180-195">對應的銀行</span><span class="sxs-lookup"><span data-stu-id="88180-195">correspondent bank</span></span>
- <span data-ttu-id="88180-196">基底的貨幣</span><span class="sxs-lookup"><span data-stu-id="88180-196">base currency</span></span>
- <span data-ttu-id="88180-197">usa 帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-197">usa account</span></span>
- <span data-ttu-id="88180-198">持有者地址</span><span class="sxs-lookup"><span data-stu-id="88180-198">holder address</span></span>
- <span data-ttu-id="88180-199">銀行地址</span><span class="sxs-lookup"><span data-stu-id="88180-199">bank address</span></span>
- <span data-ttu-id="88180-200">資訊的帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-200">information account</span></span>
- <span data-ttu-id="88180-201">基金傳輸</span><span class="sxs-lookup"><span data-stu-id="88180-201">fund transfers</span></span>
- <span data-ttu-id="88180-202">銀行費用</span><span class="sxs-lookup"><span data-stu-id="88180-202">bank charges</span></span>
- <span data-ttu-id="88180-203">銀行詳細資料</span><span class="sxs-lookup"><span data-stu-id="88180-203">bank details</span></span>
- <span data-ttu-id="88180-204">銀行業資訊</span><span class="sxs-lookup"><span data-stu-id="88180-204">banking information</span></span>
- <span data-ttu-id="88180-205">完整名稱</span><span class="sxs-lookup"><span data-stu-id="88180-205">full names</span></span>
- <span data-ttu-id="88180-206">iaea</span><span class="sxs-lookup"><span data-stu-id="88180-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="88180-207">澳洲駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-208">Format</span><span class="sxs-lookup"><span data-stu-id="88180-208">Format</span></span>

<span data-ttu-id="88180-209">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="88180-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-210">模式</span><span class="sxs-lookup"><span data-stu-id="88180-210">Pattern</span></span>

<span data-ttu-id="88180-211">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="88180-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="88180-212">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="88180-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-213">Two digits</span></span> 
- <span data-ttu-id="88180-214">五個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="88180-215">或</span><span class="sxs-lookup"><span data-stu-id="88180-215">OR</span></span>

- <span data-ttu-id="88180-216">1-2 選用字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="88180-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="88180-217">4-9 digits</span></span>

<span data-ttu-id="88180-218">或</span><span class="sxs-lookup"><span data-stu-id="88180-218">OR</span></span>

- <span data-ttu-id="88180-219">九個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-220">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-220">Checksum</span></span>

<span data-ttu-id="88180-221">否</span><span class="sxs-lookup"><span data-stu-id="88180-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-222">定義</span><span class="sxs-lookup"><span data-stu-id="88180-222">Definition</span></span>

<span data-ttu-id="88180-223">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-224">規則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-225">找不到來自 Keyword_australia_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="88180-226">找不到來自 Keyword_australia_drivers_license_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="88180-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="88180-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="88180-229">國際主導許可</span><span class="sxs-lookup"><span data-stu-id="88180-229">international driving permits</span></span>
- <span data-ttu-id="88180-230">澳洲汽車關聯</span><span class="sxs-lookup"><span data-stu-id="88180-230">australian automobile association</span></span>
- <span data-ttu-id="88180-231">國際主導允許</span><span class="sxs-lookup"><span data-stu-id="88180-231">international driving permit</span></span>
- <span data-ttu-id="88180-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="88180-232">DriverLicence</span></span>
- <span data-ttu-id="88180-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="88180-233">DriverLicences</span></span>
- <span data-ttu-id="88180-234">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-234">Driver Lic</span></span>
- <span data-ttu-id="88180-235">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-235">Driver Licence</span></span>
- <span data-ttu-id="88180-236">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-236">Driver Licences</span></span>
- <span data-ttu-id="88180-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="88180-237">DriversLic</span></span>
- <span data-ttu-id="88180-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="88180-238">DriversLicence</span></span>
- <span data-ttu-id="88180-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="88180-239">DriversLicences</span></span>
- <span data-ttu-id="88180-240">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-240">Drivers Lic</span></span>
- <span data-ttu-id="88180-241">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-241">Drivers Lics</span></span>
- <span data-ttu-id="88180-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-242">Drivers Licence</span></span>
- <span data-ttu-id="88180-243">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-243">Drivers Licences</span></span>
- <span data-ttu-id="88180-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="88180-244">Driver'Lic</span></span>
- <span data-ttu-id="88180-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="88180-245">Driver'Lics</span></span>
- <span data-ttu-id="88180-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="88180-246">Driver'Licence</span></span>
- <span data-ttu-id="88180-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="88180-247">Driver'Licences</span></span>
- <span data-ttu-id="88180-248">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="88180-248">Driver' Lic</span></span>
- <span data-ttu-id="88180-249">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="88180-249">Driver' Lics</span></span>
- <span data-ttu-id="88180-250">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-250">Driver' Licence</span></span>
- <span data-ttu-id="88180-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-251">Driver' Licences</span></span>
- <span data-ttu-id="88180-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="88180-252">Driver'sLic</span></span>
- <span data-ttu-id="88180-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="88180-253">Driver'sLics</span></span>
- <span data-ttu-id="88180-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="88180-254">Driver'sLicence</span></span>
- <span data-ttu-id="88180-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="88180-255">Driver'sLicences</span></span>
- <span data-ttu-id="88180-256">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-256">Driver's Lic</span></span>
- <span data-ttu-id="88180-257">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-257">Driver's Lics</span></span>
- <span data-ttu-id="88180-258">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-258">Driver's Licence</span></span>
- <span data-ttu-id="88180-259">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-259">Driver's Licences</span></span>
- <span data-ttu-id="88180-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="88180-260">DriverLic#</span></span>
- <span data-ttu-id="88180-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="88180-261">DriverLics#</span></span>
- <span data-ttu-id="88180-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="88180-262">DriverLicence#</span></span>
- <span data-ttu-id="88180-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="88180-263">DriverLicences#</span></span>
- <span data-ttu-id="88180-264">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-264">Driver Lic#</span></span>
- <span data-ttu-id="88180-265">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-265">Driver Lics#</span></span>
- <span data-ttu-id="88180-266">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-266">Driver Licence#</span></span>
- <span data-ttu-id="88180-267">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-267">Driver Licences#</span></span>
- <span data-ttu-id="88180-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="88180-268">DriversLic#</span></span>
- <span data-ttu-id="88180-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="88180-269">DriversLics#</span></span>
- <span data-ttu-id="88180-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="88180-270">DriversLicence#</span></span>
- <span data-ttu-id="88180-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="88180-271">DriversLicences#</span></span>
- <span data-ttu-id="88180-272">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-272">Drivers Lic#</span></span>
- <span data-ttu-id="88180-273">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-273">Drivers Lics#</span></span>
- <span data-ttu-id="88180-274">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-274">Drivers Licence#</span></span>
- <span data-ttu-id="88180-275">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-275">Drivers Licences#</span></span>
- <span data-ttu-id="88180-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-276">Driver'Lic#</span></span>
- <span data-ttu-id="88180-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-277">Driver'Lics#</span></span>
- <span data-ttu-id="88180-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="88180-278">Driver'Licence#</span></span>
- <span data-ttu-id="88180-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="88180-279">Driver'Licences#</span></span>
- <span data-ttu-id="88180-280">驅動程式 ' Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-280">Driver' Lic#</span></span>
- <span data-ttu-id="88180-281">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-281">Driver' Lics#</span></span>
- <span data-ttu-id="88180-282">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-282">Driver' Licence#</span></span>
- <span data-ttu-id="88180-283">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-283">Driver' Licences#</span></span>
- <span data-ttu-id="88180-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="88180-284">Driver'sLic#</span></span>
- <span data-ttu-id="88180-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="88180-285">Driver'sLics#</span></span>
- <span data-ttu-id="88180-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="88180-286">Driver'sLicence#</span></span>
- <span data-ttu-id="88180-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="88180-287">Driver'sLicences#</span></span>
- <span data-ttu-id="88180-288">駕 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-288">Driver's Lic#</span></span>
- <span data-ttu-id="88180-289">駕 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-289">Driver's Lics#</span></span>
- <span data-ttu-id="88180-290">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-290">Driver's Licence#</span></span>
- <span data-ttu-id="88180-291">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="88180-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="88180-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="88180-293">aaa</span><span class="sxs-lookup"><span data-stu-id="88180-293">aaa</span></span>
- <span data-ttu-id="88180-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="88180-294">DriverLicense</span></span>
- <span data-ttu-id="88180-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-295">DriverLicenses</span></span>
- <span data-ttu-id="88180-296">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-296">Driver License</span></span>
- <span data-ttu-id="88180-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-297">Driver Licenses</span></span>
- <span data-ttu-id="88180-298">執照</span><span class="sxs-lookup"><span data-stu-id="88180-298">DriversLicense</span></span>
- <span data-ttu-id="88180-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-299">DriversLicenses</span></span>
- <span data-ttu-id="88180-300">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-300">Drivers License</span></span>
- <span data-ttu-id="88180-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-301">Drivers Licenses</span></span>
- <span data-ttu-id="88180-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="88180-302">Driver'License</span></span>
- <span data-ttu-id="88180-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="88180-303">Driver'Licenses</span></span>
- <span data-ttu-id="88180-304">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-304">Driver' License</span></span>
- <span data-ttu-id="88180-305">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-305">Driver' Licenses</span></span>
- <span data-ttu-id="88180-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="88180-306">Driver'sLicense</span></span>
- <span data-ttu-id="88180-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-307">Driver'sLicenses</span></span>
- <span data-ttu-id="88180-308">駕照</span><span class="sxs-lookup"><span data-stu-id="88180-308">Driver's License</span></span>
- <span data-ttu-id="88180-309">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-309">Driver's Licenses</span></span>
- <span data-ttu-id="88180-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="88180-310">DriverLicense#</span></span>
- <span data-ttu-id="88180-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-311">DriverLicenses#</span></span>
- <span data-ttu-id="88180-312">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-312">Driver License#</span></span>
- <span data-ttu-id="88180-313">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-313">Driver Licenses#</span></span>
- <span data-ttu-id="88180-314">執照 #</span><span class="sxs-lookup"><span data-stu-id="88180-314">DriversLicense#</span></span>
- <span data-ttu-id="88180-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-315">DriversLicenses#</span></span>
- <span data-ttu-id="88180-316">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-316">Drivers License#</span></span>
- <span data-ttu-id="88180-317">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-317">Drivers Licenses#</span></span>
- <span data-ttu-id="88180-318">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="88180-318">Driver'License#</span></span>
- <span data-ttu-id="88180-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="88180-319">Driver'Licenses#</span></span>
- <span data-ttu-id="88180-320">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-320">Driver' License#</span></span>
- <span data-ttu-id="88180-321">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-321">Driver' Licenses#</span></span>
- <span data-ttu-id="88180-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="88180-322">Driver'sLicense#</span></span>
- <span data-ttu-id="88180-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="88180-324">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-324">Driver's License#</span></span>
- <span data-ttu-id="88180-325">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="88180-326">澳洲醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-327">Format</span><span class="sxs-lookup"><span data-stu-id="88180-327">Format</span></span>

<span data-ttu-id="88180-328">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-329">模式</span><span class="sxs-lookup"><span data-stu-id="88180-329">Pattern</span></span>

<span data-ttu-id="88180-330">10-11 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-330">10-11 digits:</span></span>
- <span data-ttu-id="88180-331">第一個數字是 2-6 的範圍內</span><span class="sxs-lookup"><span data-stu-id="88180-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="88180-332">第九個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="88180-333">第十個數字是簽發碼</span><span class="sxs-lookup"><span data-stu-id="88180-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="88180-334">第十一個數字 （選擇性） 是個人碼</span><span class="sxs-lookup"><span data-stu-id="88180-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-335">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-335">Checksum</span></span>

<span data-ttu-id="88180-336">是</span><span class="sxs-lookup"><span data-stu-id="88180-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-337">定義</span><span class="sxs-lookup"><span data-stu-id="88180-337">Definition</span></span>

<span data-ttu-id="88180-338">DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-339">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-340">找不到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="88180-341">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-341">The checksum passes.</span></span>

<span data-ttu-id="88180-342">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-343">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-344">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="88180-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="88180-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="88180-347">銀行帳戶詳細資料</span><span class="sxs-lookup"><span data-stu-id="88180-347">bank account details</span></span>
- <span data-ttu-id="88180-348">medicare 付款</span><span class="sxs-lookup"><span data-stu-id="88180-348">medicare payments</span></span>
- <span data-ttu-id="88180-349">抵押帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-349">mortgage account</span></span>
- <span data-ttu-id="88180-350">銀行付款</span><span class="sxs-lookup"><span data-stu-id="88180-350">bank payments</span></span>
- <span data-ttu-id="88180-351">資訊分支</span><span class="sxs-lookup"><span data-stu-id="88180-351">information branch</span></span>
- <span data-ttu-id="88180-352">信用卡貸款</span><span class="sxs-lookup"><span data-stu-id="88180-352">credit card loan</span></span>
- <span data-ttu-id="88180-353">人力服務部門</span><span class="sxs-lookup"><span data-stu-id="88180-353">department of human services</span></span>
- <span data-ttu-id="88180-354">本機服務</span><span class="sxs-lookup"><span data-stu-id="88180-354">local service</span></span>
- <span data-ttu-id="88180-355">medicare</span><span class="sxs-lookup"><span data-stu-id="88180-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="88180-356">澳洲護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-357">Format</span><span class="sxs-lookup"><span data-stu-id="88180-357">Format</span></span>

<span data-ttu-id="88180-358">字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="88180-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-359">模式</span><span class="sxs-lookup"><span data-stu-id="88180-359">Pattern</span></span>

<span data-ttu-id="88180-360">尾隨七位數字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-361">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-361">Checksum</span></span>

<span data-ttu-id="88180-362">否</span><span class="sxs-lookup"><span data-stu-id="88180-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-363">定義</span><span class="sxs-lookup"><span data-stu-id="88180-363">Definition</span></span>

<span data-ttu-id="88180-364">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-365">規則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-366">找不到來自 Keyword_passport 或 Keyword_australia_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="88180-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="88180-368">Keyword_passport</span></span>

- <span data-ttu-id="88180-369">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-369">Passport Number</span></span>
- <span data-ttu-id="88180-370">Passport 否</span><span class="sxs-lookup"><span data-stu-id="88180-370">Passport No</span></span>
- <span data-ttu-id="88180-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-371">Passport #</span></span>
- <span data-ttu-id="88180-372">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-372">Passport#</span></span>
- <span data-ttu-id="88180-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="88180-373">PassportID</span></span>
- <span data-ttu-id="88180-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="88180-374">Passportno</span></span>
- <span data-ttu-id="88180-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="88180-375">passportnumber</span></span>
- <span data-ttu-id="88180-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="88180-376">パスポート</span></span>
- <span data-ttu-id="88180-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="88180-377">パスポート番号</span></span>
- <span data-ttu-id="88180-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="88180-378">パスポートのNum</span></span>
- <span data-ttu-id="88180-379">パスポート #</span><span class="sxs-lookup"><span data-stu-id="88180-379">パスポート ＃</span></span> 
- <span data-ttu-id="88180-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="88180-380">Numéro de passeport</span></span>
- <span data-ttu-id="88180-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="88180-381">Passeport n °</span></span>
- <span data-ttu-id="88180-382">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="88180-382">Passeport Non</span></span>
- <span data-ttu-id="88180-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-383">Passeport #</span></span>
- <span data-ttu-id="88180-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-384">Passeport#</span></span>
- <span data-ttu-id="88180-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="88180-385">PasseportNon</span></span>
- <span data-ttu-id="88180-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="88180-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="88180-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="88180-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="88180-388">passport</span><span class="sxs-lookup"><span data-stu-id="88180-388">passport</span></span>
- <span data-ttu-id="88180-389">passport 詳細資料</span><span class="sxs-lookup"><span data-stu-id="88180-389">passport details</span></span>
- <span data-ttu-id="88180-390">immigration 和公民</span><span class="sxs-lookup"><span data-stu-id="88180-390">immigration and citizenship</span></span>
- <span data-ttu-id="88180-391">澳大利亞聯邦</span><span class="sxs-lookup"><span data-stu-id="88180-391">commonwealth of australia</span></span>
- <span data-ttu-id="88180-392">immigration 的部門</span><span class="sxs-lookup"><span data-stu-id="88180-392">department of immigration</span></span>
- <span data-ttu-id="88180-393">住家地址</span><span class="sxs-lookup"><span data-stu-id="88180-393">residential address</span></span>
- <span data-ttu-id="88180-394">immigration 和公民的部門</span><span class="sxs-lookup"><span data-stu-id="88180-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="88180-395">visa</span><span class="sxs-lookup"><span data-stu-id="88180-395">visa</span></span>
- <span data-ttu-id="88180-396">國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-396">national identity card</span></span>
- <span data-ttu-id="88180-397">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-397">passport number</span></span>
- <span data-ttu-id="88180-398">出差的文件</span><span class="sxs-lookup"><span data-stu-id="88180-398">travel document</span></span>
- <span data-ttu-id="88180-399">授權單位</span><span class="sxs-lookup"><span data-stu-id="88180-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="88180-400">澳洲稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="88180-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-401">Format</span><span class="sxs-lookup"><span data-stu-id="88180-401">Format</span></span>

<span data-ttu-id="88180-402">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="88180-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-403">模式</span><span class="sxs-lookup"><span data-stu-id="88180-403">Pattern</span></span>

<span data-ttu-id="88180-404">8-9 位數，通常會有空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="88180-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="88180-405">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-405">Three digits</span></span> 
- <span data-ttu-id="88180-406">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="88180-406">An optional space</span></span> 
- <span data-ttu-id="88180-407">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-407">Three digits</span></span> 
- <span data-ttu-id="88180-408">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="88180-408">An optional space</span></span> 
- <span data-ttu-id="88180-409">2-3 位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-410">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-410">Checksum</span></span>

<span data-ttu-id="88180-411">是</span><span class="sxs-lookup"><span data-stu-id="88180-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-412">定義</span><span class="sxs-lookup"><span data-stu-id="88180-412">Definition</span></span>

<span data-ttu-id="88180-413">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-414">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-415">找不到來自 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="88180-416">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="88180-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="88180-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="88180-419">澳洲商務號碼</span><span class="sxs-lookup"><span data-stu-id="88180-419">australian business number</span></span>
- <span data-ttu-id="88180-420">臨界稅率</span><span class="sxs-lookup"><span data-stu-id="88180-420">marginal tax rate</span></span>
- <span data-ttu-id="88180-421">medicare 募集</span><span class="sxs-lookup"><span data-stu-id="88180-421">medicare levy</span></span>
- <span data-ttu-id="88180-422">組合數</span><span class="sxs-lookup"><span data-stu-id="88180-422">portfolio number</span></span>
- <span data-ttu-id="88180-423">服務老手</span><span class="sxs-lookup"><span data-stu-id="88180-423">service veterans</span></span>
- <span data-ttu-id="88180-424">扣繳稅</span><span class="sxs-lookup"><span data-stu-id="88180-424">withholding tax</span></span>
- <span data-ttu-id="88180-425">個別的稅務傳回</span><span class="sxs-lookup"><span data-stu-id="88180-425">individual tax return</span></span>
- <span data-ttu-id="88180-426">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="88180-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="88180-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="88180-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="88180-428">00000000</span><span class="sxs-lookup"><span data-stu-id="88180-428">00000000</span></span>
- <span data-ttu-id="88180-429">11111111</span><span class="sxs-lookup"><span data-stu-id="88180-429">11111111</span></span>
- <span data-ttu-id="88180-430">22222222</span><span class="sxs-lookup"><span data-stu-id="88180-430">22222222</span></span>
- <span data-ttu-id="88180-431">33333333</span><span class="sxs-lookup"><span data-stu-id="88180-431">33333333</span></span>
- <span data-ttu-id="88180-432">44444444</span><span class="sxs-lookup"><span data-stu-id="88180-432">44444444</span></span>
- <span data-ttu-id="88180-433">55555555</span><span class="sxs-lookup"><span data-stu-id="88180-433">55555555</span></span>
- <span data-ttu-id="88180-434">66666666</span><span class="sxs-lookup"><span data-stu-id="88180-434">66666666</span></span>
- <span data-ttu-id="88180-435">77777777</span><span class="sxs-lookup"><span data-stu-id="88180-435">77777777</span></span>
- <span data-ttu-id="88180-436">88888888</span><span class="sxs-lookup"><span data-stu-id="88180-436">88888888</span></span>
- <span data-ttu-id="88180-437">99999999</span><span class="sxs-lookup"><span data-stu-id="88180-437">99999999</span></span>
- <span data-ttu-id="88180-438">000000000</span><span class="sxs-lookup"><span data-stu-id="88180-438">000000000</span></span>
- <span data-ttu-id="88180-439">111111111</span><span class="sxs-lookup"><span data-stu-id="88180-439">111111111</span></span>
- <span data-ttu-id="88180-440">222222222</span><span class="sxs-lookup"><span data-stu-id="88180-440">222222222</span></span>
- <span data-ttu-id="88180-441">333333333</span><span class="sxs-lookup"><span data-stu-id="88180-441">333333333</span></span>
- <span data-ttu-id="88180-442">444444444</span><span class="sxs-lookup"><span data-stu-id="88180-442">444444444</span></span>
- <span data-ttu-id="88180-443">555555555</span><span class="sxs-lookup"><span data-stu-id="88180-443">555555555</span></span>
- <span data-ttu-id="88180-444">666666666</span><span class="sxs-lookup"><span data-stu-id="88180-444">666666666</span></span>
- <span data-ttu-id="88180-445">777777777</span><span class="sxs-lookup"><span data-stu-id="88180-445">777777777</span></span>
- <span data-ttu-id="88180-446">888888888</span><span class="sxs-lookup"><span data-stu-id="88180-446">888888888</span></span>
- <span data-ttu-id="88180-447">999999999</span><span class="sxs-lookup"><span data-stu-id="88180-447">999999999</span></span>
- <span data-ttu-id="88180-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="88180-448">0000000000</span></span>
- <span data-ttu-id="88180-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="88180-449">1111111111</span></span>
- <span data-ttu-id="88180-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="88180-450">2222222222</span></span>
- <span data-ttu-id="88180-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="88180-451">3333333333</span></span>
- <span data-ttu-id="88180-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="88180-452">4444444444</span></span>
- <span data-ttu-id="88180-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="88180-453">5555555555</span></span>
- <span data-ttu-id="88180-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="88180-454">6666666666</span></span>
- <span data-ttu-id="88180-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="88180-455">7777777777</span></span>
- <span data-ttu-id="88180-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="88180-456">8888888888</span></span>
- <span data-ttu-id="88180-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="88180-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="88180-458">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="88180-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="88180-459">Format</span><span class="sxs-lookup"><span data-stu-id="88180-459">Format</span></span>

<span data-ttu-id="88180-460">將字串 「 DocumentDb 」 後面接著字元和下列模式中所述的字串。</span><span class="sxs-lookup"><span data-stu-id="88180-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-461">模式</span><span class="sxs-lookup"><span data-stu-id="88180-461">Pattern</span></span>

- <span data-ttu-id="88180-462">將字串 「 DocumentDb 」</span><span class="sxs-lookup"><span data-stu-id="88180-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="88180-463">3-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-464">大於符號 (>)、 等號 （=）、 引號 （"） 或單引號 （'）</span><span class="sxs-lookup"><span data-stu-id="88180-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="88180-465">或的任何組合 86 較低的大寫字母、 數字，轉寄斜線 （/） 或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="88180-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="88180-466">兩個等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-467">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-467">Checksum</span></span>

<span data-ttu-id="88180-468">否</span><span class="sxs-lookup"><span data-stu-id="88180-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-469">定義</span><span class="sxs-lookup"><span data-stu-id="88180-469">Definition</span></span>

<span data-ttu-id="88180-470">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-471">規則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-472">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-473">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-475">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-476">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-476">contoso</span></span>
- <span data-ttu-id="88180-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-477">fabrikam</span></span>
- <span data-ttu-id="88180-478">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-478">northwind</span></span>
- <span data-ttu-id="88180-479">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-479">sandbox</span></span>
- <span data-ttu-id="88180-480">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-480">onebox</span></span>
- <span data-ttu-id="88180-481">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-481">localhost</span></span>
- <span data-ttu-id="88180-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-482">127.0.0.1</span></span>
- <span data-ttu-id="88180-483">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-483">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-484">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-484">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="88180-485">Azure IAAS 資料庫連接字串和 Azure SQL 連線字串</span><span class="sxs-lookup"><span data-stu-id="88180-485">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="88180-486">Format</span><span class="sxs-lookup"><span data-stu-id="88180-486">Format</span></span>

<span data-ttu-id="88180-487">字串 「 伺服器 」、 「 伺服器 」 或 「 資料來源 」 後面加上字元和下列，模式中所述的字串包含字串 「 cloudapp.azure。<!--no-hyperlink-->com 」 或 「 cloudapp.azure。<!--no-hyperlink-->net 」 或 「 database.windows。<!--no-hyperlink-->net 」，以及 「 密碼 」 或 「 密碼 」 或 「 pwd 」 的字串。</span><span class="sxs-lookup"><span data-stu-id="88180-487">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.<!--no-hyperlink-->com" or "cloudapp.azure.<!--no-hyperlink-->net" or "database.windows.<!--no-hyperlink-->net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-488">模式</span><span class="sxs-lookup"><span data-stu-id="88180-488">Pattern</span></span>

- <span data-ttu-id="88180-489">字串 「 伺服器 」、 「 伺服器 」 或者 「 資料來源 」</span><span class="sxs-lookup"><span data-stu-id="88180-489">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="88180-490">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-490">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-491">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-491">An equal sign (=)</span></span>
- <span data-ttu-id="88180-492">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-492">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-493">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-493">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-494">將字串 「 cloudapp.azure。<!--no-hyperlink-->com 」、 「 cloudapp.azure。<!--no-hyperlink-->net 」，或 「 database.windows。<!--no-hyperlink-->net 」</span><span class="sxs-lookup"><span data-stu-id="88180-494">The string "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", or "database.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="88180-495">1-300 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-495">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-496">字串 「 密碼 」、 「 密碼 」 或者 「 pwd 」</span><span class="sxs-lookup"><span data-stu-id="88180-496">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="88180-497">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-498">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-498">An equal sign (=)</span></span>
- <span data-ttu-id="88180-499">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-499">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-500">不是以分號 （;） 的一或多個字元的引號 （"） 或單引號 （'）</span><span class="sxs-lookup"><span data-stu-id="88180-500">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="88180-501">分號 （;）、 引號 （"） 或單引號 （'）</span><span class="sxs-lookup"><span data-stu-id="88180-501">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-502">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-502">Checksum</span></span>

<span data-ttu-id="88180-503">否</span><span class="sxs-lookup"><span data-stu-id="88180-503">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-504">定義</span><span class="sxs-lookup"><span data-stu-id="88180-504">Definition</span></span>

<span data-ttu-id="88180-505">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-505">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-506">規則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-506">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-507">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-507">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-508">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-508">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-509">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-509">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-510">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-510">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-511">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-511">contoso</span></span>
- <span data-ttu-id="88180-512">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-512">fabrikam</span></span>
- <span data-ttu-id="88180-513">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-513">northwind</span></span>
- <span data-ttu-id="88180-514">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-514">sandbox</span></span>
- <span data-ttu-id="88180-515">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-515">onebox</span></span>
- <span data-ttu-id="88180-516">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-516">localhost</span></span>
- <span data-ttu-id="88180-517">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-517">127.0.0.1</span></span>
- <span data-ttu-id="88180-518">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-518">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-519">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-519">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="88180-520">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="88180-520">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="88180-521">Format</span><span class="sxs-lookup"><span data-stu-id="88180-521">Format</span></span>

<span data-ttu-id="88180-522">將字串 「 主機名稱 」 後面加上字元和下方，模式中所述的字串包含字串 「 azure 裝置。<!--no-hyperlink-->net 」 和 「 SharedAccessKey 」。</span><span class="sxs-lookup"><span data-stu-id="88180-522">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.<!--no-hyperlink-->net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-523">模式</span><span class="sxs-lookup"><span data-stu-id="88180-523">Pattern</span></span>

- <span data-ttu-id="88180-524">將字串 「 主機名稱 」</span><span class="sxs-lookup"><span data-stu-id="88180-524">The string "HostName"</span></span>
- <span data-ttu-id="88180-525">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-525">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-526">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-526">An equal sign (=)</span></span>
- <span data-ttu-id="88180-527">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-527">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-528">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-528">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-529">將字串 「 azure 裝置。<!--no-hyperlink-->net 」</span><span class="sxs-lookup"><span data-stu-id="88180-529">The string "azure-devices.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="88180-530">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-530">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-531">將字串 「 SharedAccessKey 」</span><span class="sxs-lookup"><span data-stu-id="88180-531">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="88180-532">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-532">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-533">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-533">An equal sign (=)</span></span>
- <span data-ttu-id="88180-534">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-534">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-535">或的任何組合 43 較低的大寫字母、 數字，轉寄斜線 （/） 或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="88180-535">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="88180-536">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-536">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-537">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-537">Checksum</span></span>

<span data-ttu-id="88180-538">否</span><span class="sxs-lookup"><span data-stu-id="88180-538">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-539">定義</span><span class="sxs-lookup"><span data-stu-id="88180-539">Definition</span></span>

<span data-ttu-id="88180-540">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-540">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-541">規則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-541">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-542">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-542">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-543">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-543">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-544">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-544">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-545">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-545">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-546">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-546">contoso</span></span>
- <span data-ttu-id="88180-547">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-547">fabrikam</span></span>
- <span data-ttu-id="88180-548">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-548">northwind</span></span>
- <span data-ttu-id="88180-549">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-549">sandbox</span></span>
- <span data-ttu-id="88180-550">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-550">onebox</span></span>
- <span data-ttu-id="88180-551">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-551">localhost</span></span>
- <span data-ttu-id="88180-552">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-552">127.0.0.1</span></span>
- <span data-ttu-id="88180-553">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-553">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-554">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-554">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="88180-555">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="88180-555">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="88180-556">Format</span><span class="sxs-lookup"><span data-stu-id="88180-556">Format</span></span>

<span data-ttu-id="88180-557">將字串 「 userpwd = 」 後面接著英數字元的字串。</span><span class="sxs-lookup"><span data-stu-id="88180-557">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-558">模式</span><span class="sxs-lookup"><span data-stu-id="88180-558">Pattern</span></span>

- <span data-ttu-id="88180-559">將字串 「 userpwd = 」</span><span class="sxs-lookup"><span data-stu-id="88180-559">The string "userpwd="</span></span>
- <span data-ttu-id="88180-560">60 小寫字母或數字的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-560">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="88180-561">引號 （"）</span><span class="sxs-lookup"><span data-stu-id="88180-561">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-562">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-562">Checksum</span></span>

<span data-ttu-id="88180-563">否</span><span class="sxs-lookup"><span data-stu-id="88180-563">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-564">定義</span><span class="sxs-lookup"><span data-stu-id="88180-564">Definition</span></span>

<span data-ttu-id="88180-565">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-565">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-566">規則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-566">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-567">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-567">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="88180-568">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-568">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-569">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-569">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-570">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-570">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-571">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-571">contoso</span></span>
- <span data-ttu-id="88180-572">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-572">fabrikam</span></span>
- <span data-ttu-id="88180-573">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-573">northwind</span></span>
- <span data-ttu-id="88180-574">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-574">sandbox</span></span>
- <span data-ttu-id="88180-575">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-575">onebox</span></span>
- <span data-ttu-id="88180-576">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-576">localhost</span></span>
- <span data-ttu-id="88180-577">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-577">127.0.0.1</span></span>
- <span data-ttu-id="88180-578">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-578">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-579">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-579">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="88180-580">Azure 意指快取的連接字串</span><span class="sxs-lookup"><span data-stu-id="88180-580">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="88180-581">Format</span><span class="sxs-lookup"><span data-stu-id="88180-581">Format</span></span>

<span data-ttu-id="88180-582">將字串 「 redis.cache.windows。<!--no-hyperlink-->net"後面加上字元和字串中的模式，如下所述包含字串 「 密碼 」 或 「 pwd 」。</span><span class="sxs-lookup"><span data-stu-id="88180-582">The string "redis.cache.windows.<!--no-hyperlink-->net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-583">模式</span><span class="sxs-lookup"><span data-stu-id="88180-583">Pattern</span></span>

- <span data-ttu-id="88180-584">將字串 「 redis.cache.windows。<!--no-hyperlink-->net 」</span><span class="sxs-lookup"><span data-stu-id="88180-584">The string "redis.cache.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="88180-585">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-585">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-586">字串 「 密碼 」 或者 「 pwd 」</span><span class="sxs-lookup"><span data-stu-id="88180-586">The string "password" or "pwd"</span></span>
- <span data-ttu-id="88180-587">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-587">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-588">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-588">An equal sign (=)</span></span>
- <span data-ttu-id="88180-589">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-589">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-590">43 較低或大寫字母、 數字的字元的任何組合反斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="88180-590">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="88180-591">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-591">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-592">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-592">Checksum</span></span>

<span data-ttu-id="88180-593">否</span><span class="sxs-lookup"><span data-stu-id="88180-593">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-594">定義</span><span class="sxs-lookup"><span data-stu-id="88180-594">Definition</span></span>

<span data-ttu-id="88180-595">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-596">規則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-596">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="88180-597">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-597">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-598">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-598">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-599">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-599">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-600">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-600">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-601">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-601">contoso</span></span>
- <span data-ttu-id="88180-602">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-602">fabrikam</span></span>
- <span data-ttu-id="88180-603">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-603">northwind</span></span>
- <span data-ttu-id="88180-604">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-604">sandbox</span></span>
- <span data-ttu-id="88180-605">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-605">onebox</span></span>
- <span data-ttu-id="88180-606">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-606">localhost</span></span>
- <span data-ttu-id="88180-607">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-607">127.0.0.1</span></span>
- <span data-ttu-id="88180-608">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-608">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-609">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-609">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="88180-610">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="88180-610">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="88180-611">Format</span><span class="sxs-lookup"><span data-stu-id="88180-611">Format</span></span>

<span data-ttu-id="88180-612">將字串 「 簽章 」 後面加上字元和下列模式中所述的字串。</span><span class="sxs-lookup"><span data-stu-id="88180-612">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-613">模式</span><span class="sxs-lookup"><span data-stu-id="88180-613">Pattern</span></span>

- <span data-ttu-id="88180-614">將字串 「 簽章 」</span><span class="sxs-lookup"><span data-stu-id="88180-614">The string "sig"</span></span>
- <span data-ttu-id="88180-615">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-615">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-616">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-616">An equal sign (=)</span></span>
- <span data-ttu-id="88180-617">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-617">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-618">較低或小寫字母、 數字或百分比符號 （%） 的 43-53 字元之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-618">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="88180-619">將字串 「 %3d 」</span><span class="sxs-lookup"><span data-stu-id="88180-619">The string "%3d"</span></span>
- <span data-ttu-id="88180-620">不是較低的大寫字母、 數字或百分比符號 （%） 的任何字元</span><span class="sxs-lookup"><span data-stu-id="88180-620">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-621">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-621">Checksum</span></span>

<span data-ttu-id="88180-622">否</span><span class="sxs-lookup"><span data-stu-id="88180-622">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-623">定義</span><span class="sxs-lookup"><span data-stu-id="88180-623">Definition</span></span>

<span data-ttu-id="88180-624">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-625">規則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-625">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="88180-626">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="88180-626">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="88180-627">Format</span><span class="sxs-lookup"><span data-stu-id="88180-627">Format</span></span>

<span data-ttu-id="88180-628">將字串 「 端點 」 後面加上字元和下方，模式中所述的字串包含字串 「 servicebus.windows。<!--no-hyperlink-->net 」 和 「 SharedAccesKey 」。</span><span class="sxs-lookup"><span data-stu-id="88180-628">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.<!--no-hyperlink-->net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-629">模式</span><span class="sxs-lookup"><span data-stu-id="88180-629">Pattern</span></span>

- <span data-ttu-id="88180-630">將字串 「 端點 」</span><span class="sxs-lookup"><span data-stu-id="88180-630">The string "EndPoint"</span></span>
- <span data-ttu-id="88180-631">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-631">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-632">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-632">An equal sign (=)</span></span>
- <span data-ttu-id="88180-633">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-633">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-634">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-634">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-635">將字串 「 servicebus.windows。<!--no-hyperlink-->net 」</span><span class="sxs-lookup"><span data-stu-id="88180-635">The string "servicebus.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="88180-636">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-636">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-637">將字串 「 SharedAccessKey 」</span><span class="sxs-lookup"><span data-stu-id="88180-637">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="88180-638">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-638">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-639">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-639">An equal sign (=)</span></span>
- <span data-ttu-id="88180-640">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-640">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-641">43 較低或大寫字母、 數字的字元的任何組合反斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="88180-641">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="88180-642">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-642">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-643">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-643">Checksum</span></span>

<span data-ttu-id="88180-644">否</span><span class="sxs-lookup"><span data-stu-id="88180-644">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-645">定義</span><span class="sxs-lookup"><span data-stu-id="88180-645">Definition</span></span>

<span data-ttu-id="88180-646">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-646">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-647">規則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-647">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="88180-648">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-648">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-649">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-649">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-650">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-650">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-651">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-651">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-652">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-652">contoso</span></span>
- <span data-ttu-id="88180-653">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-653">fabrikam</span></span>
- <span data-ttu-id="88180-654">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-654">northwind</span></span>
- <span data-ttu-id="88180-655">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-655">sandbox</span></span>
- <span data-ttu-id="88180-656">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-656">onebox</span></span>
- <span data-ttu-id="88180-657">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-657">localhost</span></span>
- <span data-ttu-id="88180-658">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-658">127.0.0.1</span></span>
- <span data-ttu-id="88180-659">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-659">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-660">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-660">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="88180-661">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="88180-661">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="88180-662">Format</span><span class="sxs-lookup"><span data-stu-id="88180-662">Format</span></span>

<span data-ttu-id="88180-663">將字串 「 DefaultEndpointsProtocol"後面加上字元和下方，模式中所述的字串包含字串 「 AccountKey 」 中。</span><span class="sxs-lookup"><span data-stu-id="88180-663">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-664">模式</span><span class="sxs-lookup"><span data-stu-id="88180-664">Pattern</span></span>

- <span data-ttu-id="88180-665">將字串 「 DefaultEndpointsProtocol 」</span><span class="sxs-lookup"><span data-stu-id="88180-665">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="88180-666">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-666">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-667">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-667">An equal sign (=)</span></span>
- <span data-ttu-id="88180-668">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-668">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-669">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-669">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-670">將字串 「 AccountKey 」</span><span class="sxs-lookup"><span data-stu-id="88180-670">The string "AccountKey"</span></span>
- <span data-ttu-id="88180-671">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-671">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-672">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-672">An equal sign (=)</span></span>
- <span data-ttu-id="88180-673">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="88180-673">0-2 whitespace characters</span></span>
- <span data-ttu-id="88180-674">較低或大寫字母、 數字，86 個字元的任何組合反斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="88180-674">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="88180-675">兩個等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-675">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-676">Checksum</span></span>

<span data-ttu-id="88180-677">否</span><span class="sxs-lookup"><span data-stu-id="88180-677">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-678">定義</span><span class="sxs-lookup"><span data-stu-id="88180-678">Definition</span></span>

<span data-ttu-id="88180-679">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-679">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-680">規則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-680">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-681">規則運算式 CEP_AzureEmulatorStorageAccountFilter**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-681">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="88180-682">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-682">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-683">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-683">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="88180-684">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="88180-684">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="88180-685">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-685">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="88180-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-687">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-687">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-688">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-688">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-689">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-689">contoso</span></span>
- <span data-ttu-id="88180-690">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-690">fabrikam</span></span>
- <span data-ttu-id="88180-691">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-691">northwind</span></span>
- <span data-ttu-id="88180-692">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-692">sandbox</span></span>
- <span data-ttu-id="88180-693">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-693">onebox</span></span>
- <span data-ttu-id="88180-694">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-694">localhost</span></span>
- <span data-ttu-id="88180-695">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-695">127.0.0.1</span></span>
- <span data-ttu-id="88180-696">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-696">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-697">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-697">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="88180-698">Azure 儲存體帳戶金鑰 （一般）</span><span class="sxs-lookup"><span data-stu-id="88180-698">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="88180-699">Format</span><span class="sxs-lookup"><span data-stu-id="88180-699">Format</span></span>

<span data-ttu-id="88180-700">或的任何組合 86 較低的大寫字母、 數字，正斜線 （/），加上加號 （+），前面或後面跟著字元下列模式中所述。</span><span class="sxs-lookup"><span data-stu-id="88180-700">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-701">模式</span><span class="sxs-lookup"><span data-stu-id="88180-701">Pattern</span></span>

- <span data-ttu-id="88180-702">0-1 的大於符號 (>)、 單引號 （'）、 等號 （=）、 引號 （"） 或數字符號 （#）</span><span class="sxs-lookup"><span data-stu-id="88180-702">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="88180-703">較低層或大寫 86 個字元的任何組合字母、 數字，正斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="88180-703">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="88180-704">兩個等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-704">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="88180-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-705">Checksum</span></span>

<span data-ttu-id="88180-706">否</span><span class="sxs-lookup"><span data-stu-id="88180-706">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-707">定義</span><span class="sxs-lookup"><span data-stu-id="88180-707">Definition</span></span>

<span data-ttu-id="88180-708">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-708">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-709">規則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-709">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="88180-710">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="88180-710">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-711">Format</span><span class="sxs-lookup"><span data-stu-id="88180-711">Format</span></span>

<span data-ttu-id="88180-712">11 位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="88180-712">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-713">模式</span><span class="sxs-lookup"><span data-stu-id="88180-713">Pattern</span></span>

<span data-ttu-id="88180-714">11 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="88180-714">11 digits plus delimiters:</span></span>
- <span data-ttu-id="88180-715">六位數和兩個句點 yy： 通話的格式。公釐。DD 的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-715">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="88180-716">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-716">A hyphen</span></span> 
- <span data-ttu-id="88180-717">三個連續數字 （奇數男生，偶數女生）</span><span class="sxs-lookup"><span data-stu-id="88180-717">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="88180-718">句點</span><span class="sxs-lookup"><span data-stu-id="88180-718">A period</span></span> 
- <span data-ttu-id="88180-719">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-719">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-720">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-720">Checksum</span></span>

<span data-ttu-id="88180-721">是</span><span class="sxs-lookup"><span data-stu-id="88180-721">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-722">定義</span><span class="sxs-lookup"><span data-stu-id="88180-722">Definition</span></span>

<span data-ttu-id="88180-723">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-723">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-724">函數 Func_belgium_national_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-724">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-725">找不到來自 Keyword_belgium_national_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-725">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="88180-726">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-726">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-727">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-727">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="88180-728">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="88180-728">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="88180-729">身分識別</span><span class="sxs-lookup"><span data-stu-id="88180-729">Identity</span></span>
- <span data-ttu-id="88180-730">註冊</span><span class="sxs-lookup"><span data-stu-id="88180-730">Registration</span></span>
- <span data-ttu-id="88180-731">識別</span><span class="sxs-lookup"><span data-stu-id="88180-731">Identification</span></span> 
- <span data-ttu-id="88180-732">ID</span><span class="sxs-lookup"><span data-stu-id="88180-732">ID</span></span> 
- <span data-ttu-id="88180-733">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="88180-733">Identiteitskaart</span></span>
- <span data-ttu-id="88180-734">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="88180-734">Registratie nummer</span></span> 
- <span data-ttu-id="88180-735">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="88180-735">Identificatie nummer</span></span> 
- <span data-ttu-id="88180-736">Identiteit</span><span class="sxs-lookup"><span data-stu-id="88180-736">Identiteit</span></span>
- <span data-ttu-id="88180-737">Registratie</span><span class="sxs-lookup"><span data-stu-id="88180-737">Registratie</span></span>
- <span data-ttu-id="88180-738">Identificatie</span><span class="sxs-lookup"><span data-stu-id="88180-738">Identificatie</span></span> 
- <span data-ttu-id="88180-739">相關 d'identité</span><span class="sxs-lookup"><span data-stu-id="88180-739">Carte d’identité</span></span> 
- <span data-ttu-id="88180-740">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="88180-740">numéro d'immatriculation</span></span>
- <span data-ttu-id="88180-741">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="88180-741">numéro d'identification</span></span>
- <span data-ttu-id="88180-742">identité</span><span class="sxs-lookup"><span data-stu-id="88180-742">identité</span></span> 
- <span data-ttu-id="88180-743">碑文</span><span class="sxs-lookup"><span data-stu-id="88180-743">inscription</span></span> 
- <span data-ttu-id="88180-744">Identifikation</span><span class="sxs-lookup"><span data-stu-id="88180-744">Identifikation</span></span>
- <span data-ttu-id="88180-745">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="88180-745">Identifizierung</span></span>
- <span data-ttu-id="88180-746">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-746">Identifikationsnummer</span></span>
- <span data-ttu-id="88180-747">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="88180-747">Personalausweis</span></span>
- <span data-ttu-id="88180-748">Registrierung</span><span class="sxs-lookup"><span data-stu-id="88180-748">Registrierung</span></span>
- <span data-ttu-id="88180-749">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-749">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="88180-750">巴西 Cpf 碼</span><span class="sxs-lookup"><span data-stu-id="88180-750">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-751">Format</span><span class="sxs-lookup"><span data-stu-id="88180-751">Format</span></span>

<span data-ttu-id="88180-752">11 位數包含檢查碼且可格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="88180-752">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-753">模式</span><span class="sxs-lookup"><span data-stu-id="88180-753">Pattern</span></span>

<span data-ttu-id="88180-754">格式：</span><span class="sxs-lookup"><span data-stu-id="88180-754">Formatted:</span></span>
- <span data-ttu-id="88180-755">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-755">Three digits</span></span> 
- <span data-ttu-id="88180-756">句點</span><span class="sxs-lookup"><span data-stu-id="88180-756">A period</span></span> 
- <span data-ttu-id="88180-757">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-757">Three digits</span></span> 
- <span data-ttu-id="88180-758">句點</span><span class="sxs-lookup"><span data-stu-id="88180-758">A period</span></span> 
- <span data-ttu-id="88180-759">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-759">Three digits</span></span> 
- <span data-ttu-id="88180-760">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-760">A hyphen</span></span> 
- <span data-ttu-id="88180-761">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-761">Two digits which are check digits</span></span>

<span data-ttu-id="88180-762">格式化：</span><span class="sxs-lookup"><span data-stu-id="88180-762">Unformatted:</span></span>
- <span data-ttu-id="88180-763">11 位數，最後二位數所在位置，請檢查位數</span><span class="sxs-lookup"><span data-stu-id="88180-763">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-764">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-764">Checksum</span></span>

<span data-ttu-id="88180-765">是</span><span class="sxs-lookup"><span data-stu-id="88180-765">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-766">定義</span><span class="sxs-lookup"><span data-stu-id="88180-766">Definition</span></span>

<span data-ttu-id="88180-767">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-767">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-768">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-768">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-769">找不到來自 Keyword_brazil_cpf 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-769">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="88180-770">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-770">The checksum passes.</span></span>

<span data-ttu-id="88180-771">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-772">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-772">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-773">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-773">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-774">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="88180-775">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="88180-775">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="88180-776">CPF</span><span class="sxs-lookup"><span data-stu-id="88180-776">CPF</span></span>
- <span data-ttu-id="88180-777">識別</span><span class="sxs-lookup"><span data-stu-id="88180-777">Identification</span></span>
- <span data-ttu-id="88180-778">註冊</span><span class="sxs-lookup"><span data-stu-id="88180-778">Registration</span></span>
- <span data-ttu-id="88180-779">收益</span><span class="sxs-lookup"><span data-stu-id="88180-779">Revenue</span></span>
- <span data-ttu-id="88180-780">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="88180-780">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="88180-781">Imposto</span><span class="sxs-lookup"><span data-stu-id="88180-781">Imposto</span></span> 
- <span data-ttu-id="88180-782">Identificação</span><span class="sxs-lookup"><span data-stu-id="88180-782">Identificação</span></span> 
- <span data-ttu-id="88180-783">Inscrição</span><span class="sxs-lookup"><span data-stu-id="88180-783">Inscrição</span></span> 
- <span data-ttu-id="88180-784">Receita</span><span class="sxs-lookup"><span data-stu-id="88180-784">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="88180-785">巴西法律實體號碼 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="88180-785">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="88180-786">Format</span><span class="sxs-lookup"><span data-stu-id="88180-786">Format</span></span>

<span data-ttu-id="88180-787">14 位數包含登記碼、 分支碼和檢查碼加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="88180-787">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-788">模式</span><span class="sxs-lookup"><span data-stu-id="88180-788">Pattern</span></span>
<span data-ttu-id="88180-789">14 位數，加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="88180-789">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="88180-790">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-790">Two digits</span></span> 
- <span data-ttu-id="88180-791">句點</span><span class="sxs-lookup"><span data-stu-id="88180-791">A period</span></span> 
- <span data-ttu-id="88180-792">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-792">Three digits</span></span> 
- <span data-ttu-id="88180-793">句點</span><span class="sxs-lookup"><span data-stu-id="88180-793">A period</span></span> 
- <span data-ttu-id="88180-794">三位數 （此前 8 位數為登記碼）</span><span class="sxs-lookup"><span data-stu-id="88180-794">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="88180-795">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="88180-795">A forward slash</span></span> 
- <span data-ttu-id="88180-796">四位數分支碼</span><span class="sxs-lookup"><span data-stu-id="88180-796">Four-digit branch number</span></span> 
- <span data-ttu-id="88180-797">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-797">A hyphen</span></span> 
- <span data-ttu-id="88180-798">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-798">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-799">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-799">Checksum</span></span>

<span data-ttu-id="88180-800">是</span><span class="sxs-lookup"><span data-stu-id="88180-800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-801">定義</span><span class="sxs-lookup"><span data-stu-id="88180-801">Definition</span></span>

<span data-ttu-id="88180-802">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-803">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-803">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-804">找不到來自 Keyword_brazil_cnpj 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-804">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="88180-805">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-805">The checksum passes.</span></span>

<span data-ttu-id="88180-806">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-807">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-807">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-808">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-808">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-809">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-809">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="88180-810">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="88180-810">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="88180-811">CNPJ</span><span class="sxs-lookup"><span data-stu-id="88180-811">CNPJ</span></span> 
- <span data-ttu-id="88180-812">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="88180-812">CNPJ/MF</span></span> 
- <span data-ttu-id="88180-813">CNPJ MF</span><span class="sxs-lookup"><span data-stu-id="88180-813">CNPJ-MF</span></span> 
- <span data-ttu-id="88180-814">法律實體的登錄，國際電話</span><span class="sxs-lookup"><span data-stu-id="88180-814">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="88180-815">納稅人登錄</span><span class="sxs-lookup"><span data-stu-id="88180-815">Taxpayers Registry</span></span> 
- <span data-ttu-id="88180-816">法律實體</span><span class="sxs-lookup"><span data-stu-id="88180-816">Legal entity</span></span> 
- <span data-ttu-id="88180-817">法律實體</span><span class="sxs-lookup"><span data-stu-id="88180-817">Legal entities</span></span> 
- <span data-ttu-id="88180-818">註冊狀態</span><span class="sxs-lookup"><span data-stu-id="88180-818">Registration Status</span></span> 
- <span data-ttu-id="88180-819">商務版</span><span class="sxs-lookup"><span data-stu-id="88180-819">Business</span></span> 
- <span data-ttu-id="88180-820">Company</span><span class="sxs-lookup"><span data-stu-id="88180-820">Company</span></span>
- <span data-ttu-id="88180-821">CNPJ</span><span class="sxs-lookup"><span data-stu-id="88180-821">CNPJ</span></span> 
- <span data-ttu-id="88180-822">Cadastro Nacional 斯坦 Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="88180-822">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="88180-823">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="88180-823">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="88180-824">CGC</span><span class="sxs-lookup"><span data-stu-id="88180-824">CGC</span></span> 
- <span data-ttu-id="88180-825">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="88180-825">Pessoa jurídica</span></span> 
- <span data-ttu-id="88180-826">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="88180-826">Pessoas jurídicas</span></span> 
- <span data-ttu-id="88180-827">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="88180-827">Situação cadastral</span></span> 
- <span data-ttu-id="88180-828">Inscrição</span><span class="sxs-lookup"><span data-stu-id="88180-828">Inscrição</span></span> 
- <span data-ttu-id="88180-829">Empresa</span><span class="sxs-lookup"><span data-stu-id="88180-829">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="88180-830">巴西國民身分證 (RG)</span><span class="sxs-lookup"><span data-stu-id="88180-830">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="88180-831">Format</span><span class="sxs-lookup"><span data-stu-id="88180-831">Format</span></span>

<span data-ttu-id="88180-832">Registro Geral （舊格式）： 九位數</span><span class="sxs-lookup"><span data-stu-id="88180-832">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="88180-833">Registro de Identidade (RIC) （新格式）： 11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-833">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-834">模式</span><span class="sxs-lookup"><span data-stu-id="88180-834">Pattern</span></span>

<span data-ttu-id="88180-835">Registro Geral （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="88180-835">Registro Geral (old format):</span></span>
- <span data-ttu-id="88180-836">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-836">Two digits</span></span> 
- <span data-ttu-id="88180-837">句點</span><span class="sxs-lookup"><span data-stu-id="88180-837">A period</span></span> 
- <span data-ttu-id="88180-838">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-838">Three digits</span></span> 
- <span data-ttu-id="88180-839">句點</span><span class="sxs-lookup"><span data-stu-id="88180-839">A period</span></span> 
- <span data-ttu-id="88180-840">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-840">Three digits</span></span> 
- <span data-ttu-id="88180-841">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-841">A hyphen</span></span> 
- <span data-ttu-id="88180-842">一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-842">One digit which is a check digit</span></span>

<span data-ttu-id="88180-843">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="88180-843">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="88180-844">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-844">10 digits</span></span> 
- <span data-ttu-id="88180-845">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-845">A hyphen</span></span> 
- <span data-ttu-id="88180-846">一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-846">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-847">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-847">Checksum</span></span>

<span data-ttu-id="88180-848">是</span><span class="sxs-lookup"><span data-stu-id="88180-848">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-849">定義</span><span class="sxs-lookup"><span data-stu-id="88180-849">Definition</span></span>

<span data-ttu-id="88180-850">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-850">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-851">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-851">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-852">找不到來自 Keyword_brazil_rg 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-852">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="88180-853">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-853">The checksum passes.</span></span>

<span data-ttu-id="88180-854">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-854">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-855">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-855">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-856">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-857">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-857">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="88180-858">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="88180-858">Keyword_brazil_rg</span></span>

<span data-ttu-id="88180-859">Cédula de identidade 身分證證 número de rregistro registro de Iidentidade registro geral RG （此關鍵字是區分大小寫） RIC （此關鍵字是區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-859">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="88180-860">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-860">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-861">Format</span><span class="sxs-lookup"><span data-stu-id="88180-861">Format</span></span>

<span data-ttu-id="88180-862">7 或 12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-862">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-863">模式</span><span class="sxs-lookup"><span data-stu-id="88180-863">Pattern</span></span>

<span data-ttu-id="88180-864">加拿大銀行帳戶號碼是 7 或 12 位數。</span><span class="sxs-lookup"><span data-stu-id="88180-864">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="88180-865">加拿大銀行帳戶交換號碼是：</span><span class="sxs-lookup"><span data-stu-id="88180-865">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="88180-866">五位數</span><span class="sxs-lookup"><span data-stu-id="88180-866">Five digits</span></span> 
- <span data-ttu-id="88180-867">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-867">A hyphen</span></span> 
- <span data-ttu-id="88180-868">三位數或</span><span class="sxs-lookup"><span data-stu-id="88180-868">Three digits OR</span></span>
- <span data-ttu-id="88180-869">零"0"</span><span class="sxs-lookup"><span data-stu-id="88180-869">A zero "0"</span></span> 
- <span data-ttu-id="88180-870">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-870">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-871">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-871">Checksum</span></span>

<span data-ttu-id="88180-872">否</span><span class="sxs-lookup"><span data-stu-id="88180-872">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-873">定義</span><span class="sxs-lookup"><span data-stu-id="88180-873">Definition</span></span>

<span data-ttu-id="88180-874">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-874">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-875">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-875">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-876">找不到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-876">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="88180-877">規則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-877">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="88180-878">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-878">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-879">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-879">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-880">找不到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-880">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-881">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-881">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="88180-882">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="88180-882">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="88180-883">加拿大節省債券</span><span class="sxs-lookup"><span data-stu-id="88180-883">canada savings bonds</span></span>
- <span data-ttu-id="88180-884">加拿大收益機構</span><span class="sxs-lookup"><span data-stu-id="88180-884">canada revenue agency</span></span>
- <span data-ttu-id="88180-885">加拿大金融機構</span><span class="sxs-lookup"><span data-stu-id="88180-885">canadian financial institution</span></span>
- <span data-ttu-id="88180-886">直接儲放表單</span><span class="sxs-lookup"><span data-stu-id="88180-886">direct deposit form</span></span>
- <span data-ttu-id="88180-887">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="88180-887">canadian citizen</span></span>
- <span data-ttu-id="88180-888">法律代表</span><span class="sxs-lookup"><span data-stu-id="88180-888">legal representative</span></span>
- <span data-ttu-id="88180-889">公證人類似公開</span><span class="sxs-lookup"><span data-stu-id="88180-889">notary public</span></span>
- <span data-ttu-id="88180-890">oaths 的專員</span><span class="sxs-lookup"><span data-stu-id="88180-890">commissioner for oaths</span></span>
- <span data-ttu-id="88180-891">子系照護權益</span><span class="sxs-lookup"><span data-stu-id="88180-891">child care benefit</span></span>
- <span data-ttu-id="88180-892">萬用子照護</span><span class="sxs-lookup"><span data-stu-id="88180-892">universal child care</span></span>
- <span data-ttu-id="88180-893">加拿大子稅務權益</span><span class="sxs-lookup"><span data-stu-id="88180-893">canada child tax benefit</span></span>
- <span data-ttu-id="88180-894">收入稅務權益</span><span class="sxs-lookup"><span data-stu-id="88180-894">income tax benefit</span></span>
- <span data-ttu-id="88180-895">協調的銷售稅務</span><span class="sxs-lookup"><span data-stu-id="88180-895">harmonized sales tax</span></span>
- <span data-ttu-id="88180-896">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="88180-896">social insurance number</span></span>
- <span data-ttu-id="88180-897">收入稅務退款</span><span class="sxs-lookup"><span data-stu-id="88180-897">income tax refund</span></span>
- <span data-ttu-id="88180-898">子系稅務權益</span><span class="sxs-lookup"><span data-stu-id="88180-898">child tax benefit</span></span>
- <span data-ttu-id="88180-899">就付款</span><span class="sxs-lookup"><span data-stu-id="88180-899">territorial payments</span></span>
- <span data-ttu-id="88180-900">機構數目</span><span class="sxs-lookup"><span data-stu-id="88180-900">institution number</span></span>
- <span data-ttu-id="88180-901">儲放要求</span><span class="sxs-lookup"><span data-stu-id="88180-901">deposit request</span></span>
- <span data-ttu-id="88180-902">銀行業資訊</span><span class="sxs-lookup"><span data-stu-id="88180-902">banking information</span></span>
- <span data-ttu-id="88180-903">直接儲放</span><span class="sxs-lookup"><span data-stu-id="88180-903">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="88180-904">加拿大駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-904">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-905">Format</span><span class="sxs-lookup"><span data-stu-id="88180-905">Format</span></span>

<span data-ttu-id="88180-906">省分而異</span><span class="sxs-lookup"><span data-stu-id="88180-906">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-907">模式</span><span class="sxs-lookup"><span data-stu-id="88180-907">Pattern</span></span>

<span data-ttu-id="88180-908">不同模式 Alberta、 不列顛哥倫比亞、 Manitoba、 New Brunswick、 Newfoundland/Labrador、 Nova Scotia、 安大略省、 Prince Edward 島、 Quebec 和薩克其萬</span><span class="sxs-lookup"><span data-stu-id="88180-908">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-909">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-909">Checksum</span></span>

<span data-ttu-id="88180-910">否</span><span class="sxs-lookup"><span data-stu-id="88180-910">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-911">定義</span><span class="sxs-lookup"><span data-stu-id="88180-911">Definition</span></span>

<span data-ttu-id="88180-912">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-913">函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-913">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-914">找到來自於 Keyword_ [province_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-914">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="88180-915">找不到來自 Keyword_canada_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-915">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-916">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-916">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="88180-917">於 Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="88180-917">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="88180-918">省分縮寫，例如 AB</span><span class="sxs-lookup"><span data-stu-id="88180-918">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="88180-919">省分名稱，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="88180-919">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="88180-920">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="88180-920">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="88180-921">DL</span><span class="sxs-lookup"><span data-stu-id="88180-921">DL</span></span>
- <span data-ttu-id="88180-922">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="88180-922">DLS</span></span>
- <span data-ttu-id="88180-923">CDL</span><span class="sxs-lookup"><span data-stu-id="88180-923">CDL</span></span>
- <span data-ttu-id="88180-924">CDLS</span><span class="sxs-lookup"><span data-stu-id="88180-924">CDLS</span></span>
- <span data-ttu-id="88180-925">DriverLic</span><span class="sxs-lookup"><span data-stu-id="88180-925">DriverLic</span></span>
- <span data-ttu-id="88180-926">DriverLics</span><span class="sxs-lookup"><span data-stu-id="88180-926">DriverLics</span></span>
- <span data-ttu-id="88180-927">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="88180-927">DriverLicense</span></span>
- <span data-ttu-id="88180-928">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-928">DriverLicenses</span></span>
- <span data-ttu-id="88180-929">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="88180-929">DriverLicence</span></span>
- <span data-ttu-id="88180-930">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="88180-930">DriverLicences</span></span>
- <span data-ttu-id="88180-931">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-931">Driver Lic</span></span>
- <span data-ttu-id="88180-932">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-932">Driver Lics</span></span>
- <span data-ttu-id="88180-933">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-933">Driver License</span></span>
- <span data-ttu-id="88180-934">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-934">Driver Licenses</span></span>
- <span data-ttu-id="88180-935">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-935">Driver Licence</span></span>
- <span data-ttu-id="88180-936">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-936">Driver Licences</span></span>
- <span data-ttu-id="88180-937">DriversLic</span><span class="sxs-lookup"><span data-stu-id="88180-937">DriversLic</span></span>
- <span data-ttu-id="88180-938">DriversLics</span><span class="sxs-lookup"><span data-stu-id="88180-938">DriversLics</span></span>
- <span data-ttu-id="88180-939">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="88180-939">DriversLicence</span></span>
- <span data-ttu-id="88180-940">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="88180-940">DriversLicences</span></span>
- <span data-ttu-id="88180-941">執照</span><span class="sxs-lookup"><span data-stu-id="88180-941">DriversLicense</span></span>
- <span data-ttu-id="88180-942">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-942">DriversLicenses</span></span>
- <span data-ttu-id="88180-943">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-943">Drivers Lic</span></span>
- <span data-ttu-id="88180-944">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-944">Drivers Lics</span></span>
- <span data-ttu-id="88180-945">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-945">Drivers License</span></span>
- <span data-ttu-id="88180-946">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-946">Drivers Licenses</span></span>
- <span data-ttu-id="88180-947">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-947">Drivers Licence</span></span>
- <span data-ttu-id="88180-948">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-948">Drivers Licences</span></span>
- <span data-ttu-id="88180-949">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="88180-949">Driver'Lic</span></span>
- <span data-ttu-id="88180-950">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="88180-950">Driver'Lics</span></span>
- <span data-ttu-id="88180-951">Driver'License</span><span class="sxs-lookup"><span data-stu-id="88180-951">Driver'License</span></span>
- <span data-ttu-id="88180-952">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="88180-952">Driver'Licenses</span></span>
- <span data-ttu-id="88180-953">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="88180-953">Driver'Licence</span></span>
- <span data-ttu-id="88180-954">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="88180-954">Driver'Licences</span></span>
- <span data-ttu-id="88180-955">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="88180-955">Driver' Lic</span></span>
- <span data-ttu-id="88180-956">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="88180-956">Driver' Lics</span></span>
- <span data-ttu-id="88180-957">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-957">Driver' License</span></span>
- <span data-ttu-id="88180-958">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-958">Driver' Licenses</span></span>
- <span data-ttu-id="88180-959">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-959">Driver' Licence</span></span>
- <span data-ttu-id="88180-960">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-960">Driver' Licences</span></span>
- <span data-ttu-id="88180-961">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="88180-961">Driver'sLic</span></span>
- <span data-ttu-id="88180-962">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="88180-962">Driver'sLics</span></span>
- <span data-ttu-id="88180-963">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="88180-963">Driver'sLicense</span></span>
- <span data-ttu-id="88180-964">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-964">Driver'sLicenses</span></span>
- <span data-ttu-id="88180-965">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="88180-965">Driver'sLicence</span></span>
- <span data-ttu-id="88180-966">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="88180-966">Driver'sLicences</span></span>
- <span data-ttu-id="88180-967">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-967">Driver's Lic</span></span>
- <span data-ttu-id="88180-968">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-968">Driver's Lics</span></span>
- <span data-ttu-id="88180-969">駕照</span><span class="sxs-lookup"><span data-stu-id="88180-969">Driver's License</span></span>
- <span data-ttu-id="88180-970">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-970">Driver's Licenses</span></span>
- <span data-ttu-id="88180-971">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-971">Driver's Licence</span></span>
- <span data-ttu-id="88180-972">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-972">Driver's Licences</span></span>
- <span data-ttu-id="88180-973">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="88180-973">Permis de Conduire</span></span>
- <span data-ttu-id="88180-974">id</span><span class="sxs-lookup"><span data-stu-id="88180-974">id</span></span>
- <span data-ttu-id="88180-975">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-975">ids</span></span>
- <span data-ttu-id="88180-976">idcard 數目</span><span class="sxs-lookup"><span data-stu-id="88180-976">idcard number</span></span>
- <span data-ttu-id="88180-977">idcard 數字</span><span class="sxs-lookup"><span data-stu-id="88180-977">idcard numbers</span></span>
- <span data-ttu-id="88180-978">idcard #</span><span class="sxs-lookup"><span data-stu-id="88180-978">idcard #</span></span>
- <span data-ttu-id="88180-979">idcard #s</span><span class="sxs-lookup"><span data-stu-id="88180-979">idcard #s</span></span>
- <span data-ttu-id="88180-980">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="88180-980">idcard card</span></span>
- <span data-ttu-id="88180-981">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="88180-981">idcard cards</span></span>
- <span data-ttu-id="88180-982">idcard</span><span class="sxs-lookup"><span data-stu-id="88180-982">idcard</span></span>
- <span data-ttu-id="88180-983">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-983">identification number</span></span>
- <span data-ttu-id="88180-984">識別數字</span><span class="sxs-lookup"><span data-stu-id="88180-984">identification numbers</span></span>
- <span data-ttu-id="88180-985">識別 #</span><span class="sxs-lookup"><span data-stu-id="88180-985">identification #</span></span>
- <span data-ttu-id="88180-986">識別 #s</span><span class="sxs-lookup"><span data-stu-id="88180-986">identification #s</span></span>
- <span data-ttu-id="88180-987">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-987">identification card</span></span>
- <span data-ttu-id="88180-988">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-988">identification cards</span></span>
- <span data-ttu-id="88180-989">識別</span><span class="sxs-lookup"><span data-stu-id="88180-989">identification</span></span> 
- <span data-ttu-id="88180-990">DL #</span><span class="sxs-lookup"><span data-stu-id="88180-990">DL#</span></span>
- <span data-ttu-id="88180-991">DL #</span><span class="sxs-lookup"><span data-stu-id="88180-991">DLS#</span></span> 
- <span data-ttu-id="88180-992">CDL #</span><span class="sxs-lookup"><span data-stu-id="88180-992">CDL#</span></span> 
- <span data-ttu-id="88180-993">CDLS #</span><span class="sxs-lookup"><span data-stu-id="88180-993">CDLS#</span></span> 
- <span data-ttu-id="88180-994">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="88180-994">DriverLic#</span></span> 
- <span data-ttu-id="88180-995">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="88180-995">DriverLics#</span></span> 
- <span data-ttu-id="88180-996">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="88180-996">DriverLicense#</span></span> 
- <span data-ttu-id="88180-997">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-997">DriverLicenses#</span></span> 
- <span data-ttu-id="88180-998">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="88180-998">DriverLicence#</span></span> 
- <span data-ttu-id="88180-999">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="88180-999">DriverLicences#</span></span> 
- <span data-ttu-id="88180-1000">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-1000">Driver Lic#</span></span>
- <span data-ttu-id="88180-1001">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-1001">Driver Lics#</span></span> 
- <span data-ttu-id="88180-1002">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1002">Driver License#</span></span> 
- <span data-ttu-id="88180-1003">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1003">Driver Licenses#</span></span> 
- <span data-ttu-id="88180-1004">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1004">Driver License#</span></span> 
- <span data-ttu-id="88180-1005">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1005">Driver Licences#</span></span> 
- <span data-ttu-id="88180-1006">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="88180-1006">DriversLic#</span></span> 
- <span data-ttu-id="88180-1007">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="88180-1007">DriversLics#</span></span> 
- <span data-ttu-id="88180-1008">執照 #</span><span class="sxs-lookup"><span data-stu-id="88180-1008">DriversLicense#</span></span> 
- <span data-ttu-id="88180-1009">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-1009">DriversLicenses#</span></span> 
- <span data-ttu-id="88180-1010">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="88180-1010">DriversLicence#</span></span> 
- <span data-ttu-id="88180-1011">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="88180-1011">DriversLicences#</span></span> 
- <span data-ttu-id="88180-1012">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-1012">Drivers Lic#</span></span> 
- <span data-ttu-id="88180-1013">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-1013">Drivers Lics#</span></span> 
- <span data-ttu-id="88180-1014">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1014">Drivers License#</span></span> 
- <span data-ttu-id="88180-1015">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1015">Drivers Licenses#</span></span> 
- <span data-ttu-id="88180-1016">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1016">Drivers Licence#</span></span> 
- <span data-ttu-id="88180-1017">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1017">Drivers Licences#</span></span> 
- <span data-ttu-id="88180-1018">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-1018">Driver'Lic#</span></span> 
- <span data-ttu-id="88180-1019">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-1019">Driver'Lics#</span></span> 
- <span data-ttu-id="88180-1020">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="88180-1020">Driver'License#</span></span> 
- <span data-ttu-id="88180-1021">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="88180-1021">Driver'Licenses#</span></span> 
- <span data-ttu-id="88180-1022">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="88180-1022">Driver'Licence#</span></span> 
- <span data-ttu-id="88180-1023">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="88180-1023">Driver'Licences#</span></span> 
- <span data-ttu-id="88180-1024">驅動程式 ' Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-1024">Driver' Lic#</span></span> 
- <span data-ttu-id="88180-1025">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-1025">Driver' Lics#</span></span> 
- <span data-ttu-id="88180-1026">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1026">Driver' License#</span></span> 
- <span data-ttu-id="88180-1027">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1027">Driver' Licenses#</span></span> 
- <span data-ttu-id="88180-1028">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1028">Driver' Licence#</span></span> 
- <span data-ttu-id="88180-1029">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1029">Driver' Licences#</span></span> 
- <span data-ttu-id="88180-1030">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="88180-1030">Driver'sLic#</span></span> 
- <span data-ttu-id="88180-1031">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="88180-1031">Driver'sLics#</span></span> 
- <span data-ttu-id="88180-1032">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="88180-1032">Driver'sLicense#</span></span> 
- <span data-ttu-id="88180-1033">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-1033">Driver'sLicenses#</span></span> 
- <span data-ttu-id="88180-1034">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="88180-1034">Driver'sLicence#</span></span> 
- <span data-ttu-id="88180-1035">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="88180-1035">Driver'sLicences#</span></span> 
- <span data-ttu-id="88180-1036">駕 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-1036">Driver's Lic#</span></span> 
- <span data-ttu-id="88180-1037">駕 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-1037">Driver's Lics#</span></span> 
- <span data-ttu-id="88180-1038">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1038">Driver's License#</span></span> 
- <span data-ttu-id="88180-1039">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1039">Driver's Licenses#</span></span> 
- <span data-ttu-id="88180-1040">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1040">Driver's Licence#</span></span> 
- <span data-ttu-id="88180-1041">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-1041">Driver's Licences#</span></span> 
- <span data-ttu-id="88180-1042">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="88180-1042">Permis de Conduire#</span></span> 
- <span data-ttu-id="88180-1043">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="88180-1043">id#</span></span> 
- <span data-ttu-id="88180-1044">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="88180-1044">ids#</span></span> 
- <span data-ttu-id="88180-1045">idcard 卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-1045">idcard card#</span></span> 
- <span data-ttu-id="88180-1046">idcard 卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-1046">idcard cards#</span></span> 
- <span data-ttu-id="88180-1047">idcard #</span><span class="sxs-lookup"><span data-stu-id="88180-1047">idcard#</span></span> 
- <span data-ttu-id="88180-1048">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-1048">identification card#</span></span> 
- <span data-ttu-id="88180-1049">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-1049">identification cards#</span></span> 
- <span data-ttu-id="88180-1050">識別 #</span><span class="sxs-lookup"><span data-stu-id="88180-1050">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="88180-1051">加拿大健保號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1051">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1052">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1052">Format</span></span>

<span data-ttu-id="88180-1053">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1053">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1054">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1054">Pattern</span></span>

<span data-ttu-id="88180-1055">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1055">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1056">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1056">Checksum</span></span>

<span data-ttu-id="88180-1057">否</span><span class="sxs-lookup"><span data-stu-id="88180-1057">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1058">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1058">Definition</span></span>

<span data-ttu-id="88180-1059">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1059">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1060">規則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1060">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1061">找不到來自 Keyword_canada_health_service_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1061">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1062">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1062">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="88180-1063">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="88180-1063">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="88180-1064">個人健康數目</span><span class="sxs-lookup"><span data-stu-id="88180-1064">personal health number</span></span>
- <span data-ttu-id="88180-1065">病患資訊</span><span class="sxs-lookup"><span data-stu-id="88180-1065">patient information</span></span>
- <span data-ttu-id="88180-1066">健康服務</span><span class="sxs-lookup"><span data-stu-id="88180-1066">health services</span></span>
- <span data-ttu-id="88180-1067">speciality 服務</span><span class="sxs-lookup"><span data-stu-id="88180-1067">speciality services</span></span>
- <span data-ttu-id="88180-1068">汽車意外</span><span class="sxs-lookup"><span data-stu-id="88180-1068">automobile accident</span></span>
- <span data-ttu-id="88180-1069">病患醫院</span><span class="sxs-lookup"><span data-stu-id="88180-1069">patient hospital</span></span>
- <span data-ttu-id="88180-1070">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="88180-1070">psychiatrist</span></span>
- <span data-ttu-id="88180-1071">工作者補償</span><span class="sxs-lookup"><span data-stu-id="88180-1071">workers compensation</span></span>
- <span data-ttu-id="88180-1072">disability</span><span class="sxs-lookup"><span data-stu-id="88180-1072">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="88180-1073">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1073">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1074">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1074">Format</span></span>

<span data-ttu-id="88180-1075">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="88180-1075">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1076">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1076">Pattern</span></span>

<span data-ttu-id="88180-1077">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="88180-1077">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1078">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1078">Checksum</span></span>

<span data-ttu-id="88180-1079">否</span><span class="sxs-lookup"><span data-stu-id="88180-1079">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1080">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1080">Definition</span></span>

<span data-ttu-id="88180-1081">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1081">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1082">規則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1082">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1083">找到來自於 Keyword_canada_passport_number 或 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1083">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1084">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1084">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="88180-1085">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="88180-1085">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="88180-1086">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="88180-1086">canadian citizenship</span></span>
- <span data-ttu-id="88180-1087">加拿大護照</span><span class="sxs-lookup"><span data-stu-id="88180-1087">canadian passport</span></span>
- <span data-ttu-id="88180-1088">passport 應用程式</span><span class="sxs-lookup"><span data-stu-id="88180-1088">passport application</span></span>
- <span data-ttu-id="88180-1089">passport 相片</span><span class="sxs-lookup"><span data-stu-id="88180-1089">passport photos</span></span>
- <span data-ttu-id="88180-1090">認證轉譯器</span><span class="sxs-lookup"><span data-stu-id="88180-1090">certified translator</span></span>
- <span data-ttu-id="88180-1091">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="88180-1091">canadian citizens</span></span>
- <span data-ttu-id="88180-1092">處理時間</span><span class="sxs-lookup"><span data-stu-id="88180-1092">processing times</span></span>
- <span data-ttu-id="88180-1093">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="88180-1093">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="88180-1094">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="88180-1094">Keyword_passport</span></span>

- <span data-ttu-id="88180-1095">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1095">Passport Number</span></span>
- <span data-ttu-id="88180-1096">Passport 否</span><span class="sxs-lookup"><span data-stu-id="88180-1096">Passport No</span></span>
- <span data-ttu-id="88180-1097">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-1097">Passport #</span></span>
- <span data-ttu-id="88180-1098">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-1098">Passport#</span></span>
- <span data-ttu-id="88180-1099">PassportID</span><span class="sxs-lookup"><span data-stu-id="88180-1099">PassportID</span></span>
- <span data-ttu-id="88180-1100">Passportno</span><span class="sxs-lookup"><span data-stu-id="88180-1100">Passportno</span></span>
- <span data-ttu-id="88180-1101">passportnumber</span><span class="sxs-lookup"><span data-stu-id="88180-1101">passportnumber</span></span>
- <span data-ttu-id="88180-1102">パスポート</span><span class="sxs-lookup"><span data-stu-id="88180-1102">パスポート</span></span>
- <span data-ttu-id="88180-1103">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="88180-1103">パスポート番号</span></span>
- <span data-ttu-id="88180-1104">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="88180-1104">パスポートのNum</span></span>
- <span data-ttu-id="88180-1105">パスポート #</span><span class="sxs-lookup"><span data-stu-id="88180-1105">パスポート＃</span></span>
- <span data-ttu-id="88180-1106">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="88180-1106">Numéro de passeport</span></span>
- <span data-ttu-id="88180-1107">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="88180-1107">Passeport n °</span></span>
- <span data-ttu-id="88180-1108">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="88180-1108">Passeport Non</span></span>
- <span data-ttu-id="88180-1109">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-1109">Passeport #</span></span>
- <span data-ttu-id="88180-1110">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-1110">Passeport#</span></span>
- <span data-ttu-id="88180-1111">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="88180-1111">PasseportNon</span></span>
- <span data-ttu-id="88180-1112">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="88180-1112">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="88180-1113">加拿大個人健康身分識別號碼 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="88180-1113">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-1114">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1114">Format</span></span>

<span data-ttu-id="88180-1115">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-1115">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1116">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1116">Pattern</span></span>

<span data-ttu-id="88180-1117">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-1117">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1118">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1118">Checksum</span></span>

<span data-ttu-id="88180-1119">否</span><span class="sxs-lookup"><span data-stu-id="88180-1119">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1120">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1120">Definition</span></span>

<span data-ttu-id="88180-1121">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 規則運算式 Regex_canada_phin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-1122">找到來自於 Keyword_canada_phin 或 keyword_canada_provinces 的關鍵字，至少有兩個關鍵字..</span><span class="sxs-lookup"><span data-stu-id="88180-1122">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1123">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="88180-1124">於 Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="88180-1124">Keyword_canada_phin</span></span>

- <span data-ttu-id="88180-1125">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1125">social insurance number</span></span>
- <span data-ttu-id="88180-1126">健康資訊法案</span><span class="sxs-lookup"><span data-stu-id="88180-1126">health information act</span></span>
- <span data-ttu-id="88180-1127">收入稅務資訊</span><span class="sxs-lookup"><span data-stu-id="88180-1127">income tax information</span></span>
- <span data-ttu-id="88180-1128">馬健康情況</span><span class="sxs-lookup"><span data-stu-id="88180-1128">manitoba health</span></span>
- <span data-ttu-id="88180-1129">健康情況註冊</span><span class="sxs-lookup"><span data-stu-id="88180-1129">health registration</span></span>
- <span data-ttu-id="88180-1130">解決方法購買</span><span class="sxs-lookup"><span data-stu-id="88180-1130">prescription purchases</span></span>
- <span data-ttu-id="88180-1131">權益合格</span><span class="sxs-lookup"><span data-stu-id="88180-1131">benefit eligibility</span></span>
- <span data-ttu-id="88180-1132">個人健康情況</span><span class="sxs-lookup"><span data-stu-id="88180-1132">personal health</span></span>
- <span data-ttu-id="88180-1133">電源的律師</span><span class="sxs-lookup"><span data-stu-id="88180-1133">power of attorney</span></span>
- <span data-ttu-id="88180-1134">登記號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1134">registration number</span></span>
- <span data-ttu-id="88180-1135">個人健康數目</span><span class="sxs-lookup"><span data-stu-id="88180-1135">personal health number</span></span>
- <span data-ttu-id="88180-1136">從業員推薦</span><span class="sxs-lookup"><span data-stu-id="88180-1136">practitioner referral</span></span>
- <span data-ttu-id="88180-1137">同等重要專業版</span><span class="sxs-lookup"><span data-stu-id="88180-1137">wellness professional</span></span>
- <span data-ttu-id="88180-1138">病患推薦</span><span class="sxs-lookup"><span data-stu-id="88180-1138">patient referral</span></span>
- <span data-ttu-id="88180-1139">健康狀況和同等重要</span><span class="sxs-lookup"><span data-stu-id="88180-1139">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="88180-1140">Keyword_canada_provinces 的關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1140">Keyword_canada_provinces</span></span>

- <span data-ttu-id="88180-1141">努勒維特</span><span class="sxs-lookup"><span data-stu-id="88180-1141">Nunavut</span></span>
- <span data-ttu-id="88180-1142">魁北克</span><span class="sxs-lookup"><span data-stu-id="88180-1142">Quebec</span></span>
- <span data-ttu-id="88180-1143">西北地區</span><span class="sxs-lookup"><span data-stu-id="88180-1143">Northwest Territories</span></span>
- <span data-ttu-id="88180-1144">安大略省</span><span class="sxs-lookup"><span data-stu-id="88180-1144">Ontario</span></span>
- <span data-ttu-id="88180-1145">不列顛哥倫比亞</span><span class="sxs-lookup"><span data-stu-id="88180-1145">British Columbia</span></span>
- <span data-ttu-id="88180-1146">Alberta</span><span class="sxs-lookup"><span data-stu-id="88180-1146">Alberta</span></span>
- <span data-ttu-id="88180-1147">薩克其萬</span><span class="sxs-lookup"><span data-stu-id="88180-1147">Saskatchewan</span></span>
- <span data-ttu-id="88180-1148">馬</span><span class="sxs-lookup"><span data-stu-id="88180-1148">Manitoba</span></span>
- <span data-ttu-id="88180-1149">Yukon</span><span class="sxs-lookup"><span data-stu-id="88180-1149">Yukon</span></span>
- <span data-ttu-id="88180-1150">紐芬蘭和 Labrador</span><span class="sxs-lookup"><span data-stu-id="88180-1150">Newfoundland and Labrador</span></span>
- <span data-ttu-id="88180-1151">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="88180-1151">New Brunswick</span></span>
- <span data-ttu-id="88180-1152">斯科</span><span class="sxs-lookup"><span data-stu-id="88180-1152">Nova Scotia</span></span>
- <span data-ttu-id="88180-1153">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="88180-1153">Prince Edward Island</span></span>
- <span data-ttu-id="88180-1154">加拿大</span><span class="sxs-lookup"><span data-stu-id="88180-1154">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="88180-1155">加拿大社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1155">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1156">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1156">Format</span></span>

<span data-ttu-id="88180-1157">使用選擇性連字號或空格的九位數</span><span class="sxs-lookup"><span data-stu-id="88180-1157">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1158">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1158">Pattern</span></span>

<span data-ttu-id="88180-1159">格式：</span><span class="sxs-lookup"><span data-stu-id="88180-1159">Formatted:</span></span>
- <span data-ttu-id="88180-1160">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-1160">Three digits</span></span> 
- <span data-ttu-id="88180-1161">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="88180-1161">A hyphen or space</span></span> 
- <span data-ttu-id="88180-1162">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-1162">Three digits</span></span> 
- <span data-ttu-id="88180-1163">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="88180-1163">A hyphen or space</span></span> 
- <span data-ttu-id="88180-1164">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-1164">Three digits</span></span>

<span data-ttu-id="88180-1165">未格式化： 九位數</span><span class="sxs-lookup"><span data-stu-id="88180-1165">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1166">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1166">Checksum</span></span>

<span data-ttu-id="88180-1167">是</span><span class="sxs-lookup"><span data-stu-id="88180-1167">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1168">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1168">Definition</span></span>

<span data-ttu-id="88180-1169">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1169">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1170">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1170">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1171">至少兩個以下的任意組合：</span><span class="sxs-lookup"><span data-stu-id="88180-1171">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="88180-1172">找不到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1172">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="88180-1173">找不到來自 Keyword_sin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1173">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="88180-1174">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-1174">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="88180-1175">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1175">The checksum passes.</span></span>

<span data-ttu-id="88180-1176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1177">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1177">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1178">找不到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1178">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="88180-1179">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1179">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1180">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1180">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="88180-1181">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="88180-1181">Keyword_sin</span></span>

- <span data-ttu-id="88180-1182">sin</span><span class="sxs-lookup"><span data-stu-id="88180-1182">sin</span></span> 
- <span data-ttu-id="88180-1183">社會保險</span><span class="sxs-lookup"><span data-stu-id="88180-1183">social insurance</span></span> 
- <span data-ttu-id="88180-1184">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="88180-1184">numero d'assurance sociale</span></span> 
- <span data-ttu-id="88180-1185">贖罪</span><span class="sxs-lookup"><span data-stu-id="88180-1185">sins</span></span> 
- <span data-ttu-id="88180-1186">ssn</span><span class="sxs-lookup"><span data-stu-id="88180-1186">ssn</span></span> 
- <span data-ttu-id="88180-1187">ssn</span><span class="sxs-lookup"><span data-stu-id="88180-1187">ssns</span></span> 
- <span data-ttu-id="88180-1188">社會安全</span><span class="sxs-lookup"><span data-stu-id="88180-1188">social security</span></span> 
- <span data-ttu-id="88180-1189">numero d'assurance 社交</span><span class="sxs-lookup"><span data-stu-id="88180-1189">numero d'assurance social</span></span> 
- <span data-ttu-id="88180-1190">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1190">national identification number</span></span> 
- <span data-ttu-id="88180-1191">國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-1191">national id</span></span> 
- <span data-ttu-id="88180-1192">sin #</span><span class="sxs-lookup"><span data-stu-id="88180-1192">sin#</span></span> 
- <span data-ttu-id="88180-1193">soc 集</span><span class="sxs-lookup"><span data-stu-id="88180-1193">soc ins</span></span> 
- <span data-ttu-id="88180-1194">社交集</span><span class="sxs-lookup"><span data-stu-id="88180-1194">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="88180-1195">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="88180-1195">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="88180-1196">駕照</span><span class="sxs-lookup"><span data-stu-id="88180-1196">driver's license</span></span> 
- <span data-ttu-id="88180-1197">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-1197">drivers license</span></span> 
- <span data-ttu-id="88180-1198">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-1198">driver's licence</span></span> 
- <span data-ttu-id="88180-1199">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-1199">drivers licence</span></span> 
- <span data-ttu-id="88180-1200">DOB</span><span class="sxs-lookup"><span data-stu-id="88180-1200">DOB</span></span> 
- <span data-ttu-id="88180-1201">出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-1201">Birthdate</span></span> 
- <span data-ttu-id="88180-1202">生日</span><span class="sxs-lookup"><span data-stu-id="88180-1202">Birthday</span></span> 
- <span data-ttu-id="88180-1203">出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-1203">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="88180-1204">智利身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1204">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1205">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1205">Format</span></span>

<span data-ttu-id="88180-1206">7-8 位數加上分隔符號檢查碼或字母</span><span class="sxs-lookup"><span data-stu-id="88180-1206">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1207">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1207">Pattern</span></span>

<span data-ttu-id="88180-1208">7-8 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="88180-1208">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="88180-1209">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1209">1-2 digits</span></span> 
- <span data-ttu-id="88180-1210">句點</span><span class="sxs-lookup"><span data-stu-id="88180-1210">A period</span></span> 
- <span data-ttu-id="88180-1211">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-1211">Three digits</span></span> 
- <span data-ttu-id="88180-1212">句點</span><span class="sxs-lookup"><span data-stu-id="88180-1212">A period</span></span> 
- <span data-ttu-id="88180-1213">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-1213">Three digits</span></span> 
- <span data-ttu-id="88180-1214">一條虛線</span><span class="sxs-lookup"><span data-stu-id="88180-1214">A dash</span></span> 
- <span data-ttu-id="88180-1215">一個數字或字母 （不區分大小寫） 這是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1215">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1216">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1216">Checksum</span></span>

<span data-ttu-id="88180-1217">是</span><span class="sxs-lookup"><span data-stu-id="88180-1217">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1218">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1218">Definition</span></span>

<span data-ttu-id="88180-1219">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1219">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1220">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1220">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1221">找不到來自 Keyword_chile_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1221">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="88180-1222">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1222">The checksum passes.</span></span>

<span data-ttu-id="88180-1223">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1224">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1224">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1225">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1225">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1226">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1226">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="88180-1227">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="88180-1227">Keyword_chile_id_card</span></span>

- <span data-ttu-id="88180-1228">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1228">National Identification Number</span></span> 
- <span data-ttu-id="88180-1229">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-1229">Identity card</span></span> 
- <span data-ttu-id="88180-1230">ID</span><span class="sxs-lookup"><span data-stu-id="88180-1230">ID</span></span> 
- <span data-ttu-id="88180-1231">識別</span><span class="sxs-lookup"><span data-stu-id="88180-1231">Identification</span></span> 
- <span data-ttu-id="88180-1232">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="88180-1232">Rol Único Nacional</span></span> 
- <span data-ttu-id="88180-1233">執行</span><span class="sxs-lookup"><span data-stu-id="88180-1233">RUN</span></span> 
- <span data-ttu-id="88180-1234">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="88180-1234">Rol Único Tributario</span></span> 
- <span data-ttu-id="88180-1235">墨守成規</span><span class="sxs-lookup"><span data-stu-id="88180-1235">RUT</span></span> 
- <span data-ttu-id="88180-1236">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="88180-1236">Cédula de Identidad</span></span> 
- <span data-ttu-id="88180-1237">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="88180-1237">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="88180-1238">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="88180-1238">Tarjeta de identificación</span></span> 
- <span data-ttu-id="88180-1239">Identificación</span><span class="sxs-lookup"><span data-stu-id="88180-1239">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="88180-1240">中國居民身分證 (PRC) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1240">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1241">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1241">Format</span></span>

<span data-ttu-id="88180-1242">18 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1242">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1243">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1243">Pattern</span></span>

<span data-ttu-id="88180-1244">18 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-1244">18 digits:</span></span>
- <span data-ttu-id="88180-1245">六位數的地址代碼</span><span class="sxs-lookup"><span data-stu-id="88180-1245">Six digits which are an address code</span></span> 
- <span data-ttu-id="88180-1246">Yyyymmdd 格式的八位數，代表出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-1246">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="88180-1247">三位數的序碼</span><span class="sxs-lookup"><span data-stu-id="88180-1247">Three digits which are an order code</span></span> 
- <span data-ttu-id="88180-1248">一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1248">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1249">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1249">Checksum</span></span>

<span data-ttu-id="88180-1250">是</span><span class="sxs-lookup"><span data-stu-id="88180-1250">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1251">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1251">Definition</span></span>

<span data-ttu-id="88180-1252">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1252">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1253">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1253">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1254">找不到來自 Keyword_china_resident_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1254">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="88180-1255">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1255">The checksum passes.</span></span>

<span data-ttu-id="88180-1256">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1256">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1257">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1257">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1258">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1258">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1259">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1259">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="88180-1260">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="88180-1260">Keyword_china_resident_id</span></span>

- <span data-ttu-id="88180-1261">居民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-1261">Resident Identity Card</span></span> 
- <span data-ttu-id="88180-1262">中國</span><span class="sxs-lookup"><span data-stu-id="88180-1262">PRC</span></span> 
- <span data-ttu-id="88180-1263">國民身分識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-1263">National Identification Card</span></span> 
- <span data-ttu-id="88180-1264">身份证</span><span class="sxs-lookup"><span data-stu-id="88180-1264">身份证</span></span> 
- <span data-ttu-id="88180-1265">居民身份证</span><span class="sxs-lookup"><span data-stu-id="88180-1265">居民 身份证</span></span> 
- <span data-ttu-id="88180-1266">居民身份证</span><span class="sxs-lookup"><span data-stu-id="88180-1266">居民身份证</span></span> 
- <span data-ttu-id="88180-1267">鉴定</span><span class="sxs-lookup"><span data-stu-id="88180-1267">鉴定</span></span> 
- <span data-ttu-id="88180-1268">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-1268">身分證</span></span> 
- <span data-ttu-id="88180-1269">居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-1269">居民 身份證</span></span>
- <span data-ttu-id="88180-1270">鑑定</span><span class="sxs-lookup"><span data-stu-id="88180-1270">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="88180-1271">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1271">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1272">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1272">Format</span></span>

<span data-ttu-id="88180-1273">16 位數，可格式化或未格式化 (dddddddddddddddd)，且必須通過 Luhn 測試。</span><span class="sxs-lookup"><span data-stu-id="88180-1273">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1274">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1274">Pattern</span></span>

<span data-ttu-id="88180-1275">偵測全球，包括 Visa、 Mastercard、 Discover Card、 JCB、 American Express、 禮品卡和大來卡所有主要品牌的非常複雜且健全的模式。</span><span class="sxs-lookup"><span data-stu-id="88180-1275">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1276">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1276">Checksum</span></span>

<span data-ttu-id="88180-1277">是，Luhn 總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1277">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1278">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1278">Definition</span></span>

<span data-ttu-id="88180-1279">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1279">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1280">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1280">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1281">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="88180-1281">One of the following is true:</span></span>
    - <span data-ttu-id="88180-1282">找不到來自 Keyword_cc_verification 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1282">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="88180-1283">找不到來自 Keyword_cc_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1283">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="88180-1284">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-1284">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="88180-1285">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1285">The checksum passes.</span></span>

<span data-ttu-id="88180-1286">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1286">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1287">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1287">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1288">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1288">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1289">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1289">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="88180-1290">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="88180-1290">Keyword_cc_verification</span></span>

- <span data-ttu-id="88180-1291">卡片驗證</span><span class="sxs-lookup"><span data-stu-id="88180-1291">card verification</span></span>
- <span data-ttu-id="88180-1292">卡識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1292">card identification number</span></span>
- <span data-ttu-id="88180-1293">cvn 驗證</span><span class="sxs-lookup"><span data-stu-id="88180-1293">cvn</span></span>
- <span data-ttu-id="88180-1294">cid</span><span class="sxs-lookup"><span data-stu-id="88180-1294">cid</span></span>
- <span data-ttu-id="88180-1295">cvc2</span><span class="sxs-lookup"><span data-stu-id="88180-1295">cvc2</span></span>
- <span data-ttu-id="88180-1296">cvv2</span><span class="sxs-lookup"><span data-stu-id="88180-1296">cvv2</span></span>
- <span data-ttu-id="88180-1297">pin 碼區塊</span><span class="sxs-lookup"><span data-stu-id="88180-1297">pin block</span></span>
- <span data-ttu-id="88180-1298">安全性驗證碼</span><span class="sxs-lookup"><span data-stu-id="88180-1298">security code</span></span>
- <span data-ttu-id="88180-1299">安全號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1299">security number</span></span>
- <span data-ttu-id="88180-1300">安全性沒有</span><span class="sxs-lookup"><span data-stu-id="88180-1300">security no</span></span>
- <span data-ttu-id="88180-1301">此問題： 數字</span><span class="sxs-lookup"><span data-stu-id="88180-1301">issue number</span></span>
- <span data-ttu-id="88180-1302">發出否</span><span class="sxs-lookup"><span data-stu-id="88180-1302">issue no</span></span>
- <span data-ttu-id="88180-1303">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="88180-1303">cryptogramme</span></span>
- <span data-ttu-id="88180-1304">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="88180-1304">numéro de sécurité</span></span>
- <span data-ttu-id="88180-1305">numero de securite</span><span class="sxs-lookup"><span data-stu-id="88180-1305">numero de securite</span></span>
- <span data-ttu-id="88180-1306">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1306">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="88180-1307">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1307">kreditkartenprufnummer</span></span>
- <span data-ttu-id="88180-1308">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="88180-1308">prüfziffer</span></span>
- <span data-ttu-id="88180-1309">prufziffer</span><span class="sxs-lookup"><span data-stu-id="88180-1309">prufziffer</span></span>
- <span data-ttu-id="88180-1310">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="88180-1310">sicherheits Kode</span></span>
- <span data-ttu-id="88180-1311">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="88180-1311">sicherheitscode</span></span>
- <span data-ttu-id="88180-1312">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1312">sicherheitsnummer</span></span>
- <span data-ttu-id="88180-1313">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="88180-1313">verfalldatum</span></span>
- <span data-ttu-id="88180-1314">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="88180-1314">codice di verifica</span></span>
- <span data-ttu-id="88180-1315">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1315">cod.</span></span> <span data-ttu-id="88180-1316">sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1316">sicurezza</span></span>
- <span data-ttu-id="88180-1317">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1317">cod sicurezza</span></span>
- <span data-ttu-id="88180-1318">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="88180-1318">n autorizzazione</span></span>
- <span data-ttu-id="88180-1319">código</span><span class="sxs-lookup"><span data-stu-id="88180-1319">código</span></span>
- <span data-ttu-id="88180-1320">codigo</span><span class="sxs-lookup"><span data-stu-id="88180-1320">codigo</span></span>
- <span data-ttu-id="88180-1321">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1321">cod.</span></span> <span data-ttu-id="88180-1322">seg</span><span class="sxs-lookup"><span data-stu-id="88180-1322">seg</span></span>
- <span data-ttu-id="88180-1323">cod seg</span><span class="sxs-lookup"><span data-stu-id="88180-1323">cod seg</span></span>
- <span data-ttu-id="88180-1324">código de segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1324">código de segurança</span></span>
- <span data-ttu-id="88180-1325">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1325">codigo de seguranca</span></span>
- <span data-ttu-id="88180-1326">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1326">codigo de segurança</span></span>
- <span data-ttu-id="88180-1327">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1327">código de seguranca</span></span>
- <span data-ttu-id="88180-1328">cód。</span><span class="sxs-lookup"><span data-stu-id="88180-1328">cód.</span></span> <span data-ttu-id="88180-1329">segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1329">segurança</span></span>
- <span data-ttu-id="88180-1330">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1330">cod.</span></span> <span data-ttu-id="88180-1331">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1331">seguranca cod.</span></span> <span data-ttu-id="88180-1332">segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1332">segurança</span></span>
- <span data-ttu-id="88180-1333">cód。</span><span class="sxs-lookup"><span data-stu-id="88180-1333">cód.</span></span> <span data-ttu-id="88180-1334">seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1334">seguranca</span></span>
- <span data-ttu-id="88180-1335">cód segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1335">cód segurança</span></span>
- <span data-ttu-id="88180-1336">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1336">cod seguranca cod segurança</span></span>
- <span data-ttu-id="88180-1337">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1337">cód seguranca</span></span>
- <span data-ttu-id="88180-1338">número de verificação</span><span class="sxs-lookup"><span data-stu-id="88180-1338">número de verificação</span></span>
- <span data-ttu-id="88180-1339">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="88180-1339">numero de verificacao</span></span>
- <span data-ttu-id="88180-1340">ablauf</span><span class="sxs-lookup"><span data-stu-id="88180-1340">ablauf</span></span>
- <span data-ttu-id="88180-1341">gültig bis</span><span class="sxs-lookup"><span data-stu-id="88180-1341">gültig bis</span></span>
- <span data-ttu-id="88180-1342">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-1342">gültigkeitsdatum</span></span>
- <span data-ttu-id="88180-1343">gultig bis</span><span class="sxs-lookup"><span data-stu-id="88180-1343">gultig bis</span></span>
- <span data-ttu-id="88180-1344">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-1344">gultigkeitsdatum</span></span>
- <span data-ttu-id="88180-1345">scadenza</span><span class="sxs-lookup"><span data-stu-id="88180-1345">scadenza</span></span>
- <span data-ttu-id="88180-1346">資料 scad</span><span class="sxs-lookup"><span data-stu-id="88180-1346">data scad</span></span>
- <span data-ttu-id="88180-1347">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="88180-1347">fecha de expiracion</span></span>
- <span data-ttu-id="88180-1348">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="88180-1348">fecha de venc</span></span>
- <span data-ttu-id="88180-1349">vencimiento</span><span class="sxs-lookup"><span data-stu-id="88180-1349">vencimiento</span></span>
- <span data-ttu-id="88180-1350">válido hasta</span><span class="sxs-lookup"><span data-stu-id="88180-1350">válido hasta</span></span>
- <span data-ttu-id="88180-1351">valido hasta</span><span class="sxs-lookup"><span data-stu-id="88180-1351">valido hasta</span></span>
- <span data-ttu-id="88180-1352">vto</span><span class="sxs-lookup"><span data-stu-id="88180-1352">vto</span></span>
- <span data-ttu-id="88180-1353">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="88180-1353">data de expiração</span></span>
- <span data-ttu-id="88180-1354">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="88180-1354">data de expiracao</span></span>
- <span data-ttu-id="88180-1355">資料長破折號 que expira</span><span class="sxs-lookup"><span data-stu-id="88180-1355">data em que expira</span></span>
- <span data-ttu-id="88180-1356">validade</span><span class="sxs-lookup"><span data-stu-id="88180-1356">validade</span></span>
- <span data-ttu-id="88180-1357">勇氣</span><span class="sxs-lookup"><span data-stu-id="88180-1357">valor</span></span>
- <span data-ttu-id="88180-1358">vencimento</span><span class="sxs-lookup"><span data-stu-id="88180-1358">vencimento</span></span>
- <span data-ttu-id="88180-1359">Venc</span><span class="sxs-lookup"><span data-stu-id="88180-1359">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="88180-1360">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="88180-1360">Keyword_cc_name</span></span>

- <span data-ttu-id="88180-1361">amex</span><span class="sxs-lookup"><span data-stu-id="88180-1361">amex</span></span>
- <span data-ttu-id="88180-1362">american express</span><span class="sxs-lookup"><span data-stu-id="88180-1362">american express</span></span>
- <span data-ttu-id="88180-1363">americanexpress</span><span class="sxs-lookup"><span data-stu-id="88180-1363">americanexpress</span></span>
- <span data-ttu-id="88180-1364">Visa</span><span class="sxs-lookup"><span data-stu-id="88180-1364">Visa</span></span>
- <span data-ttu-id="88180-1365">mastercard</span><span class="sxs-lookup"><span data-stu-id="88180-1365">mastercard</span></span>
- <span data-ttu-id="88180-1366">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="88180-1366">master card</span></span>
- <span data-ttu-id="88180-1367">mc</span><span class="sxs-lookup"><span data-stu-id="88180-1367">mc</span></span> 
- <span data-ttu-id="88180-1368">mastercards</span><span class="sxs-lookup"><span data-stu-id="88180-1368">mastercards</span></span>
- <span data-ttu-id="88180-1369">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="88180-1369">master cards</span></span>
- <span data-ttu-id="88180-1370">大來卡</span><span class="sxs-lookup"><span data-stu-id="88180-1370">diner's Club</span></span>
- <span data-ttu-id="88180-1371">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="88180-1371">diners club</span></span>
- <span data-ttu-id="88180-1372">dinersclub</span><span class="sxs-lookup"><span data-stu-id="88180-1372">dinersclub</span></span>
- <span data-ttu-id="88180-1373">探索卡</span><span class="sxs-lookup"><span data-stu-id="88180-1373">discover card</span></span>
- <span data-ttu-id="88180-1374">discovercard</span><span class="sxs-lookup"><span data-stu-id="88180-1374">discovercard</span></span>
- <span data-ttu-id="88180-1375">探索卡</span><span class="sxs-lookup"><span data-stu-id="88180-1375">discover cards</span></span>
- <span data-ttu-id="88180-1376">JCB</span><span class="sxs-lookup"><span data-stu-id="88180-1376">JCB</span></span>
- <span data-ttu-id="88180-1377">日文卡機構</span><span class="sxs-lookup"><span data-stu-id="88180-1377">japanese card bureau</span></span>
- <span data-ttu-id="88180-1378">相關表示</span><span class="sxs-lookup"><span data-stu-id="88180-1378">carte blanche</span></span>
- <span data-ttu-id="88180-1379">carteblanche</span><span class="sxs-lookup"><span data-stu-id="88180-1379">carteblanche</span></span>
- <span data-ttu-id="88180-1380">信用卡</span><span class="sxs-lookup"><span data-stu-id="88180-1380">credit card</span></span>
- <span data-ttu-id="88180-1381">cc #</span><span class="sxs-lookup"><span data-stu-id="88180-1381">cc#</span></span>
- <span data-ttu-id="88180-1382">cc # 中：</span><span class="sxs-lookup"><span data-stu-id="88180-1382">cc#:</span></span>
- <span data-ttu-id="88180-1383">到期日</span><span class="sxs-lookup"><span data-stu-id="88180-1383">expiration date</span></span>
- <span data-ttu-id="88180-1384">exp 日期</span><span class="sxs-lookup"><span data-stu-id="88180-1384">exp date</span></span>
- <span data-ttu-id="88180-1385">到期日</span><span class="sxs-lookup"><span data-stu-id="88180-1385">expiry date</span></span>
- <span data-ttu-id="88180-1386">日期 d'expiration</span><span class="sxs-lookup"><span data-stu-id="88180-1386">date d’expiration</span></span>
- <span data-ttu-id="88180-1387">日期 d'exp</span><span class="sxs-lookup"><span data-stu-id="88180-1387">date d'exp</span></span>
- <span data-ttu-id="88180-1388">日期到期</span><span class="sxs-lookup"><span data-stu-id="88180-1388">date expiration</span></span>
- <span data-ttu-id="88180-1389">銀行卡</span><span class="sxs-lookup"><span data-stu-id="88180-1389">bank card</span></span>
- <span data-ttu-id="88180-1390">bankcard</span><span class="sxs-lookup"><span data-stu-id="88180-1390">bankcard</span></span>
- <span data-ttu-id="88180-1391">證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1391">card number</span></span>
- <span data-ttu-id="88180-1392">卡片 num</span><span class="sxs-lookup"><span data-stu-id="88180-1392">card num</span></span>
- <span data-ttu-id="88180-1393">cardnumber</span><span class="sxs-lookup"><span data-stu-id="88180-1393">cardnumber</span></span>
- <span data-ttu-id="88180-1394">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="88180-1394">cardnumbers</span></span>
- <span data-ttu-id="88180-1395">卡號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1395">card numbers</span></span>
- <span data-ttu-id="88180-1396">信用卡</span><span class="sxs-lookup"><span data-stu-id="88180-1396">creditcard</span></span>
- <span data-ttu-id="88180-1397">信用卡</span><span class="sxs-lookup"><span data-stu-id="88180-1397">credit cards</span></span>
- <span data-ttu-id="88180-1398">creditcards</span><span class="sxs-lookup"><span data-stu-id="88180-1398">creditcards</span></span>
- <span data-ttu-id="88180-1399">ccn</span><span class="sxs-lookup"><span data-stu-id="88180-1399">ccn</span></span>
- <span data-ttu-id="88180-1400">持卡人</span><span class="sxs-lookup"><span data-stu-id="88180-1400">card holder</span></span>
- <span data-ttu-id="88180-1401">持卡人</span><span class="sxs-lookup"><span data-stu-id="88180-1401">cardholder</span></span>
- <span data-ttu-id="88180-1402">卡片持有者</span><span class="sxs-lookup"><span data-stu-id="88180-1402">card holders</span></span>
- <span data-ttu-id="88180-1403">cardholders</span><span class="sxs-lookup"><span data-stu-id="88180-1403">cardholders</span></span>
- <span data-ttu-id="88180-1404">檢查卡</span><span class="sxs-lookup"><span data-stu-id="88180-1404">check card</span></span>
- <span data-ttu-id="88180-1405">checkcard</span><span class="sxs-lookup"><span data-stu-id="88180-1405">checkcard</span></span>
- <span data-ttu-id="88180-1406">檢查卡</span><span class="sxs-lookup"><span data-stu-id="88180-1406">check cards</span></span>
- <span data-ttu-id="88180-1407">checkcards</span><span class="sxs-lookup"><span data-stu-id="88180-1407">checkcards</span></span>
- <span data-ttu-id="88180-1408">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="88180-1408">debit card</span></span>
- <span data-ttu-id="88180-1409">debitcard</span><span class="sxs-lookup"><span data-stu-id="88180-1409">debitcard</span></span>
- <span data-ttu-id="88180-1410">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="88180-1410">debit cards</span></span>
- <span data-ttu-id="88180-1411">debitcards</span><span class="sxs-lookup"><span data-stu-id="88180-1411">debitcards</span></span>
- <span data-ttu-id="88180-1412">atm 卡</span><span class="sxs-lookup"><span data-stu-id="88180-1412">atm card</span></span>
- <span data-ttu-id="88180-1413">atmcard</span><span class="sxs-lookup"><span data-stu-id="88180-1413">atmcard</span></span>
- <span data-ttu-id="88180-1414">atm 卡</span><span class="sxs-lookup"><span data-stu-id="88180-1414">atm cards</span></span>
- <span data-ttu-id="88180-1415">atmcards</span><span class="sxs-lookup"><span data-stu-id="88180-1415">atmcards</span></span>
- <span data-ttu-id="88180-1416">enroute</span><span class="sxs-lookup"><span data-stu-id="88180-1416">enroute</span></span>
- <span data-ttu-id="88180-1417">en-us 路由</span><span class="sxs-lookup"><span data-stu-id="88180-1417">en route</span></span>
- <span data-ttu-id="88180-1418">卡類型</span><span class="sxs-lookup"><span data-stu-id="88180-1418">card type</span></span>
- <span data-ttu-id="88180-1419">相關 bancaire</span><span class="sxs-lookup"><span data-stu-id="88180-1419">carte bancaire</span></span>
- <span data-ttu-id="88180-1420">相關 de crédit</span><span class="sxs-lookup"><span data-stu-id="88180-1420">carte de crédit</span></span>
- <span data-ttu-id="88180-1421">相關 de 信用</span><span class="sxs-lookup"><span data-stu-id="88180-1421">carte de credit</span></span>
- <span data-ttu-id="88180-1422">numéro de 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1422">numéro de carte</span></span>
- <span data-ttu-id="88180-1423">numero de 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1423">numero de carte</span></span>
- <span data-ttu-id="88180-1424">nº de la 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1424">nº de la carte</span></span>
- <span data-ttu-id="88180-1425">nº de 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1425">nº de carte</span></span>
- <span data-ttu-id="88180-1426">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="88180-1426">kreditkarte</span></span>
- <span data-ttu-id="88180-1427">karte</span><span class="sxs-lookup"><span data-stu-id="88180-1427">karte</span></span>
- <span data-ttu-id="88180-1428">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="88180-1428">karteninhaber</span></span>
- <span data-ttu-id="88180-1429">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="88180-1429">karteninhabers</span></span>
- <span data-ttu-id="88180-1430">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="88180-1430">kreditkarteninhaber</span></span>
- <span data-ttu-id="88180-1431">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="88180-1431">kreditkarteninstitut</span></span>
- <span data-ttu-id="88180-1432">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="88180-1432">kreditkartentyp</span></span>
- <span data-ttu-id="88180-1433">eigentümername</span><span class="sxs-lookup"><span data-stu-id="88180-1433">eigentümername</span></span>
- <span data-ttu-id="88180-1434">kartennr</span><span class="sxs-lookup"><span data-stu-id="88180-1434">kartennr</span></span> 
- <span data-ttu-id="88180-1435">kartennummer</span><span class="sxs-lookup"><span data-stu-id="88180-1435">kartennummer</span></span>
- <span data-ttu-id="88180-1436">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="88180-1436">kreditkartennummer</span></span>
- <span data-ttu-id="88180-1437">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="88180-1437">kreditkarten-nummer</span></span>
- <span data-ttu-id="88180-1438">carta di credito</span><span class="sxs-lookup"><span data-stu-id="88180-1438">carta di credito</span></span>
- <span data-ttu-id="88180-1439">carta credito</span><span class="sxs-lookup"><span data-stu-id="88180-1439">carta credito</span></span>
- <span data-ttu-id="88180-1440">carta</span><span class="sxs-lookup"><span data-stu-id="88180-1440">carta</span></span>
- <span data-ttu-id="88180-1441">n carta</span><span class="sxs-lookup"><span data-stu-id="88180-1441">n carta</span></span>
- <span data-ttu-id="88180-1442">編號。</span><span class="sxs-lookup"><span data-stu-id="88180-1442">nr.</span></span> <span data-ttu-id="88180-1443">carta</span><span class="sxs-lookup"><span data-stu-id="88180-1443">carta</span></span>
- <span data-ttu-id="88180-1444">編號 carta</span><span class="sxs-lookup"><span data-stu-id="88180-1444">nr carta</span></span>
- <span data-ttu-id="88180-1445">numero carta</span><span class="sxs-lookup"><span data-stu-id="88180-1445">numero carta</span></span>
- <span data-ttu-id="88180-1446">numero della carta</span><span class="sxs-lookup"><span data-stu-id="88180-1446">numero della carta</span></span>
- <span data-ttu-id="88180-1447">numero di carta</span><span class="sxs-lookup"><span data-stu-id="88180-1447">numero di carta</span></span>
- <span data-ttu-id="88180-1448">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="88180-1448">tarjeta credito</span></span>
- <span data-ttu-id="88180-1449">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="88180-1449">tarjeta de credito</span></span>
- <span data-ttu-id="88180-1450">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="88180-1450">tarjeta crédito</span></span>
- <span data-ttu-id="88180-1451">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="88180-1451">tarjeta de crédito</span></span>
- <span data-ttu-id="88180-1452">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="88180-1452">tarjeta de atm</span></span>
- <span data-ttu-id="88180-1453">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="88180-1453">tarjeta atm</span></span>
- <span data-ttu-id="88180-1454">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="88180-1454">tarjeta debito</span></span>
- <span data-ttu-id="88180-1455">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="88180-1455">tarjeta de debito</span></span>
- <span data-ttu-id="88180-1456">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="88180-1456">tarjeta débito</span></span>
- <span data-ttu-id="88180-1457">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="88180-1457">tarjeta de débito</span></span>
- <span data-ttu-id="88180-1458">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1458">nº de tarjeta</span></span>
- <span data-ttu-id="88180-1459">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1459">no.</span></span> <span data-ttu-id="88180-1460">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1460">de tarjeta</span></span>
- <span data-ttu-id="88180-1461">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1461">no de tarjeta</span></span>
- <span data-ttu-id="88180-1462">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1462">numero de tarjeta</span></span>
- <span data-ttu-id="88180-1463">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1463">número de tarjeta</span></span>
- <span data-ttu-id="88180-1464">tarjeta 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-1464">tarjeta no</span></span>
- <span data-ttu-id="88180-1465">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="88180-1465">tarjetahabiente</span></span>
- <span data-ttu-id="88180-1466">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="88180-1466">cartão de crédito</span></span>
- <span data-ttu-id="88180-1467">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="88180-1467">cartão de credito</span></span>
- <span data-ttu-id="88180-1468">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="88180-1468">cartao de crédito</span></span>
- <span data-ttu-id="88180-1469">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="88180-1469">cartao de credito</span></span>
- <span data-ttu-id="88180-1470">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="88180-1470">cartão de débito</span></span>
- <span data-ttu-id="88180-1471">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="88180-1471">cartao de débito</span></span>
- <span data-ttu-id="88180-1472">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="88180-1472">cartão de debito</span></span>
- <span data-ttu-id="88180-1473">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="88180-1473">cartao de debito</span></span>
- <span data-ttu-id="88180-1474">débito automático</span><span class="sxs-lookup"><span data-stu-id="88180-1474">débito automático</span></span>
- <span data-ttu-id="88180-1475">debito automatico</span><span class="sxs-lookup"><span data-stu-id="88180-1475">debito automatico</span></span>
- <span data-ttu-id="88180-1476">número 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1476">número do cartão</span></span>
- <span data-ttu-id="88180-1477">numero 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1477">numero do cartão</span></span> 
- <span data-ttu-id="88180-1478">número 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1478">número do cartao</span></span>
- <span data-ttu-id="88180-1479">numero 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1479">numero do cartao</span></span>
- <span data-ttu-id="88180-1480">número de cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1480">número de cartão</span></span>
- <span data-ttu-id="88180-1481">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1481">numero de cartão</span></span>
- <span data-ttu-id="88180-1482">número de cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1482">número de cartao</span></span>
- <span data-ttu-id="88180-1483">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1483">numero de cartao</span></span>
- <span data-ttu-id="88180-1484">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1484">nº do cartão</span></span>
- <span data-ttu-id="88180-1485">nº 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1485">nº do cartao</span></span>
- <span data-ttu-id="88180-1486">nº。</span><span class="sxs-lookup"><span data-stu-id="88180-1486">nº.</span></span> <span data-ttu-id="88180-1487">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1487">do cartão</span></span>
- <span data-ttu-id="88180-1488">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1488">no do cartão</span></span>
- <span data-ttu-id="88180-1489">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1489">no do cartao</span></span>
- <span data-ttu-id="88180-1490">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1490">no.</span></span> <span data-ttu-id="88180-1491">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1491">do cartão</span></span>
- <span data-ttu-id="88180-1492">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1492">no.</span></span> <span data-ttu-id="88180-1493">請勿 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1493">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="88180-1494">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1494">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1495">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1495">Format</span></span>

<span data-ttu-id="88180-1496">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-1496">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1497">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1497">Pattern</span></span>

<span data-ttu-id="88180-1498">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-1498">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1499">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1499">Checksum</span></span>

<span data-ttu-id="88180-1500">否</span><span class="sxs-lookup"><span data-stu-id="88180-1500">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1501">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1501">Definition</span></span>

<span data-ttu-id="88180-1502">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1502">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1503">函數 Func_croatia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1503">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1504">找不到來自 Keyword_croatia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1504">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-1505">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1505">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="88180-1506">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="88180-1506">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="88180-1507">克羅埃西亞身分證</span><span class="sxs-lookup"><span data-stu-id="88180-1507">Croatian identity card</span></span>
- <span data-ttu-id="88180-1508">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="88180-1508">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="88180-1509">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="88180-1509">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1510">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1510">Format</span></span>

<span data-ttu-id="88180-1511">11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1511">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1512">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1512">Pattern</span></span>

<span data-ttu-id="88180-1513">11 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-1513">11 digits:</span></span>
- <span data-ttu-id="88180-1514">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1514">10 digits</span></span> 
- <span data-ttu-id="88180-1515">最後一個數字是檢查碼國際資料交換的目的，字母 HR 新增前面十一個數字。</span><span class="sxs-lookup"><span data-stu-id="88180-1515">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1516">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1516">Checksum</span></span>

<span data-ttu-id="88180-1517">是</span><span class="sxs-lookup"><span data-stu-id="88180-1517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1518">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1518">Definition</span></span>

<span data-ttu-id="88180-1519">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1520">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1520">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1521">找不到來自 Keyword_croatia_oib_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1521">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="88180-1522">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1522">The checksum passes.</span></span>

<span data-ttu-id="88180-1523">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1523">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1524">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1524">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1525">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1525">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1526">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1526">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="88180-1527">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="88180-1527">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="88180-1528">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1528">Personal Identification Number</span></span>
- <span data-ttu-id="88180-1529">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="88180-1529">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="88180-1530">OIB 碼</span><span class="sxs-lookup"><span data-stu-id="88180-1530">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="88180-1531">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1531">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1532">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1532">Format</span></span>

<span data-ttu-id="88180-1533">具有選用的九位數正斜線 （舊格式） 搭配選用的 10 位數正斜線 （新格式）</span><span class="sxs-lookup"><span data-stu-id="88180-1533">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1534">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1534">Pattern</span></span>

<span data-ttu-id="88180-1535">九位數 （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="88180-1535">Nine digits (old format):</span></span>
- <span data-ttu-id="88180-1536">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-1536">Nine digits</span></span>

<span data-ttu-id="88180-1537">或</span><span class="sxs-lookup"><span data-stu-id="88180-1537">OR</span></span>

- <span data-ttu-id="88180-1538">代表出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="88180-1538">Six digits that represent date of birth</span></span>
- <span data-ttu-id="88180-1539">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="88180-1539">A forward slash</span></span>
- <span data-ttu-id="88180-1540">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-1540">Three digits</span></span>

<span data-ttu-id="88180-1541">10 位數 （新格式）：</span><span class="sxs-lookup"><span data-stu-id="88180-1541">10 digits (new format):</span></span>
- <span data-ttu-id="88180-1542">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1542">10 digits</span></span>

<span data-ttu-id="88180-1543">或</span><span class="sxs-lookup"><span data-stu-id="88180-1543">OR</span></span>

- <span data-ttu-id="88180-1544">代表出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="88180-1544">Six digits that represent date of birth</span></span>
- <span data-ttu-id="88180-1545">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="88180-1545">A forward slash</span></span> 
- <span data-ttu-id="88180-1546">四個位數最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1546">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1547">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1547">Checksum</span></span>

<span data-ttu-id="88180-1548">是</span><span class="sxs-lookup"><span data-stu-id="88180-1548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1549">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1549">Definition</span></span>

<span data-ttu-id="88180-1550">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_czech_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-1551">找不到來自 Keyword_czech_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1551">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="88180-1552">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1552">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="88180-1553">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1553">Keywords</span></span>

- <span data-ttu-id="88180-1554">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1554">czech personal identity number</span></span>
- <span data-ttu-id="88180-1555">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="88180-1555">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="88180-1556">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1556">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1557">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1557">Format</span></span>

<span data-ttu-id="88180-1558">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="88180-1558">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1559">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1559">Pattern</span></span>

<span data-ttu-id="88180-1560">10 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-1560">10 digits:</span></span>
- <span data-ttu-id="88180-1561">DDMMYY 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-1561">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="88180-1562">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-1562">A hyphen</span></span> 
- <span data-ttu-id="88180-1563">四個位數最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1563">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1564">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1564">Checksum</span></span>

<span data-ttu-id="88180-1565">是</span><span class="sxs-lookup"><span data-stu-id="88180-1565">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1566">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1566">Definition</span></span>

<span data-ttu-id="88180-1567">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 規則運算式 Regex_denmark_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-1568">找不到來自 Keyword_denmark_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1568">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="88180-1569">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1569">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-1570">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1570">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="88180-1571">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="88180-1571">Keyword_denmark_id</span></span>

- <span data-ttu-id="88180-1572">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1572">Personal Identification Number</span></span>
- <span data-ttu-id="88180-1573">CPR</span><span class="sxs-lookup"><span data-stu-id="88180-1573">CPR</span></span>
- <span data-ttu-id="88180-1574">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="88180-1574">Det Centrale Personregister</span></span>
- <span data-ttu-id="88180-1575">Personnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1575">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="88180-1576">藥物管理局 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="88180-1576">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1577">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1577">Format</span></span>

<span data-ttu-id="88180-1578">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="88180-1578">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1579">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1579">Pattern</span></span>

<span data-ttu-id="88180-1580">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="88180-1580">Pattern must include all of the following:</span></span>
- <span data-ttu-id="88180-1581">一個字母 （不區分大小寫） 從這組可能的字母： abcdefghjklmnprstux，此為註冊者代碼</span><span class="sxs-lookup"><span data-stu-id="88180-1581">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="88180-1582">一個字母 （不區分大小寫），也就是註冊者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="88180-1582">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="88180-1583">七位數，最後一個數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1583">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1584">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1584">Checksum</span></span>

<span data-ttu-id="88180-1585">是</span><span class="sxs-lookup"><span data-stu-id="88180-1585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1586">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1586">Definition</span></span>

<span data-ttu-id="88180-1587">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1587">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1588">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1588">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1589">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1589">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-1590">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1590">Keywords</span></span>

<span data-ttu-id="88180-1591">無</span><span class="sxs-lookup"><span data-stu-id="88180-1591">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="88180-1592">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1592">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1593">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1593">Format</span></span>

<span data-ttu-id="88180-1594">16 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1594">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1595">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1595">Pattern</span></span>

<span data-ttu-id="88180-1596">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="88180-1596">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1597">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1597">Checksum</span></span>

<span data-ttu-id="88180-1598">是</span><span class="sxs-lookup"><span data-stu-id="88180-1598">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1599">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1599">Definition</span></span>

<span data-ttu-id="88180-1600">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1600">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1601">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1601">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1602">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="88180-1602">At least one of the following is true:</span></span>
    - <span data-ttu-id="88180-1603">找不到來自 Keyword_eu_debit_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1603">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="88180-1604">找不到來自 Keyword_card_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1604">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="88180-1605">找不到來自 Keyword_card_security_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1605">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="88180-1606">找不到來自 Keyword_card_expiration_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1606">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="88180-1607">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-1607">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="88180-1608">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1608">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1609">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1609">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="88180-1610">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="88180-1610">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="88180-1611">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1611">account number</span></span> 
- <span data-ttu-id="88180-1612">證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1612">card number</span></span> 
- <span data-ttu-id="88180-1613">卡否。</span><span class="sxs-lookup"><span data-stu-id="88180-1613">card no.</span></span> 
- <span data-ttu-id="88180-1614">安全號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1614">security number</span></span> 
- <span data-ttu-id="88180-1615">cc #</span><span class="sxs-lookup"><span data-stu-id="88180-1615">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="88180-1616">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="88180-1616">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="88180-1617">acct 芳鄰</span><span class="sxs-lookup"><span data-stu-id="88180-1617">acct nbr</span></span> 
- <span data-ttu-id="88180-1618">acct num</span><span class="sxs-lookup"><span data-stu-id="88180-1618">acct num</span></span> 
- <span data-ttu-id="88180-1619">acct 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-1619">acct no</span></span> 
- <span data-ttu-id="88180-1620">american express</span><span class="sxs-lookup"><span data-stu-id="88180-1620">american express</span></span> 
- <span data-ttu-id="88180-1621">americanexpress</span><span class="sxs-lookup"><span data-stu-id="88180-1621">americanexpress</span></span> 
- <span data-ttu-id="88180-1622">americano 濃縮咖啡</span><span class="sxs-lookup"><span data-stu-id="88180-1622">americano espresso</span></span> 
- <span data-ttu-id="88180-1623">amex</span><span class="sxs-lookup"><span data-stu-id="88180-1623">amex</span></span> 
- <span data-ttu-id="88180-1624">atm 卡</span><span class="sxs-lookup"><span data-stu-id="88180-1624">atm card</span></span> 
- <span data-ttu-id="88180-1625">atm 卡</span><span class="sxs-lookup"><span data-stu-id="88180-1625">atm cards</span></span> 
- <span data-ttu-id="88180-1626">atm kaart</span><span class="sxs-lookup"><span data-stu-id="88180-1626">atm kaart</span></span> 
- <span data-ttu-id="88180-1627">atmcard</span><span class="sxs-lookup"><span data-stu-id="88180-1627">atmcard</span></span> 
- <span data-ttu-id="88180-1628">atmcards</span><span class="sxs-lookup"><span data-stu-id="88180-1628">atmcards</span></span> 
- <span data-ttu-id="88180-1629">atmkaart</span><span class="sxs-lookup"><span data-stu-id="88180-1629">atmkaart</span></span> 
- <span data-ttu-id="88180-1630">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="88180-1630">atmkaarten</span></span> 
- <span data-ttu-id="88180-1631">bancontact</span><span class="sxs-lookup"><span data-stu-id="88180-1631">bancontact</span></span> 
- <span data-ttu-id="88180-1632">銀行卡</span><span class="sxs-lookup"><span data-stu-id="88180-1632">bank card</span></span> 
- <span data-ttu-id="88180-1633">bankkaart</span><span class="sxs-lookup"><span data-stu-id="88180-1633">bankkaart</span></span> 
- <span data-ttu-id="88180-1634">持卡人</span><span class="sxs-lookup"><span data-stu-id="88180-1634">card holder</span></span> 
- <span data-ttu-id="88180-1635">卡片持有者</span><span class="sxs-lookup"><span data-stu-id="88180-1635">card holders</span></span> 
- <span data-ttu-id="88180-1636">卡片 num</span><span class="sxs-lookup"><span data-stu-id="88180-1636">card num</span></span> 
- <span data-ttu-id="88180-1637">證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1637">card number</span></span> 
- <span data-ttu-id="88180-1638">卡號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1638">card numbers</span></span> 
- <span data-ttu-id="88180-1639">卡類型</span><span class="sxs-lookup"><span data-stu-id="88180-1639">card type</span></span> 
- <span data-ttu-id="88180-1640">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="88180-1640">cardano numerico</span></span> 
- <span data-ttu-id="88180-1641">持卡人</span><span class="sxs-lookup"><span data-stu-id="88180-1641">cardholder</span></span> 
- <span data-ttu-id="88180-1642">cardholders</span><span class="sxs-lookup"><span data-stu-id="88180-1642">cardholders</span></span> 
- <span data-ttu-id="88180-1643">cardnumber</span><span class="sxs-lookup"><span data-stu-id="88180-1643">cardnumber</span></span> 
- <span data-ttu-id="88180-1644">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="88180-1644">cardnumbers</span></span> 
- <span data-ttu-id="88180-1645">carta bianca</span><span class="sxs-lookup"><span data-stu-id="88180-1645">carta bianca</span></span> 
- <span data-ttu-id="88180-1646">carta credito</span><span class="sxs-lookup"><span data-stu-id="88180-1646">carta credito</span></span> 
- <span data-ttu-id="88180-1647">carta di credito</span><span class="sxs-lookup"><span data-stu-id="88180-1647">carta di credito</span></span> 
- <span data-ttu-id="88180-1648">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="88180-1648">cartao de credito</span></span> 
- <span data-ttu-id="88180-1649">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="88180-1649">cartao de crédito</span></span> 
- <span data-ttu-id="88180-1650">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="88180-1650">cartao de debito</span></span> 
- <span data-ttu-id="88180-1651">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="88180-1651">cartao de débito</span></span> 
- <span data-ttu-id="88180-1652">相關 bancaire</span><span class="sxs-lookup"><span data-stu-id="88180-1652">carte bancaire</span></span> 
- <span data-ttu-id="88180-1653">相關表示</span><span class="sxs-lookup"><span data-stu-id="88180-1653">carte blanche</span></span> 
- <span data-ttu-id="88180-1654">相關 bleue</span><span class="sxs-lookup"><span data-stu-id="88180-1654">carte bleue</span></span> 
- <span data-ttu-id="88180-1655">相關 de 信用</span><span class="sxs-lookup"><span data-stu-id="88180-1655">carte de credit</span></span> 
- <span data-ttu-id="88180-1656">相關 de crédit</span><span class="sxs-lookup"><span data-stu-id="88180-1656">carte de crédit</span></span> 
- <span data-ttu-id="88180-1657">相關 di credito</span><span class="sxs-lookup"><span data-stu-id="88180-1657">carte di credito</span></span> 
- <span data-ttu-id="88180-1658">carteblanche</span><span class="sxs-lookup"><span data-stu-id="88180-1658">carteblanche</span></span> 
- <span data-ttu-id="88180-1659">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="88180-1659">cartão de credito</span></span> 
- <span data-ttu-id="88180-1660">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="88180-1660">cartão de crédito</span></span> 
- <span data-ttu-id="88180-1661">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="88180-1661">cartão de debito</span></span> 
- <span data-ttu-id="88180-1662">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="88180-1662">cartão de débito</span></span> 
- <span data-ttu-id="88180-1663">cb</span><span class="sxs-lookup"><span data-stu-id="88180-1663">cb</span></span> 
- <span data-ttu-id="88180-1664">ccn</span><span class="sxs-lookup"><span data-stu-id="88180-1664">ccn</span></span> 
- <span data-ttu-id="88180-1665">檢查卡</span><span class="sxs-lookup"><span data-stu-id="88180-1665">check card</span></span> 
- <span data-ttu-id="88180-1666">檢查卡</span><span class="sxs-lookup"><span data-stu-id="88180-1666">check cards</span></span> 
- <span data-ttu-id="88180-1667">checkcard</span><span class="sxs-lookup"><span data-stu-id="88180-1667">checkcard</span></span>
- <span data-ttu-id="88180-1668">checkcards</span><span class="sxs-lookup"><span data-stu-id="88180-1668">checkcards</span></span> 
- <span data-ttu-id="88180-1669">chequekaart</span><span class="sxs-lookup"><span data-stu-id="88180-1669">chequekaart</span></span> 
- <span data-ttu-id="88180-1670">cirrus</span><span class="sxs-lookup"><span data-stu-id="88180-1670">cirrus</span></span> 
- <span data-ttu-id="88180-1671">cirrus-edc-大師</span><span class="sxs-lookup"><span data-stu-id="88180-1671">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="88180-1672">controlekaart</span><span class="sxs-lookup"><span data-stu-id="88180-1672">controlekaart</span></span> 
- <span data-ttu-id="88180-1673">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="88180-1673">controlekaarten</span></span> 
- <span data-ttu-id="88180-1674">信用卡</span><span class="sxs-lookup"><span data-stu-id="88180-1674">credit card</span></span> 
- <span data-ttu-id="88180-1675">信用卡</span><span class="sxs-lookup"><span data-stu-id="88180-1675">credit cards</span></span> 
- <span data-ttu-id="88180-1676">信用卡</span><span class="sxs-lookup"><span data-stu-id="88180-1676">creditcard</span></span> 
- <span data-ttu-id="88180-1677">creditcards</span><span class="sxs-lookup"><span data-stu-id="88180-1677">creditcards</span></span> 
- <span data-ttu-id="88180-1678">debetkaart</span><span class="sxs-lookup"><span data-stu-id="88180-1678">debetkaart</span></span> 
- <span data-ttu-id="88180-1679">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="88180-1679">debetkaarten</span></span> 
- <span data-ttu-id="88180-1680">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="88180-1680">debit card</span></span> 
- <span data-ttu-id="88180-1681">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="88180-1681">debit cards</span></span> 
- <span data-ttu-id="88180-1682">debitcard</span><span class="sxs-lookup"><span data-stu-id="88180-1682">debitcard</span></span> 
- <span data-ttu-id="88180-1683">debitcards</span><span class="sxs-lookup"><span data-stu-id="88180-1683">debitcards</span></span> 
- <span data-ttu-id="88180-1684">debito automatico</span><span class="sxs-lookup"><span data-stu-id="88180-1684">debito automatico</span></span> 
- <span data-ttu-id="88180-1685">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="88180-1685">diners club</span></span> 
- <span data-ttu-id="88180-1686">dinersclub</span><span class="sxs-lookup"><span data-stu-id="88180-1686">dinersclub</span></span> 
- <span data-ttu-id="88180-1687">探索</span><span class="sxs-lookup"><span data-stu-id="88180-1687">discover</span></span> 
- <span data-ttu-id="88180-1688">探索卡</span><span class="sxs-lookup"><span data-stu-id="88180-1688">discover card</span></span> 
- <span data-ttu-id="88180-1689">探索卡</span><span class="sxs-lookup"><span data-stu-id="88180-1689">discover cards</span></span> 
- <span data-ttu-id="88180-1690">discovercard</span><span class="sxs-lookup"><span data-stu-id="88180-1690">discovercard</span></span> 
- <span data-ttu-id="88180-1691">discovercards</span><span class="sxs-lookup"><span data-stu-id="88180-1691">discovercards</span></span> 
- <span data-ttu-id="88180-1692">débito automático</span><span class="sxs-lookup"><span data-stu-id="88180-1692">débito automático</span></span>
- <span data-ttu-id="88180-1693">edc</span><span class="sxs-lookup"><span data-stu-id="88180-1693">edc</span></span> 
- <span data-ttu-id="88180-1694">eigentümername</span><span class="sxs-lookup"><span data-stu-id="88180-1694">eigentümername</span></span> 
- <span data-ttu-id="88180-1695">歐洲轉帳卡</span><span class="sxs-lookup"><span data-stu-id="88180-1695">european debit card</span></span> 
- <span data-ttu-id="88180-1696">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="88180-1696">hoofdkaart</span></span> 
- <span data-ttu-id="88180-1697">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="88180-1697">hoofdkaarten</span></span> 
- <span data-ttu-id="88180-1698">在 [viaggio</span><span class="sxs-lookup"><span data-stu-id="88180-1698">in viaggio</span></span> 
- <span data-ttu-id="88180-1699">日文卡機構</span><span class="sxs-lookup"><span data-stu-id="88180-1699">japanese card bureau</span></span> 
- <span data-ttu-id="88180-1700">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="88180-1700">japanse kaartdienst</span></span> 
- <span data-ttu-id="88180-1701">jcb</span><span class="sxs-lookup"><span data-stu-id="88180-1701">jcb</span></span> 
- <span data-ttu-id="88180-1702">kaart</span><span class="sxs-lookup"><span data-stu-id="88180-1702">kaart</span></span> 
- <span data-ttu-id="88180-1703">kaart num</span><span class="sxs-lookup"><span data-stu-id="88180-1703">kaart num</span></span> 
- <span data-ttu-id="88180-1704">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="88180-1704">kaartaantal</span></span> 
- <span data-ttu-id="88180-1705">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="88180-1705">kaartaantallen</span></span> 
- <span data-ttu-id="88180-1706">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="88180-1706">kaarthouder</span></span> 
- <span data-ttu-id="88180-1707">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="88180-1707">kaarthouders</span></span> 
- <span data-ttu-id="88180-1708">karte</span><span class="sxs-lookup"><span data-stu-id="88180-1708">karte</span></span>  
- <span data-ttu-id="88180-1709">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="88180-1709">karteninhaber</span></span> 
- <span data-ttu-id="88180-1710">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="88180-1710">karteninhabers</span></span>
- <span data-ttu-id="88180-1711">kartennr</span><span class="sxs-lookup"><span data-stu-id="88180-1711">kartennr</span></span> 
- <span data-ttu-id="88180-1712">kartennummer</span><span class="sxs-lookup"><span data-stu-id="88180-1712">kartennummer</span></span> 
- <span data-ttu-id="88180-1713">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="88180-1713">kreditkarte</span></span> 
- <span data-ttu-id="88180-1714">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="88180-1714">kreditkarten-nummer</span></span> 
- <span data-ttu-id="88180-1715">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="88180-1715">kreditkarteninhaber</span></span> 
- <span data-ttu-id="88180-1716">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="88180-1716">kreditkarteninstitut</span></span> 
- <span data-ttu-id="88180-1717">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="88180-1717">kreditkartennummer</span></span> 
- <span data-ttu-id="88180-1718">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="88180-1718">kreditkartentyp</span></span> 
- <span data-ttu-id="88180-1719">大師</span><span class="sxs-lookup"><span data-stu-id="88180-1719">maestro</span></span> 
- <span data-ttu-id="88180-1720">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="88180-1720">master card</span></span> 
- <span data-ttu-id="88180-1721">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="88180-1721">master cards</span></span> 
- <span data-ttu-id="88180-1722">mastercard</span><span class="sxs-lookup"><span data-stu-id="88180-1722">mastercard</span></span> 
- <span data-ttu-id="88180-1723">mastercards</span><span class="sxs-lookup"><span data-stu-id="88180-1723">mastercards</span></span> 
- <span data-ttu-id="88180-1724">mc</span><span class="sxs-lookup"><span data-stu-id="88180-1724">mc</span></span> 
- <span data-ttu-id="88180-1725">先生現金</span><span class="sxs-lookup"><span data-stu-id="88180-1725">mister cash</span></span> 
- <span data-ttu-id="88180-1726">n carta</span><span class="sxs-lookup"><span data-stu-id="88180-1726">n carta</span></span> 
- <span data-ttu-id="88180-1727">carta</span><span class="sxs-lookup"><span data-stu-id="88180-1727">carta</span></span> 
- <span data-ttu-id="88180-1728">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1728">no de tarjeta</span></span> 
- <span data-ttu-id="88180-1729">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1729">no do cartao</span></span> 
- <span data-ttu-id="88180-1730">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1730">no do cartão</span></span> 
- <span data-ttu-id="88180-1731">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1731">no.</span></span> <span data-ttu-id="88180-1732">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1732">de tarjeta</span></span> 
- <span data-ttu-id="88180-1733">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1733">no.</span></span> <span data-ttu-id="88180-1734">請勿 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1734">do cartao</span></span> 
- <span data-ttu-id="88180-1735">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1735">no.</span></span> <span data-ttu-id="88180-1736">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1736">do cartão</span></span> 
- <span data-ttu-id="88180-1737">編號 carta</span><span class="sxs-lookup"><span data-stu-id="88180-1737">nr carta</span></span> 
- <span data-ttu-id="88180-1738">編號。</span><span class="sxs-lookup"><span data-stu-id="88180-1738">nr.</span></span> <span data-ttu-id="88180-1739">carta</span><span class="sxs-lookup"><span data-stu-id="88180-1739">carta</span></span> 
- <span data-ttu-id="88180-1740">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1740">numeri di scheda</span></span> 
- <span data-ttu-id="88180-1741">numero carta</span><span class="sxs-lookup"><span data-stu-id="88180-1741">numero carta</span></span> 
- <span data-ttu-id="88180-1742">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1742">numero de cartao</span></span> 
- <span data-ttu-id="88180-1743">numero de 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1743">numero de carte</span></span> 
- <span data-ttu-id="88180-1744">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1744">numero de cartão</span></span> 
- <span data-ttu-id="88180-1745">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1745">numero de tarjeta</span></span>
- <span data-ttu-id="88180-1746">numero della carta</span><span class="sxs-lookup"><span data-stu-id="88180-1746">numero della carta</span></span> 
- <span data-ttu-id="88180-1747">numero di carta</span><span class="sxs-lookup"><span data-stu-id="88180-1747">numero di carta</span></span> 
- <span data-ttu-id="88180-1748">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1748">numero di scheda</span></span> 
- <span data-ttu-id="88180-1749">numero 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1749">numero do cartao</span></span> 
- <span data-ttu-id="88180-1750">numero 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1750">numero do cartão</span></span> 
- <span data-ttu-id="88180-1751">numéro de 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1751">numéro de carte</span></span> 
- <span data-ttu-id="88180-1752">nº carta</span><span class="sxs-lookup"><span data-stu-id="88180-1752">nº carta</span></span> 
- <span data-ttu-id="88180-1753">nº de 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1753">nº de carte</span></span> 
- <span data-ttu-id="88180-1754">nº de la 相關</span><span class="sxs-lookup"><span data-stu-id="88180-1754">nº de la carte</span></span> 
- <span data-ttu-id="88180-1755">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1755">nº de tarjeta</span></span> 
- <span data-ttu-id="88180-1756">nº 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1756">nº do cartao</span></span> 
- <span data-ttu-id="88180-1757">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1757">nº do cartão</span></span> 
- <span data-ttu-id="88180-1758">nº。</span><span class="sxs-lookup"><span data-stu-id="88180-1758">nº.</span></span> <span data-ttu-id="88180-1759">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1759">do cartão</span></span> 
- <span data-ttu-id="88180-1760">número de cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1760">número de cartao</span></span> 
- <span data-ttu-id="88180-1761">número de cartão</span><span class="sxs-lookup"><span data-stu-id="88180-1761">número de cartão</span></span> 
- <span data-ttu-id="88180-1762">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="88180-1762">número de tarjeta</span></span> 
- <span data-ttu-id="88180-1763">número 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="88180-1763">número do cartao</span></span> 
- <span data-ttu-id="88180-1764">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="88180-1764">scheda dell'assegno</span></span> 
- <span data-ttu-id="88180-1765">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="88180-1765">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="88180-1766">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="88180-1766">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="88180-1767">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="88180-1767">scheda della banca</span></span> 
- <span data-ttu-id="88180-1768">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="88180-1768">scheda di controllo</span></span> 
- <span data-ttu-id="88180-1769">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="88180-1769">scheda di debito</span></span> 
- <span data-ttu-id="88180-1770">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="88180-1770">scheda matrice</span></span> 
- <span data-ttu-id="88180-1771">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="88180-1771">schede dell'atmosfera</span></span> 
- <span data-ttu-id="88180-1772">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="88180-1772">schede di controllo</span></span> 
- <span data-ttu-id="88180-1773">schede di debito</span><span class="sxs-lookup"><span data-stu-id="88180-1773">schede di debito</span></span> 
- <span data-ttu-id="88180-1774">schede matrici</span><span class="sxs-lookup"><span data-stu-id="88180-1774">schede matrici</span></span> 
- <span data-ttu-id="88180-1775">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1775">scoprono la scheda</span></span> 
- <span data-ttu-id="88180-1776">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="88180-1776">scoprono le schede</span></span> 
- <span data-ttu-id="88180-1777">solo</span><span class="sxs-lookup"><span data-stu-id="88180-1777">solo</span></span> 
- <span data-ttu-id="88180-1778">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1778">supporti di scheda</span></span> 
- <span data-ttu-id="88180-1779">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1779">supporto di scheda</span></span> 
- <span data-ttu-id="88180-1780">切換</span><span class="sxs-lookup"><span data-stu-id="88180-1780">switch</span></span> 
- <span data-ttu-id="88180-1781">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="88180-1781">tarjeta atm</span></span> 
- <span data-ttu-id="88180-1782">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="88180-1782">tarjeta credito</span></span> 
- <span data-ttu-id="88180-1783">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="88180-1783">tarjeta de atm</span></span> 
- <span data-ttu-id="88180-1784">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="88180-1784">tarjeta de credito</span></span> 
- <span data-ttu-id="88180-1785">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="88180-1785">tarjeta de debito</span></span> 
- <span data-ttu-id="88180-1786">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="88180-1786">tarjeta debito</span></span> 
- <span data-ttu-id="88180-1787">tarjeta 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-1787">tarjeta no</span></span>
- <span data-ttu-id="88180-1788">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="88180-1788">tarjetahabiente</span></span> 
- <span data-ttu-id="88180-1789">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1789">tipo della scheda</span></span> 
- <span data-ttu-id="88180-1790">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="88180-1790">ufficio giapponese della</span></span> 
- <span data-ttu-id="88180-1791">scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1791">scheda</span></span> 
- <span data-ttu-id="88180-1792">v 工資</span><span class="sxs-lookup"><span data-stu-id="88180-1792">v pay</span></span> 
- <span data-ttu-id="88180-1793">v 工資</span><span class="sxs-lookup"><span data-stu-id="88180-1793">v-pay</span></span> 
- <span data-ttu-id="88180-1794">visa</span><span class="sxs-lookup"><span data-stu-id="88180-1794">visa</span></span> 
- <span data-ttu-id="88180-1795">visa 加上</span><span class="sxs-lookup"><span data-stu-id="88180-1795">visa plus</span></span> 
- <span data-ttu-id="88180-1796">visa 電</span><span class="sxs-lookup"><span data-stu-id="88180-1796">visa electron</span></span> 
- <span data-ttu-id="88180-1797">visto</span><span class="sxs-lookup"><span data-stu-id="88180-1797">visto</span></span> 
- <span data-ttu-id="88180-1798">visum</span><span class="sxs-lookup"><span data-stu-id="88180-1798">visum</span></span> 
- <span data-ttu-id="88180-1799">vpay</span><span class="sxs-lookup"><span data-stu-id="88180-1799">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="88180-1800">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="88180-1800">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="88180-1801">卡識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1801">card identification number</span></span>
- <span data-ttu-id="88180-1802">卡片驗證</span><span class="sxs-lookup"><span data-stu-id="88180-1802">card verification</span></span> 
- <span data-ttu-id="88180-1803">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="88180-1803">cardi la verifica</span></span> 
- <span data-ttu-id="88180-1804">cid</span><span class="sxs-lookup"><span data-stu-id="88180-1804">cid</span></span> 
- <span data-ttu-id="88180-1805">cod seg</span><span class="sxs-lookup"><span data-stu-id="88180-1805">cod seg</span></span> 
- <span data-ttu-id="88180-1806">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1806">cod seguranca</span></span> 
- <span data-ttu-id="88180-1807">cod segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1807">cod segurança</span></span> 
- <span data-ttu-id="88180-1808">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1808">cod sicurezza</span></span> 
- <span data-ttu-id="88180-1809">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1809">cod.</span></span> <span data-ttu-id="88180-1810">seg</span><span class="sxs-lookup"><span data-stu-id="88180-1810">seg</span></span> 
- <span data-ttu-id="88180-1811">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1811">cod.</span></span> <span data-ttu-id="88180-1812">seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1812">seguranca</span></span> 
- <span data-ttu-id="88180-1813">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1813">cod.</span></span> <span data-ttu-id="88180-1814">segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1814">segurança</span></span> 
- <span data-ttu-id="88180-1815">cod。</span><span class="sxs-lookup"><span data-stu-id="88180-1815">cod.</span></span> <span data-ttu-id="88180-1816">sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1816">sicurezza</span></span> 
- <span data-ttu-id="88180-1817">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1817">codice di sicurezza</span></span> 
- <span data-ttu-id="88180-1818">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="88180-1818">codice di verifica</span></span> 
- <span data-ttu-id="88180-1819">codigo</span><span class="sxs-lookup"><span data-stu-id="88180-1819">codigo</span></span> 
- <span data-ttu-id="88180-1820">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1820">codigo de seguranca</span></span> 
- <span data-ttu-id="88180-1821">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1821">codigo de segurança</span></span> 
- <span data-ttu-id="88180-1822">crittogramma</span><span class="sxs-lookup"><span data-stu-id="88180-1822">crittogramma</span></span> 
- <span data-ttu-id="88180-1823">密碼</span><span class="sxs-lookup"><span data-stu-id="88180-1823">cryptogram</span></span> 
- <span data-ttu-id="88180-1824">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="88180-1824">cryptogramme</span></span> 
- <span data-ttu-id="88180-1825">cv2</span><span class="sxs-lookup"><span data-stu-id="88180-1825">cv2</span></span> 
- <span data-ttu-id="88180-1826">cvc</span><span class="sxs-lookup"><span data-stu-id="88180-1826">cvc</span></span> 
- <span data-ttu-id="88180-1827">cvc2</span><span class="sxs-lookup"><span data-stu-id="88180-1827">cvc2</span></span> 
- <span data-ttu-id="88180-1828">cvn 驗證</span><span class="sxs-lookup"><span data-stu-id="88180-1828">cvn</span></span> 
- <span data-ttu-id="88180-1829">cvv</span><span class="sxs-lookup"><span data-stu-id="88180-1829">cvv</span></span> 
- <span data-ttu-id="88180-1830">cvv2</span><span class="sxs-lookup"><span data-stu-id="88180-1830">cvv2</span></span> 
- <span data-ttu-id="88180-1831">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1831">cód seguranca</span></span> 
- <span data-ttu-id="88180-1832">cód segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1832">cód segurança</span></span> 
- <span data-ttu-id="88180-1833">cód。</span><span class="sxs-lookup"><span data-stu-id="88180-1833">cód.</span></span> <span data-ttu-id="88180-1834">seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1834">seguranca</span></span> 
- <span data-ttu-id="88180-1835">cód。</span><span class="sxs-lookup"><span data-stu-id="88180-1835">cód.</span></span> <span data-ttu-id="88180-1836">segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1836">segurança</span></span> 
- <span data-ttu-id="88180-1837">código</span><span class="sxs-lookup"><span data-stu-id="88180-1837">código</span></span> 
- <span data-ttu-id="88180-1838">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="88180-1838">código de seguranca</span></span> 
- <span data-ttu-id="88180-1839">código de segurança</span><span class="sxs-lookup"><span data-stu-id="88180-1839">código de segurança</span></span> 
- <span data-ttu-id="88180-1840">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="88180-1840">de kaart controle</span></span> 
- <span data-ttu-id="88180-1841">geeft 編號 uit</span><span class="sxs-lookup"><span data-stu-id="88180-1841">geeft nr uit</span></span> 
- <span data-ttu-id="88180-1842">發出否</span><span class="sxs-lookup"><span data-stu-id="88180-1842">issue no</span></span> 
- <span data-ttu-id="88180-1843">此問題： 數字</span><span class="sxs-lookup"><span data-stu-id="88180-1843">issue number</span></span> 
- <span data-ttu-id="88180-1844">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="88180-1844">kaartidentificatienummer</span></span> 
- <span data-ttu-id="88180-1845">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1845">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="88180-1846">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1846">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="88180-1847">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="88180-1847">kwestieaantal</span></span> 
- <span data-ttu-id="88180-1848">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1848">no.</span></span> <span data-ttu-id="88180-1849">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="88180-1849">dell'edizione</span></span> 
- <span data-ttu-id="88180-1850">無。</span><span class="sxs-lookup"><span data-stu-id="88180-1850">no.</span></span> <span data-ttu-id="88180-1851">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1851">di sicurezza</span></span> 
- <span data-ttu-id="88180-1852">numero de securite</span><span class="sxs-lookup"><span data-stu-id="88180-1852">numero de securite</span></span> 
- <span data-ttu-id="88180-1853">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="88180-1853">numero de verificacao</span></span> 
- <span data-ttu-id="88180-1854">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="88180-1854">numero dell'edizione</span></span> 
- <span data-ttu-id="88180-1855">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="88180-1855">numero di identificazione della</span></span> 
- <span data-ttu-id="88180-1856">scheda</span><span class="sxs-lookup"><span data-stu-id="88180-1856">scheda</span></span> 
- <span data-ttu-id="88180-1857">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="88180-1857">numero di sicurezza</span></span> 
- <span data-ttu-id="88180-1858">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="88180-1858">numero van veiligheid</span></span> 
- <span data-ttu-id="88180-1859">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="88180-1859">numéro de sécurité</span></span> 
- <span data-ttu-id="88180-1860">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="88180-1860">nº autorizzazione</span></span> 
- <span data-ttu-id="88180-1861">número de verificação</span><span class="sxs-lookup"><span data-stu-id="88180-1861">número de verificação</span></span> 
- <span data-ttu-id="88180-1862">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="88180-1862">perno il blocco</span></span> 
- <span data-ttu-id="88180-1863">pin 碼區塊</span><span class="sxs-lookup"><span data-stu-id="88180-1863">pin block</span></span> 
- <span data-ttu-id="88180-1864">prufziffer</span><span class="sxs-lookup"><span data-stu-id="88180-1864">prufziffer</span></span> 
- <span data-ttu-id="88180-1865">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="88180-1865">prüfziffer</span></span> 
- <span data-ttu-id="88180-1866">安全性驗證碼</span><span class="sxs-lookup"><span data-stu-id="88180-1866">security code</span></span> 
- <span data-ttu-id="88180-1867">安全性沒有</span><span class="sxs-lookup"><span data-stu-id="88180-1867">security no</span></span> 
- <span data-ttu-id="88180-1868">安全號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1868">security number</span></span> 
- <span data-ttu-id="88180-1869">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="88180-1869">sicherheits kode</span></span> 
- <span data-ttu-id="88180-1870">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="88180-1870">sicherheitscode</span></span> 
- <span data-ttu-id="88180-1871">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1871">sicherheitsnummer</span></span> 
- <span data-ttu-id="88180-1872">speldblok</span><span class="sxs-lookup"><span data-stu-id="88180-1872">speldblok</span></span> 
- <span data-ttu-id="88180-1873">veiligheid 編號</span><span class="sxs-lookup"><span data-stu-id="88180-1873">veiligheid nr</span></span> 
- <span data-ttu-id="88180-1874">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="88180-1874">veiligheidsaantal</span></span> 
- <span data-ttu-id="88180-1875">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="88180-1875">veiligheidscode</span></span> 
- <span data-ttu-id="88180-1876">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1876">veiligheidsnummer</span></span> 
- <span data-ttu-id="88180-1877">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="88180-1877">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="88180-1878">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="88180-1878">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="88180-1879">ablauf</span><span class="sxs-lookup"><span data-stu-id="88180-1879">ablauf</span></span> 
- <span data-ttu-id="88180-1880">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="88180-1880">data de expiracao</span></span> 
- <span data-ttu-id="88180-1881">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="88180-1881">data de expiração</span></span> 
- <span data-ttu-id="88180-1882">資料 del exp</span><span class="sxs-lookup"><span data-stu-id="88180-1882">data del exp</span></span> 
- <span data-ttu-id="88180-1883">資料 di exp</span><span class="sxs-lookup"><span data-stu-id="88180-1883">data di exp</span></span> 
- <span data-ttu-id="88180-1884">資料 di scadenza</span><span class="sxs-lookup"><span data-stu-id="88180-1884">data di scadenza</span></span> 
- <span data-ttu-id="88180-1885">資料長破折號 que expira</span><span class="sxs-lookup"><span data-stu-id="88180-1885">data em que expira</span></span> 
- <span data-ttu-id="88180-1886">資料 scad</span><span class="sxs-lookup"><span data-stu-id="88180-1886">data scad</span></span> 
- <span data-ttu-id="88180-1887">資料 scadenza</span><span class="sxs-lookup"><span data-stu-id="88180-1887">data scadenza</span></span> 
- <span data-ttu-id="88180-1888">日期 de validité</span><span class="sxs-lookup"><span data-stu-id="88180-1888">date de validité</span></span> 
- <span data-ttu-id="88180-1889">材料 afloop</span><span class="sxs-lookup"><span data-stu-id="88180-1889">datum afloop</span></span> 
- <span data-ttu-id="88180-1890">材料 van exp</span><span class="sxs-lookup"><span data-stu-id="88180-1890">datum van exp</span></span> 
- <span data-ttu-id="88180-1891">de afloop</span><span class="sxs-lookup"><span data-stu-id="88180-1891">de afloop</span></span> 
- <span data-ttu-id="88180-1892">espira</span><span class="sxs-lookup"><span data-stu-id="88180-1892">espira</span></span> 
- <span data-ttu-id="88180-1893">espira</span><span class="sxs-lookup"><span data-stu-id="88180-1893">espira</span></span> 
- <span data-ttu-id="88180-1894">exp 日期</span><span class="sxs-lookup"><span data-stu-id="88180-1894">exp date</span></span> 
- <span data-ttu-id="88180-1895">exp 材料</span><span class="sxs-lookup"><span data-stu-id="88180-1895">exp datum</span></span> 
- <span data-ttu-id="88180-1896">到期日</span><span class="sxs-lookup"><span data-stu-id="88180-1896">expiration</span></span> 
- <span data-ttu-id="88180-1897">到期</span><span class="sxs-lookup"><span data-stu-id="88180-1897">expire</span></span> 
- <span data-ttu-id="88180-1898">到期</span><span class="sxs-lookup"><span data-stu-id="88180-1898">expires</span></span> 
- <span data-ttu-id="88180-1899">到期</span><span class="sxs-lookup"><span data-stu-id="88180-1899">expiry</span></span> 
- <span data-ttu-id="88180-1900">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="88180-1900">fecha de expiracion</span></span> 
- <span data-ttu-id="88180-1901">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="88180-1901">fecha de venc</span></span> 
- <span data-ttu-id="88180-1902">gultig bis</span><span class="sxs-lookup"><span data-stu-id="88180-1902">gultig bis</span></span> 
- <span data-ttu-id="88180-1903">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-1903">gultigkeitsdatum</span></span> 
- <span data-ttu-id="88180-1904">gültig bis</span><span class="sxs-lookup"><span data-stu-id="88180-1904">gültig bis</span></span> 
- <span data-ttu-id="88180-1905">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-1905">gültigkeitsdatum</span></span> 
- <span data-ttu-id="88180-1906">la scadenza</span><span class="sxs-lookup"><span data-stu-id="88180-1906">la scadenza</span></span> 
- <span data-ttu-id="88180-1907">scadenza</span><span class="sxs-lookup"><span data-stu-id="88180-1907">scadenza</span></span> 
- <span data-ttu-id="88180-1908">valable</span><span class="sxs-lookup"><span data-stu-id="88180-1908">valable</span></span> 
- <span data-ttu-id="88180-1909">validade</span><span class="sxs-lookup"><span data-stu-id="88180-1909">validade</span></span> 
- <span data-ttu-id="88180-1910">valido hasta</span><span class="sxs-lookup"><span data-stu-id="88180-1910">valido hasta</span></span> 
- <span data-ttu-id="88180-1911">勇氣</span><span class="sxs-lookup"><span data-stu-id="88180-1911">valor</span></span> 
- <span data-ttu-id="88180-1912">venc</span><span class="sxs-lookup"><span data-stu-id="88180-1912">venc</span></span> 
- <span data-ttu-id="88180-1913">vencimento</span><span class="sxs-lookup"><span data-stu-id="88180-1913">vencimento</span></span> 
- <span data-ttu-id="88180-1914">vencimiento</span><span class="sxs-lookup"><span data-stu-id="88180-1914">vencimiento</span></span> 
- <span data-ttu-id="88180-1915">verloopt</span><span class="sxs-lookup"><span data-stu-id="88180-1915">verloopt</span></span> 
- <span data-ttu-id="88180-1916">vervaldag</span><span class="sxs-lookup"><span data-stu-id="88180-1916">vervaldag</span></span> 
- <span data-ttu-id="88180-1917">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="88180-1917">vervaldatum</span></span> 
- <span data-ttu-id="88180-1918">vto</span><span class="sxs-lookup"><span data-stu-id="88180-1918">vto</span></span> 
- <span data-ttu-id="88180-1919">válido hasta</span><span class="sxs-lookup"><span data-stu-id="88180-1919">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="88180-1920">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-1920">EU Driver's License Number</span></span>

<span data-ttu-id="88180-1921">若要深入了解，請參閱 <<c0>歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88180-1921">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="88180-1922">歐盟國家識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1922">EU National Identification Number</span></span>

<span data-ttu-id="88180-1923">若要深入了解，請參閱 <<c0>歐盟國家識別碼號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88180-1923">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="88180-1924">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1924">EU Passport Number</span></span>

<span data-ttu-id="88180-1925">若要深入了解，請參閱 <<c0>歐盟護照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88180-1925">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="88180-1926">歐盟社會安全號碼或對等項目識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1926">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="88180-1927">若要了解更多，請參閱[歐盟社會安全號碼或對等識別碼敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="88180-1927">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="88180-1928">歐盟稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1928">EU Tax Identification Number</span></span>

<span data-ttu-id="88180-1929">若要深入了解，請參閱 <<c0>歐盟稅務識別號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="88180-1929">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="88180-1930">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-1930">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="88180-1931">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1931">Format</span></span>

<span data-ttu-id="88180-1932">六位數加上字元，指出世紀加上三位數加上檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1932">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1933">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1933">Pattern</span></span>

<span data-ttu-id="88180-1934">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="88180-1934">Pattern must include all of the following:</span></span>
- <span data-ttu-id="88180-1935">格式的六位數，格式為 DDMMYY，專屬於出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-1935">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="88180-1936">世紀標記 (可以是 '-'、 '+' 或 'a')</span><span class="sxs-lookup"><span data-stu-id="88180-1936">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="88180-1937">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-1937">Three-digit personal identification number</span></span> 
- <span data-ttu-id="88180-1938">數字或字母 （不區分大小寫） 這是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1938">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1939">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1939">Checksum</span></span>

<span data-ttu-id="88180-1940">是</span><span class="sxs-lookup"><span data-stu-id="88180-1940">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1941">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1941">Definition</span></span>

<span data-ttu-id="88180-1942">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1942">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1943">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1943">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1944">找不到來自 Keyword_finnish_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1944">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="88180-1945">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-1945">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-1946">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1946">Keywords</span></span>

- <span data-ttu-id="88180-1947">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="88180-1947">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="88180-1948">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="88180-1948">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="88180-1949">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="88180-1949">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="88180-1950">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="88180-1950">Personbeteckning</span></span>
- <span data-ttu-id="88180-1951">Personnummer</span><span class="sxs-lookup"><span data-stu-id="88180-1951">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="88180-1952">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1952">Finland Passport Number</span></span>

<span data-ttu-id="88180-1953">格式的九個字母和數字模式組合九個字母和數字的組合： 兩個字母 （不區分大小寫） 七位數總和檢查碼否定義 DLP 原則是 75%以內，則已偵測到此敏感資訊類型的如果、 內接近性是 300 個字元： 規則運算式 Regex_finland_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1953">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-1954">找不到來自 Keyword_finland_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1954">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="88180-1955"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="88180-1955"></span></span>
<span data-ttu-id="88180-1956">關鍵字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="88180-1956">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="88180-1957">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-1957">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1958">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1958">Format</span></span>

<span data-ttu-id="88180-1959">12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1959">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1960">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1960">Pattern</span></span>

<span data-ttu-id="88180-1961">12 位數驗證以忽略類似模式，例如法國電話號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1961">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1962">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1962">Checksum</span></span>

<span data-ttu-id="88180-1963">否</span><span class="sxs-lookup"><span data-stu-id="88180-1963">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1964">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1964">Definition</span></span>

<span data-ttu-id="88180-1965">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1965">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1966">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1966">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-1967">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="88180-1967">At least one of the following is true:</span></span>
- <span data-ttu-id="88180-1968">找不到來自 Keyword_french_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-1968">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="88180-1969">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-1969">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-1970">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1970">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="88180-1971">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="88180-1971">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="88180-1972">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-1972">drivers licence</span></span>
- <span data-ttu-id="88180-1973">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-1973">drivers license</span></span>
- <span data-ttu-id="88180-1974">driving 授權</span><span class="sxs-lookup"><span data-stu-id="88180-1974">driving licence</span></span>
- <span data-ttu-id="88180-1975">主導授權</span><span class="sxs-lookup"><span data-stu-id="88180-1975">driving license</span></span>
- <span data-ttu-id="88180-1976">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="88180-1976">permis de conduire</span></span>
- <span data-ttu-id="88180-1977">授權數目</span><span class="sxs-lookup"><span data-stu-id="88180-1977">licence number</span></span>
- <span data-ttu-id="88180-1978">駕照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1978">license number</span></span>
- <span data-ttu-id="88180-1979">授權數字</span><span class="sxs-lookup"><span data-stu-id="88180-1979">licence numbers</span></span>
- <span data-ttu-id="88180-1980">照編號</span><span class="sxs-lookup"><span data-stu-id="88180-1980">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="88180-1981">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="88180-1981">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="88180-1982">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1982">Format</span></span>

<span data-ttu-id="88180-1983">12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1983">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1984">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1984">Pattern</span></span>

<span data-ttu-id="88180-1985">12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-1985">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-1986">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-1986">Checksum</span></span>

<span data-ttu-id="88180-1987">否</span><span class="sxs-lookup"><span data-stu-id="88180-1987">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-1988">定義</span><span class="sxs-lookup"><span data-stu-id="88180-1988">Definition</span></span>

<span data-ttu-id="88180-1989">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-1989">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-1990">規則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-1990">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-1991">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-1991">Keywords</span></span>

<span data-ttu-id="88180-1992">無</span><span class="sxs-lookup"><span data-stu-id="88180-1992">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="88180-1993">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-1993">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-1994">Format</span><span class="sxs-lookup"><span data-stu-id="88180-1994">Format</span></span>

<span data-ttu-id="88180-1995">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="88180-1995">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-1996">模式</span><span class="sxs-lookup"><span data-stu-id="88180-1996">Pattern</span></span>

<span data-ttu-id="88180-1997">九個數字和字母：</span><span class="sxs-lookup"><span data-stu-id="88180-1997">Nine digits and letters:</span></span>
- <span data-ttu-id="88180-1998">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-1998">Two digits</span></span> 
- <span data-ttu-id="88180-1999">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-1999">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="88180-2000">五位數</span><span class="sxs-lookup"><span data-stu-id="88180-2000">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2001">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2001">Checksum</span></span>

<span data-ttu-id="88180-2002">否</span><span class="sxs-lookup"><span data-stu-id="88180-2002">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2003">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2003">Definition</span></span>

<span data-ttu-id="88180-2004">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2005">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2005">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2006">找不到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2006">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2007">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2007">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="88180-2008">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="88180-2008">Keyword_passport</span></span>

- <span data-ttu-id="88180-2009">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2009">Passport Number</span></span>
- <span data-ttu-id="88180-2010">Passport 否</span><span class="sxs-lookup"><span data-stu-id="88180-2010">Passport No</span></span>
- <span data-ttu-id="88180-2011">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-2011">Passport #</span></span>
- <span data-ttu-id="88180-2012">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-2012">Passport#</span></span>
- <span data-ttu-id="88180-2013">PassportID</span><span class="sxs-lookup"><span data-stu-id="88180-2013">PassportID</span></span>
- <span data-ttu-id="88180-2014">Passportno</span><span class="sxs-lookup"><span data-stu-id="88180-2014">Passportno</span></span>
- <span data-ttu-id="88180-2015">passportnumber</span><span class="sxs-lookup"><span data-stu-id="88180-2015">passportnumber</span></span>
- <span data-ttu-id="88180-2016">パスポート</span><span class="sxs-lookup"><span data-stu-id="88180-2016">パスポート</span></span>
- <span data-ttu-id="88180-2017">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="88180-2017">パスポート番号</span></span>
- <span data-ttu-id="88180-2018">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="88180-2018">パスポートのNum</span></span>
- <span data-ttu-id="88180-2019">パスポート #</span><span class="sxs-lookup"><span data-stu-id="88180-2019">パスポート ＃</span></span> 
- <span data-ttu-id="88180-2020">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="88180-2020">Numéro de passeport</span></span>
- <span data-ttu-id="88180-2021">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="88180-2021">Passeport n °</span></span>
- <span data-ttu-id="88180-2022">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="88180-2022">Passeport Non</span></span>
- <span data-ttu-id="88180-2023">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-2023">Passeport #</span></span>
- <span data-ttu-id="88180-2024">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-2024">Passeport#</span></span>
- <span data-ttu-id="88180-2025">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="88180-2025">PasseportNon</span></span>
- <span data-ttu-id="88180-2026">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="88180-2026">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="88180-2027">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="88180-2027">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2028">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2028">Format</span></span>

<span data-ttu-id="88180-2029">15 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2029">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2030">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2030">Pattern</span></span>

<span data-ttu-id="88180-2031">必須符合兩個模式之一：</span><span class="sxs-lookup"><span data-stu-id="88180-2031">Must match one of two patterns:</span></span>
- <span data-ttu-id="88180-2032">13 位數後尾隨尾隨兩位數的空間</span><span class="sxs-lookup"><span data-stu-id="88180-2032">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="88180-2033">或</span><span class="sxs-lookup"><span data-stu-id="88180-2033">or</span></span>
- <span data-ttu-id="88180-2034">15 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2034">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2035">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2035">Checksum</span></span>

<span data-ttu-id="88180-2036">是</span><span class="sxs-lookup"><span data-stu-id="88180-2036">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2037">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2037">Definition</span></span>

<span data-ttu-id="88180-2038">DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2038">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2039">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2039">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2040">找不到來自 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2040">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="88180-2041">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2041">The checksum passes.</span></span>

<span data-ttu-id="88180-2042">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2042">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2043">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2043">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2044">找不到來自 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2044">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="88180-2045">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2045">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2046">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2046">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="88180-2047">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="88180-2047">Keyword_fr_insee</span></span>

- <span data-ttu-id="88180-2048">insee</span><span class="sxs-lookup"><span data-stu-id="88180-2048">insee</span></span>
- <span data-ttu-id="88180-2049">securité sociale</span><span class="sxs-lookup"><span data-stu-id="88180-2049">securité sociale</span></span>
- <span data-ttu-id="88180-2050">securite sociale</span><span class="sxs-lookup"><span data-stu-id="88180-2050">securite sociale</span></span>
- <span data-ttu-id="88180-2051">國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2051">national id</span></span>
- <span data-ttu-id="88180-2052">國民身分識別</span><span class="sxs-lookup"><span data-stu-id="88180-2052">national identification</span></span>
- <span data-ttu-id="88180-2053">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="88180-2053">numéro d'identité</span></span>
- <span data-ttu-id="88180-2054">沒有 d'identité</span><span class="sxs-lookup"><span data-stu-id="88180-2054">no d'identité</span></span>
- <span data-ttu-id="88180-2055">無。</span><span class="sxs-lookup"><span data-stu-id="88180-2055">no.</span></span> <span data-ttu-id="88180-2056">d'identité</span><span class="sxs-lookup"><span data-stu-id="88180-2056">d'identité</span></span>
- <span data-ttu-id="88180-2057">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="88180-2057">numero d'identite</span></span>
- <span data-ttu-id="88180-2058">沒有 d'identite</span><span class="sxs-lookup"><span data-stu-id="88180-2058">no d'identite</span></span>
- <span data-ttu-id="88180-2059">無。</span><span class="sxs-lookup"><span data-stu-id="88180-2059">no.</span></span> <span data-ttu-id="88180-2060">d'identite</span><span class="sxs-lookup"><span data-stu-id="88180-2060">d'identite</span></span>
- <span data-ttu-id="88180-2061">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2061">social security number</span></span>
- <span data-ttu-id="88180-2062">社會安全的程式碼</span><span class="sxs-lookup"><span data-stu-id="88180-2062">social security code</span></span>
- <span data-ttu-id="88180-2063">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2063">social insurance number</span></span>
- <span data-ttu-id="88180-2064">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="88180-2064">le numéro d'identification nationale</span></span>
- <span data-ttu-id="88180-2065">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="88180-2065">d'identité nationale</span></span>
- <span data-ttu-id="88180-2066">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="88180-2066">numéro de sécurité sociale</span></span>
- <span data-ttu-id="88180-2067">le 程式碼 de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="88180-2067">le code de la sécurité sociale</span></span>
- <span data-ttu-id="88180-2068">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="88180-2068">numéro d'assurance sociale</span></span>
- <span data-ttu-id="88180-2069">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="88180-2069">numéro de sécu</span></span>
- <span data-ttu-id="88180-2070">程式碼 sécu</span><span class="sxs-lookup"><span data-stu-id="88180-2070">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="88180-2071">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-2071">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2072">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2072">Format</span></span>

<span data-ttu-id="88180-2073">11 個數字和字母的組合</span><span class="sxs-lookup"><span data-stu-id="88180-2073">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2074">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2074">Pattern</span></span>

<span data-ttu-id="88180-2075">11 個數字和字母 （不區分大小寫）：</span><span class="sxs-lookup"><span data-stu-id="88180-2075">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="88180-2076">數字或字母</span><span class="sxs-lookup"><span data-stu-id="88180-2076">A digit or letter</span></span> 
- <span data-ttu-id="88180-2077">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-2077">Two digits</span></span> 
- <span data-ttu-id="88180-2078">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="88180-2078">Six digits or letters</span></span> 
- <span data-ttu-id="88180-2079">數字</span><span class="sxs-lookup"><span data-stu-id="88180-2079">A digit</span></span> 
- <span data-ttu-id="88180-2080">數字或字母</span><span class="sxs-lookup"><span data-stu-id="88180-2080">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2081">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2081">Checksum</span></span>

<span data-ttu-id="88180-2082">是</span><span class="sxs-lookup"><span data-stu-id="88180-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2083">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2083">Definition</span></span>

<span data-ttu-id="88180-2084">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2084">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2085">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2085">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2086">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="88180-2086">At least one of the following is true:</span></span>
    - <span data-ttu-id="88180-2087">找不到來自 Keyword_german_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2087">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="88180-2088">找不到來自 Keyword_german_drivers_license_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2088">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="88180-2089">找不到來自 Keyword_german_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2089">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="88180-2090">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2090">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2091">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2091">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="88180-2092">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="88180-2092">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="88180-2093">Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2093">Führerschein</span></span>
- <span data-ttu-id="88180-2094">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2094">Fuhrerschein</span></span>
- <span data-ttu-id="88180-2095">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2095">Fuehrerschein</span></span>
- <span data-ttu-id="88180-2096">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2096">Führerscheinnummer</span></span>
- <span data-ttu-id="88180-2097">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2097">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="88180-2098">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2098">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="88180-2099">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="88180-2099">Führerschein-</span></span> 
- <span data-ttu-id="88180-2100">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="88180-2100">Fuhrerschein-</span></span> 
- <span data-ttu-id="88180-2101">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="88180-2101">Fuehrerschein-</span></span> 
- <span data-ttu-id="88180-2102">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="88180-2102">FührerscheinnummerNr</span></span>
- <span data-ttu-id="88180-2103">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="88180-2103">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="88180-2104">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="88180-2104">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="88180-2105">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="88180-2105">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="88180-2106">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="88180-2106">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="88180-2107">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="88180-2107">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="88180-2108">Führerschein-編號</span><span class="sxs-lookup"><span data-stu-id="88180-2108">Führerschein- Nr</span></span>
- <span data-ttu-id="88180-2109">Fuhrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="88180-2109">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="88180-2110">Fuehrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="88180-2110">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="88180-2111">Führerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="88180-2111">Führerschein- Klasse</span></span> 
- <span data-ttu-id="88180-2112">Fuhrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="88180-2112">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="88180-2113">Fuehrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="88180-2113">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="88180-2114">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="88180-2114">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="88180-2115">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="88180-2115">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="88180-2116">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="88180-2116">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="88180-2117">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="88180-2117">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="88180-2118">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="88180-2118">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="88180-2119">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="88180-2119">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="88180-2120">Führerschein-編號</span><span class="sxs-lookup"><span data-stu-id="88180-2120">Führerschein- Nr</span></span> 
- <span data-ttu-id="88180-2121">Fuhrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="88180-2121">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="88180-2122">Fuehrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="88180-2122">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="88180-2123">Führerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="88180-2123">Führerschein- Klasse</span></span> 
- <span data-ttu-id="88180-2124">Fuhrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="88180-2124">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="88180-2125">Fuehrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="88180-2125">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="88180-2126">DL</span><span class="sxs-lookup"><span data-stu-id="88180-2126">DL</span></span> 
- <span data-ttu-id="88180-2127">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="88180-2127">DLS</span></span>
- <span data-ttu-id="88180-2128">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="88180-2128">Driv Lic</span></span> 
- <span data-ttu-id="88180-2129">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="88180-2129">Driv Licen</span></span> 
- <span data-ttu-id="88180-2130">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2130">Driv License</span></span>
- <span data-ttu-id="88180-2131">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2131">Driv Licenses</span></span> 
- <span data-ttu-id="88180-2132">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2132">Driv Licence</span></span> 
- <span data-ttu-id="88180-2133">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2133">Driv Licences</span></span> 
- <span data-ttu-id="88180-2134">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="88180-2134">Driv Lic</span></span> 
- <span data-ttu-id="88180-2135">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="88180-2135">Driver Licen</span></span> 
- <span data-ttu-id="88180-2136">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2136">Driver License</span></span> 
- <span data-ttu-id="88180-2137">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2137">Driver Licenses</span></span> 
- <span data-ttu-id="88180-2138">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2138">Driver Licence</span></span> 
- <span data-ttu-id="88180-2139">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2139">Driver Licences</span></span> 
- <span data-ttu-id="88180-2140">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-2140">Drivers Lic</span></span> 
- <span data-ttu-id="88180-2141">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="88180-2141">Drivers Licen</span></span> 
- <span data-ttu-id="88180-2142">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2142">Drivers License</span></span> 
- <span data-ttu-id="88180-2143">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2143">Drivers Licenses</span></span> 
- <span data-ttu-id="88180-2144">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2144">Drivers Licence</span></span> 
- <span data-ttu-id="88180-2145">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2145">Drivers Licences</span></span> 
- <span data-ttu-id="88180-2146">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-2146">Driver's Lic</span></span> 
- <span data-ttu-id="88180-2147">駕 Licen</span><span class="sxs-lookup"><span data-stu-id="88180-2147">Driver's Licen</span></span> 
- <span data-ttu-id="88180-2148">駕照</span><span class="sxs-lookup"><span data-stu-id="88180-2148">Driver's License</span></span> 
- <span data-ttu-id="88180-2149">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-2149">Driver's Licenses</span></span> 
- <span data-ttu-id="88180-2150">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-2150">Driver's Licence</span></span> 
- <span data-ttu-id="88180-2151">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-2151">Driver's Licences</span></span> 
- <span data-ttu-id="88180-2152">主導 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-2152">Driving Lic</span></span> 
- <span data-ttu-id="88180-2153">主導 Licen</span><span class="sxs-lookup"><span data-stu-id="88180-2153">Driving Licen</span></span> 
- <span data-ttu-id="88180-2154">主導授權</span><span class="sxs-lookup"><span data-stu-id="88180-2154">Driving License</span></span> 
- <span data-ttu-id="88180-2155">主導授權</span><span class="sxs-lookup"><span data-stu-id="88180-2155">Driving Licenses</span></span> 
- <span data-ttu-id="88180-2156">Driving 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2156">Driving Licence</span></span> 
- <span data-ttu-id="88180-2157">Driving 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2157">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="88180-2158">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="88180-2158">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="88180-2159">編號 Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2159">Nr-Führerschein</span></span> 
- <span data-ttu-id="88180-2160">編號 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2160">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="88180-2161">編號 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2161">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="88180-2162">否 Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2162">No-Führerschein</span></span> 
- <span data-ttu-id="88180-2163">否 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2163">No-Fuhrerschein</span></span> 
- <span data-ttu-id="88180-2164">否 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2164">No-Fuehrerschein</span></span> 
- <span data-ttu-id="88180-2165">N Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2165">N-Führerschein</span></span> 
- <span data-ttu-id="88180-2166">N Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2166">N-Fuhrerschein</span></span> 
- <span data-ttu-id="88180-2167">N Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2167">N-Fuehrerschein</span></span>
- <span data-ttu-id="88180-2168">編號 Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2168">Nr-Führerschein</span></span> 
- <span data-ttu-id="88180-2169">編號 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2169">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="88180-2170">編號 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2170">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="88180-2171">否 Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2171">No-Führerschein</span></span> 
- <span data-ttu-id="88180-2172">否 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2172">No-Fuhrerschein</span></span> 
- <span data-ttu-id="88180-2173">否 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2173">No-Fuehrerschein</span></span> 
- <span data-ttu-id="88180-2174">N Führerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2174">N-Führerschein</span></span> 
- <span data-ttu-id="88180-2175">N Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2175">N-Fuhrerschein</span></span> 
- <span data-ttu-id="88180-2176">N Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="88180-2176">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="88180-2177">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="88180-2177">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="88180-2178">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-2178">ausstellungsdatum</span></span>
- <span data-ttu-id="88180-2179">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="88180-2179">ausstellungsort</span></span>
- <span data-ttu-id="88180-2180">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="88180-2180">ausstellende behöde</span></span>
- <span data-ttu-id="88180-2181">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="88180-2181">ausstellende behorde</span></span>
- <span data-ttu-id="88180-2182">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="88180-2182">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="88180-2183">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2183">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2184">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2184">Format</span></span>

<span data-ttu-id="88180-2185">10 個數字或字母</span><span class="sxs-lookup"><span data-stu-id="88180-2185">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2186">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2186">Pattern</span></span>

<span data-ttu-id="88180-2187">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="88180-2187">Pattern must include all of the following:</span></span>
- <span data-ttu-id="88180-2188">第一個字元是數字或字母 （C、 F、 G、 H、 J、 K）</span><span class="sxs-lookup"><span data-stu-id="88180-2188">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="88180-2189">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-2189">Three digits</span></span> 
- <span data-ttu-id="88180-2190">五個數字或字母 (C、 H、 J-N、 P、 R、 T、 V Z)</span><span class="sxs-lookup"><span data-stu-id="88180-2190">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="88180-2191">數字</span><span class="sxs-lookup"><span data-stu-id="88180-2191">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2192">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2192">Checksum</span></span>

<span data-ttu-id="88180-2193">是</span><span class="sxs-lookup"><span data-stu-id="88180-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2194">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2194">Definition</span></span>

<span data-ttu-id="88180-2195">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2196">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2196">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2197">找不到來自五個關鍵字清單任一的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2197">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="88180-2198">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2198">The checksum passes.</span></span>

<span data-ttu-id="88180-2199">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2199">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2200">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2200">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2201">找不到來自五個關鍵字清單任一的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2201">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="88180-2202">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2202">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2203">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="88180-2204">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="88180-2204">Keyword_german_passport</span></span>

- <span data-ttu-id="88180-2205">reisepass</span><span class="sxs-lookup"><span data-stu-id="88180-2205">reisepass</span></span>
- <span data-ttu-id="88180-2206">reisepasse</span><span class="sxs-lookup"><span data-stu-id="88180-2206">reisepasse</span></span>
- <span data-ttu-id="88180-2207">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2207">reisepassnummer</span></span>
- <span data-ttu-id="88180-2208">passport</span><span class="sxs-lookup"><span data-stu-id="88180-2208">passport</span></span>
- <span data-ttu-id="88180-2209">護照</span><span class="sxs-lookup"><span data-stu-id="88180-2209">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="88180-2210">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="88180-2210">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="88180-2211">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-2211">geburtsdatum</span></span>
- <span data-ttu-id="88180-2212">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="88180-2212">ausstellungsdatum</span></span>
- <span data-ttu-id="88180-2213">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="88180-2213">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="88180-2214">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="88180-2214">Keyword_german_passport_number</span></span>

<span data-ttu-id="88180-2215">無法對 Reisepass 編號 Reisepass</span><span class="sxs-lookup"><span data-stu-id="88180-2215">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="88180-2216">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="88180-2216">Keyword_german_passport1</span></span>

<span data-ttu-id="88180-2217">Reisepass 編號</span><span class="sxs-lookup"><span data-stu-id="88180-2217">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="88180-2218">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="88180-2218">Keyword_german_passport2</span></span>

<span data-ttu-id="88180-2219">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="88180-2219">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="88180-2220">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2220">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2221">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2221">Format</span></span>

<span data-ttu-id="88180-2222">自從 2010 年 1 年 11 月： 九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="88180-2222">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="88180-2223">從 1 1987 年 31 October 2010: 10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2223">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2224">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2224">Pattern</span></span>

<span data-ttu-id="88180-2225">自從 1 年 11 月 2010 年：</span><span class="sxs-lookup"><span data-stu-id="88180-2225">Since 1 November 2010:</span></span>
- <span data-ttu-id="88180-2226">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2226">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="88180-2227">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-2227">Eight digits</span></span>

<span data-ttu-id="88180-2228">從 1 1987 年 31 October 2010:</span><span class="sxs-lookup"><span data-stu-id="88180-2228">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="88180-2229">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2229">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2230">Checksum</span></span>

<span data-ttu-id="88180-2231">否</span><span class="sxs-lookup"><span data-stu-id="88180-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2232">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2232">Definition</span></span>

<span data-ttu-id="88180-2233">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2233">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2234">規則運算式 Regex_germany_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2234">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2235">找不到來自 Keyword_germany_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2235">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2236">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="88180-2237">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="88180-2237">Keyword_germany_id_card</span></span>

- <span data-ttu-id="88180-2238">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2238">Identity Card</span></span>
- <span data-ttu-id="88180-2239">ID</span><span class="sxs-lookup"><span data-stu-id="88180-2239">ID</span></span>
- <span data-ttu-id="88180-2240">識別</span><span class="sxs-lookup"><span data-stu-id="88180-2240">Identification</span></span>
- <span data-ttu-id="88180-2241">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="88180-2241">Personalausweis</span></span>
- <span data-ttu-id="88180-2242">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2242">Identifizierungsnummer</span></span>
- <span data-ttu-id="88180-2243">Ausweis</span><span class="sxs-lookup"><span data-stu-id="88180-2243">Ausweis</span></span>
- <span data-ttu-id="88180-2244">Identifikation</span><span class="sxs-lookup"><span data-stu-id="88180-2244">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="88180-2245">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2245">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="88180-2246">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2246">Format</span></span>

<span data-ttu-id="88180-2247">7-8 個字母和數字加上破折號的組合</span><span class="sxs-lookup"><span data-stu-id="88180-2247">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2248">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2248">Pattern</span></span>

<span data-ttu-id="88180-2249">七個字母和數字 （舊格式）︰</span><span class="sxs-lookup"><span data-stu-id="88180-2249">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="88180-2250">一個字母 （希臘文的任何字母）</span><span class="sxs-lookup"><span data-stu-id="88180-2250">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="88180-2251">一條虛線</span><span class="sxs-lookup"><span data-stu-id="88180-2251">A dash</span></span> 
- <span data-ttu-id="88180-2252">六位數</span><span class="sxs-lookup"><span data-stu-id="88180-2252">Six digits</span></span>

<span data-ttu-id="88180-2253">八個字母和數字 （新格式）︰</span><span class="sxs-lookup"><span data-stu-id="88180-2253">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="88180-2254">其大寫字元，就會發生在希臘文與拉丁文字母 (ABEZHIKMNOPTYX) 中的兩個字母</span><span class="sxs-lookup"><span data-stu-id="88180-2254">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="88180-2255">一條虛線</span><span class="sxs-lookup"><span data-stu-id="88180-2255">A dash</span></span> 
- <span data-ttu-id="88180-2256">六位數</span><span class="sxs-lookup"><span data-stu-id="88180-2256">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2257">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2257">Checksum</span></span>

<span data-ttu-id="88180-2258">否</span><span class="sxs-lookup"><span data-stu-id="88180-2258">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2259">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2259">Definition</span></span>

<span data-ttu-id="88180-2260">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2261">規則運算式 Regex_greece_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2261">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2262">找不到來自 Keyword_greece_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2262">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2263">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2263">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="88180-2264">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="88180-2264">Keyword_greece_id_card</span></span>

- <span data-ttu-id="88180-2265">希臘文身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2265">Greek identity Card</span></span>
- <span data-ttu-id="88180-2266">Tautotita</span><span class="sxs-lookup"><span data-stu-id="88180-2266">Tautotita</span></span>
- <span data-ttu-id="88180-2267">ΔΕΛΤΊΟ ΑΣΤΥΝΟΜΙΚΉΣ ΤΑΥΤΌΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="88180-2267">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="88180-2268">ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="88180-2268">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="88180-2269">香港身分證 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2269">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2270">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2270">Format</span></span>

<span data-ttu-id="88180-2271">8-9 個字母和數字加上選擇性括住的最後一個字元的組合</span><span class="sxs-lookup"><span data-stu-id="88180-2271">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2272">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2272">Pattern</span></span>

<span data-ttu-id="88180-2273">8-9 個字母的組合：</span><span class="sxs-lookup"><span data-stu-id="88180-2273">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="88180-2274">1-2 個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2274">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="88180-2275">六位數</span><span class="sxs-lookup"><span data-stu-id="88180-2275">Six digits</span></span> 
- <span data-ttu-id="88180-2276">最後一個字元 （任何數字或字母 A），也就是檢查碼 （選擇性） 括住括號。</span><span class="sxs-lookup"><span data-stu-id="88180-2276">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2277">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2277">Checksum</span></span>

<span data-ttu-id="88180-2278">是</span><span class="sxs-lookup"><span data-stu-id="88180-2278">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2279">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2279">Definition</span></span>

<span data-ttu-id="88180-2280">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2281">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2281">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2282">找不到來自 Keyword_hong_kong_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2282">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="88180-2283">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2283">The checksum passes.</span></span>

<span data-ttu-id="88180-2284">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2284">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2285">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2285">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2286">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2286">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2287">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2287">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="88180-2288">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="88180-2288">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="88180-2289">香港身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2289">hong kong identity card</span></span>
- <span data-ttu-id="88180-2290">HKIDC</span><span class="sxs-lookup"><span data-stu-id="88180-2290">HKIDC</span></span>
- <span data-ttu-id="88180-2291">證</span><span class="sxs-lookup"><span data-stu-id="88180-2291">id card</span></span>
- <span data-ttu-id="88180-2292">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2292">identity card</span></span>
- <span data-ttu-id="88180-2293">hk 身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2293">hk identity card</span></span>
- <span data-ttu-id="88180-2294">香港識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2294">hong kong id</span></span>
- <span data-ttu-id="88180-2295">香港身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2295">香港身份證</span></span>
- <span data-ttu-id="88180-2296">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2296">香港永久性居民身份證</span></span>
- <span data-ttu-id="88180-2297">身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2297">身份證</span></span>
- <span data-ttu-id="88180-2298">身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2298">身份証</span></span>
- <span data-ttu-id="88180-2299">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2299">身分證</span></span>
- <span data-ttu-id="88180-2300">身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2300">身分証</span></span>
- <span data-ttu-id="88180-2301">香港身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2301">香港身份証</span></span>
- <span data-ttu-id="88180-2302">香港身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2302">香港身分證</span></span>
- <span data-ttu-id="88180-2303">香港身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2303">香港身分証</span></span>
- <span data-ttu-id="88180-2304">香港身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2304">香港身份證</span></span>
- <span data-ttu-id="88180-2305">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2305">香港居民身份證</span></span>
- <span data-ttu-id="88180-2306">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2306">香港居民身份証</span></span>
- <span data-ttu-id="88180-2307">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2307">香港居民身分證</span></span>
- <span data-ttu-id="88180-2308">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2308">香港居民身分証</span></span>
- <span data-ttu-id="88180-2309">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2309">香港永久性居民身份証</span></span>
- <span data-ttu-id="88180-2310">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2310">香港永久性居民身分證</span></span>
- <span data-ttu-id="88180-2311">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2311">香港永久性居民身分証</span></span>
- <span data-ttu-id="88180-2312">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2312">香港永久性居民身份證</span></span>
- <span data-ttu-id="88180-2313">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2313">香港非永久性居民身份證</span></span>
- <span data-ttu-id="88180-2314">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2314">香港非永久性居民身份証</span></span>
- <span data-ttu-id="88180-2315">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2315">香港非永久性居民身分證</span></span>
- <span data-ttu-id="88180-2316">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2316">香港非永久性居民身分証</span></span>
- <span data-ttu-id="88180-2317">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2317">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="88180-2318">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2318">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="88180-2319">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2319">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="88180-2320">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2320">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="88180-2321">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="88180-2321">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="88180-2322">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="88180-2322">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="88180-2323">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2323">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="88180-2324">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="88180-2324">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="88180-2325">印度永久帳戶號碼 (PAN)</span><span class="sxs-lookup"><span data-stu-id="88180-2325">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2326">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2326">Format</span></span>

<span data-ttu-id="88180-2327">10 個字母或四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2327">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2328">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2328">Pattern</span></span>

<span data-ttu-id="88180-2329">10 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="88180-2329">10 letters or digits:</span></span>
- <span data-ttu-id="88180-2330">五個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2330">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="88180-2331">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2331">Four digits</span></span> 
- <span data-ttu-id="88180-2332">這是一個字母檢查碼的字母</span><span class="sxs-lookup"><span data-stu-id="88180-2332">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2333">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2333">Checksum</span></span>

<span data-ttu-id="88180-2334">是</span><span class="sxs-lookup"><span data-stu-id="88180-2334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2335">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2335">Definition</span></span>

<span data-ttu-id="88180-2336">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2337">規則運算式 Regex_india_permanent_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2337">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2338">找不到來自 Keyword_india_permanent_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2338">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="88180-2339">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2339">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2340">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2340">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="88180-2341">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="88180-2341">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="88180-2342">永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2342">Permanent Account Number</span></span> 
- <span data-ttu-id="88180-2343">PAN</span><span class="sxs-lookup"><span data-stu-id="88180-2343">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="88180-2344">印度唯一識別 （aadhaar） 碼數字</span><span class="sxs-lookup"><span data-stu-id="88180-2344">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2345">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2345">Format</span></span>

<span data-ttu-id="88180-2346">12 位數包含選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-2346">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2347">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2347">Pattern</span></span>

<span data-ttu-id="88180-2348">12 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2348">12 digits:</span></span>
- <span data-ttu-id="88180-2349">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2349">Four digits</span></span> 
- <span data-ttu-id="88180-2350">選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-2350">An optional space or dash</span></span> 
- <span data-ttu-id="88180-2351">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2351">Four digits</span></span> 
- <span data-ttu-id="88180-2352">選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-2352">An optional space or dash</span></span> 
- <span data-ttu-id="88180-2353">最後一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2353">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2354">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2354">Checksum</span></span>

<span data-ttu-id="88180-2355">是</span><span class="sxs-lookup"><span data-stu-id="88180-2355">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2356">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2356">Definition</span></span>

<span data-ttu-id="88180-2357">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2357">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-2358">找不到來自 Keyword_india_aadhar 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2358">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="88180-2359">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2359">The checksum passes.</span></span>
<span data-ttu-id="88180-2360">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-2361">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2361">The checksum passes.</span></span>
<span data-ttu-id="88180-2362"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="88180-2362"></span></span>

### <a name="keywords"></a><span data-ttu-id="88180-2363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2363">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="88180-2364">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="88180-2364">Keyword_india_aadhar</span></span>
- <span data-ttu-id="88180-2365">Aadhar</span><span class="sxs-lookup"><span data-stu-id="88180-2365">Aadhar</span></span>
- <span data-ttu-id="88180-2366">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="88180-2366">Aadhaar</span></span>
- <span data-ttu-id="88180-2367">UID</span><span class="sxs-lookup"><span data-stu-id="88180-2367">UID</span></span>
- <span data-ttu-id="88180-2368">आधार</span><span class="sxs-lookup"><span data-stu-id="88180-2368">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="88180-2369">印尼身分識 (Ktp) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2369">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2370">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2370">Format</span></span>

<span data-ttu-id="88180-2371">16 位數包含選擇性句點</span><span class="sxs-lookup"><span data-stu-id="88180-2371">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2372">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2372">Pattern</span></span>

<span data-ttu-id="88180-2373">16 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2373">16 digits:</span></span>
- <span data-ttu-id="88180-2374">二位數省代碼</span><span class="sxs-lookup"><span data-stu-id="88180-2374">Two-digit province code</span></span> 
- <span data-ttu-id="88180-2375">句點 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="88180-2375">A period (optional)</span></span> 
- <span data-ttu-id="88180-2376">二位數攝政或城市代碼</span><span class="sxs-lookup"><span data-stu-id="88180-2376">Two-digit regency or city code</span></span> 
- <span data-ttu-id="88180-2377">二位數次行政區代碼</span><span class="sxs-lookup"><span data-stu-id="88180-2377">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="88180-2378">句點 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="88180-2378">A period (optional)</span></span> 
- <span data-ttu-id="88180-2379">DDMMYY 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-2379">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="88180-2380">句點 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="88180-2380">A period (optional)</span></span> 
- <span data-ttu-id="88180-2381">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2381">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2382">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2382">Checksum</span></span>

<span data-ttu-id="88180-2383">否</span><span class="sxs-lookup"><span data-stu-id="88180-2383">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2384">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2384">Definition</span></span>

<span data-ttu-id="88180-2385">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2386">規則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2386">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2387">找不到來自 Keyword_indonesia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2387">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="88180-2388">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2388">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2389">規則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2389">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2390">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2390">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="88180-2391">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="88180-2391">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="88180-2392">KTP</span><span class="sxs-lookup"><span data-stu-id="88180-2392">KTP</span></span>
- <span data-ttu-id="88180-2393">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="88180-2393">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="88180-2394">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="88180-2394">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="88180-2395">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="88180-2395">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2396">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2396">Format</span></span>

<span data-ttu-id="88180-2397">國碼/地區碼 （兩個字母） 加上檢查碼 （兩位數） 再加上 bban （最多 30 個字元）</span><span class="sxs-lookup"><span data-stu-id="88180-2397">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2398">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2398">Pattern</span></span>

<span data-ttu-id="88180-2399">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="88180-2399">Pattern must include all of the following:</span></span>

- <span data-ttu-id="88180-2400">兩個字母的國碼/地區碼</span><span class="sxs-lookup"><span data-stu-id="88180-2400">Two-letter country code</span></span>
- <span data-ttu-id="88180-2401">兩位數檢查碼 （後面接著一個選用空格）</span><span class="sxs-lookup"><span data-stu-id="88180-2401">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="88180-2402">1-7 組四字母或數字 （可以以空格分隔）</span><span class="sxs-lookup"><span data-stu-id="88180-2402">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="88180-2403">1-3 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="88180-2403">1-3 letters or digits</span></span>

<span data-ttu-id="88180-2404">每個國家/地區的格式是稍有不同。</span><span class="sxs-lookup"><span data-stu-id="88180-2404">The format for each country is slightly different.</span></span> <span data-ttu-id="88180-2405">IBAN 敏感資訊類型涵蓋這些 60 國家/地區：</span><span class="sxs-lookup"><span data-stu-id="88180-2405">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="88180-2406">ad、 ae、 al，在亞利桑那州，ba，是，bg、 bh、 頻道、 cr、 cy、 cz、 de、 粗、 執行、 卻、 es、 wi-fi、 於、 fr、 gb、 ge、 gi、 gl、 /gr、 hr、 hu，ie，il，是，它、 kw、 kz、 lb、 li、 lt、 lu、 lv，mc md、 我、 mk、 mr、 細明體、 記憶nl、 [否] pl、 pt、 ro、 rs、 sa、 se、 si、 sk、 sm、 tn、.msnavedit-linkcell、 vg</span><span class="sxs-lookup"><span data-stu-id="88180-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2407">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2407">Checksum</span></span>

<span data-ttu-id="88180-2408">是</span><span class="sxs-lookup"><span data-stu-id="88180-2408">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2409">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2409">Definition</span></span>

<span data-ttu-id="88180-2410">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2410">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2411">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2411">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2412">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2412">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2413">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2413">Keywords</span></span>

<span data-ttu-id="88180-2414">無</span><span class="sxs-lookup"><span data-stu-id="88180-2414">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="88180-2415">IP 位址</span><span class="sxs-lookup"><span data-stu-id="88180-2415">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="88180-2416">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2416">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="88180-2417">IPv4:</span><span class="sxs-lookup"><span data-stu-id="88180-2417">IPv4:</span></span>
<span data-ttu-id="88180-2418">帳戶版格式化 （句點） 和未格式化 （無句點） 之 IPv4 位址的複雜模式</span><span class="sxs-lookup"><span data-stu-id="88180-2418">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="88180-2419">IPv6:</span><span class="sxs-lookup"><span data-stu-id="88180-2419">IPv6:</span></span>
<span data-ttu-id="88180-2420">哪一個帳戶表示格式化 IPv6 號碼 （其中包含冒號） 的複雜模式</span><span class="sxs-lookup"><span data-stu-id="88180-2420">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2421">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2421">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2422">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2422">Checksum</span></span>

<span data-ttu-id="88180-2423">否</span><span class="sxs-lookup"><span data-stu-id="88180-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2424">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2424">Definition</span></span>

<span data-ttu-id="88180-2425">對於 IPv6 為 DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2425">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2426">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2426">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2427">找不到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2427">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="88180-2428">DLP 原則是 95%以內，已偵測到此敏感資訊類型的對於 IPv4，如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2428">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2429">規則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2429">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2430">找不到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2430">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="88180-2431">對於 IPv6 為 DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2431">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2432">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2432">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2433">找不到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2433">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2434">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2434">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="88180-2435">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="88180-2435">Keyword_ipaddress</span></span>

- <span data-ttu-id="88180-2436">IP （此關鍵字是區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2436">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="88180-2437">ip 位址</span><span class="sxs-lookup"><span data-stu-id="88180-2437">ip address</span></span> 
- <span data-ttu-id="88180-2438">ip 位址</span><span class="sxs-lookup"><span data-stu-id="88180-2438">ip addresses</span></span>
- <span data-ttu-id="88180-2439">網際網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="88180-2439">internet protocol</span></span>
- <span data-ttu-id="88180-2440">IP כתובת ה</span><span class="sxs-lookup"><span data-stu-id="88180-2440">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="88180-2441">國際分類的治療法 （ICD-10-公分）</span><span class="sxs-lookup"><span data-stu-id="88180-2441">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2442">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2442">Format</span></span>

<span data-ttu-id="88180-2443">Dictionary</span><span class="sxs-lookup"><span data-stu-id="88180-2443">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2444">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2444">Pattern</span></span>

<span data-ttu-id="88180-2445">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2445">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2446">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2446">Checksum</span></span>

<span data-ttu-id="88180-2447">否</span><span class="sxs-lookup"><span data-stu-id="88180-2447">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2448">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2448">Definition</span></span>

<span data-ttu-id="88180-2449">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2449">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2450">找不到來自 Dictionary_icd_10_cm 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2450">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="88180-2451">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2451">Keywords</span></span>

<span data-ttu-id="88180-2452">任何字詞從 Dictionary_icd_10_cm 關鍵字字典，這根據[治療法的國際分類、 十分之一修訂，臨床修改 （ICD-10-公分）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="88180-2452">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="88180-2453">此類型只會尋找該字詞，不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="88180-2453">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="88180-2454">國際分類的治療法 （ICD-9-公分）</span><span class="sxs-lookup"><span data-stu-id="88180-2454">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2455">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2455">Format</span></span>

<span data-ttu-id="88180-2456">Dictionary</span><span class="sxs-lookup"><span data-stu-id="88180-2456">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2457">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2457">Pattern</span></span>

<span data-ttu-id="88180-2458">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2458">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2459">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2459">Checksum</span></span>

<span data-ttu-id="88180-2460">否</span><span class="sxs-lookup"><span data-stu-id="88180-2460">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2461">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2461">Definition</span></span>

<span data-ttu-id="88180-2462">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2462">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2463">找不到來自 Dictionary_icd_9_cm 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2463">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2464">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2464">Keywords</span></span>

<span data-ttu-id="88180-2465">任何字詞從 Dictionary_icd_9_cm 關鍵字字典，這根據[治療法的國際分類、 二十九個修訂，臨床修改 （ICD-9-公分）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="88180-2465">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="88180-2466">此類型只會尋找該字詞，不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="88180-2466">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="88180-2467">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2467">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2468">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2468">Format</span></span>

<span data-ttu-id="88180-2469">舊格式 （直到 2012 年 31):</span><span class="sxs-lookup"><span data-stu-id="88180-2469">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="88180-2470">七位數後尾隨 1-2 個字母</span><span class="sxs-lookup"><span data-stu-id="88180-2470">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="88180-2471">新格式 (1 Jan 2013 年):</span><span class="sxs-lookup"><span data-stu-id="88180-2471">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="88180-2472">七位數後尾隨兩個字母</span><span class="sxs-lookup"><span data-stu-id="88180-2472">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2473">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2473">Pattern</span></span>

<span data-ttu-id="88180-2474">舊格式 （直到 2012 年 31):</span><span class="sxs-lookup"><span data-stu-id="88180-2474">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="88180-2475">七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2475">Seven digits</span></span> 
- <span data-ttu-id="88180-2476">1-2 個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2476">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="88180-2477">新格式 (1 Jan 2013 年):</span><span class="sxs-lookup"><span data-stu-id="88180-2477">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="88180-2478">七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2478">Seven digits</span></span> 
- <span data-ttu-id="88180-2479">字母 （不區分大小寫） 這是一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2479">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="88180-2480">字母"A"或者"H"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2480">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2481">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2481">Checksum</span></span>

<span data-ttu-id="88180-2482">是</span><span class="sxs-lookup"><span data-stu-id="88180-2482">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2483">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2483">Definition</span></span>

<span data-ttu-id="88180-2484">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2485">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2485">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2486">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="88180-2486">One of the following is true:</span></span>
    - <span data-ttu-id="88180-2487">找不到來自 Keyword_ireland_pps 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2487">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="88180-2488">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-2488">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="88180-2489">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2489">The checksum passes.</span></span>

<span data-ttu-id="88180-2490">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2490">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2491">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2491">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2492">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2492">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2493">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2493">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="88180-2494">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="88180-2494">Keyword_ireland_pps</span></span>

- <span data-ttu-id="88180-2495">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2495">Personal Public Service Number</span></span> 
- <span data-ttu-id="88180-2496">PPS 數目</span><span class="sxs-lookup"><span data-stu-id="88180-2496">PPS Number</span></span> 
- <span data-ttu-id="88180-2497">PPS Num</span><span class="sxs-lookup"><span data-stu-id="88180-2497">PPS Num</span></span> 
- <span data-ttu-id="88180-2498">PPS [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2498">PPS No.</span></span> 
- <span data-ttu-id="88180-2499">PPS #</span><span class="sxs-lookup"><span data-stu-id="88180-2499">PPS #</span></span> 
- <span data-ttu-id="88180-2500">PPS #</span><span class="sxs-lookup"><span data-stu-id="88180-2500">PPS#</span></span> 
- <span data-ttu-id="88180-2501">PPSN</span><span class="sxs-lookup"><span data-stu-id="88180-2501">PPSN</span></span> 
- <span data-ttu-id="88180-2502">公用服務卡</span><span class="sxs-lookup"><span data-stu-id="88180-2502">Public Services Card</span></span> 
- <span data-ttu-id="88180-2503">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="88180-2503">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="88180-2504">Uimh。</span><span class="sxs-lookup"><span data-stu-id="88180-2504">Uimh.</span></span> <span data-ttu-id="88180-2505">PSP</span><span class="sxs-lookup"><span data-stu-id="88180-2505">PSP</span></span> 
- <span data-ttu-id="88180-2506">PSP</span><span class="sxs-lookup"><span data-stu-id="88180-2506">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="88180-2507">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2507">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2508">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2508">Format</span></span>

<span data-ttu-id="88180-2509">13 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2509">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2510">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2510">Pattern</span></span>

<span data-ttu-id="88180-2511">格式：</span><span class="sxs-lookup"><span data-stu-id="88180-2511">Formatted:</span></span>
- <span data-ttu-id="88180-2512">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-2512">Two digits</span></span> 
- <span data-ttu-id="88180-2513">一條虛線</span><span class="sxs-lookup"><span data-stu-id="88180-2513">A dash</span></span> 
- <span data-ttu-id="88180-2514">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-2514">Three digits</span></span> 
- <span data-ttu-id="88180-2515">一條虛線</span><span class="sxs-lookup"><span data-stu-id="88180-2515">A dash</span></span> 
- <span data-ttu-id="88180-2516">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-2516">Eight digits</span></span>

<span data-ttu-id="88180-2517">格式化：</span><span class="sxs-lookup"><span data-stu-id="88180-2517">Unformatted:</span></span>
- <span data-ttu-id="88180-2518">13 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2518">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2519">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2519">Checksum</span></span>

<span data-ttu-id="88180-2520">否</span><span class="sxs-lookup"><span data-stu-id="88180-2520">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2521">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2521">Definition</span></span>

<span data-ttu-id="88180-2522">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2523">規則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2523">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2524">找不到來自 Keyword_israel_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2524">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2525">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2525">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="88180-2526">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="88180-2526">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="88180-2527">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2527">Bank Account Number</span></span> 
- <span data-ttu-id="88180-2528">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-2528">Bank Account</span></span> 
- <span data-ttu-id="88180-2529">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2529">Account Number</span></span> 
- <span data-ttu-id="88180-2530">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="88180-2530">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="88180-2531">以色列國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2531">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="88180-2532">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2532">Format</span></span>

<span data-ttu-id="88180-2533">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-2533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2534">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2534">Pattern</span></span>

<span data-ttu-id="88180-2535">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2536">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2536">Checksum</span></span>

<span data-ttu-id="88180-2537">是</span><span class="sxs-lookup"><span data-stu-id="88180-2537">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2538">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2538">Definition</span></span>

<span data-ttu-id="88180-2539">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2540">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2540">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2541">找不到來自 Keyword_Israel_National_ID 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2541">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="88180-2542">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2542">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2543">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2543">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="88180-2544">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="88180-2544">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="88180-2545">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="88180-2545">מספר זהות</span></span> 
- <span data-ttu-id="88180-2546">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2546">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="88180-2547">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-2547">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2548">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2548">Format</span></span>

<span data-ttu-id="88180-2549">10 個字母和數字的組合</span><span class="sxs-lookup"><span data-stu-id="88180-2549">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2550">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2550">Pattern</span></span>

- <span data-ttu-id="88180-2551">10 個字母和數字的組合：</span><span class="sxs-lookup"><span data-stu-id="88180-2551">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="88180-2552">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2552">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="88180-2553">字母"A"或者"V"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2553">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="88180-2554">七個字母 （不區分大小寫）、 數字或底線字元</span><span class="sxs-lookup"><span data-stu-id="88180-2554">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="88180-2555">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2555">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2556">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2556">Checksum</span></span>

<span data-ttu-id="88180-2557">否</span><span class="sxs-lookup"><span data-stu-id="88180-2557">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2558">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2558">Definition</span></span>

<span data-ttu-id="88180-2559">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2559">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2560">規則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2560">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2561">找不到來自 Keyword_italy_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2561">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2562">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2562">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="88180-2563">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="88180-2563">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="88180-2564">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="88180-2564">numero di patente di guida</span></span> 
- <span data-ttu-id="88180-2565">patente di guida</span><span class="sxs-lookup"><span data-stu-id="88180-2565">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="88180-2566">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2566">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2567">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2567">Format</span></span>

<span data-ttu-id="88180-2568">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2568">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2569">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2569">Pattern</span></span>

<span data-ttu-id="88180-2570">銀行帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="88180-2570">Bank account number:</span></span>
- <span data-ttu-id="88180-2571">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2571">Seven or eight digits</span></span>
- <span data-ttu-id="88180-2572">銀行帳戶分行代碼：</span><span class="sxs-lookup"><span data-stu-id="88180-2572">Bank account branch code:</span></span>
- <span data-ttu-id="88180-2573">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2573">Four digits</span></span> 
- <span data-ttu-id="88180-2574">一個空格或破折號 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="88180-2574">A space or dash (optional)</span></span> 
- <span data-ttu-id="88180-2575">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-2575">Three digits</span></span>

<span data-ttu-id="88180-2576">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2576">Checksum</span></span>

<span data-ttu-id="88180-2577">否</span><span class="sxs-lookup"><span data-stu-id="88180-2577">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2578">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2578">Definition</span></span>

<span data-ttu-id="88180-2579">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2580">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2580">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2581">找不到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2581">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="88180-2582">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="88180-2582">One of the following is true:</span></span>
- <span data-ttu-id="88180-2583">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2583">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2584">找不到來自 Keyword_jp_bank_branch_code 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2584">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="88180-2585">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2586">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2586">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2587">找不到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2587">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2588">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2588">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="88180-2589">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="88180-2589">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="88180-2590">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2590">Checking Account Number</span></span> 
- <span data-ttu-id="88180-2591">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-2591">Checking Account</span></span> 
- <span data-ttu-id="88180-2592">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-2592">Checking Account #</span></span> 
- <span data-ttu-id="88180-2593">檢查 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="88180-2593">Checking Acct Number</span></span> 
- <span data-ttu-id="88180-2594">檢查 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-2594">Checking Acct #</span></span> 
- <span data-ttu-id="88180-2595">檢查 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2595">Checking Acct No.</span></span> 
- <span data-ttu-id="88180-2596">檢查帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2596">Checking Account No.</span></span> 
- <span data-ttu-id="88180-2597">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2597">Bank Account Number</span></span> 
- <span data-ttu-id="88180-2598">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-2598">Bank Account</span></span> 
- <span data-ttu-id="88180-2599">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-2599">Bank Account #</span></span> 
- <span data-ttu-id="88180-2600">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2600">Bank Acct Number</span></span> 
- <span data-ttu-id="88180-2601">銀行 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-2601">Bank Acct #</span></span> 
- <span data-ttu-id="88180-2602">銀行 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2602">Bank Acct No.</span></span> 
- <span data-ttu-id="88180-2603">銀行帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2603">Bank Account No.</span></span> 
- <span data-ttu-id="88180-2604">節省帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2604">Savings Account Number</span></span> 
- <span data-ttu-id="88180-2605">存款帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-2605">Savings Account</span></span> 
- <span data-ttu-id="88180-2606">節省帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-2606">Savings Account #</span></span> 
- <span data-ttu-id="88180-2607">節省 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="88180-2607">Savings Acct Number</span></span> 
- <span data-ttu-id="88180-2608">節省 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-2608">Savings Acct #</span></span> 
- <span data-ttu-id="88180-2609">節省 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2609">Savings Acct No.</span></span> 
- <span data-ttu-id="88180-2610">存款帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2610">Savings Account No.</span></span> 
- <span data-ttu-id="88180-2611">轉帳帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2611">Debit Account Number</span></span> 
- <span data-ttu-id="88180-2612">轉帳帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-2612">Debit Account</span></span> 
- <span data-ttu-id="88180-2613">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-2613">Debit Account #</span></span> 
- <span data-ttu-id="88180-2614">轉帳 Acct 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2614">Debit Acct Number</span></span> 
- <span data-ttu-id="88180-2615">借方 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-2615">Debit Acct #</span></span> 
- <span data-ttu-id="88180-2616">轉帳 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2616">Debit Acct No.</span></span> 
- <span data-ttu-id="88180-2617">轉帳帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2617">Debit Account No.</span></span> 
- <span data-ttu-id="88180-2618">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="88180-2618">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="88180-2619"># アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="88180-2619">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="88180-2620">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="88180-2620">＃勘定の確認</span></span> 
- <span data-ttu-id="88180-2621">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="88180-2621">勘定番号の確認</span></span> 
- <span data-ttu-id="88180-2622">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="88180-2622">口座番号の確認</span></span> 
- <span data-ttu-id="88180-2623">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2623">銀行口座番号</span></span> 
- <span data-ttu-id="88180-2624">銀行口座</span><span class="sxs-lookup"><span data-stu-id="88180-2624">銀行口座</span></span> 
- <span data-ttu-id="88180-2625">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="88180-2625">銀行口座＃</span></span> 
- <span data-ttu-id="88180-2626">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="88180-2626">銀行の勘定番号</span></span> 
- <span data-ttu-id="88180-2627">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="88180-2627">銀行のacct＃</span></span> 
- <span data-ttu-id="88180-2628">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="88180-2628">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="88180-2629">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2629">銀行口座番号</span></span>
- <span data-ttu-id="88180-2630">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2630">普通預金口座番号</span></span> 
- <span data-ttu-id="88180-2631">預金口座</span><span class="sxs-lookup"><span data-stu-id="88180-2631">預金口座</span></span> 
- <span data-ttu-id="88180-2632">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="88180-2632">貯蓄口座＃</span></span> 
- <span data-ttu-id="88180-2633">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="88180-2633">貯蓄勘定の数</span></span> 
- <span data-ttu-id="88180-2634">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="88180-2634">貯蓄勘定＃</span></span> 
- <span data-ttu-id="88180-2635">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="88180-2635">貯蓄勘定番号</span></span> 
- <span data-ttu-id="88180-2636">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2636">普通預金口座番号</span></span> 
- <span data-ttu-id="88180-2637">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2637">引き落とし口座番号</span></span> 
- <span data-ttu-id="88180-2638">口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2638">口座番号</span></span> 
- <span data-ttu-id="88180-2639">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="88180-2639">口座番号＃</span></span> 
- <span data-ttu-id="88180-2640">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="88180-2640">デビットのacct番号</span></span> 
- <span data-ttu-id="88180-2641">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="88180-2641">デビット勘定＃</span></span> 
- <span data-ttu-id="88180-2642">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="88180-2642">デビットACCTの番号</span></span> 
- <span data-ttu-id="88180-2643">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="88180-2643">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="88180-2644">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="88180-2644">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="88180-2645">Otemachi</span><span class="sxs-lookup"><span data-stu-id="88180-2645">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="88180-2646">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-2646">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2647">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2647">Format</span></span>

<span data-ttu-id="88180-2648">12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2648">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2649">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2649">Pattern</span></span>

<span data-ttu-id="88180-2650">12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2650">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2651">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2651">Checksum</span></span>

<span data-ttu-id="88180-2652">否</span><span class="sxs-lookup"><span data-stu-id="88180-2652">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2653">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2653">Definition</span></span>

<span data-ttu-id="88180-2654">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2654">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2655">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2655">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2656">找不到來自 Keyword_jp_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2656">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2657">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2657">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="88180-2658">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="88180-2658">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="88180-2659">dl #</span><span class="sxs-lookup"><span data-stu-id="88180-2659">dl#</span></span> 
- <span data-ttu-id="88180-2660">DL #</span><span class="sxs-lookup"><span data-stu-id="88180-2660">DL＃</span></span> 
- <span data-ttu-id="88180-2661">dl #</span><span class="sxs-lookup"><span data-stu-id="88180-2661">dls#</span></span> 
- <span data-ttu-id="88180-2662">DL #</span><span class="sxs-lookup"><span data-stu-id="88180-2662">DLS＃</span></span> 
- <span data-ttu-id="88180-2663">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2663">driver license</span></span> 
- <span data-ttu-id="88180-2664">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2664">driver licenses</span></span> 
- <span data-ttu-id="88180-2665">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2665">drivers license</span></span> 
- <span data-ttu-id="88180-2666">駕照</span><span class="sxs-lookup"><span data-stu-id="88180-2666">driver's license</span></span> 
- <span data-ttu-id="88180-2667">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-2667">drivers licenses</span></span> 
- <span data-ttu-id="88180-2668">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-2668">driver's licenses</span></span> 
- <span data-ttu-id="88180-2669">driving 授權</span><span class="sxs-lookup"><span data-stu-id="88180-2669">driving licence</span></span> 
- <span data-ttu-id="88180-2670">lic #</span><span class="sxs-lookup"><span data-stu-id="88180-2670">lic#</span></span> 
- <span data-ttu-id="88180-2671">LIC #</span><span class="sxs-lookup"><span data-stu-id="88180-2671">LIC＃</span></span> 
- <span data-ttu-id="88180-2672">lics #</span><span class="sxs-lookup"><span data-stu-id="88180-2672">lics#</span></span> 
- <span data-ttu-id="88180-2673">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2673">state id</span></span> 
- <span data-ttu-id="88180-2674">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2674">state identification</span></span> 
- <span data-ttu-id="88180-2675">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2675">state identification number</span></span> 
- <span data-ttu-id="88180-2676">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="88180-2676">低所得国＃</span></span> 
- <span data-ttu-id="88180-2677">免許証</span><span class="sxs-lookup"><span data-stu-id="88180-2677">免許証</span></span> 
- <span data-ttu-id="88180-2678">状態ID</span><span class="sxs-lookup"><span data-stu-id="88180-2678">状態ID</span></span>
- <span data-ttu-id="88180-2679">状態の識別</span><span class="sxs-lookup"><span data-stu-id="88180-2679">状態の識別</span></span> 
- <span data-ttu-id="88180-2680">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="88180-2680">状態の識別番号</span></span> 
- <span data-ttu-id="88180-2681">運転免許</span><span class="sxs-lookup"><span data-stu-id="88180-2681">運転免許</span></span> 
- <span data-ttu-id="88180-2682">運転免許証</span><span class="sxs-lookup"><span data-stu-id="88180-2682">運転免許証</span></span> 
- <span data-ttu-id="88180-2683">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="88180-2683">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="88180-2684">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2684">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2685">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2685">Format</span></span>

<span data-ttu-id="88180-2686">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2686">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2687">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2687">Pattern</span></span>

<span data-ttu-id="88180-2688">兩個字母 （不區分大小寫） 尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2688">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2689">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2689">Checksum</span></span>

<span data-ttu-id="88180-2690">否</span><span class="sxs-lookup"><span data-stu-id="88180-2690">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2691">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2691">Definition</span></span>

<span data-ttu-id="88180-2692">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2692">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2693">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2693">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2694">找不到來自 Keyword_jp_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2694">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2695">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2695">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="88180-2696">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="88180-2696">Keyword_jp_passport</span></span>

- <span data-ttu-id="88180-2697">パスポート</span><span class="sxs-lookup"><span data-stu-id="88180-2697">パスポート</span></span> 
- <span data-ttu-id="88180-2698">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="88180-2698">パスポート番号</span></span> 
- <span data-ttu-id="88180-2699">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="88180-2699">パスポートのNum</span></span> 
- <span data-ttu-id="88180-2700">パスポート #</span><span class="sxs-lookup"><span data-stu-id="88180-2700">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="88180-2701">日本常駐居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2701">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2702">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2702">Format</span></span>

<span data-ttu-id="88180-2703">11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2703">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2704">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2704">Pattern</span></span>

<span data-ttu-id="88180-2705">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2705">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2706">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2706">Checksum</span></span>

<span data-ttu-id="88180-2707">否</span><span class="sxs-lookup"><span data-stu-id="88180-2707">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2708">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2708">Definition</span></span>

<span data-ttu-id="88180-2709">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2709">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2710">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2710">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2711">找不到來自 Keyword_jp_resident_registration_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2711">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2712">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2712">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="88180-2713">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="88180-2713">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="88180-2714">常駐居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2714">Resident Registration Number</span></span>
- <span data-ttu-id="88180-2715">駐留註冊數目</span><span class="sxs-lookup"><span data-stu-id="88180-2715">Resident Register Number</span></span> 
- <span data-ttu-id="88180-2716">居民基本登錄數目</span><span class="sxs-lookup"><span data-stu-id="88180-2716">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="88180-2717">居民登記 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2717">Resident Registration No.</span></span> 
- <span data-ttu-id="88180-2718">駐留註冊 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2718">Resident Register No.</span></span> 
- <span data-ttu-id="88180-2719">居民基本登錄 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2719">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="88180-2720">基本居民註冊 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2720">Basic Resident Register No.</span></span> 
- <span data-ttu-id="88180-2721">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="88180-2721">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="88180-2722">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="88180-2722">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="88180-2723">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="88180-2723">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="88180-2724">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="88180-2724">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="88180-2725">日本社會保險號碼 (SIN)</span><span class="sxs-lookup"><span data-stu-id="88180-2725">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2726">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2726">Format</span></span>

<span data-ttu-id="88180-2727">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2727">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2728">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2728">Pattern</span></span>

<span data-ttu-id="88180-2729">7-12 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2729">7-12 digits:</span></span>
- <span data-ttu-id="88180-2730">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2730">Four digits</span></span> 
- <span data-ttu-id="88180-2731">連字號 （選用）</span><span class="sxs-lookup"><span data-stu-id="88180-2731">A hyphen (optional)</span></span> 
- <span data-ttu-id="88180-2732">六位數或</span><span class="sxs-lookup"><span data-stu-id="88180-2732">Six digits OR</span></span>
- <span data-ttu-id="88180-2733">7-12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2733">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2734">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2734">Checksum</span></span>

<span data-ttu-id="88180-2735">否</span><span class="sxs-lookup"><span data-stu-id="88180-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2736">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2736">Definition</span></span>

<span data-ttu-id="88180-2737">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2737">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2738">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2738">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2739">找不到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2739">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="88180-2740">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2740">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2741">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2741">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2742">找不到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2742">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2743">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2743">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="88180-2744">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="88180-2744">Keyword_jp_sin</span></span>

- <span data-ttu-id="88180-2745">社會保險 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-2745">Social Insurance No.</span></span> 
- <span data-ttu-id="88180-2746">社會保險 Num</span><span class="sxs-lookup"><span data-stu-id="88180-2746">Social Insurance Num</span></span> 
- <span data-ttu-id="88180-2747">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2747">Social Insurance Number</span></span> 
- <span data-ttu-id="88180-2748">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="88180-2748">社会保険のテンキー</span></span> 
- <span data-ttu-id="88180-2749">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="88180-2749">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="88180-2750">日文居住地證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2750">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2751">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2751">Format</span></span>

<span data-ttu-id="88180-2752">12 個字母和數字</span><span class="sxs-lookup"><span data-stu-id="88180-2752">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2753">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2753">Pattern</span></span>

<span data-ttu-id="88180-2754">12 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="88180-2754">12 letters and digits:</span></span>
- <span data-ttu-id="88180-2755">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2755">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="88180-2756">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-2756">Eight digits</span></span> 
- <span data-ttu-id="88180-2757">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-2757">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2758">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2758">Checksum</span></span>

<span data-ttu-id="88180-2759">否</span><span class="sxs-lookup"><span data-stu-id="88180-2759">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2760">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2760">Definition</span></span>

<span data-ttu-id="88180-2761">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2761">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2762">規則運算式 Regex_jp_residence_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2762">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2763">找不到來自 Keyword_jp_residence_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2763">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2764">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2764">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="88180-2765">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="88180-2765">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="88180-2766">居住地證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2766">Residence card number</span></span>
- <span data-ttu-id="88180-2767">居住地卡否</span><span class="sxs-lookup"><span data-stu-id="88180-2767">Residence card no</span></span>
- <span data-ttu-id="88180-2768">居住地卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-2768">Residence card #</span></span>
- <span data-ttu-id="88180-2769">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="88180-2769">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="88180-2770">馬來西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2770">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2771">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2771">Format</span></span>

<span data-ttu-id="88180-2772">12 位數包含選擇性連字號</span><span class="sxs-lookup"><span data-stu-id="88180-2772">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2773">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2773">Pattern</span></span>

<span data-ttu-id="88180-2774">12 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2774">12 digits:</span></span>
- <span data-ttu-id="88180-2775">YYMMDD 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-2775">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="88180-2776">一個破折號 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="88180-2776">A dash (optional)</span></span> 
- <span data-ttu-id="88180-2777">雙字母的出生地代碼</span><span class="sxs-lookup"><span data-stu-id="88180-2777">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="88180-2778">一個破折號 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="88180-2778">A dash (optional)</span></span> 
- <span data-ttu-id="88180-2779">三個隨機的數字</span><span class="sxs-lookup"><span data-stu-id="88180-2779">Three random digits</span></span> 
- <span data-ttu-id="88180-2780">一位數性別代碼</span><span class="sxs-lookup"><span data-stu-id="88180-2780">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2781">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2781">Checksum</span></span>

<span data-ttu-id="88180-2782">否</span><span class="sxs-lookup"><span data-stu-id="88180-2782">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2783">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2783">Definition</span></span>

<span data-ttu-id="88180-2784">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2785">規則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2785">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2786">找不到來自 Keyword_malaysia_id_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2786">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2787">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2787">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="88180-2788">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="88180-2788">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="88180-2789">數位應用程式卡</span><span class="sxs-lookup"><span data-stu-id="88180-2789">digital application card</span></span>
- <span data-ttu-id="88180-2790">我 /c</span><span class="sxs-lookup"><span data-stu-id="88180-2790">i/c</span></span>
- <span data-ttu-id="88180-2791">我 /c 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-2791">i/c no</span></span>
- <span data-ttu-id="88180-2792">ic</span><span class="sxs-lookup"><span data-stu-id="88180-2792">ic</span></span>
- <span data-ttu-id="88180-2793">ic 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-2793">ic no</span></span>
- <span data-ttu-id="88180-2794">證</span><span class="sxs-lookup"><span data-stu-id="88180-2794">id card</span></span>
- <span data-ttu-id="88180-2795">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-2795">identification Card</span></span>
- <span data-ttu-id="88180-2796">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2796">identity card</span></span>
- <span data-ttu-id="88180-2797">k/p</span><span class="sxs-lookup"><span data-stu-id="88180-2797">k/p</span></span>
- <span data-ttu-id="88180-2798">k/p 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-2798">k/p no</span></span>
- <span data-ttu-id="88180-2799">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="88180-2799">kad akuan diri</span></span>
- <span data-ttu-id="88180-2800">kad aplikasi 數位</span><span class="sxs-lookup"><span data-stu-id="88180-2800">kad aplikasi digital</span></span>
- <span data-ttu-id="88180-2801">kad pengenalan 馬來西亞</span><span class="sxs-lookup"><span data-stu-id="88180-2801">kad pengenalan malaysia</span></span>
- <span data-ttu-id="88180-2802">kp</span><span class="sxs-lookup"><span data-stu-id="88180-2802">kp</span></span>
- <span data-ttu-id="88180-2803">kp 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-2803">kp no</span></span>
- <span data-ttu-id="88180-2804">mykad</span><span class="sxs-lookup"><span data-stu-id="88180-2804">mykad</span></span>
- <span data-ttu-id="88180-2805">mykas</span><span class="sxs-lookup"><span data-stu-id="88180-2805">mykas</span></span>
- <span data-ttu-id="88180-2806">mykid</span><span class="sxs-lookup"><span data-stu-id="88180-2806">mykid</span></span>
- <span data-ttu-id="88180-2807">mypr</span><span class="sxs-lookup"><span data-stu-id="88180-2807">mypr</span></span>
- <span data-ttu-id="88180-2808">mytentera</span><span class="sxs-lookup"><span data-stu-id="88180-2808">mytentera</span></span>
- <span data-ttu-id="88180-2809">馬來西亞身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2809">malaysia identity card</span></span>
- <span data-ttu-id="88180-2810">馬來西亞身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2810">malaysian identity card</span></span>
- <span data-ttu-id="88180-2811">nric</span><span class="sxs-lookup"><span data-stu-id="88180-2811">nric</span></span>
- <span data-ttu-id="88180-2812">個人識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-2812">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="88180-2813">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2813">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2814">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2814">Format</span></span>

<span data-ttu-id="88180-2815">8-9 位數包含選擇性空格</span><span class="sxs-lookup"><span data-stu-id="88180-2815">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2816">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2816">Pattern</span></span>

<span data-ttu-id="88180-2817">8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2817">8-9 digits:</span></span>
- <span data-ttu-id="88180-2818">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-2818">Three digits</span></span> 
- <span data-ttu-id="88180-2819">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="88180-2819">A space (optional)</span></span> 
- <span data-ttu-id="88180-2820">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-2820">Three digits</span></span> 
- <span data-ttu-id="88180-2821">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="88180-2821">A space (optional)</span></span> 
- <span data-ttu-id="88180-2822">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2822">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2823">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2823">Checksum</span></span>

<span data-ttu-id="88180-2824">是</span><span class="sxs-lookup"><span data-stu-id="88180-2824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2825">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2825">Definition</span></span>

<span data-ttu-id="88180-2826">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2826">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2827">函數 Func_netherlands_bsn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2827">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2828">找不到來自 Keyword_netherlands_bsn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2828">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="88180-2829">函數 Func_eu_date2 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-2829">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="88180-2830">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2830">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2831">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2831">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="88180-2832">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="88180-2832">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="88180-2833">公民健保號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2833">Citizen service number</span></span> 
- <span data-ttu-id="88180-2834">BSN</span><span class="sxs-lookup"><span data-stu-id="88180-2834">BSN</span></span> 
- <span data-ttu-id="88180-2835">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="88180-2835">Burgerservicenummer</span></span> 
- <span data-ttu-id="88180-2836">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="88180-2836">Sofinummer</span></span> 
- <span data-ttu-id="88180-2837">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="88180-2837">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="88180-2838">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2838">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="88180-2839">紐西蘭衛生部編號</span><span class="sxs-lookup"><span data-stu-id="88180-2839">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2840">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2840">Format</span></span>

<span data-ttu-id="88180-2841">三個字母、 一個空格 （選用） 和四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2841">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2842">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2842">Pattern</span></span>

<span data-ttu-id="88180-2843">三個字母 （不區分大小寫） 的空間 （選用） 四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2843">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2844">Checksum</span></span>

<span data-ttu-id="88180-2845">是</span><span class="sxs-lookup"><span data-stu-id="88180-2845">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2846">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2846">Definition</span></span>

<span data-ttu-id="88180-2847">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2848">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2848">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2849">找不到來自 Keyword_nz_terms 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2849">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="88180-2850">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2850">The checksum passes.</span></span>

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

<span data-ttu-id="88180-2851">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2851">Keywords</span></span>

<span data-ttu-id="88180-2852">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="88180-2852">Keyword_nz_terms</span></span>

- <span data-ttu-id="88180-2853">NHI</span><span class="sxs-lookup"><span data-stu-id="88180-2853">NHI</span></span> 
- <span data-ttu-id="88180-2854">JPRatingExplicitAllowed</span><span class="sxs-lookup"><span data-stu-id="88180-2854">New Zealand</span></span> 
- <span data-ttu-id="88180-2855">健康情況</span><span class="sxs-lookup"><span data-stu-id="88180-2855">Health</span></span> 
- <span data-ttu-id="88180-2856">處理方式</span><span class="sxs-lookup"><span data-stu-id="88180-2856">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="88180-2857">挪威識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2857">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2858">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2858">Format</span></span>

<span data-ttu-id="88180-2859">11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2859">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2860">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2860">Pattern</span></span>

<span data-ttu-id="88180-2861">11 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2861">11 digits:</span></span>
- <span data-ttu-id="88180-2862">DDMMYY 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-2862">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="88180-2863">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2863">Three-digit individual number</span></span> 
- <span data-ttu-id="88180-2864">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2864">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2865">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2865">Checksum</span></span>

<span data-ttu-id="88180-2866">是</span><span class="sxs-lookup"><span data-stu-id="88180-2866">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2867">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2867">Definition</span></span>

<span data-ttu-id="88180-2868">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2868">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2869">函數 Func_norway_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2869">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2870">找不到來自 Keyword_norway_id_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2870">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="88180-2871">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2871">The checksum passes.</span></span>
- <span data-ttu-id="88180-2872">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2873">函數 Func_norway_id_numbe 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2873">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2874">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2874">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2875">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2875">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="88180-2876">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="88180-2876">Keyword_norway_id_number</span></span>

- <span data-ttu-id="88180-2877">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2877">Personal identification number</span></span>
- <span data-ttu-id="88180-2878">挪威文識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2878">Norwegian ID Number</span></span>
- <span data-ttu-id="88180-2879">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2879">ID Number</span></span>
- <span data-ttu-id="88180-2880">識別</span><span class="sxs-lookup"><span data-stu-id="88180-2880">Identification</span></span>
- <span data-ttu-id="88180-2881">Personnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2881">Personnummer</span></span>
- <span data-ttu-id="88180-2882">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="88180-2882">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="88180-2883">菲律賓統一多用途 ID 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2883">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2884">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2884">Format</span></span>

<span data-ttu-id="88180-2885">以連字號分隔的 12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2885">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2886">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2886">Pattern</span></span>

<span data-ttu-id="88180-2887">12 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-2887">12 digits:</span></span>
- <span data-ttu-id="88180-2888">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-2888">Four digits</span></span> 
- <span data-ttu-id="88180-2889">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-2889">A hyphen</span></span> 
- <span data-ttu-id="88180-2890">七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2890">Seven digits</span></span> 
- <span data-ttu-id="88180-2891">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-2891">A hyphen</span></span> 
- <span data-ttu-id="88180-2892">一位數</span><span class="sxs-lookup"><span data-stu-id="88180-2892">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2893">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2893">Checksum</span></span>

<span data-ttu-id="88180-2894">否</span><span class="sxs-lookup"><span data-stu-id="88180-2894">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2895">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2895">Definition</span></span>

<span data-ttu-id="88180-2896">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2896">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2897">規則運算式 Regex_philippines_unified_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2897">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2898">找不到來自 Keyword_philippines_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2898">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2899">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2899">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="88180-2900">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="88180-2900">Keyword_philippines_id</span></span>

- <span data-ttu-id="88180-2901">統一多用途識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2901">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="88180-2902">UMID</span><span class="sxs-lookup"><span data-stu-id="88180-2902">UMID</span></span> 
- <span data-ttu-id="88180-2903">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2903">Identity Card</span></span> 
- <span data-ttu-id="88180-2904">Pinag isang 多 Layunin 識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2904">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="88180-2905">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="88180-2905">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="88180-2906">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2906">Format</span></span>

<span data-ttu-id="88180-2907">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="88180-2907">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2908">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2908">Pattern</span></span>

<span data-ttu-id="88180-2909">三個字母 （不區分大小寫） 尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="88180-2909">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2910">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2910">Checksum</span></span>

<span data-ttu-id="88180-2911">是</span><span class="sxs-lookup"><span data-stu-id="88180-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2912">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2912">Definition</span></span>

<span data-ttu-id="88180-2913">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_polish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2913">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="88180-2914">找不到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2914">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="88180-2915">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2915">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2916">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2916">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="88180-2917">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="88180-2917">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="88180-2918">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="88180-2918">Dowód osobisty</span></span>
- <span data-ttu-id="88180-2919">數目 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="88180-2919">Numer dowodu osobistego</span></span>
- <span data-ttu-id="88180-2920">Nazwa 我數目 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="88180-2920">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="88180-2921">Nazwa 我編號 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="88180-2921">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="88180-2922">Nazwa 我編號 dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="88180-2922">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="88180-2923">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="88180-2923">Dowód Tożsamości</span></span>
- <span data-ttu-id="88180-2924">dow。</span><span class="sxs-lookup"><span data-stu-id="88180-2924">dow.</span></span> <span data-ttu-id="88180-2925">os。</span><span class="sxs-lookup"><span data-stu-id="88180-2925">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="88180-2926">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="88180-2926">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="88180-2927">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2927">Format</span></span>

<span data-ttu-id="88180-2928">11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2928">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2929">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2929">Pattern</span></span>

<span data-ttu-id="88180-2930">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2930">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2931">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2931">Checksum</span></span>

<span data-ttu-id="88180-2932">是</span><span class="sxs-lookup"><span data-stu-id="88180-2932">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2933">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2933">Definition</span></span>

<span data-ttu-id="88180-2934">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2934">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2935">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2935">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2936">找不到來自 Keyword_pesel_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2936">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="88180-2937">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2937">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2938">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2938">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="88180-2939">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="88180-2939">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="88180-2940">編號 PESEL</span><span class="sxs-lookup"><span data-stu-id="88180-2940">Nr PESEL</span></span>
- <span data-ttu-id="88180-2941">PESEL</span><span class="sxs-lookup"><span data-stu-id="88180-2941">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="88180-2942">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="88180-2942">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="88180-2943">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2943">Format</span></span>

<span data-ttu-id="88180-2944">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2944">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2945">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2945">Pattern</span></span>

<span data-ttu-id="88180-2946">兩個字母 （不區分大小寫） 尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="88180-2946">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2947">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2947">Checksum</span></span>

<span data-ttu-id="88180-2948">是</span><span class="sxs-lookup"><span data-stu-id="88180-2948">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2949">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2949">Definition</span></span>

<span data-ttu-id="88180-2950">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2950">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2951">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2951">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2952">找不到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2952">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="88180-2953">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-2953">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2954">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2954">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="88180-2955">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="88180-2955">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="88180-2956">數目 paszportu</span><span class="sxs-lookup"><span data-stu-id="88180-2956">Numer paszportu</span></span>
- <span data-ttu-id="88180-2957">編號。</span><span class="sxs-lookup"><span data-stu-id="88180-2957">Nr.</span></span> <span data-ttu-id="88180-2958">Paszportu</span><span class="sxs-lookup"><span data-stu-id="88180-2958">Paszportu</span></span>
- <span data-ttu-id="88180-2959">Paszport</span><span class="sxs-lookup"><span data-stu-id="88180-2959">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="88180-2960">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2960">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2961">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2961">Format</span></span>

<span data-ttu-id="88180-2962">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-2962">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2963">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2963">Pattern</span></span>

<span data-ttu-id="88180-2964">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-2964">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2965">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2965">Checksum</span></span>

<span data-ttu-id="88180-2966">否</span><span class="sxs-lookup"><span data-stu-id="88180-2966">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2967">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2967">Definition</span></span>

<span data-ttu-id="88180-2968">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2969">規則運算式 Regex_portugal_citizen_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2969">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2970">找不到來自 Keyword_portugal_citizen_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2970">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-2971">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2971">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="88180-2972">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="88180-2972">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="88180-2973">公民證</span><span class="sxs-lookup"><span data-stu-id="88180-2973">Citizen Card</span></span>
- <span data-ttu-id="88180-2974">國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2974">National ID Card</span></span>
- <span data-ttu-id="88180-2975">副本</span><span class="sxs-lookup"><span data-stu-id="88180-2975">CC</span></span>
- <span data-ttu-id="88180-2976">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="88180-2976">Cartão de Cidadão</span></span>
- <span data-ttu-id="88180-2977">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="88180-2977">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="88180-2978">沙烏地阿拉伯國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-2978">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="88180-2979">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2979">Format</span></span>

<span data-ttu-id="88180-2980">10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-2980">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2981">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2981">Pattern</span></span>

<span data-ttu-id="88180-2982">10 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-2982">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-2983">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-2983">Checksum</span></span>

<span data-ttu-id="88180-2984">否</span><span class="sxs-lookup"><span data-stu-id="88180-2984">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-2985">定義</span><span class="sxs-lookup"><span data-stu-id="88180-2985">Definition</span></span>

<span data-ttu-id="88180-2986">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-2987">規則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-2987">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-2988">找不到來自 Keyword_saudi_arabia_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-2988">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-2989">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-2989">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="88180-2990">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="88180-2990">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="88180-2991">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-2991">Identification Card</span></span> 
- <span data-ttu-id="88180-2992">我介面卡數目</span><span class="sxs-lookup"><span data-stu-id="88180-2992">I card number</span></span> 
- <span data-ttu-id="88180-2993">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-2993">ID number</span></span> 
- <span data-ttu-id="88180-2994">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="88180-2994">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="88180-2995">新加坡國民登記身分證 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-2995">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-2996">Format</span><span class="sxs-lookup"><span data-stu-id="88180-2996">Format</span></span>

<span data-ttu-id="88180-2997">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="88180-2997">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-2998">模式</span><span class="sxs-lookup"><span data-stu-id="88180-2998">Pattern</span></span>

- <span data-ttu-id="88180-2999">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="88180-2999">Nine letters and digits:</span></span>
- <span data-ttu-id="88180-3000">字母"F"、"G"、"S"或"T"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-3000">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="88180-3001">七位數</span><span class="sxs-lookup"><span data-stu-id="88180-3001">Seven digits</span></span> 
- <span data-ttu-id="88180-3002">一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3002">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3003">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3003">Checksum</span></span>

<span data-ttu-id="88180-3004">是</span><span class="sxs-lookup"><span data-stu-id="88180-3004">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3005">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3005">Definition</span></span>

<span data-ttu-id="88180-3006">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3006">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3007">規則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3007">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3008">找不到來自 Keyword_singapore_nric 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3008">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="88180-3009">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3009">The checksum passes.</span></span>

<span data-ttu-id="88180-3010">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3010">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3011">規則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3011">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3012">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3012">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3013">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3013">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="88180-3014">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="88180-3014">Keyword_singapore_nric</span></span>

- <span data-ttu-id="88180-3015">國民登記身分證</span><span class="sxs-lookup"><span data-stu-id="88180-3015">National Registration Identity Card</span></span> 
- <span data-ttu-id="88180-3016">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3016">Identity Card Number</span></span> 
- <span data-ttu-id="88180-3017">NRIC</span><span class="sxs-lookup"><span data-stu-id="88180-3017">NRIC</span></span> 
- <span data-ttu-id="88180-3018">IC</span><span class="sxs-lookup"><span data-stu-id="88180-3018">IC</span></span> 
- <span data-ttu-id="88180-3019">外部識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3019">Foreign Identification Number</span></span> 
- <span data-ttu-id="88180-3020">FIN</span><span class="sxs-lookup"><span data-stu-id="88180-3020">FIN</span></span> 
- <span data-ttu-id="88180-3021">身份证</span><span class="sxs-lookup"><span data-stu-id="88180-3021">身份证</span></span> 
- <span data-ttu-id="88180-3022">身份證</span><span class="sxs-lookup"><span data-stu-id="88180-3022">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="88180-3023">南非識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3023">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3024">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3024">Format</span></span>

<span data-ttu-id="88180-3025">可以包含空格的 13 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3025">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3026">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3026">Pattern</span></span>

<span data-ttu-id="88180-3027">13 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-3027">13 digits:</span></span>
- <span data-ttu-id="88180-3028">YYMMDD 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3028">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="88180-3029">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-3029">Four digits</span></span> 
- <span data-ttu-id="88180-3030">一位數公民指標</span><span class="sxs-lookup"><span data-stu-id="88180-3030">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="88180-3031">數字"8"或"9"</span><span class="sxs-lookup"><span data-stu-id="88180-3031">The digit "8" or "9"</span></span> 
- <span data-ttu-id="88180-3032">一位數總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3032">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3033">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3033">Checksum</span></span>

<span data-ttu-id="88180-3034">是</span><span class="sxs-lookup"><span data-stu-id="88180-3034">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3035">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3035">Definition</span></span>

<span data-ttu-id="88180-3036">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3036">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3037">函數 Func_south_africa_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3037">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3038">找不到來自 Keyword_south_africa_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3038">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="88180-3039">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3039">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3040">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3040">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="88180-3041">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="88180-3041">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="88180-3042">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-3042">Identity card</span></span>
- <span data-ttu-id="88180-3043">ID</span><span class="sxs-lookup"><span data-stu-id="88180-3043">ID</span></span>
- <span data-ttu-id="88180-3044">識別</span><span class="sxs-lookup"><span data-stu-id="88180-3044">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="88180-3045">南韓居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3045">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3046">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3046">Format</span></span>

<span data-ttu-id="88180-3047">13 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="88180-3047">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3048">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3048">Pattern</span></span>

<span data-ttu-id="88180-3049">13 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-3049">13 digits:</span></span>
- <span data-ttu-id="88180-3050">YYMMDD 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3050">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="88180-3051">連字號</span><span class="sxs-lookup"><span data-stu-id="88180-3051">A hyphen</span></span> 
- <span data-ttu-id="88180-3052">由世紀與性別判定的一位數</span><span class="sxs-lookup"><span data-stu-id="88180-3052">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="88180-3053">四位數出生地區碼</span><span class="sxs-lookup"><span data-stu-id="88180-3053">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="88180-3054">一位數，用來區分其前幾碼皆相同的人員</span><span class="sxs-lookup"><span data-stu-id="88180-3054">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="88180-3055">檢查碼。</span><span class="sxs-lookup"><span data-stu-id="88180-3055">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3056">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3056">Checksum</span></span>

<span data-ttu-id="88180-3057">是</span><span class="sxs-lookup"><span data-stu-id="88180-3057">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3058">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3058">Definition</span></span>

<span data-ttu-id="88180-3059">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3059">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3060">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3060">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3061">找不到來自 Keyword_south_korea_resident_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3061">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="88180-3062">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3062">The checksum passes.</span></span>

<span data-ttu-id="88180-3063">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3063">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3064">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3064">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3065">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3065">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3066">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3066">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="88180-3067">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="88180-3067">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="88180-3068">國民身分證</span><span class="sxs-lookup"><span data-stu-id="88180-3068">National ID card</span></span> 
- <span data-ttu-id="88180-3069">公民登記號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3069">Citizen's Registration Number</span></span> 
- <span data-ttu-id="88180-3070">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="88180-3070">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="88180-3071">RRN</span><span class="sxs-lookup"><span data-stu-id="88180-3071">RRN</span></span> 
- <span data-ttu-id="88180-3072">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="88180-3072">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="88180-3073">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="88180-3073">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-3074">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3074">Format</span></span>

<span data-ttu-id="88180-3075">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3075">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3076">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3076">Pattern</span></span>

<span data-ttu-id="88180-3077">11-12 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-3077">11-12 digits:</span></span>
- <span data-ttu-id="88180-3078">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3078">Two digits</span></span> 
- <span data-ttu-id="88180-3079">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="88180-3079">A forward slash (optional)</span></span> 
- <span data-ttu-id="88180-3080">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3080">7-8 digits</span></span> 
- <span data-ttu-id="88180-3081">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="88180-3081">A forward slash (optional)</span></span> 
- <span data-ttu-id="88180-3082">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3082">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3083">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3083">Checksum</span></span>

<span data-ttu-id="88180-3084">是</span><span class="sxs-lookup"><span data-stu-id="88180-3084">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3085">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3085">Definition</span></span>

<span data-ttu-id="88180-3086">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3086">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3087">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3087">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3088">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3088">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3089">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3089">Keywords</span></span>

<span data-ttu-id="88180-3090">無</span><span class="sxs-lookup"><span data-stu-id="88180-3090">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="88180-3091">SQL Server 連線字串</span><span class="sxs-lookup"><span data-stu-id="88180-3091">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="88180-3092">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3092">Format</span></span>

<span data-ttu-id="88180-3093">字串 「 使用者 Id 」、 「 使用者 ID 」、 「 uid 」 或 「 使用者識別碼 」 後面跟著字元和下列模式中所述的字串。</span><span class="sxs-lookup"><span data-stu-id="88180-3093">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3094">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3094">Pattern</span></span>

- <span data-ttu-id="88180-3095">字串 「 使用者 Id 」、 「 使用者 ID 」、 「 uid 」 或者 「 UserId 」</span><span class="sxs-lookup"><span data-stu-id="88180-3095">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="88180-3096">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="88180-3096">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="88180-3097">將字串 「 密碼 」 或 「 pwd 」 不的小寫字母前面 「 pwd 」</span><span class="sxs-lookup"><span data-stu-id="88180-3097">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="88180-3098">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-3098">An equal sign (=)</span></span>
- <span data-ttu-id="88180-3099">任何不錢幣符號 （$）、 百分比符號 （%），大於符號 (>) 符號字元 (@)、 引號 （"）、 分號 （;）、 左大括弧 ([]) 或左大括弧 （{}）</span><span class="sxs-lookup"><span data-stu-id="88180-3099">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="88180-3100">不是以分號 （;） 的 7-128 個字元的任何組合反斜線 （/） 或雙引號 （"）</span><span class="sxs-lookup"><span data-stu-id="88180-3100">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="88180-3101">分號 （;）或引號 （"）</span><span class="sxs-lookup"><span data-stu-id="88180-3101">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3102">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3102">Checksum</span></span>

<span data-ttu-id="88180-3103">否</span><span class="sxs-lookup"><span data-stu-id="88180-3103">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3104">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3104">Definition</span></span>

<span data-ttu-id="88180-3105">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3106">規則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3106">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3107">從 CEP_GlobalFilter 關鍵字**不**找到。</span><span class="sxs-lookup"><span data-stu-id="88180-3107">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="88180-3108">規則運算式 CEP_PasswordPlaceHolder**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3108">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3109">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3109">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3110">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3110">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="88180-3111">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="88180-3111">CEP_GlobalFilter</span></span>

- <span data-ttu-id="88180-3112">某些密碼</span><span class="sxs-lookup"><span data-stu-id="88180-3112">some-password</span></span>
- <span data-ttu-id="88180-3113">somepassword</span><span class="sxs-lookup"><span data-stu-id="88180-3113">somepassword</span></span>
- <span data-ttu-id="88180-3114">secretPassword</span><span class="sxs-lookup"><span data-stu-id="88180-3114">secretPassword</span></span>
- <span data-ttu-id="88180-3115">範例</span><span class="sxs-lookup"><span data-stu-id="88180-3115">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="88180-3116">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="88180-3116">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="88180-3117">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-3117">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-3118">Password 或 pwd 後面接著 0-2 空格，等號 （=）、 0-2 空格，並星號 （\*）-或-</span><span class="sxs-lookup"><span data-stu-id="88180-3118">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="88180-3119">Password 或 pwd 後面加上：</span><span class="sxs-lookup"><span data-stu-id="88180-3119">Password or pwd followed by:</span></span>
    - <span data-ttu-id="88180-3120">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="88180-3120">Equal sign (=)</span></span>
    - <span data-ttu-id="88180-3121">小於符號 (<)</span><span class="sxs-lookup"><span data-stu-id="88180-3121">Less than symbol (<)</span></span>
    - <span data-ttu-id="88180-3122">1-200 的字元上方-或小寫字母、 數字、 星號 （\*）、 連字號 （-）、 底線 (_) 或空白字元的任意組合</span><span class="sxs-lookup"><span data-stu-id="88180-3122">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="88180-3123">大於符號 (>)</span><span class="sxs-lookup"><span data-stu-id="88180-3123">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="88180-3124">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="88180-3124">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="88180-3125">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="88180-3125">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="88180-3126">contoso</span><span class="sxs-lookup"><span data-stu-id="88180-3126">contoso</span></span>
- <span data-ttu-id="88180-3127">fabrikam</span><span class="sxs-lookup"><span data-stu-id="88180-3127">fabrikam</span></span>
- <span data-ttu-id="88180-3128">northwind</span><span class="sxs-lookup"><span data-stu-id="88180-3128">northwind</span></span>
- <span data-ttu-id="88180-3129">沙箱化</span><span class="sxs-lookup"><span data-stu-id="88180-3129">sandbox</span></span>
- <span data-ttu-id="88180-3130">onebox</span><span class="sxs-lookup"><span data-stu-id="88180-3130">onebox</span></span>
- <span data-ttu-id="88180-3131">localhost</span><span class="sxs-lookup"><span data-stu-id="88180-3131">localhost</span></span>
- <span data-ttu-id="88180-3132">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="88180-3132">127.0.0.1</span></span>
- <span data-ttu-id="88180-3133">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="88180-3133">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="88180-3134">s int。<!--no-hyperlink-->net</span><span class="sxs-lookup"><span data-stu-id="88180-3134">s-int.<!--no-hyperlink-->net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="88180-3135">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="88180-3135">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="88180-3136">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3136">Format</span></span>

<span data-ttu-id="88180-3137">10 或 12 位數和一個選用分隔符號</span><span class="sxs-lookup"><span data-stu-id="88180-3137">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3138">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3138">Pattern</span></span>

<span data-ttu-id="88180-3139">10 或 12 位數和一個選用分隔符號：</span><span class="sxs-lookup"><span data-stu-id="88180-3139">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="88180-3140">2-4 位數 （選用）</span><span class="sxs-lookup"><span data-stu-id="88180-3140">2-4 digits (optional)</span></span> 
- <span data-ttu-id="88180-3141">格式 YYMMDD 的六位數，日期</span><span class="sxs-lookup"><span data-stu-id="88180-3141">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="88180-3142">分隔符號"-"或"+"（選用），再加上</span><span class="sxs-lookup"><span data-stu-id="88180-3142">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="88180-3143">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-3143">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3144">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3144">Checksum</span></span>

<span data-ttu-id="88180-3145">是</span><span class="sxs-lookup"><span data-stu-id="88180-3145">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3146">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3146">Definition</span></span>

<span data-ttu-id="88180-3147">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3147">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3148">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3148">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3149">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3149">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3150">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3150">Keywords</span></span>

<span data-ttu-id="88180-3151">否</span><span class="sxs-lookup"><span data-stu-id="88180-3151">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="88180-3152">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3152">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3153">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3153">Format</span></span>

<span data-ttu-id="88180-3154">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-3154">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3155">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3155">Pattern</span></span>

<span data-ttu-id="88180-3156">八個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-3156">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3157">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3157">Checksum</span></span>

<span data-ttu-id="88180-3158">否</span><span class="sxs-lookup"><span data-stu-id="88180-3158">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3159">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3159">Definition</span></span>

<span data-ttu-id="88180-3160">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3160">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3161">規則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3161">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3162">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="88180-3162">One of the following is true:</span></span>
    - <span data-ttu-id="88180-3163">找不到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3163">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="88180-3164">找不到來自 Keyword_sweden_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3164">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3165">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3165">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="88180-3166">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="88180-3166">Keyword_sweden_passport</span></span>

- <span data-ttu-id="88180-3167">visa 需求</span><span class="sxs-lookup"><span data-stu-id="88180-3167">visa requirements</span></span> 
- <span data-ttu-id="88180-3168">外星註冊卡</span><span class="sxs-lookup"><span data-stu-id="88180-3168">Alien Registration Card</span></span> 
- <span data-ttu-id="88180-3169">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="88180-3169">Schengen visas</span></span> 
- <span data-ttu-id="88180-3170">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="88180-3170">Schengen visa</span></span> 
- <span data-ttu-id="88180-3171">Visa 處理</span><span class="sxs-lookup"><span data-stu-id="88180-3171">Visa Processing</span></span> 
- <span data-ttu-id="88180-3172">Visa 類型</span><span class="sxs-lookup"><span data-stu-id="88180-3172">Visa Type</span></span> 
- <span data-ttu-id="88180-3173">單一項目</span><span class="sxs-lookup"><span data-stu-id="88180-3173">Single Entry</span></span> 
- <span data-ttu-id="88180-3174">多個項目</span><span class="sxs-lookup"><span data-stu-id="88180-3174">Multiple Entry</span></span> 
- <span data-ttu-id="88180-3175">G3 處理費用</span><span class="sxs-lookup"><span data-stu-id="88180-3175">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="88180-3176">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="88180-3176">Keyword_passport</span></span>

- <span data-ttu-id="88180-3177">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3177">Passport Number</span></span> 
- <span data-ttu-id="88180-3178">Passport 否</span><span class="sxs-lookup"><span data-stu-id="88180-3178">Passport No</span></span> 
- <span data-ttu-id="88180-3179">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-3179">Passport #</span></span> 
- <span data-ttu-id="88180-3180">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-3180">Passport#</span></span> 
- <span data-ttu-id="88180-3181">PassportID</span><span class="sxs-lookup"><span data-stu-id="88180-3181">PassportID</span></span> 
- <span data-ttu-id="88180-3182">Passportno</span><span class="sxs-lookup"><span data-stu-id="88180-3182">Passportno</span></span> 
- <span data-ttu-id="88180-3183">passportnumber</span><span class="sxs-lookup"><span data-stu-id="88180-3183">passportnumber</span></span> 
- <span data-ttu-id="88180-3184">パスポート</span><span class="sxs-lookup"><span data-stu-id="88180-3184">パスポート</span></span> 
- <span data-ttu-id="88180-3185">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="88180-3185">パスポート番号</span></span> 
- <span data-ttu-id="88180-3186">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="88180-3186">パスポートのNum</span></span> 
- <span data-ttu-id="88180-3187">パスポート #</span><span class="sxs-lookup"><span data-stu-id="88180-3187">パスポート＃</span></span> 
- <span data-ttu-id="88180-3188">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="88180-3188">Numéro de passeport</span></span> 
- <span data-ttu-id="88180-3189">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="88180-3189">Passeport n °</span></span> 
- <span data-ttu-id="88180-3190">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="88180-3190">Passeport Non</span></span> 
- <span data-ttu-id="88180-3191">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-3191">Passeport #</span></span> 
- <span data-ttu-id="88180-3192">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-3192">Passeport#</span></span> 
- <span data-ttu-id="88180-3193">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="88180-3193">PasseportNon</span></span> 
- <span data-ttu-id="88180-3194">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="88180-3194">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="88180-3195">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="88180-3195">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="88180-3196">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3196">Format</span></span>

<span data-ttu-id="88180-3197">四個字母後尾隨 5-31 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="88180-3197">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3198">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3198">Pattern</span></span>

<span data-ttu-id="88180-3199">四個字母後尾隨 5-31 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="88180-3199">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="88180-3200">四字母銀行代碼 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-3200">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="88180-3201">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="88180-3201">An optional space</span></span> 
- <span data-ttu-id="88180-3202">4-28 個字母或數字 (基本銀行帳戶號碼 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="88180-3202">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="88180-3203">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="88180-3203">An optional space</span></span> 
- <span data-ttu-id="88180-3204">1-3 個字母或數字 （BBAN 的其餘部分）</span><span class="sxs-lookup"><span data-stu-id="88180-3204">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3205">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3205">Checksum</span></span>

<span data-ttu-id="88180-3206">否</span><span class="sxs-lookup"><span data-stu-id="88180-3206">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3207">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3207">Definition</span></span>

<span data-ttu-id="88180-3208">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3208">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3209">規則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3209">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3210">找不到來自 Keyword_swift 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3210">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3211">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3211">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="88180-3212">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="88180-3212">Keyword_swift</span></span>

- <span data-ttu-id="88180-3213">國際標準 9362 組織</span><span class="sxs-lookup"><span data-stu-id="88180-3213">international organization for standardization 9362</span></span> 
- <span data-ttu-id="88180-3214">iso 9362</span><span class="sxs-lookup"><span data-stu-id="88180-3214">iso 9362</span></span> 
- <span data-ttu-id="88180-3215">iso9362</span><span class="sxs-lookup"><span data-stu-id="88180-3215">iso9362</span></span> 
- <span data-ttu-id="88180-3216">swift\#</span><span class="sxs-lookup"><span data-stu-id="88180-3216">swift\#</span></span> 
- <span data-ttu-id="88180-3217">swiftcode</span><span class="sxs-lookup"><span data-stu-id="88180-3217">swiftcode</span></span> 
- <span data-ttu-id="88180-3218">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="88180-3218">swiftnumber</span></span> 
- <span data-ttu-id="88180-3219">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="88180-3219">swiftroutingnumber</span></span> 
- <span data-ttu-id="88180-3220">swift 代碼</span><span class="sxs-lookup"><span data-stu-id="88180-3220">swift code</span></span> 
- <span data-ttu-id="88180-3221">swift 號碼 #</span><span class="sxs-lookup"><span data-stu-id="88180-3221">swift number #</span></span> 
- <span data-ttu-id="88180-3222">swift 路由號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3222">swift routing number</span></span> 
- <span data-ttu-id="88180-3223">bic 數目</span><span class="sxs-lookup"><span data-stu-id="88180-3223">bic number</span></span> 
- <span data-ttu-id="88180-3224">bic 程式碼</span><span class="sxs-lookup"><span data-stu-id="88180-3224">bic code</span></span> 
- <span data-ttu-id="88180-3225">bic\#</span><span class="sxs-lookup"><span data-stu-id="88180-3225">bic \#</span></span> 
- <span data-ttu-id="88180-3226">bic\#</span><span class="sxs-lookup"><span data-stu-id="88180-3226">bic\#</span></span> 
- <span data-ttu-id="88180-3227">銀行識別碼程式碼</span><span class="sxs-lookup"><span data-stu-id="88180-3227">bank identifier code</span></span> 
- <span data-ttu-id="88180-3228">標準化9362</span><span class="sxs-lookup"><span data-stu-id="88180-3228">標準化9362</span></span> 
- <span data-ttu-id="88180-3229">迅速 #</span><span class="sxs-lookup"><span data-stu-id="88180-3229">迅速＃</span></span> 
- <span data-ttu-id="88180-3230">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="88180-3230">SWIFTコード</span></span> 
- <span data-ttu-id="88180-3231">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="88180-3231">SWIFT番号</span></span> 
- <span data-ttu-id="88180-3232">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="88180-3232">迅速なルーティング番号</span></span> 
- <span data-ttu-id="88180-3233">BIC番号</span><span class="sxs-lookup"><span data-stu-id="88180-3233">BIC番号</span></span> 
- <span data-ttu-id="88180-3234">BICコード</span><span class="sxs-lookup"><span data-stu-id="88180-3234">BICコード</span></span> 
- <span data-ttu-id="88180-3235">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="88180-3235">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="88180-3236">組織 internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="88180-3236">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="88180-3237">rapide\#</span><span class="sxs-lookup"><span data-stu-id="88180-3237">rapide \#</span></span> 
- <span data-ttu-id="88180-3238">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="88180-3238">code SWIFT</span></span> 
- <span data-ttu-id="88180-3239">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="88180-3239">le numéro de swift</span></span> 
- <span data-ttu-id="88180-3240">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="88180-3240">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="88180-3241">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="88180-3241">le numéro BIC</span></span> 
- <span data-ttu-id="88180-3242">\#BIC</span><span class="sxs-lookup"><span data-stu-id="88180-3242">\# BIC</span></span> 
- <span data-ttu-id="88180-3243">程式碼 identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="88180-3243">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="88180-3244">台灣國家識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3244">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="88180-3245">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3245">Format</span></span>

<span data-ttu-id="88180-3246">一個字母 （英文） 尾隨九位數</span><span class="sxs-lookup"><span data-stu-id="88180-3246">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3247">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3247">Pattern</span></span>

<span data-ttu-id="88180-3248">一個字母 （英文） 尾隨九位數：</span><span class="sxs-lookup"><span data-stu-id="88180-3248">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="88180-3249">一個字母 （以英文、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-3249">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="88180-3250">數字"1"或"2"</span><span class="sxs-lookup"><span data-stu-id="88180-3250">The digit "1" or "2"</span></span> 
- <span data-ttu-id="88180-3251">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-3251">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3252">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3252">Checksum</span></span>

<span data-ttu-id="88180-3253">是</span><span class="sxs-lookup"><span data-stu-id="88180-3253">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3254">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3254">Definition</span></span>

<span data-ttu-id="88180-3255">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3255">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3256">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3256">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3257">找不到來自 Keyword_taiwanese_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3257">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="88180-3258">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3258">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3259">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3259">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="88180-3260">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="88180-3260">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="88180-3261">身份證字號</span><span class="sxs-lookup"><span data-stu-id="88180-3261">身份證字號</span></span> 
- <span data-ttu-id="88180-3262">身份證</span><span class="sxs-lookup"><span data-stu-id="88180-3262">身份證</span></span> 
- <span data-ttu-id="88180-3263">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3263">身份證號碼</span></span> 
- <span data-ttu-id="88180-3264">身份證號</span><span class="sxs-lookup"><span data-stu-id="88180-3264">身份證號</span></span> 
- <span data-ttu-id="88180-3265">身分證字號</span><span class="sxs-lookup"><span data-stu-id="88180-3265">身分證字號</span></span> 
- <span data-ttu-id="88180-3266">身分證</span><span class="sxs-lookup"><span data-stu-id="88180-3266">身分證</span></span> 
- <span data-ttu-id="88180-3267">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3267">身分證號碼</span></span> 
- <span data-ttu-id="88180-3268">身份證號</span><span class="sxs-lookup"><span data-stu-id="88180-3268">身份證號</span></span> 
- <span data-ttu-id="88180-3269">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="88180-3269">身分證統一編號</span></span> 
- <span data-ttu-id="88180-3270">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="88180-3270">國民身分證統一編號</span></span> 
- <span data-ttu-id="88180-3271">簽名</span><span class="sxs-lookup"><span data-stu-id="88180-3271">簽名</span></span> 
- <span data-ttu-id="88180-3272">蓋章</span><span class="sxs-lookup"><span data-stu-id="88180-3272">蓋章</span></span> 
- <span data-ttu-id="88180-3273">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="88180-3273">簽名或蓋章</span></span> 
- <span data-ttu-id="88180-3274">簽章</span><span class="sxs-lookup"><span data-stu-id="88180-3274">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="88180-3275">台灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3275">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3276">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3276">Format</span></span>

- <span data-ttu-id="88180-3277">生物識別護照號碼： 九位數</span><span class="sxs-lookup"><span data-stu-id="88180-3277">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="88180-3278">非生物識別護照號碼： 九位數</span><span class="sxs-lookup"><span data-stu-id="88180-3278">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3279">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3279">Pattern</span></span>
<span data-ttu-id="88180-3280">生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="88180-3280">Biometric passport number:</span></span>
- <span data-ttu-id="88180-3281">數字"3"</span><span class="sxs-lookup"><span data-stu-id="88180-3281">The digit "3"</span></span> 
- <span data-ttu-id="88180-3282">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-3282">Eight digits</span></span>

<span data-ttu-id="88180-3283">非生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="88180-3283">Non-biometric passport number:</span></span>
- <span data-ttu-id="88180-3284">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-3284">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3285">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3285">Checksum</span></span>

<span data-ttu-id="88180-3286">否</span><span class="sxs-lookup"><span data-stu-id="88180-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3287">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3287">Definition</span></span>

<span data-ttu-id="88180-3288">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3289">規則運算式 Regex_taiwan_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3289">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3290">找不到來自 Keyword_taiwan_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3290">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3291">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3291">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="88180-3292">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="88180-3292">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="88180-3293">中華民國護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3293">ROC passport number</span></span> 
- <span data-ttu-id="88180-3294">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3294">Passport number</span></span> 
- <span data-ttu-id="88180-3295">Passport 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-3295">Passport no</span></span> 
- <span data-ttu-id="88180-3296">Passport Num</span><span class="sxs-lookup"><span data-stu-id="88180-3296">Passport Num</span></span> 
- <span data-ttu-id="88180-3297">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-3297">Passport #</span></span> 
- <span data-ttu-id="88180-3298">护照</span><span class="sxs-lookup"><span data-stu-id="88180-3298">护照</span></span> 
- <span data-ttu-id="88180-3299">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="88180-3299">中華民國護照</span></span> 
- <span data-ttu-id="88180-3300">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="88180-3300">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="88180-3301">台灣居民憑證 (ARC/TARC) 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3301">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3302">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3302">Format</span></span>

<span data-ttu-id="88180-3303">10 個字母和數字</span><span class="sxs-lookup"><span data-stu-id="88180-3303">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3304">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3304">Pattern</span></span>

<span data-ttu-id="88180-3305">10 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="88180-3305">10 letters and digits:</span></span>
- <span data-ttu-id="88180-3306">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-3306">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="88180-3307">八位數</span><span class="sxs-lookup"><span data-stu-id="88180-3307">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3308">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3308">Checksum</span></span>

<span data-ttu-id="88180-3309">否</span><span class="sxs-lookup"><span data-stu-id="88180-3309">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3310">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3310">Definition</span></span>

<span data-ttu-id="88180-3311">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3311">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3312">規則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3312">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3313">找不到來自 Keyword_taiwan_resident_certificate 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3313">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3314">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3314">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="88180-3315">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="88180-3315">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="88180-3316">內建的憑證</span><span class="sxs-lookup"><span data-stu-id="88180-3316">Resident Certificate</span></span> 
- <span data-ttu-id="88180-3317">駐留 Cert</span><span class="sxs-lookup"><span data-stu-id="88180-3317">Resident Cert</span></span> 
- <span data-ttu-id="88180-3318">內建的憑證。</span><span class="sxs-lookup"><span data-stu-id="88180-3318">Resident Cert.</span></span> 
- <span data-ttu-id="88180-3319">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-3319">Identification card</span></span> 
- <span data-ttu-id="88180-3320">外星居民憑證</span><span class="sxs-lookup"><span data-stu-id="88180-3320">Alien Resident Certificate</span></span> 
- <span data-ttu-id="88180-3321">弧線</span><span class="sxs-lookup"><span data-stu-id="88180-3321">ARC</span></span> 
- <span data-ttu-id="88180-3322">台灣區域居民憑證</span><span class="sxs-lookup"><span data-stu-id="88180-3322">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="88180-3323">TARC</span><span class="sxs-lookup"><span data-stu-id="88180-3323">TARC</span></span> 
- <span data-ttu-id="88180-3324">居留證</span><span class="sxs-lookup"><span data-stu-id="88180-3324">居留證</span></span> 
- <span data-ttu-id="88180-3325">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="88180-3325">外僑居留證</span></span> 
- <span data-ttu-id="88180-3326">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="88180-3326">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="88180-3327">泰文母體識別程式碼</span><span class="sxs-lookup"><span data-stu-id="88180-3327">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="88180-3328">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3328">Format</span></span>

<span data-ttu-id="88180-3329">13 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3329">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3330">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3330">Pattern</span></span>

<span data-ttu-id="88180-3331">13 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-3331">13 digits:</span></span>
- <span data-ttu-id="88180-3332">第一個數字不是 0 或 9</span><span class="sxs-lookup"><span data-stu-id="88180-3332">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="88180-3333">12 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3333">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3334">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3334">Checksum</span></span>

<span data-ttu-id="88180-3335">是</span><span class="sxs-lookup"><span data-stu-id="88180-3335">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3336">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3336">Definition</span></span>

<span data-ttu-id="88180-3337">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3337">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3338">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3338">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3339">找不到來自 Keyword_Thai_Citizen_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3339">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="88180-3340">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3340">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3341">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3341">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3342">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3342">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="88180-3343">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="88180-3343">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="88180-3344">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3344">ID Number</span></span>
- <span data-ttu-id="88180-3345">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3345">Identification Number</span></span>
- <span data-ttu-id="88180-3346">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="88180-3346">บัตรประชาชน</span></span>
- <span data-ttu-id="88180-3347">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="88180-3347">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="88180-3348">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="88180-3348">บัตรประชาชน</span></span>
- <span data-ttu-id="88180-3349">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="88180-3349">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="88180-3350">土耳其文的國家識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3350">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3351">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3351">Format</span></span>

<span data-ttu-id="88180-3352">11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3352">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3353">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3353">Pattern</span></span>

<span data-ttu-id="88180-3354">11 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3354">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3355">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3355">Checksum</span></span>

<span data-ttu-id="88180-3356">是</span><span class="sxs-lookup"><span data-stu-id="88180-3356">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3357">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3357">Definition</span></span>

<span data-ttu-id="88180-3358">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3358">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3359">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3359">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3360">找不到來自 Keyword_Turkish_National_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3360">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="88180-3361">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3362">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3362">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3363">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="88180-3364">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="88180-3364">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="88180-3365">繁體中文 Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="88180-3365">TC Kimlik No</span></span>
- <span data-ttu-id="88180-3366">繁體中文 Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="88180-3366">TC Kimlik numarası</span></span>
- <span data-ttu-id="88180-3367">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="88180-3367">Vatandaşlık numarası</span></span>
- <span data-ttu-id="88180-3368">Vatandaşlık 沒有</span><span class="sxs-lookup"><span data-stu-id="88180-3368">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="88180-3369">英國</span><span class="sxs-lookup"><span data-stu-id="88180-3369">U.K.</span></span> <span data-ttu-id="88180-3370">駕照編號</span><span class="sxs-lookup"><span data-stu-id="88180-3370">Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3371">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3371">Format</span></span>

<span data-ttu-id="88180-3372">18 個字母和數字中指定之格式的組合</span><span class="sxs-lookup"><span data-stu-id="88180-3372">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3373">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3373">Pattern</span></span>

<span data-ttu-id="88180-3374">18 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="88180-3374">18 letters and digits:</span></span>
- <span data-ttu-id="88180-3375">五個字母 （不區分大小寫） 或取代字母的數字"9"</span><span class="sxs-lookup"><span data-stu-id="88180-3375">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="88180-3376">一位數</span><span class="sxs-lookup"><span data-stu-id="88180-3376">One digit</span></span> 
- <span data-ttu-id="88180-3377">五位數的日期格式 ddmmy 表示出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3377">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="88180-3378">兩個字母 （不區分大小寫） 或取代字母的數字"9"</span><span class="sxs-lookup"><span data-stu-id="88180-3378">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="88180-3379">五位數</span><span class="sxs-lookup"><span data-stu-id="88180-3379">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3380">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3380">Checksum</span></span>

<span data-ttu-id="88180-3381">是</span><span class="sxs-lookup"><span data-stu-id="88180-3381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3382">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3382">Definition</span></span>

<span data-ttu-id="88180-3383">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3383">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3384">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3384">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3385">找不到來自 Keyword_uk_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3385">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="88180-3386">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3386">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3387">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="88180-3388">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="88180-3388">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="88180-3389">DVLA</span><span class="sxs-lookup"><span data-stu-id="88180-3389">DVLA</span></span> 
- <span data-ttu-id="88180-3390">淺 van 能夠</span><span class="sxs-lookup"><span data-stu-id="88180-3390">light vans</span></span> 
- <span data-ttu-id="88180-3391">quadbikes</span><span class="sxs-lookup"><span data-stu-id="88180-3391">quadbikes</span></span> 
- <span data-ttu-id="88180-3392">馬達車輛</span><span class="sxs-lookup"><span data-stu-id="88180-3392">motor cars</span></span> 
- <span data-ttu-id="88180-3393">125cc</span><span class="sxs-lookup"><span data-stu-id="88180-3393">125cc</span></span> 
- <span data-ttu-id="88180-3394">sidecar</span><span class="sxs-lookup"><span data-stu-id="88180-3394">sidecar</span></span> 
- <span data-ttu-id="88180-3395">tricycles</span><span class="sxs-lookup"><span data-stu-id="88180-3395">tricycles</span></span> 
- <span data-ttu-id="88180-3396">機車</span><span class="sxs-lookup"><span data-stu-id="88180-3396">motorcycles</span></span> 
- <span data-ttu-id="88180-3397">photocard 授權</span><span class="sxs-lookup"><span data-stu-id="88180-3397">photocard licence</span></span> 
- <span data-ttu-id="88180-3398">學習者單元驅動程式</span><span class="sxs-lookup"><span data-stu-id="88180-3398">learner drivers</span></span> 
- <span data-ttu-id="88180-3399">授權持有者</span><span class="sxs-lookup"><span data-stu-id="88180-3399">licence holder</span></span> 
- <span data-ttu-id="88180-3400">授權持有者</span><span class="sxs-lookup"><span data-stu-id="88180-3400">licence holders</span></span> 
- <span data-ttu-id="88180-3401">driving 授權</span><span class="sxs-lookup"><span data-stu-id="88180-3401">driving licences</span></span> 
- <span data-ttu-id="88180-3402">driving 授權</span><span class="sxs-lookup"><span data-stu-id="88180-3402">driving licence</span></span> 
- <span data-ttu-id="88180-3403">雙重控制汽車</span><span class="sxs-lookup"><span data-stu-id="88180-3403">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="88180-3404">英國</span><span class="sxs-lookup"><span data-stu-id="88180-3404">U.K.</span></span> <span data-ttu-id="88180-3405">Electoral Roll 數目</span><span class="sxs-lookup"><span data-stu-id="88180-3405">Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3406">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3406">Format</span></span>

<span data-ttu-id="88180-3407">兩個字母後尾隨 1-4 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3407">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3408">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3408">Pattern</span></span>

<span data-ttu-id="88180-3409">兩個字母 （不區分大小寫） 尾隨 1-4 個數字</span><span class="sxs-lookup"><span data-stu-id="88180-3409">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3410">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3410">Checksum</span></span>

<span data-ttu-id="88180-3411">否</span><span class="sxs-lookup"><span data-stu-id="88180-3411">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3412">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3412">Definition</span></span>

<span data-ttu-id="88180-3413">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3414">規則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3414">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3415">找不到來自 Keyword_uk_electoral 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3415">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3416">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3416">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="88180-3417">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="88180-3417">Keyword_uk_electoral</span></span>

- <span data-ttu-id="88180-3418">會議提名</span><span class="sxs-lookup"><span data-stu-id="88180-3418">council nomination</span></span> 
- <span data-ttu-id="88180-3419">提名表單</span><span class="sxs-lookup"><span data-stu-id="88180-3419">nomination form</span></span> 
- <span data-ttu-id="88180-3420">選舉註冊</span><span class="sxs-lookup"><span data-stu-id="88180-3420">electoral register</span></span> 
- <span data-ttu-id="88180-3421">electoral roll</span><span class="sxs-lookup"><span data-stu-id="88180-3421">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="88180-3422">英國</span><span class="sxs-lookup"><span data-stu-id="88180-3422">U.K.</span></span> <span data-ttu-id="88180-3423">國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3423">National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3424">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3424">Format</span></span>

<span data-ttu-id="88180-3425">以空格分隔的 10-17 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3425">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3426">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3426">Pattern</span></span>

<span data-ttu-id="88180-3427">10-17 位數：</span><span class="sxs-lookup"><span data-stu-id="88180-3427">10-17 digits:</span></span>
- <span data-ttu-id="88180-3428">3 或 10 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3428">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="88180-3429">一個空格</span><span class="sxs-lookup"><span data-stu-id="88180-3429">A space</span></span> 
- <span data-ttu-id="88180-3430">三位數</span><span class="sxs-lookup"><span data-stu-id="88180-3430">Three digits</span></span> 
- <span data-ttu-id="88180-3431">一個空格</span><span class="sxs-lookup"><span data-stu-id="88180-3431">A space</span></span> 
- <span data-ttu-id="88180-3432">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-3432">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3433">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3433">Checksum</span></span>

<span data-ttu-id="88180-3434">是</span><span class="sxs-lookup"><span data-stu-id="88180-3434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3435">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3435">Definition</span></span>

<span data-ttu-id="88180-3436">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3437">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3437">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3438">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="88180-3438">One of the following is true:</span></span>
    - <span data-ttu-id="88180-3439">找不到來自 Keyword_uk_nhs_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3439">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="88180-3440">找不到來自 Keyword_uk_nhs_number1 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3440">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="88180-3441">找不到來自 Keyword_uk_nhs_number_dob 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3441">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="88180-3442">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="88180-3442">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3443">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="88180-3444">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="88180-3444">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="88180-3445">國民健保服務</span><span class="sxs-lookup"><span data-stu-id="88180-3445">national health service</span></span> 
- <span data-ttu-id="88180-3446">nhs</span><span class="sxs-lookup"><span data-stu-id="88180-3446">nhs</span></span> 
- <span data-ttu-id="88180-3447">健康情況服務授權</span><span class="sxs-lookup"><span data-stu-id="88180-3447">health services authority</span></span> 
- <span data-ttu-id="88180-3448">健康情況授權</span><span class="sxs-lookup"><span data-stu-id="88180-3448">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="88180-3449">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="88180-3449">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="88180-3450">病患識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3450">patient id</span></span> 
- <span data-ttu-id="88180-3451">病患識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3451">patient identification</span></span> 
- <span data-ttu-id="88180-3452">病患否</span><span class="sxs-lookup"><span data-stu-id="88180-3452">patient no</span></span> 
- <span data-ttu-id="88180-3453">病患的數字</span><span class="sxs-lookup"><span data-stu-id="88180-3453">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="88180-3454">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="88180-3454">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="88180-3455">GP</span><span class="sxs-lookup"><span data-stu-id="88180-3455">GP</span></span> 
- <span data-ttu-id="88180-3456">DOB</span><span class="sxs-lookup"><span data-stu-id="88180-3456">DOB</span></span> 
- <span data-ttu-id="88180-3457">D.O.B</span><span class="sxs-lookup"><span data-stu-id="88180-3457">D.O.B</span></span> 
- <span data-ttu-id="88180-3458">出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3458">Date of Birth</span></span> 
- <span data-ttu-id="88180-3459">出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3459">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="88180-3460">英國</span><span class="sxs-lookup"><span data-stu-id="88180-3460">U.K.</span></span> <span data-ttu-id="88180-3461">國家保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="88180-3461">National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="88180-3462">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3462">Format</span></span>

<span data-ttu-id="88180-3463">7 個字元或空格或連字號分隔的 9 個字元</span><span class="sxs-lookup"><span data-stu-id="88180-3463">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3464">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3464">Pattern</span></span>

<span data-ttu-id="88180-3465">兩個可能的模式：</span><span class="sxs-lookup"><span data-stu-id="88180-3465">Two possible patterns:</span></span>

- <span data-ttu-id="88180-3466">兩個字母 (有效 NINOs 中此前置詞，此模式會驗證; 使用僅限特定字元不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="88180-3466">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="88180-3467">六位數</span><span class="sxs-lookup"><span data-stu-id="88180-3467">Six digits</span></span>
- <span data-ttu-id="88180-3468">可以是 'A'、 'B'、 'C'，或有 ' （例如前置詞，只有某些字元中允許之尾碼; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="88180-3468">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="88180-3469">或</span><span class="sxs-lookup"><span data-stu-id="88180-3469">OR</span></span>

- <span data-ttu-id="88180-3470">兩個字母</span><span class="sxs-lookup"><span data-stu-id="88180-3470">Two letters</span></span>
- <span data-ttu-id="88180-3471">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3471">A space or dash</span></span>
- <span data-ttu-id="88180-3472">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3472">Two digits</span></span>
- <span data-ttu-id="88180-3473">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3473">A space or dash</span></span>
- <span data-ttu-id="88180-3474">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3474">Two digits</span></span>
- <span data-ttu-id="88180-3475">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3475">A space or dash</span></span>
- <span data-ttu-id="88180-3476">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3476">Two digits</span></span>
- <span data-ttu-id="88180-3477">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3477">A space or dash</span></span>
- <span data-ttu-id="88180-3478">可以是 'A'、 'B'、 'C'，或有 '</span><span class="sxs-lookup"><span data-stu-id="88180-3478">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3479">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3479">Checksum</span></span>

<span data-ttu-id="88180-3480">否</span><span class="sxs-lookup"><span data-stu-id="88180-3480">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3481">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3481">Definition</span></span>

<span data-ttu-id="88180-3482">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3482">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3483">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3483">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3484">找不到來自 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3484">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="88180-3485">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3485">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3486">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3486">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3487">找不到來自 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3487">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3488">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3488">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="88180-3489">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="88180-3489">Keyword_uk_nino</span></span>

- <span data-ttu-id="88180-3490">國家保險號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3490">national insurance number</span></span> 
- <span data-ttu-id="88180-3491">國家保險捐款</span><span class="sxs-lookup"><span data-stu-id="88180-3491">national insurance contributions</span></span> 
- <span data-ttu-id="88180-3492">保護法案</span><span class="sxs-lookup"><span data-stu-id="88180-3492">protection act</span></span> 
- <span data-ttu-id="88180-3493">保險</span><span class="sxs-lookup"><span data-stu-id="88180-3493">insurance</span></span> 
- <span data-ttu-id="88180-3494">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3494">social security number</span></span> 
- <span data-ttu-id="88180-3495">保險應用程式</span><span class="sxs-lookup"><span data-stu-id="88180-3495">insurance application</span></span> 
- <span data-ttu-id="88180-3496">醫療應用程式</span><span class="sxs-lookup"><span data-stu-id="88180-3496">medical application</span></span> 
- <span data-ttu-id="88180-3497">社會保險</span><span class="sxs-lookup"><span data-stu-id="88180-3497">social insurance</span></span> 
- <span data-ttu-id="88180-3498">醫療注意事項</span><span class="sxs-lookup"><span data-stu-id="88180-3498">medical attention</span></span> 
- <span data-ttu-id="88180-3499">社會安全</span><span class="sxs-lookup"><span data-stu-id="88180-3499">social security</span></span> 
- <span data-ttu-id="88180-3500">英國</span><span class="sxs-lookup"><span data-stu-id="88180-3500">great britain</span></span> 
- <span data-ttu-id="88180-3501">保險</span><span class="sxs-lookup"><span data-stu-id="88180-3501">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="88180-3502">美國 / 英國</span><span class="sxs-lookup"><span data-stu-id="88180-3502">U.S. / U.K.</span></span> <span data-ttu-id="88180-3503">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3503">Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3504">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3504">Format</span></span>

<span data-ttu-id="88180-3505">九位數</span><span class="sxs-lookup"><span data-stu-id="88180-3505">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3506">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3506">Pattern</span></span>

<span data-ttu-id="88180-3507">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-3507">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3508">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3508">Checksum</span></span>

<span data-ttu-id="88180-3509">否</span><span class="sxs-lookup"><span data-stu-id="88180-3509">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3510">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3510">Definition</span></span>

<span data-ttu-id="88180-3511">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3511">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3512">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3512">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3513">找不到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3513">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3514">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3514">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="88180-3515">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="88180-3515">Keyword_passport</span></span>

- <span data-ttu-id="88180-3516">護照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3516">Passport Number</span></span> 
- <span data-ttu-id="88180-3517">Passport 否</span><span class="sxs-lookup"><span data-stu-id="88180-3517">Passport No</span></span> 
- <span data-ttu-id="88180-3518">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-3518">Passport #</span></span> 
- <span data-ttu-id="88180-3519">Passport #</span><span class="sxs-lookup"><span data-stu-id="88180-3519">Passport#</span></span> 
- <span data-ttu-id="88180-3520">PassportID</span><span class="sxs-lookup"><span data-stu-id="88180-3520">PassportID</span></span> 
- <span data-ttu-id="88180-3521">Passportno</span><span class="sxs-lookup"><span data-stu-id="88180-3521">Passportno</span></span> 
- <span data-ttu-id="88180-3522">passportnumber</span><span class="sxs-lookup"><span data-stu-id="88180-3522">passportnumber</span></span> 
- <span data-ttu-id="88180-3523">パスポート</span><span class="sxs-lookup"><span data-stu-id="88180-3523">パスポート</span></span> 
- <span data-ttu-id="88180-3524">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="88180-3524">パスポート番号</span></span> 
- <span data-ttu-id="88180-3525">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="88180-3525">パスポートのNum</span></span> 
- <span data-ttu-id="88180-3526">パスポート #</span><span class="sxs-lookup"><span data-stu-id="88180-3526">パスポート＃</span></span> 
- <span data-ttu-id="88180-3527">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="88180-3527">Numéro de passeport</span></span> 
- <span data-ttu-id="88180-3528">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="88180-3528">Passeport n °</span></span> 
- <span data-ttu-id="88180-3529">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="88180-3529">Passeport Non</span></span> 
- <span data-ttu-id="88180-3530">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-3530">Passeport #</span></span> 
- <span data-ttu-id="88180-3531">Passeport #</span><span class="sxs-lookup"><span data-stu-id="88180-3531">Passeport#</span></span> 
- <span data-ttu-id="88180-3532">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="88180-3532">PasseportNon</span></span> 
- <span data-ttu-id="88180-3533">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="88180-3533">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="88180-3534">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3534">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3535">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3535">Format</span></span>

<span data-ttu-id="88180-3536">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="88180-3536">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3537">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3537">Pattern</span></span>

<span data-ttu-id="88180-3538">8-17 個連續數字</span><span class="sxs-lookup"><span data-stu-id="88180-3538">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3539">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3539">Checksum</span></span>

<span data-ttu-id="88180-3540">否</span><span class="sxs-lookup"><span data-stu-id="88180-3540">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3541">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3541">Definition</span></span>

<span data-ttu-id="88180-3542">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3542">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3543">規則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3543">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3544">找不到來自 Keyword_usa_Bank_Account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3544">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="88180-3545">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3545">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="88180-3546">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="88180-3546">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="88180-3547">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3547">Checking Account Number</span></span> 
- <span data-ttu-id="88180-3548">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-3548">Checking Account</span></span> 
- <span data-ttu-id="88180-3549">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-3549">Checking Account #</span></span> 
- <span data-ttu-id="88180-3550">檢查 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="88180-3550">Checking Acct Number</span></span> 
- <span data-ttu-id="88180-3551">檢查 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-3551">Checking Acct #</span></span> 
- <span data-ttu-id="88180-3552">檢查 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3552">Checking Acct No.</span></span> 
- <span data-ttu-id="88180-3553">檢查帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3553">Checking Account No.</span></span> 
- <span data-ttu-id="88180-3554">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3554">Bank Account Number</span></span> 
- <span data-ttu-id="88180-3555">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-3555">Bank Account #</span></span> 
- <span data-ttu-id="88180-3556">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3556">Bank Acct Number</span></span> 
- <span data-ttu-id="88180-3557">銀行 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-3557">Bank Acct #</span></span> 
- <span data-ttu-id="88180-3558">銀行 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3558">Bank Acct No.</span></span> 
- <span data-ttu-id="88180-3559">銀行帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3559">Bank Account No.</span></span> 
- <span data-ttu-id="88180-3560">節省帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3560">Savings Account Number</span></span> 
- <span data-ttu-id="88180-3561">省下的帳戶。</span><span class="sxs-lookup"><span data-stu-id="88180-3561">Savings Account.</span></span> 
- <span data-ttu-id="88180-3562">節省帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-3562">Savings Account #</span></span> 
- <span data-ttu-id="88180-3563">節省 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="88180-3563">Savings Acct Number</span></span> 
- <span data-ttu-id="88180-3564">節省 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-3564">Savings Acct #</span></span> 
- <span data-ttu-id="88180-3565">節省 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3565">Savings Acct No.</span></span> 
- <span data-ttu-id="88180-3566">存款帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3566">Savings Account No.</span></span> 
- <span data-ttu-id="88180-3567">轉帳帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3567">Debit Account Number</span></span> 
- <span data-ttu-id="88180-3568">轉帳帳戶</span><span class="sxs-lookup"><span data-stu-id="88180-3568">Debit Account</span></span> 
- <span data-ttu-id="88180-3569">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="88180-3569">Debit Account #</span></span> 
- <span data-ttu-id="88180-3570">轉帳 Acct 號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3570">Debit Acct Number</span></span> 
- <span data-ttu-id="88180-3571">借方 Acct #</span><span class="sxs-lookup"><span data-stu-id="88180-3571">Debit Acct #</span></span> 
- <span data-ttu-id="88180-3572">轉帳 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3572">Debit Acct No.</span></span> 
- <span data-ttu-id="88180-3573">轉帳帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="88180-3573">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="88180-3574">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3574">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="88180-3575">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3575">Format</span></span>

<span data-ttu-id="88180-3576">隨州別</span><span class="sxs-lookup"><span data-stu-id="88180-3576">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3577">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3577">Pattern</span></span>

<span data-ttu-id="88180-3578">狀態-例如，紐約而定：</span><span class="sxs-lookup"><span data-stu-id="88180-3578">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="88180-3579">九位數格式化 like ddd ddd ddd 會比對。</span><span class="sxs-lookup"><span data-stu-id="88180-3579">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="88180-3580">不會符合 ddddddddd 類似的九位數。</span><span class="sxs-lookup"><span data-stu-id="88180-3580">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3581">Checksum</span></span>

<span data-ttu-id="88180-3582">否</span><span class="sxs-lookup"><span data-stu-id="88180-3582">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3583">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3583">Definition</span></span>

<span data-ttu-id="88180-3584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3585">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3585">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3586">找到來自於 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3586">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="88180-3587">找不到來自 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3587">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="88180-3588">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3588">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3589">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3589">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3590">找到來自於 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3590">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="88180-3591">找不到來自 Keyword_us_drivers_license_abbreviations 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3591">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="88180-3592">找不到來自 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3592">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3593">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3593">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="88180-3594">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="88180-3594">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="88180-3595">DL</span><span class="sxs-lookup"><span data-stu-id="88180-3595">DL</span></span> 
- <span data-ttu-id="88180-3596">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="88180-3596">DLS</span></span> 
- <span data-ttu-id="88180-3597">CDL</span><span class="sxs-lookup"><span data-stu-id="88180-3597">CDL</span></span> 
- <span data-ttu-id="88180-3598">CDLS</span><span class="sxs-lookup"><span data-stu-id="88180-3598">CDLS</span></span> 
- <span data-ttu-id="88180-3599">ID</span><span class="sxs-lookup"><span data-stu-id="88180-3599">ID</span></span> 
- <span data-ttu-id="88180-3600">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3600">IDs</span></span> 
- <span data-ttu-id="88180-3601">DL #</span><span class="sxs-lookup"><span data-stu-id="88180-3601">DL#</span></span> 
- <span data-ttu-id="88180-3602">DL #</span><span class="sxs-lookup"><span data-stu-id="88180-3602">DLS#</span></span> 
- <span data-ttu-id="88180-3603">CDL #</span><span class="sxs-lookup"><span data-stu-id="88180-3603">CDL#</span></span> 
- <span data-ttu-id="88180-3604">CDLS #</span><span class="sxs-lookup"><span data-stu-id="88180-3604">CDLS#</span></span> 
- <span data-ttu-id="88180-3605">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="88180-3605">ID#</span></span>
- <span data-ttu-id="88180-3606">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="88180-3606">IDs#</span></span> 
- <span data-ttu-id="88180-3607">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3607">ID number</span></span> 
- <span data-ttu-id="88180-3608">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="88180-3608">ID numbers</span></span> 
- <span data-ttu-id="88180-3609">LIC</span><span class="sxs-lookup"><span data-stu-id="88180-3609">LIC</span></span> 
- <span data-ttu-id="88180-3610">LIC #</span><span class="sxs-lookup"><span data-stu-id="88180-3610">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="88180-3611">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="88180-3611">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="88180-3612">DriverLic</span><span class="sxs-lookup"><span data-stu-id="88180-3612">DriverLic</span></span> 
- <span data-ttu-id="88180-3613">DriverLics</span><span class="sxs-lookup"><span data-stu-id="88180-3613">DriverLics</span></span> 
- <span data-ttu-id="88180-3614">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="88180-3614">DriverLicense</span></span> 
- <span data-ttu-id="88180-3615">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-3615">DriverLicenses</span></span> 
- <span data-ttu-id="88180-3616">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-3616">Driver Lic</span></span> 
- <span data-ttu-id="88180-3617">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-3617">Driver Lics</span></span> 
- <span data-ttu-id="88180-3618">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-3618">Driver License</span></span> 
- <span data-ttu-id="88180-3619">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-3619">Driver Licenses</span></span> 
- <span data-ttu-id="88180-3620">DriversLic</span><span class="sxs-lookup"><span data-stu-id="88180-3620">DriversLic</span></span> 
- <span data-ttu-id="88180-3621">DriversLics</span><span class="sxs-lookup"><span data-stu-id="88180-3621">DriversLics</span></span> 
- <span data-ttu-id="88180-3622">執照</span><span class="sxs-lookup"><span data-stu-id="88180-3622">DriversLicense</span></span> 
- <span data-ttu-id="88180-3623">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-3623">DriversLicenses</span></span> 
- <span data-ttu-id="88180-3624">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-3624">Drivers Lic</span></span> 
- <span data-ttu-id="88180-3625">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-3625">Drivers Lics</span></span> 
- <span data-ttu-id="88180-3626">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-3626">Drivers License</span></span> 
- <span data-ttu-id="88180-3627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="88180-3627">Drivers Licenses</span></span> 
- <span data-ttu-id="88180-3628">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="88180-3628">Driver'Lic</span></span> 
- <span data-ttu-id="88180-3629">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="88180-3629">Driver'Lics</span></span> 
- <span data-ttu-id="88180-3630">Driver'License</span><span class="sxs-lookup"><span data-stu-id="88180-3630">Driver'License</span></span> 
- <span data-ttu-id="88180-3631">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="88180-3631">Driver'Licenses</span></span> 
- <span data-ttu-id="88180-3632">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="88180-3632">Driver' Lic</span></span> 
- <span data-ttu-id="88180-3633">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="88180-3633">Driver' Lics</span></span> 
- <span data-ttu-id="88180-3634">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-3634">Driver' License</span></span> 
- <span data-ttu-id="88180-3635">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="88180-3635">Driver' Licenses</span></span>
- <span data-ttu-id="88180-3636">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="88180-3636">Driver'sLic</span></span> 
- <span data-ttu-id="88180-3637">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="88180-3637">Driver'sLics</span></span> 
- <span data-ttu-id="88180-3638">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="88180-3638">Driver'sLicense</span></span> 
- <span data-ttu-id="88180-3639">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="88180-3639">Driver'sLicenses</span></span> 
- <span data-ttu-id="88180-3640">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="88180-3640">Driver's Lic</span></span> 
- <span data-ttu-id="88180-3641">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="88180-3641">Driver's Lics</span></span> 
- <span data-ttu-id="88180-3642">駕照</span><span class="sxs-lookup"><span data-stu-id="88180-3642">Driver's License</span></span> 
- <span data-ttu-id="88180-3643">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="88180-3643">Driver's Licenses</span></span> 
- <span data-ttu-id="88180-3644">識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3644">identification number</span></span> 
- <span data-ttu-id="88180-3645">識別數字</span><span class="sxs-lookup"><span data-stu-id="88180-3645">identification numbers</span></span> 
- <span data-ttu-id="88180-3646">識別 #</span><span class="sxs-lookup"><span data-stu-id="88180-3646">identification #</span></span> 
- <span data-ttu-id="88180-3647">證</span><span class="sxs-lookup"><span data-stu-id="88180-3647">id card</span></span> 
- <span data-ttu-id="88180-3648">id 卡</span><span class="sxs-lookup"><span data-stu-id="88180-3648">id cards</span></span> 
- <span data-ttu-id="88180-3649">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-3649">identification card</span></span> 
- <span data-ttu-id="88180-3650">識別卡</span><span class="sxs-lookup"><span data-stu-id="88180-3650">identification cards</span></span> 
- <span data-ttu-id="88180-3651">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="88180-3651">DriverLic#</span></span> 
- <span data-ttu-id="88180-3652">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="88180-3652">DriverLics#</span></span> 
- <span data-ttu-id="88180-3653">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="88180-3653">DriverLicense#</span></span> 
- <span data-ttu-id="88180-3654">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-3654">DriverLicenses#</span></span> 
- <span data-ttu-id="88180-3655">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-3655">Driver Lic#</span></span> 
- <span data-ttu-id="88180-3656">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-3656">Driver Lics#</span></span> 
- <span data-ttu-id="88180-3657">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3657">Driver License#</span></span> 
- <span data-ttu-id="88180-3658">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3658">Driver Licenses#</span></span> 
- <span data-ttu-id="88180-3659">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="88180-3659">DriversLic#</span></span> 
- <span data-ttu-id="88180-3660">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="88180-3660">DriversLics#</span></span> 
- <span data-ttu-id="88180-3661">執照 #</span><span class="sxs-lookup"><span data-stu-id="88180-3661">DriversLicense#</span></span> 
- <span data-ttu-id="88180-3662">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-3662">DriversLicenses#</span></span> 
- <span data-ttu-id="88180-3663">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-3663">Drivers Lic#</span></span> 
- <span data-ttu-id="88180-3664">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-3664">Drivers Lics#</span></span> 
- <span data-ttu-id="88180-3665">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3665">Drivers License#</span></span> 
- <span data-ttu-id="88180-3666">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3666">Drivers Licenses#</span></span> 
- <span data-ttu-id="88180-3667">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-3667">Driver'Lic#</span></span> 
- <span data-ttu-id="88180-3668">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-3668">Driver'Lics#</span></span> 
- <span data-ttu-id="88180-3669">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="88180-3669">Driver'License#</span></span> 
- <span data-ttu-id="88180-3670">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="88180-3670">Driver'Licenses#</span></span> 
- <span data-ttu-id="88180-3671">驅動程式 ' Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-3671">Driver' Lic#</span></span> 
- <span data-ttu-id="88180-3672">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-3672">Driver' Lics#</span></span> 
- <span data-ttu-id="88180-3673">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3673">Driver' License#</span></span> 
- <span data-ttu-id="88180-3674">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3674">Driver' Licenses#</span></span> 
- <span data-ttu-id="88180-3675">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="88180-3675">Driver'sLic#</span></span> 
- <span data-ttu-id="88180-3676">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="88180-3676">Driver'sLics#</span></span> 
- <span data-ttu-id="88180-3677">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="88180-3677">Driver'sLicense#</span></span> 
- <span data-ttu-id="88180-3678">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="88180-3678">Driver'sLicenses#</span></span> 
- <span data-ttu-id="88180-3679">駕 Lic #</span><span class="sxs-lookup"><span data-stu-id="88180-3679">Driver's Lic#</span></span> 
- <span data-ttu-id="88180-3680">駕 Lics #</span><span class="sxs-lookup"><span data-stu-id="88180-3680">Driver's Lics#</span></span> 
- <span data-ttu-id="88180-3681">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3681">Driver's License#</span></span> 
- <span data-ttu-id="88180-3682">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="88180-3682">Driver's Licenses#</span></span> 
- <span data-ttu-id="88180-3683">證 #</span><span class="sxs-lookup"><span data-stu-id="88180-3683">id card#</span></span> 
- <span data-ttu-id="88180-3684">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-3684">id cards#</span></span> 
- <span data-ttu-id="88180-3685">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-3685">identification card#</span></span> 
- <span data-ttu-id="88180-3686">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="88180-3686">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="88180-3687">於 Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="88180-3687">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="88180-3688">州別縮寫 (例如"NY")</span><span class="sxs-lookup"><span data-stu-id="88180-3688">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="88180-3689">州名稱 (例如"New York")</span><span class="sxs-lookup"><span data-stu-id="88180-3689">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="88180-3690">美國個別 Taxpayer 識別號碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="88180-3690">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-3691">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3691">Format</span></span>

<span data-ttu-id="88180-3692">九位數，以"9"開頭且包含"7"8"的第四個位數，可選擇加上空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3692">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3693">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3693">Pattern</span></span>

<span data-ttu-id="88180-3694">格式：</span><span class="sxs-lookup"><span data-stu-id="88180-3694">Formatted:</span></span>
- <span data-ttu-id="88180-3695">數字"9"</span><span class="sxs-lookup"><span data-stu-id="88180-3695">The digit "9"</span></span> 
- <span data-ttu-id="88180-3696">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3696">Two digits</span></span> 
- <span data-ttu-id="88180-3697">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3697">A space or dash</span></span> 
- <span data-ttu-id="88180-3698">"7"或者"8"</span><span class="sxs-lookup"><span data-stu-id="88180-3698">A "7" or "8"</span></span> 
- <span data-ttu-id="88180-3699">數字</span><span class="sxs-lookup"><span data-stu-id="88180-3699">A digit</span></span> 
- <span data-ttu-id="88180-3700">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="88180-3700">A space, or dash</span></span> 
- <span data-ttu-id="88180-3701">四位數</span><span class="sxs-lookup"><span data-stu-id="88180-3701">Four digits</span></span>

<span data-ttu-id="88180-3702">格式化：</span><span class="sxs-lookup"><span data-stu-id="88180-3702">Unformatted:</span></span>
- <span data-ttu-id="88180-3703">數字"9"</span><span class="sxs-lookup"><span data-stu-id="88180-3703">The digit "9"</span></span> 
- <span data-ttu-id="88180-3704">兩位數</span><span class="sxs-lookup"><span data-stu-id="88180-3704">Two digits</span></span> 
- <span data-ttu-id="88180-3705">"7"或者"8"</span><span class="sxs-lookup"><span data-stu-id="88180-3705">A "7" or "8"</span></span> 
- <span data-ttu-id="88180-3706">五位數</span><span class="sxs-lookup"><span data-stu-id="88180-3706">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3707">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3707">Checksum</span></span>

<span data-ttu-id="88180-3708">否</span><span class="sxs-lookup"><span data-stu-id="88180-3708">No</span></span>

### <a name="definition"></a><span data-ttu-id="88180-3709">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3709">Definition</span></span>

<span data-ttu-id="88180-3710">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3710">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3711">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3711">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3712">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="88180-3712">At least one of the following is true:</span></span>
    - <span data-ttu-id="88180-3713">找不到來自 Keyword_itin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3713">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="88180-3714">函數 Func_us_address 找到正確日期格式中的地址。</span><span class="sxs-lookup"><span data-stu-id="88180-3714">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="88180-3715">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-3715">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="88180-3716">找不到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3716">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="88180-3717">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3717">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3718">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3718">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3719">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="88180-3719">At least one of the following is true:</span></span>
    - <span data-ttu-id="88180-3720">找不到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3720">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="88180-3721">函數 Func_us_address 找到正確日期格式中的地址。</span><span class="sxs-lookup"><span data-stu-id="88180-3721">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="88180-3722">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="88180-3722">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3723">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3723">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="88180-3724">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="88180-3724">Keyword_itin</span></span>

- <span data-ttu-id="88180-3725">taxpayer</span><span class="sxs-lookup"><span data-stu-id="88180-3725">taxpayer</span></span> 
- <span data-ttu-id="88180-3726">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3726">tax id</span></span> 
- <span data-ttu-id="88180-3727">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="88180-3727">tax identification</span></span> 
- <span data-ttu-id="88180-3728">itin</span><span class="sxs-lookup"><span data-stu-id="88180-3728">itin</span></span> 
- <span data-ttu-id="88180-3729">ssn</span><span class="sxs-lookup"><span data-stu-id="88180-3729">ssn</span></span> 
- <span data-ttu-id="88180-3730">錫</span><span class="sxs-lookup"><span data-stu-id="88180-3730">tin</span></span> 
- <span data-ttu-id="88180-3731">社會安全</span><span class="sxs-lookup"><span data-stu-id="88180-3731">social security</span></span> 
- <span data-ttu-id="88180-3732">稅務付款者</span><span class="sxs-lookup"><span data-stu-id="88180-3732">tax payer</span></span> 
- <span data-ttu-id="88180-3733">itins</span><span class="sxs-lookup"><span data-stu-id="88180-3733">itins</span></span> 
- <span data-ttu-id="88180-3734">taxid</span><span class="sxs-lookup"><span data-stu-id="88180-3734">taxid</span></span> 
- <span data-ttu-id="88180-3735">個別 taxpayer</span><span class="sxs-lookup"><span data-stu-id="88180-3735">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="88180-3736">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="88180-3736">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="88180-3737">License</span><span class="sxs-lookup"><span data-stu-id="88180-3737">License</span></span> 
- <span data-ttu-id="88180-3738">DL</span><span class="sxs-lookup"><span data-stu-id="88180-3738">DL</span></span> 
- <span data-ttu-id="88180-3739">DOB</span><span class="sxs-lookup"><span data-stu-id="88180-3739">DOB</span></span> 
- <span data-ttu-id="88180-3740">出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3740">Birthdate</span></span> 
- <span data-ttu-id="88180-3741">生日</span><span class="sxs-lookup"><span data-stu-id="88180-3741">Birthday</span></span> 
- <span data-ttu-id="88180-3742">出生日期</span><span class="sxs-lookup"><span data-stu-id="88180-3742">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="88180-3743">美國社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="88180-3743">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="88180-3744">Format</span><span class="sxs-lookup"><span data-stu-id="88180-3744">Format</span></span>

<span data-ttu-id="88180-3745">9 位數，可採用格式化或未格式化模式</span><span class="sxs-lookup"><span data-stu-id="88180-3745">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="88180-3746">SSN 如果發出 mid 2011 之前，已增強式格式設定其中某些部分的數字必須落在有效特定範圍內 （但沒有任何總和檢查碼）。</span><span class="sxs-lookup"><span data-stu-id="88180-3746">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="88180-3747">模式</span><span class="sxs-lookup"><span data-stu-id="88180-3747">Pattern</span></span>

<span data-ttu-id="88180-3748">四個函數尋找 Ssn 四個不同的模式：</span><span class="sxs-lookup"><span data-stu-id="88180-3748">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="88180-3749">Func_ssn 找到與預先 2011年強式的格式設定，以連字號或空格 (ddd ddd-dd-dddd 或 ddd dd dddd) 格式化 Ssn</span><span class="sxs-lookup"><span data-stu-id="88180-3749">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="88180-3750">Func_unformatted_ssn 找尋找 Ssn 具有預先 2011年強式的格式設定，會以未格式化為九個連續數字 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="88180-3750">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="88180-3751">Func_randomized_formatted_ssn 找到以連字號或空格 (ddd ddd-dd-dddd 或 ddd dd dddd) 格式化的文章 2011 Ssn</span><span class="sxs-lookup"><span data-stu-id="88180-3751">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="88180-3752">Func_randomized_unformatted_ssn 找到 post 2011 Ssn 所格式化為九個連續數字 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="88180-3752">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="88180-3753">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="88180-3753">Checksum</span></span>

<span data-ttu-id="88180-3754">否</span><span class="sxs-lookup"><span data-stu-id="88180-3754">No</span></span>


### <a name="definition"></a><span data-ttu-id="88180-3755">定義</span><span class="sxs-lookup"><span data-stu-id="88180-3755">Definition</span></span>

<span data-ttu-id="88180-3756">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3757">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3757">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3758">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3758">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="88180-3759">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3759">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3760">函數 func_unformatted_ssn 找找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3760">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3761">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3761">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="88180-3762">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3762">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3763">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3763">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3764">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3764">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="88180-3765">函數 func_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3765">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="88180-3766">DLP 原則是 55%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="88180-3766">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="88180-3767">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3767">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="88180-3768">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="88180-3768">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="88180-3769">函數 func_unformatted_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="88180-3769">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="88180-3770">關鍵字</span><span class="sxs-lookup"><span data-stu-id="88180-3770">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="88180-3771">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="88180-3771">Keyword_ssn</span></span>

- <span data-ttu-id="88180-3772">社會安全</span><span class="sxs-lookup"><span data-stu-id="88180-3772">Social Security</span></span> 
- <span data-ttu-id="88180-3773">社會安全 #</span><span class="sxs-lookup"><span data-stu-id="88180-3773">Social Security#</span></span> 
- <span data-ttu-id="88180-3774">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="88180-3774">Soc Sec</span></span> 
- <span data-ttu-id="88180-3775">SSN</span><span class="sxs-lookup"><span data-stu-id="88180-3775">SSN</span></span> 
- <span data-ttu-id="88180-3776">SSN</span><span class="sxs-lookup"><span data-stu-id="88180-3776">SSNS</span></span> 
- <span data-ttu-id="88180-3777">SSN #</span><span class="sxs-lookup"><span data-stu-id="88180-3777">SSN#</span></span> 
- <span data-ttu-id="88180-3778">SS #</span><span class="sxs-lookup"><span data-stu-id="88180-3778">SS#</span></span> 
- <span data-ttu-id="88180-3779">SSID</span><span class="sxs-lookup"><span data-stu-id="88180-3779">SSID</span></span> 
   

