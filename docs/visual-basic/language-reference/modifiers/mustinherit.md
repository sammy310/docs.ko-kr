---
title: MustInherit
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 84df7a5cfdad3b5bc6764675725a5d0cb402b0b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396209"
---
# <a name="mustinherit-visual-basic"></a>MustInherit(Visual Basic)
클래스를 기본 클래스로만 사용할 수 있고이 클래스에서 직접 개체를 만들 수 없도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 *기본 클래스* ( *추상 클래스*라고도 함)의 목적은 클래스에서 파생 되는 모든 클래스에 공통적인 기능을 정의 하는 것입니다. 이렇게 하면 파생 클래스가 공통 요소를 다시 정의할 필요가 없습니다. 경우에 따라이 일반적인 기능은 사용 가능한 개체를 만들기에 충분 하지 않으며 각 파생 클래스는 누락 된 기능을 정의 합니다. 이러한 경우에는 사용 하는 코드가 파생 된 클래스 에서만 개체를 만들도록 할 수 있습니다. `MustInherit`기본 클래스에서를 사용 하 여이를 적용 합니다.  
  
 클래스의 또 다른 용도 `MustInherit` 는 변수를 관련 클래스 집합으로 제한 하는 것입니다. 기본 클래스를 정의 하 고이 클래스에서 이러한 관련 클래스를 모두 파생 시킬 수 있습니다. 기본 클래스는 모든 파생 클래스에 공통적인 기능을 제공 하지 않아도 되지만 변수에 값을 할당 하는 필터 역할을 할 수 있습니다. 소비 하는 코드에서 변수를 기본 클래스로 선언 하는 경우 Visual Basic를 사용 하 여 파생 클래스 중 하나의 개체만 해당 변수에 할당할 수 있습니다.  
  
 .NET Framework는, 및 중에서 여러 클래스를 정의 합니다 `MustInherit` <xref:System.Array> <xref:System.Enum> <xref:System.ValueType> . <xref:System.ValueType>는 변수를 제한 하는 기본 클래스의 예입니다. 모든 값 형식은에서 파생 <xref:System.ValueType> 됩니다. 변수를로 선언 하는 경우에 <xref:System.ValueType> 는 값 형식만 해당 변수에 할당할 수 있습니다.  
  
## <a name="rules"></a>규칙  
  
- **선언 컨텍스트.** 문에서만를 사용할 수 있습니다 `MustInherit` `Class` .  
  
- **결합된 한정자.** `MustInherit`을 동일한 선언에 함께 지정할 수 없습니다 `NotInheritable` .  
  
## <a name="example"></a>예제  
 다음 예제에서는 강제 상속과 강제 재정의를 모두 보여 줍니다. 기본 클래스는 `shape` 변수를 정의 합니다 `acrossLine` . 및 클래스 `circle` 는 `square` 에서 파생 `shape` 됩니다. 의 정의를 상속 `acrossLine` 하지만 `area` 각 종류의 셰이프에 대해 계산이 다르므로 함수를 정의 해야 합니다.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 `shape1`및 `shape2` 를 형식으로 선언할 수 있습니다 `shape` . 그러나에서 개체를 만들 수 없습니다 `shape` .이는 함수 기능이 `area` 없고로 표시 되어 있기 때문입니다 `MustInherit` .  
  
 로 선언 되기 때문에 `shape` 및 변수는 `shape1` `shape2` 파생 된 클래스 및의 개체로 제한 됩니다 `circle` `square` . Visual Basic를 사용 하 여 이러한 변수에 다른 개체를 할당할 수 없으며,이는 높은 수준의 형식 안전성을 제공 합니다.  
  
## <a name="usage"></a>사용량  
 `MustInherit`이 컨텍스트에서는 한정자를 사용할 수 있습니다.  
  
 [Class 문](../statements/class-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [Inherits Statement](../statements/inherits-statement.md)
- [NotInheritable](notinheritable.md)
- [C++ 키워드](../keywords/index.md)
- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
