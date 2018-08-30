---
title: 套用至清單或文件庫的資訊版權管理 (IRM)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
description: 您可以使用資訊版權管理 (IRM) 協助控制及保護從清單或文件庫下載的檔案。
ms.openlocfilehash: 5a48abf13841716d4dba34311d69ca2e6a5ea422
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526683"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="b71bb-103">套用至清單或文件庫的資訊版權管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="b71bb-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="b71bb-104">您可以使用資訊版權管理 (IRM) 協助控制及保護從清單或文件庫下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="b71bb-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b71bb-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="b71bb-105">Before you begin</span></span>

- <span data-ttu-id="b71bb-p101">Azure 版權管理服務 (Azure RMS) 從 Azure 資訊保護及內部同等 Active Directory Rights Management Services (AD RMS) 支援資訊版權管理的網站。沒有不同或其他安裝所需。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p101">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites. No separate or additional installations are required.</span></span>
    
- <span data-ttu-id="b71bb-108">將 IRM 套用至清單或文件庫之前它必須先啟用您的網站管理員。</span><span class="sxs-lookup"><span data-stu-id="b71bb-108">Before you apply IRM to a list or library it must first be enabled by an administrator for your site.</span></span>
    
- <span data-ttu-id="b71bb-109">若要套用至清單或文件庫的 IRM，您必須具備清單或文件庫的管理員權的限。</span><span class="sxs-lookup"><span data-stu-id="b71bb-109">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>
    
- <span data-ttu-id="b71bb-p102">如果您使用 SharePoint Online，讓使用者下載較大的受 IRM 保護之檔案時可能會發生逾時。如果發生這種情況，然後使用您的 Office 程式套用 IRM 保護及較大的檔案儲存在不使用 IRM 的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p102">If you are using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files. If this happens, then apply IRM protection by using your Office programs, and store larger files in a SharePoint library that does not use IRM.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b71bb-112">如果您使用 SharePoint Server 2013，伺服器管理員必須在所有前端網頁伺服器的每一個您組織中的人員想要使用 IRM 保護的檔案類型安裝保護裝置。</span><span class="sxs-lookup"><span data-stu-id="b71bb-112">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span> 
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="b71bb-113">套用至清單或文件庫的 IRM</span><span class="sxs-lookup"><span data-stu-id="b71bb-113">Apply IRM to a list or library</span></span>
<span data-ttu-id="b71bb-114"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="b71bb-114"></span></span>

