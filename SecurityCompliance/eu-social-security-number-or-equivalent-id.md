---
title: 歐盟社會安全號碼或對等資格識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟社會安全號碼或對等識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: abcefb6930e9c02d2f32d84b65accfecf1e20d95
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216523"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="52745-104">歐盟社會安全號碼或對等資格識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="52745-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="52745-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="52745-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="52745-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="52745-108">格式</span><span class="sxs-lookup"><span data-stu-id="52745-108">Format</span></span>

<span data-ttu-id="52745-109">指定之格式的 10 位數字</span><span class="sxs-lookup"><span data-stu-id="52745-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-110">模式</span><span class="sxs-lookup"><span data-stu-id="52745-110">Pattern</span></span>

<span data-ttu-id="52745-111">10 位數：</span><span class="sxs-lookup"><span data-stu-id="52745-111">10 digits:</span></span>
  
-  <span data-ttu-id="52745-112">會對應到序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="52745-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="52745-113">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="52745-113">One check digit</span></span>
    
- <span data-ttu-id="52745-114">會對應至出生日期 (DDMMYY) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="52745-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52745-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-115">Checksum</span></span>

<span data-ttu-id="52745-116">是</span><span class="sxs-lookup"><span data-stu-id="52745-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-117">定義</span><span class="sxs-lookup"><span data-stu-id="52745-117">Definition</span></span>

<span data-ttu-id="52745-118">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-119">此函數`Func_austria_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-120">從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-121">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-122">此函數`Func_austria_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="52745-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-125">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="52745-125">social security no</span></span>
  
<span data-ttu-id="52745-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="52745-126">social security number</span></span>
  
<span data-ttu-id="52745-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="52745-127">social security code</span></span>
  
<span data-ttu-id="52745-128">保險數目</span><span class="sxs-lookup"><span data-stu-id="52745-128">insurance number</span></span>
  
<span data-ttu-id="52745-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="52745-129">austrian ssn</span></span>
  
<span data-ttu-id="52745-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="52745-130">ssn#</span></span>
  
<span data-ttu-id="52745-131">ssn</span><span class="sxs-lookup"><span data-stu-id="52745-131">ssn</span></span>
  
<span data-ttu-id="52745-132">保險程式碼</span><span class="sxs-lookup"><span data-stu-id="52745-132">insurance code</span></span>
  
<span data-ttu-id="52745-133">保險程式碼 #</span><span class="sxs-lookup"><span data-stu-id="52745-133">insurance code#</span></span>
  
<span data-ttu-id="52745-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="52745-134">socialsecurityno#</span></span>
  
<span data-ttu-id="52745-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="52745-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="52745-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="52745-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="52745-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="52745-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="52745-138">比利時</span><span class="sxs-lookup"><span data-stu-id="52745-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="52745-139">格式</span><span class="sxs-lookup"><span data-stu-id="52745-139">Format</span></span>

<span data-ttu-id="52745-140">不含空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="52745-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-141">模式</span><span class="sxs-lookup"><span data-stu-id="52745-141">Pattern</span></span>

<span data-ttu-id="52745-142">11 位數</span><span class="sxs-lookup"><span data-stu-id="52745-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52745-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-143">Checksum</span></span>

<span data-ttu-id="52745-144">是</span><span class="sxs-lookup"><span data-stu-id="52745-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-145">定義</span><span class="sxs-lookup"><span data-stu-id="52745-145">Definition</span></span>

<span data-ttu-id="52745-146">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-147">此函數`Func_belgium_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-148">從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-149">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-150">此函數`Func_belgium_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="52745-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-153">比利時國際號碼</span><span class="sxs-lookup"><span data-stu-id="52745-153">belgian national number</span></span>
  
<span data-ttu-id="52745-154">國際號碼</span><span class="sxs-lookup"><span data-stu-id="52745-154">national number</span></span>
  
<span data-ttu-id="52745-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="52745-155">social security number</span></span>
  
<span data-ttu-id="52745-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-156">nationalnumber#</span></span>
  
<span data-ttu-id="52745-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="52745-157">ssn#</span></span>
  
<span data-ttu-id="52745-158">ssn</span><span class="sxs-lookup"><span data-stu-id="52745-158">ssn</span></span>
  
<span data-ttu-id="52745-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="52745-159">nationalnumber</span></span>
  
<span data-ttu-id="52745-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="52745-160">bnn#</span></span>
  
