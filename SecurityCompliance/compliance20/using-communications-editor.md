---
title: 使用溝通編輯器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607569"
---
# <a name="using-the-communications-editor"></a><span data-ttu-id="5eaa5-102">使用通訊編輯器</span><span class="sxs-lookup"><span data-stu-id="5eaa5-102">Using the Communications Editor</span></span>
<span data-ttu-id="5eaa5-103">當您定義入口網站內容的內容、 法律保留通知和相關的 reminders 呈報，您可以運用通訊編輯器來設定的格式和動態自訂您的內容。</span><span class="sxs-lookup"><span data-stu-id="5eaa5-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="5eaa5-104">Rtf 編輯器</span><span class="sxs-lookup"><span data-stu-id="5eaa5-104">Rich-Text Editor</span></span> 

<span data-ttu-id="5eaa5-p101">通訊編輯器可讓使用者自訂使用編輯器選項的文字。例如，使用者可以變更字型類型、 建立項目符號清單、 醒目提示內容及其他。</span><span class="sxs-lookup"><span data-stu-id="5eaa5-p101">The Communications Editor allows user to customize the text using the editor options. For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

<<include screenshot>>

## <a name="merge-field-variables"></a><span data-ttu-id="5eaa5-107">合併欄位變數</span><span class="sxs-lookup"><span data-stu-id="5eaa5-107">Merge Field Variables</span></span>

<span data-ttu-id="5eaa5-p102">您可以運用電子郵件合併變數將通訊本文中嵌入自訂的 okay 屬性從通訊編輯器。傳送至 okay、 時就會以對應的欄位填入合併功能變數。例如時傳送到 okay John Smith，合併功能變數 [Okay 名稱] 將轉譯與對應的名稱。</span><span class="sxs-lookup"><span data-stu-id="5eaa5-p102">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text. When sent to the custodian, the merge field will be populated with the corresponding field. For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="5eaa5-p103">您可以使用電子郵件合併列印欄位選取 [請 rtf 編輯器控制項上方的**合併列印欄位**圖示。版面配置區將會加入根據關閉使用者的資料指標的位置。</span><span class="sxs-lookup"><span data-stu-id="5eaa5-p103">You can use email merge fields by selecting the **Merge Field** icons on the top of the rich-text editor control. The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="5eaa5-113">合併列印欄位變數清單</span><span class="sxs-lookup"><span data-stu-id="5eaa5-113">List of Merge Field Variables</span></span>
| <span data-ttu-id="5eaa5-114">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="5eaa5-114">Field Name</span></span>                  | <span data-ttu-id="5eaa5-115">欄位的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="5eaa5-115">Field Details</span></span> | 
| :------------------- | :-------------------: |
| <span data-ttu-id="5eaa5-116">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="5eaa5-116">Display Name</span></span>  | <span data-ttu-id="5eaa5-117">Okay 的名字與姓氏</span><span class="sxs-lookup"><span data-stu-id="5eaa5-117">Custodian's first and last name</span></span> | 
| <span data-ttu-id="5eaa5-118">認可連結</span><span class="sxs-lookup"><span data-stu-id="5eaa5-118">Acknowledgement Link</span></span>                 | <span data-ttu-id="5eaa5-119">記錄每個 okay 認可的自訂的連結</span><span class="sxs-lookup"><span data-stu-id="5eaa5-119">Customized link to record each custodian's acknowledgement</span></span>                 |
| <span data-ttu-id="5eaa5-120">入口網站的連結</span><span class="sxs-lookup"><span data-stu-id="5eaa5-120">Portal Link</span></span>     | <span data-ttu-id="5eaa5-121">自訂的連結 okay 規範入口網站</span><span class="sxs-lookup"><span data-stu-id="5eaa5-121">Customized link for the custodian's Compliance Portal</span></span>                 |
| <span data-ttu-id="5eaa5-122">發出主管人員</span><span class="sxs-lookup"><span data-stu-id="5eaa5-122">Issuing Officer</span></span>                   | <span data-ttu-id="5eaa5-123">指定發行主管電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="5eaa5-123">Email address of the specified issuing officer</span></span>                   |
| <span data-ttu-id="5eaa5-124">發行日期</span><span class="sxs-lookup"><span data-stu-id="5eaa5-124">Issuing Date</span></span>                   | <span data-ttu-id="5eaa5-125">請注意已發出 (UTC) 的日期</span><span class="sxs-lookup"><span data-stu-id="5eaa5-125">date that the notice was issued (UTC)</span></span>              |