![資訊版權管理設定](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="b71bb-116">移至您要設定 IRM 的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="b71bb-116">Go to the list or library for which you want to configure IRM.</span></span>
    
2. <span data-ttu-id="b71bb-p103">在功能區] 上按一下 [**文件庫**] 索引標籤和 [**文件庫設定**。（如果您正在工作清單中，按一下 [**清單**] 索引標籤和 [**清單設定**。）</span><span class="sxs-lookup"><span data-stu-id="b71bb-p103">On the ribbon, click the **Library** tab, and then click **Library Settings**. (If you are working in a list, click the **List** tab, and then click **List Settings**).</span></span>
    
    ![在功能區上的 [SharePoint 文件庫設定] 按鈕](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="b71bb-p104">在 [**權限與管理**] 按一下 [**資訊版權管理**]。如果未出現 [資訊版權管理] 連結，您網站可能未啟用 IRM。請連絡您的伺服器管理員以查看是否可以為網站啟用 IRM。資訊版權管理連結不會出現圖片庫。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p104">Under **Permissions and Management**, click **Information Rights Management**. If the Information Rights Management link does not appear, IRM might not be enabled for your site. Contact your server administrator to see if it is possible to enable IRM for your site. The Information Rights Management link does not appear for picture libraries.</span></span>
    
4. <span data-ttu-id="b71bb-124">在 [**資訊版權管理設定**] 頁面上選取 [限制權限套用到此清單或文件庫下載的文件的 [**限制下載此文件庫中的文件的權限**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-124">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents that are downloaded from this list or library.</span></span> 
    
5. <span data-ttu-id="b71bb-p105">在 [**建立權限原則標題**] 方塊中輸入您可以稍後使用來區分此原則的其他原則原則的描述性名稱。例如，您可以輸入**公司機密**如果限制權限套用至清單或文件庫，將會包含機密公司文件。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p105">In the **Create a permission policy title** box, type a descriptive name for the policy that you can use later to differentiate this policy from other policies. For example, you can type **Company Confidential** if you are applying restricted permission to a list or library that will contain company documents that are confidential.</span></span> 
    
6. <span data-ttu-id="b71bb-p106">在 [**新增權限原則描述**] 方塊中輸入要使用此清單或文件庫的說明時應如何處理此清單或文件庫中的文件的人員顯示的描述。例如，您可以輸入**討論只能與其他員工此文件的內容**如果您想要限制存取權給內部員工這些文件中的資訊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p106">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library. For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 
    
7. <span data-ttu-id="b71bb-129">若要將其他限制套用到此清單或文件庫中的文件、 [**顯示選項**]，並執行下列任一項：</span><span class="sxs-lookup"><span data-stu-id="b71bb-129">To apply additional restrictions to the documents in this list or library, click **Show Options**, and do any of the following:</span></span>
    
|<span data-ttu-id="b71bb-130">**若要執行這項作業：**</span><span class="sxs-lookup"><span data-stu-id="b71bb-130">**To do this:**</span></span>|<span data-ttu-id="b71bb-131">**執行這項作業：**</span><span class="sxs-lookup"><span data-stu-id="b71bb-131">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b71bb-132">允許其他人從這個清單或文件庫中列印文件</span><span class="sxs-lookup"><span data-stu-id="b71bb-132">Allow people to print documents from this list or library</span></span>  <br/> |<span data-ttu-id="b71bb-133">選取**要列印的允許檢視器**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-133">Select the **Allow viewers to print** check box.</span></span>  <br/> |
|<span data-ttu-id="b71bb-134">允許人員具有至少文件上執行內嵌程式碼或巨集的 [檢視項目] 權限。</span><span class="sxs-lookup"><span data-stu-id="b71bb-134">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>  <br/> |<span data-ttu-id="b71bb-135">選取 [**檢視程式才能執行指令碼及螢幕讀者在下載文件的函數**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-135">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.</span></span>  <br/> <span data-ttu-id="b71bb-136">如果您選取這個選項，使用者無法執行程式碼來將擷取的文件內容。</span><span class="sxs-lookup"><span data-stu-id="b71bb-136">If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="b71bb-137">需要的人員確認其認證的特定的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="b71bb-137">Require that people verify their credentials at specific intervals.</span></span>  <br/> <span data-ttu-id="b71bb-p107">如果您想要限制存取權在指定期間的內容，選取這個選項。如果您選取這個選項，才能存取內容的人的發行授權即將到期後指定之的數目及時人員都必須回到驗證其認證及下載的新複本的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p107">Select this option if you want to restrict access to content to a specified period of time. If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>  <br/> |<span data-ttu-id="b71bb-140">選取 [**使用者必須先確認他們使用此間隔的認證 （天）** 核取方塊，並再指定您想要讓使用者可以檢視的文件的天數。</span><span class="sxs-lookup"><span data-stu-id="b71bb-140">Select the **Users must verify their credentials using this interval (days)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>  <br/> |
| <span data-ttu-id="b71bb-141">防止人員上傳到此清單或文件庫不支援 IRM 的文件。</span><span class="sxs-lookup"><span data-stu-id="b71bb-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span>  <br/>  <span data-ttu-id="b71bb-142">如果您選取此選項時，人員將無法上傳任何下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="b71bb-142">If you select this option, people will not be able to upload any of the following file types:</span></span>  <br/>  <span data-ttu-id="b71bb-143">沒有對應的 IRM 保護裝置在所有前端網頁伺服器上安裝的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b71bb-143">File types that do not have corresponding IRM protectors installed on all of the front-end Web servers.</span></span>  <br/>  <span data-ttu-id="b71bb-144">SharePoint Server 2010 無法解密的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b71bb-144">File types that SharePoint Server 2010 cannot decrypt.</span></span>  <br/>  <span data-ttu-id="b71bb-145">會在另一個程式中受保護的 IRM 的檔案類型</span><span class="sxs-lookup"><span data-stu-id="b71bb-145">File types that are IRM protected in another program</span></span>  <br/> |<span data-ttu-id="b71bb-146">選取 [**不允許使用者上傳的不支援 IRM 的文件**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-146">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>  <br/> |
|<span data-ttu-id="b71bb-147">移除受限制權限此清單或文件庫上特定日期。</span><span class="sxs-lookup"><span data-stu-id="b71bb-147">Remove restricted permissions from this list or library on a specific date.</span></span>  <br/> |<span data-ttu-id="b71bb-148">選取 [**停止限制在文件庫的存取**] 核取方塊，然後再選取 [您想要的日期。</span><span class="sxs-lookup"><span data-stu-id="b71bb-148">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>  <br/> |
|<span data-ttu-id="b71bb-149">控制項之程式開啟文件的授權快取認證的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="b71bb-149">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>  <br/> |<span data-ttu-id="b71bb-150">在**設定群組保護和認證間隔**輸入 theinterval 快取中的天數的認證。</span><span class="sxs-lookup"><span data-stu-id="b71bb-150">In the **Set group protection and credentials interval**, enter theinterval for caching credentials in number of days.</span></span>  <br/> |
|<span data-ttu-id="b71bb-151">允許群組保護，讓使用者可以共用相同的群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b71bb-151">Allow group protection so that users can share with members of the same group.</span></span>  <br/> |<span data-ttu-id="b71bb-152">選取 [**允許群組保護**，然後輸入共用的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="b71bb-152">Select **Allow group protection**, and enter the group's name for sharing.</span></span>  <br/> |
   
8. <span data-ttu-id="b71bb-153">選取您要的選項之後，請按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b71bb-153">After you finish selecting the options you want, click **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="b71bb-154">資訊版權管理新功能</span><span class="sxs-lookup"><span data-stu-id="b71bb-154">What is Information Rights Management?</span></span>
<span data-ttu-id="b71bb-155"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="b71bb-155"></span></span>

<span data-ttu-id="b71bb-p108">資訊版權管理 (IRM) 可讓您限制使用者可以對已從清單或文件庫下載的檔案採取的動作。IRM 加密下載的檔案並限制的使用者和允許解密這些檔案的程式]。IRM 也可以限制的權限的使用者可以讀取檔案，使其無法採取動作，例如列印份數的檔案或從這些複製文字。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p108">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries. IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files. IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="b71bb-p109">您可以使用清單或文件庫上的 IRM 限制機密內容的散佈。例如，如果您建立文件庫與所選的行銷代表共用即將來臨的產品的相關資訊，您可以使用 IRM 防止這些個人共用此內容與其他公司內的員工。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p109">You can use IRM on lists or libraries to limit the dissemination of sensitive content. For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="b71bb-p110">在網站上，您會套用 IRM 整個清單或文件庫，而不是個別的檔案。這會使確保一致的保護層級的整個集的文件或檔案更容易。IRM 如此可協助您的組織來強制執行管理及散佈的機密或專屬資訊的公司原則。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p110">On a site, you apply IRM to an entire list or library, rather than to individual files. This makes it easier to ensure a consistent level of protection for an entire set of documents or files. IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b71bb-164">本頁內容資訊版權管理的相關資訊的任何 Microsoft SharePoint Server 2013 與 SharePoint Server 2016 授權字詞協議替代任何參照 「 資訊版權管理 」 的字詞。</span><span class="sxs-lookup"><span data-stu-id="b71bb-164">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="b71bb-165">IRM 如何協助保護內容</span><span class="sxs-lookup"><span data-stu-id="b71bb-165">How IRM can help protect content</span></span>
<span data-ttu-id="b71bb-166"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="b71bb-166"></span></span>

<span data-ttu-id="b71bb-167">IRM 可協助保護受限制的內容如下：</span><span class="sxs-lookup"><span data-stu-id="b71bb-167">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="b71bb-168">有助於防止從複製、 修改、 列印、 傳真、 或複製並貼上未經授權的使用的內容授權檢視器</span><span class="sxs-lookup"><span data-stu-id="b71bb-168">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="b71bb-169">若要防止使用 Print Screen 功能在 Microsoft Windows 中複製的內容已授權的檢視器可協助</span><span class="sxs-lookup"><span data-stu-id="b71bb-169">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="b71bb-170">若要防止未經授權的檢視器如果它從伺服器下載之後傳送電子郵件中檢視的內容可協助</span><span class="sxs-lookup"><span data-stu-id="b71bb-170">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="b71bb-171">在指定期間內的時間之後，使用者必須確認其認證並再次下載內容的內容會限制存取</span><span class="sxs-lookup"><span data-stu-id="b71bb-171">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="b71bb-172">協助強制執行公司原則的管理及散佈的組織內的內容</span><span class="sxs-lookup"><span data-stu-id="b71bb-172">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="b71bb-173">IRM 不能如何協助保護內容</span><span class="sxs-lookup"><span data-stu-id="b71bb-173">How IRM cannot help protect content</span></span>
<span data-ttu-id="b71bb-174"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="b71bb-174"></span></span>

<span data-ttu-id="b71bb-175">IRM 無法防止受限制的內容下列：</span><span class="sxs-lookup"><span data-stu-id="b71bb-175">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="b71bb-176">清除、 竊取、 擷取或由如特洛伊木馬、 按鍵記錄器及間諜軟體特定類型的惡意程式傳輸</span><span class="sxs-lookup"><span data-stu-id="b71bb-176">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="b71bb-177">遺失或損毀因為電腦病毒的動作</span><span class="sxs-lookup"><span data-stu-id="b71bb-177">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="b71bb-178">手動複製或重新輸入的內容從螢幕顯示</span><span class="sxs-lookup"><span data-stu-id="b71bb-178">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="b71bb-179">數位或網片攝影的螢幕顯示的內容</span><span class="sxs-lookup"><span data-stu-id="b71bb-179">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="b71bb-180">透過協力廠商螢幕擷取程式複製</span><span class="sxs-lookup"><span data-stu-id="b71bb-180">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="b71bb-181">複製的內容中繼資料 （資料行值） 透過協力廠商螢幕擷取程式或複製並貼上巨集指令</span><span class="sxs-lookup"><span data-stu-id="b71bb-181">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="b71bb-182">將資訊版權管理套用至清單或文件庫</span><span class="sxs-lookup"><span data-stu-id="b71bb-182">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="b71bb-183">IRM 清單和文件庫的運作方式</span><span class="sxs-lookup"><span data-stu-id="b71bb-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="b71bb-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="b71bb-184"></span></span>

<span data-ttu-id="b71bb-p111">IRM 保護套用至清單或文件庫層級的檔案。當文件庫啟用 IRM 時，版權管理會套用於所有的文件庫中的檔案。當清單啟用 IRM 時，版權管理只適用於清單項目不實際的清單項目附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p111">IRM protection is applied to files at the list or library level. When IRM is enabled for a library, rights management applies to all of the files in that library. When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="b71bb-p112">當人員下載中啟用 IRM 的清單或文件庫的檔案時，以便只授權的人員可檢視它們加密檔案。每個受版權管理檔案也包含會限制在檢視之檔案的人員的發行授權。一般限制包括唯讀屬性，停用的文字，防止人員從儲存的本機複本，並防止人員列印檔案複製進行檔案。可讀取的 IRM 支援的檔案類型的用戶端程式受版權管理檔案內使用的發行授權強制執行這些限制。這是如何受版權管理檔案會保留在其保護即使它從伺服器下載。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p112">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="b71bb-p113">從清單或文件庫下載時套用至檔案的限制類型根據包含該檔案的網站上的個別使用者的權限。下表說明如何在網站上的權限對應至 IRM 權限。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p113">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file. The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="b71bb-195">**權限**</span><span class="sxs-lookup"><span data-stu-id="b71bb-195">**Permissions**</span></span>|<span data-ttu-id="b71bb-196">**IRM 權限**</span><span class="sxs-lookup"><span data-stu-id="b71bb-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b71bb-197">管理權限、 管理網站</span><span class="sxs-lookup"><span data-stu-id="b71bb-197">Manage Permissions, Manage Web Site</span></span>  <br/> |<span data-ttu-id="b71bb-198">**完全控制**（如用戶端程式所定義）： 這個權限通常可讓使用者讀取、 編輯、 複製、 儲存及修改受版權管理內容的權限。</span><span class="sxs-lookup"><span data-stu-id="b71bb-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>  <br/> |
|<span data-ttu-id="b71bb-199">編輯項目、 管理清單、 新增並自訂頁面</span><span class="sxs-lookup"><span data-stu-id="b71bb-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>  <br/> |<span data-ttu-id="b71bb-200">**編輯**、**複製**及**儲存**： 使用者可以列印檔案只有當在清單或文件庫的資訊版權管理設定] 頁面上選取 [**允許使用者列印文件**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="b71bb-201">檢視項目</span><span class="sxs-lookup"><span data-stu-id="b71bb-201">View Items</span></span>  <br/> |<span data-ttu-id="b71bb-p114">**讀取**： 使用者可以讀取文件，但無法複製或修改其內容。使用者可以列印只有當在清單或文件庫的資訊版權管理設定] 頁面上選取 [**允許使用者列印文件**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b71bb-p114">**Read**: A user can read the document, but cannot copy or modify its content. A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.  </span></span><br/> |
|<span data-ttu-id="b71bb-204">其他</span><span class="sxs-lookup"><span data-stu-id="b71bb-204">Other</span></span>  <br/> |<span data-ttu-id="b71bb-205">沒有其他權限會直接對應到 IRM 權限。</span><span class="sxs-lookup"><span data-stu-id="b71bb-205">No other permissions correspond directly to IRM permissions.</span></span>  <br/> |
   
<span data-ttu-id="b71bb-p115">當您針對清單或文件庫在 SharePoint Server 2013 中的啟用 IRM 時，您可以僅保護清單或文件庫的所有前端網頁伺服器安裝保護裝置中的檔案類型。保護裝置是控制加密與解密的受版權管理的特定檔案格式的檔案計畫。SharePoint 包含下列檔案類型的保護裝置：</span><span class="sxs-lookup"><span data-stu-id="b71bb-p115">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end Web servers. A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format. SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="b71bb-209">Microsoft Office InfoPath 表單</span><span class="sxs-lookup"><span data-stu-id="b71bb-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="b71bb-210">下列的 Microsoft Office 程式 97-2003年檔案格式： Word、 Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b71bb-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="b71bb-211">Office Open XML 格式的下列的 Microsoft Office 程式： Word、 Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b71bb-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="b71bb-212">XML Paper Specification (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="b71bb-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="b71bb-213">如果您的組織計劃使用 IRM 保護除了上列以外的其他檔案類型]，伺服器管理員必須安裝保護裝置這些其他檔案格式。</span><span class="sxs-lookup"><span data-stu-id="b71bb-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

