---
title: '호환성이 손상되는 변경: 일부 라틴어-1 문자의 유니코드 범주가 변경됨'
description: Char 메서드가 라틴어-1 범위의 문자에 대해 올바른 유니코드 범주를 반환하는 .NET 5.0의 세계화 관련 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 04/07/2020
ms.openlocfilehash: 8bd093a89857c83921fc0bf987348b529f74ce68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760050"
---
# <a name="unicode-category-changed-for-some-latin-1-characters"></a>일부 라틴어-1 문자의 유니코드 범주가 변경됨

<xref:System.Char> 메서드는 이제 라틴어-1 범위의 문자에 대해 올바른 유니코드 범주를 반환합니다. 범주는 유니코드 표준의 범주와 일치합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 <xref:System.Char> 메서드는 라틴어-1 범위의 문자에 대해 유니코드 범주의 고정 목록을 사용했습니다. 그러나 유니코드 표준은 해당 API가 구현된 이후 이러한 문자 중 일부의 범주를 변경했으며 이에 따른 불일치가 발생합니다. 또한 <xref:System.Char> API와 <xref:System.Globalization.CharUnicodeInfo> API 간에 불일치가 있었으며, 이는 유니코드 표준을 따릅니다. .NET 5.0 이상 버전에서 <xref:System.Char> 메서드는 모든 문자에 대한 유니코드 표준과 일치하는 유니코드 범주를 사용하고 반환합니다.

다음 표에서는 .NET 5.0에서 유니코드 범주가 변경된 문자를 보여 줍니다.

| 문자    | 유니코드 범주<br>이전 .NET 버전 | 유니코드 범주<br>.NET 5.0 이상 버전 |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| §(\u00a7)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| ª(\u00aa)   | `LowercaseLetter`                             | `OtherLetter`                                      |
| SHY(\u00ad) | `DashPunctuation`                             | `Format`                                           |
| ¶(\u00b6)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| º(\u00ba)   | `LowercaseLetter`                             | `OtherLetter`                                      |

## <a name="version-introduced"></a>도입된 버전

.NET 5.0

## <a name="recommended-action"></a>권장 조치

<xref:System.Char> 클래스를 사용하여 유니코드 문자 범주를 가져오는 코드가 있으며 범주가 변경되지 않는다고 가정하는 경우 범주를 업데이트해야 할 수도 있습니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.Char> 형식에서 반환된 범주가 유니코드 표준과 <xref:System.Globalization.CharUnicodeInfo> 형식 둘 다와 일치하도록 이렇게 변경했습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

또한 유니코드 문자 범주를 얻기 위해 <xref:System.Char>에 의존하는 클래스(예: <xref:System.Text.RegularExpressions.Regex>)는 이 변경의 영향을 받습니다.

<!--

### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

### Category

- Core .NET libraries
- Globalization
-
-->
