---
title: nullable 참조 형식 - C# 참조
description: C# nullable 참조 형식 및 사용 방법 알아보기
ms.date: 04/06/2020
ms.openlocfilehash: 274a613a8381a2b7718c9025f51aadb2eb32af36
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471865"
---
# <a name="nullable-reference-types-c-reference"></a>nullable 참조 형식(C# 참조)

> [!NOTE]
> 이 문서에서는 nullable 참조 형식을 설명합니다. [nullable 값 형식](nullable-value-types.md)을 선언할 수도 있습니다.

nullable 참조 형식은 ‘nullable 인식 컨텍스트’에 옵트인된 코드에서 C# 8.0부터 사용할 수 있습니다.  nullable 참조 형식, null 정적 분석 경고 및 [null 허용 연산자](../operators/null-forgiving.md)는 선택적 언어 기능입니다. 모두 기본적으로 꺼져 있습니다. ‘nullable 컨텍스트’는 빌드 설정을 사용하여 프로젝트 수준에서 제어되거나 pragma를 사용하여 빌드 설정에서 제어됩니다. 

 nullable 인식 컨텍스트에서:

- 참조 형식 `T`의 변수는 null이 아닌 값으로 초기화되어야 하며, `null`일 수 있는 값이 할당되지 않을 수 있습니다.
- 참조 형식 `T?`의 변수는 `null`로 초기화되거나 `null`이 할당될 수 있지만, 역참조하기 전에 `null`에 대해 확인되어야 합니다.
- `m!`의 경우와 같이 null 허용 연산자를 적용하면 `T?` 형식의 `m` 변수는 null이 아닌 것으로 간주합니다.

null을 허용하지 않는 참조 형식과 `T` nullable 참조 형식 `T?` 간 차이점은 컴파일러의 이전 규칙 해석에 따라 적용됩니다. `T` 형식의 변수 및 `T?` 형식의 변수는 동일한 .NET 형식으로 나타냅니다. 다음 예제에서는 null을 허용하지 않는 문자열 및 nullable 문자열을 선언하고 null 허용 연산자를 사용하여 null을 허용하지 않는 문자열에 값을 할당합니다.

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetCoreSyntax":::

`notNull` 및 `nullable` 변수는 둘 다 <xref:System.String> 형식으로 나타냅니다. null을 허용하지 않는 형식 및 nullable 형식은 둘 다 같은 형식으로 저장되므로 nullable 참조 형식을 사용할 수 있는 여러 위치가 있습니다. 일반적으로 nullable 참조 형식은 기본 클래스 또는 구현된 인터페이스로 사용할 수 없습니다. nullable 참조 형식은 개체 생성 또는 형식 테스트 식에 사용할 수 없습니다. nullable 참조 형식은 멤버 액세스 식의 형식일 수 없습니다. 다음 예제에서는 다음 구문을 보여 줍니다.

```csharp
public MyClass : System.Object? // not allowed
{
}

var nullEmpty = System.String?.Empty; // Not allowed
var maybeObject = new object?(); // Not allowed
try
{
    if (thing is string? nullableString) // not allowed
        Console.WriteLine(nullableString);
} catch (Exception? e) // Not Allowed
{
    Console.WriteLine("error");
}
```

## <a name="nullable-references-and-static-analysis"></a>nullable 참조 및 정적 분석

이전 섹션의 예제에서는 nullable 참조 형식의 특성을 보여 줍니다. nullable 참조 형식은 새 클래스 형식이 아니라 기존 참조 형식의 주석입니다. 컴파일러는 해당 주석을 사용하여 코드에서 잠재적 null 참조 오류를 찾을 수 있습니다. null을 허용하지 않는 참조 형식과 nullable 참조 형식 간에는 런타임 차이가 없습니다. 컴파일러는 null을 허용하지 않는 참조 형식에 대한 런타임 검사를 추가하지 않습니다. 컴파일 시간 분석에는 이점이 있습니다. 컴파일러는 코드에서 잠재적 null 오류를 찾고 해결하는 데 도움이 되는 경고를 생성합니다. 의도를 선언하고 코드가 해당 의도를 위반하면 컴파일러가 경고를 표시합니다.

