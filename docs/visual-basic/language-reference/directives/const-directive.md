---
title: '#Const 지시문 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 5458bbebc6064eb6273b8deb5447b8941e1d233f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746699"
---
# <a name="const-directive"></a>#Const 지시문
Visual Basic에 대 한 조건부 컴파일러 상수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>요소  
 `constname`  
 필수 요소. 정의 되는 상수의의 이름입니다.  
  
 `expression`  
 필수 요소. 리터럴, 다른 조건부 컴파일러 상수를 제외한 모든 산술 또는 논리 연산자를 포함 하는 조합을 `Is`합니다.  
  
## <a name="remarks"></a>설명  
 조건부 컴파일러 상수는 항상 표시 되는 파일에 private입니다. 공용 컴파일러 상수를 사용 하 여 만들 수 없습니다는 `#Const` 지시문; 또는 사용자 인터페이스에만 만들 수 있습니다는 `/define` 컴파일러 옵션입니다.  
  
 조건부 컴파일러 상수와 리터럴만 사용할 수 있습니다 `expression`합니다. 사용 하 여 정의 되는 표준 상수를 사용 하 여 `Const` 오류가 발생 합니다. 반대로 사용 하 여 정의 된 상수를 사용할 수 있습니다는 `#Const` 조건부 컴파일에 키워드입니다. 상수를 정의의 값이 있는 경우에서 `Nothing`합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `#Const` 지시문을 사용합니다.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>참고자료

- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
