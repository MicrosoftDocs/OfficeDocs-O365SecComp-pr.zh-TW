---
title: 針對資訊障礙原則屬性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 用做參考的這篇文章，您可以使用資訊障礙原則中的各種屬性。
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668288"
---
# <a name="attributes-for-information-barrier-policies-preview"></a>資訊障礙原則 （預覽） 的屬性

Azure Active Directory 中的某些屬性可以用於將使用者分。 線段然後作為篩選資訊障礙原則。 例如，您可以使用**部門**部門所定義的使用者區段 （在同一時間假設兩個部門的任何單一員工 works） 組織內。 

本文提供可用的屬性的清單。 若要深入了解資訊障礙，請參閱下列資源：
- [資訊障礙 （預覽）](information-barriers.md)
- [在 Microsoft Teams （預覽） 中定義資訊障礙的原則](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何在資訊障礙原則中使用屬性

本文中所列的屬性可用來定義 （或編輯） 的使用者區段。 區段做為參數 (UserGroupFilter) 中的資訊障礙原則，如下列範例所示：

|範例  |指令程式  |
|---------|---------|
|定義稱為 Segment1 線段使用的部門屬性     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|定義線段，稱為 SegmentA （假設此屬性包含群組名稱，例如 「 BlueGroup 」），使用 MemberOf 屬性     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|定義線段，稱為 DayTraders 使用 ExtensionAttribute1 （假設此屬性包含工作標題，例如 「 DayTrader 」）|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

當您定義的區段時，使用您的所有區段相同的屬性。 例如，如果您定義使用*部門*一些區段，定義所有使用*部門*的線段。 未定義使用*部門*和其他人使用*MemberOf*一些區段。 請確定您的區段不會重疊;每位使用者應該指派給一個區段。 

若要深入了解，請參閱[使用 PowerShell 的定義區段](information-barriers-policies.md#define-segments-using-powershell)。

## <a name="reference"></a>參考

下表列出您可以使用資訊障礙的屬性。

|Azure Active Directory 屬性名稱 （LDAP 顯示名稱）  |Exchange 屬性名稱  |
|---------|---------|
|共同撰寫       | 共同撰寫        |
|Company     |Company         |
|部門     |部門         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |別名 |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|郵件   |WindowsEmailAddress    |
|描述    |描述    |
|MemberOf   |MemberOfGroup  |

## <a name="related-topics"></a>相關主題

[在 Microsoft Teams （預覽） 中定義資訊障礙的原則](information-barriers-policies.md)

[疑難排解資訊障礙 （預覽）](information-barriers-troubleshooting.md)

[資訊障礙 （預覽）](information-barriers.md)



