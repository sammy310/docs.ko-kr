---
title: TryCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dc4807781f9e1aaf894016952911bd7b32c42948
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875324"
---
# <a name="trycast-operator-visual-basic"></a>TryCast 연산자(Visual Basic)

에는 예외를 throw 하지 않는 형식 변환 연산이 도입 되었습니다.  
  
## <a name="remarks"></a>설명  

 시도 된 변환이 실패 하 `CType` 고 `DirectCast` 둘 다 오류를 throw 하는 경우 <xref:System.InvalidCastException> 이로 인해 응용 프로그램의 성능에 부정적인 영향을 줄 수 있습니다. `TryCast` 은 [아무 것도](../nothing.md)반환 하지 않으므로 가능한 예외를 처리 하지 않고 반환 된 결과만 테스트 하면 `Nothing` 됩니다.  
  
 `TryCast` [CType 함수와](../functions/ctype-function.md) [DirectCast Operator](directcast-operator.md) 키워드를 사용 하는 것과 동일한 방식으로 키워드를 사용 합니다. 식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다. `TryCast` 는 클래스 및 인터페이스와 같은 참조 형식 에서만 작동 합니다. 두 형식 간에 상속 또는 구현 관계가 필요 합니다. 즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.  
  
## <a name="errors-and-failures"></a>오류 및 오류  

 `TryCast` 는 상속 또는 구현 관계가 없다는 것을 감지 하면 컴파일러 오류를 생성 합니다. 그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다. 원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다. 이 경우 `TryCast` [아무 것도](../nothing.md)반환 되지 않습니다.  
  
## <a name="conversion-keywords"></a>변환 키워드  

 형식 변환 키워드의 비교는 다음과 같습니다.  
  
|키워드|데이터 형식|인수 관계|런타임 오류|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.|되거나 <xref:System.InvalidCastException>|  
|[DirectCast 연산자](directcast-operator.md)|모든 데이터 형식|한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.|되거나 <xref:System.InvalidCastException>|  
|`TryCast`|참조 형식만|한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.|[아무 것도](../nothing.md) 반환 하지 않음|  
  
## <a name="example"></a>예제  

 다음 예제에서는 `TryCast`을 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참조

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
