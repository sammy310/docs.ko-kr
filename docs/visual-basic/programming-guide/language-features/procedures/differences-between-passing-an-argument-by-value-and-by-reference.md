---
title: 인수를 값으로 전달할 때와 참조로 전달할 때의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 84ec3bac2532b2cef72ddda347251bc987801c3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341225"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>인수를 값으로 전달할 때와 참조로 전달할 때의 차이점(Visual Basic)
하나 이상의 인수를 프로시저에 전달 하는 경우 각 인수는 호출 코드의 기본 프로그래밍 요소에 해당 합니다. 이 기본 요소의 값 이나 참조를 전달할 수 있습니다. 이를 *전달 메커니즘*이라고 합니다.  
  
## <a name="passing-by-value"></a>값으로 전달  
 프로시저 정의에서 해당 매개 변수에 대해 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 키워드를 지정 하 여 인수를 *값으로* 전달 합니다. 이 전달 메커니즘을 사용 하는 경우 Visual Basic는 기본 프로그래밍 요소의 값을 프로시저의 지역 변수로 복사 합니다. 프로시저 코드에는 호출 코드의 기본 요소에 대 한 액세스 권한이 없습니다.  
  
## <a name="passing-by-reference"></a>참조로 전달  
 프로시저 정의에서 해당 매개 변수에 대해 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 지정 하 여 인수를 *참조로* 전달 합니다. 이 전달 메커니즘을 사용 하는 경우 Visual Basic은 호출 코드의 기본 프로그래밍 요소에 대 한 직접 참조를 프로시저에 제공 합니다.  
  
## <a name="passing-mechanism-and-element-type"></a>메커니즘 및 요소 형식 전달  
 전달 메커니즘의 선택은 기본 요소 형식의 분류와 동일 하지 않습니다. 값 또는 참조로 전달 하는 것은 프로시저 코드에 제공 Visual Basic는 것을 의미 합니다. 값 형식 또는 참조 형식은 프로그래밍 요소를 메모리에 저장 하는 방법을 나타냅니다.  
  
 그러나 전달 메커니즘 및 요소 형식은 서로 연관 되어 있습니다. 참조 형식의 값은 메모리의 다른 위치에 있는 데이터에 대 한 포인터입니다. 즉, 참조 형식을 값으로 전달 하는 경우 기본 요소 자체에 액세스할 수 없는 경우에도 프로시저 코드에 기본 요소 데이터에 대 한 포인터가 있습니다. 예를 들어 요소가 배열 변수인 경우 프로시저 코드는 변수에 대 한 액세스 권한을 갖지 않지만 배열 멤버에 액세스할 수 있습니다.  
  
## <a name="ability-to-modify"></a>수정 기능  
 수정할 수 없는 요소를 인수로 전달 하는 경우 프로시저는 호출 코드에서 `ByVal` 또는 `ByRef`전달 되는지 여부를 수정할 수 없습니다.  
  
 수정 가능한 요소에 대해 다음 표에서는 요소 형식과 전달 메커니즘 간의 상호 작용을 요약 합니다.  
  
|요소 형식|전달 된 `ByVal`|전달 된 `ByRef`|  
|------------------|--------------------|--------------------|  
|값 형식 (값만 포함)|프로시저는 변수나 해당 멤버를 변경할 수 없습니다.|프로시저는 변수와 해당 멤버를 변경할 수 있습니다.|  
|참조 형식 (클래스 또는 구조체 인스턴스에 대 한 포인터 포함)|프로시저는 변수를 변경할 수 없지만 해당 변수를 가리키는 인스턴스의 멤버를 변경할 수 있습니다.|프로시저는 변수가 가리키는 인스턴스의 멤버 및 멤버를 변경할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)
- [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)
- [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
