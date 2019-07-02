---
title: 敏感資訊類型在找什麼
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/20/2019
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全&amp;規範中心中的資料遺失防護 (DLP) 包含80機密資訊類型, 可供您在 DLP 原則中使用。 本主題列出所有的敏感資訊類型, 並顯示 DLP 原則在偵測每個類型時所尋找的內容。
ms.openlocfilehash: 1e1aeea164c15bb64c6040f7821bf006ee8ff42f
ms.sourcegitcommit: b8737e52724a343d99082961bc113bba819d5681
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "34247296"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="2102f-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="2102f-104">What the sensitive information types look for</span></span>

<span data-ttu-id="2102f-105">Office 365 安全&amp;規範中心中的資料遺失防護 (DLP) 包含許多機密資訊類型, 可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="2102f-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="2102f-106">本主題列出所有的敏感資訊類型, 並顯示 DLP 原則在偵測每個類型時所尋找的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="2102f-107">機密資訊類型是以可以由正則運算式或函數識別的模式所定義。</span><span class="sxs-lookup"><span data-stu-id="2102f-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="2102f-108">此外, 確切的證據 (例如關鍵字和校驗和) 可以用來識別敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2102f-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="2102f-109">評估程式中也會使用信賴等級和鄰近性。</span><span class="sxs-lookup"><span data-stu-id="2102f-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="2102f-110">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-111">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-111">Format</span></span>

<span data-ttu-id="2102f-112">可能是格式化或未格式化模式的9位數</span><span class="sxs-lookup"><span data-stu-id="2102f-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-113">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-113">Pattern</span></span>

<span data-ttu-id="2102f-114">格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-114">Formatted:</span></span>
- <span data-ttu-id="2102f-115">以0、1、2、3、6、7或8開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="2102f-116">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-116">A hyphen</span></span>
- <span data-ttu-id="2102f-117">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-117">Four digits</span></span>
- <span data-ttu-id="2102f-118">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-118">A hyphen</span></span>
- <span data-ttu-id="2102f-119">一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-119">A digit</span></span>

<span data-ttu-id="2102f-120">未格式化: 以0、1、2、3、6、7或8開頭的9個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="2102f-121">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-121">Checksum</span></span>

<span data-ttu-id="2102f-122">否</span><span class="sxs-lookup"><span data-stu-id="2102f-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-123">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-123">Definition</span></span>

<span data-ttu-id="2102f-124">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-126">找到 Keyword_ABA_Routing 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="2102f-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="2102f-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="2102f-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="2102f-129">aba</span><span class="sxs-lookup"><span data-stu-id="2102f-129">aba</span></span>
- <span data-ttu-id="2102f-130">aba</span><span class="sxs-lookup"><span data-stu-id="2102f-130">aba #</span></span>
- <span data-ttu-id="2102f-131">aba 路由 #</span><span class="sxs-lookup"><span data-stu-id="2102f-131">aba routing #</span></span>
- <span data-ttu-id="2102f-132">aba 路由號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-132">aba routing number</span></span>
- <span data-ttu-id="2102f-133">aba</span><span class="sxs-lookup"><span data-stu-id="2102f-133">aba#</span></span>
- <span data-ttu-id="2102f-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="2102f-134">abarouting#</span></span>
- <span data-ttu-id="2102f-135">aba 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-135">aba number</span></span>
- <span data-ttu-id="2102f-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-136">abaroutingnumber</span></span>
- <span data-ttu-id="2102f-137">美洲銀行關聯路由 #</span><span class="sxs-lookup"><span data-stu-id="2102f-137">american bank association routing #</span></span>
- <span data-ttu-id="2102f-138">美洲銀行關聯路由號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-138">american bank association routing number</span></span>
- <span data-ttu-id="2102f-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="2102f-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="2102f-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="2102f-141">銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-141">bank routing number</span></span>
- <span data-ttu-id="2102f-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="2102f-142">bankrouting#</span></span>
- <span data-ttu-id="2102f-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-143">bankroutingnumber</span></span>
- <span data-ttu-id="2102f-144">路由傳輸號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-144">routing transit number</span></span>
- <span data-ttu-id="2102f-145">RTN</span><span class="sxs-lookup"><span data-stu-id="2102f-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="2102f-146">阿根廷民族身分識別 (DNI) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-147">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-147">Format</span></span>

<span data-ttu-id="2102f-148">以句點隔開的八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-149">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-149">Pattern</span></span>

<span data-ttu-id="2102f-150">八位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-150">Eight digits:</span></span>
- <span data-ttu-id="2102f-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-151">Two digits</span></span>
- <span data-ttu-id="2102f-152">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-152">A period</span></span>
- <span data-ttu-id="2102f-153">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-153">Three digits</span></span>
- <span data-ttu-id="2102f-154">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-154">A period</span></span>
- <span data-ttu-id="2102f-155">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-156">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-156">Checksum</span></span>

<span data-ttu-id="2102f-157">否</span><span class="sxs-lookup"><span data-stu-id="2102f-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-158">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-158">Definition</span></span>

<span data-ttu-id="2102f-159">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-160">正則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-161">找到 Keyword_argentina_national_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="2102f-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="2102f-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="2102f-164">阿根廷國內身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="2102f-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="2102f-165">Identity</span></span> 
- <span data-ttu-id="2102f-166">身分識別民族身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="2102f-167">DNI</span><span class="sxs-lookup"><span data-stu-id="2102f-167">DNI</span></span> 
- <span data-ttu-id="2102f-168">個人的 NIC 登錄</span><span class="sxs-lookup"><span data-stu-id="2102f-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="2102f-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="2102f-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="2102f-170">Registro Nacional de 內華達角色</span><span class="sxs-lookup"><span data-stu-id="2102f-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="2102f-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="2102f-171">Identidad</span></span> 
- <span data-ttu-id="2102f-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="2102f-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="2102f-173">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-174">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-174">Format</span></span>

<span data-ttu-id="2102f-175">含或不含銀行狀態分公司號碼的6-10 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-176">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-176">Pattern</span></span>

<span data-ttu-id="2102f-177">帳戶號碼是6-10 位數。</span><span class="sxs-lookup"><span data-stu-id="2102f-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="2102f-178">澳大利亞銀行狀態分公司號碼:</span><span class="sxs-lookup"><span data-stu-id="2102f-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="2102f-179">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-179">Three digits</span></span> 
- <span data-ttu-id="2102f-180">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-180">A hyphen</span></span> 
- <span data-ttu-id="2102f-181">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-182">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-182">Checksum</span></span>

<span data-ttu-id="2102f-183">否</span><span class="sxs-lookup"><span data-stu-id="2102f-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-184">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-184">Definition</span></span>

<span data-ttu-id="2102f-185">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-186">正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="2102f-187">找到 Keyword_australia_bank_account_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="2102f-188">正則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="2102f-189">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-190">正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="2102f-191">找到 Keyword_australia_bank_account_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="2102f-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2102f-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="2102f-194">swift 銀行代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-194">swift bank code</span></span>
- <span data-ttu-id="2102f-195">通信銀行</span><span class="sxs-lookup"><span data-stu-id="2102f-195">correspondent bank</span></span>
- <span data-ttu-id="2102f-196">基礎貨幣</span><span class="sxs-lookup"><span data-stu-id="2102f-196">base currency</span></span>
- <span data-ttu-id="2102f-197">美國帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-197">usa account</span></span>
- <span data-ttu-id="2102f-198">持有者位址</span><span class="sxs-lookup"><span data-stu-id="2102f-198">holder address</span></span>
- <span data-ttu-id="2102f-199">銀行位址</span><span class="sxs-lookup"><span data-stu-id="2102f-199">bank address</span></span>
- <span data-ttu-id="2102f-200">資訊帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-200">information account</span></span>
- <span data-ttu-id="2102f-201">基金傳輸</span><span class="sxs-lookup"><span data-stu-id="2102f-201">fund transfers</span></span>
- <span data-ttu-id="2102f-202">銀行費用</span><span class="sxs-lookup"><span data-stu-id="2102f-202">bank charges</span></span>
- <span data-ttu-id="2102f-203">銀行詳細資料</span><span class="sxs-lookup"><span data-stu-id="2102f-203">bank details</span></span>
- <span data-ttu-id="2102f-204">銀行資訊</span><span class="sxs-lookup"><span data-stu-id="2102f-204">banking information</span></span>
- <span data-ttu-id="2102f-205">完整名稱</span><span class="sxs-lookup"><span data-stu-id="2102f-205">full names</span></span>
- <span data-ttu-id="2102f-206">iaea</span><span class="sxs-lookup"><span data-stu-id="2102f-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="2102f-207">澳大利亞駕照編號</span><span class="sxs-lookup"><span data-stu-id="2102f-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-208">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-208">Format</span></span>

<span data-ttu-id="2102f-209">九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="2102f-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-210">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-210">Pattern</span></span>

<span data-ttu-id="2102f-211">九個字母和數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="2102f-212">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-213">Two digits</span></span> 
- <span data-ttu-id="2102f-214">五個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="2102f-215">或</span><span class="sxs-lookup"><span data-stu-id="2102f-215">OR</span></span>

- <span data-ttu-id="2102f-216">1-2 選用字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-217">4-9 digits</span></span>

<span data-ttu-id="2102f-218">或</span><span class="sxs-lookup"><span data-stu-id="2102f-218">OR</span></span>

- <span data-ttu-id="2102f-219">九個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-220">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-220">Checksum</span></span>

<span data-ttu-id="2102f-221">否</span><span class="sxs-lookup"><span data-stu-id="2102f-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-222">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-222">Definition</span></span>

<span data-ttu-id="2102f-223">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-224">正則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-225">找到 Keyword_australia_drivers_license_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="2102f-226">找不到 Keyword_australia_drivers_license_number_exclusions 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="2102f-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2102f-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="2102f-229">國際驅動允許</span><span class="sxs-lookup"><span data-stu-id="2102f-229">international driving permits</span></span>
- <span data-ttu-id="2102f-230">澳大利亞汽車協會</span><span class="sxs-lookup"><span data-stu-id="2102f-230">australian automobile association</span></span>
- <span data-ttu-id="2102f-231">國際駕駛允許</span><span class="sxs-lookup"><span data-stu-id="2102f-231">international driving permit</span></span>
- <span data-ttu-id="2102f-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="2102f-232">DriverLicence</span></span>
- <span data-ttu-id="2102f-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="2102f-233">DriverLicences</span></span>
- <span data-ttu-id="2102f-234">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-234">Driver Lic</span></span>
- <span data-ttu-id="2102f-235">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-235">Driver Licence</span></span>
- <span data-ttu-id="2102f-236">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-236">Driver Licences</span></span>
- <span data-ttu-id="2102f-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2102f-237">DriversLic</span></span>
- <span data-ttu-id="2102f-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="2102f-238">DriversLicence</span></span>
- <span data-ttu-id="2102f-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="2102f-239">DriversLicences</span></span>
- <span data-ttu-id="2102f-240">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-240">Drivers Lic</span></span>
- <span data-ttu-id="2102f-241">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-241">Drivers Lics</span></span>
- <span data-ttu-id="2102f-242">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-242">Drivers Licence</span></span>
- <span data-ttu-id="2102f-243">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-243">Drivers Licences</span></span>
- <span data-ttu-id="2102f-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-244">Driver'Lic</span></span>
- <span data-ttu-id="2102f-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-245">Driver'Lics</span></span>
- <span data-ttu-id="2102f-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2102f-246">Driver'Licence</span></span>
- <span data-ttu-id="2102f-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2102f-247">Driver'Licences</span></span>
- <span data-ttu-id="2102f-248">驅動程式 ' .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-248">Driver' Lic</span></span>
- <span data-ttu-id="2102f-249">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-249">Driver' Lics</span></span>
- <span data-ttu-id="2102f-250">驅動程式 ' 許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-250">Driver' Licence</span></span>
- <span data-ttu-id="2102f-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-251">Driver' Licences</span></span>
- <span data-ttu-id="2102f-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2102f-252">Driver'sLic</span></span>
- <span data-ttu-id="2102f-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2102f-253">Driver'sLics</span></span>
- <span data-ttu-id="2102f-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="2102f-254">Driver'sLicence</span></span>
- <span data-ttu-id="2102f-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="2102f-255">Driver'sLicences</span></span>
- <span data-ttu-id="2102f-256">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-256">Driver's Lic</span></span>
- <span data-ttu-id="2102f-257">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-257">Driver's Lics</span></span>
- <span data-ttu-id="2102f-258">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-258">Driver's Licence</span></span>
- <span data-ttu-id="2102f-259">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-259">Driver's Licences</span></span>
- <span data-ttu-id="2102f-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-260">DriverLic#</span></span>
- <span data-ttu-id="2102f-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-261">DriverLics#</span></span>
- <span data-ttu-id="2102f-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="2102f-262">DriverLicence#</span></span>
- <span data-ttu-id="2102f-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="2102f-263">DriverLicences#</span></span>
- <span data-ttu-id="2102f-264">驅動程式 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-264">Driver Lic#</span></span>
- <span data-ttu-id="2102f-265">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-265">Driver Lics#</span></span>
- <span data-ttu-id="2102f-266">驅動程式許可證 #</span><span class="sxs-lookup"><span data-stu-id="2102f-266">Driver Licence#</span></span>
- <span data-ttu-id="2102f-267">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-267">Driver Licences#</span></span>
- <span data-ttu-id="2102f-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-268">DriversLic#</span></span>
- <span data-ttu-id="2102f-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-269">DriversLics#</span></span>
- <span data-ttu-id="2102f-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="2102f-270">DriversLicence#</span></span>
- <span data-ttu-id="2102f-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="2102f-271">DriversLicences#</span></span>
- <span data-ttu-id="2102f-272">驅動程式 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-272">Drivers Lic#</span></span>
- <span data-ttu-id="2102f-273">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-273">Drivers Lics#</span></span>
- <span data-ttu-id="2102f-274">驅動程式許可證 #</span><span class="sxs-lookup"><span data-stu-id="2102f-274">Drivers Licence#</span></span>
- <span data-ttu-id="2102f-275">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-275">Drivers Licences#</span></span>
- <span data-ttu-id="2102f-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="2102f-276">Driver'Lic#</span></span>
- <span data-ttu-id="2102f-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="2102f-277">Driver'Lics#</span></span>
- <span data-ttu-id="2102f-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="2102f-278">Driver'Licence#</span></span>
- <span data-ttu-id="2102f-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="2102f-279">Driver'Licences#</span></span>
- <span data-ttu-id="2102f-280">驅動程式 ' .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-280">Driver' Lic#</span></span>
- <span data-ttu-id="2102f-281">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-281">Driver' Lics#</span></span>
- <span data-ttu-id="2102f-282">驅動程式 ' 許可證 #</span><span class="sxs-lookup"><span data-stu-id="2102f-282">Driver' Licence#</span></span>
- <span data-ttu-id="2102f-283">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-283">Driver' Licences#</span></span>
- <span data-ttu-id="2102f-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-284">Driver'sLic#</span></span>
- <span data-ttu-id="2102f-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-285">Driver'sLics#</span></span>
- <span data-ttu-id="2102f-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="2102f-286">Driver'sLicence#</span></span>
- <span data-ttu-id="2102f-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="2102f-287">Driver'sLicences#</span></span>
- <span data-ttu-id="2102f-288">驅動程式的 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-288">Driver's Lic#</span></span>
- <span data-ttu-id="2102f-289">Driver 的 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-289">Driver's Lics#</span></span>
- <span data-ttu-id="2102f-290">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-290">Driver's Licence#</span></span>
- <span data-ttu-id="2102f-291">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="2102f-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="2102f-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="2102f-293">aaa</span><span class="sxs-lookup"><span data-stu-id="2102f-293">aaa</span></span>
- <span data-ttu-id="2102f-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-294">DriverLicense</span></span>
- <span data-ttu-id="2102f-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-295">DriverLicenses</span></span>
- <span data-ttu-id="2102f-296">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-296">Driver License</span></span>
- <span data-ttu-id="2102f-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-297">Driver Licenses</span></span>
- <span data-ttu-id="2102f-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-298">DriversLicense</span></span>
- <span data-ttu-id="2102f-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-299">DriversLicenses</span></span>
- <span data-ttu-id="2102f-300">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-300">Drivers License</span></span>
- <span data-ttu-id="2102f-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-301">Drivers Licenses</span></span>
- <span data-ttu-id="2102f-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="2102f-302">Driver'License</span></span>
- <span data-ttu-id="2102f-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="2102f-303">Driver'Licenses</span></span>
- <span data-ttu-id="2102f-304">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-304">Driver' License</span></span>
- <span data-ttu-id="2102f-305">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-305">Driver' Licenses</span></span>
- <span data-ttu-id="2102f-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-306">Driver'sLicense</span></span>
- <span data-ttu-id="2102f-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-307">Driver'sLicenses</span></span>
- <span data-ttu-id="2102f-308">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-308">Driver's License</span></span>
- <span data-ttu-id="2102f-309">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-309">Driver's Licenses</span></span>
- <span data-ttu-id="2102f-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-310">DriverLicense#</span></span>
- <span data-ttu-id="2102f-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-311">DriverLicenses#</span></span>
- <span data-ttu-id="2102f-312">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-312">Driver License#</span></span>
- <span data-ttu-id="2102f-313">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-313">Driver Licenses#</span></span>
- <span data-ttu-id="2102f-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-314">DriversLicense#</span></span>
- <span data-ttu-id="2102f-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-315">DriversLicenses#</span></span>
- <span data-ttu-id="2102f-316">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-316">Drivers License#</span></span>
- <span data-ttu-id="2102f-317">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-317">Drivers Licenses#</span></span>
- <span data-ttu-id="2102f-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="2102f-318">Driver'License#</span></span>
- <span data-ttu-id="2102f-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-319">Driver'Licenses#</span></span>
- <span data-ttu-id="2102f-320">驅動程式 ' License #</span><span class="sxs-lookup"><span data-stu-id="2102f-320">Driver' License#</span></span>
- <span data-ttu-id="2102f-321">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-321">Driver' Licenses#</span></span>
- <span data-ttu-id="2102f-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-322">Driver'sLicense#</span></span>
- <span data-ttu-id="2102f-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="2102f-324">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-324">Driver's License#</span></span>
- <span data-ttu-id="2102f-325">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="2102f-326">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-327">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-327">Format</span></span>

<span data-ttu-id="2102f-328">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-329">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-329">Pattern</span></span>

<span data-ttu-id="2102f-330">10-11 位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-330">10-11 digits:</span></span>
- <span data-ttu-id="2102f-331">第一個數位在2-6 的範圍內</span><span class="sxs-lookup"><span data-stu-id="2102f-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="2102f-332">第九個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="2102f-333">第十個數字是發行位數</span><span class="sxs-lookup"><span data-stu-id="2102f-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="2102f-334">第十個數字 (選用) 是個別的數位</span><span class="sxs-lookup"><span data-stu-id="2102f-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-335">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-335">Checksum</span></span>

<span data-ttu-id="2102f-336">是</span><span class="sxs-lookup"><span data-stu-id="2102f-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-337">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-337">Definition</span></span>

<span data-ttu-id="2102f-338">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 95%:</span><span class="sxs-lookup"><span data-stu-id="2102f-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-339">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-340">找到 Keyword_Australia_Medical_Account_Number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="2102f-341">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-341">The checksum passes.</span></span>

<span data-ttu-id="2102f-342">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-343">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-344">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="2102f-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="2102f-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="2102f-347">銀行帳戶詳細資料</span><span class="sxs-lookup"><span data-stu-id="2102f-347">bank account details</span></span>
- <span data-ttu-id="2102f-348">medicare 付款</span><span class="sxs-lookup"><span data-stu-id="2102f-348">medicare payments</span></span>
- <span data-ttu-id="2102f-349">抵押帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-349">mortgage account</span></span>
- <span data-ttu-id="2102f-350">銀行付款</span><span class="sxs-lookup"><span data-stu-id="2102f-350">bank payments</span></span>
- <span data-ttu-id="2102f-351">資訊分支</span><span class="sxs-lookup"><span data-stu-id="2102f-351">information branch</span></span>
- <span data-ttu-id="2102f-352">信用卡貸款</span><span class="sxs-lookup"><span data-stu-id="2102f-352">credit card loan</span></span>
- <span data-ttu-id="2102f-353">人力服務部門</span><span class="sxs-lookup"><span data-stu-id="2102f-353">department of human services</span></span>
- <span data-ttu-id="2102f-354">本機服務</span><span class="sxs-lookup"><span data-stu-id="2102f-354">local service</span></span>
- <span data-ttu-id="2102f-355">medicare</span><span class="sxs-lookup"><span data-stu-id="2102f-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="2102f-356">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-357">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-357">Format</span></span>

<span data-ttu-id="2102f-358">字母后尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-359">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-359">Pattern</span></span>

<span data-ttu-id="2102f-360">字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-361">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-361">Checksum</span></span>

<span data-ttu-id="2102f-362">否</span><span class="sxs-lookup"><span data-stu-id="2102f-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-363">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-363">Definition</span></span>

<span data-ttu-id="2102f-364">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-365">正則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-366">找到 Keyword_passport 或 Keyword_australia_passport_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2102f-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-368">Keyword_passport</span></span>

- <span data-ttu-id="2102f-369">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-369">Passport Number</span></span>
- <span data-ttu-id="2102f-370">護照否</span><span class="sxs-lookup"><span data-stu-id="2102f-370">Passport No</span></span>
- <span data-ttu-id="2102f-371">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-371">Passport #</span></span>
- <span data-ttu-id="2102f-372">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-372">Passport#</span></span>
- <span data-ttu-id="2102f-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="2102f-373">PassportID</span></span>
- <span data-ttu-id="2102f-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="2102f-374">Passportno</span></span>
- <span data-ttu-id="2102f-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-375">passportnumber</span></span>
- <span data-ttu-id="2102f-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="2102f-376">パスポート</span></span>
- <span data-ttu-id="2102f-377">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="2102f-377">パスポート番号</span></span>
- <span data-ttu-id="2102f-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2102f-378">パスポートのNum</span></span>
- <span data-ttu-id="2102f-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="2102f-379">パスポート ＃</span></span> 
- <span data-ttu-id="2102f-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2102f-380">Numéro de passeport</span></span>
- <span data-ttu-id="2102f-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2102f-381">Passeport n °</span></span>
- <span data-ttu-id="2102f-382">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="2102f-382">Passeport Non</span></span>
- <span data-ttu-id="2102f-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2102f-383">Passeport #</span></span>
- <span data-ttu-id="2102f-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2102f-384">Passeport#</span></span>
- <span data-ttu-id="2102f-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2102f-385">PasseportNon</span></span>
- <span data-ttu-id="2102f-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2102f-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="2102f-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="2102f-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="2102f-388">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-388">passport</span></span>
- <span data-ttu-id="2102f-389">護照詳細資料</span><span class="sxs-lookup"><span data-stu-id="2102f-389">passport details</span></span>
- <span data-ttu-id="2102f-390">immigration 和公民</span><span class="sxs-lookup"><span data-stu-id="2102f-390">immigration and citizenship</span></span>
- <span data-ttu-id="2102f-391">澳大利亞英聯邦</span><span class="sxs-lookup"><span data-stu-id="2102f-391">commonwealth of australia</span></span>
- <span data-ttu-id="2102f-392">immigration 部門</span><span class="sxs-lookup"><span data-stu-id="2102f-392">department of immigration</span></span>
- <span data-ttu-id="2102f-393">住家住址</span><span class="sxs-lookup"><span data-stu-id="2102f-393">residential address</span></span>
- <span data-ttu-id="2102f-394">immigration 和公民部門</span><span class="sxs-lookup"><span data-stu-id="2102f-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="2102f-395">visa</span><span class="sxs-lookup"><span data-stu-id="2102f-395">visa</span></span>
- <span data-ttu-id="2102f-396">民族身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-396">national identity card</span></span>
- <span data-ttu-id="2102f-397">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-397">passport number</span></span>
- <span data-ttu-id="2102f-398">旅行檔</span><span class="sxs-lookup"><span data-stu-id="2102f-398">travel document</span></span>
- <span data-ttu-id="2102f-399">發證機構</span><span class="sxs-lookup"><span data-stu-id="2102f-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="2102f-400">澳大利亞稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="2102f-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-401">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-401">Format</span></span>

<span data-ttu-id="2102f-402">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-403">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-403">Pattern</span></span>

<span data-ttu-id="2102f-404">8-9 位數通常會以空格呈現, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2102f-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="2102f-405">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-405">Three digits</span></span> 
- <span data-ttu-id="2102f-406">選擇性的空間</span><span class="sxs-lookup"><span data-stu-id="2102f-406">An optional space</span></span> 
- <span data-ttu-id="2102f-407">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-407">Three digits</span></span> 
- <span data-ttu-id="2102f-408">選擇性的空間</span><span class="sxs-lookup"><span data-stu-id="2102f-408">An optional space</span></span> 
- <span data-ttu-id="2102f-409">2-3 位數, 最後一個數位是檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-410">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-410">Checksum</span></span>

<span data-ttu-id="2102f-411">是</span><span class="sxs-lookup"><span data-stu-id="2102f-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-412">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-412">Definition</span></span>

<span data-ttu-id="2102f-413">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-414">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-415">找不到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="2102f-416">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-416">The checksum passes.</span></span>

