---
title: 將您組織的品牌新增至您的加密郵件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 身為 Office 365 全域管理員，您可以套用貴組織的品牌貴組織的加密的電子郵件和加密入口網站的內容。
ms.openlocfilehash: 6b51aefc10c0070749fcf4bc8c2d56c7ff7a3ef3
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152465"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="fff74-103">將貴組織的品牌新增至您的加密郵件</span><span class="sxs-lookup"><span data-stu-id="fff74-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="fff74-104">以 Exchange Online 或 Exchange Online Protection 系統管理員身分，您可以套用貴公司商標新增至自訂貴組織的 Office 365 郵件加密電子郵件的外觀和加密入口網站的內容。</span><span class="sxs-lookup"><span data-stu-id="fff74-104">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the encryption portal.</span></span> <span data-ttu-id="fff74-105">使用 Get-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet，您可以自訂加密的電子郵件的收件者的檢視體驗的下列層面：</span><span class="sxs-lookup"><span data-stu-id="fff74-105">Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="fff74-106">包含加密訊息的電子郵件簡介文字</span><span class="sxs-lookup"><span data-stu-id="fff74-106">Introductory text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="fff74-107">包含加密訊息的電子郵件免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="fff74-107">Disclaimer text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="fff74-108">OME 入口網站中出現的文字</span><span class="sxs-lookup"><span data-stu-id="fff74-108">Text that appears in the OME portal</span></span>

- <span data-ttu-id="fff74-109">會出現在電子郵件訊息和 OME 入口網站的標誌</span><span class="sxs-lookup"><span data-stu-id="fff74-109">Logo that appears in the email message and OME portal</span></span>

- <span data-ttu-id="fff74-110">在電子郵件訊息和 OME 入口網站的背景色彩</span><span class="sxs-lookup"><span data-stu-id="fff74-110">Background color in the email message and OME portal</span></span>

<span data-ttu-id="fff74-111">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="fff74-111">You can also revert back to the default look and feel at any time.</span></span>

 <span data-ttu-id="fff74-112">如果您想要更多控制，您可以使用 Office 365 進階郵件加密，並建立多個範本來自您組織的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fff74-112">If you'd like more control, you can use Office 365 Advanced Message Encryption and create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="fff74-113">使用這些範本，您可以控制不只是電子郵件、 外觀與風格，但也可以控制使用者經驗的部分。</span><span class="sxs-lookup"><span data-stu-id="fff74-113">Using these templates, you can control more than just the look and feel of the email messages, but also control parts of the end-user experience.</span></span> <span data-ttu-id="fff74-114">例如，您可以指定收件者的郵件套用此範本，而且誰使用 Google、 Yahoo，以及 Microsoft 帳戶可以使用這些帳戶來登入 Office 365 郵件加密入口網站。</span><span class="sxs-lookup"><span data-stu-id="fff74-114">For example, you can specify whether or not recipients of mail that have this template applied and who use Google, Yahoo, and Microsoft Accounts can use these accounts to sign in to the Office 365 Message Encryption portal.</span></span> <span data-ttu-id="fff74-115">您可以使用範本來滿足幾個使用情況下，例如：</span><span class="sxs-lookup"><span data-stu-id="fff74-115">You might use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="fff74-116">每個部門，例如財務、 銷售等的範本。</span><span class="sxs-lookup"><span data-stu-id="fff74-116">Templates for each department, such as Finance, Sales, etc.</span></span>

- <span data-ttu-id="fff74-117">不同產品的範本</span><span class="sxs-lookup"><span data-stu-id="fff74-117">Templates for different products</span></span>

- <span data-ttu-id="fff74-118">不同地理區域或國家/地區的範本</span><span class="sxs-lookup"><span data-stu-id="fff74-118">Templates for different geographical regions or countries</span></span>

- <span data-ttu-id="fff74-119">是否要允許要撤銷的電子郵件</span><span class="sxs-lookup"><span data-stu-id="fff74-119">Whether or not you want to allow emails to be revoked</span></span>

