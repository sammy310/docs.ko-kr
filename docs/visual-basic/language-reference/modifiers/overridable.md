---
description: '자세한 정보: 재정의 가능 (Visual Basic)'
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: acbbd715113c836a3fb7f8a88bf74307c38ac682
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730501"
---
# <a name="overridable-visual-basic"></a>Overridable(Visual Basic)

속성 또는 프로시저가 파생 클래스의 이름이 같은 속성 또는 프로시저로 재정의 될 수 있도록 지정 합니다.  
  
## <a name="remarks"></a>설명  

 `Overridable`한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다. [NotOverridable](notoverridable.md) 한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.  자세한 내용은 [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.  
  
 `Overridable`또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다. 속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable` . 그렇지 않으면 `NotOverridable` 입니다.  
  
 을 숨기 나 재정의 하 여 상속 된 요소를 다시 정의할 수 있지만 두 방법 간에는 상당한 차이가 있습니다. 자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.  
  
 재정의할 수 있는 요소를 *가상* 요소 라고도 합니다. 재정의할 수는 있지만 일 필요가 없는 경우에는 *구체적* 요소가 라고도 합니다.  
  
 `Overridable`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.  
  
## <a name="combined-modifiers"></a>결합 된 한정자  

 `Overridable`메서드에 대해 또는를 지정할 수 없습니다 `NotOverridable` `Private` .  
  
 `Overridable` `MustOverride` `NotOverridable` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .  
  
 재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.  
  
## <a name="usage"></a>사용량  

 `Overridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Sub 문](../statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [한정자](index.md)
- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [New](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [재정의](overrides.md)
- [C++ 키워드](../keywords/index.md)
- [Visual Basic에서 숨김](../../programming-guide/language-features/declared-elements/shadowing.md)
