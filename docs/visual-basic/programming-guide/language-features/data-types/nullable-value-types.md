---
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249684"
---
# <a name="nullable-value-types-visual-basic"></a>Nullable 값 형식(Visual Basic)

경우에 따라 특정 상황에서 정의된 값이 없는 값 형식을 사용할 수 있습니다. 예를 들어 데이터베이스의 필드는 의미 있는 할당된 값을 갖는 것과 할당된 값이 없는 것을 구별해야 할 수 있습니다. 값 형식을 확장하여 일반 값 또는 null 값을 사용할 수 있습니다. 이러한 확장을 *null형식이라고*합니다.

각 nullable 값 형식은 <xref:System.Nullable%601> 제네릭 구조에서 생성됩니다. 작업 관련 활동을 추적하는 데이터베이스를 고려합니다. 다음 예제는 nullable `Boolean` 형식을 생성 하 고 해당 형식의 변수를 선언 합니다. 세 가지 방법으로 선언을 작성할 수 있습니다.

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

변수는 `ridesBusToWork` `True`의 `False`값을 보유할 수 있습니다. 초기 기본값은 전혀 값이 아니며, 이 경우 이 사람에 대한 정보가 아직 가져오지 않은 것을 의미할 수 있습니다. 반대로, `False` 정보를 입수하고 사람이 출근하기 위해 버스를 타지 않는다는 것을 의미 할 수 있습니다.

nullable 값 형식을 사용 하 고 nullable 값 형식의 요소를 사용 하 고 배열을 선언할 수 있습니다 변수 및 속성을 선언할 수 있습니다. nullable 값 형식을 매개 변수로 프로시저를 선언할 수 있으며 `Function` 프로시저에서 nullable 값 형식을 반환할 수 있습니다.

배열, a `String`또는 클래스와 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다. 기본 형식은 값 형식이어야 합니다. 자세한 내용은 [값 유형 및 참조 유형을](value-types-and-reference-types.md)참조하십시오.

## <a name="using-a-nullable-type-variable"></a>Nullable 형식 변수 사용

nullable 값 형식의 가장 중요한 <xref:System.Nullable%601.HasValue%2A> 멤버는 해당 멤버와 <xref:System.Nullable%601.Value%2A> 속성입니다. nullable 값 형식의 변수의 <xref:System.Nullable%601.HasValue%2A> 경우 변수에 정의된 값이 포함되어 있는지 여부를 알려줍니다. 의 경우 에서 값을 <xref:System.Nullable%601.Value%2A>읽을 수 있습니다. <xref:System.Nullable%601.HasValue%2A> `True` 둘 다 <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> 속성입니다. `ReadOnly`

### <a name="default-values"></a>기본값

nullable 값 형식을 사용 하 고 <xref:System.Nullable%601.HasValue%2A> 변수를 선언 하는 `False`경우 해당 속성의 기본값입니다. 즉, 기본적으로 변수는 기본 값 형식의 기본값 대신 정의된 값이 없습니다. 다음 예제에서 `numberOfChildren` `Integer` 변수는 처음에는 형식의 기본값이 0이더라도 정의된 값이 없습니다.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

null 값은 정의되지 않거나 알 수 없는 값을 나타내는 데 유용합니다. 로 선언된 경우 `numberOfChildren` 현재 정보를 사용할 수 없음을 나타낼 수 있는 값이 없습니다. `Integer`

### <a name="storing-values"></a>값 저장

일반적인 방법으로 nullable 값 형식의 변수 또는 속성에 값을 저장 합니다. 다음 예제에서는 이전 예제에서 `numberOfChildren` 선언된 변수에 값을 할당합니다.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

nullable 값 형식의 변수 또는 속성에 정의된 값이 포함된 경우 값이 할당되지 않은 초기 상태로 되돌릴 수 있습니다. 다음 예제와 같이 변수 또는 `Nothing`속성을 로 설정하여 이 작업을 수행합니다.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> nullable 값 `Nothing` 형식의 변수에 할당할 수 있지만 등기호를 `Nothing` 사용하여 테스트할 수는 없습니다. 와 같은 기호를 `someVar = Nothing`사용하는 비교는 `Nothing`항상 을 평가합니다. 에 <xref:System.Nullable%601.HasValue%2A> 대한 `False`변수의 속성을 테스트하거나 `Is` 또는 `IsNot` 연산자를 사용하여 테스트할 수 있습니다.

### <a name="retrieving-values"></a>값 검색

nullable 값 형식의 변수 값을 검색하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 테스트하여 값이 있는지 확인해야 합니다. 때 값을 <xref:System.Nullable%601.HasValue%2A> 읽으려고 하면 `False`Visual Basic예외가 <xref:System.InvalidOperationException> 발생합니다. 다음 예제에서는 이전 예제의 변수를 `numberOfChildren` 읽는 권장된 방법을 보여 주어 있습니다.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Null 형식 비교

nullable `Boolean` 변수가 부울 식에서 사용되는 경우 결과는 `True` `False`" `Nothing`또는 . 다음은 에 대한 `And` 진실 `Or`테이블입니다. 이제 세 가지 가능한 값이 있기 때문에 `b1` 평가할 9개의 조합이 있습니다. `b2`

|b1|B2|b1 및 b2|b1 또는 b2|
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

부울 변수 또는 식의 값이 `Nothing`있는 경우 `true` `false`는 아래 예제를 고려해 보세요.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

이 예제에서는 `b1 And b2` 을 `Nothing`평가합니다. 결과적으로 절은 `Else` 각 `If` 명령문에서 실행되고 출력은 다음과 같습니다.

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso`단락 `OrElse`평가를 사용하는 경우 첫 번째 로 평가할 때 두 번째 `Nothing`이연산생을 평가해야 합니다.

## <a name="propagation"></a>전파

산술, 비교, 시프트 또는 형식 작업의 피연산자 중 하나 또는 둘 다가 nullable 값 형식인 경우 작업의 결과는 nullable 값 형식이기도 합니다. 두 피연산자 모두 값이 `Nothing`없는 경우, 두 피연산자는 모두 nullable 값 형식이 아닌 것처럼 피연산자의 기본 값에서 작업이 수행됩니다. 다음 예제에서는 `compare1` 변수와 `sum1` 암시적으로 입력됩니다. 마우스 포인터를 놓으면 컴파일러가 두 포인터 모두에 대해 null able 값 형식을 유추하는 것을 볼 수 있습니다.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

하나 또는 둘 다의 값이 있는 `Nothing`경우 은. `Nothing`

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>데이터와 함께 Nullable 형식 사용

데이터베이스는 nullable 값 형식을 사용하는 가장 중요한 장소 중 하나입니다. 현재 모든 데이터베이스 개체가 nullable 값 형식을 지원하지는 않지만 디자이너가 생성한 테이블 어댑터는 사용할 수 있습니다. [nullable 형식에 대한 TableAdapter 지원을](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)참조하십시오.

## <a name="see-also"></a>참조

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [데이터 유형](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [TableAdapters를 사용하여 데이터 세트 채우기](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [If 연산자](../../../language-reference/operators/if-operator.md)
- [지역 형식 유추](../variables/local-type-inference.md)
- [Is 연산자](../../../language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../language-reference/operators/isnot-operator.md)
- [무효화 가능한 값 유형(C#)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
