---
description: '자세히 알아보기: 방법: 변수의 범위 제어 (Visual Basic)'
title: '방법: 변수의 범위 제어'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: c6da599f76883cba545efbdf9570aa05770602a2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429873"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>방법: 변수의 범위 제어(Visual Basic)

일반적으로 변수는 *범위* 내에 있거나 선언 하는 지역 전체에서 참조로 표시 됩니다. 경우에 따라 변수의 *액세스 수준이* 범위에 영향을 줄 수 있습니다.  
  
 자세한 내용은 [Scope in Visual Basic](scope.md)을 참조하세요.  
  
## <a name="scope-at-block-or-procedure-level"></a>블록 또는 프로시저 수준에서의 범위  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>블록 내 에서만 변수를 표시 하려면  
  
- 루프의 및 문 사이에 있는 경우와 같이 해당 블록의 시작 및 종료 선언 문 간에 변수에 [Dim 문을](../../../language-reference/statements/dim-statement.md) 추가 합니다 `For` `Next` `For` .  
  
     변수는 블록 내 에서만 참조할 수 있습니다.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>프로시저 내 에서만 변수를 표시 하려면  
  
- `Dim`프로시저 내의 변수는 물론 블록 외부 (예: ... `With` `End With` 블록)에 문을 추가 합니다.  
  
     프로시저 내에서 프로시저 내에 포함 된 모든 블록을 포함 하 여 변수만 참조할 수 있습니다.  
  
## <a name="scope-at-module-or-namespace-level"></a>모듈 또는 네임 스페이스 수준에서의 범위  

 편의를 위해 모듈, 클래스 및 구조에는 단일 용어 *모듈 수준이* 동일 하 게 적용 됩니다. 모듈 수준 변수의 액세스 수준에 따라 해당 범위가 결정 됩니다. 모듈, 클래스 또는 구조가 포함 된 네임 스페이스도 범위에 영향을 미칩니다.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>모듈, 클래스 또는 구조 전체에서 변수를 표시 하도록 설정 하려면  
  
1. `Dim`모듈, 클래스 또는 구조체 내에 있는 변수에 대 한 문을 프로시저 외부에 저장 합니다.  
  
2. 문에 [Private](../../../language-reference/modifiers/private.md) 키워드를 포함 `Dim` 합니다.  
  
3. 모듈, 클래스 또는 구조체 내의 어디에서 나 변수를 참조할 수 있지만 외부에서는 참조할 수 없습니다.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>네임 스페이스 전체에서 변수를 표시 하려면  
  
1. `Dim`모듈, 클래스 또는 구조체 내에 있는 변수에 대 한 문을 프로시저 외부에 저장 합니다.  
  
2. 문에 [Friend](../../../language-reference/modifiers/friend.md) 또는 [Public](../../../language-reference/modifiers/public.md) 키워드를 포함 `Dim` 합니다.  
  
3. 모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 내의 어디에서 나 변수를 참조할 수 있습니다.  
  
## <a name="example"></a>예  

 다음 예제에서는 모듈 수준에서 변수를 선언 하 고 모듈 내의 코드에 대 한 표시 여부를 제한 합니다.  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 위의 예에서는 모듈에 정의 된 모든 프로시저가 `demonstrateScope` 변수를 참조할 수 있습니다 `String` `strMsg` . 프로시저를 `usePrivateVariable` 호출 하면 대화 상자에 문자열 변수의 내용이 표시 됩니다 `strMsg` .  
  
 앞의 예제를 다음과 같이 변경 하 여 문자열 변수를 `strMsg` 선언 네임 스페이스의 모든 위치에서 코드로 참조할 수 있습니다.  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  

 변수의 범위가 작을수록 동일한 이름의 다른 변수 대신 실수로 참조 하는 기회를 줄일 수 있습니다. 참조 일치 문제를 최소화할 수도 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  

 변수의 범위가 작을수록 악의적인 코드가이를 부적절 하 게 사용할 수 있는 기회가 줄어듭니다.  
  
## <a name="see-also"></a>추가 정보

- [Visual Basic의 범위](scope.md)
- [Visual Basic의 수명](lifetime.md)
- [Visual Basic의 액세스 수준](access-levels.md)
- [변수](../variables/index.md)
- [변수 선언](../variables/variable-declaration.md)
- [Dim 문](../../../language-reference/statements/dim-statement.md)
