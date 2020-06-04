---
title: Visual Basic 프로그램의 구조
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: dc6b38d78f02a42c8e7cc2aa964e9f3f74996f44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408766"
---
# <a name="structure-of-a-visual-basic-program"></a>Visual Basic 프로그램의 구조
Visual Basic 프로그램은 표준 구성 요소에서 빌드됩니다. *솔루션* 은 하나 이상의 프로젝트로 구성 됩니다. 그러면 *프로젝트* 에 하나 이상의 어셈블리가 포함 될 수 있습니다. 각 *어셈블리* 는 하나 이상의 소스 파일에서 컴파일됩니다. *소스 파일* 은 궁극적으로 모든 코드를 포함 하는 클래스, 구조체, 모듈 및 인터페이스의 정의와 구현을 제공 합니다.  
  
 Visual Basic 프로그램의 이러한 구성 요소에 대 한 자세한 내용은 .NET의 [솔루션 및 프로젝트](/visualstudio/ide/solutions-and-projects-in-visual-studio) 및 [어셈블리](../../../standard/assembly/index.md)를 참조 하세요.  
  
## <a name="file-level-programming-elements"></a>파일 수준 프로그래밍 요소  
 프로젝트 또는 파일을 시작 하 고 코드 편집기를 열면 일부 코드가 이미 있고 올바른 순서로 표시 됩니다. 작성 하는 모든 코드는 다음 순서를 따라야 합니다.  
  
1. `Option`할당문  
  
2. `Imports`할당문  
  
3. `Namespace`문 및 네임 스페이스 수준 요소  
  
 문을 다른 순서로 입력 하면 컴파일 오류가 발생할 수 있습니다.  
  
 프로그램에는 조건부 컴파일 문도 포함 될 수도 있습니다. 이러한 파일을 원본 파일에서 이전 시퀀스의 문 사이에 섞어서 수 있습니다.  
  
### <a name="option-statements"></a>Option 문  
 `Option`문은 후속 코드에 대 한 접지 규칙을 설정 하 여 구문 및 논리 오류를 방지 합니다. [Option Explicit 문은](../../language-reference/statements/option-explicit-statement.md) 모든 변수가 올바르게 선언 되 고 철자가 올바른지 확인 하므로 디버깅 시간이 줄어듭니다. [Option Strict 문은](../../language-reference/statements/option-strict-statement.md) 다른 데이터 형식의 변수 사이에서 작업할 때 발생할 수 있는 논리 오류 및 데이터 손실을 최소화 하는 데 도움이 됩니다. [Option Compare 문은](../../language-reference/statements/option-compare-statement.md) 또는 값을 기준으로 문자열이 서로 비교 되는 방식을 지정 합니다 `Binary` `Text` .  
  
### <a name="imports-statements"></a>Imports 문  
 [Imports 문 (.Net 네임 스페이스 및 형식)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) 을 포함 하 여 프로젝트 외부에 정의 된 이름을 가져올 수 있습니다. `Imports`문을 사용 하면 코드에서 가져온 네임 스페이스 내에 정의 된 클래스 및 기타 형식을 한정할 필요 없이 참조할 수 있습니다. 필요한 만큼 문을 사용할 수 있습니다 `Imports` . 자세한 내용은 [참조 및 Imports 문](references-and-the-imports-statement.md)을 참조 하세요.  
  
### <a name="namespace-statements"></a>Namespace 문  
 네임 스페이스는 그룹화 및 액세스 용이성을 위해 프로그래밍 요소를 구성 하 고 분류 하는 데 도움이 됩니다. [Namespace 문을](../../language-reference/statements/namespace-statement.md) 사용 하 여 특정 네임 스페이스 내에서 다음 문을 분류 합니다. 자세한 내용은 [Visual Basic의 네임스페이스](namespaces.md)를 참조하세요.  
  
