---
description: '자세한 정보: 데이터 형식에 대 한 효율적인 사용 (Visual Basic)'
title: 데이터 형식의 효율적 사용
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
ms.openlocfilehash: e7660bbdec530ef18d663975e314d90b64e4b055
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476438"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>데이터 형식의 효율적 사용(Visual Basic)

선언 되지 않은 변수와 데이터 형식 없이 선언 된 변수에는 `Object` 데이터 형식이 할당 됩니다. 이렇게 하면 프로그램을 신속 하 게 작성할 수 있지만 더 느리게 실행 될 수 있습니다.

## <a name="strong-typing"></a>강력한 형식 지정

 모든 변수에 대 한 데이터 형식을 지정 하는 것을 *강력한 형식화* 라고 합니다. 강력한 형식화를 사용 하는 경우 다음과 같은 여러 이점이 있습니다.

- 변수에 대해 IntelliSense를 지원할 수 있습니다. 이렇게 하면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.

- 컴파일러 형식 검사를 활용 합니다. 이는 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 문을 catch 합니다. 또한 지원 하지 않는 개체의 메서드에 대 한 호출을 catch 합니다.

- 그러면 코드 실행 속도가 빨라집니다.

## <a name="most-efficient-data-types"></a>가장 효율적인 데이터 형식

 분수를 포함 하지 않는 변수의 경우 정수 계열 데이터 형식이 비정 수 형식 보다 더 효율적입니다. Visual Basic에서 `Integer` 및 `UInteger` 는 가장 효율적인 숫자 형식입니다.

 `Double`현재 플랫폼의 프로세서는 배정밀도로 부동 소수점 연산을 수행 하므로 소수 자릿수의 경우 가장 효율적인 데이터 형식입니다. 그러나를 사용 하 `Double` 는 연산은와 같은 정수 계열 형식과는 속도가 빠르지 않습니다 `Integer` .

## <a name="specifying-data-type"></a>데이터 형식 지정

 [Dim 문을](../../../language-reference/statements/dim-statement.md) 사용 하 여 특정 형식의 변수를 선언 합니다. 다음 예제와 같이 [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)또는 [Private](../../../language-reference/modifiers/private.md) 키워드를 사용 하 여 해당 액세스 수준을 동시에 지정할 수 있습니다.

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a>문자 변환

 `AscW`및 `ChrW` 함수는 유니코드로 작동 합니다. 및에 대 한 기본 설정에서 사용 해야 하며 `Asc` `Chr` ,이는 유니코드로 변환 해야 합니다.

## <a name="see-also"></a>추가 정보

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [데이터 형식](index.md)
- [숫자 데이터 형식](numeric-data-types.md)
- [변수 선언](../variables/variable-declaration.md)
- [IntelliSense 사용](/visualstudio/ide/using-intellisense)
