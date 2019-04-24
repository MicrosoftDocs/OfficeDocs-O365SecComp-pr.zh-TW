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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255551"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="70d33-104">歐盟社會安全號碼或對等項目識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="70d33-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="70d33-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="70d33-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="70d33-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="70d33-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="70d33-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="70d33-108">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-108">Format</span></span>

<span data-ttu-id="70d33-109">10 位數，代表指定之格式</span><span class="sxs-lookup"><span data-stu-id="70d33-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-110">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-110">Pattern</span></span>

<span data-ttu-id="70d33-111">10 位數：</span><span class="sxs-lookup"><span data-stu-id="70d33-111">10 digits:</span></span>
  
-  <span data-ttu-id="70d33-112">會對應至序號的三位數</span><span class="sxs-lookup"><span data-stu-id="70d33-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="70d33-113">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-113">One check digit</span></span>
    
- <span data-ttu-id="70d33-114">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="70d33-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="70d33-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-115">Checksum</span></span>

<span data-ttu-id="70d33-116">是</span><span class="sxs-lookup"><span data-stu-id="70d33-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-117">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-117">Definition</span></span>

<span data-ttu-id="70d33-118">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-119">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-120">從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-121">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-122">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="70d33-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-125">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="70d33-125">social security no</span></span>
  
<span data-ttu-id="70d33-126">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-126">social security number</span></span>
  
<span data-ttu-id="70d33-127">社會安全的程式碼</span><span class="sxs-lookup"><span data-stu-id="70d33-127">social security code</span></span>
  
<span data-ttu-id="70d33-128">保險號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-128">insurance number</span></span>
  
<span data-ttu-id="70d33-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-129">austrian ssn</span></span>
  
<span data-ttu-id="70d33-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-130">ssn#</span></span>
  
<span data-ttu-id="70d33-131">ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-131">ssn</span></span>
  
<span data-ttu-id="70d33-132">保險程式碼</span><span class="sxs-lookup"><span data-stu-id="70d33-132">insurance code</span></span>
  
<span data-ttu-id="70d33-133">保險程式碼 #</span><span class="sxs-lookup"><span data-stu-id="70d33-133">insurance code#</span></span>
  
<span data-ttu-id="70d33-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="70d33-134">socialsecurityno#</span></span>
  
<span data-ttu-id="70d33-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="70d33-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="70d33-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="70d33-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="70d33-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="70d33-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="70d33-138">比利時</span><span class="sxs-lookup"><span data-stu-id="70d33-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="70d33-139">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-139">Format</span></span>

<span data-ttu-id="70d33-140">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="70d33-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-141">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-141">Pattern</span></span>

<span data-ttu-id="70d33-142">11 位數</span><span class="sxs-lookup"><span data-stu-id="70d33-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="70d33-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-143">Checksum</span></span>

<span data-ttu-id="70d33-144">是</span><span class="sxs-lookup"><span data-stu-id="70d33-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-145">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-145">Definition</span></span>

<span data-ttu-id="70d33-146">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-147">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-148">從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-149">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-150">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="70d33-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-153">比利時國民身分的數字</span><span class="sxs-lookup"><span data-stu-id="70d33-153">belgian national number</span></span>
  
<span data-ttu-id="70d33-154">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-154">national number</span></span>
  
<span data-ttu-id="70d33-155">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-155">social security number</span></span>
  
<span data-ttu-id="70d33-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-156">nationalnumber#</span></span>
  
<span data-ttu-id="70d33-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-157">ssn#</span></span>
  
<span data-ttu-id="70d33-158">ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-158">ssn</span></span>
  
<span data-ttu-id="70d33-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="70d33-159">nationalnumber</span></span>
  
<span data-ttu-id="70d33-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="70d33-160">bnn#</span></span>
  
<span data-ttu-id="70d33-161">bnn</span><span class="sxs-lookup"><span data-stu-id="70d33-161">bnn</span></span>
  
<span data-ttu-id="70d33-162">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-162">personal id number</span></span>
  
<span data-ttu-id="70d33-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-163">personalidnumber#</span></span>
  
