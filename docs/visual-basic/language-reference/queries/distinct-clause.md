---
title: Distinct 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 5aecffbce036500d294d03a925798d51f1269af6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401396"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 절 (Visual Basic)
후속 쿼리 절에서 중복 값을 제거 하도록 현재 범위 변수의 값을 제한 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>설명  
 절을 사용 `Distinct` 하 여 고유한 항목의 목록을 반환할 수 있습니다. `Distinct`절이 있으면 쿼리에서 중복 쿼리 결과가 무시 됩니다. 절은 `Distinct` 절에 지정 된 모든 반환 필드의 중복 값에 적용 됩니다 `Select` . `Select`절이 지정 되지 않은 경우 절 `Distinct` 에서 식별 된 쿼리의 범위 변수에 절이 적용 됩니다 `From` . 범위 변수가 변경할 수 없는 형식이 아닌 경우에는 해당 형식의 모든 멤버가 기존 쿼리 결과와 일치 하는 경우에만 쿼리 결과가 무시 됩니다.  
  
## <a name="example"></a>예제  
 다음 쿼리 식은 고객 목록과 고객 주문 목록을 조인 합니다. `Distinct`고유한 고객 이름 및 주문 날짜 목록을 반환 하는 절이 포함 되어 있습니다.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [From 절](from-clause.md)
- [Select 절](select-clause.md)
- [Where 절](where-clause.md)
