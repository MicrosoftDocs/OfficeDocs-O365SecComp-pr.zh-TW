---
title: 歐盟社會安全號碼或對等項目識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼或對等識別碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410798"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="4adc4-104">歐盟社會安全號碼或對等項目識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="4adc4-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4adc4-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="4adc4-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="4adc4-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="4adc4-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="4adc4-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-108">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-108">Format</span></span>

<span data-ttu-id="4adc4-109">10 位數，代表指定之格式</span><span class="sxs-lookup"><span data-stu-id="4adc4-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-110">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-110">Pattern</span></span>

<span data-ttu-id="4adc4-111">10 位數：</span><span class="sxs-lookup"><span data-stu-id="4adc4-111">10 digits:</span></span>
  
-  <span data-ttu-id="4adc4-112">會對應至序號的三位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="4adc4-113">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-113">One check digit</span></span>
    
- <span data-ttu-id="4adc4-114">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4adc4-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-115">Checksum</span></span>

<span data-ttu-id="4adc4-116">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-117">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-117">Definition</span></span>

<span data-ttu-id="4adc4-118">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-119">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-120">從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-121">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-122">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="4adc4-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-125">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="4adc4-125">social security no</span></span>
  
<span data-ttu-id="4adc4-126">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-126">social security number</span></span>
  
<span data-ttu-id="4adc4-127">社會安全的程式碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-127">social security code</span></span>
  
<span data-ttu-id="4adc4-128">保險號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-128">insurance number</span></span>
  
<span data-ttu-id="4adc4-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-129">austrian ssn</span></span>
  
<span data-ttu-id="4adc4-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-130">ssn#</span></span>
  
<span data-ttu-id="4adc4-131">ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-131">ssn</span></span>
  
<span data-ttu-id="4adc4-132">保險程式碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-132">insurance code</span></span>
  
<span data-ttu-id="4adc4-133">保險程式碼 #</span><span class="sxs-lookup"><span data-stu-id="4adc4-133">insurance code#</span></span>
  
<span data-ttu-id="4adc4-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="4adc4-134">socialsecurityno#</span></span>
  
<span data-ttu-id="4adc4-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="4adc4-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="4adc4-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="4adc4-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="4adc4-138">比利時</span><span class="sxs-lookup"><span data-stu-id="4adc4-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-139">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-139">Format</span></span>

<span data-ttu-id="4adc4-140">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="4adc4-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-141">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-141">Pattern</span></span>

<span data-ttu-id="4adc4-142">11 位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4adc4-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-143">Checksum</span></span>

<span data-ttu-id="4adc4-144">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-145">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-145">Definition</span></span>

<span data-ttu-id="4adc4-146">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-147">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-148">從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-149">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-150">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="4adc4-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-153">比利時國民身分的數字</span><span class="sxs-lookup"><span data-stu-id="4adc4-153">belgian national number</span></span>
  
<span data-ttu-id="4adc4-154">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-154">national number</span></span>
  
<span data-ttu-id="4adc4-155">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-155">social security number</span></span>
  
<span data-ttu-id="4adc4-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-156">nationalnumber#</span></span>
  
<span data-ttu-id="4adc4-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-157">ssn#</span></span>
  
<span data-ttu-id="4adc4-158">ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-158">ssn</span></span>
  
<span data-ttu-id="4adc4-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="4adc4-159">nationalnumber</span></span>
  
<span data-ttu-id="4adc4-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-160">bnn#</span></span>
  
<span data-ttu-id="4adc4-161">bnn</span><span class="sxs-lookup"><span data-stu-id="4adc4-161">bnn</span></span>
  
<span data-ttu-id="4adc4-162">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-162">personal id number</span></span>
  
<span data-ttu-id="4adc4-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-163">personalidnumber#</span></span>
  
<span data-ttu-id="4adc4-164">numéro 國際電話</span><span class="sxs-lookup"><span data-stu-id="4adc4-164">numéro national</span></span>
  
