---
title: DirectCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 96cb2082d59373deb34d6894270205b7c1045850
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371520"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast 연산자(Visual Basic)
상속 또는 구현을 기반으로 하는 형식 변환 작업을 소개 합니다.  
  
## <a name="remarks"></a>설명  
 `DirectCast`는 변환에 Visual Basic 런타임 도우미 루틴을 사용 하지 않으므로 `CType` 데이터 형식으로 변환 하는 경우 보다 약간 더 나은 성능을 제공할 수 있습니다 `Object` .  
  
 `DirectCast` [CType 함수와](../functions/ctype-function.md) [TryCast Operator](trycast-operator.md) 키워드를 사용 하는 방법과 유사 하 게 키워드를 사용 합니다. 식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다. `DirectCast`두 인수의 데이터 형식 간에 상속 또는 구현 관계가 필요 합니다. 즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.  
  
## <a name="errors-and-failures"></a>오류 및 오류  
 `DirectCast`는 상속 또는 구현 관계가 없다는 것을 감지 하면 컴파일러 오류를 생성 합니다. 그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다. 원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다. 이 경우 런타임에서 오류를 throw <xref:System.InvalidCastException> 합니다.  
  
## <a name="conversion-keywords"></a>변환 키워드  
 형식 변환 키워드의 비교는 다음과 같습니다.  
  
|키워드|데이터 형식|인수 관계|런타임 오류|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.|되거나<xref:System.InvalidCastException>|  
|`DirectCast`|모든 데이터 형식|한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.|되거나<xref:System.InvalidCastException>|  
|[TryCast 연산자](trycast-operator.md)|참조 형식만|한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.|[아무 것도](../nothing.md) 반환 하지 않음|  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 가지 사용 방법을 보여 줍니다 `DirectCast` . 하나는 런타임에 실패 하 고 다른 하나는 성공 합니다.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 앞의 예제에서의 런타임 형식은입니다 `q` `Double` . `CType``Double`는로 변환 될 수 있으므로 성공 `Integer` 합니다. 그러나 `DirectCast` 변환이 있는 경우에도의 런타임 형식은와의 상속 관계가 없기 때문에 첫 번째는 런타임에 실패 합니다 `Double` `Integer` . 두 번째는 `DirectCast` 형식에서를 <xref:System.Windows.Forms.Form> 상속 하는 형식으로 변환 하기 때문에 성공 합니다 <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Form> .  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
