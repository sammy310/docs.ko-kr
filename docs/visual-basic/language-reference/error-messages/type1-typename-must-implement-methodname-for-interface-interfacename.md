---
title: <type1>'<typename>'은 '<interfacename>' 인터페이스에 대한 '<methodname>'을 구현해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 8bf8872277ec901e066a8b950aaf3e61babfcc48
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872105"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1>'\<typename>'은 '\<interfacename>' 인터페이스에 대한 '\<methodname>'을 구현해야 합니다.

클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지는 않습니다. 인터페이스의 모든 멤버를 구현 해야 합니다.  
  
 **오류 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 인터페이스에 정의 된 것과 동일한 이름 및 서명을 사용 하 여 프로시저를 선언 합니다. 적어도 `End Function` 또는 문을 포함 해야 `End Sub` 합니다.  
  
2. `Implements`또는 문의 끝에 절을 추가 `Function` `Sub` 합니다. 다음은 그 예입니다.  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>참조

- [Implements 문](../statements/implements-statement.md)
- [인터페이스](../../programming-guide/language-features/interfaces/index.md)
