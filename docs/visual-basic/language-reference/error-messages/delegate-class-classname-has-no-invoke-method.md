---
title: "'<classname>' 대리자 클래스에는 Invoke 메서드가 없으므로 이러한 형식의 식은 프로시저 호출의 대상일 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409714"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>'\<classname>' 대리자 클래스에는 Invoke 메서드가 없으므로 이러한 형식의 식은 프로시저 호출의 대상일 수 없습니다.
대리자 `Invoke` `Invoke` 클래스에서가 구현 되지 않았기 때문에 대리자를 통한 호출이 실패 했습니다.  
  
 **오류 ID:** BC30220  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 문을 사용 하 여 대리자 클래스의 인스턴스를 만들고 `Dim` 프로시저가 연산자를 사용 하 여 대리자 인스턴스에 할당 되었는지 확인 `AddressOf` 합니다.  
  
2. 대리자 클래스를 구현 하는 코드를 찾고 프로시저를 구현 하는지 확인 합니다 `Invoke` .  
  
## <a name="see-also"></a>참고 항목

- [대리자](../../programming-guide/language-features/delegates/index.md)
- [Delegate 문](../statements/delegate-statement.md)
- [AddressOf 연산자](../operators/addressof-operator.md)
- [Dim 문](../statements/dim-statement.md)
