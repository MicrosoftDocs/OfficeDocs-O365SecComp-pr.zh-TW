---
title: 外寄和內送的郵件流程
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 系統管理員可以了解輸出和輸入的郵件流程] 小工具在 Office 365 安全性 & 合規性中心中的郵件流程儀表板中。
ms.openlocfilehash: 98806a699909056b4295911a031bb7b14233ede5
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454885"
---
# <a name="outbound-and-inbound-mail-flow"></a>外寄和內送的郵件流程

**輸出和輸入的郵件流程**] 小工具結合了來自**連接器報表**及離職**TLS 概觀報告**在同一個位置的資訊。

![輸出和輸入郵件流程中的報表在 Office 365 安全性 & 合規性中心中的郵件流程儀表板](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

[] 小工具中的資訊有關連接器和 Office 365 中的 TLS 郵件保護。 如需詳細資訊，請參閱下列主題：

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>受保護傳輸中 （TLS) 的郵件

**輸出和輸入的郵件流程**] 小工具會顯示 TLS 加密的郵件會傳遞到及傳送自 Office 365 組織時所使用的連線。 建立與其他電子郵件服務的連線加密的 TLS 時由兩邊所提供 TLS。 [] 小工具提供郵件流程中的最後一週的快照集。 當您按一下 [**檢視詳細資料**時，**郵件保護 （由 TLS) 的傳輸中**彈出式視窗會顯示您進入及離開貴組織的 TLS 保護。

![保護 Office 365 安全性 & 合規性中心中 （藉由 TLS) 加密彈出式視窗中的郵件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

目前，TLS 1.2 是最安全的 Office 365 所提供的 TLS 版本。 通常，您需要知道規範稽核正在使用 TLS 加密。 您可能沒有直接的關聯性與大部分的來源和目的地電子郵件伺服器 （不屬於您，以及 Microsoft 都不會），因此您不需要以改善這些伺服器會使用 TLS 加密的許多選項。

但是，您可以使用[連接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)來確保最佳使用 TLS 保護您的電子郵件伺服器和 Office 365 之間所傳送的郵件。 Office 365 和您自己的電子郵件伺服器或屬於協力廠商的伺服器之間的郵件流程會是較重要且機密比一般的郵件，因此您會想要將額外的安全性和警覺套用到這些郵件。 您可以升級或修正您自己的電子郵件伺服器，以改善正在使用中，或連絡您的夥伴進行相同的 TLS 加密。 **連接器報表**顯示郵件流程音量和使用 Office 365 連接器的郵件使用 TLS 加密。

## <a name="connector-report"></a>連接器報表

當您按一下**郵件保護 （由 TLS) 的傳輸中**的彈出式視窗**連接器報告**連結時，報表就會顯示郵件傳送到及傳送自使用連接器的 Office 365 組織的相關資訊。 您使用您自己的電子郵件伺服器和 Office 365 或您的合作夥伴伺服器與 Office 365 之間的連接器。 每個連接器的郵件音量和 TLS 加密的連線使用。 此外，您也可以檢視已傳送或接收 Office 365 中，而不需使用連接器的郵件資料。

[**郵件流程**] 檢視顯示過去一週的透過連接器的郵件數量。 您可以藉由選取**篩選**您可以在此提高為 30 天的最大值的範圍變更的日期範圍。 **所有郵件流程**檢視顯示所有的郵件流程到及傳送自所有連接器透過 Office 365 組織。 您可以選取特定連接器以在下拉式功能表中的名稱。

您可以從下分解為 TLS 保護透過連接器的郵件，請參閱下拉式清單選取**TLS 使用狀況**] 檢視。 為**TLS 概觀報告**」 報告，這個檢視顯示不同的 TLS 版本的百分比。 為 TLS 1.0 連線，您真的需要取得您的電子郵件伺服器或您的合作夥伴伺服器升級，或若要避免發生問題時 TLS 1.0 支援會最後已被取代的 Office 365 中修正。 如需詳細資訊，請參閱[關於 Office 365 中加密的技術參考細節](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)。

深入了解指向連接器，以協助您注意到連接器的潛在 TLS 加密問題。 深入了解是：**否 TLS 是超過 25%** 或**TLS 1.0 大於 50%**。 如果您看到這些見解，您需要調查之相關聯的連接器，或連絡您的夥伴組織的電子郵件伺服器。
