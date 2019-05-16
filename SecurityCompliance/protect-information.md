---
title: 保護資訊
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 保護資訊的登陸頁面
ms.openlocfilehash: 696684778604f4259166bdc3059944285833cba1
ms.sourcegitcommit: 4eb4ca899adcf4d86501530f875eb49af8cdaeb7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2019
ms.locfileid: "34083176"
---
# <a name="protect-information"></a>保護資訊

Microsoft 365 和 Office 365 包含可以套用到特定類型的資料來保護資訊的功能。


|**功能**|**詳細資訊**|
|:-----|:-----|
|[敏感度標籤](sensitivity-labels.md) <br/> |使用敏感度標籤中，您可以分類並協助保護敏感內容。 防護選項，包括標籤、 浮水印及加密。 敏感度標籤會使用 Azure 資訊保護。 如果您使用 Azure 資訊保護標籤，現在我們建議您避免在其他中建立新的標籤系統置中直到您已完成的移轉之後。 請參閱[Azure 資訊保護移轉](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels)。 <br/> [保留標籤](retention-policies.md)是不同的敏感度標籤。 保留標籤可以幫助您保留或刪除內容根據您定義的原則。 這些可協助組織遵守產業法規及內部原則。|
|[資料外洩防護](data-loss-prevention-policies.md)(DLP)  <br/> |使用 DLP 原則，您可以識別、 監視和自動保護 Office 365 中的敏感資訊。 資料外洩防護原則可以使用敏感度標籤和敏感資訊類型來識別敏感資訊。 <br/> |
|[敏感資訊類型](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 也包含許多準備好讓您可以使用 DLP 原則中，以及自動分類敏感度與保留標籤的敏感資訊類型。 敏感資訊類型也可用的[Azure 資訊保護掃描器](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)來分類及保護內部部署檔案。 敏感資訊類型定義如何自動化程序會辨識特定資訊類型，例如健康服務號碼與信用卡號碼。   <br/> |
|[Office 365 郵件加密](ome.md)(OME)  <br/> |使用 Office 365 郵件加密，組織可以傳送和接收您組織內部和外部的人員之間的加密的電子郵件訊息。 Office 365 郵件加密的運作與 Outlook.com、 yahoo ！、 Gmail，以及其他電子郵件服務。 電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。 <br/> |
|[Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |Azure 資訊保護 （有時稱為 AIP） 可協助組織，以分類、 標籤，並選擇性地保護文件和電子郵件。 系統管理員可以自動將標籤套用所定義的規則和條件。 使用者可以手動將標籤套用至檔案和郵件。 您也可以提供使用者需套用標籤時機的建議。<br/> 如果您使用敏感度標籤或 Office 郵件加密，您已經在使用分類及保護功能。 如果您還未移轉至 Office 365 的 Azure 資訊保護標籤，繼續進行 Azure 資訊保護中管理這些。  <br/>您可以執行[Azure 資訊保護掃描器](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)來分類及保護 Windows 伺服器、 網路共用、 SharePoint Server 網站和文件庫上的檔案內部。 這可以是用來識別資料移轉到 Office 365 的第一個步驟。
|使用客戶管理的加密金鑰的 azure 資訊保護 <br/> |某些組織基於業務需求或規範需求来保留的加密金鑰的控制項。 這並不常見。 Azure 資訊保護可讓組織將您自己的金鑰 (BYOK) 移至服務。 如需詳細資訊，請參閱 <<c0>提到您自己的 Azure 資訊保護的金鑰 (BYOK)。 另一個較複雜的選項被提供的保留內部部署，加密金鑰稱為保留您自己的金鑰 (HYOK) 的需求的客戶。  如需詳細資訊，請參閱[保留您自己的 Azure 資訊保護的金鑰 (HYOK)](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions)。 <br/> |
    

