---
title: 將 SIEM 伺服器與 Office 365 雲端 App 安全性整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: 您可以使用 Office 365 雲端應用程式安全性整合 SIEM 伺服器。請閱讀本篇文章以取得它的運作方式，以及如何設定它的概觀。
ms.openlocfilehash: 6b9d51d91d4b1ae55dd0dd16a92872daa4ecef90
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "23043261"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="18c1a-104">將 SIEM 伺服器與 Office 365 雲端 App 安全性整合</span><span class="sxs-lookup"><span data-stu-id="18c1a-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="18c1a-105">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="18c1a-105">****Evaluation** \>**</span></span>|<span data-ttu-id="18c1a-106">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="18c1a-106">****Planning** \>**</span></span>|<span data-ttu-id="18c1a-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="18c1a-107">****Deployment** \>**</span></span>|<span data-ttu-id="18c1a-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="18c1a-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="18c1a-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="18c1a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="18c1a-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="18c1a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="18c1a-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="18c1a-111">You are here!</span></span>  <br/> [<span data-ttu-id="18c1a-112">下一步</span><span class="sxs-lookup"><span data-stu-id="18c1a-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="18c1a-113">開始使用</span><span class="sxs-lookup"><span data-stu-id="18c1a-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="18c1a-p102">您可以整合[Office 365 雲端應用程式的安全性](get-ready-for-office-365-cas.md)與安全性資訊和事件管理 (SIEM) 伺服器以啟用集中式監視的提醒。這是特別有用的使用雲端服務的組織與內部伺服器應用程式。整合和 SIEM server 可讓您更妥善地保護同時維持自動化特定安全性程序並相互關聯有所助益之間雲端架構的一般安全性的工作流程] 的 [您的 Office 365 應用程式的安全性小組與內部事件。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p102">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts. This is especially beneficial for organizations who are using cloud services and on-premises server applications. Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="18c1a-p103">當您第一次使用 Office 365 雲端應用程式安全性整合 SIEM 伺服器時，從最後一個兩天的通知轉寄給 SIEM 伺服器上，為所有的提醒從加上 then 上 （根據您選取任何篩選器）。此外，如果您停用此功能段，當您再次啟用它，它會轉寄過去兩天的警示，然後所有通知從然後起。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p103">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select). Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>
 
## <a name="siem-integration-architecture"></a><span data-ttu-id="18c1a-119">SIEM 整合架構</span><span class="sxs-lookup"><span data-stu-id="18c1a-119">SIEM integration architecture</span></span>

<span data-ttu-id="18c1a-p104">SIEM 代理程式已設定在貴組織的網路。當部署和設定 SIEM 代理程式會提取所設定的資料類型 （警示） 使用 Office 365 雲端應用程式安全性 RESTful api （英文）。連接埠 443 上加密 HTTPS 通道上再傳送流量。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p104">A SIEM agent is set up in your organization's network. When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs. The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="18c1a-123">當 SIEM 代理程式會從 Office 365 雲端應用程式安全性擷取資料時，它會 Syslog 郵件傳送至本機 SIEM 伺服器使用 （TCP 或 UDP 以自訂連接埠） 在安裝期間所提供的網路組態。</span><span class="sxs-lookup"><span data-stu-id="18c1a-123">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![SIEM 與雲端應用程式安全性架構](media/siem-architecture.png)

## <a name="supported-siem-servers"></a><span data-ttu-id="18c1a-125">支援的 SIEM 伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1a-125">Supported SIEM servers</span></span>

<span data-ttu-id="18c1a-126">Office 365 雲端應用程式安全性目前支援下列 SIEM 伺服器：</span><span class="sxs-lookup"><span data-stu-id="18c1a-126">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="18c1a-127">微焦點討論 ArcSight</span><span class="sxs-lookup"><span data-stu-id="18c1a-127">Micro Focus ArcSight</span></span>
- <span data-ttu-id="18c1a-128">一般 CEF</span><span class="sxs-lookup"><span data-stu-id="18c1a-128">Generic CEF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18c1a-129">必要條件</span><span class="sxs-lookup"><span data-stu-id="18c1a-129">Prerequisites</span></span>