<span data-ttu-id="52745-161">bnn</span><span class="sxs-lookup"><span data-stu-id="52745-161">bnn</span></span>
  
<span data-ttu-id="52745-162">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-162">personal id number</span></span>
  
<span data-ttu-id="52745-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-163">personalidnumber#</span></span>
  
<span data-ttu-id="52745-164">國際 numéro</span><span class="sxs-lookup"><span data-stu-id="52745-164">numéro national</span></span>
  
<span data-ttu-id="52745-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="52745-165">numéro de sécurité</span></span>
  
<span data-ttu-id="52745-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="52745-166">numéro d'assuré</span></span>
  
<span data-ttu-id="52745-167">國際 identifiant</span><span class="sxs-lookup"><span data-stu-id="52745-167">identifiant national</span></span>
  
<span data-ttu-id="52745-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="52745-168">identifiantnational#</span></span>
  
<span data-ttu-id="52745-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="52745-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="52745-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="52745-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="52745-171">格式</span><span class="sxs-lookup"><span data-stu-id="52745-171">Format</span></span>

<span data-ttu-id="52745-172">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="52745-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-173">模式</span><span class="sxs-lookup"><span data-stu-id="52745-173">Pattern</span></span>

 <span data-ttu-id="52745-174">11 位數：</span><span class="sxs-lookup"><span data-stu-id="52745-174">11 digits:</span></span> 
  
-  <span data-ttu-id="52745-175">十位數</span><span class="sxs-lookup"><span data-stu-id="52745-175">Ten digits</span></span> 
    
- <span data-ttu-id="52745-176">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="52745-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52745-177">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-177">Checksum</span></span>

<span data-ttu-id="52745-178">是</span><span class="sxs-lookup"><span data-stu-id="52745-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-179">定義</span><span class="sxs-lookup"><span data-stu-id="52745-179">Definition</span></span>

<span data-ttu-id="52745-180">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-181">此函數`Func_croatia_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-182">從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-183">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-184">此函數`Func_croatia_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="52745-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-187">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-187">personal identification number</span></span>
  
<span data-ttu-id="52745-188">主要市民數</span><span class="sxs-lookup"><span data-stu-id="52745-188">master citizen number</span></span>
  
<span data-ttu-id="52745-189">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-189">national identification number</span></span>
  
<span data-ttu-id="52745-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="52745-190">social security number</span></span>
  
<span data-ttu-id="52745-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-191">nationalnumber#</span></span>
  
<span data-ttu-id="52745-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="52745-192">ssn#</span></span>
  
<span data-ttu-id="52745-193">ssn</span><span class="sxs-lookup"><span data-stu-id="52745-193">ssn</span></span>
  
<span data-ttu-id="52745-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="52745-194">nationalnumber</span></span>
  
<span data-ttu-id="52745-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="52745-195">bnn#</span></span>
  
<span data-ttu-id="52745-196">bnn</span><span class="sxs-lookup"><span data-stu-id="52745-196">bnn</span></span>
  
<span data-ttu-id="52745-197">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-197">personal id number</span></span>
  
<span data-ttu-id="52745-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-198">personalidnumber#</span></span>
  
<span data-ttu-id="52745-199">oib</span><span class="sxs-lookup"><span data-stu-id="52745-199">oib</span></span>
  
<span data-ttu-id="52745-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="52745-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="52745-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="52745-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="52745-202">格式</span><span class="sxs-lookup"><span data-stu-id="52745-202">Format</span></span>

<span data-ttu-id="52745-203">十位數和中指定的型態反斜線</span><span class="sxs-lookup"><span data-stu-id="52745-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-204">模式</span><span class="sxs-lookup"><span data-stu-id="52745-204">Pattern</span></span>

<span data-ttu-id="52745-205">十位數和反斜線：</span><span class="sxs-lookup"><span data-stu-id="52745-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="52745-206">會對應至出生日期 (YYMMDD) 的六個位數：</span><span class="sxs-lookup"><span data-stu-id="52745-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="52745-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="52745-207">A backslash</span></span>
    
- <span data-ttu-id="52745-208">會對應至分隔人員出生日期相同的序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="52745-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="52745-209">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="52745-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52745-210">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-210">Checksum</span></span>

<span data-ttu-id="52745-211">是</span><span class="sxs-lookup"><span data-stu-id="52745-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-212">定義</span><span class="sxs-lookup"><span data-stu-id="52745-212">Definition</span></span>

<span data-ttu-id="52745-213">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-214">此函數`Func_czech_republic_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-215">從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-216">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-217">此函數`Func_czech_republic_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="52745-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-220">出生數目</span><span class="sxs-lookup"><span data-stu-id="52745-220">birth number</span></span>
  
