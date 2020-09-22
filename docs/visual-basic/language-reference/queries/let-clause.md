---
title: Let 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: a6ff3fc80a2b6752c61a8b8f7d4ce62b5a46baad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869884"
---
# <a name="let-clause-visual-basic"></a>Let 절(Visual Basic)

값을 계산 하 여 쿼리 내의 새 변수에 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`variable`|필수 요소. 제공 된 식의 결과를 참조 하는 데 사용할 수 있는 별칭입니다.|  
|`expression`|필수 사항입니다. 지정 된 변수에 계산 되어 할당 되는 식입니다.|  
  
## <a name="remarks"></a>설명  

 절을 사용 하면 `Let` 각 쿼리 결과의 값을 계산 하 고 별칭을 사용 하 여 참조할 수 있습니다. 이 별칭은 절과 같은 다른 절에서 사용할 수 있습니다 `Where` . `Let`절을 사용 하면 쿼리에 포함 된 식 절에 별칭을 지정 하 고 expression 절을 사용할 때마다 별칭을 대체할 수 있기 때문에 더 쉽게 읽을 수 있는 쿼리 문을 만들 수 있습니다.  
  
 절에는 개수와 할당을 모두 포함할 수 있습니다 `variable` `expression` `Let` . 각 할당을 쉼표 (,)로 구분 합니다.  
  
## <a name="example"></a>예제  

 다음 코드 예에서는 절을 사용 하 여 `Let` 제품에 대해 10% 할인을 계산 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [Select 절](select-clause.md)
- [From 절](from-clause.md)
- [Where 절](where-clause.md)