```
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="2102f-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="2102f-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="2102f-419">澳大利亞公司號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-419">australian business number</span></span>
- <span data-ttu-id="2102f-420">邊際稅率</span><span class="sxs-lookup"><span data-stu-id="2102f-420">marginal tax rate</span></span>
- <span data-ttu-id="2102f-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="2102f-421">medicare levy</span></span>
- <span data-ttu-id="2102f-422">產品群組編號</span><span class="sxs-lookup"><span data-stu-id="2102f-422">portfolio number</span></span>
- <span data-ttu-id="2102f-423">服務 veterans</span><span class="sxs-lookup"><span data-stu-id="2102f-423">service veterans</span></span>
- <span data-ttu-id="2102f-424">預繳稅金</span><span class="sxs-lookup"><span data-stu-id="2102f-424">withholding tax</span></span>
- <span data-ttu-id="2102f-425">個別稅收回報</span><span class="sxs-lookup"><span data-stu-id="2102f-425">individual tax return</span></span>
- <span data-ttu-id="2102f-426">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="2102f-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="2102f-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="2102f-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="2102f-428">00000000</span><span class="sxs-lookup"><span data-stu-id="2102f-428">00000000</span></span>
- <span data-ttu-id="2102f-429">11111111</span><span class="sxs-lookup"><span data-stu-id="2102f-429">11111111</span></span>
- <span data-ttu-id="2102f-430">22222222</span><span class="sxs-lookup"><span data-stu-id="2102f-430">22222222</span></span>
- <span data-ttu-id="2102f-431">33333333</span><span class="sxs-lookup"><span data-stu-id="2102f-431">33333333</span></span>
- <span data-ttu-id="2102f-432">44444444</span><span class="sxs-lookup"><span data-stu-id="2102f-432">44444444</span></span>
- <span data-ttu-id="2102f-433">55555555</span><span class="sxs-lookup"><span data-stu-id="2102f-433">55555555</span></span>
- <span data-ttu-id="2102f-434">66666666</span><span class="sxs-lookup"><span data-stu-id="2102f-434">66666666</span></span>
- <span data-ttu-id="2102f-435">77777777</span><span class="sxs-lookup"><span data-stu-id="2102f-435">77777777</span></span>
- <span data-ttu-id="2102f-436">88888888</span><span class="sxs-lookup"><span data-stu-id="2102f-436">88888888</span></span>
- <span data-ttu-id="2102f-437">99999999</span><span class="sxs-lookup"><span data-stu-id="2102f-437">99999999</span></span>
- <span data-ttu-id="2102f-438">000000000</span><span class="sxs-lookup"><span data-stu-id="2102f-438">000000000</span></span>
- <span data-ttu-id="2102f-439">111111111</span><span class="sxs-lookup"><span data-stu-id="2102f-439">111111111</span></span>
- <span data-ttu-id="2102f-440">222222222</span><span class="sxs-lookup"><span data-stu-id="2102f-440">222222222</span></span>
- <span data-ttu-id="2102f-441">333333333</span><span class="sxs-lookup"><span data-stu-id="2102f-441">333333333</span></span>
- <span data-ttu-id="2102f-442">444444444</span><span class="sxs-lookup"><span data-stu-id="2102f-442">444444444</span></span>
- <span data-ttu-id="2102f-443">555555555</span><span class="sxs-lookup"><span data-stu-id="2102f-443">555555555</span></span>
- <span data-ttu-id="2102f-444">666666666</span><span class="sxs-lookup"><span data-stu-id="2102f-444">666666666</span></span>
- <span data-ttu-id="2102f-445">777777777</span><span class="sxs-lookup"><span data-stu-id="2102f-445">777777777</span></span>
- <span data-ttu-id="2102f-446">888888888</span><span class="sxs-lookup"><span data-stu-id="2102f-446">888888888</span></span>
- <span data-ttu-id="2102f-447">999999999</span><span class="sxs-lookup"><span data-stu-id="2102f-447">999999999</span></span>
- <span data-ttu-id="2102f-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="2102f-448">0000000000</span></span>
- <span data-ttu-id="2102f-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="2102f-449">1111111111</span></span>
- <span data-ttu-id="2102f-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="2102f-450">2222222222</span></span>
- <span data-ttu-id="2102f-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="2102f-451">3333333333</span></span>
- <span data-ttu-id="2102f-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="2102f-452">4444444444</span></span>
- <span data-ttu-id="2102f-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="2102f-453">5555555555</span></span>
- <span data-ttu-id="2102f-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="2102f-454">6666666666</span></span>
- <span data-ttu-id="2102f-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="2102f-455">7777777777</span></span>
- <span data-ttu-id="2102f-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="2102f-456">8888888888</span></span>
- <span data-ttu-id="2102f-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="2102f-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="2102f-458">Azure DocumentDB 授權金鑰</span><span class="sxs-lookup"><span data-stu-id="2102f-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="2102f-459">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-459">Format</span></span>

<span data-ttu-id="2102f-460">字串 "DocumentDb", 後面接著下模式所列的字元和字串。</span><span class="sxs-lookup"><span data-stu-id="2102f-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-461">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-461">Pattern</span></span>

- <span data-ttu-id="2102f-462">字串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="2102f-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="2102f-463">介於3-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-464">大於符號 (>)、等號 (=)、引號 (") 或單引號 (')</span><span class="sxs-lookup"><span data-stu-id="2102f-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="2102f-465">任何86小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 的組合</span><span class="sxs-lookup"><span data-stu-id="2102f-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2102f-466">兩個等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-467">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-467">Checksum</span></span>

<span data-ttu-id="2102f-468">否</span><span class="sxs-lookup"><span data-stu-id="2102f-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-469">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-469">Definition</span></span>

<span data-ttu-id="2102f-470">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-471">正則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-472">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-473">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-475">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-476">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-476">contoso</span></span>
- <span data-ttu-id="2102f-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-477">fabrikam</span></span>
- <span data-ttu-id="2102f-478">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-478">northwind</span></span>
- <span data-ttu-id="2102f-479">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-479">sandbox</span></span>
- <span data-ttu-id="2102f-480">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-480">onebox</span></span>
- <span data-ttu-id="2102f-481">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-481">localhost</span></span>
- <span data-ttu-id="2102f-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-482">127.0.0.1</span></span>
- <span data-ttu-id="2102f-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-484">com</span><span class="sxs-lookup"><span data-stu-id="2102f-484">com</span></span>
- <span data-ttu-id="2102f-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-486">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="2102f-487">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="2102f-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2102f-488">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-488">Format</span></span>

<span data-ttu-id="2102f-489">字串 "Server"、"server" 或 "data source", 後面接著下模式所述的字元和字串, 包括字串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="2102f-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-490">com "或" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="2102f-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="2102f-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-492">net ", 以及字串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="2102f-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-493">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-493">Pattern</span></span>

- <span data-ttu-id="2102f-494">字串 "Server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="2102f-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="2102f-495">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-496">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-496">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-497">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-498">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-499">字串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="2102f-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="2102f-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="2102f-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-502">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-502">net"</span></span>
- <span data-ttu-id="2102f-503">介於1-300 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-504">字串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="2102f-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="2102f-505">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-506">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-506">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-507">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-508">一或多個字元, 不是分號 (;)、引號 (") 或單引號 (')</span><span class="sxs-lookup"><span data-stu-id="2102f-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="2102f-509">分號 (;)、引號 (") 或單引號 (')</span><span class="sxs-lookup"><span data-stu-id="2102f-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-510">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-510">Checksum</span></span>

<span data-ttu-id="2102f-511">否</span><span class="sxs-lookup"><span data-stu-id="2102f-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-512">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-512">Definition</span></span>

<span data-ttu-id="2102f-513">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-514">正則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-515">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-518">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-519">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-519">contoso</span></span>
- <span data-ttu-id="2102f-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-520">fabrikam</span></span>
- <span data-ttu-id="2102f-521">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-521">northwind</span></span>
- <span data-ttu-id="2102f-522">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-522">sandbox</span></span>
- <span data-ttu-id="2102f-523">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-523">onebox</span></span>
- <span data-ttu-id="2102f-524">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-524">localhost</span></span>
- <span data-ttu-id="2102f-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-525">127.0.0.1</span></span>
- <span data-ttu-id="2102f-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-527">com</span><span class="sxs-lookup"><span data-stu-id="2102f-527">com</span></span>
- <span data-ttu-id="2102f-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-529">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="2102f-530">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="2102f-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2102f-531">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-531">Format</span></span>

<span data-ttu-id="2102f-532">字串 "HostName", 後面接著下模式所述的字元和字串, 包括字串 "azure 裝置。</span><span class="sxs-lookup"><span data-stu-id="2102f-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="2102f-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-534">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-534">Pattern</span></span>

- <span data-ttu-id="2102f-535">字串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="2102f-535">The string "HostName"</span></span>
- <span data-ttu-id="2102f-536">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-537">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-537">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-538">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-539">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-540">字串 "azure 裝置。</span><span class="sxs-lookup"><span data-stu-id="2102f-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-541">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-541">net"</span></span>
- <span data-ttu-id="2102f-542">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-543">字串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="2102f-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="2102f-544">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-545">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-545">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-546">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-547">任何43小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 的組合</span><span class="sxs-lookup"><span data-stu-id="2102f-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2102f-548">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-549">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-549">Checksum</span></span>

<span data-ttu-id="2102f-550">否</span><span class="sxs-lookup"><span data-stu-id="2102f-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-551">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-551">Definition</span></span>

<span data-ttu-id="2102f-552">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-553">正則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-554">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-555">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-557">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-558">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-558">contoso</span></span>
- <span data-ttu-id="2102f-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-559">fabrikam</span></span>
- <span data-ttu-id="2102f-560">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-560">northwind</span></span>
- <span data-ttu-id="2102f-561">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-561">sandbox</span></span>
- <span data-ttu-id="2102f-562">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-562">onebox</span></span>
- <span data-ttu-id="2102f-563">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-563">localhost</span></span>
- <span data-ttu-id="2102f-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-564">127.0.0.1</span></span>
- <span data-ttu-id="2102f-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-566">com</span><span class="sxs-lookup"><span data-stu-id="2102f-566">com</span></span>
- <span data-ttu-id="2102f-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-568">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="2102f-569">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="2102f-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="2102f-570">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-570">Format</span></span>

<span data-ttu-id="2102f-571">字串 "userpwd =", 後面接著一個字母數位字串。</span><span class="sxs-lookup"><span data-stu-id="2102f-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-572">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-572">Pattern</span></span>

- <span data-ttu-id="2102f-573">字串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="2102f-573">The string "userpwd="</span></span>
- <span data-ttu-id="2102f-574">任何60小寫字母或數位的組合</span><span class="sxs-lookup"><span data-stu-id="2102f-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="2102f-575">引號 (")</span><span class="sxs-lookup"><span data-stu-id="2102f-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-576">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-576">Checksum</span></span>

<span data-ttu-id="2102f-577">否</span><span class="sxs-lookup"><span data-stu-id="2102f-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-578">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-578">Definition</span></span>

<span data-ttu-id="2102f-579">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-580">正則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-581">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="2102f-582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-584">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-585">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-585">contoso</span></span>
- <span data-ttu-id="2102f-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-586">fabrikam</span></span>
- <span data-ttu-id="2102f-587">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-587">northwind</span></span>
- <span data-ttu-id="2102f-588">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-588">sandbox</span></span>
- <span data-ttu-id="2102f-589">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-589">onebox</span></span>
- <span data-ttu-id="2102f-590">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-590">localhost</span></span>
- <span data-ttu-id="2102f-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-591">127.0.0.1</span></span>
- <span data-ttu-id="2102f-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-593">com</span><span class="sxs-lookup"><span data-stu-id="2102f-593">com</span></span>
- <span data-ttu-id="2102f-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-595">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="2102f-596">Azure Redis 快取連接字串</span><span class="sxs-lookup"><span data-stu-id="2102f-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2102f-597">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-597">Format</span></span>

<span data-ttu-id="2102f-598">字串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="2102f-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-599">net ", 後面接著是下模式所述的字元和字串, 包括字串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="2102f-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-600">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-600">Pattern</span></span>

- <span data-ttu-id="2102f-601">字串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="2102f-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-602">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-602">net"</span></span>
- <span data-ttu-id="2102f-603">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-604">字串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="2102f-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="2102f-605">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-606">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-606">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-607">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-608">43個字元的任何組合, 其為小寫或大寫的字母、數位、正斜線 (/) 或加號 (+)</span><span class="sxs-lookup"><span data-stu-id="2102f-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2102f-609">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-610">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-610">Checksum</span></span>

<span data-ttu-id="2102f-611">否</span><span class="sxs-lookup"><span data-stu-id="2102f-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-612">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-612">Definition</span></span>

<span data-ttu-id="2102f-613">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-614">正則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="2102f-615">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-618">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-619">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-619">contoso</span></span>
- <span data-ttu-id="2102f-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-620">fabrikam</span></span>
- <span data-ttu-id="2102f-621">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-621">northwind</span></span>
- <span data-ttu-id="2102f-622">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-622">sandbox</span></span>
- <span data-ttu-id="2102f-623">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-623">onebox</span></span>
- <span data-ttu-id="2102f-624">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-624">localhost</span></span>
- <span data-ttu-id="2102f-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-625">127.0.0.1</span></span>
- <span data-ttu-id="2102f-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-627">com</span><span class="sxs-lookup"><span data-stu-id="2102f-627">com</span></span>
- <span data-ttu-id="2102f-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-629">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="2102f-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="2102f-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="2102f-631">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-631">Format</span></span>

<span data-ttu-id="2102f-632">字串 "sig", 後面接著下模式所列的字元和字串。</span><span class="sxs-lookup"><span data-stu-id="2102f-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-633">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-633">Pattern</span></span>

- <span data-ttu-id="2102f-634">字串 "sig"</span><span class="sxs-lookup"><span data-stu-id="2102f-634">The string "sig"</span></span>
- <span data-ttu-id="2102f-635">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-636">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-636">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-637">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-638">介於43-53 個字元的任何組合, 其為小寫字母、數位或百分比符號 (%)</span><span class="sxs-lookup"><span data-stu-id="2102f-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="2102f-639">字串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="2102f-639">The string "%3d"</span></span>
- <span data-ttu-id="2102f-640">不是小寫或大寫字母、數位或百分比符號 (%) 的任何字元</span><span class="sxs-lookup"><span data-stu-id="2102f-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-641">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-641">Checksum</span></span>

<span data-ttu-id="2102f-642">否</span><span class="sxs-lookup"><span data-stu-id="2102f-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-643">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-643">Definition</span></span>

<span data-ttu-id="2102f-644">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-645">正則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="2102f-646">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="2102f-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2102f-647">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-647">Format</span></span>

<span data-ttu-id="2102f-648">字串 "EndPoint", 後面接著下模式所述的字元和字串, 包括字串 "</span><span class="sxs-lookup"><span data-stu-id="2102f-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="2102f-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-650">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-650">Pattern</span></span>

- <span data-ttu-id="2102f-651">字串 "端點"</span><span class="sxs-lookup"><span data-stu-id="2102f-651">The string "EndPoint"</span></span>
- <span data-ttu-id="2102f-652">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-653">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-653">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-654">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-655">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-656">字串 "</span><span class="sxs-lookup"><span data-stu-id="2102f-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-657">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-657">net"</span></span>
- <span data-ttu-id="2102f-658">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-659">字串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="2102f-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="2102f-660">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-661">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-661">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-662">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-663">43個字元的任何組合, 其為小寫或大寫的字母、數位、正斜線 (/) 或加號 (+)</span><span class="sxs-lookup"><span data-stu-id="2102f-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2102f-664">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-665">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-665">Checksum</span></span>

<span data-ttu-id="2102f-666">否</span><span class="sxs-lookup"><span data-stu-id="2102f-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-667">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-667">Definition</span></span>

<span data-ttu-id="2102f-668">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-669">正則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="2102f-670">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-671">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-673">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-674">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-674">contoso</span></span>
- <span data-ttu-id="2102f-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-675">fabrikam</span></span>
- <span data-ttu-id="2102f-676">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-676">northwind</span></span>
- <span data-ttu-id="2102f-677">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-677">sandbox</span></span>
- <span data-ttu-id="2102f-678">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-678">onebox</span></span>
- <span data-ttu-id="2102f-679">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-679">localhost</span></span>
- <span data-ttu-id="2102f-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-680">127.0.0.1</span></span>
- <span data-ttu-id="2102f-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-682">com</span><span class="sxs-lookup"><span data-stu-id="2102f-682">com</span></span>
- <span data-ttu-id="2102f-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-684">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="2102f-685">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="2102f-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="2102f-686">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-686">Format</span></span>

<span data-ttu-id="2102f-687">字串 "DefaultEndpointsProtocol", 後面接著下模式所述的字元和字串, 包括字串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="2102f-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-688">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-688">Pattern</span></span>

- <span data-ttu-id="2102f-689">字串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="2102f-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="2102f-690">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-691">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-691">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-692">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-693">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-694">字串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="2102f-694">The string "AccountKey"</span></span>
- <span data-ttu-id="2102f-695">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-696">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-696">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-697">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="2102f-698">86個字元的任何組合, 其為小寫或大寫的字母、數位、正斜線 (/) 或加號 (+)</span><span class="sxs-lookup"><span data-stu-id="2102f-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2102f-699">兩個等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-700">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-700">Checksum</span></span>

<span data-ttu-id="2102f-701">否</span><span class="sxs-lookup"><span data-stu-id="2102f-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-702">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-702">Definition</span></span>

<span data-ttu-id="2102f-703">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-704">正則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-705">正則運算式 CEP_AzureEmulatorStorageAccountFilter 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-706">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-707">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="2102f-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="2102f-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="2102f-709">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="2102f-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-712">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-713">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-713">contoso</span></span>
- <span data-ttu-id="2102f-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-714">fabrikam</span></span>
- <span data-ttu-id="2102f-715">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-715">northwind</span></span>
- <span data-ttu-id="2102f-716">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-716">sandbox</span></span>
- <span data-ttu-id="2102f-717">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-717">onebox</span></span>
- <span data-ttu-id="2102f-718">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-718">localhost</span></span>
- <span data-ttu-id="2102f-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-719">127.0.0.1</span></span>
- <span data-ttu-id="2102f-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-721">com</span><span class="sxs-lookup"><span data-stu-id="2102f-721">com</span></span>
- <span data-ttu-id="2102f-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-723">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="2102f-724">Azure 儲存體帳戶金鑰 (一般)</span><span class="sxs-lookup"><span data-stu-id="2102f-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-725">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-725">Format</span></span>

<span data-ttu-id="2102f-726">任何86小寫或大寫字母、數位、正斜杠 (/) 或加號 (+) 的組合, 並在下方的模式中列出的字元前後加上。</span><span class="sxs-lookup"><span data-stu-id="2102f-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-727">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-727">Pattern</span></span>

- <span data-ttu-id="2102f-728">大於符號 (>)、單引號 (')、等號 (=)、引號 (") 或數位記號 (#) 的0-1</span><span class="sxs-lookup"><span data-stu-id="2102f-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="2102f-729">86個字元的任何組合, 其為小寫或大寫的字母、數位、正斜杠 (/) 或加號 (+)</span><span class="sxs-lookup"><span data-stu-id="2102f-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2102f-730">兩個等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="2102f-731">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-731">Checksum</span></span>

<span data-ttu-id="2102f-732">否</span><span class="sxs-lookup"><span data-stu-id="2102f-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-733">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-733">Definition</span></span>

<span data-ttu-id="2102f-734">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-735">正則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="2102f-736">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="2102f-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-737">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-737">Format</span></span>

<span data-ttu-id="2102f-738">11位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="2102f-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-739">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-739">Pattern</span></span>

<span data-ttu-id="2102f-740">11位數加上分隔符號:</span><span class="sxs-lookup"><span data-stu-id="2102f-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="2102f-741">六位數和兩個句點, 格式為 YY。距.出生日期的 DD</span><span class="sxs-lookup"><span data-stu-id="2102f-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="2102f-742">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-742">A hyphen</span></span> 
- <span data-ttu-id="2102f-743">三個連續數位 (奇數代表男生, 即使是女生)</span><span class="sxs-lookup"><span data-stu-id="2102f-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="2102f-744">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-744">A period</span></span> 
- <span data-ttu-id="2102f-745">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-746">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-746">Checksum</span></span>

<span data-ttu-id="2102f-747">是</span><span class="sxs-lookup"><span data-stu-id="2102f-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-748">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-748">Definition</span></span>

<span data-ttu-id="2102f-749">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-750">函數 Func_belgium_national_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-751">找到 Keyword_belgium_national_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="2102f-752">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-753">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="2102f-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="2102f-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="2102f-755">身分識別</span><span class="sxs-lookup"><span data-stu-id="2102f-755">Identity</span></span>
- <span data-ttu-id="2102f-756">進程</span><span class="sxs-lookup"><span data-stu-id="2102f-756">Registration</span></span>
- <span data-ttu-id="2102f-757">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-757">Identification</span></span> 
- <span data-ttu-id="2102f-758">ID</span><span class="sxs-lookup"><span data-stu-id="2102f-758">ID</span></span> 
- <span data-ttu-id="2102f-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="2102f-759">Identiteitskaart</span></span>
- <span data-ttu-id="2102f-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="2102f-760">Registratie nummer</span></span> 
- <span data-ttu-id="2102f-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="2102f-761">Identificatie nummer</span></span> 
- <span data-ttu-id="2102f-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="2102f-762">Identiteit</span></span>
- <span data-ttu-id="2102f-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="2102f-763">Registratie</span></span>
- <span data-ttu-id="2102f-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="2102f-764">Identificatie</span></span> 
- <span data-ttu-id="2102f-765">D'identité</span><span class="sxs-lookup"><span data-stu-id="2102f-765">Carte d’identité</span></span> 
- <span data-ttu-id="2102f-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="2102f-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="2102f-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="2102f-767">numéro d'identification</span></span>
- <span data-ttu-id="2102f-768">identité</span><span class="sxs-lookup"><span data-stu-id="2102f-768">identité</span></span> 
- <span data-ttu-id="2102f-769">inscription</span><span class="sxs-lookup"><span data-stu-id="2102f-769">inscription</span></span> 
- <span data-ttu-id="2102f-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="2102f-770">Identifikation</span></span>
- <span data-ttu-id="2102f-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2102f-771">Identifizierung</span></span>
- <span data-ttu-id="2102f-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-772">Identifikationsnummer</span></span>
- <span data-ttu-id="2102f-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2102f-773">Personalausweis</span></span>
- <span data-ttu-id="2102f-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="2102f-774">Registrierung</span></span>
- <span data-ttu-id="2102f-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="2102f-776">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-777">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-777">Format</span></span>

<span data-ttu-id="2102f-778">11位數包含檢查碼, 可以格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-779">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-779">Pattern</span></span>

<span data-ttu-id="2102f-780">格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-780">Formatted:</span></span>
- <span data-ttu-id="2102f-781">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-781">Three digits</span></span> 
- <span data-ttu-id="2102f-782">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-782">A period</span></span> 
- <span data-ttu-id="2102f-783">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-783">Three digits</span></span> 
- <span data-ttu-id="2102f-784">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-784">A period</span></span> 
- <span data-ttu-id="2102f-785">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-785">Three digits</span></span> 
- <span data-ttu-id="2102f-786">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-786">A hyphen</span></span> 
- <span data-ttu-id="2102f-787">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-787">Two digits which are check digits</span></span>

<span data-ttu-id="2102f-788">非</span><span class="sxs-lookup"><span data-stu-id="2102f-788">Unformatted:</span></span>
- <span data-ttu-id="2102f-789">11位數的最後兩位數是檢查數位</span><span class="sxs-lookup"><span data-stu-id="2102f-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-790">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-790">Checksum</span></span>

<span data-ttu-id="2102f-791">是</span><span class="sxs-lookup"><span data-stu-id="2102f-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-792">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-792">Definition</span></span>

<span data-ttu-id="2102f-793">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-794">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-795">找到 Keyword_brazil_cpf 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="2102f-796">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-796">The checksum passes.</span></span>

<span data-ttu-id="2102f-797">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-798">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-799">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-800">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="2102f-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="2102f-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="2102f-802">CPF</span><span class="sxs-lookup"><span data-stu-id="2102f-802">CPF</span></span>
- <span data-ttu-id="2102f-803">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-803">Identification</span></span>
- <span data-ttu-id="2102f-804">進程</span><span class="sxs-lookup"><span data-stu-id="2102f-804">Registration</span></span>
- <span data-ttu-id="2102f-805">收益</span><span class="sxs-lookup"><span data-stu-id="2102f-805">Revenue</span></span>
- <span data-ttu-id="2102f-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="2102f-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="2102f-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="2102f-807">Imposto</span></span> 
- <span data-ttu-id="2102f-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="2102f-808">Identificação</span></span> 
- <span data-ttu-id="2102f-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="2102f-809">Inscrição</span></span> 
- <span data-ttu-id="2102f-810">Receita</span><span class="sxs-lookup"><span data-stu-id="2102f-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="2102f-811">巴西法人編號 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="2102f-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-812">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-812">Format</span></span>

<span data-ttu-id="2102f-813">14位數, 包含註冊號碼、分支號碼和支票數位, 加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="2102f-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-814">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-814">Pattern</span></span>
<span data-ttu-id="2102f-815">14位數, 加上分隔符號:</span><span class="sxs-lookup"><span data-stu-id="2102f-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="2102f-816">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-816">Two digits</span></span> 
- <span data-ttu-id="2102f-817">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-817">A period</span></span> 
- <span data-ttu-id="2102f-818">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-818">Three digits</span></span> 
- <span data-ttu-id="2102f-819">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-819">A period</span></span> 
- <span data-ttu-id="2102f-820">三位數 (前八位數是註冊號碼)</span><span class="sxs-lookup"><span data-stu-id="2102f-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="2102f-821">正斜線</span><span class="sxs-lookup"><span data-stu-id="2102f-821">A forward slash</span></span> 
- <span data-ttu-id="2102f-822">四位數的分支編號</span><span class="sxs-lookup"><span data-stu-id="2102f-822">Four-digit branch number</span></span> 
- <span data-ttu-id="2102f-823">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-823">A hyphen</span></span> 
- <span data-ttu-id="2102f-824">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-825">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-825">Checksum</span></span>

<span data-ttu-id="2102f-826">是</span><span class="sxs-lookup"><span data-stu-id="2102f-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-827">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-827">Definition</span></span>

<span data-ttu-id="2102f-828">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-829">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-830">找到 Keyword_brazil_cnpj 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="2102f-831">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-831">The checksum passes.</span></span>

<span data-ttu-id="2102f-832">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-833">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-834">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-835">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="2102f-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="2102f-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="2102f-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="2102f-837">CNPJ</span></span> 
- <span data-ttu-id="2102f-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="2102f-838">CNPJ/MF</span></span> 
- <span data-ttu-id="2102f-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="2102f-839">CNPJ-MF</span></span> 
- <span data-ttu-id="2102f-840">合法實體的國家登錄</span><span class="sxs-lookup"><span data-stu-id="2102f-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="2102f-841">Taxpayers 登錄</span><span class="sxs-lookup"><span data-stu-id="2102f-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="2102f-842">法律實體</span><span class="sxs-lookup"><span data-stu-id="2102f-842">Legal entity</span></span> 
- <span data-ttu-id="2102f-843">法律實體</span><span class="sxs-lookup"><span data-stu-id="2102f-843">Legal entities</span></span> 
- <span data-ttu-id="2102f-844">註冊狀態</span><span class="sxs-lookup"><span data-stu-id="2102f-844">Registration Status</span></span> 
- <span data-ttu-id="2102f-845">商務版</span><span class="sxs-lookup"><span data-stu-id="2102f-845">Business</span></span> 
- <span data-ttu-id="2102f-846">Company</span><span class="sxs-lookup"><span data-stu-id="2102f-846">Company</span></span>
- <span data-ttu-id="2102f-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="2102f-847">CNPJ</span></span> 
- <span data-ttu-id="2102f-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="2102f-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="2102f-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="2102f-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="2102f-850">CGC</span><span class="sxs-lookup"><span data-stu-id="2102f-850">CGC</span></span> 
- <span data-ttu-id="2102f-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="2102f-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="2102f-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="2102f-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="2102f-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="2102f-853">Situação cadastral</span></span> 
- <span data-ttu-id="2102f-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="2102f-854">Inscrição</span></span> 
- <span data-ttu-id="2102f-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="2102f-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="2102f-856">巴西民族身分識別卡 (RG)</span><span class="sxs-lookup"><span data-stu-id="2102f-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-857">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-857">Format</span></span>

<span data-ttu-id="2102f-858">Registro Geral (舊格式): 九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="2102f-859">Registro de Identidade (RIC) (新格式):11 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-860">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-860">Pattern</span></span>

<span data-ttu-id="2102f-861">Registro Geral (舊格式):</span><span class="sxs-lookup"><span data-stu-id="2102f-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="2102f-862">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-862">Two digits</span></span> 
- <span data-ttu-id="2102f-863">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-863">A period</span></span> 
- <span data-ttu-id="2102f-864">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-864">Three digits</span></span> 
- <span data-ttu-id="2102f-865">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-865">A period</span></span> 
- <span data-ttu-id="2102f-866">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-866">Three digits</span></span> 
- <span data-ttu-id="2102f-867">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-867">A hyphen</span></span> 
- <span data-ttu-id="2102f-868">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-868">One digit which is a check digit</span></span>

<span data-ttu-id="2102f-869">Registro de Identidade (RIC) (新格式):</span><span class="sxs-lookup"><span data-stu-id="2102f-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="2102f-870">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-870">10 digits</span></span> 
- <span data-ttu-id="2102f-871">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-871">A hyphen</span></span> 
- <span data-ttu-id="2102f-872">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-873">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-873">Checksum</span></span>

<span data-ttu-id="2102f-874">是</span><span class="sxs-lookup"><span data-stu-id="2102f-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-875">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-875">Definition</span></span>

<span data-ttu-id="2102f-876">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-877">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-878">找到 Keyword_brazil_rg 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="2102f-879">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-879">The checksum passes.</span></span>

<span data-ttu-id="2102f-880">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-881">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-882">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-883">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="2102f-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="2102f-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="2102f-885">Cédula de identidade identity Registro 民族 id número de rregistro Iidentidade de Registro geral RIC RG (此關鍵字區分大小寫) (此關鍵字區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="2102f-886">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-887">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-887">Format</span></span>

<span data-ttu-id="2102f-888">7或12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-889">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-889">Pattern</span></span>

<span data-ttu-id="2102f-890">加拿大銀行帳戶號碼為7或12位數。</span><span class="sxs-lookup"><span data-stu-id="2102f-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="2102f-891">加拿大銀行帳戶中轉號碼為:</span><span class="sxs-lookup"><span data-stu-id="2102f-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="2102f-892">五位數</span><span class="sxs-lookup"><span data-stu-id="2102f-892">Five digits</span></span> 
- <span data-ttu-id="2102f-893">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-893">A hyphen</span></span> 
- <span data-ttu-id="2102f-894">三位數或</span><span class="sxs-lookup"><span data-stu-id="2102f-894">Three digits OR</span></span>
- <span data-ttu-id="2102f-895">零 "0"</span><span class="sxs-lookup"><span data-stu-id="2102f-895">A zero "0"</span></span> 
- <span data-ttu-id="2102f-896">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-897">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-897">Checksum</span></span>

<span data-ttu-id="2102f-898">否</span><span class="sxs-lookup"><span data-stu-id="2102f-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-899">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-899">Definition</span></span>

<span data-ttu-id="2102f-900">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-901">正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-902">找到 Keyword_canada_bank_account_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="2102f-903">正則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="2102f-904">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-905">正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-906">找到 Keyword_canada_bank_account_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-907">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="2102f-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2102f-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="2102f-909">加拿大節省 bonds</span><span class="sxs-lookup"><span data-stu-id="2102f-909">canada savings bonds</span></span>
- <span data-ttu-id="2102f-910">加拿大收入機構</span><span class="sxs-lookup"><span data-stu-id="2102f-910">canada revenue agency</span></span>
- <span data-ttu-id="2102f-911">加拿大金融機構</span><span class="sxs-lookup"><span data-stu-id="2102f-911">canadian financial institution</span></span>
- <span data-ttu-id="2102f-912">直接存放表單</span><span class="sxs-lookup"><span data-stu-id="2102f-912">direct deposit form</span></span>
- <span data-ttu-id="2102f-913">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="2102f-913">canadian citizen</span></span>
- <span data-ttu-id="2102f-914">法律代表</span><span class="sxs-lookup"><span data-stu-id="2102f-914">legal representative</span></span>
- <span data-ttu-id="2102f-915">notary 公用</span><span class="sxs-lookup"><span data-stu-id="2102f-915">notary public</span></span>
- <span data-ttu-id="2102f-916">oaths 的英國專員辦公室</span><span class="sxs-lookup"><span data-stu-id="2102f-916">commissioner for oaths</span></span>
- <span data-ttu-id="2102f-917">兒童護理權益</span><span class="sxs-lookup"><span data-stu-id="2102f-917">child care benefit</span></span>
- <span data-ttu-id="2102f-918">通用子級護理</span><span class="sxs-lookup"><span data-stu-id="2102f-918">universal child care</span></span>
- <span data-ttu-id="2102f-919">加拿大子稅務權益</span><span class="sxs-lookup"><span data-stu-id="2102f-919">canada child tax benefit</span></span>
- <span data-ttu-id="2102f-920">所得稅權益</span><span class="sxs-lookup"><span data-stu-id="2102f-920">income tax benefit</span></span>
- <span data-ttu-id="2102f-921">調和加值稅</span><span class="sxs-lookup"><span data-stu-id="2102f-921">harmonized sales tax</span></span>
- <span data-ttu-id="2102f-922">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-922">social insurance number</span></span>
- <span data-ttu-id="2102f-923">所得稅退款</span><span class="sxs-lookup"><span data-stu-id="2102f-923">income tax refund</span></span>
- <span data-ttu-id="2102f-924">子稅務權益</span><span class="sxs-lookup"><span data-stu-id="2102f-924">child tax benefit</span></span>
- <span data-ttu-id="2102f-925">territorial 付款</span><span class="sxs-lookup"><span data-stu-id="2102f-925">territorial payments</span></span>
- <span data-ttu-id="2102f-926">機構號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-926">institution number</span></span>
- <span data-ttu-id="2102f-927">存放要求</span><span class="sxs-lookup"><span data-stu-id="2102f-927">deposit request</span></span>
- <span data-ttu-id="2102f-928">銀行資訊</span><span class="sxs-lookup"><span data-stu-id="2102f-928">banking information</span></span>
- <span data-ttu-id="2102f-929">直接存款</span><span class="sxs-lookup"><span data-stu-id="2102f-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="2102f-930">加拿大駕照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-931">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-931">Format</span></span>

<span data-ttu-id="2102f-932">依省</span><span class="sxs-lookup"><span data-stu-id="2102f-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-933">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-933">Pattern</span></span>

<span data-ttu-id="2102f-934">涵蓋 Alberta、不列顛哥倫比亞、Manitoba、新 Brunswick、紐芬蘭/Labrador、Nova Scotia、安大略、Prince Edward 孤島、魁北克和薩斯的各種模式</span><span class="sxs-lookup"><span data-stu-id="2102f-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-935">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-935">Checksum</span></span>

<span data-ttu-id="2102f-936">否</span><span class="sxs-lookup"><span data-stu-id="2102f-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-937">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-937">Definition</span></span>

<span data-ttu-id="2102f-938">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-939">函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-940">找到 Keyword_ [province_name] _drivers_license_name 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2102f-941">找到 Keyword_canada_drivers_license 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="2102f-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="2102f-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="2102f-944">省份縮寫, 例如 AB</span><span class="sxs-lookup"><span data-stu-id="2102f-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="2102f-945">省份名稱, 例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="2102f-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="2102f-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2102f-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="2102f-947">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-947">DL</span></span>
- <span data-ttu-id="2102f-948">DLS</span><span class="sxs-lookup"><span data-stu-id="2102f-948">DLS</span></span>
- <span data-ttu-id="2102f-949">採用</span><span class="sxs-lookup"><span data-stu-id="2102f-949">CDL</span></span>
- <span data-ttu-id="2102f-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="2102f-950">CDLS</span></span>
- <span data-ttu-id="2102f-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="2102f-951">DriverLic</span></span>
- <span data-ttu-id="2102f-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="2102f-952">DriverLics</span></span>
- <span data-ttu-id="2102f-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-953">DriverLicense</span></span>
- <span data-ttu-id="2102f-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-954">DriverLicenses</span></span>
- <span data-ttu-id="2102f-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="2102f-955">DriverLicence</span></span>
- <span data-ttu-id="2102f-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="2102f-956">DriverLicences</span></span>
- <span data-ttu-id="2102f-957">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-957">Driver Lic</span></span>
- <span data-ttu-id="2102f-958">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-958">Driver Lics</span></span>
- <span data-ttu-id="2102f-959">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-959">Driver License</span></span>
- <span data-ttu-id="2102f-960">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-960">Driver Licenses</span></span>
- <span data-ttu-id="2102f-961">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-961">Driver Licence</span></span>
- <span data-ttu-id="2102f-962">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-962">Driver Licences</span></span>
- <span data-ttu-id="2102f-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2102f-963">DriversLic</span></span>
- <span data-ttu-id="2102f-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="2102f-964">DriversLics</span></span>
- <span data-ttu-id="2102f-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="2102f-965">DriversLicence</span></span>
- <span data-ttu-id="2102f-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="2102f-966">DriversLicences</span></span>
- <span data-ttu-id="2102f-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-967">DriversLicense</span></span>
- <span data-ttu-id="2102f-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-968">DriversLicenses</span></span>
- <span data-ttu-id="2102f-969">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-969">Drivers Lic</span></span>
- <span data-ttu-id="2102f-970">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-970">Drivers Lics</span></span>
- <span data-ttu-id="2102f-971">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-971">Drivers License</span></span>
- <span data-ttu-id="2102f-972">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-972">Drivers Licenses</span></span>
- <span data-ttu-id="2102f-973">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-973">Drivers Licence</span></span>
- <span data-ttu-id="2102f-974">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-974">Drivers Licences</span></span>
- <span data-ttu-id="2102f-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-975">Driver'Lic</span></span>
- <span data-ttu-id="2102f-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-976">Driver'Lics</span></span>
- <span data-ttu-id="2102f-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="2102f-977">Driver'License</span></span>
- <span data-ttu-id="2102f-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="2102f-978">Driver'Licenses</span></span>
- <span data-ttu-id="2102f-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2102f-979">Driver'Licence</span></span>
- <span data-ttu-id="2102f-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2102f-980">Driver'Licences</span></span>
- <span data-ttu-id="2102f-981">驅動程式 ' .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-981">Driver' Lic</span></span>
- <span data-ttu-id="2102f-982">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-982">Driver' Lics</span></span>
- <span data-ttu-id="2102f-983">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-983">Driver' License</span></span>
- <span data-ttu-id="2102f-984">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-984">Driver' Licenses</span></span>
- <span data-ttu-id="2102f-985">驅動程式 ' 許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-985">Driver' Licence</span></span>
- <span data-ttu-id="2102f-986">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-986">Driver' Licences</span></span>
- <span data-ttu-id="2102f-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2102f-987">Driver'sLic</span></span>
- <span data-ttu-id="2102f-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2102f-988">Driver'sLics</span></span>
- <span data-ttu-id="2102f-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-989">Driver'sLicense</span></span>
- <span data-ttu-id="2102f-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-990">Driver'sLicenses</span></span>
- <span data-ttu-id="2102f-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="2102f-991">Driver'sLicence</span></span>
- <span data-ttu-id="2102f-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="2102f-992">Driver'sLicences</span></span>
- <span data-ttu-id="2102f-993">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-993">Driver's Lic</span></span>
- <span data-ttu-id="2102f-994">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-994">Driver's Lics</span></span>
- <span data-ttu-id="2102f-995">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-995">Driver's License</span></span>
- <span data-ttu-id="2102f-996">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-996">Driver's Licenses</span></span>
- <span data-ttu-id="2102f-997">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-997">Driver's Licence</span></span>
- <span data-ttu-id="2102f-998">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-998">Driver's Licences</span></span>
- <span data-ttu-id="2102f-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="2102f-999">Permis de Conduire</span></span>
- <span data-ttu-id="2102f-1000">id</span><span class="sxs-lookup"><span data-stu-id="2102f-1000">id</span></span>
- <span data-ttu-id="2102f-1001">識別</span><span class="sxs-lookup"><span data-stu-id="2102f-1001">ids</span></span>
- <span data-ttu-id="2102f-1002">idcard 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1002">idcard number</span></span>
- <span data-ttu-id="2102f-1003">idcard 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1003">idcard numbers</span></span>
- <span data-ttu-id="2102f-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="2102f-1004">idcard #</span></span>
- <span data-ttu-id="2102f-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="2102f-1005">idcard #s</span></span>
- <span data-ttu-id="2102f-1006">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1006">idcard card</span></span>
- <span data-ttu-id="2102f-1007">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1007">idcard cards</span></span>
- <span data-ttu-id="2102f-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1008">idcard</span></span>
- <span data-ttu-id="2102f-1009">識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1009">identification number</span></span>
- <span data-ttu-id="2102f-1010">識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1010">identification numbers</span></span>
- <span data-ttu-id="2102f-1011">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1011">identification #</span></span>
- <span data-ttu-id="2102f-1012">識別 #s</span><span class="sxs-lookup"><span data-stu-id="2102f-1012">identification #s</span></span>
- <span data-ttu-id="2102f-1013">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1013">identification card</span></span>
- <span data-ttu-id="2102f-1014">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1014">identification cards</span></span>
- <span data-ttu-id="2102f-1015">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1015">identification</span></span> 
- <span data-ttu-id="2102f-1016">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-1016">DL#</span></span>
- <span data-ttu-id="2102f-1017">DLS</span><span class="sxs-lookup"><span data-stu-id="2102f-1017">DLS#</span></span> 
- <span data-ttu-id="2102f-1018">採用</span><span class="sxs-lookup"><span data-stu-id="2102f-1018">CDL#</span></span> 
- <span data-ttu-id="2102f-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="2102f-1019">CDLS#</span></span> 
- <span data-ttu-id="2102f-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-1020">DriverLic#</span></span> 
- <span data-ttu-id="2102f-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-1021">DriverLics#</span></span> 
- <span data-ttu-id="2102f-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-1022">DriverLicense#</span></span> 
- <span data-ttu-id="2102f-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="2102f-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="2102f-1024">DriverLicence#</span></span> 
- <span data-ttu-id="2102f-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="2102f-1025">DriverLicences#</span></span> 
- <span data-ttu-id="2102f-1026">驅動程式 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-1026">Driver Lic#</span></span>
- <span data-ttu-id="2102f-1027">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-1027">Driver Lics#</span></span> 
- <span data-ttu-id="2102f-1028">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1028">Driver License#</span></span> 
- <span data-ttu-id="2102f-1029">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="2102f-1030">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1030">Driver License#</span></span> 
- <span data-ttu-id="2102f-1031">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1031">Driver Licences#</span></span> 
- <span data-ttu-id="2102f-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-1032">DriversLic#</span></span> 
- <span data-ttu-id="2102f-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-1033">DriversLics#</span></span> 
- <span data-ttu-id="2102f-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-1034">DriversLicense#</span></span> 
- <span data-ttu-id="2102f-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="2102f-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="2102f-1036">DriversLicence#</span></span> 
- <span data-ttu-id="2102f-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="2102f-1037">DriversLicences#</span></span> 
- <span data-ttu-id="2102f-1038">驅動程式 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="2102f-1039">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="2102f-1040">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1040">Drivers License#</span></span> 
- <span data-ttu-id="2102f-1041">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="2102f-1042">驅動程式許可證 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="2102f-1043">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="2102f-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="2102f-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="2102f-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="2102f-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="2102f-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="2102f-1046">Driver'License#</span></span> 
- <span data-ttu-id="2102f-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="2102f-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="2102f-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="2102f-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="2102f-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="2102f-1050">驅動程式 ' .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="2102f-1051">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="2102f-1052">驅動程式 ' License #</span><span class="sxs-lookup"><span data-stu-id="2102f-1052">Driver' License#</span></span> 
- <span data-ttu-id="2102f-1053">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="2102f-1054">驅動程式 ' 許可證 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="2102f-1055">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="2102f-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="2102f-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="2102f-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="2102f-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="2102f-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="2102f-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="2102f-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="2102f-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="2102f-1062">驅動程式的 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="2102f-1063">Driver 的 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="2102f-1064">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1064">Driver's License#</span></span> 
- <span data-ttu-id="2102f-1065">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="2102f-1066">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="2102f-1067">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="2102f-1068">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="2102f-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="2102f-1069">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1069">id#</span></span> 
- <span data-ttu-id="2102f-1070">識別</span><span class="sxs-lookup"><span data-stu-id="2102f-1070">ids#</span></span> 
- <span data-ttu-id="2102f-1071">idcard 卡片 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1071">idcard card#</span></span> 
- <span data-ttu-id="2102f-1072">idcard 卡片 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1072">idcard cards#</span></span> 
- <span data-ttu-id="2102f-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="2102f-1073">idcard#</span></span> 
- <span data-ttu-id="2102f-1074">身分識別卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1074">identification card#</span></span> 
- <span data-ttu-id="2102f-1075">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-1075">identification cards#</span></span> 
- <span data-ttu-id="2102f-1076">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="2102f-1077">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1078">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1078">Format</span></span>

<span data-ttu-id="2102f-1079">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1080">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1080">Pattern</span></span>

<span data-ttu-id="2102f-1081">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1082">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1082">Checksum</span></span>

<span data-ttu-id="2102f-1083">否</span><span class="sxs-lookup"><span data-stu-id="2102f-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1084">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1084">Definition</span></span>

<span data-ttu-id="2102f-1085">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1086">正則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1087">找到 Keyword_canada_health_service_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1088">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="2102f-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="2102f-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="2102f-1090">個人健康情況號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1090">personal health number</span></span>
- <span data-ttu-id="2102f-1091">患者資訊</span><span class="sxs-lookup"><span data-stu-id="2102f-1091">patient information</span></span>
- <span data-ttu-id="2102f-1092">健康情況服務</span><span class="sxs-lookup"><span data-stu-id="2102f-1092">health services</span></span>
- <span data-ttu-id="2102f-1093">speciality 服務</span><span class="sxs-lookup"><span data-stu-id="2102f-1093">speciality services</span></span>
- <span data-ttu-id="2102f-1094">汽車意外</span><span class="sxs-lookup"><span data-stu-id="2102f-1094">automobile accident</span></span>
- <span data-ttu-id="2102f-1095">病人醫院</span><span class="sxs-lookup"><span data-stu-id="2102f-1095">patient hospital</span></span>
- <span data-ttu-id="2102f-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="2102f-1096">psychiatrist</span></span>
- <span data-ttu-id="2102f-1097">工作者補助</span><span class="sxs-lookup"><span data-stu-id="2102f-1097">workers compensation</span></span>
- <span data-ttu-id="2102f-1098">程度</span><span class="sxs-lookup"><span data-stu-id="2102f-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="2102f-1099">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1100">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1100">Format</span></span>

<span data-ttu-id="2102f-1101">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1102">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1102">Pattern</span></span>

<span data-ttu-id="2102f-1103">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1104">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1104">Checksum</span></span>

<span data-ttu-id="2102f-1105">否</span><span class="sxs-lookup"><span data-stu-id="2102f-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1106">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1106">Definition</span></span>

<span data-ttu-id="2102f-1107">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1108">正則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1109">找到 Keyword_canada_passport_number 或 Keyword_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1110">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="2102f-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="2102f-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="2102f-1112">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="2102f-1112">canadian citizenship</span></span>
- <span data-ttu-id="2102f-1113">加拿大 passport</span><span class="sxs-lookup"><span data-stu-id="2102f-1113">canadian passport</span></span>
- <span data-ttu-id="2102f-1114">passport 應用程式</span><span class="sxs-lookup"><span data-stu-id="2102f-1114">passport application</span></span>
- <span data-ttu-id="2102f-1115">護照相片</span><span class="sxs-lookup"><span data-stu-id="2102f-1115">passport photos</span></span>
- <span data-ttu-id="2102f-1116">認證轉換程式</span><span class="sxs-lookup"><span data-stu-id="2102f-1116">certified translator</span></span>
- <span data-ttu-id="2102f-1117">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="2102f-1117">canadian citizens</span></span>
- <span data-ttu-id="2102f-1118">處理時間</span><span class="sxs-lookup"><span data-stu-id="2102f-1118">processing times</span></span>
- <span data-ttu-id="2102f-1119">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="2102f-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2102f-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-1120">Keyword_passport</span></span>

- <span data-ttu-id="2102f-1121">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1121">Passport Number</span></span>
- <span data-ttu-id="2102f-1122">護照否</span><span class="sxs-lookup"><span data-stu-id="2102f-1122">Passport No</span></span>
- <span data-ttu-id="2102f-1123">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-1123">Passport #</span></span>
- <span data-ttu-id="2102f-1124">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-1124">Passport#</span></span>
- <span data-ttu-id="2102f-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="2102f-1125">PassportID</span></span>
- <span data-ttu-id="2102f-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="2102f-1126">Passportno</span></span>
- <span data-ttu-id="2102f-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-1127">passportnumber</span></span>
- <span data-ttu-id="2102f-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="2102f-1128">パスポート</span></span>
- <span data-ttu-id="2102f-1129">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="2102f-1129">パスポート番号</span></span>
- <span data-ttu-id="2102f-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2102f-1130">パスポートのNum</span></span>
- <span data-ttu-id="2102f-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2102f-1131">パスポート＃</span></span>
- <span data-ttu-id="2102f-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2102f-1132">Numéro de passeport</span></span>
- <span data-ttu-id="2102f-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2102f-1133">Passeport n °</span></span>
- <span data-ttu-id="2102f-1134">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="2102f-1134">Passeport Non</span></span>
- <span data-ttu-id="2102f-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2102f-1135">Passeport #</span></span>
- <span data-ttu-id="2102f-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2102f-1136">Passeport#</span></span>
- <span data-ttu-id="2102f-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2102f-1137">PasseportNon</span></span>
- <span data-ttu-id="2102f-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2102f-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="2102f-1139">加拿大個人健康身分識別號碼 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="2102f-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1140">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1140">Format</span></span>

<span data-ttu-id="2102f-1141">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1142">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1142">Pattern</span></span>

<span data-ttu-id="2102f-1143">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1144">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1144">Checksum</span></span>

<span data-ttu-id="2102f-1145">否</span><span class="sxs-lookup"><span data-stu-id="2102f-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1146">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1146">Definition</span></span>

<span data-ttu-id="2102f-1147">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%: 正則運算式 Regex_canada_phin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-1148">找出至少兩個來自 Keyword_canada_phin 或 Keyword_canada_provinces 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="2102f-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="2102f-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="2102f-1151">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1151">social insurance number</span></span>
- <span data-ttu-id="2102f-1152">健康資訊法案</span><span class="sxs-lookup"><span data-stu-id="2102f-1152">health information act</span></span>
- <span data-ttu-id="2102f-1153">所得稅資訊</span><span class="sxs-lookup"><span data-stu-id="2102f-1153">income tax information</span></span>
- <span data-ttu-id="2102f-1154">manitoba 健康情況</span><span class="sxs-lookup"><span data-stu-id="2102f-1154">manitoba health</span></span>
- <span data-ttu-id="2102f-1155">健康情況註冊</span><span class="sxs-lookup"><span data-stu-id="2102f-1155">health registration</span></span>
- <span data-ttu-id="2102f-1156">處方購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1156">prescription purchases</span></span>
- <span data-ttu-id="2102f-1157">福利資格</span><span class="sxs-lookup"><span data-stu-id="2102f-1157">benefit eligibility</span></span>
- <span data-ttu-id="2102f-1158">個人健康情況</span><span class="sxs-lookup"><span data-stu-id="2102f-1158">personal health</span></span>
- <span data-ttu-id="2102f-1159">律師的權力</span><span class="sxs-lookup"><span data-stu-id="2102f-1159">power of attorney</span></span>
- <span data-ttu-id="2102f-1160">註冊號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1160">registration number</span></span>
- <span data-ttu-id="2102f-1161">個人健康情況號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1161">personal health number</span></span>
- <span data-ttu-id="2102f-1162">practitioner 參照</span><span class="sxs-lookup"><span data-stu-id="2102f-1162">practitioner referral</span></span>
- <span data-ttu-id="2102f-1163">wellness 專業版</span><span class="sxs-lookup"><span data-stu-id="2102f-1163">wellness professional</span></span>
- <span data-ttu-id="2102f-1164">患者參考</span><span class="sxs-lookup"><span data-stu-id="2102f-1164">patient referral</span></span>
- <span data-ttu-id="2102f-1165">健康情況和 wellness</span><span class="sxs-lookup"><span data-stu-id="2102f-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="2102f-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="2102f-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="2102f-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="2102f-1167">Nunavut</span></span>
- <span data-ttu-id="2102f-1168">加拿大</span><span class="sxs-lookup"><span data-stu-id="2102f-1168">Quebec</span></span>
- <span data-ttu-id="2102f-1169">西北領地</span><span class="sxs-lookup"><span data-stu-id="2102f-1169">Northwest Territories</span></span>
- <span data-ttu-id="2102f-1170">省</span><span class="sxs-lookup"><span data-stu-id="2102f-1170">Ontario</span></span>
- <span data-ttu-id="2102f-1171">英屬哥倫比亞</span><span class="sxs-lookup"><span data-stu-id="2102f-1171">British Columbia</span></span>
- <span data-ttu-id="2102f-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="2102f-1172">Alberta</span></span>
- <span data-ttu-id="2102f-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="2102f-1173">Saskatchewan</span></span>
- <span data-ttu-id="2102f-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="2102f-1174">Manitoba</span></span>
- <span data-ttu-id="2102f-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="2102f-1175">Yukon</span></span>
- <span data-ttu-id="2102f-1176">紐芬蘭和 Labrador</span><span class="sxs-lookup"><span data-stu-id="2102f-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="2102f-1177">新 Brunswick</span><span class="sxs-lookup"><span data-stu-id="2102f-1177">New Brunswick</span></span>
- <span data-ttu-id="2102f-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="2102f-1178">Nova Scotia</span></span>
- <span data-ttu-id="2102f-1179">Prince Edward 島</span><span class="sxs-lookup"><span data-stu-id="2102f-1179">Prince Edward Island</span></span>
- <span data-ttu-id="2102f-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="2102f-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="2102f-1181">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1182">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1182">Format</span></span>

<span data-ttu-id="2102f-1183">具有選擇性連字號或空格的九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1184">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1184">Pattern</span></span>

<span data-ttu-id="2102f-1185">格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-1185">Formatted:</span></span>
- <span data-ttu-id="2102f-1186">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1186">Three digits</span></span> 
- <span data-ttu-id="2102f-1187">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="2102f-1187">A hyphen or space</span></span> 
- <span data-ttu-id="2102f-1188">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1188">Three digits</span></span> 
- <span data-ttu-id="2102f-1189">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="2102f-1189">A hyphen or space</span></span> 
- <span data-ttu-id="2102f-1190">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1190">Three digits</span></span>

<span data-ttu-id="2102f-1191">未格式化: 九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1192">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1192">Checksum</span></span>

<span data-ttu-id="2102f-1193">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1194">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1194">Definition</span></span>

<span data-ttu-id="2102f-1195">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1196">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1197">下列任一組合的至少兩個:</span><span class="sxs-lookup"><span data-stu-id="2102f-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="2102f-1198">找到 Keyword_sin 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="2102f-1199">找到 Keyword_sin_collaborative 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="2102f-1200">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2102f-1201">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1201">The checksum passes.</span></span>

<span data-ttu-id="2102f-1202">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1203">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1204">找到 Keyword_sin 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="2102f-1205">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="2102f-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="2102f-1207">Keyword_sin</span></span>

- <span data-ttu-id="2102f-1208">正弦</span><span class="sxs-lookup"><span data-stu-id="2102f-1208">sin</span></span> 
- <span data-ttu-id="2102f-1209">社交保險</span><span class="sxs-lookup"><span data-stu-id="2102f-1209">social insurance</span></span> 
- <span data-ttu-id="2102f-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="2102f-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="2102f-1211">原罪</span><span class="sxs-lookup"><span data-stu-id="2102f-1211">sins</span></span> 
- <span data-ttu-id="2102f-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="2102f-1212">ssn</span></span> 
- <span data-ttu-id="2102f-1213">主旨 ssn</span><span class="sxs-lookup"><span data-stu-id="2102f-1213">ssns</span></span> 
- <span data-ttu-id="2102f-1214">社會保險</span><span class="sxs-lookup"><span data-stu-id="2102f-1214">social security</span></span> 
- <span data-ttu-id="2102f-1215">numero d'assurance 社交</span><span class="sxs-lookup"><span data-stu-id="2102f-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="2102f-1216">國際身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1216">national identification number</span></span> 
- <span data-ttu-id="2102f-1217">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1217">national id</span></span> 
- <span data-ttu-id="2102f-1218">正弦</span><span class="sxs-lookup"><span data-stu-id="2102f-1218">sin#</span></span> 
- <span data-ttu-id="2102f-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="2102f-1219">soc ins</span></span> 
- <span data-ttu-id="2102f-1220">社交</span><span class="sxs-lookup"><span data-stu-id="2102f-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="2102f-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="2102f-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="2102f-1222">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-1222">driver's license</span></span> 
- <span data-ttu-id="2102f-1223">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-1223">drivers license</span></span> 
- <span data-ttu-id="2102f-1224">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-1224">driver's licence</span></span> 
- <span data-ttu-id="2102f-1225">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-1225">drivers licence</span></span> 
- <span data-ttu-id="2102f-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="2102f-1226">DOB</span></span> 
- <span data-ttu-id="2102f-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-1227">Birthdate</span></span> 
- <span data-ttu-id="2102f-1228">生日</span><span class="sxs-lookup"><span data-stu-id="2102f-1228">Birthday</span></span> 
- <span data-ttu-id="2102f-1229">出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="2102f-1230">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1231">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1231">Format</span></span>

<span data-ttu-id="2102f-1232">7-8 位數加上分隔符號 a a check 數位或字母</span><span class="sxs-lookup"><span data-stu-id="2102f-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1233">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1233">Pattern</span></span>

<span data-ttu-id="2102f-1234">7-8 位數加上分隔符號:</span><span class="sxs-lookup"><span data-stu-id="2102f-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="2102f-1235">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1235">1-2 digits</span></span> 
- <span data-ttu-id="2102f-1236">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-1236">A period</span></span> 
- <span data-ttu-id="2102f-1237">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1237">Three digits</span></span> 
- <span data-ttu-id="2102f-1238">句點</span><span class="sxs-lookup"><span data-stu-id="2102f-1238">A period</span></span> 
- <span data-ttu-id="2102f-1239">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1239">Three digits</span></span> 
- <span data-ttu-id="2102f-1240">虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-1240">A dash</span></span> 
- <span data-ttu-id="2102f-1241">一種數位或字母 (不區分大小寫), 這是一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1242">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1242">Checksum</span></span>

<span data-ttu-id="2102f-1243">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1244">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1244">Definition</span></span>

<span data-ttu-id="2102f-1245">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1246">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1247">找到 Keyword_chile_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="2102f-1248">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1248">The checksum passes.</span></span>

<span data-ttu-id="2102f-1249">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1250">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1251">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="2102f-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="2102f-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="2102f-1254">國際身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1254">National Identification Number</span></span> 
- <span data-ttu-id="2102f-1255">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1255">Identity card</span></span> 
- <span data-ttu-id="2102f-1256">ID</span><span class="sxs-lookup"><span data-stu-id="2102f-1256">ID</span></span> 
- <span data-ttu-id="2102f-1257">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1257">Identification</span></span> 
- <span data-ttu-id="2102f-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="2102f-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="2102f-1259">完</span><span class="sxs-lookup"><span data-stu-id="2102f-1259">RUN</span></span> 
- <span data-ttu-id="2102f-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="2102f-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="2102f-1261">RUT</span><span class="sxs-lookup"><span data-stu-id="2102f-1261">RUT</span></span> 
- <span data-ttu-id="2102f-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="2102f-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="2102f-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="2102f-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="2102f-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="2102f-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="2102f-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="2102f-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="2102f-1266">中國居民身分識別卡 (中國) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1267">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1267">Format</span></span>

<span data-ttu-id="2102f-1268">18位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1269">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1269">Pattern</span></span>

<span data-ttu-id="2102f-1270">18位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-1270">18 digits:</span></span>
- <span data-ttu-id="2102f-1271">六位數的位址代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="2102f-1272">在 YYYYMMDD 中, 以出生日期表示的八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2102f-1273">三位數的訂單碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="2102f-1274">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1275">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1275">Checksum</span></span>

<span data-ttu-id="2102f-1276">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1277">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1277">Definition</span></span>

<span data-ttu-id="2102f-1278">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1279">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1280">找到 Keyword_china_resident_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="2102f-1281">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1281">The checksum passes.</span></span>

<span data-ttu-id="2102f-1282">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1283">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1284">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1285">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="2102f-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="2102f-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="2102f-1287">駐留身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="2102f-1288">中華人民共和國</span><span class="sxs-lookup"><span data-stu-id="2102f-1288">PRC</span></span> 
- <span data-ttu-id="2102f-1289">民族身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1289">National Identification Card</span></span> 
- <span data-ttu-id="2102f-1290">身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-1290">身份证</span></span> 
- <span data-ttu-id="2102f-1291">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-1291">居民 身份证</span></span> 
- <span data-ttu-id="2102f-1292">居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-1292">居民身份证</span></span> 
- <span data-ttu-id="2102f-1293">鑒定</span><span class="sxs-lookup"><span data-stu-id="2102f-1293">鉴定</span></span> 
- <span data-ttu-id="2102f-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-1294">身分證</span></span> 
- <span data-ttu-id="2102f-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-1295">居民 身份證</span></span>
- <span data-ttu-id="2102f-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="2102f-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="2102f-1297">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1298">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1298">Format</span></span>

<span data-ttu-id="2102f-1299">可以格式化或未格式化 (dddddddddddddddd) 且必須通過 Luhn 測試的16位數。</span><span class="sxs-lookup"><span data-stu-id="2102f-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1300">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1300">Pattern</span></span>

<span data-ttu-id="2102f-1301">一種非常複雜且健全的模式, 可偵測全球所有主要品牌的卡, 包括簽證、MasterCard、探索卡、JCB、北美版、禮品卡及 diner 卡。</span><span class="sxs-lookup"><span data-stu-id="2102f-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1302">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1302">Checksum</span></span>

<span data-ttu-id="2102f-1303">是, Luhn 校驗和</span><span class="sxs-lookup"><span data-stu-id="2102f-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1304">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1304">Definition</span></span>

<span data-ttu-id="2102f-1305">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1306">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1307">下列其中一項為真:</span><span class="sxs-lookup"><span data-stu-id="2102f-1307">One of the following is true:</span></span>
    - <span data-ttu-id="2102f-1308">找到 Keyword_cc_verification 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="2102f-1309">找到 Keyword_cc_name 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="2102f-1310">函數 Func_expiration_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2102f-1311">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1311">The checksum passes.</span></span>

<span data-ttu-id="2102f-1312">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1313">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1314">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="2102f-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="2102f-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="2102f-1317">卡驗證</span><span class="sxs-lookup"><span data-stu-id="2102f-1317">card verification</span></span>
- <span data-ttu-id="2102f-1318">卡片識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1318">card identification number</span></span>
- <span data-ttu-id="2102f-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="2102f-1319">cvn</span></span>
- <span data-ttu-id="2102f-1320">cid</span><span class="sxs-lookup"><span data-stu-id="2102f-1320">cid</span></span>
- <span data-ttu-id="2102f-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="2102f-1321">cvc2</span></span>
- <span data-ttu-id="2102f-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="2102f-1322">cvv2</span></span>
- <span data-ttu-id="2102f-1323">pin 區塊</span><span class="sxs-lookup"><span data-stu-id="2102f-1323">pin block</span></span>
- <span data-ttu-id="2102f-1324">安全性程式碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1324">security code</span></span>
- <span data-ttu-id="2102f-1325">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1325">security number</span></span>
- <span data-ttu-id="2102f-1326">安全性否</span><span class="sxs-lookup"><span data-stu-id="2102f-1326">security no</span></span>
- <span data-ttu-id="2102f-1327">發行號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1327">issue number</span></span>
- <span data-ttu-id="2102f-1328">問題否</span><span class="sxs-lookup"><span data-stu-id="2102f-1328">issue no</span></span>
- <span data-ttu-id="2102f-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="2102f-1329">cryptogramme</span></span>
- <span data-ttu-id="2102f-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="2102f-1330">numéro de sécurité</span></span>
- <span data-ttu-id="2102f-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="2102f-1331">numero de securite</span></span>
- <span data-ttu-id="2102f-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="2102f-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="2102f-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2102f-1334">prüfziffer</span></span>
- <span data-ttu-id="2102f-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="2102f-1335">prufziffer</span></span>
- <span data-ttu-id="2102f-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="2102f-1336">sicherheits Kode</span></span>
- <span data-ttu-id="2102f-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="2102f-1337">sicherheitscode</span></span>
- <span data-ttu-id="2102f-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="2102f-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1339">verfalldatum</span></span>
- <span data-ttu-id="2102f-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="2102f-1340">codice di verifica</span></span>
- <span data-ttu-id="2102f-1341">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1341">cod.</span></span> <span data-ttu-id="2102f-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1342">sicurezza</span></span>
- <span data-ttu-id="2102f-1343">貨到 sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1343">cod sicurezza</span></span>
- <span data-ttu-id="2102f-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2102f-1344">n autorizzazione</span></span>
- <span data-ttu-id="2102f-1345">código</span><span class="sxs-lookup"><span data-stu-id="2102f-1345">código</span></span>
- <span data-ttu-id="2102f-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="2102f-1346">codigo</span></span>
- <span data-ttu-id="2102f-1347">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1347">cod.</span></span> <span data-ttu-id="2102f-1348">seg</span><span class="sxs-lookup"><span data-stu-id="2102f-1348">seg</span></span>
- <span data-ttu-id="2102f-1349">貨到 seg</span><span class="sxs-lookup"><span data-stu-id="2102f-1349">cod seg</span></span>
- <span data-ttu-id="2102f-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1350">código de segurança</span></span>
- <span data-ttu-id="2102f-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1351">codigo de seguranca</span></span>
- <span data-ttu-id="2102f-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1352">codigo de segurança</span></span>
- <span data-ttu-id="2102f-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1353">código de seguranca</span></span>
- <span data-ttu-id="2102f-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="2102f-1354">cód.</span></span> <span data-ttu-id="2102f-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1355">segurança</span></span>
- <span data-ttu-id="2102f-1356">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1356">cod.</span></span> <span data-ttu-id="2102f-1357">seguranca 貨貨。</span><span class="sxs-lookup"><span data-stu-id="2102f-1357">seguranca cod.</span></span> <span data-ttu-id="2102f-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1358">segurança</span></span>
- <span data-ttu-id="2102f-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="2102f-1359">cód.</span></span> <span data-ttu-id="2102f-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1360">seguranca</span></span>
- <span data-ttu-id="2102f-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1361">cód segurança</span></span>
- <span data-ttu-id="2102f-1362">貨到 seguranca 貨到 segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="2102f-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1363">cód seguranca</span></span>
- <span data-ttu-id="2102f-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="2102f-1364">número de verificação</span></span>
- <span data-ttu-id="2102f-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="2102f-1365">numero de verificacao</span></span>
- <span data-ttu-id="2102f-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="2102f-1366">ablauf</span></span>
- <span data-ttu-id="2102f-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="2102f-1367">gültig bis</span></span>
- <span data-ttu-id="2102f-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="2102f-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="2102f-1369">gultig bis</span></span>
- <span data-ttu-id="2102f-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="2102f-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="2102f-1371">scadenza</span></span>
- <span data-ttu-id="2102f-1372">資料 scad</span><span class="sxs-lookup"><span data-stu-id="2102f-1372">data scad</span></span>
- <span data-ttu-id="2102f-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="2102f-1373">fecha de expiracion</span></span>
- <span data-ttu-id="2102f-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="2102f-1374">fecha de venc</span></span>
- <span data-ttu-id="2102f-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="2102f-1375">vencimiento</span></span>
- <span data-ttu-id="2102f-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="2102f-1376">válido hasta</span></span>
- <span data-ttu-id="2102f-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="2102f-1377">valido hasta</span></span>
- <span data-ttu-id="2102f-1378">vto</span><span class="sxs-lookup"><span data-stu-id="2102f-1378">vto</span></span>
- <span data-ttu-id="2102f-1379">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="2102f-1379">data de expiração</span></span>
- <span data-ttu-id="2102f-1380">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="2102f-1380">data de expiracao</span></span>
- <span data-ttu-id="2102f-1381">資料 em mail.que expira</span><span class="sxs-lookup"><span data-stu-id="2102f-1381">data em que expira</span></span>
- <span data-ttu-id="2102f-1382">validade</span><span class="sxs-lookup"><span data-stu-id="2102f-1382">validade</span></span>
- <span data-ttu-id="2102f-1383">valor</span><span class="sxs-lookup"><span data-stu-id="2102f-1383">valor</span></span>
- <span data-ttu-id="2102f-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="2102f-1384">vencimento</span></span>
- <span data-ttu-id="2102f-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="2102f-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="2102f-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="2102f-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="2102f-1387">amex</span><span class="sxs-lookup"><span data-stu-id="2102f-1387">amex</span></span>
- <span data-ttu-id="2102f-1388">美洲 express</span><span class="sxs-lookup"><span data-stu-id="2102f-1388">american express</span></span>
- <span data-ttu-id="2102f-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="2102f-1389">americanexpress</span></span>
- <span data-ttu-id="2102f-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="2102f-1390">Visa</span></span>
- <span data-ttu-id="2102f-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="2102f-1391">mastercard</span></span>
- <span data-ttu-id="2102f-1392">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1392">master card</span></span>
- <span data-ttu-id="2102f-1393">mc</span><span class="sxs-lookup"><span data-stu-id="2102f-1393">mc</span></span> 
- <span data-ttu-id="2102f-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="2102f-1394">mastercards</span></span>
- <span data-ttu-id="2102f-1395">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1395">master cards</span></span>
- <span data-ttu-id="2102f-1396">diner 俱樂部</span><span class="sxs-lookup"><span data-stu-id="2102f-1396">diner's Club</span></span>
- <span data-ttu-id="2102f-1397">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="2102f-1397">diners club</span></span>
- <span data-ttu-id="2102f-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="2102f-1398">dinersclub</span></span>
- <span data-ttu-id="2102f-1399">探索卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1399">discover card</span></span>
- <span data-ttu-id="2102f-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="2102f-1400">discovercard</span></span>
- <span data-ttu-id="2102f-1401">探索卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1401">discover cards</span></span>
- <span data-ttu-id="2102f-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="2102f-1402">JCB</span></span>
- <span data-ttu-id="2102f-1403">日式卡局</span><span class="sxs-lookup"><span data-stu-id="2102f-1403">japanese card bureau</span></span>
- <span data-ttu-id="2102f-1404">blanche</span><span class="sxs-lookup"><span data-stu-id="2102f-1404">carte blanche</span></span>
- <span data-ttu-id="2102f-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="2102f-1405">carteblanche</span></span>
- <span data-ttu-id="2102f-1406">信用卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1406">credit card</span></span>
- <span data-ttu-id="2102f-1407">'</span><span class="sxs-lookup"><span data-stu-id="2102f-1407">cc#</span></span>
- <span data-ttu-id="2102f-1408">抄送 #:</span><span class="sxs-lookup"><span data-stu-id="2102f-1408">cc#:</span></span>
- <span data-ttu-id="2102f-1409">到期日</span><span class="sxs-lookup"><span data-stu-id="2102f-1409">expiration date</span></span>
- <span data-ttu-id="2102f-1410">到期日</span><span class="sxs-lookup"><span data-stu-id="2102f-1410">exp date</span></span>
- <span data-ttu-id="2102f-1411">到期日</span><span class="sxs-lookup"><span data-stu-id="2102f-1411">expiry date</span></span>
- <span data-ttu-id="2102f-1412">日期 d'expiration</span><span class="sxs-lookup"><span data-stu-id="2102f-1412">date d’expiration</span></span>
- <span data-ttu-id="2102f-1413">日期 d'exp</span><span class="sxs-lookup"><span data-stu-id="2102f-1413">date d'exp</span></span>
- <span data-ttu-id="2102f-1414">到期日</span><span class="sxs-lookup"><span data-stu-id="2102f-1414">date expiration</span></span>
- <span data-ttu-id="2102f-1415">銀行卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1415">bank card</span></span>
- <span data-ttu-id="2102f-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1416">bankcard</span></span>
- <span data-ttu-id="2102f-1417">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1417">card number</span></span>
- <span data-ttu-id="2102f-1418">卡號</span><span class="sxs-lookup"><span data-stu-id="2102f-1418">card num</span></span>
- <span data-ttu-id="2102f-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-1419">cardnumber</span></span>
- <span data-ttu-id="2102f-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="2102f-1420">cardnumbers</span></span>
- <span data-ttu-id="2102f-1421">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1421">card numbers</span></span>
- <span data-ttu-id="2102f-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1422">creditcard</span></span>
- <span data-ttu-id="2102f-1423">信用卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1423">credit cards</span></span>
- <span data-ttu-id="2102f-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1424">creditcards</span></span>
- <span data-ttu-id="2102f-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="2102f-1425">ccn</span></span>
- <span data-ttu-id="2102f-1426">持卡人</span><span class="sxs-lookup"><span data-stu-id="2102f-1426">card holder</span></span>
- <span data-ttu-id="2102f-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="2102f-1427">cardholder</span></span>
- <span data-ttu-id="2102f-1428">持卡人</span><span class="sxs-lookup"><span data-stu-id="2102f-1428">card holders</span></span>
- <span data-ttu-id="2102f-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="2102f-1429">cardholders</span></span>
- <span data-ttu-id="2102f-1430">檢查卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1430">check card</span></span>
- <span data-ttu-id="2102f-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1431">checkcard</span></span>
- <span data-ttu-id="2102f-1432">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1432">check cards</span></span>
- <span data-ttu-id="2102f-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1433">checkcards</span></span>
- <span data-ttu-id="2102f-1434">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1434">debit card</span></span>
- <span data-ttu-id="2102f-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1435">debitcard</span></span>
- <span data-ttu-id="2102f-1436">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1436">debit cards</span></span>
- <span data-ttu-id="2102f-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1437">debitcards</span></span>
- <span data-ttu-id="2102f-1438">atm 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1438">atm card</span></span>
- <span data-ttu-id="2102f-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1439">atmcard</span></span>
- <span data-ttu-id="2102f-1440">atm 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1440">atm cards</span></span>
- <span data-ttu-id="2102f-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1441">atmcards</span></span>
- <span data-ttu-id="2102f-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="2102f-1442">enroute</span></span>
- <span data-ttu-id="2102f-1443">en 路由</span><span class="sxs-lookup"><span data-stu-id="2102f-1443">en route</span></span>
- <span data-ttu-id="2102f-1444">卡片類型</span><span class="sxs-lookup"><span data-stu-id="2102f-1444">card type</span></span>
- <span data-ttu-id="2102f-1445">bancaire</span><span class="sxs-lookup"><span data-stu-id="2102f-1445">carte bancaire</span></span>
- <span data-ttu-id="2102f-1446">crédit</span><span class="sxs-lookup"><span data-stu-id="2102f-1446">carte de crédit</span></span>
- <span data-ttu-id="2102f-1447">支付額度</span><span class="sxs-lookup"><span data-stu-id="2102f-1447">carte de credit</span></span>
- <span data-ttu-id="2102f-1448">numéro 的重複購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1448">numéro de carte</span></span>
- <span data-ttu-id="2102f-1449">numero 的重複購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1449">numero de carte</span></span>
- <span data-ttu-id="2102f-1450">n º de 照購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1450">nº de la carte</span></span>
- <span data-ttu-id="2102f-1451">n º重複購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1451">nº de carte</span></span>
- <span data-ttu-id="2102f-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="2102f-1452">kreditkarte</span></span>
- <span data-ttu-id="2102f-1453">karte</span><span class="sxs-lookup"><span data-stu-id="2102f-1453">karte</span></span>
- <span data-ttu-id="2102f-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="2102f-1454">karteninhaber</span></span>
- <span data-ttu-id="2102f-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="2102f-1455">karteninhabers</span></span>
- <span data-ttu-id="2102f-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="2102f-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="2102f-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="2102f-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="2102f-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="2102f-1458">kreditkartentyp</span></span>
- <span data-ttu-id="2102f-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="2102f-1459">eigentümername</span></span>
- <span data-ttu-id="2102f-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="2102f-1460">kartennr</span></span> 
- <span data-ttu-id="2102f-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1461">kartennummer</span></span>
- <span data-ttu-id="2102f-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1462">kreditkartennummer</span></span>
- <span data-ttu-id="2102f-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="2102f-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1464">carta di credito</span></span>
- <span data-ttu-id="2102f-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1465">carta credito</span></span>
- <span data-ttu-id="2102f-1466">carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1466">carta</span></span>
- <span data-ttu-id="2102f-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1467">n carta</span></span>
- <span data-ttu-id="2102f-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="2102f-1468">nr.</span></span> <span data-ttu-id="2102f-1469">carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1469">carta</span></span>
- <span data-ttu-id="2102f-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1470">nr carta</span></span>
- <span data-ttu-id="2102f-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1471">numero carta</span></span>
- <span data-ttu-id="2102f-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1472">numero della carta</span></span>
- <span data-ttu-id="2102f-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1473">numero di carta</span></span>
- <span data-ttu-id="2102f-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1474">tarjeta credito</span></span>
- <span data-ttu-id="2102f-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1475">tarjeta de credito</span></span>
- <span data-ttu-id="2102f-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="2102f-1476">tarjeta crédito</span></span>
- <span data-ttu-id="2102f-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="2102f-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="2102f-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="2102f-1478">tarjeta de atm</span></span>
- <span data-ttu-id="2102f-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="2102f-1479">tarjeta atm</span></span>
- <span data-ttu-id="2102f-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1480">tarjeta debito</span></span>
- <span data-ttu-id="2102f-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1481">tarjeta de debito</span></span>
- <span data-ttu-id="2102f-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="2102f-1482">tarjeta débito</span></span>
- <span data-ttu-id="2102f-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="2102f-1483">tarjeta de débito</span></span>
- <span data-ttu-id="2102f-1484">n º de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1484">nº de tarjeta</span></span>
- <span data-ttu-id="2102f-1485">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1485">no.</span></span> <span data-ttu-id="2102f-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1486">de tarjeta</span></span>
- <span data-ttu-id="2102f-1487">無任何 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1487">no de tarjeta</span></span>
- <span data-ttu-id="2102f-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1488">numero de tarjeta</span></span>
- <span data-ttu-id="2102f-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1489">número de tarjeta</span></span>
- <span data-ttu-id="2102f-1490">tarjeta 否</span><span class="sxs-lookup"><span data-stu-id="2102f-1490">tarjeta no</span></span>
- <span data-ttu-id="2102f-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="2102f-1491">tarjetahabiente</span></span>
- <span data-ttu-id="2102f-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="2102f-1492">cartão de crédito</span></span>
- <span data-ttu-id="2102f-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1493">cartão de credito</span></span>
- <span data-ttu-id="2102f-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="2102f-1494">cartao de crédito</span></span>
- <span data-ttu-id="2102f-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1495">cartao de credito</span></span>
- <span data-ttu-id="2102f-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="2102f-1496">cartão de débito</span></span>
- <span data-ttu-id="2102f-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="2102f-1497">cartao de débito</span></span>
- <span data-ttu-id="2102f-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1498">cartão de debito</span></span>
- <span data-ttu-id="2102f-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1499">cartao de debito</span></span>
- <span data-ttu-id="2102f-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="2102f-1500">débito automático</span></span>
- <span data-ttu-id="2102f-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="2102f-1501">debito automatico</span></span>
- <span data-ttu-id="2102f-1502">número 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1502">número do cartão</span></span>
- <span data-ttu-id="2102f-1503">numero 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1503">numero do cartão</span></span> 
- <span data-ttu-id="2102f-1504">número 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1504">número do cartao</span></span>
- <span data-ttu-id="2102f-1505">numero 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1505">numero do cartao</span></span>
- <span data-ttu-id="2102f-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1506">número de cartão</span></span>
- <span data-ttu-id="2102f-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1507">numero de cartão</span></span>
- <span data-ttu-id="2102f-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1508">número de cartao</span></span>
- <span data-ttu-id="2102f-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1509">numero de cartao</span></span>
- <span data-ttu-id="2102f-1510">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1510">nº do cartão</span></span>
- <span data-ttu-id="2102f-1511">n º do cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1511">nº do cartao</span></span>
- <span data-ttu-id="2102f-1512">n º</span><span class="sxs-lookup"><span data-stu-id="2102f-1512">nº.</span></span> <span data-ttu-id="2102f-1513">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1513">do cartão</span></span>
- <span data-ttu-id="2102f-1514">不 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1514">no do cartão</span></span>
- <span data-ttu-id="2102f-1515">不 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1515">no do cartao</span></span>
- <span data-ttu-id="2102f-1516">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1516">no.</span></span> <span data-ttu-id="2102f-1517">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1517">do cartão</span></span>
- <span data-ttu-id="2102f-1518">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1518">no.</span></span> <span data-ttu-id="2102f-1519">執行 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="2102f-1520">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1521">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1521">Format</span></span>

<span data-ttu-id="2102f-1522">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1523">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1523">Pattern</span></span>

<span data-ttu-id="2102f-1524">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1525">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1525">Checksum</span></span>

<span data-ttu-id="2102f-1526">否</span><span class="sxs-lookup"><span data-stu-id="2102f-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1527">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1527">Definition</span></span>

<span data-ttu-id="2102f-1528">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1529">函數 Func_croatia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1530">找到 Keyword_croatia_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-1531">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="2102f-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="2102f-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="2102f-1533">克羅地亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1533">Croatian identity card</span></span>
- <span data-ttu-id="2102f-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="2102f-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="2102f-1535">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1536">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1536">Format</span></span>

<span data-ttu-id="2102f-1537">11位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1538">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1538">Pattern</span></span>

<span data-ttu-id="2102f-1539">11位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-1539">11 digits:</span></span>
- <span data-ttu-id="2102f-1540">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1540">10 digits</span></span> 
- <span data-ttu-id="2102f-1541">最後一個數位是用來進行國際資料交換的檢查碼, 則字母 HR 會加上11位數之前。</span><span class="sxs-lookup"><span data-stu-id="2102f-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1542">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1542">Checksum</span></span>

<span data-ttu-id="2102f-1543">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1544">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1544">Definition</span></span>

<span data-ttu-id="2102f-1545">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1546">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1547">找到 Keyword_croatia_oib_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="2102f-1548">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1548">The checksum passes.</span></span>

<span data-ttu-id="2102f-1549">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1550">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1551">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1552">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="2102f-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="2102f-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="2102f-1554">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1554">Personal Identification Number</span></span>
- <span data-ttu-id="2102f-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="2102f-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="2102f-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="2102f-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="2102f-1557">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1558">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1558">Format</span></span>

<span data-ttu-id="2102f-1559">具有選用正斜線 (舊格式) 的九位數, 具有選用正斜線的10位數 (新格式)</span><span class="sxs-lookup"><span data-stu-id="2102f-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1560">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1560">Pattern</span></span>

<span data-ttu-id="2102f-1561">九位數 (舊格式):</span><span class="sxs-lookup"><span data-stu-id="2102f-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="2102f-1562">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1562">Nine digits</span></span>

<span data-ttu-id="2102f-1563">或</span><span class="sxs-lookup"><span data-stu-id="2102f-1563">OR</span></span>

- <span data-ttu-id="2102f-1564">六位數代表出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="2102f-1565">正斜線</span><span class="sxs-lookup"><span data-stu-id="2102f-1565">A forward slash</span></span>
- <span data-ttu-id="2102f-1566">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1566">Three digits</span></span>

<span data-ttu-id="2102f-1567">10位數 (新格式):</span><span class="sxs-lookup"><span data-stu-id="2102f-1567">10 digits (new format):</span></span>
- <span data-ttu-id="2102f-1568">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1568">10 digits</span></span>

<span data-ttu-id="2102f-1569">或</span><span class="sxs-lookup"><span data-stu-id="2102f-1569">OR</span></span>

- <span data-ttu-id="2102f-1570">六位數代表出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="2102f-1571">正斜線</span><span class="sxs-lookup"><span data-stu-id="2102f-1571">A forward slash</span></span> 
- <span data-ttu-id="2102f-1572">四位數的最後一個數位是檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1573">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1573">Checksum</span></span>

<span data-ttu-id="2102f-1574">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1575">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1575">Definition</span></span>

<span data-ttu-id="2102f-1576">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%: 函數 Func_czech_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-1577">找到 Keyword_czech_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="2102f-1578">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="2102f-1579">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1579">Keywords</span></span>

- <span data-ttu-id="2102f-1580">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1580">czech personal identity number</span></span>
- <span data-ttu-id="2102f-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="2102f-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="2102f-1582">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1583">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1583">Format</span></span>

<span data-ttu-id="2102f-1584">10位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1585">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1585">Pattern</span></span>

<span data-ttu-id="2102f-1586">10位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-1586">10 digits:</span></span>
- <span data-ttu-id="2102f-1587">DDMMYY 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2102f-1588">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-1588">A hyphen</span></span> 
- <span data-ttu-id="2102f-1589">四位數的最後一個數位是檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1590">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1590">Checksum</span></span>

<span data-ttu-id="2102f-1591">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1592">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1592">Definition</span></span>

<span data-ttu-id="2102f-1593">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%: 正則運算式 Regex_denmark_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-1594">找到 Keyword_denmark_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="2102f-1595">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-1596">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="2102f-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="2102f-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="2102f-1598">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1598">Personal Identification Number</span></span>
- <span data-ttu-id="2102f-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="2102f-1599">CPR</span></span>
- <span data-ttu-id="2102f-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="2102f-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="2102f-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="2102f-1602">藥品機關 (DEA) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1603">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1603">Format</span></span>

<span data-ttu-id="2102f-1604">兩個字母后尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1605">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1605">Pattern</span></span>

<span data-ttu-id="2102f-1606">模式必須包含下列各項:</span><span class="sxs-lookup"><span data-stu-id="2102f-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2102f-1607">此組可能的字母 (不區分大小寫): abcdefghjklmnprstux, 這是報名者程式碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="2102f-1608">一個字母 (不區分大小寫), 這是報名者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="2102f-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="2102f-1609">七位數, 最後一個是檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1610">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1610">Checksum</span></span>

<span data-ttu-id="2102f-1611">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1612">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1612">Definition</span></span>

<span data-ttu-id="2102f-1613">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1614">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1615">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-1616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1616">Keywords</span></span>

<span data-ttu-id="2102f-1617">無</span><span class="sxs-lookup"><span data-stu-id="2102f-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="2102f-1618">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1619">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1619">Format</span></span>

<span data-ttu-id="2102f-1620">16位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1621">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1621">Pattern</span></span>

<span data-ttu-id="2102f-1622">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1623">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1623">Checksum</span></span>

<span data-ttu-id="2102f-1624">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1625">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1625">Definition</span></span>

<span data-ttu-id="2102f-1626">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1627">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1628">至少下列其中一個值為 true:</span><span class="sxs-lookup"><span data-stu-id="2102f-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="2102f-1629">找到 Keyword_eu_debit_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="2102f-1630">找到 Keyword_card_terms_dict 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="2102f-1631">找到 Keyword_card_security_terms_dict 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="2102f-1632">找到 Keyword_card_expiration_terms_dict 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="2102f-1633">函數 Func_expiration_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2102f-1634">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1635">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="2102f-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="2102f-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="2102f-1637">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1637">account number</span></span> 
- <span data-ttu-id="2102f-1638">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1638">card number</span></span> 
- <span data-ttu-id="2102f-1639">卡片編號</span><span class="sxs-lookup"><span data-stu-id="2102f-1639">card no.</span></span> 
- <span data-ttu-id="2102f-1640">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1640">security number</span></span> 
- <span data-ttu-id="2102f-1641">'</span><span class="sxs-lookup"><span data-stu-id="2102f-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="2102f-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2102f-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="2102f-1643">帳戶 nbr</span><span class="sxs-lookup"><span data-stu-id="2102f-1643">acct nbr</span></span> 
- <span data-ttu-id="2102f-1644">帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-1644">acct num</span></span> 
- <span data-ttu-id="2102f-1645">帳戶否</span><span class="sxs-lookup"><span data-stu-id="2102f-1645">acct no</span></span> 
- <span data-ttu-id="2102f-1646">美洲 express</span><span class="sxs-lookup"><span data-stu-id="2102f-1646">american express</span></span> 
- <span data-ttu-id="2102f-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="2102f-1647">americanexpress</span></span> 
- <span data-ttu-id="2102f-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="2102f-1648">americano espresso</span></span> 
- <span data-ttu-id="2102f-1649">amex</span><span class="sxs-lookup"><span data-stu-id="2102f-1649">amex</span></span> 
- <span data-ttu-id="2102f-1650">atm 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1650">atm card</span></span> 
- <span data-ttu-id="2102f-1651">atm 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1651">atm cards</span></span> 
- <span data-ttu-id="2102f-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1652">atm kaart</span></span> 
- <span data-ttu-id="2102f-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1653">atmcard</span></span> 
- <span data-ttu-id="2102f-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1654">atmcards</span></span> 
- <span data-ttu-id="2102f-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1655">atmkaart</span></span> 
- <span data-ttu-id="2102f-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="2102f-1656">atmkaarten</span></span> 
- <span data-ttu-id="2102f-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="2102f-1657">bancontact</span></span> 
- <span data-ttu-id="2102f-1658">銀行卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1658">bank card</span></span> 
- <span data-ttu-id="2102f-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1659">bankkaart</span></span> 
- <span data-ttu-id="2102f-1660">持卡人</span><span class="sxs-lookup"><span data-stu-id="2102f-1660">card holder</span></span> 
- <span data-ttu-id="2102f-1661">持卡人</span><span class="sxs-lookup"><span data-stu-id="2102f-1661">card holders</span></span> 
- <span data-ttu-id="2102f-1662">卡號</span><span class="sxs-lookup"><span data-stu-id="2102f-1662">card num</span></span> 
- <span data-ttu-id="2102f-1663">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1663">card number</span></span> 
- <span data-ttu-id="2102f-1664">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1664">card numbers</span></span> 
- <span data-ttu-id="2102f-1665">卡片類型</span><span class="sxs-lookup"><span data-stu-id="2102f-1665">card type</span></span> 
- <span data-ttu-id="2102f-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="2102f-1666">cardano numerico</span></span> 
- <span data-ttu-id="2102f-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="2102f-1667">cardholder</span></span> 
- <span data-ttu-id="2102f-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="2102f-1668">cardholders</span></span> 
- <span data-ttu-id="2102f-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-1669">cardnumber</span></span> 
- <span data-ttu-id="2102f-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="2102f-1670">cardnumbers</span></span> 
- <span data-ttu-id="2102f-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="2102f-1671">carta bianca</span></span> 
- <span data-ttu-id="2102f-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1672">carta credito</span></span> 
- <span data-ttu-id="2102f-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1673">carta di credito</span></span> 
- <span data-ttu-id="2102f-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1674">cartao de credito</span></span> 
- <span data-ttu-id="2102f-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="2102f-1675">cartao de crédito</span></span> 
- <span data-ttu-id="2102f-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1676">cartao de debito</span></span> 
- <span data-ttu-id="2102f-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="2102f-1677">cartao de débito</span></span> 
- <span data-ttu-id="2102f-1678">bancaire</span><span class="sxs-lookup"><span data-stu-id="2102f-1678">carte bancaire</span></span> 
- <span data-ttu-id="2102f-1679">blanche</span><span class="sxs-lookup"><span data-stu-id="2102f-1679">carte blanche</span></span> 
- <span data-ttu-id="2102f-1680">bleue</span><span class="sxs-lookup"><span data-stu-id="2102f-1680">carte bleue</span></span> 
- <span data-ttu-id="2102f-1681">支付額度</span><span class="sxs-lookup"><span data-stu-id="2102f-1681">carte de credit</span></span> 
- <span data-ttu-id="2102f-1682">crédit</span><span class="sxs-lookup"><span data-stu-id="2102f-1682">carte de crédit</span></span> 
- <span data-ttu-id="2102f-1683">credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1683">carte di credito</span></span> 
- <span data-ttu-id="2102f-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="2102f-1684">carteblanche</span></span> 
- <span data-ttu-id="2102f-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1685">cartão de credito</span></span> 
- <span data-ttu-id="2102f-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="2102f-1686">cartão de crédito</span></span> 
- <span data-ttu-id="2102f-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1687">cartão de debito</span></span> 
- <span data-ttu-id="2102f-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="2102f-1688">cartão de débito</span></span> 
- <span data-ttu-id="2102f-1689">cb</span><span class="sxs-lookup"><span data-stu-id="2102f-1689">cb</span></span> 
- <span data-ttu-id="2102f-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="2102f-1690">ccn</span></span> 
- <span data-ttu-id="2102f-1691">檢查卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1691">check card</span></span> 
- <span data-ttu-id="2102f-1692">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1692">check cards</span></span> 
- <span data-ttu-id="2102f-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1693">checkcard</span></span>
- <span data-ttu-id="2102f-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1694">checkcards</span></span> 
- <span data-ttu-id="2102f-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1695">chequekaart</span></span> 
- <span data-ttu-id="2102f-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="2102f-1696">cirrus</span></span> 
- <span data-ttu-id="2102f-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="2102f-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="2102f-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1698">controlekaart</span></span> 
- <span data-ttu-id="2102f-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="2102f-1699">controlekaarten</span></span> 
- <span data-ttu-id="2102f-1700">信用卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1700">credit card</span></span> 
- <span data-ttu-id="2102f-1701">信用卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1701">credit cards</span></span> 
- <span data-ttu-id="2102f-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1702">creditcard</span></span> 
- <span data-ttu-id="2102f-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1703">creditcards</span></span> 
- <span data-ttu-id="2102f-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1704">debetkaart</span></span> 
- <span data-ttu-id="2102f-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="2102f-1705">debetkaarten</span></span> 
- <span data-ttu-id="2102f-1706">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1706">debit card</span></span> 
- <span data-ttu-id="2102f-1707">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1707">debit cards</span></span> 
- <span data-ttu-id="2102f-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="2102f-1708">debitcard</span></span> 
- <span data-ttu-id="2102f-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="2102f-1709">debitcards</span></span> 
- <span data-ttu-id="2102f-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="2102f-1710">debito automatico</span></span> 
- <span data-ttu-id="2102f-1711">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="2102f-1711">diners club</span></span> 
- <span data-ttu-id="2102f-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="2102f-1712">dinersclub</span></span> 
- <span data-ttu-id="2102f-1713">探索</span><span class="sxs-lookup"><span data-stu-id="2102f-1713">discover</span></span> 
- <span data-ttu-id="2102f-1714">探索卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1714">discover card</span></span> 
- <span data-ttu-id="2102f-1715">探索卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-1715">discover cards</span></span> 
- <span data-ttu-id="2102f-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="2102f-1716">discovercard</span></span> 
- <span data-ttu-id="2102f-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="2102f-1717">discovercards</span></span> 
- <span data-ttu-id="2102f-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="2102f-1718">débito automático</span></span>
- <span data-ttu-id="2102f-1719">edc</span><span class="sxs-lookup"><span data-stu-id="2102f-1719">edc</span></span> 
- <span data-ttu-id="2102f-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="2102f-1720">eigentümername</span></span> 
- <span data-ttu-id="2102f-1721">歐洲借貸卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1721">european debit card</span></span> 
- <span data-ttu-id="2102f-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1722">hoofdkaart</span></span> 
- <span data-ttu-id="2102f-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="2102f-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="2102f-1724">在 viaggio</span><span class="sxs-lookup"><span data-stu-id="2102f-1724">in viaggio</span></span> 
- <span data-ttu-id="2102f-1725">日式卡局</span><span class="sxs-lookup"><span data-stu-id="2102f-1725">japanese card bureau</span></span> 
- <span data-ttu-id="2102f-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="2102f-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="2102f-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="2102f-1727">jcb</span></span> 
- <span data-ttu-id="2102f-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="2102f-1728">kaart</span></span> 
- <span data-ttu-id="2102f-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="2102f-1729">kaart num</span></span> 
- <span data-ttu-id="2102f-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="2102f-1730">kaartaantal</span></span> 
- <span data-ttu-id="2102f-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="2102f-1731">kaartaantallen</span></span> 
- <span data-ttu-id="2102f-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="2102f-1732">kaarthouder</span></span> 
- <span data-ttu-id="2102f-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="2102f-1733">kaarthouders</span></span> 
- <span data-ttu-id="2102f-1734">karte</span><span class="sxs-lookup"><span data-stu-id="2102f-1734">karte</span></span>  
- <span data-ttu-id="2102f-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="2102f-1735">karteninhaber</span></span> 
- <span data-ttu-id="2102f-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="2102f-1736">karteninhabers</span></span>
- <span data-ttu-id="2102f-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="2102f-1737">kartennr</span></span> 
- <span data-ttu-id="2102f-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1738">kartennummer</span></span> 
- <span data-ttu-id="2102f-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="2102f-1739">kreditkarte</span></span> 
- <span data-ttu-id="2102f-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="2102f-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="2102f-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="2102f-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="2102f-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="2102f-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="2102f-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="2102f-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="2102f-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="2102f-1745">maestro</span></span> 
- <span data-ttu-id="2102f-1746">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1746">master card</span></span> 
- <span data-ttu-id="2102f-1747">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="2102f-1747">master cards</span></span> 
- <span data-ttu-id="2102f-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="2102f-1748">mastercard</span></span> 
- <span data-ttu-id="2102f-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="2102f-1749">mastercards</span></span> 
- <span data-ttu-id="2102f-1750">mc</span><span class="sxs-lookup"><span data-stu-id="2102f-1750">mc</span></span> 
- <span data-ttu-id="2102f-1751">mister 現金</span><span class="sxs-lookup"><span data-stu-id="2102f-1751">mister cash</span></span> 
- <span data-ttu-id="2102f-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1752">n carta</span></span> 
- <span data-ttu-id="2102f-1753">carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1753">carta</span></span> 
- <span data-ttu-id="2102f-1754">無任何 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1754">no de tarjeta</span></span> 
- <span data-ttu-id="2102f-1755">不 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1755">no do cartao</span></span> 
- <span data-ttu-id="2102f-1756">不 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1756">no do cartão</span></span> 
- <span data-ttu-id="2102f-1757">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1757">no.</span></span> <span data-ttu-id="2102f-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1758">de tarjeta</span></span> 
- <span data-ttu-id="2102f-1759">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1759">no.</span></span> <span data-ttu-id="2102f-1760">執行 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1760">do cartao</span></span> 
- <span data-ttu-id="2102f-1761">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1761">no.</span></span> <span data-ttu-id="2102f-1762">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1762">do cartão</span></span> 
- <span data-ttu-id="2102f-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1763">nr carta</span></span> 
- <span data-ttu-id="2102f-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="2102f-1764">nr.</span></span> <span data-ttu-id="2102f-1765">carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1765">carta</span></span> 
- <span data-ttu-id="2102f-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1766">numeri di scheda</span></span> 
- <span data-ttu-id="2102f-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1767">numero carta</span></span> 
- <span data-ttu-id="2102f-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1768">numero de cartao</span></span> 
- <span data-ttu-id="2102f-1769">numero 的重複購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1769">numero de carte</span></span> 
- <span data-ttu-id="2102f-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1770">numero de cartão</span></span> 
- <span data-ttu-id="2102f-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1771">numero de tarjeta</span></span>
- <span data-ttu-id="2102f-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1772">numero della carta</span></span> 
- <span data-ttu-id="2102f-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1773">numero di carta</span></span> 
- <span data-ttu-id="2102f-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1774">numero di scheda</span></span> 
- <span data-ttu-id="2102f-1775">numero 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1775">numero do cartao</span></span> 
- <span data-ttu-id="2102f-1776">numero 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1776">numero do cartão</span></span> 
- <span data-ttu-id="2102f-1777">numéro 的重複購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1777">numéro de carte</span></span> 
- <span data-ttu-id="2102f-1778">n º carta</span><span class="sxs-lookup"><span data-stu-id="2102f-1778">nº carta</span></span> 
- <span data-ttu-id="2102f-1779">n º重複購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1779">nº de carte</span></span> 
- <span data-ttu-id="2102f-1780">n º de 照購買</span><span class="sxs-lookup"><span data-stu-id="2102f-1780">nº de la carte</span></span> 
- <span data-ttu-id="2102f-1781">n º de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="2102f-1782">n º do cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1782">nº do cartao</span></span> 
- <span data-ttu-id="2102f-1783">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1783">nº do cartão</span></span> 
- <span data-ttu-id="2102f-1784">n º</span><span class="sxs-lookup"><span data-stu-id="2102f-1784">nº.</span></span> <span data-ttu-id="2102f-1785">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1785">do cartão</span></span> 
- <span data-ttu-id="2102f-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1786">número de cartao</span></span> 
- <span data-ttu-id="2102f-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="2102f-1787">número de cartão</span></span> 
- <span data-ttu-id="2102f-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2102f-1788">número de tarjeta</span></span> 
- <span data-ttu-id="2102f-1789">número 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="2102f-1789">número do cartao</span></span> 
- <span data-ttu-id="2102f-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="2102f-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="2102f-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2102f-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="2102f-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2102f-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="2102f-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="2102f-1793">scheda della banca</span></span> 
- <span data-ttu-id="2102f-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="2102f-1794">scheda di controllo</span></span> 
- <span data-ttu-id="2102f-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1795">scheda di debito</span></span> 
- <span data-ttu-id="2102f-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="2102f-1796">scheda matrice</span></span> 
- <span data-ttu-id="2102f-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2102f-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="2102f-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="2102f-1798">schede di controllo</span></span> 
- <span data-ttu-id="2102f-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1799">schede di debito</span></span> 
- <span data-ttu-id="2102f-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="2102f-1800">schede matrici</span></span> 
- <span data-ttu-id="2102f-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="2102f-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="2102f-1802">scoprono le schede</span></span> 
- <span data-ttu-id="2102f-1803">核</span><span class="sxs-lookup"><span data-stu-id="2102f-1803">solo</span></span> 
- <span data-ttu-id="2102f-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1804">supporti di scheda</span></span> 
- <span data-ttu-id="2102f-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1805">supporto di scheda</span></span> 
- <span data-ttu-id="2102f-1806">更換</span><span class="sxs-lookup"><span data-stu-id="2102f-1806">switch</span></span> 
- <span data-ttu-id="2102f-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="2102f-1807">tarjeta atm</span></span> 
- <span data-ttu-id="2102f-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1808">tarjeta credito</span></span> 
- <span data-ttu-id="2102f-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="2102f-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="2102f-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="2102f-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="2102f-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="2102f-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="2102f-1812">tarjeta debito</span></span> 
- <span data-ttu-id="2102f-1813">tarjeta 否</span><span class="sxs-lookup"><span data-stu-id="2102f-1813">tarjeta no</span></span>
- <span data-ttu-id="2102f-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="2102f-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="2102f-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1815">tipo della scheda</span></span> 
- <span data-ttu-id="2102f-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="2102f-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="2102f-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1817">scheda</span></span> 
- <span data-ttu-id="2102f-1818">v 支付</span><span class="sxs-lookup"><span data-stu-id="2102f-1818">v pay</span></span> 
- <span data-ttu-id="2102f-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="2102f-1819">v-pay</span></span> 
- <span data-ttu-id="2102f-1820">visa</span><span class="sxs-lookup"><span data-stu-id="2102f-1820">visa</span></span> 
- <span data-ttu-id="2102f-1821">簽證加</span><span class="sxs-lookup"><span data-stu-id="2102f-1821">visa plus</span></span> 
- <span data-ttu-id="2102f-1822">簽證電</span><span class="sxs-lookup"><span data-stu-id="2102f-1822">visa electron</span></span> 
- <span data-ttu-id="2102f-1823">visto</span><span class="sxs-lookup"><span data-stu-id="2102f-1823">visto</span></span> 
- <span data-ttu-id="2102f-1824">visum</span><span class="sxs-lookup"><span data-stu-id="2102f-1824">visum</span></span> 
- <span data-ttu-id="2102f-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="2102f-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="2102f-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2102f-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="2102f-1827">卡片識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1827">card identification number</span></span>
- <span data-ttu-id="2102f-1828">卡驗證</span><span class="sxs-lookup"><span data-stu-id="2102f-1828">card verification</span></span> 
- <span data-ttu-id="2102f-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="2102f-1829">cardi la verifica</span></span> 
- <span data-ttu-id="2102f-1830">cid</span><span class="sxs-lookup"><span data-stu-id="2102f-1830">cid</span></span> 
- <span data-ttu-id="2102f-1831">貨到 seg</span><span class="sxs-lookup"><span data-stu-id="2102f-1831">cod seg</span></span> 
- <span data-ttu-id="2102f-1832">貨到 seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1832">cod seguranca</span></span> 
- <span data-ttu-id="2102f-1833">貨到 segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1833">cod segurança</span></span> 
- <span data-ttu-id="2102f-1834">貨到 sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1834">cod sicurezza</span></span> 
- <span data-ttu-id="2102f-1835">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1835">cod.</span></span> <span data-ttu-id="2102f-1836">seg</span><span class="sxs-lookup"><span data-stu-id="2102f-1836">seg</span></span> 
- <span data-ttu-id="2102f-1837">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1837">cod.</span></span> <span data-ttu-id="2102f-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1838">seguranca</span></span> 
- <span data-ttu-id="2102f-1839">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1839">cod.</span></span> <span data-ttu-id="2102f-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1840">segurança</span></span> 
- <span data-ttu-id="2102f-1841">清單.</span><span class="sxs-lookup"><span data-stu-id="2102f-1841">cod.</span></span> <span data-ttu-id="2102f-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1842">sicurezza</span></span> 
- <span data-ttu-id="2102f-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="2102f-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="2102f-1844">codice di verifica</span></span> 
- <span data-ttu-id="2102f-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="2102f-1845">codigo</span></span> 
- <span data-ttu-id="2102f-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="2102f-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1847">codigo de segurança</span></span> 
- <span data-ttu-id="2102f-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="2102f-1848">crittogramma</span></span> 
- <span data-ttu-id="2102f-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="2102f-1849">cryptogram</span></span> 
- <span data-ttu-id="2102f-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="2102f-1850">cryptogramme</span></span> 
- <span data-ttu-id="2102f-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="2102f-1851">cv2</span></span> 
- <span data-ttu-id="2102f-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="2102f-1852">cvc</span></span> 
- <span data-ttu-id="2102f-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="2102f-1853">cvc2</span></span> 
- <span data-ttu-id="2102f-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="2102f-1854">cvn</span></span> 
- <span data-ttu-id="2102f-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="2102f-1855">cvv</span></span> 
- <span data-ttu-id="2102f-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="2102f-1856">cvv2</span></span> 
- <span data-ttu-id="2102f-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1857">cód seguranca</span></span> 
- <span data-ttu-id="2102f-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1858">cód segurança</span></span> 
- <span data-ttu-id="2102f-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="2102f-1859">cód.</span></span> <span data-ttu-id="2102f-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1860">seguranca</span></span> 
- <span data-ttu-id="2102f-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="2102f-1861">cód.</span></span> <span data-ttu-id="2102f-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1862">segurança</span></span> 
- <span data-ttu-id="2102f-1863">código</span><span class="sxs-lookup"><span data-stu-id="2102f-1863">código</span></span> 
- <span data-ttu-id="2102f-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="2102f-1864">código de seguranca</span></span> 
- <span data-ttu-id="2102f-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="2102f-1865">código de segurança</span></span> 
- <span data-ttu-id="2102f-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="2102f-1866">de kaart controle</span></span> 
- <span data-ttu-id="2102f-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="2102f-1867">geeft nr uit</span></span> 
- <span data-ttu-id="2102f-1868">問題否</span><span class="sxs-lookup"><span data-stu-id="2102f-1868">issue no</span></span> 
- <span data-ttu-id="2102f-1869">發行號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1869">issue number</span></span> 
- <span data-ttu-id="2102f-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="2102f-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="2102f-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="2102f-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="2102f-1873">kwestieaantal</span></span> 
- <span data-ttu-id="2102f-1874">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1874">no.</span></span> <span data-ttu-id="2102f-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="2102f-1875">dell'edizione</span></span> 
- <span data-ttu-id="2102f-1876">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-1876">no.</span></span> <span data-ttu-id="2102f-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1877">di sicurezza</span></span> 
- <span data-ttu-id="2102f-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="2102f-1878">numero de securite</span></span> 
- <span data-ttu-id="2102f-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="2102f-1879">numero de verificacao</span></span> 
- <span data-ttu-id="2102f-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="2102f-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="2102f-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="2102f-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="2102f-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="2102f-1882">scheda</span></span> 
- <span data-ttu-id="2102f-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2102f-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="2102f-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="2102f-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="2102f-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="2102f-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="2102f-1886">n º autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2102f-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="2102f-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="2102f-1887">número de verificação</span></span> 
- <span data-ttu-id="2102f-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="2102f-1888">perno il blocco</span></span> 
- <span data-ttu-id="2102f-1889">pin 區塊</span><span class="sxs-lookup"><span data-stu-id="2102f-1889">pin block</span></span> 
- <span data-ttu-id="2102f-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="2102f-1890">prufziffer</span></span> 
- <span data-ttu-id="2102f-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2102f-1891">prüfziffer</span></span> 
- <span data-ttu-id="2102f-1892">安全性程式碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1892">security code</span></span> 
- <span data-ttu-id="2102f-1893">安全性否</span><span class="sxs-lookup"><span data-stu-id="2102f-1893">security no</span></span> 
- <span data-ttu-id="2102f-1894">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1894">security number</span></span> 
- <span data-ttu-id="2102f-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="2102f-1895">sicherheits kode</span></span> 
- <span data-ttu-id="2102f-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="2102f-1896">sicherheitscode</span></span> 
- <span data-ttu-id="2102f-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="2102f-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="2102f-1898">speldblok</span></span> 
- <span data-ttu-id="2102f-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="2102f-1899">veiligheid nr</span></span> 
- <span data-ttu-id="2102f-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="2102f-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="2102f-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="2102f-1901">veiligheidscode</span></span> 
- <span data-ttu-id="2102f-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="2102f-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="2102f-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2102f-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="2102f-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="2102f-1905">ablauf</span></span> 
- <span data-ttu-id="2102f-1906">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="2102f-1906">data de expiracao</span></span> 
- <span data-ttu-id="2102f-1907">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="2102f-1907">data de expiração</span></span> 
- <span data-ttu-id="2102f-1908">資料 del exp</span><span class="sxs-lookup"><span data-stu-id="2102f-1908">data del exp</span></span> 
- <span data-ttu-id="2102f-1909">資料 di exp</span><span class="sxs-lookup"><span data-stu-id="2102f-1909">data di exp</span></span> 
- <span data-ttu-id="2102f-1910">資料 di scadenza</span><span class="sxs-lookup"><span data-stu-id="2102f-1910">data di scadenza</span></span> 
- <span data-ttu-id="2102f-1911">資料 em mail.que expira</span><span class="sxs-lookup"><span data-stu-id="2102f-1911">data em que expira</span></span> 
- <span data-ttu-id="2102f-1912">資料 scad</span><span class="sxs-lookup"><span data-stu-id="2102f-1912">data scad</span></span> 
- <span data-ttu-id="2102f-1913">資料 scadenza</span><span class="sxs-lookup"><span data-stu-id="2102f-1913">data scadenza</span></span> 
- <span data-ttu-id="2102f-1914">日期 de validité</span><span class="sxs-lookup"><span data-stu-id="2102f-1914">date de validité</span></span> 
- <span data-ttu-id="2102f-1915">基準 afloop</span><span class="sxs-lookup"><span data-stu-id="2102f-1915">datum afloop</span></span> 
- <span data-ttu-id="2102f-1916">基準 van exp</span><span class="sxs-lookup"><span data-stu-id="2102f-1916">datum van exp</span></span> 
- <span data-ttu-id="2102f-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="2102f-1917">de afloop</span></span> 
- <span data-ttu-id="2102f-1918">espira</span><span class="sxs-lookup"><span data-stu-id="2102f-1918">espira</span></span> 
- <span data-ttu-id="2102f-1919">espira</span><span class="sxs-lookup"><span data-stu-id="2102f-1919">espira</span></span> 
- <span data-ttu-id="2102f-1920">到期日</span><span class="sxs-lookup"><span data-stu-id="2102f-1920">exp date</span></span> 
- <span data-ttu-id="2102f-1921">exp 基準</span><span class="sxs-lookup"><span data-stu-id="2102f-1921">exp datum</span></span> 
- <span data-ttu-id="2102f-1922">到期</span><span class="sxs-lookup"><span data-stu-id="2102f-1922">expiration</span></span> 
- <span data-ttu-id="2102f-1923">期限</span><span class="sxs-lookup"><span data-stu-id="2102f-1923">expire</span></span> 
- <span data-ttu-id="2102f-1924">到期</span><span class="sxs-lookup"><span data-stu-id="2102f-1924">expires</span></span> 
- <span data-ttu-id="2102f-1925">永不</span><span class="sxs-lookup"><span data-stu-id="2102f-1925">expiry</span></span> 
- <span data-ttu-id="2102f-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="2102f-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="2102f-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="2102f-1927">fecha de venc</span></span> 
- <span data-ttu-id="2102f-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="2102f-1928">gultig bis</span></span> 
- <span data-ttu-id="2102f-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="2102f-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="2102f-1930">gültig bis</span></span> 
- <span data-ttu-id="2102f-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="2102f-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="2102f-1932">la scadenza</span></span> 
- <span data-ttu-id="2102f-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="2102f-1933">scadenza</span></span> 
- <span data-ttu-id="2102f-1934">valable</span><span class="sxs-lookup"><span data-stu-id="2102f-1934">valable</span></span> 
- <span data-ttu-id="2102f-1935">validade</span><span class="sxs-lookup"><span data-stu-id="2102f-1935">validade</span></span> 
- <span data-ttu-id="2102f-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="2102f-1936">valido hasta</span></span> 
- <span data-ttu-id="2102f-1937">valor</span><span class="sxs-lookup"><span data-stu-id="2102f-1937">valor</span></span> 
- <span data-ttu-id="2102f-1938">venc</span><span class="sxs-lookup"><span data-stu-id="2102f-1938">venc</span></span> 
- <span data-ttu-id="2102f-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="2102f-1939">vencimento</span></span> 
- <span data-ttu-id="2102f-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="2102f-1940">vencimiento</span></span> 
- <span data-ttu-id="2102f-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="2102f-1941">verloopt</span></span> 
- <span data-ttu-id="2102f-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="2102f-1942">vervaldag</span></span> 
- <span data-ttu-id="2102f-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="2102f-1943">vervaldatum</span></span> 
- <span data-ttu-id="2102f-1944">vto</span><span class="sxs-lookup"><span data-stu-id="2102f-1944">vto</span></span> 
- <span data-ttu-id="2102f-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="2102f-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="2102f-1946">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1946">EU Driver's License Number</span></span>

<span data-ttu-id="2102f-1947">若要深入瞭解, 請參閱[歐盟駕駛執照號碼敏感資訊類型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="2102f-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="2102f-1948">歐盟國家身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1948">EU National Identification Number</span></span>

<span data-ttu-id="2102f-1949">若要深入瞭解, 請參閱[歐盟國家身分識別號碼敏感資訊類型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="2102f-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="2102f-1950">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1950">EU Passport Number</span></span>

<span data-ttu-id="2102f-1951">若要深入瞭解, 請參閱[歐盟護照號碼敏感資訊類型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="2102f-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="2102f-1952">歐盟社會保險號碼或同等識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="2102f-1953">若要深入瞭解, 請參閱[歐盟社會保險號碼或對等 ID 敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="2102f-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="2102f-1954">歐盟納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="2102f-1955">若要深入瞭解, 請參閱[歐盟納稅身分識別號碼敏感資訊類型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="2102f-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="2102f-1956">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1957">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1957">Format</span></span>

<span data-ttu-id="2102f-1958">六位數加上一個字元, 表示一個世紀加上三個數字加上一個校驗位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1959">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1959">Pattern</span></span>

<span data-ttu-id="2102f-1960">模式必須包含下列各項:</span><span class="sxs-lookup"><span data-stu-id="2102f-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2102f-1961">DDMMYY 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="2102f-1962">世紀標記 ('-'、' + ' 或 ' a ')</span><span class="sxs-lookup"><span data-stu-id="2102f-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="2102f-1963">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="2102f-1964">一種數位或字母 (不區分大小寫), 這是一種檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1965">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1965">Checksum</span></span>

<span data-ttu-id="2102f-1966">是</span><span class="sxs-lookup"><span data-stu-id="2102f-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1967">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1967">Definition</span></span>

<span data-ttu-id="2102f-1968">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1969">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1970">找到 Keyword_finnish_national_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="2102f-1971">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-1972">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1972">Keywords</span></span>

- <span data-ttu-id="2102f-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="2102f-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="2102f-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="2102f-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="2102f-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="2102f-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="2102f-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="2102f-1976">Personbeteckning</span></span>
- <span data-ttu-id="2102f-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="2102f-1978">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1978">Finland Passport Number</span></span>

<span data-ttu-id="2102f-1979">將九個字母和數位模式組合搭配九個字母和數位的格式組合: 兩個字母 (不區分大小寫) 七位數校驗和無定義 DLP 75 原則在300字元的鄰近性: 正則運算式 Regex_finland_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-1980">找到 Keyword_finland_passport_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="2102f-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="2102f-1981"></span></span>
<span data-ttu-id="2102f-1982">關鍵字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="2102f-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="2102f-1983">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="2102f-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-1984">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-1984">Format</span></span>

<span data-ttu-id="2102f-1985">12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-1986">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-1986">Pattern</span></span>

<span data-ttu-id="2102f-1987">12位數的折扣類似模式, 例如法文電話號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-1988">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-1988">Checksum</span></span>

<span data-ttu-id="2102f-1989">否</span><span class="sxs-lookup"><span data-stu-id="2102f-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-1990">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-1990">Definition</span></span>

<span data-ttu-id="2102f-1991">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-1992">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-1993">至少下列其中一個值為 true:</span><span class="sxs-lookup"><span data-stu-id="2102f-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="2102f-1994">找到 Keyword_french_drivers_license 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="2102f-1995">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-1996">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="2102f-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2102f-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="2102f-1998">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-1998">drivers licence</span></span>
- <span data-ttu-id="2102f-1999">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-1999">drivers license</span></span>
- <span data-ttu-id="2102f-2000">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2000">driving licence</span></span>
- <span data-ttu-id="2102f-2001">駕駛授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2001">driving license</span></span>
- <span data-ttu-id="2102f-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="2102f-2002">permis de conduire</span></span>
- <span data-ttu-id="2102f-2003">許可號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2003">licence number</span></span>
- <span data-ttu-id="2102f-2004">授權號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2004">license number</span></span>
- <span data-ttu-id="2102f-2005">許可號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2005">licence numbers</span></span>
- <span data-ttu-id="2102f-2006">授權號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="2102f-2007">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="2102f-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2008">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2008">Format</span></span>

<span data-ttu-id="2102f-2009">12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2010">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2010">Pattern</span></span>

<span data-ttu-id="2102f-2011">12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2012">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2012">Checksum</span></span>

<span data-ttu-id="2102f-2013">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2014">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2014">Definition</span></span>

<span data-ttu-id="2102f-2015">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2016">正則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2017">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2017">Keywords</span></span>

<span data-ttu-id="2102f-2018">無</span><span class="sxs-lookup"><span data-stu-id="2102f-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="2102f-2019">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2020">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2020">Format</span></span>

<span data-ttu-id="2102f-2021">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2022">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2022">Pattern</span></span>

<span data-ttu-id="2102f-2023">九個數字和字母:</span><span class="sxs-lookup"><span data-stu-id="2102f-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="2102f-2024">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2024">Two digits</span></span> 
- <span data-ttu-id="2102f-2025">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-2026">五位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2027">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2027">Checksum</span></span>

<span data-ttu-id="2102f-2028">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2029">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2029">Definition</span></span>

<span data-ttu-id="2102f-2030">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2031">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2032">找到 Keyword_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2033">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2102f-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-2034">Keyword_passport</span></span>

- <span data-ttu-id="2102f-2035">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2035">Passport Number</span></span>
- <span data-ttu-id="2102f-2036">護照否</span><span class="sxs-lookup"><span data-stu-id="2102f-2036">Passport No</span></span>
- <span data-ttu-id="2102f-2037">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-2037">Passport #</span></span>
- <span data-ttu-id="2102f-2038">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-2038">Passport#</span></span>
- <span data-ttu-id="2102f-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="2102f-2039">PassportID</span></span>
- <span data-ttu-id="2102f-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="2102f-2040">Passportno</span></span>
- <span data-ttu-id="2102f-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-2041">passportnumber</span></span>
- <span data-ttu-id="2102f-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="2102f-2042">パスポート</span></span>
- <span data-ttu-id="2102f-2043">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2043">パスポート番号</span></span>
- <span data-ttu-id="2102f-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2102f-2044">パスポートのNum</span></span>
- <span data-ttu-id="2102f-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2045">パスポート ＃</span></span> 
- <span data-ttu-id="2102f-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2102f-2046">Numéro de passeport</span></span>
- <span data-ttu-id="2102f-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2102f-2047">Passeport n °</span></span>
- <span data-ttu-id="2102f-2048">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="2102f-2048">Passeport Non</span></span>
- <span data-ttu-id="2102f-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2102f-2049">Passeport #</span></span>
- <span data-ttu-id="2102f-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2102f-2050">Passeport#</span></span>
- <span data-ttu-id="2102f-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2102f-2051">PasseportNon</span></span>
- <span data-ttu-id="2102f-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2102f-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="2102f-2053">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="2102f-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2054">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2054">Format</span></span>

<span data-ttu-id="2102f-2055">15位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2056">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2056">Pattern</span></span>

<span data-ttu-id="2102f-2057">必須符合兩種模式的其中一種:</span><span class="sxs-lookup"><span data-stu-id="2102f-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="2102f-2058">13位數後接一個空格, 後面接著兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="2102f-2059">或</span><span class="sxs-lookup"><span data-stu-id="2102f-2059">or</span></span>
- <span data-ttu-id="2102f-2060">15個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2061">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2061">Checksum</span></span>

<span data-ttu-id="2102f-2062">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2063">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2063">Definition</span></span>

<span data-ttu-id="2102f-2064">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 95%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2065">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2066">找到 Keyword_fr_insee 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="2102f-2067">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2067">The checksum passes.</span></span>

<span data-ttu-id="2102f-2068">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2069">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2070">找不到 Keyword_fr_insee 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="2102f-2071">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2072">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="2102f-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="2102f-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="2102f-2074">insee</span><span class="sxs-lookup"><span data-stu-id="2102f-2074">insee</span></span>
- <span data-ttu-id="2102f-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="2102f-2075">securité sociale</span></span>
- <span data-ttu-id="2102f-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="2102f-2076">securite sociale</span></span>
- <span data-ttu-id="2102f-2077">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2077">national id</span></span>
- <span data-ttu-id="2102f-2078">民族識別</span><span class="sxs-lookup"><span data-stu-id="2102f-2078">national identification</span></span>
- <span data-ttu-id="2102f-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="2102f-2079">numéro d'identité</span></span>
- <span data-ttu-id="2102f-2080">沒有 d'identité</span><span class="sxs-lookup"><span data-stu-id="2102f-2080">no d'identité</span></span>
- <span data-ttu-id="2102f-2081">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-2081">no.</span></span> <span data-ttu-id="2102f-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="2102f-2082">d'identité</span></span>
- <span data-ttu-id="2102f-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="2102f-2083">numero d'identite</span></span>
- <span data-ttu-id="2102f-2084">沒有 d'identite</span><span class="sxs-lookup"><span data-stu-id="2102f-2084">no d'identite</span></span>
- <span data-ttu-id="2102f-2085">不。</span><span class="sxs-lookup"><span data-stu-id="2102f-2085">no.</span></span> <span data-ttu-id="2102f-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="2102f-2086">d'identite</span></span>
- <span data-ttu-id="2102f-2087">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2087">social security number</span></span>
- <span data-ttu-id="2102f-2088">社會保險程式碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2088">social security code</span></span>
- <span data-ttu-id="2102f-2089">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2089">social insurance number</span></span>
- <span data-ttu-id="2102f-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="2102f-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="2102f-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="2102f-2091">d'identité nationale</span></span>
- <span data-ttu-id="2102f-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2102f-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="2102f-2093">le 程式碼 de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2102f-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="2102f-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="2102f-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="2102f-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="2102f-2095">numéro de sécu</span></span>
- <span data-ttu-id="2102f-2096">程式碼 sécu</span><span class="sxs-lookup"><span data-stu-id="2102f-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="2102f-2097">德文駕照編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2098">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2098">Format</span></span>

<span data-ttu-id="2102f-2099">11位數和字母的組合</span><span class="sxs-lookup"><span data-stu-id="2102f-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2100">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2100">Pattern</span></span>

<span data-ttu-id="2102f-2101">11個數字和字母 (不區分大小寫):</span><span class="sxs-lookup"><span data-stu-id="2102f-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="2102f-2102">一個數位或字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2102">A digit or letter</span></span> 
- <span data-ttu-id="2102f-2103">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2103">Two digits</span></span> 
- <span data-ttu-id="2102f-2104">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2104">Six digits or letters</span></span> 
- <span data-ttu-id="2102f-2105">一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2105">A digit</span></span> 
- <span data-ttu-id="2102f-2106">一個數位或字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2107">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2107">Checksum</span></span>

<span data-ttu-id="2102f-2108">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2109">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2109">Definition</span></span>

<span data-ttu-id="2102f-2110">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2111">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2112">至少下列其中一個值為 true:</span><span class="sxs-lookup"><span data-stu-id="2102f-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="2102f-2113">找到 Keyword_german_drivers_license_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="2102f-2114">找到 Keyword_german_drivers_license_collaborative 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="2102f-2115">找到 Keyword_german_drivers_license 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="2102f-2116">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2117">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="2102f-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="2102f-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2119">Führerschein</span></span>
- <span data-ttu-id="2102f-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2120">Fuhrerschein</span></span>
- <span data-ttu-id="2102f-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2121">Fuehrerschein</span></span>
- <span data-ttu-id="2102f-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="2102f-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="2102f-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="2102f-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="2102f-2125">Führerschein-</span></span> 
- <span data-ttu-id="2102f-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="2102f-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="2102f-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="2102f-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="2102f-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2102f-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="2102f-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2102f-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="2102f-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2102f-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="2102f-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="2102f-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="2102f-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="2102f-2134">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="2102f-2135">Fuhrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="2102f-2136">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="2102f-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="2102f-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="2102f-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="2102f-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2102f-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="2102f-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2102f-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="2102f-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2102f-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="2102f-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2102f-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2102f-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2102f-2146">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="2102f-2147">Fuhrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="2102f-2148">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="2102f-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="2102f-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="2102f-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="2102f-2152">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-2152">DL</span></span> 
- <span data-ttu-id="2102f-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="2102f-2153">DLS</span></span>
- <span data-ttu-id="2102f-2154">Driv .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-2154">Driv Lic</span></span> 
- <span data-ttu-id="2102f-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="2102f-2155">Driv Licen</span></span> 
- <span data-ttu-id="2102f-2156">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2156">Driv License</span></span>
- <span data-ttu-id="2102f-2157">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2157">Driv Licenses</span></span> 
- <span data-ttu-id="2102f-2158">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2158">Driv Licence</span></span> 
- <span data-ttu-id="2102f-2159">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2159">Driv Licences</span></span> 
- <span data-ttu-id="2102f-2160">Driv .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-2160">Driv Lic</span></span> 
- <span data-ttu-id="2102f-2161">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="2102f-2161">Driver Licen</span></span> 
- <span data-ttu-id="2102f-2162">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2162">Driver License</span></span> 
- <span data-ttu-id="2102f-2163">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2163">Driver Licenses</span></span> 
- <span data-ttu-id="2102f-2164">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2164">Driver Licence</span></span> 
- <span data-ttu-id="2102f-2165">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2165">Driver Licences</span></span> 
- <span data-ttu-id="2102f-2166">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-2166">Drivers Lic</span></span> 
- <span data-ttu-id="2102f-2167">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="2102f-2167">Drivers Licen</span></span> 
- <span data-ttu-id="2102f-2168">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2168">Drivers License</span></span> 
- <span data-ttu-id="2102f-2169">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="2102f-2170">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2170">Drivers Licence</span></span> 
- <span data-ttu-id="2102f-2171">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2171">Drivers Licences</span></span> 
- <span data-ttu-id="2102f-2172">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-2172">Driver's Lic</span></span> 
- <span data-ttu-id="2102f-2173">驅動程式的 Licen</span><span class="sxs-lookup"><span data-stu-id="2102f-2173">Driver's Licen</span></span> 
- <span data-ttu-id="2102f-2174">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-2174">Driver's License</span></span> 
- <span data-ttu-id="2102f-2175">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="2102f-2176">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-2176">Driver's Licence</span></span> 
- <span data-ttu-id="2102f-2177">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-2177">Driver's Licences</span></span> 
- <span data-ttu-id="2102f-2178">驅動許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2178">Driving Lic</span></span> 
- <span data-ttu-id="2102f-2179">驅車 Licen</span><span class="sxs-lookup"><span data-stu-id="2102f-2179">Driving Licen</span></span> 
- <span data-ttu-id="2102f-2180">駕駛授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2180">Driving License</span></span> 
- <span data-ttu-id="2102f-2181">驅動授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2181">Driving Licenses</span></span> 
- <span data-ttu-id="2102f-2182">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2182">Driving Licence</span></span> 
- <span data-ttu-id="2102f-2183">駕駛授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="2102f-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="2102f-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="2102f-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="2102f-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="2102f-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="2102f-2188">非 Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2188">No-Führerschein</span></span> 
- <span data-ttu-id="2102f-2189">非 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="2102f-2190">非 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="2102f-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2191">N-Führerschein</span></span> 
- <span data-ttu-id="2102f-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="2102f-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="2102f-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="2102f-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="2102f-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="2102f-2197">非 Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2197">No-Führerschein</span></span> 
- <span data-ttu-id="2102f-2198">非 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="2102f-2199">非 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="2102f-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2200">N-Führerschein</span></span> 
- <span data-ttu-id="2102f-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="2102f-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2102f-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="2102f-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2102f-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="2102f-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="2102f-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="2102f-2205">ausstellungsort</span></span>
- <span data-ttu-id="2102f-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="2102f-2206">ausstellende behöde</span></span>
- <span data-ttu-id="2102f-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="2102f-2207">ausstellende behorde</span></span>
- <span data-ttu-id="2102f-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="2102f-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="2102f-2209">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2210">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2210">Format</span></span>

<span data-ttu-id="2102f-2211">10個數字或字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2212">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2212">Pattern</span></span>

<span data-ttu-id="2102f-2213">模式必須包含下列各項:</span><span class="sxs-lookup"><span data-stu-id="2102f-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2102f-2214">第一個字元是此組中的數位或字母 (C、F、G、H、J、K)</span><span class="sxs-lookup"><span data-stu-id="2102f-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="2102f-2215">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2215">Three digits</span></span> 
- <span data-ttu-id="2102f-2216">此集合中有五個數字或字母 (C、-H、J-N、P、R、T、V-Z)</span><span class="sxs-lookup"><span data-stu-id="2102f-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="2102f-2217">一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2218">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2218">Checksum</span></span>

<span data-ttu-id="2102f-2219">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2220">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2220">Definition</span></span>

<span data-ttu-id="2102f-2221">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2222">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2223">找到任何五個關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="2102f-2224">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2224">The checksum passes.</span></span>

<span data-ttu-id="2102f-2225">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2226">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2227">找到任何五個關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="2102f-2228">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2229">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="2102f-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="2102f-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="2102f-2231">reisepass</span></span>
- <span data-ttu-id="2102f-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="2102f-2232">reisepasse</span></span>
- <span data-ttu-id="2102f-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2233">reisepassnummer</span></span>
- <span data-ttu-id="2102f-2234">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-2234">passport</span></span>
- <span data-ttu-id="2102f-2235">passports</span><span class="sxs-lookup"><span data-stu-id="2102f-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="2102f-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="2102f-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="2102f-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-2237">geburtsdatum</span></span>
- <span data-ttu-id="2102f-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="2102f-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="2102f-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="2102f-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="2102f-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="2102f-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="2102f-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="2102f-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="2102f-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="2102f-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="2102f-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="2102f-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="2102f-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="2102f-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="2102f-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="2102f-2246">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2247">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2247">Format</span></span>

<span data-ttu-id="2102f-2248">自1月 2010: 九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="2102f-2249">從1年4月1987至31年10月 2010:10 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2250">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2250">Pattern</span></span>

<span data-ttu-id="2102f-2251">自2010年11月1日:</span><span class="sxs-lookup"><span data-stu-id="2102f-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="2102f-2252">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-2253">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2253">Eight digits</span></span>

<span data-ttu-id="2102f-2254">從1年4月1987直到10月 2010:</span><span class="sxs-lookup"><span data-stu-id="2102f-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="2102f-2255">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2256">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2256">Checksum</span></span>

<span data-ttu-id="2102f-2257">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2258">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2258">Definition</span></span>

<span data-ttu-id="2102f-2259">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2260">正則運算式 Regex_germany_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2261">找到 Keyword_germany_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2262">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="2102f-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="2102f-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="2102f-2264">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2264">Identity Card</span></span>
- <span data-ttu-id="2102f-2265">ID</span><span class="sxs-lookup"><span data-stu-id="2102f-2265">ID</span></span>
- <span data-ttu-id="2102f-2266">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2266">Identification</span></span>
- <span data-ttu-id="2102f-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2102f-2267">Personalausweis</span></span>
- <span data-ttu-id="2102f-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="2102f-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="2102f-2269">Ausweis</span></span>
- <span data-ttu-id="2102f-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="2102f-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="2102f-2271">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2272">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2272">Format</span></span>

<span data-ttu-id="2102f-2273">7-8 字母和數位的組合加上虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2274">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2274">Pattern</span></span>

<span data-ttu-id="2102f-2275">七個字母和數位 (舊格式):</span><span class="sxs-lookup"><span data-stu-id="2102f-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="2102f-2276">一個字母 (希臘文字母表的任何字母)</span><span class="sxs-lookup"><span data-stu-id="2102f-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="2102f-2277">虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2277">A dash</span></span> 
- <span data-ttu-id="2102f-2278">六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2278">Six digits</span></span>

<span data-ttu-id="2102f-2279">八個字母和數位 (新格式):</span><span class="sxs-lookup"><span data-stu-id="2102f-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="2102f-2280">兩個字母大寫字元同時出現在希臘文和拉丁字母表 (ABEZHIKMNOPTYX)</span><span class="sxs-lookup"><span data-stu-id="2102f-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="2102f-2281">虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2281">A dash</span></span> 
- <span data-ttu-id="2102f-2282">六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2283">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2283">Checksum</span></span>

<span data-ttu-id="2102f-2284">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2285">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2285">Definition</span></span>

<span data-ttu-id="2102f-2286">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2287">正則運算式 Regex_greece_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2288">找到 Keyword_greece_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2289">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="2102f-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="2102f-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="2102f-2291">希臘文身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2291">Greek identity Card</span></span>
- <span data-ttu-id="2102f-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="2102f-2292">Tautotita</span></span>
- <span data-ttu-id="2102f-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="2102f-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="2102f-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="2102f-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="2102f-2295">中國香港身分識別卡 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2296">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2296">Format</span></span>

<span data-ttu-id="2102f-2297">8-9 字母和數位的組合, 以及最後一個字元周圍的選擇性括弧</span><span class="sxs-lookup"><span data-stu-id="2102f-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2298">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2298">Pattern</span></span>

<span data-ttu-id="2102f-2299">8-9 字母的組合:</span><span class="sxs-lookup"><span data-stu-id="2102f-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="2102f-2300">1-2 個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-2301">六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2301">Six digits</span></span> 
- <span data-ttu-id="2102f-2302">最後一個字元 (任何數位或字母 A), 也就是檢查碼, 並選擇性地括在括弧內。</span><span class="sxs-lookup"><span data-stu-id="2102f-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2303">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2303">Checksum</span></span>

<span data-ttu-id="2102f-2304">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2305">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2305">Definition</span></span>

<span data-ttu-id="2102f-2306">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2307">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2308">找到 Keyword_hong_kong_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="2102f-2309">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2309">The checksum passes.</span></span>

<span data-ttu-id="2102f-2310">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2311">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2312">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2313">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="2102f-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="2102f-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="2102f-2315">中國香港身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2315">hong kong identity card</span></span>
- <span data-ttu-id="2102f-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="2102f-2316">HKIDC</span></span>
- <span data-ttu-id="2102f-2317">id 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2317">id card</span></span>
- <span data-ttu-id="2102f-2318">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2318">identity card</span></span>
- <span data-ttu-id="2102f-2319">hk 身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2319">hk identity card</span></span>
- <span data-ttu-id="2102f-2320">中國香港 id</span><span class="sxs-lookup"><span data-stu-id="2102f-2320">hong kong id</span></span>
- <span data-ttu-id="2102f-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2321">香港身份證</span></span>
- <span data-ttu-id="2102f-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="2102f-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2323">身份證</span></span>
- <span data-ttu-id="2102f-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2324">身份証</span></span>
- <span data-ttu-id="2102f-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2325">身分證</span></span>
- <span data-ttu-id="2102f-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2326">身分証</span></span>
- <span data-ttu-id="2102f-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2327">香港身份証</span></span>
- <span data-ttu-id="2102f-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2328">香港身分證</span></span>
- <span data-ttu-id="2102f-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2329">香港身分証</span></span>
- <span data-ttu-id="2102f-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2330">香港身份證</span></span>
- <span data-ttu-id="2102f-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2331">香港居民身份證</span></span>
- <span data-ttu-id="2102f-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2332">香港居民身份証</span></span>
- <span data-ttu-id="2102f-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2333">香港居民身分證</span></span>
- <span data-ttu-id="2102f-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2334">香港居民身分証</span></span>
- <span data-ttu-id="2102f-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="2102f-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="2102f-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="2102f-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="2102f-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="2102f-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="2102f-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="2102f-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="2102f-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="2102f-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="2102f-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="2102f-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="2102f-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="2102f-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2102f-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="2102f-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="2102f-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2102f-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="2102f-2351">印度永久帳戶號碼 (PAN)</span><span class="sxs-lookup"><span data-stu-id="2102f-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2352">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2352">Format</span></span>

<span data-ttu-id="2102f-2353">10個字母或數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2354">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2354">Pattern</span></span>

<span data-ttu-id="2102f-2355">10個字母或數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-2355">10 letters or digits:</span></span>
- <span data-ttu-id="2102f-2356">五個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-2357">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2357">Four digits</span></span> 
- <span data-ttu-id="2102f-2358">一種字母, 是一種字母檢查位</span><span class="sxs-lookup"><span data-stu-id="2102f-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2359">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2359">Checksum</span></span>

<span data-ttu-id="2102f-2360">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2361">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2361">Definition</span></span>

<span data-ttu-id="2102f-2362">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2363">正則運算式 Regex_india_permanent_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2364">找到 Keyword_india_permanent_account_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="2102f-2365">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="2102f-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="2102f-2368">永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="2102f-2369">掃視</span><span class="sxs-lookup"><span data-stu-id="2102f-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="2102f-2370">印度唯一識別碼 (Aadhaar) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2371">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2371">Format</span></span>

<span data-ttu-id="2102f-2372">12位數包含選擇性空格或短杠</span><span class="sxs-lookup"><span data-stu-id="2102f-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2373">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2373">Pattern</span></span>

<span data-ttu-id="2102f-2374">12位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2374">12 digits:</span></span>
- <span data-ttu-id="2102f-2375">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2375">Four digits</span></span> 
- <span data-ttu-id="2102f-2376">選擇性的空格或虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2376">An optional space or dash</span></span> 
- <span data-ttu-id="2102f-2377">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2377">Four digits</span></span> 
- <span data-ttu-id="2102f-2378">選擇性的空格或虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2378">An optional space or dash</span></span> 
- <span data-ttu-id="2102f-2379">是檢查碼的最後一個數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2380">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2380">Checksum</span></span>

<span data-ttu-id="2102f-2381">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2382">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2382">Definition</span></span>

<span data-ttu-id="2102f-2383">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%: 函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-2384">找到 Keyword_india_aadhar 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="2102f-2385">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2385">The checksum passes.</span></span>
<span data-ttu-id="2102f-2386">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%: 函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-2387">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="2102f-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="2102f-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="2102f-2389">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="2102f-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="2102f-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="2102f-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="2102f-2391">Aadhar</span></span>
- <span data-ttu-id="2102f-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="2102f-2392">Aadhaar</span></span>
- <span data-ttu-id="2102f-2393">UID</span><span class="sxs-lookup"><span data-stu-id="2102f-2393">UID</span></span>
- <span data-ttu-id="2102f-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="2102f-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="2102f-2395">印尼身分識別卡 (KTP) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2396">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2396">Format</span></span>

<span data-ttu-id="2102f-2397">包含選用期間的16位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2398">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2398">Pattern</span></span>

<span data-ttu-id="2102f-2399">16位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2399">16 digits:</span></span>
- <span data-ttu-id="2102f-2400">兩位數的省碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2400">Two-digit province code</span></span> 
- <span data-ttu-id="2102f-2401">句點 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="2102f-2401">A period (optional)</span></span> 
- <span data-ttu-id="2102f-2402">兩位數攝政或城市代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="2102f-2403">兩位數 subdistrict 程式碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="2102f-2404">句點 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="2102f-2404">A period (optional)</span></span> 
- <span data-ttu-id="2102f-2405">DDMMYY 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2102f-2406">句點 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="2102f-2406">A period (optional)</span></span> 
- <span data-ttu-id="2102f-2407">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2408">Checksum</span></span>

<span data-ttu-id="2102f-2409">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2410">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2410">Definition</span></span>

<span data-ttu-id="2102f-2411">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2412">正則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2413">找到 Keyword_indonesia_id_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="2102f-2414">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2415">正則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2416">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="2102f-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="2102f-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="2102f-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="2102f-2418">KTP</span></span>
- <span data-ttu-id="2102f-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="2102f-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="2102f-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="2102f-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="2102f-2421">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="2102f-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2422">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2422">Format</span></span>

<span data-ttu-id="2102f-2423">國家/地區代碼 (兩個字母) 加上檢查數位 (兩位數) 加上 bban 號碼 (最多30個字元)</span><span class="sxs-lookup"><span data-stu-id="2102f-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2424">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2424">Pattern</span></span>

<span data-ttu-id="2102f-2425">模式必須包含下列各項:</span><span class="sxs-lookup"><span data-stu-id="2102f-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="2102f-2426">兩個字母的國家代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2426">Two-letter country code</span></span>
- <span data-ttu-id="2102f-2427">兩個檢查數位 (後面加上一個選擇性的空格)</span><span class="sxs-lookup"><span data-stu-id="2102f-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="2102f-2428">1-7 四個字母或數位的群組 (可由空格分隔)</span><span class="sxs-lookup"><span data-stu-id="2102f-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="2102f-2429">1-3 個字母或數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2429">1-3 letters or digits</span></span>

<span data-ttu-id="2102f-2430">每個國家/地區的格式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="2102f-2430">The format for each country is slightly different.</span></span> <span data-ttu-id="2102f-2431">IBAN 敏感資訊類型涵蓋下列60個國家/地區:</span><span class="sxs-lookup"><span data-stu-id="2102f-2431">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="2102f-2432">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、深色、do、ee、es、fi、fo、fr、gb、kz、gi、、、、、、、、mr、mt、nl-nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="2102f-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2433">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2433">Checksum</span></span>

<span data-ttu-id="2102f-2434">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2435">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2435">Definition</span></span>

<span data-ttu-id="2102f-2436">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2437">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2438">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2439">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2439">Keywords</span></span>

<span data-ttu-id="2102f-2440">無</span><span class="sxs-lookup"><span data-stu-id="2102f-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="2102f-2441">IP 位址</span><span class="sxs-lookup"><span data-stu-id="2102f-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2442">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="2102f-2443">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="2102f-2443">IPv4:</span></span>
<span data-ttu-id="2102f-2444">用來格式化 (句點) 及未格式化 (無期間) 版本的 IPv4 位址的複雜模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="2102f-2445">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="2102f-2445">IPv6:</span></span>
<span data-ttu-id="2102f-2446">格式化 IPv6 號碼 (包括冒號) 的複雜模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2447">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2448">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2448">Checksum</span></span>

<span data-ttu-id="2102f-2449">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2450">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2450">Definition</span></span>

<span data-ttu-id="2102f-2451">對於 IPv6, 如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2452">正則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2453">找不到 Keyword_ipaddress 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="2102f-2454">對於 IPv4, 如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 95%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2455">正則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2456">找到 Keyword_ipaddress 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="2102f-2457">對於 IPv6, 如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 95%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2458">正則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2459">找不到 Keyword_ipaddress 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="2102f-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="2102f-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="2102f-2462">IP (此關鍵字區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="2102f-2463">ip 位址</span><span class="sxs-lookup"><span data-stu-id="2102f-2463">ip address</span></span> 
- <span data-ttu-id="2102f-2464">ip 位址</span><span class="sxs-lookup"><span data-stu-id="2102f-2464">ip addresses</span></span>
- <span data-ttu-id="2102f-2465">網際網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="2102f-2465">internet protocol</span></span>
- <span data-ttu-id="2102f-2466">IP-כתובתה</span><span class="sxs-lookup"><span data-stu-id="2102f-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="2102f-2467">國際分類的疾病 (ICD-10-釐米)</span><span class="sxs-lookup"><span data-stu-id="2102f-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2468">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2468">Format</span></span>

<span data-ttu-id="2102f-2469">Dictionary</span><span class="sxs-lookup"><span data-stu-id="2102f-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2470">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2470">Pattern</span></span>

<span data-ttu-id="2102f-2471">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2472">Checksum</span></span>

<span data-ttu-id="2102f-2473">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2474">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2474">Definition</span></span>

<span data-ttu-id="2102f-2475">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2476">找到 Dictionary_icd_10_cm 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="2102f-2477">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2477">Keywords</span></span>

<span data-ttu-id="2102f-2478">Dictionary_icd_10_cm 關鍵字字典中的任何字詞, 以[疾病的國際分類、第十個修訂版、臨床修改 (icd-10 釐米)](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。</span><span class="sxs-lookup"><span data-stu-id="2102f-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="2102f-2479">此類型只會查看字詞, 而非保險碼。</span><span class="sxs-lookup"><span data-stu-id="2102f-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="2102f-2480">疾病的國際分類 (ICD-9 釐米)</span><span class="sxs-lookup"><span data-stu-id="2102f-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2481">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2481">Format</span></span>

<span data-ttu-id="2102f-2482">Dictionary</span><span class="sxs-lookup"><span data-stu-id="2102f-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2483">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2483">Pattern</span></span>

<span data-ttu-id="2102f-2484">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2485">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2485">Checksum</span></span>

<span data-ttu-id="2102f-2486">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2487">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2487">Definition</span></span>

<span data-ttu-id="2102f-2488">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2489">找到 Dictionary_icd_9_cm 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2490">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2490">Keywords</span></span>

<span data-ttu-id="2102f-2491">Dictionary_icd_9_cm 關鍵字字典中的任何字詞, 以[疾病的國際分類、第九個修訂版、臨床修改 (icd-9 釐米)](https://go.microsoft.com/fwlink/?linkid=852605)為基礎。</span><span class="sxs-lookup"><span data-stu-id="2102f-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="2102f-2492">此類型只會查看字詞, 而非保險碼。</span><span class="sxs-lookup"><span data-stu-id="2102f-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="2102f-2493">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2494">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2494">Format</span></span>

<span data-ttu-id="2102f-2495">舊格式 (直到31十二月 2012):</span><span class="sxs-lookup"><span data-stu-id="2102f-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="2102f-2496">七位數後尾隨1-2 個字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="2102f-2497">新的格式 (1 Jan 2013 和 after):</span><span class="sxs-lookup"><span data-stu-id="2102f-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="2102f-2498">七位數後尾隨兩個字母</span><span class="sxs-lookup"><span data-stu-id="2102f-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2499">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2499">Pattern</span></span>

<span data-ttu-id="2102f-2500">舊格式 (直到31十二月 2012):</span><span class="sxs-lookup"><span data-stu-id="2102f-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="2102f-2501">七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2501">Seven digits</span></span> 
- <span data-ttu-id="2102f-2502">1-2 個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="2102f-2503">新的格式 (1 Jan 2013 和 after):</span><span class="sxs-lookup"><span data-stu-id="2102f-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="2102f-2504">七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2504">Seven digits</span></span> 
- <span data-ttu-id="2102f-2505">一個字母 (不區分大小寫), 這是一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="2102f-2506">字母 "A" 或 "H" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2507">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2507">Checksum</span></span>

<span data-ttu-id="2102f-2508">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2509">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2509">Definition</span></span>

<span data-ttu-id="2102f-2510">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2511">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2512">下列其中一項為真:</span><span class="sxs-lookup"><span data-stu-id="2102f-2512">One of the following is true:</span></span>
    - <span data-ttu-id="2102f-2513">找到 Keyword_ireland_pps 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="2102f-2514">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2102f-2515">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2515">The checksum passes.</span></span>

<span data-ttu-id="2102f-2516">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2517">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2518">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2519">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="2102f-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="2102f-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="2102f-2521">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="2102f-2522">PPS 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2522">PPS Number</span></span> 
- <span data-ttu-id="2102f-2523">PPS Num</span><span class="sxs-lookup"><span data-stu-id="2102f-2523">PPS Num</span></span> 
- <span data-ttu-id="2102f-2524">PPS No。</span><span class="sxs-lookup"><span data-stu-id="2102f-2524">PPS No.</span></span> 
- <span data-ttu-id="2102f-2525">PPS-2</span><span class="sxs-lookup"><span data-stu-id="2102f-2525">PPS #</span></span> 
- <span data-ttu-id="2102f-2526">PPS-2</span><span class="sxs-lookup"><span data-stu-id="2102f-2526">PPS#</span></span> 
- <span data-ttu-id="2102f-2527">PPSN</span><span class="sxs-lookup"><span data-stu-id="2102f-2527">PPSN</span></span> 
- <span data-ttu-id="2102f-2528">公用服務卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-2528">Public Services Card</span></span> 
- <span data-ttu-id="2102f-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="2102f-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="2102f-2530">Uimh.</span><span class="sxs-lookup"><span data-stu-id="2102f-2530">Uimh.</span></span> <span data-ttu-id="2102f-2531">節電</span><span class="sxs-lookup"><span data-stu-id="2102f-2531">PSP</span></span> 
- <span data-ttu-id="2102f-2532">節電</span><span class="sxs-lookup"><span data-stu-id="2102f-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="2102f-2533">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2534">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2534">Format</span></span>

<span data-ttu-id="2102f-2535">13位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2536">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2536">Pattern</span></span>

<span data-ttu-id="2102f-2537">格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-2537">Formatted:</span></span>
- <span data-ttu-id="2102f-2538">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2538">Two digits</span></span> 
- <span data-ttu-id="2102f-2539">虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2539">A dash</span></span> 
- <span data-ttu-id="2102f-2540">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2540">Three digits</span></span> 
- <span data-ttu-id="2102f-2541">虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-2541">A dash</span></span> 
- <span data-ttu-id="2102f-2542">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2542">Eight digits</span></span>

<span data-ttu-id="2102f-2543">非</span><span class="sxs-lookup"><span data-stu-id="2102f-2543">Unformatted:</span></span>
- <span data-ttu-id="2102f-2544">13個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2545">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2545">Checksum</span></span>

<span data-ttu-id="2102f-2546">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2547">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2547">Definition</span></span>

<span data-ttu-id="2102f-2548">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2549">正則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2550">找到 Keyword_israel_bank_account_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2551">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="2102f-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="2102f-2553">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2553">Bank Account Number</span></span> 
- <span data-ttu-id="2102f-2554">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-2554">Bank Account</span></span> 
- <span data-ttu-id="2102f-2555">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2555">Account Number</span></span> 
- <span data-ttu-id="2102f-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="2102f-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="2102f-2557">以色列國家 ID</span><span class="sxs-lookup"><span data-stu-id="2102f-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2558">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2558">Format</span></span>

<span data-ttu-id="2102f-2559">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2560">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2560">Pattern</span></span>

<span data-ttu-id="2102f-2561">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2562">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2562">Checksum</span></span>

<span data-ttu-id="2102f-2563">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2564">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2564">Definition</span></span>

<span data-ttu-id="2102f-2565">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2566">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2567">找到 Keyword_Israel_National_ID 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="2102f-2568">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2569">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="2102f-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="2102f-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="2102f-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="2102f-2571">מספר זהות</span></span> 
- <span data-ttu-id="2102f-2572">民族識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="2102f-2573">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2574">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2574">Format</span></span>

<span data-ttu-id="2102f-2575">10個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="2102f-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2576">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2576">Pattern</span></span>

- <span data-ttu-id="2102f-2577">10個字母和數位的組合:</span><span class="sxs-lookup"><span data-stu-id="2102f-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="2102f-2578">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-2579">字母 "A" 或 "V" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-2580">七個字母 (不區分大小寫)、數位或底線字元</span><span class="sxs-lookup"><span data-stu-id="2102f-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="2102f-2581">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2582">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2582">Checksum</span></span>

<span data-ttu-id="2102f-2583">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2584">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2584">Definition</span></span>

<span data-ttu-id="2102f-2585">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2586">正則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2587">找到 Keyword_italy_drivers_license_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2588">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="2102f-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="2102f-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="2102f-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="2102f-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="2102f-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="2102f-2592">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2593">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2593">Format</span></span>

<span data-ttu-id="2102f-2594">七個或八個數字</span><span class="sxs-lookup"><span data-stu-id="2102f-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2595">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2595">Pattern</span></span>

<span data-ttu-id="2102f-2596">銀行帳戶號碼:</span><span class="sxs-lookup"><span data-stu-id="2102f-2596">Bank account number:</span></span>
- <span data-ttu-id="2102f-2597">七個或八個數字</span><span class="sxs-lookup"><span data-stu-id="2102f-2597">Seven or eight digits</span></span>
- <span data-ttu-id="2102f-2598">銀行帳戶分支碼:</span><span class="sxs-lookup"><span data-stu-id="2102f-2598">Bank account branch code:</span></span>
- <span data-ttu-id="2102f-2599">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2599">Four digits</span></span> 
- <span data-ttu-id="2102f-2600">一個空格或連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="2102f-2601">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2601">Three digits</span></span>

<span data-ttu-id="2102f-2602">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2602">Checksum</span></span>

<span data-ttu-id="2102f-2603">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2604">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2604">Definition</span></span>

<span data-ttu-id="2102f-2605">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2606">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2607">找到 Keyword_jp_bank_account 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="2102f-2608">下列其中一項為真:</span><span class="sxs-lookup"><span data-stu-id="2102f-2608">One of the following is true:</span></span>
- <span data-ttu-id="2102f-2609">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2610">找到 Keyword_jp_bank_branch_code 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="2102f-2611">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2612">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2613">找到 Keyword_jp_bank_account 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2614">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="2102f-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="2102f-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="2102f-2616">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2616">Checking Account Number</span></span> 
- <span data-ttu-id="2102f-2617">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-2617">Checking Account</span></span> 
- <span data-ttu-id="2102f-2618">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2618">Checking Account #</span></span> 
- <span data-ttu-id="2102f-2619">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="2102f-2620">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2620">Checking Acct #</span></span> 
- <span data-ttu-id="2102f-2621">檢查帳戶是否為 [否]。</span><span class="sxs-lookup"><span data-stu-id="2102f-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="2102f-2622">檢查帳戶否。</span><span class="sxs-lookup"><span data-stu-id="2102f-2622">Checking Account No.</span></span> 
- <span data-ttu-id="2102f-2623">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2623">Bank Account Number</span></span> 
- <span data-ttu-id="2102f-2624">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-2624">Bank Account</span></span> 
- <span data-ttu-id="2102f-2625">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2625">Bank Account #</span></span> 
- <span data-ttu-id="2102f-2626">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="2102f-2627">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2627">Bank Acct #</span></span> 
- <span data-ttu-id="2102f-2628">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="2102f-2629">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2629">Bank Account No.</span></span> 
- <span data-ttu-id="2102f-2630">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2630">Savings Account Number</span></span> 
- <span data-ttu-id="2102f-2631">儲蓄帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-2631">Savings Account</span></span> 
- <span data-ttu-id="2102f-2632">儲蓄帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2632">Savings Account #</span></span> 
- <span data-ttu-id="2102f-2633">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="2102f-2634">儲蓄帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2634">Savings Acct #</span></span> 
- <span data-ttu-id="2102f-2635">儲蓄帳戶否。</span><span class="sxs-lookup"><span data-stu-id="2102f-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="2102f-2636">儲蓄帳戶編號。</span><span class="sxs-lookup"><span data-stu-id="2102f-2636">Savings Account No.</span></span> 
- <span data-ttu-id="2102f-2637">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2637">Debit Account Number</span></span> 
- <span data-ttu-id="2102f-2638">借方科目</span><span class="sxs-lookup"><span data-stu-id="2102f-2638">Debit Account</span></span> 
- <span data-ttu-id="2102f-2639">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2639">Debit Account #</span></span> 
- <span data-ttu-id="2102f-2640">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="2102f-2641">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2641">Debit Acct #</span></span> 
- <span data-ttu-id="2102f-2642">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="2102f-2643">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2643">Debit Account No.</span></span> 
- <span data-ttu-id="2102f-2644">口座番號を當座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="2102f-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="2102f-2645">#アカウントの確認、勘定番號の確認</span><span class="sxs-lookup"><span data-stu-id="2102f-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="2102f-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="2102f-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="2102f-2647">勘定番號の確認</span><span class="sxs-lookup"><span data-stu-id="2102f-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="2102f-2648">口座番號の確認</span><span class="sxs-lookup"><span data-stu-id="2102f-2648">口座番号の確認</span></span> 
- <span data-ttu-id="2102f-2649">銀行口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2649">銀行口座番号</span></span> 
- <span data-ttu-id="2102f-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="2102f-2650">銀行口座</span></span> 
- <span data-ttu-id="2102f-2651">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2651">銀行口座＃</span></span> 
- <span data-ttu-id="2102f-2652">銀行の勘定番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="2102f-2653">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="2102f-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="2102f-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="2102f-2655">銀行口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2655">銀行口座番号</span></span>
- <span data-ttu-id="2102f-2656">普通預金口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="2102f-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="2102f-2657">預金口座</span></span> 
- <span data-ttu-id="2102f-2658">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="2102f-2659">貯蓄勘定の數</span><span class="sxs-lookup"><span data-stu-id="2102f-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="2102f-2660">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="2102f-2661">貯蓄勘定番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="2102f-2662">普通預金口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="2102f-2663">引き落とし口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="2102f-2664">口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2664">口座番号</span></span> 
- <span data-ttu-id="2102f-2665">口座番號＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2665">口座番号＃</span></span> 
- <span data-ttu-id="2102f-2666">デビットのacct番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="2102f-2667">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="2102f-2668">デビットACCTの番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="2102f-2669">デビット口座番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="2102f-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="2102f-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="2102f-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="2102f-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="2102f-2672">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2673">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2673">Format</span></span>

<span data-ttu-id="2102f-2674">12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2675">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2675">Pattern</span></span>

<span data-ttu-id="2102f-2676">12個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2677">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2677">Checksum</span></span>

<span data-ttu-id="2102f-2678">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2679">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2679">Definition</span></span>

<span data-ttu-id="2102f-2680">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2681">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2682">找到 Keyword_jp_drivers_license_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2683">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="2102f-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="2102f-2685">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-2685">dl#</span></span> 
- <span data-ttu-id="2102f-2686">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-2686">DL＃</span></span> 
- <span data-ttu-id="2102f-2687">dls</span><span class="sxs-lookup"><span data-stu-id="2102f-2687">dls#</span></span> 
- <span data-ttu-id="2102f-2688">DLS</span><span class="sxs-lookup"><span data-stu-id="2102f-2688">DLS＃</span></span> 
- <span data-ttu-id="2102f-2689">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2689">driver license</span></span> 
- <span data-ttu-id="2102f-2690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2690">driver licenses</span></span> 
- <span data-ttu-id="2102f-2691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2691">drivers license</span></span> 
- <span data-ttu-id="2102f-2692">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-2692">driver's license</span></span> 
- <span data-ttu-id="2102f-2693">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-2693">drivers licenses</span></span> 
- <span data-ttu-id="2102f-2694">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-2694">driver's licenses</span></span> 
- <span data-ttu-id="2102f-2695">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2695">driving licence</span></span> 
- <span data-ttu-id="2102f-2696">許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2696">lic#</span></span> 
- <span data-ttu-id="2102f-2697">許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-2697">LIC＃</span></span> 
- <span data-ttu-id="2102f-2698">lics#</span><span class="sxs-lookup"><span data-stu-id="2102f-2698">lics#</span></span> 
- <span data-ttu-id="2102f-2699">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2699">state id</span></span> 
- <span data-ttu-id="2102f-2700">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2700">state identification</span></span> 
- <span data-ttu-id="2102f-2701">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2701">state identification number</span></span> 
- <span data-ttu-id="2102f-2702">低所得國＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2702">低所得国＃</span></span> 
- <span data-ttu-id="2102f-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="2102f-2703">免許証</span></span> 
- <span data-ttu-id="2102f-2704">狀態ID</span><span class="sxs-lookup"><span data-stu-id="2102f-2704">状態ID</span></span>
- <span data-ttu-id="2102f-2705">狀態の識別</span><span class="sxs-lookup"><span data-stu-id="2102f-2705">状態の識別</span></span> 
- <span data-ttu-id="2102f-2706">狀態の識別番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2706">状態の識別番号</span></span> 
- <span data-ttu-id="2102f-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="2102f-2707">運転免許</span></span> 
- <span data-ttu-id="2102f-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="2102f-2708">運転免許証</span></span> 
- <span data-ttu-id="2102f-2709">運転免許証番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="2102f-2710">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2711">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2711">Format</span></span>

<span data-ttu-id="2102f-2712">兩個字母后尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2713">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2713">Pattern</span></span>

<span data-ttu-id="2102f-2714">兩個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2715">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2715">Checksum</span></span>

<span data-ttu-id="2102f-2716">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2717">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2717">Definition</span></span>

<span data-ttu-id="2102f-2718">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2719">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2720">找到 Keyword_jp_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2721">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="2102f-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="2102f-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="2102f-2723">パスポート</span></span> 
- <span data-ttu-id="2102f-2724">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2724">パスポート番号</span></span> 
- <span data-ttu-id="2102f-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2102f-2725">パスポートのNum</span></span> 
- <span data-ttu-id="2102f-2726">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2102f-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="2102f-2727">日本居民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2728">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2728">Format</span></span>

<span data-ttu-id="2102f-2729">11位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2730">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2730">Pattern</span></span>

<span data-ttu-id="2102f-2731">11個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2732">Checksum</span></span>

<span data-ttu-id="2102f-2733">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2734">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2734">Definition</span></span>

<span data-ttu-id="2102f-2735">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2736">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2737">找到 Keyword_jp_resident_registration_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="2102f-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="2102f-2740">居民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2740">Resident Registration Number</span></span>
- <span data-ttu-id="2102f-2741">居民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2741">Resident Register Number</span></span> 
- <span data-ttu-id="2102f-2742">居民基本登錄號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="2102f-2743">居民註冊編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="2102f-2744">居民註冊編號。</span><span class="sxs-lookup"><span data-stu-id="2102f-2744">Resident Register No.</span></span> 
- <span data-ttu-id="2102f-2745">派駐人員基本登錄編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="2102f-2746">基本駐留寄存器否。</span><span class="sxs-lookup"><span data-stu-id="2102f-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="2102f-2747">住民登録番號、登録番號をレジデント</span><span class="sxs-lookup"><span data-stu-id="2102f-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="2102f-2748">住民基本登録番號、登録番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="2102f-2749">住民基本レジストリ番號を常駐</span><span class="sxs-lookup"><span data-stu-id="2102f-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="2102f-2750">登録番號を常駐住民基本台帳登録番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="2102f-2751">日本社交保險號碼 (SIN)</span><span class="sxs-lookup"><span data-stu-id="2102f-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2752">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2752">Format</span></span>

<span data-ttu-id="2102f-2753">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2754">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2754">Pattern</span></span>

<span data-ttu-id="2102f-2755">7-12 位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2755">7-12 digits:</span></span>
- <span data-ttu-id="2102f-2756">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2756">Four digits</span></span> 
- <span data-ttu-id="2102f-2757">連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="2102f-2758">六位數或</span><span class="sxs-lookup"><span data-stu-id="2102f-2758">Six digits OR</span></span>
- <span data-ttu-id="2102f-2759">7-12 連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2760">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2760">Checksum</span></span>

<span data-ttu-id="2102f-2761">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2762">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2762">Definition</span></span>

<span data-ttu-id="2102f-2763">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2764">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2765">找到 Keyword_jp_sin 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="2102f-2766">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2767">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2768">找到 Keyword_jp_sin 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2769">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="2102f-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="2102f-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="2102f-2771">社交保險</span><span class="sxs-lookup"><span data-stu-id="2102f-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="2102f-2772">社交保險號</span><span class="sxs-lookup"><span data-stu-id="2102f-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="2102f-2773">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="2102f-2774">社會保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="2102f-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="2102f-2775">社會保険番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="2102f-2776">日式住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2777">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2777">Format</span></span>

<span data-ttu-id="2102f-2778">12個字母和數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2779">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2779">Pattern</span></span>

<span data-ttu-id="2102f-2780">12個字母和數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-2780">12 letters and digits:</span></span>
- <span data-ttu-id="2102f-2781">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="2102f-2782">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2782">Eight digits</span></span> 
- <span data-ttu-id="2102f-2783">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2784">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2784">Checksum</span></span>

<span data-ttu-id="2102f-2785">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2786">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2786">Definition</span></span>

<span data-ttu-id="2102f-2787">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2788">正則運算式 Regex_jp_residence_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2789">找到 Keyword_jp_residence_card_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2790">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="2102f-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="2102f-2792">居住卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2792">Residence card number</span></span>
- <span data-ttu-id="2102f-2793">不含住宅卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2793">Residence card no</span></span>
- <span data-ttu-id="2102f-2794">居住卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-2794">Residence card #</span></span>
- <span data-ttu-id="2102f-2795">在留カード番號</span><span class="sxs-lookup"><span data-stu-id="2102f-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="2102f-2796">馬來西亞識別碼卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2797">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2797">Format</span></span>

<span data-ttu-id="2102f-2798">12位數包含選用的連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2799">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2799">Pattern</span></span>

<span data-ttu-id="2102f-2800">12位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2800">12 digits:</span></span>
- <span data-ttu-id="2102f-2801">YYMMDD 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2102f-2802">一條虛線 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-2802">A dash (optional)</span></span> 
- <span data-ttu-id="2102f-2803">兩個字母的出生日期代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="2102f-2804">一條虛線 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-2804">A dash (optional)</span></span> 
- <span data-ttu-id="2102f-2805">三個亂數字</span><span class="sxs-lookup"><span data-stu-id="2102f-2805">Three random digits</span></span> 
- <span data-ttu-id="2102f-2806">一位數的性別代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2807">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2807">Checksum</span></span>

<span data-ttu-id="2102f-2808">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2809">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2809">Definition</span></span>

<span data-ttu-id="2102f-2810">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2811">正則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2812">找到 Keyword_malaysia_id_card_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2813">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="2102f-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="2102f-2815">數位應用程式卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2815">digital application card</span></span>
- <span data-ttu-id="2102f-2816">i/c</span><span class="sxs-lookup"><span data-stu-id="2102f-2816">i/c</span></span>
- <span data-ttu-id="2102f-2817">i/c 否</span><span class="sxs-lookup"><span data-stu-id="2102f-2817">i/c no</span></span>
- <span data-ttu-id="2102f-2818">內部</span><span class="sxs-lookup"><span data-stu-id="2102f-2818">ic</span></span>
- <span data-ttu-id="2102f-2819">內部公司編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2819">ic no</span></span>
- <span data-ttu-id="2102f-2820">id 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2820">id card</span></span>
- <span data-ttu-id="2102f-2821">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2821">identification Card</span></span>
- <span data-ttu-id="2102f-2822">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2822">identity card</span></span>
- <span data-ttu-id="2102f-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="2102f-2823">k/p</span></span>
- <span data-ttu-id="2102f-2824">k/p 否</span><span class="sxs-lookup"><span data-stu-id="2102f-2824">k/p no</span></span>
- <span data-ttu-id="2102f-2825">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="2102f-2825">kad akuan diri</span></span>
- <span data-ttu-id="2102f-2826">kad aplikasi 數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="2102f-2827">kad pengenalan 馬來西亞</span><span class="sxs-lookup"><span data-stu-id="2102f-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="2102f-2828">kp</span><span class="sxs-lookup"><span data-stu-id="2102f-2828">kp</span></span>
- <span data-ttu-id="2102f-2829">kp 否</span><span class="sxs-lookup"><span data-stu-id="2102f-2829">kp no</span></span>
- <span data-ttu-id="2102f-2830">mykad</span><span class="sxs-lookup"><span data-stu-id="2102f-2830">mykad</span></span>
- <span data-ttu-id="2102f-2831">mykas</span><span class="sxs-lookup"><span data-stu-id="2102f-2831">mykas</span></span>
- <span data-ttu-id="2102f-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="2102f-2832">mykid</span></span>
- <span data-ttu-id="2102f-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="2102f-2833">mypr</span></span>
- <span data-ttu-id="2102f-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="2102f-2834">mytentera</span></span>
- <span data-ttu-id="2102f-2835">馬來西亞身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-2835">malaysia identity card</span></span>
- <span data-ttu-id="2102f-2836">馬來西亞身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-2836">malaysian identity card</span></span>
- <span data-ttu-id="2102f-2837">nric</span><span class="sxs-lookup"><span data-stu-id="2102f-2837">nric</span></span>
- <span data-ttu-id="2102f-2838">個人身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="2102f-2839">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2840">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2840">Format</span></span>

<span data-ttu-id="2102f-2841">包含選擇性空格的8-9 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2842">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2842">Pattern</span></span>

<span data-ttu-id="2102f-2843">8-9 位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2843">8-9 digits:</span></span>
- <span data-ttu-id="2102f-2844">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2844">Three digits</span></span> 
- <span data-ttu-id="2102f-2845">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-2845">A space (optional)</span></span> 
- <span data-ttu-id="2102f-2846">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2846">Three digits</span></span> 
- <span data-ttu-id="2102f-2847">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-2847">A space (optional)</span></span> 
- <span data-ttu-id="2102f-2848">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2849">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2849">Checksum</span></span>

<span data-ttu-id="2102f-2850">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2851">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2851">Definition</span></span>

<span data-ttu-id="2102f-2852">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2853">函數 Func_netherlands_bsn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2854">找到 Keyword_netherlands_bsn 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="2102f-2855">函數 Func_eu_date2 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="2102f-2856">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2857">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="2102f-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="2102f-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="2102f-2859">公民服務號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2859">Citizen service number</span></span> 
- <span data-ttu-id="2102f-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="2102f-2860">BSN</span></span> 
- <span data-ttu-id="2102f-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="2102f-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2862">Sofinummer</span></span> 
- <span data-ttu-id="2102f-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="2102f-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="2102f-2865">紐西蘭的健康情況號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2866">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2866">Format</span></span>

<span data-ttu-id="2102f-2867">三個字母、一個空格 (選用) 及四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2868">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2868">Pattern</span></span>

<span data-ttu-id="2102f-2869">三個字母 (不區分大小寫) 一個空格 (選用) 四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2870">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2870">Checksum</span></span>

<span data-ttu-id="2102f-2871">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2872">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2872">Definition</span></span>

<span data-ttu-id="2102f-2873">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2874">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2875">找到 Keyword_nz_terms 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="2102f-2876">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2876">The checksum passes.</span></span>

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

<span data-ttu-id="2102f-2877">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2877">Keywords</span></span>

<span data-ttu-id="2102f-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="2102f-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="2102f-2879">NHI</span><span class="sxs-lookup"><span data-stu-id="2102f-2879">NHI</span></span> 
- <span data-ttu-id="2102f-2880">JPRatingExplicitAllowed</span><span class="sxs-lookup"><span data-stu-id="2102f-2880">New Zealand</span></span> 
- <span data-ttu-id="2102f-2881">健康情況</span><span class="sxs-lookup"><span data-stu-id="2102f-2881">Health</span></span> 
- <span data-ttu-id="2102f-2882">處理</span><span class="sxs-lookup"><span data-stu-id="2102f-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="2102f-2883">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2884">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2884">Format</span></span>

<span data-ttu-id="2102f-2885">11位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2886">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2886">Pattern</span></span>

<span data-ttu-id="2102f-2887">11位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2887">11 digits:</span></span>
- <span data-ttu-id="2102f-2888">DDMMYY 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2102f-2889">三位數個人號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="2102f-2890">兩個檢查數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2891">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2891">Checksum</span></span>

<span data-ttu-id="2102f-2892">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2893">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2893">Definition</span></span>

<span data-ttu-id="2102f-2894">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2895">函數 Func_norway_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2896">找到 Keyword_norway_id_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="2102f-2897">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2897">The checksum passes.</span></span>
- <span data-ttu-id="2102f-2898">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2899">函數 Func_norway_id_numbe 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2900">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2901">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="2102f-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="2102f-2903">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2903">Personal identification number</span></span>
- <span data-ttu-id="2102f-2904">挪威文識別碼編號</span><span class="sxs-lookup"><span data-stu-id="2102f-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="2102f-2905">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2905">ID Number</span></span>
- <span data-ttu-id="2102f-2906">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2906">Identification</span></span>
- <span data-ttu-id="2102f-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2907">Personnummer</span></span>
- <span data-ttu-id="2102f-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="2102f-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="2102f-2909">菲律賓統一式多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2910">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2910">Format</span></span>

<span data-ttu-id="2102f-2911">以連字號隔開的12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2912">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2912">Pattern</span></span>

<span data-ttu-id="2102f-2913">12位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-2913">12 digits:</span></span>
- <span data-ttu-id="2102f-2914">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2914">Four digits</span></span> 
- <span data-ttu-id="2102f-2915">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-2915">A hyphen</span></span> 
- <span data-ttu-id="2102f-2916">七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2916">Seven digits</span></span> 
- <span data-ttu-id="2102f-2917">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-2917">A hyphen</span></span> 
- <span data-ttu-id="2102f-2918">一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2919">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2919">Checksum</span></span>

<span data-ttu-id="2102f-2920">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2921">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2921">Definition</span></span>

<span data-ttu-id="2102f-2922">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2923">正則運算式 Regex_philippines_unified_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2924">找到 Keyword_philippines_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2925">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="2102f-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="2102f-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="2102f-2927">統一式多用途識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="2102f-2928">UMID</span><span class="sxs-lookup"><span data-stu-id="2102f-2928">UMID</span></span> 
- <span data-ttu-id="2102f-2929">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2929">Identity Card</span></span> 
- <span data-ttu-id="2102f-2930">Pinag-isang 多 Layunin 識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="2102f-2931">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="2102f-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2932">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2932">Format</span></span>

<span data-ttu-id="2102f-2933">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2934">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2934">Pattern</span></span>

<span data-ttu-id="2102f-2935">三個字母 (不區分大小寫) 後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2936">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2936">Checksum</span></span>

<span data-ttu-id="2102f-2937">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2938">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2938">Definition</span></span>

<span data-ttu-id="2102f-2939">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%: 函數 Func_polish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="2102f-2940">找到 Keyword_polish_national_id_passport_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="2102f-2941">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="2102f-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="2102f-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="2102f-2944">Dowód osobisty</span></span>
- <span data-ttu-id="2102f-2945">轉寄 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2102f-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="2102f-2946">Nazwa i 轉寄 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2102f-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="2102f-2947">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2102f-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="2102f-2948">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="2102f-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="2102f-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="2102f-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="2102f-2950">dow.</span><span class="sxs-lookup"><span data-stu-id="2102f-2950">dow.</span></span> <span data-ttu-id="2102f-2951">安裝的作業系統.</span><span class="sxs-lookup"><span data-stu-id="2102f-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="2102f-2952">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="2102f-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2953">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2953">Format</span></span>

<span data-ttu-id="2102f-2954">11位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2955">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2955">Pattern</span></span>

<span data-ttu-id="2102f-2956">11個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2957">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2957">Checksum</span></span>

<span data-ttu-id="2102f-2958">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2959">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2959">Definition</span></span>

<span data-ttu-id="2102f-2960">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2961">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2962">找到 Keyword_pesel_identification_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="2102f-2963">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2964">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="2102f-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="2102f-2966">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="2102f-2966">Nr PESEL</span></span>
- <span data-ttu-id="2102f-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="2102f-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="2102f-2968">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="2102f-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2969">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2969">Format</span></span>

<span data-ttu-id="2102f-2970">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2971">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2971">Pattern</span></span>

<span data-ttu-id="2102f-2972">兩個字母 (不區分大小寫) 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2973">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2973">Checksum</span></span>

<span data-ttu-id="2102f-2974">是</span><span class="sxs-lookup"><span data-stu-id="2102f-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2975">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2975">Definition</span></span>

<span data-ttu-id="2102f-2976">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2977">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2978">找到 Keyword_polish_national_id_passport_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="2102f-2979">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-2980">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="2102f-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="2102f-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="2102f-2982">轉寄 paszportu</span><span class="sxs-lookup"><span data-stu-id="2102f-2982">Numer paszportu</span></span>
- <span data-ttu-id="2102f-2983">Nr.</span><span class="sxs-lookup"><span data-stu-id="2102f-2983">Nr.</span></span> <span data-ttu-id="2102f-2984">Paszportu</span><span class="sxs-lookup"><span data-stu-id="2102f-2984">Paszportu</span></span>
- <span data-ttu-id="2102f-2985">Paszport</span><span class="sxs-lookup"><span data-stu-id="2102f-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="2102f-2986">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-2987">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-2987">Format</span></span>

<span data-ttu-id="2102f-2988">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-2989">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-2989">Pattern</span></span>

<span data-ttu-id="2102f-2990">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-2991">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-2991">Checksum</span></span>

<span data-ttu-id="2102f-2992">否</span><span class="sxs-lookup"><span data-stu-id="2102f-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-2993">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-2993">Definition</span></span>

<span data-ttu-id="2102f-2994">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-2995">正則運算式 Regex_portugal_citizen_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-2996">找到 Keyword_portugal_citizen_card 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-2997">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="2102f-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="2102f-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="2102f-2999">公民卡片</span><span class="sxs-lookup"><span data-stu-id="2102f-2999">Citizen Card</span></span>
- <span data-ttu-id="2102f-3000">國際身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3000">National ID Card</span></span>
- <span data-ttu-id="2102f-3001">副本</span><span class="sxs-lookup"><span data-stu-id="2102f-3001">CC</span></span>
- <span data-ttu-id="2102f-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="2102f-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="2102f-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="2102f-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="2102f-3004">沙烏地阿拉伯國 ID</span><span class="sxs-lookup"><span data-stu-id="2102f-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3005">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3005">Format</span></span>

<span data-ttu-id="2102f-3006">10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3007">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3007">Pattern</span></span>

<span data-ttu-id="2102f-3008">10個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3009">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3009">Checksum</span></span>

<span data-ttu-id="2102f-3010">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3011">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3011">Definition</span></span>

<span data-ttu-id="2102f-3012">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3013">正則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3014">找到 Keyword_saudi_arabia_national_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3015">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="2102f-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="2102f-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="2102f-3017">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3017">Identification Card</span></span> 
- <span data-ttu-id="2102f-3018">我的卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3018">I card number</span></span> 
- <span data-ttu-id="2102f-3019">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3019">ID number</span></span> 
- <span data-ttu-id="2102f-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="2102f-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="2102f-3021">新加坡國家註冊身分識別卡 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3022">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3022">Format</span></span>

<span data-ttu-id="2102f-3023">九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3024">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3024">Pattern</span></span>

- <span data-ttu-id="2102f-3025">九個字母和數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="2102f-3026">字母 "F"、"G"、"S" 或 "T" (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-3027">七位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3027">Seven digits</span></span> 
- <span data-ttu-id="2102f-3028">字母檢查數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3029">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3029">Checksum</span></span>

<span data-ttu-id="2102f-3030">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3031">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3031">Definition</span></span>

<span data-ttu-id="2102f-3032">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3033">正則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3034">找到 Keyword_singapore_nric 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="2102f-3035">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3035">The checksum passes.</span></span>

<span data-ttu-id="2102f-3036">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3037">正則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3038">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3039">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="2102f-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="2102f-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="2102f-3041">國家註冊身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="2102f-3042">身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3042">Identity Card Number</span></span> 
- <span data-ttu-id="2102f-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="2102f-3043">NRIC</span></span> 
- <span data-ttu-id="2102f-3044">內部</span><span class="sxs-lookup"><span data-stu-id="2102f-3044">IC</span></span> 
- <span data-ttu-id="2102f-3045">外部標識號</span><span class="sxs-lookup"><span data-stu-id="2102f-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="2102f-3046">FIN</span><span class="sxs-lookup"><span data-stu-id="2102f-3046">FIN</span></span> 
- <span data-ttu-id="2102f-3047">身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-3047">身份证</span></span> 
- <span data-ttu-id="2102f-3048">身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="2102f-3049">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3050">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3050">Format</span></span>

<span data-ttu-id="2102f-3051">可能包含空格的13位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3052">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3052">Pattern</span></span>

<span data-ttu-id="2102f-3053">13位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-3053">13 digits:</span></span>
- <span data-ttu-id="2102f-3054">YYMMDD 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2102f-3055">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3055">Four digits</span></span> 
- <span data-ttu-id="2102f-3056">一位數的公民指標</span><span class="sxs-lookup"><span data-stu-id="2102f-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="2102f-3057">數位 "8" 或 "9"</span><span class="sxs-lookup"><span data-stu-id="2102f-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="2102f-3058">一位數為 checksum 的數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3059">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3059">Checksum</span></span>

<span data-ttu-id="2102f-3060">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3061">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3061">Definition</span></span>

<span data-ttu-id="2102f-3062">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3063">函數 Func_south_africa_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3064">找到 Keyword_south_africa_identification_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="2102f-3065">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3066">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="2102f-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="2102f-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="2102f-3068">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3068">Identity card</span></span>
- <span data-ttu-id="2102f-3069">ID</span><span class="sxs-lookup"><span data-stu-id="2102f-3069">ID</span></span>
- <span data-ttu-id="2102f-3070">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="2102f-3071">韓國居民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3072">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3072">Format</span></span>

<span data-ttu-id="2102f-3073">13位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3074">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3074">Pattern</span></span>

<span data-ttu-id="2102f-3075">13位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-3075">13 digits:</span></span>
- <span data-ttu-id="2102f-3076">YYMMDD 格式的六位數, 其為出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2102f-3077">連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3077">A hyphen</span></span> 
- <span data-ttu-id="2102f-3078">由世紀和性別決定的一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="2102f-3079">四位數的出生地區代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="2102f-3080">用來區分先前數位相同之人員的一種數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="2102f-3081">檢查數位。</span><span class="sxs-lookup"><span data-stu-id="2102f-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3082">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3082">Checksum</span></span>

<span data-ttu-id="2102f-3083">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3084">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3084">Definition</span></span>

<span data-ttu-id="2102f-3085">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3086">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3087">找到 Keyword_south_korea_resident_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="2102f-3088">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3088">The checksum passes.</span></span>

<span data-ttu-id="2102f-3089">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3090">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3091">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3092">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="2102f-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="2102f-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="2102f-3094">國際身分識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3094">National ID card</span></span> 
- <span data-ttu-id="2102f-3095">公民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="2102f-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="2102f-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="2102f-3097">RRN</span><span class="sxs-lookup"><span data-stu-id="2102f-3097">RRN</span></span> 
- <span data-ttu-id="2102f-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="2102f-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="2102f-3099">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="2102f-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3100">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3100">Format</span></span>

<span data-ttu-id="2102f-3101">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3102">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3102">Pattern</span></span>

<span data-ttu-id="2102f-3103">11-12 位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-3103">11-12 digits:</span></span>
- <span data-ttu-id="2102f-3104">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3104">Two digits</span></span> 
- <span data-ttu-id="2102f-3105">正斜線 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="2102f-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="2102f-3106">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3106">7-8 digits</span></span> 
- <span data-ttu-id="2102f-3107">正斜線 (選擇性)</span><span class="sxs-lookup"><span data-stu-id="2102f-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="2102f-3108">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3109">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3109">Checksum</span></span>

<span data-ttu-id="2102f-3110">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3111">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3111">Definition</span></span>

<span data-ttu-id="2102f-3112">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3113">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3114">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3115">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3115">Keywords</span></span>

<span data-ttu-id="2102f-3116">無</span><span class="sxs-lookup"><span data-stu-id="2102f-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="2102f-3117">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="2102f-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3118">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3118">Format</span></span>

<span data-ttu-id="2102f-3119">字串 "User Id"、"User ID"、"uid" 或 "UserId", 後面接著下模式所列的字元和字串。</span><span class="sxs-lookup"><span data-stu-id="2102f-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3120">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3120">Pattern</span></span>

- <span data-ttu-id="2102f-3121">字串「使用者識別碼」、「使用者識別碼」、「uid」或「UserId」</span><span class="sxs-lookup"><span data-stu-id="2102f-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="2102f-3122">介於1-200 小寫或大寫的字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="2102f-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2102f-3123">字串 "Password" 或 "pwd", 其中 "pwd" 的前面不是小寫字母</span><span class="sxs-lookup"><span data-stu-id="2102f-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="2102f-3124">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-3124">An equal sign (=)</span></span>
- <span data-ttu-id="2102f-3125">不是貨幣符號 ($) 的任何字元、百分比符號 (%)、大於符號 (>)、符號 (@)、引號 (")、分號 (;)、左大括弧 ([) 或左括弧 ({)</span><span class="sxs-lookup"><span data-stu-id="2102f-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="2102f-3126">任何7-128 個字元的組合, 不是分號 (;)、正斜線 (/) 或引號 (")</span><span class="sxs-lookup"><span data-stu-id="2102f-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="2102f-3127">分號 (;)或引號 (")</span><span class="sxs-lookup"><span data-stu-id="2102f-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3128">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3128">Checksum</span></span>

<span data-ttu-id="2102f-3129">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3130">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3130">Definition</span></span>

<span data-ttu-id="2102f-3131">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3132">正則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3133">找**不**到 CEP_GlobalFilter 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="2102f-3134">正則運算式 CEP_PasswordPlaceHolder 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3135">正則運算式 CEP_CommonExampleKeywords 找**不**到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3136">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="2102f-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="2102f-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="2102f-3138">部分密碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3138">some-password</span></span>
- <span data-ttu-id="2102f-3139">somepassword</span><span class="sxs-lookup"><span data-stu-id="2102f-3139">somepassword</span></span>
- <span data-ttu-id="2102f-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="2102f-3140">secretPassword</span></span>
- <span data-ttu-id="2102f-3141">樣例</span><span class="sxs-lookup"><span data-stu-id="2102f-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="2102f-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="2102f-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="2102f-3143">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-3144">密碼或密碼後接0-2 個空格、等號 (=)、0-2 空間及星號 (\*)--或----------------</span><span class="sxs-lookup"><span data-stu-id="2102f-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="2102f-3145">密碼或密碼, 後面接著:</span><span class="sxs-lookup"><span data-stu-id="2102f-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="2102f-3146">等號 (=)</span><span class="sxs-lookup"><span data-stu-id="2102f-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="2102f-3147">小於符號 (<)</span><span class="sxs-lookup"><span data-stu-id="2102f-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="2102f-3148">由1-200 字元組成的任何組合, 其為大寫或小寫字母、數位、星號 (\*)、連字號 (-)、底線 (_) 或空白字元</span><span class="sxs-lookup"><span data-stu-id="2102f-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="2102f-3149">大於符號 (>)</span><span class="sxs-lookup"><span data-stu-id="2102f-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2102f-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2102f-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2102f-3151">(請注意, 從技術上講, 這個敏感資訊類型會使用正則運算式, 而不是關鍵字清單來識別這些關鍵字。)</span><span class="sxs-lookup"><span data-stu-id="2102f-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2102f-3152">contoso</span><span class="sxs-lookup"><span data-stu-id="2102f-3152">contoso</span></span>
- <span data-ttu-id="2102f-3153">fabrikam</span><span class="sxs-lookup"><span data-stu-id="2102f-3153">fabrikam</span></span>
- <span data-ttu-id="2102f-3154">示例</span><span class="sxs-lookup"><span data-stu-id="2102f-3154">northwind</span></span>
- <span data-ttu-id="2102f-3155">沙箱</span><span class="sxs-lookup"><span data-stu-id="2102f-3155">sandbox</span></span>
- <span data-ttu-id="2102f-3156">onebox</span><span class="sxs-lookup"><span data-stu-id="2102f-3156">onebox</span></span>
- <span data-ttu-id="2102f-3157">發出</span><span class="sxs-lookup"><span data-stu-id="2102f-3157">localhost</span></span>
- <span data-ttu-id="2102f-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2102f-3158">127.0.0.1</span></span>
- <span data-ttu-id="2102f-3159">testacs.</span><span class="sxs-lookup"><span data-stu-id="2102f-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-3160">com</span><span class="sxs-lookup"><span data-stu-id="2102f-3160">com</span></span>
- <span data-ttu-id="2102f-3161">s-int。</span><span class="sxs-lookup"><span data-stu-id="2102f-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2102f-3162">net-library</span><span class="sxs-lookup"><span data-stu-id="2102f-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="2102f-3163">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="2102f-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3164">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3164">Format</span></span>

<span data-ttu-id="2102f-3165">10或12位數和選擇性分隔符號</span><span class="sxs-lookup"><span data-stu-id="2102f-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3166">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3166">Pattern</span></span>

<span data-ttu-id="2102f-3167">10或12位數和選擇性分隔符號:</span><span class="sxs-lookup"><span data-stu-id="2102f-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="2102f-3168">2-4 位數 (選用)</span><span class="sxs-lookup"><span data-stu-id="2102f-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="2102f-3169">日期格式 YYMMDD 的六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="2102f-3170">分隔符號 "-" 或 "+" (選擇性), 加上</span><span class="sxs-lookup"><span data-stu-id="2102f-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="2102f-3171">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3172">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3172">Checksum</span></span>

<span data-ttu-id="2102f-3173">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3174">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3174">Definition</span></span>

<span data-ttu-id="2102f-3175">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3176">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3177">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3178">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3178">Keywords</span></span>

<span data-ttu-id="2102f-3179">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="2102f-3180">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3181">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3181">Format</span></span>

<span data-ttu-id="2102f-3182">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3183">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3183">Pattern</span></span>

<span data-ttu-id="2102f-3184">八個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3185">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3185">Checksum</span></span>

<span data-ttu-id="2102f-3186">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3187">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3187">Definition</span></span>

<span data-ttu-id="2102f-3188">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3189">正則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3190">下列其中一項為真:</span><span class="sxs-lookup"><span data-stu-id="2102f-3190">One of the following is true:</span></span>
    - <span data-ttu-id="2102f-3191">找到 Keyword_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="2102f-3192">找到 Keyword_sweden_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3193">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="2102f-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="2102f-3195">簽證需求</span><span class="sxs-lookup"><span data-stu-id="2102f-3195">visa requirements</span></span> 
- <span data-ttu-id="2102f-3196">外部註冊卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="2102f-3197">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="2102f-3197">Schengen visas</span></span> 
- <span data-ttu-id="2102f-3198">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="2102f-3198">Schengen visa</span></span> 
- <span data-ttu-id="2102f-3199">簽證處理</span><span class="sxs-lookup"><span data-stu-id="2102f-3199">Visa Processing</span></span> 
- <span data-ttu-id="2102f-3200">簽證類型</span><span class="sxs-lookup"><span data-stu-id="2102f-3200">Visa Type</span></span> 
- <span data-ttu-id="2102f-3201">單一專案</span><span class="sxs-lookup"><span data-stu-id="2102f-3201">Single Entry</span></span> 
- <span data-ttu-id="2102f-3202">多個專案</span><span class="sxs-lookup"><span data-stu-id="2102f-3202">Multiple Entry</span></span> 
- <span data-ttu-id="2102f-3203">G3 處理費用</span><span class="sxs-lookup"><span data-stu-id="2102f-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="2102f-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-3204">Keyword_passport</span></span>

- <span data-ttu-id="2102f-3205">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3205">Passport Number</span></span> 
- <span data-ttu-id="2102f-3206">護照否</span><span class="sxs-lookup"><span data-stu-id="2102f-3206">Passport No</span></span> 
- <span data-ttu-id="2102f-3207">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-3207">Passport #</span></span> 
- <span data-ttu-id="2102f-3208">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-3208">Passport#</span></span> 
- <span data-ttu-id="2102f-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="2102f-3209">PassportID</span></span> 
- <span data-ttu-id="2102f-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="2102f-3210">Passportno</span></span> 
- <span data-ttu-id="2102f-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-3211">passportnumber</span></span> 
- <span data-ttu-id="2102f-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="2102f-3212">パスポート</span></span> 
- <span data-ttu-id="2102f-3213">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="2102f-3213">パスポート番号</span></span> 
- <span data-ttu-id="2102f-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2102f-3214">パスポートのNum</span></span> 
- <span data-ttu-id="2102f-3215">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2102f-3215">パスポート＃</span></span> 
- <span data-ttu-id="2102f-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2102f-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="2102f-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2102f-3217">Passeport n °</span></span> 
- <span data-ttu-id="2102f-3218">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="2102f-3218">Passeport Non</span></span> 
- <span data-ttu-id="2102f-3219">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2102f-3219">Passeport #</span></span> 
- <span data-ttu-id="2102f-3220">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2102f-3220">Passeport#</span></span> 
- <span data-ttu-id="2102f-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2102f-3221">PasseportNon</span></span> 
- <span data-ttu-id="2102f-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2102f-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="2102f-3223">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3224">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3224">Format</span></span>

<span data-ttu-id="2102f-3225">四個字母后尾隨5-31 個字母或數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3226">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3226">Pattern</span></span>

<span data-ttu-id="2102f-3227">四個字母后尾隨5-31 個字母或數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="2102f-3228">四字母銀行代碼 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-3229">選擇性的空間</span><span class="sxs-lookup"><span data-stu-id="2102f-3229">An optional space</span></span> 
- <span data-ttu-id="2102f-3230">4-28 個字母或數位 (基本銀行帳戶號碼 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="2102f-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="2102f-3231">選擇性的空間</span><span class="sxs-lookup"><span data-stu-id="2102f-3231">An optional space</span></span> 
- <span data-ttu-id="2102f-3232">1-3 個字母或數位 (其餘的 BBAN)</span><span class="sxs-lookup"><span data-stu-id="2102f-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3233">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3233">Checksum</span></span>

<span data-ttu-id="2102f-3234">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3235">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3235">Definition</span></span>

<span data-ttu-id="2102f-3236">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3237">正則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3238">找到 Keyword_swift 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3239">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="2102f-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="2102f-3240">Keyword_swift</span></span>

- <span data-ttu-id="2102f-3241">標準化9362的國際組織</span><span class="sxs-lookup"><span data-stu-id="2102f-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="2102f-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="2102f-3242">iso 9362</span></span> 
- <span data-ttu-id="2102f-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="2102f-3243">iso9362</span></span> 
- <span data-ttu-id="2102f-3244">快速\#</span><span class="sxs-lookup"><span data-stu-id="2102f-3244">swift\#</span></span> 
- <span data-ttu-id="2102f-3245">swiftcode</span><span class="sxs-lookup"><span data-stu-id="2102f-3245">swiftcode</span></span> 
- <span data-ttu-id="2102f-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-3246">swiftnumber</span></span> 
- <span data-ttu-id="2102f-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="2102f-3248">swift 代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3248">swift code</span></span> 
- <span data-ttu-id="2102f-3249">swift 號碼 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3249">swift number #</span></span> 
- <span data-ttu-id="2102f-3250">swift 路由號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3250">swift routing number</span></span> 
- <span data-ttu-id="2102f-3251">bic 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3251">bic number</span></span> 
- <span data-ttu-id="2102f-3252">bic 程式碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3252">bic code</span></span> 
- <span data-ttu-id="2102f-3253">bic\#</span><span class="sxs-lookup"><span data-stu-id="2102f-3253">bic \#</span></span> 
- <span data-ttu-id="2102f-3254">bic\#</span><span class="sxs-lookup"><span data-stu-id="2102f-3254">bic\#</span></span> 
- <span data-ttu-id="2102f-3255">銀行識別碼代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3255">bank identifier code</span></span> 
- <span data-ttu-id="2102f-3256">標準化9362</span><span class="sxs-lookup"><span data-stu-id="2102f-3256">標準化9362</span></span> 
- <span data-ttu-id="2102f-3257">迅速＃</span><span class="sxs-lookup"><span data-stu-id="2102f-3257">迅速＃</span></span> 
- <span data-ttu-id="2102f-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="2102f-3258">SWIFTコード</span></span> 
- <span data-ttu-id="2102f-3259">SWIFT番號</span><span class="sxs-lookup"><span data-stu-id="2102f-3259">SWIFT番号</span></span> 
- <span data-ttu-id="2102f-3260">迅速なルーティング番號</span><span class="sxs-lookup"><span data-stu-id="2102f-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="2102f-3261">BIC番號</span><span class="sxs-lookup"><span data-stu-id="2102f-3261">BIC番号</span></span> 
- <span data-ttu-id="2102f-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="2102f-3262">BICコード</span></span> 
- <span data-ttu-id="2102f-3263">銀行識別コードのための國際組織</span><span class="sxs-lookup"><span data-stu-id="2102f-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="2102f-3264">組織 internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="2102f-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="2102f-3265">rapide\#</span><span class="sxs-lookup"><span data-stu-id="2102f-3265">rapide \#</span></span> 
- <span data-ttu-id="2102f-3266">程式碼 SWIFT</span><span class="sxs-lookup"><span data-stu-id="2102f-3266">code SWIFT</span></span> 
- <span data-ttu-id="2102f-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="2102f-3267">le numéro de swift</span></span> 
- <span data-ttu-id="2102f-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="2102f-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="2102f-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="2102f-3269">le numéro BIC</span></span> 
- <span data-ttu-id="2102f-3270">\#BIC</span><span class="sxs-lookup"><span data-stu-id="2102f-3270">\# BIC</span></span> 
- <span data-ttu-id="2102f-3271">程式碼 identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="2102f-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="2102f-3272">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="2102f-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3273">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3273">Format</span></span>

<span data-ttu-id="2102f-3274">一個字母 (英文) 後尾隨九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3275">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3275">Pattern</span></span>

<span data-ttu-id="2102f-3276">一個字母 (英文) 後尾隨九位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="2102f-3277">一個字母 (英文, 不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="2102f-3278">數位 "1" 或 "2"</span><span class="sxs-lookup"><span data-stu-id="2102f-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="2102f-3279">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3280">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3280">Checksum</span></span>

<span data-ttu-id="2102f-3281">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3282">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3282">Definition</span></span>

<span data-ttu-id="2102f-3283">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3284">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3285">找到 Keyword_taiwanese_national_id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="2102f-3286">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3287">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="2102f-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="2102f-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="2102f-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3289">身份證字號</span></span> 
- <span data-ttu-id="2102f-3290">身份證</span><span class="sxs-lookup"><span data-stu-id="2102f-3290">身份證</span></span> 
- <span data-ttu-id="2102f-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3291">身份證號碼</span></span> 
- <span data-ttu-id="2102f-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="2102f-3292">身份證號</span></span> 
- <span data-ttu-id="2102f-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3293">身分證字號</span></span> 
- <span data-ttu-id="2102f-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="2102f-3294">身分證</span></span> 
- <span data-ttu-id="2102f-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3295">身分證號碼</span></span> 
- <span data-ttu-id="2102f-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="2102f-3296">身份證號</span></span> 
- <span data-ttu-id="2102f-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3297">身分證統一編號</span></span> 
- <span data-ttu-id="2102f-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="2102f-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="2102f-3299">簽名</span></span> 
- <span data-ttu-id="2102f-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="2102f-3300">蓋章</span></span> 
- <span data-ttu-id="2102f-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="2102f-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="2102f-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="2102f-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="2102f-3303">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3304">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3304">Format</span></span>

- <span data-ttu-id="2102f-3305">生物識別護照號碼: 九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="2102f-3306">非生物識別護照號碼: 九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3307">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3307">Pattern</span></span>
<span data-ttu-id="2102f-3308">生物識別護照號碼:</span><span class="sxs-lookup"><span data-stu-id="2102f-3308">Biometric passport number:</span></span>
- <span data-ttu-id="2102f-3309">數位 "3"</span><span class="sxs-lookup"><span data-stu-id="2102f-3309">The digit "3"</span></span> 
- <span data-ttu-id="2102f-3310">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3310">Eight digits</span></span>

<span data-ttu-id="2102f-3311">無法生物識別的護照號碼:</span><span class="sxs-lookup"><span data-stu-id="2102f-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="2102f-3312">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3313">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3313">Checksum</span></span>

<span data-ttu-id="2102f-3314">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3315">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3315">Definition</span></span>

<span data-ttu-id="2102f-3316">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3317">正則運算式 Regex_taiwan_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3318">找到 Keyword_taiwan_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3319">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="2102f-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="2102f-3321">ROC 護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3321">ROC passport number</span></span> 
- <span data-ttu-id="2102f-3322">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3322">Passport number</span></span> 
- <span data-ttu-id="2102f-3323">護照否</span><span class="sxs-lookup"><span data-stu-id="2102f-3323">Passport no</span></span> 
- <span data-ttu-id="2102f-3324">護照編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3324">Passport Num</span></span> 
- <span data-ttu-id="2102f-3325">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-3325">Passport #</span></span> 
- <span data-ttu-id="2102f-3326">護照</span><span class="sxs-lookup"><span data-stu-id="2102f-3326">护照</span></span> 
- <span data-ttu-id="2102f-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="2102f-3327">中華民國護照</span></span> 
- <span data-ttu-id="2102f-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="2102f-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="2102f-3329">臺灣駐留憑證 (ARC/TARC) 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3330">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3330">Format</span></span>

<span data-ttu-id="2102f-3331">10個字母和數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3332">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3332">Pattern</span></span>

<span data-ttu-id="2102f-3333">10個字母和數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-3333">10 letters and digits:</span></span>
- <span data-ttu-id="2102f-3334">兩個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="2102f-3335">八位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3336">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3336">Checksum</span></span>

<span data-ttu-id="2102f-3337">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3338">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3338">Definition</span></span>

<span data-ttu-id="2102f-3339">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3340">正則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3341">找到 Keyword_taiwan_resident_certificate 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3342">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="2102f-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="2102f-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="2102f-3344">駐留憑證</span><span class="sxs-lookup"><span data-stu-id="2102f-3344">Resident Certificate</span></span> 
- <span data-ttu-id="2102f-3345">居民憑證</span><span class="sxs-lookup"><span data-stu-id="2102f-3345">Resident Cert</span></span> 
- <span data-ttu-id="2102f-3346">常駐憑證。</span><span class="sxs-lookup"><span data-stu-id="2102f-3346">Resident Cert.</span></span> 
- <span data-ttu-id="2102f-3347">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3347">Identification card</span></span> 
- <span data-ttu-id="2102f-3348">外部駐留憑證</span><span class="sxs-lookup"><span data-stu-id="2102f-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="2102f-3349">ARC</span><span class="sxs-lookup"><span data-stu-id="2102f-3349">ARC</span></span> 
- <span data-ttu-id="2102f-3350">臺灣區域駐留憑證</span><span class="sxs-lookup"><span data-stu-id="2102f-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="2102f-3351">TARC</span><span class="sxs-lookup"><span data-stu-id="2102f-3351">TARC</span></span> 
- <span data-ttu-id="2102f-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="2102f-3352">居留證</span></span> 
- <span data-ttu-id="2102f-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="2102f-3353">外僑居留證</span></span> 
- <span data-ttu-id="2102f-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="2102f-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="2102f-3355">泰文填充識別代碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3356">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3356">Format</span></span>

<span data-ttu-id="2102f-3357">13位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3358">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3358">Pattern</span></span>

<span data-ttu-id="2102f-3359">13位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-3359">13 digits:</span></span>
- <span data-ttu-id="2102f-3360">第一個數位不是0或9</span><span class="sxs-lookup"><span data-stu-id="2102f-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="2102f-3361">12位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3362">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3362">Checksum</span></span>

<span data-ttu-id="2102f-3363">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3364">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3364">Definition</span></span>

<span data-ttu-id="2102f-3365">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3366">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3367">找到 Keyword_Thai_Citizen_Id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="2102f-3368">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3369">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3370">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="2102f-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="2102f-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="2102f-3372">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3372">ID Number</span></span>
- <span data-ttu-id="2102f-3373">識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3373">Identification Number</span></span>
- <span data-ttu-id="2102f-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2102f-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="2102f-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2102f-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="2102f-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2102f-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="2102f-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2102f-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="2102f-3378">土耳其文民族識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3379">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3379">Format</span></span>

<span data-ttu-id="2102f-3380">11位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3381">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3381">Pattern</span></span>

<span data-ttu-id="2102f-3382">11位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3383">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3383">Checksum</span></span>

<span data-ttu-id="2102f-3384">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3385">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3385">Definition</span></span>

<span data-ttu-id="2102f-3386">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3387">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3388">找到 Keyword_Turkish_National_Id 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="2102f-3389">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3390">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3391">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="2102f-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="2102f-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="2102f-3393">TC Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="2102f-3393">TC Kimlik No</span></span>
- <span data-ttu-id="2102f-3394">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="2102f-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="2102f-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="2102f-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="2102f-3396">Vatandaşlık 否</span><span class="sxs-lookup"><span data-stu-id="2102f-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="2102f-3397">英制</span><span class="sxs-lookup"><span data-stu-id="2102f-3397">U.K.</span></span> <span data-ttu-id="2102f-3398">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3398">Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3399">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3399">Format</span></span>

<span data-ttu-id="2102f-3400">以指定格式的18個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="2102f-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3401">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3401">Pattern</span></span>

<span data-ttu-id="2102f-3402">18個字母和數位:</span><span class="sxs-lookup"><span data-stu-id="2102f-3402">18 letters and digits:</span></span>
- <span data-ttu-id="2102f-3403">五個字母 (不區分大小寫) 或取代字母的數位 "9"</span><span class="sxs-lookup"><span data-stu-id="2102f-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="2102f-3404">一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3404">One digit</span></span> 
- <span data-ttu-id="2102f-3405">出生日期日期格式 DDMMY 的五位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="2102f-3406">兩個字母 (不區分大小寫) 或取代字母的數位 "9"</span><span class="sxs-lookup"><span data-stu-id="2102f-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="2102f-3407">五位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3408">Checksum</span></span>

<span data-ttu-id="2102f-3409">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3410">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3410">Definition</span></span>

<span data-ttu-id="2102f-3411">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3412">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3413">找到 Keyword_uk_drivers_license 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="2102f-3414">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3415">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="2102f-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2102f-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="2102f-3417">DVLA</span><span class="sxs-lookup"><span data-stu-id="2102f-3417">DVLA</span></span> 
- <span data-ttu-id="2102f-3418">淺 vans</span><span class="sxs-lookup"><span data-stu-id="2102f-3418">light vans</span></span> 
- <span data-ttu-id="2102f-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="2102f-3419">quadbikes</span></span> 
- <span data-ttu-id="2102f-3420">汽車轎車</span><span class="sxs-lookup"><span data-stu-id="2102f-3420">motor cars</span></span> 
- <span data-ttu-id="2102f-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="2102f-3421">125cc</span></span> 
- <span data-ttu-id="2102f-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="2102f-3422">sidecar</span></span> 
- <span data-ttu-id="2102f-3423">tricycles</span><span class="sxs-lookup"><span data-stu-id="2102f-3423">tricycles</span></span> 
- <span data-ttu-id="2102f-3424">motorcycles</span><span class="sxs-lookup"><span data-stu-id="2102f-3424">motorcycles</span></span> 
- <span data-ttu-id="2102f-3425">photocard 許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-3425">photocard licence</span></span> 
- <span data-ttu-id="2102f-3426">learner 驅動程式</span><span class="sxs-lookup"><span data-stu-id="2102f-3426">learner drivers</span></span> 
- <span data-ttu-id="2102f-3427">許可證持有者</span><span class="sxs-lookup"><span data-stu-id="2102f-3427">licence holder</span></span> 
- <span data-ttu-id="2102f-3428">許可證持有者</span><span class="sxs-lookup"><span data-stu-id="2102f-3428">licence holders</span></span> 
- <span data-ttu-id="2102f-3429">駕駛授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3429">driving licences</span></span> 
- <span data-ttu-id="2102f-3430">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-3430">driving licence</span></span> 
- <span data-ttu-id="2102f-3431">雙控制汽車</span><span class="sxs-lookup"><span data-stu-id="2102f-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="2102f-3432">英制</span><span class="sxs-lookup"><span data-stu-id="2102f-3432">U.K.</span></span> <span data-ttu-id="2102f-3433">Electoral 卷號</span><span class="sxs-lookup"><span data-stu-id="2102f-3433">Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3434">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3434">Format</span></span>

<span data-ttu-id="2102f-3435">兩個字母后尾隨1-4 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3436">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3436">Pattern</span></span>

<span data-ttu-id="2102f-3437">兩個字母 (不區分大小寫), 後面接著1-4 個數字</span><span class="sxs-lookup"><span data-stu-id="2102f-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3438">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3438">Checksum</span></span>

<span data-ttu-id="2102f-3439">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3440">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3440">Definition</span></span>

<span data-ttu-id="2102f-3441">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3442">正則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3443">找到 Keyword_uk_electoral 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3444">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="2102f-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="2102f-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="2102f-3446">理事會提名</span><span class="sxs-lookup"><span data-stu-id="2102f-3446">council nomination</span></span> 
- <span data-ttu-id="2102f-3447">提名表單</span><span class="sxs-lookup"><span data-stu-id="2102f-3447">nomination form</span></span> 
- <span data-ttu-id="2102f-3448">electoral 寄存器</span><span class="sxs-lookup"><span data-stu-id="2102f-3448">electoral register</span></span> 
- <span data-ttu-id="2102f-3449">electoral 捲筒</span><span class="sxs-lookup"><span data-stu-id="2102f-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="2102f-3450">英制</span><span class="sxs-lookup"><span data-stu-id="2102f-3450">U.K.</span></span> <span data-ttu-id="2102f-3451">國家健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3451">National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3452">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3452">Format</span></span>

<span data-ttu-id="2102f-3453">以空格分隔的10-17 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3454">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3454">Pattern</span></span>

<span data-ttu-id="2102f-3455">10-17 位數:</span><span class="sxs-lookup"><span data-stu-id="2102f-3455">10-17 digits:</span></span>
- <span data-ttu-id="2102f-3456">3或10位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="2102f-3457">一個空格</span><span class="sxs-lookup"><span data-stu-id="2102f-3457">A space</span></span> 
- <span data-ttu-id="2102f-3458">三位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3458">Three digits</span></span> 
- <span data-ttu-id="2102f-3459">一個空格</span><span class="sxs-lookup"><span data-stu-id="2102f-3459">A space</span></span> 
- <span data-ttu-id="2102f-3460">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3461">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3461">Checksum</span></span>

<span data-ttu-id="2102f-3462">是</span><span class="sxs-lookup"><span data-stu-id="2102f-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3463">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3463">Definition</span></span>

<span data-ttu-id="2102f-3464">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3465">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3466">下列其中一項為真:</span><span class="sxs-lookup"><span data-stu-id="2102f-3466">One of the following is true:</span></span>
    - <span data-ttu-id="2102f-3467">找到 Keyword_uk_nhs_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="2102f-3468">找到 Keyword_uk_nhs_number1 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="2102f-3469">找到 Keyword_uk_nhs_number_dob 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="2102f-3470">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="2102f-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3471">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="2102f-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="2102f-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="2102f-3473">國內健康情況服務</span><span class="sxs-lookup"><span data-stu-id="2102f-3473">national health service</span></span> 
- <span data-ttu-id="2102f-3474">nhs</span><span class="sxs-lookup"><span data-stu-id="2102f-3474">nhs</span></span> 
- <span data-ttu-id="2102f-3475">健康情況服務授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3475">health services authority</span></span> 
- <span data-ttu-id="2102f-3476">健康情況授權單位</span><span class="sxs-lookup"><span data-stu-id="2102f-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="2102f-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="2102f-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="2102f-3478">患者識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3478">patient id</span></span> 
- <span data-ttu-id="2102f-3479">患者識別</span><span class="sxs-lookup"><span data-stu-id="2102f-3479">patient identification</span></span> 
- <span data-ttu-id="2102f-3480">患者否</span><span class="sxs-lookup"><span data-stu-id="2102f-3480">patient no</span></span> 
- <span data-ttu-id="2102f-3481">患者號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="2102f-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="2102f-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="2102f-3483">GP</span><span class="sxs-lookup"><span data-stu-id="2102f-3483">GP</span></span> 
- <span data-ttu-id="2102f-3484">DOB</span><span class="sxs-lookup"><span data-stu-id="2102f-3484">DOB</span></span> 
- <span data-ttu-id="2102f-3485">D. B. B</span><span class="sxs-lookup"><span data-stu-id="2102f-3485">D.O.B</span></span> 
- <span data-ttu-id="2102f-3486">出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-3486">Date of Birth</span></span> 
- <span data-ttu-id="2102f-3487">出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="2102f-3488">英制</span><span class="sxs-lookup"><span data-stu-id="2102f-3488">U.K.</span></span> <span data-ttu-id="2102f-3489">民族保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="2102f-3489">National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3490">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3490">Format</span></span>

<span data-ttu-id="2102f-3491">以空格或虛線隔開的7個字元或9個字元</span><span class="sxs-lookup"><span data-stu-id="2102f-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3492">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3492">Pattern</span></span>

<span data-ttu-id="2102f-3493">兩種可能的模式:</span><span class="sxs-lookup"><span data-stu-id="2102f-3493">Two possible patterns:</span></span>

- <span data-ttu-id="2102f-3494">兩個字母 (有效的 NINOs 只會使用此前置詞中的特定字元, 此模式會驗證, 不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="2102f-3495">六位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3495">Six digits</span></span>
- <span data-ttu-id="2102f-3496">' A '、' B '、' C ' 或 ' d ' (就像是前置詞, 尾碼中只允許有某些字元; 不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="2102f-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="2102f-3497">或</span><span class="sxs-lookup"><span data-stu-id="2102f-3497">OR</span></span>

- <span data-ttu-id="2102f-3498">兩個字母</span><span class="sxs-lookup"><span data-stu-id="2102f-3498">Two letters</span></span>
- <span data-ttu-id="2102f-3499">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3499">A space or dash</span></span>
- <span data-ttu-id="2102f-3500">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3500">Two digits</span></span>
- <span data-ttu-id="2102f-3501">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3501">A space or dash</span></span>
- <span data-ttu-id="2102f-3502">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3502">Two digits</span></span>
- <span data-ttu-id="2102f-3503">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3503">A space or dash</span></span>
- <span data-ttu-id="2102f-3504">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3504">Two digits</span></span>
- <span data-ttu-id="2102f-3505">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3505">A space or dash</span></span>
- <span data-ttu-id="2102f-3506">' A '、' B '、' C ' 或 ' d '</span><span class="sxs-lookup"><span data-stu-id="2102f-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3507">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3507">Checksum</span></span>

<span data-ttu-id="2102f-3508">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3509">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3509">Definition</span></span>

<span data-ttu-id="2102f-3510">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3511">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3512">找到 Keyword_uk_nino 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="2102f-3513">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3514">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3515">找不到 Keyword_uk_nino 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="2102f-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="2102f-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="2102f-3518">民族保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3518">national insurance number</span></span> 
- <span data-ttu-id="2102f-3519">全國保險份額</span><span class="sxs-lookup"><span data-stu-id="2102f-3519">national insurance contributions</span></span> 
- <span data-ttu-id="2102f-3520">保護法案</span><span class="sxs-lookup"><span data-stu-id="2102f-3520">protection act</span></span> 
- <span data-ttu-id="2102f-3521">業務員</span><span class="sxs-lookup"><span data-stu-id="2102f-3521">insurance</span></span> 
- <span data-ttu-id="2102f-3522">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3522">social security number</span></span> 
- <span data-ttu-id="2102f-3523">保險應用程式</span><span class="sxs-lookup"><span data-stu-id="2102f-3523">insurance application</span></span> 
- <span data-ttu-id="2102f-3524">醫療應用程式</span><span class="sxs-lookup"><span data-stu-id="2102f-3524">medical application</span></span> 
- <span data-ttu-id="2102f-3525">社交保險</span><span class="sxs-lookup"><span data-stu-id="2102f-3525">social insurance</span></span> 
- <span data-ttu-id="2102f-3526">醫療注意力</span><span class="sxs-lookup"><span data-stu-id="2102f-3526">medical attention</span></span> 
- <span data-ttu-id="2102f-3527">社會保險</span><span class="sxs-lookup"><span data-stu-id="2102f-3527">social security</span></span> 
- <span data-ttu-id="2102f-3528">英國</span><span class="sxs-lookup"><span data-stu-id="2102f-3528">great britain</span></span> 
- <span data-ttu-id="2102f-3529">業務員</span><span class="sxs-lookup"><span data-stu-id="2102f-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="2102f-3530">美國/英國</span><span class="sxs-lookup"><span data-stu-id="2102f-3530">U.S. / U.K.</span></span> <span data-ttu-id="2102f-3531">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3531">Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3532">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3532">Format</span></span>

<span data-ttu-id="2102f-3533">九位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3534">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3534">Pattern</span></span>

<span data-ttu-id="2102f-3535">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3536">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3536">Checksum</span></span>

<span data-ttu-id="2102f-3537">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3538">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3538">Definition</span></span>

<span data-ttu-id="2102f-3539">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3540">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3541">找到 Keyword_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3542">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2102f-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2102f-3543">Keyword_passport</span></span>

- <span data-ttu-id="2102f-3544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3544">Passport Number</span></span> 
- <span data-ttu-id="2102f-3545">護照否</span><span class="sxs-lookup"><span data-stu-id="2102f-3545">Passport No</span></span> 
- <span data-ttu-id="2102f-3546">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-3546">Passport #</span></span> 
- <span data-ttu-id="2102f-3547">通行證</span><span class="sxs-lookup"><span data-stu-id="2102f-3547">Passport#</span></span> 
- <span data-ttu-id="2102f-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="2102f-3548">PassportID</span></span> 
- <span data-ttu-id="2102f-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="2102f-3549">Passportno</span></span> 
- <span data-ttu-id="2102f-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2102f-3550">passportnumber</span></span> 
- <span data-ttu-id="2102f-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="2102f-3551">パスポート</span></span> 
- <span data-ttu-id="2102f-3552">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="2102f-3552">パスポート番号</span></span> 
- <span data-ttu-id="2102f-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2102f-3553">パスポートのNum</span></span> 
- <span data-ttu-id="2102f-3554">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2102f-3554">パスポート＃</span></span> 
- <span data-ttu-id="2102f-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2102f-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="2102f-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2102f-3556">Passeport n °</span></span> 
- <span data-ttu-id="2102f-3557">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="2102f-3557">Passeport Non</span></span> 
- <span data-ttu-id="2102f-3558">Passeport #</span><span class="sxs-lookup"><span data-stu-id="2102f-3558">Passeport #</span></span> 
- <span data-ttu-id="2102f-3559">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2102f-3559">Passeport#</span></span> 
- <span data-ttu-id="2102f-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2102f-3560">PasseportNon</span></span> 
- <span data-ttu-id="2102f-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2102f-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="2102f-3562">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3563">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3563">Format</span></span>

<span data-ttu-id="2102f-3564">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3565">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3565">Pattern</span></span>

<span data-ttu-id="2102f-3566">8-17 連續數位</span><span class="sxs-lookup"><span data-stu-id="2102f-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3567">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3567">Checksum</span></span>

<span data-ttu-id="2102f-3568">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3569">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3569">Definition</span></span>

<span data-ttu-id="2102f-3570">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3571">正則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3572">找到 Keyword_usa_Bank_Account 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2102f-3573">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="2102f-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="2102f-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="2102f-3575">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3575">Checking Account Number</span></span> 
- <span data-ttu-id="2102f-3576">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="2102f-3576">Checking Account</span></span> 
- <span data-ttu-id="2102f-3577">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3577">Checking Account #</span></span> 
- <span data-ttu-id="2102f-3578">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="2102f-3579">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3579">Checking Acct #</span></span> 
- <span data-ttu-id="2102f-3580">檢查帳戶是否為 [否]。</span><span class="sxs-lookup"><span data-stu-id="2102f-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="2102f-3581">檢查帳戶否。</span><span class="sxs-lookup"><span data-stu-id="2102f-3581">Checking Account No.</span></span> 
- <span data-ttu-id="2102f-3582">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3582">Bank Account Number</span></span> 
- <span data-ttu-id="2102f-3583">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3583">Bank Account #</span></span> 
- <span data-ttu-id="2102f-3584">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="2102f-3585">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3585">Bank Acct #</span></span> 
- <span data-ttu-id="2102f-3586">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="2102f-3587">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3587">Bank Account No.</span></span> 
- <span data-ttu-id="2102f-3588">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3588">Savings Account Number</span></span> 
- <span data-ttu-id="2102f-3589">儲蓄帳戶。</span><span class="sxs-lookup"><span data-stu-id="2102f-3589">Savings Account.</span></span> 
- <span data-ttu-id="2102f-3590">儲蓄帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3590">Savings Account #</span></span> 
- <span data-ttu-id="2102f-3591">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="2102f-3592">儲蓄帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3592">Savings Acct #</span></span> 
- <span data-ttu-id="2102f-3593">儲蓄帳戶否。</span><span class="sxs-lookup"><span data-stu-id="2102f-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="2102f-3594">儲蓄帳戶編號。</span><span class="sxs-lookup"><span data-stu-id="2102f-3594">Savings Account No.</span></span> 
- <span data-ttu-id="2102f-3595">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3595">Debit Account Number</span></span> 
- <span data-ttu-id="2102f-3596">借方科目</span><span class="sxs-lookup"><span data-stu-id="2102f-3596">Debit Account</span></span> 
- <span data-ttu-id="2102f-3597">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3597">Debit Account #</span></span> 
- <span data-ttu-id="2102f-3598">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="2102f-3599">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3599">Debit Acct #</span></span> 
- <span data-ttu-id="2102f-3600">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="2102f-3601">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="2102f-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="2102f-3602">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3603">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3603">Format</span></span>

<span data-ttu-id="2102f-3604">取決於狀態</span><span class="sxs-lookup"><span data-stu-id="2102f-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3605">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3605">Pattern</span></span>

<span data-ttu-id="2102f-3606">取決於狀態--例如紐約:</span><span class="sxs-lookup"><span data-stu-id="2102f-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="2102f-3607">有九位數的格式, 例如 ddd ddd ddd 會相符。</span><span class="sxs-lookup"><span data-stu-id="2102f-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="2102f-3608">9個數字, 例如 ddddddddd 將不相符。</span><span class="sxs-lookup"><span data-stu-id="2102f-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3609">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3609">Checksum</span></span>

<span data-ttu-id="2102f-3610">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3611">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3611">Definition</span></span>

<span data-ttu-id="2102f-3612">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3613">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3614">找到 Keyword_ [state_name] _drivers_license_name 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2102f-3615">找到 Keyword_us_drivers_license 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="2102f-3616">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3617">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3618">找到 Keyword_ [state_name] _drivers_license_name 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2102f-3619">找到 Keyword_us_drivers_license_abbreviations 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="2102f-3620">找不到 Keyword_us_drivers_license 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="2102f-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="2102f-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="2102f-3623">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-3623">DL</span></span> 
- <span data-ttu-id="2102f-3624">DLS</span><span class="sxs-lookup"><span data-stu-id="2102f-3624">DLS</span></span> 
- <span data-ttu-id="2102f-3625">採用</span><span class="sxs-lookup"><span data-stu-id="2102f-3625">CDL</span></span> 
- <span data-ttu-id="2102f-3626">CDLS</span><span class="sxs-lookup"><span data-stu-id="2102f-3626">CDLS</span></span> 
- <span data-ttu-id="2102f-3627">ID</span><span class="sxs-lookup"><span data-stu-id="2102f-3627">ID</span></span> 
- <span data-ttu-id="2102f-3628">識別</span><span class="sxs-lookup"><span data-stu-id="2102f-3628">IDs</span></span> 
- <span data-ttu-id="2102f-3629">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-3629">DL#</span></span> 
- <span data-ttu-id="2102f-3630">DLS</span><span class="sxs-lookup"><span data-stu-id="2102f-3630">DLS#</span></span> 
- <span data-ttu-id="2102f-3631">採用</span><span class="sxs-lookup"><span data-stu-id="2102f-3631">CDL#</span></span> 
- <span data-ttu-id="2102f-3632">CDLS#</span><span class="sxs-lookup"><span data-stu-id="2102f-3632">CDLS#</span></span> 
- <span data-ttu-id="2102f-3633">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3633">ID#</span></span>
- <span data-ttu-id="2102f-3634">識別</span><span class="sxs-lookup"><span data-stu-id="2102f-3634">IDs#</span></span> 
- <span data-ttu-id="2102f-3635">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3635">ID number</span></span> 
- <span data-ttu-id="2102f-3636">ID 號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3636">ID numbers</span></span> 
- <span data-ttu-id="2102f-3637">許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-3637">LIC</span></span> 
- <span data-ttu-id="2102f-3638">許可證</span><span class="sxs-lookup"><span data-stu-id="2102f-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="2102f-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2102f-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="2102f-3640">DriverLic</span><span class="sxs-lookup"><span data-stu-id="2102f-3640">DriverLic</span></span> 
- <span data-ttu-id="2102f-3641">DriverLics</span><span class="sxs-lookup"><span data-stu-id="2102f-3641">DriverLics</span></span> 
- <span data-ttu-id="2102f-3642">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-3642">DriverLicense</span></span> 
- <span data-ttu-id="2102f-3643">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-3643">DriverLicenses</span></span> 
- <span data-ttu-id="2102f-3644">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-3644">Driver Lic</span></span> 
- <span data-ttu-id="2102f-3645">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-3645">Driver Lics</span></span> 
- <span data-ttu-id="2102f-3646">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3646">Driver License</span></span> 
- <span data-ttu-id="2102f-3647">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3647">Driver Licenses</span></span> 
- <span data-ttu-id="2102f-3648">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2102f-3648">DriversLic</span></span> 
- <span data-ttu-id="2102f-3649">DriversLics</span><span class="sxs-lookup"><span data-stu-id="2102f-3649">DriversLics</span></span> 
- <span data-ttu-id="2102f-3650">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-3650">DriversLicense</span></span> 
- <span data-ttu-id="2102f-3651">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-3651">DriversLicenses</span></span> 
- <span data-ttu-id="2102f-3652">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-3652">Drivers Lic</span></span> 
- <span data-ttu-id="2102f-3653">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-3653">Drivers Lics</span></span> 
- <span data-ttu-id="2102f-3654">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3654">Drivers License</span></span> 
- <span data-ttu-id="2102f-3655">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="2102f-3656">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-3656">Driver'Lic</span></span> 
- <span data-ttu-id="2102f-3657">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-3657">Driver'Lics</span></span> 
- <span data-ttu-id="2102f-3658">Driver'License</span><span class="sxs-lookup"><span data-stu-id="2102f-3658">Driver'License</span></span> 
- <span data-ttu-id="2102f-3659">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="2102f-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="2102f-3660">驅動程式 ' .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-3660">Driver' Lic</span></span> 
- <span data-ttu-id="2102f-3661">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-3661">Driver' Lics</span></span> 
- <span data-ttu-id="2102f-3662">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3662">Driver' License</span></span> 
- <span data-ttu-id="2102f-3663">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="2102f-3663">Driver' Licenses</span></span>
- <span data-ttu-id="2102f-3664">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2102f-3664">Driver'sLic</span></span> 
- <span data-ttu-id="2102f-3665">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2102f-3665">Driver'sLics</span></span> 
- <span data-ttu-id="2102f-3666">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="2102f-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="2102f-3667">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2102f-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="2102f-3668">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="2102f-3668">Driver's Lic</span></span> 
- <span data-ttu-id="2102f-3669">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="2102f-3669">Driver's Lics</span></span> 
- <span data-ttu-id="2102f-3670">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-3670">Driver's License</span></span> 
- <span data-ttu-id="2102f-3671">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="2102f-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="2102f-3672">識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3672">identification number</span></span> 
- <span data-ttu-id="2102f-3673">識別號碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3673">identification numbers</span></span> 
- <span data-ttu-id="2102f-3674">識別碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3674">identification #</span></span> 
- <span data-ttu-id="2102f-3675">id 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3675">id card</span></span> 
- <span data-ttu-id="2102f-3676">id 卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3676">id cards</span></span> 
- <span data-ttu-id="2102f-3677">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3677">identification card</span></span> 
- <span data-ttu-id="2102f-3678">識別卡</span><span class="sxs-lookup"><span data-stu-id="2102f-3678">identification cards</span></span> 
- <span data-ttu-id="2102f-3679">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-3679">DriverLic#</span></span> 
- <span data-ttu-id="2102f-3680">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-3680">DriverLics#</span></span> 
- <span data-ttu-id="2102f-3681">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-3681">DriverLicense#</span></span> 
- <span data-ttu-id="2102f-3682">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="2102f-3683">驅動程式 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-3683">Driver Lic#</span></span> 
- <span data-ttu-id="2102f-3684">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-3684">Driver Lics#</span></span> 
- <span data-ttu-id="2102f-3685">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3685">Driver License#</span></span> 
- <span data-ttu-id="2102f-3686">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="2102f-3687">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-3687">DriversLic#</span></span> 
- <span data-ttu-id="2102f-3688">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-3688">DriversLics#</span></span> 
- <span data-ttu-id="2102f-3689">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-3689">DriversLicense#</span></span> 
- <span data-ttu-id="2102f-3690">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="2102f-3691">驅動程式 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="2102f-3692">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="2102f-3693">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3693">Drivers License#</span></span> 
- <span data-ttu-id="2102f-3694">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="2102f-3695">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="2102f-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="2102f-3696">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="2102f-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="2102f-3697">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="2102f-3697">Driver'License#</span></span> 
- <span data-ttu-id="2102f-3698">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="2102f-3699">驅動程式 ' .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="2102f-3700">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="2102f-3701">驅動程式 ' License #</span><span class="sxs-lookup"><span data-stu-id="2102f-3701">Driver' License#</span></span> 
- <span data-ttu-id="2102f-3702">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="2102f-3703">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="2102f-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="2102f-3704">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="2102f-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="2102f-3705">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="2102f-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="2102f-3706">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="2102f-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="2102f-3707">驅動程式的 .Lic #</span><span class="sxs-lookup"><span data-stu-id="2102f-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="2102f-3708">Driver 的 Lics #</span><span class="sxs-lookup"><span data-stu-id="2102f-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="2102f-3709">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3709">Driver's License#</span></span> 
- <span data-ttu-id="2102f-3710">駕駛執照 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="2102f-3711">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3711">id card#</span></span> 
- <span data-ttu-id="2102f-3712">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3712">id cards#</span></span> 
- <span data-ttu-id="2102f-3713">身分識別卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3713">identification card#</span></span> 
- <span data-ttu-id="2102f-3714">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="2102f-3715">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="2102f-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="2102f-3716">狀態縮寫 (例如, "NY")</span><span class="sxs-lookup"><span data-stu-id="2102f-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="2102f-3717">狀態名稱 (例如 "紐約")</span><span class="sxs-lookup"><span data-stu-id="2102f-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="2102f-3718">美國個別納稅人識別號碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="2102f-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3719">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3719">Format</span></span>

<span data-ttu-id="2102f-3720">以 "9" 開頭且包含 "7" 或 "8" 的九位數做為第四位數, 選擇性地以空格或虛線格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3721">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3721">Pattern</span></span>

<span data-ttu-id="2102f-3722">格式化</span><span class="sxs-lookup"><span data-stu-id="2102f-3722">Formatted:</span></span>
- <span data-ttu-id="2102f-3723">數位 "9"</span><span class="sxs-lookup"><span data-stu-id="2102f-3723">The digit "9"</span></span> 
- <span data-ttu-id="2102f-3724">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3724">Two digits</span></span> 
- <span data-ttu-id="2102f-3725">一個空格或連字號</span><span class="sxs-lookup"><span data-stu-id="2102f-3725">A space or dash</span></span> 
- <span data-ttu-id="2102f-3726">"7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="2102f-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="2102f-3727">一位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3727">A digit</span></span> 
- <span data-ttu-id="2102f-3728">空格或虛線</span><span class="sxs-lookup"><span data-stu-id="2102f-3728">A space, or dash</span></span> 
- <span data-ttu-id="2102f-3729">四位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3729">Four digits</span></span>

<span data-ttu-id="2102f-3730">非</span><span class="sxs-lookup"><span data-stu-id="2102f-3730">Unformatted:</span></span>
- <span data-ttu-id="2102f-3731">數位 "9"</span><span class="sxs-lookup"><span data-stu-id="2102f-3731">The digit "9"</span></span> 
- <span data-ttu-id="2102f-3732">兩位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3732">Two digits</span></span> 
- <span data-ttu-id="2102f-3733">"7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="2102f-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="2102f-3734">五位數</span><span class="sxs-lookup"><span data-stu-id="2102f-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3735">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3735">Checksum</span></span>

<span data-ttu-id="2102f-3736">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="2102f-3737">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3737">Definition</span></span>

<span data-ttu-id="2102f-3738">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3739">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3740">至少下列其中一個值為 true:</span><span class="sxs-lookup"><span data-stu-id="2102f-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="2102f-3741">找到 Keyword_itin 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="2102f-3742">函數 Func_us_address 找到正確日期格式的位址。</span><span class="sxs-lookup"><span data-stu-id="2102f-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="2102f-3743">函數 Func_us_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="2102f-3744">找到 Keyword_itin_collaborative 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="2102f-3745">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3746">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3747">至少下列其中一個值為 true:</span><span class="sxs-lookup"><span data-stu-id="2102f-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="2102f-3748">找到 Keyword_itin_collaborative 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="2102f-3749">函數 Func_us_address 找到正確日期格式的位址。</span><span class="sxs-lookup"><span data-stu-id="2102f-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="2102f-3750">函數 Func_us_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="2102f-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="2102f-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="2102f-3752">Keyword_itin</span></span>

- <span data-ttu-id="2102f-3753">納稅人</span><span class="sxs-lookup"><span data-stu-id="2102f-3753">taxpayer</span></span> 
- <span data-ttu-id="2102f-3754">稅號</span><span class="sxs-lookup"><span data-stu-id="2102f-3754">tax id</span></span> 
- <span data-ttu-id="2102f-3755">納稅識別</span><span class="sxs-lookup"><span data-stu-id="2102f-3755">tax identification</span></span> 
- <span data-ttu-id="2102f-3756">itin</span><span class="sxs-lookup"><span data-stu-id="2102f-3756">itin</span></span> 
- <span data-ttu-id="2102f-3757">ssn</span><span class="sxs-lookup"><span data-stu-id="2102f-3757">ssn</span></span> 
- <span data-ttu-id="2102f-3758">述</span><span class="sxs-lookup"><span data-stu-id="2102f-3758">tin</span></span> 
- <span data-ttu-id="2102f-3759">社會保險</span><span class="sxs-lookup"><span data-stu-id="2102f-3759">social security</span></span> 
- <span data-ttu-id="2102f-3760">納稅人</span><span class="sxs-lookup"><span data-stu-id="2102f-3760">tax payer</span></span> 
- <span data-ttu-id="2102f-3761">itins</span><span class="sxs-lookup"><span data-stu-id="2102f-3761">itins</span></span> 
- <span data-ttu-id="2102f-3762">taxid</span><span class="sxs-lookup"><span data-stu-id="2102f-3762">taxid</span></span> 
- <span data-ttu-id="2102f-3763">個別納稅人</span><span class="sxs-lookup"><span data-stu-id="2102f-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="2102f-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="2102f-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="2102f-3765">License</span><span class="sxs-lookup"><span data-stu-id="2102f-3765">License</span></span> 
- <span data-ttu-id="2102f-3766">通訊</span><span class="sxs-lookup"><span data-stu-id="2102f-3766">DL</span></span> 
- <span data-ttu-id="2102f-3767">DOB</span><span class="sxs-lookup"><span data-stu-id="2102f-3767">DOB</span></span> 
- <span data-ttu-id="2102f-3768">出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-3768">Birthdate</span></span> 
- <span data-ttu-id="2102f-3769">生日</span><span class="sxs-lookup"><span data-stu-id="2102f-3769">Birthday</span></span> 
- <span data-ttu-id="2102f-3770">出生日期</span><span class="sxs-lookup"><span data-stu-id="2102f-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="2102f-3771">U.S. 社會保險號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="2102f-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="2102f-3772">格式</span><span class="sxs-lookup"><span data-stu-id="2102f-3772">Format</span></span>

<span data-ttu-id="2102f-3773">9位數, 可能是格式化或未格式化的模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="2102f-3774">如果在2011之前發行, 則 SSN 有強的格式設定, 其中的某些部分必須介於特定範圍內才能有效 (但沒有任何 checksum)。</span><span class="sxs-lookup"><span data-stu-id="2102f-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="2102f-3775">模式</span><span class="sxs-lookup"><span data-stu-id="2102f-3775">Pattern</span></span>

<span data-ttu-id="2102f-3776">四個函數在四種不同的模式中尋找主旨 ssn:</span><span class="sxs-lookup"><span data-stu-id="2102f-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="2102f-3777">Func_ssn 找到主旨 ssn, 其格式為: 以虛線或空格格式化的預先2011強格式 (ddd-dd-dddd 或 ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="2102f-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="2102f-3778">Func_unformatted_ssn 找到主旨 ssn, 且具有非格式化為9個連續數位 (ddddddddd) 的2011之前強格式設定</span><span class="sxs-lookup"><span data-stu-id="2102f-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="2102f-3779">Func_randomized_formatted_ssn 找到以虛線或空格格式化的 post 2011 主旨 ssn (ddd-dd-dddd 或 ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="2102f-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="2102f-3780">Func_randomized_unformatted_ssn 找到非格式化為九個連續數位的2011後主旨 ssn (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="2102f-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="2102f-3781">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2102f-3781">Checksum</span></span>

<span data-ttu-id="2102f-3782">否</span><span class="sxs-lookup"><span data-stu-id="2102f-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="2102f-3783">定義</span><span class="sxs-lookup"><span data-stu-id="2102f-3783">Definition</span></span>

<span data-ttu-id="2102f-3784">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 85%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3785">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3786">找到 Keyword_ssn 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2102f-3787">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 75%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3788">函數 Func_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3789">找到 Keyword_ssn 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2102f-3790">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 65%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3791">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3792">找到 Keyword_ssn 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="2102f-3793">函數 Func_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="2102f-3794">如果接近300個字元以內, 則 DLP 原則偵測到此敏感資訊類型的置信度 55%:</span><span class="sxs-lookup"><span data-stu-id="2102f-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2102f-3795">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2102f-3796">找到 Keyword_ssn 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="2102f-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="2102f-3797">函數 Func_unformatted_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2102f-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2102f-3798">關鍵字</span><span class="sxs-lookup"><span data-stu-id="2102f-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="2102f-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="2102f-3799">Keyword_ssn</span></span>

- <span data-ttu-id="2102f-3800">社會保險</span><span class="sxs-lookup"><span data-stu-id="2102f-3800">Social Security</span></span> 
- <span data-ttu-id="2102f-3801">社交安全性 #</span><span class="sxs-lookup"><span data-stu-id="2102f-3801">Social Security#</span></span> 
- <span data-ttu-id="2102f-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="2102f-3802">Soc Sec</span></span> 
- <span data-ttu-id="2102f-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="2102f-3803">SSN</span></span> 
- <span data-ttu-id="2102f-3804">主旨 SSN</span><span class="sxs-lookup"><span data-stu-id="2102f-3804">SSNS</span></span> 
- <span data-ttu-id="2102f-3805">SSN</span><span class="sxs-lookup"><span data-stu-id="2102f-3805">SSN#</span></span> 
- <span data-ttu-id="2102f-3806">SS</span><span class="sxs-lookup"><span data-stu-id="2102f-3806">SS#</span></span> 
- <span data-ttu-id="2102f-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="2102f-3807">SSID</span></span> 
   