- <span data-ttu-id="fff74-120">是否要傳送給外部收件者，以在指定天數後過期的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fff74-120">Whether or not you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="fff74-121">一旦您已經建立範本，您可以套用至已加密的電子郵件使用 Exchange 郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="fff74-121">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="fff74-122">如果您有 Office 365 進階郵件加密，您可以撤銷任何已品牌使用這些範本的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fff74-122">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>
  
||
|:-----|
|<span data-ttu-id="fff74-123">本文屬於較大的一連串的 Office 365 郵件加密的相關文章。</span><span class="sxs-lookup"><span data-stu-id="fff74-123">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="fff74-124">本文適用於系統管理員和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="fff74-124">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="fff74-125">如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="fff74-125">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span>|
||

## <a name="create-branding-templates"></a><span data-ttu-id="fff74-126">建立品牌的範本</span><span class="sxs-lookup"><span data-stu-id="fff74-126">Create branding templates</span></span>

<span data-ttu-id="fff74-127">您為組織中使用 Windows PowerShell 新增 Set-omeconfiguration 指令程式建立品牌的範本。</span><span class="sxs-lookup"><span data-stu-id="fff74-127">You create branding templates for your organization in Windows PowerShell with the New-OMEConfiguration cmdlet.</span></span> <span data-ttu-id="fff74-128">一旦您已經建立該範本，您可以使用 Set-omeconfiguration 指令程式定義之範本的部分。</span><span class="sxs-lookup"><span data-stu-id="fff74-128">Once you've created the template, you define the pieces of the template by using the Set-OMEConfiguration cmdlet.</span></span> <span data-ttu-id="fff74-129">您可以建立多個範本。</span><span class="sxs-lookup"><span data-stu-id="fff74-129">You can create multiple templates.</span></span>

![可自訂電子郵件組件](media/ome-template-breakout.png)
  
1. <span data-ttu-id="fff74-131">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="fff74-131">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="fff74-132">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="fff74-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="fff74-133">使用新增 Set-omeconfiguration 指令程式來建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="fff74-133">Use the New-OMEConfiguration cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   <span data-ttu-id="fff74-134">For example,</span><span class="sxs-lookup"><span data-stu-id="fff74-134">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity <Branding template 1>
   ```

3. <span data-ttu-id="fff74-135">定義您定義使用 Set-omeconfiguration 指令程式[Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)所述之範本所做的自訂或使用下表取得指引。</span><span class="sxs-lookup"><span data-stu-id="fff74-135">Define the customizations for the template you just defined by using the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) or use the following table for guidance.</span></span>

|<span data-ttu-id="fff74-136">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="fff74-136">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="fff74-137">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="fff74-137">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fff74-138">背景色彩</span><span class="sxs-lookup"><span data-stu-id="fff74-138">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="fff74-139">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-139">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|<span data-ttu-id="fff74-140">商標</span><span class="sxs-lookup"><span data-stu-id="fff74-140">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="fff74-141">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-141">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="fff74-142">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="fff74-142">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="fff74-143">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="fff74-143">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="fff74-144">標誌影像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="fff74-144">Optimal size of logo image: 170x70 pixels</span></span>|
|<span data-ttu-id="fff74-145">寄件者的名稱和電子郵件地址] 旁的文字</span><span class="sxs-lookup"><span data-stu-id="fff74-145">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="fff74-146">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-146">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="fff74-147">「 讀取的郵件 」 按鈕顯示的文字</span><span class="sxs-lookup"><span data-stu-id="fff74-147">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="fff74-148">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-148">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="fff74-149">欄上方會出現在 「 讀取的郵件 」 按鈕下方的文字</span><span class="sxs-lookup"><span data-stu-id="fff74-149">Text that appears above below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="fff74-150">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-150">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="fff74-151">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="fff74-151">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="fff74-152">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-152">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="fff74-153">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="fff74-153">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="fff74-154">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-154">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="fff74-155">若要啟用或停用驗證，使用此自訂範本次傳遞程式碼</span><span class="sxs-lookup"><span data-stu-id="fff74-155">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="fff74-156">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-156">**Examples:**</span></span> <br/><span data-ttu-id="fff74-157">若要啟用一次性密碼此自訂範本</span><span class="sxs-lookup"><span data-stu-id="fff74-157">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="fff74-158">若要停用一次性密碼此自訂範本</span><span class="sxs-lookup"><span data-stu-id="fff74-158">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="fff74-159">若要啟用或停用此自訂範本的 Microsoft、 Google 或 Yahoo 身分識別與驗證</span><span class="sxs-lookup"><span data-stu-id="fff74-159">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="fff74-160">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-160">**Examples:**</span></span> <br/><span data-ttu-id="fff74-161">若要啟用此自訂範本的社交識別碼</span><span class="sxs-lookup"><span data-stu-id="fff74-161">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="fff74-162">若要停用社交此自訂的範本識別碼</span><span class="sxs-lookup"><span data-stu-id="fff74-162">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a><span data-ttu-id="fff74-163">若要移除依 OME 加密 OME 入口網站和電子郵件訊息的品牌自訂內容</span><span class="sxs-lookup"><span data-stu-id="fff74-163">To remove brand customizations from the OME portal and email messages encrypted by OME</span></span>
  
1. <span data-ttu-id="fff74-164">[連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="fff74-164">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="fff74-165">[Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)所述，請使用**Set-omeconfiguration**指令程式。</span><span class="sxs-lookup"><span data-stu-id="fff74-165">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration).</span></span> <span data-ttu-id="fff74-166">若要移除您組織的品牌自訂項目從 DisclaimerText，EmailText，和 PortalText 值，將值設定為空字串， `""`。</span><span class="sxs-lookup"><span data-stu-id="fff74-166">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`.</span></span> <span data-ttu-id="fff74-167">針對所有影像值，例如標誌，將值設為`"$null"`。</span><span class="sxs-lookup"><span data-stu-id="fff74-167">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

