---
title: DLP 功能所尋找的項目
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 敏感資訊類型會尋找特定模式, 並透過確保正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊來 corroborate 它。 某些功能是由內建函式執行。 本主題說明這些函數所尋找的內容, 以協助您瞭解預先定義的機密資訊類型的運作方式。
ms.openlocfilehash: 044920a7ff28ffc1c4338a642bc130ee07ef7264
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077999"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="050e0-105">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="050e0-105">What the DLP functions look for</span></span>

<span data-ttu-id="050e0-106">資料遺失防護 (DLP) 包含敏感資訊類型, 例如信用卡號碼和歐盟借貸卡號碼, 可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="050e0-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="050e0-107">這些機密資訊類型會尋找特定模式, 並透過確保正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊來 corroborate 它。</span><span class="sxs-lookup"><span data-stu-id="050e0-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="050e0-108">某些功能是由內建函式執行。</span><span class="sxs-lookup"><span data-stu-id="050e0-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="050e0-109">例如, 信用卡號碼敏感資訊類型會使用函數來尋找格式類似到期日的日期, 以協助 corroborate 號碼是信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="050e0-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="050e0-110">本主題說明這些函數所尋找的內容, 以協助您瞭解預先定義的機密資訊類型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="050e0-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="050e0-111">如需詳細資訊, 請參閱[敏感資訊類型的外觀](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="050e0-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="050e0-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="050e0-112">Func_us_date</span></span>

<span data-ttu-id="050e0-113">此函數會以美國常用的格式來尋找日期。這包括格式「月/日/年」、「月-日-年」和「年月年」。</span><span class="sxs-lookup"><span data-stu-id="050e0-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="050e0-114">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="050e0-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="050e0-115">範例:</span><span class="sxs-lookup"><span data-stu-id="050e0-115">Examples:</span></span>
  
- <span data-ttu-id="050e0-116">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="050e0-116">December 2, 2016</span></span>
    
- <span data-ttu-id="050e0-117">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="050e0-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="050e0-118">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="050e0-118">dec 02 2016</span></span>
    
- <span data-ttu-id="050e0-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="050e0-119">12/2/2016</span></span>
    
- <span data-ttu-id="050e0-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="050e0-120">12/02/16</span></span>
    
- <span data-ttu-id="050e0-121">十二月-2-2016</span><span class="sxs-lookup"><span data-stu-id="050e0-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="050e0-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="050e0-122">12-2-16</span></span>
    
<span data-ttu-id="050e0-123">公認的月份名稱:</span><span class="sxs-lookup"><span data-stu-id="050e0-123">Accepted month names:</span></span>
  
- <span data-ttu-id="050e0-124">英文</span><span class="sxs-lookup"><span data-stu-id="050e0-124">English</span></span>
    
  - <span data-ttu-id="050e0-125">一月份、二月、三月、四月、5、六月、七月、八月、九月、十二月、十二月、十二月、十二月、十二月、十二月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="050e0-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="050e0-126">Jan 年3月4日當年5月11月11月。</span><span class="sxs-lookup"><span data-stu-id="050e0-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="050e0-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="050e0-127">Func_eu_date</span></span>

<span data-ttu-id="050e0-128">此函數會以歐盟常用的格式來尋找日期</span><span class="sxs-lookup"><span data-stu-id="050e0-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="050e0-129">(以及美國以外的大多數位置)。</span><span class="sxs-lookup"><span data-stu-id="050e0-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="050e0-130">這包括 [日/月/年]、[日-月-年] 和「日月年度」的格式。</span><span class="sxs-lookup"><span data-stu-id="050e0-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="050e0-131">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="050e0-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="050e0-132">範例:</span><span class="sxs-lookup"><span data-stu-id="050e0-132">Examples:</span></span>
  
- <span data-ttu-id="050e0-133">2十二月2016</span><span class="sxs-lookup"><span data-stu-id="050e0-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="050e0-134">02十二月2016</span><span class="sxs-lookup"><span data-stu-id="050e0-134">02 dec 2016</span></span>
    
- <span data-ttu-id="050e0-135">2十二月16</span><span class="sxs-lookup"><span data-stu-id="050e0-135">2 Dec 16</span></span>
    
- <span data-ttu-id="050e0-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="050e0-136">2/12/2016</span></span>
    
