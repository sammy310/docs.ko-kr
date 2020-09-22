---
title: Group Join 절
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
ms.openlocfilehash: 8d5f3ec80cb39825a3a283907d614b9be28e6e91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869904"
---
# <a name="group-join-clause-visual-basic"></a>Group Join 절 (Visual Basic)

두 컬렉션을 단일 계층 구조 컬렉션으로 결합합니다. 조인 작업은 일치 하는 키를 기반으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`element`|필수 요소. 조인 되는 컬렉션에 대 한 제어 변수입니다.|  
|`type`|선택 사항입니다. `element`의 형식입니다. 을 지정 하지 않으면 `type` 의 형식이 `element` 에서 유추 됩니다 `collection` .|  
|`collection`|필수 사항입니다. 연산자의 좌 변에 있는 컬렉션과 결합할 컬렉션입니다 `Group Join` . 절은 `Group Join` `Join` 절 이나 다른 절에 중첩 될 수 있습니다 `Group Join` .|  
|`key1` `Equals` `key2`|필수 사항입니다. 조인 되는 컬렉션의 키를 식별 합니다. `Equals`조인 되는 컬렉션의 키를 비교 하려면 연산자를 사용 해야 합니다. 연산자를 사용 하 여 `And` 여러 키를 식별 하 여 조인 조건을 결합할 수 있습니다. `key1`매개 변수는 연산자의 좌 변에 있는 컬렉션에서 가져와야 합니다 `Join` . `key2`매개 변수는 연산자의 우변에 있는 컬렉션에서 가져와야 합니다 `Join` .<br /><br /> 조인 조건에 사용 되는 키는 컬렉션에서 두 개 이상의 항목을 포함 하는 식일 수 있습니다. 그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.|  
|`expressionList`|필수 사항입니다. 컬렉션의 요소 그룹을 집계 하는 방법을 식별 하는 하나 이상의 식입니다. 그룹화 된 결과의 멤버 이름을 식별 하려면 `Group` 키워드 ()를 사용 `<alias> = Group` 합니다. 그룹에 적용할 집계 함수를 포함할 수도 있습니다.|  
  
## <a name="remarks"></a>설명  

 `Group Join`절은 조인 중인 컬렉션에서 일치 하는 키 값을 기준으로 두 개의 컬렉션을 결합 합니다. 결과 컬렉션에는 첫 번째 컬렉션의 키 값과 일치 하는 두 번째 컬렉션의 요소 컬렉션을 참조 하는 멤버가 포함 될 수 있습니다. 또한 두 번째 컬렉션에서 그룹화 된 요소에 적용할 집계 함수를 지정할 수 있습니다. 집계 함수에 대 한 자세한 내용은 [Aggregate 절](aggregate-clause.md)을 참조 하십시오.  
  
 예를 들어 관리자 컬렉션 및 직원 컬렉션을 고려 합니다. 두 컬렉션의 요소에는 특정 관리자에 게 보고 하는 직원을 식별 하는 ManagerID 속성이 있습니다. 조인 작업의 결과에는 일치 하는 ManagerID 값이 있는 각 관리자 및 직원의 결과가 포함 됩니다. 작업 결과에는 `Group Join` 관리자의 전체 목록이 포함 됩니다. 각 관리자 결과에는 특정 관리자와 일치 하는 직원 목록을 참조 하는 멤버가 있습니다.  
  
 작업으로 인해 발생 하는 컬렉션에는 절의 절에서 식별 된 `Group Join` 컬렉션의 값 조합 `From` 및 절의 절에서 식별 된 식이 포함 될 수 있습니다 `Into` `Group Join` . 절의 유효한 식에 대 한 자세한 내용은 `Into` [Aggregate 절](aggregate-clause.md)을 참조 하십시오.  
  
 `Group Join`작업은 연산자의 좌 변에 식별 된 컬렉션의 모든 결과를 반환 합니다 `Group Join` . 조인 되는 컬렉션에 일치 하는 항목이 없는 경우에도 마찬가지입니다. 이는 `LEFT OUTER JOIN` SQL의와 비슷합니다.  
  
 절을 사용 `Join` 하 여 컬렉션을 단일 컬렉션으로 결합할 수 있습니다. 이는 `INNER JOIN` SQL의와 동일 합니다.  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 절을 사용 하 여 두 컬렉션을 조인 합니다 `Group Join` .  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Join 절](join-clause.md)
- [Where 절](where-clause.md)
- [Group By 절](group-by-clause.md)
