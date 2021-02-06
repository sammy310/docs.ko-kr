---
description: '자세한 정보: Take 절 (Visual Basic)'
title: Take 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 6542d262490d9d4acff893b2a99ffb60dd1446a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653539"
---
# <a name="take-clause-visual-basic"></a>Take 절 (Visual Basic)

컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>부분  

 `count`  
 필수 사항입니다. 반환할 시퀀스의 요소 수로 계산 되는 값 또는 식입니다.  
  
## <a name="remarks"></a>설명  

 `Take`절을 실행 하면 결과 목록의 시작 부분에서 지정 된 개수의 연속 요소가 쿼리에 포함 됩니다. 포함할 요소의 수는 `count` 매개 변수로 지정 됩니다.  
  
 절 `Take` 과 함께 절을 사용 `Skip` 하 여 쿼리 세그먼트의 데이터 범위를 반환할 수 있습니다. 이렇게 하려면 범위의 첫 번째 요소 인덱스를 절에 전달 하 `Skip` 고 범위의 크기를 절에 전달 `Take` 합니다. 이 경우 절 뒤에 `Take` 절을 지정 해야 합니다 `Skip` .  
  
 쿼리에서 절을 사용 하는 경우에는 `Take` 절에서 의도 된 결과를 포함 하도록 하는 순서로 결과가 반환 되는지 확인 해야 할 수도 있습니다 `Take` . 쿼리 결과를 정렬 하는 방법에 대 한 자세한 내용은 [Order By 절](order-by-clause.md)을 참조 하십시오.  
  
 절을 사용 하 여 `TakeWhile` 제공 된 조건에 따라 특정 요소만 반환 되도록 지정할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 코드 예에서는 절과 함께 절을 사용 하 여 `Take` `Skip` 페이지의 쿼리에서 데이터를 반환 합니다. GetCustomers 함수는 절을 사용 하 여 `Skip` 목록에서 제공 된 시작 인덱스 값까지 고객을 우회 하 고 절을 사용 하 여 `Take` 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Order By 절](order-by-clause.md)
- [Take While 절](take-while-clause.md)
- [Skip 절](skip-clause.md)
