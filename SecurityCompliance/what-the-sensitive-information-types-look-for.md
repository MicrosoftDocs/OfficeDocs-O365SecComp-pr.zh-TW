---
title: 敏感性資訊類型所尋找的項目
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: d161435c75149183289cfbfd6abe79d55e371e31
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266869"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="86dd5-104">敏感性資訊類型所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="86dd5-104">What the sensitive information types look for</span></span>

<span data-ttu-id="86dd5-105">Office 365 安全性中的資料遺失防護 (DLP)&amp;合規性中心包含許多可供您可以使用 DLP 原則中的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="86dd5-106">本主題列出所有的這些敏感資訊類型，並顯示 DLP 原則看起來當它偵測到每個類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="86dd5-107">敏感資訊類型是由能夠識別規則運算式或函數的模式所定義。</span><span class="sxs-lookup"><span data-stu-id="86dd5-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="86dd5-108">此外，例如關鍵字和總和檢查碼佐證性證據可以用來識別敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="86dd5-109">信賴等級和接近性也會用於評估程序。</span><span class="sxs-lookup"><span data-stu-id="86dd5-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="86dd5-110">阿拉巴馬州路由號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-111">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-111">Format</span></span>

<span data-ttu-id="86dd5-112">這可能是採用格式化或未格式化模式的 9 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-113">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-113">Pattern</span></span>

<span data-ttu-id="86dd5-114">格式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-114">Formatted:</span></span>
- <span data-ttu-id="86dd5-115">以 0、 1、 2、 3、 6、 7 或 8 開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="86dd5-116">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-116">A hyphen</span></span>
- <span data-ttu-id="86dd5-117">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-117">Four digits</span></span>
- <span data-ttu-id="86dd5-118">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-118">A hyphen</span></span>
- <span data-ttu-id="86dd5-119">數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-119">A digit</span></span>

<span data-ttu-id="86dd5-120">未格式化： 9 個連續數字以 0、 1、 2、 3、 6、 7 或 8 開頭</span><span class="sxs-lookup"><span data-stu-id="86dd5-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="86dd5-121">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-121">Checksum</span></span>

<span data-ttu-id="86dd5-122">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-123">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-123">Definition</span></span>

<span data-ttu-id="86dd5-124">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-126">找不到來自 Keyword_ABA_Routing 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="86dd5-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="86dd5-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="86dd5-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="86dd5-129">阿拉巴馬州銀行</span><span class="sxs-lookup"><span data-stu-id="86dd5-129">aba</span></span>
- <span data-ttu-id="86dd5-130">阿拉巴馬州銀行 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-130">aba #</span></span>
- <span data-ttu-id="86dd5-131">阿拉巴馬州銀行路由 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-131">aba routing #</span></span>
- <span data-ttu-id="86dd5-132">阿拉巴馬州銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-132">aba routing number</span></span>
- <span data-ttu-id="86dd5-133">阿拉巴馬州銀行 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-133">aba#</span></span>
- <span data-ttu-id="86dd5-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="86dd5-134">abarouting#</span></span>
- <span data-ttu-id="86dd5-135">阿拉巴馬州銀行號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-135">aba number</span></span>
- <span data-ttu-id="86dd5-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-136">abaroutingnumber</span></span>
- <span data-ttu-id="86dd5-137">美國銀行關聯路由 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-137">american bank association routing #</span></span>
- <span data-ttu-id="86dd5-138">美國銀行關聯路由號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-138">american bank association routing number</span></span>
- <span data-ttu-id="86dd5-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="86dd5-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="86dd5-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="86dd5-141">銀行路由號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-141">bank routing number</span></span>
- <span data-ttu-id="86dd5-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="86dd5-142">bankrouting#</span></span>
- <span data-ttu-id="86dd5-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-143">bankroutingnumber</span></span>
- <span data-ttu-id="86dd5-144">路由傳輸數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-144">routing transit number</span></span>
- <span data-ttu-id="86dd5-145">RTN</span><span class="sxs-lookup"><span data-stu-id="86dd5-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="86dd5-146">阿根廷國民識別 （dni） 碼數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-147">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-147">Format</span></span>

<span data-ttu-id="86dd5-148">以句點分隔的八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-149">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-149">Pattern</span></span>

<span data-ttu-id="86dd5-150">八位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-150">Eight digits:</span></span>
- <span data-ttu-id="86dd5-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-151">Two digits</span></span>
- <span data-ttu-id="86dd5-152">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-152">A period</span></span>
- <span data-ttu-id="86dd5-153">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-153">Three digits</span></span>
- <span data-ttu-id="86dd5-154">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-154">A period</span></span>
- <span data-ttu-id="86dd5-155">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-156">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-156">Checksum</span></span>

<span data-ttu-id="86dd5-157">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-158">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-158">Definition</span></span>

<span data-ttu-id="86dd5-159">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-160">規則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-161">找不到來自 Keyword_argentina_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="86dd5-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="86dd5-164">阿根廷國民識別數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="86dd5-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-165">Identity</span></span> 
- <span data-ttu-id="86dd5-166">Identification 國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="86dd5-167">DNI</span><span class="sxs-lookup"><span data-stu-id="86dd5-167">DNI</span></span> 
- <span data-ttu-id="86dd5-168">NIC 國民身分登錄的人員</span><span class="sxs-lookup"><span data-stu-id="86dd5-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="86dd5-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="86dd5-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="86dd5-170">Registro Nacional de 美國的人物代表</span><span class="sxs-lookup"><span data-stu-id="86dd5-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="86dd5-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="86dd5-171">Identidad</span></span> 
- <span data-ttu-id="86dd5-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="86dd5-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="86dd5-173">澳洲銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-174">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-174">Format</span></span>

<span data-ttu-id="86dd5-175">包含或不含銀行代號的 6-10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-176">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-176">Pattern</span></span>

<span data-ttu-id="86dd5-177">帳戶號碼為 6-10 位數。</span><span class="sxs-lookup"><span data-stu-id="86dd5-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="86dd5-178">澳洲銀行代號：</span><span class="sxs-lookup"><span data-stu-id="86dd5-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="86dd5-179">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-179">Three digits</span></span> 
- <span data-ttu-id="86dd5-180">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-180">A hyphen</span></span> 
- <span data-ttu-id="86dd5-181">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-182">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-182">Checksum</span></span>

<span data-ttu-id="86dd5-183">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-184">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-184">Definition</span></span>

<span data-ttu-id="86dd5-185">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-186">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。.</span><span class="sxs-lookup"><span data-stu-id="86dd5-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="86dd5-187">找不到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="86dd5-188">規則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="86dd5-189">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-190">規則運算式 Regex_australia_bank_account_number 找到符合模式的內容。.</span><span class="sxs-lookup"><span data-stu-id="86dd5-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="86dd5-191">找不到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="86dd5-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="86dd5-194">swift 銀行代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-194">swift bank code</span></span>
- <span data-ttu-id="86dd5-195">對應的銀行</span><span class="sxs-lookup"><span data-stu-id="86dd5-195">correspondent bank</span></span>
- <span data-ttu-id="86dd5-196">基底的貨幣</span><span class="sxs-lookup"><span data-stu-id="86dd5-196">base currency</span></span>
- <span data-ttu-id="86dd5-197">usa 帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-197">usa account</span></span>
- <span data-ttu-id="86dd5-198">持有者地址</span><span class="sxs-lookup"><span data-stu-id="86dd5-198">holder address</span></span>
- <span data-ttu-id="86dd5-199">銀行地址</span><span class="sxs-lookup"><span data-stu-id="86dd5-199">bank address</span></span>
- <span data-ttu-id="86dd5-200">資訊的帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-200">information account</span></span>
- <span data-ttu-id="86dd5-201">基金傳輸</span><span class="sxs-lookup"><span data-stu-id="86dd5-201">fund transfers</span></span>
- <span data-ttu-id="86dd5-202">銀行費用</span><span class="sxs-lookup"><span data-stu-id="86dd5-202">bank charges</span></span>
- <span data-ttu-id="86dd5-203">銀行詳細資料</span><span class="sxs-lookup"><span data-stu-id="86dd5-203">bank details</span></span>
- <span data-ttu-id="86dd5-204">銀行業資訊</span><span class="sxs-lookup"><span data-stu-id="86dd5-204">banking information</span></span>
- <span data-ttu-id="86dd5-205">完整名稱</span><span class="sxs-lookup"><span data-stu-id="86dd5-205">full names</span></span>
- <span data-ttu-id="86dd5-206">iaea</span><span class="sxs-lookup"><span data-stu-id="86dd5-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="86dd5-207">澳洲駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-208">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-208">Format</span></span>

<span data-ttu-id="86dd5-209">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-210">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-210">Pattern</span></span>

<span data-ttu-id="86dd5-211">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="86dd5-212">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-213">Two digits</span></span> 
- <span data-ttu-id="86dd5-214">五個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="86dd5-215">或</span><span class="sxs-lookup"><span data-stu-id="86dd5-215">OR</span></span>

- <span data-ttu-id="86dd5-216">1-2 選用字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-217">4-9 digits</span></span>

<span data-ttu-id="86dd5-218">或</span><span class="sxs-lookup"><span data-stu-id="86dd5-218">OR</span></span>

- <span data-ttu-id="86dd5-219">九個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-220">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-220">Checksum</span></span>

<span data-ttu-id="86dd5-221">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-222">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-222">Definition</span></span>

<span data-ttu-id="86dd5-223">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-224">規則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-225">找不到來自 Keyword_australia_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="86dd5-226">找不到來自 Keyword_australia_drivers_license_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="86dd5-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="86dd5-229">國際主導許可</span><span class="sxs-lookup"><span data-stu-id="86dd5-229">international driving permits</span></span>
- <span data-ttu-id="86dd5-230">澳洲汽車關聯</span><span class="sxs-lookup"><span data-stu-id="86dd5-230">australian automobile association</span></span>
- <span data-ttu-id="86dd5-231">國際主導允許</span><span class="sxs-lookup"><span data-stu-id="86dd5-231">international driving permit</span></span>
- <span data-ttu-id="86dd5-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="86dd5-232">DriverLicence</span></span>
- <span data-ttu-id="86dd5-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="86dd5-233">DriverLicences</span></span>
- <span data-ttu-id="86dd5-234">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-234">Driver Lic</span></span>
- <span data-ttu-id="86dd5-235">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-235">Driver Licence</span></span>
- <span data-ttu-id="86dd5-236">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-236">Driver Licences</span></span>
- <span data-ttu-id="86dd5-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-237">DriversLic</span></span>
- <span data-ttu-id="86dd5-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="86dd5-238">DriversLicence</span></span>
- <span data-ttu-id="86dd5-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="86dd5-239">DriversLicences</span></span>
- <span data-ttu-id="86dd5-240">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-240">Drivers Lic</span></span>
- <span data-ttu-id="86dd5-241">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-241">Drivers Lics</span></span>
- <span data-ttu-id="86dd5-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-242">Drivers Licence</span></span>
- <span data-ttu-id="86dd5-243">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-243">Drivers Licences</span></span>
- <span data-ttu-id="86dd5-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-244">Driver'Lic</span></span>
- <span data-ttu-id="86dd5-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-245">Driver'Lics</span></span>
- <span data-ttu-id="86dd5-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="86dd5-246">Driver'Licence</span></span>
- <span data-ttu-id="86dd5-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="86dd5-247">Driver'Licences</span></span>
- <span data-ttu-id="86dd5-248">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-248">Driver' Lic</span></span>
- <span data-ttu-id="86dd5-249">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-249">Driver' Lics</span></span>
- <span data-ttu-id="86dd5-250">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-250">Driver' Licence</span></span>
- <span data-ttu-id="86dd5-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-251">Driver' Licences</span></span>
- <span data-ttu-id="86dd5-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-252">Driver'sLic</span></span>
- <span data-ttu-id="86dd5-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-253">Driver'sLics</span></span>
- <span data-ttu-id="86dd5-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="86dd5-254">Driver'sLicence</span></span>
- <span data-ttu-id="86dd5-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="86dd5-255">Driver'sLicences</span></span>
- <span data-ttu-id="86dd5-256">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-256">Driver's Lic</span></span>
- <span data-ttu-id="86dd5-257">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-257">Driver's Lics</span></span>
- <span data-ttu-id="86dd5-258">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-258">Driver's Licence</span></span>
- <span data-ttu-id="86dd5-259">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-259">Driver's Licences</span></span>
- <span data-ttu-id="86dd5-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-260">DriverLic#</span></span>
- <span data-ttu-id="86dd5-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-261">DriverLics#</span></span>
- <span data-ttu-id="86dd5-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-262">DriverLicence#</span></span>
- <span data-ttu-id="86dd5-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-263">DriverLicences#</span></span>
- <span data-ttu-id="86dd5-264">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-264">Driver Lic#</span></span>
- <span data-ttu-id="86dd5-265">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-265">Driver Lics#</span></span>
- <span data-ttu-id="86dd5-266">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-266">Driver Licence#</span></span>
- <span data-ttu-id="86dd5-267">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-267">Driver Licences#</span></span>
- <span data-ttu-id="86dd5-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-268">DriversLic#</span></span>
- <span data-ttu-id="86dd5-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-269">DriversLics#</span></span>
- <span data-ttu-id="86dd5-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-270">DriversLicence#</span></span>
- <span data-ttu-id="86dd5-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-271">DriversLicences#</span></span>
- <span data-ttu-id="86dd5-272">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-272">Drivers Lic#</span></span>
- <span data-ttu-id="86dd5-273">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-273">Drivers Lics#</span></span>
- <span data-ttu-id="86dd5-274">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-274">Drivers Licence#</span></span>
- <span data-ttu-id="86dd5-275">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-275">Drivers Licences#</span></span>
- <span data-ttu-id="86dd5-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-276">Driver'Lic#</span></span>
- <span data-ttu-id="86dd5-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-277">Driver'Lics#</span></span>
- <span data-ttu-id="86dd5-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-278">Driver'Licence#</span></span>
- <span data-ttu-id="86dd5-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-279">Driver'Licences#</span></span>
- <span data-ttu-id="86dd5-280">驅動程式 ' Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-280">Driver' Lic#</span></span>
- <span data-ttu-id="86dd5-281">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-281">Driver' Lics#</span></span>
- <span data-ttu-id="86dd5-282">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-282">Driver' Licence#</span></span>
- <span data-ttu-id="86dd5-283">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-283">Driver' Licences#</span></span>
- <span data-ttu-id="86dd5-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-284">Driver'sLic#</span></span>
- <span data-ttu-id="86dd5-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-285">Driver'sLics#</span></span>
- <span data-ttu-id="86dd5-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-286">Driver'sLicence#</span></span>
- <span data-ttu-id="86dd5-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-287">Driver'sLicences#</span></span>
- <span data-ttu-id="86dd5-288">駕 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-288">Driver's Lic#</span></span>
- <span data-ttu-id="86dd5-289">駕 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-289">Driver's Lics#</span></span>
- <span data-ttu-id="86dd5-290">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-290">Driver's Licence#</span></span>
- <span data-ttu-id="86dd5-291">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="86dd5-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="86dd5-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="86dd5-293">aaa</span><span class="sxs-lookup"><span data-stu-id="86dd5-293">aaa</span></span>
- <span data-ttu-id="86dd5-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="86dd5-294">DriverLicense</span></span>
- <span data-ttu-id="86dd5-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-295">DriverLicenses</span></span>
- <span data-ttu-id="86dd5-296">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-296">Driver License</span></span>
- <span data-ttu-id="86dd5-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-297">Driver Licenses</span></span>
- <span data-ttu-id="86dd5-298">執照</span><span class="sxs-lookup"><span data-stu-id="86dd5-298">DriversLicense</span></span>
- <span data-ttu-id="86dd5-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-299">DriversLicenses</span></span>
- <span data-ttu-id="86dd5-300">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-300">Drivers License</span></span>
- <span data-ttu-id="86dd5-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-301">Drivers Licenses</span></span>
- <span data-ttu-id="86dd5-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="86dd5-302">Driver'License</span></span>
- <span data-ttu-id="86dd5-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-303">Driver'Licenses</span></span>
- <span data-ttu-id="86dd5-304">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-304">Driver' License</span></span>
- <span data-ttu-id="86dd5-305">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-305">Driver' Licenses</span></span>
- <span data-ttu-id="86dd5-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="86dd5-306">Driver'sLicense</span></span>
- <span data-ttu-id="86dd5-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-307">Driver'sLicenses</span></span>
- <span data-ttu-id="86dd5-308">駕照</span><span class="sxs-lookup"><span data-stu-id="86dd5-308">Driver's License</span></span>
- <span data-ttu-id="86dd5-309">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-309">Driver's Licenses</span></span>
- <span data-ttu-id="86dd5-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="86dd5-310">DriverLicense#</span></span>
- <span data-ttu-id="86dd5-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-311">DriverLicenses#</span></span>
- <span data-ttu-id="86dd5-312">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-312">Driver License#</span></span>
- <span data-ttu-id="86dd5-313">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-313">Driver Licenses#</span></span>
- <span data-ttu-id="86dd5-314">執照 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-314">DriversLicense#</span></span>
- <span data-ttu-id="86dd5-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-315">DriversLicenses#</span></span>
- <span data-ttu-id="86dd5-316">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-316">Drivers License#</span></span>
- <span data-ttu-id="86dd5-317">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-317">Drivers Licenses#</span></span>
- <span data-ttu-id="86dd5-318">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="86dd5-318">Driver'License#</span></span>
- <span data-ttu-id="86dd5-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-319">Driver'Licenses#</span></span>
- <span data-ttu-id="86dd5-320">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-320">Driver' License#</span></span>
- <span data-ttu-id="86dd5-321">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-321">Driver' Licenses#</span></span>
- <span data-ttu-id="86dd5-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="86dd5-322">Driver'sLicense#</span></span>
- <span data-ttu-id="86dd5-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="86dd5-324">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-324">Driver's License#</span></span>
- <span data-ttu-id="86dd5-325">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="86dd5-326">澳洲醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-327">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-327">Format</span></span>

<span data-ttu-id="86dd5-328">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-329">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-329">Pattern</span></span>

<span data-ttu-id="86dd5-330">10-11 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-330">10-11 digits:</span></span>
- <span data-ttu-id="86dd5-331">第一個數字是 2-6 的範圍內</span><span class="sxs-lookup"><span data-stu-id="86dd5-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="86dd5-332">第九個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="86dd5-333">第十個數字是簽發碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="86dd5-334">第十一個數字 （選擇性） 是個人碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-335">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-335">Checksum</span></span>

<span data-ttu-id="86dd5-336">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-337">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-337">Definition</span></span>

<span data-ttu-id="86dd5-338">DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-339">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-340">找不到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="86dd5-341">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-341">The checksum passes.</span></span>

<span data-ttu-id="86dd5-342">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-343">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-344">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="86dd5-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="86dd5-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="86dd5-347">銀行帳戶詳細資料</span><span class="sxs-lookup"><span data-stu-id="86dd5-347">bank account details</span></span>
- <span data-ttu-id="86dd5-348">medicare 付款</span><span class="sxs-lookup"><span data-stu-id="86dd5-348">medicare payments</span></span>
- <span data-ttu-id="86dd5-349">抵押帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-349">mortgage account</span></span>
- <span data-ttu-id="86dd5-350">銀行付款</span><span class="sxs-lookup"><span data-stu-id="86dd5-350">bank payments</span></span>
- <span data-ttu-id="86dd5-351">資訊分支</span><span class="sxs-lookup"><span data-stu-id="86dd5-351">information branch</span></span>
- <span data-ttu-id="86dd5-352">信用卡貸款</span><span class="sxs-lookup"><span data-stu-id="86dd5-352">credit card loan</span></span>
- <span data-ttu-id="86dd5-353">人力服務部門</span><span class="sxs-lookup"><span data-stu-id="86dd5-353">department of human services</span></span>
- <span data-ttu-id="86dd5-354">本機服務</span><span class="sxs-lookup"><span data-stu-id="86dd5-354">local service</span></span>
- <span data-ttu-id="86dd5-355">medicare</span><span class="sxs-lookup"><span data-stu-id="86dd5-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="86dd5-356">澳洲護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-357">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-357">Format</span></span>

<span data-ttu-id="86dd5-358">字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-359">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-359">Pattern</span></span>

<span data-ttu-id="86dd5-360">尾隨七位數字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-361">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-361">Checksum</span></span>

<span data-ttu-id="86dd5-362">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-363">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-363">Definition</span></span>

<span data-ttu-id="86dd5-364">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-365">規則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-366">找不到來自 Keyword_passport 或 Keyword_australia_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="86dd5-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-368">Keyword_passport</span></span>

- <span data-ttu-id="86dd5-369">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-369">Passport Number</span></span>
- <span data-ttu-id="86dd5-370">Passport 否</span><span class="sxs-lookup"><span data-stu-id="86dd5-370">Passport No</span></span>
- <span data-ttu-id="86dd5-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-371">Passport #</span></span>
- <span data-ttu-id="86dd5-372">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-372">Passport#</span></span>
- <span data-ttu-id="86dd5-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="86dd5-373">PassportID</span></span>
- <span data-ttu-id="86dd5-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="86dd5-374">Passportno</span></span>
- <span data-ttu-id="86dd5-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-375">passportnumber</span></span>
- <span data-ttu-id="86dd5-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="86dd5-376">パスポート</span></span>
- <span data-ttu-id="86dd5-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-377">パスポート番号</span></span>
- <span data-ttu-id="86dd5-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="86dd5-378">パスポートのNum</span></span>
- <span data-ttu-id="86dd5-379">パスポート #</span><span class="sxs-lookup"><span data-stu-id="86dd5-379">パスポート ＃</span></span> 
- <span data-ttu-id="86dd5-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="86dd5-380">Numéro de passeport</span></span>
- <span data-ttu-id="86dd5-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="86dd5-381">Passeport n °</span></span>
- <span data-ttu-id="86dd5-382">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="86dd5-382">Passeport Non</span></span>
- <span data-ttu-id="86dd5-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-383">Passeport #</span></span>
- <span data-ttu-id="86dd5-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-384">Passeport#</span></span>
- <span data-ttu-id="86dd5-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="86dd5-385">PasseportNon</span></span>
- <span data-ttu-id="86dd5-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="86dd5-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="86dd5-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="86dd5-388">passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-388">passport</span></span>
- <span data-ttu-id="86dd5-389">passport 詳細資料</span><span class="sxs-lookup"><span data-stu-id="86dd5-389">passport details</span></span>
- <span data-ttu-id="86dd5-390">immigration 和公民</span><span class="sxs-lookup"><span data-stu-id="86dd5-390">immigration and citizenship</span></span>
- <span data-ttu-id="86dd5-391">澳大利亞聯邦</span><span class="sxs-lookup"><span data-stu-id="86dd5-391">commonwealth of australia</span></span>
- <span data-ttu-id="86dd5-392">immigration 的部門</span><span class="sxs-lookup"><span data-stu-id="86dd5-392">department of immigration</span></span>
- <span data-ttu-id="86dd5-393">住家地址</span><span class="sxs-lookup"><span data-stu-id="86dd5-393">residential address</span></span>
- <span data-ttu-id="86dd5-394">immigration 和公民的部門</span><span class="sxs-lookup"><span data-stu-id="86dd5-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="86dd5-395">visa</span><span class="sxs-lookup"><span data-stu-id="86dd5-395">visa</span></span>
- <span data-ttu-id="86dd5-396">國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-396">national identity card</span></span>
- <span data-ttu-id="86dd5-397">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-397">passport number</span></span>
- <span data-ttu-id="86dd5-398">出差的文件</span><span class="sxs-lookup"><span data-stu-id="86dd5-398">travel document</span></span>
- <span data-ttu-id="86dd5-399">授權單位</span><span class="sxs-lookup"><span data-stu-id="86dd5-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="86dd5-400">澳洲稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-401">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-401">Format</span></span>

<span data-ttu-id="86dd5-402">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-403">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-403">Pattern</span></span>

<span data-ttu-id="86dd5-404">8-9 位數，通常會有空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="86dd5-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="86dd5-405">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-405">Three digits</span></span> 
- <span data-ttu-id="86dd5-406">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-406">An optional space</span></span> 
- <span data-ttu-id="86dd5-407">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-407">Three digits</span></span> 
- <span data-ttu-id="86dd5-408">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-408">An optional space</span></span> 
- <span data-ttu-id="86dd5-409">2-3 位數，最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-410">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-410">Checksum</span></span>

<span data-ttu-id="86dd5-411">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-412">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-412">Definition</span></span>

<span data-ttu-id="86dd5-413">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-414">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-415">找不到來自 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="86dd5-416">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="86dd5-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="86dd5-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="86dd5-419">澳洲商務號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-419">australian business number</span></span>
- <span data-ttu-id="86dd5-420">臨界稅率</span><span class="sxs-lookup"><span data-stu-id="86dd5-420">marginal tax rate</span></span>
- <span data-ttu-id="86dd5-421">medicare 募集</span><span class="sxs-lookup"><span data-stu-id="86dd5-421">medicare levy</span></span>
- <span data-ttu-id="86dd5-422">組合數</span><span class="sxs-lookup"><span data-stu-id="86dd5-422">portfolio number</span></span>
- <span data-ttu-id="86dd5-423">服務老手</span><span class="sxs-lookup"><span data-stu-id="86dd5-423">service veterans</span></span>
- <span data-ttu-id="86dd5-424">扣繳稅</span><span class="sxs-lookup"><span data-stu-id="86dd5-424">withholding tax</span></span>
- <span data-ttu-id="86dd5-425">個別的稅務傳回</span><span class="sxs-lookup"><span data-stu-id="86dd5-425">individual tax return</span></span>
- <span data-ttu-id="86dd5-426">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="86dd5-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="86dd5-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="86dd5-428">00000000</span><span class="sxs-lookup"><span data-stu-id="86dd5-428">00000000</span></span>
- <span data-ttu-id="86dd5-429">11111111</span><span class="sxs-lookup"><span data-stu-id="86dd5-429">11111111</span></span>
- <span data-ttu-id="86dd5-430">22222222</span><span class="sxs-lookup"><span data-stu-id="86dd5-430">22222222</span></span>
- <span data-ttu-id="86dd5-431">33333333</span><span class="sxs-lookup"><span data-stu-id="86dd5-431">33333333</span></span>
- <span data-ttu-id="86dd5-432">44444444</span><span class="sxs-lookup"><span data-stu-id="86dd5-432">44444444</span></span>
- <span data-ttu-id="86dd5-433">55555555</span><span class="sxs-lookup"><span data-stu-id="86dd5-433">55555555</span></span>
- <span data-ttu-id="86dd5-434">66666666</span><span class="sxs-lookup"><span data-stu-id="86dd5-434">66666666</span></span>
- <span data-ttu-id="86dd5-435">77777777</span><span class="sxs-lookup"><span data-stu-id="86dd5-435">77777777</span></span>
- <span data-ttu-id="86dd5-436">88888888</span><span class="sxs-lookup"><span data-stu-id="86dd5-436">88888888</span></span>
- <span data-ttu-id="86dd5-437">99999999</span><span class="sxs-lookup"><span data-stu-id="86dd5-437">99999999</span></span>
- <span data-ttu-id="86dd5-438">000000000</span><span class="sxs-lookup"><span data-stu-id="86dd5-438">000000000</span></span>
- <span data-ttu-id="86dd5-439">111111111</span><span class="sxs-lookup"><span data-stu-id="86dd5-439">111111111</span></span>
- <span data-ttu-id="86dd5-440">222222222</span><span class="sxs-lookup"><span data-stu-id="86dd5-440">222222222</span></span>
- <span data-ttu-id="86dd5-441">333333333</span><span class="sxs-lookup"><span data-stu-id="86dd5-441">333333333</span></span>
- <span data-ttu-id="86dd5-442">444444444</span><span class="sxs-lookup"><span data-stu-id="86dd5-442">444444444</span></span>
- <span data-ttu-id="86dd5-443">555555555</span><span class="sxs-lookup"><span data-stu-id="86dd5-443">555555555</span></span>
- <span data-ttu-id="86dd5-444">666666666</span><span class="sxs-lookup"><span data-stu-id="86dd5-444">666666666</span></span>
- <span data-ttu-id="86dd5-445">777777777</span><span class="sxs-lookup"><span data-stu-id="86dd5-445">777777777</span></span>
- <span data-ttu-id="86dd5-446">888888888</span><span class="sxs-lookup"><span data-stu-id="86dd5-446">888888888</span></span>
- <span data-ttu-id="86dd5-447">999999999</span><span class="sxs-lookup"><span data-stu-id="86dd5-447">999999999</span></span>
- <span data-ttu-id="86dd5-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="86dd5-448">0000000000</span></span>
- <span data-ttu-id="86dd5-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="86dd5-449">1111111111</span></span>
- <span data-ttu-id="86dd5-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="86dd5-450">2222222222</span></span>
- <span data-ttu-id="86dd5-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="86dd5-451">3333333333</span></span>
- <span data-ttu-id="86dd5-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="86dd5-452">4444444444</span></span>
- <span data-ttu-id="86dd5-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="86dd5-453">5555555555</span></span>
- <span data-ttu-id="86dd5-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="86dd5-454">6666666666</span></span>
- <span data-ttu-id="86dd5-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="86dd5-455">7777777777</span></span>
- <span data-ttu-id="86dd5-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="86dd5-456">8888888888</span></span>
- <span data-ttu-id="86dd5-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="86dd5-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="86dd5-458">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="86dd5-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-459">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-459">Format</span></span>

<span data-ttu-id="86dd5-460">將字串 「 DocumentDb 」 後面接著字元和下列模式中所述的字串。</span><span class="sxs-lookup"><span data-stu-id="86dd5-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-461">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-461">Pattern</span></span>

- <span data-ttu-id="86dd5-462">將字串 「 DocumentDb 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="86dd5-463">3-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-464">大於符號 (>)、 等號 （=）、 引號 （"） 或單引號 （'）</span><span class="sxs-lookup"><span data-stu-id="86dd5-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="86dd5-465">或的任何組合 86 較低的大寫字母、 數字，轉寄斜線 （/） 或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="86dd5-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="86dd5-466">兩個等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-467">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-467">Checksum</span></span>

<span data-ttu-id="86dd5-468">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-469">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-469">Definition</span></span>

<span data-ttu-id="86dd5-470">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-471">規則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-472">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-473">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-475">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-476">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-476">contoso</span></span>
- <span data-ttu-id="86dd5-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-477">fabrikam</span></span>
- <span data-ttu-id="86dd5-478">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-478">northwind</span></span>
- <span data-ttu-id="86dd5-479">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-479">sandbox</span></span>
- <span data-ttu-id="86dd5-480">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-480">onebox</span></span>
- <span data-ttu-id="86dd5-481">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-481">localhost</span></span>
- <span data-ttu-id="86dd5-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-482">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-483">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-484">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-484">com</span></span>
- <span data-ttu-id="86dd5-485">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-486">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="86dd5-487">Azure IAAS 資料庫連接字串和 Azure SQL 連線字串</span><span class="sxs-lookup"><span data-stu-id="86dd5-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-488">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-488">Format</span></span>

<span data-ttu-id="86dd5-489">字串 「 伺服器 」、 「 伺服器 」 或 「 資料來源 」 後面加上字元和下列，模式中所述的字串包含字串 「 cloudapp.azure。</span><span class="sxs-lookup"><span data-stu-id="86dd5-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-490">com 」 或者 「 cloudapp.azure。</span><span class="sxs-lookup"><span data-stu-id="86dd5-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-491">net 」 或者 「 database.windows。</span><span class="sxs-lookup"><span data-stu-id="86dd5-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-492">net 」 及 「 密碼 」 或 「 密碼 」 或 「 pwd 」 的字串。</span><span class="sxs-lookup"><span data-stu-id="86dd5-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-493">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-493">Pattern</span></span>

- <span data-ttu-id="86dd5-494">字串 「 伺服器 」、 「 伺服器 」 或者 「 資料來源 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="86dd5-495">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-496">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-496">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-497">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-498">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-499">將字串 「 cloudapp.azure。</span><span class="sxs-lookup"><span data-stu-id="86dd5-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-500">com 」、 「 cloudapp.azure。</span><span class="sxs-lookup"><span data-stu-id="86dd5-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-501">net 」，或者 「 database.windows。</span><span class="sxs-lookup"><span data-stu-id="86dd5-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-502">net 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-502">net"</span></span>
- <span data-ttu-id="86dd5-503">1-300 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-504">字串 「 密碼 」、 「 密碼 」 或者 「 pwd 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="86dd5-505">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-506">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-506">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-507">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-508">不是以分號 （;） 的一或多個字元的引號 （"） 或單引號 （'）</span><span class="sxs-lookup"><span data-stu-id="86dd5-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="86dd5-509">分號 （;）、 引號 （"） 或單引號 （'）</span><span class="sxs-lookup"><span data-stu-id="86dd5-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-510">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-510">Checksum</span></span>

