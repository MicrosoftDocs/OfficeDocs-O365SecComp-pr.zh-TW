---
title: 在 Office 365 中封存協力廠商資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 系統管理員可以從匯入協力廠商資料社交媒體平台、 立即訊息平台及文件共同作業平台至 Office 365 組織中的信箱。這可讓您封存 Office 365 中的 Facebook、 Twitter 與資料來源的資料。然後您可以與協力廠商資料 appply Office 365 的符合性功能 （例如法務保存措施、 內容搜尋和保留原則）。
ms.openlocfilehash: 0f9f8b5a4ce5b4359430a3b15acc7bf16b2f0290
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296676"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="d4357-105">在 Office 365 中封存協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="d4357-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="d4357-p102">Office 365 可讓系統管理員匯入及封存立即訊息平台和文件共同作業平台，至 Office 365 組織中信箱的社交媒體平台的協力廠商資料。您可以匯入至 Office 365 的協力廠商資料來源的範例包括：</span><span class="sxs-lookup"><span data-stu-id="d4357-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="d4357-108">**社交**-Twitter、 Facebook、 Yammer 及 LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d4357-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="d4357-109">**立即訊息**-Yahoo Messenger、 GoogleTalk、 及 Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="d4357-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="d4357-110">**文件共同作業**-方塊和投寄箱</span><span class="sxs-lookup"><span data-stu-id="d4357-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="d4357-111">**垂直產業**-客戶關係管理 （例如 Salesforce 交談） 和 Financials （例如湯氏路透社和 Bloomberg）</span><span class="sxs-lookup"><span data-stu-id="d4357-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="d4357-112">**SMS/文字郵件**-BlackBerry</span><span class="sxs-lookup"><span data-stu-id="d4357-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="d4357-p103">在匯入協力廠商資料之後，您可以套用 Office 365 的符合性功能 — 例如訴訟暫止狀態、 內容搜尋、 就地封存、 稽核、 及 Office 365 的保留原則-此資料。例如，當信箱處於訴訟暫止狀態，則會保留與協力廠商資料。您可以使用內容搜尋來搜尋協力廠商資料。或您可以套用封存和保留原則就像您可以為 Microsoft 資料的第三方資料。在短封存 Office 365 中的第三方資料可協助組織保持在最符合政府和法規的原則。</span><span class="sxs-lookup"><span data-stu-id="d4357-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="d4357-118">以下是程序和步驟的概觀 （英文） 需要協力廠商將資料匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d4357-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="d4357-119">步驟 1：尋找協力廠商資料合作夥伴</span><span class="sxs-lookup"><span data-stu-id="d4357-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="d4357-120">步驟 2：在 Office 365 中建立及設定協力廠商資料信箱</span><span class="sxs-lookup"><span data-stu-id="d4357-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="d4357-121">步驟 3：設定協力廠商資料的使用者信箱</span><span class="sxs-lookup"><span data-stu-id="d4357-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="d4357-122">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="d4357-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="d4357-123">步驟 5： 在 Azure Active Directory 中登錄的協力廠商資料連接器</span><span class="sxs-lookup"><span data-stu-id="d4357-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="d4357-124">如何將第三方的資料匯入程序 works></span><span class="sxs-lookup"><span data-stu-id="d4357-124">How the third-party data import process works></span></span>

