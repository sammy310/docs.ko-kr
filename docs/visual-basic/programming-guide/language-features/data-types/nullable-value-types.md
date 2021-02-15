---
description: '자세한 정보: Nullable 값 형식 (Visual Basic)'
title: Nullable 값 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: acc91d98a3ed288a9bf0bcf6abbd3d8a516bd699
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483887"
---
# <a name="nullable-value-types-visual-basic"></a>Nullable 값 형식(Visual Basic)

특정 상황에서 정의 된 값이 없는 값 형식을 사용 하는 경우가 있습니다. 예를 들어 데이터베이스의 필드는 할당 된 값이 있는 것을 의미 하는 값이 할당 되는 것을 구분 해야 할 수 있습니다. 값 형식은 일반 값 이나 null 값을 사용 하도록 확장할 수 있습니다. 이러한 확장을 *nullable 형식* 이라고 합니다.

각 nullable 값 형식은 제네릭 구조체에서 생성 됩니다 <xref:System.Nullable%601> . 작업 관련 작업을 추적 하는 데이터베이스를 고려 합니다. 다음 예제에서는 nullable 형식을 생성 하 `Boolean` 고 해당 형식의 변수를 선언 합니다. 다음 세 가지 방법으로 선언을 작성할 수 있습니다.

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

변수는 값, 값 또는 값을 `ridesBusToWork` 가질 수 `True` `False` 없습니다. 초기 기본값은 값이 아닙니다 .이 경우이 사용자에 대 한 정보가 아직 획득 되지 않았음을 의미할 수 있습니다. 이와 대조적으로는 `False` 정보를 얻고 사용자가 버스를 사용 하 여 작업을 수행 하지 않았음을 의미할 수 있습니다.

Nullable 값 형식을 사용 하 여 변수 및 속성을 선언할 수 있으며 nullable 값 형식의 요소가 포함 된 배열을 선언할 수 있습니다. Null을 허용 하는 값 형식을 포함 하는 프로시저를 매개 변수로 선언할 수 있으며 프로시저에서 nullable 값 형식을 반환할 수 있습니다 `Function` .

배열, 또는 클래스와 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다 `String` . 내부 형식은 값 형식 이어야 합니다. 자세한 내용은 [값 형식 및 참조 형식](value-types-and-reference-types.md)을 참조 하세요.

## <a name="using-a-nullable-type-variable"></a>Nullable 형식 변수 사용

Nullable 값 형식의 가장 중요 한 멤버는 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 속성입니다. Nullable 값 형식의 변수에 대해는 <xref:System.Nullable%601.HasValue%2A> 변수에 정의 된 값이 포함 되어 있는지 여부를 알려 줍니다. <xref:System.Nullable%601.HasValue%2A>가 이면 `True` 에서 값을 읽을 수 있습니다 <xref:System.Nullable%601.Value%2A> . 및는 모두 <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> `ReadOnly` 속성입니다.

### <a name="default-values"></a>기본값

Nullable 값 형식으로 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A> 속성의 기본값은 `False` 입니다. 즉, 기본적으로 변수에는 기본 값 형식의 기본 값 대신 정의 된 값이 없습니다. 다음 예제에서 변수의 `numberOfChildren` 기본값은 0 이지만 원래 값에는 정의 된 값이 없습니다 `Integer` .

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Null 값은 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다. 가 `numberOfChildren` 로 선언 된 경우 `Integer` 정보를 현재 사용할 수 없음을 나타낼 수 있는 값이 없습니다.

### <a name="storing-values"></a>값 저장

