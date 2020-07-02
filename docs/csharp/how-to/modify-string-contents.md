---
title: 문자열 내용 수정 방법 - C# 가이드
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: e607a8a2e96a73f64463d75a75a2bfe3f518d118
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324164"
---
# <a name="how-to-modify-string-contents-in-c"></a>C\#에서 문자열 내용을 수정하는 방법

이 문서에서는 기존 `string`을 수정하여 `string`을 생성하는 다양한 기술을 보여 줍니다. 설명된 모든 기술은 새 `string` 개체로 수정의 결과를 반환합니다. 원래 문자열과 수정된 문자열이 고유 인스턴스임을 보여 주기 위해 이 예제에서는 결과를 새 변수에 저장합니다. 각 예제를 실행할 때 원래 `string`과 수정된 새 `string`을 확인할 수 있습니다.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

이 문서에서 설명되는 여러 가지 기술이 있습니다. 기존 텍스트를 바꿀 수 있습니다. 패턴을 검색하고 다른 텍스트와 일치하는 텍스트를 바꿀 수 있습니다. 일련의 문자로 문자열을 처리할 수 있습니다. 공백을 제거하는 편리한 메서드를 사용할 수도 있습니다. 시나리오에 가장 일치하는 기술을 선택합니다.

## <a name="replace-text"></a>텍스트 바꾸기

다음 코드는 기존 텍스트를 대체로 바꿔 새 문자열을 만듭니다.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet1":::

위의 코드는 문자열의 이러한 *변경할 수 없는* 속성을 보여 줍니다. 앞의 예제에서 원래 문자열, `source`가 수정되지 않는 것을 볼 수 있습니다. <xref:System.String.Replace%2A?displayProperty=nameWithType> 메서드는 수정 내용을 포함하는 새 `string`을 만듭니다.

<xref:System.String.Replace%2A> 메서드는 문자열 또는 단일 문자를 바꿀 수 있습니다. 두 경우 모두에서 검색된 텍스트의 모든 항목이 대체됩니다.  다음 예제에서는 모든 ' ' 문자를 '\_'로 바꿉니다.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet2":::

원본 문자열은 변경되지 않으며, 새 문자열은 교체와 함께 반환됩니다.

## <a name="trim-white-space"></a>공백 제거

<xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> 및 <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> 메서드를 사용하여 선행 또는 후행 공백을 제거할 수 있습니다.  다음 코드에서는 각 예제를 보여 줍니다. 원본 문자열 변경되지 않습니다. 이러한 메서드는 수정된 내용이 포함된 새 문자열을 반환합니다.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet3":::

## <a name="remove-text"></a>텍스트 제거

<xref:System.String.Remove%2A?displayProperty=nameWithType> 메서드를 사용하여 문자열에서 텍스트를 제거할 수 있습니다. 이 메서드는 특정 인덱스에서 시작하는 문자 수를 제거합니다. 다음 예제에서는 <xref:System.String.Remove%2A>가 뒤에 오는 <xref:System.String.IndexOf%2A?displayProperty=nameWithType>을 사용하여 문자열에서 텍스트를 제거하는 방법을 보여 줍니다.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet4":::

## <a name="replace-matching-patterns"></a>일치 패턴 바꾸기

[정규식](../../standard/base-types/regular-expressions.md)을 사용하여 패턴에 의해 정의된 새 텍스트로 텍스트 일치 패턴을 바꿀 수 있습니다. 다음 예제에서는 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 클래스를 사용하여 원본 문자열의 패턴을 찾고 적절한 대/소문자로 대체합니다. <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> 메서드는 해당 인수 중 하나로 대체 논리를 제공하는 함수를 사용합니다. 이 예제에서 해당 함수, `LocalReplaceMatchCase`는 샘플 메서드 내에서 선언된 **로컬 함수**입니다. `LocalReplaceMatchCase`는 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스를 사용하여 적절한 대/소문자로 대체 문자열을 작성합니다.

정규식은 알려진 텍스트가 아닌 패턴을 따르는 텍스트를 검색하고 대체하는 데 가장 유용합니다. 자세한 내용은 [문자열 검색 방법](search-strings.md)을 참조하세요. 검색 패턴, "the\s"는 공백 문자가 뒤에 오는 문자 "the"를 검색합니다. 패턴의 해당 부분을 사용하면 원본 문자열의 "there"와 일치하지 않습니다. 정규식 언어 요소에 대한 자세한 내용은 [정규식 언어 - 빠른 참조](../../standard/base-types/regular-expression-language-quick-reference.md)를 참조하세요.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet5":::

<xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> 메서드는 <xref:System.Text.StringBuilder> 개체의 내용으로 변경할 수 없는 문자열을 반환합니다.

## <a name="modifying-individual-characters"></a>개별 문자 수정

문자열에서 문자 배열을 생성하고, 배열의 내용을 수정한 다음, 수정된 배열의 내용에서 새 문자열을 만들 수 있습니다.

다음 예제에서는 문자열에서 문자 집합을 대체하는 방법을 보여 줍니다. 먼저 <xref:System.String.ToCharArray?displayProperty=nameWithType> 메서드를 사용하여 문자의 배열을 만듭니다. <xref:System.String.IndexOf%2A> 메서드를 사용하여 단어 "fox"의 시작 인덱스를 찾습니다. 다음 세 개의 문자는 서로 다른 단어로 바뀝니다. 마지막으로 새 문자열은 업데이트된 문자 배열에서 생성됩니다.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet6":::

## <a name="programmatically-build-up-string-content"></a>프로그래밍 방식으로 문자열 콘텐츠 작성

문자열은 변경할 수 없으므로 이전 예제에서는 모두 임시 문자열 또는 문자 배열을 만듭니다. 고성능 시나리오에서는 이 힙 할당을 방지하는 것이 좋습니다. .NET Core는 중간 임시 문자열 할당을 방지하면서 콜백을 통해 문자열의 문자 콘텐츠를 프로그래밍 방식으로 채울 수 있는 <xref:System.String.Create%2A?displayProperty=nameWithType> 메서드를 제공합니다.

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet7":::

안전하지 않은 코드를 사용하여 고정 블록의 문자열을 수정할 수 있지만 문자열을 만든 후에는 문자열 콘텐츠를 수정하지 않는 것이 **좋습니다**. 그렇게 하면 예측할 수 없는 방식으로 작업이 중단되기 때문입니다. 예를 들어 콘텐츠가 동일한 문자열을 다른 사용자가 인턴(intern)하는 경우 해당 사용자는 복사본을 얻게 되며 문자열을 수정해도 해당 사용자의 문자열은 수정되지 않습니다.

## <a name="see-also"></a>참조

- [.NET Framework 정규식](../../standard/base-types/regular-expressions.md)
- [정규식 언어 - 빠른 참조](../../standard/base-types/regular-expression-language-quick-reference.md)
