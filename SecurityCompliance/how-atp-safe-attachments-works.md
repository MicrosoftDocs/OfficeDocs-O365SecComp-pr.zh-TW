---
title: Office 365 ATP 安全附件的運作方式
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: '[安全附件] 功能可提供電子郵件附件的按一下時間驗證。 使用安全附件來保護您的組織, 防止他人以電子郵件傳送或接收的惡意檔案。'
ms.openlocfilehash: 99d31e327343971f6a7630e2a43ffd3044fbf976
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/30/2019
ms.locfileid: "34592251"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a><span data-ttu-id="00885-104">Office 365 ATP 安全附件的運作方式</span><span class="sxs-lookup"><span data-stu-id="00885-104">How ffice 365 ATP Safe Attachments works</span></span>

## <a name="how-it-works"></a><span data-ttu-id="00885-105">運作方式</span><span class="sxs-lookup"><span data-stu-id="00885-105">How it works</span></span>

<span data-ttu-id="00885-106">ATP 安全附件功能會檢查您組織中人員的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="00885-106">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="00885-107">當 ATP 安全附件原則到位, 且該原則所涵蓋的人員會在 Office 365 中查看其電子郵件時, 會檢查其電子郵件附件, 並根據您的 ATP 安全附件原則採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="00885-107">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="00885-108">根據您的原則定義方式, 使用者可以繼續運作, 而不需要知道他們是否已傳送惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="00885-108">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="00885-109">以下是工作中 ATP 安全附件的兩個範例。</span><span class="sxs-lookup"><span data-stu-id="00885-109">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="00885-110">**範例 1: 電子郵件附件**假設您會收到具有附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="00885-110">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="00885-111">如果附件是安全的, 或實際包含的惡意程式碼是用來竊取使用者認證的, 並不是顯而易見的。</span><span class="sxs-lookup"><span data-stu-id="00885-111">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="00885-112">在「管理員」的組織中, 安全性管理員在幾天前定義 ATP 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="00885-112">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="00885-113">使用 ATP 安全附件功能時, 電子郵件附件會在虛擬環境中開啟和測試, 然後才會收到。</span><span class="sxs-lookup"><span data-stu-id="00885-113">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="00885-114">如果附件被判定為惡意, 就會自動將其移除。</span><span class="sxs-lookup"><span data-stu-id="00885-114">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="00885-115">如果附件是安全的, 當您按一下時, 它會如預期的方式開啟。</span><span class="sxs-lookup"><span data-stu-id="00885-115">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="00885-116">**範例 2: SharePoint Online 中的**檔案假設 Jean-francois 收到檔案, 並將其上傳至 SharePoint Online 中的文件庫。</span><span class="sxs-lookup"><span data-stu-id="00885-116">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="00885-117">Jean-francois 會與小組的其餘部分共用檔案的連結, 而不知道該檔案實際上是惡意的。</span><span class="sxs-lookup"><span data-stu-id="00885-117">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="00885-118">幸運的是, [SharePoint、OneDrive 及 Microsoft 團隊的 ATP](atp-for-spo-odb-and-teams.md)會偵測惡意檔案並加以封鎖。</span><span class="sxs-lookup"><span data-stu-id="00885-118">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="00885-119">幾天之後, Chris 會開啟檔。</span><span class="sxs-lookup"><span data-stu-id="00885-119">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="00885-120">雖然 Chris 可以看到該檔案, 但是 Chris 無法開啟或共用, 這會保護 Chris 的電腦與其他惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="00885-120">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="00885-121">ATP 安全附件原則可以套用至組織中的特定人員或群組, 或套用至整個網域。</span><span class="sxs-lookup"><span data-stu-id="00885-121">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="00885-122">此外, ATP 安全附件原則可以設定為在掃描實際附件時使用預留位置附件。</span><span class="sxs-lookup"><span data-stu-id="00885-122">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="00885-123">若要深入瞭解, 請參閱**[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="00885-123">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="00885-124">ATP 安全附件掃描會在您的 Office 365 資料所在的同一個區域中進行。</span><span class="sxs-lookup"><span data-stu-id="00885-124">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="00885-125">如需資料中心地理位置的詳細資訊, 請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="00885-125">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

