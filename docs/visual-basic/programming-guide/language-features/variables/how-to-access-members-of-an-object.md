---
description: '자세히 알아보기: 방법: 개체의 멤버에 액세스 (Visual Basic)'
title: '방법: 개체의 멤버에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: b4aed213bbe520b7b7027acc146d0973f7273fd1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435527"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>방법: 개체의 멤버에 액세스(Visual Basic)

개체를 참조 하는 개체 변수를 사용 하는 경우 해당 개체의 멤버 (예: 메서드, 속성, 필드 및 이벤트)로 작업 하는 경우가 많습니다. 예를 들어 새 개체를 만든 후에는 <xref:System.Windows.Forms.Form> 해당 속성을 설정 <xref:System.Windows.Forms.Control.Text%2A> 하거나 메서드를 호출할 수 있습니다 <xref:System.Windows.Forms.Control.Focus%2A> .

## <a name="accessing-members"></a>멤버 액세스

개체를 참조 하는 변수를 통해 개체의 멤버에 액세스 합니다.

#### <a name="to-access-members-of-an-object"></a>개체의 멤버에 액세스 하려면

- `.`개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자 ()를 사용 합니다.

    ```vb
    currentText = newForm.Text
    ```

    멤버를 [공유](../../../language-reference/modifiers/shared.md)하는 경우 변수에 액세스할 필요가 없습니다.

## <a name="accessing-members-of-an-object-of-known-type"></a>알려진 형식 개체의 멤버에 액세스

컴파일 타임에 개체의 형식을 알고 있는 경우이를 참조 하는 변수에 대 한 *초기 바인딩을* 사용할 수 있습니다.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>컴파일 타임에 형식을 알고 있는 개체의 멤버에 액세스 하려면

1. 변수에 할당 하려는 개체의 형식이 되도록 개체 변수를 선언 합니다.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    를 사용 하 여 `Option Strict On` <xref:System.Windows.Forms.Form> 개체 (또는에서 파생 된 형식의 개체)만에 할당할 수 있습니다 <xref:System.Windows.Forms.Form> `extraForm` . 확대 변환으로 클래스 또는 구조체를 정의한 경우 `CType` <xref:System.Windows.Forms.Form> 해당 클래스 또는 구조체를에 할당할 수도 있습니다 `extraForm` .

2. `.`개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자 ()를 사용 합니다.

    ```vb
    extraForm.Show()
    ```

    설정에 관계 없이 클래스와 관련 된 모든 메서드와 속성에 액세스할 수 있습니다 <xref:System.Windows.Forms.Form> `Option Strict` .

## <a name="accessing-members-of-an-object-of-unknown-type"></a>알 수 없는 형식의 개체 멤버 액세스

컴파일 타임에 개체 형식을 알 수 없는 경우이를 참조 하는 모든 변수에 대해 *런타임에 바인딩을* 사용 해야 합니다.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>컴파일 타임에 형식을 알 수 없는 개체의 멤버에 액세스 하려면

1. 개체 변수를 [개체 데이터 형식](../../../language-reference/data-types/object-data-type.md)으로 선언 합니다. 변수를로 선언 하는 것은로 선언 하는 것과 `Object` 같습니다 <xref:System.Object?displayProperty=nameWithType> .

    ```vb
    Dim someControl As Object
    ```

    `Option Strict On`에서는 클래스에 정의 된 멤버에만 액세스할 수 있습니다 <xref:System.Object> .

2. `.`개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자 ()를 사용 합니다.

    ```vb
    someControl.GetType()
    ```

    개체 변수에 할당 하는 개체의 멤버에 액세스할 수 있으려면를 설정 해야 합니다 `Option Strict Off` . 이 작업을 수행 하는 경우 컴파일러는 지정 된 멤버가 변수에 할당 한 개체에 의해 노출 되는 것을 보장할 수 없습니다. 개체에서 액세스 하려는 멤버를 노출 하지 않는 경우 <xref:System.MemberAccessException> 예외가 발생 합니다.

## <a name="see-also"></a>추가 정보

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [개체 변수](object-variables.md)
- [개체 변수 선언](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Option Strict 문](../../../language-reference/statements/option-strict-statement.md)