### <a name="conditional-compilation-statements"></a>조건부 컴파일 문  
 조건부 컴파일 문은 소스 파일의 거의 모든 위치에 나타날 수 있습니다. 특정 조건에 따라 코드의 일부를 컴파일 시간에 포함 하거나 제외 시킵니다. 조건부 코드는 디버깅 모드 에서만 실행 되므로 응용 프로그램을 디버깅 하는 데 사용할 수도 있습니다. 자세한 내용은 [조건부 컴파일](conditional-compilation.md)을 참조 하세요.  
  
## <a name="namespace-level-programming-elements"></a>네임 스페이스 수준 프로그래밍 요소  
 클래스, 구조체 및 모듈은 소스 파일의 모든 코드를 포함 합니다. 네임 스페이스는 네임 스페이스 또는 소스 파일 수준에서 나타날 수 있는 *네임 스페이스 수준* 요소입니다. 다른 모든 프로그래밍 요소의 선언을 보유 합니다. 요소 시그니처를 정의 하지만 구현을 제공 하지 않는 인터페이스는 모듈 수준에도 표시 됩니다. 모듈 수준 요소에 대 한 자세한 내용은 다음을 참조 하세요.  
  
- [Class 문](../../language-reference/statements/class-statement.md)  
  
- [Structure 문](../../language-reference/statements/structure-statement.md)  
  
- [Module 문](../../language-reference/statements/module-statement.md)  
  
- [Interface 문](../../language-reference/statements/interface-statement.md)  
  
 네임 스페이스 수준에서 데이터 요소는 열거형 및 대리자입니다.  
  
## <a name="module-level-programming-elements"></a>모듈 수준 프로그래밍 요소  
 프로시저, 연산자, 속성 및 이벤트는 실행 코드 (런타임에 동작을 수행 하는 문)를 보유할 수 있는 유일한 프로그래밍 요소입니다. 프로그램의 *모듈 수준* 요소입니다. 프로시저 수준 요소에 대 한 자세한 내용은 다음을 참조 하십시오.  
  
- [Function 문](../../language-reference/statements/function-statement.md)  
  
- [Sub 문](../../language-reference/statements/sub-statement.md)  
  
- [Declare 문](../../language-reference/statements/declare-statement.md)  
  
- [Operator Statement](../../language-reference/statements/operator-statement.md)  
  
- [Property Statement](../../language-reference/statements/property-statement.md)  
  
- [Event 문](../../language-reference/statements/event-statement.md)  
  
 모듈 수준에서 데이터 요소는 변수, 상수, 열거형 및 대리자입니다.  
  
## <a name="procedure-level-programming-elements"></a>프로시저 수준 프로그래밍 요소  
 *프로시저 수준* 요소의 내용 대부분은 프로그램의 런타임 코드를 구성 하는 실행 가능한 문입니다. 모든 실행 코드는 일부 프로시저 ( `Function` ,,,,,,,)에 있어야 합니다 `Sub` `Operator` `Get` `Set` `AddHandler` `RemoveHandler` `RaiseEvent` . 자세한 내용은 [문](../language-features/statements.md)을 참조하십시오.  
  
 프로시저 수준에서 데이터 요소는 지역 변수 및 상수로 제한 됩니다.  
  
## <a name="the-main-procedure"></a>주 프로시저  
 `Main`프로시저는 응용 프로그램이 로드 될 때 실행 되는 첫 번째 코드입니다. `Main`응용 프로그램에 대 한 시작 지점 및 전반적인 제어 역할을 합니다. 다음과 같은 네 가지 종류의이 있습니다 `Main` .  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 이 절차의 가장 일반적인 방법은 `Sub Main()` 입니다. 자세한 내용은 [Visual Basic 주 절차](main-procedure.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 Main 프로시저](main-procedure.md)
- [Visual Basic 명명 규칙](naming-conventions.md)
- [Visual Basic 제한 사항](limitations.md)
