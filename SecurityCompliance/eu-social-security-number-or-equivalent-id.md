---
title: 歐盟社會安全號碼或對等項目識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼或對等識別碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154485"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="3dcfa-104">歐盟社會安全號碼或對等項目識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="3dcfa-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="3dcfa-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3dcfa-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="3dcfa-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-108">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-108">Format</span></span>

<span data-ttu-id="3dcfa-109">10 位數，代表指定之格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-110">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-110">Pattern</span></span>

<span data-ttu-id="3dcfa-111">10 位數：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-111">10 digits:</span></span>
  
-  <span data-ttu-id="3dcfa-112">會對應至序號的三位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="3dcfa-113">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-113">One check digit</span></span>
    
- <span data-ttu-id="3dcfa-114">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3dcfa-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-115">Checksum</span></span>

<span data-ttu-id="3dcfa-116">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-117">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-117">Definition</span></span>

<span data-ttu-id="3dcfa-118">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-119">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-120">從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-121">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-122">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="3dcfa-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-125">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="3dcfa-125">social security no</span></span>
  
<span data-ttu-id="3dcfa-126">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-126">social security number</span></span>
  
<span data-ttu-id="3dcfa-127">社會安全的程式碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-127">social security code</span></span>
  
<span data-ttu-id="3dcfa-128">保險號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-128">insurance number</span></span>
  
<span data-ttu-id="3dcfa-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-129">austrian ssn</span></span>
  
<span data-ttu-id="3dcfa-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-130">ssn#</span></span>
  
<span data-ttu-id="3dcfa-131">ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-131">ssn</span></span>
  
<span data-ttu-id="3dcfa-132">保險程式碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-132">insurance code</span></span>
  
<span data-ttu-id="3dcfa-133">保險程式碼 #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-133">insurance code#</span></span>
  
<span data-ttu-id="3dcfa-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-134">socialsecurityno#</span></span>
  
<span data-ttu-id="3dcfa-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="3dcfa-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="3dcfa-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="3dcfa-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="3dcfa-138">比利時</span><span class="sxs-lookup"><span data-stu-id="3dcfa-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-139">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-139">Format</span></span>

<span data-ttu-id="3dcfa-140">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="3dcfa-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-141">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-141">Pattern</span></span>

<span data-ttu-id="3dcfa-142">11 位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3dcfa-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-143">Checksum</span></span>

<span data-ttu-id="3dcfa-144">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-145">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-145">Definition</span></span>

<span data-ttu-id="3dcfa-146">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-147">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-148">從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-149">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-150">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="3dcfa-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-153">比利時國民身分的數字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-153">belgian national number</span></span>
  
<span data-ttu-id="3dcfa-154">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-154">national number</span></span>
  
<span data-ttu-id="3dcfa-155">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-155">social security number</span></span>
  
<span data-ttu-id="3dcfa-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-156">nationalnumber#</span></span>
  
<span data-ttu-id="3dcfa-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-157">ssn#</span></span>
  
<span data-ttu-id="3dcfa-158">ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-158">ssn</span></span>
  
<span data-ttu-id="3dcfa-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="3dcfa-159">nationalnumber</span></span>
  
<span data-ttu-id="3dcfa-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-160">bnn#</span></span>
  
<span data-ttu-id="3dcfa-161">bnn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-161">bnn</span></span>
  
<span data-ttu-id="3dcfa-162">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-162">personal id number</span></span>
  
<span data-ttu-id="3dcfa-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-163">personalidnumber#</span></span>
  
<span data-ttu-id="3dcfa-164">numéro 國際電話</span><span class="sxs-lookup"><span data-stu-id="3dcfa-164">numéro national</span></span>
  
<span data-ttu-id="3dcfa-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="3dcfa-165">numéro de sécurité</span></span>
  
<span data-ttu-id="3dcfa-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="3dcfa-166">numéro d'assuré</span></span>
  
<span data-ttu-id="3dcfa-167">identifiant 國際電話</span><span class="sxs-lookup"><span data-stu-id="3dcfa-167">identifiant national</span></span>
  
<span data-ttu-id="3dcfa-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-168">identifiantnational#</span></span>
  
<span data-ttu-id="3dcfa-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="3dcfa-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="3dcfa-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-171">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-171">Format</span></span>

<span data-ttu-id="3dcfa-172">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="3dcfa-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-173">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-173">Pattern</span></span>

 <span data-ttu-id="3dcfa-174">11 位數：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-174">11 digits:</span></span> 
  
-  <span data-ttu-id="3dcfa-175">十位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-175">Ten digits</span></span> 
    
- <span data-ttu-id="3dcfa-176">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3dcfa-177">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-177">Checksum</span></span>

