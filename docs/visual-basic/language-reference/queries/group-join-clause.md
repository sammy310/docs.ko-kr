---
title: Group Join 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 3da4ca2db299a65b2c0f1fa259bbaabe4f53aa33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945316"
---
# <a name="group-join-clause-visual-basic"></a>Group Join 절(Visual Basic)
두 컬렉션을 단일 계층 구조 컬렉션으로 결합합니다. 조인 작업은 키를 일치 하는 기준으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`element`|필수 요소. 조인 중인 컬렉션에 대 한 제어 변수입니다.|  
|`type`|선택 사항입니다. `element`의 형식입니다. 없으면 `type` 지정 된 형식의 `element` 에서 유추 됩니다 `collection`합니다.|  
|`collection`|필수 요소. 왼쪽에 있는 컬렉션과 결합할 컬렉션을 `Group Join` 연산자입니다. A `Group Join` 절에 중첩 될 수는 `Join` 절 또는 다른 `Group Join` 절.|  
|`key1` `Equals` `key2`|필수 요소. 조인 중인 컬렉션에 대 한 키를 식별 합니다. 사용 해야는 `Equals` 조인 중인 컬렉션에서 키를 비교 하는 연산자입니다. 조인 조건을 사용 하 여 결합할 수 있습니다는 `And` 여러 키를 식별 하는 연산자입니다. `key1` 의 왼쪽에 있는 컬렉션에서 매개 변수 여야 합니다 `Join` 연산자. `key2` 의 오른쪽에 있는 컬렉션에서 매개 변수 여야 합니다 `Join` 연산자.<br /><br /> 조인 조건에 사용 되는 키 컬렉션에서 둘 이상의 항목을 포함 하는 식을 수 있습니다. 그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.|  
|`expressionList`|필수 요소. 컬렉션에서 요소 그룹 집계 되는 방법을 식별 하는 하나 이상의 식입니다. 그룹화 된 결과의 멤버 이름을 식별 하려면 사용 합니다 `Group` 키워드 (`<alias> = Group`). 그룹에 적용할 집계 함수를 포함할 수도 있습니다.|  
  
## <a name="remarks"></a>설명  
 `Group Join` 절 조인 중인 컬렉션에서 키 값을 일치를 기준으로 하는 두 개의 컬렉션을 결합 합니다. 결과 컬렉션을 첫 번째 컬렉션에서 키 값과 일치 하는 두 번째 컬렉션에서 요소의 컬렉션을 참조 하는 멤버를 포함할 수 있습니다. 또한 두 번째 컬렉션에서 그룹화 된 요소에 적용할 집계 함수를 지정할 수 있습니다. 집계 함수에 대 한 자세한 내용은 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.  
  
 예를 들어, 관리자의 컬렉션 및 컬렉션 직원을 고려해 야 합니다. 두 컬렉션의 요소를 특정 관리자에 게 보고 하는 직원을 식별 하는 ManagerID 속성을 가집니다. 조인 연산의 결과는 각 관리자와 일치 하는 ManagerID 값을 사용 하 여 직원에 대 한 결과 포함 됩니다. 결과 `Group Join` 작업 관리자의 전체 목록을 포함 됩니다. 각 관리자 결과 멤버는 특정 관리자와 일치 하는 직원의 목록을 참조 하는 것입니다.  
  
 결과 컬렉션을 `Group Join` 작업에서 식별 된 컬렉션에서 값의 조합을 포함할 수 있습니다는 `From` 절 및 식에서 식별 된를 `Into` 절을 `Group Join` 절. 에 대 한 올바른 식에 대 한 자세한 내용은 합니다 `Into` 절을 참조 하세요 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 A `Group Join` 작업은 왼쪽에서 식별 된 컬렉션에서 모든 결과 반환 합니다 `Group Join` 연산자입니다. 일치 하는 조인 중인 컬렉션에 없는 경우에 마찬가지입니다. 비슷합니다는 `LEFT OUTER JOIN` sql에서입니다.  
  
 사용할 수는 `Join` 절을 단일 컬렉션으로 결합할 수 있습니다. 이 해당 하는 `INNER JOIN` sql에서입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 사용 하 여 두 컬렉션 조인 된 `Group Join` 절.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>참고자료

- [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](../../../visual-basic/language-reference/queries/index.md)
- [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
- [Join 절](../../../visual-basic/language-reference/queries/join-clause.md)
- [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By 절](../../../visual-basic/language-reference/queries/group-by-clause.md)
