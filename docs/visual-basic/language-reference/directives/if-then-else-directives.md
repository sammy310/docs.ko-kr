---
title: '#다음과 같은 경우... Then... #Else 지시문 (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823391"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else 지시문
선택한 Visual Basic 코드 블록을을 조건부로 컴파일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a>요소  
 `expression`  
 에 필요한 `#If` 및 `#ElseIf` 선택적 문을 다른 곳입니다. 만으로 구성 된 하나 이상의 조건부 컴파일러 상수, 리터럴 및 연산자 계산 되는 식일 `True` 또는 `False`합니다.  
  
 `statements`  
 에 필요한 `#If` 문 블록에서는 선택적 다른 곳입니다. Visual Basic 프로그램 선 또는 연결 된 식이 계산 되는 경우 컴파일되는 컴파일러 지시문 `True`합니다.  
  
 `#End If`  
 종료는 `#If` 문 블록입니다.  
  
## <a name="remarks"></a>설명  
 동작 화면에서를 `#If...Then...#Else` 지시문 동일 하 게와 표시는 `If...Then...Else` 문. 그러나 합니다 `#If...Then...#Else` 지시문은 컴파일러에 의해 컴파일되는 내용을 반면 평가 `If...Then...Else` 문은 런타임에 조건을 평가 합니다.  
  
 조건부 컴파일은 일반적으로 다양 한 플랫폼에 대 한 동일한 프로그램을 컴파일하는 데 사용 됩니다. 방지 하기 위해 사용 되는 실행 파일에 표시 되는 코드를 디버깅 합니다. 조건부 컴파일 중에 제외 되는 코드 크기 또는 성능에 영향을 주지 것이 아니므로 완전히 최종 실행 파일에서 생략 됩니다.  
  
 모든 평가의 결과 관계 없이 모든 식을 사용 하 여 평가 됩니다 `Option Compare Binary`합니다. 합니다 `Option Compare` 문 식에 영향을 주지 않습니다 `#If` 및 `#ElseIf` 문입니다.  
  
> [!NOTE]
>  없는 한 줄 형식의 합니다 `#If`, `#Else`, `#ElseIf`, 및 `#End If` 지시문 존재 합니다. 다른 코드가 없어야 지시문와 동일한 줄에 나타날 수 있습니다. 

조건부 컴파일 블록 내에서 문을 논리 문을 완료 해야 합니다. 예를 들어 함수의 특성만 조건부로 컴파일할 수 없습니다 있지만 특성과 함께 함수를 조건적으로 선언할 수 있습니다.

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a>예제
 이 예제에서는 `#If...Then...#Else` 구문을 특정 문은 컴파일 여부를 결정 합니다.  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참고자료

- [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