<span data-ttu-id="4adc4-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="4adc4-165">numéro de sécurité</span></span>
  
<span data-ttu-id="4adc4-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="4adc4-166">numéro d'assuré</span></span>
  
<span data-ttu-id="4adc4-167">identifiant 國際電話</span><span class="sxs-lookup"><span data-stu-id="4adc4-167">identifiant national</span></span>
  
<span data-ttu-id="4adc4-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="4adc4-168">identifiantnational#</span></span>
  
<span data-ttu-id="4adc4-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="4adc4-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="4adc4-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="4adc4-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-171">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-171">Format</span></span>

<span data-ttu-id="4adc4-172">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="4adc4-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-173">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-173">Pattern</span></span>

 <span data-ttu-id="4adc4-174">11 位數：</span><span class="sxs-lookup"><span data-stu-id="4adc4-174">11 digits:</span></span> 
  
-  <span data-ttu-id="4adc4-175">十位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-175">Ten digits</span></span> 
    
- <span data-ttu-id="4adc4-176">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4adc4-177">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-177">Checksum</span></span>

<span data-ttu-id="4adc4-178">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-179">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-179">Definition</span></span>

<span data-ttu-id="4adc4-180">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-181">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-182">從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-183">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-184">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="4adc4-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-187">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-187">personal identification number</span></span>
  
<span data-ttu-id="4adc4-188">主版公民數目</span><span class="sxs-lookup"><span data-stu-id="4adc4-188">master citizen number</span></span>
  
<span data-ttu-id="4adc4-189">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-189">national identification number</span></span>
  
<span data-ttu-id="4adc4-190">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-190">social security number</span></span>
  
<span data-ttu-id="4adc4-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-191">nationalnumber#</span></span>
  
<span data-ttu-id="4adc4-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-192">ssn#</span></span>
  
<span data-ttu-id="4adc4-193">ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-193">ssn</span></span>
  
<span data-ttu-id="4adc4-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="4adc4-194">nationalnumber</span></span>
  
<span data-ttu-id="4adc4-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-195">bnn#</span></span>
  
<span data-ttu-id="4adc4-196">bnn</span><span class="sxs-lookup"><span data-stu-id="4adc4-196">bnn</span></span>
  
<span data-ttu-id="4adc4-197">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-197">personal id number</span></span>
  
<span data-ttu-id="4adc4-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-198">personalidnumber#</span></span>
  
<span data-ttu-id="4adc4-199">oib 碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-199">oib</span></span>
  
<span data-ttu-id="4adc4-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="4adc4-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="4adc4-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="4adc4-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-202">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-202">Format</span></span>

<span data-ttu-id="4adc4-203">十個數字和中指定的型態的反斜線</span><span class="sxs-lookup"><span data-stu-id="4adc4-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-204">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-204">Pattern</span></span>

<span data-ttu-id="4adc4-205">十位數和一個反斜線：</span><span class="sxs-lookup"><span data-stu-id="4adc4-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="4adc4-206">會對應至 (YYMMDD) 的出生日期的六位數：</span><span class="sxs-lookup"><span data-stu-id="4adc4-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="4adc4-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="4adc4-207">A backslash</span></span>
    
- <span data-ttu-id="4adc4-208">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="4adc4-209">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4adc4-210">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-210">Checksum</span></span>

<span data-ttu-id="4adc4-211">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-212">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-212">Definition</span></span>

<span data-ttu-id="4adc4-213">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-214">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-215">從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-216">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-217">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="4adc4-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-220">出生數目</span><span class="sxs-lookup"><span data-stu-id="4adc4-220">birth number</span></span>
  
<span data-ttu-id="4adc4-221">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-221">national identification number</span></span>
  
<span data-ttu-id="4adc4-222">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-222">personal identification number</span></span>
  
<span data-ttu-id="4adc4-223">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-223">social security number</span></span>
  
