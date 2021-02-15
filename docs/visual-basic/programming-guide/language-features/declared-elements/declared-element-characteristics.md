---
description: '자세히 알아보기: 선언 된 요소 특성 (Visual Basic)'
title: 선언 요소의 특징
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
ms.openlocfilehash: c441b5f55144bead5b11b1d5ddbd0119d6def86b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468462"
---
# <a name="declared-element-characteristics-visual-basic"></a>선언된 요소 특성(Visual Basic)

선언 된 요소의 *특징* 은 코드와 상호 작용 하는 방법에 영향을 주는 요소에 대 한 측면입니다. 선언 된 모든 요소에는 다음과 같은 특징이 하나 이상 있습니다.  
  
- *데이터 형식* -요소에서 보유할 수 있는 값과 해당 값을 저장 하는 방법입니다. 자세한 내용은 [데이터 형식](../../../language-reference/data-types/index.md)을 참조하세요.  
  
- *수명* -요소를 사용할 수 있는 실행 시간의 기간입니다. 자세한 내용은 [Visual Basic 수명](lifetime.md)을 참조 하세요.  
  
- *범위* — 이름을 한정 하지 않고 요소를 참조할 수 있는 모든 코드 집합입니다. 자세한 내용은 [방법: 변수의 범위 제어](how-to-control-the-scope-of-a-variable.md)를 참조 하세요.  
  
- *액세스 수준* -요소를 사용 하는 코드에 대 한 권한입니다. 자세한 내용은 [방법: 변수의 가용성 제어](how-to-control-the-availability-of-a-variable.md)를 참조 하세요.  
  
## <a name="characteristics-of-the-elements"></a>요소의 특징  

 다음 표에서는 선언 된 요소와 각 요소에 적용 되는 특성을 보여 줍니다.  
  
|요소|데이터 형식|수명|범위 <sup>1</sup>|액세스 수준|  
|-------------|---------------|--------------|------------------------|------------------|  
|변수|예|예|예|예|  
|상수|예|예|예|예|  
|열거형|예|예|예|예|  
|구조체|예|예|예|예|  
|속성|예|예|예|예|  
|메서드|아니요|예|예|예|  
|프로시저 ( `Sub` 또는 `Function` )|예|예|예|예|  
|프로시저 매개 변수|예|예|예|예|  
|함수 반환|예|예|예|예|  
|연산자|예|예|예|예|  
|인터페이스|예|예|예|예|  
|클래스|예|예|예|예|  
|이벤트|예|예|예|예|  
|대리자|예|예|예|예|  
  
 <sup>1</sup> 범위는 *표시 유형* 이 라고도 합니다.  
  
## <a name="see-also"></a>추가 정보

- [선언 요소](index.md)
- [Declared Element Names](declared-element-names.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Visual Basic의 수명](lifetime.md)
- [Visual Basic의 범위](scope.md)
- [Visual Basic의 액세스 수준](access-levels.md)
- [데이터 형식](../data-types/index.md)
- [변수 선언](../variables/variable-declaration.md)
