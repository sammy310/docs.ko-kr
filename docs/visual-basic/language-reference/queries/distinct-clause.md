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
ms.openlocfilehash: 94471898807ef4552564c3e01465f2b2f6211d0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335369"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 절(Visual Basic)
후속 쿼리 절에서 중복 값을 제거 하도록 현재 범위 변수의 값을 제한 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>주의  
 `Distinct` 절을 사용 하 여 고유한 항목의 목록을 반환할 수 있습니다. `Distinct` 절은 쿼리가 중복 쿼리 결과를 무시 하도록 합니다. `Distinct` 절은 `Select` 절에서 지정한 모든 반환 필드에 대해 중복 값에 적용 됩니다. `Select` 절이 지정 되지 않은 경우 `Distinct` 절은 `From` 절에서 식별 된 쿼리의 범위 변수에 적용 됩니다. 범위 변수가 변경할 수 없는 형식이 아닌 경우에는 해당 형식의 모든 멤버가 기존 쿼리 결과와 일치 하는 경우에만 쿼리 결과가 무시 됩니다.  
  
## <a name="example"></a>예제  
 다음 쿼리 식은 고객 목록과 고객 주문 목록을 조인 합니다. 고유한 고객 이름 및 주문 날짜 목록을 반환 하는 `Distinct` 절이 포함 되어 있습니다.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](../../../visual-basic/language-reference/queries/index.md)
- [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