<span data-ttu-id="70d33-164">numéro 國際電話</span><span class="sxs-lookup"><span data-stu-id="70d33-164">numéro national</span></span>
  
<span data-ttu-id="70d33-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="70d33-165">numéro de sécurité</span></span>
  
<span data-ttu-id="70d33-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="70d33-166">numéro d'assuré</span></span>
  
<span data-ttu-id="70d33-167">identifiant 國際電話</span><span class="sxs-lookup"><span data-stu-id="70d33-167">identifiant national</span></span>
  
<span data-ttu-id="70d33-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="70d33-168">identifiantnational#</span></span>
  
<span data-ttu-id="70d33-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="70d33-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="70d33-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="70d33-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="70d33-171">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-171">Format</span></span>

<span data-ttu-id="70d33-172">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="70d33-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-173">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-173">Pattern</span></span>

 <span data-ttu-id="70d33-174">11 位數：</span><span class="sxs-lookup"><span data-stu-id="70d33-174">11 digits:</span></span> 
  
-  <span data-ttu-id="70d33-175">十位數</span><span class="sxs-lookup"><span data-stu-id="70d33-175">Ten digits</span></span> 
    
- <span data-ttu-id="70d33-176">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="70d33-177">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-177">Checksum</span></span>

<span data-ttu-id="70d33-178">是</span><span class="sxs-lookup"><span data-stu-id="70d33-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-179">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-179">Definition</span></span>

<span data-ttu-id="70d33-180">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-181">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-182">從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-183">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-184">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="70d33-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-187">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-187">personal identification number</span></span>
  
<span data-ttu-id="70d33-188">主版公民數目</span><span class="sxs-lookup"><span data-stu-id="70d33-188">master citizen number</span></span>
  
<span data-ttu-id="70d33-189">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-189">national identification number</span></span>
  
<span data-ttu-id="70d33-190">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-190">social security number</span></span>
  
<span data-ttu-id="70d33-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-191">nationalnumber#</span></span>
  
<span data-ttu-id="70d33-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-192">ssn#</span></span>
  
<span data-ttu-id="70d33-193">ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-193">ssn</span></span>
  
<span data-ttu-id="70d33-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="70d33-194">nationalnumber</span></span>
  
<span data-ttu-id="70d33-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="70d33-195">bnn#</span></span>
  
<span data-ttu-id="70d33-196">bnn</span><span class="sxs-lookup"><span data-stu-id="70d33-196">bnn</span></span>
  
<span data-ttu-id="70d33-197">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-197">personal id number</span></span>
  
<span data-ttu-id="70d33-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-198">personalidnumber#</span></span>
  
<span data-ttu-id="70d33-199">oib 碼</span><span class="sxs-lookup"><span data-stu-id="70d33-199">oib</span></span>
  
<span data-ttu-id="70d33-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="70d33-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="70d33-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="70d33-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="70d33-202">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-202">Format</span></span>

<span data-ttu-id="70d33-203">十個數字和中指定的型態的反斜線</span><span class="sxs-lookup"><span data-stu-id="70d33-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-204">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-204">Pattern</span></span>

<span data-ttu-id="70d33-205">十位數和一個反斜線：</span><span class="sxs-lookup"><span data-stu-id="70d33-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="70d33-206">會對應至 (YYMMDD) 的出生日期的六位數：</span><span class="sxs-lookup"><span data-stu-id="70d33-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="70d33-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="70d33-207">A backslash</span></span>
    
- <span data-ttu-id="70d33-208">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="70d33-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="70d33-209">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="70d33-210">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-210">Checksum</span></span>

<span data-ttu-id="70d33-211">是</span><span class="sxs-lookup"><span data-stu-id="70d33-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-212">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-212">Definition</span></span>

<span data-ttu-id="70d33-213">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-214">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-215">從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-216">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-217">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="70d33-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-220">出生數目</span><span class="sxs-lookup"><span data-stu-id="70d33-220">birth number</span></span>
  
<span data-ttu-id="70d33-221">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-221">national identification number</span></span>
  
