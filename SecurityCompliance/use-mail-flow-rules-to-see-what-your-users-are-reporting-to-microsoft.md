---
title: 使用以查看您的使用者會報告給 Microsoft 的郵件流程規則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/23/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: 您可以建立 Exchange 傳輸規則，以防止使用者傳送電子郵件訊息給 Microsoft 進行分析並用於您自己的安全性程序
ms.openlocfilehash: f2376668e2a1a16eba9913178a100fc31763b227
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026770"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用以查看您的使用者會報告給 Microsoft 的郵件流程規則

有多個您可以傳送正誤差與 false 誤判正常的郵件給 Microsoft 進行分析的方式。身為管理員，您可以使用郵件流程規則以查看新使用者會向 Microsoft 回報垃圾郵件、 非垃圾郵件和網路釣魚詐騙。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。相反地，您可以建立 Exchange 傳輸規則，以防止使用者傳送電子郵件訊息給 Microsoft 進行分析並用於您自己的安全性程序。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

預估完成時間：5 分鐘
  
您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 傳輸規則 」 項目和[用戶端和行動裝置權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主題中的 「 Outlook Web App 信箱原則 」 項目。 
  
如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>使用 EAC 來建立檢視使用者手動垃圾郵件]、 [網路釣魚、 及 [不是垃圾郵件報告的郵件流程規則
<a name="sectionSection1"> </a>

1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則，如果]** 下選取 **[收件者]**，然後選擇 **[位址包含任何這些文字]**。
    
5. 在 **[指定單字或片語]** 方塊中，執行下列作業： 
    - 輸入 **abuse@messaging.microsoft.com**，然後按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png)，接著輸入 **junk@office365.microsoft.com**，然後按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png)。這些電子郵件地址可用來將誤判正常郵件提交給 Microsoft。
    - 輸入**phish@office365.microsoft.com** ] 和 [![新增圖示](media/ITPro-EAC-AddIcon.png)。此電子郵件地址用來送出未接的網路釣魚訊息給 Microsoft。
    - 輸入 **false_positive@messaging.microsoft.com**，然後按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png)，接著輸入 **not_junk@office365.microsoft.com**，然後按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png)。這些電子郵件地址可用來將誤判郵件提交給 Microsoft。
    - 按一下 **[確定]**。
    
6. 在 [**執行下列動作**，選取 [ **[密件副本郵件至...** 與您想要的信箱然後，然後選取 [接收的郵件。 
    
7. 您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。施行規則之前，建議先測試規則一段時間。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) 包含這些選擇的詳細資訊。 
    
8. 按一下 **[儲存]** 按鈕儲存規則。它就會出現在規則清單中。 
    
建立並強制執行規則後，從組織傳送至指定的電子郵件地址的任何郵件會複製到指定的信箱。
  