<span data-ttu-id="d4357-125">下圖和描述會說明協力廠商資料匯入程序的運作方式。</span><span class="sxs-lookup"><span data-stu-id="d4357-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![協力廠商資料匯入程序的運作方式](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="d4357-127">客戶適用於設定連接器將從協力廠商資料來源擷取項目並再匯入 Office 365 的 [項目選擇的其合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="d4357-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="d4357-p104">協力廠商連接器會連接到 （根據排程或做為設定） 的協力廠商 API 透過協力廠商資料來源，並從資料來源擷取項目。協力廠商連接器將電子郵件訊息格式轉換項目的內容。請參閱[的詳細資訊](#more-information)] 區段中的郵件格式結構描述的說明。</span><span class="sxs-lookup"><span data-stu-id="d4357-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="d4357-131">協力廠商連接器會使用 Exchange Web 服務 (EWS) 透過已知的終點連線到 Office 365 中的 Azure 服務。</span><span class="sxs-lookup"><span data-stu-id="d4357-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="d4357-p105">項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：</span><span class="sxs-lookup"><span data-stu-id="d4357-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="d4357-p106">a.**項目所擁有的對應至 Office 365 使用者帳戶的使用者識別碼**-如果協力廠商連接器可以對應至特定使用者在 Office 365 中，此項目 ID 複製到 [**清除**] 資料夾中的使用者的使用者識別碼的協力廠商資料來源中的項目可復原項目] 資料夾。使用者無法存取 [清除] 資料夾中的項目。不過，您可以使用 Office 365 eDiscovery 工具來搜尋 [清除] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="d4357-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="d4357-p107">b.**所沒有的對應至 Office 365 使用者帳戶的使用者識別碼的項目**-如果協力廠商連接器無法將項目的使用者識別碼對應至特定使用者在 Office 365 中，此項目 ID 複製到的協力廠商資料信箱的 [**收件匣**] 資料夾。將項目匯入至收件匣可讓您或有人登入與協力廠商信箱來檢視和管理這些項目，並查看任何調整是否需要進行的協力廠商連接器設定在組織中。</span><span class="sxs-lookup"><span data-stu-id="d4357-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="d4357-141">步驟 1：尋找協力廠商資料合作夥伴</span><span class="sxs-lookup"><span data-stu-id="d4357-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="d4357-p108">封存 Office 365 中的第三方資料的重要元件會尋找並使用擷取協力廠商資料來源的資料及將其匯入 Office 365 中專門是 Microsoft 合作夥伴。它將資料匯入之後，可以封存和保留與您組織的其他 Microsoft 資料，例如電子郵件從 Exchange 和 SharePoint 和 OneDrive for Business 文件。合作夥伴會建立的資料擷取您組織的協力廠商資料來源 （例如 BlackBerry、 Facebook、 Google +、 湯氏路透社、 Twitter 及 YouTube） 並將該資料傳遞給將項目匯入至 Exchange 信箱作為 Office 365 API 的連接器電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d4357-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="d4357-145">下列各節將列出 Microsoft 合作夥伴 — 以及它們所支援之協力廠商資料來源 — 可參與計劃封存 Office 365 中的第三方資料。</span><span class="sxs-lookup"><span data-stu-id="d4357-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="d4357-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="d4357-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="d4357-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="d4357-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="d4357-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="d4357-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="d4357-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="d4357-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="d4357-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="d4357-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="d4357-151">Verba</span><span class="sxs-lookup"><span data-stu-id="d4357-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="d4357-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="d4357-152">17a-4 LLC</span></span>

<span data-ttu-id="d4357-153">17a-4 LLC 支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="d4357-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="d4357-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="d4357-154">BlackBerry</span></span>
    
- <span data-ttu-id="d4357-155">Bloomberg 資料流</span><span class="sxs-lookup"><span data-stu-id="d4357-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="d4357-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="d4357-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="d4357-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="d4357-157">FactSet</span></span>
    
- <span data-ttu-id="d4357-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="d4357-158">HipChat</span></span>
    
- <span data-ttu-id="d4357-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="d4357-159">InvestEdge</span></span>
    
- <span data-ttu-id="d4357-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="d4357-160">LivePerson</span></span>
    
- <span data-ttu-id="d4357-161">
MessageLabs 資料流
</span><span class="sxs-lookup"><span data-stu-id="d4357-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="d4357-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="d4357-162">OpenText</span></span>
    
- <span data-ttu-id="d4357-163">Oracle/ATG 'click-to-call' 即時說明
</span><span class="sxs-lookup"><span data-stu-id="d4357-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="d4357-164">樞紐分析 IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="d4357-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="d4357-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4357-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="d4357-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="d4357-166">MindAlign</span></span>
    
- <span data-ttu-id="d4357-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="d4357-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="d4357-168">
商務用 Skype (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="d4357-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="d4357-169">
商務用 Skype Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="d4357-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="d4357-170">SQL 資料庫</span><span class="sxs-lookup"><span data-stu-id="d4357-170">SQL Databases</span></span>
    
- <span data-ttu-id="d4357-171">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="d4357-171">Squawker</span></span>
    
- <span data-ttu-id="d4357-172">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="d4357-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="d4357-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="d4357-173">Actiance</span></span>

<span data-ttu-id="d4357-174">[Actiance](https://www.actiance.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="d4357-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d4357-175">AIM</span><span class="sxs-lookup"><span data-stu-id="d4357-175">AIM</span></span>
    
- <span data-ttu-id="d4357-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="d4357-176">American Idol</span></span>
    
- <span data-ttu-id="d4357-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="d4357-177">Apple Juice</span></span>
    
- <span data-ttu-id="d4357-178">
含樞紐分析用戶端的 AOL
</span><span class="sxs-lookup"><span data-stu-id="d4357-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="d4357-179">Ares</span><span class="sxs-lookup"><span data-stu-id="d4357-179">Ares</span></span>
    
- <span data-ttu-id="d4357-180">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="d4357-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="d4357-181">Bear Share</span><span class="sxs-lookup"><span data-stu-id="d4357-181">Bear Share</span></span>
    
- <span data-ttu-id="d4357-182">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="d4357-182">Bit Torrent</span></span>
    
- <span data-ttu-id="d4357-183">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-184">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-185">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-186">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-187">Bloomberg 郵件
</span><span class="sxs-lookup"><span data-stu-id="d4357-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="d4357-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="d4357-188">CellTrust</span></span>
    
- <span data-ttu-id="d4357-189">Chat Import
</span><span class="sxs-lookup"><span data-stu-id="d4357-189">Chat Import</span></span>
    
- <span data-ttu-id="d4357-190">Chat Real Time Logging and Policy
</span><span class="sxs-lookup"><span data-stu-id="d4357-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="d4357-191">Chatter
</span><span class="sxs-lookup"><span data-stu-id="d4357-191">Chatter</span></span>
    
- <span data-ttu-id="d4357-192">Cisco IM&amp;平台服務伺服器 (v9.0.1、 v9.1、 v9.1.1 SU1、 v10、 v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="d4357-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="d4357-193">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="d4357-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="d4357-194">Collaboration Import
</span><span class="sxs-lookup"><span data-stu-id="d4357-194">Collaboration Import</span></span>
    
- <span data-ttu-id="d4357-195">Collaboration Real Time Logging
</span><span class="sxs-lookup"><span data-stu-id="d4357-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="d4357-196">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="d4357-196">Direct Connect</span></span>
    
- <span data-ttu-id="d4357-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="d4357-197">Facebook</span></span>
    
- <span data-ttu-id="d4357-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="d4357-198">FactSet</span></span>
    
- <span data-ttu-id="d4357-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="d4357-199">FastTrack</span></span>
    
- <span data-ttu-id="d4357-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="d4357-200">Gnutella</span></span>
    
- <span data-ttu-id="d4357-201">Google+
</span><span class="sxs-lookup"><span data-stu-id="d4357-201">Google+</span></span>
    
- <span data-ttu-id="d4357-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="d4357-202">GoToMyPC</span></span>
    
- <span data-ttu-id="d4357-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="d4357-203">Hopster</span></span>
    
- <span data-ttu-id="d4357-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="d4357-204">HubConnex</span></span>
    
- <span data-ttu-id="d4357-205">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)
</span><span class="sxs-lookup"><span data-stu-id="d4357-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="d4357-206">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="d4357-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="d4357-207">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="d4357-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="d4357-208">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="d4357-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="d4357-209">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="d4357-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="d4357-210">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
</span><span class="sxs-lookup"><span data-stu-id="d4357-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="d4357-211">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="d4357-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="d4357-212">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="d4357-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="d4357-213">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="d4357-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="d4357-214">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="d4357-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="d4357-215">IM Import
</span><span class="sxs-lookup"><span data-stu-id="d4357-215">IM Import</span></span>
    
- <span data-ttu-id="d4357-216">IM Real Time Logging and Policy
</span><span class="sxs-lookup"><span data-stu-id="d4357-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="d4357-217">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="d4357-217">Indii Messenger</span></span>
    
- <span data-ttu-id="d4357-218">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="d4357-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="d4357-219">IRC</span><span class="sxs-lookup"><span data-stu-id="d4357-219">IRC</span></span>
    
- <span data-ttu-id="d4357-220">Jive
</span><span class="sxs-lookup"><span data-stu-id="d4357-220">Jive</span></span>
    
- <span data-ttu-id="d4357-221">Jive 6 Real Time Logging (v6、v7)
</span><span class="sxs-lookup"><span data-stu-id="d4357-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="d4357-222">Jive Import</span><span class="sxs-lookup"><span data-stu-id="d4357-222">Jive Import</span></span>
    
- <span data-ttu-id="d4357-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="d4357-223">JXTA</span></span>
    
- <span data-ttu-id="d4357-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d4357-224">LinkedIn</span></span>
    
- <span data-ttu-id="d4357-225">
Microsoft Lync (2010、2013)
</span><span class="sxs-lookup"><span data-stu-id="d4357-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="d4357-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="d4357-226">MFTP</span></span>
    
- <span data-ttu-id="d4357-227">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="d4357-228">Microsoft SharePoint (2010、2013)
</span><span class="sxs-lookup"><span data-stu-id="d4357-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="d4357-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d4357-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="d4357-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="d4357-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="d4357-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="d4357-231">MindAlign</span></span>
    
- <span data-ttu-id="d4357-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="d4357-232">Mobile Guard</span></span>
    
- <span data-ttu-id="d4357-233">MSN</span><span class="sxs-lookup"><span data-stu-id="d4357-233">MSN</span></span>
    
- <span data-ttu-id="d4357-234">My Space</span><span class="sxs-lookup"><span data-stu-id="d4357-234">My Space</span></span>
    
- <span data-ttu-id="d4357-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="d4357-235">NEONetwork</span></span>
    
- <span data-ttu-id="d4357-236">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="d4357-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="d4357-237">Office 365 Shared IM
</span><span class="sxs-lookup"><span data-stu-id="d4357-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="d4357-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="d4357-238">Pinterest</span></span>
    
- <span data-ttu-id="d4357-239">Pivot</span><span class="sxs-lookup"><span data-stu-id="d4357-239">Pivot</span></span>
    
- <span data-ttu-id="d4357-240">QQ</span><span class="sxs-lookup"><span data-stu-id="d4357-240">QQ</span></span>
    
- <span data-ttu-id="d4357-241">商務用 Skype 2015</span><span class="sxs-lookup"><span data-stu-id="d4357-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="d4357-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="d4357-242">SoftEther</span></span>
    
- <span data-ttu-id="d4357-243">Symphony
</span><span class="sxs-lookup"><span data-stu-id="d4357-243">Symphony</span></span>
    
- <span data-ttu-id="d4357-244">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="d4357-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="d4357-245">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="d4357-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="d4357-246">Tor</span><span class="sxs-lookup"><span data-stu-id="d4357-246">Tor</span></span>
    
- <span data-ttu-id="d4357-247">TTT</span><span class="sxs-lookup"><span data-stu-id="d4357-247">TTT</span></span>
    
- <span data-ttu-id="d4357-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="d4357-248">Twitter</span></span>
    
- <span data-ttu-id="d4357-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="d4357-249">WinMX</span></span>
    
- <span data-ttu-id="d4357-250">Winny</span><span class="sxs-lookup"><span data-stu-id="d4357-250">Winny</span></span>
    
- <span data-ttu-id="d4357-251">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="d4357-251">Yahoo</span></span>
    
- <span data-ttu-id="d4357-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="d4357-252">Yammer</span></span>
    
- <span data-ttu-id="d4357-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="d4357-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="d4357-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="d4357-254">ArchiveSocial</span></span>

<span data-ttu-id="d4357-255">[ArchiveSocial](https://www.archivesocial.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="d4357-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d4357-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="d4357-256">Facebook</span></span>
    
- <span data-ttu-id="d4357-257">Flickr
</span><span class="sxs-lookup"><span data-stu-id="d4357-257">Flickr</span></span>
    
- <span data-ttu-id="d4357-258">Instagram
</span><span class="sxs-lookup"><span data-stu-id="d4357-258">Instagram</span></span>
    
- <span data-ttu-id="d4357-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d4357-259">LinkedIn</span></span>
    
- <span data-ttu-id="d4357-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="d4357-260">Pinterest</span></span>
    
- <span data-ttu-id="d4357-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="d4357-261">Twitter</span></span>
    
- <span data-ttu-id="d4357-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="d4357-262">YouTube</span></span>
    
- <span data-ttu-id="d4357-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="d4357-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="d4357-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="d4357-264">Globanet</span></span>

<span data-ttu-id="d4357-265">[Globanet](https://www.globanet.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="d4357-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d4357-266">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="d4357-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="d4357-267">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-268">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-269">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-270">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d4357-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d4357-271">Bloomberg Chat
</span><span class="sxs-lookup"><span data-stu-id="d4357-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="d4357-272">Bloomberg 郵件
</span><span class="sxs-lookup"><span data-stu-id="d4357-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="d4357-273">Box</span><span class="sxs-lookup"><span data-stu-id="d4357-273">Box</span></span>
    
- <span data-ttu-id="d4357-274">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="d4357-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="d4357-275">Cisco IM&amp;平台服務伺服器 (v10、 v10.5.1 SU1 v11.0、 v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="d4357-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="d4357-276">Cisco Webex 小組</span><span class="sxs-lookup"><span data-stu-id="d4357-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="d4357-277">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="d4357-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="d4357-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="d4357-278">CrowdCompass</span></span>

- <span data-ttu-id="d4357-279">自訂分隔符號文字檔
</span><span class="sxs-lookup"><span data-stu-id="d4357-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="d4357-280">自訂 XML 檔案
</span><span class="sxs-lookup"><span data-stu-id="d4357-280">Custom XML files</span></span>
    
- <span data-ttu-id="d4357-281">Facebook （頁面）</span><span class="sxs-lookup"><span data-stu-id="d4357-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="d4357-282">Factset
</span><span class="sxs-lookup"><span data-stu-id="d4357-282">Factset</span></span>
    
- <span data-ttu-id="d4357-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="d4357-283">FXConnect</span></span>
    
- <span data-ttu-id="d4357-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="d4357-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="d4357-285">Jive
</span><span class="sxs-lookup"><span data-stu-id="d4357-285">Jive</span></span>
    
- <span data-ttu-id="d4357-286">Macgregor XIP
</span><span class="sxs-lookup"><span data-stu-id="d4357-286">Macgregor XIP</span></span>

- <span data-ttu-id="d4357-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d4357-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="d4357-288">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d4357-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="d4357-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4357-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="d4357-290">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="d4357-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="d4357-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="d4357-291">Mobile Guard</span></span>
    
- <span data-ttu-id="d4357-292">Pivot</span><span class="sxs-lookup"><span data-stu-id="d4357-292">Pivot</span></span>
    
- <span data-ttu-id="d4357-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="d4357-293">Salesforce Chatter</span></span>

- <span data-ttu-id="d4357-294">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="d4357-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="d4357-295">商務用 Skype 2007 版 R2 - 2016 (內部部署)
</span><span class="sxs-lookup"><span data-stu-id="d4357-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="d4357-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="d4357-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="d4357-297">Symphony
</span><span class="sxs-lookup"><span data-stu-id="d4357-297">Symphony</span></span>
    
- <span data-ttu-id="d4357-298">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="d4357-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="d4357-299">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="d4357-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="d4357-300">Thomson Reuters Dealings 3000 / FX Trading
</span><span class="sxs-lookup"><span data-stu-id="d4357-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="d4357-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="d4357-301">Twitter</span></span>
    
- <span data-ttu-id="d4357-302">UBS Chat
</span><span class="sxs-lookup"><span data-stu-id="d4357-302">UBS Chat</span></span>
    
- <span data-ttu-id="d4357-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="d4357-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="d4357-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="d4357-304">OpenText</span></span>

<span data-ttu-id="d4357-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="d4357-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d4357-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="d4357-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="d4357-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="d4357-307">Axs Exchange</span></span>
    
- <span data-ttu-id="d4357-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="d4357-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="d4357-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="d4357-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="d4357-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="d4357-310">Axs Signed</span></span>
    
- <span data-ttu-id="d4357-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="d4357-311">Bloomberg</span></span>
    
- <span data-ttu-id="d4357-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="d4357-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="d4357-313">Verba</span><span class="sxs-lookup"><span data-stu-id="d4357-313">Verba</span></span>

<span data-ttu-id="d4357-314">[Verba](https://www.verba.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="d4357-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d4357-315">Avaya Aura Video
</span><span class="sxs-lookup"><span data-stu-id="d4357-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="d4357-316">Avaya Aura Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="d4357-317">Avtec Radio
</span><span class="sxs-lookup"><span data-stu-id="d4357-317">Avtec Radio</span></span>
    
- <span data-ttu-id="d4357-318">Bosch/Telex Radio
</span><span class="sxs-lookup"><span data-stu-id="d4357-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="d4357-319">BroadSoft Video
</span><span class="sxs-lookup"><span data-stu-id="d4357-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="d4357-320">BroadSoft Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="d4357-321">Centile Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-321">Centile Voice</span></span>
    
- <span data-ttu-id="d4357-322">Cisco Jabber IM
</span><span class="sxs-lookup"><span data-stu-id="d4357-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="d4357-323">Cisco UC Video
</span><span class="sxs-lookup"><span data-stu-id="d4357-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="d4357-324">Cisco UC Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="d4357-325">Cisco UCCX/UCCE 影片</span><span class="sxs-lookup"><span data-stu-id="d4357-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="d4357-326">Cisco UCCX/UCCE 語音</span><span class="sxs-lookup"><span data-stu-id="d4357-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="d4357-327">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="d4357-327">ESChat Radio</span></span>
    
- <span data-ttu-id="d4357-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="d4357-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="d4357-329">IP Trade Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="d4357-330">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="d4357-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="d4357-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="d4357-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="d4357-332">Mitel MiContact Center for Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="d4357-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="d4357-333">Oracle / Acme Packet Session Border Controller Video  
</span><span class="sxs-lookup"><span data-stu-id="d4357-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="d4357-334">Oracle / Acme Packet Session Border Controller Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="d4357-335">Singtel Mobile Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="d4357-336">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="d4357-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="d4357-337">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="d4357-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="d4357-338">商務用 Skype/Lync IM
</span><span class="sxs-lookup"><span data-stu-id="d4357-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="d4357-339">商務用 Skype/Lync Video
</span><span class="sxs-lookup"><span data-stu-id="d4357-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="d4357-340">商務用 Skype/Lync Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="d4357-341">Speakerbus Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="d4357-342">Standard SIP/H.323 Video 
</span><span class="sxs-lookup"><span data-stu-id="d4357-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="d4357-343">Standard SIP/H.323 Voice 
</span><span class="sxs-lookup"><span data-stu-id="d4357-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="d4357-344">Truphone Voice
</span><span class="sxs-lookup"><span data-stu-id="d4357-344">Truphone Voice</span></span>
    
- <span data-ttu-id="d4357-345">TwistedPair Radio
</span><span class="sxs-lookup"><span data-stu-id="d4357-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="d4357-346">Windows Desktop Computer Screen 
</span><span class="sxs-lookup"><span data-stu-id="d4357-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="d4357-347">步驟 2：在 Office 365 中建立及設定協力廠商資料信箱</span><span class="sxs-lookup"><span data-stu-id="d4357-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="d4357-p109">以下是建立及設定將資料匯入 Office 365 的協力廠商資料信箱的步驟。為舊清楚、 項目將會匯入此信箱是否協力廠商連接器無法對應至 Office 365 使用者帳戶的使用者識別碼的項目。</span><span class="sxs-lookup"><span data-stu-id="d4357-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="d4357-350">**完成這些工作在 Office 365 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="d4357-350">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="d4357-p110">Office 365 中建立新的使用者帳戶並將其指派 Exchange Online 計劃 2 的授權;請參閱[新增使用者至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。計劃 2 授權，才能信箱置於訴訟暫止狀態或啟用封存信箱已無限制的儲存配額。</span><span class="sxs-lookup"><span data-stu-id="d4357-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="d4357-353">將協力廠商資料信箱的使用者帳戶新增至 Office 365; 中的**Exchange 系統管理員**系統管理角色請參閱[指派 Office 365 中的系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。</span><span class="sxs-lookup"><span data-stu-id="d4357-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d4357-p111">請寫下此使用者帳戶的認證。您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。</span><span class="sxs-lookup"><span data-stu-id="d4357-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="d4357-356">**完成這些工作在 Exchange 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="d4357-356">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="d4357-p112">隱藏從通訊錄與您的組織 ； 在其他通訊清單的第三方資料信箱請參閱[Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058)。或者，您可以執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="d4357-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="d4357-359">指派協力廠商資料信箱的**FullAccess**權限，讓系統管理員或法務人員可以在 Outlook 桌面用戶端; 中開啟與協力廠商資料信箱請參閱[收件者的管理權限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="d4357-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="d4357-360">啟用下列規範相關 Office 365 的功能與協力廠商資料信箱：</span><span class="sxs-lookup"><span data-stu-id="d4357-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="d4357-p113">啟用封存信箱 ；請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)並[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。這可讓您藉由設定會與協力廠商資料的項目移至封存信箱的封存原則主要信箱中釋放儲存空間。這會提供給您不受限制的存放區的第三方資料。</span><span class="sxs-lookup"><span data-stu-id="d4357-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="d4357-p114">協力廠商資料信箱可以置於訴訟暫止狀態。您也可以套用 Office 365 安全性 Office 365 保留原則&amp;規範中心。將這個信箱設定保留會保留與協力廠商資料的項目 （無限期或指定的持續期間） 並防止從信箱清除。請參閱下列主題的其中一個：</span><span class="sxs-lookup"><span data-stu-id="d4357-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="d4357-368">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="d4357-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="d4357-369">Office 365 中的保留原則的概觀</span><span class="sxs-lookup"><span data-stu-id="d4357-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="d4357-p115">啟用信箱稽核記錄的擁有者、 委派、 和系統信箱的存取權與協力廠商資料 ；請參閱[啟用信箱稽核 Office 365 中](enable-mailbox-auditing.md)。這可讓您以稽核在任何具有存取權的協力廠商資料信箱的使用者所執行的所有活動。</span><span class="sxs-lookup"><span data-stu-id="d4357-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="d4357-372">步驟 3：設定協力廠商資料的使用者信箱</span><span class="sxs-lookup"><span data-stu-id="d4357-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="d4357-p116">下一步是設定為支援與協力廠商資料的使用者信箱。使用 Exchange 系統管理中心或使用相對應的 Windows PowerShell cmdlet 來完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="d4357-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="d4357-375">啟用封存信箱的每位使用者;請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)並[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d4357-375">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="d4357-376">置於使用者信箱訴訟暫止狀態或適用於 Office 365 保留原則請參閱下列主題的其中一個：</span><span class="sxs-lookup"><span data-stu-id="d4357-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="d4357-377">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="d4357-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="d4357-378">Office 365 中的保留原則的概觀</span><span class="sxs-lookup"><span data-stu-id="d4357-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="d4357-379">如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。</span><span class="sxs-lookup"><span data-stu-id="d4357-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="d4357-380">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="d4357-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="d4357-381">最後一個步驟是讓您的合作夥伴具有下列資訊，讓他們可以設定連接器以連接到您的 Office 365 組織，將資料匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="d4357-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="d4357-382">用來連線至 Office 365 的 Azure 服務端點：</span><span class="sxs-lookup"><span data-stu-id="d4357-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="d4357-p117">登入您在步驟 2 中建立的協力廠商資料信箱認證 （Office 365 使用者識別碼和密碼）。這些認證是必要的協力廠商連接器可以存取和使用者信箱與協力廠商資料信箱匯入項目。</span><span class="sxs-lookup"><span data-stu-id="d4357-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="d4357-385">步驟 5： 在 Azure Active Directory 中登錄的協力廠商資料連接器</span><span class="sxs-lookup"><span data-stu-id="d4357-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="d4357-p118">啟動 2018 September 30、 Office 365 的 Azure 服務會開始使用經過驗證在 Exchange Online 進行驗證嘗試連線至 Office 365 組織匯入資料的第三方資料連接器。這項變更的原因是經過驗證提供更多安全性比目前的方法來連線至 Azure 服務使用先前所述的端點的家協力廠商連接器的基礎。</span><span class="sxs-lookup"><span data-stu-id="d4357-p118">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data. The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="d4357-p119">若要啟用協力廠商資料連接線連線到 Office 365 使用新的現代的驗證方法，在 Office 365 組織中的系統管理員必須同意登錄為 Azure Active Directory 中的受信任的服務應用程式的連接器。做法是接受權限要求允許存取您的組織資料 Azure Active Directory 中的連接器。接受此要求之後，與協力廠商資料新增為 Azure Active directory 企業應用程式及連接器表示為服務主要名稱。如同意程序的詳細資訊，請參閱[租用戶系統同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="d4357-p119">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory. This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory. After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal. For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="d4357-392">存取及接受登錄連接器要求的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="d4357-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="d4357-393">前往[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)及使用的 Office 365 全域管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="d4357-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="d4357-p120">會顯示下列對話方塊。您可以展開檢閱會指派給連接器的權限插入號。</span><span class="sxs-lookup"><span data-stu-id="d4357-p120">The following dialog box is displayed. You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="d4357-396">![顯示 [權限要求] 對話方塊](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="d4357-396">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="d4357-397">按一下 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="d4357-397">Click **Accept**.</span></span>

<span data-ttu-id="d4357-p121">接受邀請之後，會顯示[Azure 入口網站](https://portal.azure.com)。若要檢視您組織的應用程式清單，請按一下 [ **Azure Active Directory** > **企業應用程式**。**企業應用程式**blade 會列出 Office 365 協力廠商資料連接器。</span><span class="sxs-lookup"><span data-stu-id="d4357-p121">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed. To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**. The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4357-p122">之後 2018 September 30、 協力廠商將不會再將資料匯入您組織中信箱如果您不在 Azure Active Directory 登錄協力廠商資料連接器。也必須遵循下列步驟 5 中的程序在 Azure Active Directory 中登錄現有的協力廠商資料連接器 （與其 2018 September 30、 之前建立） 的附註。</span><span class="sxs-lookup"><span data-stu-id="d4357-p122">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory. Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="d4357-403">Grant 同意的協力廠商資料連接器</span><span class="sxs-lookup"><span data-stu-id="d4357-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="d4357-p123">您的組織 consents 權限要求在 Azure Active Directory 中登錄的協力廠商資料連接器之後，您的組織可以撤銷隨時該同意。不過，撤銷連接器同意表示可與協力廠商資料來源的資料將不會再匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d4357-p123">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time. However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="d4357-p124">若要撤銷的協力廠商資料連接器的同意，您可以刪除應用程式 （刪除的對應的服務主要名稱） 從 Azure 入口網站，或使用[使用**企業應用程式**blade 部署 Azure Active Directory移除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) Office 365 PowerShell 中。您也可以使用 Azure Active Directory PowerShell 中的[移除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)指令程式。</span><span class="sxs-lookup"><span data-stu-id="d4357-p124">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="d4357-408">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d4357-408">More information</span></span>

- <span data-ttu-id="d4357-p125">為舊清楚，從協力廠商資料來源匯入至做為電子郵件的 Exchange 信箱的項目。協力廠商連接器匯入使用 Office 365 API 所需的結構描述的項目。下表說明郵件項目的屬性與協力廠商的資料來源之後匯入至 Exchange 信箱以電子郵件訊息。表也會指出是否 message 屬性是必要項目。必須填入必要屬性。如果項目缺少一個必要的屬性，將不會匯入至 Office 365。匯入程序將會傳回錯誤訊息說明為何項目未匯入和遺漏的屬性。</span><span class="sxs-lookup"><span data-stu-id="d4357-p125">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="d4357-416">**郵件屬性**</span><span class="sxs-lookup"><span data-stu-id="d4357-416">**Message property**</span></span>|<span data-ttu-id="d4357-417">**必要項目？**</span><span class="sxs-lookup"><span data-stu-id="d4357-417">**Mandatory?**</span></span>|<span data-ttu-id="d4357-418">**描述**</span><span class="sxs-lookup"><span data-stu-id="d4357-418">**Description**</span></span>|<span data-ttu-id="d4357-419">**範例值**</span><span class="sxs-lookup"><span data-stu-id="d4357-419">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d4357-420">**FROM**</span><span class="sxs-lookup"><span data-stu-id="d4357-420">**FROM**</span></span> <br/> |<span data-ttu-id="d4357-421">是</span><span class="sxs-lookup"><span data-stu-id="d4357-421">Yes</span></span>  <br/> |<span data-ttu-id="d4357-p126">最初建立或傳送項目之協力廠商資料來源中的使用者。協力廠商連接器會嘗試將對應所有參與者 （FROM 和 TO 欄位中的使用者） 的 Office 365 使用者帳戶從來源項目 （例如 Twitter 控點） 的使用者識別碼。郵件的複本會匯入至每個參與者的信箱。如果任何項目從參與者可以對應至 Office 365 使用者帳戶，此項目將會匯入至 Office 365 中的第三方封存信箱。</span><span class="sxs-lookup"><span data-stu-id="d4357-p126">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="d4357-p127">項目的寄件者身分識別的參與者必須具備的項目以匯入 Office 365 組織中使用中信箱。如果寄件者沒有作用中的信箱，會傳回下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="d4357-p127">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="d4357-428">**TO**</span><span class="sxs-lookup"><span data-stu-id="d4357-428">**TO**</span></span> <br/> |<span data-ttu-id="d4357-429">是</span><span class="sxs-lookup"><span data-stu-id="d4357-429">Yes</span></span>  <br/> |<span data-ttu-id="d4357-430">接收項目的使用者，如果適用於資料來源中的項目。</span><span class="sxs-lookup"><span data-stu-id="d4357-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="d4357-431">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="d4357-431">**SUBJECT**</span></span> <br/> |<span data-ttu-id="d4357-432">否</span><span class="sxs-lookup"><span data-stu-id="d4357-432">No</span></span>  <br/> |<span data-ttu-id="d4357-433">來源項目的主旨。</span><span class="sxs-lookup"><span data-stu-id="d4357-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="d4357-434">**日期**</span><span class="sxs-lookup"><span data-stu-id="d4357-434">**DATE**</span></span> <br/> |<span data-ttu-id="d4357-435">是</span><span class="sxs-lookup"><span data-stu-id="d4357-435">Yes</span></span>  <br/> |<span data-ttu-id="d4357-436">項目最初建立或張貼在客戶資料來源的日期。例如，Twitter 訊息推文的日期。</span><span class="sxs-lookup"><span data-stu-id="d4357-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="d4357-437">**BODY**</span><span class="sxs-lookup"><span data-stu-id="d4357-437">**BODY**</span></span> <br/> |<span data-ttu-id="d4357-438">否</span><span class="sxs-lookup"><span data-stu-id="d4357-438">No</span></span>  <br/> |<span data-ttu-id="d4357-p128">郵件或張貼內容。某些資料來源而言，此屬性的內容可能是**SUBJECT**屬性的內容相同。匯入程序期間的協力廠商連接器會嘗試將維護儘可能將內容來源的完整不失真。請盡可能檔案、 圖形或其他內容從來源項目的本文隨附於此屬性。否則請內容從來源項目包含在**附件**屬性。此屬性的內容取決來源平台功能及協力廠商連接器上。</span><span class="sxs-lookup"><span data-stu-id="d4357-p128">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="d4357-445">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="d4357-445">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="d4357-446">否</span><span class="sxs-lookup"><span data-stu-id="d4357-446">No</span></span>  <br/> |<span data-ttu-id="d4357-p129">如果資料來源 （例如 Twitter 或立即訊息交談中叫） 中的項目具有附加的檔案或包含圖像、 協力廠商連線將第一次嘗試將附件納入**BODY**屬性。如果不是可行的則會新增到 \* \* 附件 \* \* 屬性。附件的其他範例 Facebook、 中繼資料與內容來源及回覆郵件或張貼中包含 「 讚 」。</span><span class="sxs-lookup"><span data-stu-id="d4357-p129">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="d4357-450">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="d4357-450">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="d4357-451">是</span><span class="sxs-lookup"><span data-stu-id="d4357-451">Yes</span></span>  <br/> | <span data-ttu-id="d4357-p130">這是多重值屬性，會建立及填入的協力廠商連接器。此屬性的格式是`IPM.NOTE.Source.Event`。(此屬性必須以開頭`IPM.NOTE`； 此格式會類似的`IPM.NOTE.X`郵件類別。)此屬性包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d4357-p130">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="d4357-455">`Source`-會指出與協力廠商資料來源 ；例如，Twitter、 Facebook 或 BlackBerry。</span><span class="sxs-lookup"><span data-stu-id="d4357-455">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="d4357-p131">`Event`-會指出已執行所產生的項目 ； 協力廠商資料來源中的活動類型例如，Twitter 或 Facebook 中的張貼叫。事件屬於特定資料來源。</span><span class="sxs-lookup"><span data-stu-id="d4357-p131">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="d4357-p132">此屬性的目的之一是事件的篩選出或項目源自類型為基礎的資料來源為基礎的特定項目。例如，在 eDiscovery 搜尋無法建立搜尋查詢以尋找當天的特定使用者的所有 tweets。</span><span class="sxs-lookup"><span data-stu-id="d4357-p132">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="d4357-p133">當項目已成功匯入至 Office 365 中的信箱時的唯一識別碼會傳回回到來電者的 HTTP 回應的一部分。此識別碼 — 呼叫`x-IngestionCorrelationID`— 可用於後續的疑難排解用途協力廠商的端對端追蹤項目。建議合作夥伴擷取此資訊與據此記錄其結尾。以下是範例顯示此識別碼 HTTP 回應：</span><span class="sxs-lookup"><span data-stu-id="d4357-p133">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="d4357-p134">您可以使用 「 內容搜尋工具在 Office 365 安全性&amp;規範中心來搜尋的項目已匯入 Office 365 中的信箱與協力廠商的資料來源。若要搜尋特別針對這些匯入的項目，您可以使用成對的下列郵件屬性值在 [關鍵字] 方塊中的內容搜尋。.</span><span class="sxs-lookup"><span data-stu-id="d4357-p134">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="d4357-p135">**`kind:externaldata`**-使用此屬性值配對搜尋所有的協力廠商的資料類型。例如，若要搜尋的項目都已匯入協力廠商的資料來源及匯入的項目之主旨屬性中包含單字"contoso"，您會使用關鍵字查詢`kind:externaldata AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="d4357-p135">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="d4357-p136">**`itemclass:ipm.externaldata.<third-party data type>`**-使用此屬性值組搜尋指定類型的協力廠商資料。例如，若要只搜尋 Facebook 資料包含單字"contoso"主旨屬性中，您會使用關鍵字查詢`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="d4357-p136">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="d4357-471">如要使用的協力廠商資料類型值的完整清單`itemclass`屬性，請參閱[使用搜尋的已匯入 Office 365 的協力廠商資料的內容搜尋](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="d4357-471">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="d4357-472">如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰</span><span class="sxs-lookup"><span data-stu-id="d4357-472">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="d4357-473">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="d4357-473">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="d4357-474">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="d4357-474">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