<span data-ttu-id="fff74-168">**加密自訂選項**</span><span class="sxs-lookup"><span data-stu-id="fff74-168">**Encryption customization options**</span></span>

<span data-ttu-id="fff74-169">**將加密體驗的這項功能回復為預設文字和影像**</span><span class="sxs-lookup"><span data-stu-id="fff74-169">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="fff74-170">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="fff74-170">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fff74-171">加密電子郵件隨附的預設文字</span><span class="sxs-lookup"><span data-stu-id="fff74-171">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="fff74-172">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="fff74-172">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="fff74-173">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-173">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|<span data-ttu-id="fff74-174">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="fff74-174">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="fff74-175">**範例：**</span><span class="sxs-lookup"><span data-stu-id="fff74-175">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|<span data-ttu-id="fff74-176">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="fff74-176">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="fff74-177">**範例回還原預設值：**</span><span class="sxs-lookup"><span data-stu-id="fff74-177">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|<span data-ttu-id="fff74-178">商標</span><span class="sxs-lookup"><span data-stu-id="fff74-178">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="fff74-179">**範例回還原預設值：**</span><span class="sxs-lookup"><span data-stu-id="fff74-179">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|<span data-ttu-id="fff74-180">背景色彩</span><span class="sxs-lookup"><span data-stu-id="fff74-180">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="fff74-181">**範例回還原預設值：**</span><span class="sxs-lookup"><span data-stu-id="fff74-181">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a><span data-ttu-id="fff74-182">建立適用於 Exchange 郵件流程規則將自訂品牌對加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="fff74-182">Create an Exchange mail flow rule that applies custom branding to encrypted emails</span></span>

