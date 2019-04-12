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
description: 系統管理員可以從匯入協力廠商資料社交媒體平台、 立即訊息平台，以及文件共同作業平台到 Office 365 組織中的信箱。 這可讓您封存在 Office 365 中的 Facebook、 Twitter 和資料來源中的資料。 然後您可以將 Office 365 符合性功能 （例如合法持有、 內容搜尋和保留原則） 套用至協力廠商資料。
ms.openlocfilehash: 06ac436b1583187e89cb7f1beb26411ba02becec
ms.sourcegitcommit: 86ff2eba1d57b9d5288840788529e69ad9d836b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31818610"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="c8305-105">在 Office 365 中封存協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="c8305-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="c8305-106">Office 365 可讓系統管理員匯入及封存立即訊息平台，與文件共同作業平台，您的 Office 365 組織中的信箱從社交媒體平台的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c8305-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="c8305-107">您可以匯入至 Office 365 的協力廠商資料來源的範例包括下列：</span><span class="sxs-lookup"><span data-stu-id="c8305-107">Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="c8305-108">**社交**-Twitter、 Facebook、 Yammer 和 LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c8305-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="c8305-109">**立即訊息**-Yahoo Messenger、 GoogleTalk 和 Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c8305-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="c8305-110">**文件共同作業**-方塊和 DropBox</span><span class="sxs-lookup"><span data-stu-id="c8305-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="c8305-111">**垂直產業**-客戶關係管理 （例如 Salesforce Chatter) 和金融服務 （例如 Thomson Reuters 及 Bloomberg）</span><span class="sxs-lookup"><span data-stu-id="c8305-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="c8305-112">**SMS/簡訊**-BlackBerry</span><span class="sxs-lookup"><span data-stu-id="c8305-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="c8305-113">協力廠商資料匯入之後，您可以套用 Office 365 合規性功能，例如訴訟暫止狀態、 內容搜尋、 就地封存、 稽核、 及 Office 365 保留原則 — 此資料。</span><span class="sxs-lookup"><span data-stu-id="c8305-113">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data.</span></span> <span data-ttu-id="c8305-114">例如，當信箱置於訴訟暫止狀態時，協力廠商資料將會保留。</span><span class="sxs-lookup"><span data-stu-id="c8305-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="c8305-115">您可以使用內容搜尋來搜尋協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c8305-115">You can search third-party data by using Content Search.</span></span> <span data-ttu-id="c8305-116">或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以對 Microsoft 資料進行的動作一樣。</span><span class="sxs-lookup"><span data-stu-id="c8305-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="c8305-117">總之，封存在 Office 365 中的協力廠商資料可協助組織符合規範與政府法規的原則。</span><span class="sxs-lookup"><span data-stu-id="c8305-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="c8305-118">Xxxx'x 協力廠商資料匯入至 Office 365 所需的程序和步驟的概觀。</span><span class="sxs-lookup"><span data-stu-id="c8305-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="c8305-119">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="c8305-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="c8305-120">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="c8305-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="c8305-121">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="c8305-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="c8305-122">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="c8305-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="c8305-123">步驟 5： 在 Azure Active Directory 中註冊的協力廠商資料連接器</span><span class="sxs-lookup"><span data-stu-id="c8305-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="c8305-124">協力廠商資料匯入程序的運作方式</span><span class="sxs-lookup"><span data-stu-id="c8305-124">How the third-party data import process works</span></span>

<span data-ttu-id="c8305-125">下圖和描述會說明協力廠商資料匯入程序的運作方式。</span><span class="sxs-lookup"><span data-stu-id="c8305-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![協力廠商資料匯入程序的運作方式](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="c8305-127">客戶的運作方式與設定連接器，從協力廠商資料來源擷取項目，並再匯入 Office 365 的 [這些項目所選擇的其合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="c8305-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="c8305-128">協力廠商連接器會連接到 （根據排程或做為設定） 的協力廠商 API 透過協力廠商資料來源，並從資料來源擷取項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-128">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="c8305-129">協力廠商連接器會將項目的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="c8305-129">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="c8305-130">請參閱 [More information](#more-information) 一節以取得訊息格式結構描述的說明。</span><span class="sxs-lookup"><span data-stu-id="c8305-130">See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="c8305-131">協力廠商連接器會連接至 Office 365 中的 Azure 服務透過已知端點使用 Exchange Web 服務 (EWS)。</span><span class="sxs-lookup"><span data-stu-id="c8305-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="c8305-p105">項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：</span><span class="sxs-lookup"><span data-stu-id="c8305-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="c8305-134">a.</span><span class="sxs-lookup"><span data-stu-id="c8305-134">a.</span></span> <span data-ttu-id="c8305-135">**具有，會對應至 Office 365 使用者帳戶的使用者識別碼的項目**-如果協力廠商連接器可以將協力廠商資料來源中的項目的使用者識別碼對應至特定使用者在 Office 365 中，項目識別碼會複製到使用者的記錄中的 [**清除**] 資料夾overable 項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c8305-135">**Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="c8305-136">使用者無法存取 [清除] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-136">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="c8305-137">不過，您可以使用 Office 365 電子文件探索工具來搜尋 [清除] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-137">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="c8305-138">b.</span><span class="sxs-lookup"><span data-stu-id="c8305-138">b.</span></span> <span data-ttu-id="c8305-139">**項目，不需要會對應至 Office 365 使用者帳戶的使用者識別碼**-如果協力廠商連接器無法將項目的使用者識別碼對應至特定使用者在 Office 365 中，項目識別碼會複製到的協力廠商資料信箱的 [**收件匣**] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c8305-139">**Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="c8305-140">將項目匯入至收件匣可讓您或組織中的某個人登入協力廠商信箱來檢視和管理這些項目，並查看是否需要在協力廠商連接器組態中進行任何調整。</span><span class="sxs-lookup"><span data-stu-id="c8305-140">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="c8305-141">步驟 1：尋找協力廠商資料合作夥伴</span><span class="sxs-lookup"><span data-stu-id="c8305-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="c8305-142">封存 Office 365 中的協力廠商資料的主要元件是尋找並使用 Microsoft 合作夥伴，專門負責擷取協力廠商資料來源的資料，並將它匯入至 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="c8305-142">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="c8305-143">它在匯入資料之後，可以封存和保留沿著與您組織的其他 Microsoft 資料，例如來自 Exchange 電子郵件和文件中的 SharePoint 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c8305-143">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="c8305-144">協力廠商建立連接器，從貴組織的協力廠商資料來源 （如 BlackBerry、 Facebook、 Google +、 Thomson Reuters、 Twitter 和 YouTube） 擷取資料，並將該資料傳遞給將項目匯入至 Exchange 信箱做為 Office 365 API電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c8305-144">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="c8305-145">下列各節列出的 Microsoft 合作夥伴 — 以及它們所支援的協力廠商資料來源 —，參與程式來封存 Office 365 中的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c8305-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="c8305-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="c8305-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="c8305-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="c8305-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="c8305-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="c8305-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="c8305-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="c8305-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="c8305-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="c8305-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="c8305-151">Verba</span><span class="sxs-lookup"><span data-stu-id="c8305-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="c8305-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="c8305-152">17a-4 LLC</span></span>

