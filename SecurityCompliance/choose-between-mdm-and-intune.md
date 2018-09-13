---
title: 選擇 office 365 MDM 或 Microsoft Intune
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c93d9ab9-efb2-4349-9b93-30c30562ee22
description: Microsoft Intune 與 Office 365 的內建行動裝置管理可讓您管理組織中的行動裝置。但此主題中所述的主要差異。
ms.openlocfilehash: 339399e2e518c22fa9f0f7482fc527990f1a8541
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526218"
---
# <a name="choose-between-mdm-for-office-365-and-microsoft-intune"></a><span data-ttu-id="7cda3-104">選擇 office 365 MDM 或 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7cda3-104">Choose between MDM for Office 365 and Microsoft Intune</span></span>

<span data-ttu-id="7cda3-p102">Microsoft Intune 與 Office 365 的內建行動裝置管理可讓您管理組織中的行動裝置。但有主要差異，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7cda3-p102">Microsoft Intune and built-in Mobile Device Management for Office 365 both give you the ability to manage mobile devices in your organization. But there are key differences, described in the following table.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cda3-p103">您可以管理使用者與在相同的 Office 365 租用戶中使用 Intune 與 Office 365 與其行動裝置。設定 Intune 及 MDM 可讓您決定哪一個解決方案是最適合的特定使用者和其裝置。如果您有兩個可用的選項，您可以選擇是否針對 Office 365 或更豐富的功能 Intune 解決方案管理 MDM 使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="7cda3-p103">You can manage users and their mobile devices using both Intune and Office 365 in the same Office 365 tenant. Setting up both Intune and MDM lets you decide which solution is best for specific users and their devices. If you have both options available, you can choose whether you manage a user's devices with MDM for Office 365 or the more feature-rich Intune solution.</span></span> 
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="7cda3-110">**功能區**</span><span class="sxs-lookup"><span data-stu-id="7cda3-110">**Feature area**</span></span> <br/> |<span data-ttu-id="7cda3-111">**MDM for Office 365**</span><span class="sxs-lookup"><span data-stu-id="7cda3-111">**MDM for Office 365**</span></span> <br/> |<span data-ttu-id="7cda3-112">**Microsoft Intune**</span><span class="sxs-lookup"><span data-stu-id="7cda3-112">**Microsoft Intune**</span></span> <br/> |
|<span data-ttu-id="7cda3-113">成本</span><span class="sxs-lookup"><span data-stu-id="7cda3-113">Cost</span></span>  <br/> |<span data-ttu-id="7cda3-114">包含許多 Office 365 商業訂閱。</span><span class="sxs-lookup"><span data-stu-id="7cda3-114">Included with many Office 365 commercial subscriptions.</span></span>  <br/> |<span data-ttu-id="7cda3-115">需要 Microsoft Intune 付費的訂閱或可購買與企業行動性套件。</span><span class="sxs-lookup"><span data-stu-id="7cda3-115">Requires a paid subscription for Microsoft Intune or can be purchased with Enterprise Mobility Suite.</span></span>  <br/> |
|<span data-ttu-id="7cda3-116">管理裝置的方式</span><span class="sxs-lookup"><span data-stu-id="7cda3-116">How you manage devices</span></span>  <br/> |<span data-ttu-id="7cda3-117">管理裝置使用[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)Office 365。</span><span class="sxs-lookup"><span data-stu-id="7cda3-117">Manage devices using the [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) Office 365.</span></span>  <br/> |<span data-ttu-id="7cda3-118">如果您使用 Intune 本身，管理裝置使用 Intune 系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="7cda3-118">If you use Intune by itself, you manage devices using the Intune admin console.</span></span>  <br/> <span data-ttu-id="7cda3-119">如果您使用 System Center 2012 Configuration Manager 整合 Intune，您會使用 Configuration Manager console 來管理裝置內部部署與雲端中。</span><span class="sxs-lookup"><span data-stu-id="7cda3-119">If you integrate Intune with System Center 2012 Configuration Manager, you use the Configuration Manager console to manage devices on-premises and in the cloud.</span></span>  <br/> |
|<span data-ttu-id="7cda3-120">您可以管理的裝置</span><span class="sxs-lookup"><span data-stu-id="7cda3-120">Devices you can manage</span></span>  <br/> |<span data-ttu-id="7cda3-121">IOS、 Android、 及 Windows 雲端式管理裝置</span><span class="sxs-lookup"><span data-stu-id="7cda3-121">Cloud-based management for iOS, Android, and Windows devices</span></span>  <br/> |<span data-ttu-id="7cda3-122">雲端管理的 iOS、 Mac OS X、 Android、 Windows 8.1 （電話和 PC） 及稍後要包含 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="7cda3-122">Cloud-based management for iOS, Mac OS X, Android, Windows 8.1 (Phone and PC) and later to include Windows 10.</span></span> <br/> |
|<span data-ttu-id="7cda3-123">主要功能</span><span class="sxs-lookup"><span data-stu-id="7cda3-123">Key capabilities</span></span>  <br/> |<span data-ttu-id="7cda3-124">協助確保可以存取 Office 365 公司電子郵件和文件只有在電話或平板電腦的管理您的公司以及 IT 原則符合上。</span><span class="sxs-lookup"><span data-stu-id="7cda3-124">Help ensure that Office 365 corporate email and documents can be accessed only on phones and tablets that are managed by your company and that are compliant with your IT policies.</span></span>  <br/> <span data-ttu-id="7cda3-125">設定和管理安全性原則層級的 pin 鎖定及 jailbreak 偵測裝置，以協助防止未經授權的使用者存取公司的電子郵件和裝置上的資料遺失或竊時類似。</span><span class="sxs-lookup"><span data-stu-id="7cda3-125">Set and manage security policies, like device level pin lock and jailbreak detection, to help prevent unauthorized users from accessing corporate email and data on a device when it is lost or stolen.</span></span>  <br/> <span data-ttu-id="7cda3-126">移除員工的裝置的 Office 365 公司資料時備妥離開其個人的資料。</span><span class="sxs-lookup"><span data-stu-id="7cda3-126">Remove Office 365 company data from an employee's device while leaving their personal data in place.</span></span>  <br/> <span data-ttu-id="7cda3-127">[Office 365 的內建行動裝置管理功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)中所包含的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7cda3-127">Details are included in [capabilities of Built-in Mobile Device Management for Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0).</span></span>  <br/> |<span data-ttu-id="7cda3-128">Office 365 功能的 MDM 加上：</span><span class="sxs-lookup"><span data-stu-id="7cda3-128">MDM for Office 365 capabilities, plus:</span></span>  <br/> <span data-ttu-id="7cda3-129">協助使用者在安全地存取公司資源與憑證、 Wi-fi、 VPN 和電子郵件設定檔。</span><span class="sxs-lookup"><span data-stu-id="7cda3-129">Help users securely access corporate resource with certificates, Wi-Fi, VPN, and email profiles.</span></span>  <br/> <span data-ttu-id="7cda3-130">註冊並管理的公司擁有的裝置，簡化原則和應用程式部署的集合。</span><span class="sxs-lookup"><span data-stu-id="7cda3-130">Enroll and manage collections of corporate-owned devices, simplifying policy and app deployment.</span></span>  <br/> <span data-ttu-id="7cda3-131">對使用者部署您的內部企業營運系統應用程式和存放區中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cda3-131">Deploy your internal line-of-business apps and apps in stores to users.</span></span>  <br/> <span data-ttu-id="7cda3-132">讓使用者更安全地存取公司資訊使用 Office 行動裝置及線條的商務應用程式其了解，同時限制協助確保資料的安全性動作想要複製、 剪下、 貼上另存為，由 Intune 管理這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cda3-132">Enable your users to more securely access corporate information using the Office mobile and line-of business apps they know, while ensuring security of data by helping to restrict actions like copy, cut, paste, and save as, to only those apps managed by Intune.</span></span>  <br/> <span data-ttu-id="7cda3-133">可讓更安全 web 瀏覽使用 Intune 受管理的瀏覽器應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cda3-133">Enable more secure web browsing using the Intune Managed Browser app.</span></span>  <br/> <span data-ttu-id="7cda3-134">從雲端管理的 Pc 與任何基礎結構所需使用 Intune，或連線 Intune 至 Configuration Manager 來管理您的裝置包括 Pc、 Mac、 Linux 以及 UNIX 的所有伺服器及單一管理主控台從行動裝置。</span><span class="sxs-lookup"><span data-stu-id="7cda3-134">Manage PCs from the cloud with no infrastructure required using Intune, or connect Intune to Configuration Manager to manage all of your devices including PCs, Macs, Linux and UNIX servers, and mobile devices from a single management console.</span></span>  <br/> <span data-ttu-id="7cda3-p104">Intune 訂閱也可讓您設定 MAM （行動裝置應用程式管理） 原則使用 Azure 入口網站中，即使人的裝置不會註冊 Intune。請參閱 ＜ [Protect 應用程式資料 MAM 原則 （英文）](https://go.microsoft.com/fwlink/?LinkId=825439)。</span><span class="sxs-lookup"><span data-stu-id="7cda3-p104">An Intune subscription also allows you to set up MAM (mobile app management) policies by using the Azure portal, even if people's devices aren't enrolled in Intune. See [Protect app data using MAM policies](https://go.microsoft.com/fwlink/?LinkId=825439).  </span></span><br/> |


## <a name="related-topics"></a><span data-ttu-id="7cda3-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="7cda3-137">Related topics</span></span>
   
<span data-ttu-id="7cda3-138">深入了解 Microsoft Intune 影片訓練課程[Microsoft 雲端服務： 管理 Office 365 和 Intune](https://support.office.com/article/c1224e20-3d49-4f40-99ee-fd0991880376.aspx)、 LinkedIn 學習由致力提供給您。</span><span class="sxs-lookup"><span data-stu-id="7cda3-138">Learn more about Microsoft Intune with the video training course [Microsoft Cloud Services: Administer Office 365 and Intune](https://support.office.com/article/c1224e20-3d49-4f40-99ee-fd0991880376.aspx), brought to you by LinkedIn Learning.</span></span>
  
