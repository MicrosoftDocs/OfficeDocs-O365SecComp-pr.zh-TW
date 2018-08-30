---
title: Exchange Online 的資訊版權管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: 人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。
ms.openlocfilehash: 5036fe359215de1c2674d7efabbb283c78418a19
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002560"
---
# <a name="information-rights-management-in-exchange-online"></a><span data-ttu-id="645ea-104">Exchange Online 的資訊版權管理</span><span class="sxs-lookup"><span data-stu-id="645ea-104">Information Rights Management in Exchange Online</span></span>

<span data-ttu-id="645ea-p102">人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。</span><span class="sxs-lookup"><span data-stu-id="645ea-p102">People often use email to exchange sensitive information, such as financial data, legal contracts, confidential product information, sales reports and projections, patient health information, or customer and employee information. As a result, mailboxes can become repositories for large amounts of potentially sensitive information and information leakage can become a serious threat to your organization.</span></span>
  
<span data-ttu-id="645ea-p103">若要協助防止資訊外洩，Exchange Online 包括資訊版權管理 (IRM) 功能所提供的電子郵件訊息與附件的線上及離線保護。IRM 保護可以套用在 Microsoft Outlook 或 Outlook web 上的使用者，以及它可由系統管理員使用傳輸保護規則或 Outlook 保護規則套用。IRM 可協助您及您的使用者控制項可以存取、 轉寄、 列印或複製電子郵件中的機密資料。</span><span class="sxs-lookup"><span data-stu-id="645ea-p103">To help prevent information leakage, Exchange Online includes Information Rights Management (IRM) functionality that provides online and offline protection of email messages and attachments. IRM protection can be applied by users in Microsoft Outlook or Outlook on the web, and it can be applied by administrators using transport protection rules or Outlook protection rules. IRM helps you and your users control who can access, forward, print, or copy sensitive data within an email.</span></span>
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a><span data-ttu-id="645ea-110">IRM 與 Office 365 郵件加密 (OME) 和 Azure Active Directory 的運作方式的變更</span><span class="sxs-lookup"><span data-stu-id="645ea-110">Changes to how IRM works with Office 365 Message Encryption (OME) and Azure Active Directory</span></span>

