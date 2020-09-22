---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 8eec54a12c7fb748df46e8c48a8b07eab983cc72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867865"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable(Visual Basic)

속성이 나 프로시저를 파생 클래스에서 재정의할 수 없도록 지정 합니다.  
  
## <a name="remarks"></a>설명  

 `NotOverridable`한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.  [재정의할](overridable.md) 수 있는 한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다. 자세한 내용은 [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.  
  
 `Overridable`또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다. 속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable` . 그렇지 않으면 `NotOverridable` 입니다.  
  
 재정의할 수 없는 요소를 *sealed* 요소 라고도 합니다.  
  
 `NotOverridable`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다. `NotOverridable`다른 속성 또는 프로시저를 재정의 하는 속성 또는 프로시저 (즉,와 함께 사용)만 지정할 수 있습니다 `Overrides` .  
  
## <a name="combined-modifiers"></a>결합 된 한정자  

 `Overridable`메서드에 대해 또는를 지정할 수 없습니다 `NotOverridable` `Private` .  
  
 `NotOverridable` `MustOverride` `Overridable` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .  
  
## <a name="usage"></a>사용량  

 `NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Sub 문](../statements/sub-statement.md)  
  
## <a name="see-also"></a>참조

- [한정자](index.md)
- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [New](mustoverride.md)
- [Overrides](overridable.md)
- [재정의](overrides.md)
- [키워드](../keywords/index.md)
- [Visual Basic에서 숨김](../../programming-guide/language-features/declared-elements/shadowing.md)
