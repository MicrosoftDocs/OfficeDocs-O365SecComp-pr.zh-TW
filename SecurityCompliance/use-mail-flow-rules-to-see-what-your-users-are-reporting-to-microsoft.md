---
title: 使用郵件流程規則來查看您的使用者回報給 Microsoft 哪些內容
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: 您可以建立 Exchange 傳輸規則，以防止使用者傳送電子郵件訊息給 Microsoft 進行分析並用於您自己的安全性程序
ms.openlocfilehash: 7ee8fb2bca1071ccd4080379485c1670a5e66a73
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206406"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用郵件流程規則來查看您的使用者回報給 Microsoft 哪些內容

有多個您可以傳送正誤差與 false 誤判正常的郵件給 Microsoft 進行分析的方式。身為管理員，您可以使用郵件流程規則以查看新使用者會向 Microsoft 回報垃圾郵件、 非垃圾郵件和網路釣魚詐騙。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。相反地，您可以建立 Exchange 傳輸規則，以防止使用者傳送電子郵件訊息給 Microsoft 進行分析並用於您自己的安全性程序。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

預估完成時間：5 分鐘
  
您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 傳輸規則 」 項目和[用戶端和行動裝置權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主題中的 「 web 信箱原則時 outlook 的 App 」 項目。 
  
如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>使用 EAC 來建立檢視使用者手動垃圾郵件]、 [網路釣魚、 及 [不是垃圾郵件報告的郵件流程規則

1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則，如果]** 下選取 **[收件者]**，然後選擇 **[位址包含任何這些文字]**。
    
5. 在 **[指定單字或片語]** 方塊中，執行下列作業： 
    - 類型`abuse@messaging.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後輸入`junk@office365.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)。這些電子郵件地址用來提交誤判正常的郵件給 Microsoft。
    - 類型`phish@office365.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)。此電子郵件地址用來送出未接的網路釣魚訊息給 Microsoft。
    - 類型`false_positive@messaging.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後輸入`not_junk@office365.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)。這些電子郵件地址用來提交誤判的郵件給 Microsoft。
    - 按一下 **[確定]**。
    
6. 在 [**執行下列動作**，選取 [ **[密件副本郵件至...** 與您想要的信箱然後，然後選取 [接收的郵件。 
    
7. 如果您想要您可以讓選取項目稽核規則、 測試規則、 特定時間期間啟動規則和其他選取項目。建議您測試一段之前您強制執行規則。請參閱[mail flow 規則的程序](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。 
    
8. 按一下 **[儲存]** 按鈕儲存規則。它就會出現在規則清單中。 
    
建立並強制執行規則後，從組織傳送至指定的電子郵件地址的任何郵件會複製到指定的信箱。
  

