---
title: <type1>'<typename>'구현 해야 합니다'<methodname>'interface'에 대 한<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304911"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1 >'\<typename >'를 구현 해야 합니다 '\<methodname >' 인터페이스에 대 한 '\<interfacename >'
클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지 않습니다. 인터페이스의 모든 멤버를 구현 해야 합니다.  
  
 **오류 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 동일한 이름 및 서명을 인터페이스에 정의 된 대로 사용 하 여 프로시저를 선언 합니다. 포함 해야 적어도 `End Function` 또는 `End Sub` 문입니다.  
  
2. 추가 `Implements` 의 끝에 절을 `Function` 또는 `Sub` 문입니다. 예를 들어:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>참고자료

- [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)
- [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
