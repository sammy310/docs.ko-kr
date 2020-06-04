---
title: 데이터 필터링
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: f7a1aa76dc93cc03952e55f5f8fc3f75176a3f9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383419"
---
# <a name="filtering-data-visual-basic"></a>데이터 필터링 (Visual Basic)

필터링은 지정된 조건을 충족하는 요소만 포함하도록 결과 집합을 제한하는 작업을 가리킵니다. 필터링은 선택이라고도 합니다.

다음 그림에서는 문자 시퀀스를 필터링한 결과를 보여 줍니다. 필터링 작업에 대한 조건자는 문자가 'A'가 되도록 지정합니다.

![LINQ 필터링 작업을 보여주는 다이어그램](./media/filtering-data/linq-filter-operation.png)

선택을 수행하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열됩니다.

## <a name="methods"></a>메서드

|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|
|-----------------|-----------------|------------------------------------------|----------------------|
|OfType|지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 선택합니다.|적용할 수 없음|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|Where|조건자 함수를 기반으로 하는 값을 선택합니다.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>쿼리 식 구문 예제

다음 예제에서는를 사용 하 여 `Where` 특정 길이가 지정 된 문자열을 배열에서 필터링 합니다.

```vb
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}

Dim query = From word In words
            Where word.Length = 3
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
```

## <a name="see-also"></a>참고 항목

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [Where 절](../../../language-reference/queries/where-clause.md)
- [방법: 쿼리 결과 필터링](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [방법: 리플렉션을 사용 하 여 어셈블리의 메타 데이터 쿼리 (LINQ) (Visual Basic)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [방법: 지정 된 특성 또는 이름으로 파일 쿼리 (Visual Basic)](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
