---
title: 클래스의 명시적 인스턴스가 없는 공유 메서드 또는 공유 멤버 이니셜라이저에서는 클래스의 인스턴스 멤버를 참조할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: aad068b5857eb956ded63fa2a57cb163d3cf5c58
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322695"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>클래스의 명시적 인스턴스가 없는 공유 메서드 또는 공유 멤버 이니셜라이저에서는 클래스의 인스턴스 멤버를 참조할 수 없습니다.
공유 프로시저 내에서 클래스의 공유 되지 않은 멤버를 참조 하려고 했습니다. 다음 예제에서는 이러한 상황을 보여 줍니다.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 위의 예에서 대입문은 `x = 10` 이 오류 메시지를 생성 합니다. 공유 프로시저 인스턴스 변수를 액세스 하려고 합니다. 때문입니다.  
  
 변수의 `x` 으로 선언 하지 않은 인스턴스 멤버 이므로 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다. 클래스의 각 인스턴스에 `sample` 는 자체 개별 변수 `x`합니다. 특정 인스턴스에서 설정 하거나 값을 변경할 때 `x`, 값의 영향을 주지 않습니다 `x` 다른 인스턴스에 있습니다.  
  
 그러나 절차 `setX` 됩니다 `Shared` 클래스의 모든 인스턴스 간에 `sample`입니다. 즉, 클래스의 인스턴스 하나를 사용 하 여 연결 되지 않지만 대신 개별 인스턴스와 독립적으로 작동 합니다. 특정 인스턴스를 사용 하 여 연결 없음이 있어 `setX` 인스턴스 변수에 액세스할 수 없습니다. 경우에 작동 해야 `Shared` 변수입니다. 때 `setX` 설정 하거나, 새 값이 클래스의 모든 인스턴스에서 사용할 수 있는 공유 변수 값을 변경 합니다.  
  
 **오류 ID:** BC30369  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 멤버 클래스의 모든 인스턴스 간에 공유 하거나 각 인스턴스에 대 한 개별 유지 여부를 결정 합니다.  
  
2. 모든 인스턴스 간에 공유 멤버의 단일 복사본을 원한다 면 추가 된 `Shared` 멤버 선언에는 키워드입니다. 유지 된 `Shared` 프로시저 선언에서 키워드입니다.  
  
3. 멤버의 개별 자체 복사본을 각 인스턴스를 원하는 경우 지정 하지 않으면 `Shared` 멤버 선언에 대 한 합니다. 제거 된 `Shared` 프로시저 선언에서 키워드입니다.  
  
## <a name="see-also"></a>참고자료

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
