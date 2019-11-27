---
title: 표준 쿼리 연산자의 쿼리 식 구문
ms.date: 07/20/2015
ms.assetid: eb978d86-d3b5-497b-95ce-a054bea8f510
ms.openlocfilehash: f0c8438c8d092cbf4f1cdb8e3adba7bd9d939c32
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346547"
---
# <a name="query-expression-syntax-for-standard-query-operators-visual-basic"></a>표준 쿼리 연산자 (Visual Basic)에 대 한 쿼리 식 구문
자주 사용 되는 표준 쿼리 연산자 중 일부에는 *쿼리 식*의 일부로 호출할 수 있는 전용 Visual Basic 언어 키워드 구문이 있습니다. 쿼리 식은 *메서드 기반* 양식과는 다른, 가독성이 더 우수한 쿼리 표현 양식입니다. 쿼리 식 절은 컴파일 시간에 쿼리 메서드 호출로 변환됩니다.  
  
## <a name="query-expression-syntax-table"></a>쿼리 식 구문 표  
 다음 표에는 동등한 쿼리 식 절이 있는 표준 쿼리 연산자가 나열되어 있습니다.  
  
|메서드|Visual Basic 쿼리 식 구문|  
|------------|------------------------------------------|  
|<xref:System.Linq.Enumerable.All%2A>|`Aggregate … In … Into All(…)`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Any%2A>|`Aggregate … In … Into Any()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Average%2A>|`Aggregate … In … Into Average()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Cast%2A>|`From … As …`<br /><br /> 자세한 내용은 [From 절](../../../../visual-basic/language-reference/queries/from-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Count%2A>|`Aggregate … In … Into Count()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|`Distinct`<br /><br /> 자세한 내용은 [Distinct 절](../../../../visual-basic/language-reference/queries/distinct-clause.md)을 참조 하십시오.|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`Group … By … Into …`<br /><br /> 자세한 내용은 [Group By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)을 참조 하십시오.|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`Group Join … In … On …`<br /><br /> 자세한 내용은 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`From x In …, y In … Where x.a = b.a`<br /><br /> -또는-<br /><br /> `Join … [As …]In … On …`<br /><br /> 자세한 내용은 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.LongCount%2A>|`Aggregate … In … Into LongCount()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Max%2A>|`Aggregate … In … Into Max()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Min%2A>|`Aggregate … In … Into Min()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By`<br /><br /> 자세한 내용은 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By … Descending`<br /><br /> 자세한 내용은 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Select%2A>|`Select`<br /><br /> (자세한 내용은 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)을 참조 하세요.)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|여러 `From` 절<br /><br /> 자세한 내용은 [From 절](../../../../visual-basic/language-reference/queries/from-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Skip%2A>|`Skip`<br /><br /> 자세한 내용은 [Skip 절](../../../../visual-basic/language-reference/queries/skip-clause.md)을 참조 하십시오.|  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|`Skip While`<br /><br /> 자세한 내용은 [Skip While 절](../../../../visual-basic/language-reference/queries/skip-while-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Sum%2A>|`Aggregate … In … Into Sum()`<br /><br /> 자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Take%2A>|`Take`<br /><br /> 자세한 내용은 [Take 절](../../../../visual-basic/language-reference/queries/take-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.TakeWhile%2A>|`Take While`<br /><br /> 자세한 내용은 [Take While 절](../../../../visual-basic/language-reference/queries/take-while-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, …`<br /><br /> 자세한 내용은 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, … Descending`<br /><br /> 자세한 내용은 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조 하세요.|  
|<xref:System.Linq.Enumerable.Where%2A>|`Where`<br /><br /> 자세한 내용은 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)을 참조 하세요.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [실행 방식에 따라 표준 쿼리 연산자 분류 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
