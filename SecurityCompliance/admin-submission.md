---
title: 在 Office 365 中，O365 提交，Office 365 垃圾郵件問題，O365 誤判系統提交提交 office 365 中的釣魚程式、 送出掃描、 可疑的電子郵件，Office 365 中的電子郵件、 掃描郵件、 有 Microsoft 掃描的釣魚程式]，讓 Microsoft 的垃圾郵件掃描巨集、 送出電子郵件、 送出電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何送出可疑的電子郵件，可能的網路釣魚郵件、 垃圾郵件，以及其他可能有害的郵件、 Url 和檔案從您的 Office 365 租用戶給 Microsoft 進行掃描。
ms.openlocfilehash: 5a909e8b587e2a1265c1b2afbd5e063d46a04e2c
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230947"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="5d7dd-103">如何送出可疑的垃圾郵件、 釣魚程式、 Url 和 microsoft Office 365 掃描的檔案</span><span class="sxs-lookup"><span data-stu-id="5d7dd-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="5d7dd-104">系統管理員可以傳送電子郵件掃描由 Microsoft Office 365 中使用的檔案或網路郵件 ID、 Url 和檔案。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="5d7dd-105">更新送出資料] 區段中仍然會包含使用者所報告的郵件，並可供所有客戶使用 EOP。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="5d7dd-106">當您提交的電子郵件時，您會收到郵件中的可能已允許內送電子郵件到您的租用戶，任何原則的相關資訊以及檢查任何 Url 和附件。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="5d7dd-107">可能已允許郵件的原則包含個別使用者的安全寄件者清單，以及您在租用戶層級原則，例如 ETR 規則。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="5d7dd-108">如何提交給 Microsoft 的 Office 365 掃描的內容</span><span class="sxs-lookup"><span data-stu-id="5d7dd-108">How to submit content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="5d7dd-109">若要提交給 Microsoft 的內容按一下最左側的 [送出資料] 頁面上的 [**新的送出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="5d7dd-110">頁面右側彈出式視窗會顯示送出任一電子郵件、 URL，或檔案的選項。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-an-email-to-microsoft"></a><span data-ttu-id="5d7dd-111">提交給 Microsoft 電子郵件</span><span class="sxs-lookup"><span data-stu-id="5d7dd-111">Submit an email to Microsoft</span></span>
![電子郵件送出範例](media/submission-flyout-email.PNG)
1. <span data-ttu-id="5d7dd-113">若要提交的電子郵件，選取 [**電子郵件**和指定**網路郵件識別碼**的電子郵件或電子郵件檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="5d7dd-114">指定您想要執行原則檢查的收件者。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="5d7dd-115">原則檢查會決定電子郵件是否略過掃描由於使用者或租用戶層級原則。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="5d7dd-116">指定是否電子郵件應被封鎖與否。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="5d7dd-117">如果應該已封鎖電子郵件，指定如果它應該已封鎖為垃圾郵件、 網路釣魚或惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="5d7dd-118">如果您不確定哪種類型可能是，使用您的最佳 judgement。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="5d7dd-119">如果由於原則提交時略過篩選，您會看到該原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="5d7dd-120">如果因為一或多個原則不略過篩選，將會在幾分鐘的時間內完成掃描。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="5d7dd-121">在 [狀態] 連結，即可看到提交的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="5d7dd-122">這包括原則檢查和掃描 verdict 的結果。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="5d7dd-123">請注意這不會透過 Office 365 ATP 完整篩選堆疊一次執行電子郵件，但會執行部分重新掃描郵件、 URL 或檔案的某些屬性為基礎。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="5d7dd-124">按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-124">Click the **Submit** button.</span></span>

### <a name="submit-a-url-to-microsoft"></a><span data-ttu-id="5d7dd-125">提交給 Microsoft 的 URL</span><span class="sxs-lookup"><span data-stu-id="5d7dd-125">Submit a URL to Microsoft</span></span>
![電子郵件送出範例](media/submission-url-flyout.png)
1. <span data-ttu-id="5d7dd-127">若要提交 URL 從彈出式視窗中選取**URL** 。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="5d7dd-128">輸入完整的 URL 包括通訊協定 (**https://**)。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="5d7dd-129">如果您選取**應被篩選**，請指定 URL 如果是網路釣魚或惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="5d7dd-130">按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-file-to-microsoft"></a><span data-ttu-id="5d7dd-131">提交給 Microsoft 檔案</span><span class="sxs-lookup"><span data-stu-id="5d7dd-131">Submit a file to Microsoft</span></span>
![電子郵件送出範例](media/submission-file-flyout.PNG)
1. <span data-ttu-id="5d7dd-133">提交從彈出式檔案選取**檔案**並上傳檔案至您想要掃描。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="5d7dd-134">按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d7dd-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5d7dd-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="5d7dd-135">Related topics</span></span>

[<span data-ttu-id="5d7dd-136">Office 365 進階的威脅保護計劃 2</span><span class="sxs-lookup"><span data-stu-id="5d7dd-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="5d7dd-137">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="5d7dd-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="5d7dd-138">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="5d7dd-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

