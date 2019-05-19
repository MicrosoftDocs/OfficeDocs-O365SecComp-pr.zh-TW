---
title: 使用精確資料比對建立自訂敏感性資訊類型
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 05/15/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型。
ms.openlocfilehash: 3b15bf0197918d6bbc3897f9fa578c40b70d3f4e
ms.sourcegitcommit: 4eb4ca899adcf4d86501530f875eb49af8cdaeb7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2019
ms.locfileid: "34083186"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification-preview"></a><span data-ttu-id="ceee2-103">使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型 (預覽)</span><span class="sxs-lookup"><span data-stu-id="ceee2-103">See Create a custom sensitive information type with Exact Data Match based classification (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="ceee2-104">概觀</span><span class="sxs-lookup"><span data-stu-id="ceee2-104">Overview</span></span>

<span data-ttu-id="ceee2-105">[自訂敏感性資訊類型](custom-sensitive-info-types.md)用來協助防止意外或不當地共用敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="ceee2-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="ceee2-106">身為系統管理員，您可以使用[安全性與合規性中心](create-a-custom-sensitive-information-type.md)或 [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) 來根據模式、辨識項 (關鍵字如*員工*、*徽章*、*識別碼*等)、鄰近字元 (辨識項與特定模式中字元的鄰近程度)，以及信賴等級，來定義自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ceee2-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="ceee2-107">這類的自訂敏感性資訊類型符合許多組織的業務需求。</span><span class="sxs-lookup"><span data-stu-id="ceee2-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="ceee2-108">不過，如果您想要使用確切資料值，而非使用模式和鄰近的自訂敏感性資訊類型，該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ceee2-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of patterns and proximity?</span></span> <span data-ttu-id="ceee2-109">使用以精確資料比對 (EDM) 為基礎的分類，您可以建立其設計目的為以下的自訂敏感性資訊類型：</span><span class="sxs-lookup"><span data-stu-id="ceee2-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>
- <span data-ttu-id="ceee2-110">動態且可更新；</span><span class="sxs-lookup"><span data-stu-id="ceee2-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="ceee2-111">更可調整；</span><span class="sxs-lookup"><span data-stu-id="ceee2-111">be more scalable;</span></span>
- <span data-ttu-id="ceee2-112">造成較少的誤判；</span><span class="sxs-lookup"><span data-stu-id="ceee2-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="ceee2-113">使用結構化的敏感性資料；</span><span class="sxs-lookup"><span data-stu-id="ceee2-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="ceee2-114">更安全地處理敏感性資訊；以及</span><span class="sxs-lookup"><span data-stu-id="ceee2-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="ceee2-115">能與數個 Microsoft 雲端服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ceee2-115">be used with several Microsoft cloud services.</span></span>

![以 EDM 為基礎的分類](media/EDMClassification.png)

<span data-ttu-id="ceee2-117">以 EDM 為基礎的分類可讓您建立自訂敏感性資訊類型，其參考敏感性資訊資料庫中的確切值。</span><span class="sxs-lookup"><span data-stu-id="ceee2-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="ceee2-118">資料庫可以每日或每週重新整理，而且可以包含最多 1 千萬列資料。</span><span class="sxs-lookup"><span data-stu-id="ceee2-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="ceee2-119">因此，隨著員工、病患或客戶來來去去，以及記錄變更，您的自訂敏感性資訊類型會維持最新且適用。</span><span class="sxs-lookup"><span data-stu-id="ceee2-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="ceee2-120">同時，您可以對原則使用以 EDM 為基礎的分類，例如[資料外洩防護原則](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security 檔案原則](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ceee2-121">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="ceee2-121">Required licenses and permissions</span></span>

- <span data-ttu-id="ceee2-122">您必須是全域管理員、合規性系統管理員或 Exchange Online 系統管理員才能執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="ceee2-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="ceee2-123">若要進一步了解 DLP 權限，請參閱[權限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