<span data-ttu-id="c8305-153">17a-4 LLC 支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="c8305-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="c8305-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="c8305-154">BlackBerry</span></span>
    
- <span data-ttu-id="c8305-155">Bloomberg 資料流</span><span class="sxs-lookup"><span data-stu-id="c8305-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="c8305-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c8305-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="c8305-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="c8305-157">FactSet</span></span>
    
- <span data-ttu-id="c8305-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="c8305-158">HipChat</span></span>
    
- <span data-ttu-id="c8305-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="c8305-159">InvestEdge</span></span>
    
- <span data-ttu-id="c8305-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="c8305-160">LivePerson</span></span>
    
- <span data-ttu-id="c8305-161">MessageLabs 資料流</span><span class="sxs-lookup"><span data-stu-id="c8305-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="c8305-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="c8305-162">OpenText</span></span>
    
- <span data-ttu-id="c8305-163">Oracle/ATG 'click-to-call' 即時說明</span><span class="sxs-lookup"><span data-stu-id="c8305-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="c8305-164">樞紐分析 IMTRADER</span><span class="sxs-lookup"><span data-stu-id="c8305-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="c8305-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8305-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="c8305-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="c8305-166">MindAlign</span></span>
    
- <span data-ttu-id="c8305-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="c8305-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="c8305-168">商務用 Skype (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="c8305-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="c8305-169">商務用 Skype Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="c8305-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="c8305-170">SQL 資料庫</span><span class="sxs-lookup"><span data-stu-id="c8305-170">SQL Databases</span></span>
    
- <span data-ttu-id="c8305-171">Squawker</span><span class="sxs-lookup"><span data-stu-id="c8305-171">Squawker</span></span>
    
- <span data-ttu-id="c8305-172">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="c8305-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="c8305-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="c8305-173">Actiance</span></span>

<span data-ttu-id="c8305-174">[Actiance](https://www.actiance.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="c8305-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="c8305-175">目標</span><span class="sxs-lookup"><span data-stu-id="c8305-175">AIM</span></span>
    
- <span data-ttu-id="c8305-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="c8305-176">American Idol</span></span>
    
- <span data-ttu-id="c8305-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="c8305-177">Apple Juice</span></span>
    
- <span data-ttu-id="c8305-178">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="c8305-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="c8305-179">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="c8305-179">Ares</span></span>
    
- <span data-ttu-id="c8305-180">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="c8305-181">Bear Share</span><span class="sxs-lookup"><span data-stu-id="c8305-181">Bear Share</span></span>
    
- <span data-ttu-id="c8305-182">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="c8305-182">Bit Torrent</span></span>
    
- <span data-ttu-id="c8305-183">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-184">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-185">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-186">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-187">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="c8305-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="c8305-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="c8305-188">CellTrust</span></span>
    
- <span data-ttu-id="c8305-189">Chat Import</span><span class="sxs-lookup"><span data-stu-id="c8305-189">Chat Import</span></span>
    
- <span data-ttu-id="c8305-190">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="c8305-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="c8305-191">Chatter</span><span class="sxs-lookup"><span data-stu-id="c8305-191">Chatter</span></span>
    
- <span data-ttu-id="c8305-192">Cisco IM &amp; Presence Server (v9.0.1、 v9.1、 v9.1.1 SU1、 v10、 v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="c8305-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="c8305-193">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="c8305-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="c8305-194">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="c8305-194">Collaboration Import</span></span>
    
- <span data-ttu-id="c8305-195">Collaboration Real Time Logging</span><span class="sxs-lookup"><span data-stu-id="c8305-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="c8305-196">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="c8305-196">Direct Connect</span></span>
    
- <span data-ttu-id="c8305-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="c8305-197">Facebook</span></span>
    
- <span data-ttu-id="c8305-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="c8305-198">FactSet</span></span>
    
- <span data-ttu-id="c8305-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c8305-199">FastTrack</span></span>
    
- <span data-ttu-id="c8305-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="c8305-200">Gnutella</span></span>
    
- <span data-ttu-id="c8305-201">Google +</span><span class="sxs-lookup"><span data-stu-id="c8305-201">Google+</span></span>
    
- <span data-ttu-id="c8305-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="c8305-202">GoToMyPC</span></span>
    
- <span data-ttu-id="c8305-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="c8305-203">Hopster</span></span>
    
- <span data-ttu-id="c8305-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="c8305-204">HubConnex</span></span>
    
- <span data-ttu-id="c8305-205">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="c8305-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="c8305-206">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="c8305-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="c8305-207">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="c8305-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="c8305-208">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="c8305-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="c8305-209">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="c8305-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="c8305-210">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="c8305-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="c8305-211">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="c8305-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="c8305-212">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="c8305-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="c8305-213">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="c8305-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="c8305-214">冰/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c8305-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="c8305-215">IM Import</span><span class="sxs-lookup"><span data-stu-id="c8305-215">IM Import</span></span>
    
- <span data-ttu-id="c8305-216">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="c8305-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="c8305-217">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="c8305-217">Indii Messenger</span></span>
    
- <span data-ttu-id="c8305-218">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c8305-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="c8305-219">IRC</span><span class="sxs-lookup"><span data-stu-id="c8305-219">IRC</span></span>
    
- <span data-ttu-id="c8305-220">Jive</span><span class="sxs-lookup"><span data-stu-id="c8305-220">Jive</span></span>
    
- <span data-ttu-id="c8305-221">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="c8305-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="c8305-222">Jive Import</span><span class="sxs-lookup"><span data-stu-id="c8305-222">Jive Import</span></span>
    
- <span data-ttu-id="c8305-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="c8305-223">JXTA</span></span>
    
- <span data-ttu-id="c8305-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c8305-224">LinkedIn</span></span>
    
- <span data-ttu-id="c8305-225">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="c8305-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="c8305-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="c8305-226">MFTP</span></span>
    
- <span data-ttu-id="c8305-227">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="c8305-228">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="c8305-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="c8305-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c8305-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="c8305-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="c8305-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="c8305-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="c8305-231">MindAlign</span></span>
    
- <span data-ttu-id="c8305-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="c8305-232">Mobile Guard</span></span>
    
- <span data-ttu-id="c8305-233">MSN</span><span class="sxs-lookup"><span data-stu-id="c8305-233">MSN</span></span>
    
- <span data-ttu-id="c8305-234">My Space</span><span class="sxs-lookup"><span data-stu-id="c8305-234">My Space</span></span>
    
- <span data-ttu-id="c8305-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="c8305-235">NEONetwork</span></span>
    
- <span data-ttu-id="c8305-236">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="c8305-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="c8305-237">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="c8305-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="c8305-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c8305-238">Pinterest</span></span>
    
- <span data-ttu-id="c8305-239">樞紐</span><span class="sxs-lookup"><span data-stu-id="c8305-239">Pivot</span></span>
    
- <span data-ttu-id="c8305-240">QQ</span><span class="sxs-lookup"><span data-stu-id="c8305-240">QQ</span></span>
    
- <span data-ttu-id="c8305-241">商務用 Skype 2015</span><span class="sxs-lookup"><span data-stu-id="c8305-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="c8305-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="c8305-242">SoftEther</span></span>
    
- <span data-ttu-id="c8305-243">號交響曲</span><span class="sxs-lookup"><span data-stu-id="c8305-243">Symphony</span></span>
    
- <span data-ttu-id="c8305-244">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="c8305-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="c8305-245">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="c8305-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="c8305-246">Tor</span><span class="sxs-lookup"><span data-stu-id="c8305-246">Tor</span></span>
    
- <span data-ttu-id="c8305-247">TTT</span><span class="sxs-lookup"><span data-stu-id="c8305-247">TTT</span></span>
    
- <span data-ttu-id="c8305-248">在 twitter</span><span class="sxs-lookup"><span data-stu-id="c8305-248">Twitter</span></span>
    
- <span data-ttu-id="c8305-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="c8305-249">WinMX</span></span>
    
- <span data-ttu-id="c8305-250">Winny</span><span class="sxs-lookup"><span data-stu-id="c8305-250">Winny</span></span>
    
- <span data-ttu-id="c8305-251">Yahoo</span><span class="sxs-lookup"><span data-stu-id="c8305-251">Yahoo</span></span>
    
- <span data-ttu-id="c8305-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="c8305-252">Yammer</span></span>
    
- <span data-ttu-id="c8305-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="c8305-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="c8305-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="c8305-254">ArchiveSocial</span></span>

<span data-ttu-id="c8305-255">[ArchiveSocial](https://www.archivesocial.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="c8305-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="c8305-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="c8305-256">Facebook</span></span>
    
- <span data-ttu-id="c8305-257">Flickr</span><span class="sxs-lookup"><span data-stu-id="c8305-257">Flickr</span></span>
    
- <span data-ttu-id="c8305-258">Instagram</span><span class="sxs-lookup"><span data-stu-id="c8305-258">Instagram</span></span>
    
- <span data-ttu-id="c8305-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c8305-259">LinkedIn</span></span>
    
- <span data-ttu-id="c8305-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c8305-260">Pinterest</span></span>
    
- <span data-ttu-id="c8305-261">在 twitter</span><span class="sxs-lookup"><span data-stu-id="c8305-261">Twitter</span></span>
    
- <span data-ttu-id="c8305-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="c8305-262">YouTube</span></span>
    
- <span data-ttu-id="c8305-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="c8305-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="c8305-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="c8305-264">Globanet</span></span>

<span data-ttu-id="c8305-265">[Globanet](https://www.globanet.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="c8305-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="c8305-266">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="c8305-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="c8305-267">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-268">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-269">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-270">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="c8305-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="c8305-271">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="c8305-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="c8305-272">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="c8305-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="c8305-273">Box</span><span class="sxs-lookup"><span data-stu-id="c8305-273">Box</span></span>
    
- <span data-ttu-id="c8305-274">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c8305-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="c8305-275">Cisco IM &amp; Presence Server (v10、 v10.5.1 SU1、 v11.0、 v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="c8305-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="c8305-276">Cisco Webex 小組</span><span class="sxs-lookup"><span data-stu-id="c8305-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="c8305-277">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="c8305-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="c8305-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="c8305-278">CrowdCompass</span></span>

- <span data-ttu-id="c8305-279">自訂分隔符號文字檔</span><span class="sxs-lookup"><span data-stu-id="c8305-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="c8305-280">自訂 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="c8305-280">Custom XML files</span></span>
    
- <span data-ttu-id="c8305-281">Facebook （網頁）</span><span class="sxs-lookup"><span data-stu-id="c8305-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="c8305-282">Factset</span><span class="sxs-lookup"><span data-stu-id="c8305-282">Factset</span></span>
    
- <span data-ttu-id="c8305-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="c8305-283">FXConnect</span></span>
    
- <span data-ttu-id="c8305-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c8305-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="c8305-285">Jive</span><span class="sxs-lookup"><span data-stu-id="c8305-285">Jive</span></span>
    
- <span data-ttu-id="c8305-286">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="c8305-286">Macgregor XIP</span></span>

- <span data-ttu-id="c8305-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c8305-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="c8305-288">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="c8305-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="c8305-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8305-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="c8305-290">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="c8305-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="c8305-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="c8305-291">Mobile Guard</span></span>
    
- <span data-ttu-id="c8305-292">樞紐</span><span class="sxs-lookup"><span data-stu-id="c8305-292">Pivot</span></span>
    
- <span data-ttu-id="c8305-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c8305-293">Salesforce Chatter</span></span>

- <span data-ttu-id="c8305-294">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="c8305-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="c8305-295">商務用 Skype 2007 版 R2 - 2016 (內部部署)</span><span class="sxs-lookup"><span data-stu-id="c8305-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="c8305-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="c8305-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="c8305-297">號交響曲</span><span class="sxs-lookup"><span data-stu-id="c8305-297">Symphony</span></span>
    
- <span data-ttu-id="c8305-298">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="c8305-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="c8305-299">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="c8305-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="c8305-300">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="c8305-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="c8305-301">在 twitter</span><span class="sxs-lookup"><span data-stu-id="c8305-301">Twitter</span></span>
    
- <span data-ttu-id="c8305-302">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="c8305-302">UBS Chat</span></span>
    
- <span data-ttu-id="c8305-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="c8305-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="c8305-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="c8305-304">OpenText</span></span>

<span data-ttu-id="c8305-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="c8305-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="c8305-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="c8305-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="c8305-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="c8305-307">Axs Exchange</span></span>
    
- <span data-ttu-id="c8305-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="c8305-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="c8305-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="c8305-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="c8305-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="c8305-310">Axs Signed</span></span>
    
- <span data-ttu-id="c8305-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c8305-311">Bloomberg</span></span>
    
- <span data-ttu-id="c8305-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="c8305-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="c8305-313">Verba</span><span class="sxs-lookup"><span data-stu-id="c8305-313">Verba</span></span>

<span data-ttu-id="c8305-314">[Verba](https://www.verba.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="c8305-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="c8305-315">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="c8305-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="c8305-316">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="c8305-317">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="c8305-317">Avtec Radio</span></span>
    
- <span data-ttu-id="c8305-318">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="c8305-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="c8305-319">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="c8305-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="c8305-320">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="c8305-321">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-321">Centile Voice</span></span>
    
- <span data-ttu-id="c8305-322">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="c8305-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="c8305-323">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="c8305-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="c8305-324">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="c8305-325">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="c8305-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="c8305-326">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="c8305-327">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="c8305-327">ESChat Radio</span></span>
    
- <span data-ttu-id="c8305-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="c8305-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="c8305-329">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="c8305-330">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="c8305-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="c8305-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="c8305-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="c8305-332">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="c8305-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="c8305-333">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="c8305-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="c8305-334">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="c8305-335">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="c8305-336">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="c8305-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="c8305-337">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="c8305-338">商務用 Skype/Lync IM</span><span class="sxs-lookup"><span data-stu-id="c8305-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="c8305-339">商務用 Skype/Lync Video</span><span class="sxs-lookup"><span data-stu-id="c8305-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="c8305-340">商務用 Skype/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="c8305-341">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="c8305-342">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="c8305-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="c8305-343">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="c8305-344">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="c8305-344">Truphone Voice</span></span>
    
- <span data-ttu-id="c8305-345">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="c8305-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="c8305-346">Windows Desktop Computer Screen</span><span class="sxs-lookup"><span data-stu-id="c8305-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="c8305-347">步驟 2：在 Office 365 中建立及設定協力廠商資料信箱</span><span class="sxs-lookup"><span data-stu-id="c8305-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="c8305-348">以下是建立和設定將資料匯入 Office 365 的協力廠商資料信箱的步驟。</span><span class="sxs-lookup"><span data-stu-id="c8305-348">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="c8305-349">如同先前的說明，項目匯入到此信箱是否協力廠商連接器無法將項目的使用者識別碼對應至 Office 365 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8305-349">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 **<span data-ttu-id="c8305-350">在 Microsoft 365 系統管理中心完成這些工作</span><span class="sxs-lookup"><span data-stu-id="c8305-350">Complete these tasks in the Microsoft 365 admin center</span></span>**
  
1. <span data-ttu-id="c8305-351">在 Office 365 中建立新的使用者帳戶，並將它指派 Exchange Online Plan 2 授權。請參閱[新增使用者至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。</span><span class="sxs-lookup"><span data-stu-id="c8305-351">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="c8305-352">若要讓信箱處於訴訟暫止狀態或啟用封存信箱時不受限制的儲存配額，需要計劃 2 授權。</span><span class="sxs-lookup"><span data-stu-id="c8305-352">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="c8305-353">將協力廠商資料信箱的使用者帳戶新增至 Office 365; 中的**Exchange 系統管理員**系統管理角色請參閱[指派 Office 365 中的系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。</span><span class="sxs-lookup"><span data-stu-id="c8305-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8305-354">請寫下此使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c8305-354">Write down the credentials for this user account.</span></span> <span data-ttu-id="c8305-355">您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。</span><span class="sxs-lookup"><span data-stu-id="c8305-355">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 **<span data-ttu-id="c8305-356">在 Exchange 系統管理中心完成這些工作</span><span class="sxs-lookup"><span data-stu-id="c8305-356">Complete these tasks in the Exchange admin center</span></span>**
  
1. <span data-ttu-id="c8305-357">隱藏通訊錄及其他通訊清單中您的組織; 從協力廠商資料信箱請參閱[Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058)。</span><span class="sxs-lookup"><span data-stu-id="c8305-357">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="c8305-358">或者，您可以執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="c8305-358">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="c8305-359">指派給協力廠商資料信箱的**FullAccess**權限，讓系統管理員或法務人員可以在 Outlook 桌面用戶端; 中開啟的協力廠商資料信箱請參閱[管理收件者的權限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="c8305-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="c8305-360">啟用下列符合性相關 Office 365 功能的協力廠商資料信箱：</span><span class="sxs-lookup"><span data-stu-id="c8305-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="c8305-361">啟用封存信箱;請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限制封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c8305-361">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="c8305-362">這可讓您藉由將協力廠商資料的項目移至封存信箱的封存原則設定的主要信箱中釋放儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c8305-362">This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="c8305-363">這會提供您協力廠商資料的無限儲存容量。</span><span class="sxs-lookup"><span data-stu-id="c8305-363">This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="c8305-364">將協力廠商資料信箱處於 [訴訟暫止] 狀態。</span><span class="sxs-lookup"><span data-stu-id="c8305-364">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="c8305-365">您也可以套用在安全性與合規性中心的 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="c8305-365">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="c8305-366">將此信箱置於保留狀態會保留協力廠商資料項目 （無限期或於指定期間內），並防止從信箱清除郵件。</span><span class="sxs-lookup"><span data-stu-id="c8305-366">Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="c8305-367">請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="c8305-367">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="c8305-368">將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="c8305-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="c8305-369">在 Office 365 中的保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="c8305-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="c8305-370">啟用信箱稽核記錄的擁有者、 代理人及系統管理存取權的協力廠商資料信箱;請參閱 <<c0>啟用 Office 365 中的稽核的信箱。</span><span class="sxs-lookup"><span data-stu-id="c8305-370">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="c8305-371">這樣可讓您以稽核在所具有的存取權的協力廠商資料信箱的任何使用者執行的所有活動。</span><span class="sxs-lookup"><span data-stu-id="c8305-371">This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="c8305-372">步驟 3：設定協力廠商資料的使用者信箱</span><span class="sxs-lookup"><span data-stu-id="c8305-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="c8305-373">下一步是設定使用者信箱以支援協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="c8305-373">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="c8305-374">使用 Exchange 系統管理中心或使用對應的 Windows PowerShell cmdlet，以完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="c8305-374">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="c8305-375">啟用封存信箱的每位使用者。請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限制封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c8305-375">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="c8305-376">將使用者信箱置於訴訟暫止狀態或適用於 Office 365 保留原則;請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="c8305-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="c8305-377">將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="c8305-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="c8305-378">在 Office 365 中的保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="c8305-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="c8305-379">如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="c8305-380">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="c8305-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="c8305-381">最後一個步驟是讓您的合作夥伴具有下列資訊，讓他們可以設定連接器以連接到您的 Office 365 組織，將資料匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="c8305-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="c8305-382">用來連線至 Office 365 中的 Azure 服務的端點：</span><span class="sxs-lookup"><span data-stu-id="c8305-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="c8305-383">登入您在步驟 2 中建立的協力廠商資料信箱的認證 （Office 365 使用者識別碼和密碼）。</span><span class="sxs-lookup"><span data-stu-id="c8305-383">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="c8305-384">協力廠商連接器需要這些認證才能存取項目以及將其匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="c8305-384">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="c8305-385">步驟 5： 在 Azure Active Directory 中註冊的協力廠商資料連接器</span><span class="sxs-lookup"><span data-stu-id="c8305-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="c8305-386">啟動 2018 年 9 月 30 日，Office 365 中的 Azure 服務將開始使用新式驗證在 Exchange Online 來驗證嘗試連線至 Office 365 組織，以匯入資料的協力廠商資料連接器。</span><span class="sxs-lookup"><span data-stu-id="c8305-386">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="c8305-387">這項變更的原因是新式驗證提供比目前的方法根據核准清單第三方連接器用來連線到 Azure 服務先前所述的端點更高的安全性。</span><span class="sxs-lookup"><span data-stu-id="c8305-387">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="c8305-388">若要啟用協力廠商資料連接器，以連線至 Office 365 中，使用新的新式驗證方法，在您的 Office 365 組織中系統管理員必須同意註冊為 Azure Active Directory 中的受信任的服務應用程式的連接器。</span><span class="sxs-lookup"><span data-stu-id="c8305-388">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="c8305-389">這是接受以允許存取貴組織的資料在 Azure Active Directory 連接器的權限要求。</span><span class="sxs-lookup"><span data-stu-id="c8305-389">This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="c8305-390">接受此邀請之後，協力廠商資料連接器會新增為企業應用程式至 Azure Active Directory，並代表服務主要名稱。</span><span class="sxs-lookup"><span data-stu-id="c8305-390">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="c8305-391">如需詳細資訊的同意程序，請參閱[租用戶系統管理員同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="c8305-391">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="c8305-392">以下是步驟來存取，並接受邀請来登錄連接器：</span><span class="sxs-lookup"><span data-stu-id="c8305-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="c8305-393">前往[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，並使用 Office 365 全域系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="c8305-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="c8305-394">下列對話方塊會顯示。</span><span class="sxs-lookup"><span data-stu-id="c8305-394">The following dialog box is displayed.</span></span> <span data-ttu-id="c8305-395">您可以展開檢閱會指派給連接器的權限插入號。</span><span class="sxs-lookup"><span data-stu-id="c8305-395">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/>![權限要求] 對話方塊隨即顯示](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. <span data-ttu-id="c8305-397">按一下 [接受]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8305-397">Click **Accept**.</span></span>

<span data-ttu-id="c8305-398">接受邀請之後，會顯示[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="c8305-398">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="c8305-399">若要檢視您組織的應用程式的清單，請按一下 [ **Azure Active Directory** > **企業應用程式**。</span><span class="sxs-lookup"><span data-stu-id="c8305-399">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="c8305-400">Office 365 協力廠商資料連接器會列在 [**企業應用程式**] 刀鋒視窗上。</span><span class="sxs-lookup"><span data-stu-id="c8305-400">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8305-401">2018 年 9 月 30 日之後, 協力廠商資料將無法再匯入您的組織中的信箱如果您不在 Azure Active Directory 中註冊的協力廠商資料連接器。</span><span class="sxs-lookup"><span data-stu-id="c8305-401">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="c8305-402">也必須依照下列步驟 5 中的程序在 Azure Active Directory 中註冊現有的協力廠商資料連接器 （那些 2018 年 9 月 30 日之前所建立） 的附註。</span><span class="sxs-lookup"><span data-stu-id="c8305-402">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="c8305-403">撤銷同意的協力廠商資料連接器</span><span class="sxs-lookup"><span data-stu-id="c8305-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="c8305-404">您的組織 consents 要在 Azure Active Directory 中註冊的協力廠商資料連接器的權限要求之後，您的組織可以撤銷隨時該同意。</span><span class="sxs-lookup"><span data-stu-id="c8305-404">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="c8305-405">但是，撤銷同意的連接器會代表從協力廠商資料來源的資料將無法再匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8305-405">However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="c8305-406">若要撤銷同意的協力廠商資料連接器，您可以刪除應用程式 （藉由刪除對應的服務主要） 從 Azure 入口網站中，或使用[使用**企業應用程式**] 刀鋒視窗上的 Azure Active Directory移除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)在 Office 365 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c8305-406">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="c8305-407">您也可以在 Azure Active Directory PowerShell 中使用[移除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)指令程式。</span><span class="sxs-lookup"><span data-stu-id="c8305-407">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="c8305-408">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c8305-408">More information</span></span>

- <span data-ttu-id="c8305-409">如先前所述，協力廠商資料來源的項目是匯入至 Exchange 信箱做為電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c8305-409">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="c8305-410">協力廠商連接器會匯入使用 Office 365 API 所需的結構描述的項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-410">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="c8305-411">下表說明協力廠商資料來源的項目在匯入至 Exchange 信箱當做為電子郵件之後的郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="c8305-411">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="c8305-412">表格也會指出郵件屬性是否為必要的。</span><span class="sxs-lookup"><span data-stu-id="c8305-412">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="c8305-413">必須填入必要屬性。</span><span class="sxs-lookup"><span data-stu-id="c8305-413">Mandatory properties must be populated.</span></span> <span data-ttu-id="c8305-414">如果項目遺漏必要的屬性，它不會匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8305-414">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="c8305-415">匯入程序將傳回錯誤訊息，說明為什麼未匯入項目以及遺失哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="c8305-415">The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |**<span data-ttu-id="c8305-416">郵件屬性</span><span class="sxs-lookup"><span data-stu-id="c8305-416">Message property</span></span>**|**<span data-ttu-id="c8305-417">強制嗎？</span><span class="sxs-lookup"><span data-stu-id="c8305-417">Mandatory?</span></span>**|**<span data-ttu-id="c8305-418">描述</span><span class="sxs-lookup"><span data-stu-id="c8305-418">Description</span></span>**|**<span data-ttu-id="c8305-419">範例值</span><span class="sxs-lookup"><span data-stu-id="c8305-419">Example value</span></span>**|
    |:-----|:-----|:-----|:-----|
    |**<span data-ttu-id="c8305-420">FROM</span><span class="sxs-lookup"><span data-stu-id="c8305-420">FROM</span></span>** <br/> |<span data-ttu-id="c8305-421">是</span><span class="sxs-lookup"><span data-stu-id="c8305-421">Yes</span></span>  <br/> |<span data-ttu-id="c8305-422">最初在協力廠商資料來源中建立或傳送項目的使用者。</span><span class="sxs-lookup"><span data-stu-id="c8305-422">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="c8305-423">協力廠商連接器會嘗試將從來源項目 （例如 Twitter 控點） 至 Office 365 使用者帳戶的使用者識別碼對應的所有參與者 （的 FROM 和 TO 欄位中的使用者）。</span><span class="sxs-lookup"><span data-stu-id="c8305-423">The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="c8305-424">郵件副本會匯入至每個參與者的信箱。</span><span class="sxs-lookup"><span data-stu-id="c8305-424">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="c8305-425">如果沒有任何一個項目從參與者可以對應至 Office 365 使用者帳戶，Office 365 中的第三方封存信箱會被匯入項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-425">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="c8305-426">識別為項目的寄件者的參與者必須有 Office 365 組織中的項目匯入至作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="c8305-426">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="c8305-427">如果寄件者沒有作用中的信箱，則會傳回下列錯誤︰</span><span class="sxs-lookup"><span data-stu-id="c8305-427">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**<span data-ttu-id="c8305-428">TO</span><span class="sxs-lookup"><span data-stu-id="c8305-428">TO</span></span>** <br/> |<span data-ttu-id="c8305-429">是</span><span class="sxs-lookup"><span data-stu-id="c8305-429">Yes</span></span>  <br/> |<span data-ttu-id="c8305-430">接收項目的使用者，如果適用於資料來源中的項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |**<span data-ttu-id="c8305-431">主旨</span><span class="sxs-lookup"><span data-stu-id="c8305-431">SUBJECT</span></span>** <br/> |<span data-ttu-id="c8305-432">否</span><span class="sxs-lookup"><span data-stu-id="c8305-432">No</span></span>  <br/> |<span data-ttu-id="c8305-433">來源項目的主旨。</span><span class="sxs-lookup"><span data-stu-id="c8305-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**<span data-ttu-id="c8305-434">日期</span><span class="sxs-lookup"><span data-stu-id="c8305-434">DATE</span></span>** <br/> |<span data-ttu-id="c8305-435">是</span><span class="sxs-lookup"><span data-stu-id="c8305-435">Yes</span></span>  <br/> |<span data-ttu-id="c8305-436">項目最初建立或張貼在客戶資料來源的日期。例如，Twitter 訊息推文的日期。</span><span class="sxs-lookup"><span data-stu-id="c8305-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |**<span data-ttu-id="c8305-437">本文</span><span class="sxs-lookup"><span data-stu-id="c8305-437">BODY</span></span>** <br/> |<span data-ttu-id="c8305-438">否</span><span class="sxs-lookup"><span data-stu-id="c8305-438">No</span></span>  <br/> |<span data-ttu-id="c8305-439">訊息或文章的內容。</span><span class="sxs-lookup"><span data-stu-id="c8305-439">The contents of the message or post.</span></span> <span data-ttu-id="c8305-440">對於某些資料來源，這個屬性的內容可能與 **SUBJECT** 屬性的內容相同。</span><span class="sxs-lookup"><span data-stu-id="c8305-440">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="c8305-441">在匯入程序期間，協力廠商連接器會盡可能嘗試維護內容來源不失真。</span><span class="sxs-lookup"><span data-stu-id="c8305-441">During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="c8305-442">如果可能的話，來源項目的內文中的檔案、圖形或其他內容會包含在此屬性中。</span><span class="sxs-lookup"><span data-stu-id="c8305-442">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="c8305-443">否則，來源項目的內容會包含在 **ATTACHMENT** 屬性。</span><span class="sxs-lookup"><span data-stu-id="c8305-443">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="c8305-444">此屬性的內容取決於來源平台功能和協力廠商連接器上。</span><span class="sxs-lookup"><span data-stu-id="c8305-444">The contents of this property will depend on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**<span data-ttu-id="c8305-445">附件</span><span class="sxs-lookup"><span data-stu-id="c8305-445">ATTACHMENT</span></span>** <br/> |<span data-ttu-id="c8305-446">否</span><span class="sxs-lookup"><span data-stu-id="c8305-446">No</span></span>  <br/> |<span data-ttu-id="c8305-447">如果資料來源 （例如 Twitter 或立即訊息交談中叫） 中的項目已經附加的檔案，或包含圖像，合作夥伴連線將第一次嘗試在**BODY**屬性中包含附件。</span><span class="sxs-lookup"><span data-stu-id="c8305-447">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="c8305-448">如果不可行的則它會新增至 \* \* 附件 \* \* 屬性。</span><span class="sxs-lookup"><span data-stu-id="c8305-448">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="c8305-449">其他附件範例包括 Facebook 的「讚」、內容來源的中繼資料和訊息或文章的回應。</span><span class="sxs-lookup"><span data-stu-id="c8305-449">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |**<span data-ttu-id="c8305-450">MESSAGECLASS</span><span class="sxs-lookup"><span data-stu-id="c8305-450">MESSAGECLASS</span></span>** <br/> |<span data-ttu-id="c8305-451">是</span><span class="sxs-lookup"><span data-stu-id="c8305-451">Yes</span></span>  <br/> | <span data-ttu-id="c8305-452">這是多重值屬性，由合作夥伴連接器建立並填入。</span><span class="sxs-lookup"><span data-stu-id="c8305-452">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="c8305-453">此屬性的格式是`IPM.NOTE.Source.Event`。</span><span class="sxs-lookup"><span data-stu-id="c8305-453">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="c8305-454">(此屬性的開頭必須`IPM.NOTE`; 這種格式是類似的`IPM.NOTE.X`郵件類別。)此屬性包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c8305-454">(This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/>`Source` <span data-ttu-id="c8305-455">-會指出的協力廠商資料來源;例如，Twitter、 Facebook 或 BlackBerry。</span><span class="sxs-lookup"><span data-stu-id="c8305-455">- Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  `Event` <span data-ttu-id="c8305-456">-會指出已執行所產生的項目; 協力廠商資料來源中的活動類型例如，Twitter 或 Facebook 中的張貼叫。</span><span class="sxs-lookup"><span data-stu-id="c8305-456">- Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="c8305-457">事件只適用於資料來源。</span><span class="sxs-lookup"><span data-stu-id="c8305-457">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="c8305-458">此屬性的其中一個用途是要根據項目產生來源位置的資料來源或根據事件類型，篩選特定項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-458">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="c8305-459">例如，在 eDiscovery 搜尋中，您可以建立搜尋查詢來尋找特定使用者所張貼的所有推文。</span><span class="sxs-lookup"><span data-stu-id="c8305-459">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="c8305-460">當項目已成功匯入至 Office 365 中的信箱時的唯一識別碼會傳回回到一部分的 HTTP 回應來電者。</span><span class="sxs-lookup"><span data-stu-id="c8305-460">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="c8305-461">此識別碼 — 呼叫`x-IngestionCorrelationID`— 可用於由協力廠商的項目數的端對端追蹤後續疑難排解用途。</span><span class="sxs-lookup"><span data-stu-id="c8305-461">This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="c8305-462">建議夥伴擷取這項資訊並加以記錄。</span><span class="sxs-lookup"><span data-stu-id="c8305-462">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="c8305-463">以下是顯示此識別碼之 HTTP 回應的範例：</span><span class="sxs-lookup"><span data-stu-id="c8305-463">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="c8305-464">您可以使用安全性與合規性中心中的內容搜尋工具來搜尋協力廠商資料來源匯入至 Office 365 中的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="c8305-464">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="c8305-465">若要搜尋特別針對這些匯入的項目，您可以使用下列郵件屬性值配對關鍵字] 方塊中的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="c8305-465">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="c8305-466">**`kind:externaldata`**-使用此屬性值組來搜尋所有協力廠商資料類型。</span><span class="sxs-lookup"><span data-stu-id="c8305-466">**`kind:externaldata`** - Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="c8305-467">例如，若要搜尋的項目都已匯入與協力廠商資料來源，並匯入的項目之主旨屬性中包含 「 contoso 」 字樣，您會使用關鍵字查詢`kind:externaldata AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="c8305-467">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="c8305-468">**`itemclass:ipm.externaldata.<third-party data type>`**-使用此屬性值組會只搜尋指定資料類型的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="c8305-468">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="c8305-469">例如，若要只搜尋包含主旨屬性中的 「 contoso 」 字樣的 Facebook 資料，您會使用關鍵字查詢`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="c8305-469">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="c8305-470">如需完整清單，要使用的協力廠商資料類型的值`itemclass`屬性，請參閱[使用內容搜尋 」 來搜尋協力廠商資料匯入的 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="c8305-470">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="c8305-471">如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰</span><span class="sxs-lookup"><span data-stu-id="c8305-471">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="c8305-472">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="c8305-472">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="c8305-473">內容搜尋的關鍵字查詢和搜尋條件</span><span class="sxs-lookup"><span data-stu-id="c8305-473">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
