---
title: Take While 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 632e9e2195f21a3aa1d1ffd28e9838905c471156
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869657"
---
# <a name="take-while-clause-visual-basic"></a>Take While 절 (Visual Basic)

지정된 조건이 `true`이면 컬렉션의 요소를 포함하고 나머지 요소를 무시합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`expression`|필수 요소. 요소를 테스트할 조건을 나타내는 식입니다. 식은 값을 반환 `Boolean` 하거나로 평가할와 같은 기능을 반환 해야 합니다 `Integer` `Boolean` .|  
  
## <a name="remarks"></a>설명  

 `Take While`절은 제공 된가 반환 될 때까지 쿼리 결과의 시작 부분에 있는 요소를 포함 합니다 `expression` `false` . 가 반환 된 후에는 `expression` `false` 쿼리에서 나머지 요소를 모두 무시 합니다. `expression`나머지 결과에 대해서는이 무시 됩니다.  
  
 절은 `Take While` `Where` `Where` 특정 조건을 충족 하는 쿼리의 모든 요소를 포함 하는 데 사용할 수 있다는 점에서 절과 다릅니다. `Take While`절은 조건이 충족 되지 않을 때까지 요소를 포함 합니다. `Take While`절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.  
  
## <a name="example"></a>예제  

 다음 코드 예에서는 절을 사용 하 여 `Take While` 주문이 없는 첫 번째 고객이 발견 될 때까지 결과를 검색 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Take 절](take-clause.md)
- [Skip While 절](skip-while-clause.md)
- [Where 절](where-clause.md)