- <span data-ttu-id="050e0-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="050e0-137">02/12/16</span></span>
    
- <span data-ttu-id="050e0-138">2-十二月-2016</span><span class="sxs-lookup"><span data-stu-id="050e0-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="050e0-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="050e0-139">2-12-16</span></span>
    
<span data-ttu-id="050e0-140">公認的月份名稱:</span><span class="sxs-lookup"><span data-stu-id="050e0-140">Accepted month names:</span></span>
  
- <span data-ttu-id="050e0-141">英文</span><span class="sxs-lookup"><span data-stu-id="050e0-141">English</span></span>
    
  - <span data-ttu-id="050e0-142">一月份、二月、三月、四月、5、六月、七月、八月、九月、十二月、十二月、十二月、十二月、十二月、十二月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="050e0-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="050e0-143">Jan 年3月4日當年5月11月11月。</span><span class="sxs-lookup"><span data-stu-id="050e0-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="050e0-144">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="050e0-144">Dutch</span></span>
    
  - <span data-ttu-id="050e0-145">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="050e0-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="050e0-146">jan 二月 maart apr mei 年9月8日當年9月 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="050e0-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="050e0-147">法文</span><span class="sxs-lookup"><span data-stu-id="050e0-147">French</span></span>
    
  - <span data-ttu-id="050e0-148">janvier、février、火星、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="050e0-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="050e0-149">janv.</span><span class="sxs-lookup"><span data-stu-id="050e0-149">janv.</span></span> <span data-ttu-id="050e0-150">févr.</span><span class="sxs-lookup"><span data-stu-id="050e0-150">févr.</span></span> <span data-ttu-id="050e0-151">火星 avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="050e0-151">mars avril mai juin juil.</span></span> <span data-ttu-id="050e0-152">août 年9月。</span><span class="sxs-lookup"><span data-stu-id="050e0-152">août sept.</span></span> <span data-ttu-id="050e0-153">10.</span><span class="sxs-lookup"><span data-stu-id="050e0-153">oct.</span></span> <span data-ttu-id="050e0-154">11.</span><span class="sxs-lookup"><span data-stu-id="050e0-154">nov.</span></span> <span data-ttu-id="050e0-155">déc.</span><span class="sxs-lookup"><span data-stu-id="050e0-155">déc.</span></span>
    
- <span data-ttu-id="050e0-156">德文</span><span class="sxs-lookup"><span data-stu-id="050e0-156">German</span></span>
    
  - <span data-ttu-id="050e0-157">jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember</span><span class="sxs-lookup"><span data-stu-id="050e0-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="050e0-158">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="050e0-158">Jan./Jän.</span></span> <span data-ttu-id="050e0-159">März 年4月 Juli Juni。</span><span class="sxs-lookup"><span data-stu-id="050e0-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="050e0-160">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="050e0-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="050e0-161">義大利文</span><span class="sxs-lookup"><span data-stu-id="050e0-161">Italian</span></span>
    
  - <span data-ttu-id="050e0-162">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="050e0-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="050e0-163">genn.</span><span class="sxs-lookup"><span data-stu-id="050e0-163">genn.</span></span> <span data-ttu-id="050e0-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="050e0-164">febbr.</span></span> <span data-ttu-id="050e0-165">mar.</span><span class="sxs-lookup"><span data-stu-id="050e0-165">mar.</span></span> <span data-ttu-id="050e0-166">4.</span><span class="sxs-lookup"><span data-stu-id="050e0-166">apr.</span></span> <span data-ttu-id="050e0-167">magg.</span><span class="sxs-lookup"><span data-stu-id="050e0-167">magg.</span></span> <span data-ttu-id="050e0-168">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="050e0-168">giugno luglio ag.</span></span> <span data-ttu-id="050e0-169">sett.</span><span class="sxs-lookup"><span data-stu-id="050e0-169">sett.</span></span> <span data-ttu-id="050e0-170">ott.</span><span class="sxs-lookup"><span data-stu-id="050e0-170">ott.</span></span> <span data-ttu-id="050e0-171">11.</span><span class="sxs-lookup"><span data-stu-id="050e0-171">nov.</span></span> <span data-ttu-id="050e0-172">.dic.</span><span class="sxs-lookup"><span data-stu-id="050e0-172">dic.</span></span>
    
