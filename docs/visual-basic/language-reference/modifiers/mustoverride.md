---
title: '%%amp;lt;CLSCompliant(False)%%amp;gt;'
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351489"
---
# <a name="mustoverride-visual-basic"></a>MustOverride(Visual Basic)
속성 또는 프로시저가이 클래스에서 구현 되지 않고 파생 클래스에서 재정의 되어야 사용할 수 있도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `MustOverride`는 속성 또는 프로시저 선언문 에서만 사용할 수 있습니다. `MustOverride`를 지정 하는 속성 또는 프로시저는 클래스의 멤버 여야 하 고 클래스는 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)로 표시 되어야 합니다.  
  
## <a name="rules"></a>규칙  
  
- **선언이 완전 하지 않습니다.** `MustOverride`지정 하면 `End Function`, `End Property`또는 `End Sub` 문이 아니더라도 속성 또는 프로시저에 대 한 추가 코드 줄을 제공 하지 않습니다.  
  
- **결합 된 한정자입니다.** 동일한 선언에서 `NotOverridable`, `Overridable`또는 `Shared`와 함께 `MustOverride`를 지정할 수 없습니다.  
  
- **숨김 및 재정의.** 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다. 자세한 내용은 [Visual Basic에서 숨기기](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.  
  
- **대체 용어.** 재정의를 제외 하 고 사용할 수 없는 요소는 *순수 가상* 요소 라고도 합니다.  
  
 `MustOverride` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고자료

- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [키워드](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic에서 숨김](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
