---
title: DLP 功能所尋找的項目
ms.author: chrfox
author: chrfox
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
description: 敏感資訊類型尋找特定的模式，並證實來確保適當的格式設定、 強制執行總和檢查碼，並尋找相關的關鍵字或其他資訊。 某些這項功能是由內部函式執行。 本主題說明這些函式查詢，以協助您瞭解預先定義的敏感資訊類型的運作方式。
ms.openlocfilehash: c192a17c488e5a7252a3599204d2bdeda4d0637c
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230317"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="b4f94-105">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="b4f94-105">What the DLP functions look for</span></span>

<span data-ttu-id="b4f94-106">資料外洩防護 (DLP) 包含敏感資訊類型，例如信用卡號碼和歐盟轉帳卡號碼，可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="b4f94-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="b4f94-107">這些敏感資訊類型尋找特定的模式，並證實來確保適當的格式設定、 強制執行總和檢查碼，並尋找相關的關鍵字或其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b4f94-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="b4f94-108">某些這項功能是由內部函式執行。</span><span class="sxs-lookup"><span data-stu-id="b4f94-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="b4f94-109">例如，信用卡號碼敏感資訊類型會使用函數來看起來像到期日，以協助證實格式化的日期數字是信用卡號。</span><span class="sxs-lookup"><span data-stu-id="b4f94-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="b4f94-110">本主題說明這些函式查詢，以協助您瞭解預先定義的敏感資訊類型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="b4f94-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="b4f94-111">如需詳細資訊，請參閱[敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f94-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="b4f94-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="b4f94-112">Func_us_date</span></span>

<span data-ttu-id="b4f94-113">此函數會尋找常用在美國格式的日期這包括格式 「 月/日/年 」、 「 月-日-年 」，以及 「 月份日期年份 」。</span><span class="sxs-lookup"><span data-stu-id="b4f94-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="b4f94-114">縮寫的月份的名稱不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="b4f94-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="b4f94-115">範例:</span><span class="sxs-lookup"><span data-stu-id="b4f94-115">Examples:</span></span>
  
- <span data-ttu-id="b4f94-116">2016 年 12 月 2日日</span><span class="sxs-lookup"><span data-stu-id="b4f94-116">December 2, 2016</span></span>
    
- <span data-ttu-id="b4f94-117">2016 年 12 月 2日日</span><span class="sxs-lookup"><span data-stu-id="b4f94-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="b4f94-118">12 / 02 2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-118">dec 02 2016</span></span>
    
- <span data-ttu-id="b4f94-119">2016 年 12 月 2 日</span><span class="sxs-lookup"><span data-stu-id="b4f94-119">12/2/2016</span></span>
    
- <span data-ttu-id="b4f94-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="b4f94-120">12/02/16</span></span>
    
- <span data-ttu-id="b4f94-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="b4f94-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="b4f94-122">12-2-16</span></span>
    
<span data-ttu-id="b4f94-123">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="b4f94-123">Accepted month names:</span></span>
  
- <span data-ttu-id="b4f94-124">英文</span><span class="sxs-lookup"><span data-stu-id="b4f94-124">English</span></span>
    
  - <span data-ttu-id="b4f94-125">January、 February、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="b4f94-126">年 1 月 2005 年 2 月 Mar.2004 年 4 月可能年 6 月 7 月 ie Sept.年 10 月 11 Dec。</span><span class="sxs-lookup"><span data-stu-id="b4f94-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="b4f94-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="b4f94-127">Func_eu_date</span></span>

<span data-ttu-id="b4f94-128">此函數會尋找在 E.U.中常用的格式的日期</span><span class="sxs-lookup"><span data-stu-id="b4f94-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="b4f94-129">（與許多美國以外的位置）。</span><span class="sxs-lookup"><span data-stu-id="b4f94-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="b4f94-130">這包括格式 「 日/月/年 」、 「 日-月-年 」，以及 「 日月年 」。</span><span class="sxs-lookup"><span data-stu-id="b4f94-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="b4f94-131">縮寫的月份的名稱不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="b4f94-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="b4f94-132">範例:</span><span class="sxs-lookup"><span data-stu-id="b4f94-132">Examples:</span></span>
  
- <span data-ttu-id="b4f94-133">2 年 12 月 2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="b4f94-134">2016 年 12 月 02</span><span class="sxs-lookup"><span data-stu-id="b4f94-134">02 dec 2016</span></span>
    
- <span data-ttu-id="b4f94-135">2 年 12 月 16</span><span class="sxs-lookup"><span data-stu-id="b4f94-135">2 Dec 16</span></span>
    
- <span data-ttu-id="b4f94-136">2016 年 2 月 12 日</span><span class="sxs-lookup"><span data-stu-id="b4f94-136">2/12/2016</span></span>
    
- <span data-ttu-id="b4f94-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="b4f94-137">02/12/16</span></span>
    
- <span data-ttu-id="b4f94-138">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="b4f94-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="b4f94-139">2-12-16</span></span>
    
<span data-ttu-id="b4f94-140">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="b4f94-140">Accepted month names:</span></span>
  
- <span data-ttu-id="b4f94-141">英文</span><span class="sxs-lookup"><span data-stu-id="b4f94-141">English</span></span>
    
  - <span data-ttu-id="b4f94-142">January、 February、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="b4f94-143">年 1 月 2005 年 2 月 Mar.2004 年 4 月可能年 6 月 7 月 ie Sept.年 10 月 11 Dec。</span><span class="sxs-lookup"><span data-stu-id="b4f94-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="b4f94-144">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="b4f94-144">Dutch</span></span>
    
  - <span data-ttu-id="b4f94-145">januari，februari，maart、 April、 mei、 juni、 juli、 奧古斯特一，September、 ocktober，年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="b4f94-146">年 2 月 maart apr mei 年 7 月年 8 月 sep 年 10 月 okt 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="b4f94-147">法文</span><span class="sxs-lookup"><span data-stu-id="b4f94-147">French</span></span>
    
  - <span data-ttu-id="b4f94-148">janvier，février，mars，avril、 mai、 juin juillet、 août、 septembre、 octobre，novembre décembre</span><span class="sxs-lookup"><span data-stu-id="b4f94-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="b4f94-149">janv。</span><span class="sxs-lookup"><span data-stu-id="b4f94-149">janv.</span></span> <span data-ttu-id="b4f94-150">févr。</span><span class="sxs-lookup"><span data-stu-id="b4f94-150">févr.</span></span> <span data-ttu-id="b4f94-151">mars avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="b4f94-151">mars avril mai juin juil.</span></span> <span data-ttu-id="b4f94-152">août 年。</span><span class="sxs-lookup"><span data-stu-id="b4f94-152">août sept.</span></span> <span data-ttu-id="b4f94-153">oct。</span><span class="sxs-lookup"><span data-stu-id="b4f94-153">oct.</span></span> <span data-ttu-id="b4f94-154">11 月。</span><span class="sxs-lookup"><span data-stu-id="b4f94-154">nov.</span></span> <span data-ttu-id="b4f94-155">déc。</span><span class="sxs-lookup"><span data-stu-id="b4f94-155">déc.</span></span>
    
- <span data-ttu-id="b4f94-156">德文</span><span class="sxs-lookup"><span data-stu-id="b4f94-156">German</span></span>
    
  - <span data-ttu-id="b4f94-157">jänuar，februar，märz，April，mai，juni juli，August，September，oktober，November，dezember</span><span class="sxs-lookup"><span data-stu-id="b4f94-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="b4f94-158">Jan。 / Jän。</span><span class="sxs-lookup"><span data-stu-id="b4f94-158">Jan./Jän.</span></span> <span data-ttu-id="b4f94-159">2005 年 2 月 März 2004 年 4 月 Mai Juni Juli ie Sept.Okt。</span><span class="sxs-lookup"><span data-stu-id="b4f94-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="b4f94-160">11 Dez。</span><span class="sxs-lookup"><span data-stu-id="b4f94-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="b4f94-161">義大利文</span><span class="sxs-lookup"><span data-stu-id="b4f94-161">Italian</span></span>
    
  - <span data-ttu-id="b4f94-162">gennaio，febbraio、 marzo、 aprile、 maggio、 giugno、 luglio、 agosto、 settembre，ottobre，novembre dicembre</span><span class="sxs-lookup"><span data-stu-id="b4f94-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="b4f94-163">genn。</span><span class="sxs-lookup"><span data-stu-id="b4f94-163">genn.</span></span> <span data-ttu-id="b4f94-164">febbr。</span><span class="sxs-lookup"><span data-stu-id="b4f94-164">febbr.</span></span> <span data-ttu-id="b4f94-165">mar。</span><span class="sxs-lookup"><span data-stu-id="b4f94-165">mar.</span></span> <span data-ttu-id="b4f94-166">apr。</span><span class="sxs-lookup"><span data-stu-id="b4f94-166">apr.</span></span> <span data-ttu-id="b4f94-167">magg。</span><span class="sxs-lookup"><span data-stu-id="b4f94-167">magg.</span></span> <span data-ttu-id="b4f94-168">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="b4f94-168">giugno luglio ag.</span></span> <span data-ttu-id="b4f94-169">是家。</span><span class="sxs-lookup"><span data-stu-id="b4f94-169">sett.</span></span> <span data-ttu-id="b4f94-170">ott。</span><span class="sxs-lookup"><span data-stu-id="b4f94-170">ott.</span></span> <span data-ttu-id="b4f94-171">11 月。</span><span class="sxs-lookup"><span data-stu-id="b4f94-171">nov.</span></span> <span data-ttu-id="b4f94-172">字典。</span><span class="sxs-lookup"><span data-stu-id="b4f94-172">dic.</span></span>
    
- <span data-ttu-id="b4f94-173">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="b4f94-173">Portuguese</span></span>
    
  - <span data-ttu-id="b4f94-174">janeiro fevereiro、 março、 marco、 abril、 maio、 junho、 julho，agosto，setembro、 outubro、 novembro、 dezembro</span><span class="sxs-lookup"><span data-stu-id="b4f94-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="b4f94-175">jan fev mar abr mai 年 7 月以前 11 月 dez 出設定</span><span class="sxs-lookup"><span data-stu-id="b4f94-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="b4f94-176">西班牙文</span><span class="sxs-lookup"><span data-stu-id="b4f94-176">Spanish</span></span>
    
  - <span data-ttu-id="b4f94-177">enero，febrero、 marzo、 abril、 mayo、 junio、 julio、 agosto、 septiembre，octubre，noviembre diciembre</span><span class="sxs-lookup"><span data-stu-id="b4f94-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="b4f94-178">enero 年。</span><span class="sxs-lookup"><span data-stu-id="b4f94-178">enero feb.</span></span> <span data-ttu-id="b4f94-179">marzo abr.</span><span class="sxs-lookup"><span data-stu-id="b4f94-179">marzo abr.</span></span> <span data-ttu-id="b4f94-180">mayo 年。</span><span class="sxs-lookup"><span data-stu-id="b4f94-180">mayo jun.</span></span> <span data-ttu-id="b4f94-181">年 7 月。</span><span class="sxs-lookup"><span data-stu-id="b4f94-181">jul.</span></span> <span data-ttu-id="b4f94-182">agosto sept./集。</span><span class="sxs-lookup"><span data-stu-id="b4f94-182">agosto sept./set.</span></span> <span data-ttu-id="b4f94-183">oct。</span><span class="sxs-lookup"><span data-stu-id="b4f94-183">oct.</span></span> <span data-ttu-id="b4f94-184">11 月。</span><span class="sxs-lookup"><span data-stu-id="b4f94-184">nov.</span></span> <span data-ttu-id="b4f94-185">字典。</span><span class="sxs-lookup"><span data-stu-id="b4f94-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="b4f94-186">Func_eu_date1 （已過時）</span><span class="sxs-lookup"><span data-stu-id="b4f94-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="b4f94-187">這個函數已過時，因為它支援僅葡萄牙文的月份名稱，這樣現在已包含於`Func_eu_date`上述函數。</span><span class="sxs-lookup"><span data-stu-id="b4f94-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="b4f94-188">此函數會尋找常用於葡萄牙文格式的日期。</span><span class="sxs-lookup"><span data-stu-id="b4f94-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="b4f94-189">這個函數的格式是相同`Func_eu_date`、 如上所述僅中所用的語言。</span><span class="sxs-lookup"><span data-stu-id="b4f94-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="b4f94-190">範例:</span><span class="sxs-lookup"><span data-stu-id="b4f94-190">Examples:</span></span>
  
- <span data-ttu-id="b4f94-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="b4f94-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-192">02 dez 2016</span></span>
    
- <span data-ttu-id="b4f94-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="b4f94-193">2 Dez 16</span></span>
    
- <span data-ttu-id="b4f94-194">2016 年 2 月 12 日</span><span class="sxs-lookup"><span data-stu-id="b4f94-194">2/12/2016</span></span>
    
- <span data-ttu-id="b4f94-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="b4f94-195">02/12/16</span></span>
    
- <span data-ttu-id="b4f94-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="b4f94-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="b4f94-197">2-12-16</span></span>
    
<span data-ttu-id="b4f94-198">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="b4f94-198">Accepted month names:</span></span>
  
- <span data-ttu-id="b4f94-199">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="b4f94-199">Portuguese</span></span>
    
  - <span data-ttu-id="b4f94-200">janeiro fevereiro、 março、 marco、 abril、 maio、 junho、 julho，agosto，setembro、 outubro、 novembro、 dezembro</span><span class="sxs-lookup"><span data-stu-id="b4f94-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="b4f94-201">jan fev mar abr mai 年 7 月以前 11 月 dez 出設定</span><span class="sxs-lookup"><span data-stu-id="b4f94-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="b4f94-202">Func_eu_date2 （已過時）</span><span class="sxs-lookup"><span data-stu-id="b4f94-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="b4f94-203">這個函數已過時，因為它支援僅荷蘭文的月份名稱，這樣現在已包含於`Func_eu_date`上述函數。</span><span class="sxs-lookup"><span data-stu-id="b4f94-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="b4f94-204">此函數會尋找在荷蘭文中常用的格式的日期。</span><span class="sxs-lookup"><span data-stu-id="b4f94-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="b4f94-205">這個函數的格式是相同`Func_eu_date`、 如上所述僅中所用的語言。</span><span class="sxs-lookup"><span data-stu-id="b4f94-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="b4f94-206">範例:</span><span class="sxs-lookup"><span data-stu-id="b4f94-206">Examples:</span></span>
  
- <span data-ttu-id="b4f94-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="b4f94-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-208">02 mei 2016</span></span>
    
- <span data-ttu-id="b4f94-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="b4f94-209">2 Mei 16</span></span>
    
- <span data-ttu-id="b4f94-210">2016 年 2 月 12 日</span><span class="sxs-lookup"><span data-stu-id="b4f94-210">2/12/2016</span></span>
    
- <span data-ttu-id="b4f94-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="b4f94-211">02/12/16</span></span>
    
- <span data-ttu-id="b4f94-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="b4f94-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="b4f94-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="b4f94-213">2-12-16</span></span>
    
<span data-ttu-id="b4f94-214">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="b4f94-214">Accepted month names:</span></span>
  
- <span data-ttu-id="b4f94-215">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="b4f94-215">Dutch</span></span>
    
  - <span data-ttu-id="b4f94-216">januari，februari，maart、 April、 mei、 juni、 juli、 奧古斯特一，September、 ocktober，年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="b4f94-217">年 2 月 maart apr mei 年 7 月年 8 月 sep 年 10 月 okt 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="b4f94-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="b4f94-218">Func_expiration_date</span></span>

<span data-ttu-id="b4f94-219">此函數會尋找常使用的信用卡和轉帳卡，但不包括因月份的天數的格式的日期。</span><span class="sxs-lookup"><span data-stu-id="b4f94-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="b4f94-220">此函數會比對中的 「 月/年 」、 「 月-年 」、 「 [月份名稱] 年 」 和 「 [月份縮寫] 年 」 格式的日期。</span><span class="sxs-lookup"><span data-stu-id="b4f94-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="b4f94-221">縮寫的月份的名稱不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="b4f94-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="b4f94-222">範例:</span><span class="sxs-lookup"><span data-stu-id="b4f94-222">Examples:</span></span>
  
- <span data-ttu-id="b4f94-223">MM/YY--例如，01/11 或 1/11</span><span class="sxs-lookup"><span data-stu-id="b4f94-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="b4f94-224">MM/YYYY--例如，01/2011年或 1/2011</span><span class="sxs-lookup"><span data-stu-id="b4f94-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="b4f94-225">MM-YY--例如，01-22 或 1-11</span><span class="sxs-lookup"><span data-stu-id="b4f94-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="b4f94-226">MM-YYYY--例如，01-2000年或 1-2000</span><span class="sxs-lookup"><span data-stu-id="b4f94-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="b4f94-227">下列格式支援 YY 或 YYYY:</span><span class="sxs-lookup"><span data-stu-id="b4f94-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="b4f94-228">-MONTH-YYYY-例如。Jan 2010 或 january 2010 或 Jan 10 或 january-10</span><span class="sxs-lookup"><span data-stu-id="b4f94-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="b4f94-229">Month YYYY--例如，' january 2010' 或 'Jan 2010' 或' january 10' 或 ' Jan 10'</span><span class="sxs-lookup"><span data-stu-id="b4f94-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="b4f94-230">MonthYYYY--例如，'january2010' 或 'Jan2010' 或 'january10' 或者 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="b4f94-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="b4f94-231">Month/YYYY--例如，' january/2010 '或' Jan/2010 '、 'january/10' 或 ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="b4f94-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="b4f94-232">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="b4f94-232">Accepted month names:</span></span>
  
- <span data-ttu-id="b4f94-233">英文</span><span class="sxs-lookup"><span data-stu-id="b4f94-233">English</span></span>
    
  - <span data-ttu-id="b4f94-234">January、 February、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="b4f94-235">Jan 年 3 月 Apr 可能年 6 月 7 日年 10 月 11 月 12 月</span><span class="sxs-lookup"><span data-stu-id="b4f94-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="b4f94-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="b4f94-236">Func_us_address</span></span>

<span data-ttu-id="b4f94-237">此函數尋找美國狀態名稱或郵寄縮寫後面接著有效的郵遞區號，就像它們用於郵寄地址。</span><span class="sxs-lookup"><span data-stu-id="b4f94-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="b4f94-238">郵遞區號必須是郵遞區號的下列其中一個正確的美國狀態名稱或縮寫相關聯。</span><span class="sxs-lookup"><span data-stu-id="b4f94-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="b4f94-239">美國狀態名稱和郵遞區號無法以字母或標點符號分隔。</span><span class="sxs-lookup"><span data-stu-id="b4f94-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="b4f94-240">範例:</span><span class="sxs-lookup"><span data-stu-id="b4f94-240">Examples:</span></span>
  
- <span data-ttu-id="b4f94-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="b4f94-241">Washington 98052</span></span>
    
- <span data-ttu-id="b4f94-242">Washington 98052 9998</span><span class="sxs-lookup"><span data-stu-id="b4f94-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="b4f94-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="b4f94-243">WA 98052</span></span>
    
- <span data-ttu-id="b4f94-244">WA 98052 9998</span><span class="sxs-lookup"><span data-stu-id="b4f94-244">WA 98052-9998</span></span>
    

