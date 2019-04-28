---
title: Visual Basic의 조건부 컴파일
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758459"
---
# <a name="conditional-compilation-in-visual-basic"></a>Visual Basic의 조건부 컴파일
*조건부 컴파일*, 특정 코드 블록을 프로그램에서 선택적으로 컴파일되고 나머지는 무시 됩니다.  
  
 작성 하려는 하는 예를 들어, 여러 언어에 대 한 응용 프로그램을 지역화 하려면 수는 동일한 프로그래밍 작업에 여러 가지 속도 비교 하는 문을 디버깅 합니다. 조건부 컴파일 문에서 런타임 아닌 컴파일 타임 중에 실행 하도록 설계 되었습니다.  
  
 사용 하 여 조건부로 컴파일할 코드 블록을 표시 합니다 `#If...Then...#Else` 지시문입니다. 예를 들어, 프랑스어 및 독일어를 만들려면 버전 같은 동일한 응용 프로그램의 소스 코드를 플랫폼 특정 코드 세그먼트를 포함할 `#If...Then` 미리 정의 된 상수를 사용 하 여 문을 `FrenchVersion` 고 `GermanVersion`입니다. 다음 예제에서는 어떻게:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 값을 설정 하는 경우는 `FrenchVersion` 조건부 컴파일 상수를 `True` 프랑스어 버전에 대 한 조건부 코드를 컴파일 타임에 컴파일됩니다. 값을 설정 하는 경우는 `GermanVersion` 상수입니다 `True`, 컴파일러는 독일어 버전을 사용 합니다. 둘 다로 설정 되어 있으면 `True`, 지난에서 코드 `Else` 블록이 실행 됩니다.  
  
> [!NOTE]
>  자동 완성은 코드를 편집 하는 경우 not 함수 코드를 현재 분기의 일부가 아닌 경우 조건부 컴파일 지시문을 사용 합니다.  
  
## <a name="declaring-conditional-compilation-constants"></a>조건부 컴파일 상수를 선언합니다.  
 세 가지 방법 중 하나로 조건부 컴파일 상수를 설정할 수 있습니다.  
  
- 에 **프로젝트 디자이너**  
  
- 명령줄 컴파일러를 사용 하는 경우 명령줄에서  
  
- 코드에서  
  
 조건부 컴파일 상수는 특별 한 범위가 있으며 표준 코드에서 액세스할 수 없습니다. 조건부 컴파일 상수 범위가 설정 방법에 따라 달라 집니다. 다음 표에서 각 위에서 언급 한 세 가지 방법을 사용 하 여 선언 된 상수의 범위를 나열 합니다.  
  
|상수를 설정 하는 방법|상수의 범위|  
|---|---|  
|**프로젝트 디자이너**|프로젝트의 모든 파일|  
|명령줄|명령줄 컴파일러에 전달 하는 모든 파일|  
|`#Const` 코드에서 문|이전에 선언 된 파일을 개인|  
  
|프로젝트 디자이너에서 상수를 설정 하려면|  
|---|  
|-실행 파일을 만들기 전에 다음을 수행 합니다에서 상수를 설정 합니다 **프로젝트 디자이너** 에 나와 있는 단계를 수행 하 여 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)합니다.|  
  
|명령줄에서 상수를 설정 하려면|  
|---|  
|-사용 합니다 **/d** 다음 예제와 같이 조건부 컴파일 상수를 입력으로 전환 합니다.<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     공간이 간의 필요 하지 않습니다 합니다 **/d** 스위치 및 첫 번째 상수입니다. 자세한 내용은 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)합니다.<br />     명령줄 선언에 입력 된 선언을 재정의 **프로젝트 디자이너**, 하지만 해당 지우지 마세요. 인수에서 설정할 **프로젝트 디자이너** 다음에 컴파일할 계속 적용 됩니다.<br />     상수 자체 코드에서를 작성할 때 규칙이 없습니다 엄격한 해당 배치에 대 한 해당 범위에 선언 되는 전체 모듈 때문입니다.|  
  
|코드에서 상수를 설정 하려면|  
|---|  
|-상수 사용 되는 모듈의 선언 블록에 배치 합니다. 이렇게 구성 하 고 읽기 쉽게 코드를 유지 합니다.|  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|---|---|  
|[프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|코드를 더 쉽게 읽고 유지 관리에 대 한 제안을 제공 합니다.|  
  
## <a name="reference"></a>참조  
 [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
