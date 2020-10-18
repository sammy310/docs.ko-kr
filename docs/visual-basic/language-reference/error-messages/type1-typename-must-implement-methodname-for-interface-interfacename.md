---
title: <type1>'<typename>'은 '<interfacename>' 인터페이스에 대한 '<methodname>'을 구현해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 68c6f65e6be229cc74458fa56fe3d3aa889c18f7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161870"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a>BC30149: \<type1> ' ' \<typename> 은 ' ' \<methodname> 인터페이스에 대해 ' '을 (를) 구현 해야 합니다. \<interfacename>

클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지는 않습니다. 인터페이스의 모든 멤버를 구현 해야 합니다.

 **오류 ID:** BC30149

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 인터페이스에 정의 된 것과 동일한 이름 및 서명을 사용 하 여 프로시저를 선언 합니다. 적어도 `End Function` 또는 문을 포함 해야 `End Sub` 합니다.

2. `Implements`또는 문의 끝에 절을 추가 `Function` `Sub` 합니다. 예를 들면 다음과 같습니다.

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a>참고 항목

- [Implements 문](../statements/implements-statement.md)
- [인터페이스](../../programming-guide/language-features/interfaces/index.md)