<span data-ttu-id="86dd5-511">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-512">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-512">Definition</span></span>

<span data-ttu-id="86dd5-513">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-514">規則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-515">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-518">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-519">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-519">contoso</span></span>
- <span data-ttu-id="86dd5-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-520">fabrikam</span></span>
- <span data-ttu-id="86dd5-521">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-521">northwind</span></span>
- <span data-ttu-id="86dd5-522">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-522">sandbox</span></span>
- <span data-ttu-id="86dd5-523">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-523">onebox</span></span>
- <span data-ttu-id="86dd5-524">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-524">localhost</span></span>
- <span data-ttu-id="86dd5-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-525">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-526">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-527">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-527">com</span></span>
- <span data-ttu-id="86dd5-528">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-529">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="86dd5-530">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="86dd5-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-531">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-531">Format</span></span>

<span data-ttu-id="86dd5-532">將字串 「 主機名稱 」 後面加上字元和下方，模式中所述的字串包含字串 「 azure 裝置。</span><span class="sxs-lookup"><span data-stu-id="86dd5-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-533">net 」 和 「 SharedAccessKey 」。</span><span class="sxs-lookup"><span data-stu-id="86dd5-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-534">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-534">Pattern</span></span>

- <span data-ttu-id="86dd5-535">將字串 「 主機名稱 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-535">The string "HostName"</span></span>
- <span data-ttu-id="86dd5-536">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-537">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-537">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-538">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-539">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-540">將字串 「 azure 裝置。</span><span class="sxs-lookup"><span data-stu-id="86dd5-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-541">net 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-541">net"</span></span>
- <span data-ttu-id="86dd5-542">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-543">將字串 「 SharedAccessKey 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="86dd5-544">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-545">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-545">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-546">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-547">或的任何組合 43 較低的大寫字母、 數字，轉寄斜線 （/） 或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="86dd5-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="86dd5-548">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-549">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-549">Checksum</span></span>

<span data-ttu-id="86dd5-550">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-551">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-551">Definition</span></span>

<span data-ttu-id="86dd5-552">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-553">規則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-554">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-555">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-557">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-558">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-558">contoso</span></span>
- <span data-ttu-id="86dd5-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-559">fabrikam</span></span>
- <span data-ttu-id="86dd5-560">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-560">northwind</span></span>
- <span data-ttu-id="86dd5-561">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-561">sandbox</span></span>
- <span data-ttu-id="86dd5-562">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-562">onebox</span></span>
- <span data-ttu-id="86dd5-563">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-563">localhost</span></span>
- <span data-ttu-id="86dd5-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-564">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-565">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-566">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-566">com</span></span>
- <span data-ttu-id="86dd5-567">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-568">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="86dd5-569">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-570">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-570">Format</span></span>

<span data-ttu-id="86dd5-571">將字串 「 userpwd = 」 後面接著英數字元的字串。</span><span class="sxs-lookup"><span data-stu-id="86dd5-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-572">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-572">Pattern</span></span>

- <span data-ttu-id="86dd5-573">將字串 「 userpwd = 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-573">The string "userpwd="</span></span>
- <span data-ttu-id="86dd5-574">60 小寫字母或數字的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="86dd5-575">引號 （"）</span><span class="sxs-lookup"><span data-stu-id="86dd5-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-576">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-576">Checksum</span></span>

<span data-ttu-id="86dd5-577">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-578">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-578">Definition</span></span>

<span data-ttu-id="86dd5-579">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-580">規則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-581">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="86dd5-582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-584">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-585">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-585">contoso</span></span>
- <span data-ttu-id="86dd5-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-586">fabrikam</span></span>
- <span data-ttu-id="86dd5-587">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-587">northwind</span></span>
- <span data-ttu-id="86dd5-588">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-588">sandbox</span></span>
- <span data-ttu-id="86dd5-589">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-589">onebox</span></span>
- <span data-ttu-id="86dd5-590">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-590">localhost</span></span>
- <span data-ttu-id="86dd5-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-591">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-592">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-593">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-593">com</span></span>
- <span data-ttu-id="86dd5-594">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-595">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="86dd5-596">Azure 意指快取的連接字串</span><span class="sxs-lookup"><span data-stu-id="86dd5-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-597">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-597">Format</span></span>

<span data-ttu-id="86dd5-598">將字串 「 redis.cache.windows。</span><span class="sxs-lookup"><span data-stu-id="86dd5-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-599">net"後面加上字元和下方，模式中所述的字串包含字串 「 密碼 」 或 「 pwd 」。</span><span class="sxs-lookup"><span data-stu-id="86dd5-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-600">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-600">Pattern</span></span>

- <span data-ttu-id="86dd5-601">將字串 「 redis.cache.windows。</span><span class="sxs-lookup"><span data-stu-id="86dd5-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-602">net 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-602">net"</span></span>
- <span data-ttu-id="86dd5-603">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-604">字串 「 密碼 」 或者 「 pwd 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="86dd5-605">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-606">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-606">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-607">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-608">43 較低或大寫字母、 數字的字元的任何組合反斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="86dd5-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="86dd5-609">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-610">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-610">Checksum</span></span>

<span data-ttu-id="86dd5-611">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-612">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-612">Definition</span></span>

<span data-ttu-id="86dd5-613">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-614">規則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="86dd5-615">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-618">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-619">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-619">contoso</span></span>
- <span data-ttu-id="86dd5-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-620">fabrikam</span></span>
- <span data-ttu-id="86dd5-621">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-621">northwind</span></span>
- <span data-ttu-id="86dd5-622">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-622">sandbox</span></span>
- <span data-ttu-id="86dd5-623">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-623">onebox</span></span>
- <span data-ttu-id="86dd5-624">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-624">localhost</span></span>
- <span data-ttu-id="86dd5-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-625">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-626">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-627">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-627">com</span></span>
- <span data-ttu-id="86dd5-628">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-629">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="86dd5-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="86dd5-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-631">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-631">Format</span></span>

<span data-ttu-id="86dd5-632">將字串 「 簽章 」 後面加上字元和下列模式中所述的字串。</span><span class="sxs-lookup"><span data-stu-id="86dd5-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-633">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-633">Pattern</span></span>

- <span data-ttu-id="86dd5-634">將字串 「 簽章 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-634">The string "sig"</span></span>
- <span data-ttu-id="86dd5-635">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-636">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-636">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-637">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-638">較低或小寫字母、 數字或百分比符號 （%） 的 43-53 字元之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="86dd5-639">將字串 「 %3d 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-639">The string "%3d"</span></span>
- <span data-ttu-id="86dd5-640">不是較低的大寫字母、 數字或百分比符號 （%） 的任何字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-641">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-641">Checksum</span></span>

<span data-ttu-id="86dd5-642">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-643">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-643">Definition</span></span>

<span data-ttu-id="86dd5-644">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-645">規則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="86dd5-646">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="86dd5-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-647">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-647">Format</span></span>

<span data-ttu-id="86dd5-648">將字串 「 端點 」 後面加上字元和下方，模式中所述的字串包含字串 「 servicebus.windows。</span><span class="sxs-lookup"><span data-stu-id="86dd5-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-649">net 」 和 「 SharedAccesKey 」。</span><span class="sxs-lookup"><span data-stu-id="86dd5-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-650">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-650">Pattern</span></span>

- <span data-ttu-id="86dd5-651">將字串 「 端點 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-651">The string "EndPoint"</span></span>
- <span data-ttu-id="86dd5-652">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-653">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-653">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-654">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-655">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-656">將字串 「 servicebus.windows。</span><span class="sxs-lookup"><span data-stu-id="86dd5-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-657">net 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-657">net"</span></span>
- <span data-ttu-id="86dd5-658">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-659">將字串 「 SharedAccessKey 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="86dd5-660">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-661">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-661">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-662">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-663">43 較低或大寫字母、 數字的字元的任何組合反斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="86dd5-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="86dd5-664">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-665">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-665">Checksum</span></span>

<span data-ttu-id="86dd5-666">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-667">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-667">Definition</span></span>

<span data-ttu-id="86dd5-668">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-669">規則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="86dd5-670">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-671">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-673">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-674">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-674">contoso</span></span>
- <span data-ttu-id="86dd5-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-675">fabrikam</span></span>
- <span data-ttu-id="86dd5-676">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-676">northwind</span></span>
- <span data-ttu-id="86dd5-677">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-677">sandbox</span></span>
- <span data-ttu-id="86dd5-678">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-678">onebox</span></span>
- <span data-ttu-id="86dd5-679">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-679">localhost</span></span>
- <span data-ttu-id="86dd5-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-680">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-681">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-682">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-682">com</span></span>
- <span data-ttu-id="86dd5-683">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-684">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="86dd5-685">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="86dd5-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-686">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-686">Format</span></span>

<span data-ttu-id="86dd5-687">將字串 「 DefaultEndpointsProtocol"後面加上字元和下方，模式中所述的字串包含字串 「 AccountKey 」 中。</span><span class="sxs-lookup"><span data-stu-id="86dd5-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-688">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-688">Pattern</span></span>

- <span data-ttu-id="86dd5-689">將字串 「 DefaultEndpointsProtocol 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="86dd5-690">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-691">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-691">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-692">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-693">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-694">將字串 「 AccountKey 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-694">The string "AccountKey"</span></span>
- <span data-ttu-id="86dd5-695">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-696">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-696">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-697">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="86dd5-698">較低或大寫字母、 數字，86 個字元的任何組合反斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="86dd5-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="86dd5-699">兩個等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-700">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-700">Checksum</span></span>

<span data-ttu-id="86dd5-701">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-702">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-702">Definition</span></span>

<span data-ttu-id="86dd5-703">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-704">規則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-705">規則運算式 CEP_AzureEmulatorStorageAccountFilter**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-706">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-707">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="86dd5-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="86dd5-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="86dd5-709">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="86dd5-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-712">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-713">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-713">contoso</span></span>
- <span data-ttu-id="86dd5-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-714">fabrikam</span></span>
- <span data-ttu-id="86dd5-715">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-715">northwind</span></span>
- <span data-ttu-id="86dd5-716">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-716">sandbox</span></span>
- <span data-ttu-id="86dd5-717">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-717">onebox</span></span>
- <span data-ttu-id="86dd5-718">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-718">localhost</span></span>
- <span data-ttu-id="86dd5-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-719">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-720">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-721">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-721">com</span></span>
- <span data-ttu-id="86dd5-722">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-723">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="86dd5-724">Azure 儲存體帳戶金鑰 （一般）</span><span class="sxs-lookup"><span data-stu-id="86dd5-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-725">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-725">Format</span></span>

<span data-ttu-id="86dd5-726">或的任何組合 86 較低的大寫字母、 數字，正斜線 （/），加上加號 （+），前面或後面跟著字元下列模式中所述。</span><span class="sxs-lookup"><span data-stu-id="86dd5-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-727">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-727">Pattern</span></span>

- <span data-ttu-id="86dd5-728">0-1 的大於符號 (>)、 單引號 （'）、 等號 （=）、 引號 （"） 或數字符號 （#）</span><span class="sxs-lookup"><span data-stu-id="86dd5-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="86dd5-729">較低層或大寫 86 個字元的任何組合字母、 數字，正斜線 （/），或加上加號 （+）</span><span class="sxs-lookup"><span data-stu-id="86dd5-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="86dd5-730">兩個等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="86dd5-731">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-731">Checksum</span></span>

<span data-ttu-id="86dd5-732">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-733">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-733">Definition</span></span>

<span data-ttu-id="86dd5-734">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-735">規則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="86dd5-736">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-737">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-737">Format</span></span>

<span data-ttu-id="86dd5-738">11 位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="86dd5-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-739">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-739">Pattern</span></span>

<span data-ttu-id="86dd5-740">11 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="86dd5-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="86dd5-741">六位數和兩個句點 yy： 通話的格式。公釐。DD 的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="86dd5-742">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-742">A hyphen</span></span> 
- <span data-ttu-id="86dd5-743">三個連續數字 （奇數男生，偶數女生）</span><span class="sxs-lookup"><span data-stu-id="86dd5-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="86dd5-744">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-744">A period</span></span> 
- <span data-ttu-id="86dd5-745">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-746">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-746">Checksum</span></span>

<span data-ttu-id="86dd5-747">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-748">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-748">Definition</span></span>

<span data-ttu-id="86dd5-749">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-750">函數 Func_belgium_national_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-751">找不到來自 Keyword_belgium_national_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="86dd5-752">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-753">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="86dd5-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="86dd5-755">身分識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-755">Identity</span></span>
- <span data-ttu-id="86dd5-756">註冊</span><span class="sxs-lookup"><span data-stu-id="86dd5-756">Registration</span></span>
- <span data-ttu-id="86dd5-757">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-757">Identification</span></span> 
- <span data-ttu-id="86dd5-758">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-758">ID</span></span> 
- <span data-ttu-id="86dd5-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-759">Identiteitskaart</span></span>
- <span data-ttu-id="86dd5-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-760">Registratie nummer</span></span> 
- <span data-ttu-id="86dd5-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-761">Identificatie nummer</span></span> 
- <span data-ttu-id="86dd5-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="86dd5-762">Identiteit</span></span>
- <span data-ttu-id="86dd5-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="86dd5-763">Registratie</span></span>
- <span data-ttu-id="86dd5-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="86dd5-764">Identificatie</span></span> 
- <span data-ttu-id="86dd5-765">相關 d'identité</span><span class="sxs-lookup"><span data-stu-id="86dd5-765">Carte d’identité</span></span> 
- <span data-ttu-id="86dd5-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="86dd5-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="86dd5-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="86dd5-767">numéro d'identification</span></span>
- <span data-ttu-id="86dd5-768">identité</span><span class="sxs-lookup"><span data-stu-id="86dd5-768">identité</span></span> 
- <span data-ttu-id="86dd5-769">碑文</span><span class="sxs-lookup"><span data-stu-id="86dd5-769">inscription</span></span> 
- <span data-ttu-id="86dd5-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="86dd5-770">Identifikation</span></span>
- <span data-ttu-id="86dd5-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="86dd5-771">Identifizierung</span></span>
- <span data-ttu-id="86dd5-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-772">Identifikationsnummer</span></span>
- <span data-ttu-id="86dd5-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="86dd5-773">Personalausweis</span></span>
- <span data-ttu-id="86dd5-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="86dd5-774">Registrierung</span></span>
- <span data-ttu-id="86dd5-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="86dd5-776">巴西 Cpf 碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-777">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-777">Format</span></span>

<span data-ttu-id="86dd5-778">11 位數包含檢查碼且可格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="86dd5-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-779">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-779">Pattern</span></span>

<span data-ttu-id="86dd5-780">格式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-780">Formatted:</span></span>
- <span data-ttu-id="86dd5-781">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-781">Three digits</span></span> 
- <span data-ttu-id="86dd5-782">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-782">A period</span></span> 
- <span data-ttu-id="86dd5-783">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-783">Three digits</span></span> 
- <span data-ttu-id="86dd5-784">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-784">A period</span></span> 
- <span data-ttu-id="86dd5-785">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-785">Three digits</span></span> 
- <span data-ttu-id="86dd5-786">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-786">A hyphen</span></span> 
- <span data-ttu-id="86dd5-787">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-787">Two digits which are check digits</span></span>

<span data-ttu-id="86dd5-788">格式化：</span><span class="sxs-lookup"><span data-stu-id="86dd5-788">Unformatted:</span></span>
- <span data-ttu-id="86dd5-789">11 位數，最後二位數所在位置，請檢查位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-790">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-790">Checksum</span></span>

<span data-ttu-id="86dd5-791">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-792">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-792">Definition</span></span>

<span data-ttu-id="86dd5-793">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-794">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-795">找不到來自 Keyword_brazil_cpf 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="86dd5-796">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-796">The checksum passes.</span></span>

<span data-ttu-id="86dd5-797">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-798">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-799">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-800">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="86dd5-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="86dd5-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="86dd5-802">CPF</span><span class="sxs-lookup"><span data-stu-id="86dd5-802">CPF</span></span>
- <span data-ttu-id="86dd5-803">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-803">Identification</span></span>
- <span data-ttu-id="86dd5-804">註冊</span><span class="sxs-lookup"><span data-stu-id="86dd5-804">Registration</span></span>
- <span data-ttu-id="86dd5-805">收益</span><span class="sxs-lookup"><span data-stu-id="86dd5-805">Revenue</span></span>
- <span data-ttu-id="86dd5-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="86dd5-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="86dd5-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="86dd5-807">Imposto</span></span> 
- <span data-ttu-id="86dd5-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="86dd5-808">Identificação</span></span> 
- <span data-ttu-id="86dd5-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="86dd5-809">Inscrição</span></span> 
- <span data-ttu-id="86dd5-810">Receita</span><span class="sxs-lookup"><span data-stu-id="86dd5-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="86dd5-811">巴西法律實體號碼 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="86dd5-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-812">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-812">Format</span></span>

<span data-ttu-id="86dd5-813">14 位數包含登記碼、 分支碼和檢查碼加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="86dd5-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-814">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-814">Pattern</span></span>
<span data-ttu-id="86dd5-815">14 位數，加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="86dd5-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="86dd5-816">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-816">Two digits</span></span> 
- <span data-ttu-id="86dd5-817">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-817">A period</span></span> 
- <span data-ttu-id="86dd5-818">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-818">Three digits</span></span> 
- <span data-ttu-id="86dd5-819">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-819">A period</span></span> 
- <span data-ttu-id="86dd5-820">三位數 （此前 8 位數為登記碼）</span><span class="sxs-lookup"><span data-stu-id="86dd5-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="86dd5-821">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="86dd5-821">A forward slash</span></span> 
- <span data-ttu-id="86dd5-822">四位數分支碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-822">Four-digit branch number</span></span> 
- <span data-ttu-id="86dd5-823">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-823">A hyphen</span></span> 
- <span data-ttu-id="86dd5-824">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-825">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-825">Checksum</span></span>

<span data-ttu-id="86dd5-826">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-827">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-827">Definition</span></span>

<span data-ttu-id="86dd5-828">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-829">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-830">找不到來自 Keyword_brazil_cnpj 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="86dd5-831">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-831">The checksum passes.</span></span>

<span data-ttu-id="86dd5-832">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-833">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-834">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-835">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="86dd5-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="86dd5-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="86dd5-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="86dd5-837">CNPJ</span></span> 
- <span data-ttu-id="86dd5-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="86dd5-838">CNPJ/MF</span></span> 
- <span data-ttu-id="86dd5-839">CNPJ MF</span><span class="sxs-lookup"><span data-stu-id="86dd5-839">CNPJ-MF</span></span> 
- <span data-ttu-id="86dd5-840">法律實體的登錄，國際電話</span><span class="sxs-lookup"><span data-stu-id="86dd5-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="86dd5-841">納稅人登錄</span><span class="sxs-lookup"><span data-stu-id="86dd5-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="86dd5-842">法律實體</span><span class="sxs-lookup"><span data-stu-id="86dd5-842">Legal entity</span></span> 
- <span data-ttu-id="86dd5-843">法律實體</span><span class="sxs-lookup"><span data-stu-id="86dd5-843">Legal entities</span></span> 
- <span data-ttu-id="86dd5-844">註冊狀態</span><span class="sxs-lookup"><span data-stu-id="86dd5-844">Registration Status</span></span> 
- <span data-ttu-id="86dd5-845">商務版</span><span class="sxs-lookup"><span data-stu-id="86dd5-845">Business</span></span> 
- <span data-ttu-id="86dd5-846">Company</span><span class="sxs-lookup"><span data-stu-id="86dd5-846">Company</span></span>
- <span data-ttu-id="86dd5-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="86dd5-847">CNPJ</span></span> 
- <span data-ttu-id="86dd5-848">Cadastro Nacional 斯坦 Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="86dd5-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="86dd5-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="86dd5-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="86dd5-850">CGC</span><span class="sxs-lookup"><span data-stu-id="86dd5-850">CGC</span></span> 
- <span data-ttu-id="86dd5-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="86dd5-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="86dd5-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="86dd5-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="86dd5-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="86dd5-853">Situação cadastral</span></span> 
- <span data-ttu-id="86dd5-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="86dd5-854">Inscrição</span></span> 
- <span data-ttu-id="86dd5-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="86dd5-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="86dd5-856">巴西國民身分證 (RG)</span><span class="sxs-lookup"><span data-stu-id="86dd5-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-857">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-857">Format</span></span>

<span data-ttu-id="86dd5-858">Registro Geral （舊格式）： 九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="86dd5-859">Registro de Identidade (RIC) （新格式）： 11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-860">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-860">Pattern</span></span>

<span data-ttu-id="86dd5-861">Registro Geral （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="86dd5-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="86dd5-862">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-862">Two digits</span></span> 
- <span data-ttu-id="86dd5-863">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-863">A period</span></span> 
- <span data-ttu-id="86dd5-864">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-864">Three digits</span></span> 
- <span data-ttu-id="86dd5-865">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-865">A period</span></span> 
- <span data-ttu-id="86dd5-866">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-866">Three digits</span></span> 
- <span data-ttu-id="86dd5-867">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-867">A hyphen</span></span> 
- <span data-ttu-id="86dd5-868">一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-868">One digit which is a check digit</span></span>

<span data-ttu-id="86dd5-869">Registro de Identidade (RIC) （新格式）：</span><span class="sxs-lookup"><span data-stu-id="86dd5-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="86dd5-870">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-870">10 digits</span></span> 
- <span data-ttu-id="86dd5-871">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-871">A hyphen</span></span> 
- <span data-ttu-id="86dd5-872">一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-873">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-873">Checksum</span></span>

<span data-ttu-id="86dd5-874">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-875">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-875">Definition</span></span>

<span data-ttu-id="86dd5-876">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-877">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-878">找不到來自 Keyword_brazil_rg 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="86dd5-879">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-879">The checksum passes.</span></span>

<span data-ttu-id="86dd5-880">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-881">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-882">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-883">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="86dd5-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="86dd5-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="86dd5-885">Cédula de identidade 身分證證 número de rregistro registro de Iidentidade registro geral RG （此關鍵字是區分大小寫） RIC （此關鍵字是區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="86dd5-886">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-887">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-887">Format</span></span>

<span data-ttu-id="86dd5-888">7 或 12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-889">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-889">Pattern</span></span>

<span data-ttu-id="86dd5-890">加拿大銀行帳戶號碼是 7 或 12 位數。</span><span class="sxs-lookup"><span data-stu-id="86dd5-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="86dd5-891">加拿大銀行帳戶交換號碼是：</span><span class="sxs-lookup"><span data-stu-id="86dd5-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="86dd5-892">五位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-892">Five digits</span></span> 
- <span data-ttu-id="86dd5-893">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-893">A hyphen</span></span> 
- <span data-ttu-id="86dd5-894">三位數或</span><span class="sxs-lookup"><span data-stu-id="86dd5-894">Three digits OR</span></span>
- <span data-ttu-id="86dd5-895">零"0"</span><span class="sxs-lookup"><span data-stu-id="86dd5-895">A zero "0"</span></span> 
- <span data-ttu-id="86dd5-896">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-897">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-897">Checksum</span></span>

<span data-ttu-id="86dd5-898">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-899">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-899">Definition</span></span>

<span data-ttu-id="86dd5-900">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-901">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-902">找不到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="86dd5-903">規則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="86dd5-904">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-905">規則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-906">找不到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-907">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="86dd5-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="86dd5-909">加拿大節省債券</span><span class="sxs-lookup"><span data-stu-id="86dd5-909">canada savings bonds</span></span>
- <span data-ttu-id="86dd5-910">加拿大收益機構</span><span class="sxs-lookup"><span data-stu-id="86dd5-910">canada revenue agency</span></span>
- <span data-ttu-id="86dd5-911">加拿大金融機構</span><span class="sxs-lookup"><span data-stu-id="86dd5-911">canadian financial institution</span></span>
- <span data-ttu-id="86dd5-912">直接儲放表單</span><span class="sxs-lookup"><span data-stu-id="86dd5-912">direct deposit form</span></span>
- <span data-ttu-id="86dd5-913">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="86dd5-913">canadian citizen</span></span>
- <span data-ttu-id="86dd5-914">法律代表</span><span class="sxs-lookup"><span data-stu-id="86dd5-914">legal representative</span></span>
- <span data-ttu-id="86dd5-915">公證人類似公開</span><span class="sxs-lookup"><span data-stu-id="86dd5-915">notary public</span></span>
- <span data-ttu-id="86dd5-916">oaths 的專員</span><span class="sxs-lookup"><span data-stu-id="86dd5-916">commissioner for oaths</span></span>
- <span data-ttu-id="86dd5-917">子系照護權益</span><span class="sxs-lookup"><span data-stu-id="86dd5-917">child care benefit</span></span>
- <span data-ttu-id="86dd5-918">萬用子照護</span><span class="sxs-lookup"><span data-stu-id="86dd5-918">universal child care</span></span>
- <span data-ttu-id="86dd5-919">加拿大子稅務權益</span><span class="sxs-lookup"><span data-stu-id="86dd5-919">canada child tax benefit</span></span>
- <span data-ttu-id="86dd5-920">收入稅務權益</span><span class="sxs-lookup"><span data-stu-id="86dd5-920">income tax benefit</span></span>
- <span data-ttu-id="86dd5-921">協調的銷售稅務</span><span class="sxs-lookup"><span data-stu-id="86dd5-921">harmonized sales tax</span></span>
- <span data-ttu-id="86dd5-922">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-922">social insurance number</span></span>
- <span data-ttu-id="86dd5-923">收入稅務退款</span><span class="sxs-lookup"><span data-stu-id="86dd5-923">income tax refund</span></span>
- <span data-ttu-id="86dd5-924">子系稅務權益</span><span class="sxs-lookup"><span data-stu-id="86dd5-924">child tax benefit</span></span>
- <span data-ttu-id="86dd5-925">就付款</span><span class="sxs-lookup"><span data-stu-id="86dd5-925">territorial payments</span></span>
- <span data-ttu-id="86dd5-926">機構數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-926">institution number</span></span>
- <span data-ttu-id="86dd5-927">儲放要求</span><span class="sxs-lookup"><span data-stu-id="86dd5-927">deposit request</span></span>
- <span data-ttu-id="86dd5-928">銀行業資訊</span><span class="sxs-lookup"><span data-stu-id="86dd5-928">banking information</span></span>
- <span data-ttu-id="86dd5-929">直接儲放</span><span class="sxs-lookup"><span data-stu-id="86dd5-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="86dd5-930">加拿大駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-931">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-931">Format</span></span>

<span data-ttu-id="86dd5-932">省分而異</span><span class="sxs-lookup"><span data-stu-id="86dd5-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-933">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-933">Pattern</span></span>

<span data-ttu-id="86dd5-934">不同模式 Alberta、 不列顛哥倫比亞、 Manitoba、 New Brunswick、 Newfoundland/Labrador、 Nova Scotia、 安大略省、 Prince Edward 島、 Quebec 和薩克其萬</span><span class="sxs-lookup"><span data-stu-id="86dd5-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-935">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-935">Checksum</span></span>

<span data-ttu-id="86dd5-936">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-937">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-937">Definition</span></span>

