---
description: '다음에 대 한 자세한 정보: 수량자 작업 (Visual Basic)'
title: 수량자 작업
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 7cbd8a9cf18a0ad8b70ada58d7fa6602dce4bd1b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430094"
---
# <a name="quantifier-operations-visual-basic"></a>수량자 작업 (Visual Basic)

수량자 작업은 시퀀스에서 조건을 충족하는 요소가 일부인지 전체인지를 나타내는 <xref:System.Boolean> 값을 반환합니다.  
  
 다음 그림은 두 개의 서로 다른 소스 시퀀스에 대한 두 개의 서로 다른 수량자 작업을 보여 줍니다. 첫 번째 작업은 요소 중 하나 이상이 문자 'A'이고 결과가 `true`인지 묻습니다. 두 번째 작업은 모든 요소가 문자 'A'이고 결과가 `true`인지 묻습니다.  
  
 ![LINQ 수량자 작업](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 다음 섹션에는 수량자 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|모두|시퀀스의 모든 요소가 조건을 만족하는지를 확인합니다.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|임의의 값|시퀀스의 임의의 요소가 조건을 만족하는지를 확인합니다.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|포함|시퀀스에 지정된 요소가 들어 있는지를 확인합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  

 이러한 예제에서는 `Aggregate` LINQ 쿼리에서 필터링 조건의 일부로 Visual Basic의 절을 사용 합니다.  
  
 다음 예제에서는 `Aggregate` 절과 확장 메서드를 사용 하 여 <xref:System.Linq.Enumerable.All%2A> 애완 동물 모두가 지정 된 기간 보다 오래 된 사용자를 컬렉션에서 반환 합니다.  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 다음 예제에서는 `Aggregate` 절과 확장 메서드를 사용 하 여 <xref:System.Linq.Enumerable.Any%2A> 지정 된 기간 보다 오래 된 pet가 하나 이상 있는 사용자를 컬렉션에서 반환 합니다.  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [방법: 지정된 단어 집합이 들어 있는 문장 쿼리(LINQ)(Visual Basic)](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
