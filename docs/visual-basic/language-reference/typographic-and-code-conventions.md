---
title: 글꼴 표시 및 코드 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: 4906c5ebadb7ce77f2d0e53b2fc5dbab69c5b41f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352707"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>글꼴 표시 및 코드 규칙(Visual Basic)

Visual Basic 설명서에서는 다음의 입력 및 코드 규칙을 사용 합니다.  
  
## <a name="typographic-conventions"></a>인쇄 규칙  
  
|예제|설명|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|언어별 키워드 및 런타임 멤버는 초기 대문자를 가지 며이 예제에 나와 있는 것 처럼 형식이 지정 됩니다.|  
|**SmallProject**, **buttoncollection**|입력 하 라는 단어와 문구는이 예제에 표시 된 대로 형식이 지정 됩니다.|  
|[Module 문](../../visual-basic/language-reference/statements/module-statement.md)|클릭 하 여 다른 도움말 페이지로 이동할 수 있는 링크는이 예제에 표시 된 것 처럼 서식 지정 됩니다.|  
|*개체*, *variableName*, `argumentList`|사용자가 제공 하는 정보에 대 한 자리 표시자는이 예제에 표시 된 대로 형식이 지정 됩니다.|  
|[Shadows], [ *Expressionlist* ]|구문에서 선택적 항목은 대괄호로 묶여 있습니다.|  
|{`Public` &#124; `Friend` &#124; `Private`}|구문에서 둘 이상의 항목을 선택 해야 하는 경우 항목은 중괄호로 묶이고 세로 막대로 구분 됩니다.<br /><br /> 항목을 하나만 선택 해야 합니다.|  
|[`Protected` &#124; `Friend`]|구문에서 두 개 이상의 항목 중에서 선택할 수 있는 옵션이 있으면 항목은 대괄호로 묶여 있으며 세로 막대로 구분 됩니다.<br /><br /> 항목의 조합을 선택 하거나 항목을 선택 하지 않을 수 있습니다.|  
|[{`ByVal` &#124; `ByRef`}]|구문에서 둘 이상의 항목을 선택할 수 있지만 항목을 완전히 생략할 수 있는 경우 항목은 중괄호로 묶고 세로 막대로 구분 된 대괄호로 묶여 있습니다.|  
|*memberName*1, *MemberName*2, *memberName*3|예제에 표시 된 것 처럼 동일한 자리 표시자의 여러 인스턴스는 아래 첨자로 구분 됩니다.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|구문에서 줄임표 (...)를 사용 하 여 줄임표 바로 앞에 있는 종류의 항목을 무한 하 게 표시 합니다.<br /><br /> 코드에서 줄임표는 명확 하 게 하기 위해 코드를 생략 함을 나타냅니다.|  
|ESC, ENTER|키보드의 키 이름과 키 시퀀스는 모두 대문자로 표시 됩니다.|  
|Alt+F1|키 이름 사이에 더하기 기호 (+)가 표시 되 면 한 키를 누른 채 다른 키를 눌러야 합니다. 예를 들어, ALT + f 1은 ALT 키를 누른 채 F1 키를 누르는 것을 의미 합니다.|  
  
## <a name="code-conventions"></a>코드 규칙  
  
|예제|설명|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|코드 샘플은 고정 피치 글꼴로 표시 되 고 다음 예제와 같이 형식이 지정 됩니다.|  
|이전 문은 `sampleString`의 값을 "Hello, 세계!"로 설정 합니다.|설명 텍스트의 코드 요소는 다음 예제와 같이 고정 피치 글꼴로 표시 됩니다.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|코드 주석은 아포스트로피 (') 또는 REM 키워드에 의해 도입 됩니다.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|줄 끝에서 밑줄 (_)이 뒤에 오는 공백은 다음 줄에서 문이 계속 됨을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic 언어 참조](../../visual-basic/language-reference/index.md)
- [키워드](../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic 런타임 라이브러리 멤버](../../visual-basic/language-reference/runtime-library-members.md)
- [Visual Basic 명명 규칙](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [방법: 코드에서 문 분리 및 결합](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [코드 주석](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