<span data-ttu-id="4adc4-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-224">nationalnumber#</span></span>
  
<span data-ttu-id="4adc4-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-225">ssn#</span></span>
  
<span data-ttu-id="4adc4-226">ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-226">ssn</span></span>
  
<span data-ttu-id="4adc4-227">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-227">national number</span></span>
  
<span data-ttu-id="4adc4-228">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-228">personal id number</span></span>
  
<span data-ttu-id="4adc4-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-229">personalidnumber#</span></span>
  
<span data-ttu-id="4adc4-230">rč</span><span class="sxs-lookup"><span data-stu-id="4adc4-230">rč</span></span>
  
<span data-ttu-id="4adc4-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="4adc4-231">rodné číslo</span></span>
  
<span data-ttu-id="4adc4-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="4adc4-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="4adc4-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="4adc4-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-234">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-234">Format</span></span>

<span data-ttu-id="4adc4-235">十個數字和中指定的型態連字號</span><span class="sxs-lookup"><span data-stu-id="4adc4-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-236">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-236">Pattern</span></span>

<span data-ttu-id="4adc4-237">十位數，並連字號：</span><span class="sxs-lookup"><span data-stu-id="4adc4-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="4adc4-238">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="4adc4-239">連字號</span><span class="sxs-lookup"><span data-stu-id="4adc4-239">A hyphen</span></span>
    
- <span data-ttu-id="4adc4-240">會對應至序號的四位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4adc4-241">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-241">Checksum</span></span>

<span data-ttu-id="4adc4-242">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-243">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-243">Definition</span></span>

<span data-ttu-id="4adc4-244">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-245">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-246">從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-247">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-248">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="4adc4-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-251">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-251">personal identification number</span></span>
  
<span data-ttu-id="4adc4-252">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-252">national identification number</span></span>
  
<span data-ttu-id="4adc4-253">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-253">social security number</span></span>
  
<span data-ttu-id="4adc4-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-254">nationalnumber#</span></span>
  
<span data-ttu-id="4adc4-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-255">ssn#</span></span>
  
<span data-ttu-id="4adc4-256">ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-256">ssn</span></span>
  
<span data-ttu-id="4adc4-257">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-257">national number</span></span>
  
<span data-ttu-id="4adc4-258">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-258">personal id number</span></span>
  
<span data-ttu-id="4adc4-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-259">personalidnumber#</span></span>
  
<span data-ttu-id="4adc4-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-260">cpr-nummer</span></span>
  
<span data-ttu-id="4adc4-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="4adc4-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="4adc4-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-263">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-263">Format</span></span>

<span data-ttu-id="4adc4-264">11 個字元組合，以指定的格式</span><span class="sxs-lookup"><span data-stu-id="4adc4-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-265">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-265">Pattern</span></span>

<span data-ttu-id="4adc4-266">以指定的格式 11 個字元組合：</span><span class="sxs-lookup"><span data-stu-id="4adc4-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="4adc4-267">六位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-267">Six digits</span></span> 
    
- <span data-ttu-id="4adc4-268">實例的其中一項：</span><span class="sxs-lookup"><span data-stu-id="4adc4-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="4adc4-269">加上符號</span><span class="sxs-lookup"><span data-stu-id="4adc4-269">Plus symbol</span></span>
    
  - <span data-ttu-id="4adc4-270">減號</span><span class="sxs-lookup"><span data-stu-id="4adc4-270">Minus symbol</span></span>
    
  - <span data-ttu-id="4adc4-271">字母"A"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4adc4-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="4adc4-272">三位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-272">Three digits</span></span>
    
- <span data-ttu-id="4adc4-273">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="4adc4-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4adc4-274">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-274">Checksum</span></span>

<span data-ttu-id="4adc4-275">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-276">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-276">Definition</span></span>

<span data-ttu-id="4adc4-277">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-278">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-279">從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-280">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-281">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="4adc4-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-284">識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-284">identification number</span></span>
  
