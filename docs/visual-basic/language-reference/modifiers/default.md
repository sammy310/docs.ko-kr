---
title: 기본값
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: ad4c9528f208cc2c31f07b0506d1b049a7568c86
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351576"
---
# <a name="default-visual-basic"></a>Default(Visual Basic)
속성을 해당 클래스, 구조체 또는 인터페이스의 기본 속성으로 식별 합니다.  
  
## <a name="remarks"></a>설명  
 클래스, 구조체 또는 인터페이스는 하나 이상의 매개 변수를 사용 하는 경우 해당 속성 중 하나를 *기본 속성*으로 지정할 수 있습니다. 코드에서 멤버를 지정 하지 않고 클래스 또는 구조체에 대 한 참조를 만드는 경우 Visual Basic는 기본 속성에 대 한 참조를 확인 합니다.  
  
 기본 속성은 소스 코드 문자를 조금 줄일 수 있지만 코드를 읽기 어렵게 만들 수 있습니다. 호출 코드가 클래스 또는 구조체를 사용 하는 데 익숙하지 않은 경우 클래스 또는 구조체 이름에 대 한 참조를 만들 때 참조가 클래스나 구조체 자체에 액세스 하는지 아니면 기본 속성에 액세스 하는지 여부를 확신할 수 없습니다. 이로 인해 컴파일러 오류 또는 미묘한 런타임 논리 오류가 발생할 수 있습니다.  
  
 항상 [Option Strict 문을](../../../visual-basic/language-reference/statements/option-strict-statement.md) 사용 하 여 컴파일러 유형 검사를 `On`로 설정 하면 기본 속성 오류의 가능성을 약간 줄일 수 있습니다.  
  
 코드에서 미리 정의 된 클래스 또는 구조체를 사용 하려는 경우 기본 속성이 있는지 여부를 확인 하 고, 해당 하는 경우 이름을 지정 해야 합니다.  
  
 이러한 단점 때문에 기본 속성을 정의 하지 않는 것이 좋습니다. 코드 가독성을 위해 기본 속성도 항상 모든 속성을 명시적으로 참조 하는 것도 고려해 야 합니다.  
  
 이 컨텍스트에서는 `Default` 한정자를 사용할 수 있습니다.  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>참고자료

- [방법: Visual Basic에서 기본 속성 선언 및 호출](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [키워드](../../../visual-basic/language-reference/keywords/index.md)
