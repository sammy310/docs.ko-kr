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
ms.openlocfilehash: af722f7aee021f244b411cdc61619b7de3c20607
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866227"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While 절 (Visual Basic)

지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`expression`|필수 요소. 요소를 테스트할 조건을 나타내는 식입니다. 식은 값을 반환 `Boolean` 하거나로 평가할와 같은 기능을 반환 해야 합니다 `Integer` `Boolean` .|  
  
## <a name="remarks"></a>설명  

 `Skip While`절은 제공 된가 반환 될 때까지 쿼리 결과의 시작 부분에서 요소를 무시 합니다 `expression` `false` . `expression`가 반환 된 후 `false` 쿼리는 나머지 요소를 모두 반환 합니다. `expression`나머지 결과에 대해서는이 무시 됩니다.  
  
 절은 절 `Skip While` 과 다르므로 절은 `Where` `Where` 특정 조건을 충족 하지 않는 쿼리에서 모든 요소를 제외 하는 데 사용할 수 있습니다. `Skip While`절은 조건이 충족 되지 않을 때까지 요소만 제외 합니다. `Skip While`절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.  
  
 절을 사용 하 여 쿼리 결과의 시작 부분에서 특정 개수의 결과를 무시할 수 있습니다 `Skip` .  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 `Skip While` 미국에서 첫 번째 고객이 발견 될 때까지 절을 사용 하 여 결과를 무시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Skip 절](skip-clause.md)
- [Take While 절](take-while-clause.md)
- [Where 절](where-clause.md)
