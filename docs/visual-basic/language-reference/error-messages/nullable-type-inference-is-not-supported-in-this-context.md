---
title: 이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249502"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.
값 형식 및 구조체는 null로 선언할 수 있습니다.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 그러나 형식 추론과 함께 nullable 선언을 사용할 수 없습니다. 다음 예제에서 이 오류가 발생합니다.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **오류 ID:** BC36629  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 절을 `As` 사용하여 변수를 nullable 값 문자로 선언합니다.  
  
## <a name="see-also"></a>참조

- [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
