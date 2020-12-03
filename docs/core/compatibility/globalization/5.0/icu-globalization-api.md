---
title: '호환성이 손상되는 변경: Windows에서 세계화 API가 ICU 라이브러리를 사용'
description: NLS 대신 ICU 라이브러리가 세계화 기능에 사용되는 .NET 5.0의 세계화 관련 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 05/19/2020
ms.openlocfilehash: efc20e21969ea4a83c9122e40b262e1dc38e6770
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760055"
---
# <a name="globalization-apis-use-icu-libraries-on-windows"></a>Windows에서 세계화 API가 ICU 라이브러리를 사용

.NET 5.0 이상 버전에서는 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 세계화 기능에 [ICU(International Components for Unicode)](http://site.icu-project.org/home) 라이브러리를 사용합니다.

## <a name="change-description"></a>변경 내용 설명

.NET Core 1.0~3.1 및 .NET Framework 4 이상에서 .NET 라이브러리는 Windows의 세계화 기능에 [국가별 언어 지원(NLS)](/windows/win32/intl/national-language-support) API를 사용합니다. 예를 들어 NLS 함수는 문자열 비교, 문화권 정보 가져오기, 해당 문화권에서 문자열 대/소문자 구분 수행에 사용되었습니다.

.NET 5.0부터 앱이 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 .NET 라이브러리는 기본적으로 [ICU](http://site.icu-project.org/home) 세계화 API를 사용합니다.

> [!NOTE]
> Windows 10 2019년 5월 업데이트 이상 버전에는 ICU 네이티브 라이브러리가 함께 제공됩니다. .NET 런타임에서 ICU를 로드할 수 없는 경우 대신 NLS를 사용합니다.

## <a name="behavioral-differences"></a>동작의 차이

세계화 기능을 사용 중임을 인식하지 못하는 경우에도 앱에 변경 내용이 표시될 수 있습니다. 이 섹션에는 표시될 수 있는 몇 가지 동작 변경이 나와 있지만 다른 내용도 있습니다.

### <a name="stringindexof"></a>String.IndexOf

<xref:System.String.IndexOf(System.String)?displayProperty=nameWithType>을 호출하여 문자열에서 줄 바꿈 문자의 인덱스를 찾는 다음 코드를 사용하는 것이 좋습니다.

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- Windows의 .NET 이전 버전에서는 코드 조각이 `6`을 인쇄합니다.
- Windows 19H1 이상 버전의 .NET 5.0 이상 버전에서는 코드 조각이 `-1`을 인쇄합니다.

문화권을 구분하는 검색 대신 서수 검색을 수행하여 이 코드를 수정하려면 <xref:System.String.IndexOf(System.String,System.StringComparison)> 오버로드를 호출하고 <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>을 인수로 전달합니다.

코드 분석 규칙 [CA1307: 명확성을 위해 StringComparison 지정](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) 및 [CA1309: 서수 StringComparison 사용](../../../../fundamentals/code-analysis/quality-rules/ca1309.md)을 실행하여 코드에서 이러한 호출 사이트를 찾을 수 있습니다.

자세한 내용은 [.NET 5+에서 문자열 비교 시 동작 변경](../../../../standard/base-types/string-comparison-net-5-plus.md)을 참조하세요.

### <a name="currency-symbol"></a>통화 기호

통화 형식 지정자 `C`를 사용하여 문자열의 형식을 지정하는 다음 코드를 사용하는 것이 좋습니다. 현재 스레드의 문화권은 국가가 아니라 언어만 포함하는 문화권으로 설정되어 있습니다.

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- Windows의 .NET 이전 버전에서 텍스트의 값은 `"100,00 €"`입니다.
- Windows 19H1 이상 버전의 .NET 5.0 이상 버전에서 텍스트의 값은 유로 대신 국제 통화 기호를 사용하는 `"100,00 ¤"`입니다. ICU의 의도는 통화가 언어가 아닌 국가 또는 지역의 속성이라는 것입니다.

## <a name="reason-for-change"></a>변경 이유

이 변경은 지원되는 모든 운영 체제에서 .NET의 세계화 동작을 통일하기 위해 도입되었습니다. 또한 애플리케이션이 운영 체제의 기본 제공 라이브러리에 의존하지 않고 자체 세계화 라이브러리를 묶을 수 있는 기능도 제공합니다.

## <a name="version-introduced"></a>도입된 버전

.NET 5.0

## <a name="recommended-action"></a>권장 조치

개발자는 아무 작업도 수행하지 않아도 됩니다. 하지만 NLS 세계화 API를 계속 사용하려는 경우 [런타임 스위치](../../../run-time-config/globalization.md#nls)를 설정하여 해당 동작으로 되돌릴 수 있습니다. 사용 가능한 스위치에 대한 자세한 내용은 [.NET 세계화 및 ICU](../../../../standard/globalization-localization/globalization-icu.md) 문서를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <xref:System.Globalization?displayProperty=fullName> 네임스페이스의 대부분의 형식
- <xref:System.Array.Sort%2A?displayProperty=fullName>(문자열 배열을 정렬하는 경우)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName>(목록 요소가 문자열인 경우)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>(키가 문자열인 경우)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>(키가 문자열인 경우)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>(집합에 문자열이 포함된 경우)

<!--

### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

### Category

- Core .NET libraries
- Globalization

-->
