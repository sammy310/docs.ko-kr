---
title: Skip 절
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 40e89160baf663f7d6785e5d3e09ad6cc4eefbde
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866309"
---
# <a name="skip-clause-visual-basic"></a>Skip 절 (Visual Basic)

컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>부분  

 `count`  
 필수 사항입니다. 건너뛸 시퀀스의 요소 수로 계산 되는 값 또는 식입니다.  
  
## <a name="remarks"></a>설명  

 절을 사용 `Skip` 하면 쿼리가 결과 목록의 시작 부분에 있는 요소를 무시 하 고 나머지 요소를 반환 합니다. 건너뛸 요소의 수는 `count` 매개 변수로 식별 됩니다.  
  
 절 `Skip` 과 함께 절을 사용 `Take` 하 여 쿼리 세그먼트의 데이터 범위를 반환할 수 있습니다. 이렇게 하려면 범위의 첫 번째 요소 인덱스를 절에 전달 하 `Skip` 고 범위의 크기를 절에 전달 `Take` 합니다.  
  
 쿼리에서 절을 사용 하는 경우 절에서 의도 한 결과를 무시 하도록 하는 `Skip` 순서로 결과가 반환 되는지 확인 해야 할 수도 있습니다 `Skip` . 쿼리 결과를 정렬 하는 방법에 대 한 자세한 내용은 [Order By 절](order-by-clause.md)을 참조 하십시오.  
  
 `SkipWhile`제공 된 조건에 따라 특정 요소만 무시 되도록 지정 하려면 절을 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 코드 예에서는 절과 함께 절을 사용 하 여 `Skip` `Take` 페이지의 쿼리에서 데이터를 반환 합니다. 함수는 절을 사용 하 여 `GetCustomers` `Skip` 제공 된 시작 인덱스 값까지 목록의 고객을 우회 하 고 절을 사용 하 여 `Take` 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Order By 절](order-by-clause.md)
- [Skip While 절](skip-while-clause.md)
- [Take 절](take-clause.md)