<span data-ttu-id="4adc4-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-285">personal id</span></span>
  
<span data-ttu-id="4adc4-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-286">identity number</span></span>
  
<span data-ttu-id="4adc4-287">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-287">finnish national id number</span></span>
  
<span data-ttu-id="4adc4-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-288">personalidnumber#</span></span>
  
<span data-ttu-id="4adc4-289">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-289">national identification number</span></span>
  
<span data-ttu-id="4adc4-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-290">id number</span></span>
  
<span data-ttu-id="4adc4-291">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="4adc4-291">national id no.</span></span>
  
<span data-ttu-id="4adc4-292">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-292">national id number</span></span>
  
<span data-ttu-id="4adc4-293">識別碼不</span><span class="sxs-lookup"><span data-stu-id="4adc4-293">id no</span></span>
  
<span data-ttu-id="4adc4-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="4adc4-294">tunnistenumero</span></span>
  
<span data-ttu-id="4adc4-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="4adc4-295">henkilötunnus</span></span>
  
<span data-ttu-id="4adc4-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="4adc4-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="4adc4-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="4adc4-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="4adc4-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="4adc4-298">identiteetti numero</span></span>
  
<span data-ttu-id="4adc4-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="4adc4-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="4adc4-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="4adc4-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="4adc4-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="4adc4-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="4adc4-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="4adc4-302">tunnusnumero</span></span>
  
<span data-ttu-id="4adc4-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="4adc4-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="4adc4-304">hetu</span><span class="sxs-lookup"><span data-stu-id="4adc4-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="4adc4-305">法國</span><span class="sxs-lookup"><span data-stu-id="4adc4-305">France</span></span>

<span data-ttu-id="4adc4-306">如需詳細資訊，請參閱 「 法國社會安全號碼 (INSEE) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4adc4-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="4adc4-307">德國</span><span class="sxs-lookup"><span data-stu-id="4adc4-307">Germany</span></span>

<span data-ttu-id="4adc4-308">如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4adc4-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="4adc4-309">希臘</span><span class="sxs-lookup"><span data-stu-id="4adc4-309">Greece</span></span>

<span data-ttu-id="4adc4-310">如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4adc4-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="4adc4-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="4adc4-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-312">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-312">Format</span></span>

<span data-ttu-id="4adc4-313">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-314">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-314">Pattern</span></span>

<span data-ttu-id="4adc4-315">九位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4adc4-316">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-316">Checksum</span></span>

<span data-ttu-id="4adc4-317">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-318">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-318">Definition</span></span>

<span data-ttu-id="4adc4-319">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-320">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-321">從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-322">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-323">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="4adc4-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-326">匈牙利文社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-326">hungarian social security number</span></span>
  
<span data-ttu-id="4adc4-327">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-327">social security number</span></span>
  
<span data-ttu-id="4adc4-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="4adc4-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="4adc4-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-329">hssn#</span></span>
  
<span data-ttu-id="4adc4-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="4adc4-330">socialsecuritynno</span></span>
  
<span data-ttu-id="4adc4-331">hssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-331">hssn</span></span>
  
<span data-ttu-id="4adc4-332">泰</span><span class="sxs-lookup"><span data-stu-id="4adc4-332">taj</span></span>
  
<span data-ttu-id="4adc4-333">泰 #</span><span class="sxs-lookup"><span data-stu-id="4adc4-333">taj#</span></span>
  
<span data-ttu-id="4adc4-334">ssn</span><span class="sxs-lookup"><span data-stu-id="4adc4-334">ssn</span></span>
  
<span data-ttu-id="4adc4-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="4adc4-335">ssn#</span></span>
  
<span data-ttu-id="4adc4-336">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="4adc4-336">social security no</span></span>
  
<span data-ttu-id="4adc4-337">áfa</span><span class="sxs-lookup"><span data-stu-id="4adc4-337">áfa</span></span>
  