nullable 사용 컨텍스트에서 컴파일러는 nullable 참조 형식 및 null을 허용하지 않는 참조 형식의 변수에서 정적 분석을 수행합니다. 컴파일러는 각 참조 변수의 null 상태를 ‘null이 아님’ 또는 ‘null일 수 있음’으로 추적합니다.   null을 허용하지 않는 참조의 기본 상태는 ‘null이 아님’입니다.  nullable 참조의 기본 상태는 ‘null일 수 있음’입니다. 

null을 허용하지 않는 참조 형식은 해당 null 상태가 ‘null이 아님’이므로 항상 안전하게 역참조할 수 있습니다.  해당 규칙을 적용하기 위해 null을 허용하지 않는 참조 형식이 null이 아닌 값으로 초기화되지 않는 경우 컴파일러는 경고를 실행합니다. 지역 변수는 선언된 위치에 할당되어야 합니다. 모든 생성자는 본문, 호출된 생성자 또는 필드 이니셜라이저를 사용하여 모든 필드를 할당해야 합니다. 상태가 ‘null일 수 있음’인 참조에 null을 허용하지 않는 참조가 할당되는 경우 컴파일러는 경고를 실행합니다.  그러나 null을 허용하지 않는 참조는 ‘null이 아님’이므로 해당 변수가 역참조될 때 경고가 실행되지 않습니다. 

nullable 참조 형식은 `null`에 초기화되거나 할당될 수 있습니다. 따라서 정적 분석에서는 역참조되기 전에 변수가 ‘null이 아님’인지 확인해야 합니다.  nullable 참조가 ‘null일 수 있음’으로 확인되면 해당 참조는 null을 허용하지 않는 참조 변수에 할당될 수 없습니다.  다음 클래스는 해당 경고의 예를 보여 줍니다.

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetClassWithNullable":::

다음 코드 조각은 이 클래스를 사용하는 경우 컴파일러가 경고를 내보내는 위치를 보여 줍니다.

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetLocalWarnings":::

앞의 예제에서는 참조 변수의 null 상태를 확인하는 컴파일러의 정적 분석을 보여 줍니다. 컴파일러는 null 검사 및 할당에 대한 언어 규칙을 적용하여 분석에 대해 알립니다.  컴파일러는 메서드 또는 속성의 의미 체계를 가정할 수 없습니다. Null 검사를 수행하는 메서드를 호출하는 경우 컴파일러는 해당 메서드가 변수의 null 상태에 영향을 준다는 것을 알 수 없습니다. 컴파일러에 인수 및 반환 값의 의미 체계를 알리는 여러 가지 특성을 API에 추가할 수 있습니다. 해당 특성은 .NET Core 라이브러리의 여러 일반적인 API에 적용되었습니다. 예를 들어 <xref:System.String.IsNullOrEmpty%2A>가 업데이트되었으며 컴파일러는 해당 메서드를 null 검사로 올바르게 해석합니다. Null 상태 정적 분석에 적용되는 특성에 대한 자세한 내용은 [nullable 특성](../attributes/nullable-analysis.md) 문서를 참조하세요.

## <a name="setting-the-nullable-context"></a>nullable 컨텍스트 설정

두 가지 방법으로 nullable 컨텍스트를 제어할 수 있습니다. 프로젝트 수준에서 `<Nullable>enable</Nullable>` 프로젝트 설정을 추가할 수 있습니다. 단일 C# 소스 파일에서 `#nullable enable` pragma를 추가하여 nullable 컨텍스트를 사용하도록 설정할 수 있습니다. [nullable 전략 설정](../../nullable-migration-strategies.md) 문서를 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 제안을 참조하세요.

- [nullable 참조 형식](~/_csharplang/proposals/csharp-8.0/nullable-reference-types.md)
- [Nullable 참조 형식 사양 초안](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [Nullable 값 형식](nullable-value-types.md)