<span data-ttu-id="52745-221">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-221">national identification number</span></span>
  
<span data-ttu-id="52745-222">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-222">personal identification number</span></span>
  
<span data-ttu-id="52745-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="52745-223">social security number</span></span>
  
<span data-ttu-id="52745-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-224">nationalnumber#</span></span>
  
<span data-ttu-id="52745-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="52745-225">ssn#</span></span>
  
<span data-ttu-id="52745-226">ssn</span><span class="sxs-lookup"><span data-stu-id="52745-226">ssn</span></span>
  
<span data-ttu-id="52745-227">國際號碼</span><span class="sxs-lookup"><span data-stu-id="52745-227">national number</span></span>
  
<span data-ttu-id="52745-228">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-228">personal id number</span></span>
  
<span data-ttu-id="52745-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-229">personalidnumber#</span></span>
  
<span data-ttu-id="52745-230">rč</span><span class="sxs-lookup"><span data-stu-id="52745-230">rč</span></span>
  
<span data-ttu-id="52745-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="52745-231">rodné číslo</span></span>
  
<span data-ttu-id="52745-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="52745-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="52745-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="52745-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="52745-234">格式</span><span class="sxs-lookup"><span data-stu-id="52745-234">Format</span></span>

<span data-ttu-id="52745-235">十位數和中指定的型態連字號</span><span class="sxs-lookup"><span data-stu-id="52745-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-236">模式</span><span class="sxs-lookup"><span data-stu-id="52745-236">Pattern</span></span>

<span data-ttu-id="52745-237">十位數和連字號：</span><span class="sxs-lookup"><span data-stu-id="52745-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="52745-238">會對應至出生日期 (DDMMYY) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="52745-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="52745-239">一個連字號</span><span class="sxs-lookup"><span data-stu-id="52745-239">A hyphen</span></span>
    
- <span data-ttu-id="52745-240">會對應到序號的四位數</span><span class="sxs-lookup"><span data-stu-id="52745-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52745-241">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-241">Checksum</span></span>

<span data-ttu-id="52745-242">是</span><span class="sxs-lookup"><span data-stu-id="52745-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-243">定義</span><span class="sxs-lookup"><span data-stu-id="52745-243">Definition</span></span>

<span data-ttu-id="52745-244">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-245">此函數`Func_denmark_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-246">從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-247">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-248">此函數`Func_denmark_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="52745-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-251">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-251">personal identification number</span></span>
  
<span data-ttu-id="52745-252">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-252">national identification number</span></span>
  
<span data-ttu-id="52745-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="52745-253">social security number</span></span>
  
<span data-ttu-id="52745-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-254">nationalnumber#</span></span>
  
<span data-ttu-id="52745-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="52745-255">ssn#</span></span>
  
<span data-ttu-id="52745-256">ssn</span><span class="sxs-lookup"><span data-stu-id="52745-256">ssn</span></span>
  
<span data-ttu-id="52745-257">國際號碼</span><span class="sxs-lookup"><span data-stu-id="52745-257">national number</span></span>
  
<span data-ttu-id="52745-258">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-258">personal id number</span></span>
  
<span data-ttu-id="52745-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-259">personalidnumber#</span></span>
  
<span data-ttu-id="52745-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="52745-260">cpr-nummer</span></span>
  
<span data-ttu-id="52745-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="52745-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="52745-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="52745-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="52745-263">格式</span><span class="sxs-lookup"><span data-stu-id="52745-263">Format</span></span>

<span data-ttu-id="52745-264">以指定的格式 11 個字元組合</span><span class="sxs-lookup"><span data-stu-id="52745-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-265">模式</span><span class="sxs-lookup"><span data-stu-id="52745-265">Pattern</span></span>

<span data-ttu-id="52745-266">以指定的格式 11 個字元組合：</span><span class="sxs-lookup"><span data-stu-id="52745-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="52745-267">六位數</span><span class="sxs-lookup"><span data-stu-id="52745-267">Six digits</span></span> 
    
- <span data-ttu-id="52745-268">一個執行個體其中一項：</span><span class="sxs-lookup"><span data-stu-id="52745-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="52745-269">加上符號</span><span class="sxs-lookup"><span data-stu-id="52745-269">Plus symbol</span></span>
    
  - <span data-ttu-id="52745-270">減去符號</span><span class="sxs-lookup"><span data-stu-id="52745-270">Minus symbol</span></span>
    
  - <span data-ttu-id="52745-271">字母"A"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="52745-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="52745-272">三位數</span><span class="sxs-lookup"><span data-stu-id="52745-272">Three digits</span></span>
    
- <span data-ttu-id="52745-273">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="52745-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52745-274">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-274">Checksum</span></span>

<span data-ttu-id="52745-275">是</span><span class="sxs-lookup"><span data-stu-id="52745-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-276">定義</span><span class="sxs-lookup"><span data-stu-id="52745-276">Definition</span></span>

<span data-ttu-id="52745-277">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-278">此函數`Func_finland_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-279">從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-280">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-281">此函數`Func_finland_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="52745-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="52745-284">identification number</span></span>
  
