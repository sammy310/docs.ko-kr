---
title: '방법: 프로시저의 매개 변수 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: e703346113348556b8a3ea41a7934a55a8008522
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388078"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>방법: 프로시저의 매개 변수 정의(Visual Basic)
*매개 변수* 를 사용 하면 호출 코드에서 호출 시 프로시저에 값을 전달할 수 있습니다. 변수를 선언 하는 것과 동일한 방식으로 프로시저에 대 한 각 매개 변수를 선언 하 고 해당 이름 및 데이터 형식을 지정 합니다. 또한 전달 메커니즘과 매개 변수가 선택적인 지 여부를 지정 합니다.  
  
 자세한 내용은 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)를 참조 하세요.  
  
### <a name="to-define-a-procedure-parameter"></a>프로시저 매개 변수를 정의 하려면  
  
1. 프로시저 선언에서 매개 변수 이름을 다른 매개 변수에서 쉼표로 구분 하 여 프로시저의 매개 변수 목록에 추가 합니다.  
  
2. 매개 변수의 데이터 형식을 결정 합니다.  
  
3. `As`데이터 형식을 지정 하려면 매개 변수 이름 뒤에 절을 추가 합니다.  
  
4. 매개 변수에 대해 원하는 전달 메커니즘을 결정 합니다. 프로시저에서 호출 코드의 값을 변경할 수 없도록 하려면 일반적으로 매개 변수를 값으로 전달 합니다.  
  
5. 매개 변수 이름 앞에 [ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md) 를 사용 하 여 전달 메커니즘을 지정 합니다. 자세한 내용은 [값으로 인수를 전달 하는 것과 참조로 인수를 전달 하는 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조 하세요.  
  
6. 매개 변수가 선택적 요소 이면 전달 메커니즘 앞에 [옵션](../../../language-reference/modifiers/optional.md) 을 추가 하 고 매개 변수 데이터 형식에 등호 ( `=` )와 기본값을 추가 합니다.  
  
     다음 예에서는 `Sub` 세 개의 매개 변수가 있는 프로시저의 개요를 정의 합니다. 처음 두 개는 필수 항목이 며 세 번째는 선택 사항입니다. 매개 변수 선언은 매개 변수 목록에서 쉼표로 구분 됩니다.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     첫 번째 매개 변수는 `customer` 개체를 수락 하 고 `updateCustomer` `c` 인수가 [ByRef](../../../language-reference/modifiers/byref.md)로 전달 되기 때문에에 전달 된 변수를 직접 업데이트할 수 있습니다. 이 프로시저는 [ByVal](../../../language-reference/modifiers/byval.md)로 전달 되기 때문에 마지막 두 인수 값을 변경할 수 없습니다.  
  
     호출 하는 코드에서 매개 변수의 값을 제공 하지 않으면이 값을 `level` 기본값인 0으로 설정 Visual Basic.  
  
     형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가 인 경우 `Off` `As` 매개 변수를 정의할 때 절은 선택 사항입니다. 그러나 한 매개 변수에서 절을 사용 하는 경우 모든 매개 변수는 `As` 이를 사용 해야 합니다. 형식 검사 스위치가 인 경우 `On` `As` 모든 매개 변수 정의에 절이 필요 합니다.  
  
     모든 프로그래밍 요소에 대 한 데이터 형식을 지정 하는 것을 *강력한 형식화*라고 합니다. 를 설정 하면 `Option Strict On` Visual Basic 강력한 형식을 적용 합니다. 다음과 같은 이유로이 작업을 수행 하는 것이 좋습니다.  
  
    - 변수 및 매개 변수에 대해 IntelliSense를 지원할 수 있습니다. 이렇게 하면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.  
  
    - 컴파일러에서 형식 검사를 수행할 수 있습니다. 이렇게 하면 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 문을 catch 하는 데 도움이 됩니다. 또한 지원 하지 않는 개체의 메서드에 대 한 호출을 catch 합니다.  
  
    - 그러면 코드 실행 속도가 빨라집니다. 한 가지 이유는 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않는 경우 Visual Basic 컴파일러에서 해당 형식을 할당 하는 것입니다 `Object` . 컴파일된 코드에서 및 기타 데이터 형식 사이를 변환 해야 하 여 성능이 저하 될 수 있습니다 `Object` .  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [함수 프로시저](./function-procedures.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [재귀 프로시저](./recursive-procedures.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [개체 및 클래스](../objects-and-classes/index.md)
- [개체 지향 프로그래밍(Visual Basic)](../../concepts/object-oriented-programming.md)
