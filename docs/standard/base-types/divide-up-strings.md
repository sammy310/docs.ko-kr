---
title: 문자열을 부분 문자열로 분리
description: String.Split, 정규식, String.Substring 등 문자열의 일부를 추출하는 다양한 방법에 대해 알아봅니다.
ms.date: 10/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: 88947c4576b0496e4b4e45042d665e3ca5857c53
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403483"
---
# <a name="extract-substrings-from-a-string"></a>문자열에서 부분 문자열 추출

이 문서에서는 문자열의 일부를 추출하는 몇 가지 방법을 설명합니다.

- 원하는 부분 문자열이 알려진 구분 문자(또는 문자)로 구분된 경우 [Split 메서드](#stringsplit-method)를 사용합니다.
- [정규식](#regular-expressions)은 문자열이 고정 패턴을 준수하는 경우에 유용합니다.
- 문자열의 모든 부분 문자열을 추출하려는 것이 아니라면 [IndexOf 메서드와 Substring 메서드](#stringindexof-and-stringsubstring-methods)를 함께 사용하세요.

## <a name="stringsplit-method"></a>String.Split 메서드

<xref:System.String.Split%2A?displayProperty=nameWithType>은 지정하는 하나 이상의 구분 문자에 따라 문자열을 부분 문자열 그룹으로 분할하는 데 도움이 되는 몇 가지 오버로드를 제공합니다. 최종 결과에서 전체 부분 문자열 수를 제한하거나, 부분 문자열에서 공백 문자를 자르거나, 빈 부분 문자열을 제외할 수 있습니다.

다음 예제는 `String.Split()`의 세 가지 오버로드를 보여 줍니다. 첫 번째 예제는 구분 문자를 전달하지 않고 <xref:System.String.Split(System.Char[])> 오버로드를 호출합니다. 구분 문자를 지정하지 않으면 `String.Split()`은 공백 문자인 기본 구분 기호를 사용하여 문자열을 분할합니다.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

여기에서 볼 수 있듯이 마침표 문자(`.`)가 두 부분 문자열에 포함됩니다. 마침표 문자를 제외하려는 경우 마침표 문자를 추가 구분 문자로 추가할 수 있습니다. 다음 예제는 이 작업을 수행하는 방법을 보여 줍니다.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

부분 문자열에서 마침표가 사라졌지만 이제는 두 개의 빈 부분 문자열이 추가로 포함되었습니다. 이러한 빈 부분 문자열은 단어와 그 뒤에 오는 마침표 사이의 부분 문자열을 나타냅니다. 결과 배열에서 빈 부분 문자열을 생략하려면 <xref:System.String.Split(System.Char[],System.StringSplitOptions)> 오버로드를 호출하고 `options` 매개 변수의 <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>을 지정합니다.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a>정규식

문자열이 고정 패턴을 따르는 경우 정규식을 사용하여 해당 요소를 추출하고 처리할 수 있습니다. 예를 들어 문자열이 "  숫자 피연산자 숫자" 형식을 사용하는 경우 [정규식](regular-expressions.md)을 사용하여 문자열의 요소를 추출하고 처리할 수 있습니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

정규식 패턴 `(\d+)\s+([-+*/])\s+(\d+)`는 다음과 같이 정의됩니다.

|무늬|Description|
|-------------|-----------------|
|`(\d+)`|하나 이상의 10진수 숫자가 일치하는지 확인합니다. 이 그룹은 첫 번째 캡처링 그룹입니다.|
|`\s+`|하나 이상의 공백 문자를 찾습니다.|
|`([-+*/])`|산술 연산자 기호(+, -, *, /)를 찾습니다. 이 그룹은 두 번째 캡처링 그룹입니다.|
|`\s+`|하나 이상의 공백 문자를 찾습니다.|
|`(\d+)`|하나 이상의 10진수 숫자가 일치하는지 확인합니다. 이 그룹은 세 번째 캡처링 그룹입니다.|

정규식을 사용하여 고정 문자 집합이 아닌 패턴을 기반으로 문자열에서 부분 문자열을 추출할 수도 있습니다. 다음은 이러한 조건 중 하나가 발생하는 일반적인 시나리오입니다.

- 하나 이상의 구분 문자가 <xref:System.String> 인스턴스에서 항상 구분 기호로 사용되지는 않습니다.

- 구분 문자의 시퀀스와 수는 변수이거나 알 수 없습니다.

예를 들어 <xref:System.String.Split%2A> 메서드는 다음 문자열을 분할하는 데 사용할 수 없습니다. `\n`(줄 바꿈) 문자 수가 변수이고 이 문자가 항상 구분 기호로 사용되지는 않기 때문입니다.

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

정규식은 다음 예제에서 볼 수 있듯이 이 문자열을 쉽게 분할할 수 있습니다.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

정규식 패턴 `\[([^\[\]]+)\]`는 다음과 같이 정의됩니다.

|무늬|Description|
|-------------|-----------------|
|`\[`|여는 대괄호를 찾습니다.|
|`([^\[\]]+)`|여는 대괄호나 닫는 대괄호가 아닌 문자를 한 번 이상 찾습니다. 이 그룹은 첫 번째 캡처링 그룹입니다.|
|`\]`|닫는 대괄호를 찾습니다.|

<xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드는 고정 문자 집합 대신 정규식 패턴을 기반으로 문자열을 분할한다는 점을 제외하면 <xref:System.String.Split%2A?displayProperty=nameWithType>과 거의 동일합니다. 예를 들어 다음 예제에서는 <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 하이픈과 기타 문자의 다양한 조합으로 구분된 부분 문자열이 포함된 문자열을 분할합니다.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

정규식 패턴 `\s-\s?[+*]?\s?-\s`는 다음과 같이 정의됩니다.

|무늬|Description|
|-------------|-----------------|
|`\s-`|뒤에 하이픈이 오는 공백 문자를 찾습니다.|
|`\s?`|0번 이상 나오는 공백 문자를 찾습니다.|
|`[+*]?`|0번 또는 한 번 나오는 + 또는 * 문자를 찾습니다.|
|`\s?`|0번 이상 나오는 공백 문자를 찾습니다.|
|`-\s`|뒤에 공백 문자가 오는 하이픈을 찾습니다.|

## <a name="stringindexof-and-stringsubstring-methods"></a>String.IndexOf 및 String.Substring 메서드

문자열의 모든 부분 문자열에 관심이 있는 것이 아니라면 일치가 시작되는 인덱스를 반환하는 문자열 비교 메서드 중 하나를 사용하는 것이 좋습니다. 그런 다음 <xref:System.String.Substring%2A> 메서드를 호출하여 원하는 부분 문자열을 추출할 수 있습니다. 문자열 비교 메서드는 다음과 같습니다.

- 문자열 인스턴스에서 처음 나오는 문자 또는 문자열의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.IndexOf%2A>

- 문자 배열에서 문자가 처음 나오는 현재 문자열 인스턴스의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.IndexOfAny%2A>

- 문자열 인스턴스에서 마지막으로 나오는 문자 또는 문자열의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.LastIndexOf%2A>

- 문자 배열에서 문자가 마지막으로 나오는 현재 문자열 인스턴스의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.LastIndexOfAny%2A>

다음 예제는 <xref:System.String.IndexOf%2A> 메서드를 사용하여 문자열의 마침표를 찾습니다. 그런 다음 <xref:System.String.Substring%2A> 메서드를 사용하여 전체 문장을 반환합니다.

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a>참조

- [.NET의 기본적인 문자열 작업](basic-string-operations.md)
- [.NET 정규식](regular-expressions.md)
- [C#에서 String.Split을 사용하여 문자열을 구문 분석하는 방법](../../csharp/how-to/parse-strings-using-split.md)
