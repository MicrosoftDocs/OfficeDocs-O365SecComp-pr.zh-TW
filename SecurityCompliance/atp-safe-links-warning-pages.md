---
title: Office 365 ATP 安全連結警告頁面
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: IT Pro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
description: 取得您可能會看到 Office 365 進階威脅保護位於工時警告頁面的概觀。
ms.openlocfilehash: eae893da6bb2692ae4fb9f934bc892d2058beecd
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782130"
---
# <a name="office-365-atp-safe-links-warning-pages"></a>Office 365 ATP 安全連結警告頁面

[Office 365 的進階的威脅保護](office-365-atp.md)(ATP) 可協助保護您的組織網路釣魚嘗試及透過功能，例如[ATP 安全連結](atp-safe-links.md)、 [ATP 安全附件](atp-safe-attachments.md)及[反網路釣魚保護](anti-phishing-protection.md)惡意程式碼。備妥保護時，就會檢查電子郵件訊息與 Office 文件中的連結 (Url)。如果 URL 會被識別為可疑或惡意，可能會遭到封鎖在按一下時開啟 URL。而非直接進入網站，您可能會看到警告] 頁面。 
  
請閱讀本篇文章以查看[警告頁面的範例](atp-safe-links-warning-pages.md#examples)，以及[最近使用更新為警告頁面](atp-safe-links-warning-pages.md#updates)可能會出現。
  
## <a name="examples-of-warning-pages"></a>警告頁面的範例

### <a name="atp-is-scanning-the-link"></a>ATP 會掃描連結

URL 是要掃描的 ATP 安全的連結。您可能必須等候幾分鐘再試一次] 連結。

![ATP 會掃描連結](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a>URL 是可疑的電子郵件訊息

URL 是似乎類似於其他視為可疑的電子郵件訊息的電子郵件訊息中。我們建議您再次檢查電子郵件再繼續進行至網站。

![此 URL 會在可疑的電子郵件訊息](media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>URL 會被識別為網路釣魚嘗試在郵件中

URL 會被識別為網路釣魚攻擊電子郵件訊息中。因此，封鎖電子郵件中的所有 Url。我們建議您不要不繼續至網站。

![此 URL 會被識別為網路釣魚嘗試在郵件中](media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a>站台已識別為惡意

URL 指向已識別為惡意的網站。  <br/> 我們建議您不要不繼續至網站。

![此網站已識別為惡意](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a>封鎖網站

您的組織會封鎖 URL。有數個原因可能會封鎖 URL 的原因。我們建議您連絡組織的 Office 365 系統管理員。

![封鎖此站台](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a>發生錯誤

發生錯誤的某種類型，並無法開啟 URL。

![發生錯誤](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a>警告頁面新版更新

Office 365 ATP 最近已更新數個警告頁面。如果尚未準備看到 [更新] 頁面，您將推出。更新加入新的色彩配置、 詳細資訊，並繼續進行至而不管的特定警告和建議的網站的能力。

### <a name="url-scan-in-progress"></a>進行中的 URL 掃描

原始的警告] 頁面上：

![原始的警告] 頁面上進行中的 URL 掃描的相關](media/04368763-763f-43d6-94a4-a48291d36893.png)

更新的警告] 頁面上：

![ATP 會掃描連結](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>惡意網站警告

原始的警告] 頁面上：

![原始的警告] 頁面上的惡意網站的相關](media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

更新的警告] 頁面上：

![此網站已識別為惡意](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>封鎖 URL 警告

原始的警告] 頁面上：

![原始的警告] 頁面上的封鎖 URL 的相關](media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

更新的警告] 頁面上：

![封鎖此站台](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>「 發生錯誤 」 警告] 頁面

原始的警告] 頁面上：

![原始"發生錯誤 」 警告] 頁面](media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

更新的警告] 頁面上：

![發生錯誤](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
   
## <a name="related-topics"></a>相關主題

[Office 如何協助您免受網路釣魚配置](https://support.office.com/article/be0de46a-29cd-4c59-aaaf-136cf177d593)
  
[Office 365 ATP 安全連結](atp-safe-links.md)
  
[Office 365 ATP 安全附件](atp-safe-attachments.md)
  
[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)
  

