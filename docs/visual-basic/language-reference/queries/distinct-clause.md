---
title: Distinct 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830060"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 절(Visual Basic)
후속 쿼리 절에 중복 값을 제거 하려면 현재 범위 변수 값을 제한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>설명  
 사용할 수는 `Distinct` 절 고유 항목의 목록을 반환 합니다. `Distinct` 절로 인해 쿼리는 중복 되는 쿼리 결과 무시 하도록 합니다. `Distinct` 절에서 지정 된 필드를 반환 하는 모든 중복 값에 적용 된 `Select` 절. 없으면 `Select` 절을 지정 합니다 `Distinct` 절에서 식별 된 쿼리에 대 한 범위 변수에 적용 되는 `From` 절. 범위 변수는 변경할 수 없는 형식이 없는 경우 형식의 모든 멤버는 기존 쿼리 결과 일치 하는 경우 쿼리는 쿼리 결과 무시만 합니다.  
  
## <a name="example"></a>예제  
 다음 쿼리 식은 고객 주문 목록과 고객 목록에 조인합니다. `Distinct` 절이 고유한 고객 이름 목록을 반환 하 고 주문 날짜를 포함 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>참고자료

- [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](../../../visual-basic/language-reference/queries/index.md)
- [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
