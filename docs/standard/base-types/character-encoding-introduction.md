---
title: .NET의 문자 인코딩 소개
description: .NET의 문자 인코딩/디코딩에 대해 알아봅니다.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: 572fcd289eea720873d94e7fc71f3b4a030d1d70
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282311"
---
# <a name="character-encoding-in-net"></a>.NET의 문자 인코딩

이 문서에서는 .NET에서 사용되는 문자 인코딩 시스템을 소개합니다. 이 문서에서는 <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune> 및 <xref:System.Globalization.StringInfo> 형식이 유니코드, UTF-16 및 UTF-8에서 작동하는 방식에 대해 설명합니다.

여기서 ‘문자’라는 용어는 ‘판독기가 단일 표시 요소로 인식’한다는 일반적인 의미로 사용합니다.  일반적인 예는 문자 "a", 기호 "@" 및 이모지 "🐂"입니다. [문자소 클러스터](#grapheme-clusters) 섹션에 설명된 것처럼 한 문자처럼 보이는 것이 실제로는 독립적인 여러 표시 요소로 구성된 경우도 있습니다.

## <a name="the-no-locstring-and-no-locchar-types"></a>string 및 char 형식

[string](xref:System.String) 클래스의 인스턴스는 일부 텍스트를 나타냅니다. `string`은 논리적으로 16비트 값의 시퀀스이며, 각각은 [char](xref:System.Char) 구조체의 인스턴스입니다. [string.Length](xref:System.String.Length) 속성은 `string` 인스턴스의 `char` 인스턴스 수를 반환합니다.

다음 샘플 함수는 `string`에 있는 모든 `char` 인스턴스의 값을 16진수 표기법으로 출력합니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

이 함수에 string “Hello”를 전달하면 다음과 같은 출력이 표시됩니다.

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

각 문자는 단일 `char` 값으로 표현됩니다. 이 패턴은 대부분의 세계 언어에 적용됩니다. 예를 들어 다음은 *nǐ hǎo* 로 발음되고 *Hello* 를 의미하는 중국어 문자 2자의 출력입니다.

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

그러나 일부 언어와 일부 기호 및 이모지에서는 `char` 인스턴스 2개를 사용하여 단일 문자를 나타냅니다. 예를 들어 오세이지족 언어에서 *Osage* 를 의미하는 단어의 문자와 `char` 인스턴스를 비교해 보겠습니다.

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

위의 예제에서 공백을 제외한 각 문자는 `char` 인스턴스 2개로 표현됩니다.

ox 이모지를 보여 주는 다음 예제에 표시된 것처럼 단일 유니코드 이모지도 두 개의 `char`로 표현됩니다.

```output
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

예제를 통해 `char` 인스턴스 수를 나타내는 `string.Length` 값과 표시되는 문자 수가 반드시 같은 것은 아님을 알 수 있습니다. 단일 `char` 인스턴스만으로 한 문자를 나타낼 수 없는 경우도 있습니다.

단일 문자에 매핑되는 `char` 쌍을 ‘서로게이트 쌍’이라고 합니다. 그 작동 방식을 이해하려면 유니코드 및 UTF-16 인코딩을 이해해야 합니다.

## <a name="unicode-code-points"></a>유니코드 코드 포인트

유니코드는 다양한 언어 및 스크립트를 사용하여 다양한 플랫폼에서 사용하기 위한 국제 인코딩 표준입니다.

유니코드 표준은 110만 개 이상의 [코드 포인트](https://www.unicode.org/glossary/#code_point)를 정의합니다. 코드 포인트는 0과 `U+10FFFF`(10진수 1,114,111) 사이의 정수 값입니다. 일부 코드 포인트는 문자, 기호 또는 이모지에 할당됩니다. 다른 코드 포인트는 텍스트 또는 문자가 표시되는 방식을 제어하는 작업(예: 새 줄로 이동)에 할당됩니다. 많은 코드 포인트가 아직 할당되지 않은 상태입니다.

다음은 코드 포인트 할당의 몇 가지 예제와 해당 유니코드 차트의 링크입니다.

|Decimal|Hex       |예제|설명|
|------:|----------|-------|-----------|
|10     | `U+000A` |N/A| [줄 바꿈](https://www.unicode.org/charts/PDF/U0000.pdf) |
|97     | `U+0061` | a | [라틴 소문자 A](https://www.unicode.org/charts/PDF/U0000.pdf) |
|562    | `U+0232` | Ȳ | [장음 기호를 사용하는 라틴어 대문자 Y](https://www.unicode.org/charts/PDF/U0180.pdf) |
|68,675 | `U+10C43`| 𐱃 | [고대 튀르크 문자 ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|127,801| `U+1F339`| 🌹 | [장미 이모지](https://www.unicode.org/charts/PDF/U1F300.pdf) |

코드 포인트는 관례적으로 `U+xxxx` 구문을 사용하여 지칭됩니다. 여기서 `xxxx`는 16진수로 인코딩된 정수 값입니다.

코드 포인트의 전체 범위 내에 두 가지 하위 범위가 있습니다.

* **BMP(기본 다국어 평면)** 는 `U+0000..U+FFFF` 범위에 있습니다. 이 16비트 범위는 전 세계 쓰기 시스템을 대부분 포괄하는 데 충분한 65,536개 코드 포인트를 제공합니다.
* **보조 코드 포인트** 는 `U+10000..U+10FFFF` 범위에 있습니다. 이 21비트 범위는 덜 알려진 언어와 이모지 같은 다른 용도로 사용할 수 있는 백만 개 이상의 추가 코드 포인트를 제공합니다.

다음 다이어그램에서는 BMP와 보조 코드 포인트의 관계를 보여 줍니다.

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP 및 보조 코드 포인트":::

## <a name="utf-16-code-units"></a>UTF-16 코드 단위

16비트 유니코드 변환 형식([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16))은 16비트 ‘코드 단위’를 사용하여 유니코드 코드 포인트를 나타내는 문자 인코딩 시스템입니다. .NET에서는 UTF-16을 사용하여 `string`의 텍스트를 인코딩합니다. `char` 인스턴스는 16비트 코드 단위를 나타냅니다.

단일 16비트 코드 단위는 기본 다국어 평면 16비트 범위의 코드 포인트를 나타낼 수 있습니다. 하지만 보조 범위의 코드 포인트의 경우 두 개의 `char` 인스턴스가 필요합니다.

## <a name="surrogate-pairs"></a>서로게이트 쌍

두 개의 16비트 값을 단일 21비트 값으로 변환하는 과정은 `U+D800`부터 `U+DFFF`까지(10진수 55.296부터 57,343까지)의 특수 범위인 *서로게이트 코드 포인트* 를 통해 간단해집니다.

다음 다이어그램에서는 BMP와 서로게이트 코드 포인트의 관계를 보여 줍니다.

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="BMP 및 서로게이트 코드 포인트":::

*상위 서로게이트* 코드 포인트(`U+D800..U+DBFF`) 바로 다음에 *하위 서로게이트* 코드 포인트(`U+DC00..U+DFFF`)가 오는 경우 이 쌍은 다음 수식을 사용하여 보조 코드 포인트로 해석됩니다.

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

다음은 10진수 표기법을 사용하는 동일한 수식입니다.

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

*상위* 서로게이트 코드 포인트가 *하위* 서로게이트 코드 포인트보다 높은 값을 갖는 것은 아닙니다. 상위 서로게이트 코드 포인트는 전체 21비트 코드 포인트 범위의 상위 차수 11비트를 계산하는 데 사용되기 때문에 "상위"라고 합니다. 하위 서로게이트 코드 포인트는 하위 차수 10비트를 계산하는 데 사용됩니다.

예를 들어 서로게이트 쌍 `0xD83C` 및 `0xDF39`에 해당하는 실제 코드 포인트는 다음과 같이 계산됩니다.

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

다음은 10진수 표기법을 사용한 동일한 계산입니다.

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

앞의 예제에서는 `"\ud83c\udf39"`가 앞서 언급한 `U+1F339 ROSE ('🌹')` 코드 포인트의 UTF-16 인코딩입니다.

## <a name="unicode-scalar-values"></a>유니코드 스칼라 값

용어 [유니코드 스칼라 값](https://www.unicode.org/glossary/#unicode_scalar_value)은 서로게이트 코드 포인트가 아닌 모든 코드 포인트를 참조합니다. 즉, 스칼라 값은 문자가 할당되었거나 나중에 문자가 할당될 수 있는 모든 코드 포인트입니다. 여기서 “문자”는 텍스트 또는 문자가 표시되는 방식을 제어하는 작업 등을 포함하여 코드 포인트에 할당될 수 있는 모든 것을 가리킵니다.

다음 다이어그램에서는 스칼라 값 코드 포인트를 보여 줍니다.

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="스칼라 값":::

### <a name="the-no-locrune-type-as-a-scalar-value"></a>스칼라 값의 Rune 형식

.NET Core 3.0부터 <xref:System.Text.Rune?displayProperty=fullName> 형식은 유니코드 스칼라 값을 나타냅니다. **`Rune`는 .NET Core 2.x 또는 .NET Framework 4.x에서 사용할 수 없습니다.**

`Rune` 생성자는 결과 인스턴스가 유효한 유니코드 스칼라 값인지 확인합니다. 유효하지 않은 경우에는 예외를 throw합니다. 다음 예제에서는 입력이 유효한 스칼라 값을 나타내므로 `Rune` 인스턴스를 성공적으로 인스턴스화하는 코드를 보여 줍니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

다음 예제에서는 코드 포인트가 서로게이트 범위에 있고 서로게이트 쌍에 속하지 않기 때문에 예외를 throw합니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

다음 예제에서는 코드 포인트가 보조 범위를 초과하기 때문에 예외를 throw합니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="no-locrune-usage-example-changing-letter-case"></a>Rune 사용 예제: 문자 대/소문자 변경

`char`를 사용하고 스칼라 값 코드 포인트에서 작동하는 것으로 가정하는 API는 `char`가 서로게이트 쌍의 일부인 경우 올바르게 작동하지 않습니다. 예를 들어 string의 각 char에서 <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType>를 호출하는 다음 메서드를 살펴보겠습니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

`input` string에 소문자 데저렛 문자 `er`(`𐑉`)이 포함되는 경우 이 코드는 대문자(`𐐡`)로 변환되지 않습니다. 이 코드는 각 서로게이트 코드 포인트 `U+D801` 및 `U+DC49`에서 별도로 `char.ToUpperInvariant`를 호출합니다. 그러나 `U+D801` 자체에는 해당 정보를 소문자로 식별하는 데 충분한 정보가 없으므로 `char.ToUpperInvariant`는 이를 그대로 둡니다. 그리고 `U+DC49`도 동일한 방식으로 처리합니다. 그 결과 `input` string의 소문자 '𐑉'가 대문자 '𐑉'로 변환되지 않습니다.

string를 올바르게 대문자로 변환하는 두 가지 옵션은 다음과 같습니다.

* `char` 및 `char`를 반복하는 대신 입력 string에서 <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType>를 호출합니다. `string.ToUpperInvariant` 메서드는 각 서로게이트 쌍의 두 부분에 모두 액세스할 수 있으므로 모든 유니코드 코드 포인트를 올바르게 처리할 수 있습니다.
* 다음 예제와 같이 `char` 인스턴스 대신 `Rune` 인스턴스로 유니코드 스칼라 값을 반복합니다. `Rune` 인스턴스는 유효한 유니코드 스칼라 값이므로 스칼라 값에 대해 작동할 것으로 간주되는 API에 전달될 수 있습니다. 예를 들어 다음 예제와 같이 <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType>를 호출하면 올바른 결과가 반환됩니다.

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-no-locrune-apis"></a>기타 Rune API

`Rune` 형식은 다수의 `char` API의 아날로그를 제공합니다. 예를 들어 다음 메서드는 `char` 형식에 대한 정적 API를 미러링합니다.

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

`Rune` 인스턴스에서 원시 스칼라 값을 가져오려면 <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> 속성을 사용합니다.

`Rune` 인스턴스를 `char`의 시퀀스로 다시 변환하려면 <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> 또는 <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> 메서드를 사용합니다.

모든 유니코드 스칼라 값은 단일 `char` 또는 서로게이트 쌍으로 표현할 수 있으므로 `Rune` 인스턴스는 최대 2개의 `char` 인스턴스로 나타낼 수 있습니다. <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType>를 사용하여 `Rune` 인스턴스를 표현하는 데 필요한 `char` 인스턴스 수를 확인합니다.

.NET `Rune` 형식에 대한 자세한 내용은 [`Rune` API 참조](xref:System.Text.Rune)를 참조하세요.

## <a name="grapheme-clusters"></a>문자소 클러스터

한 문자처럼 보이는 것이 여러 코드 포인트가 조합된 결과일 수 있으므로 “문자” 대신 자주 사용되는 보다 서술적인 용어가 [문자소 클러스터](https://www.unicode.org/glossary/#grapheme_cluster)입니다. .NET에서 해당 용어는 [텍스트 요소](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A)입니다.

`string` 인스턴스 “a”, “á”, “á”, “`👩🏽‍🚒`” 등을 살펴보겠습니다, 운영 체제가 유니코드 표준에 지정된 대로 이들 항목을 처리하는 경우 각 `string` 인스턴스는 단일 텍스트 요소나 문자소 클러스터로 나타납니다. 하지만 마지막 두 개는 둘 이상의 스칼라 값 코드 포인트로 표현됩니다.

* string "a"는 하나의 스칼라 값으로 표현되고 하나의 `char` 인스턴스를 포함합니다.

  * `U+0061 LATIN SMALL LETTER A`

* string "á"는 하나의 스칼라 값으로 표현되고 하나의 `char` 인스턴스를 포함합니다.

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* string "á"는 "Á"와 같아 보이지만 두 개의 스칼라 값으로 표현되고 두 개의 `char` 인스턴스를 포함합니다.

  * `U+0061 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* 마지막으로 string "`👩🏽‍🚒`"은 4개의 스칼라 값으로 표현되고 7개의 `char` 인스턴스를 포함합니다.

  * `U+1F469 WOMAN`(보조 범위, 서로게이트 쌍 필요)
  * `U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4`(보조 범위, 서로게이트 쌍 필요)
  * `U+200D ZERO WIDTH JOINER`
  * `U+1F692 FIRE ENGINE`(보조 범위, 서로게이트 쌍 필요)

위의 예제 중 일부(예: 결합 악센트 한정자 또는 스킨 톤 한정자)에서는 코드 포인트가 화면에 독립 실행형 요소로 표시되지 않습니다. 대신, 텍스트 요소의 모양을 수정하는 데 사용됩니다. 예제를 통해 단일 “문자” 또는 “문자소 클러스터”로 간주되는 것을 구성하기 위해 여러 스칼라 값이 필요할 수 있음을 알 수 있습니다.

`string`의 문자소 클러스터를 열거하려면 다음 예제와 같이 <xref:System.Globalization.StringInfo> 클래스를 사용합니다. Swift에 대해 잘 알고 있는 경우 .NET `StringInfo` 형식은 개념적으로 [Swift의 `character` 형식](https://developer.apple.com/documentation/swift/character)과 비슷합니다.

### <a name="example-count-no-locchar-no-locrune-and-text-element-instances"></a>예: count char, Rune 및 텍스트 요소 인스턴스

.NET API에서는 문자소 클러스터를 *텍스트 요소* 라고 합니다. 다음 메서드는 `string`에서 `char`, `Rune` 및 텍스트 요소 인스턴스 간의 차이점을 보여 줍니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

.NET Framework 또는 .NET Core 3.1 이전 버전에서 이 코드를 실행하는 경우 이모지의 텍스트 요소 수에 `4`가 표시됩니다. 이는 .NET 5에서 수정된 `StringInfo` 클래스의 버그로 인한 것입니다.

### <a name="example-splitting-no-locstring-instances"></a>예: string 인스턴스 분할

`string` 인스턴스를 분할하는 경우 서로게이트 쌍 및 문자소 클러스터를 분할하지 마세요. 다음은 string에 10자마다 줄 바꿈을 삽입하려는 코드의 잘못된 예입니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

이 코드는 `char` 인스턴스를 열거하기 때문에 10개 `char`의 경계에 걸쳐 있는 서로게이트 쌍이 분할되고 그 사이에 줄 바꿈이 삽입됩니다. 서로게이트 코드 포인트는 쌍으로만 의미가 있으므로 이 삽입은 데이터를 손상시킵니다.

`char` 인스턴스 대신 `Rune` 인스턴스(스칼라 값)를 열거하는 경우 데이터 손상 가능성이 제거되지 않습니다. 한 `Rune` 인스턴스 집합이 10개 `char`의 경계에 걸쳐 있는 문자소 클러스터를 구성할 수 있습니다. 문자소 클러스터 집합이 분할된 경우 올바르게 해석할 수 없습니다.

다음 예제와 같이 문자소 클러스터(또는 텍스트 요소)를 계산하여 string을 줄 바꿈하는 것이 더 나은 방법입니다.

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

그러나 앞에서 설명한 것처럼 .NET 5 이외의 .NET 구현에서는 `StringInfo` 클래스가 일부 문자소 클러스터를 잘못 처리할 수 있습니다.

## <a name="utf-8-and-utf-32"></a>UTF-8 및 UTF-32

이전 섹션에서는 UTF-16에 초점을 두었습니다. .NET이 `string` 인스턴스를 인코딩하는 데 사용하기 때문이었습니다. 다른 유니코드용 인코딩 시스템 [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) 및 [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32)도 있습니다. 이러한 인코딩은 각각 8비트 코드 단위 및 32비트 코드 단위를 사용합니다.

UTF-16과 마찬가지로 UTF-8은 일부 유니코드 스칼라 값을 나타내기 위해 여러 코드 단위가 필요합니다. UTF-32는 단일 32비트 코드 단위로 모든 스칼라 값을 나타낼 수 있습니다.

다음은 이러한 세 가지 유니코드 인코딩 시스템에서 동일한 유니코드 코드 포인트를 표현하는 방법을 보여 주는 몇 가지 예제입니다.

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

앞서 설명한 것처럼 [서로게이트 쌍](#surrogate-pairs)의 단일 UTF-16 코드 단위는 그 자체로는 의미가 없습니다. 동일한 방식으로 단일 UTF-8 코드 단위가 스칼라 값을 계산하기 위해 2, 3 또는 4개의 시퀀스로 사용되는 경우에는 자체로는 의미가 없습니다.

### <a name="endianness"></a>endian

.NET에서 string의 UTF-16 코드 단위는 연속 메모리에 16비트 정수(`char` 인스턴스)의 시퀀스로 저장됩니다. 개별 코드 단위의 비트는 현재 아키텍처의 [endian](https://en.wikipedia.org/wiki/Endianness)에 따라 배치됩니다.

Little-Endian 아키텍처에서는 UTF-16 코드 포인트 `[ D801 DCCC ]`로 구성된 string이 바이트 `[ 0x01, 0xD8, 0xCC, 0xDC ]`로 메모리에 배치됩니다. Big-Endian 아키텍처에서는 동일한 string이 바이트 `[ 0xD8, 0x01, 0xDC, 0xCC ]`로 메모리에 배치됩니다.

서로 통신하는 컴퓨터 시스템은 네트워크를 통과하는 데이터의 표현에 동의해야 합니다. 대부분의 네트워크 프로토콜은 텍스트를 전송할 때 UTF-8을 표준으로 사용하여 Little-Endian 컴퓨터와 통신하는 Big-Endian 컴퓨터에서 발생하는 문제를 부분적으로 방지합니다. UTF-8 코드 포인트 `[ F0 90 93 8C ]`로 구성되는 string은 endian에 관계없이 항상 바이트 `[ 0xF0, 0x90, 0x93, 0x8C ]`로 표현됩니다.

텍스트를 전송하는 데 UTF-8을 사용하기 위해 .NET 애플리케이션은 종종 다음 예제와 같은 코드를 사용합니다.

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

앞의 예제에서 [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) 메서드는 UTF-16 `string`을 일련의 유니코드 스칼라 값으로 다시 디코딩한 다음 해당 스칼라 값을 UTF-8로 인코드하여 결과 시퀀스를 `byte` 배열에 배치합니다. [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) 메서드는 반대 방향으로 변환을 수행하여 UTF-8 `byte` 배열을 UTF-16 `string`로 변환합니다.

> [!WARNING]
> UTF-8은 인터넷에서 일반적이므로 네트워크에서 원시 바이트를 읽고 데이터를 UTF-8인 것처럼 처리하는 것이 좋습니다. 그러나 잘 구성된 인코딩인지 유효성을 검사해야 합니다. 악의적인 클라이언트가 잘못 구성된 UTF-8을 서비스에 제출할 수 있습니다. 이러한 데이터를 잘 구성된 것처럼 작업하는 경우 애플리케이션에서 오류 또는 보안 허점이 발생할 수 있습니다. UTF-8 데이터의 유효성을 검사하려면 들어오는 데이터를 `string`으로 변환하는 동안 유효성 검사를 수행하는 `Encoding.UTF8.GetString`와 같은 메서드를 사용할 수 있습니다.

### <a name="well-formed-encoding"></a>잘 구성된 인코딩

잘 구성된 유니코드 인코딩은 오류 없이 명확하게 디코딩할 수 있는 유니코드 스칼라 값의 시퀀스로 디코딩할 수 있는 코드 단위의 string입니다. 잘 구성된 데이터는 UTF-8, UTF-16 및 UTF-32 사이에서 자유롭게 트랜스코딩될 수 있습니다.

인코딩 시퀀스가 잘 구성되었는지 여부는 컴퓨터 아키텍처의 endian과 관련이 없습니다. 잘못 구성된 UTF-8 시퀀스는 Big-Endian 및 Little-Endian 컴퓨터 모두에서 동일한 방식으로 잘못 구성된 것입니다.

다음은 잘못 구성된 인코딩의 몇 가지 예제입니다.

* UTF-8에서 시퀀스 `[ 6C C2 61 ]`은 잘못 구성된 것입니다. `C2` 뒤에 `61`이 올 수 없기 때문입니다.

* UTF-16에서 시퀀스 `[ DC00 DD00 ]`(또는 C#의 string `"\udc00\udd00"`)는 잘못 구성된 것입니다. 하위 서로게이트 `DC00` 뒤에 다른 하위 서로게이트 `DD00`가 올 수 없기 때문입니다.

* UTF-32에서 시퀀스 `[ 0011ABCD ]`는 잘못 구성된 것입니다. `0011ABCD`가 유니코드 스칼라 값 범위를 벗어나기 때문입니다.

.NET에서 `string` 인스턴스는 거의 항상 잘 구성된 UTF-16 데이터를 포함하지만 이것이 보장되지는 않습니다. 다음 예제에서는 `string` 인스턴스에 잘못 구성된 UTF-16 데이터를 만드는 유효한 C# 코드를 보여 줍니다.

* 잘못 구성된 리터럴:

  ```csharp
  const string s = "\ud800";
  ```

* 서로게이트 쌍을 분할하는 substring:

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

[`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A)과 같은 API는 잘못 구성된 `string` 인스턴스를 반환하지 않습니다. `Encoding.GetString` 및 `Encoding.GetBytes` 메서드는 입력에서 잘못 구성된 시퀀스를 검색하고 출력을 생성할 때 문자 대체를 수행합니다. 예를 들어 [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A)이 입력에서 ASCII가 아닌 바이트(U+0000..U+007F 범위를 벗어남)를 발견할 경우 반환된 `string` 인스턴스에 '?'를 삽입합니다. [`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A)은 반환된 `string` 인스턴스에서 잘못 구성된 UTF-8 시퀀스를 `U+FFFD REPLACEMENT CHARACTER ('�')`로 바꿉니다. 자세한 내용은 [유니코드 표준](https://www.unicode.org/versions/latest/) 섹션 5.22 및 3.9를 참조하세요.

잘못 구성된 시퀀스가 발견될 때 문자 대체를 수행하는 대신 예외를 throw하도록 기본 제공 `Encoding` 클래스를 구성할 수도 있습니다. 이 방법은 문자 대체가 허용되지 않을 수 있는 보안 관련 애플리케이션에서 자주 사용됩니다.

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

기본 제공 `Encoding` 클래스를 사용하는 방법에 대한 자세한 내용은 [.NET에서 문자 인코딩 클래스를 사용하는 방법](character-encoding.md)을 참조하세요.

## <a name="see-also"></a>참조

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [전역화 및 지역화](../globalization-localization/index.md)
