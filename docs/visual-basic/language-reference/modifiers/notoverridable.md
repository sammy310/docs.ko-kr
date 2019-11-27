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
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351452"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable(Visual Basic)
속성이 나 프로시저를 파생 클래스에서 재정의할 수 없도록 지정 합니다.  
  
## <a name="remarks"></a>주의  
 `NotOverridable` 한정자는 속성 또는 메서드가 파생 클래스에서 재정의 되지 않도록 합니다.  [재정의할](../../../visual-basic/language-reference/modifiers/overridable.md) 수 있는 한정자를 사용 하면 클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있습니다. 자세한 내용은 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.  
  
 `Overridable` 또는 `NotOverridable` 한정자가 지정 되지 않은 경우 기본 설정은 속성이 나 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는지 여부에 따라 달라 집니다. 속성 또는 메서드가 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은 `Overridable`입니다. 그렇지 않으면 `NotOverridable`됩니다.  
  
 재정의할 수 없는 요소를 *sealed* 요소 라고도 합니다.  
  
 `NotOverridable`는 속성 또는 프로시저 선언문 에서만 사용할 수 있습니다. 다른 속성 또는 프로시저를 재정의 하는 속성 또는 프로시저 (즉, `Overrides`와 함께 사용 하는 경우에만 `NotOverridable` 지정할 수 있습니다.  
  
## <a name="combined-modifiers"></a>결합 된 한정자  
 `Private` 메서드에 대해 `Overridable` 또는 `NotOverridable`를 지정할 수 없습니다.  
  
 동일한 선언에서 `MustOverride`, `Overridable`또는 `Shared`와 함께 `NotOverridable`를 지정할 수 없습니다.  
  
## <a name="usage"></a>사용법  
 `NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [한정자](../../../visual-basic/language-reference/modifiers/index.md)
- [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MyBase](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)
- [키워드](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic에서 숨김](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
