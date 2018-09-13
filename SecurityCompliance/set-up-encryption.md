---
title: 設定 Office 365 企業版中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 使用 Office 365 某些加密功能的預設開啟;其他功能可以設定成符合特定規範或法律規定。
ms.openlocfilehash: 80deced80283ac36d82ac15cee9af6d390c4749a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526502"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a><span data-ttu-id="8f612-103">設定 Office 365 企業版中的加密</span><span class="sxs-lookup"><span data-stu-id="8f612-103">Set up encryption in Office 365 Enterprise</span></span>

<span data-ttu-id="8f612-p101">加密可以從所讀取的未經授權的使用者來保護您的內容。因為您可以選擇[加密 Office 365 中的](encryption.md)使用各種不同的技術和方法，沒有一個單一位置供您開啟或加密設定。本文提供您可以設定或加密設定的資訊保護策略的一部分的各種方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8f612-p101">Encryption can protect your content from being read by unauthorized users. Because [encryption in Office 365](encryption.md) can be done using various technologies and methods, there isn't one single place where you turn on or set up encryption. This article provides information about various ways you can set up or configure encryption as part of your information protection strategy.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8f612-107">如果您要尋找更多技術加密的相關的詳細資訊，請參閱[Office 365 中加密的相關的技術參考 （英文） 詳細資料](technical-reference-details-about-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="8f612-107">If you are looking for more technical details about encryption, see [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).</span></span> 
  
<span data-ttu-id="8f612-p102">Office 365 的數種加密功能預設可用。其他加密功能可以設定成符合特定規範或法律規定。下表說明針對不同案例的數種加密方法。</span><span class="sxs-lookup"><span data-stu-id="8f612-p102">With Office 365, several encryption capabilities are available by default. Additional encryption capabilities can be configured to meet certain compliance or legal requirements. The following table describes several encryption methods for different scenarios.</span></span>
  
|<span data-ttu-id="8f612-111">**案例**</span><span class="sxs-lookup"><span data-stu-id="8f612-111">**Scenario**</span></span>|<span data-ttu-id="8f612-112">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="8f612-112">**Encryption Methods**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f612-113">檔案都儲存在 Windows 電腦上</span><span class="sxs-lookup"><span data-stu-id="8f612-113">Files are saved on Windows computers</span></span>  <br/> |<span data-ttu-id="8f612-p103">您可以選擇加密層級的電腦上 Windows 裝置使用 BitLocker。為企業系統管理員或 IT 專業人員，您可以設定此使用 Microsoft Deployment Toolkit (MDT)。請參閱 ＜ [Set up MDT 的 BitLocker](https://go.microsoft.com/fwlink/?linkid=849282)。</span><span class="sxs-lookup"><span data-stu-id="8f612-p103">Encryption at the computer level can be done using BitLocker on Windows devices. As an enterprise administrator or IT Pro, you can set this up using the Microsoft Deployment Toolkit (MDT). See [Set up MDT for BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  </span></span><br/> |
|<span data-ttu-id="8f612-117">檔案都儲存在行動裝置上</span><span class="sxs-lookup"><span data-stu-id="8f612-117">Files are saved on mobile devices</span></span>  <br/> |<span data-ttu-id="8f612-p104">某些類型的行動裝置加密預設儲存至那些裝置的檔案。使用[內建行動裝置管理 Office 365 的功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)，您可以設定原則決定是否要讓行動裝置能夠存取 Office 365 中的資料。例如，您可以設定原則允許裝置的加密來存取 Office 365 資料的內容。請參閱[建立及部署裝置安全性原則](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。</span><span class="sxs-lookup"><span data-stu-id="8f612-p104">Some kinds of mobile devices encrypt files that are saved to those devices by default. With [Capabilities of built-in Mobile Device Management for Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0), you can set policies that determine whether to allow mobile devices to access data in Office 365. For example, you can set a policy that allows only devices that encrypt content to access Office 365 data. See [Create and deploy device security policies](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  </span></span><br/> <span data-ttu-id="8f612-p105">與 Office 365 進行互動方式行動裝置上的其他控制項，您可以考慮新增[Microsoft Intune](https://aka.ms/qzln04)。請參閱 ＜ [Choose between MDM for Office 365 and Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22)。</span><span class="sxs-lookup"><span data-stu-id="8f612-p105">For additional control over how mobile devices interact with Office 365, you can consider adding [Microsoft Intune](https://aka.ms/qzln04). See [Choose between MDM for Office 365 and Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22).  </span></span><br/> |
|<span data-ttu-id="8f612-124">您需要用來加密您在 Microsoft 資料中心中的資料的加密金鑰的控制權</span><span class="sxs-lookup"><span data-stu-id="8f612-124">You need control over the encryption keys used to encrypt your data in Microsoft's data centers</span></span>  <br/> | <span data-ttu-id="8f612-125">Office 365 系統管理員身分您可以控制您組織的加密金鑰及使用方式來加密 Microsoft 資料中心的靜態資料的 Office 365，則設定。</span><span class="sxs-lookup"><span data-stu-id="8f612-125">As an Office 365 administrator, you can control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span>  <br/> [<span data-ttu-id="8f612-126">使用客戶金鑰控制 Office 365 中的資料</span><span class="sxs-lookup"><span data-stu-id="8f612-126">Controlling your data in Office 365 using Customer Key</span></span>](controlling-your-data-using-customer-key.md) <br/> [<span data-ttu-id="8f612-127">客戶金鑰的 Office 365 常見問題集</span><span class="sxs-lookup"><span data-stu-id="8f612-127">Customer Key for Office 365 FAQ</span></span>](service-encryption-with-customer-key-faq.md) <br/> |
|<span data-ttu-id="8f612-128">人員會傳達透過電子郵件 (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="8f612-128">People are communicating via email (Exchange Online)</span></span>  <br/> | <span data-ttu-id="8f612-p106">身為 Exchange Online 管理員，您必須設定電子郵件加密的數個選項。這些包括：</span><span class="sxs-lookup"><span data-stu-id="8f612-p106">As an Exchange Online administrator, you have several options for configuring email encryption. These include:  </span></span><br/>  <span data-ttu-id="8f612-131">使用 Azure 版權管理 (Azure RMS) 與[Office 365 郵件加密 (OME)](set-up-new-message-encryption-capabilities.md)啟用來傳送加密的郵件貴組織內外的人員</span><span class="sxs-lookup"><span data-stu-id="8f612-131">Using [Office 365 message encryption (OME)](set-up-new-message-encryption-capabilities.md) with Azure Rights Management (Azure RMS) to enable people to send encrypted messages inside or outside your organization</span></span>  <br/>  <span data-ttu-id="8f612-132">使用[用於訊息簽署和加密的 S/MIME](https://aka.ms/c6dozg)加密及數位簽署電子郵件</span><span class="sxs-lookup"><span data-stu-id="8f612-132">Using [S/MIME for message signing and encryption](https://aka.ms/c6dozg) to encrypt and digitally sign email messages</span></span>  <br/>  <span data-ttu-id="8f612-133">若要[設定連接器的安全郵件流程與其他組織](https://aka.ms/hs809p)使用 TLS</span><span class="sxs-lookup"><span data-stu-id="8f612-133">Using TLS to [set up connectors for secure mail flow with another organization](https://aka.ms/hs809p)</span></span> <br/>  <span data-ttu-id="8f612-134">請參閱[Office 365 中的電子郵件加密](https://aka.ms/hic3f7)。</span><span class="sxs-lookup"><span data-stu-id="8f612-134">See [Email encryption in Office 365](https://aka.ms/hic3f7).</span></span>  <br/> |
|<span data-ttu-id="8f612-135">檔案存取小組網站或文件庫 (OneDrive for Business 或 SharePoint Online)</span><span class="sxs-lookup"><span data-stu-id="8f612-135">Files are accessed from team sites or document libraries (OneDrive for Business or SharePoint Online)</span></span>  <br/> |<span data-ttu-id="8f612-p107">人員會使用檔案儲存至 OneDrive for Business 或 SharePoint Online、 時使用 TLS 連線。這是內建 Office 365 自動。請參閱[OneDrive for Business 和 SharePoint Online 中的資料加密](https://go.microsoft.com/fwlink/?linkid=526379)。</span><span class="sxs-lookup"><span data-stu-id="8f612-p107">When people are working with files saved to OneDrive for Business or SharePoint Online, TLS connections are used. This is built into Office 365 automatically. See [Data Encryption in OneDrive for Business and SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  </span></span><br/> |
|<span data-ttu-id="8f612-139">檔案共用的線上會議和 IM 交談 (Skype 商務 online)</span><span class="sxs-lookup"><span data-stu-id="8f612-139">Files are shared in online meetings and IM conversations (Skype for Business Online)</span></span>  <br/> |<span data-ttu-id="8f612-p108">人員使用的商務 Online 使用 Skype 檔案、 時 TLS 用連線。這是內建 Office 365 自動。請參閱[安全性和封存 (Skype Online 企業版)](https://aka.ms/nuq4ws)。</span><span class="sxs-lookup"><span data-stu-id="8f612-p108">When people are working with files using Skype for Business Online, TLS is used for the connection. This is built into Office 365 automatically. See [Security and Archiving (Skype for Business Online)](https://aka.ms/nuq4ws).  </span></span><br/> |
   
## <a name="additional-information"></a><span data-ttu-id="8f612-143">其他資訊</span><span class="sxs-lookup"><span data-stu-id="8f612-143">Additional information</span></span>

<span data-ttu-id="8f612-144">若要深入了解包含加密選項的檔案保護方案，請參閱[Office 365 中的檔案保護解決方案](https://www.microsoft.com/en-us/download/details.aspx?id=55523)。</span><span class="sxs-lookup"><span data-stu-id="8f612-144">To learn more about file protection solutions that include encryption options, see [File Protection Solutions in Office 365](https://www.microsoft.com/en-us/download/details.aspx?id=55523).</span></span>
  
