---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: b252f7939e812f31103d4bd98ffd50953679f042
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351472"
---
# <a name="narrowing-visual-basic"></a>Narrowing(Visual Basic)
변환 연산자 (`CType`)가 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 값 중 일부를 보유할 수 없는 형식으로 변환 함을 나타냅니다.  
  
## <a name="converting-with-the-narrowing-keyword"></a>축소 키워드를 사용 하 여 변환  
 변환 프로시저는 `Narrowing`외에 `Public Shared`를 지정 해야 합니다.  
  
 축소 변환은 런타임에 항상 성공 하지 않으며 데이터 손실이 발생 하거나 실패할 수 있습니다. 예제는 `Integer`, `Date``String` 및 기본 형식을 파생 형식에 `Long` 합니다. 기본 형식에 파생 형식의 멤버가 모두 포함 되어 있지 않아 파생 형식의 인스턴스가 아닌 경우 마지막 변환은 축소입니다.  
  
 `Option Strict` `On`되는 경우 사용 하는 코드는 모든 축소 변환에 대해 `CType`를 사용 해야 합니다.  
  
 이 컨텍스트에서는 `Narrowing` 키워드를 사용할 수 있습니다.  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)
- [확장](../../../visual-basic/language-reference/modifiers/widening.md)
- [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