<span data-ttu-id="3dcfa-178">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-179">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-179">Definition</span></span>

<span data-ttu-id="3dcfa-180">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-181">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-182">從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-183">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-184">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="3dcfa-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-187">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-187">personal identification number</span></span>
  
<span data-ttu-id="3dcfa-188">主版公民數目</span><span class="sxs-lookup"><span data-stu-id="3dcfa-188">master citizen number</span></span>
  
<span data-ttu-id="3dcfa-189">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-189">national identification number</span></span>
  
<span data-ttu-id="3dcfa-190">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-190">social security number</span></span>
  
<span data-ttu-id="3dcfa-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-191">nationalnumber#</span></span>
  
<span data-ttu-id="3dcfa-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-192">ssn#</span></span>
  
<span data-ttu-id="3dcfa-193">ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-193">ssn</span></span>
  
<span data-ttu-id="3dcfa-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="3dcfa-194">nationalnumber</span></span>
  
<span data-ttu-id="3dcfa-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-195">bnn#</span></span>
  
<span data-ttu-id="3dcfa-196">bnn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-196">bnn</span></span>
  
<span data-ttu-id="3dcfa-197">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-197">personal id number</span></span>
  
<span data-ttu-id="3dcfa-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-198">personalidnumber#</span></span>
  
<span data-ttu-id="3dcfa-199">oib 碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-199">oib</span></span>
  
<span data-ttu-id="3dcfa-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="3dcfa-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="3dcfa-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="3dcfa-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-202">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-202">Format</span></span>

<span data-ttu-id="3dcfa-203">十個數字和中指定的型態的反斜線</span><span class="sxs-lookup"><span data-stu-id="3dcfa-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-204">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-204">Pattern</span></span>

<span data-ttu-id="3dcfa-205">十位數和一個反斜線：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="3dcfa-206">會對應至 (YYMMDD) 的出生日期的六位數：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="3dcfa-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="3dcfa-207">A backslash</span></span>
    
- <span data-ttu-id="3dcfa-208">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="3dcfa-209">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3dcfa-210">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-210">Checksum</span></span>

<span data-ttu-id="3dcfa-211">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-212">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-212">Definition</span></span>

<span data-ttu-id="3dcfa-213">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-214">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-215">從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-216">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-217">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="3dcfa-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-220">出生數目</span><span class="sxs-lookup"><span data-stu-id="3dcfa-220">birth number</span></span>
  
<span data-ttu-id="3dcfa-221">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-221">national identification number</span></span>
  
<span data-ttu-id="3dcfa-222">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-222">personal identification number</span></span>
  
<span data-ttu-id="3dcfa-223">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-223">social security number</span></span>
  
<span data-ttu-id="3dcfa-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-224">nationalnumber#</span></span>
  
<span data-ttu-id="3dcfa-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-225">ssn#</span></span>
  
<span data-ttu-id="3dcfa-226">ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-226">ssn</span></span>
  
<span data-ttu-id="3dcfa-227">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-227">national number</span></span>
  
<span data-ttu-id="3dcfa-228">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-228">personal id number</span></span>
  
<span data-ttu-id="3dcfa-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-229">personalidnumber#</span></span>
  
<span data-ttu-id="3dcfa-230">rč</span><span class="sxs-lookup"><span data-stu-id="3dcfa-230">rč</span></span>
  
<span data-ttu-id="3dcfa-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="3dcfa-231">rodné číslo</span></span>
  
<span data-ttu-id="3dcfa-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="3dcfa-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="3dcfa-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="3dcfa-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-234">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-234">Format</span></span>

<span data-ttu-id="3dcfa-235">十個數字和中指定的型態連字號</span><span class="sxs-lookup"><span data-stu-id="3dcfa-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-236">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-236">Pattern</span></span>

<span data-ttu-id="3dcfa-237">十位數，並連字號：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="3dcfa-238">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="3dcfa-239">連字號</span><span class="sxs-lookup"><span data-stu-id="3dcfa-239">A hyphen</span></span>
    
- <span data-ttu-id="3dcfa-240">會對應至序號的四位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3dcfa-241">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-241">Checksum</span></span>

<span data-ttu-id="3dcfa-242">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-243">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-243">Definition</span></span>

<span data-ttu-id="3dcfa-244">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-245">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-246">從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-247">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-248">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="3dcfa-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-251">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-251">personal identification number</span></span>
  
<span data-ttu-id="3dcfa-252">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-252">national identification number</span></span>
  
<span data-ttu-id="3dcfa-253">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-253">social security number</span></span>
  
<span data-ttu-id="3dcfa-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-254">nationalnumber#</span></span>
  
<span data-ttu-id="3dcfa-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-255">ssn#</span></span>
  
