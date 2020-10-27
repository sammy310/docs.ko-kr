---
title: 튜플 형식 - C# 참조
description: 'C# 튜플 알아보기: 관련 데이터 요소를 느슨하게 그룹화하는 데 사용할 수 있는 간단한 데이터 구조'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: d996c7afecba1b58bfd8337fa444fd71790dd482
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471774"
---
# <a name="tuple-types-c-reference"></a>튜플 형식(C# 참조)

C# 7.0 이상에서 사용할 수 있는 ‘튜플’ 기능은 간단한 데이터 구조로 여러 데이터 요소를 그룹화하는 간결한 구문을 제공합니다. 다음 예제에서는 튜플 변수를 선언하고 초기화하며 관련 데이터 멤버에 액세스하는 방법을 보여 줍니다.

[!code-csharp-interactive[tuple intro](snippets/shared/ValueTuples.cs#Introduction)]

앞의 예제와 같이 튜플 형식을 정의하려면 모든 관련 데이터 멤버의 형식과 필요한 경우 [필드 이름](#tuple-field-names)을 지정합니다. 튜플 형식으로 메서드를 정의할 수는 없지만 다음 예제와 같이 .NET에서 제공하는 메서드를 사용할 수 있습니다.

[!code-csharp-interactive[tuple methods](snippets/shared/ValueTuples.cs#MethodOnTuples)]

C# 7.3부터 튜플 형식은 [같음 연산자](../operators/equality-operators.md) `==` 및 `!=`을 지원합니다. 자세한 내용은 [튜플 같음](#tuple-equality) 섹션을 참조하세요.

튜플 형식은 [값 형식](value-types.md)이며 튜플 요소는 공용 필드입니다. 이에 따라 튜플은 ‘변경 가능한’ 값 형식으로 설정됩니다.

> [!NOTE]
> 튜플 기능을 사용하려면 .NET Core 및 .NET Framework 4.7 이상에서 사용할 수 있는 <xref:System.ValueTuple?displayProperty=nameWithType> 형식 및 관련 제네릭 형식(예: <xref:System.ValueTuple%602?displayProperty=nameWithType>)이 필요합니다. .NET Framework 4.6.2 이하를 대상으로 하는 프로젝트에서 튜플을 사용하려면 프로젝트에 NuGet 패키지 [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/)을 추가합니다.

임의의 많은 요소를 포함하는 튜플을 정의할 수 있습니다.

[!code-csharp-interactive[large tuple](snippets/shared/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a>튜플 사용 사례

튜플의 가장 일반적인 사용 사례 중 하나는 메서드 반환 형식입니다. 즉, [`out` 메서드 매개 변수](../keywords/out-parameter-modifier.md)를 정의하는 대신 다음 예제와 같이 메서드 결과를 튜플 반환 형식으로 그룹화할 수 있습니다.

[!code-csharp-interactive[multiple method outputs](snippets/shared/ValueTuples.cs#MultipleReturns)]

앞의 예제와 같이 반환된 튜플 인스턴스를 직접 사용하거나 개별 변수로 [분해](#tuple-assignment-and-deconstruction)할 수 있습니다.

[익명 형식](../../programming-guide/classes-and-structs/anonymous-types.md) 대신 튜플 형식을 사용할 수도 있습니다(예: LINQ 쿼리에서). 자세한 내용은 [무명 형식과 튜플 형식 중에서 선택](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)을 참조하세요.

일반적으로 튜플을 사용하여 관련 데이터 요소를 느슨하게 그룹화합니다. 이 방법은 대개 프라이빗 및 내부 유틸리티 메서드 내에서 유용합니다. 공용 API의 경우 [클래스](../keywords/class.md) 또는 [구조체](struct.md) 형식을 정의하는 것이 좋습니다.

## <a name="tuple-field-names"></a>튜플 필드 이름

다음 예제와 같이 튜플 초기화 식이나 튜플 형식 정의에 튜플 필드의 이름을 명시적으로 지정할 수 있습니다.

[!code-csharp-interactive[explicit field names](snippets/shared/ValueTuples.cs#ExplicitFieldNames)]

C# 7.1부터는 필드 이름을 지정하지 않으면 다음 예제와 같이 튜플 초기화 식의 해당 변수 이름에서 이름이 유추될 수 있습니다.

[!code-csharp-interactive[inferred field names](snippets/shared/ValueTuples.cs#InferFieldNames)]

이를 튜플 프로젝션 이니셜라이저라고 합니다. 다음과 같은 경우에 변수 이름은 튜플 필드 이름으로 프로젝션되지 않습니다.

- 후보 이름이 튜플 형식의 멤버 이름인 경우(예: `Item3`, `ToString` 또는 `Rest`)
- 후보 이름이 명시적이든 암시적이든 다른 튜플 필드 이름과 중복되는 경우

이 경우 명시적으로 필드 이름을 지정하거나 기본 이름으로 필드에 액세스합니다.

튜플 필드의 기본 이름은 `Item1`, `Item2`, `Item3` 등입니다. 다음 예제와 같이 필드 이름이 명시적으로 지정되거나 유추되는 경우에도 언제든지 필드의 기본 이름을 사용할 수 있습니다.

[!code-csharp-interactive[default field names](snippets/shared/ValueTuples.cs#DefaultFieldNames)]

[튜플 할당](#tuple-assignment-and-deconstruction) 및 [튜플 같음 비교](#tuple-equality)에서는 필드 이름을 고려하지 않습니다.

컴파일 시간에 컴파일러는 기본값이 아닌 필드 이름을 해당하는 기본 이름으로 바꿉니다. 따라서 명시적으로 지정되거나 유추된 필드 이름을 런타임에 사용할 수 없습니다.

## <a name="tuple-assignment-and-deconstruction"></a>튜플 할당 및 분해

C#은 다음 두 조건을 모두 충족하는 튜플 형식 간에 할당을 지원합니다.

- 두 튜플 형식의 요소 수가 동일함
- 각 튜플 위치에서 오른쪽 튜플 요소의 형식이 해당하는 왼쪽 튜플 요소의 형식과 동일하거나 해당 형식으로 암시적으로 변환 가능함

튜플 요소 값은 튜플 요소의 순서에 따라 할당됩니다. 다음 예제와 같이 튜플 필드의 이름은 무시되고 할당되지 않습니다.

[!code-csharp-interactive[tuple assignment](snippets/shared/ValueTuples.cs#Assignment)]

`=` 대입 연산자를 사용하여 튜플 인스턴스를 개별 변수로 ‘분해’할 수도 있습니다. 다음 중 한 가지 방법으로 해당 작업을 수행할 수 있습니다.

- 괄호 안에 각 변수의 형식을 명시적으로 선언합니다.

  [!code-csharp-interactive[specify types of variables](snippets/shared/ValueTuples.cs#DeconstructExplicit)]

- 괄호 밖에서 `var` 키워드를 사용하여 형식화된 변수를 암시적으로 선언하며 컴파일러가 해당 형식을 유추하도록 합니다.

  [!code-csharp-interactive[implicitly typed variables](snippets/shared/ValueTuples.cs#DeconstructVar)]

- 기존 변수를 사용합니다.

  [!code-csharp-interactive[existing variables](snippets/shared/ValueTuples.cs#DeconstructExisting)]

튜플 및 기타 형식을 분해하는 방법에 관한 자세한 내용은 [튜플 및 기타 형식 분해](../../deconstruct.md)를 참조하세요.

## <a name="tuple-equality"></a>튜플 같음

C# 7.3부터 튜플 형식에서는 `==` 및 `!=` 연산자를 지원합니다. 해당 연산자는 튜플 요소 순서에 따라 왼쪽 피연산자의 멤버를 오른쪽 피연산자의 해당 멤버와 비교합니다.

[!code-csharp-interactive[tuple equality](snippets/shared/ValueTuples.cs#TupleEquality)]

앞의 예제와 같이 `==` 및 `!=` 연산에는 튜플 필드 이름이 고려되지 않습니다.

다음 조건이 둘 다 충족되면 두 튜플을 비교할 수 있습니다.

- 두 튜플의 요소 수가 동일합니다. 예를 들어 `t1` 및 `t2`의 요소 수가 다른 경우 `t1 != t2`는 컴파일되지 않습니다.
- 각 튜플 위치에서 왼쪽 및 오른쪽 튜플 피연산자의 해당 요소는 `==` 및 `!=` 연산자와 비교할 수 있습니다. 예를 들어 `1`은 `(1, 2)`와 비교할 수 없기 때문에 `(1, (2, 3)) == ((1, 2), 3)`은 컴파일되지 않습니다.

`==` 및 `!=` 연산자는 단락(short-circuiting) 방식으로 튜플을 비교합니다. 즉, 같지 않은 요소 쌍을 충족하거나 튜플의 끝에 도달하는 즉시 연산이 중지됩니다. 그러나 다음 예제와 같이 비교하기 전에 ‘모든’ 튜플 요소가 평가됩니다.

[!code-csharp-interactive[tuple element evaluation](snippets/shared/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a>출력 매개 변수 튜플

일반적으로 [`out` 매개 변수](../keywords/out-parameter-modifier.md)를 포함하는 메서드는 튜플을 반환하는 메서드로 리팩터링합니다. 그러나 `out` 매개 변수가 튜플 형식일 수 있는 경우가 있습니다. 다음 예제에서는 튜플을 `out` 매개 변수로 사용하는 방법을 보여 줍니다.

[!code-csharp-interactive[tuple as out parameter](snippets/shared/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a>튜플과 `System.Tuple` 비교

<xref:System.ValueTuple?displayProperty=nameWithType> 형식으로 지원되는 C# 튜플은 <xref:System.Tuple?displayProperty=nameWithType> 형식으로 표현되는 튜플과 다릅니다. 주요 차이점은 다음과 같습니다.

- `ValueTuple` 형식은 [값 형식](value-types.md)입니다. `Tuple` 형식은 [참조 형식](../keywords/reference-types.md)입니다.
- `ValueTuple` 형식은 변경할 수 있습니다. `Tuple` 형식은 변경할 수 없습니다.
- `ValueTuple` 형식의 데이터 멤버는 필드입니다. `Tuple` 형식의 데이터 멤버는 속성입니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 다음 기능 제안 노트를 참조하세요.

- [튜플 이름 유추(즉, 튜플 프로젝션 이니셜라이저)](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [튜플 형식에서 `==` 및 `!=` 지원](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [값 형식](value-types.md)
- [무명 형식과 튜플 형식 중에서 선택](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
