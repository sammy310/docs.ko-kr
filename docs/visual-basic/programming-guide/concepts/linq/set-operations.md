---
description: '자세한 정보: Set 작업 (Visual Basic)'
title: 집합 작업
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: 9c75c9e029ba260917f59c7d2ea0341c157bf406
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471671"
---
# <a name="set-operations-visual-basic"></a>Set 작업 (Visual Basic)

LINQ의 집합 작업은 동일 컬렉션이나 별개 컬렉션(또는 집합)에 동등한 요소가 있는지 여부에 따라 결과 집합을 생성하는 쿼리 작업을 가리킵니다.

다음 섹션에는 집합 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.

## <a name="methods"></a>메서드

|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|
|-----------------|-----------------|------------------------------------------|----------------------|
|Distinct|컬렉션에서 중복 값을 제거합니다.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|Except|두 번째 컬렉션에 표시되지 않는 한 컬렉션의 요소를 의미하는 차집합을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|Intersect|두 컬렉션에 각각 표시되는 요소를 의미하는 교집합을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|Union|두 컬렉션 중 하나에 표시되는 고유한 요소를 의미하는 합집합을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a>집합 작업 비교

### <a name="distinct"></a>Distinct

다음 그림에서는 문자 시퀀스에 대한 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 메서드의 동작을 보여 줍니다. 반환된 시퀀스에는 입력 시퀀스의 고유한 요소가 포함됩니다.

![Distinct()의 동작을 보여주는 그래픽](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a>Except

다음 그림에서는 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>의 동작을 보여 줍니다. 반환된 시퀀스에는 두 번째 입력 시퀀스에 없는 첫 번째 입력 시퀀스의 요소만 포함됩니다.

![Except&#40;&#41;의 동작을 보여 주는 그래픽.](./media/set-operations/except-behavior-graphic.png "Except의 동작을 보여 줍니다.")

### <a name="intersect"></a>Intersect

다음 그림에서는 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>의 동작을 보여 줍니다. 반환된 시퀀스에는 입력 시퀀스 둘 다에 공통적으로 있는 요소가 포함됩니다.

![두 시퀀스의 교집합을 보여주는 그래픽](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a>Union

다음 그림은 두 개의 문자 시퀀스에 대한 합집합을 보여 줍니다. 반환된 시퀀스에는 두 입력 시퀀스의 고유한 요소가 모두 포함됩니다.

![두 시퀀스의 결합을 보여주는 그래픽](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a>쿼리 식 구문 예제

다음 예제에서는 LINQ 쿼리에 절을 사용 하 여 `Distinct` 정수 목록에서 고유 번호를 반환 합니다.

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a>추가 정보

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [Distinct 절](../../../language-reference/queries/distinct-clause.md)
- [방법: 문자열 컬렉션 결합 및 비교 (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)
- [방법: 두 목록 간의 차집합을 설정 찾기 (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)