- <span data-ttu-id="050e0-173">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="050e0-173">Portuguese</span></span>
    
  - <span data-ttu-id="050e0-174">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="050e0-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="050e0-175">jan fev mar abr mai 06 年前設定11月 dez</span><span class="sxs-lookup"><span data-stu-id="050e0-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="050e0-176">西班牙文</span><span class="sxs-lookup"><span data-stu-id="050e0-176">Spanish</span></span>
    
  - <span data-ttu-id="050e0-177">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="050e0-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="050e0-178">enero 年2月。</span><span class="sxs-lookup"><span data-stu-id="050e0-178">enero feb.</span></span> <span data-ttu-id="050e0-179">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="050e0-179">marzo abr.</span></span> <span data-ttu-id="050e0-180">mayo 年6月。</span><span class="sxs-lookup"><span data-stu-id="050e0-180">mayo jun.</span></span> <span data-ttu-id="050e0-181">年7月.</span><span class="sxs-lookup"><span data-stu-id="050e0-181">jul.</span></span> <span data-ttu-id="050e0-182">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="050e0-182">agosto sept./set.</span></span> <span data-ttu-id="050e0-183">10.</span><span class="sxs-lookup"><span data-stu-id="050e0-183">oct.</span></span> <span data-ttu-id="050e0-184">11.</span><span class="sxs-lookup"><span data-stu-id="050e0-184">nov.</span></span> <span data-ttu-id="050e0-185">.dic.</span><span class="sxs-lookup"><span data-stu-id="050e0-185">dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="050e0-186">Func_eu_date1 (已過時)</span><span class="sxs-lookup"><span data-stu-id="050e0-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="050e0-187">此函數已被取代, 因為它只支援葡萄牙文月份名稱, 而這些名稱現在`Func_eu_date`已包含于上述函數中。</span><span class="sxs-lookup"><span data-stu-id="050e0-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="050e0-188">此函數會以葡萄牙文常用的格式來尋找日期。</span><span class="sxs-lookup"><span data-stu-id="050e0-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="050e0-189">此函數`Func_eu_date`的格式與使用的語言不同。</span><span class="sxs-lookup"><span data-stu-id="050e0-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="050e0-190">範例:</span><span class="sxs-lookup"><span data-stu-id="050e0-190">Examples:</span></span>
  
- <span data-ttu-id="050e0-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="050e0-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="050e0-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="050e0-192">02 dez 2016</span></span>
    
- <span data-ttu-id="050e0-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="050e0-193">2 Dez 16</span></span>
    
- <span data-ttu-id="050e0-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="050e0-194">2/12/2016</span></span>
    
- <span data-ttu-id="050e0-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="050e0-195">02/12/16</span></span>
    
- <span data-ttu-id="050e0-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="050e0-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="050e0-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="050e0-197">2-12-16</span></span>
    
<span data-ttu-id="050e0-198">公認的月份名稱:</span><span class="sxs-lookup"><span data-stu-id="050e0-198">Accepted month names:</span></span>
  
- <span data-ttu-id="050e0-199">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="050e0-199">Portuguese</span></span>
    
  - <span data-ttu-id="050e0-200">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="050e0-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="050e0-201">jan fev mar abr mai 06 年前設定11月 dez</span><span class="sxs-lookup"><span data-stu-id="050e0-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="050e0-202">Func_eu_date2 (已過時)</span><span class="sxs-lookup"><span data-stu-id="050e0-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="050e0-203">此函數已被取代, 因為它只支援荷蘭月份名稱, 而該名稱現在`Func_eu_date`已包含于上述函數中。</span><span class="sxs-lookup"><span data-stu-id="050e0-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="050e0-204">此函數會以荷蘭文常用的格式來尋找日期。</span><span class="sxs-lookup"><span data-stu-id="050e0-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="050e0-205">此函數`Func_eu_date`的格式與使用的語言不同。</span><span class="sxs-lookup"><span data-stu-id="050e0-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="050e0-206">範例:</span><span class="sxs-lookup"><span data-stu-id="050e0-206">Examples:</span></span>
  
- <span data-ttu-id="050e0-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="050e0-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="050e0-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="050e0-208">02 mei 2016</span></span>
    
- <span data-ttu-id="050e0-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="050e0-209">2 Mei 16</span></span>
    
