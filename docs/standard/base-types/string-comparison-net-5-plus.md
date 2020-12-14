---
title: .NET 5+에서 문자열 비교 시 동작 변경
description: Windows에서 .NET 5 이상 버전의 문자열 비교 동작 변경에 대해 알아봅니다.
ms.date: 12/07/2020
ms.openlocfilehash: a53c36b31785fb43c0aa5f5040042abb6d40031a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851753"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a>.NET 5+에서 문자열 비교 시 동작 변경

.NET 5.0에, 세계화 API가 [이제 기본적으로 ICU를 사용](../../core/compatibility/globalization/5.0/icu-globalization-api.md)하는 런타임 동작 변경이 도입되었습니다. 이것은 Windows에서 실행할 때 운영 체제의 NLS(국가별 언어 지원) 기능을 활용하는 이전 .NET Core 및 .NET Framework과 달라진 점입니다. 이와 같이 동작 변경을 되돌릴 수 있는 호환성 스위치를 비롯한 변경에 대한 자세한 내용은 [.NET 세계화 및 ICU](../globalization-localization/globalization-icu.md)를 참조하세요.

## <a name="reason-for-change"></a>변경 이유

이 변경은 지원되는 모든 운영 체제에서 .NET의 세계화 동작을 통일하기 위해 도입되었습니다. 또한 애플리케이션이 OS의 기본 제공 라이브러리에 의존하지 않고 자체 세계화 라이브러리를 묶을 수 있는 기능도 제공합니다. 자세한 내용은 [호환성이 손상되는 변경 알림](../../core/compatibility/globalization/5.0/icu-globalization-api.md)을 참조하세요.

## <a name="behavioral-differences"></a>동작의 차이

<xref:System.StringComparison> 인수를 사용하는 오버로드를 호출하지 않고 `string.IndexOf(string)`와 같은 함수를 사용하는 경우 서수 검색을 수행하려 할 때 뜻하지 않게 문화권별 동작에 대한 종속성을 대신 사용하게 될 수 있습니다. NLS와 ICU는 언어 비교자에서 구현하는 논리가 다르므로 `string.IndexOf(string)`와 같은 메서드의 결과가 예기치 않은 값을 반환할 수 있습니다.

이는 세계화 기능이 항상 활성 상태일 것으로 예상하지 않는 곳에서도 나타날 수 있습니다. 예를 들어 다음 코드는 현재 런타임에 따라 다른 답을 생성할 수 있습니다.

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a>예기치 않은 동작 방지

이 섹션에서는 .NET 5.0의 예기치 않은 동작 변경을 처리하는 두 가지 옵션을 제공합니다.

### <a name="enable-code-analyzers"></a>코드 분석기 사용

[코드 분석기](../../fundamentals/code-analysis/overview.md)는 버그가 있을 수 있는 호출 사이트를 검색할 수 있습니다. 의외의 동작을 방지하려면 프로젝트에서 .NET 컴파일러 플랫폼(Roslyn) 분석기를 사용하는 것이 좋습니다. 분석기는 서수 비교자를 사용하려 할 때 뜻하지 않게 언어 비교자를 사용할 수 있는 코드에 플래그를 지정하는 데 도움이 됩니다. 다음 규칙은 이러한 문제에 플래그를 지정하는 데 도움이 됩니다.

- [CA1307: 명확성을 위해 StringComparison 지정](../../fundamentals/code-analysis/quality-rules/ca1307.md)
- [CA1309: 서수 StringComparison을 사용하세요.](../../fundamentals/code-analysis/quality-rules/ca1309.md)
- [CA1310: 정확성을 위해 StringComparison 지정](../../fundamentals/code-analysis/quality-rules/ca1310.md)

이러한 특정 규칙은 기본적으로 사용되지 않습니다. 해당 규칙을 사용하도록 설정하고 위반을 빌드 오류로 표시하려면 프로젝트 파일에 다음 속성을 설정합니다.

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
  <WarningsAsErrors>$(WarningsAsErrors);CA1307;CA1309;CA1310</WarningsAsErrors>
