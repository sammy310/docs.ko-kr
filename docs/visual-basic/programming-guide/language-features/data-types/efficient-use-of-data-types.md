---
title: 데이터 형식의 효율적 사용(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 0b517bca3a9e296eb891e30df91c1d32eb357432
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907220"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>데이터 형식의 효율적 사용(Visual Basic)
데이터 형식 없이 선언 된 변수와 선언 되지 않은 변수 할당 되는 `Object` 데이터 형식입니다. 이 사용 하면 쉽게 프로그램을 신속 하 게 작성할 수 있지만 느리게 실행 되기를 발생할 수 있습니다.  
  
## <a name="strong-typing"></a>강력한 형식화  
 모든 변수에 대 한 데이터 형식을 지정 하는 이라고 *강력한 형식화*합니다. 강력한 형식 지정을 사용 하 여에 몇 가지 이점이 있습니다.  
  
- 변수에 대 한 IntelliSense 지원을 수 있습니다. 이렇게 하면 코드에서 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.  
  
- 이 컴파일러에서 형식 검사 하는 작업을 활용 합니다. 이 문은 런타임에 오버플로 같은 오류로 인해 실패할 수 있는 catch 합니다. 또한 지원 하지 않는 개체에 메서드 호출을 catch 합니다.  
  
- 코드의 더 빠른 실행에서 발생합니다.  
  
## <a name="most-efficient-data-types"></a>가장 효율적인 데이터 형식  
 분수를 포함 하지 않은 변수는 정수 데이터 형식의 비정 수 형식 보다 더 효율적입니다. Visual basic에서는 `Integer` 및 `UInteger` 은 가장 효율적인 숫자 유형입니다.  
  
 소수에 `Double` 가장 효율적인 데이터 형식 이므로 현재 플랫폼의 프로세서에서 배정밀도 부동 소수점 작업을 수행 합니다. 그러나 작업과 `Double` 와 같은 정수 계열 형식과 마찬가지로 빠르지 않습니다 `Integer`합니다.  
  
## <a name="specifying-data-type"></a>데이터 형식 지정  
 사용 된 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 특정 형식의 변수를 선언 합니다. 해당 액세스 수준을 사용 하 여 동시에 지정할 수 있습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md)를 [보호 된](../../../../visual-basic/language-reference/modifiers/protected.md)를 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 에서처럼 키워드는 다음 예입니다.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>문자 변환  
 합니다 `AscW` 및 `ChrW` 함수는 유니코드에서 작동 합니다. 우선적으로 사용 해야 `Asc` 고 `Chr`, 내부 및 외부로 유니코드 변환 해야 하는 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [숫자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [IntelliSense 사용](/visualstudio/ide/using-intellisense)
