---
title: '호환성이 손상되는 변경: Cryptography.Oid는 기능상 초기화 전용임'
description: 값을 변경하려고 하면 Cryptography.Oid의 속성 setter가 예외를 throw하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 08/16/2020
ms.openlocfilehash: a3b5a393e2a84f7c9a60c2a821ecfda9c6acd2e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759648"
---
# <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>System.Security.Cryptography.Oid는 기능상 초기화 전용임

ASN.1 개체 식별자 값과 “식별” 이름을 나타내는 데 사용되는 <xref:System.Security.Cryptography.Oid?displayProperty=fullName> 클래스가 이전에는 완전히 변경 가능했습니다. 이 가변성은 간과되거나 예상치 못한 것으로 인식되는 경우가 많았습니다. 이미 할당된 값을 변경하려고 하면 속성 setter가 이제 <xref:System.PlatformNotSupportedException>을 throw합니다.

## <a name="change-description"></a>변경 내용 설명

이전 버전에서는 <xref:System.Security.Cryptography.Oid>의 속성 setter를 사용하여 <xref:System.Security.Cryptography.Oid.FriendlyName> 및 <xref:System.Security.Cryptography.Oid.Value> 속성의 값을 변경할 수 있습니다.

.NET 5.0 이상 버전에서는 속성 setter에서 값을 초기화하는 것만 가능합니다. 속성 setter에 대한 이전 호출이나 생성자를 통해 속성 값이 있는 경우에는 속성 setter에서 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.

## <a name="reason-for-change"></a>변경 이유

이렇게 변경하면 퍼블릭 API에서 반환 값의 일부로 <xref:System.Security.Cryptography.Oid> 개체를 재사용하여 개체 할당 프로필을 줄일 수 있습니다. <xref:System.Security.Cryptography.Oid> 값을 입력으로 사용할 때 “방어적인” 임시 복사본을 만들지 않아도 됩니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

개체 초기화 이외의 다른 용도로 <xref:System.Security.Cryptography.Oid> 속성 setter를 사용하지 않습니다. 새 값을 나타내려면 기존 개체의 값을 변경하는 대신 새 인스턴스를 사용합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

### Category

Cryptography

-->
