---
title: ReadOnly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 6e361cbe89f4c51f28199b008de817c2d48ef326
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825393"
---
# <a name="readonly-visual-basic"></a>ReadOnly(Visual Basic)
변수 또는 속성을 읽을 수 있지만 기록 되지 않습니다 지정 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** `ReadOnly`는 모듈 수준에서만 사용할 수 있습니다. 즉, 선언 컨텍스트는 `ReadOnly` 요소 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저 수는 없습니다.  
  
-   **결합 된 한정자입니다.** 지정할 수 없습니다 `ReadOnly` 와 함께 `Static` 같은 선언에 있습니다.  
  
-   **값을 할당 합니다.** 사용 하는 코드는 `ReadOnly` 속성의 값을 설정할 수 없습니다. 하지만 기본 저장소에 액세스할 수 있는 코드에 할당 하거나 언제 든 지 값을 변경할 수 있습니다.  
  
     값을 할당할 수 있습니다는 `ReadOnly` 변수 선언 또는 클래스 또는 구조체 정의 되어 있는 생성자만 합니다.  
  
## <a name="when-to-use-a-readonly-variable"></a>읽기 전용 변수를 사용 하는 경우  
 경우에는 사용할 수 없습니다는 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md) 선언 및 상수 값을 할당 합니다. 예를 들어를 `Const` 문을 할당 하려는 데이터 형식이 허용 되지 않거나 상수 식 사용 하 여 컴파일 타임에 값을 계산할 수 있습니다. 모를 수도 있습니다도 값을 컴파일 시간에 있습니다. 이러한 경우에 사용할 수는 `ReadOnly` 상수 값을 보유할 변수로 대체 합니다.  
  
> [!IMPORTANT]
>  변수 자체는 경우에 해당 멤버를 변경할 수 있습니다 변수의 데이터 형식은 참조 형식, 배열 또는 클래스 인스턴스를 같은 경우 `ReadOnly`합니다. 다음은 이에 대한 예입니다.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 를 초기화할 때 배열을 가리키는 `characterArray()` 포함 "x", "y" 및 "z"입니다. 때문에 변수의 `characterArray` 는 `ReadOnly`초기화 된 후;는 해당 값을 변경할 수 없습니다, 새 배열을 할당할 수 없습니다. 그러나 하나 이상의 배열 멤버의 값을 변경할 수 있습니다. 다음 절차에 대 한 호출 `changeArrayElement`를 가리키는 배열 `characterArray()` 포함 "x", "M" 및 "z"입니다.  
  
 이 프로시저 매개 변수를 선언 비슷합니다 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)를 하면 프로시저가 호출 인수 자체를 변경할 수 있지만 해당 멤버를 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `ReadOnly` 직원 고용 날짜에 대 한 속성입니다. 속성 값을 내부적으로 클래스 저장소는 `Private` 변수와 유일한 코드 클래스 내에서 해당 값을 변경할 수 있습니다. 그러나 속성은 `Public`, 클래스에 액세스할 수 있는 모든 코드는 속성을 읽을 수 있습니다.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 `ReadOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>참고자료

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
