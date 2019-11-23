---
title: Skip While 절
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333148"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While Clause (Visual Basic)
지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`expression`|필수 요소. An expression that represents a condition to test elements for. The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.|  
  
## <a name="remarks"></a>주의  
 The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`. After `expression` returns `false`, the query returns all the remaining elements. The `expression` is ignored for the remaining results.  
  
 The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition. The `Skip While` clause excludes elements only until the first time that the condition is not satisfied. The `Skip While` clause is most useful when you are working with an ordered query result.  
  
 You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.  
  
## <a name="example"></a>예제  
 The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](../../../visual-basic/language-reference/queries/index.md)
- [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip 절](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