<span data-ttu-id="645ea-p104">年 9 月 2017，當您設定新的 Office 365 郵件加密功能您的組織，您也設定 IRM 搭配 Azure 版權管理 (Azure RMS)。您無法再設定以 Azure RMS 的 IRM 分開。而是 OME 與版權管理可以順暢地搭配使用。如需詳細資訊的新功能，請參閱[Office 365 郵件加密常見問題集](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。如果您已經準備好要開始使用在組織內的新 OME 功能，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。</span><span class="sxs-lookup"><span data-stu-id="645ea-p104">As of September 2017, when you set up the new Office 365 Message Encryption capabilities for your organization, you also set up IRM for use with Azure Rights Management (Azure RMS). You no longer set up IRM with Azure RMS separately. Instead, OME and rights management work seamlessly together. For more details about the new capabilities, see [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e). If you're ready to get started using the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span>
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a><span data-ttu-id="645ea-116">IRM 與 Exchange Online 與 Active Directory Rights Management Services 的運作方式</span><span class="sxs-lookup"><span data-stu-id="645ea-116">How IRM works with Exchange Online and Active Directory Rights Management Services</span></span>

<span data-ttu-id="645ea-p105">Exchange Online IRM 使用內部部署 Active Directory Rights Management Services (AD RMS)、 Windows Server 2008 和較新版本的資訊保護技術。IRM 保護套用至電子郵件將 AD RMS 權限原則範本套用至電子郵件訊息。權限附加郵件本身使保護發生線上及離線和內部與外部組織的防火牆。</span><span class="sxs-lookup"><span data-stu-id="645ea-p105">Exchange Online IRM uses on-premises Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="645ea-p106">使用者可套用至電子郵件訊息來控制已在郵件的收件者的權限的範本。可以由將 AD RMS 權限原則套用至郵件控制動作，例如轉寄、 擷取訊息的資訊、 儲存一則訊息或列印郵件。</span><span class="sxs-lookup"><span data-stu-id="645ea-p106">Users can apply a template to an email message to control the permissions that recipients have on a message. Actions, such as forwarding, extracting information from a message, saving a message or printing a message can be controlled by applying an AD RMS rights policy to the message.</span></span>
  
<span data-ttu-id="645ea-p107">您可以設定 IRM 以使用 AD RMS 伺服器正在執行 Windows Server 2008 或更新版本。您可以使用此 AD RMS 伺服器的雲端架構組織中管理 AD RMS 權限原則範本。Outlook 也會依賴 AD RMS 伺服器以讓使用者能夠將 IRM 保護套用到傳送的訊息。如需詳細資訊，請參閱[設定 IRM 以使用內部部署 AD RMS 伺服器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。</span><span class="sxs-lookup"><span data-stu-id="645ea-p107">You can configure IRM to use an AD RMS server running Windows Server 2008 or later. You can use this AD RMS server to manage the AD RMS rights policy templates for your cloud-based organization. Outlook also relies on the AD RMS server to enable users to apply IRM protection to messages they send. For details, see [Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md).</span></span> 
  
<span data-ttu-id="645ea-126">啟用之後，您就可以依照下列方式，將 IRM 保護套用至郵件：</span><span class="sxs-lookup"><span data-stu-id="645ea-126">After it's enabled, IRM protection can be applied to messages as follows:</span></span>
  
- <span data-ttu-id="645ea-p108">**使用者可手動套用使用 Outlook 和 Outlook web 上的範本。** 使用者可以套用 AD RMS 權限原則範本至電子郵件訊息從 [**設定權限**] 清單中選取範本。當使用者傳送受 IRM 保護之訊息時、 使用的支援的格式的任何附加的檔案還會收到相同 IRM 保護郵件。IRM 保護套用至 Word、 Excel 及 PowerPoint 以及.xps 檔案和附加的電子郵件相關聯的檔案。</span><span class="sxs-lookup"><span data-stu-id="645ea-p108">**Users can manually apply a template using Outlook and Outlook on the web.** Users can apply an AD RMS rights policy template to an email message by selecting the template from the **Set permissions** list. When users send an IRM-protected message, any attached files that use a supported format also receive the same IRM protection as the message. IRM protection is applied to files associated with Word, Excel, and PowerPoint, as well as .xps files and attached email messages.</span></span> 
    
- <span data-ttu-id="645ea-p109">**系統管理員可以使用自動將 IRM 保護套用至 Outlook 和 Outlook web 上的傳輸保護規則。** 您可以建立 IRM 保護的郵件傳輸保護規則。設定 AD RMS 權限原則範本套用至符合的規則條件的郵件傳輸保護規則動作。啟用 IRM 之後，您的組織 AD RMS 權限原則範本可用搭配呼叫**套用權限保護到具有郵件**傳輸保護規則動作。</span><span class="sxs-lookup"><span data-stu-id="645ea-p109">**Administrators can use transport protection rules to apply IRM protection automatically to both Outlook and Outlook on the web.** You can create transport protection rules to IRM-protect messages. Configure the transport protection rule action to apply an AD RMS rights policy template to messages that meet the rule condition. After you enable IRM, your organization's AD RMS rights policy templates are available to use with the transport protection rule action called **Apply rights protection to the message with**.</span></span>
    
- <span data-ttu-id="645ea-p110">**系統管理員可以建立 Outlook protection rules。** Outlook 保護規則會自動將 IRM 保護套用至根據郵件條件來包含寄件者的部門將郵件傳送給、 Outlook 2010 (不在網路上的 Outlook) 中郵件和收件者位於內部或外部您組織。如需詳細資訊，請參閱 ＜ [Create Outlook 保護規則](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx)。</span><span class="sxs-lookup"><span data-stu-id="645ea-p110">**Administrators can create Outlook protection rules.** Outlook protection rules automatically apply IRM-protection to messages in Outlook 2010 (not Outlook on the web) based on message conditions that include the sender's department, who the message is sent to, and whether recipients are inside or outside your organization. For details, see [Create an Outlook Protection Rule](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).</span></span>
    

