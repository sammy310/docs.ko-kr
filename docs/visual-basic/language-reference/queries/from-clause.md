---
title: From 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 120ba6da11bffc3a0e81873d1fd606633724723d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875251"
---
# <a name="from-clause-visual-basic"></a>From 절 (Visual Basic)

하나 이상의 범위 변수와 쿼리할 컬렉션을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`element`|필수 요소. 컬렉션의 요소를 반복 하는 데 사용 되는 *범위 변수* 입니다. 범위 변수는 `collection` 쿼리를 통해가 반복 될 때의 각 멤버를 참조 하는 데 사용 됩니다 `collection` . 는 열거 가능한 형식 이어야 합니다.|  
|`type`|선택 사항입니다. `element`의 형식입니다. 을 지정 하지 않으면 `type` 의 형식이 `element` 에서 유추 됩니다 `collection` .|  
|`collection`|필수 사항입니다. 쿼리할 컬렉션을 참조 합니다. 는 열거 가능한 형식 이어야 합니다.|  
  
## <a name="remarks"></a>설명  

 `From`절은 쿼리의 소스 데이터와 소스 컬렉션의 요소를 참조 하는 데 사용 되는 변수를 식별 하는 데 사용 됩니다. 이러한 변수를 *범위 변수*라고 합니다. 절 `From` `Aggregate` 이 집계 된 결과만 반환 하는 쿼리를 식별 하는 데 사용 되는 경우를 제외 하 고는 쿼리에 필요 합니다. 자세한 내용은 [Aggregate 절](aggregate-clause.md)을 참조 하세요.  
  
 쿼리에 여러 절을 지정 `From` 하 여 조인할 여러 컬렉션을 식별할 수 있습니다. 여러 컬렉션을 지정 하는 경우 이러한 컬렉션은 독립적으로 반복 되거나 관련 된 경우 조인할 수 있습니다. `Select`절을 사용 하거나 또는 절을 사용 하 여 명시적으로 컬렉션을 조인할 수 있습니다 `Join` `Group Join` . 또는 여러 범위 변수와 컬렉션을 단일 절에 지정할 수 있으며 `From` , 각 관련 범위 변수와 컬렉션은 쉼표로 구분 됩니다. 다음 코드 예에서는 절의 구문 옵션을 모두 보여 줍니다 `From` .  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 `From`절은 루프의 범위와 비슷한 쿼리의 범위를 정의 합니다 `For` . 따라서 `element` 쿼리 범위의 각 범위 변수에는 고유한 이름이 있어야 합니다. 쿼리에 대해 절을 여러 개 지정할 수 있으므로 `From` 후속 `From` 절은 절의 범위 변수를 참조 `From` 하거나 이전 절의 범위 변수를 참조할 수 있습니다 `From` . 예를 들어 다음 예에서는 `From` 두 번째 절의 컬렉션이 첫 번째 절에 있는 범위 변수의 속성을 기반으로 하는 중첩 절을 보여 줍니다.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 각 `From` 절 뒤에는 쿼리를 구체화 하기 위한 추가 쿼리 절의 조합이 올 수 있습니다. 다음과 같은 방법으로 쿼리를 구체화할 수 있습니다.  
  
- 또는 절을 사용 하 여 명시적으로 또는 절을 사용 하 여 여러 컬렉션을 암시적으로 결합 `From` `Select` `Join` `Group Join` 합니다.  
  
- 절을 사용 `Where` 하 여 쿼리 결과를 필터링 합니다.  
  
- 절을 사용 하 여 결과를 정렬 합니다 `Order By` .  
  
- 절을 사용 하 여 비슷한 결과를 함께 그룹화 `Group By` 합니다.  
  
- `Aggregate`전체 쿼리 결과를 평가 하는 집계 함수를 식별 하려면 절을 사용 합니다.  
  
- 절을 사용 `Let` 하 여 해당 값이 컬렉션이 아닌 식에 의해 결정 되는 반복 변수를 도입 합니다.  
  
- 절을 사용 `Distinct` 하 여 중복 쿼리 결과를 무시 합니다.  
  
- ,, 및 절을 사용 하 여 반환할 결과의 일부를 식별 `Skip` `Take` `Skip While` `Take While` 합니다.  
  
## <a name="example"></a>예제  

 다음 쿼리 식에서는 절을 사용 하 여 `From` `cust` 컬렉션의 각 개체에 대해 범위 변수를 선언 합니다 `Customer` `customers` . `Where`절은 범위 변수를 사용 하 여 지정 된 지역의 고객에 대 한 출력을 제한 합니다. `For Each`루프는 쿼리 결과에 있는 각 고객의 회사 이름을 표시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>참조

- [쿼리](index.md)
- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [For Each...Next 문](../statements/for-each-next-statement.md)
- [For...Next 문](../statements/for-next-statement.md)
- [Select 절](select-clause.md)
- [Where 절](where-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Distinct 절](distinct-clause.md)
- [Join 절](join-clause.md)
- [Group Join 절](group-join-clause.md)
- [Order By 절](order-by-clause.md)
- [Let 절](let-clause.md)
- [Skip 절](skip-clause.md)
- [Take 절](take-clause.md)
- [Skip While 절](skip-while-clause.md)
- [Take While 절](take-while-clause.md)
