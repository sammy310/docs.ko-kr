---
title: 집계 작업
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 8e2c9698de67dc4def348a03c9d69713a6130f31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383795"
---
# <a name="aggregation-operations-visual-basic"></a>집계 작업 (Visual Basic)
집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다. 예를 들어 1달 동안의 일일 온도 값에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.  
  
 다음 그림은 숫자 시퀀스에 대한 두 가지 집계 작업의 결과를 보여 줍니다. 첫 번째 작업은 숫자의 합계를 계산합니다. 두 번째 작업은 시퀀스의 최대 값을 반환합니다.  
  
 ![LINQ 집계 작업을 보여주는 그림](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 다음 섹션에는 집계 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Aggregate|컬렉션 값에 대해 사용자 지정 집계 작업을 수행합니다.|적용할 수 없음|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|평균|값 컬렉션의 평균 값을 계산합니다.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|개수|컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|큰 컬렉션에서 요소(선택적으로 조건자 함수를 충족하는 요소만) 개수를 계산합니다.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|최대값|컬렉션의 최대값을 확인합니다.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|최소값|컬렉션의 최소값을 확인합니다.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|합계|컬렉션에 있는 값의 합계를 계산합니다.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="average"></a>평균  
 다음 코드 예제에서는 Visual Basic의 절을 사용 하 여 `Aggregate Into Average` 온도를 나타내는 숫자 배열의 평균 온도를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>개수  
 다음 코드 예제에서는 `Aggregate Into Count` Visual Basic 절을 사용 하 여 배열에서 80 보다 크거나 같은 값의 수를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  
 다음 코드 예제에서는 절을 사용 `Aggregate Into LongCount` 하 여 배열에 있는 값의 개수를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>최대값  
 다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Max` 온도를 나타내는 숫자 배열의 최대 온도를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>최소값  
 다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Min` 온도를 나타내는 숫자 배열의 최소 온도를 계산 합니다.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>합계  
 다음 코드 예제에서는 절을 사용 하 여 `Aggregate Into Sum` 비용을 나타내는 값 배열의 총 비용을 계산 합니다.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [방법: CSV 텍스트 파일의 열 값 계산 (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [방법: 데이터 개수, 합 또는 평균 계산](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [방법: 쿼리 결과의 최소값 또는 최대값 찾기](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(Visual Basic)](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [방법: 폴더 집합의 총 바이트 수 쿼리 (LINQ) (Visual Basic)](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
