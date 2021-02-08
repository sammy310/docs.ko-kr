---
description: '#Const 지시문에 대해 자세히 알아보세요.'
title: '#Const 지시문'
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
ms.openlocfilehash: 9597666ee1320f5dfda226040f93a84eb60a3deb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797278"
---
# <a name="const-directive"></a>#Const 지시문

Visual Basic에 대 한 조건부 컴파일러 상수를 정의 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>부분  

 `constname`  
 필수 사항입니다. 정의 되는 상수의 이름입니다.  
  
 `expression`  
 필수 사항입니다. 리터럴, 기타 조건부 컴파일러 상수 또는를 제외한 모든 산술 연산자 또는 논리 연산자를 포함 하는 모든 조합 `Is` 입니다.  
  
## <a name="remarks"></a>설명  

 조건부 컴파일러 상수는 항상 표시 되는 파일에 대해 private입니다. 지시문을 사용 하 여 공용 컴파일러 상수를 만들 수 없습니다 `#Const` . 사용자 인터페이스 또는 컴파일러 옵션을 사용 하 여 만들 수 있습니다 `/define` .  
  
 에서는 조건부 컴파일러 상수 및 리터럴만 사용할 수 있습니다 `expression` . 로 정의 된 표준 상수를 사용 `Const` 하면 오류가 발생 합니다. 반대로 조건부 컴파일에만 키워드를 사용 하 여 정의 된 상수를 사용할 수 있습니다 `#Const` . 상수는 정의 되지 않을 수도 있으며,이 경우 값은 `Nothing` 입니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 `#Const` 지시문을 사용합니다.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- [-define(Visual Basic)](../../reference/command-line-compiler/define.md)
- [#If...Then...#Else 지시문](if-then-else-directives.md)
- [Const 문](../statements/const-statement.md)
- [조건부 컴파일](../../programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else 문](../statements/if-then-else-statement.md)
