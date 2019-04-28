---
title: Aggregate 절(Visual Basic)
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 21781db637c71abbbe9366bc95b6ee4c89ac2246
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712632"
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate 절(Visual Basic)
컬렉션에 하나 이상의 집계 함수를 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`element`|필수 요소. 컬렉션의 요소를 반복 하는 데 사용 하는 변수입니다.|  
|`type`|선택 사항입니다. `element`의 형식입니다. 형식이 지정 되지 않은, 경우 유형의 `element` 에서 유추 됩니다 `collection`합니다.|  
|`collection`|필수 요소. 에 적용할 컬렉션을 의미 합니다.|  
|`clause`|선택 사항입니다. 하나 이상의 절 등 쿼리는 `Where` aggregate 절 또는 절을 적용 하 여 쿼리 결과를 구체화할 절.|  
|`expressionList`|필수 요소. 하나 이상의 쉼표로 구분 된 식 컬렉션에 적용할 집계 함수를 식별 하는입니다. 쿼리 결과에 멤버 이름을 지정 하는 집계 함수에 별칭을 적용할 수 있습니다. 별칭 없음이 제공 하는 경우 집계 함수의 이름 사용 됩니다. 예를 들어이 항목의 뒷부분에 나오는 집계 함수에 대 한 섹션을 참조 합니다.|  
  
## <a name="remarks"></a>설명  
 `Aggregate` 쿼리에서 집계 함수를 포함 하려면 절을 사용할 수 있습니다. 집계 함수는 값의 집합에 대해 검사 및 계산을 수행 하 고 단일 값을 반환 합니다. 쿼리 결과 형식의 멤버를 사용 하 여 계산 된 값에 액세스할 수 있습니다. 사용할 수 있는 표준 집계 함수를 `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, 및 `Sum` 함수입니다. 이러한 함수는 sql에서 집계에 익숙한 개발자에 게 친숙 합니다. 이 항목의 다음 섹션에 설명 되어 있습니다.  
  
 집계 함수의 결과 쿼리 결과 형식의 필드와 쿼리 결과에 포함 됩니다. 집계 값을 포함 하는 쿼리 결과 형식의 멤버의 이름을 지정 하는 집계 함수 결과 대 한 별칭을 제공할 수 있습니다. 별칭 없음이 제공 하는 경우 집계 함수의 이름 사용 됩니다.  
  
 `Aggregate` 절에 쿼리를 시작할 수 또는 추가 쿼리 절과 포함할 수 있습니다. 경우는 `Aggregate` 절에 쿼리 시작 되는 결과에 지정 된 집계 함수의 결과인 단일 값을 `Into` 절. 둘 이상의 집계 함수에 지정 된 경우는 `Into` 절 쿼리 결과의 각 집계 함수를 참조 하는 별도 속성을 사용 하 여 단일 형식을 반환 합니다.는 `Into` 절. 경우는 `Aggregate` 절 추가 쿼리 절과 포함 되는지, 쿼리 컬렉션에서 반환 되는 형식 결과의 각 집계 함수를 참조 하려면 별도 속성은는 `Into` 절.  
  
## <a name="aggregate-functions"></a>집계 함수

다음은 사용할 수 있는 표준 집계 함수는 `Aggregate` 절.  
  
### <a name="all"></a>모두

반환 `true` 컬렉션의 모든 요소가 지정 된 조건을 충족 하는 경우 그렇지 `false`합니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>임의의 값

반환 `true` 컬렉션의 임의 요소가 지정 된 조건을 충족 하는 경우 그렇지 `false`합니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>평균

컬렉션에 있는 모든 요소의 평균을 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>개수

컬렉션의 요소 수를 셉니다. 선택적인 제공할 수 있습니다 `Boolean` 만 조건을 만족 하는 컬렉션의 요소 수를 계산 하는 식입니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>그룹화

참조의 결과로 그룹화 된 쿼리 결과 `Group By` 또는 `Group Join` 절. 합니다 `Group` 함수에만 유효 합니다 `Into` 절을 `Group By` 또는 `Group Join` 절. 자세한 내용 및 예제를 참조 하세요 [그룹 By 절](../../../visual-basic/language-reference/queries/group-by-clause.md) 하 고 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.

### <a name="longcount"></a>LongCount

컬렉션의 요소 수를 셉니다. 선택적인 제공할 수 있습니다 `Boolean` 만 조건을 만족 하는 컬렉션의 요소 수를 계산 하는 식입니다. 결과 `Long`합니다. 예를 들어 참조는 `Count` 집계 함수입니다.

### <a name="max"></a>최대

컬렉션에서 최대값을 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>최소

컬렉션의 최소값을 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

컬렉션에 있는 모든 요소의 합계를 계산 하거나 컬렉션의 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>예제  

다음 예제에서는 사용 하는 방법을 보여 줍니다는 `Aggregate` 절에 집계 함수를 쿼리 결과에 적용 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>사용자 정의 집계 함수 만들기

 에 대 한 확장 메서드를 추가 하 여 쿼리 식에서 사용자 고유의 사용자 지정 집계 함수를 포함할 수 있습니다는 <xref:System.Collections.Generic.IEnumerable%601> 형식입니다. 사용자 지정 메서드가 계산 또는 집계 함수 참조는 열거 가능한 컬렉션에 대 한 작업을 수행할 수 있습니다. 확장 메서드에 대한 자세한 내용은 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하세요.  
  
 예를 들어, 다음 예제에서는 숫자 컬렉션의 중앙값을 계산 하는 사용자 지정 집계 함수를 보여 줍니다. 두 가지 오버 로드의는 `Median` 확장 메서드. 첫 번째 오버 로드를 입력으로 받아들입니다, 형식의 컬렉션인 `IEnumerable(Of Double)`합니다. 경우는 `Median` 유형 쿼리 필드에 대 한 집계 함수가 호출 될 `Double`,이 메서드가 호출 됩니다. 두 번째 오버 로드는 `Median` 메서드는 제네릭 형식 전달 될 수 있습니다. 제네릭 오버 로드를 `Median` 메서드를 참조 하는 두 번째 매개 변수를 사용 합니다 `Func(Of T, Double)` 람다 식 (컬렉션)에서 형식에 대 한 값 형식의 해당 값으로 프로젝션 할 `Double`. 다음의 다른 오버 로드에 중간 값 계산에 위임 된 `Median` 메서드. 람다 식에 대한 자세한 내용은 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 다음 예제에서는 호출 하는 샘플 쿼리를 `Median` 형식의 컬렉션에 대 한 함수 집계 `Integer`, 및 형식의 컬렉션인 `Double`. 호출 하는 쿼리를 `Median` 형식의 컬렉션에 대 한 함수 집계 `Double` 의 오버 로드를 호출 합니다 `Median` 형식의 컬렉션을 입력으로 허용 되는 방법 `Double`합니다. 호출 하는 쿼리를 `Median` 형식의 컬렉션에 대 한 함수 집계 `Integer` 의 제네릭 오버 로드를 호출 합니다 `Median` 메서드.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>참고자료

- [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](../../../visual-basic/language-reference/queries/index.md)
- [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By 절](../../../visual-basic/language-reference/queries/group-by-clause.md)