<span data-ttu-id="70d33-222">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-222">personal identification number</span></span>
  
<span data-ttu-id="70d33-223">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-223">social security number</span></span>
  
<span data-ttu-id="70d33-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-224">nationalnumber#</span></span>
  
<span data-ttu-id="70d33-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-225">ssn#</span></span>
  
<span data-ttu-id="70d33-226">ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-226">ssn</span></span>
  
<span data-ttu-id="70d33-227">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-227">national number</span></span>
  
<span data-ttu-id="70d33-228">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-228">personal id number</span></span>
  
<span data-ttu-id="70d33-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-229">personalidnumber#</span></span>
  
<span data-ttu-id="70d33-230">rč</span><span class="sxs-lookup"><span data-stu-id="70d33-230">rč</span></span>
  
<span data-ttu-id="70d33-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="70d33-231">rodné číslo</span></span>
  
<span data-ttu-id="70d33-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="70d33-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="70d33-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="70d33-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="70d33-234">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-234">Format</span></span>

<span data-ttu-id="70d33-235">十個數字和中指定的型態連字號</span><span class="sxs-lookup"><span data-stu-id="70d33-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-236">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-236">Pattern</span></span>

<span data-ttu-id="70d33-237">十位數，並連字號：</span><span class="sxs-lookup"><span data-stu-id="70d33-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="70d33-238">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="70d33-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="70d33-239">連字號</span><span class="sxs-lookup"><span data-stu-id="70d33-239">A hyphen</span></span>
    
- <span data-ttu-id="70d33-240">會對應至序號的四位數</span><span class="sxs-lookup"><span data-stu-id="70d33-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="70d33-241">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-241">Checksum</span></span>

<span data-ttu-id="70d33-242">是</span><span class="sxs-lookup"><span data-stu-id="70d33-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-243">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-243">Definition</span></span>

<span data-ttu-id="70d33-244">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-245">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-246">從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-247">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-248">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="70d33-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-251">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-251">personal identification number</span></span>
  
<span data-ttu-id="70d33-252">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-252">national identification number</span></span>
  
<span data-ttu-id="70d33-253">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-253">social security number</span></span>
  
<span data-ttu-id="70d33-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-254">nationalnumber#</span></span>
  
<span data-ttu-id="70d33-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-255">ssn#</span></span>
  
<span data-ttu-id="70d33-256">ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-256">ssn</span></span>
  
<span data-ttu-id="70d33-257">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-257">national number</span></span>
  
<span data-ttu-id="70d33-258">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-258">personal id number</span></span>
  
<span data-ttu-id="70d33-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-259">personalidnumber#</span></span>
  
<span data-ttu-id="70d33-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="70d33-260">cpr-nummer</span></span>
  
<span data-ttu-id="70d33-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="70d33-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="70d33-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="70d33-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="70d33-263">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-263">Format</span></span>

<span data-ttu-id="70d33-264">11 個字元組合，以指定的格式</span><span class="sxs-lookup"><span data-stu-id="70d33-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-265">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-265">Pattern</span></span>

<span data-ttu-id="70d33-266">以指定的格式 11 個字元組合：</span><span class="sxs-lookup"><span data-stu-id="70d33-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="70d33-267">六位數</span><span class="sxs-lookup"><span data-stu-id="70d33-267">Six digits</span></span> 
    
- <span data-ttu-id="70d33-268">實例的其中一項：</span><span class="sxs-lookup"><span data-stu-id="70d33-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="70d33-269">加上符號</span><span class="sxs-lookup"><span data-stu-id="70d33-269">Plus symbol</span></span>
    
  - <span data-ttu-id="70d33-270">減號</span><span class="sxs-lookup"><span data-stu-id="70d33-270">Minus symbol</span></span>
    
  - <span data-ttu-id="70d33-271">字母"A"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="70d33-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="70d33-272">三位數</span><span class="sxs-lookup"><span data-stu-id="70d33-272">Three digits</span></span>
    
- <span data-ttu-id="70d33-273">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="70d33-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="70d33-274">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-274">Checksum</span></span>

