---
title: DirectCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331317"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast 연산자(Visual Basic)
상속 또는 구현을 기반으로 하는 형식 변환 작업을 소개 합니다.  
  
## <a name="remarks"></a>주의  
 `DirectCast`는 변환에 Visual Basic 런타임 도우미 루틴을 사용 하지 않으므로 `Object`데이터 형식으로 변환 하는 경우 `CType` 보다 약간 더 나은 성능을 제공할 수 있습니다.  
  
 [CType 함수와](../../../visual-basic/language-reference/functions/ctype-function.md) [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드를 사용 하는 것과 비슷한 방식으로 `DirectCast` 키워드를 사용 합니다. 식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다. `DirectCast`에서는 두 인수의 데이터 형식 간에 상속 또는 구현 관계가 필요 합니다. 즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.  
  
## <a name="errors-and-failures"></a>오류 및 오류  
 상속 또는 구현 관계가 없다는 것을 감지 하면 `DirectCast` 컴파일러 오류가 생성 됩니다. 그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다. 원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다. 이 경우 런타임이 <xref:System.InvalidCastException> 오류를 throw 합니다.  
  
## <a name="conversion-keywords"></a>변환 키워드  
 형식 변환 키워드의 비교는 다음과 같습니다.  
  
|키워드|데이터 형식|인수 관계|런타임 오류|  
|---|---|---|---|  
|[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.|<xref:System.InvalidCastException>를 throw 합니다.|  
|`DirectCast`|모든 데이터 형식|한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.|<xref:System.InvalidCastException>를 throw 합니다.|  
|[TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)|참조 형식만|한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.|[아무 것도](../../../visual-basic/language-reference/nothing.md) 반환 하지 않음|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `DirectCast`의 두 가지 사용을 보여 줍니다. 하나는 런타임에 실패 하 고 다른 하나는 성공 합니다.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 위의 예제에서는 `q`의 런타임 형식이 `Double`됩니다. `Double` `Integer`으로 변환할 수 있기 때문에 `CType` 성공 합니다. 그러나 변환이 있는 경우에도 `Double`의 런타임 형식에 `Integer`와의 상속 관계가 없기 때문에 첫 번째 `DirectCast`는 런타임에 실패 합니다. 두 번째 `DirectCast`은 형식 <xref:System.Windows.Forms.Form>에서 <xref:System.Windows.Forms.Form> 상속 하는 <xref:System.Windows.Forms.Control>형식으로 변환 하기 때문에 성공 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
