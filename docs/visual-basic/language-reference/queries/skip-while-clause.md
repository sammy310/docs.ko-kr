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
# <a name="skip-while-clause-visual-basic"></a>Skip While 절(Visual Basic)
지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`expression`|필수입니다. 요소를 테스트할 조건을 나타내는 식입니다. 식은 `Boolean`으로 평가할 `Integer`와 같이 `Boolean` 값 또는 기능적으로 동일한 기능을 반환 해야 합니다.|  
  
## <a name="remarks"></a>주의  
 `Skip While` 절은 제공 된 `expression` `false`반환 될 때까지 쿼리 결과의 시작 부분에서 요소를 무시 합니다. `expression`에서 `false`를 반환한 후 쿼리는 나머지 요소를 모두 반환 합니다. 나머지 결과에 대해서는 `expression` 무시 됩니다.  
  
 `Skip While` 절은 `Where` 절을 사용 하 여 특정 조건을 충족 하지 않는 쿼리에서 모든 요소를 제외할 수 있다는 점에서 `Where` 절과 다릅니다. `Skip While` 절은 조건이 충족 되지 않을 때까지 요소만 제외 합니다. `Skip While` 절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.  
  
 `Skip` 절을 사용 하 여 쿼리 결과의 시작 부분에서 특정 개수의 결과를 무시할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 미국에서 첫 번째 고객이 발견 될 때까지 `Skip While` 절을 사용 하 여 결과를 무시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](../../../visual-basic/language-reference/queries/index.md)
- [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip 절](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