<span data-ttu-id="70d33-275">是</span><span class="sxs-lookup"><span data-stu-id="70d33-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-276">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-276">Definition</span></span>

<span data-ttu-id="70d33-277">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-278">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-279">從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-280">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-281">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="70d33-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-284">識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-284">identification number</span></span>
  
<span data-ttu-id="70d33-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-285">personal id</span></span>
  
<span data-ttu-id="70d33-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-286">identity number</span></span>
  
<span data-ttu-id="70d33-287">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-287">finnish national id number</span></span>
  
<span data-ttu-id="70d33-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-288">personalidnumber#</span></span>
  
<span data-ttu-id="70d33-289">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-289">national identification number</span></span>
  
<span data-ttu-id="70d33-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-290">id number</span></span>
  
<span data-ttu-id="70d33-291">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="70d33-291">national id no.</span></span>
  
<span data-ttu-id="70d33-292">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-292">national id number</span></span>
  
<span data-ttu-id="70d33-293">識別碼不</span><span class="sxs-lookup"><span data-stu-id="70d33-293">id no</span></span>
  
<span data-ttu-id="70d33-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="70d33-294">tunnistenumero</span></span>
  
<span data-ttu-id="70d33-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="70d33-295">henkilötunnus</span></span>
  
<span data-ttu-id="70d33-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="70d33-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="70d33-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="70d33-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="70d33-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="70d33-298">identiteetti numero</span></span>
  
<span data-ttu-id="70d33-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="70d33-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="70d33-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="70d33-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="70d33-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="70d33-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="70d33-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="70d33-302">tunnusnumero</span></span>
  
<span data-ttu-id="70d33-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="70d33-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="70d33-304">hetu</span><span class="sxs-lookup"><span data-stu-id="70d33-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="70d33-305">法國</span><span class="sxs-lookup"><span data-stu-id="70d33-305">France</span></span>

<span data-ttu-id="70d33-306">如需詳細資訊，請參閱 「 法國社會安全號碼 (INSEE) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="70d33-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="70d33-307">德國</span><span class="sxs-lookup"><span data-stu-id="70d33-307">Germany</span></span>

<span data-ttu-id="70d33-308">如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="70d33-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="70d33-309">希臘</span><span class="sxs-lookup"><span data-stu-id="70d33-309">Greece</span></span>

<span data-ttu-id="70d33-310">如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="70d33-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="70d33-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="70d33-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="70d33-312">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-312">Format</span></span>

<span data-ttu-id="70d33-313">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="70d33-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-314">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-314">Pattern</span></span>

<span data-ttu-id="70d33-315">九位數</span><span class="sxs-lookup"><span data-stu-id="70d33-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="70d33-316">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-316">Checksum</span></span>

<span data-ttu-id="70d33-317">是</span><span class="sxs-lookup"><span data-stu-id="70d33-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-318">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-318">Definition</span></span>

<span data-ttu-id="70d33-319">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-320">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-321">從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-322">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-323">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="70d33-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-326">匈牙利文社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-326">hungarian social security number</span></span>
  
<span data-ttu-id="70d33-327">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="70d33-327">social security number</span></span>
  
<span data-ttu-id="70d33-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="70d33-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="70d33-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-329">hssn#</span></span>
  
<span data-ttu-id="70d33-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="70d33-330">socialsecuritynno</span></span>
  
<span data-ttu-id="70d33-331">hssn</span><span class="sxs-lookup"><span data-stu-id="70d33-331">hssn</span></span>
  
<span data-ttu-id="70d33-332">泰</span><span class="sxs-lookup"><span data-stu-id="70d33-332">taj</span></span>
  
<span data-ttu-id="70d33-333">泰 #</span><span class="sxs-lookup"><span data-stu-id="70d33-333">taj#</span></span>
  
<span data-ttu-id="70d33-334">ssn</span><span class="sxs-lookup"><span data-stu-id="70d33-334">ssn</span></span>
  
<span data-ttu-id="70d33-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="70d33-335">ssn#</span></span>
  
