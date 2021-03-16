---
title: '호환성이 손상되는 변경: StringInfo 및 TextElementEnumerator가 이제 UAX29 규격임'
description: StringInfo 및 TextElementEnumerator가 최신 버전의 유니코드 표준에 따라 문자소 클러스터를 처리하는 .NET 5의 세계화 관련 호환성이 손상되는 변경 내용에 관해 알아봅니다.
ms.date: 04/07/2020
ms.openlocfilehash: cf770e30bfadf1973bbe018cc9d2783ed6234723
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256707"
---
# <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a>StringInfo 및 TextElementEnumerator가 이제 UAX29 규격임

이 변경 전에 <xref:System.Globalization.StringInfo?displayProperty=fullName> 및 <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>는 모든 문자소 클러스터를 제대로 처리하지 못했습니다. 일부 문자소는 함께 유지되지 않고 구성 요소로 분할되었습니다. 이제 <xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator>는 최신 버전의 유니코드 표준에 따라 문자소 클러스터를 처리합니다.

또한 Visual Basic에서 문자열의 문자 순서를 반대로 만드는 <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> 메서드는 이제 문자소 클러스터에 대한 유니코드 표준을 따릅니다.

## <a name="change-description"></a>변경 내용 설명

[문자소](https://www.unicode.org/glossary/#grapheme) 또는 [확장 문자소 클러스터](https://www.unicode.org/glossary/#extended_grapheme_cluster)는 여러 유니코드 코드 포인트로 구성될 수 있는 단일 사용자 인식 문자입니다. 예를 들어 태국어 문자 "kam"(:::no-loc text="กำ":::)을 포함하는 문자열은 다음 두 개의 문자로 구성됩니다.

- :::no-loc text="ก":::(= '\u0e01') THAI CHARACTER KO KAI
- :::no-loc text=" ำ":::(= '\u0e33') THAI CHARACTER SARA AM

사용자에게 표시되는 경우 운영 체제는 두 문자를 결합하여 단일 표시 문자(또는 문자소)인 "kam"(또는 :::no-loc text="กำ":::)을 형성합니다. 이모지도 비슷한 방식으로 표시하기 위해 결합된 여러 문자로 구성될 수 있습니다.

> [!TIP]
> .NET 문서에서는 문자소를 참조하는 경우 “텍스트 요소”라는 용어를 사용하는 경우도 있습니다.

<xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator> 클래스는 문자열을 검사하고 포함된 문자소에 관한 정보를 반환합니다. .NET Framework(모든 버전) 및 .NET Core 3.x 이하에서 이 두 개의 클래스는 일부 결합 클래스를 처리하지만 [유니코드 표준](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries)을 완전하게 준수하지는 않는 사용자 지정 논리를 사용합니다. 예를 들어 <xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator> 클래스는 해당 구성 요소를 함께 유지하는 대신 단일 태국어 문자 “kam”을 다시 구성 요소로 분할합니다. 또한 해당 클래스는 단일 문자소 클러스터로 함께 유지하는 대신 이모지 문자 "🤷🏽‍♀️"를 4개의 클러스터(어깨를 으쓱하는 사람, 피부색 한정자, 성별 한정자 및 표시되지 않는 결합자)로 잘못 분할합니다.

.NET 5부터 <xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator> 클래스는 [유니코드 표준 부록\# 29 수정 35, 섹션 3](https://www.unicode.org/reports/tr29/tr29-35.html)에서 정의한 대로 유니코드 표준을 구현합니다. 특히 이제는 모든 결합 클래스에 대해 [확장 문자소 클러스터](https://www.unicode.org/glossary/#extended_grapheme_cluster)를 반환합니다.

다음 C# 코드를 생각해 볼 수 있습니다.

```csharp
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

.NET Framework 및 .NET Core 3.x 이하 버전에서는 문자소가 분할되고 콘솔 출력은 다음과 같습니다.

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

.NET 5 이상 버전에서 문자소는 함께 유지되며 콘솔 출력은 다음과 같습니다.

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

또한 .NET 5부터 Visual Basic에서 문자열의 문자 순서를 반대로 만드는 <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> 메서드는 이제 문자소 클러스터에 대한 유니코드 표준을 따릅니다.

해당 변경 내용은 .Net Core 3.0에서 <xref:System.Text.Rune?displayProperty=fullName> 형식으로 도입된 유니코드 스칼라 값 열거형 API를 보완하기 위해 확장 문자소 클러스터 열거형 API를 비롯하여 .NET의 광범위한 유니코드 및 UTF-8 개선 사항 세트에 포함됩니다.

## <a name="version-introduced"></a>도입된 버전

.NET 5.0

## <a name="recommended-action"></a>권장 조치

아무 작업도 수행할 필요가 없습니다. 앱은 자동으로 다양한 세계화 관련 시나리오에서 더 많은 표준 규격 방식으로 동작합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

### Category

Globalization

-->