<span data-ttu-id="3dcfa-256">ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-256">ssn</span></span>
  
<span data-ttu-id="3dcfa-257">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-257">national number</span></span>
  
<span data-ttu-id="3dcfa-258">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-258">personal id number</span></span>
  
<span data-ttu-id="3dcfa-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-259">personalidnumber#</span></span>
  
<span data-ttu-id="3dcfa-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-260">cpr-nummer</span></span>
  
<span data-ttu-id="3dcfa-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="3dcfa-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="3dcfa-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-263">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-263">Format</span></span>

<span data-ttu-id="3dcfa-264">11 個字元組合，以指定的格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-265">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-265">Pattern</span></span>

<span data-ttu-id="3dcfa-266">以指定的格式 11 個字元組合：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="3dcfa-267">六位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-267">Six digits</span></span> 
    
- <span data-ttu-id="3dcfa-268">實例的其中一項：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="3dcfa-269">加上符號</span><span class="sxs-lookup"><span data-stu-id="3dcfa-269">Plus symbol</span></span>
    
  - <span data-ttu-id="3dcfa-270">減號</span><span class="sxs-lookup"><span data-stu-id="3dcfa-270">Minus symbol</span></span>
    
  - <span data-ttu-id="3dcfa-271">字母"A"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="3dcfa-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="3dcfa-272">三位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-272">Three digits</span></span>
    
- <span data-ttu-id="3dcfa-273">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3dcfa-274">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-274">Checksum</span></span>

<span data-ttu-id="3dcfa-275">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-276">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-276">Definition</span></span>

<span data-ttu-id="3dcfa-277">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-278">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-279">從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-280">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-281">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="3dcfa-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-284">識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-284">identification number</span></span>
  
<span data-ttu-id="3dcfa-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-285">personal id</span></span>
  
<span data-ttu-id="3dcfa-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-286">identity number</span></span>
  
<span data-ttu-id="3dcfa-287">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-287">finnish national id number</span></span>
  
<span data-ttu-id="3dcfa-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-288">personalidnumber#</span></span>
  
<span data-ttu-id="3dcfa-289">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-289">national identification number</span></span>
  
<span data-ttu-id="3dcfa-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-290">id number</span></span>
  
<span data-ttu-id="3dcfa-291">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-291">national id no.</span></span>
  
<span data-ttu-id="3dcfa-292">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-292">national id number</span></span>
  
<span data-ttu-id="3dcfa-293">識別碼不</span><span class="sxs-lookup"><span data-stu-id="3dcfa-293">id no</span></span>
  
<span data-ttu-id="3dcfa-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="3dcfa-294">tunnistenumero</span></span>
  
<span data-ttu-id="3dcfa-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="3dcfa-295">henkilötunnus</span></span>
  
<span data-ttu-id="3dcfa-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="3dcfa-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="3dcfa-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="3dcfa-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="3dcfa-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="3dcfa-298">identiteetti numero</span></span>
  
<span data-ttu-id="3dcfa-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="3dcfa-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="3dcfa-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="3dcfa-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="3dcfa-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="3dcfa-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="3dcfa-302">tunnusnumero</span></span>
  
<span data-ttu-id="3dcfa-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="3dcfa-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="3dcfa-304">hetu</span><span class="sxs-lookup"><span data-stu-id="3dcfa-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="3dcfa-305">法國</span><span class="sxs-lookup"><span data-stu-id="3dcfa-305">France</span></span>

<span data-ttu-id="3dcfa-306">如需詳細資訊，請參閱 「 法國社會安全號碼 (INSEE) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3dcfa-307">德國</span><span class="sxs-lookup"><span data-stu-id="3dcfa-307">Germany</span></span>

<span data-ttu-id="3dcfa-308">如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3dcfa-309">希臘</span><span class="sxs-lookup"><span data-stu-id="3dcfa-309">Greece</span></span>

<span data-ttu-id="3dcfa-310">如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="3dcfa-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="3dcfa-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-312">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-312">Format</span></span>

<span data-ttu-id="3dcfa-313">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-314">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-314">Pattern</span></span>

<span data-ttu-id="3dcfa-315">九位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3dcfa-316">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-316">Checksum</span></span>

<span data-ttu-id="3dcfa-317">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-318">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-318">Definition</span></span>

<span data-ttu-id="3dcfa-319">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-320">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-321">從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-322">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-323">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="3dcfa-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-326">匈牙利文社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-326">hungarian social security number</span></span>
  
<span data-ttu-id="3dcfa-327">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-327">social security number</span></span>
  
<span data-ttu-id="3dcfa-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="3dcfa-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-329">hssn#</span></span>
  