<span data-ttu-id="70d33-336">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="70d33-336">social security no</span></span>
  
<span data-ttu-id="70d33-337">áfa</span><span class="sxs-lookup"><span data-stu-id="70d33-337">áfa</span></span>
  
<span data-ttu-id="70d33-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="70d33-338">közösségi adószám</span></span>
  
<span data-ttu-id="70d33-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="70d33-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="70d33-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="70d33-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="70d33-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="70d33-341">áfa szám</span></span>
  
<span data-ttu-id="70d33-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="70d33-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="70d33-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="70d33-343">Portugal</span></span>

<span data-ttu-id="70d33-344">如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="70d33-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="70d33-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="70d33-345">Spain</span></span>

<span data-ttu-id="70d33-346">如需詳細資訊，請參閱 「 西班牙社會安全號碼 (SSN) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="70d33-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="70d33-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="70d33-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="70d33-348">格式</span><span class="sxs-lookup"><span data-stu-id="70d33-348">Format</span></span>

<span data-ttu-id="70d33-349">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="70d33-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="70d33-350">模式</span><span class="sxs-lookup"><span data-stu-id="70d33-350">Pattern</span></span>

<span data-ttu-id="70d33-351">12 位數：</span><span class="sxs-lookup"><span data-stu-id="70d33-351">12 digits:</span></span>
  
-  <span data-ttu-id="70d33-352">會對應至出生日期 (YYYYMMDD) 的八位數</span><span class="sxs-lookup"><span data-stu-id="70d33-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="70d33-353">會對應至序號的三位數其中：</span><span class="sxs-lookup"><span data-stu-id="70d33-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="70d33-354">序號中的最後一個數字表示性別因 1 女 2 男奇數和偶數女性的工作分派</span><span class="sxs-lookup"><span data-stu-id="70d33-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="70d33-355">最多 1990，工作分派的序號採納郡出生數字的承載或 （如果出生之前 1947年） 其中他有已住，根據稅務記錄上 1947 年 1 月 1，具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants</span><span class="sxs-lookup"><span data-stu-id="70d33-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="70d33-356">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="70d33-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="70d33-357">Checksum</span></span>

<span data-ttu-id="70d33-358">是</span><span class="sxs-lookup"><span data-stu-id="70d33-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="70d33-359">定義</span><span class="sxs-lookup"><span data-stu-id="70d33-359">Definition</span></span>

<span data-ttu-id="70d33-360">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-361">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="70d33-362">從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="70d33-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="70d33-363">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="70d33-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="70d33-364">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="70d33-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="70d33-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="70d33-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="70d33-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="70d33-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="70d33-367">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-367">personal id number</span></span>
  
<span data-ttu-id="70d33-368">識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-368">identification number</span></span>
  
<span data-ttu-id="70d33-369">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="70d33-369">personal id no</span></span>
  
<span data-ttu-id="70d33-370">身分識別沒有</span><span class="sxs-lookup"><span data-stu-id="70d33-370">identity no</span></span>
  
<span data-ttu-id="70d33-371">識別任何</span><span class="sxs-lookup"><span data-stu-id="70d33-371">identification no</span></span>
  
<span data-ttu-id="70d33-372">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="70d33-372">personal identification no</span></span>
  
<span data-ttu-id="70d33-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="70d33-373">personnummer id</span></span>
  
<span data-ttu-id="70d33-374">personligt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="70d33-374">personligt id-nummer</span></span>
  
<span data-ttu-id="70d33-375">unikt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="70d33-375">unikt id-nummer</span></span>
  
<span data-ttu-id="70d33-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="70d33-376">personnummer</span></span>
  
<span data-ttu-id="70d33-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="70d33-377">identifikationsnumret</span></span>
  
<span data-ttu-id="70d33-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="70d33-378">personnummer#</span></span>
  
<span data-ttu-id="70d33-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="70d33-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="70d33-380">另請參閱</span><span class="sxs-lookup"><span data-stu-id="70d33-380">See also</span></span>

[<span data-ttu-id="70d33-381">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="70d33-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