일반적으로 nullable 값 형식의 변수 또는 속성에 값을 저장 합니다. 다음 예제에서는 `numberOfChildren` 이전 예제에서 선언 된 변수에 값을 할당 합니다.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Nullable 값 형식의 변수 또는 속성이 정의 된 값을 포함 하는 경우 해당 값이 할당 되지 않은 초기 상태로 되돌아갈 수 있습니다. 다음 예제와 같이 변수 또는 속성을로 설정 하 여이 작업을 수행 `Nothing` 합니다.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> `Nothing`Nullable 값 형식의 변수에 할당할 수 있지만 등호를 사용 하 여에 대해 테스트할 수는 없습니다 `Nothing` . 등호를 사용 하는 비교는 `someVar = Nothing` 항상로 평가 `Nothing` 됩니다. <xref:System.Nullable%601.HasValue%2A> `False` 또는 연산자를 사용 하 여에 대해 변수의 속성을 테스트 하거나 테스트할 수 있습니다 `Is` `IsNot` .

### <a name="retrieving-values"></a>값 검색

Nullable 값 형식의 변수 값을 검색 하려면 먼저 해당 속성을 테스트 <xref:System.Nullable%601.HasValue%2A> 하 여 값이 있는지 확인 해야 합니다. 가 일 때 값을 읽으려고 하는 <xref:System.Nullable%601.HasValue%2A> 경우 `False` Visual Basic 예외를 throw <xref:System.InvalidOperationException> 합니다. 다음 예제에서는 이전 예제의 변수를 읽는 데 권장 되는 방법을 보여 줍니다 `numberOfChildren` .

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Nullable 형식 비교

Nullable `Boolean` 변수가 부울 식에 사용 되는 경우 결과는, 또는가 될 수 있습니다 `True` `False` `Nothing` . 다음은 및에 대 한 진위 테이블입니다 `And` `Or` . `b1`및는 `b2` 세 가지 가능한 값을 가지 므로 평가할 조합 수는 9 개입니다.

|b1|b2|b1 및 b2|b1 또는 b2|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

부울 변수나 식의 값이 이면이 고 `Nothing` , 그렇지 않으면 `true` `false` 입니다. 다음 예제를 살펴보십시오.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

이 예에서는가 `b1 And b2` 로 평가 `Nothing` 됩니다. 따라서 `Else` 절은 각 문에서 실행 되며 출력은 다음과 같습니다 `If` .

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso``OrElse`단락 평가를 사용 하는 및는 첫 번째 피연산자가로 평가 될 때 두 번째 피연산자를 계산 해야 합니다 `Nothing` .

## <a name="propagation"></a>전파

산술 연산자, 비교 연산자 또는 형식 작업의 피연산자 중 하나 또는 둘 다가 nullable 값 형식인 경우 연산의 결과도 nullable 값 형식입니다. 두 피연산자의 값이 모두 null이 아닌 경우 null을 허용 하는 값 `Nothing` 형식인 것 처럼 연산이 피연산자의 내부 값에 대해 수행 됩니다. 다음 예제에서는 및 변수를 `compare1` `sum1` 암시적으로 형식화 합니다. 마우스 포인터를 올려 놓으면 컴파일러가 둘 모두에 대해 nullable 값 형식을 유추 하는 것을 알 수 있습니다.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

피연산자 중 하나 또는 둘 다의 값이 이면 `Nothing` 결과는가 됩니다 `Nothing` .

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>데이터에 Nullable 형식 사용

데이터베이스는 nullable 값 형식을 사용 하는 가장 중요 한 위치 중 하나입니다. 일부 데이터베이스 개체는 현재 nullable 값 형식을 지원 하지만 디자이너에서 생성 된 테이블 어댑터는 지원 하지 않습니다. [Nullable 형식에 대 한 TableAdapter 지원을](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)참조 하세요.

## <a name="see-also"></a>추가 정보

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [데이터 형식](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [TableAdapters를 사용하여 데이터 세트 채우기](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [If 연산자](../../../language-reference/operators/if-operator.md)
- [지역 형식 유추](../variables/local-type-inference.md)
- [Is 연산자](../../../language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../language-reference/operators/isnot-operator.md)
- [Nullable 값 형식 (c #)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