- <span data-ttu-id="050e0-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="050e0-210">2/12/2016</span></span>
    
- <span data-ttu-id="050e0-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="050e0-211">02/12/16</span></span>
    
- <span data-ttu-id="050e0-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="050e0-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="050e0-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="050e0-213">2-12-16</span></span>
    
<span data-ttu-id="050e0-214">公認的月份名稱:</span><span class="sxs-lookup"><span data-stu-id="050e0-214">Accepted month names:</span></span>
  
- <span data-ttu-id="050e0-215">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="050e0-215">Dutch</span></span>
    
  - <span data-ttu-id="050e0-216">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="050e0-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="050e0-217">jan 二月 maart apr mei 年9月8日當年9月 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="050e0-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="050e0-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="050e0-218">Func_expiration_date</span></span>

<span data-ttu-id="050e0-219">此函數會以信用卡和轉帳卡所使用的格式來尋找日期, 而不是以月為單位來排除天數。</span><span class="sxs-lookup"><span data-stu-id="050e0-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="050e0-220">此函數會比對 "month/year"、"month"、"[month] year" 和 "[month 縮略語] year" 格式的日期。</span><span class="sxs-lookup"><span data-stu-id="050e0-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="050e0-221">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="050e0-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="050e0-222">範例:</span><span class="sxs-lookup"><span data-stu-id="050e0-222">Examples:</span></span>
  
- <span data-ttu-id="050e0-223">MM/YY--例如, 01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="050e0-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="050e0-224">MM/YYYY--例如, 01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="050e0-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="050e0-225">MM-YY--例如, 01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="050e0-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="050e0-226">MM-YYYY--例如, 01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="050e0-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="050e0-227">下列格式支援 YY 或 YYYY:</span><span class="sxs-lookup"><span data-stu-id="050e0-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="050e0-228">Month--例如。Jan-2010 或一月-2010 或 Jan-10 或一月-10</span><span class="sxs-lookup"><span data-stu-id="050e0-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="050e0-229">Month YYYY--例如, ' 一月份 2010 ' 或 ' Jan 2010 ' 或 ' 一月 10 ' 或 ' Jan 10 '</span><span class="sxs-lookup"><span data-stu-id="050e0-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="050e0-230">MonthYYYY--例如 "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="050e0-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="050e0-231">Month/YYYY--例如, ' 一月份/2010 ' 或 ' Jan/2010 ' 或 ' Jan/10 ' 或 ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="050e0-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="050e0-232">公認的月份名稱:</span><span class="sxs-lookup"><span data-stu-id="050e0-232">Accepted month names:</span></span>
  
- <span data-ttu-id="050e0-233">英文</span><span class="sxs-lookup"><span data-stu-id="050e0-233">English</span></span>
    
  - <span data-ttu-id="050e0-234">一月份、二月、三月、四月、5、六月、七月、八月、九月、十二月、十二月、十二月、十二月、十二月、十二月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="050e0-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="050e0-235">Jan 年2月3月4日當年11月11月8月9日</span><span class="sxs-lookup"><span data-stu-id="050e0-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="050e0-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="050e0-236">Func_us_address</span></span>

<span data-ttu-id="050e0-237">此函數會尋找美國狀態名稱或郵政縮寫, 後面接著有效的郵遞區號, 就像在郵政位址中使用一樣。</span><span class="sxs-lookup"><span data-stu-id="050e0-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="050e0-238">郵遞區號必須是與美國狀態名稱或縮寫相關聯的正確郵遞區號之一。</span><span class="sxs-lookup"><span data-stu-id="050e0-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="050e0-239">美國的狀態名稱和郵遞區號不能以標點符號或字母隔開。</span><span class="sxs-lookup"><span data-stu-id="050e0-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="050e0-240">範例:</span><span class="sxs-lookup"><span data-stu-id="050e0-240">Examples:</span></span>
  
- <span data-ttu-id="050e0-241">華盛頓98052</span><span class="sxs-lookup"><span data-stu-id="050e0-241">Washington 98052</span></span>
    
- <span data-ttu-id="050e0-242">華盛頓98052-9998</span><span class="sxs-lookup"><span data-stu-id="050e0-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="050e0-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="050e0-243">WA 98052</span></span>
    
- <span data-ttu-id="050e0-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="050e0-244">WA 98052-9998</span></span>
    