</PropertyGroup>
```

다음 코드 조각은 관련 코드 분석기 경고 또는 오류를 생성하는 코드 예제를 보여 줍니다.

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1310 for string; CA1307 matches on char ','
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

마찬가지로 정렬된 문자열 컬렉션을 인스턴스화하거나 기존 문자열 기반 컬렉션을 정렬하는 경우 명시적 비교자를 지정합니다.

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

### <a name="revert-back-to-nls-behaviors"></a>NLS 동작으로 되돌리기

Windows에서 실행할 때 .NET 5 애플리케이션을 이전 NLS 동작으로 되돌리려면 [.NET 세계화 및 ICU](../globalization-localization/globalization-icu.md)의 단계를 수행합니다. 이 애플리케이션 전체 호환성 스위치는 애플리케이션 수준에서 설정해야 합니다. 개별 라이브러리는 이 동작을 옵트인하거나 옵트아웃할 수 없습니다.

> [!TIP]
> 코드 상태를 개선하고 숨어 있는 기존 버그를 발견하려면 [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) 및 [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) 코드 분석 규칙을 사용하는 것이 좋습니다. 자세한 내용은 [코드 분석기 사용](#enable-code-analyzers)을 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

대부분의 .NET 애플리케이션에서는 .NET 5.0의 변경으로 인한 예기치 않은 동작이 발생하지 않습니다. 그러나 영향을 받는 API 수가 많고 이러한 API는 .NET 에코시스템의 기본 요소이기 때문에, .NET 5.0에서 원치 않는 동작이 도입되거나 애플리케이션에 이미 존재하던 숨어 있는 버그가 드러날 가능성에 유의해야 합니다.

영향을 받는 API는 다음과 같습니다.

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <xref:System.Globalization.TextInfo?displayProperty=fullName>(대부분의 멤버)
- <xref:System.Globalization.CompareInfo?displayProperty=fullName>(대부분의 멤버)
- <xref:System.Array.Sort%2A?displayProperty=fullName>(문자열 배열을 정렬하는 경우)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName>(목록 요소가 문자열인 경우)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>(키가 문자열인 경우)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>(키가 문자열인 경우)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>(집합에 문자열이 포함된 경우)

> [!NOTE]
> 이 목록은 영향을 받는 API의 전체 목록이 아닙니다.

위의 모든 API는 기본적으로 스레드의 [현재 문화권](xref:System.Threading.Thread.CurrentCulture)을 사용하여 언어 문자열 검색 및 비교를 수행합니다. 언어 검색 및 비교와 서수 검색 및 비교의 차이점은 [서수 검색 및 비교 대 언어 검색 및 비교](#ordinal-vs-linguistic-search-and-comparison)에 설명되어 있습니다.

ICU가 구현하는 언어 문자열 비교는 NLS와 다르기 때문에, 이전 버전의 .NET Core나 .NET Framework에서 .NET 5.0으로 업그레이드하고 영향을 받는 API 중 하나를 호출하는 Windows 기반 애플리케이션은 API가 다른 동작을 보이기 시작하는 것을 알 수 있습니다.

### <a name="exceptions"></a>예외

* API가 명시적인 `StringComparison` 또는 `CultureInfo` 매개 변수를 허용하는 경우 이 매개 변수는 API의 기본 동작을 재정의합니다.
* `CurrentCulture[IgnoreCase]` 또는 `InvariantCulture[IgnoreCase]`를 지정하는 명시적 `StringComparison` 인수를 호출자가 전달하지 않으면 첫 번째 매개 변수가 `char` 형식(예를 들어 <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>)인 `System.String` 멤버는 서수 검색을 사용합니다.

각 <xref:System.String> API의 기본 동작에 대한 자세한 분석은 [기본 검색 및 비교 형식](#default-search-and-comparison-types) 섹션을 참조하세요.

## <a name="ordinal-vs-linguistic-search-and-comparison"></a>서수 검색 및 비교 대 언어 검색 및 비교

서수(비언어라고도 함) 검색 및 비교는 문자열을 개별 `char` 요소로 분해하여 문자 대응 검색 또는 비교를 수행합니다. 예를 들어 `"dog"` 문자열과 `"dog"` 문자열은 `Ordinal` 비교자에서 같음으로 비교됩니다. 두 문자열이 정확히 동일한 문자 순서로 구성되어 있기 때문입니다. 하지만 `"dog"`와 `"Dog"`는 `Ordinal` 비교자에서 같지 않음으로 비교되는데, 정확히 동일한 문자 순서로 구성되지 않았기 때문입니다. 즉, 대문자 `'D'`의 코드 포인트 `U+0044`가 소문자 `'d'`의 코드 포인트 `U+0064` 전에 나오므로 `"Dog"` 전에 `"dog"`이 정렬됩니다.

`OrdinalIgnoreCase` 비교자는 계속 문자 대응 방식으로 작동하지만 작업을 수행하는 동안 대/소문자 차이를 제거합니다. `OrdinalIgnoreCase` 비교자에서는 문자 쌍 `'d'`와 `'D'`는 문자 쌍 `'á'`와 `'Á'`처럼 같음으로 비교됩니다. 하지만 악센트가 없는 문자 `'a'`는 악센트가 있는 문자 `'á'`와 같지 않음으로 비교됩니다.

다음 표에는 몇 가지 예가 나와 있습니다.

| String 1 | String 2 | `Ordinal` 비교 | `OrdinalIgnoreCase` 비교 |
|---|---|---|---|
| `"dog"` | `"dog"` | equal | equal |
| `"dog"` | `"Dog"` | 같지 않음 | equal |
| `"resume"` | `"Resume"` | 같지 않음 | equal |
| `"resume"` | `"résumé"` | 같지 않음 | 같지 않음 |

유니코드에서도 문자열은 여러 가지 메모리 내 표현을 가질 수 있습니다. 예를 들어 e 양음 부호(é)는 다음과 같은 두 가지 방법으로 표현할 수 있습니다.

* 단일 리터럴 `'é'` 문자(`'\u00E9'`로도 씀).
* 결합 악센트 한정자 문자 `'\u0301'`이 뒤에 오는 악센트 없는 리터럴 `'e'` 문자.

즉, 다음 네 개의 문자열은 구성 요소가 서로 다르더라도 모두 `"résumé"`로 표시됩니다. 이 문자열들은 리터럴 `'é'` 문자 또는 악센트가 없는 리터럴 `'e'` 문자와 결합 악센트 한정자 `'\u0301'`의 조합을 사용합니다.

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

서수 비교자에서는 이러한 문자열 중 어느 것도 서로 같음으로 비교되지 않습니다. 그 이유는 화면에 렌더링될 때 모두 똑같이 보이더라도 서로 다른 기본 문자 시퀀스를 포함하고 있기 때문입니다.

`string.IndexOf(..., StringComparison.Ordinal)` 작업을 수행할 때 런타임은 정확한 부분 문자열 일치 항목을 찾습니다. 결과는 다음과 같습니다.

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

서수 검색 및 비교 루틴은 현재 스레드의 문화권 설정에 영향을 받지 않습니다.

언어 검색 및 비교 루틴은 문자열을 데이터 정렬 요소로 분해하고 이러한 요소에 대해 검색 또는 비교를 수행합니다. 문자열의 문자와 해당 구성 요소 데이터 정렬 요소 사이에 1:1 매핑이 반드시 필요하지는 않습니다. 예를 들어 길이가 2인 문자열은 단일 데이터 정렬 요소로만 구성될 수 있습니다. 두 문자열이 언어적으로 인식되는 방식으로 비교되는 경우, 비교자는 문자열의 리터럴 문자가 서로 다른 경우에도 두 문자열의 데이터 정렬 요소에 동일한 의미상 의미가 있는지 여부를 확인합니다.

문자열 `"résumé"`와 네 가지 다른 표현을 다시 생각해 보세요. 다음 표는 각 표현을 데이터 정렬 요소로 분할하여 보여 줍니다.

| String | 데이터 정렬 요소 |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

데이터 정렬 요소는 판독기가 단일 문자 또는 문자 클러스터로 인식하는 항목과 대체로 일치합니다. 개념적으로는 [문자소 클러스터](character-encoding-introduction.md#grapheme-clusters)와 유사하지만 포함하는 범위가 약간 더 큽니다.

언어 비교자에서는 정확한 일치가 필요하지 않습니다. 대신 데이터 정렬 요소가 해당 의미상 의미에 따라 비교됩니다. 예를 들어 언어 비교자는 `"\u00E9"` 부분 문자열과 `"e\u0301"` 부분 문자열을 같음으로 처리하는데, 둘 다 의미상 “양음 부호 악센트 한정자가 있는 소문자 e”를 뜻하기 때문입니다. 이를 통해 `IndexOf` 메서드는 다음 코드 샘플에 나온 것처럼 의미상 동등한 부분 문자열 `"\u00E9"`가 포함된 더 큰 문자열 내에서 `"e\u0301"` 부분 문자열을 일치시킬 수 있습니다.

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

그 결과, 언어 비교가 사용되는 경우 길이가 다른 두 문자열이 같음으로 비교될 수 있습니다. 호출자는 이러한 시나리오에서 문자열 길이를 처리하는 특수한 사례 논리를 적용하지 않도록 주의해야 합니다.

문화권 인식 검색 및 비교 루틴은 언어 검색 및 비교 루틴의 특수한 형태입니다. 문화권 인식 비교자에서 데이터 정렬 요소의 개념은 지정된 문화권과 관련된 정보를 포함하도록 확장됩니다.

예를 들어 [헝가리어 알파벳에서](https://en.wikipedia.org/wiki/Hungarian_alphabet) 연속으로 나타나는 두 문자 \<dz\>는 \<d\> 또는 \<z\>와 구별되는 고유한 자체 문자로 간주됩니다. 즉, 문자열에 \<dz\>가 보이는 경우 헝가리어 문화권 인식 비교자는 이를 단일 데이터 정렬 요소로 처리합니다.

| String | 데이터 정렬 요소 | 설명 |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | (표준 언어 비교자 사용) |
| `"endz"` | `"e" + "n" + "dz"` | (헝가리어 문화권 인식 비교자 사용) |

헝가리어 문화권 인식 비교자를 사용하는 경우 이는 문자열 `"endz"`가 부분 문자열 `"z"`로 끝나지 않음을 뜻합니다. <\dz\>와 <\z\>가 의미상 의미가 서로 다른 데이터 정렬 요소로 간주되기 때문입니다.

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - 동작: 언어 비교자와 문화권 인식 비교자의 동작은 수시로 조정될 수 있습니다. ICU와 이전 Windows NLS 기능 모두 세계 언어의 변화를 반영하여 업데이트됩니다. 자세한 내용은 블로그 게시물 [Local (culture) data churn](/archive/blogs/shawnste/locale-culture-data-churn)을 참조하세요. 서수 비교자의 동작은 정확한 비트 검색 및 비교를 수행하므로 변경되지 않습니다. 하지만 유니코드가 더 많은 문자 집합을 포함하도록 확장되고 기존 대/소문자 데이터의 누락을 수정함에 따라 *OrdinalIgnoreCase* 비교자의 동작이 변경될 수 있습니다.
> - 사용: `StringComparison.InvariantCulture` 비교자와 `StringComparison.InvariantCultureIgnoreCase` 비교자는 문화권을 인식하지 않는 언어 비교자입니다. 즉, 이러한 비교자는 악센트가 있는 문자 é에 가능한 기본 표현이 여러 개 있을 수 있다는 개념과 이러한 모든 표현을 같음으로 처리해야 한다는 것을 이해합니다. 그러나 문화권을 인식하지 않는 언어 비교자에는 위에 나온 것처럼 \<d\> 또는 \<z\>와는 다른 \<dz\>의 특별한 처리가 포함되지 않습니다. 또한 독일어 Eszett(ß)와 같은 문자도 특별히 처리하지 않습니다.

.NET은 고정 전역화 모드도 제공합니다. 이 옵트인 모드는 언어 검색 및 비교 루틴을 처리하는 코드 경로를 사용하지 않도록 설정합니다. 이 모드에서 모든 작업은 호출자가 어떤 `CultureInfo` 또는 `StringComparison` 인수를 제공하든 관계 없이 서수 또는 *OrdinalIgnoreCase* 동작을 사용합니다. 자세한 내용은 [세계화를 위한 런타임 구성 옵션](../../core/run-time-config/globalization.md)과 [.NET Core 세계화 고정 모드](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)를 참조하세요.

자세한 내용은 [.NET에서의 문자열 비교 모범 사례](best-practices-strings.md)를 참조하세요.

## <a name="security-implications"></a>보안 의미

앱에서 영향을 받는 API가 필터링에 사용되는 경우 CA1307 및 CA1309 코드 분석 규칙을 사용하도록 설정하여 실수로 언어 검색이 서수 검색 대신 사용되었을 수 있는 위치를 찾는 것이 좋습니다. 다음과 같은 코드 패턴은 보안 악용에 취약할 수 있습니다.

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

`string.IndexOf(string)` 메서드는 기본적으로 언어 검색을 사용하기 때문에 문자열에 리터럴 `'<'` 또는 `'&'` 문자가 포함되고 `string.IndexOf(string)` 루틴에서 검색 부분 문자열을 찾을 수 없다는 `-1`가 반환될 수 있습니다. 코드 분석 규칙 CA1307과 CA1309는 이러한 호출 사이트에 플래그를 지정하고, 잠재적 문제가 있음을 개발자에게 알립니다.

## <a name="default-search-and-comparison-types"></a>기본 검색 및 비교 형식

다음 표에는 다양한 문자열 및 문자열 형식 API의 기본 검색 및 비교 형식이 나와 있습니다. 호출자가 명시적인 `CultureInfo` 또는 `StringComparison` 매개 변수를 제공하는 경우 이 매개 변수는 모든 기본값에 적용됩니다.

| API | 기본 동작 | 설명 |
|---|---|---|
| `string.Compare` | CurrentCulture | |
| `string.CompareTo` | CurrentCulture | |
| `string.Contains` | 서수 | |
| `string.EndsWith` | 서수 | (첫 번째 매개 변수가 `char`인 경우) |
| `string.EndsWith` | CurrentCulture | (첫 번째 매개 변수가 `string`인 경우) |
| `string.Equals` | 서수 | |
| `string.GetHashCode` | 서수 | |
| `string.IndexOf` | 서수 | (첫 번째 매개 변수가 `char`인 경우) |
| `string.IndexOf` | CurrentCulture | (첫 번째 매개 변수가 `string`인 경우) |
| `string.IndexOfAny` | 서수 | |
| `string.LastIndexOf` | 서수 | (첫 번째 매개 변수가 `char`인 경우) |
| `string.LastIndexOf` | CurrentCulture | (첫 번째 매개 변수가 `string`인 경우) |
| `string.LastIndexOfAny` | 서수 | |
| `string.Replace` | 서수 | |
| `string.Split` | 서수 | |
| `string.StartsWith` | 서수 | (첫 번째 매개 변수가 `char`인 경우) |
| `string.StartsWith` | CurrentCulture | (첫 번째 매개 변수가 `string`인 경우) |
| `string.ToLower` | CurrentCulture | |
| `string.ToLowerInvariant` | InvariantCulture | |
| `string.ToUpper` | CurrentCulture | |
| `string.ToUpperInvariant` | InvariantCulture | |
| `string.Trim` | 서수 | |
| `string.TrimEnd` | 서수 | |
| `string.TrimStart` | 서수 | |
| `string == string` | 서수 | |
| `string != string` | 서수 | |

`string` API와 달리 모든 `MemoryExtensions` API는 다음을 제외하고 기본적으로 서수 검색 및 비교를 수행합니다.

| API | 기본 동작 | 설명 |
|---|---|---|
| `MemoryExtensions.ToLower` | CurrentCulture | (null `CultureInfo` 인수를 전달한 경우) |
| `MemoryExtensions.ToLowerInvariant` | InvariantCulture | |
| `MemoryExtensions.ToUpper` | CurrentCulture | (null `CultureInfo` 인수를 전달한 경우) |
| `MemoryExtensions.ToUpperInvariant` | InvariantCulture | |

결과적으로 `string` 사용에서 `ReadOnlySpan<char>` 사용으로 코드를 변환하면 의도하지 않은 동작 변경이 발생할 수 있습니다. 그 예는 다음과 같습니다.

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

이를 해결하는 데 권장되는 방법은 명시적 `StringComparison` 매개 변수를 이러한 API에 전달하는 것입니다. 코드 분석 규칙 CA1307와 CA1309가 도움이 될 수 있습니다.

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a>참조

- [세계화 관련 호환성이 손상되는 변경](../../core/compatibility/globalization.md)
- [.NET에서의 문자열 비교 모범 사례](best-practices-strings.md)
- [C#에서 문자열을 비교하는 방법](../../csharp/how-to/compare-strings.md)
- [.NET 세계화 및 ICU](../globalization-localization/globalization-icu.md)
- [서수 문자열 작업과 문화권 구분 문자열 작업 비교](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [.NET 소스 코드 분석 개요](../../fundamentals/code-analysis/overview.md)
