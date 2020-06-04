---
title: Join 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359776"
---
# <a name="join-clause-visual-basic"></a>Join 절 (Visual Basic)

두 컬렉션을 단일 컬렉션으로 결합합니다. 조인 작업은 일치 하는 키를 기반으로 하며 연산자를 사용 합니다 `Equals` .

## <a name="syntax"></a>구문

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>부분

`element` 필수입니다. 조인 되는 컬렉션에 대 한 제어 변수입니다.

`collection`  
필수 요소. 연산자의 좌 변에 있는 컬렉션과 결합할 컬렉션 `Join` 입니다. `Join`절은 다른 `Join` 절 또는 절에 중첩 될 수 있습니다 `Group Join` .

`joinClause`  
선택 사항입니다. `Join`쿼리를 추가로 구체화 하는 하나 이상의 추가 절입니다.

`groupJoinClause`  
선택 사항입니다. `Group Join`쿼리를 추가로 구체화 하는 하나 이상의 추가 절입니다.

`key1` `Equals` `key2`  
필수 요소. 조인 되는 컬렉션의 키를 식별 합니다. `Equals`조인 되는 컬렉션의 키를 비교 하려면 연산자를 사용 해야 합니다. 연산자를 사용 하 여 `And` 여러 키를 식별 하 여 조인 조건을 결합할 수 있습니다. `key1`연산자의 좌 변에 있는 컬렉션에서 가져와야 합니다 `Join` . `key2`연산자의 우변에 있는 컬렉션에서 가져와야 합니다 `Join` .

조인 조건에 사용 되는 키는 컬렉션에서 두 개 이상의 항목을 포함 하는 식일 수 있습니다. 그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.

## <a name="remarks"></a>설명

`Join`절은 조인 중인 컬렉션에서 일치 하는 키 값을 기준으로 두 개의 컬렉션을 결합 합니다. 결과 컬렉션에는 연산자의 왼쪽에서 식별 된 컬렉션의 모든 값 조합 `Join` 및 절에서 식별 된 컬렉션이 포함 될 수 있습니다 `Join` . 이 쿼리는 연산자에 의해 지정 된 조건이 충족 되는 결과만 반환 합니다 `Equals` . 이는 `INNER JOIN` SQL의와 동일 합니다.

`Join`쿼리에서 여러 절을 사용 하 여 둘 이상의 컬렉션을 단일 컬렉션으로 조인할 수 있습니다.

절이 없으면 암시적 조인을 수행 하 여 컬렉션을 결합할 수 있습니다 `Join` . 이렇게 하려면 `In` 절에 여러 절을 포함 하 `From` 고 `Where` 조인에 사용할 키를 식별 하는 절을 지정 합니다.

절을 사용 `Group Join` 하 여 컬렉션을 단일 계층 구조 컬렉션으로 결합할 수 있습니다. 이는 `LEFT OUTER JOIN` SQL의와 비슷합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 암시적 조인을 수행 하 여 고객 목록을 주문과 결합 합니다.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>예제

다음 코드 예제에서는 절을 사용 하 여 두 컬렉션을 조인 합니다 `Join` .

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

이 예제는 다음과 유사한 출력을 생성 합니다.

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>예제

다음 코드 예제에서는 `Join` 두 개의 키 열이 있는 절을 사용 하 여 두 컬렉션을 조인 합니다.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

예제는 다음과 유사한 출력을 생성 합니다.

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Group Join 절](group-join-clause.md)
- [Where 절](where-clause.md)
