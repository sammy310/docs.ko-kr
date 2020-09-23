---
title: 데이터 분할
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 07e33c4ce0d062a0f083d8970c0ad01f98923a52
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075319"
---
# <a name="partitioning-data-visual-basic"></a>데이터 분할 (Visual Basic)

LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.  
  
 다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다. 첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다. 두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다. 세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.  
  
 ![세 개의 LINQ 분할 작업을 보여주는 그림.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.  
  
## <a name="operators"></a>연산자  
  
|연산자 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|시퀀스에서 지정한 위치까지 요소를 건너뜁니다.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|시퀀스에서 지정된 위치까지 요소를 사용합니다.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="skip"></a>건너뛰기  

 다음 코드 예제에서는 `Skip` 배열의 나머지 문자열을 반환 하기 전에 Visual Basic의 절을 사용 하 여 문자열 배열에서 처음 네 개의 문자열을 건너뜁니다.  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a>SkipWhile  

 다음 코드 예제에서는 `Skip While` 문자열의 첫 문자가 "a" 인 동안 Visual Basic의 절을 사용 하 여 배열의 문자열을 건너뜁니다. 배열의 나머지 문자열이 반환 됩니다.  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a>Take  

 다음 코드 예제에서는 Visual Basic의 절을 사용 하 여 `Take` 문자열 배열에서 처음 두 문자열을 반환 합니다.  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a>TakeWhile  

 다음 코드 예제에서는 `Take While` 문자열의 길이가 5 이하인 동안 Visual Basic의 절을 사용 하 여 배열에서 문자열을 반환 합니다.  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a>참조

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [Skip 절](../../../language-reference/queries/skip-clause.md)
- [Skip While 절](../../../language-reference/queries/skip-while-clause.md)
- [Take 절](../../../language-reference/queries/take-clause.md)
- [Take While 절](../../../language-reference/queries/take-while-clause.md)
