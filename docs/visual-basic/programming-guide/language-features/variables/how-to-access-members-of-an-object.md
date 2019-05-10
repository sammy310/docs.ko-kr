---
title: '방법: 개체 (Visual Basic)의 멤버에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 46c5eb9bc79b3a408a5a4fc9f40fee7391937c58
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663596"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>방법: 개체 (Visual Basic)의 멤버에 액세스
개체 변수에 개체를 참조 하는 경우, 해당 메서드, 속성, 필드 및 이벤트와 같은 경우 해당 개체의 멤버를 사용 하려는 경우가 많습니다. 예를 들어 만든 후 새 <xref:System.Windows.Forms.Form> 개체를 설정 하려는 경우 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성 또는 호출 해당 <xref:System.Windows.Forms.Control.Focus%2A> 메서드.  
  
## <a name="accessing-members"></a>멤버 액세스  
 참조 하는 변수를 통해 개체의 멤버에 액세스할 수 있습니다.  
  
#### <a name="to-access-members-of-an-object"></a>개체의 멤버에 액세스  
  
- 멤버 액세스 연산자를 사용 하 여 (`.`) 간의 개체 변수 이름과 멤버 이름입니다.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     멤버 이면 [공유](../../../../visual-basic/language-reference/modifiers/shared.md), 변수를 액세스할 필요가 없습니다.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>알려진 형식의 개체의 멤버에 액세스  
 컴파일 타임에 개체의 형식을 알고 있는 경우 사용할 수 있습니다 *초기 바인딩* 참조 하는 변수에 대 한 합니다.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>유형을 컴파일 시간에 알 수 있는 개체의 멤버에 액세스  
  
1. 변수에 할당 하려는 개체의 형식으로 개체 변수를 선언 합니다.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     사용 하 여 `Option Strict On`에 할당할 수 있습니다 <xref:System.Windows.Forms.Form> 개체 (에서 파생 된 형식의 개체 또는 <xref:System.Windows.Forms.Form>)를 `extraForm`입니다. 클래스 또는 구조체를 확대 정의한 경우 `CType` 변환할 <xref:System.Windows.Forms.Form>, 해당 클래스를 할당 하거나 구조체 수도 `extraForm`합니다.  
  
2. 멤버 액세스 연산자를 사용 하 여 (`.`) 간의 개체 변수 이름과 멤버 이름입니다.  
  
    ```  
    extraForm.Show()  
    ```  
  
     모든 메서드 및 속성에 액세스할 수 있습니다는 <xref:System.Windows.Forms.Form> 무엇이 든 간에 클래스는 `Option Strict` 설정 됩니다.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>알 수 없는 형식의 개체의 멤버에 액세스  
 컴파일 타임에 개체의 형식을 알지 못하는 경우 사용 해야 *런타임에 바인딩* 참조 하는 모든 변수에 대해 합니다.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>모르는 형식이 컴파일 타임에 개체의 멤버에 액세스  
  
1. 개체 변수를 선언 합니다 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다. (으로 변수 선언 `Object` 으로 선언 하는 것과 같습니다 <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     사용 하 여 `Option Strict On`에 정의 된 멤버에만 액세스할 수 있습니다는 <xref:System.Object> 클래스입니다.  
  
2. 멤버 액세스 연산자를 사용 하 여 (`.`) 간의 개체 변수 이름과 멤버 이름입니다.  
  
    ```  
    someControl.GetType()  
    ```  
  
     개체 변수에 할당 하는 모든 개체의 멤버에 액세스할 수를 설정 해야 `Option Strict Off`합니다. 이렇게 하면 컴파일러는 개체를 변수에 할당 하 여 지정된 된 멤버 노출 된다는 것을 보장할 수 없습니다. 개체에 액세스 하려는 멤버를 노출 하지 않습니다 경우는 <xref:System.MemberAccessException> 예외가 발생 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
