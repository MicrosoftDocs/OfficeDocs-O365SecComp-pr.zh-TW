---
title: 原則與防護組合的方式時郵件紅色標幟
description: 原則的套用，和電子郵件由 EOP，及/或 ATP 標記惡意程式碼、 垃圾郵件、 高信賴度垃圾郵件、 網路釣魚及大量時採取的動作。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365、 安全中心，ATP、 Windows Defender ATP、 Office 365 ATP、 Azure ATP
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 73f44e747581664f075608d972ee80c8381ca7fd
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30994833"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>哪些原則適用於何時多個保護方法與在您的電子郵件上執行的偵測掃描

有可能，傳入的郵件可能由多個表單的保護 (例如這兩個 EOP*和*ATP)，加上標幟並多個偵測掃描 （例如垃圾郵件*和*網路釣魚）。 這是可行的因為有 ATP 防網路釣魚原則 ATP 的客戶，與 EOP 客戶的 EOP 反網路釣魚原則。 這也表示郵件可能會瀏覽多個偵測掃描惡意程式碼、 網路釣魚，與使用者模擬，例如。 指定所有此活動，可能會有哪些原則適用於某些混淆。

一般而言，在**CAT （類別）** 屬性中的**X Forefront-反垃圾郵件報告**標頭中識別套用至郵件的原則。 如果您有多個反網路釣魚原則時，會套用在最高優先順序的一個。

下列的原則套用到_所有組織_。

|Priority (優先順序) |原則  |類別  |受管理的位置 |
|---------|---------|---------|---------|
|1     | 惡意程式碼      | MALW      | 惡意程式碼原則   |
|2     | 網路釣魚     | PHSH     | 設定您的垃圾郵件篩選原則     |
|3     | 高信賴度的垃圾郵件      | HSPM        | 設定您的垃圾郵件篩選原則        |
|4     | 詐騙        | SPOOF        | 反網路釣魚原則，詐騙智慧        |
|5     | 垃圾郵件         | SPM         | 設定您的垃圾郵件篩選原則         |
|6     | 大量         | BULK        | 設定您的垃圾郵件篩選原則         |

此外，這些原則套用至_組織的 ATP_。

|Priority (優先順序) |原則  |類別  |受管理的位置 |
|---------|---------|---------|---------|
|7     | 網域冒充         | DIMP         | 設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則        |
|8     | 使用者冒充        | UIMP         | 設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則         |

例如，如果您有兩個原則有其各自的優先順序：

|原則  |Priority (優先順序)  |使用者/網域冒充  |反詐騙  |
|---------|---------|---------|---------|
|A     | 1        | 開啟        |關閉         |
|B     | 2        | 關閉        | 開啟        |

如果郵件有已識別為_使用者模擬_和_詐騙_（請參閱反詐騙於上表中），而且相同一組使用者原則的範圍限於原則 B，郵件加上標幟，並視為_詐騙_。 不過，因為而雖然詐騙執行較高的優先順序 (4) 的多使用者模擬 (8)、 反詐騙已關閉，會不套用任何動作。

請記住，系統管理員可以建立優先的清單中的原則 （請參閱上方的 [優先順序] 欄位），但只能將一個原則將會執行，並將其動作套用。 表示原則 A 和 B 中的使用者會有較高優先順序原則 （A 是 #1） 執行，且郵件不會篩選透過任何進一步的原則。 如果反 spoofiing 已關閉，將會不執行任何動作。

因為可能會在多個原則中有許多使用者群組，它可能 behoove 系統管理員，請考慮使用較少的原則與更多的功能。 務必確定完整原則所涵蓋的所有使用者。

若要讓其他類型的網路釣魚原則套用，您將需要調整的各種不同的原則套用到使用者的設定。



