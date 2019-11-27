---
title: '방법: 변수의 사용 가능성 제어'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 886b57909cf6ba25dbaceea5c5f06eb4e3ba6f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345386"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>방법: 변수의 사용 가능성 제어(Visual Basic)
*액세스 수준을*지정 하 여 변수의 가용성을 제어 합니다. 액세스 수준에 따라 변수에 대 한 읽기 또는 쓰기 권한이 있는 코드가 결정 됩니다.  
  
- *멤버 변수* (모듈 수준 및 프로시저 외부에서 정의 됨)는 기본적으로 공용 액세스로 사용 됩니다. 즉, 해당 변수를 볼 수 있는 모든 코드에서 액세스할 수 있습니다. 액세스 한정자를 지정 하 여이를 변경할 수 있습니다.  
  
- *지역 변수* (프로시저 내에서 정의 됨)에는 공용 액세스 권한이 있지만 프로시저 내의 코드만 액세스할 수 있는 명목상 있습니다. 지역 변수의 액세스 수준을 변경할 수는 없지만 해당 변수의 액세스 수준을 포함 하는 프로시저의 액세스 수준을 변경할 수는 있습니다.  
  
 자세한 내용은 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.  
  
## <a name="private-and-public-access"></a>개인 및 공용 액세스  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>모듈, 클래스 또는 구조체 내 에서만 변수를 액세스할 수 있도록 하려면  
  
1. 모듈, 클래스 또는 구조체 내에서 프로시저 외부에 있는 변수에 [Dim 문을](../../../../visual-basic/language-reference/statements/dim-statement.md) 추가 합니다.  
  
2. [Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 `Dim` 문에 포함 합니다.  
  
     모듈, 클래스 또는 구조체 내의 어디에서 나 변수를 읽거나 쓸 수 있습니다.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>변수를 볼 수 있는 모든 코드에서 액세스할 수 있도록 하려면  
  
1. 멤버 변수의 경우 모듈, 클래스 또는 구조체 내에 있는 변수에 대 한 `Dim` 문을 프로시저 외부에 저장 합니다.  
  
2. `Dim` 문에 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 포함 합니다.  
  
     어셈블리와 상호 작용 하는 모든 코드에서 변수를 읽거나 쓸 수 있습니다.  
  
 -또는-  
  
1. 지역 변수의 경우 프로시저 안에 변수에 대 한 `Dim` 문을 추가 합니다.  
  
2. `Dim` 문에는 `Public` 키워드를 포함 하지 마십시오.  
  
     프로시저 내의 어디에서 나 변수를 읽거나 쓸 수 있습니다.  
  
## <a name="protected-and-friend-access"></a>보호 및 Friend 액세스  
 변수의 액세스 수준을 해당 클래스 및 파생 클래스 또는 해당 어셈블리로 제한할 수 있습니다. 이러한 제한의 합집합을 지정 하 여 파생 클래스의 코드나 동일한 어셈블리에 있는 다른 위치의 코드에서 액세스할 수 있습니다. 동일한 선언에서 `Protected`와 `Friend` 키워드를 결합 하 여이 union을 지정 합니다.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>해당 클래스 및 파생 클래스 에서만 변수를 액세스할 수 있도록 하려면  
  
1. 프로시저 외부에 있는 변수에 대 한 `Dim` 문을 클래스 내부에 저장 합니다.  
  
2. `Dim` 문에 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) 키워드를 포함 합니다.  
  
     클래스 내 어디에서 나 클래스 내에서 파생 된 클래스 내에서 또는 파생 체인의 모든 클래스 외부에서 변수를 읽거나 쓸 수 있습니다.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>동일한 어셈블리 내 에서만 변수를 액세스할 수 있도록 하려면  
  
1. 모듈, 클래스 또는 구조체 내의 변수에 대 한 `Dim` 문을 프로시저 외부에 저장 합니다.  
  
2. [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 키워드를 `Dim` 문에 포함 합니다.  
  
     모듈, 클래스 또는 구조체의 모든 위치 뿐만 아니라 동일한 어셈블리의 모든 코드에서 변수를 읽거나 쓸 수 있습니다. 단, 어셈블리 외부에서는 읽을 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Public`, `Protected`, `Friend`, `Protected Friend`및 `Private` 액세스 수준을 사용 하 여 변수 선언을 보여 줍니다. `Dim` 문이 액세스 수준을 지정 하는 경우 `Dim` 키워드를 포함할 필요가 없습니다.  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 변수의 액세스 수준이 더 제한적 이면 악의적인 코드가이를 부적절 하 게 사용할 수 있는 가능성이 줄어듭니다.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../../visual-basic/language-reference/modifiers/private.md)
