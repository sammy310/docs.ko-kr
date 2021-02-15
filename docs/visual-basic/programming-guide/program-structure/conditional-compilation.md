---
description: '자세한 정보: Visual Basic의 조건부 컴파일'
title: 조건부 컴파일
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: e9cb8a5af4dfbf2ffadef8edd8f6583614188391
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476139"
---
# <a name="conditional-compilation-in-visual-basic"></a>Visual Basic의 조건부 컴파일

*조건부 컴파일에서* 프로그램의 특정 코드 블록은 선택적으로 컴파일되고 다른 항목은 무시 됩니다.  
  
 예를 들어 서로 다른 방법의 속도와 동일한 프로그래밍 작업을 비교 하는 디버깅 문을 작성 하거나 응용 프로그램에서 여러 언어를 지역화할 수 있습니다. 조건부 컴파일 문은 런타임에 실행 되지 않고 컴파일 시간에 실행 되도록 설계 되었습니다.  
  
 지시문을 사용 하 여 조건부로 컴파일되는 코드 블록을 나타냅니다 `#If...Then...#Else` . 예를 들어 동일한 소스 코드에서 프랑스어 및 독일어 버전의 동일한 응용 프로그램을 만들려면 `#If...Then` 미리 정의 된 상수 및를 사용 하 여 문에 플랫폼별 코드 세그먼트를 포함 `FrenchVersion` `GermanVersion` 합니다. 다음 예에서는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 `FrenchVersion`컴파일 시간에 조건부 컴파일 상수 값을로 설정 하면 `True` 프랑스어 버전의 조건부 코드가 컴파일됩니다. 상수 값을로 설정 하는 경우 `GermanVersion` `True` 컴파일러는 독일어 버전을 사용 합니다. 둘 다로 설정 하지 않으면 `True` 마지막 블록의 코드가 `Else` 실행 됩니다.  
  
> [!NOTE]
> 코드를 편집 하 고 코드를 현재 분기에 포함 하지 않는 경우 조건부 컴파일 지시문을 사용 하면 자동 완성이 작동 하지 않습니다.  
  
## <a name="declaring-conditional-compilation-constants"></a>조건부 컴파일 상수 선언  

 다음 세 가지 방법 중 하나로 조건부 컴파일 상수를 설정할 수 있습니다.  
  
- **프로젝트 디자이너** 에서  
  
- 명령줄 컴파일러를 사용 하는 경우 명령줄에서  
  
- 코드에서  
  
 조건부 컴파일 상수는 특수 한 범위를 가지 며 표준 코드에서 액세스할 수 없습니다. 조건부 컴파일 상수의 범위는 설정 된 방식에 따라 달라 집니다. 다음 표에서는 위에 설명 된 세 가지 방법을 사용 하 여 선언 된 상수 범위를 나열 합니다.  
  
|상수 설정 방법|상수 범위|  
|---|---|  
|**프로젝트 디자이너**|프로젝트의 모든 파일에 공개|  
|명령 줄|명령줄 컴파일러에 전달 된 모든 파일에 공용|  
|`#Const` 코드의 문|선언 된 파일 전용|  
  
|프로젝트 디자이너에서 상수를 설정 하려면|  
|---|  
|-실행 파일을 만들기 전에 프로젝트 **디자이너** 에서 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)에 제공 된 단계에 따라 상수를 설정 합니다.|  
  
|명령줄에서 상수를 설정 하려면|  
|---|  
|-다음 예제와 같이- **d** 스위치를 사용 하 여 조건부 컴파일 상수를 입력 합니다.<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     **-D** 스위치와 첫 번째 상수 사이에는 공간이 필요 하지 않습니다. 자세한 내용은 [-define (Visual Basic)](../../reference/command-line-compiler/define.md)을 참조 하세요.<br />     명령줄 선언은 **프로젝트 디자이너** 에 입력 된 선언을 재정의 하지만이를 지우지 않습니다. **프로젝트 디자이너** 에 설정 되는 인수는 후속 컴파일에서 적용 됩니다.<br />     코드 자체에서 상수를 작성 하는 경우 해당 범위는 선언 된 전체 모듈 이므로 배치에 대 한 엄격한 규칙이 없습니다.|  
  
|코드에서 상수를 설정 하려면|  
|---|  
|-상수를 사용 되는 모듈의 선언 블록에 추가 합니다. 이렇게 하면 코드를 구성 하 고 읽기 쉽게 유지할 수 있습니다.|  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|---|---|  
|[프로그램 구조 및 코드 규칙](program-structure-and-code-conventions.md)|코드를 쉽게 읽고 유지 관리할 수 있는 제안 사항을 제공 합니다.|  
  
## <a name="reference"></a>참조  

 [#Const 지시문](../../language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else 지시문](../../language-reference/directives/if-then-else-directives.md)  
  
 [-define(Visual Basic)](../../reference/command-line-compiler/define.md)