<span data-ttu-id="86dd5-938">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-939">函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-940">找到來自於 Keyword_ [province_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="86dd5-941">找不到來自 Keyword_canada_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="86dd5-943">於 Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="86dd5-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="86dd5-944">省分縮寫，例如 AB</span><span class="sxs-lookup"><span data-stu-id="86dd5-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="86dd5-945">省分名稱，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="86dd5-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="86dd5-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="86dd5-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="86dd5-947">DL</span><span class="sxs-lookup"><span data-stu-id="86dd5-947">DL</span></span>
- <span data-ttu-id="86dd5-948">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="86dd5-948">DLS</span></span>
- <span data-ttu-id="86dd5-949">CDL</span><span class="sxs-lookup"><span data-stu-id="86dd5-949">CDL</span></span>
- <span data-ttu-id="86dd5-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="86dd5-950">CDLS</span></span>
- <span data-ttu-id="86dd5-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-951">DriverLic</span></span>
- <span data-ttu-id="86dd5-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-952">DriverLics</span></span>
- <span data-ttu-id="86dd5-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="86dd5-953">DriverLicense</span></span>
- <span data-ttu-id="86dd5-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-954">DriverLicenses</span></span>
- <span data-ttu-id="86dd5-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="86dd5-955">DriverLicence</span></span>
- <span data-ttu-id="86dd5-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="86dd5-956">DriverLicences</span></span>
- <span data-ttu-id="86dd5-957">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-957">Driver Lic</span></span>
- <span data-ttu-id="86dd5-958">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-958">Driver Lics</span></span>
- <span data-ttu-id="86dd5-959">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-959">Driver License</span></span>
- <span data-ttu-id="86dd5-960">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-960">Driver Licenses</span></span>
- <span data-ttu-id="86dd5-961">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-961">Driver Licence</span></span>
- <span data-ttu-id="86dd5-962">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-962">Driver Licences</span></span>
- <span data-ttu-id="86dd5-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-963">DriversLic</span></span>
- <span data-ttu-id="86dd5-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-964">DriversLics</span></span>
- <span data-ttu-id="86dd5-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="86dd5-965">DriversLicence</span></span>
- <span data-ttu-id="86dd5-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="86dd5-966">DriversLicences</span></span>
- <span data-ttu-id="86dd5-967">執照</span><span class="sxs-lookup"><span data-stu-id="86dd5-967">DriversLicense</span></span>
- <span data-ttu-id="86dd5-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-968">DriversLicenses</span></span>
- <span data-ttu-id="86dd5-969">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-969">Drivers Lic</span></span>
- <span data-ttu-id="86dd5-970">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-970">Drivers Lics</span></span>
- <span data-ttu-id="86dd5-971">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-971">Drivers License</span></span>
- <span data-ttu-id="86dd5-972">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-972">Drivers Licenses</span></span>
- <span data-ttu-id="86dd5-973">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-973">Drivers Licence</span></span>
- <span data-ttu-id="86dd5-974">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-974">Drivers Licences</span></span>
- <span data-ttu-id="86dd5-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-975">Driver'Lic</span></span>
- <span data-ttu-id="86dd5-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-976">Driver'Lics</span></span>
- <span data-ttu-id="86dd5-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="86dd5-977">Driver'License</span></span>
- <span data-ttu-id="86dd5-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-978">Driver'Licenses</span></span>
- <span data-ttu-id="86dd5-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="86dd5-979">Driver'Licence</span></span>
- <span data-ttu-id="86dd5-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="86dd5-980">Driver'Licences</span></span>
- <span data-ttu-id="86dd5-981">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-981">Driver' Lic</span></span>
- <span data-ttu-id="86dd5-982">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-982">Driver' Lics</span></span>
- <span data-ttu-id="86dd5-983">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-983">Driver' License</span></span>
- <span data-ttu-id="86dd5-984">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-984">Driver' Licenses</span></span>
- <span data-ttu-id="86dd5-985">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-985">Driver' Licence</span></span>
- <span data-ttu-id="86dd5-986">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-986">Driver' Licences</span></span>
- <span data-ttu-id="86dd5-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-987">Driver'sLic</span></span>
- <span data-ttu-id="86dd5-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-988">Driver'sLics</span></span>
- <span data-ttu-id="86dd5-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="86dd5-989">Driver'sLicense</span></span>
- <span data-ttu-id="86dd5-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-990">Driver'sLicenses</span></span>
- <span data-ttu-id="86dd5-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="86dd5-991">Driver'sLicence</span></span>
- <span data-ttu-id="86dd5-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="86dd5-992">Driver'sLicences</span></span>
- <span data-ttu-id="86dd5-993">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-993">Driver's Lic</span></span>
- <span data-ttu-id="86dd5-994">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-994">Driver's Lics</span></span>
- <span data-ttu-id="86dd5-995">駕照</span><span class="sxs-lookup"><span data-stu-id="86dd5-995">Driver's License</span></span>
- <span data-ttu-id="86dd5-996">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-996">Driver's Licenses</span></span>
- <span data-ttu-id="86dd5-997">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-997">Driver's Licence</span></span>
- <span data-ttu-id="86dd5-998">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-998">Driver's Licences</span></span>
- <span data-ttu-id="86dd5-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="86dd5-999">Permis de Conduire</span></span>
- <span data-ttu-id="86dd5-1000">id</span><span class="sxs-lookup"><span data-stu-id="86dd5-1000">id</span></span>
- <span data-ttu-id="86dd5-1001">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1001">ids</span></span>
- <span data-ttu-id="86dd5-1002">idcard 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-1002">idcard number</span></span>
- <span data-ttu-id="86dd5-1003">idcard 數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1003">idcard numbers</span></span>
- <span data-ttu-id="86dd5-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1004">idcard #</span></span>
- <span data-ttu-id="86dd5-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="86dd5-1005">idcard #s</span></span>
- <span data-ttu-id="86dd5-1006">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1006">idcard card</span></span>
- <span data-ttu-id="86dd5-1007">idcard 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1007">idcard cards</span></span>
- <span data-ttu-id="86dd5-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1008">idcard</span></span>
- <span data-ttu-id="86dd5-1009">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1009">identification number</span></span>
- <span data-ttu-id="86dd5-1010">識別數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1010">identification numbers</span></span>
- <span data-ttu-id="86dd5-1011">識別 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1011">identification #</span></span>
- <span data-ttu-id="86dd5-1012">識別 #s</span><span class="sxs-lookup"><span data-stu-id="86dd5-1012">identification #s</span></span>
- <span data-ttu-id="86dd5-1013">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1013">identification card</span></span>
- <span data-ttu-id="86dd5-1014">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1014">identification cards</span></span>
- <span data-ttu-id="86dd5-1015">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-1015">identification</span></span> 
- <span data-ttu-id="86dd5-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1016">DL#</span></span>
- <span data-ttu-id="86dd5-1017">DL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1017">DLS#</span></span> 
- <span data-ttu-id="86dd5-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1018">CDL#</span></span> 
- <span data-ttu-id="86dd5-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1019">CDLS#</span></span> 
- <span data-ttu-id="86dd5-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1020">DriverLic#</span></span> 
- <span data-ttu-id="86dd5-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1021">DriverLics#</span></span> 
- <span data-ttu-id="86dd5-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1022">DriverLicense#</span></span> 
- <span data-ttu-id="86dd5-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="86dd5-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1024">DriverLicence#</span></span> 
- <span data-ttu-id="86dd5-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1025">DriverLicences#</span></span> 
- <span data-ttu-id="86dd5-1026">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1026">Driver Lic#</span></span>
- <span data-ttu-id="86dd5-1027">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1027">Driver Lics#</span></span> 
- <span data-ttu-id="86dd5-1028">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1028">Driver License#</span></span> 
- <span data-ttu-id="86dd5-1029">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="86dd5-1030">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1030">Driver License#</span></span> 
- <span data-ttu-id="86dd5-1031">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1031">Driver Licences#</span></span> 
- <span data-ttu-id="86dd5-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1032">DriversLic#</span></span> 
- <span data-ttu-id="86dd5-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1033">DriversLics#</span></span> 
- <span data-ttu-id="86dd5-1034">執照 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1034">DriversLicense#</span></span> 
- <span data-ttu-id="86dd5-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="86dd5-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1036">DriversLicence#</span></span> 
- <span data-ttu-id="86dd5-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1037">DriversLicences#</span></span> 
- <span data-ttu-id="86dd5-1038">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="86dd5-1039">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="86dd5-1040">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1040">Drivers License#</span></span> 
- <span data-ttu-id="86dd5-1041">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="86dd5-1042">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="86dd5-1043">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="86dd5-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="86dd5-1045">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="86dd5-1046">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1046">Driver'License#</span></span> 
- <span data-ttu-id="86dd5-1047">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="86dd5-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="86dd5-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="86dd5-1050">驅動程式 ' Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="86dd5-1051">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="86dd5-1052">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1052">Driver' License#</span></span> 
- <span data-ttu-id="86dd5-1053">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="86dd5-1054">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="86dd5-1055">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="86dd5-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="86dd5-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="86dd5-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="86dd5-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="86dd5-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="86dd5-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="86dd5-1062">駕 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="86dd5-1063">駕 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="86dd5-1064">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1064">Driver's License#</span></span> 
- <span data-ttu-id="86dd5-1065">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="86dd5-1066">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="86dd5-1067">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="86dd5-1068">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="86dd5-1069">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1069">id#</span></span> 
- <span data-ttu-id="86dd5-1070">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1070">ids#</span></span> 
- <span data-ttu-id="86dd5-1071">idcard 卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1071">idcard card#</span></span> 
- <span data-ttu-id="86dd5-1072">idcard 卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1072">idcard cards#</span></span> 
- <span data-ttu-id="86dd5-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1073">idcard#</span></span> 
- <span data-ttu-id="86dd5-1074">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1074">identification card#</span></span> 
- <span data-ttu-id="86dd5-1075">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1075">identification cards#</span></span> 
- <span data-ttu-id="86dd5-1076">識別 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="86dd5-1077">加拿大健保號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1078">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1078">Format</span></span>

<span data-ttu-id="86dd5-1079">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1080">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1080">Pattern</span></span>

<span data-ttu-id="86dd5-1081">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1082">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1082">Checksum</span></span>

<span data-ttu-id="86dd5-1083">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1084">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1084">Definition</span></span>

<span data-ttu-id="86dd5-1085">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1086">規則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1087">找不到來自 Keyword_canada_health_service_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1088">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="86dd5-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="86dd5-1090">個人健康數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-1090">personal health number</span></span>
- <span data-ttu-id="86dd5-1091">病患資訊</span><span class="sxs-lookup"><span data-stu-id="86dd5-1091">patient information</span></span>
- <span data-ttu-id="86dd5-1092">健康服務</span><span class="sxs-lookup"><span data-stu-id="86dd5-1092">health services</span></span>
- <span data-ttu-id="86dd5-1093">speciality 服務</span><span class="sxs-lookup"><span data-stu-id="86dd5-1093">speciality services</span></span>
- <span data-ttu-id="86dd5-1094">汽車意外</span><span class="sxs-lookup"><span data-stu-id="86dd5-1094">automobile accident</span></span>
- <span data-ttu-id="86dd5-1095">病患醫院</span><span class="sxs-lookup"><span data-stu-id="86dd5-1095">patient hospital</span></span>
- <span data-ttu-id="86dd5-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="86dd5-1096">psychiatrist</span></span>
- <span data-ttu-id="86dd5-1097">工作者補償</span><span class="sxs-lookup"><span data-stu-id="86dd5-1097">workers compensation</span></span>
- <span data-ttu-id="86dd5-1098">disability</span><span class="sxs-lookup"><span data-stu-id="86dd5-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="86dd5-1099">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1100">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1100">Format</span></span>

<span data-ttu-id="86dd5-1101">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1102">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1102">Pattern</span></span>

<span data-ttu-id="86dd5-1103">兩個大寫字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1104">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1104">Checksum</span></span>

<span data-ttu-id="86dd5-1105">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1106">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1106">Definition</span></span>

<span data-ttu-id="86dd5-1107">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1108">規則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1109">找到來自於 Keyword_canada_passport_number 或 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1110">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="86dd5-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="86dd5-1112">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="86dd5-1112">canadian citizenship</span></span>
- <span data-ttu-id="86dd5-1113">加拿大護照</span><span class="sxs-lookup"><span data-stu-id="86dd5-1113">canadian passport</span></span>
- <span data-ttu-id="86dd5-1114">passport 應用程式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1114">passport application</span></span>
- <span data-ttu-id="86dd5-1115">passport 相片</span><span class="sxs-lookup"><span data-stu-id="86dd5-1115">passport photos</span></span>
- <span data-ttu-id="86dd5-1116">認證轉譯器</span><span class="sxs-lookup"><span data-stu-id="86dd5-1116">certified translator</span></span>
- <span data-ttu-id="86dd5-1117">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="86dd5-1117">canadian citizens</span></span>
- <span data-ttu-id="86dd5-1118">處理時間</span><span class="sxs-lookup"><span data-stu-id="86dd5-1118">processing times</span></span>
- <span data-ttu-id="86dd5-1119">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="86dd5-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-1120">Keyword_passport</span></span>

- <span data-ttu-id="86dd5-1121">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1121">Passport Number</span></span>
- <span data-ttu-id="86dd5-1122">Passport 否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1122">Passport No</span></span>
- <span data-ttu-id="86dd5-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1123">Passport #</span></span>
- <span data-ttu-id="86dd5-1124">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1124">Passport#</span></span>
- <span data-ttu-id="86dd5-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="86dd5-1125">PassportID</span></span>
- <span data-ttu-id="86dd5-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="86dd5-1126">Passportno</span></span>
- <span data-ttu-id="86dd5-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1127">passportnumber</span></span>
- <span data-ttu-id="86dd5-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="86dd5-1128">パスポート</span></span>
- <span data-ttu-id="86dd5-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-1129">パスポート番号</span></span>
- <span data-ttu-id="86dd5-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1130">パスポートのNum</span></span>
- <span data-ttu-id="86dd5-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1131">パスポート＃</span></span>
- <span data-ttu-id="86dd5-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="86dd5-1132">Numéro de passeport</span></span>
- <span data-ttu-id="86dd5-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="86dd5-1133">Passeport n °</span></span>
- <span data-ttu-id="86dd5-1134">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="86dd5-1134">Passeport Non</span></span>
- <span data-ttu-id="86dd5-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1135">Passeport #</span></span>
- <span data-ttu-id="86dd5-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1136">Passeport#</span></span>
- <span data-ttu-id="86dd5-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="86dd5-1137">PasseportNon</span></span>
- <span data-ttu-id="86dd5-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="86dd5-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="86dd5-1139">加拿大個人健康身分識別號碼 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1140">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1140">Format</span></span>

<span data-ttu-id="86dd5-1141">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1142">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1142">Pattern</span></span>

<span data-ttu-id="86dd5-1143">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1144">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1144">Checksum</span></span>

<span data-ttu-id="86dd5-1145">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1146">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1146">Definition</span></span>

<span data-ttu-id="86dd5-1147">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 規則運算式 Regex_canada_phin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-1148">找到來自於 Keyword_canada_phin 或 keyword_canada_provinces 的關鍵字，至少有兩個關鍵字..</span><span class="sxs-lookup"><span data-stu-id="86dd5-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="86dd5-1150">於 Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="86dd5-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="86dd5-1151">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1151">social insurance number</span></span>
- <span data-ttu-id="86dd5-1152">健康資訊法案</span><span class="sxs-lookup"><span data-stu-id="86dd5-1152">health information act</span></span>
- <span data-ttu-id="86dd5-1153">收入稅務資訊</span><span class="sxs-lookup"><span data-stu-id="86dd5-1153">income tax information</span></span>
- <span data-ttu-id="86dd5-1154">馬健康情況</span><span class="sxs-lookup"><span data-stu-id="86dd5-1154">manitoba health</span></span>
- <span data-ttu-id="86dd5-1155">健康情況註冊</span><span class="sxs-lookup"><span data-stu-id="86dd5-1155">health registration</span></span>
- <span data-ttu-id="86dd5-1156">解決方法購買</span><span class="sxs-lookup"><span data-stu-id="86dd5-1156">prescription purchases</span></span>
- <span data-ttu-id="86dd5-1157">權益合格</span><span class="sxs-lookup"><span data-stu-id="86dd5-1157">benefit eligibility</span></span>
- <span data-ttu-id="86dd5-1158">個人健康情況</span><span class="sxs-lookup"><span data-stu-id="86dd5-1158">personal health</span></span>
- <span data-ttu-id="86dd5-1159">電源的律師</span><span class="sxs-lookup"><span data-stu-id="86dd5-1159">power of attorney</span></span>
- <span data-ttu-id="86dd5-1160">登記號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1160">registration number</span></span>
- <span data-ttu-id="86dd5-1161">個人健康數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-1161">personal health number</span></span>
- <span data-ttu-id="86dd5-1162">從業員推薦</span><span class="sxs-lookup"><span data-stu-id="86dd5-1162">practitioner referral</span></span>
- <span data-ttu-id="86dd5-1163">同等重要專業版</span><span class="sxs-lookup"><span data-stu-id="86dd5-1163">wellness professional</span></span>
- <span data-ttu-id="86dd5-1164">病患推薦</span><span class="sxs-lookup"><span data-stu-id="86dd5-1164">patient referral</span></span>
- <span data-ttu-id="86dd5-1165">健康狀況和同等重要</span><span class="sxs-lookup"><span data-stu-id="86dd5-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="86dd5-1166">Keyword_canada_provinces 的關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="86dd5-1167">努勒維特</span><span class="sxs-lookup"><span data-stu-id="86dd5-1167">Nunavut</span></span>
- <span data-ttu-id="86dd5-1168">魁北克</span><span class="sxs-lookup"><span data-stu-id="86dd5-1168">Quebec</span></span>
- <span data-ttu-id="86dd5-1169">西北地區</span><span class="sxs-lookup"><span data-stu-id="86dd5-1169">Northwest Territories</span></span>
- <span data-ttu-id="86dd5-1170">安大略省</span><span class="sxs-lookup"><span data-stu-id="86dd5-1170">Ontario</span></span>
- <span data-ttu-id="86dd5-1171">不列顛哥倫比亞</span><span class="sxs-lookup"><span data-stu-id="86dd5-1171">British Columbia</span></span>
- <span data-ttu-id="86dd5-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1172">Alberta</span></span>
- <span data-ttu-id="86dd5-1173">薩克其萬</span><span class="sxs-lookup"><span data-stu-id="86dd5-1173">Saskatchewan</span></span>
- <span data-ttu-id="86dd5-1174">馬</span><span class="sxs-lookup"><span data-stu-id="86dd5-1174">Manitoba</span></span>
- <span data-ttu-id="86dd5-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="86dd5-1175">Yukon</span></span>
- <span data-ttu-id="86dd5-1176">紐芬蘭和 Labrador</span><span class="sxs-lookup"><span data-stu-id="86dd5-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="86dd5-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="86dd5-1177">New Brunswick</span></span>
- <span data-ttu-id="86dd5-1178">斯科</span><span class="sxs-lookup"><span data-stu-id="86dd5-1178">Nova Scotia</span></span>
- <span data-ttu-id="86dd5-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="86dd5-1179">Prince Edward Island</span></span>
- <span data-ttu-id="86dd5-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="86dd5-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="86dd5-1181">加拿大社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1182">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1182">Format</span></span>

<span data-ttu-id="86dd5-1183">使用選擇性連字號或空格的九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1184">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1184">Pattern</span></span>

<span data-ttu-id="86dd5-1185">格式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1185">Formatted:</span></span>
- <span data-ttu-id="86dd5-1186">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1186">Three digits</span></span> 
- <span data-ttu-id="86dd5-1187">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-1187">A hyphen or space</span></span> 
- <span data-ttu-id="86dd5-1188">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1188">Three digits</span></span> 
- <span data-ttu-id="86dd5-1189">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-1189">A hyphen or space</span></span> 
- <span data-ttu-id="86dd5-1190">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1190">Three digits</span></span>

<span data-ttu-id="86dd5-1191">未格式化： 九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1192">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1192">Checksum</span></span>

<span data-ttu-id="86dd5-1193">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1194">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1194">Definition</span></span>

<span data-ttu-id="86dd5-1195">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1196">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1197">至少兩個以下的任意組合：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="86dd5-1198">找不到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="86dd5-1199">找不到來自 Keyword_sin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="86dd5-1200">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="86dd5-1201">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1201">The checksum passes.</span></span>

<span data-ttu-id="86dd5-1202">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1203">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1204">找不到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="86dd5-1205">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="86dd5-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="86dd5-1207">Keyword_sin</span></span>

- <span data-ttu-id="86dd5-1208">sin</span><span class="sxs-lookup"><span data-stu-id="86dd5-1208">sin</span></span> 
- <span data-ttu-id="86dd5-1209">社會保險</span><span class="sxs-lookup"><span data-stu-id="86dd5-1209">social insurance</span></span> 
- <span data-ttu-id="86dd5-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="86dd5-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="86dd5-1211">贖罪</span><span class="sxs-lookup"><span data-stu-id="86dd5-1211">sins</span></span> 
- <span data-ttu-id="86dd5-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="86dd5-1212">ssn</span></span> 
- <span data-ttu-id="86dd5-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="86dd5-1213">ssns</span></span> 
- <span data-ttu-id="86dd5-1214">社會安全</span><span class="sxs-lookup"><span data-stu-id="86dd5-1214">social security</span></span> 
- <span data-ttu-id="86dd5-1215">numero d'assurance 社交</span><span class="sxs-lookup"><span data-stu-id="86dd5-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="86dd5-1216">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1216">national identification number</span></span> 
- <span data-ttu-id="86dd5-1217">國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1217">national id</span></span> 
- <span data-ttu-id="86dd5-1218">sin #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1218">sin#</span></span> 
- <span data-ttu-id="86dd5-1219">soc 集</span><span class="sxs-lookup"><span data-stu-id="86dd5-1219">soc ins</span></span> 
- <span data-ttu-id="86dd5-1220">社交集</span><span class="sxs-lookup"><span data-stu-id="86dd5-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="86dd5-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="86dd5-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="86dd5-1222">駕照</span><span class="sxs-lookup"><span data-stu-id="86dd5-1222">driver's license</span></span> 
- <span data-ttu-id="86dd5-1223">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-1223">drivers license</span></span> 
- <span data-ttu-id="86dd5-1224">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-1224">driver's licence</span></span> 
- <span data-ttu-id="86dd5-1225">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-1225">drivers licence</span></span> 
- <span data-ttu-id="86dd5-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="86dd5-1226">DOB</span></span> 
- <span data-ttu-id="86dd5-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1227">Birthdate</span></span> 
- <span data-ttu-id="86dd5-1228">生日</span><span class="sxs-lookup"><span data-stu-id="86dd5-1228">Birthday</span></span> 
- <span data-ttu-id="86dd5-1229">出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="86dd5-1230">智利身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1231">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1231">Format</span></span>

<span data-ttu-id="86dd5-1232">7-8 位數加上分隔符號檢查碼或字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1233">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1233">Pattern</span></span>

<span data-ttu-id="86dd5-1234">7-8 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="86dd5-1235">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1235">1-2 digits</span></span> 
- <span data-ttu-id="86dd5-1236">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-1236">A period</span></span> 
- <span data-ttu-id="86dd5-1237">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1237">Three digits</span></span> 
- <span data-ttu-id="86dd5-1238">句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-1238">A period</span></span> 
- <span data-ttu-id="86dd5-1239">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1239">Three digits</span></span> 
- <span data-ttu-id="86dd5-1240">一條虛線</span><span class="sxs-lookup"><span data-stu-id="86dd5-1240">A dash</span></span> 
- <span data-ttu-id="86dd5-1241">一個數字或字母 （不區分大小寫） 這是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1242">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1242">Checksum</span></span>

<span data-ttu-id="86dd5-1243">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1244">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1244">Definition</span></span>

<span data-ttu-id="86dd5-1245">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1246">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1247">找不到來自 Keyword_chile_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="86dd5-1248">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1248">The checksum passes.</span></span>

<span data-ttu-id="86dd5-1249">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1250">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1251">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="86dd5-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="86dd5-1254">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1254">National Identification Number</span></span> 
- <span data-ttu-id="86dd5-1255">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1255">Identity card</span></span> 
- <span data-ttu-id="86dd5-1256">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1256">ID</span></span> 
- <span data-ttu-id="86dd5-1257">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-1257">Identification</span></span> 
- <span data-ttu-id="86dd5-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="86dd5-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="86dd5-1259">執行</span><span class="sxs-lookup"><span data-stu-id="86dd5-1259">RUN</span></span> 
- <span data-ttu-id="86dd5-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="86dd5-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="86dd5-1261">墨守成規</span><span class="sxs-lookup"><span data-stu-id="86dd5-1261">RUT</span></span> 
- <span data-ttu-id="86dd5-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="86dd5-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="86dd5-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="86dd5-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="86dd5-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="86dd5-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="86dd5-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="86dd5-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="86dd5-1266">中國居民身分證 (PRC) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1267">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1267">Format</span></span>

<span data-ttu-id="86dd5-1268">18 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1269">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1269">Pattern</span></span>

<span data-ttu-id="86dd5-1270">18 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1270">18 digits:</span></span>
- <span data-ttu-id="86dd5-1271">六位數的地址代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="86dd5-1272">Yyyymmdd 格式的八位數，代表出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-1273">三位數的序碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="86dd5-1274">一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1275">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1275">Checksum</span></span>

<span data-ttu-id="86dd5-1276">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1277">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1277">Definition</span></span>

<span data-ttu-id="86dd5-1278">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1279">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1280">找不到來自 Keyword_china_resident_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="86dd5-1281">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1281">The checksum passes.</span></span>

<span data-ttu-id="86dd5-1282">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1283">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1284">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1285">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="86dd5-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="86dd5-1287">居民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="86dd5-1288">中國</span><span class="sxs-lookup"><span data-stu-id="86dd5-1288">PRC</span></span> 
- <span data-ttu-id="86dd5-1289">國民身分識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1289">National Identification Card</span></span> 
- <span data-ttu-id="86dd5-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="86dd5-1290">身份证</span></span> 
- <span data-ttu-id="86dd5-1291">居民身份证</span><span class="sxs-lookup"><span data-stu-id="86dd5-1291">居民 身份证</span></span> 
- <span data-ttu-id="86dd5-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="86dd5-1292">居民身份证</span></span> 
- <span data-ttu-id="86dd5-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="86dd5-1293">鉴定</span></span> 
- <span data-ttu-id="86dd5-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1294">身分證</span></span> 
- <span data-ttu-id="86dd5-1295">居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1295">居民 身份證</span></span>
- <span data-ttu-id="86dd5-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="86dd5-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="86dd5-1297">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1298">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1298">Format</span></span>

<span data-ttu-id="86dd5-1299">16 位數，可格式化或未格式化 (dddddddddddddddd)，且必須通過 Luhn 測試。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1300">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1300">Pattern</span></span>

<span data-ttu-id="86dd5-1301">偵測全球，包括 Visa、 Mastercard、 Discover Card、 JCB、 American Express、 禮品卡和大來卡所有主要品牌的非常複雜且健全的模式。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1302">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1302">Checksum</span></span>

<span data-ttu-id="86dd5-1303">是，Luhn 總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1304">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1304">Definition</span></span>

<span data-ttu-id="86dd5-1305">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1306">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1307">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1307">One of the following is true:</span></span>
    - <span data-ttu-id="86dd5-1308">找不到來自 Keyword_cc_verification 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="86dd5-1309">找不到來自 Keyword_cc_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="86dd5-1310">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="86dd5-1311">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1311">The checksum passes.</span></span>

<span data-ttu-id="86dd5-1312">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1313">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1314">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="86dd5-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="86dd5-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="86dd5-1317">卡片驗證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1317">card verification</span></span>
- <span data-ttu-id="86dd5-1318">卡識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1318">card identification number</span></span>
- <span data-ttu-id="86dd5-1319">cvn 驗證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1319">cvn</span></span>
- <span data-ttu-id="86dd5-1320">cid</span><span class="sxs-lookup"><span data-stu-id="86dd5-1320">cid</span></span>
- <span data-ttu-id="86dd5-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="86dd5-1321">cvc2</span></span>
- <span data-ttu-id="86dd5-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="86dd5-1322">cvv2</span></span>
- <span data-ttu-id="86dd5-1323">pin 碼區塊</span><span class="sxs-lookup"><span data-stu-id="86dd5-1323">pin block</span></span>
- <span data-ttu-id="86dd5-1324">安全性驗證碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1324">security code</span></span>
- <span data-ttu-id="86dd5-1325">安全號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1325">security number</span></span>
- <span data-ttu-id="86dd5-1326">安全性沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-1326">security no</span></span>
- <span data-ttu-id="86dd5-1327">此問題： 數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1327">issue number</span></span>
- <span data-ttu-id="86dd5-1328">發出否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1328">issue no</span></span>
- <span data-ttu-id="86dd5-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="86dd5-1329">cryptogramme</span></span>
- <span data-ttu-id="86dd5-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="86dd5-1330">numéro de sécurité</span></span>
- <span data-ttu-id="86dd5-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="86dd5-1331">numero de securite</span></span>
- <span data-ttu-id="86dd5-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="86dd5-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="86dd5-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1334">prüfziffer</span></span>
- <span data-ttu-id="86dd5-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1335">prufziffer</span></span>
- <span data-ttu-id="86dd5-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="86dd5-1336">sicherheits Kode</span></span>
- <span data-ttu-id="86dd5-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="86dd5-1337">sicherheitscode</span></span>
- <span data-ttu-id="86dd5-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="86dd5-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1339">verfalldatum</span></span>
- <span data-ttu-id="86dd5-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="86dd5-1340">codice di verifica</span></span>
- <span data-ttu-id="86dd5-1341">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1341">cod.</span></span> <span data-ttu-id="86dd5-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1342">sicurezza</span></span>
- <span data-ttu-id="86dd5-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1343">cod sicurezza</span></span>
- <span data-ttu-id="86dd5-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="86dd5-1344">n autorizzazione</span></span>
- <span data-ttu-id="86dd5-1345">código</span><span class="sxs-lookup"><span data-stu-id="86dd5-1345">código</span></span>
- <span data-ttu-id="86dd5-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="86dd5-1346">codigo</span></span>
- <span data-ttu-id="86dd5-1347">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1347">cod.</span></span> <span data-ttu-id="86dd5-1348">seg</span><span class="sxs-lookup"><span data-stu-id="86dd5-1348">seg</span></span>
- <span data-ttu-id="86dd5-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="86dd5-1349">cod seg</span></span>
- <span data-ttu-id="86dd5-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1350">código de segurança</span></span>
- <span data-ttu-id="86dd5-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1351">codigo de seguranca</span></span>
- <span data-ttu-id="86dd5-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1352">codigo de segurança</span></span>
- <span data-ttu-id="86dd5-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1353">código de seguranca</span></span>
- <span data-ttu-id="86dd5-1354">cód。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1354">cód.</span></span> <span data-ttu-id="86dd5-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1355">segurança</span></span>
- <span data-ttu-id="86dd5-1356">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1356">cod.</span></span> <span data-ttu-id="86dd5-1357">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1357">seguranca cod.</span></span> <span data-ttu-id="86dd5-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1358">segurança</span></span>
- <span data-ttu-id="86dd5-1359">cód。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1359">cód.</span></span> <span data-ttu-id="86dd5-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1360">seguranca</span></span>
- <span data-ttu-id="86dd5-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1361">cód segurança</span></span>
- <span data-ttu-id="86dd5-1362">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="86dd5-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1363">cód seguranca</span></span>
- <span data-ttu-id="86dd5-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="86dd5-1364">número de verificação</span></span>
- <span data-ttu-id="86dd5-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1365">numero de verificacao</span></span>
- <span data-ttu-id="86dd5-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="86dd5-1366">ablauf</span></span>
- <span data-ttu-id="86dd5-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="86dd5-1367">gültig bis</span></span>
- <span data-ttu-id="86dd5-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="86dd5-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="86dd5-1369">gultig bis</span></span>
- <span data-ttu-id="86dd5-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="86dd5-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1371">scadenza</span></span>
- <span data-ttu-id="86dd5-1372">資料 scad</span><span class="sxs-lookup"><span data-stu-id="86dd5-1372">data scad</span></span>
- <span data-ttu-id="86dd5-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="86dd5-1373">fecha de expiracion</span></span>
- <span data-ttu-id="86dd5-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1374">fecha de venc</span></span>
- <span data-ttu-id="86dd5-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="86dd5-1375">vencimiento</span></span>
- <span data-ttu-id="86dd5-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1376">válido hasta</span></span>
- <span data-ttu-id="86dd5-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1377">valido hasta</span></span>
- <span data-ttu-id="86dd5-1378">vto</span><span class="sxs-lookup"><span data-stu-id="86dd5-1378">vto</span></span>
- <span data-ttu-id="86dd5-1379">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="86dd5-1379">data de expiração</span></span>
- <span data-ttu-id="86dd5-1380">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1380">data de expiracao</span></span>
- <span data-ttu-id="86dd5-1381">資料長破折號 que expira</span><span class="sxs-lookup"><span data-stu-id="86dd5-1381">data em que expira</span></span>
- <span data-ttu-id="86dd5-1382">validade</span><span class="sxs-lookup"><span data-stu-id="86dd5-1382">validade</span></span>
- <span data-ttu-id="86dd5-1383">勇氣</span><span class="sxs-lookup"><span data-stu-id="86dd5-1383">valor</span></span>
- <span data-ttu-id="86dd5-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="86dd5-1384">vencimento</span></span>
- <span data-ttu-id="86dd5-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="86dd5-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="86dd5-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="86dd5-1387">amex</span><span class="sxs-lookup"><span data-stu-id="86dd5-1387">amex</span></span>
- <span data-ttu-id="86dd5-1388">american express</span><span class="sxs-lookup"><span data-stu-id="86dd5-1388">american express</span></span>
- <span data-ttu-id="86dd5-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="86dd5-1389">americanexpress</span></span>
- <span data-ttu-id="86dd5-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="86dd5-1390">Visa</span></span>
- <span data-ttu-id="86dd5-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1391">mastercard</span></span>
- <span data-ttu-id="86dd5-1392">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1392">master card</span></span>
- <span data-ttu-id="86dd5-1393">mc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1393">mc</span></span> 
- <span data-ttu-id="86dd5-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1394">mastercards</span></span>
- <span data-ttu-id="86dd5-1395">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1395">master cards</span></span>
- <span data-ttu-id="86dd5-1396">大來卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1396">diner's Club</span></span>
- <span data-ttu-id="86dd5-1397">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="86dd5-1397">diners club</span></span>
- <span data-ttu-id="86dd5-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="86dd5-1398">dinersclub</span></span>
- <span data-ttu-id="86dd5-1399">探索卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1399">discover card</span></span>
- <span data-ttu-id="86dd5-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1400">discovercard</span></span>
- <span data-ttu-id="86dd5-1401">探索卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1401">discover cards</span></span>
- <span data-ttu-id="86dd5-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="86dd5-1402">JCB</span></span>
- <span data-ttu-id="86dd5-1403">日文卡機構</span><span class="sxs-lookup"><span data-stu-id="86dd5-1403">japanese card bureau</span></span>
- <span data-ttu-id="86dd5-1404">相關表示</span><span class="sxs-lookup"><span data-stu-id="86dd5-1404">carte blanche</span></span>
- <span data-ttu-id="86dd5-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="86dd5-1405">carteblanche</span></span>
- <span data-ttu-id="86dd5-1406">信用卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1406">credit card</span></span>
- <span data-ttu-id="86dd5-1407">cc #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1407">cc#</span></span>
- <span data-ttu-id="86dd5-1408">cc # 中：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1408">cc#:</span></span>
- <span data-ttu-id="86dd5-1409">到期日</span><span class="sxs-lookup"><span data-stu-id="86dd5-1409">expiration date</span></span>
- <span data-ttu-id="86dd5-1410">exp 日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1410">exp date</span></span>
- <span data-ttu-id="86dd5-1411">到期日</span><span class="sxs-lookup"><span data-stu-id="86dd5-1411">expiry date</span></span>
- <span data-ttu-id="86dd5-1412">日期 d'expiration</span><span class="sxs-lookup"><span data-stu-id="86dd5-1412">date d’expiration</span></span>
- <span data-ttu-id="86dd5-1413">日期 d'exp</span><span class="sxs-lookup"><span data-stu-id="86dd5-1413">date d'exp</span></span>
- <span data-ttu-id="86dd5-1414">日期到期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1414">date expiration</span></span>
- <span data-ttu-id="86dd5-1415">銀行卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1415">bank card</span></span>
- <span data-ttu-id="86dd5-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1416">bankcard</span></span>
- <span data-ttu-id="86dd5-1417">證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1417">card number</span></span>
- <span data-ttu-id="86dd5-1418">卡片 num</span><span class="sxs-lookup"><span data-stu-id="86dd5-1418">card num</span></span>
- <span data-ttu-id="86dd5-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1419">cardnumber</span></span>
- <span data-ttu-id="86dd5-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="86dd5-1420">cardnumbers</span></span>
- <span data-ttu-id="86dd5-1421">卡號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1421">card numbers</span></span>
- <span data-ttu-id="86dd5-1422">信用卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1422">creditcard</span></span>
- <span data-ttu-id="86dd5-1423">信用卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1423">credit cards</span></span>
- <span data-ttu-id="86dd5-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1424">creditcards</span></span>
- <span data-ttu-id="86dd5-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="86dd5-1425">ccn</span></span>
- <span data-ttu-id="86dd5-1426">持卡人</span><span class="sxs-lookup"><span data-stu-id="86dd5-1426">card holder</span></span>
- <span data-ttu-id="86dd5-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="86dd5-1427">cardholder</span></span>
- <span data-ttu-id="86dd5-1428">卡片持有者</span><span class="sxs-lookup"><span data-stu-id="86dd5-1428">card holders</span></span>
- <span data-ttu-id="86dd5-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="86dd5-1429">cardholders</span></span>
- <span data-ttu-id="86dd5-1430">檢查卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1430">check card</span></span>
- <span data-ttu-id="86dd5-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1431">checkcard</span></span>
- <span data-ttu-id="86dd5-1432">檢查卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1432">check cards</span></span>
- <span data-ttu-id="86dd5-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1433">checkcards</span></span>
- <span data-ttu-id="86dd5-1434">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1434">debit card</span></span>
- <span data-ttu-id="86dd5-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1435">debitcard</span></span>
- <span data-ttu-id="86dd5-1436">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1436">debit cards</span></span>
- <span data-ttu-id="86dd5-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1437">debitcards</span></span>
- <span data-ttu-id="86dd5-1438">atm 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1438">atm card</span></span>
- <span data-ttu-id="86dd5-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1439">atmcard</span></span>
- <span data-ttu-id="86dd5-1440">atm 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1440">atm cards</span></span>
- <span data-ttu-id="86dd5-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1441">atmcards</span></span>
- <span data-ttu-id="86dd5-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="86dd5-1442">enroute</span></span>
- <span data-ttu-id="86dd5-1443">en-us 路由</span><span class="sxs-lookup"><span data-stu-id="86dd5-1443">en route</span></span>
- <span data-ttu-id="86dd5-1444">卡類型</span><span class="sxs-lookup"><span data-stu-id="86dd5-1444">card type</span></span>
- <span data-ttu-id="86dd5-1445">相關 bancaire</span><span class="sxs-lookup"><span data-stu-id="86dd5-1445">carte bancaire</span></span>
- <span data-ttu-id="86dd5-1446">相關 de crédit</span><span class="sxs-lookup"><span data-stu-id="86dd5-1446">carte de crédit</span></span>
- <span data-ttu-id="86dd5-1447">相關 de 信用</span><span class="sxs-lookup"><span data-stu-id="86dd5-1447">carte de credit</span></span>
- <span data-ttu-id="86dd5-1448">numéro de 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1448">numéro de carte</span></span>
- <span data-ttu-id="86dd5-1449">numero de 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1449">numero de carte</span></span>
- <span data-ttu-id="86dd5-1450">nº de la 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1450">nº de la carte</span></span>
- <span data-ttu-id="86dd5-1451">nº de 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1451">nº de carte</span></span>
- <span data-ttu-id="86dd5-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="86dd5-1452">kreditkarte</span></span>
- <span data-ttu-id="86dd5-1453">karte</span><span class="sxs-lookup"><span data-stu-id="86dd5-1453">karte</span></span>
- <span data-ttu-id="86dd5-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1454">karteninhaber</span></span>
- <span data-ttu-id="86dd5-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="86dd5-1455">karteninhabers</span></span>
- <span data-ttu-id="86dd5-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="86dd5-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="86dd5-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="86dd5-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="86dd5-1458">kreditkartentyp</span></span>
- <span data-ttu-id="86dd5-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="86dd5-1459">eigentümername</span></span>
- <span data-ttu-id="86dd5-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="86dd5-1460">kartennr</span></span> 
- <span data-ttu-id="86dd5-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1461">kartennummer</span></span>
- <span data-ttu-id="86dd5-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1462">kreditkartennummer</span></span>
- <span data-ttu-id="86dd5-1463">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="86dd5-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1464">carta di credito</span></span>
- <span data-ttu-id="86dd5-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1465">carta credito</span></span>
- <span data-ttu-id="86dd5-1466">carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1466">carta</span></span>
- <span data-ttu-id="86dd5-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1467">n carta</span></span>
- <span data-ttu-id="86dd5-1468">編號。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1468">nr.</span></span> <span data-ttu-id="86dd5-1469">carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1469">carta</span></span>
- <span data-ttu-id="86dd5-1470">編號 carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1470">nr carta</span></span>
- <span data-ttu-id="86dd5-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1471">numero carta</span></span>
- <span data-ttu-id="86dd5-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1472">numero della carta</span></span>
- <span data-ttu-id="86dd5-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1473">numero di carta</span></span>
- <span data-ttu-id="86dd5-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1474">tarjeta credito</span></span>
- <span data-ttu-id="86dd5-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1475">tarjeta de credito</span></span>
- <span data-ttu-id="86dd5-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1476">tarjeta crédito</span></span>
- <span data-ttu-id="86dd5-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="86dd5-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="86dd5-1478">tarjeta de atm</span></span>
- <span data-ttu-id="86dd5-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="86dd5-1479">tarjeta atm</span></span>
- <span data-ttu-id="86dd5-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1480">tarjeta debito</span></span>
- <span data-ttu-id="86dd5-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1481">tarjeta de debito</span></span>
- <span data-ttu-id="86dd5-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1482">tarjeta débito</span></span>
- <span data-ttu-id="86dd5-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1483">tarjeta de débito</span></span>
- <span data-ttu-id="86dd5-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1484">nº de tarjeta</span></span>
- <span data-ttu-id="86dd5-1485">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1485">no.</span></span> <span data-ttu-id="86dd5-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1486">de tarjeta</span></span>
- <span data-ttu-id="86dd5-1487">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1487">no de tarjeta</span></span>
- <span data-ttu-id="86dd5-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1488">numero de tarjeta</span></span>
- <span data-ttu-id="86dd5-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1489">número de tarjeta</span></span>
- <span data-ttu-id="86dd5-1490">tarjeta 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-1490">tarjeta no</span></span>
- <span data-ttu-id="86dd5-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="86dd5-1491">tarjetahabiente</span></span>
- <span data-ttu-id="86dd5-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1492">cartão de crédito</span></span>
- <span data-ttu-id="86dd5-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1493">cartão de credito</span></span>
- <span data-ttu-id="86dd5-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1494">cartao de crédito</span></span>
- <span data-ttu-id="86dd5-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1495">cartao de credito</span></span>
- <span data-ttu-id="86dd5-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1496">cartão de débito</span></span>
- <span data-ttu-id="86dd5-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1497">cartao de débito</span></span>
- <span data-ttu-id="86dd5-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1498">cartão de debito</span></span>
- <span data-ttu-id="86dd5-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1499">cartao de debito</span></span>
- <span data-ttu-id="86dd5-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="86dd5-1500">débito automático</span></span>
- <span data-ttu-id="86dd5-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="86dd5-1501">debito automatico</span></span>
- <span data-ttu-id="86dd5-1502">número 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1502">número do cartão</span></span>
- <span data-ttu-id="86dd5-1503">numero 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1503">numero do cartão</span></span> 
- <span data-ttu-id="86dd5-1504">número 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1504">número do cartao</span></span>
- <span data-ttu-id="86dd5-1505">numero 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1505">numero do cartao</span></span>
- <span data-ttu-id="86dd5-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1506">número de cartão</span></span>
- <span data-ttu-id="86dd5-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1507">numero de cartão</span></span>
- <span data-ttu-id="86dd5-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1508">número de cartao</span></span>
- <span data-ttu-id="86dd5-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1509">numero de cartao</span></span>
- <span data-ttu-id="86dd5-1510">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1510">nº do cartão</span></span>
- <span data-ttu-id="86dd5-1511">nº 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1511">nº do cartao</span></span>
- <span data-ttu-id="86dd5-1512">nº。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1512">nº.</span></span> <span data-ttu-id="86dd5-1513">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1513">do cartão</span></span>
- <span data-ttu-id="86dd5-1514">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1514">no do cartão</span></span>
- <span data-ttu-id="86dd5-1515">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1515">no do cartao</span></span>
- <span data-ttu-id="86dd5-1516">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1516">no.</span></span> <span data-ttu-id="86dd5-1517">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1517">do cartão</span></span>
- <span data-ttu-id="86dd5-1518">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1518">no.</span></span> <span data-ttu-id="86dd5-1519">請勿 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="86dd5-1520">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1521">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1521">Format</span></span>

<span data-ttu-id="86dd5-1522">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1523">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1523">Pattern</span></span>

<span data-ttu-id="86dd5-1524">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1525">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1525">Checksum</span></span>

<span data-ttu-id="86dd5-1526">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1527">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1527">Definition</span></span>

<span data-ttu-id="86dd5-1528">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1529">函數 Func_croatia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1530">找不到來自 Keyword_croatia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-1531">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="86dd5-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="86dd5-1533">克羅埃西亞身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1533">Croatian identity card</span></span>
- <span data-ttu-id="86dd5-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="86dd5-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="86dd5-1535">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1536">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1536">Format</span></span>

<span data-ttu-id="86dd5-1537">11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1538">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1538">Pattern</span></span>

<span data-ttu-id="86dd5-1539">11 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1539">11 digits:</span></span>
- <span data-ttu-id="86dd5-1540">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1540">10 digits</span></span> 
- <span data-ttu-id="86dd5-1541">最後一個數字是檢查碼國際資料交換的目的，字母 HR 新增前面十一個數字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1542">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1542">Checksum</span></span>

<span data-ttu-id="86dd5-1543">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1544">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1544">Definition</span></span>

<span data-ttu-id="86dd5-1545">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1546">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1547">找不到來自 Keyword_croatia_oib_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="86dd5-1548">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1548">The checksum passes.</span></span>

<span data-ttu-id="86dd5-1549">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1550">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1551">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1552">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="86dd5-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="86dd5-1554">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1554">Personal Identification Number</span></span>
- <span data-ttu-id="86dd5-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="86dd5-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="86dd5-1556">OIB 碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="86dd5-1557">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1558">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1558">Format</span></span>

<span data-ttu-id="86dd5-1559">具有選用的九位數正斜線 （舊格式） 搭配選用的 10 位數正斜線 （新格式）</span><span class="sxs-lookup"><span data-stu-id="86dd5-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1560">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1560">Pattern</span></span>

<span data-ttu-id="86dd5-1561">九位數 （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="86dd5-1562">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1562">Nine digits</span></span>

<span data-ttu-id="86dd5-1563">或</span><span class="sxs-lookup"><span data-stu-id="86dd5-1563">OR</span></span>

- <span data-ttu-id="86dd5-1564">代表出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="86dd5-1565">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="86dd5-1565">A forward slash</span></span>
- <span data-ttu-id="86dd5-1566">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1566">Three digits</span></span>

<span data-ttu-id="86dd5-1567">10 位數 （新格式）：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1567">10 digits (new format):</span></span>
- <span data-ttu-id="86dd5-1568">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1568">10 digits</span></span>

<span data-ttu-id="86dd5-1569">或</span><span class="sxs-lookup"><span data-stu-id="86dd5-1569">OR</span></span>

- <span data-ttu-id="86dd5-1570">代表出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="86dd5-1571">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="86dd5-1571">A forward slash</span></span> 
- <span data-ttu-id="86dd5-1572">四個位數最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1573">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1573">Checksum</span></span>

<span data-ttu-id="86dd5-1574">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1575">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1575">Definition</span></span>

<span data-ttu-id="86dd5-1576">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_czech_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-1577">找不到來自 Keyword_czech_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="86dd5-1578">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="86dd5-1579">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1579">Keywords</span></span>

- <span data-ttu-id="86dd5-1580">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1580">czech personal identity number</span></span>
- <span data-ttu-id="86dd5-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="86dd5-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="86dd5-1582">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1583">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1583">Format</span></span>

<span data-ttu-id="86dd5-1584">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1585">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1585">Pattern</span></span>

<span data-ttu-id="86dd5-1586">10 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1586">10 digits:</span></span>
- <span data-ttu-id="86dd5-1587">DDMMYY 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-1588">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-1588">A hyphen</span></span> 
- <span data-ttu-id="86dd5-1589">四個位數最後一個數字是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1590">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1590">Checksum</span></span>

<span data-ttu-id="86dd5-1591">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1592">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1592">Definition</span></span>

<span data-ttu-id="86dd5-1593">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 規則運算式 Regex_denmark_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-1594">找不到來自 Keyword_denmark_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="86dd5-1595">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-1596">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="86dd5-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="86dd5-1598">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1598">Personal Identification Number</span></span>
- <span data-ttu-id="86dd5-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="86dd5-1599">CPR</span></span>
- <span data-ttu-id="86dd5-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="86dd5-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="86dd5-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="86dd5-1602">藥物管理局 (DEA) 編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1603">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1603">Format</span></span>

<span data-ttu-id="86dd5-1604">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1605">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1605">Pattern</span></span>

<span data-ttu-id="86dd5-1606">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="86dd5-1607">一個字母 （不區分大小寫） 從這組可能的字母： abcdefghjklmnprstux，此為註冊者代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="86dd5-1608">一個字母 （不區分大小寫），也就是註冊者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="86dd5-1609">七位數，最後一個數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1610">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1610">Checksum</span></span>

<span data-ttu-id="86dd5-1611">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1612">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1612">Definition</span></span>

<span data-ttu-id="86dd5-1613">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1614">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1615">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-1616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1616">Keywords</span></span>

<span data-ttu-id="86dd5-1617">無</span><span class="sxs-lookup"><span data-stu-id="86dd5-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="86dd5-1618">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1619">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1619">Format</span></span>

<span data-ttu-id="86dd5-1620">16 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1621">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1621">Pattern</span></span>

<span data-ttu-id="86dd5-1622">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1623">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1623">Checksum</span></span>

<span data-ttu-id="86dd5-1624">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1625">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1625">Definition</span></span>

<span data-ttu-id="86dd5-1626">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1627">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1628">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="86dd5-1629">找不到來自 Keyword_eu_debit_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="86dd5-1630">找不到來自 Keyword_card_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="86dd5-1631">找不到來自 Keyword_card_security_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="86dd5-1632">找不到來自 Keyword_card_expiration_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="86dd5-1633">函數 Func_expiration_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="86dd5-1634">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1635">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="86dd5-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="86dd5-1637">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1637">account number</span></span> 
- <span data-ttu-id="86dd5-1638">證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1638">card number</span></span> 
- <span data-ttu-id="86dd5-1639">卡否。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1639">card no.</span></span> 
- <span data-ttu-id="86dd5-1640">安全號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1640">security number</span></span> 
- <span data-ttu-id="86dd5-1641">cc #</span><span class="sxs-lookup"><span data-stu-id="86dd5-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="86dd5-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="86dd5-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="86dd5-1643">acct 芳鄰</span><span class="sxs-lookup"><span data-stu-id="86dd5-1643">acct nbr</span></span> 
- <span data-ttu-id="86dd5-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="86dd5-1644">acct num</span></span> 
- <span data-ttu-id="86dd5-1645">acct 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-1645">acct no</span></span> 
- <span data-ttu-id="86dd5-1646">american express</span><span class="sxs-lookup"><span data-stu-id="86dd5-1646">american express</span></span> 
- <span data-ttu-id="86dd5-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="86dd5-1647">americanexpress</span></span> 
- <span data-ttu-id="86dd5-1648">americano 濃縮咖啡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1648">americano espresso</span></span> 
- <span data-ttu-id="86dd5-1649">amex</span><span class="sxs-lookup"><span data-stu-id="86dd5-1649">amex</span></span> 
- <span data-ttu-id="86dd5-1650">atm 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1650">atm card</span></span> 
- <span data-ttu-id="86dd5-1651">atm 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1651">atm cards</span></span> 
- <span data-ttu-id="86dd5-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1652">atm kaart</span></span> 
- <span data-ttu-id="86dd5-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1653">atmcard</span></span> 
- <span data-ttu-id="86dd5-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1654">atmcards</span></span> 
- <span data-ttu-id="86dd5-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1655">atmkaart</span></span> 
- <span data-ttu-id="86dd5-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="86dd5-1656">atmkaarten</span></span> 
- <span data-ttu-id="86dd5-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="86dd5-1657">bancontact</span></span> 
- <span data-ttu-id="86dd5-1658">銀行卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1658">bank card</span></span> 
- <span data-ttu-id="86dd5-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1659">bankkaart</span></span> 
- <span data-ttu-id="86dd5-1660">持卡人</span><span class="sxs-lookup"><span data-stu-id="86dd5-1660">card holder</span></span> 
- <span data-ttu-id="86dd5-1661">卡片持有者</span><span class="sxs-lookup"><span data-stu-id="86dd5-1661">card holders</span></span> 
- <span data-ttu-id="86dd5-1662">卡片 num</span><span class="sxs-lookup"><span data-stu-id="86dd5-1662">card num</span></span> 
- <span data-ttu-id="86dd5-1663">證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1663">card number</span></span> 
- <span data-ttu-id="86dd5-1664">卡號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1664">card numbers</span></span> 
- <span data-ttu-id="86dd5-1665">卡類型</span><span class="sxs-lookup"><span data-stu-id="86dd5-1665">card type</span></span> 
- <span data-ttu-id="86dd5-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="86dd5-1666">cardano numerico</span></span> 
- <span data-ttu-id="86dd5-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="86dd5-1667">cardholder</span></span> 
- <span data-ttu-id="86dd5-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="86dd5-1668">cardholders</span></span> 
- <span data-ttu-id="86dd5-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1669">cardnumber</span></span> 
- <span data-ttu-id="86dd5-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="86dd5-1670">cardnumbers</span></span> 
- <span data-ttu-id="86dd5-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1671">carta bianca</span></span> 
- <span data-ttu-id="86dd5-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1672">carta credito</span></span> 
- <span data-ttu-id="86dd5-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1673">carta di credito</span></span> 
- <span data-ttu-id="86dd5-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1674">cartao de credito</span></span> 
- <span data-ttu-id="86dd5-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1675">cartao de crédito</span></span> 
- <span data-ttu-id="86dd5-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1676">cartao de debito</span></span> 
- <span data-ttu-id="86dd5-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1677">cartao de débito</span></span> 
- <span data-ttu-id="86dd5-1678">相關 bancaire</span><span class="sxs-lookup"><span data-stu-id="86dd5-1678">carte bancaire</span></span> 
- <span data-ttu-id="86dd5-1679">相關表示</span><span class="sxs-lookup"><span data-stu-id="86dd5-1679">carte blanche</span></span> 
- <span data-ttu-id="86dd5-1680">相關 bleue</span><span class="sxs-lookup"><span data-stu-id="86dd5-1680">carte bleue</span></span> 
- <span data-ttu-id="86dd5-1681">相關 de 信用</span><span class="sxs-lookup"><span data-stu-id="86dd5-1681">carte de credit</span></span> 
- <span data-ttu-id="86dd5-1682">相關 de crédit</span><span class="sxs-lookup"><span data-stu-id="86dd5-1682">carte de crédit</span></span> 
- <span data-ttu-id="86dd5-1683">相關 di credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1683">carte di credito</span></span> 
- <span data-ttu-id="86dd5-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="86dd5-1684">carteblanche</span></span> 
- <span data-ttu-id="86dd5-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1685">cartão de credito</span></span> 
- <span data-ttu-id="86dd5-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1686">cartão de crédito</span></span> 
- <span data-ttu-id="86dd5-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1687">cartão de debito</span></span> 
- <span data-ttu-id="86dd5-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1688">cartão de débito</span></span> 
- <span data-ttu-id="86dd5-1689">cb</span><span class="sxs-lookup"><span data-stu-id="86dd5-1689">cb</span></span> 
- <span data-ttu-id="86dd5-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="86dd5-1690">ccn</span></span> 
- <span data-ttu-id="86dd5-1691">檢查卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1691">check card</span></span> 
- <span data-ttu-id="86dd5-1692">檢查卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1692">check cards</span></span> 
- <span data-ttu-id="86dd5-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1693">checkcard</span></span>
- <span data-ttu-id="86dd5-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1694">checkcards</span></span> 
- <span data-ttu-id="86dd5-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1695">chequekaart</span></span> 
- <span data-ttu-id="86dd5-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="86dd5-1696">cirrus</span></span> 
- <span data-ttu-id="86dd5-1697">cirrus-edc-大師</span><span class="sxs-lookup"><span data-stu-id="86dd5-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="86dd5-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1698">controlekaart</span></span> 
- <span data-ttu-id="86dd5-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="86dd5-1699">controlekaarten</span></span> 
- <span data-ttu-id="86dd5-1700">信用卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1700">credit card</span></span> 
- <span data-ttu-id="86dd5-1701">信用卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1701">credit cards</span></span> 
- <span data-ttu-id="86dd5-1702">信用卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1702">creditcard</span></span> 
- <span data-ttu-id="86dd5-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1703">creditcards</span></span> 
- <span data-ttu-id="86dd5-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1704">debetkaart</span></span> 
- <span data-ttu-id="86dd5-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="86dd5-1705">debetkaarten</span></span> 
- <span data-ttu-id="86dd5-1706">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1706">debit card</span></span> 
- <span data-ttu-id="86dd5-1707">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1707">debit cards</span></span> 
- <span data-ttu-id="86dd5-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1708">debitcard</span></span> 
- <span data-ttu-id="86dd5-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1709">debitcards</span></span> 
- <span data-ttu-id="86dd5-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="86dd5-1710">debito automatico</span></span> 
- <span data-ttu-id="86dd5-1711">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="86dd5-1711">diners club</span></span> 
- <span data-ttu-id="86dd5-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="86dd5-1712">dinersclub</span></span> 
- <span data-ttu-id="86dd5-1713">探索</span><span class="sxs-lookup"><span data-stu-id="86dd5-1713">discover</span></span> 
- <span data-ttu-id="86dd5-1714">探索卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1714">discover card</span></span> 
- <span data-ttu-id="86dd5-1715">探索卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1715">discover cards</span></span> 
- <span data-ttu-id="86dd5-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1716">discovercard</span></span> 
- <span data-ttu-id="86dd5-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1717">discovercards</span></span> 
- <span data-ttu-id="86dd5-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="86dd5-1718">débito automático</span></span>
- <span data-ttu-id="86dd5-1719">edc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1719">edc</span></span> 
- <span data-ttu-id="86dd5-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="86dd5-1720">eigentümername</span></span> 
- <span data-ttu-id="86dd5-1721">歐洲轉帳卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1721">european debit card</span></span> 
- <span data-ttu-id="86dd5-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1722">hoofdkaart</span></span> 
- <span data-ttu-id="86dd5-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="86dd5-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="86dd5-1724">在 [viaggio</span><span class="sxs-lookup"><span data-stu-id="86dd5-1724">in viaggio</span></span> 
- <span data-ttu-id="86dd5-1725">日文卡機構</span><span class="sxs-lookup"><span data-stu-id="86dd5-1725">japanese card bureau</span></span> 
- <span data-ttu-id="86dd5-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="86dd5-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="86dd5-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="86dd5-1727">jcb</span></span> 
- <span data-ttu-id="86dd5-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="86dd5-1728">kaart</span></span> 
- <span data-ttu-id="86dd5-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="86dd5-1729">kaart num</span></span> 
- <span data-ttu-id="86dd5-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="86dd5-1730">kaartaantal</span></span> 
- <span data-ttu-id="86dd5-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="86dd5-1731">kaartaantallen</span></span> 
- <span data-ttu-id="86dd5-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="86dd5-1732">kaarthouder</span></span> 
- <span data-ttu-id="86dd5-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="86dd5-1733">kaarthouders</span></span> 
- <span data-ttu-id="86dd5-1734">karte</span><span class="sxs-lookup"><span data-stu-id="86dd5-1734">karte</span></span>  
- <span data-ttu-id="86dd5-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1735">karteninhaber</span></span> 
- <span data-ttu-id="86dd5-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="86dd5-1736">karteninhabers</span></span>
- <span data-ttu-id="86dd5-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="86dd5-1737">kartennr</span></span> 
- <span data-ttu-id="86dd5-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1738">kartennummer</span></span> 
- <span data-ttu-id="86dd5-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="86dd5-1739">kreditkarte</span></span> 
- <span data-ttu-id="86dd5-1740">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="86dd5-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="86dd5-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="86dd5-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="86dd5-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="86dd5-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="86dd5-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="86dd5-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="86dd5-1745">大師</span><span class="sxs-lookup"><span data-stu-id="86dd5-1745">maestro</span></span> 
- <span data-ttu-id="86dd5-1746">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1746">master card</span></span> 
- <span data-ttu-id="86dd5-1747">主圖形卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-1747">master cards</span></span> 
- <span data-ttu-id="86dd5-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="86dd5-1748">mastercard</span></span> 
- <span data-ttu-id="86dd5-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="86dd5-1749">mastercards</span></span> 
- <span data-ttu-id="86dd5-1750">mc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1750">mc</span></span> 
- <span data-ttu-id="86dd5-1751">先生現金</span><span class="sxs-lookup"><span data-stu-id="86dd5-1751">mister cash</span></span> 
- <span data-ttu-id="86dd5-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1752">n carta</span></span> 
- <span data-ttu-id="86dd5-1753">carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1753">carta</span></span> 
- <span data-ttu-id="86dd5-1754">沒有 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1754">no de tarjeta</span></span> 
- <span data-ttu-id="86dd5-1755">沒有執行 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1755">no do cartao</span></span> 
- <span data-ttu-id="86dd5-1756">沒有執行 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1756">no do cartão</span></span> 
- <span data-ttu-id="86dd5-1757">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1757">no.</span></span> <span data-ttu-id="86dd5-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1758">de tarjeta</span></span> 
- <span data-ttu-id="86dd5-1759">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1759">no.</span></span> <span data-ttu-id="86dd5-1760">請勿 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1760">do cartao</span></span> 
- <span data-ttu-id="86dd5-1761">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1761">no.</span></span> <span data-ttu-id="86dd5-1762">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1762">do cartão</span></span> 
- <span data-ttu-id="86dd5-1763">編號 carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1763">nr carta</span></span> 
- <span data-ttu-id="86dd5-1764">編號。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1764">nr.</span></span> <span data-ttu-id="86dd5-1765">carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1765">carta</span></span> 
- <span data-ttu-id="86dd5-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1766">numeri di scheda</span></span> 
- <span data-ttu-id="86dd5-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1767">numero carta</span></span> 
- <span data-ttu-id="86dd5-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1768">numero de cartao</span></span> 
- <span data-ttu-id="86dd5-1769">numero de 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1769">numero de carte</span></span> 
- <span data-ttu-id="86dd5-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1770">numero de cartão</span></span> 
- <span data-ttu-id="86dd5-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1771">numero de tarjeta</span></span>
- <span data-ttu-id="86dd5-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1772">numero della carta</span></span> 
- <span data-ttu-id="86dd5-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1773">numero di carta</span></span> 
- <span data-ttu-id="86dd5-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1774">numero di scheda</span></span> 
- <span data-ttu-id="86dd5-1775">numero 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1775">numero do cartao</span></span> 
- <span data-ttu-id="86dd5-1776">numero 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1776">numero do cartão</span></span> 
- <span data-ttu-id="86dd5-1777">numéro de 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1777">numéro de carte</span></span> 
- <span data-ttu-id="86dd5-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1778">nº carta</span></span> 
- <span data-ttu-id="86dd5-1779">nº de 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1779">nº de carte</span></span> 
- <span data-ttu-id="86dd5-1780">nº de la 相關</span><span class="sxs-lookup"><span data-stu-id="86dd5-1780">nº de la carte</span></span> 
- <span data-ttu-id="86dd5-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="86dd5-1782">nº 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1782">nº do cartao</span></span> 
- <span data-ttu-id="86dd5-1783">nº 不要 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1783">nº do cartão</span></span> 
- <span data-ttu-id="86dd5-1784">nº。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1784">nº.</span></span> <span data-ttu-id="86dd5-1785">請勿 cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1785">do cartão</span></span> 
- <span data-ttu-id="86dd5-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1786">número de cartao</span></span> 
- <span data-ttu-id="86dd5-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="86dd5-1787">número de cartão</span></span> 
- <span data-ttu-id="86dd5-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1788">número de tarjeta</span></span> 
- <span data-ttu-id="86dd5-1789">número 不要 cartao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1789">número do cartao</span></span> 
- <span data-ttu-id="86dd5-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="86dd5-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="86dd5-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="86dd5-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="86dd5-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="86dd5-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="86dd5-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1793">scheda della banca</span></span> 
- <span data-ttu-id="86dd5-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="86dd5-1794">scheda di controllo</span></span> 
- <span data-ttu-id="86dd5-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1795">scheda di debito</span></span> 
- <span data-ttu-id="86dd5-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="86dd5-1796">scheda matrice</span></span> 
- <span data-ttu-id="86dd5-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="86dd5-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="86dd5-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="86dd5-1798">schede di controllo</span></span> 
- <span data-ttu-id="86dd5-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1799">schede di debito</span></span> 
- <span data-ttu-id="86dd5-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="86dd5-1800">schede matrici</span></span> 
- <span data-ttu-id="86dd5-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="86dd5-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="86dd5-1802">scoprono le schede</span></span> 
- <span data-ttu-id="86dd5-1803">solo</span><span class="sxs-lookup"><span data-stu-id="86dd5-1803">solo</span></span> 
- <span data-ttu-id="86dd5-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1804">supporti di scheda</span></span> 
- <span data-ttu-id="86dd5-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1805">supporto di scheda</span></span> 
- <span data-ttu-id="86dd5-1806">切換</span><span class="sxs-lookup"><span data-stu-id="86dd5-1806">switch</span></span> 
- <span data-ttu-id="86dd5-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="86dd5-1807">tarjeta atm</span></span> 
- <span data-ttu-id="86dd5-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1808">tarjeta credito</span></span> 
- <span data-ttu-id="86dd5-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="86dd5-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="86dd5-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="86dd5-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="86dd5-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="86dd5-1812">tarjeta debito</span></span> 
- <span data-ttu-id="86dd5-1813">tarjeta 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-1813">tarjeta no</span></span>
- <span data-ttu-id="86dd5-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="86dd5-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="86dd5-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1815">tipo della scheda</span></span> 
- <span data-ttu-id="86dd5-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="86dd5-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="86dd5-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1817">scheda</span></span> 
- <span data-ttu-id="86dd5-1818">v 工資</span><span class="sxs-lookup"><span data-stu-id="86dd5-1818">v pay</span></span> 
- <span data-ttu-id="86dd5-1819">v 工資</span><span class="sxs-lookup"><span data-stu-id="86dd5-1819">v-pay</span></span> 
- <span data-ttu-id="86dd5-1820">visa</span><span class="sxs-lookup"><span data-stu-id="86dd5-1820">visa</span></span> 
- <span data-ttu-id="86dd5-1821">visa 加上</span><span class="sxs-lookup"><span data-stu-id="86dd5-1821">visa plus</span></span> 
- <span data-ttu-id="86dd5-1822">visa 電</span><span class="sxs-lookup"><span data-stu-id="86dd5-1822">visa electron</span></span> 
- <span data-ttu-id="86dd5-1823">visto</span><span class="sxs-lookup"><span data-stu-id="86dd5-1823">visto</span></span> 
- <span data-ttu-id="86dd5-1824">visum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1824">visum</span></span> 
- <span data-ttu-id="86dd5-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="86dd5-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="86dd5-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="86dd5-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="86dd5-1827">卡識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1827">card identification number</span></span>
- <span data-ttu-id="86dd5-1828">卡片驗證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1828">card verification</span></span> 
- <span data-ttu-id="86dd5-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="86dd5-1829">cardi la verifica</span></span> 
- <span data-ttu-id="86dd5-1830">cid</span><span class="sxs-lookup"><span data-stu-id="86dd5-1830">cid</span></span> 
- <span data-ttu-id="86dd5-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="86dd5-1831">cod seg</span></span> 
- <span data-ttu-id="86dd5-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1832">cod seguranca</span></span> 
- <span data-ttu-id="86dd5-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1833">cod segurança</span></span> 
- <span data-ttu-id="86dd5-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1834">cod sicurezza</span></span> 
- <span data-ttu-id="86dd5-1835">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1835">cod.</span></span> <span data-ttu-id="86dd5-1836">seg</span><span class="sxs-lookup"><span data-stu-id="86dd5-1836">seg</span></span> 
- <span data-ttu-id="86dd5-1837">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1837">cod.</span></span> <span data-ttu-id="86dd5-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1838">seguranca</span></span> 
- <span data-ttu-id="86dd5-1839">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1839">cod.</span></span> <span data-ttu-id="86dd5-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1840">segurança</span></span> 
- <span data-ttu-id="86dd5-1841">cod。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1841">cod.</span></span> <span data-ttu-id="86dd5-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1842">sicurezza</span></span> 
- <span data-ttu-id="86dd5-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="86dd5-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="86dd5-1844">codice di verifica</span></span> 
- <span data-ttu-id="86dd5-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="86dd5-1845">codigo</span></span> 
- <span data-ttu-id="86dd5-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="86dd5-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1847">codigo de segurança</span></span> 
- <span data-ttu-id="86dd5-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="86dd5-1848">crittogramma</span></span> 
- <span data-ttu-id="86dd5-1849">密碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1849">cryptogram</span></span> 
- <span data-ttu-id="86dd5-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="86dd5-1850">cryptogramme</span></span> 
- <span data-ttu-id="86dd5-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="86dd5-1851">cv2</span></span> 
- <span data-ttu-id="86dd5-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1852">cvc</span></span> 
- <span data-ttu-id="86dd5-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="86dd5-1853">cvc2</span></span> 
- <span data-ttu-id="86dd5-1854">cvn 驗證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1854">cvn</span></span> 
- <span data-ttu-id="86dd5-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="86dd5-1855">cvv</span></span> 
- <span data-ttu-id="86dd5-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="86dd5-1856">cvv2</span></span> 
- <span data-ttu-id="86dd5-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1857">cód seguranca</span></span> 
- <span data-ttu-id="86dd5-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1858">cód segurança</span></span> 
- <span data-ttu-id="86dd5-1859">cód。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1859">cód.</span></span> <span data-ttu-id="86dd5-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1860">seguranca</span></span> 
- <span data-ttu-id="86dd5-1861">cód。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1861">cód.</span></span> <span data-ttu-id="86dd5-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1862">segurança</span></span> 
- <span data-ttu-id="86dd5-1863">código</span><span class="sxs-lookup"><span data-stu-id="86dd5-1863">código</span></span> 
- <span data-ttu-id="86dd5-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="86dd5-1864">código de seguranca</span></span> 
- <span data-ttu-id="86dd5-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="86dd5-1865">código de segurança</span></span> 
- <span data-ttu-id="86dd5-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="86dd5-1866">de kaart controle</span></span> 
- <span data-ttu-id="86dd5-1867">geeft 編號 uit</span><span class="sxs-lookup"><span data-stu-id="86dd5-1867">geeft nr uit</span></span> 
- <span data-ttu-id="86dd5-1868">發出否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1868">issue no</span></span> 
- <span data-ttu-id="86dd5-1869">此問題： 數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1869">issue number</span></span> 
- <span data-ttu-id="86dd5-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="86dd5-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="86dd5-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="86dd5-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="86dd5-1873">kwestieaantal</span></span> 
- <span data-ttu-id="86dd5-1874">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1874">no.</span></span> <span data-ttu-id="86dd5-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="86dd5-1875">dell'edizione</span></span> 
- <span data-ttu-id="86dd5-1876">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1876">no.</span></span> <span data-ttu-id="86dd5-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1877">di sicurezza</span></span> 
- <span data-ttu-id="86dd5-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="86dd5-1878">numero de securite</span></span> 
- <span data-ttu-id="86dd5-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1879">numero de verificacao</span></span> 
- <span data-ttu-id="86dd5-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="86dd5-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="86dd5-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="86dd5-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="86dd5-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="86dd5-1882">scheda</span></span> 
- <span data-ttu-id="86dd5-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="86dd5-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="86dd5-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="86dd5-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="86dd5-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="86dd5-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="86dd5-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="86dd5-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="86dd5-1887">número de verificação</span></span> 
- <span data-ttu-id="86dd5-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="86dd5-1888">perno il blocco</span></span> 
- <span data-ttu-id="86dd5-1889">pin 碼區塊</span><span class="sxs-lookup"><span data-stu-id="86dd5-1889">pin block</span></span> 
- <span data-ttu-id="86dd5-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1890">prufziffer</span></span> 
- <span data-ttu-id="86dd5-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1891">prüfziffer</span></span> 
- <span data-ttu-id="86dd5-1892">安全性驗證碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1892">security code</span></span> 
- <span data-ttu-id="86dd5-1893">安全性沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-1893">security no</span></span> 
- <span data-ttu-id="86dd5-1894">安全號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1894">security number</span></span> 
- <span data-ttu-id="86dd5-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="86dd5-1895">sicherheits kode</span></span> 
- <span data-ttu-id="86dd5-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="86dd5-1896">sicherheitscode</span></span> 
- <span data-ttu-id="86dd5-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="86dd5-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="86dd5-1898">speldblok</span></span> 
- <span data-ttu-id="86dd5-1899">veiligheid 編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-1899">veiligheid nr</span></span> 
- <span data-ttu-id="86dd5-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="86dd5-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="86dd5-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="86dd5-1901">veiligheidscode</span></span> 
- <span data-ttu-id="86dd5-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="86dd5-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="86dd5-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="86dd5-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="86dd5-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="86dd5-1905">ablauf</span></span> 
- <span data-ttu-id="86dd5-1906">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="86dd5-1906">data de expiracao</span></span> 
- <span data-ttu-id="86dd5-1907">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="86dd5-1907">data de expiração</span></span> 
- <span data-ttu-id="86dd5-1908">資料 del exp</span><span class="sxs-lookup"><span data-stu-id="86dd5-1908">data del exp</span></span> 
- <span data-ttu-id="86dd5-1909">資料 di exp</span><span class="sxs-lookup"><span data-stu-id="86dd5-1909">data di exp</span></span> 
- <span data-ttu-id="86dd5-1910">資料 di scadenza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1910">data di scadenza</span></span> 
- <span data-ttu-id="86dd5-1911">資料長破折號 que expira</span><span class="sxs-lookup"><span data-stu-id="86dd5-1911">data em que expira</span></span> 
- <span data-ttu-id="86dd5-1912">資料 scad</span><span class="sxs-lookup"><span data-stu-id="86dd5-1912">data scad</span></span> 
- <span data-ttu-id="86dd5-1913">資料 scadenza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1913">data scadenza</span></span> 
- <span data-ttu-id="86dd5-1914">日期 de validité</span><span class="sxs-lookup"><span data-stu-id="86dd5-1914">date de validité</span></span> 
- <span data-ttu-id="86dd5-1915">材料 afloop</span><span class="sxs-lookup"><span data-stu-id="86dd5-1915">datum afloop</span></span> 
- <span data-ttu-id="86dd5-1916">材料 van exp</span><span class="sxs-lookup"><span data-stu-id="86dd5-1916">datum van exp</span></span> 
- <span data-ttu-id="86dd5-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="86dd5-1917">de afloop</span></span> 
- <span data-ttu-id="86dd5-1918">espira</span><span class="sxs-lookup"><span data-stu-id="86dd5-1918">espira</span></span> 
- <span data-ttu-id="86dd5-1919">espira</span><span class="sxs-lookup"><span data-stu-id="86dd5-1919">espira</span></span> 
- <span data-ttu-id="86dd5-1920">exp 日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1920">exp date</span></span> 
- <span data-ttu-id="86dd5-1921">exp 材料</span><span class="sxs-lookup"><span data-stu-id="86dd5-1921">exp datum</span></span> 
- <span data-ttu-id="86dd5-1922">到期日</span><span class="sxs-lookup"><span data-stu-id="86dd5-1922">expiration</span></span> 
- <span data-ttu-id="86dd5-1923">到期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1923">expire</span></span> 
- <span data-ttu-id="86dd5-1924">到期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1924">expires</span></span> 
- <span data-ttu-id="86dd5-1925">到期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1925">expiry</span></span> 
- <span data-ttu-id="86dd5-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="86dd5-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="86dd5-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1927">fecha de venc</span></span> 
- <span data-ttu-id="86dd5-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="86dd5-1928">gultig bis</span></span> 
- <span data-ttu-id="86dd5-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="86dd5-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="86dd5-1930">gültig bis</span></span> 
- <span data-ttu-id="86dd5-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="86dd5-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1932">la scadenza</span></span> 
- <span data-ttu-id="86dd5-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="86dd5-1933">scadenza</span></span> 
- <span data-ttu-id="86dd5-1934">valable</span><span class="sxs-lookup"><span data-stu-id="86dd5-1934">valable</span></span> 
- <span data-ttu-id="86dd5-1935">validade</span><span class="sxs-lookup"><span data-stu-id="86dd5-1935">validade</span></span> 
- <span data-ttu-id="86dd5-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1936">valido hasta</span></span> 
- <span data-ttu-id="86dd5-1937">勇氣</span><span class="sxs-lookup"><span data-stu-id="86dd5-1937">valor</span></span> 
- <span data-ttu-id="86dd5-1938">venc</span><span class="sxs-lookup"><span data-stu-id="86dd5-1938">venc</span></span> 
- <span data-ttu-id="86dd5-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="86dd5-1939">vencimento</span></span> 
- <span data-ttu-id="86dd5-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="86dd5-1940">vencimiento</span></span> 
- <span data-ttu-id="86dd5-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="86dd5-1941">verloopt</span></span> 
- <span data-ttu-id="86dd5-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="86dd5-1942">vervaldag</span></span> 
- <span data-ttu-id="86dd5-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-1943">vervaldatum</span></span> 
- <span data-ttu-id="86dd5-1944">vto</span><span class="sxs-lookup"><span data-stu-id="86dd5-1944">vto</span></span> 
- <span data-ttu-id="86dd5-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="86dd5-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="86dd5-1946">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-1946">EU Driver's License Number</span></span>

<span data-ttu-id="86dd5-1947">若要深入了解，請參閱 <<c0>歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="86dd5-1948">歐盟國家識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1948">EU National Identification Number</span></span>

<span data-ttu-id="86dd5-1949">若要深入了解，請參閱 <<c0>歐盟國家識別碼號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="86dd5-1950">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1950">EU Passport Number</span></span>

<span data-ttu-id="86dd5-1951">若要深入了解，請參閱 <<c0>歐盟護照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="86dd5-1952">歐盟社會安全號碼或對等項目識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="86dd5-1953">若要了解更多，請參閱[歐盟社會安全號碼或對等識別碼敏感資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="86dd5-1954">歐盟稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="86dd5-1955">若要深入了解，請參閱 <<c0>歐盟稅務識別號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="86dd5-1956">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1957">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1957">Format</span></span>

<span data-ttu-id="86dd5-1958">六位數加上字元，指出世紀加上三位數加上檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1959">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1959">Pattern</span></span>

<span data-ttu-id="86dd5-1960">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="86dd5-1961">格式的六位數，格式為 DDMMYY，專屬於出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="86dd5-1962">世紀標記 (可以是 '-'、 '+' 或 'a')</span><span class="sxs-lookup"><span data-stu-id="86dd5-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="86dd5-1963">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="86dd5-1964">數字或字母 （不區分大小寫） 這是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1965">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1965">Checksum</span></span>

<span data-ttu-id="86dd5-1966">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1967">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1967">Definition</span></span>

<span data-ttu-id="86dd5-1968">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1969">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1970">找不到來自 Keyword_finnish_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="86dd5-1971">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-1972">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1972">Keywords</span></span>

- <span data-ttu-id="86dd5-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="86dd5-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="86dd5-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="86dd5-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="86dd5-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="86dd5-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="86dd5-1976">Personbeteckning</span></span>
- <span data-ttu-id="86dd5-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="86dd5-1978">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1978">Finland Passport Number</span></span>

<span data-ttu-id="86dd5-1979">格式的九個字母和數字模式組合九個字母和數字的組合： 兩個字母 （不區分大小寫） 七位數總和檢查碼否定義 DLP 原則是 75%以內，則已偵測到此敏感資訊類型的如果、 內接近性是 300 個字元： 規則運算式 Regex_finland_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-1980">找不到來自 Keyword_finland_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="86dd5-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="86dd5-1981"></span></span>
<span data-ttu-id="86dd5-1982">關鍵字 Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="86dd5-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="86dd5-1983">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-1984">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1984">Format</span></span>

<span data-ttu-id="86dd5-1985">12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-1986">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-1986">Pattern</span></span>

<span data-ttu-id="86dd5-1987">12 位數驗證以忽略類似模式，例如法國電話號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-1988">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-1988">Checksum</span></span>

<span data-ttu-id="86dd5-1989">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-1990">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-1990">Definition</span></span>

<span data-ttu-id="86dd5-1991">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-1992">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-1993">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="86dd5-1994">找不到來自 Keyword_french_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="86dd5-1995">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-1996">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="86dd5-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="86dd5-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="86dd5-1998">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-1998">drivers licence</span></span>
- <span data-ttu-id="86dd5-1999">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-1999">drivers license</span></span>
- <span data-ttu-id="86dd5-2000">driving 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2000">driving licence</span></span>
- <span data-ttu-id="86dd5-2001">主導授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2001">driving license</span></span>
- <span data-ttu-id="86dd5-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="86dd5-2002">permis de conduire</span></span>
- <span data-ttu-id="86dd5-2003">授權數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-2003">licence number</span></span>
- <span data-ttu-id="86dd5-2004">駕照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2004">license number</span></span>
- <span data-ttu-id="86dd5-2005">授權數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2005">licence numbers</span></span>
- <span data-ttu-id="86dd5-2006">照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="86dd5-2007">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2008">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2008">Format</span></span>

<span data-ttu-id="86dd5-2009">12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2010">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2010">Pattern</span></span>

<span data-ttu-id="86dd5-2011">12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2012">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2012">Checksum</span></span>

<span data-ttu-id="86dd5-2013">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2014">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2014">Definition</span></span>

<span data-ttu-id="86dd5-2015">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2016">規則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2017">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2017">Keywords</span></span>

<span data-ttu-id="86dd5-2018">無</span><span class="sxs-lookup"><span data-stu-id="86dd5-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="86dd5-2019">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2020">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2020">Format</span></span>

<span data-ttu-id="86dd5-2021">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2022">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2022">Pattern</span></span>

<span data-ttu-id="86dd5-2023">九個數字和字母：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="86dd5-2024">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2024">Two digits</span></span> 
- <span data-ttu-id="86dd5-2025">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-2026">五位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2027">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2027">Checksum</span></span>

<span data-ttu-id="86dd5-2028">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2029">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2029">Definition</span></span>

<span data-ttu-id="86dd5-2030">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2031">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2032">找不到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2033">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="86dd5-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-2034">Keyword_passport</span></span>

- <span data-ttu-id="86dd5-2035">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2035">Passport Number</span></span>
- <span data-ttu-id="86dd5-2036">Passport 否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2036">Passport No</span></span>
- <span data-ttu-id="86dd5-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2037">Passport #</span></span>
- <span data-ttu-id="86dd5-2038">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2038">Passport#</span></span>
- <span data-ttu-id="86dd5-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="86dd5-2039">PassportID</span></span>
- <span data-ttu-id="86dd5-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="86dd5-2040">Passportno</span></span>
- <span data-ttu-id="86dd5-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-2041">passportnumber</span></span>
- <span data-ttu-id="86dd5-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="86dd5-2042">パスポート</span></span>
- <span data-ttu-id="86dd5-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2043">パスポート番号</span></span>
- <span data-ttu-id="86dd5-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="86dd5-2044">パスポートのNum</span></span>
- <span data-ttu-id="86dd5-2045">パスポート #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2045">パスポート ＃</span></span> 
- <span data-ttu-id="86dd5-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="86dd5-2046">Numéro de passeport</span></span>
- <span data-ttu-id="86dd5-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="86dd5-2047">Passeport n °</span></span>
- <span data-ttu-id="86dd5-2048">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="86dd5-2048">Passeport Non</span></span>
- <span data-ttu-id="86dd5-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2049">Passeport #</span></span>
- <span data-ttu-id="86dd5-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2050">Passeport#</span></span>
- <span data-ttu-id="86dd5-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="86dd5-2051">PasseportNon</span></span>
- <span data-ttu-id="86dd5-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="86dd5-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="86dd5-2053">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2054">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2054">Format</span></span>

<span data-ttu-id="86dd5-2055">15 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2056">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2056">Pattern</span></span>

<span data-ttu-id="86dd5-2057">必須符合兩個模式之一：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="86dd5-2058">13 位數後尾隨尾隨兩位數的空間</span><span class="sxs-lookup"><span data-stu-id="86dd5-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="86dd5-2059">或</span><span class="sxs-lookup"><span data-stu-id="86dd5-2059">or</span></span>
- <span data-ttu-id="86dd5-2060">15 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2061">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2061">Checksum</span></span>

<span data-ttu-id="86dd5-2062">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2063">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2063">Definition</span></span>

<span data-ttu-id="86dd5-2064">DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2065">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2066">找不到來自 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="86dd5-2067">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2067">The checksum passes.</span></span>

<span data-ttu-id="86dd5-2068">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2069">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2070">找不到來自 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="86dd5-2071">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2072">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="86dd5-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="86dd5-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="86dd5-2074">insee</span><span class="sxs-lookup"><span data-stu-id="86dd5-2074">insee</span></span>
- <span data-ttu-id="86dd5-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2075">securité sociale</span></span>
- <span data-ttu-id="86dd5-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2076">securite sociale</span></span>
- <span data-ttu-id="86dd5-2077">國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2077">national id</span></span>
- <span data-ttu-id="86dd5-2078">國民身分識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-2078">national identification</span></span>
- <span data-ttu-id="86dd5-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="86dd5-2079">numéro d'identité</span></span>
- <span data-ttu-id="86dd5-2080">沒有 d'identité</span><span class="sxs-lookup"><span data-stu-id="86dd5-2080">no d'identité</span></span>
- <span data-ttu-id="86dd5-2081">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2081">no.</span></span> <span data-ttu-id="86dd5-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="86dd5-2082">d'identité</span></span>
- <span data-ttu-id="86dd5-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="86dd5-2083">numero d'identite</span></span>
- <span data-ttu-id="86dd5-2084">沒有 d'identite</span><span class="sxs-lookup"><span data-stu-id="86dd5-2084">no d'identite</span></span>
- <span data-ttu-id="86dd5-2085">無。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2085">no.</span></span> <span data-ttu-id="86dd5-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="86dd5-2086">d'identite</span></span>
- <span data-ttu-id="86dd5-2087">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2087">social security number</span></span>
- <span data-ttu-id="86dd5-2088">社會安全的程式碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2088">social security code</span></span>
- <span data-ttu-id="86dd5-2089">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2089">social insurance number</span></span>
- <span data-ttu-id="86dd5-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="86dd5-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2091">d'identité nationale</span></span>
- <span data-ttu-id="86dd5-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="86dd5-2093">le 程式碼 de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="86dd5-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="86dd5-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="86dd5-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="86dd5-2095">numéro de sécu</span></span>
- <span data-ttu-id="86dd5-2096">程式碼 sécu</span><span class="sxs-lookup"><span data-stu-id="86dd5-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="86dd5-2097">德國駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2098">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2098">Format</span></span>

<span data-ttu-id="86dd5-2099">11 個數字和字母的組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2100">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2100">Pattern</span></span>

<span data-ttu-id="86dd5-2101">11 個數字和字母 （不區分大小寫）：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="86dd5-2102">數字或字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2102">A digit or letter</span></span> 
- <span data-ttu-id="86dd5-2103">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2103">Two digits</span></span> 
- <span data-ttu-id="86dd5-2104">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2104">Six digits or letters</span></span> 
- <span data-ttu-id="86dd5-2105">數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2105">A digit</span></span> 
- <span data-ttu-id="86dd5-2106">數字或字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2107">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2107">Checksum</span></span>

<span data-ttu-id="86dd5-2108">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2109">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2109">Definition</span></span>

<span data-ttu-id="86dd5-2110">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2111">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2112">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="86dd5-2113">找不到來自 Keyword_german_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="86dd5-2114">找不到來自 Keyword_german_drivers_license_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="86dd5-2115">找不到來自 Keyword_german_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="86dd5-2116">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2117">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="86dd5-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="86dd5-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2119">Führerschein</span></span>
- <span data-ttu-id="86dd5-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2120">Fuhrerschein</span></span>
- <span data-ttu-id="86dd5-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2121">Fuehrerschein</span></span>
- <span data-ttu-id="86dd5-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="86dd5-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="86dd5-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="86dd5-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="86dd5-2125">Führerschein-</span></span> 
- <span data-ttu-id="86dd5-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="86dd5-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="86dd5-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="86dd5-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="86dd5-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="86dd5-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="86dd5-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="86dd5-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="86dd5-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="86dd5-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="86dd5-2134">Führerschein-編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="86dd5-2135">Fuhrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="86dd5-2136">Fuehrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="86dd5-2137">Führerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="86dd5-2138">Fuhrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="86dd5-2139">Fuehrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="86dd5-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="86dd5-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="86dd5-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="86dd5-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="86dd5-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="86dd5-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="86dd5-2146">Führerschein-編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="86dd5-2147">Fuhrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="86dd5-2148">Fuehrerschein-編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="86dd5-2149">Führerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="86dd5-2150">Fuhrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="86dd5-2151">Fuehrerschein-Klasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="86dd5-2152">DL</span><span class="sxs-lookup"><span data-stu-id="86dd5-2152">DL</span></span> 
- <span data-ttu-id="86dd5-2153">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="86dd5-2153">DLS</span></span>
- <span data-ttu-id="86dd5-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-2154">Driv Lic</span></span> 
- <span data-ttu-id="86dd5-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="86dd5-2155">Driv Licen</span></span> 
- <span data-ttu-id="86dd5-2156">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2156">Driv License</span></span>
- <span data-ttu-id="86dd5-2157">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2157">Driv Licenses</span></span> 
- <span data-ttu-id="86dd5-2158">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2158">Driv Licence</span></span> 
- <span data-ttu-id="86dd5-2159">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2159">Driv Licences</span></span> 
- <span data-ttu-id="86dd5-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-2160">Driv Lic</span></span> 
- <span data-ttu-id="86dd5-2161">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="86dd5-2161">Driver Licen</span></span> 
- <span data-ttu-id="86dd5-2162">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2162">Driver License</span></span> 
- <span data-ttu-id="86dd5-2163">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2163">Driver Licenses</span></span> 
- <span data-ttu-id="86dd5-2164">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2164">Driver Licence</span></span> 
- <span data-ttu-id="86dd5-2165">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2165">Driver Licences</span></span> 
- <span data-ttu-id="86dd5-2166">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-2166">Drivers Lic</span></span> 
- <span data-ttu-id="86dd5-2167">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="86dd5-2167">Drivers Licen</span></span> 
- <span data-ttu-id="86dd5-2168">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2168">Drivers License</span></span> 
- <span data-ttu-id="86dd5-2169">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="86dd5-2170">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2170">Drivers Licence</span></span> 
- <span data-ttu-id="86dd5-2171">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2171">Drivers Licences</span></span> 
- <span data-ttu-id="86dd5-2172">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-2172">Driver's Lic</span></span> 
- <span data-ttu-id="86dd5-2173">駕 Licen</span><span class="sxs-lookup"><span data-stu-id="86dd5-2173">Driver's Licen</span></span> 
- <span data-ttu-id="86dd5-2174">駕照</span><span class="sxs-lookup"><span data-stu-id="86dd5-2174">Driver's License</span></span> 
- <span data-ttu-id="86dd5-2175">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="86dd5-2176">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2176">Driver's Licence</span></span> 
- <span data-ttu-id="86dd5-2177">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2177">Driver's Licences</span></span> 
- <span data-ttu-id="86dd5-2178">主導 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-2178">Driving Lic</span></span> 
- <span data-ttu-id="86dd5-2179">主導 Licen</span><span class="sxs-lookup"><span data-stu-id="86dd5-2179">Driving Licen</span></span> 
- <span data-ttu-id="86dd5-2180">主導授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2180">Driving License</span></span> 
- <span data-ttu-id="86dd5-2181">主導授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2181">Driving Licenses</span></span> 
- <span data-ttu-id="86dd5-2182">Driving 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2182">Driving Licence</span></span> 
- <span data-ttu-id="86dd5-2183">Driving 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="86dd5-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="86dd5-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="86dd5-2185">編號 Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="86dd5-2186">編號 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="86dd5-2187">編號 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="86dd5-2188">否 Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2188">No-Führerschein</span></span> 
- <span data-ttu-id="86dd5-2189">否 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="86dd5-2190">否 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="86dd5-2191">N Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2191">N-Führerschein</span></span> 
- <span data-ttu-id="86dd5-2192">N Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="86dd5-2193">N Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="86dd5-2194">編號 Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="86dd5-2195">編號 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="86dd5-2196">編號 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="86dd5-2197">否 Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2197">No-Führerschein</span></span> 
- <span data-ttu-id="86dd5-2198">否 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="86dd5-2199">否 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="86dd5-2200">N Führerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2200">N-Führerschein</span></span> 
- <span data-ttu-id="86dd5-2201">N Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="86dd5-2202">N Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="86dd5-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="86dd5-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="86dd5-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="86dd5-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="86dd5-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="86dd5-2205">ausstellungsort</span></span>
- <span data-ttu-id="86dd5-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="86dd5-2206">ausstellende behöde</span></span>
- <span data-ttu-id="86dd5-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="86dd5-2207">ausstellende behorde</span></span>
- <span data-ttu-id="86dd5-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="86dd5-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="86dd5-2209">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2210">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2210">Format</span></span>

<span data-ttu-id="86dd5-2211">10 個數字或字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2212">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2212">Pattern</span></span>

<span data-ttu-id="86dd5-2213">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="86dd5-2214">第一個字元是數字或字母 （C、 F、 G、 H、 J、 K）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="86dd5-2215">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2215">Three digits</span></span> 
- <span data-ttu-id="86dd5-2216">五個數字或字母 (C、 H、 J-N、 P、 R、 T、 V Z)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="86dd5-2217">數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2218">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2218">Checksum</span></span>

<span data-ttu-id="86dd5-2219">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2220">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2220">Definition</span></span>

<span data-ttu-id="86dd5-2221">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2222">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2223">找不到來自五個關鍵字清單任一的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="86dd5-2224">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2224">The checksum passes.</span></span>

<span data-ttu-id="86dd5-2225">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2226">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2227">找不到來自五個關鍵字清單任一的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="86dd5-2228">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2229">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="86dd5-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="86dd5-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="86dd5-2231">reisepass</span></span>
- <span data-ttu-id="86dd5-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="86dd5-2232">reisepasse</span></span>
- <span data-ttu-id="86dd5-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2233">reisepassnummer</span></span>
- <span data-ttu-id="86dd5-2234">passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-2234">passport</span></span>
- <span data-ttu-id="86dd5-2235">護照</span><span class="sxs-lookup"><span data-stu-id="86dd5-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="86dd5-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="86dd5-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="86dd5-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-2237">geburtsdatum</span></span>
- <span data-ttu-id="86dd5-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="86dd5-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="86dd5-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="86dd5-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="86dd5-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="86dd5-2241">無法對 Reisepass 編號 Reisepass</span><span class="sxs-lookup"><span data-stu-id="86dd5-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="86dd5-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="86dd5-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="86dd5-2243">Reisepass 編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="86dd5-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="86dd5-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="86dd5-2245">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="86dd5-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="86dd5-2246">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2247">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2247">Format</span></span>

<span data-ttu-id="86dd5-2248">自從 2010 年 1 年 11 月： 九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="86dd5-2249">從 1 1987 年 31 October 2010: 10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2250">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2250">Pattern</span></span>

<span data-ttu-id="86dd5-2251">自從 1 年 11 月 2010 年：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="86dd5-2252">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-2253">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2253">Eight digits</span></span>

<span data-ttu-id="86dd5-2254">從 1 1987 年 31 October 2010:</span><span class="sxs-lookup"><span data-stu-id="86dd5-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="86dd5-2255">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2256">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2256">Checksum</span></span>

<span data-ttu-id="86dd5-2257">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2258">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2258">Definition</span></span>

<span data-ttu-id="86dd5-2259">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2260">規則運算式 Regex_germany_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2261">找不到來自 Keyword_germany_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2262">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="86dd5-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="86dd5-2264">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2264">Identity Card</span></span>
- <span data-ttu-id="86dd5-2265">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2265">ID</span></span>
- <span data-ttu-id="86dd5-2266">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-2266">Identification</span></span>
- <span data-ttu-id="86dd5-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="86dd5-2267">Personalausweis</span></span>
- <span data-ttu-id="86dd5-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="86dd5-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="86dd5-2269">Ausweis</span></span>
- <span data-ttu-id="86dd5-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="86dd5-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="86dd5-2271">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2272">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2272">Format</span></span>

<span data-ttu-id="86dd5-2273">7-8 個字母和數字加上破折號的組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2274">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2274">Pattern</span></span>

<span data-ttu-id="86dd5-2275">七個字母和數字 （舊格式）︰</span><span class="sxs-lookup"><span data-stu-id="86dd5-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="86dd5-2276">一個字母 （希臘文的任何字母）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="86dd5-2277">一條虛線</span><span class="sxs-lookup"><span data-stu-id="86dd5-2277">A dash</span></span> 
- <span data-ttu-id="86dd5-2278">六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2278">Six digits</span></span>

<span data-ttu-id="86dd5-2279">八個字母和數字 （新格式）︰</span><span class="sxs-lookup"><span data-stu-id="86dd5-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="86dd5-2280">其大寫字元，就會發生在希臘文與拉丁文字母 (ABEZHIKMNOPTYX) 中的兩個字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="86dd5-2281">一條虛線</span><span class="sxs-lookup"><span data-stu-id="86dd5-2281">A dash</span></span> 
- <span data-ttu-id="86dd5-2282">六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2283">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2283">Checksum</span></span>

<span data-ttu-id="86dd5-2284">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2285">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2285">Definition</span></span>

<span data-ttu-id="86dd5-2286">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2287">規則運算式 Regex_greece_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2288">找不到來自 Keyword_greece_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2289">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="86dd5-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="86dd5-2291">希臘文身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2291">Greek identity Card</span></span>
- <span data-ttu-id="86dd5-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="86dd5-2292">Tautotita</span></span>
- <span data-ttu-id="86dd5-2293">ΔΕΛΤΊΟ ΑΣΤΥΝΟΜΙΚΉΣ ΤΑΥΤΌΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="86dd5-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="86dd5-2294">ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="86dd5-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="86dd5-2295">香港身分證 (HKID) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2296">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2296">Format</span></span>

<span data-ttu-id="86dd5-2297">8-9 個字母和數字加上選擇性括住的最後一個字元的組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2298">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2298">Pattern</span></span>

<span data-ttu-id="86dd5-2299">8-9 個字母的組合：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="86dd5-2300">1-2 個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-2301">六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2301">Six digits</span></span> 
- <span data-ttu-id="86dd5-2302">最後一個字元 （任何數字或字母 A），也就是檢查碼 （選擇性） 括住括號。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2303">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2303">Checksum</span></span>

<span data-ttu-id="86dd5-2304">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2305">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2305">Definition</span></span>

<span data-ttu-id="86dd5-2306">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2307">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2308">找不到來自 Keyword_hong_kong_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="86dd5-2309">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2309">The checksum passes.</span></span>

<span data-ttu-id="86dd5-2310">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2311">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2312">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2313">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="86dd5-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="86dd5-2315">香港身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2315">hong kong identity card</span></span>
- <span data-ttu-id="86dd5-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="86dd5-2316">HKIDC</span></span>
- <span data-ttu-id="86dd5-2317">證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2317">id card</span></span>
- <span data-ttu-id="86dd5-2318">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2318">identity card</span></span>
- <span data-ttu-id="86dd5-2319">hk 身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2319">hk identity card</span></span>
- <span data-ttu-id="86dd5-2320">香港識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2320">hong kong id</span></span>
- <span data-ttu-id="86dd5-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2321">香港身份證</span></span>
- <span data-ttu-id="86dd5-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="86dd5-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2323">身份證</span></span>
- <span data-ttu-id="86dd5-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2324">身份証</span></span>
- <span data-ttu-id="86dd5-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2325">身分證</span></span>
- <span data-ttu-id="86dd5-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2326">身分証</span></span>
- <span data-ttu-id="86dd5-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2327">香港身份証</span></span>
- <span data-ttu-id="86dd5-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2328">香港身分證</span></span>
- <span data-ttu-id="86dd5-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2329">香港身分証</span></span>
- <span data-ttu-id="86dd5-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2330">香港身份證</span></span>
- <span data-ttu-id="86dd5-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2331">香港居民身份證</span></span>
- <span data-ttu-id="86dd5-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2332">香港居民身份証</span></span>
- <span data-ttu-id="86dd5-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2333">香港居民身分證</span></span>
- <span data-ttu-id="86dd5-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2334">香港居民身分証</span></span>
- <span data-ttu-id="86dd5-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="86dd5-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="86dd5-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="86dd5-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="86dd5-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="86dd5-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="86dd5-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="86dd5-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="86dd5-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="86dd5-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="86dd5-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="86dd5-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="86dd5-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="86dd5-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="86dd5-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="86dd5-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="86dd5-2351">印度永久帳戶號碼 (PAN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2352">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2352">Format</span></span>

<span data-ttu-id="86dd5-2353">10 個字母或四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2354">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2354">Pattern</span></span>

<span data-ttu-id="86dd5-2355">10 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2355">10 letters or digits:</span></span>
- <span data-ttu-id="86dd5-2356">五個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-2357">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2357">Four digits</span></span> 
- <span data-ttu-id="86dd5-2358">這是一個字母檢查碼的字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2359">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2359">Checksum</span></span>

<span data-ttu-id="86dd5-2360">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2361">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2361">Definition</span></span>

<span data-ttu-id="86dd5-2362">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2363">規則運算式 Regex_india_permanent_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2364">找不到來自 Keyword_india_permanent_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="86dd5-2365">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="86dd5-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="86dd5-2368">永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="86dd5-2369">PAN</span><span class="sxs-lookup"><span data-stu-id="86dd5-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="86dd5-2370">印度唯一識別 （aadhaar） 碼數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2371">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2371">Format</span></span>

<span data-ttu-id="86dd5-2372">12 位數包含選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2373">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2373">Pattern</span></span>

<span data-ttu-id="86dd5-2374">12 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2374">12 digits:</span></span>
- <span data-ttu-id="86dd5-2375">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2375">Four digits</span></span> 
- <span data-ttu-id="86dd5-2376">選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2376">An optional space or dash</span></span> 
- <span data-ttu-id="86dd5-2377">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2377">Four digits</span></span> 
- <span data-ttu-id="86dd5-2378">選擇性空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2378">An optional space or dash</span></span> 
- <span data-ttu-id="86dd5-2379">最後一位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2380">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2380">Checksum</span></span>

<span data-ttu-id="86dd5-2381">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2382">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2382">Definition</span></span>

<span data-ttu-id="86dd5-2383">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-2384">找不到來自 Keyword_india_aadhar 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="86dd5-2385">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2385">The checksum passes.</span></span>
<span data-ttu-id="86dd5-2386">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-2387">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="86dd5-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="86dd5-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="86dd5-2389">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="86dd5-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="86dd5-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="86dd5-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="86dd5-2391">Aadhar</span></span>
- <span data-ttu-id="86dd5-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="86dd5-2392">Aadhaar</span></span>
- <span data-ttu-id="86dd5-2393">UID</span><span class="sxs-lookup"><span data-stu-id="86dd5-2393">UID</span></span>
- <span data-ttu-id="86dd5-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="86dd5-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="86dd5-2395">印尼身分識 (Ktp) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2396">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2396">Format</span></span>

<span data-ttu-id="86dd5-2397">16 位數包含選擇性句點</span><span class="sxs-lookup"><span data-stu-id="86dd5-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2398">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2398">Pattern</span></span>

<span data-ttu-id="86dd5-2399">16 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2399">16 digits:</span></span>
- <span data-ttu-id="86dd5-2400">二位數省代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2400">Two-digit province code</span></span> 
- <span data-ttu-id="86dd5-2401">句點 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2401">A period (optional)</span></span> 
- <span data-ttu-id="86dd5-2402">二位數攝政或城市代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="86dd5-2403">二位數次行政區代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="86dd5-2404">句點 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2404">A period (optional)</span></span> 
- <span data-ttu-id="86dd5-2405">DDMMYY 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-2406">句點 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2406">A period (optional)</span></span> 
- <span data-ttu-id="86dd5-2407">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2408">Checksum</span></span>

<span data-ttu-id="86dd5-2409">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2410">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2410">Definition</span></span>

<span data-ttu-id="86dd5-2411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2412">規則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2413">找不到來自 Keyword_indonesia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="86dd5-2414">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2415">規則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2416">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="86dd5-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="86dd5-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="86dd5-2418">KTP</span></span>
- <span data-ttu-id="86dd5-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="86dd5-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="86dd5-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="86dd5-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="86dd5-2421">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2422">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2422">Format</span></span>

<span data-ttu-id="86dd5-2423">國碼/地區碼 （兩個字母） 加上檢查碼 （兩位數） 再加上 bban （最多 30 個字元）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2424">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2424">Pattern</span></span>

<span data-ttu-id="86dd5-2425">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="86dd5-2426">兩個字母的國碼/地區碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2426">Two-letter country code</span></span>
- <span data-ttu-id="86dd5-2427">兩位數檢查碼 （後面接著一個選用空格）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="86dd5-2428">1-7 組四字母或數字 （可以以空格分隔）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="86dd5-2429">1-3 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2429">1-3 letters or digits</span></span>

<span data-ttu-id="86dd5-2430">每個國家/地區的格式是稍有不同。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2430">The format for each country is slightly different.</span></span> <span data-ttu-id="86dd5-2431">IBAN 敏感資訊類型涵蓋這些 60 國家/地區：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2431">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="86dd5-2432">ad、 ae、 al，在亞利桑那州，ba，是，bg、 bh、 頻道、 cr、 cy、 cz、 de、 粗、 執行、 卻、 es、 wi-fi、 於、 fr、 gb、 ge、 gi、 gl、 /gr、 hr、 hu，ie，il，是，它、 kw、 kz、 lb、 li、 lt、 lu、 lv，mc md、 我、 mk、 mr、 細明體、 記憶nl、 [否] pl、 pt、 ro、 rs、 sa、 se、 si、 sk、 sm、 tn、.msnavedit-linkcell、 vg</span><span class="sxs-lookup"><span data-stu-id="86dd5-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2433">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2433">Checksum</span></span>

<span data-ttu-id="86dd5-2434">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2435">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2435">Definition</span></span>

<span data-ttu-id="86dd5-2436">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2437">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2438">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2439">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2439">Keywords</span></span>

<span data-ttu-id="86dd5-2440">無</span><span class="sxs-lookup"><span data-stu-id="86dd5-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="86dd5-2441">IP 位址</span><span class="sxs-lookup"><span data-stu-id="86dd5-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2442">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="86dd5-2443">IPv4:</span><span class="sxs-lookup"><span data-stu-id="86dd5-2443">IPv4:</span></span>
<span data-ttu-id="86dd5-2444">帳戶版格式化 （句點） 和未格式化 （無句點） 之 IPv4 位址的複雜模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="86dd5-2445">IPv6:</span><span class="sxs-lookup"><span data-stu-id="86dd5-2445">IPv6:</span></span>
<span data-ttu-id="86dd5-2446">哪一個帳戶表示格式化 IPv6 號碼 （其中包含冒號） 的複雜模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2447">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2448">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2448">Checksum</span></span>

<span data-ttu-id="86dd5-2449">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2450">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2450">Definition</span></span>

<span data-ttu-id="86dd5-2451">對於 IPv6 為 DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2452">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2453">找不到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="86dd5-2454">DLP 原則是 95%以內，已偵測到此敏感資訊類型的對於 IPv4，如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2455">規則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2456">找不到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="86dd5-2457">對於 IPv6 為 DLP 原則是 95%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2458">規則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2459">找不到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="86dd5-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="86dd5-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="86dd5-2462">IP （此關鍵字是區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="86dd5-2463">ip 位址</span><span class="sxs-lookup"><span data-stu-id="86dd5-2463">ip address</span></span> 
- <span data-ttu-id="86dd5-2464">ip 位址</span><span class="sxs-lookup"><span data-stu-id="86dd5-2464">ip addresses</span></span>
- <span data-ttu-id="86dd5-2465">網際網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="86dd5-2465">internet protocol</span></span>
- <span data-ttu-id="86dd5-2466">IP כתובת ה</span><span class="sxs-lookup"><span data-stu-id="86dd5-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="86dd5-2467">國際分類的治療法 （ICD-10-公分）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2468">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2468">Format</span></span>

<span data-ttu-id="86dd5-2469">Dictionary</span><span class="sxs-lookup"><span data-stu-id="86dd5-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2470">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2470">Pattern</span></span>

<span data-ttu-id="86dd5-2471">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2472">Checksum</span></span>

<span data-ttu-id="86dd5-2473">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2474">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2474">Definition</span></span>

<span data-ttu-id="86dd5-2475">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2476">找不到來自 Dictionary_icd_10_cm 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="86dd5-2477">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2477">Keywords</span></span>

<span data-ttu-id="86dd5-2478">任何字詞從 Dictionary_icd_10_cm 關鍵字字典，這根據[治療法的國際分類、 十分之一修訂，臨床修改 （ICD-10-公分）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="86dd5-2479">此類型只會尋找該字詞，不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="86dd5-2480">國際分類的治療法 （ICD-9-公分）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2481">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2481">Format</span></span>

<span data-ttu-id="86dd5-2482">Dictionary</span><span class="sxs-lookup"><span data-stu-id="86dd5-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2483">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2483">Pattern</span></span>

<span data-ttu-id="86dd5-2484">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2485">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2485">Checksum</span></span>

<span data-ttu-id="86dd5-2486">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2487">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2487">Definition</span></span>

<span data-ttu-id="86dd5-2488">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2489">找不到來自 Dictionary_icd_9_cm 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2490">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2490">Keywords</span></span>

<span data-ttu-id="86dd5-2491">任何字詞從 Dictionary_icd_9_cm 關鍵字字典，這根據[治療法的國際分類、 二十九個修訂，臨床修改 （ICD-9-公分）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="86dd5-2492">此類型只會尋找該字詞，不保險代碼。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="86dd5-2493">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2494">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2494">Format</span></span>

<span data-ttu-id="86dd5-2495">舊格式 （直到 2012 年 31):</span><span class="sxs-lookup"><span data-stu-id="86dd5-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="86dd5-2496">七位數後尾隨 1-2 個字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="86dd5-2497">新格式 (1 Jan 2013 年):</span><span class="sxs-lookup"><span data-stu-id="86dd5-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="86dd5-2498">七位數後尾隨兩個字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2499">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2499">Pattern</span></span>

<span data-ttu-id="86dd5-2500">舊格式 （直到 2012 年 31):</span><span class="sxs-lookup"><span data-stu-id="86dd5-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="86dd5-2501">七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2501">Seven digits</span></span> 
- <span data-ttu-id="86dd5-2502">1-2 個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="86dd5-2503">新格式 (1 Jan 2013 年):</span><span class="sxs-lookup"><span data-stu-id="86dd5-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="86dd5-2504">七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2504">Seven digits</span></span> 
- <span data-ttu-id="86dd5-2505">字母 （不區分大小寫） 這是一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="86dd5-2506">字母"A"或者"H"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2507">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2507">Checksum</span></span>

<span data-ttu-id="86dd5-2508">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2509">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2509">Definition</span></span>

<span data-ttu-id="86dd5-2510">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2511">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2512">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2512">One of the following is true:</span></span>
    - <span data-ttu-id="86dd5-2513">找不到來自 Keyword_ireland_pps 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="86dd5-2514">函數 Func_eu_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="86dd5-2515">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2515">The checksum passes.</span></span>

<span data-ttu-id="86dd5-2516">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2517">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2518">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2519">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="86dd5-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="86dd5-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="86dd5-2521">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="86dd5-2522">PPS 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-2522">PPS Number</span></span> 
- <span data-ttu-id="86dd5-2523">PPS Num</span><span class="sxs-lookup"><span data-stu-id="86dd5-2523">PPS Num</span></span> 
- <span data-ttu-id="86dd5-2524">PPS [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2524">PPS No.</span></span> 
- <span data-ttu-id="86dd5-2525">PPS #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2525">PPS #</span></span> 
- <span data-ttu-id="86dd5-2526">PPS #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2526">PPS#</span></span> 
- <span data-ttu-id="86dd5-2527">PPSN</span><span class="sxs-lookup"><span data-stu-id="86dd5-2527">PPSN</span></span> 
- <span data-ttu-id="86dd5-2528">公用服務卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-2528">Public Services Card</span></span> 
- <span data-ttu-id="86dd5-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="86dd5-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="86dd5-2530">Uimh。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2530">Uimh.</span></span> <span data-ttu-id="86dd5-2531">PSP</span><span class="sxs-lookup"><span data-stu-id="86dd5-2531">PSP</span></span> 
- <span data-ttu-id="86dd5-2532">PSP</span><span class="sxs-lookup"><span data-stu-id="86dd5-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="86dd5-2533">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2534">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2534">Format</span></span>

<span data-ttu-id="86dd5-2535">13 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2536">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2536">Pattern</span></span>

<span data-ttu-id="86dd5-2537">格式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2537">Formatted:</span></span>
- <span data-ttu-id="86dd5-2538">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2538">Two digits</span></span> 
- <span data-ttu-id="86dd5-2539">一條虛線</span><span class="sxs-lookup"><span data-stu-id="86dd5-2539">A dash</span></span> 
- <span data-ttu-id="86dd5-2540">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2540">Three digits</span></span> 
- <span data-ttu-id="86dd5-2541">一條虛線</span><span class="sxs-lookup"><span data-stu-id="86dd5-2541">A dash</span></span> 
- <span data-ttu-id="86dd5-2542">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2542">Eight digits</span></span>

<span data-ttu-id="86dd5-2543">格式化：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2543">Unformatted:</span></span>
- <span data-ttu-id="86dd5-2544">13 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2545">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2545">Checksum</span></span>

<span data-ttu-id="86dd5-2546">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2547">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2547">Definition</span></span>

<span data-ttu-id="86dd5-2548">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2549">規則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2550">找不到來自 Keyword_israel_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2551">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="86dd5-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="86dd5-2553">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2553">Bank Account Number</span></span> 
- <span data-ttu-id="86dd5-2554">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-2554">Bank Account</span></span> 
- <span data-ttu-id="86dd5-2555">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2555">Account Number</span></span> 
- <span data-ttu-id="86dd5-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="86dd5-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="86dd5-2557">以色列國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2558">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2558">Format</span></span>

<span data-ttu-id="86dd5-2559">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2560">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2560">Pattern</span></span>

<span data-ttu-id="86dd5-2561">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2562">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2562">Checksum</span></span>

<span data-ttu-id="86dd5-2563">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2564">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2564">Definition</span></span>

<span data-ttu-id="86dd5-2565">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2566">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2567">找不到來自 Keyword_Israel_National_ID 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="86dd5-2568">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2569">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="86dd5-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="86dd5-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="86dd5-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="86dd5-2571">מספר זהות</span></span> 
- <span data-ttu-id="86dd5-2572">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="86dd5-2573">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2574">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2574">Format</span></span>

<span data-ttu-id="86dd5-2575">10 個字母和數字的組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2576">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2576">Pattern</span></span>

- <span data-ttu-id="86dd5-2577">10 個字母和數字的組合：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="86dd5-2578">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-2579">字母"A"或者"V"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-2580">七個字母 （不區分大小寫）、 數字或底線字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="86dd5-2581">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2582">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2582">Checksum</span></span>

<span data-ttu-id="86dd5-2583">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2584">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2584">Definition</span></span>

<span data-ttu-id="86dd5-2585">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2586">規則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2587">找不到來自 Keyword_italy_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2588">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="86dd5-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="86dd5-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="86dd5-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="86dd5-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="86dd5-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="86dd5-2592">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2593">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2593">Format</span></span>

<span data-ttu-id="86dd5-2594">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2595">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2595">Pattern</span></span>

<span data-ttu-id="86dd5-2596">銀行帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2596">Bank account number:</span></span>
- <span data-ttu-id="86dd5-2597">7 或 8 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2597">Seven or eight digits</span></span>
- <span data-ttu-id="86dd5-2598">銀行帳戶分行代碼：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2598">Bank account branch code:</span></span>
- <span data-ttu-id="86dd5-2599">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2599">Four digits</span></span> 
- <span data-ttu-id="86dd5-2600">一個空格或破折號 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="86dd5-2601">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2601">Three digits</span></span>

<span data-ttu-id="86dd5-2602">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2602">Checksum</span></span>

<span data-ttu-id="86dd5-2603">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2604">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2604">Definition</span></span>

<span data-ttu-id="86dd5-2605">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2606">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2607">找不到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="86dd5-2608">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2608">One of the following is true:</span></span>
- <span data-ttu-id="86dd5-2609">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2610">找不到來自 Keyword_jp_bank_branch_code 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="86dd5-2611">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2612">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2613">找不到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2614">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="86dd5-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="86dd5-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="86dd5-2616">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2616">Checking Account Number</span></span> 
- <span data-ttu-id="86dd5-2617">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-2617">Checking Account</span></span> 
- <span data-ttu-id="86dd5-2618">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2618">Checking Account #</span></span> 
- <span data-ttu-id="86dd5-2619">檢查 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="86dd5-2620">檢查 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2620">Checking Acct #</span></span> 
- <span data-ttu-id="86dd5-2621">檢查 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="86dd5-2622">檢查帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2622">Checking Account No.</span></span> 
- <span data-ttu-id="86dd5-2623">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2623">Bank Account Number</span></span> 
- <span data-ttu-id="86dd5-2624">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-2624">Bank Account</span></span> 
- <span data-ttu-id="86dd5-2625">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2625">Bank Account #</span></span> 
- <span data-ttu-id="86dd5-2626">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="86dd5-2627">銀行 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2627">Bank Acct #</span></span> 
- <span data-ttu-id="86dd5-2628">銀行 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="86dd5-2629">銀行帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2629">Bank Account No.</span></span> 
- <span data-ttu-id="86dd5-2630">節省帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2630">Savings Account Number</span></span> 
- <span data-ttu-id="86dd5-2631">存款帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-2631">Savings Account</span></span> 
- <span data-ttu-id="86dd5-2632">節省帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2632">Savings Account #</span></span> 
- <span data-ttu-id="86dd5-2633">節省 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="86dd5-2634">節省 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2634">Savings Acct #</span></span> 
- <span data-ttu-id="86dd5-2635">節省 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="86dd5-2636">存款帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2636">Savings Account No.</span></span> 
- <span data-ttu-id="86dd5-2637">轉帳帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2637">Debit Account Number</span></span> 
- <span data-ttu-id="86dd5-2638">轉帳帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-2638">Debit Account</span></span> 
- <span data-ttu-id="86dd5-2639">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2639">Debit Account #</span></span> 
- <span data-ttu-id="86dd5-2640">轉帳 Acct 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="86dd5-2641">借方 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2641">Debit Acct #</span></span> 
- <span data-ttu-id="86dd5-2642">轉帳 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="86dd5-2643">轉帳帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2643">Debit Account No.</span></span> 
- <span data-ttu-id="86dd5-2644">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="86dd5-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="86dd5-2645"># アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="86dd5-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="86dd5-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="86dd5-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="86dd5-2647">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="86dd5-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="86dd5-2648">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="86dd5-2648">口座番号の確認</span></span> 
- <span data-ttu-id="86dd5-2649">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2649">銀行口座番号</span></span> 
- <span data-ttu-id="86dd5-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="86dd5-2650">銀行口座</span></span> 
- <span data-ttu-id="86dd5-2651">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2651">銀行口座＃</span></span> 
- <span data-ttu-id="86dd5-2652">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="86dd5-2653">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="86dd5-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="86dd5-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="86dd5-2655">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2655">銀行口座番号</span></span>
- <span data-ttu-id="86dd5-2656">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="86dd5-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="86dd5-2657">預金口座</span></span> 
- <span data-ttu-id="86dd5-2658">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="86dd5-2659">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="86dd5-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="86dd5-2660">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="86dd5-2661">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="86dd5-2662">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="86dd5-2663">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="86dd5-2664">口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2664">口座番号</span></span> 
- <span data-ttu-id="86dd5-2665">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2665">口座番号＃</span></span> 
- <span data-ttu-id="86dd5-2666">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="86dd5-2667">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="86dd5-2668">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="86dd5-2669">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="86dd5-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="86dd5-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="86dd5-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="86dd5-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="86dd5-2672">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2673">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2673">Format</span></span>

<span data-ttu-id="86dd5-2674">12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2675">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2675">Pattern</span></span>

<span data-ttu-id="86dd5-2676">12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2677">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2677">Checksum</span></span>

<span data-ttu-id="86dd5-2678">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2679">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2679">Definition</span></span>

<span data-ttu-id="86dd5-2680">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2681">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2682">找不到來自 Keyword_jp_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2683">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="86dd5-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="86dd5-2685">dl #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2685">dl#</span></span> 
- <span data-ttu-id="86dd5-2686">DL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2686">DL＃</span></span> 
- <span data-ttu-id="86dd5-2687">dl #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2687">dls#</span></span> 
- <span data-ttu-id="86dd5-2688">DL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2688">DLS＃</span></span> 
- <span data-ttu-id="86dd5-2689">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2689">driver license</span></span> 
- <span data-ttu-id="86dd5-2690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2690">driver licenses</span></span> 
- <span data-ttu-id="86dd5-2691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2691">drivers license</span></span> 
- <span data-ttu-id="86dd5-2692">駕照</span><span class="sxs-lookup"><span data-stu-id="86dd5-2692">driver's license</span></span> 
- <span data-ttu-id="86dd5-2693">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2693">drivers licenses</span></span> 
- <span data-ttu-id="86dd5-2694">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2694">driver's licenses</span></span> 
- <span data-ttu-id="86dd5-2695">driving 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-2695">driving licence</span></span> 
- <span data-ttu-id="86dd5-2696">lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2696">lic#</span></span> 
- <span data-ttu-id="86dd5-2697">LIC #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2697">LIC＃</span></span> 
- <span data-ttu-id="86dd5-2698">lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2698">lics#</span></span> 
- <span data-ttu-id="86dd5-2699">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2699">state id</span></span> 
- <span data-ttu-id="86dd5-2700">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2700">state identification</span></span> 
- <span data-ttu-id="86dd5-2701">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2701">state identification number</span></span> 
- <span data-ttu-id="86dd5-2702">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2702">低所得国＃</span></span> 
- <span data-ttu-id="86dd5-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2703">免許証</span></span> 
- <span data-ttu-id="86dd5-2704">状態ID</span><span class="sxs-lookup"><span data-stu-id="86dd5-2704">状態ID</span></span>
- <span data-ttu-id="86dd5-2705">状態の識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-2705">状態の識別</span></span> 
- <span data-ttu-id="86dd5-2706">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2706">状態の識別番号</span></span> 
- <span data-ttu-id="86dd5-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="86dd5-2707">運転免許</span></span> 
- <span data-ttu-id="86dd5-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="86dd5-2708">運転免許証</span></span> 
- <span data-ttu-id="86dd5-2709">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="86dd5-2710">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2711">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2711">Format</span></span>

<span data-ttu-id="86dd5-2712">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2713">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2713">Pattern</span></span>

<span data-ttu-id="86dd5-2714">兩個字母 （不區分大小寫） 尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2715">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2715">Checksum</span></span>

<span data-ttu-id="86dd5-2716">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2717">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2717">Definition</span></span>

<span data-ttu-id="86dd5-2718">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2719">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2720">找不到來自 Keyword_jp_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2721">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="86dd5-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="86dd5-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="86dd5-2723">パスポート</span></span> 
- <span data-ttu-id="86dd5-2724">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2724">パスポート番号</span></span> 
- <span data-ttu-id="86dd5-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="86dd5-2725">パスポートのNum</span></span> 
- <span data-ttu-id="86dd5-2726">パスポート #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="86dd5-2727">日本常駐居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2728">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2728">Format</span></span>

<span data-ttu-id="86dd5-2729">11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2730">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2730">Pattern</span></span>

<span data-ttu-id="86dd5-2731">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2732">Checksum</span></span>

<span data-ttu-id="86dd5-2733">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2734">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2734">Definition</span></span>

<span data-ttu-id="86dd5-2735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2736">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2737">找不到來自 Keyword_jp_resident_registration_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="86dd5-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="86dd5-2740">常駐居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2740">Resident Registration Number</span></span>
- <span data-ttu-id="86dd5-2741">駐留註冊數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-2741">Resident Register Number</span></span> 
- <span data-ttu-id="86dd5-2742">居民基本登錄數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="86dd5-2743">居民登記 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="86dd5-2744">駐留註冊 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2744">Resident Register No.</span></span> 
- <span data-ttu-id="86dd5-2745">居民基本登錄 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="86dd5-2746">基本居民註冊 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="86dd5-2747">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="86dd5-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="86dd5-2748">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="86dd5-2749">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="86dd5-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="86dd5-2750">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="86dd5-2751">日本社會保險號碼 (SIN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2752">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2752">Format</span></span>

<span data-ttu-id="86dd5-2753">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2754">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2754">Pattern</span></span>

<span data-ttu-id="86dd5-2755">7-12 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2755">7-12 digits:</span></span>
- <span data-ttu-id="86dd5-2756">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2756">Four digits</span></span> 
- <span data-ttu-id="86dd5-2757">連字號 （選用）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="86dd5-2758">六位數或</span><span class="sxs-lookup"><span data-stu-id="86dd5-2758">Six digits OR</span></span>
- <span data-ttu-id="86dd5-2759">7-12 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2760">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2760">Checksum</span></span>

<span data-ttu-id="86dd5-2761">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2762">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2762">Definition</span></span>

<span data-ttu-id="86dd5-2763">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2764">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2765">找不到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="86dd5-2766">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2767">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2768">找不到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2769">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="86dd5-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="86dd5-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="86dd5-2771">社會保險 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="86dd5-2772">社會保險 Num</span><span class="sxs-lookup"><span data-stu-id="86dd5-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="86dd5-2773">社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="86dd5-2774">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="86dd5-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="86dd5-2775">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="86dd5-2776">日文居住地證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2777">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2777">Format</span></span>

<span data-ttu-id="86dd5-2778">12 個字母和數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2779">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2779">Pattern</span></span>

<span data-ttu-id="86dd5-2780">12 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2780">12 letters and digits:</span></span>
- <span data-ttu-id="86dd5-2781">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="86dd5-2782">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2782">Eight digits</span></span> 
- <span data-ttu-id="86dd5-2783">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2784">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2784">Checksum</span></span>

<span data-ttu-id="86dd5-2785">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2786">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2786">Definition</span></span>

<span data-ttu-id="86dd5-2787">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2788">規則運算式 Regex_jp_residence_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2789">找不到來自 Keyword_jp_residence_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2790">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="86dd5-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="86dd5-2792">居住地證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2792">Residence card number</span></span>
- <span data-ttu-id="86dd5-2793">居住地卡否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2793">Residence card no</span></span>
- <span data-ttu-id="86dd5-2794">居住地卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-2794">Residence card #</span></span>
- <span data-ttu-id="86dd5-2795">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="86dd5-2796">馬來西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2797">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2797">Format</span></span>

<span data-ttu-id="86dd5-2798">12 位數包含選擇性連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2799">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2799">Pattern</span></span>

<span data-ttu-id="86dd5-2800">12 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2800">12 digits:</span></span>
- <span data-ttu-id="86dd5-2801">YYMMDD 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-2802">一個破折號 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2802">A dash (optional)</span></span> 
- <span data-ttu-id="86dd5-2803">雙字母的出生地代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="86dd5-2804">一個破折號 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2804">A dash (optional)</span></span> 
- <span data-ttu-id="86dd5-2805">三個隨機的數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2805">Three random digits</span></span> 
- <span data-ttu-id="86dd5-2806">一位數性別代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2807">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2807">Checksum</span></span>

<span data-ttu-id="86dd5-2808">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2809">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2809">Definition</span></span>

<span data-ttu-id="86dd5-2810">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2811">規則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2812">找不到來自 Keyword_malaysia_id_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2813">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="86dd5-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="86dd5-2815">數位應用程式卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-2815">digital application card</span></span>
- <span data-ttu-id="86dd5-2816">我 /c</span><span class="sxs-lookup"><span data-stu-id="86dd5-2816">i/c</span></span>
- <span data-ttu-id="86dd5-2817">我 /c 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-2817">i/c no</span></span>
- <span data-ttu-id="86dd5-2818">ic</span><span class="sxs-lookup"><span data-stu-id="86dd5-2818">ic</span></span>
- <span data-ttu-id="86dd5-2819">ic 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-2819">ic no</span></span>
- <span data-ttu-id="86dd5-2820">證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2820">id card</span></span>
- <span data-ttu-id="86dd5-2821">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-2821">identification Card</span></span>
- <span data-ttu-id="86dd5-2822">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2822">identity card</span></span>
- <span data-ttu-id="86dd5-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="86dd5-2823">k/p</span></span>
- <span data-ttu-id="86dd5-2824">k/p 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-2824">k/p no</span></span>
- <span data-ttu-id="86dd5-2825">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="86dd5-2825">kad akuan diri</span></span>
- <span data-ttu-id="86dd5-2826">kad aplikasi 數位</span><span class="sxs-lookup"><span data-stu-id="86dd5-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="86dd5-2827">kad pengenalan 馬來西亞</span><span class="sxs-lookup"><span data-stu-id="86dd5-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="86dd5-2828">kp</span><span class="sxs-lookup"><span data-stu-id="86dd5-2828">kp</span></span>
- <span data-ttu-id="86dd5-2829">kp 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-2829">kp no</span></span>
- <span data-ttu-id="86dd5-2830">mykad</span><span class="sxs-lookup"><span data-stu-id="86dd5-2830">mykad</span></span>
- <span data-ttu-id="86dd5-2831">mykas</span><span class="sxs-lookup"><span data-stu-id="86dd5-2831">mykas</span></span>
- <span data-ttu-id="86dd5-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="86dd5-2832">mykid</span></span>
- <span data-ttu-id="86dd5-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="86dd5-2833">mypr</span></span>
- <span data-ttu-id="86dd5-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="86dd5-2834">mytentera</span></span>
- <span data-ttu-id="86dd5-2835">馬來西亞身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2835">malaysia identity card</span></span>
- <span data-ttu-id="86dd5-2836">馬來西亞身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2836">malaysian identity card</span></span>
- <span data-ttu-id="86dd5-2837">nric</span><span class="sxs-lookup"><span data-stu-id="86dd5-2837">nric</span></span>
- <span data-ttu-id="86dd5-2838">個人識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="86dd5-2839">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2840">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2840">Format</span></span>

<span data-ttu-id="86dd5-2841">8-9 位數包含選擇性空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2842">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2842">Pattern</span></span>

<span data-ttu-id="86dd5-2843">8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2843">8-9 digits:</span></span>
- <span data-ttu-id="86dd5-2844">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2844">Three digits</span></span> 
- <span data-ttu-id="86dd5-2845">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2845">A space (optional)</span></span> 
- <span data-ttu-id="86dd5-2846">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2846">Three digits</span></span> 
- <span data-ttu-id="86dd5-2847">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="86dd5-2847">A space (optional)</span></span> 
- <span data-ttu-id="86dd5-2848">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2849">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2849">Checksum</span></span>

<span data-ttu-id="86dd5-2850">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2851">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2851">Definition</span></span>

<span data-ttu-id="86dd5-2852">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2853">函數 Func_netherlands_bsn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2854">找不到來自 Keyword_netherlands_bsn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="86dd5-2855">函數 Func_eu_date2 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="86dd5-2856">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2857">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="86dd5-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="86dd5-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="86dd5-2859">公民健保號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2859">Citizen service number</span></span> 
- <span data-ttu-id="86dd5-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="86dd5-2860">BSN</span></span> 
- <span data-ttu-id="86dd5-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="86dd5-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2862">Sofinummer</span></span> 
- <span data-ttu-id="86dd5-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="86dd5-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="86dd5-2865">紐西蘭衛生部編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2866">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2866">Format</span></span>

<span data-ttu-id="86dd5-2867">三個字母、 一個空格 （選用） 和四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2868">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2868">Pattern</span></span>

<span data-ttu-id="86dd5-2869">三個字母 （不區分大小寫） 的空間 （選用） 四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2870">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2870">Checksum</span></span>

<span data-ttu-id="86dd5-2871">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2872">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2872">Definition</span></span>

<span data-ttu-id="86dd5-2873">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2874">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2875">找不到來自 Keyword_nz_terms 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="86dd5-2876">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2876">The checksum passes.</span></span>

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

<span data-ttu-id="86dd5-2877">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2877">Keywords</span></span>

<span data-ttu-id="86dd5-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="86dd5-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="86dd5-2879">NHI</span><span class="sxs-lookup"><span data-stu-id="86dd5-2879">NHI</span></span> 
- <span data-ttu-id="86dd5-2880">JPRatingExplicitAllowed</span><span class="sxs-lookup"><span data-stu-id="86dd5-2880">New Zealand</span></span> 
- <span data-ttu-id="86dd5-2881">健康情況</span><span class="sxs-lookup"><span data-stu-id="86dd5-2881">Health</span></span> 
- <span data-ttu-id="86dd5-2882">處理方式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="86dd5-2883">挪威識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2884">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2884">Format</span></span>

<span data-ttu-id="86dd5-2885">11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2886">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2886">Pattern</span></span>

<span data-ttu-id="86dd5-2887">11 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2887">11 digits:</span></span>
- <span data-ttu-id="86dd5-2888">DDMMYY 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-2889">三位數個人識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="86dd5-2890">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2891">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2891">Checksum</span></span>

<span data-ttu-id="86dd5-2892">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2893">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2893">Definition</span></span>

<span data-ttu-id="86dd5-2894">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2895">函數 Func_norway_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2896">找不到來自 Keyword_norway_id_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="86dd5-2897">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2897">The checksum passes.</span></span>
- <span data-ttu-id="86dd5-2898">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2899">函數 Func_norway_id_numbe 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2900">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2901">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="86dd5-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="86dd5-2903">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2903">Personal identification number</span></span>
- <span data-ttu-id="86dd5-2904">挪威文識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="86dd5-2905">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2905">ID Number</span></span>
- <span data-ttu-id="86dd5-2906">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-2906">Identification</span></span>
- <span data-ttu-id="86dd5-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2907">Personnummer</span></span>
- <span data-ttu-id="86dd5-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="86dd5-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="86dd5-2909">菲律賓統一多用途 ID 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2910">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2910">Format</span></span>

<span data-ttu-id="86dd5-2911">以連字號分隔的 12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2912">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2912">Pattern</span></span>

<span data-ttu-id="86dd5-2913">12 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2913">12 digits:</span></span>
- <span data-ttu-id="86dd5-2914">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2914">Four digits</span></span> 
- <span data-ttu-id="86dd5-2915">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2915">A hyphen</span></span> 
- <span data-ttu-id="86dd5-2916">七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2916">Seven digits</span></span> 
- <span data-ttu-id="86dd5-2917">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-2917">A hyphen</span></span> 
- <span data-ttu-id="86dd5-2918">一位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2919">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2919">Checksum</span></span>

<span data-ttu-id="86dd5-2920">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2921">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2921">Definition</span></span>

<span data-ttu-id="86dd5-2922">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2923">規則運算式 Regex_philippines_unified_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2924">找不到來自 Keyword_philippines_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2925">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="86dd5-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="86dd5-2927">統一多用途識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="86dd5-2928">UMID</span><span class="sxs-lookup"><span data-stu-id="86dd5-2928">UMID</span></span> 
- <span data-ttu-id="86dd5-2929">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2929">Identity Card</span></span> 
- <span data-ttu-id="86dd5-2930">Pinag isang 多 Layunin 識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="86dd5-2931">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2932">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2932">Format</span></span>

<span data-ttu-id="86dd5-2933">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2934">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2934">Pattern</span></span>

<span data-ttu-id="86dd5-2935">三個字母 （不區分大小寫） 尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2936">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2936">Checksum</span></span>

<span data-ttu-id="86dd5-2937">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2938">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2938">Definition</span></span>

<span data-ttu-id="86dd5-2939">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元： 函數 Func_polish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="86dd5-2940">找不到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="86dd5-2941">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="86dd5-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="86dd5-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="86dd5-2944">Dowód osobisty</span></span>
- <span data-ttu-id="86dd5-2945">數目 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="86dd5-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="86dd5-2946">Nazwa 我數目 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="86dd5-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="86dd5-2947">Nazwa 我編號 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="86dd5-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="86dd5-2948">Nazwa 我編號 dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="86dd5-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="86dd5-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="86dd5-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="86dd5-2950">dow。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2950">dow.</span></span> <span data-ttu-id="86dd5-2951">os。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="86dd5-2952">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="86dd5-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2953">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2953">Format</span></span>

<span data-ttu-id="86dd5-2954">11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2955">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2955">Pattern</span></span>

<span data-ttu-id="86dd5-2956">11 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2957">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2957">Checksum</span></span>

<span data-ttu-id="86dd5-2958">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2959">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2959">Definition</span></span>

<span data-ttu-id="86dd5-2960">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2961">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2962">找不到來自 Keyword_pesel_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="86dd5-2963">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2964">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="86dd5-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="86dd5-2966">編號 PESEL</span><span class="sxs-lookup"><span data-stu-id="86dd5-2966">Nr PESEL</span></span>
- <span data-ttu-id="86dd5-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="86dd5-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="86dd5-2968">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="86dd5-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2969">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2969">Format</span></span>

<span data-ttu-id="86dd5-2970">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2971">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2971">Pattern</span></span>

<span data-ttu-id="86dd5-2972">兩個字母 （不區分大小寫） 尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2973">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2973">Checksum</span></span>

<span data-ttu-id="86dd5-2974">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2975">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2975">Definition</span></span>

<span data-ttu-id="86dd5-2976">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2977">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2978">找不到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="86dd5-2979">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-2980">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="86dd5-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="86dd5-2982">數目 paszportu</span><span class="sxs-lookup"><span data-stu-id="86dd5-2982">Numer paszportu</span></span>
- <span data-ttu-id="86dd5-2983">編號。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2983">Nr.</span></span> <span data-ttu-id="86dd5-2984">Paszportu</span><span class="sxs-lookup"><span data-stu-id="86dd5-2984">Paszportu</span></span>
- <span data-ttu-id="86dd5-2985">Paszport</span><span class="sxs-lookup"><span data-stu-id="86dd5-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="86dd5-2986">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-2987">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2987">Format</span></span>

<span data-ttu-id="86dd5-2988">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-2989">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-2989">Pattern</span></span>

<span data-ttu-id="86dd5-2990">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-2991">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-2991">Checksum</span></span>

<span data-ttu-id="86dd5-2992">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-2993">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-2993">Definition</span></span>

<span data-ttu-id="86dd5-2994">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-2995">規則運算式 Regex_portugal_citizen_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-2996">找不到來自 Keyword_portugal_citizen_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-2997">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="86dd5-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="86dd5-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="86dd5-2999">公民證</span><span class="sxs-lookup"><span data-stu-id="86dd5-2999">Citizen Card</span></span>
- <span data-ttu-id="86dd5-3000">國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3000">National ID Card</span></span>
- <span data-ttu-id="86dd5-3001">副本</span><span class="sxs-lookup"><span data-stu-id="86dd5-3001">CC</span></span>
- <span data-ttu-id="86dd5-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="86dd5-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="86dd5-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="86dd5-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="86dd5-3004">沙烏地阿拉伯國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3005">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3005">Format</span></span>

<span data-ttu-id="86dd5-3006">10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3007">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3007">Pattern</span></span>

<span data-ttu-id="86dd5-3008">10 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3009">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3009">Checksum</span></span>

<span data-ttu-id="86dd5-3010">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3011">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3011">Definition</span></span>

<span data-ttu-id="86dd5-3012">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3013">規則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3014">找不到來自 Keyword_saudi_arabia_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3015">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="86dd5-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="86dd5-3017">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-3017">Identification Card</span></span> 
- <span data-ttu-id="86dd5-3018">我介面卡數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3018">I card number</span></span> 
- <span data-ttu-id="86dd5-3019">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3019">ID number</span></span> 
- <span data-ttu-id="86dd5-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="86dd5-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="86dd5-3021">新加坡國民登記身分證 (NRIC) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3022">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3022">Format</span></span>

<span data-ttu-id="86dd5-3023">九個字母和數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3024">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3024">Pattern</span></span>

- <span data-ttu-id="86dd5-3025">九個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="86dd5-3026">字母"F"、"G"、"S"或"T"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-3027">七位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3027">Seven digits</span></span> 
- <span data-ttu-id="86dd5-3028">一個字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3029">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3029">Checksum</span></span>

<span data-ttu-id="86dd5-3030">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3031">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3031">Definition</span></span>

<span data-ttu-id="86dd5-3032">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3033">規則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3034">找不到來自 Keyword_singapore_nric 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="86dd5-3035">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3035">The checksum passes.</span></span>

<span data-ttu-id="86dd5-3036">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3037">規則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3038">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3039">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="86dd5-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="86dd5-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="86dd5-3041">國民登記身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="86dd5-3042">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3042">Identity Card Number</span></span> 
- <span data-ttu-id="86dd5-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="86dd5-3043">NRIC</span></span> 
- <span data-ttu-id="86dd5-3044">IC</span><span class="sxs-lookup"><span data-stu-id="86dd5-3044">IC</span></span> 
- <span data-ttu-id="86dd5-3045">外部識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="86dd5-3046">FIN</span><span class="sxs-lookup"><span data-stu-id="86dd5-3046">FIN</span></span> 
- <span data-ttu-id="86dd5-3047">身份证</span><span class="sxs-lookup"><span data-stu-id="86dd5-3047">身份证</span></span> 
- <span data-ttu-id="86dd5-3048">身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="86dd5-3049">南非識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3050">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3050">Format</span></span>

<span data-ttu-id="86dd5-3051">可以包含空格的 13 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3052">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3052">Pattern</span></span>

<span data-ttu-id="86dd5-3053">13 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3053">13 digits:</span></span>
- <span data-ttu-id="86dd5-3054">YYMMDD 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-3055">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3055">Four digits</span></span> 
- <span data-ttu-id="86dd5-3056">一位數公民指標</span><span class="sxs-lookup"><span data-stu-id="86dd5-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="86dd5-3057">數字"8"或"9"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="86dd5-3058">一位數總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3059">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3059">Checksum</span></span>

<span data-ttu-id="86dd5-3060">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3061">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3061">Definition</span></span>

<span data-ttu-id="86dd5-3062">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3063">函數 Func_south_africa_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3064">找不到來自 Keyword_south_africa_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="86dd5-3065">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3066">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="86dd5-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="86dd5-3068">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3068">Identity card</span></span>
- <span data-ttu-id="86dd5-3069">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3069">ID</span></span>
- <span data-ttu-id="86dd5-3070">識別</span><span class="sxs-lookup"><span data-stu-id="86dd5-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="86dd5-3071">南韓居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3072">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3072">Format</span></span>

<span data-ttu-id="86dd5-3073">13 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3074">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3074">Pattern</span></span>

<span data-ttu-id="86dd5-3075">13 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3075">13 digits:</span></span>
- <span data-ttu-id="86dd5-3076">YYMMDD 格式的六位數的出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="86dd5-3077">連字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3077">A hyphen</span></span> 
- <span data-ttu-id="86dd5-3078">由世紀與性別判定的一位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="86dd5-3079">四位數出生地區碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="86dd5-3080">一位數，用來區分其前幾碼皆相同的人員</span><span class="sxs-lookup"><span data-stu-id="86dd5-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="86dd5-3081">檢查碼。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3082">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3082">Checksum</span></span>

<span data-ttu-id="86dd5-3083">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3084">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3084">Definition</span></span>

<span data-ttu-id="86dd5-3085">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3086">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3087">找不到來自 Keyword_south_korea_resident_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="86dd5-3088">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3088">The checksum passes.</span></span>

<span data-ttu-id="86dd5-3089">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3090">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3091">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3092">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="86dd5-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="86dd5-3094">國民身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3094">National ID card</span></span> 
- <span data-ttu-id="86dd5-3095">公民登記號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="86dd5-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="86dd5-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="86dd5-3097">RRN</span><span class="sxs-lookup"><span data-stu-id="86dd5-3097">RRN</span></span> 
- <span data-ttu-id="86dd5-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="86dd5-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="86dd5-3099">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3100">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3100">Format</span></span>

<span data-ttu-id="86dd5-3101">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3102">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3102">Pattern</span></span>

<span data-ttu-id="86dd5-3103">11-12 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3103">11-12 digits:</span></span>
- <span data-ttu-id="86dd5-3104">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3104">Two digits</span></span> 
- <span data-ttu-id="86dd5-3105">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="86dd5-3106">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3106">7-8 digits</span></span> 
- <span data-ttu-id="86dd5-3107">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="86dd5-3108">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3109">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3109">Checksum</span></span>

<span data-ttu-id="86dd5-3110">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3111">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3111">Definition</span></span>

<span data-ttu-id="86dd5-3112">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3113">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3114">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3115">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3115">Keywords</span></span>

<span data-ttu-id="86dd5-3116">無</span><span class="sxs-lookup"><span data-stu-id="86dd5-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="86dd5-3117">SQL Server 連線字串</span><span class="sxs-lookup"><span data-stu-id="86dd5-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3118">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3118">Format</span></span>

<span data-ttu-id="86dd5-3119">字串 「 使用者 Id 」、 「 使用者 ID 」、 「 uid 」 或 「 使用者識別碼 」 後面跟著字元和下列模式中所述的字串。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3120">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3120">Pattern</span></span>

- <span data-ttu-id="86dd5-3121">字串 「 使用者 Id 」、 「 使用者 ID 」、 「 uid 」 或者 「 UserId 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="86dd5-3122">1-200 較低的大寫字母、 數字、 符號、 特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="86dd5-3123">將字串 「 密碼 」 或 「 pwd 」 不的小寫字母前面 「 pwd 」</span><span class="sxs-lookup"><span data-stu-id="86dd5-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="86dd5-3124">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3124">An equal sign (=)</span></span>
- <span data-ttu-id="86dd5-3125">任何不錢幣符號 （$）、 百分比符號 （%），大於符號 (>) 符號字元 (@)、 引號 （"）、 分號 （;）、 左大括弧 ([]) 或左大括弧 （{}）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="86dd5-3126">不是以分號 （;） 的 7-128 個字元的任何組合反斜線 （/） 或雙引號 （"）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="86dd5-3127">分號 （;）或引號 （"）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3128">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3128">Checksum</span></span>

<span data-ttu-id="86dd5-3129">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3130">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3130">Definition</span></span>

<span data-ttu-id="86dd5-3131">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3132">規則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3133">從 CEP_GlobalFilter 關鍵字**不**找到。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="86dd5-3134">規則運算式 CEP_PasswordPlaceHolder**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3135">規則運算式 CEP_CommonExampleKeywords**不**尋找符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3136">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="86dd5-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="86dd5-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="86dd5-3138">某些密碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3138">some-password</span></span>
- <span data-ttu-id="86dd5-3139">somepassword</span><span class="sxs-lookup"><span data-stu-id="86dd5-3139">somepassword</span></span>
- <span data-ttu-id="86dd5-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="86dd5-3140">secretPassword</span></span>
- <span data-ttu-id="86dd5-3141">範例</span><span class="sxs-lookup"><span data-stu-id="86dd5-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="86dd5-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="86dd5-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="86dd5-3143">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-3144">Password 或 pwd 後面接著 0-2 空格，等號 （=）、 0-2 空格，並星號 （\*）-或-</span><span class="sxs-lookup"><span data-stu-id="86dd5-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="86dd5-3145">Password 或 pwd 後面加上：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="86dd5-3146">等號 （=）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="86dd5-3147">小於符號 (<)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="86dd5-3148">1-200 的字元上方-或小寫字母、 數字、 星號 （\*）、 連字號 （-）、 底線 (_) 或空白字元的任意組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="86dd5-3149">大於符號 (>)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="86dd5-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="86dd5-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="86dd5-3151">（請注意技術上而言，此敏感資訊類型會指出這些關鍵字使用規則運算式，而不是關鍵字的清單）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="86dd5-3152">contoso</span><span class="sxs-lookup"><span data-stu-id="86dd5-3152">contoso</span></span>
- <span data-ttu-id="86dd5-3153">fabrikam</span><span class="sxs-lookup"><span data-stu-id="86dd5-3153">fabrikam</span></span>
- <span data-ttu-id="86dd5-3154">northwind</span><span class="sxs-lookup"><span data-stu-id="86dd5-3154">northwind</span></span>
- <span data-ttu-id="86dd5-3155">沙箱化</span><span class="sxs-lookup"><span data-stu-id="86dd5-3155">sandbox</span></span>
- <span data-ttu-id="86dd5-3156">onebox</span><span class="sxs-lookup"><span data-stu-id="86dd5-3156">onebox</span></span>
- <span data-ttu-id="86dd5-3157">localhost</span><span class="sxs-lookup"><span data-stu-id="86dd5-3157">localhost</span></span>
- <span data-ttu-id="86dd5-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="86dd5-3158">127.0.0.1</span></span>
- <span data-ttu-id="86dd5-3159">testacs。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-3160">com</span><span class="sxs-lookup"><span data-stu-id="86dd5-3160">com</span></span>
- <span data-ttu-id="86dd5-3161">s int。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="86dd5-3162">net</span><span class="sxs-lookup"><span data-stu-id="86dd5-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="86dd5-3163">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3164">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3164">Format</span></span>

<span data-ttu-id="86dd5-3165">10 或 12 位數和一個選用分隔符號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3166">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3166">Pattern</span></span>

<span data-ttu-id="86dd5-3167">10 或 12 位數和一個選用分隔符號：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="86dd5-3168">2-4 位數 （選用）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="86dd5-3169">格式 YYMMDD 的六位數，日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="86dd5-3170">分隔符號"-"或"+"（選用），再加上</span><span class="sxs-lookup"><span data-stu-id="86dd5-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="86dd5-3171">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3172">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3172">Checksum</span></span>

<span data-ttu-id="86dd5-3173">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3174">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3174">Definition</span></span>

<span data-ttu-id="86dd5-3175">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3176">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3177">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3178">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3178">Keywords</span></span>

<span data-ttu-id="86dd5-3179">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="86dd5-3180">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3181">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3181">Format</span></span>

<span data-ttu-id="86dd5-3182">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3183">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3183">Pattern</span></span>

<span data-ttu-id="86dd5-3184">八個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3185">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3185">Checksum</span></span>

<span data-ttu-id="86dd5-3186">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3187">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3187">Definition</span></span>

<span data-ttu-id="86dd5-3188">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3189">規則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3190">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3190">One of the following is true:</span></span>
    - <span data-ttu-id="86dd5-3191">找不到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="86dd5-3192">找不到來自 Keyword_sweden_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3193">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="86dd5-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="86dd5-3195">visa 需求</span><span class="sxs-lookup"><span data-stu-id="86dd5-3195">visa requirements</span></span> 
- <span data-ttu-id="86dd5-3196">外星註冊卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="86dd5-3197">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3197">Schengen visas</span></span> 
- <span data-ttu-id="86dd5-3198">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="86dd5-3198">Schengen visa</span></span> 
- <span data-ttu-id="86dd5-3199">Visa 處理</span><span class="sxs-lookup"><span data-stu-id="86dd5-3199">Visa Processing</span></span> 
- <span data-ttu-id="86dd5-3200">Visa 類型</span><span class="sxs-lookup"><span data-stu-id="86dd5-3200">Visa Type</span></span> 
- <span data-ttu-id="86dd5-3201">單一項目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3201">Single Entry</span></span> 
- <span data-ttu-id="86dd5-3202">多個項目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3202">Multiple Entry</span></span> 
- <span data-ttu-id="86dd5-3203">G3 處理費用</span><span class="sxs-lookup"><span data-stu-id="86dd5-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="86dd5-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-3204">Keyword_passport</span></span>

- <span data-ttu-id="86dd5-3205">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3205">Passport Number</span></span> 
- <span data-ttu-id="86dd5-3206">Passport 否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3206">Passport No</span></span> 
- <span data-ttu-id="86dd5-3207">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3207">Passport #</span></span> 
- <span data-ttu-id="86dd5-3208">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3208">Passport#</span></span> 
- <span data-ttu-id="86dd5-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="86dd5-3209">PassportID</span></span> 
- <span data-ttu-id="86dd5-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="86dd5-3210">Passportno</span></span> 
- <span data-ttu-id="86dd5-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-3211">passportnumber</span></span> 
- <span data-ttu-id="86dd5-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="86dd5-3212">パスポート</span></span> 
- <span data-ttu-id="86dd5-3213">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-3213">パスポート番号</span></span> 
- <span data-ttu-id="86dd5-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="86dd5-3214">パスポートのNum</span></span> 
- <span data-ttu-id="86dd5-3215">パスポート #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3215">パスポート＃</span></span> 
- <span data-ttu-id="86dd5-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="86dd5-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="86dd5-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="86dd5-3217">Passeport n °</span></span> 
- <span data-ttu-id="86dd5-3218">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="86dd5-3218">Passeport Non</span></span> 
- <span data-ttu-id="86dd5-3219">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3219">Passeport #</span></span> 
- <span data-ttu-id="86dd5-3220">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3220">Passeport#</span></span> 
- <span data-ttu-id="86dd5-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="86dd5-3221">PasseportNon</span></span> 
- <span data-ttu-id="86dd5-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="86dd5-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="86dd5-3223">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3224">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3224">Format</span></span>

<span data-ttu-id="86dd5-3225">四個字母後尾隨 5-31 個字母或數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3226">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3226">Pattern</span></span>

<span data-ttu-id="86dd5-3227">四個字母後尾隨 5-31 個字母或數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="86dd5-3228">四字母銀行代碼 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-3229">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-3229">An optional space</span></span> 
- <span data-ttu-id="86dd5-3230">4-28 個字母或數字 (基本銀行帳戶號碼 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="86dd5-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="86dd5-3231">一個選用空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-3231">An optional space</span></span> 
- <span data-ttu-id="86dd5-3232">1-3 個字母或數字 （BBAN 的其餘部分）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3233">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3233">Checksum</span></span>

<span data-ttu-id="86dd5-3234">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3235">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3235">Definition</span></span>

<span data-ttu-id="86dd5-3236">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3237">規則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3238">找不到來自 Keyword_swift 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3239">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="86dd5-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="86dd5-3240">Keyword_swift</span></span>

- <span data-ttu-id="86dd5-3241">國際標準 9362 組織</span><span class="sxs-lookup"><span data-stu-id="86dd5-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="86dd5-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="86dd5-3242">iso 9362</span></span> 
- <span data-ttu-id="86dd5-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="86dd5-3243">iso9362</span></span> 
- <span data-ttu-id="86dd5-3244">swift\#</span><span class="sxs-lookup"><span data-stu-id="86dd5-3244">swift\#</span></span> 
- <span data-ttu-id="86dd5-3245">swiftcode</span><span class="sxs-lookup"><span data-stu-id="86dd5-3245">swiftcode</span></span> 
- <span data-ttu-id="86dd5-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-3246">swiftnumber</span></span> 
- <span data-ttu-id="86dd5-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="86dd5-3248">swift 代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3248">swift code</span></span> 
- <span data-ttu-id="86dd5-3249">swift 號碼 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3249">swift number #</span></span> 
- <span data-ttu-id="86dd5-3250">swift 路由號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3250">swift routing number</span></span> 
- <span data-ttu-id="86dd5-3251">bic 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3251">bic number</span></span> 
- <span data-ttu-id="86dd5-3252">bic 程式碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3252">bic code</span></span> 
- <span data-ttu-id="86dd5-3253">bic\#</span><span class="sxs-lookup"><span data-stu-id="86dd5-3253">bic \#</span></span> 
- <span data-ttu-id="86dd5-3254">bic\#</span><span class="sxs-lookup"><span data-stu-id="86dd5-3254">bic\#</span></span> 
- <span data-ttu-id="86dd5-3255">銀行識別碼程式碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3255">bank identifier code</span></span> 
- <span data-ttu-id="86dd5-3256">標準化9362</span><span class="sxs-lookup"><span data-stu-id="86dd5-3256">標準化9362</span></span> 
- <span data-ttu-id="86dd5-3257">迅速 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3257">迅速＃</span></span> 
- <span data-ttu-id="86dd5-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="86dd5-3258">SWIFTコード</span></span> 
- <span data-ttu-id="86dd5-3259">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-3259">SWIFT番号</span></span> 
- <span data-ttu-id="86dd5-3260">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="86dd5-3261">BIC番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-3261">BIC番号</span></span> 
- <span data-ttu-id="86dd5-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="86dd5-3262">BICコード</span></span> 
- <span data-ttu-id="86dd5-3263">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="86dd5-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="86dd5-3264">組織 internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="86dd5-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="86dd5-3265">rapide\#</span><span class="sxs-lookup"><span data-stu-id="86dd5-3265">rapide \#</span></span> 
- <span data-ttu-id="86dd5-3266">SWIFT 代碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3266">code SWIFT</span></span> 
- <span data-ttu-id="86dd5-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="86dd5-3267">le numéro de swift</span></span> 
- <span data-ttu-id="86dd5-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="86dd5-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="86dd5-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="86dd5-3269">le numéro BIC</span></span> 
- <span data-ttu-id="86dd5-3270">\#BIC</span><span class="sxs-lookup"><span data-stu-id="86dd5-3270">\# BIC</span></span> 
- <span data-ttu-id="86dd5-3271">程式碼 identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="86dd5-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="86dd5-3272">台灣國家識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3273">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3273">Format</span></span>

<span data-ttu-id="86dd5-3274">一個字母 （英文） 尾隨九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3275">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3275">Pattern</span></span>

<span data-ttu-id="86dd5-3276">一個字母 （英文） 尾隨九位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="86dd5-3277">一個字母 （以英文、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-3278">數字"1"或"2"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="86dd5-3279">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3280">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3280">Checksum</span></span>

<span data-ttu-id="86dd5-3281">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3282">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3282">Definition</span></span>

<span data-ttu-id="86dd5-3283">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3284">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3285">找不到來自 Keyword_taiwanese_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="86dd5-3286">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3287">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="86dd5-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="86dd5-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="86dd5-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3289">身份證字號</span></span> 
- <span data-ttu-id="86dd5-3290">身份證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3290">身份證</span></span> 
- <span data-ttu-id="86dd5-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3291">身份證號碼</span></span> 
- <span data-ttu-id="86dd5-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3292">身份證號</span></span> 
- <span data-ttu-id="86dd5-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3293">身分證字號</span></span> 
- <span data-ttu-id="86dd5-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3294">身分證</span></span> 
- <span data-ttu-id="86dd5-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3295">身分證號碼</span></span> 
- <span data-ttu-id="86dd5-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3296">身份證號</span></span> 
- <span data-ttu-id="86dd5-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3297">身分證統一編號</span></span> 
- <span data-ttu-id="86dd5-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="86dd5-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="86dd5-3299">簽名</span></span> 
- <span data-ttu-id="86dd5-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="86dd5-3300">蓋章</span></span> 
- <span data-ttu-id="86dd5-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="86dd5-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="86dd5-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="86dd5-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="86dd5-3303">台灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3304">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3304">Format</span></span>

- <span data-ttu-id="86dd5-3305">生物識別護照號碼： 九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="86dd5-3306">非生物識別護照號碼： 九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3307">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3307">Pattern</span></span>
<span data-ttu-id="86dd5-3308">生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3308">Biometric passport number:</span></span>
- <span data-ttu-id="86dd5-3309">數字"3"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3309">The digit "3"</span></span> 
- <span data-ttu-id="86dd5-3310">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3310">Eight digits</span></span>

<span data-ttu-id="86dd5-3311">非生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="86dd5-3312">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3313">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3313">Checksum</span></span>

<span data-ttu-id="86dd5-3314">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3315">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3315">Definition</span></span>

<span data-ttu-id="86dd5-3316">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3317">規則運算式 Regex_taiwan_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3318">找不到來自 Keyword_taiwan_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3319">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="86dd5-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="86dd5-3321">中華民國護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3321">ROC passport number</span></span> 
- <span data-ttu-id="86dd5-3322">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3322">Passport number</span></span> 
- <span data-ttu-id="86dd5-3323">Passport 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-3323">Passport no</span></span> 
- <span data-ttu-id="86dd5-3324">Passport Num</span><span class="sxs-lookup"><span data-stu-id="86dd5-3324">Passport Num</span></span> 
- <span data-ttu-id="86dd5-3325">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3325">Passport #</span></span> 
- <span data-ttu-id="86dd5-3326">护照</span><span class="sxs-lookup"><span data-stu-id="86dd5-3326">护照</span></span> 
- <span data-ttu-id="86dd5-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="86dd5-3327">中華民國護照</span></span> 
- <span data-ttu-id="86dd5-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="86dd5-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="86dd5-3329">台灣居民憑證 (ARC/TARC) 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3330">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3330">Format</span></span>

<span data-ttu-id="86dd5-3331">10 個字母和數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3332">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3332">Pattern</span></span>

<span data-ttu-id="86dd5-3333">10 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3333">10 letters and digits:</span></span>
- <span data-ttu-id="86dd5-3334">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="86dd5-3335">八位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3336">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3336">Checksum</span></span>

<span data-ttu-id="86dd5-3337">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3338">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3338">Definition</span></span>

<span data-ttu-id="86dd5-3339">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3340">規則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3341">找不到來自 Keyword_taiwan_resident_certificate 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3342">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="86dd5-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="86dd5-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="86dd5-3344">內建的憑證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3344">Resident Certificate</span></span> 
- <span data-ttu-id="86dd5-3345">駐留 Cert</span><span class="sxs-lookup"><span data-stu-id="86dd5-3345">Resident Cert</span></span> 
- <span data-ttu-id="86dd5-3346">內建的憑證。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3346">Resident Cert.</span></span> 
- <span data-ttu-id="86dd5-3347">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-3347">Identification card</span></span> 
- <span data-ttu-id="86dd5-3348">外星居民憑證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="86dd5-3349">弧線</span><span class="sxs-lookup"><span data-stu-id="86dd5-3349">ARC</span></span> 
- <span data-ttu-id="86dd5-3350">台灣區域居民憑證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="86dd5-3351">TARC</span><span class="sxs-lookup"><span data-stu-id="86dd5-3351">TARC</span></span> 
- <span data-ttu-id="86dd5-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3352">居留證</span></span> 
- <span data-ttu-id="86dd5-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3353">外僑居留證</span></span> 
- <span data-ttu-id="86dd5-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="86dd5-3355">泰文母體識別程式碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3356">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3356">Format</span></span>

<span data-ttu-id="86dd5-3357">13 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3358">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3358">Pattern</span></span>

<span data-ttu-id="86dd5-3359">13 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3359">13 digits:</span></span>
- <span data-ttu-id="86dd5-3360">第一個數字不是 0 或 9</span><span class="sxs-lookup"><span data-stu-id="86dd5-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="86dd5-3361">12 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3362">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3362">Checksum</span></span>

<span data-ttu-id="86dd5-3363">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3364">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3364">Definition</span></span>

<span data-ttu-id="86dd5-3365">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3366">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3367">找不到來自 Keyword_Thai_Citizen_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="86dd5-3368">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3369">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3370">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="86dd5-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="86dd5-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="86dd5-3372">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3372">ID Number</span></span>
- <span data-ttu-id="86dd5-3373">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3373">Identification Number</span></span>
- <span data-ttu-id="86dd5-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="86dd5-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="86dd5-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="86dd5-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="86dd5-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="86dd5-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="86dd5-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="86dd5-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="86dd5-3378">土耳其文的國家識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3379">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3379">Format</span></span>

<span data-ttu-id="86dd5-3380">11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3381">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3381">Pattern</span></span>

<span data-ttu-id="86dd5-3382">11 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3383">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3383">Checksum</span></span>

<span data-ttu-id="86dd5-3384">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3385">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3385">Definition</span></span>

<span data-ttu-id="86dd5-3386">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3387">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3388">找不到來自 Keyword_Turkish_National_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="86dd5-3389">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3390">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3391">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="86dd5-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="86dd5-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="86dd5-3393">繁體中文 Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3393">TC Kimlik No</span></span>
- <span data-ttu-id="86dd5-3394">繁體中文 Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="86dd5-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="86dd5-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="86dd5-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="86dd5-3396">Vatandaşlık 沒有</span><span class="sxs-lookup"><span data-stu-id="86dd5-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="86dd5-3397">英國</span><span class="sxs-lookup"><span data-stu-id="86dd5-3397">U.K.</span></span> <span data-ttu-id="86dd5-3398">駕照編號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3398">Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3399">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3399">Format</span></span>

<span data-ttu-id="86dd5-3400">18 個字母和數字中指定之格式的組合</span><span class="sxs-lookup"><span data-stu-id="86dd5-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3401">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3401">Pattern</span></span>

<span data-ttu-id="86dd5-3402">18 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3402">18 letters and digits:</span></span>
- <span data-ttu-id="86dd5-3403">五個字母 （不區分大小寫） 或取代字母的數字"9"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="86dd5-3404">一位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3404">One digit</span></span> 
- <span data-ttu-id="86dd5-3405">五位數的日期格式 ddmmy 表示出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="86dd5-3406">兩個字母 （不區分大小寫） 或取代字母的數字"9"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="86dd5-3407">五位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3408">Checksum</span></span>

<span data-ttu-id="86dd5-3409">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3410">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3410">Definition</span></span>

<span data-ttu-id="86dd5-3411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3412">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3413">找不到來自 Keyword_uk_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="86dd5-3414">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3415">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="86dd5-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="86dd5-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="86dd5-3417">DVLA</span><span class="sxs-lookup"><span data-stu-id="86dd5-3417">DVLA</span></span> 
- <span data-ttu-id="86dd5-3418">淺 van 能夠</span><span class="sxs-lookup"><span data-stu-id="86dd5-3418">light vans</span></span> 
- <span data-ttu-id="86dd5-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="86dd5-3419">quadbikes</span></span> 
- <span data-ttu-id="86dd5-3420">馬達車輛</span><span class="sxs-lookup"><span data-stu-id="86dd5-3420">motor cars</span></span> 
- <span data-ttu-id="86dd5-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="86dd5-3421">125cc</span></span> 
- <span data-ttu-id="86dd5-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="86dd5-3422">sidecar</span></span> 
- <span data-ttu-id="86dd5-3423">tricycles</span><span class="sxs-lookup"><span data-stu-id="86dd5-3423">tricycles</span></span> 
- <span data-ttu-id="86dd5-3424">機車</span><span class="sxs-lookup"><span data-stu-id="86dd5-3424">motorcycles</span></span> 
- <span data-ttu-id="86dd5-3425">photocard 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3425">photocard licence</span></span> 
- <span data-ttu-id="86dd5-3426">學習者單元驅動程式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3426">learner drivers</span></span> 
- <span data-ttu-id="86dd5-3427">授權持有者</span><span class="sxs-lookup"><span data-stu-id="86dd5-3427">licence holder</span></span> 
- <span data-ttu-id="86dd5-3428">授權持有者</span><span class="sxs-lookup"><span data-stu-id="86dd5-3428">licence holders</span></span> 
- <span data-ttu-id="86dd5-3429">driving 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3429">driving licences</span></span> 
- <span data-ttu-id="86dd5-3430">driving 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3430">driving licence</span></span> 
- <span data-ttu-id="86dd5-3431">雙重控制汽車</span><span class="sxs-lookup"><span data-stu-id="86dd5-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="86dd5-3432">英國</span><span class="sxs-lookup"><span data-stu-id="86dd5-3432">U.K.</span></span> <span data-ttu-id="86dd5-3433">Electoral Roll 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3433">Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3434">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3434">Format</span></span>

<span data-ttu-id="86dd5-3435">兩個字母後尾隨 1-4 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3436">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3436">Pattern</span></span>

<span data-ttu-id="86dd5-3437">兩個字母 （不區分大小寫） 尾隨 1-4 個數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3438">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3438">Checksum</span></span>

<span data-ttu-id="86dd5-3439">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3440">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3440">Definition</span></span>

<span data-ttu-id="86dd5-3441">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3442">規則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3443">找不到來自 Keyword_uk_electoral 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3444">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="86dd5-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="86dd5-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="86dd5-3446">會議提名</span><span class="sxs-lookup"><span data-stu-id="86dd5-3446">council nomination</span></span> 
- <span data-ttu-id="86dd5-3447">提名表單</span><span class="sxs-lookup"><span data-stu-id="86dd5-3447">nomination form</span></span> 
- <span data-ttu-id="86dd5-3448">選舉註冊</span><span class="sxs-lookup"><span data-stu-id="86dd5-3448">electoral register</span></span> 
- <span data-ttu-id="86dd5-3449">electoral roll</span><span class="sxs-lookup"><span data-stu-id="86dd5-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="86dd5-3450">英國</span><span class="sxs-lookup"><span data-stu-id="86dd5-3450">U.K.</span></span> <span data-ttu-id="86dd5-3451">國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3451">National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3452">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3452">Format</span></span>

<span data-ttu-id="86dd5-3453">以空格分隔的 10-17 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3454">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3454">Pattern</span></span>

<span data-ttu-id="86dd5-3455">10-17 位數：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3455">10-17 digits:</span></span>
- <span data-ttu-id="86dd5-3456">3 或 10 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="86dd5-3457">一個空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-3457">A space</span></span> 
- <span data-ttu-id="86dd5-3458">三位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3458">Three digits</span></span> 
- <span data-ttu-id="86dd5-3459">一個空格</span><span class="sxs-lookup"><span data-stu-id="86dd5-3459">A space</span></span> 
- <span data-ttu-id="86dd5-3460">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3461">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3461">Checksum</span></span>

<span data-ttu-id="86dd5-3462">是</span><span class="sxs-lookup"><span data-stu-id="86dd5-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3463">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3463">Definition</span></span>

<span data-ttu-id="86dd5-3464">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3465">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3466">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3466">One of the following is true:</span></span>
    - <span data-ttu-id="86dd5-3467">找不到來自 Keyword_uk_nhs_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="86dd5-3468">找不到來自 Keyword_uk_nhs_number1 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="86dd5-3469">找不到來自 Keyword_uk_nhs_number_dob 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="86dd5-3470">總和檢查碼通過。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3471">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="86dd5-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="86dd5-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="86dd5-3473">國民健保服務</span><span class="sxs-lookup"><span data-stu-id="86dd5-3473">national health service</span></span> 
- <span data-ttu-id="86dd5-3474">nhs</span><span class="sxs-lookup"><span data-stu-id="86dd5-3474">nhs</span></span> 
- <span data-ttu-id="86dd5-3475">健康情況服務授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3475">health services authority</span></span> 
- <span data-ttu-id="86dd5-3476">健康情況授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="86dd5-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="86dd5-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="86dd5-3478">病患識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3478">patient id</span></span> 
- <span data-ttu-id="86dd5-3479">病患識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3479">patient identification</span></span> 
- <span data-ttu-id="86dd5-3480">病患否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3480">patient no</span></span> 
- <span data-ttu-id="86dd5-3481">病患的數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="86dd5-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="86dd5-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="86dd5-3483">GP</span><span class="sxs-lookup"><span data-stu-id="86dd5-3483">GP</span></span> 
- <span data-ttu-id="86dd5-3484">DOB</span><span class="sxs-lookup"><span data-stu-id="86dd5-3484">DOB</span></span> 
- <span data-ttu-id="86dd5-3485">D.O.B</span><span class="sxs-lookup"><span data-stu-id="86dd5-3485">D.O.B</span></span> 
- <span data-ttu-id="86dd5-3486">出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3486">Date of Birth</span></span> 
- <span data-ttu-id="86dd5-3487">出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="86dd5-3488">英國</span><span class="sxs-lookup"><span data-stu-id="86dd5-3488">U.K.</span></span> <span data-ttu-id="86dd5-3489">國家保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3489">National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3490">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3490">Format</span></span>

<span data-ttu-id="86dd5-3491">7 個字元或空格或連字號分隔的 9 個字元</span><span class="sxs-lookup"><span data-stu-id="86dd5-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3492">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3492">Pattern</span></span>

<span data-ttu-id="86dd5-3493">兩個可能的模式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3493">Two possible patterns:</span></span>

- <span data-ttu-id="86dd5-3494">兩個字母 (有效 NINOs 中此前置詞，此模式會驗證; 使用僅限特定字元不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="86dd5-3495">六位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3495">Six digits</span></span>
- <span data-ttu-id="86dd5-3496">可以是 'A'、 'B'、 'C'，或有 ' （例如前置詞，只有某些字元中允許之尾碼; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="86dd5-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="86dd5-3497">或</span><span class="sxs-lookup"><span data-stu-id="86dd5-3497">OR</span></span>

- <span data-ttu-id="86dd5-3498">兩個字母</span><span class="sxs-lookup"><span data-stu-id="86dd5-3498">Two letters</span></span>
- <span data-ttu-id="86dd5-3499">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3499">A space or dash</span></span>
- <span data-ttu-id="86dd5-3500">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3500">Two digits</span></span>
- <span data-ttu-id="86dd5-3501">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3501">A space or dash</span></span>
- <span data-ttu-id="86dd5-3502">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3502">Two digits</span></span>
- <span data-ttu-id="86dd5-3503">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3503">A space or dash</span></span>
- <span data-ttu-id="86dd5-3504">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3504">Two digits</span></span>
- <span data-ttu-id="86dd5-3505">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3505">A space or dash</span></span>
- <span data-ttu-id="86dd5-3506">可以是 'A'、 'B'、 'C'，或有 '</span><span class="sxs-lookup"><span data-stu-id="86dd5-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3507">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3507">Checksum</span></span>

<span data-ttu-id="86dd5-3508">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3509">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3509">Definition</span></span>

<span data-ttu-id="86dd5-3510">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3511">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3512">找不到來自 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="86dd5-3513">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3514">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3515">找不到來自 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="86dd5-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="86dd5-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="86dd5-3518">國家保險號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3518">national insurance number</span></span> 
- <span data-ttu-id="86dd5-3519">國家保險捐款</span><span class="sxs-lookup"><span data-stu-id="86dd5-3519">national insurance contributions</span></span> 
- <span data-ttu-id="86dd5-3520">保護法案</span><span class="sxs-lookup"><span data-stu-id="86dd5-3520">protection act</span></span> 
- <span data-ttu-id="86dd5-3521">保險</span><span class="sxs-lookup"><span data-stu-id="86dd5-3521">insurance</span></span> 
- <span data-ttu-id="86dd5-3522">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3522">social security number</span></span> 
- <span data-ttu-id="86dd5-3523">保險應用程式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3523">insurance application</span></span> 
- <span data-ttu-id="86dd5-3524">醫療應用程式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3524">medical application</span></span> 
- <span data-ttu-id="86dd5-3525">社會保險</span><span class="sxs-lookup"><span data-stu-id="86dd5-3525">social insurance</span></span> 
- <span data-ttu-id="86dd5-3526">醫療注意事項</span><span class="sxs-lookup"><span data-stu-id="86dd5-3526">medical attention</span></span> 
- <span data-ttu-id="86dd5-3527">社會安全</span><span class="sxs-lookup"><span data-stu-id="86dd5-3527">social security</span></span> 
- <span data-ttu-id="86dd5-3528">英國</span><span class="sxs-lookup"><span data-stu-id="86dd5-3528">great britain</span></span> 
- <span data-ttu-id="86dd5-3529">保險</span><span class="sxs-lookup"><span data-stu-id="86dd5-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="86dd5-3530">美國 / 英國</span><span class="sxs-lookup"><span data-stu-id="86dd5-3530">U.S. / U.K.</span></span> <span data-ttu-id="86dd5-3531">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3531">Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3532">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3532">Format</span></span>

<span data-ttu-id="86dd5-3533">九位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3534">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3534">Pattern</span></span>

<span data-ttu-id="86dd5-3535">九個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3536">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3536">Checksum</span></span>

<span data-ttu-id="86dd5-3537">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3538">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3538">Definition</span></span>

<span data-ttu-id="86dd5-3539">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3540">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3541">找不到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3542">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="86dd5-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="86dd5-3543">Keyword_passport</span></span>

- <span data-ttu-id="86dd5-3544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3544">Passport Number</span></span> 
- <span data-ttu-id="86dd5-3545">Passport 否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3545">Passport No</span></span> 
- <span data-ttu-id="86dd5-3546">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3546">Passport #</span></span> 
- <span data-ttu-id="86dd5-3547">Passport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3547">Passport#</span></span> 
- <span data-ttu-id="86dd5-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="86dd5-3548">PassportID</span></span> 
- <span data-ttu-id="86dd5-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="86dd5-3549">Passportno</span></span> 
- <span data-ttu-id="86dd5-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="86dd5-3550">passportnumber</span></span> 
- <span data-ttu-id="86dd5-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="86dd5-3551">パスポート</span></span> 
- <span data-ttu-id="86dd5-3552">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="86dd5-3552">パスポート番号</span></span> 
- <span data-ttu-id="86dd5-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="86dd5-3553">パスポートのNum</span></span> 
- <span data-ttu-id="86dd5-3554">パスポート #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3554">パスポート＃</span></span> 
- <span data-ttu-id="86dd5-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="86dd5-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="86dd5-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="86dd5-3556">Passeport n °</span></span> 
- <span data-ttu-id="86dd5-3557">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="86dd5-3557">Passeport Non</span></span> 
- <span data-ttu-id="86dd5-3558">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3558">Passeport #</span></span> 
- <span data-ttu-id="86dd5-3559">Passeport #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3559">Passeport#</span></span> 
- <span data-ttu-id="86dd5-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="86dd5-3560">PasseportNon</span></span> 
- <span data-ttu-id="86dd5-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="86dd5-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="86dd5-3562">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3563">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3563">Format</span></span>

<span data-ttu-id="86dd5-3564">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3565">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3565">Pattern</span></span>

<span data-ttu-id="86dd5-3566">8-17 個連續數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3567">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3567">Checksum</span></span>

<span data-ttu-id="86dd5-3568">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3569">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3569">Definition</span></span>

<span data-ttu-id="86dd5-3570">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3571">規則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3572">找不到來自 Keyword_usa_Bank_Account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86dd5-3573">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="86dd5-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="86dd5-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="86dd5-3575">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3575">Checking Account Number</span></span> 
- <span data-ttu-id="86dd5-3576">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-3576">Checking Account</span></span> 
- <span data-ttu-id="86dd5-3577">檢查帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3577">Checking Account #</span></span> 
- <span data-ttu-id="86dd5-3578">檢查 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="86dd5-3579">檢查 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3579">Checking Acct #</span></span> 
- <span data-ttu-id="86dd5-3580">檢查 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="86dd5-3581">檢查帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3581">Checking Account No.</span></span> 
- <span data-ttu-id="86dd5-3582">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3582">Bank Account Number</span></span> 
- <span data-ttu-id="86dd5-3583">銀行帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3583">Bank Account #</span></span> 
- <span data-ttu-id="86dd5-3584">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="86dd5-3585">銀行 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3585">Bank Acct #</span></span> 
- <span data-ttu-id="86dd5-3586">銀行 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="86dd5-3587">銀行帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3587">Bank Account No.</span></span> 
- <span data-ttu-id="86dd5-3588">節省帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3588">Savings Account Number</span></span> 
- <span data-ttu-id="86dd5-3589">省下的帳戶。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3589">Savings Account.</span></span> 
- <span data-ttu-id="86dd5-3590">節省帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3590">Savings Account #</span></span> 
- <span data-ttu-id="86dd5-3591">節省 Acct 數目</span><span class="sxs-lookup"><span data-stu-id="86dd5-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="86dd5-3592">節省 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3592">Savings Acct #</span></span> 
- <span data-ttu-id="86dd5-3593">節省 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="86dd5-3594">存款帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3594">Savings Account No.</span></span> 
- <span data-ttu-id="86dd5-3595">轉帳帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3595">Debit Account Number</span></span> 
- <span data-ttu-id="86dd5-3596">轉帳帳戶</span><span class="sxs-lookup"><span data-stu-id="86dd5-3596">Debit Account</span></span> 
- <span data-ttu-id="86dd5-3597">借方帳戶 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3597">Debit Account #</span></span> 
- <span data-ttu-id="86dd5-3598">轉帳 Acct 號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="86dd5-3599">借方 Acct #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3599">Debit Acct #</span></span> 
- <span data-ttu-id="86dd5-3600">轉帳 Acct [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="86dd5-3601">轉帳帳戶 [否]。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="86dd5-3602">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3603">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3603">Format</span></span>

<span data-ttu-id="86dd5-3604">隨州別</span><span class="sxs-lookup"><span data-stu-id="86dd5-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3605">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3605">Pattern</span></span>

<span data-ttu-id="86dd5-3606">狀態-例如，紐約而定：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="86dd5-3607">九位數格式化 like ddd ddd ddd 會比對。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="86dd5-3608">不會符合 ddddddddd 類似的九位數。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3609">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3609">Checksum</span></span>

<span data-ttu-id="86dd5-3610">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3611">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3611">Definition</span></span>

<span data-ttu-id="86dd5-3612">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3613">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3614">找到來自於 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="86dd5-3615">找不到來自 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="86dd5-3616">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3617">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3618">找到來自於 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="86dd5-3619">找不到來自 Keyword_us_drivers_license_abbreviations 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="86dd5-3620">找不到來自 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="86dd5-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="86dd5-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="86dd5-3623">DL</span><span class="sxs-lookup"><span data-stu-id="86dd5-3623">DL</span></span> 
- <span data-ttu-id="86dd5-3624">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="86dd5-3624">DLS</span></span> 
- <span data-ttu-id="86dd5-3625">CDL</span><span class="sxs-lookup"><span data-stu-id="86dd5-3625">CDL</span></span> 
- <span data-ttu-id="86dd5-3626">CDLS</span><span class="sxs-lookup"><span data-stu-id="86dd5-3626">CDLS</span></span> 
- <span data-ttu-id="86dd5-3627">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3627">ID</span></span> 
- <span data-ttu-id="86dd5-3628">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3628">IDs</span></span> 
- <span data-ttu-id="86dd5-3629">DL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3629">DL#</span></span> 
- <span data-ttu-id="86dd5-3630">DL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3630">DLS#</span></span> 
- <span data-ttu-id="86dd5-3631">CDL #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3631">CDL#</span></span> 
- <span data-ttu-id="86dd5-3632">CDLS #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3632">CDLS#</span></span> 
- <span data-ttu-id="86dd5-3633">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3633">ID#</span></span>
- <span data-ttu-id="86dd5-3634">識別碼 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3634">IDs#</span></span> 
- <span data-ttu-id="86dd5-3635">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3635">ID number</span></span> 
- <span data-ttu-id="86dd5-3636">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3636">ID numbers</span></span> 
- <span data-ttu-id="86dd5-3637">LIC</span><span class="sxs-lookup"><span data-stu-id="86dd5-3637">LIC</span></span> 
- <span data-ttu-id="86dd5-3638">LIC #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="86dd5-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="86dd5-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="86dd5-3640">DriverLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3640">DriverLic</span></span> 
- <span data-ttu-id="86dd5-3641">DriverLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3641">DriverLics</span></span> 
- <span data-ttu-id="86dd5-3642">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="86dd5-3642">DriverLicense</span></span> 
- <span data-ttu-id="86dd5-3643">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-3643">DriverLicenses</span></span> 
- <span data-ttu-id="86dd5-3644">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3644">Driver Lic</span></span> 
- <span data-ttu-id="86dd5-3645">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3645">Driver Lics</span></span> 
- <span data-ttu-id="86dd5-3646">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3646">Driver License</span></span> 
- <span data-ttu-id="86dd5-3647">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3647">Driver Licenses</span></span> 
- <span data-ttu-id="86dd5-3648">DriversLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3648">DriversLic</span></span> 
- <span data-ttu-id="86dd5-3649">DriversLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3649">DriversLics</span></span> 
- <span data-ttu-id="86dd5-3650">執照</span><span class="sxs-lookup"><span data-stu-id="86dd5-3650">DriversLicense</span></span> 
- <span data-ttu-id="86dd5-3651">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-3651">DriversLicenses</span></span> 
- <span data-ttu-id="86dd5-3652">驅動程式 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3652">Drivers Lic</span></span> 
- <span data-ttu-id="86dd5-3653">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3653">Drivers Lics</span></span> 
- <span data-ttu-id="86dd5-3654">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3654">Drivers License</span></span> 
- <span data-ttu-id="86dd5-3655">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="86dd5-3656">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3656">Driver'Lic</span></span> 
- <span data-ttu-id="86dd5-3657">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3657">Driver'Lics</span></span> 
- <span data-ttu-id="86dd5-3658">Driver'License</span><span class="sxs-lookup"><span data-stu-id="86dd5-3658">Driver'License</span></span> 
- <span data-ttu-id="86dd5-3659">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="86dd5-3660">驅動程式 ' Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3660">Driver' Lic</span></span> 
- <span data-ttu-id="86dd5-3661">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3661">Driver' Lics</span></span> 
- <span data-ttu-id="86dd5-3662">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3662">Driver' License</span></span> 
- <span data-ttu-id="86dd5-3663">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3663">Driver' Licenses</span></span>
- <span data-ttu-id="86dd5-3664">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3664">Driver'sLic</span></span> 
- <span data-ttu-id="86dd5-3665">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3665">Driver'sLics</span></span> 
- <span data-ttu-id="86dd5-3666">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="86dd5-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="86dd5-3667">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="86dd5-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="86dd5-3668">駕 Lic</span><span class="sxs-lookup"><span data-stu-id="86dd5-3668">Driver's Lic</span></span> 
- <span data-ttu-id="86dd5-3669">駕 Lics</span><span class="sxs-lookup"><span data-stu-id="86dd5-3669">Driver's Lics</span></span> 
- <span data-ttu-id="86dd5-3670">駕照</span><span class="sxs-lookup"><span data-stu-id="86dd5-3670">Driver's License</span></span> 
- <span data-ttu-id="86dd5-3671">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="86dd5-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="86dd5-3672">識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3672">identification number</span></span> 
- <span data-ttu-id="86dd5-3673">識別數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3673">identification numbers</span></span> 
- <span data-ttu-id="86dd5-3674">識別 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3674">identification #</span></span> 
- <span data-ttu-id="86dd5-3675">證</span><span class="sxs-lookup"><span data-stu-id="86dd5-3675">id card</span></span> 
- <span data-ttu-id="86dd5-3676">id 卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-3676">id cards</span></span> 
- <span data-ttu-id="86dd5-3677">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-3677">identification card</span></span> 
- <span data-ttu-id="86dd5-3678">識別卡</span><span class="sxs-lookup"><span data-stu-id="86dd5-3678">identification cards</span></span> 
- <span data-ttu-id="86dd5-3679">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3679">DriverLic#</span></span> 
- <span data-ttu-id="86dd5-3680">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3680">DriverLics#</span></span> 
- <span data-ttu-id="86dd5-3681">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3681">DriverLicense#</span></span> 
- <span data-ttu-id="86dd5-3682">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="86dd5-3683">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3683">Driver Lic#</span></span> 
- <span data-ttu-id="86dd5-3684">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3684">Driver Lics#</span></span> 
- <span data-ttu-id="86dd5-3685">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3685">Driver License#</span></span> 
- <span data-ttu-id="86dd5-3686">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="86dd5-3687">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3687">DriversLic#</span></span> 
- <span data-ttu-id="86dd5-3688">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3688">DriversLics#</span></span> 
- <span data-ttu-id="86dd5-3689">執照 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3689">DriversLicense#</span></span> 
- <span data-ttu-id="86dd5-3690">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="86dd5-3691">驅動程式 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="86dd5-3692">驅動程式 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="86dd5-3693">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3693">Drivers License#</span></span> 
- <span data-ttu-id="86dd5-3694">驅動程式授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="86dd5-3695">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="86dd5-3696">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="86dd5-3697">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3697">Driver'License#</span></span> 
- <span data-ttu-id="86dd5-3698">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="86dd5-3699">驅動程式 ' Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="86dd5-3700">驅動程式 ' Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="86dd5-3701">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3701">Driver' License#</span></span> 
- <span data-ttu-id="86dd5-3702">驅動程式 ' 授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="86dd5-3703">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="86dd5-3704">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="86dd5-3705">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="86dd5-3706">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="86dd5-3707">駕 Lic #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="86dd5-3708">駕 Lics #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="86dd5-3709">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3709">Driver's License#</span></span> 
- <span data-ttu-id="86dd5-3710">驅動程式的授權 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="86dd5-3711">證 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3711">id card#</span></span> 
- <span data-ttu-id="86dd5-3712">id 卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3712">id cards#</span></span> 
- <span data-ttu-id="86dd5-3713">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3713">identification card#</span></span> 
- <span data-ttu-id="86dd5-3714">識別卡 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="86dd5-3715">於 Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="86dd5-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="86dd5-3716">州別縮寫 (例如"NY")</span><span class="sxs-lookup"><span data-stu-id="86dd5-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="86dd5-3717">州名稱 (例如"New York")</span><span class="sxs-lookup"><span data-stu-id="86dd5-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="86dd5-3718">美國個別 Taxpayer 識別號碼 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3719">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3719">Format</span></span>

<span data-ttu-id="86dd5-3720">九位數，以"9"開頭且包含"7"8"的第四個位數，可選擇加上空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3721">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3721">Pattern</span></span>

<span data-ttu-id="86dd5-3722">格式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3722">Formatted:</span></span>
- <span data-ttu-id="86dd5-3723">數字"9"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3723">The digit "9"</span></span> 
- <span data-ttu-id="86dd5-3724">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3724">Two digits</span></span> 
- <span data-ttu-id="86dd5-3725">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3725">A space or dash</span></span> 
- <span data-ttu-id="86dd5-3726">"7"或者"8"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="86dd5-3727">數字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3727">A digit</span></span> 
- <span data-ttu-id="86dd5-3728">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="86dd5-3728">A space, or dash</span></span> 
- <span data-ttu-id="86dd5-3729">四位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3729">Four digits</span></span>

<span data-ttu-id="86dd5-3730">格式化：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3730">Unformatted:</span></span>
- <span data-ttu-id="86dd5-3731">數字"9"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3731">The digit "9"</span></span> 
- <span data-ttu-id="86dd5-3732">兩位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3732">Two digits</span></span> 
- <span data-ttu-id="86dd5-3733">"7"或者"8"</span><span class="sxs-lookup"><span data-stu-id="86dd5-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="86dd5-3734">五位數</span><span class="sxs-lookup"><span data-stu-id="86dd5-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3735">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3735">Checksum</span></span>

<span data-ttu-id="86dd5-3736">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="86dd5-3737">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3737">Definition</span></span>

<span data-ttu-id="86dd5-3738">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3739">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3740">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="86dd5-3741">找不到來自 Keyword_itin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="86dd5-3742">函數 Func_us_address 找到正確日期格式中的地址。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="86dd5-3743">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="86dd5-3744">找不到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="86dd5-3745">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3746">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3747">至少下列一種為真：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="86dd5-3748">找不到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="86dd5-3749">函數 Func_us_address 找到正確日期格式中的地址。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="86dd5-3750">函數 Func_us_date 找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="86dd5-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="86dd5-3752">Keyword_itin</span></span>

- <span data-ttu-id="86dd5-3753">taxpayer</span><span class="sxs-lookup"><span data-stu-id="86dd5-3753">taxpayer</span></span> 
- <span data-ttu-id="86dd5-3754">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3754">tax id</span></span> 
- <span data-ttu-id="86dd5-3755">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3755">tax identification</span></span> 
- <span data-ttu-id="86dd5-3756">itin</span><span class="sxs-lookup"><span data-stu-id="86dd5-3756">itin</span></span> 
- <span data-ttu-id="86dd5-3757">ssn</span><span class="sxs-lookup"><span data-stu-id="86dd5-3757">ssn</span></span> 
- <span data-ttu-id="86dd5-3758">錫</span><span class="sxs-lookup"><span data-stu-id="86dd5-3758">tin</span></span> 
- <span data-ttu-id="86dd5-3759">社會安全</span><span class="sxs-lookup"><span data-stu-id="86dd5-3759">social security</span></span> 
- <span data-ttu-id="86dd5-3760">稅務付款者</span><span class="sxs-lookup"><span data-stu-id="86dd5-3760">tax payer</span></span> 
- <span data-ttu-id="86dd5-3761">itins</span><span class="sxs-lookup"><span data-stu-id="86dd5-3761">itins</span></span> 
- <span data-ttu-id="86dd5-3762">taxid</span><span class="sxs-lookup"><span data-stu-id="86dd5-3762">taxid</span></span> 
- <span data-ttu-id="86dd5-3763">個別 taxpayer</span><span class="sxs-lookup"><span data-stu-id="86dd5-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="86dd5-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="86dd5-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="86dd5-3765">License</span><span class="sxs-lookup"><span data-stu-id="86dd5-3765">License</span></span> 
- <span data-ttu-id="86dd5-3766">DL</span><span class="sxs-lookup"><span data-stu-id="86dd5-3766">DL</span></span> 
- <span data-ttu-id="86dd5-3767">DOB</span><span class="sxs-lookup"><span data-stu-id="86dd5-3767">DOB</span></span> 
- <span data-ttu-id="86dd5-3768">出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3768">Birthdate</span></span> 
- <span data-ttu-id="86dd5-3769">生日</span><span class="sxs-lookup"><span data-stu-id="86dd5-3769">Birthday</span></span> 
- <span data-ttu-id="86dd5-3770">出生日期</span><span class="sxs-lookup"><span data-stu-id="86dd5-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="86dd5-3771">美國社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="86dd5-3772">格式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3772">Format</span></span>

<span data-ttu-id="86dd5-3773">9 位數，可採用格式化或未格式化模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="86dd5-3774">SSN 如果發出 mid 2011 之前，已增強式格式設定其中某些部分的數字必須落在有效特定範圍內 （但沒有任何總和檢查碼）。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="86dd5-3775">模式</span><span class="sxs-lookup"><span data-stu-id="86dd5-3775">Pattern</span></span>

<span data-ttu-id="86dd5-3776">四個函數尋找 Ssn 四個不同的模式：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="86dd5-3777">Func_ssn 找到與預先 2011年強式的格式設定，以連字號或空格 (ddd ddd-dd-dddd 或 ddd dd dddd) 格式化 Ssn</span><span class="sxs-lookup"><span data-stu-id="86dd5-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="86dd5-3778">Func_unformatted_ssn 找尋找 Ssn 具有預先 2011年強式的格式設定，會以未格式化為九個連續數字 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="86dd5-3779">Func_randomized_formatted_ssn 找到以連字號或空格 (ddd ddd-dd-dddd 或 ddd dd dddd) 格式化的文章 2011 Ssn</span><span class="sxs-lookup"><span data-stu-id="86dd5-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="86dd5-3780">Func_randomized_unformatted_ssn 找到 post 2011 Ssn 所格式化為九個連續數字 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="86dd5-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="86dd5-3781">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="86dd5-3781">Checksum</span></span>

<span data-ttu-id="86dd5-3782">否</span><span class="sxs-lookup"><span data-stu-id="86dd5-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="86dd5-3783">定義</span><span class="sxs-lookup"><span data-stu-id="86dd5-3783">Definition</span></span>

<span data-ttu-id="86dd5-3784">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3785">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3786">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="86dd5-3787">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3788">函數 func_unformatted_ssn 找找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3789">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="86dd5-3790">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3791">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3792">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="86dd5-3793">函數 func_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="86dd5-3794">DLP 原則是 55%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="86dd5-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="86dd5-3795">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="86dd5-3796">找不到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="86dd5-3797">函數 func_unformatted_ssn 找不到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="86dd5-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="86dd5-3798">關鍵字</span><span class="sxs-lookup"><span data-stu-id="86dd5-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="86dd5-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="86dd5-3799">Keyword_ssn</span></span>

- <span data-ttu-id="86dd5-3800">社會安全</span><span class="sxs-lookup"><span data-stu-id="86dd5-3800">Social Security</span></span> 
- <span data-ttu-id="86dd5-3801">社會安全 #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3801">Social Security#</span></span> 
- <span data-ttu-id="86dd5-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="86dd5-3802">Soc Sec</span></span> 
- <span data-ttu-id="86dd5-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="86dd5-3803">SSN</span></span> 
- <span data-ttu-id="86dd5-3804">SSN</span><span class="sxs-lookup"><span data-stu-id="86dd5-3804">SSNS</span></span> 
- <span data-ttu-id="86dd5-3805">SSN #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3805">SSN#</span></span> 
- <span data-ttu-id="86dd5-3806">SS #</span><span class="sxs-lookup"><span data-stu-id="86dd5-3806">SS#</span></span> 
- <span data-ttu-id="86dd5-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="86dd5-3807">SSID</span></span> 
   

