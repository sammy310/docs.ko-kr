---
title: Overload Resolution
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266874"
---
# <a name="overload-resolution-visual-basic"></a>오버로드 확인(Visual Basic)
Visual Basic 컴파일러가 여러 오버로드된 버전에서 정의된 프로시저에 대한 호출이 발생하면 컴파일러는 호출할 오버로드를 결정해야 합니다. 다음 단계를 수행 하 여이 작업을 수행 합니다.  
  
1. **접근성.** 호출 코드가 호출하지 못하도록 하는 액세스 수준이 있는 오버로드를 제거합니다.  
  
2. **매개 변수 수입니다.** 호출에서 제공되는 것과 다른 수의 매개 변수를 정의하는 오버로드를 제거합니다.  
  
3. **매개 변수 데이터 유형입니다.** 컴파일러는 인스턴스 메서드가 확장 메서드보다 기본 설정을 제공합니다. 프로시저 호출과 일치하도록 확대 변환만 필요한 인스턴스 메서드가 발견되면 모든 확장 메서드가 삭제되고 컴파일러는 인스턴스 메서드 후보만 으로 계속됩니다. 이러한 인스턴스 메서드를 찾을 수 없는 경우 인스턴스 및 확장 메서드를 모두 사용 하 고 계속 됩니다.  
  
     이 단계에서는 호출 인수의 데이터 형식을 오버로드에 정의된 매개 변수 유형으로 변환할 수 없는 오버로드를 제거합니다.  
  
4. **전환 범위 축소.** 호출 인수 형식에서 정의된 매개 변수 형식으로 의 축소 변환이 필요한 오버로드를 제거합니다. 형식 검사 스위치(옵션 엄격 명령문)가 `On` `Off`있는지 여부에 관계없이 이 사실은 다음과 같은 것입니다.[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
  
5. **최소 확대.** 컴파일러는 나머지 오버로드를 쌍으로 고려합니다. 각 쌍에 대해 정의된 매개 변수의 데이터 형식을 비교합니다. 오버로드 중 하나의 형식이 모두 다른 형식의 해당 형식으로 확대되면 컴파일러는 후자를 제거합니다. 즉, 최소한의 확대가 필요한 오버로드를 유지합니다.  
  
6. **단일 후보.** 하나의 오버로드만 남아 있고 해당 오버로드에 대한 호출을 해결할 때까지 쌍으로 오버로드를 계속 고려합니다. 컴파일러가 단일 후보로 오버로드를 줄일 수 없는 경우 오류가 생성됩니다.  
  
 다음 그림에서는 호출할 오버로드된 버전 집합을 결정하는 프로세스를 보여 주며, 이 프로세스를 보여 주시면 됩니다.  
  
 ![오버로드 확인 프로세스의 흐름도](./media/overload-resolution/determine-overloaded-version.gif "오버로드된 버전 간 해결")
  
 다음 예제에서는 이 오버로드 해결 프로세스를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 첫 번째 호출에서 컴파일러는 첫 번째 인수 ()`Short`형식이 해당 매개 변수 ()의`Byte`유형으로 좁혀지므로 첫 번째 오버로드를 제거합니다. 그런`Short` 다음 두 번째 오버로드(및)의 `Single`각 인수 유형이 세 번째 오버로드(및)의`Integer` `Single`해당 유형으로 확장되므로 세 번째 오버로드를 제거합니다. 두 번째 오버로드는 더 적은 확대가 필요하므로 컴파일러는 호출에 사용합니다.  
  
 두 번째 호출에서 컴파일러는 축소를 기준으로 오버로드를 제거할 수 없습니다. 인수 형식의 확대가 적어 두 번째 오버로드를 호출할 수 있기 때문에 첫 번째 호출과 동일한 이유로 세 번째 오버로드를 제거합니다. 그러나 컴파일러는 첫 번째 오버로드와 두 번째 오버로드 사이에서 해결할 수 없습니다. 각각에는 다른 형식의 해당 유형으로 확장되는 정의된`Byte` `Short`매개 `Single` 변수 `Double`유형이 하나 있습니다(하지만 )로 확장됩니다. 따라서 컴파일러는 오버로드 확인 오류를 생성합니다.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>오버로드된 옵션 및 ParamArray 인수  
 프로시저의 두 오버로드에 마지막 매개 변수가 하나의 [경우 Optional로](../../../../visual-basic/language-reference/modifiers/optional.md) 선언되고 다른 하나는 [ParamArray로](../../../../visual-basic/language-reference/modifiers/paramarray.md) 선언되는 경우 컴파일러는 다음과 같이 해당 프로시저에 대한 호출을 해결합니다.  
  
|호출이 마지막 인수를 다음으로 제공하는 경우|컴파일러는 마지막 인수를 선언하는 오버로드에 대한 호출을 확인합니다.|  
|---|---|  
|값 없음(인수생략)|`Optional`|  
|단일 값|`Optional`|  
|쉼표로 구분된 목록에서 둘 이상의 값|`ParamArray`|  
|모든 길이의 배열(빈 배열 포함)|`ParamArray`|  
  
## <a name="see-also"></a>참고 항목

- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)
- [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [확장 메서드](./extension-methods.md)