<span data-ttu-id="52745-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-285">personal id</span></span>
  
<span data-ttu-id="52745-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="52745-286">identity number</span></span>
  
<span data-ttu-id="52745-287">芬蘭國家識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-287">finnish national id number</span></span>
  
<span data-ttu-id="52745-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="52745-288">personalidnumber#</span></span>
  
<span data-ttu-id="52745-289">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-289">national identification number</span></span>
  
<span data-ttu-id="52745-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-290">id number</span></span>
  
<span data-ttu-id="52745-291">國家識別碼沒有。</span><span class="sxs-lookup"><span data-stu-id="52745-291">national id no.</span></span>
  
<span data-ttu-id="52745-292">國家識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-292">national id number</span></span>
  
<span data-ttu-id="52745-293">識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="52745-293">id no</span></span>
  
<span data-ttu-id="52745-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="52745-294">tunnistenumero</span></span>
  
<span data-ttu-id="52745-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="52745-295">henkilötunnus</span></span>
  
<span data-ttu-id="52745-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="52745-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="52745-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="52745-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="52745-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="52745-298">identiteetti numero</span></span>
  
<span data-ttu-id="52745-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="52745-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="52745-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="52745-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="52745-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="52745-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="52745-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="52745-302">tunnusnumero</span></span>
  
<span data-ttu-id="52745-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="52745-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="52745-304">hetu</span><span class="sxs-lookup"><span data-stu-id="52745-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="52745-305">法國</span><span class="sxs-lookup"><span data-stu-id="52745-305">France</span></span>

<span data-ttu-id="52745-306">如需詳細資訊，請參閱節"法國社會安全號碼 (INSEE)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="52745-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="52745-307">德國</span><span class="sxs-lookup"><span data-stu-id="52745-307">Germany</span></span>

<span data-ttu-id="52745-308">如需詳細資訊，請參閱節"德國識別卡 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="52745-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="52745-309">希臘</span><span class="sxs-lookup"><span data-stu-id="52745-309">Greece</span></span>

<span data-ttu-id="52745-310">如需詳細資訊，請參閱節"希臘國家識別碼卡片"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="52745-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="52745-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="52745-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="52745-312">格式</span><span class="sxs-lookup"><span data-stu-id="52745-312">Format</span></span>

<span data-ttu-id="52745-313">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="52745-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-314">模式</span><span class="sxs-lookup"><span data-stu-id="52745-314">Pattern</span></span>

<span data-ttu-id="52745-315">九位數</span><span class="sxs-lookup"><span data-stu-id="52745-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52745-316">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-316">Checksum</span></span>

<span data-ttu-id="52745-317">是</span><span class="sxs-lookup"><span data-stu-id="52745-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-318">定義</span><span class="sxs-lookup"><span data-stu-id="52745-318">Definition</span></span>