<span data-ttu-id="fff74-183">您已建立的品牌的範本後，您可以建立 Exchange 郵件流程規則來套用該自訂品牌根據特定條件。</span><span class="sxs-lookup"><span data-stu-id="fff74-183">After you've created a branding template, you can create Exchange mail flow rules to apply that custom branding based on certain conditions.</span></span> <span data-ttu-id="fff74-184">在下列案例中的自訂品牌套用這類規則：</span><span class="sxs-lookup"><span data-stu-id="fff74-184">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="fff74-185">如果電子郵件以手動方式加密的使用者從 Outlook 或網頁 （原先稱為 Outlook Web App） 用戶端</span><span class="sxs-lookup"><span data-stu-id="fff74-185">If the email was manually encrypted by the end-user from the Outlook or Outlook on the web (formerly known as Outlook Web App) clients</span></span>

- <span data-ttu-id="fff74-186">如果電子郵件會自動加密的 Exchange 郵件流程規則] 或 [Office 365 資料外洩防護原則</span><span class="sxs-lookup"><span data-stu-id="fff74-186">If the email was automatically encrypted by an Exchange Mail Flow rule or Office 365 Data Loss Prevention policy</span></span>

<span data-ttu-id="fff74-187">如需如何建立適用於加密 Exchange 郵件流程規則的詳細資訊，請參閱 <<c0>定義郵件流規則以加密 Office 365 中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fff74-187">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="fff74-188">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="fff74-188">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="fff74-189">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="fff74-189">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="fff74-190">在 Office 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="fff74-190">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="fff74-191">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="fff74-191">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="fff74-192">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="fff74-192">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="fff74-193">在 [**名稱**] 中，輸入規則名稱，例如銷售部門的品牌。</span><span class="sxs-lookup"><span data-stu-id="fff74-193">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="fff74-194">在 [**套用此規則，如果**選擇一個條件，從可用的條件清單中選取 [**寄件者位於在組織內**的條件，以及其他您想要的條件。</span><span class="sxs-lookup"><span data-stu-id="fff74-194">In **Apply this rule if** select a condition, select the condition **The sender is located inside the organization** as well as other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="fff74-195">例如，您可能想要套用特定的品牌範本，以：</span><span class="sxs-lookup"><span data-stu-id="fff74-195">For example, you might want to apply a particular branding template to:</span></span>

     - <span data-ttu-id="fff74-196">所有加密的電子郵件寄件者的財務部門成員</span><span class="sxs-lookup"><span data-stu-id="fff74-196">All encrypted emails sent from members of the finance department</span></span>
     - <span data-ttu-id="fff74-197">與特定關鍵字例如 「 外部 」 或 「 夥伴 」 傳送加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="fff74-197">Encrypted emails sent with a certain keyword such as “External” or “Partner”</span></span>
     - <span data-ttu-id="fff74-198">加密的電子郵件傳送至特定網域</span><span class="sxs-lookup"><span data-stu-id="fff74-198">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="fff74-199">從**執行下列動作**，選取 [**修改郵件安全性** > **套用自訂商標至 OME 郵件**。</span><span class="sxs-lookup"><span data-stu-id="fff74-199">From **Do the following**, select **Modify the message security** > **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="fff74-200">接下來，從下拉式清單中，選取與您所建立的品牌範本。</span><span class="sxs-lookup"><span data-stu-id="fff74-200">Next, from the drop-down, select a branding template from those that you created.</span></span>

8. <span data-ttu-id="fff74-201">（選用）如果您想郵件流程規則，以也適用於加密除了自訂品牌，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇 [**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="fff74-201">(Optional) If you want the mail flow rule to also apply encryption in addition to the custom branding, From **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="fff74-202">從清單中選取的 RMS 範本，選擇 [**儲存**]，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="fff74-202">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
     <span data-ttu-id="fff74-203">範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="fff74-203">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="fff74-204">如果清單是空的請確定您已設定 Office 365 郵件加密與新功能[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。</span><span class="sxs-lookup"><span data-stu-id="fff74-204">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="fff74-205">如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="fff74-205">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="fff74-206">[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="fff74-206">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="fff74-207">[**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="fff74-207">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

     <span data-ttu-id="fff74-208">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="fff74-208">You can choose **add action** if you want to specify another action.</span></span>
