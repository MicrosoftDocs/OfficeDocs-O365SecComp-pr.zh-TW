---
title: 從範本建立 DLP 原則
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '若要開始使用 DLP 原則的最簡單的、 最常見方式是使用其中一個包含在 Office 365 中的範本。 '
ms.openlocfilehash: 4e3a5d731538e4998858b5f9f7a296c43e6774ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526807"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="da77a-103">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="da77a-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="da77a-p101">若要開始使用 DLP 原則的最簡單的、 最常見方式是使用其中一個包含在 Office 365 中的範本。您可以使用其中一個時，這些範本或自訂規則以符合組織的特定規範需求。</span><span class="sxs-lookup"><span data-stu-id="da77a-p101">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365. You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="da77a-p102">Office 365 包含 40 多個現成可用的範本，可協助您符合各種常見法規與商業原則需求。例如，下列項目就有 DLP 原則範本：</span><span class="sxs-lookup"><span data-stu-id="da77a-p102">Office 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs. For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="da77a-108">Gramm-Leach-Bliley Act (GLBA)</span><span class="sxs-lookup"><span data-stu-id="da77a-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="da77a-109">支付卡行業資料安全標準 (PCI DSS)</span><span class="sxs-lookup"><span data-stu-id="da77a-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="da77a-110">美國個人識別資訊 (美國 PII)</span><span class="sxs-lookup"><span data-stu-id="da77a-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="da77a-111">美國健康保險法案 (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="da77a-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="da77a-p103">您可以修改任何現有的規則或新增規則，以微調範本。例如，您可以將新的敏感資訊類型新增至規則、修改規則中的計數使其更難以或容易觸發、允許人員藉由提供正當業務理由來覆寫規則中的動作，或變更通知和事件報告的傳送對象。DLP 原則範本可做為許多常見規範案例的彈性起始點。</span><span class="sxs-lookup"><span data-stu-id="da77a-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="da77a-115">您也可以選擇自訂範本 (沒有任何預設規則)，然後從頭設定 DLP 原則，以符合組織的特定規範需求。</span><span class="sxs-lookup"><span data-stu-id="da77a-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="da77a-116">範例： 識別敏感資訊跨所有 OneDrive for Business 的網站和組織外部人員限制存取</span><span class="sxs-lookup"><span data-stu-id="da77a-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="da77a-p104">OneDrive for Business 帳戶輕鬆人員整個組織共同作業及共用文件。但法務人員的一般考量敏感資訊儲存在 OneDrive for Business 的帳戶可能不經意共用與組織外部的人員。DLP 原則可協助減輕這類風險。</span><span class="sxs-lookup"><span data-stu-id="da77a-p104">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="da77a-p105">在這個範例中，您將建立 DLP 原則識別美國 PII 資料，包括個別 Taxpayer 識別號碼 (ITIN)、 社會安全編號、 及美國護照號碼。您將開始使用範本，並接著則將會修改的範本以符合組織的規範需求 — 尤其是您將會：</span><span class="sxs-lookup"><span data-stu-id="da77a-p105">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="da77a-122">新增一些機密 information—U.S。 銀行帳戶號碼] 和 [美國驅動程式的授權數字類型 — 使 DLP 原則提供保護，即使有更多機密資料。</span><span class="sxs-lookup"><span data-stu-id="da77a-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="da77a-123">將原則較寫設定使敏感資訊的單一項目是足夠限制外部使用者的存取。</span><span class="sxs-lookup"><span data-stu-id="da77a-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="da77a-p106">允許使用者透過提供業務上理由或報告為誤判覆寫動作。如此一來，您的 DLP 原則將不會防止從快速完成，其工作時有有效的商業原因共用機密資訊在組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="da77a-p106">Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="da77a-126">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="da77a-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="da77a-127">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="da77a-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="da77a-p107">登入 Office 365 中，使用您工作或學校的帳戶。您現在是 Office 365 安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="da77a-p107">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="da77a-130">安全性&amp;規範中心\>左導覽\>**資料外洩防護** \> **原則** \> **+ 建立原則**。</span><span class="sxs-lookup"><span data-stu-id="da77a-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![建立原則] 按鈕](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="da77a-132">選擇會保護您需要的敏感資訊類型的 DLP 原則範本\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="da77a-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="da77a-133">您將在這個範例中，選取 [**隱私權** \> **美國個人識別資訊 (PII) 資料**因為它已經包含您想要保護的敏感資訊類型的大部分 — 將在稍後新增一些。</span><span class="sxs-lookup"><span data-stu-id="da77a-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="da77a-134">當您選取範本時，您可以閱讀以了解的敏感資訊的範本類型所提供的保護右邊的描述。</span><span class="sxs-lookup"><span data-stu-id="da77a-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![選擇 DLP 原則範本] 頁面](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="da77a-136">命名原則\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="da77a-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="da77a-137">若要選擇您想要保護的 DLP 原則的位置，請執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="da77a-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="da77a-138">選擇**Office 365 中的所有位置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="da77a-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="da77a-p108">選擇 [**讓我選擇特定位置** \> **下一步**。此範例中，選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="da77a-p108">Choose **Let me choose specific locations** \> **Next**. For this example, choose this.</span></span>
    
    <span data-ttu-id="da77a-141">若要包含或排除整個位置例如所有的 Exchange 電子郵件或 OneDrive 的所有帳戶，請開啟或關閉切換該位置的**狀態**。</span><span class="sxs-lookup"><span data-stu-id="da77a-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="da77a-p109">若要加上只有特定的 SharePoint 網站或 OneDrive for Business 的帳戶，切換至**狀態**，和 [連結底下**加入**選擇特定網站或帳戶。當您將原則套用至網站，設定於該原則會自動套用至該網站的所有子網站的規則。</span><span class="sxs-lookup"><span data-stu-id="da77a-p109">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts. When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![DLP 原則可以套用的位置選項](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="da77a-145">在這個範例中，以保護機密資訊儲存在所有 OneDrive for Business 的帳戶， **Exchange 電子郵件**與**SharePoint 網站**]，關閉**狀態**和留**狀態**上**OneDrive**帳戶。</span><span class="sxs-lookup"><span data-stu-id="da77a-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="da77a-146">選擇 [**進階設定，可使用** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="da77a-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="da77a-p110">DLP 原則範本包含預先定義的規則條件與動作的偵測及作用於特定的敏感資訊類型。您可以編輯、 刪除或關閉的任何現有的規則，或新增新的。完成之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="da77a-p110">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information. You can edit, delete, or turn off any of the existing rules, or add new ones. When done, click **Next**.</span></span>
    
    ![規則會跟著展開在美國 PII 原則範本](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="da77a-151">在這個範例中，美國 PII 資料範本包含兩個預先定義的規則：</span><span class="sxs-lookup"><span data-stu-id="da77a-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="da77a-p111">**低的內容量偵測到美國 PII**此規則會尋找包含的每個三種類型的檔案位置與組織外部人員共用的機密資訊 （ITIN、 SSN，以及美國護照號碼）、 1 到 10 個項目之間的檔案。如果找到規則傳送的電子郵件通知給主要網站集合管理員、 文件擁有者和人員前次修改文件。</span><span class="sxs-lookup"><span data-stu-id="da77a-p111">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="da77a-p112">**內容的高數量偵測到美國 PII**此規則會尋找的檔案，其中包含的每個相同的三個敏感資訊類型、 10 個或多個項目位置與組織外部人員共用檔案。如果找到此動作也會傳送電子郵件通知，加上加以限制存取的檔案。OneDrive for Business 帳戶中的內容，這表示文件的權限受到限制的主要網站集合管理員、 文件擁有者及上次修改文件的人以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="da77a-p112">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="da77a-p113">若要符合組織的特定需求，您可能要讓規則更容易使用觸發程序，使敏感資訊的單一項目是足夠封鎖的外部使用者存取。您了解之後查看這些規則，您不需要低或高計數規則 — 需要僅限單一規則封鎖存取如果找到任何出現項目中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="da77a-p113">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="da77a-159">讓您擴充名為 [**低的內容量偵測到美國 PII**的規則\>**刪除規則**。</span><span class="sxs-lookup"><span data-stu-id="da77a-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    ![刪除規則] 按鈕](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="da77a-p114">現在，在此範例中，您必須新增兩個機密資訊類型 （US 銀行帳戶號碼和美國驅動程式的授權數字） 允許其他人覆寫規則，而變更任何出現項目計數。您可以執行所有動作來編輯規則，因此請選取 [**內容的高數量偵測到美國 PII** \> **編輯規則**。</span><span class="sxs-lookup"><span data-stu-id="da77a-p114">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    ![編輯規則] 按鈕](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="da77a-p115">在 [**條件**] 區段中新增的敏感資訊類型、 \> **新增或變更的類型**。然後，在 **[新增或變更的類型**] 下\>選擇 [**新增**\>選取**美國銀行帳戶號碼**和**美國駕照編號** \> **新增** \> **完成**。</span><span class="sxs-lookup"><span data-stu-id="da77a-p115">To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![新增或變更類型的選項](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![新增或變更類型] 窗格](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="da77a-p116">在**執行個體計數**下變更計數 （觸發規則所需的敏感資訊的執行個體數），\>選擇每種類型的**最小**值\>輸入 1。最小計數不能是空的。最大計數可以是空的。空白**最大**值轉換成**任何**。</span><span class="sxs-lookup"><span data-stu-id="da77a-p116">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="da77a-p117">完成時，所有的機密資訊類型的最小計數應為 [ **1**和最大計數應為**任何**。換句話說，這種敏感資訊類型的任何出現項目會滿足此條件。</span><span class="sxs-lookup"><span data-stu-id="da77a-p117">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![敏感資訊類型的執行個體計數](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="da77a-174">進行最終的自訂，您不想要封鎖來自他們具有有效的業務上理由或遇到誤判，因此您想要包含選項來覆寫 [封鎖] 動作使用者通知時執行其工作人員 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="da77a-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="da77a-175">在**使用者的通知**] 區段中，您可以看到的電子郵件通知及原則提示的預設開啟此範本中的規則。</span><span class="sxs-lookup"><span data-stu-id="da77a-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="da77a-p118">在**使用者會覆寫**] 區段中，您可以看到的業務上理由覆寫已開啟，但不是會報告誤判覆寫。選擇 [**自動如果它們回報為誤判覆寫規則**。</span><span class="sxs-lookup"><span data-stu-id="da77a-p118">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    ![通知] 區段中使用者和使用者會覆寫] 區段](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="da77a-179">規則編輯器頂端此規則的名稱從變更**內容的高數量偵測到美國 PII**的預設值**具有美國 PII 偵測到任何**內容因為它現在會由其敏感資訊類型的任何出現項目觸發。</span><span class="sxs-lookup"><span data-stu-id="da77a-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="da77a-180">下方的規則編輯器\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="da77a-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="da77a-181">檢閱條件和動作為此規則\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="da77a-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="da77a-p119">在右邊，請注意切換之規則的**狀態**。如果您關閉整個原則、 原則中所包含的所有規則也都已關閉。不過，此處您可以關閉特定規則而關閉整個原則。當您需要調查會產生誤判大量的規則可以是很有用。</span><span class="sxs-lookup"><span data-stu-id="da77a-p119">On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="da77a-186">在 [下一步] 頁面的讀取和了解下列與然後選擇是否要開啟之規則或測試先取出\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="da77a-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="da77a-p120">建立 DLP 原則之前，您應該考量啟用這些逐漸評估影響並完整地強制之前測試其有效性。例如，您不想要不小心封鎖數以千計的人員需要以取得完成其工作的文件的新 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="da77a-p120">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="da77a-189">如果您具有大型的潛在影響建立 DLP 原則，建議您遵循此順序：</span><span class="sxs-lookup"><span data-stu-id="da77a-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="da77a-p121">以測試模式啟動但不顯示原則提示，然後使用 DLP 報告來評估影響。您可以使用 DLP 報告來檢視原則相符項目的號碼、位置、類型和嚴重性。根據結果，您可以視需要微調規則。在測試模式中，DLP 原則不會影響您的組織中工作人員的生產力。</span><span class="sxs-lookup"><span data-stu-id="da77a-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="da77a-p122">移至測試模式並顯示通知和原則提示，以便您開始教導使用者相關規範原則及熟悉即將套用的規則。在這個階段，您也可以要求使用者回報誤判，以便您進一步調整規則。</span><span class="sxs-lookup"><span data-stu-id="da77a-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="da77a-p123">開啟原則強制執行規則以及內容的保護。繼續進行監視 DLP 報告任何附隨報告或以確保結果是您想要的通知。</span><span class="sxs-lookup"><span data-stu-id="da77a-p123">Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![使用測試模式和開啟原則的選項](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="da77a-199">檢閱此原則設定\>選擇 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="da77a-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="da77a-200">建立並開啟 DLP 原則後，它會部署到任何內容來源，它包含如 SharePoint Online 網站或 OneDrive for Business 的帳戶原則開頭自動強制執行規則上的內容。</span><span class="sxs-lookup"><span data-stu-id="da77a-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="da77a-201">檢視 DLP 原則的狀態</span><span class="sxs-lookup"><span data-stu-id="da77a-201">View the status of a DLP policy</span></span>

<span data-ttu-id="da77a-p124">在任何時候，您可以在 [**資料外洩防護**] 區段中的安全性**原則**] 頁面上檢視狀態的 DLP 原則&amp;規範中心。您可以在這裡找到如或是否已順利啟用或停用原則原則是否已在測試模式中的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="da77a-p124">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="da77a-204">下列是不同狀態及其代表的意義。</span><span class="sxs-lookup"><span data-stu-id="da77a-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="da77a-205">**狀態**</span><span class="sxs-lookup"><span data-stu-id="da77a-205">**Status**</span></span>|<span data-ttu-id="da77a-206">**說明**</span><span class="sxs-lookup"><span data-stu-id="da77a-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da77a-207">**正在開啟…**</span><span class="sxs-lookup"><span data-stu-id="da77a-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="da77a-p125">正在將原則部署到其包含的內容來源。尚未在所有來源上強制執行此原則。</span><span class="sxs-lookup"><span data-stu-id="da77a-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="da77a-210">**測試，有通知**</span><span class="sxs-lookup"><span data-stu-id="da77a-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="da77a-p126">原則處於測試模式。不會套用規則中的動作，但會收集原則相符項目，並且可使用 DLP 報告加以檢視。原則相符項目的相關通知會傳送給指定收件者。</span><span class="sxs-lookup"><span data-stu-id="da77a-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="da77a-214">**測試，沒有通知**</span><span class="sxs-lookup"><span data-stu-id="da77a-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="da77a-p127">原則處於測試模式。不會套用規則中的動作，但會收集原則相符項目，並且可使用 DLP 報告加以檢視。原則相符項目的相關通知不會傳送給指定收件者。</span><span class="sxs-lookup"><span data-stu-id="da77a-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="da77a-218">**開啟**</span><span class="sxs-lookup"><span data-stu-id="da77a-218">**On**</span></span> <br/> |<span data-ttu-id="da77a-p128">原則在使用中且已強制執行。原則已成功部署到其所有內容來源。</span><span class="sxs-lookup"><span data-stu-id="da77a-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="da77a-221">**正在關閉…**</span><span class="sxs-lookup"><span data-stu-id="da77a-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="da77a-p129">正在將原則從其包含的內容來源移除。此原則在某些來源上仍然在作用中且已強制執行。關閉原則可能需要 45 分鐘。</span><span class="sxs-lookup"><span data-stu-id="da77a-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="da77a-225">**關閉**</span><span class="sxs-lookup"><span data-stu-id="da77a-225">**Off**</span></span> <br/> |<span data-ttu-id="da77a-p130">原則不在作用中且並未強制執行。原則的設定 (來源、關鍵字、期限等) 已儲存。</span><span class="sxs-lookup"><span data-stu-id="da77a-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="da77a-228">**刪除中...**</span><span class="sxs-lookup"><span data-stu-id="da77a-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="da77a-p131">正在刪除原則。原則不在作用中且並未強制執行。</span><span class="sxs-lookup"><span data-stu-id="da77a-p131">The policy is in the process of being deleted. The policy is not active and not enforced.</span></span>  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="da77a-231">關閉 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="da77a-231">Turn off a DLP policy</span></span>

<span data-ttu-id="da77a-p132">您可以編輯或任何時候關閉 DLP 原則。關閉原則停用所有的原則規則。</span><span class="sxs-lookup"><span data-stu-id="da77a-p132">You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="da77a-234">若要編輯或關閉 [**原則**] 頁面上的 DLP 原則\>選取原則\>**編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="da77a-234">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
![[編輯原則] 按鈕](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="da77a-236">此外，您可以關閉每個規則個別編輯原則，然後關閉該規則**狀態**切換如前文所述。</span><span class="sxs-lookup"><span data-stu-id="da77a-236">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="da77a-237">其他資訊</span><span class="sxs-lookup"><span data-stu-id="da77a-237">More information</span></span>

- [<span data-ttu-id="da77a-238">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="da77a-238">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="da77a-239">針對 DLP 原則傳送通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="da77a-239">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="da77a-240">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="da77a-240">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="da77a-241">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="da77a-241">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="da77a-242">敏感資訊類型詳細目錄</span><span class="sxs-lookup"><span data-stu-id="da77a-242">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