<span data-ttu-id="52745-319">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-320">此函數`Func_hungary_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-321">從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-322">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-323">此函數`Func_hungary_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="52745-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-326">匈牙利文社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="52745-326">hungarian social security number</span></span>
  
<span data-ttu-id="52745-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="52745-327">social security number</span></span>
  
<span data-ttu-id="52745-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="52745-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="52745-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="52745-329">hssn#</span></span>
  
<span data-ttu-id="52745-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="52745-330">socialsecuritynno</span></span>
  
<span data-ttu-id="52745-331">hssn</span><span class="sxs-lookup"><span data-stu-id="52745-331">hssn</span></span>
  
<span data-ttu-id="52745-332">泰</span><span class="sxs-lookup"><span data-stu-id="52745-332">taj</span></span>
  
<span data-ttu-id="52745-333">泰 #</span><span class="sxs-lookup"><span data-stu-id="52745-333">taj#</span></span>
  
<span data-ttu-id="52745-334">ssn</span><span class="sxs-lookup"><span data-stu-id="52745-334">ssn</span></span>
  
<span data-ttu-id="52745-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="52745-335">ssn#</span></span>
  
<span data-ttu-id="52745-336">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="52745-336">social security no</span></span>
  
<span data-ttu-id="52745-337">áfa</span><span class="sxs-lookup"><span data-stu-id="52745-337">áfa</span></span>
  
<span data-ttu-id="52745-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="52745-338">közösségi adószám</span></span>
  
<span data-ttu-id="52745-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="52745-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="52745-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="52745-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="52745-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="52745-341">áfa szám</span></span>
  
<span data-ttu-id="52745-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="52745-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="52745-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="52745-343">Portugal</span></span>

<span data-ttu-id="52745-344">如需詳細資訊，請參閱節"葡萄牙市民卡卡號"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="52745-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="52745-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="52745-345">Spain</span></span>

<span data-ttu-id="52745-346">如需詳細資訊，請參閱節"西班牙社會安全號碼 (SSN)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="52745-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="52745-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="52745-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="52745-348">格式</span><span class="sxs-lookup"><span data-stu-id="52745-348">Format</span></span>

<span data-ttu-id="52745-349">12 的數字不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="52745-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52745-350">模式</span><span class="sxs-lookup"><span data-stu-id="52745-350">Pattern</span></span>

<span data-ttu-id="52745-351">12 位數：</span><span class="sxs-lookup"><span data-stu-id="52745-351">12 digits:</span></span>
  
-  <span data-ttu-id="52745-352">八個對應至出生日期 (YYYYMMDD) 的數字</span><span class="sxs-lookup"><span data-stu-id="52745-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="52745-353">會對應到序號的三個字其中：</span><span class="sxs-lookup"><span data-stu-id="52745-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="52745-354">序號中的最後一個數字表示性別因 2 男為奇數和偶數女性的工作分派</span><span class="sxs-lookup"><span data-stu-id="52745-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="52745-355">序號的工作分派至郡號碼的承載出生或是 （如果出生之前 1947年），所通信最多個 1990，其中他有已住，根據稅記錄 1947 年 1 月 1 上具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants</span><span class="sxs-lookup"><span data-stu-id="52745-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="52745-356">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="52745-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52745-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="52745-357">Checksum</span></span>

<span data-ttu-id="52745-358">是</span><span class="sxs-lookup"><span data-stu-id="52745-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52745-359">定義</span><span class="sxs-lookup"><span data-stu-id="52745-359">Definition</span></span>

<span data-ttu-id="52745-360">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="52745-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-361">此函數`Func_sweden_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52745-362">從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="52745-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="52745-363">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="52745-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52745-364">此函數`Func_sweden_eu_ssn_or_equivalent`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="52745-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52745-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="52745-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="52745-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="52745-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="52745-367">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="52745-367">personal id number</span></span>
  
<span data-ttu-id="52745-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="52745-368">identification number</span></span>
  
<span data-ttu-id="52745-369">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="52745-369">personal id no</span></span>
  
<span data-ttu-id="52745-370">identity 為無</span><span class="sxs-lookup"><span data-stu-id="52745-370">identity no</span></span>
  
<span data-ttu-id="52745-371">識別任何</span><span class="sxs-lookup"><span data-stu-id="52745-371">identification no</span></span>
  
<span data-ttu-id="52745-372">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="52745-372">personal identification no</span></span>
  
<span data-ttu-id="52745-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="52745-373">personnummer id</span></span>
  
<span data-ttu-id="52745-374">personligt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="52745-374">personligt id-nummer</span></span>
  
<span data-ttu-id="52745-375">unikt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="52745-375">unikt id-nummer</span></span>
  
<span data-ttu-id="52745-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="52745-376">personnummer</span></span>
  
<span data-ttu-id="52745-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="52745-377">identifikationsnumret</span></span>
  
<span data-ttu-id="52745-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="52745-378">personnummer#</span></span>
  
<span data-ttu-id="52745-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="52745-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52745-380">另請參閱</span><span class="sxs-lookup"><span data-stu-id="52745-380">See also</span></span>

[<span data-ttu-id="52745-381">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="52745-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

