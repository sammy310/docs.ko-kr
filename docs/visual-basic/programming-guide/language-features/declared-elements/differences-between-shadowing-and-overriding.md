---
title: 숨기기와 재정의의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 8d1ebdcd0a23dff69a7acca22268c03e30ec06d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345412"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>숨기기와 재정의의 차이점(Visual Basic)
기본 클래스에서 상속 하는 클래스를 정의 하는 경우 파생 클래스에서 하나 이상의 기본 클래스 요소를 다시 정의 하려는 경우가 있습니다. 이러한 용도로 숨김과 재정의를 모두 사용할 수 있습니다.  
  
## <a name="comparison"></a>비교  
 숨김 및 재정의는 모두 파생 클래스가 기본 클래스에서 상속 하는 경우와 선언 된 요소를 다른 요소와 모두 재정의 하는 데 사용 됩니다. 하지만 둘 사이에는 상당한 차이점이 있습니다.  
  
 다음 표에서는 숨김과를 재정의 하는 것을 비교 합니다.  
  
||||  
|---|---|---|  
|비교 지점|섀도잉|재정의|  
|용도|파생 클래스에 이미 정의 된 멤버를 소개 하는 후속 기본 클래스 수정 으로부터 보호 합니다.|동일한 호출 시퀀스<sup>1</sup> 을 사용 하 여 프로시저 또는 속성의 다른 구현을 정의 함으로써 다형성을 달성 합니다.|  
|다시 정의 요소|선언 된 모든 요소 형식|프로시저 (`Function`, `Sub`또는 `Operator`) 또는 속성만|  
|요소 재정의|선언 된 모든 요소 형식|동일한 호출 시퀀스<sup>1</sup> 을 사용 하는 프로시저나 속성만|  
|재정의 요소의 액세스 수준|모든 액세스 수준|재정의 된 요소의 액세스 수준을 변경할 수 없습니다.|  
|재정의 요소의 가독성 및 쓰기 가능성|모든 조합|재정의 된 속성의 가독성 또는 쓰기 가능성를 변경할 수 없습니다.|  
|재정의를 제어 합니다.|기본 클래스 요소는 숨김을 적용 하거나 금지할 수 없습니다.|기본 클래스 요소는 `MustOverride`, `NotOverridable`또는을 지정할 수 있습니다 `Overridable`|  
|키워드 사용|파생 클래스에서 `Shadows` 권장 `Shadows` `Shadows` 또는<sup>`Overrides` 지정 하지</sup> 않은 경우를 가정 합니다.|기본 클래스에 `Overridable` 또는 `MustOverride` 필요 합니다. 파생 클래스에 `Overrides` 필요 합니다.|  
|파생 클래스에서 파생 되는 클래스에의 한 재정의 요소 상속|추가 파생 클래스에서 상속 되는 요소 숨김 숨겨진 요소는 계속 숨겨져 있습니다.<sup>3</sup>|추가로 파생 된 클래스에서 상속 된 요소 재정의 재정의 된 요소가 계속 재정의 되었습니다.|  
  
 <sup>1</sup> *호출 시퀀스* 는 요소 형식 (`Function`, `Sub`, `Operator`또는 `Property`), 이름, 매개 변수 목록 및 반환 형식으로 구성 됩니다. 속성 또는 그 밖의 다른 방법으로는 프로시저를 재정의할 수 없습니다. 다른 종류의 프로시저 (`Function`, `Sub`또는 `Operator`)를 재정의할 수 없습니다.  
  
 <sup>2</sup> `Shadows` 또는 `Overrides`을 지정 하지 않으면 컴파일러에서 사용 하려는 재정의의 종류를 확인할 수 있도록 경고 메시지를 발행 합니다. 경고를 무시 하면 섀도잉 메커니즘이 사용 됩니다.  
  
 <sup>3</sup> 추가 파생 클래스에서 섀도잉 요소에 액세스할 수 없는 경우 숨김은 상속 되지 않습니다. 예를 들어, 섀도잉 요소를 `Private`선언 하는 경우 파생 클래스에서 파생 되는 클래스는 숨기는 요소가 아니라 원래 요소를 상속 합니다.  
  
## <a name="guidelines"></a>지침  
 일반적으로 다음과 같은 경우에 재정의를 사용 합니다.  
  
- 다형 파생 클래스를 정의 합니다.  
  
- 컴파일러가 동일한 요소 형식 및 호출 시퀀스를 강제 적용 하는 것이 좋습니다.  
  
 일반적으로 다음과 같은 경우에 섀도잉을 사용 합니다.  
  
- 기본 클래스를 수정 하 고 사용자와 동일한 이름을 사용 하 여 요소를 정의 하는 것이 예상 됩니다.  
  
- 요소 형식 또는 호출 시퀀스를 자유롭게 변경 하려고 합니다.  
  
## <a name="see-also"></a>참고 항목

- [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic에서 숨김](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [방법: 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [방법: 상속된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [방법: 파생 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)