<span data-ttu-id="4adc4-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="4adc4-338">közösségi adószám</span></span>
  
<span data-ttu-id="4adc4-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="4adc4-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="4adc4-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="4adc4-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="4adc4-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="4adc4-341">áfa szám</span></span>
  
<span data-ttu-id="4adc4-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="4adc4-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="4adc4-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="4adc4-343">Portugal</span></span>

<span data-ttu-id="4adc4-344">如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4adc4-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="4adc4-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="4adc4-345">Spain</span></span>

<span data-ttu-id="4adc4-346">如需詳細資訊，請參閱 「 西班牙社會安全號碼 (SSN) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4adc4-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="4adc4-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="4adc4-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="4adc4-348">Format</span><span class="sxs-lookup"><span data-stu-id="4adc4-348">Format</span></span>

<span data-ttu-id="4adc4-349">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4adc4-350">模式</span><span class="sxs-lookup"><span data-stu-id="4adc4-350">Pattern</span></span>

<span data-ttu-id="4adc4-351">12 位數：</span><span class="sxs-lookup"><span data-stu-id="4adc4-351">12 digits:</span></span>
  
-  <span data-ttu-id="4adc4-352">會對應至出生日期 (YYYYMMDD) 的八位數</span><span class="sxs-lookup"><span data-stu-id="4adc4-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="4adc4-353">會對應至序號的三位數其中：</span><span class="sxs-lookup"><span data-stu-id="4adc4-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="4adc4-354">序號中的最後一個數字表示性別因 1 女 2 男奇數和偶數女性的工作分派</span><span class="sxs-lookup"><span data-stu-id="4adc4-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="4adc4-355">最多 1990，工作分派的序號採納郡出生數字的承載或 （如果出生之前 1947年） 其中他有已住，根據稅務記錄上 1947 年 1 月 1，具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants</span><span class="sxs-lookup"><span data-stu-id="4adc4-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="4adc4-356">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4adc4-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-357">Checksum</span></span>

<span data-ttu-id="4adc4-358">是</span><span class="sxs-lookup"><span data-stu-id="4adc4-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4adc4-359">定義</span><span class="sxs-lookup"><span data-stu-id="4adc4-359">Definition</span></span>

<span data-ttu-id="4adc4-360">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-361">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4adc4-362">從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="4adc4-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="4adc4-363">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4adc4-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4adc4-364">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4adc4-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4adc4-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4adc4-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="4adc4-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="4adc4-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="4adc4-367">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-367">personal id number</span></span>
  
<span data-ttu-id="4adc4-368">識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-368">identification number</span></span>
  
<span data-ttu-id="4adc4-369">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="4adc4-369">personal id no</span></span>
  
<span data-ttu-id="4adc4-370">身分識別沒有</span><span class="sxs-lookup"><span data-stu-id="4adc4-370">identity no</span></span>
  
<span data-ttu-id="4adc4-371">識別任何</span><span class="sxs-lookup"><span data-stu-id="4adc4-371">identification no</span></span>
  
<span data-ttu-id="4adc4-372">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="4adc4-372">personal identification no</span></span>
  
<span data-ttu-id="4adc4-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="4adc4-373">personnummer id</span></span>
  
<span data-ttu-id="4adc4-374">personligt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-374">personligt id-nummer</span></span>
  
<span data-ttu-id="4adc4-375">unikt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-375">unikt id-nummer</span></span>
  
<span data-ttu-id="4adc4-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="4adc4-376">personnummer</span></span>
  
<span data-ttu-id="4adc4-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="4adc4-377">identifikationsnumret</span></span>
  
<span data-ttu-id="4adc4-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="4adc4-378">personnummer#</span></span>
  
<span data-ttu-id="4adc4-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="4adc4-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4adc4-380">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4adc4-380">See also</span></span>

[<span data-ttu-id="4adc4-381">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="4adc4-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

