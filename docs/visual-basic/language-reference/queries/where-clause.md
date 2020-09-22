---
title: Where 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 3a43554fb25592bf413525a2df109010e4868492
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869635"
---
# <a name="where-clause-visual-basic"></a>Where 절 (Visual Basic)

쿼리의 필터링 조건을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>부분  

 `condition`  
 필수 사항입니다. 컬렉션의 현재 항목에 대 한 값이 출력 컬렉션에 포함 되는지 여부를 결정 하는 식입니다. 식은 값 또는 값에 해당 하는 값으로 계산 되어야 합니다 `Boolean` `Boolean` . 조건이로 평가 되 면 `True` 요소가 쿼리 결과에 포함 되 고, 그렇지 않으면 요소가 쿼리 결과에서 제외 됩니다.  
  
## <a name="remarks"></a>설명  

 `Where`절을 사용 하면 특정 조건을 충족 하는 요소만 선택 하 여 쿼리 데이터를 필터링 할 수 있습니다. 해당 값이 절을 `Where` 평가 하도록 하는 요소 `True` 는 쿼리 결과에 포함 되 고 다른 요소는 제외 됩니다. 절에 사용 되는 식은 `Where` `Boolean` `Boolean` 값이 0 인 경우로 계산 되는 정수와 같이 또는에 해당 하는로 계산 되어야 합니다 `False` . ,,,, `Where` 및와 같은 논리 연산자를 사용 하 여 절에서 여러 식을 조합할 수 있습니다 `And` `Or` `AndAlso` `OrElse` `Is` `IsNot` .  
  
 기본적으로 쿼리 식은 액세스할 때까지 계산 되지 않습니다. 예를 들어, 데이터 바인딩된 경우 나 루프에서 반복 될 때 쿼리 식은 계산 되지 않습니다 `For` . 따라서 절은 쿼리를 `Where` 액세스할 때까지 평가 되지 않습니다. 절에 사용 되는 쿼리 외부 값이 있는 경우 `Where` 쿼리 실행 시 절에서 적절 한 값이 사용 되는지 확인 `Where` 합니다. 쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.  
  
 절 내에서 함수를 호출 `Where` 하 여 컬렉션의 현재 요소에서 값에 대 한 계산 또는 연산을 수행할 수 있습니다. 절에서 함수를 호출 하면 `Where` 쿼리가 액세스 될 때 대신 정의 될 때 쿼리를 즉시 실행할 수 있습니다. 쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 쿼리 식에서는 절을 사용 하 여 `From` `cust` 컬렉션의 각 개체에 대해 범위 변수를 선언 합니다 `Customer` `customers` . `Where`절은 범위 변수를 사용 하 여 지정 된 지역의 고객에 대 한 출력을 제한 합니다. `For Each`루프는 쿼리 결과에 있는 각 고객의 회사 이름을 표시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>예제  

 다음 예에서는 `And` `Or` 절에서 및 논리 연산자를 사용 합니다 `Where` .  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [From 절](from-clause.md)
- [Select 절](select-clause.md)
- [For Each...Next 문](../statements/for-each-next-statement.md)