<span data-ttu-id="3dcfa-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="3dcfa-330">socialsecuritynno</span></span>
  
<span data-ttu-id="3dcfa-331">hssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-331">hssn</span></span>
  
<span data-ttu-id="3dcfa-332">泰</span><span class="sxs-lookup"><span data-stu-id="3dcfa-332">taj</span></span>
  
<span data-ttu-id="3dcfa-333">泰 #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-333">taj#</span></span>
  
<span data-ttu-id="3dcfa-334">ssn</span><span class="sxs-lookup"><span data-stu-id="3dcfa-334">ssn</span></span>
  
<span data-ttu-id="3dcfa-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-335">ssn#</span></span>
  
<span data-ttu-id="3dcfa-336">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="3dcfa-336">social security no</span></span>
  
<span data-ttu-id="3dcfa-337">áfa</span><span class="sxs-lookup"><span data-stu-id="3dcfa-337">áfa</span></span>
  
<span data-ttu-id="3dcfa-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="3dcfa-338">közösségi adószám</span></span>
  
<span data-ttu-id="3dcfa-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="3dcfa-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="3dcfa-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="3dcfa-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="3dcfa-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="3dcfa-341">áfa szám</span></span>
  
<span data-ttu-id="3dcfa-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="3dcfa-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3dcfa-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="3dcfa-343">Portugal</span></span>

<span data-ttu-id="3dcfa-344">如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="3dcfa-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="3dcfa-345">Spain</span></span>

<span data-ttu-id="3dcfa-346">如需詳細資訊，請參閱 「 西班牙社會安全號碼 (SSN) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="3dcfa-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="3dcfa-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="3dcfa-348">格式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-348">Format</span></span>

<span data-ttu-id="3dcfa-349">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3dcfa-350">模式</span><span class="sxs-lookup"><span data-stu-id="3dcfa-350">Pattern</span></span>

<span data-ttu-id="3dcfa-351">12 位數：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-351">12 digits:</span></span>
  
-  <span data-ttu-id="3dcfa-352">會對應至出生日期 (YYYYMMDD) 的八位數</span><span class="sxs-lookup"><span data-stu-id="3dcfa-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="3dcfa-353">會對應至序號的三位數其中：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="3dcfa-354">序號中的最後一個數字表示性別因 1 女 2 男奇數和偶數女性的工作分派</span><span class="sxs-lookup"><span data-stu-id="3dcfa-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="3dcfa-355">最多 1990，工作分派的序號採納郡出生數字的承載或 （如果出生之前 1947年） 其中他有已住，根據稅務記錄上 1947 年 1 月 1，具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants</span><span class="sxs-lookup"><span data-stu-id="3dcfa-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="3dcfa-356">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3dcfa-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-357">Checksum</span></span>

<span data-ttu-id="3dcfa-358">是</span><span class="sxs-lookup"><span data-stu-id="3dcfa-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3dcfa-359">定義</span><span class="sxs-lookup"><span data-stu-id="3dcfa-359">Definition</span></span>

<span data-ttu-id="3dcfa-360">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-361">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3dcfa-362">從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="3dcfa-363">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="3dcfa-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3dcfa-364">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="3dcfa-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="3dcfa-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3dcfa-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="3dcfa-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="3dcfa-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="3dcfa-367">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-367">personal id number</span></span>
  
<span data-ttu-id="3dcfa-368">識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-368">identification number</span></span>
  
<span data-ttu-id="3dcfa-369">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="3dcfa-369">personal id no</span></span>
  
<span data-ttu-id="3dcfa-370">身分識別沒有</span><span class="sxs-lookup"><span data-stu-id="3dcfa-370">identity no</span></span>
  
<span data-ttu-id="3dcfa-371">識別任何</span><span class="sxs-lookup"><span data-stu-id="3dcfa-371">identification no</span></span>
  
<span data-ttu-id="3dcfa-372">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="3dcfa-372">personal identification no</span></span>
  
<span data-ttu-id="3dcfa-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-373">personnummer id</span></span>
  
<span data-ttu-id="3dcfa-374">personligt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-374">personligt id-nummer</span></span>
  
<span data-ttu-id="3dcfa-375">unikt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-375">unikt id-nummer</span></span>
  
<span data-ttu-id="3dcfa-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="3dcfa-376">personnummer</span></span>
  
<span data-ttu-id="3dcfa-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="3dcfa-377">identifikationsnumret</span></span>
  
<span data-ttu-id="3dcfa-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-378">personnummer#</span></span>
  
<span data-ttu-id="3dcfa-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="3dcfa-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3dcfa-380">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3dcfa-380">See also</span></span>

[<span data-ttu-id="3dcfa-381">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="3dcfa-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