- <span data-ttu-id="18c1a-p105">您必須是全域管理員或安全性管理員可執行本文所述的工作。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="18c1a-p105">You must be a global administrator or security administrator to perform the tasks described in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="18c1a-132">您必須[啟用 Office 365 雲端應用程式安全性](turn-on-office-365-cas.md)您的組織。</span><span class="sxs-lookup"><span data-stu-id="18c1a-132">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="18c1a-133">必須開啟[稽核記錄](turn-audit-log-search-on-or-off.md)，for Office 365</span><span class="sxs-lookup"><span data-stu-id="18c1a-133">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="18c1a-134">您必須符合下列需求才能設定 SIEM 伺服器整合的標準伺服器：</span><span class="sxs-lookup"><span data-stu-id="18c1a-134">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="18c1a-135">作業系統： Windows 或 Linux （這可以是在虛擬機器）</span><span class="sxs-lookup"><span data-stu-id="18c1a-135">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="18c1a-136">CPU： 2</span><span class="sxs-lookup"><span data-stu-id="18c1a-136">CPU: 2</span></span>
    - <span data-ttu-id="18c1a-137">磁碟空間： 20 GB</span><span class="sxs-lookup"><span data-stu-id="18c1a-137">Disk space: 20 GB</span></span>
    - <span data-ttu-id="18c1a-138">RAM： 2 GB</span><span class="sxs-lookup"><span data-stu-id="18c1a-138">RAM: 2 GB</span></span>
    - <span data-ttu-id="18c1a-139">安裝[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)</span><span class="sxs-lookup"><span data-stu-id="18c1a-139">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="18c1a-140">設定[網路需求](https://docs.microsoft.com/cloud-app-security/network-requirements)所述的防火牆</span><span class="sxs-lookup"><span data-stu-id="18c1a-140">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="18c1a-p106">您必須具有**遠端 syslog 主機**及**Syslot 連接埠號碼**的詳細資料。網路管理員或安全性管理員應該能夠協助您找出該資訊。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p106">You must have details about your **Remote syslog host** and **Syslot port number**. A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="18c1a-143">您必須下載[JAR 檔案](https://go.microsoft.com/fwlink/?linkid=838596)需要整合 SIEM server 同意[軟體授權](https://go.microsoft.com/fwlink/?linkid=862491)條款。</span><span class="sxs-lookup"><span data-stu-id="18c1a-143">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="integrate-office-365-cloud-app-security"></a><span data-ttu-id="18c1a-144">整合 Office 365 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="18c1a-144">Integrate Office 365 Cloud App Security</span></span>
    
### <a name="step-1-set-it-up-in-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="18c1a-145">步驟 1： 設定它在 Office 365 雲端應用程式安全性入口網站</span><span class="sxs-lookup"><span data-stu-id="18c1a-145">Step 1: Set it up in the Office 365 Cloud App Security portal</span></span>

1. <span data-ttu-id="18c1a-p107">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="18c1a-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="18c1a-148">移至 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-148">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="18c1a-p108">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p108">Choose **Go to Office 365 Cloud App Security**. </span></span></br>
    <span data-ttu-id="18c1a-150">![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-150">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="18c1a-151">按一下 [**設定** \> **安全性延伸模組**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-151">Click **Settings** \> **Security extensions**.</span></span></br>
<span data-ttu-id="18c1a-152">![選擇 [設定] > 安全性延伸模組](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-152">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

5. <span data-ttu-id="18c1a-153">選擇 [**新增 SIEM 代理程式**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-153">Choose **Add SIEM agent**.</span></span></br><span data-ttu-id="18c1a-154">![選擇 [新增 SIEM 代理程式。](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-154">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
6. <span data-ttu-id="18c1a-155">選擇 [**啟動精靈**]。</span><span class="sxs-lookup"><span data-stu-id="18c1a-155">Choose **Start wizard**.</span></span></br><span data-ttu-id="18c1a-156">![取得說明或啟動精靈](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-156">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
7. <span data-ttu-id="18c1a-p109">在**一般**步驟中，指定的名稱，然後**選取 [SIEM 格式**並設定任何**進階設定**相關的格式。然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p109">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format. Then choose **Next**.</span></span></br><span data-ttu-id="18c1a-159">![指定的名稱與類型](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-159">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
8. <span data-ttu-id="18c1a-p110">在 [**遠端 Syslog** ] 步驟中指定的 IP 位址或**遠端 syslog 主機**及**Syslog 連接埠號碼**組成的主機名稱。選取 [TCP] 或 [UDP] 做為遠端 Syslog 通訊協定。（您可以使用您的網路管理員或安全性管理員以取得這些詳細資料若您尚未擁有工作）。然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p110">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol. (You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span></br><span data-ttu-id="18c1a-163">![指定遠端 Syslog 詳細資料](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-163">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
9. <span data-ttu-id="18c1a-164">在 [**資料類型**的步驟，執行下列其中一個動作] 和 [**下一步**：</span><span class="sxs-lookup"><span data-stu-id="18c1a-164">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="18c1a-165">保留預設設定的**所有提醒**</span><span class="sxs-lookup"><span data-stu-id="18c1a-165">Keep the default setting of **All Alerts**</span></span></br><span data-ttu-id="18c1a-166">或</span><span class="sxs-lookup"><span data-stu-id="18c1a-166">OR</span></span>
    - <span data-ttu-id="18c1a-p111">按一下 [**所有提醒**、，然後選擇 [**特定篩選器**。定義篩選器以選取您想要 SIEM 伺服器傳送的提醒的類型。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p111">Click **All alerts**, and then choose **Specific filters**. Define filters to select the kinds of alerts you want to send to your SIEM server. </span></span></br><span data-ttu-id="18c1a-169">![精靈] 的資料類型步驟](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-169">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
10. <span data-ttu-id="18c1a-170">在 [恭喜] 畫面上複製的權杖並將其儲存供日後。</span><span class="sxs-lookup"><span data-stu-id="18c1a-170">On the Congratulations screen, copy the token and save it for later.</span></span></br>![SIEM 代理程式建立畫面](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="18c1a-p112">此時，您已設定好 SIEM 代理程式在 Office 365 雲端應用程式安全性]，但尚未完成 SIEM server 的整合。繼續下一個步驟以繼續 SIEM server 的整合。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p112">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished. Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="18c1a-p113">按一下 [關閉] 並在安全性延伸模組] 畫面上保留精靈] 之後，您可以看到表格中所新增的 SIEM 代理程式。它要等到更新版本連線就會顯示狀態的**建立日期**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p113">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table. It will show a status of **Created** until it's connected later.</span></span>

![建立 SIEM 代理程式](media/SIEMAgentCreated.png)
    
### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a><span data-ttu-id="18c1a-177">步驟 2： 下載糖檔案並在您的伺服器上執行</span><span class="sxs-lookup"><span data-stu-id="18c1a-177">Step 2: Download the JAR file and run it on your server</span></span>

1. <span data-ttu-id="18c1a-p114">下載[Microsoft 雲端應用程式安全性 SIEM 代理程式](https://go.microsoft.com/fwlink/?linkid=838596)並解壓縮資料夾。（您必須同意這些[軟體授權合約](https://go.microsoft.com/fwlink/?linkid=862491)才能繼續執行。）</span><span class="sxs-lookup"><span data-stu-id="18c1a-p114">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder. (You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="18c1a-180">.Jar 檔案解壓縮 zip 資料夾並在您的伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="18c1a-180">Extract the .jar file from the zipped folder and run it on your server.</span></span>
    
3. <span data-ttu-id="18c1a-181">在執行後檔案，請在命令提示字元中執行下列： 命令：</span><span class="sxs-lookup"><span data-stu-id="18c1a-181">After running the file, run the following: command:</span></span></br>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
#### <a name="important-notes"></a><span data-ttu-id="18c1a-182">重要附註</span><span class="sxs-lookup"><span data-stu-id="18c1a-182">Important notes</span></span>

- <span data-ttu-id="18c1a-183">檔案名稱可能會有所不同根據 SIEM 代理程式的版本。</span><span class="sxs-lookup"><span data-stu-id="18c1a-183">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="18c1a-184">建議您的伺服器上執行糖填滿，server 安裝期間。</span><span class="sxs-lookup"><span data-stu-id="18c1a-184">We recommend that you run the JAR fill on your server during server setup.</span></span>
    - <span data-ttu-id="18c1a-185">**Windows**： 執行為排定的工作，同時務必使用設定至**不論使用者登入與否均執行**工作並清除 [**如果它是執行超過停止的任務**] 選項。</span><span class="sxs-lookup"><span data-stu-id="18c1a-185">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="18c1a-186">**Linux**： 將執行的命令以**&** 至`rc.local`檔案。</span><span class="sxs-lookup"><span data-stu-id="18c1a-186">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> </br><span data-ttu-id="18c1a-187">範例：</span><span class="sxs-lookup"><span data-stu-id="18c1a-187">Example:</span></span></br> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="18c1a-p115">在方括參數是選擇性的而且應用於唯有相關。使用下列變數：</span><span class="sxs-lookup"><span data-stu-id="18c1a-p115">Parameters in brackets [] are optional, and should be used only if relevant. Use the following variables:</span></span>
    - <span data-ttu-id="18c1a-190">**DIRNAME**是您想要用於本機代理程式偵錯記錄檔的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="18c1a-190">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>
    - <span data-ttu-id="18c1a-191">**位址 [: 連接埠]** 是 proxy 伺服器位址和連接埠的伺服器用來連線到網際網路。</span><span class="sxs-lookup"><span data-stu-id="18c1a-191">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>
    - <span data-ttu-id="18c1a-192">**TOKEN**是您在第一個程序中複製的 SIEM 代理程式權杖。</span><span class="sxs-lookup"><span data-stu-id="18c1a-192">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>
    - <span data-ttu-id="18c1a-193">若要取得說明，請輸入`-h`。</span><span class="sxs-lookup"><span data-stu-id="18c1a-193">To get help, type `-h`.</span></span> 
  
### <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="18c1a-194">步驟 3： 驗證 SIEM 代理程式正常運作</span><span class="sxs-lookup"><span data-stu-id="18c1a-194">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="18c1a-195">請務必在 Office 365 雲端應用程式安全性入口網站中的 SIEM 代理程式的狀態不會顯示為**連線錯誤**或**已中斷連線**及會有任何代理程式通知。</span><span class="sxs-lookup"><span data-stu-id="18c1a-195">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span></br><span data-ttu-id="18c1a-196">例如，我們可以看到 SIEM 伺服器所連接：</span><span class="sxs-lookup"><span data-stu-id="18c1a-196">For example, here we can see the SIEM server is connected:</span></span></br><span data-ttu-id="18c1a-197">![SIEM 伺服器連線](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-197">![SIEM server connected](media/siem-connected.png)</span></span></br><span data-ttu-id="18c1a-198">然後，我們可以看到 SIEM 伺服器中斷連線：</span><span class="sxs-lookup"><span data-stu-id="18c1a-198">And here, we can see the SIEM server is disconnected:</span></span></br><span data-ttu-id="18c1a-199">![未連接的 SIEM 伺服器](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="18c1a-199">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="18c1a-200">在您 Syslog/SIEM 的伺服器，請確定您會看到提醒已從 Office 365 雲端應用程式安全性抵達。</span><span class="sxs-lookup"><span data-stu-id="18c1a-200">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="regenerating-your-token"></a><span data-ttu-id="18c1a-201">重新產生您權杖</span><span class="sxs-lookup"><span data-stu-id="18c1a-201">Regenerating your token</span></span>

<span data-ttu-id="18c1a-p116">如果您遺失您權杖，您就可以永遠重新產生它。在表格中，找出 SIEM 代理程式的列。按一下省略符號、，然後選擇 [**重新產生的語彙基元**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p116">If you lose your token, you can always regenerate it. In the table, locate the row for the SIEM agent. Click the ellipses, and then choose **Regenerate token**.</span></span>

![重新產生的語彙基元 SIEM 代理程式按一下省略符號](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
## <a name="editing-your-siem-agent"></a><span data-ttu-id="18c1a-206">編輯 SIEM 代理程式</span><span class="sxs-lookup"><span data-stu-id="18c1a-206">Editing your SIEM agent</span></span>

<span data-ttu-id="18c1a-p117">若要編輯您 SIEM 代理程式在表格中，找到列 SIEM 代理程式。按一下省略符號、，然後選擇 [**編輯**。如果您編輯 SIEM 代理程式，您不需要重新執行.jar 檔 ；自動更新。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p117">To edit your SIEM agent, in the table, locate the row for the SIEM agent. Click the ellipses, and then choose **Edit**. If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.</span></span>

![若要編輯 SIEM 代理程式，並選擇 [省略符號，然後選擇 [編輯。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
## <a name="deleting-your-siem-agent"></a><span data-ttu-id="18c1a-211">刪除 SIEM 代理程式</span><span class="sxs-lookup"><span data-stu-id="18c1a-211">Deleting your SIEM agent</span></span>

<span data-ttu-id="18c1a-p118">若要刪除您 SIEM 代理程式在表格中，找到列 SIEM 代理程式。按一下省略符號、，然後選擇 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p118">To delete your SIEM agent, in the table, locate the row for the SIEM agent. Click the ellipses, and then choose **Delete**.</span></span>

![若要刪除的 SIEM 代理程式，並選擇 [省略符號，然後選擇 [刪除]。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

## <a name="sample-logfiles"></a><span data-ttu-id="18c1a-215">範例的記錄檔</span><span class="sxs-lookup"><span data-stu-id="18c1a-215">Sample logfiles</span></span>

<span data-ttu-id="18c1a-216">以下是可能 SIEM 伺服器傳送的提醒記錄檔範例：</span><span class="sxs-lookup"><span data-stu-id="18c1a-216">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="18c1a-217">而以下是範例 CEF 格式</span><span class="sxs-lookup"><span data-stu-id="18c1a-217">And here's a sample in CEF format</span></span>


|<span data-ttu-id="18c1a-218">CEF 欄位名稱</span><span class="sxs-lookup"><span data-stu-id="18c1a-218">CEF field name</span></span>  | <span data-ttu-id="18c1a-219">描述</span><span class="sxs-lookup"><span data-stu-id="18c1a-219">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="18c1a-220">啟動</span><span class="sxs-lookup"><span data-stu-id="18c1a-220">start</span></span>     | <span data-ttu-id="18c1a-221">提醒的時間戳記</span><span class="sxs-lookup"><span data-stu-id="18c1a-221">alert timestamp</span></span>        |
|<span data-ttu-id="18c1a-222">結束</span><span class="sxs-lookup"><span data-stu-id="18c1a-222">end</span></span>     | <span data-ttu-id="18c1a-223">提醒的時間戳記</span><span class="sxs-lookup"><span data-stu-id="18c1a-223">alert timestamp</span></span>        |
|<span data-ttu-id="18c1a-224">rt</span><span class="sxs-lookup"><span data-stu-id="18c1a-224">rt</span></span>     | <span data-ttu-id="18c1a-225">提醒的時間戳記</span><span class="sxs-lookup"><span data-stu-id="18c1a-225">alert timestamp</span></span>        |
|<span data-ttu-id="18c1a-226">msg</span><span class="sxs-lookup"><span data-stu-id="18c1a-226">msg</span></span>     | <span data-ttu-id="18c1a-227">在 Office 365 雲端應用程式安全性入口網站中所示警示描述</span><span class="sxs-lookup"><span data-stu-id="18c1a-227">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="18c1a-228">suser</span><span class="sxs-lookup"><span data-stu-id="18c1a-228">suser</span></span>     | <span data-ttu-id="18c1a-229">警示主體使用者</span><span class="sxs-lookup"><span data-stu-id="18c1a-229">alert subject user</span></span>        |
|<span data-ttu-id="18c1a-230">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="18c1a-230">destinationServiceName</span></span>     | <span data-ttu-id="18c1a-231">提醒源自應用程式，例如 Office 365、 SharePoint、 或 OneDrive</span><span class="sxs-lookup"><span data-stu-id="18c1a-231">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="18c1a-232">csLabel</span><span class="sxs-lookup"><span data-stu-id="18c1a-232">csLabel</span></span>     | <span data-ttu-id="18c1a-p119">而異 （標籤有不同的意義）。一般而言，標籤是自我闡明的例如 targetObjects。</span><span class="sxs-lookup"><span data-stu-id="18c1a-p119">Varies (labels have different meanings). Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="18c1a-235">cs</span><span class="sxs-lookup"><span data-stu-id="18c1a-235">cs</span></span>     | <span data-ttu-id="18c1a-236">對應的標籤 （例如如同標籤範例通知之目標使用者） 的資訊</span><span class="sxs-lookup"><span data-stu-id="18c1a-236">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |
  
## <a name="next-steps"></a><span data-ttu-id="18c1a-237">後續步驟</span><span class="sxs-lookup"><span data-stu-id="18c1a-237">Next steps</span></span>

- [<span data-ttu-id="18c1a-238">推出 Office 365 雲端 App 安全性後的使用活動</span><span class="sxs-lookup"><span data-stu-id="18c1a-238">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="18c1a-239">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="18c1a-239">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="18c1a-240">群組簡化管理 IP 位址</span><span class="sxs-lookup"><span data-stu-id="18c1a-240">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

