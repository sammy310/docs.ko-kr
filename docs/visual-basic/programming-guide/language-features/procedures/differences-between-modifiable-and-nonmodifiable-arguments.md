---
title: 수정할 수 있는 인수와 수정할 수 없는 인수의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 662ad3039bb3fd5c44847d5b2a97a033a18ad063
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071964"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)

프로시저를 호출 하는 경우 일반적으로 하나 이상의 인수를 전달 합니다. 각 인수는 기본 프로그래밍 요소에 해당 합니다. 기본 요소와 인수 자체는 수정할 수 있거나 수정할 수 없습니다.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>수정 가능 하 고 수정할 요소가 없는 요소  

 프로그래밍 요소는 해당 값이 변경 될 수 있는 *수정 가능한 요소*이거나, 만들어진 후 고정 값이 있는 수정할 수 없는 *요소*일 수 있습니다.  
  
 다음 표에서는 수정 및 수정할 때의 프로그래밍 요소를 보여 줍니다.  
  
|수정 가능한 요소|수정할 때 요소|  
|-------------------------|----------------------------|  
|읽기 전용을 제외 하 고 개체 변수를 포함 하 여 지역 변수 (프로시저 내에 선언 됨)|읽기 전용 변수, 필드 및 속성|  
|필드 (모듈, 클래스 및 구조체의 멤버 변수) (읽기 전용 제외)|상수 및 리터럴|  
|읽기 전용을 제외한 속성|열거형 멤버|  
|배열 요소|식 (요소를 수정할 수 있는 경우에도)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>수정 가능 하 고 수정 가능한 인수  

 *수정 가능한 인수* 는 수정 가능한 기본 요소를 포함 하는 인수입니다. 호출 코드는 언제 든 지 새 값을 저장할 수 있으며, [ByRef](../../../language-reference/modifiers/byref.md)인수를 전달 하는 경우 프로시저의 코드는 호출 코드의 내부 요소를 수정할 수도 있습니다.  
  
 수정할 수 없는 *인수* 에는 수정할 수 없는 내부 요소가 있거나 [ByVal](../../../language-reference/modifiers/byval.md)로 전달 됩니다. 이 프로시저는 수정 가능한 요소인 경우에도 호출 코드의 기본 요소를 수정할 수 없습니다. 수정할 수 없는 요소인 경우 호출 코드 자체에서 수정할 수 없습니다.  
  
 호출 된 프로시저는 수정할 수 없는 인수의 로컬 복사본을 수정할 수 있지만이 수정 작업은 호출 코드의 기본 요소에는 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [인수를 값으로 전달할 때와 참조로 전달할 때의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)
- [방법: 값 변경으로부터 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)
- [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
