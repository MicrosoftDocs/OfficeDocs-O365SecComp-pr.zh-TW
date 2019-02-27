---
title: 使用通訊編輯器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c2957c88217bce4c9a34f8d3f9a9e291f1223cc9
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30294966"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="f5799-102">使用通訊編輯器</span><span class="sxs-lookup"><span data-stu-id="f5799-102">Use the communications editor</span></span>

<span data-ttu-id="f5799-103">當您定義入口網站內容的內容、 法律保留通知和相關的 reminders 呈報，您可以運用通訊編輯器來設定的格式和動態自訂您的內容。</span><span class="sxs-lookup"><span data-stu-id="f5799-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="f5799-104">Rtf 編輯器</span><span class="sxs-lookup"><span data-stu-id="f5799-104">Rich text editor</span></span> 

<span data-ttu-id="f5799-p101">通訊編輯器可讓使用者自訂使用編輯器選項的文字。例如，使用者可以變更字型類型、 建立項目符號清單、 醒目提示內容及其他。</span><span class="sxs-lookup"><span data-stu-id="f5799-p101">The Communications Editor allows user to customize the text using the editor options. For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="f5799-107">合併欄位變數</span><span class="sxs-lookup"><span data-stu-id="f5799-107">Merge field variables</span></span>

<span data-ttu-id="f5799-p102">您可以運用電子郵件合併變數將通訊本文中嵌入自訂的 okay 屬性從通訊編輯器。傳送至 okay、 時就會以對應的欄位填入合併功能變數。例如時傳送到 okay John Smith，合併功能變數 [Okay 名稱] 將轉譯與對應的名稱。</span><span class="sxs-lookup"><span data-stu-id="f5799-p102">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text. When sent to the custodian, the merge field will be populated with the corresponding field. For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="f5799-p103">您可以使用電子郵件合併列印欄位選取 [請 rtf 編輯器控制項上方的**合併列印欄位**圖示。版面配置區將會加入根據關閉使用者的資料指標的位置。</span><span class="sxs-lookup"><span data-stu-id="f5799-p103">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control. The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="f5799-113">合併列印欄位變數清單</span><span class="sxs-lookup"><span data-stu-id="f5799-113">List of merge field variables</span></span>

| <span data-ttu-id="f5799-114">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="f5799-114">Field name</span></span>                  | <span data-ttu-id="f5799-115">欄位的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f5799-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="f5799-116">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="f5799-116">Display Name</span></span>  | <span data-ttu-id="f5799-117">Okay 的名字與姓氏。</span><span class="sxs-lookup"><span data-stu-id="f5799-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="f5799-118">認可連結</span><span class="sxs-lookup"><span data-stu-id="f5799-118">Acknowledgement Link</span></span> | <span data-ttu-id="f5799-119">記錄每個 okay 認可自訂的連結。</span><span class="sxs-lookup"><span data-stu-id="f5799-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="f5799-120">入口網站的連結</span><span class="sxs-lookup"><span data-stu-id="f5799-120">Portal Link</span></span>     | <span data-ttu-id="f5799-121">自訂 okay 規範入口網站的連結。</span><span class="sxs-lookup"><span data-stu-id="f5799-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="f5799-122">發出主管人員</span><span class="sxs-lookup"><span data-stu-id="f5799-122">Issuing Officer</span></span>                   | <span data-ttu-id="f5799-123">指定發行主管電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f5799-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="f5799-124">發行日期</span><span class="sxs-lookup"><span data-stu-id="f5799-124">Issuing Date</span></span>                   | <span data-ttu-id="f5799-125">日期明已核發給 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="f5799-125">The date that the notice was issued (UTC).</span></span>              |