- <span data-ttu-id="ceee2-124">在正式推出時，以 EDM 為基礎的分類將包含在下列訂閱中：</span><span class="sxs-lookup"><span data-stu-id="ceee2-124">When generally available, EDM-based classification will be included in the following subscriptions:</span></span>
    - <span data-ttu-id="ceee2-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ceee2-125">Office 365 Enterprise E5</span></span>
    - <span data-ttu-id="ceee2-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ceee2-126">Microsoft 365 E5</span></span>
    - <span data-ttu-id="ceee2-127">Microsoft 365 資訊保護和合規性</span><span class="sxs-lookup"><span data-stu-id="ceee2-127">Microsoft 365 Information Protection and Compliance</span></span>
    - <span data-ttu-id="ceee2-128">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="ceee2-128">Office 365 Advanced Compliance</span></span>

> [!NOTE]
> <span data-ttu-id="ceee2-129">**以 EDM 為基礎的分類**目前對 [Office 365 (包含 Exchange Online 和 Microsoft Teams) 中的 DLP](data-loss-prevention-policies.md) 與 [Cloud App Security](https://docs.microsoft.com/cloud-app-security) 處於預覽。</span><span class="sxs-lookup"><span data-stu-id="ceee2-129">**EDM-based classification is currently in preview** for [DLP in Office 365](data-loss-prevention-policies.md) (with Exchange Online and Microsoft Teams) and [Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="ceee2-130">如果您的組織有 [DLP 功能](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp)，您可以嘗試以 EDM 為基礎的分類。</span><span class="sxs-lookup"><span data-stu-id="ceee2-130">If your organization has [DLP capabilities](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp), you can try EDM-based classification.</span></span> <span data-ttu-id="ceee2-131">如果您還未加入預覽，請[連絡 Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) 來開始。</span><span class="sxs-lookup"><span data-stu-id="ceee2-131">If you are not already participating in the preview, [contact Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) to get started.</span></span> 

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="ceee2-132">工作流程概覽</span><span class="sxs-lookup"><span data-stu-id="ceee2-132">The work flow at a glance</span></span>

|<span data-ttu-id="ceee2-133">階段</span><span class="sxs-lookup"><span data-stu-id="ceee2-133">Phase</span></span>  |<span data-ttu-id="ceee2-134">需要的項目</span><span class="sxs-lookup"><span data-stu-id="ceee2-134">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="ceee2-135">第 1 部分：設定以 EDM 為基礎的分類</span><span class="sxs-lookup"><span data-stu-id="ceee2-135">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="ceee2-136">(視需要)</span><span class="sxs-lookup"><span data-stu-id="ceee2-136">(As needed)</span></span><br/><span data-ttu-id="ceee2-137">- [編輯資料庫結構描述](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="ceee2-137">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="ceee2-138">- [移除結構描述](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="ceee2-138">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="ceee2-139">- 敏感性資料的讀取存取權</span><span class="sxs-lookup"><span data-stu-id="ceee2-139">- Read access to the sensitive data</span></span><br/><span data-ttu-id="ceee2-140">- .xml 格式的資料庫結構描述 (提供範例)</span><span class="sxs-lookup"><span data-stu-id="ceee2-140">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="ceee2-141">- .xml 格式的規則套件 (提供範例)</span><span class="sxs-lookup"><span data-stu-id="ceee2-141">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="ceee2-142">- 安全性與合規性中心的系統管理員權限 (使用 PowerShell)</span><span class="sxs-lookup"><span data-stu-id="ceee2-142">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="ceee2-143">第 2 部分：編製索引及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="ceee2-143">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="ceee2-144">(視需要)</span><span class="sxs-lookup"><span data-stu-id="ceee2-144">(As needed)</span></span><br/>[<span data-ttu-id="ceee2-145">重新整理資料</span><span class="sxs-lookup"><span data-stu-id="ceee2-145">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="ceee2-146">- 自訂安全性群組和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ceee2-146">- Custom security group and user account</span></span><br/><span data-ttu-id="ceee2-147">- 具有 EDM 上傳代理程式電腦的本機系統管理員存取權</span><span class="sxs-lookup"><span data-stu-id="ceee2-147">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="ceee2-148">- 敏感性資料的讀取存取權</span><span class="sxs-lookup"><span data-stu-id="ceee2-148">- Read access to the sensitive data</span></span><br/><span data-ttu-id="ceee2-149">- 重新整理資料的程序和排程</span><span class="sxs-lookup"><span data-stu-id="ceee2-149">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="ceee2-150">第 3 部分：使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="ceee2-150">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="ceee2-151">- 具有 DLP 的 Office 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="ceee2-151">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="ceee2-152">- 已啟用以 EDM 為基礎的分類功能 (預覽)</span><span class="sxs-lookup"><span data-stu-id="ceee2-152">- EDM-based classification feature enabled (in preview)</span></span> |

## <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="ceee2-153">第 1 部分：設定以 EDM 為基礎的分類</span><span class="sxs-lookup"><span data-stu-id="ceee2-153">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="ceee2-154">設定和配置以 EDM 為基礎的分類涉及將敏感性資料儲存為 .csv 格式、定義您的敏感性資訊的資料庫結構描述、建立規則套件，以及上傳結構描述和規則套件。</span><span class="sxs-lookup"><span data-stu-id="ceee2-154">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="ceee2-155">定義用於敏感性資訊的資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="ceee2-155">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="ceee2-156">找出您要使用的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="ceee2-156">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="ceee2-157">將資料匯出至應用程式，例如 Microsoft Excel，並將檔案以 .csv 格式儲存。</span><span class="sxs-lookup"><span data-stu-id="ceee2-157">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="ceee2-158">資料檔案可能包含：</span><span class="sxs-lookup"><span data-stu-id="ceee2-158">The data file can include:</span></span>

    - <span data-ttu-id="ceee2-159">最多 1 千萬列敏感性資料</span><span class="sxs-lookup"><span data-stu-id="ceee2-159">Up to 10 million rows of sensitive data</span></span>
    - <span data-ttu-id="ceee2-160">每個資料來源最多 32 個資料欄 (欄位)</span><span class="sxs-lookup"><span data-stu-id="ceee2-160">Up to 32 columns (fields) per data source</span></span>

2. <span data-ttu-id="ceee2-161">以 .csv 檔案格式將敏感性資料結構化，使得第一列包含用於以 EDM 為基礎的分類的欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="ceee2-161">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="ceee2-162">在您的 .csv 檔案中，您可能會有欄位名稱，例如 "ssn"、"birthdate"、"firstname"、"lastname"，依此類推。</span><span class="sxs-lookup"><span data-stu-id="ceee2-162">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="ceee2-163">舉例來說，我們的 .csv 檔案稱為 *PatientRecords.csv*，且其資料欄包括 *PatientID*、*MRN*、*lastname*、*FirstName*、*SSN* 等。</span><span class="sxs-lookup"><span data-stu-id="ceee2-163">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *lastname*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="ceee2-164">以 .xml 格式定義用於敏感性資訊的資料庫結構描述 (類似以下的範例)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-164">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="ceee2-165">將此結構描述檔案命名為 `edm.xml`，然後設定它，使得資料庫中的每一個資料欄，都會有使用語法 `<Field name="" unique="" searchable=""/>` 的行。</span><span class="sxs-lookup"><span data-stu-id="ceee2-165">Name this schema file `edm.xml`, and configure it such that for each column in the database, there is a line that uses the syntax `<Field name="" unique="" searchable=""/>`.</span></span> 

    - <span data-ttu-id="ceee2-166">使用資料欄名稱作為*欄位名稱*值。</span><span class="sxs-lookup"><span data-stu-id="ceee2-166">Use column names for *Field name* values.</span></span>
    - <span data-ttu-id="ceee2-167">對包含唯一值 (社會安全號碼、識別碼等) 的欄位使用 *unique="true"*；否則請使用 *unique="false"*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-167">Use *unique="true"* for the fields that contain unique values (Social Security numbers, identification numbers, etc.); otherwise, use *unique="false"*.</span></span>
    - <span data-ttu-id="ceee2-168">對您想讓它可供搜尋的欄位使用 *searchable="true"*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-168">Use *searchable="true"* for the fields that you want to be searchable.</span></span> <span data-ttu-id="ceee2-169">請勿對每個資料庫指定超過五個可供搜尋的欄位。</span><span class="sxs-lookup"><span data-stu-id="ceee2-169">Do not specify more than five fields per database to be searchable.</span></span> <span data-ttu-id="ceee2-170">其餘欄位都應該有 *searchable="false"*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-170">All the rest should have *searchable="false"*.</span></span>  

    <span data-ttu-id="ceee2-171">例如，下列 .xml 檔會為病患記錄資料庫定義結構描述，並將五個欄位指定為可供搜尋：*PatientID*、*MRN*、*SSN*、*電話*以及 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-171">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> 
    
    <span data-ttu-id="ceee2-172">(您可以複製、修改及使用我們的範例。)</span><span class="sxs-lookup"><span data-stu-id="ceee2-172">(You can copy, modify, and use our example.)</span></span>
    
    <span data-ttu-id="ceee2-173">\`\`\`<?xml version="1.0" encoding="utf-8"?> <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm"></span><span class="sxs-lookup"><span data-stu-id="ceee2-173"></span></span>
        <span data-ttu-id="ceee2-174"><DataStore name="PatientRecords" description="病患記錄的結構描述</span><span class="sxs-lookup"><span data-stu-id="ceee2-174"><DataStore name="PatientRecords" description="Schema for patient records</span></span>" version="1">
            <span data-ttu-id="ceee2-175"><Field name="PatientID" unique="false" searchable="true" /> <Field name="MRN" unique="false" searchable="true" /></span><span class="sxs-lookup"><span data-stu-id="ceee2-175"></span></span>
            <Field name="FirstName" unique="false" searchable="false" />
            <Field name="LastName" unique="false" searchable="false" />
            <Field name="SSN" unique="false" searchable="true" />
            <Field name="Phone" unique="false" searchable="true" />
            <Field name="DOB" unique="false" searchable="true" />
            <Field name="Gender" unique="false" searchable="false" />
            <Field name="Address" unique="false" searchable="false" />
        </DataStore>
    </EdmSchema>
    ```

4. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

5. To upload the database schema, run the following cmdlets, one at a time:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    You will be prompted to confirm, as follows:

       Confirm
       Are you sure you want to perform this action?
       New EDM Schema for the data store 'patientrecords' will be imported.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: `New-DlpEdmSchema -FileData $edmSchemaXml`
    
Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package. Proceed to the section [Set up a rule package](#set-up-a-rule-package).

#### Editing the schema for EDM-based classification 

(As needed) If you want to make changes to your edm.xml file, such as changing which fields are used for EDM-based classification, follow these steps:

1. Edit your edm.mxl file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).

2. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

3. To update your database schema, run the following cmdlets, one at a time:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    You will be prompted to confirm, as follows:

       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be updated.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: `Set-DlpEdmSchema -FileData $edmSchemaXml`

#### Removing the schema for EDM-based classification

(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:

1. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Run the following PowerShell cmdlet, substituting the data store name of "patientrecords" with the one you want to remove:

    `Remove-DlpEdmSchema -Identity patientrecords`

     You will be prompted to confirm, as follows:
    
       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be removed.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
    
    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: `Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false`

### Set up a rule package

1. Create a rule package in .xml format (with Unicode encoding), similar to the following example. (You can copy, modify, and use our example.) 

   Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*. Our example rule package includes those fields and references the database schema file (edm.xml), with one *ExactMatch* items per searchable field. Consider the following ExactMatch item:

   ```
    <span data-ttu-id="ceee2-176"><ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" > <Pattern confidenceLevel="65"> <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" /> </Pattern> </ExactMatch></span><span class="sxs-lookup"><span data-stu-id="ceee2-176"></span></span>
   ```

    In this example, note the following:

    - The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.
    - The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.
    - The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**. (In this case, we use the existing sensitive information type of U.S. Social Security Number.)

    When you set up your rule package, make sure to correctly reference your .csv file and edm.xml file. (You can copy, modify, and use our example.) 

    ```<?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
      <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
        <Version build="0" major="2" minor="0" revision="0" />
        <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
        <Details defaultLangCode="en-us">
          <LocalizedDetails langcode="en-us">
            <PublisherName>IP DLP</PublisherName>
            <Name>Health Care EDM Rulepack</Name>
            <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
          </LocalizedDetails>
        </Details>
      </RulePack>
      <Rules>
        <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
          <Pattern confidenceLevel="65">
            <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            <Any minMatches ="3" maxMatches ="100">
              <match matches="PatientID" />
              <match matches="MRN"/>
              <match matches="FirstName"/>
              <match matches="LastName"/>
              <match matches="Phone"/>
              <match matches="DOB"/>
            </Any>
          </Pattern>
        </ExactMatch>
        <LocalizedStrings>
          <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
            <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
            <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
          </Resource>
        </LocalizedStrings>
      </Rules>
    </RulePackage>
    ```
    
2. <span data-ttu-id="ceee2-177">執行下列 PowerShell Cmdlet，一次上傳一個規則套件：</span><span class="sxs-lookup"><span data-stu-id="ceee2-177">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

    `$rulepack=Get-Content .\rulepack.xml -Encoding Byte -ReadCount 0`

    `New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack`

<span data-ttu-id="ceee2-178">此時，您已設定以 EDM 為基礎的分類。</span><span class="sxs-lookup"><span data-stu-id="ceee2-178">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="ceee2-179">下一個步驟是要對敏感性資料編製索引及上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="ceee2-179">The next step is to index the sensitive data, and then upload the indexed data.</span></span> 

## <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="ceee2-180">第 2 部分：編製索引及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="ceee2-180">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="ceee2-181">在此階段，您會設定自訂安全性群組和使用者帳戶，並設定 EDM 上傳代理程式工具。</span><span class="sxs-lookup"><span data-stu-id="ceee2-181">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="ceee2-182">然後，您會使用工具來為敏感性資料編製索引，並上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="ceee2-182">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="ceee2-183">設定安全群組和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ceee2-183">Set up the security group and user account</span></span>

1. <span data-ttu-id="ceee2-184">以全域系統管理員身分，移至系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 並建立名為 `EDM_DataUploaders` 的[安全性群組](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-184">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called `EDM_DataUploaders`.</span></span> 

2. <span data-ttu-id="ceee2-185">將一或多個使用者新增至 *EDM_DataUploaders* 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ceee2-185">Add one or more users to the *EDM_DataUploaders* security group.</span></span> <span data-ttu-id="ceee2-186">(這些使用者將管理敏感性資訊的資料庫。)</span><span class="sxs-lookup"><span data-stu-id="ceee2-186">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="ceee2-187">請確定管理敏感性資料的每個使用者，為用於 EDM 上傳代理程式之電腦上的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ceee2-187">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="ceee2-188">設定 EDM 上傳代理程式</span><span class="sxs-lookup"><span data-stu-id="ceee2-188">Set up the EDM Upload Agent</span></span>

> [!NOTE]
> <span data-ttu-id="ceee2-189">在開始此程序之前，請確定您為 *EDM_DataUploaders* 安全性群組的成員和您的電腦上的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ceee2-189">Before you begin this procedure, make sure that you are a member of the *EDM_DataUploaders* security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="ceee2-190">在 [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639) 下載並安裝 EDM 上傳代理程式。</span><span class="sxs-lookup"><span data-stu-id="ceee2-190">Download and install the EDM Upload Agent at [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="ceee2-191">根據預設，安裝位置應該為 `C:\Program Files\Microsoft\EdmUploadAgent`。</span><span class="sxs-lookup"><span data-stu-id="ceee2-191">By default, the installation location should be `C:\Program Files\Microsoft\EdmUploadAgent`.</span></span> 

2. <span data-ttu-id="ceee2-192">若要授權 EDM 上傳代理程式，請開啟 Windows 命令提示字元 (以系統管理員身分)，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ceee2-192">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="ceee2-193">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ceee2-193">Sign in to Office 365 for business with your work or school account.</span></span>

<span data-ttu-id="ceee2-194">下一個步驟是使用 EDM 上傳代理程式來為敏感性資料編製索引，然後上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="ceee2-194">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="ceee2-195">編製索引及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="ceee2-195">Index and upload the sensitive data</span></span>

1. <span data-ttu-id="ceee2-196">將敏感性資料檔案 (回想我們的範例是 *PatientRecords.csv*) 儲存至電腦上的本機磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ceee2-196">Save the sensitive data file (recall our example is *PatientRecords.csv*) to the local drive on the machine.</span></span> <span data-ttu-id="ceee2-197">(我們將範例 *PatientRecords.csv* 檔案儲存至 `C:\Edm\Data`。)</span><span class="sxs-lookup"><span data-stu-id="ceee2-197">(We saved our example *PatientRecords.csv* file to `C:\Edm\Data`.)</span></span>

2. <span data-ttu-id="ceee2-198">若要為敏感性資料編製索引，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ceee2-198">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /CreateHash /DataStoreName <DataStoreName> /DataFile <DataFilePath> /HashLocation <HashedFileLocation>`

    <span data-ttu-id="ceee2-199">範例：**EdmUploadAgent.exe /CreateHash /DataStoreName PatientRecords /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="ceee2-199">Example: **EdmUploadAgent.exe /CreateHash /DataStoreName PatientRecords /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span> 

3. <span data-ttu-id="ceee2-200">若要上傳已編製索引的資料，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ceee2-200">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /UploadHash /DataStoreName <DataStoreName> /HashFile <HashedSourceFilePath>`

    <span data-ttu-id="ceee2-201">範例：**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\Edm\Hash\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="ceee2-201">Example: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\Edm\Hash\PatientRecords.EdmHash**</span></span> 

4. <span data-ttu-id="ceee2-202">若要確認您的敏感性資料已上傳，請在 Windows 命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ceee2-202">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /GetDataStore`

    <span data-ttu-id="ceee2-203">您會看到資料儲存區的清單，以及上次更新時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ceee2-203">You'll see a list of data stores and when they were last updated, similar to the following:</span></span> <br/>![GetDataStore Cmdlet 和結果的範例](media/EDM-GetDataStore-example.png)

5. <span data-ttu-id="ceee2-205">針對[重新整理您的敏感性資訊資料庫](#refreshing-your-sensitive-information-database)，繼續設定程序和排程。</span><span class="sxs-lookup"><span data-stu-id="ceee2-205">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="ceee2-206">此時，您已準備好使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="ceee2-206">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="ceee2-207">例如，您可以[使用以 EDM 為基礎的分類來設定 DLP 原則](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-207">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span> 

### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="ceee2-208">重新整理您的敏感性資訊資料庫</span><span class="sxs-lookup"><span data-stu-id="ceee2-208">Refreshing your sensitive information database</span></span>

<span data-ttu-id="ceee2-209">您可以每日或每週重新整理您的敏感性資訊資料庫，而 EDM 上傳工具可以重新為敏感性資料編製索引，然後重新上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="ceee2-209">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span> 

1. <span data-ttu-id="ceee2-210">決定您重新整理敏感性資訊資料庫的程序和頻率 (每日或每週)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-210">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="ceee2-211">將敏感性資料重新匯出至應用程式，例如 Microsoft Excel，並將檔案儲存為 .csv 格式。</span><span class="sxs-lookup"><span data-stu-id="ceee2-211">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="ceee2-212">當您遵循[編製索引及上傳敏感性資料](#index-and-upload-the-sensitive-data)中所述的步驟時，請保持使用相同的檔案名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="ceee2-212">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ceee2-213">如果 .csv 檔案的結構 (欄位名稱) 沒有任何變更，重新整理資料時，您不需要對資料庫結構描述檔案進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="ceee2-213">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="ceee2-214">但如果您必須進行變更，請務必相應地編輯[資料庫結構描述](#editing-the-schema-for-edm-based-classification)和[規則套件](#set-up-a-rule-package)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-214">But if you must make changes, make sure to edit the [database schema](#editing-the-schema-for-edm-based-classification) and your [rule package](#set-up-a-rule-package) accordingly.</span></span>        

3. <span data-ttu-id="ceee2-215">使用[工作排程器](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)來將[編製索引及上傳敏感性資料](#index-and-upload-the-sensitive-data)程序中的步驟 2 和 3 自動化。</span><span class="sxs-lookup"><span data-stu-id="ceee2-215">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="ceee2-216">您可以使用數個方法來排程工作：</span><span class="sxs-lookup"><span data-stu-id="ceee2-216">You can schedule tasks using several methods:</span></span>
    
    |<span data-ttu-id="ceee2-217">方法</span><span class="sxs-lookup"><span data-stu-id="ceee2-217">Method</span></span>  |<span data-ttu-id="ceee2-218">處理方式</span><span class="sxs-lookup"><span data-stu-id="ceee2-218">What to do</span></span>  |
    |---------|---------|
    |<span data-ttu-id="ceee2-219">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ceee2-219">Windows PowerShell</span></span>     |<span data-ttu-id="ceee2-220">請參閱 [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) 文件，以及本文中的[範例 PowerShell 指令碼](#example-powershell-script-for-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="ceee2-220">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span>|
    |<span data-ttu-id="ceee2-221">工作排程器 API</span><span class="sxs-lookup"><span data-stu-id="ceee2-221">Task Scheduler API</span></span> |<span data-ttu-id="ceee2-222">請參閱[工作排程器](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)文件</span><span class="sxs-lookup"><span data-stu-id="ceee2-222">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span> |
    |<span data-ttu-id="ceee2-223">Windows 使用者介面</span><span class="sxs-lookup"><span data-stu-id="ceee2-223">Windows user interface</span></span>     |<span data-ttu-id="ceee2-224">在 Windows 中，按一下 [開始]\*\*\*\*，然後輸入 `Task Scheduler`。</span><span class="sxs-lookup"><span data-stu-id="ceee2-224">In Windows, click **Start**, and type `Task Scheduler`.</span></span> <span data-ttu-id="ceee2-225">然後在結果清單中，以滑鼠右鍵按一下 [工作排程器]\*\*\*\*，然後選擇 [以系統管理員身分執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-225">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>          |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="ceee2-226">工作排程器的 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="ceee2-226">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="ceee2-227">本節包含的範例 PowerShell 指令碼，可供您用來對編製資料索引及上傳已編製索引的資料工作進行排程：</span><span class="sxs-lookup"><span data-stu-id="ceee2-227">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

```powershell
param([string]$dataStoreName,[string]$fileLocation)
# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\$env:USERNAME"
$edminstallpath = 'C:\Program Files\Microsoft\EdmUploadAgent\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\$dataStoreName$csvext"
$hashFile = "$fileLocation\$dataStoreName$edmext"
# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($creds.Password))
# Register the scheduled task
$taskName = 'EDMUpload_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
## <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="ceee2-228">第 3 部分：使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="ceee2-228">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="ceee2-229">您可以使用以 EDM 為基礎的分類搭配資訊保護功能，例如 [Office 365 DLP 原則](data-loss-prevention-policies.md)與 [Microsoft Cloud App Security 檔案原則](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="ceee2-229">You can use EDM-based classification with information protection features, such as [Office 365 DLP policies](data-loss-prevention-policies.md) and [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span> <span data-ttu-id="ceee2-230">下列程序說明如何使用 EDM 搭配在 Office 365 安全性與合規性中心建立的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="ceee2-230">The following procedure describes how to use EDM with a DLP policy that is created in the Office 365 Security & Compliance Center.</span></span>

### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="ceee2-231">建立 DLP 原則來搭配 EDM</span><span class="sxs-lookup"><span data-stu-id="ceee2-231">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="ceee2-232">前往安全性與合規性中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="ceee2-232">Go to the Security & Compliance Center</span></span>

2. <span data-ttu-id="ceee2-233">按一下 [資料外洩防護]\*\*\*\*  >  [原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-233">Click **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="ceee2-234">選擇 [建立原則]\*\*\*\*  >  [自訂]\*\*\*\*  >  [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-234">Choose **Create a policy** > **Custom** > **Next**.</span></span>

4. <span data-ttu-id="ceee2-235">在 [為您的原則命名]\*\*\*\* 索引標籤下，指定名稱和描述，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-235">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="ceee2-236">在 [選擇位置]\*\*\*\* 索引標籤上，按一下 [讓我選擇特定位置]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-236">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="ceee2-237">![選擇位置選項](media/DLP-EDM-newpolicy-chooselocations.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-237">![Choose locations option](media/DLP-EDM-newpolicy-chooselocations.png)</span></span><br/>

6. <span data-ttu-id="ceee2-238">在 [狀態]\*\*\*\* 資料欄中，選取 [Exchange 電子郵件]\*\*\*\*，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-238">In the **Status** column, select **Exchange email** only, and then choose **Next**.</span></span> <br/><span data-ttu-id="ceee2-239">![僅限 Exchange 的 EDM 原則](media/EDM-DLPpolicy-ExchangeOnly.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-239">![EDM policy with Exchange only](media/EDM-DLPpolicy-ExchangeOnly.png)</span></span><br/>

7. <span data-ttu-id="ceee2-240">在 [原則設定]\*\*\*\* 索引標籤上，選擇 [使用進階設定]\*\*\*\*，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-240">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span><br/><span data-ttu-id="ceee2-241">![使用進階設定](media/edm-dlp-policy-advancedsettings.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-241">![Use advanced settings](media/edm-dlp-policy-advancedsettings.png)</span></span><br/>

8. <span data-ttu-id="ceee2-242">選擇 [+ 新增規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-242">Choose **+ New rule**.</span></span><br/><span data-ttu-id="ceee2-243">![建立規則](media/edm-dlp-newrule.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-243">![Create a transport rule</span></span><br/>

9. <span data-ttu-id="ceee2-244">在 [名稱]\*\*\*\* 區段中，指定規則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="ceee2-244">In the **Name and Type** section, enter a name and description for the Data Analysis view.</span></span><br/><span data-ttu-id="ceee2-245">![新增規則欄位](media/edm-dlp-newruleform.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-245">![New rule fields](media/edm-dlp-newruleform.png)</span></span><br/>

10. <span data-ttu-id="ceee2-246">在 [條件]\*\*\*\* 區段中，於 [+ 新增條件]\*\*\*\* 清單中，選擇 [內容包含敏感性類型]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-246">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="ceee2-247">![內容包含敏感性資訊類型](media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-247">![Content contains sensitive info types](media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="ceee2-248">搜尋您設定規則套件時建立的敏感性資訊類型，然後選擇 [+ 新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-248">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span><br/><span data-ttu-id="ceee2-249">![尋找敏感性資訊類型](media/edm-dlp-newrulefindsensitiverulepack.png)</span><span class="sxs-lookup"><span data-stu-id="ceee2-249">![Find the sensitive info type](media/edm-dlp-newrulefindsensitiverulepack.png)</span></span><br/><span data-ttu-id="ceee2-250">然後選擇 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-250">Then choose **Done**.</span></span>

12. <span data-ttu-id="ceee2-251">完成選取規則的選項，例如**使用者通知**、**使用者覆寫**、**事件報告**，依此類推，然後選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-251">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="ceee2-252">在 [原則設定]\*\*\*\* 索引標籤上，檢閱您的規則，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-252">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="ceee2-253">指定是否立即開啟原則、測試它，或是保持關閉。</span><span class="sxs-lookup"><span data-stu-id="ceee2-253">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="ceee2-254">接著選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-254">Then choose **Next**.</span></span>

15. <span data-ttu-id="ceee2-255">在 [檢閱您的設定]\*\*\*\* 索引標籤上，檢閱您的原則。</span><span class="sxs-lookup"><span data-stu-id="ceee2-255">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="ceee2-256">視需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="ceee2-256">Make any needed modifications.</span></span> <span data-ttu-id="ceee2-257">完成後，選擇 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ceee2-257">When you're ready, choose **Create**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ceee2-258">允許大約一小時的時間，讓您的新 DLP 原則在您的整個資料中心生效。</span><span class="sxs-lookup"><span data-stu-id="ceee2-258">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ceee2-259">相關文章</span><span class="sxs-lookup"><span data-stu-id="ceee2-259">Related articles</span></span>

[<span data-ttu-id="ceee2-260">內建的敏感性資訊類型以及其尋求的目標</span><span class="sxs-lookup"><span data-stu-id="ceee2-260">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="ceee2-261">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="ceee2-261">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="ceee2-262">DLP 原則的概觀</span><span class="sxs-lookup"><span data-stu-id="ceee2-262">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="ceee2-263">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ceee2-263">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)