---
description: '자세한 정보: 연산자 오버로드'
title: 연산자 오버로드
ms.date: 10/22/2008
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: e6552f35081afa542e4dc14239206a63c7c1bd59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713327"
---
# <a name="operator-overloads"></a>연산자 오버로드

연산자 오버로드를 사용하면 프레임워크 형식이 기본 제공 언어 기본 형식인 것처럼 표시할 수 있습니다.

 연산자 오버로드는 상황에 따라 허용되고 유용하지만 주의해서 사용해야 합니다. 프레임워크 디자이너에서 간단한 메서드가 되어야 하는 작업에 연산자를 사용하기 시작하는 경우처럼 연산자 오버로드가 남용되는 경우가 많습니다. 다음 지침은 연산자 오버로드를 사용할 시기 및 방법을 결정하는 데 도움이 됩니다.

 ❌ 기본(기본 제공) 형식처럼 보여야 하는 형식을 제외하고는 연산자 오버로드를 정의하면 안 됩니다.

 ✔️ 기본 형식처럼 보여야 하는 형식에서는 연산자 오버로드를 정의하는 것이 좋습니다.

 예를 들어 <xref:System.String?displayProperty=nameWithType>에는 `operator==` 및 `operator!=`가 정의되어 있습니다.

 ✔️ 숫자를 나타내는 구조체에는 연산자 오버로드를 정의하세요(예: <xref:System.Decimal?displayProperty=nameWithType>).

 ❌ 연산자 오버로드를 정의할 때는 잔꾀를 부리지 마세요.

 연산자 오버로드는 작업의 결과가 즉시 명확하게 나타나는 경우에 유용합니다. 예를 들어 다른 `DateTime`에서 하나의 <xref:System.DateTime>을 빼고 <xref:System.TimeSpan>을 가져오는 것이 좋습니다. 그러나 논리 공용 구조체 연산자를 사용하여 두 데이터베이스 쿼리를 통합하거나 시프트 연산자를 사용하여 스트림에 쓰는 것은 적합하지 않습니다.

 ❌ 피연산자 중 하나 이상이 오버로드를 정의하는 형식이 아닐 경우 연산자 오버로드를 제공하지 마세요.

 ✔ 대칭 방식으로 연산자를 오버로드하세요.

 예를 들어 `operator==`를 오버로드하는 경우 `operator!=`도 오버로드해야 합니다. 마찬가지로 `operator<`를 오버로드하는 경우 `operator>`도 오버로드해야 합니다.

 ✔️ 오버로드된 각 연산자에 해당하는 식별 이름과 함께 메서드를 제공하는 것이 좋습니다.

 많은 언어에서 연산자 오버로드를 지원하지 않습니다. 따라서 연산자를 오버로드하는 형식에는 동일한 기능을 제공하는 적절한 도메인 특정 이름과 함께 보조 메서드를 포함하는 것이 좋습니다.

 다음 표에는 연산자 목록과 해당하는 메서드 식별 이름이 나와 있습니다.

|C# 연산자 기호|메타데이터 이름|친숙한 이름|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a>Operator == 오버로드

 `operator ==` 오버로드는 매우 복잡합니다. 연산자의 의미 체계는 <xref:System.Object.Equals%2A?displayProperty=nameWithType>과 같은 여러 다른 멤버와 호환되어야 합니다.

### <a name="conversion-operators"></a>변환 연산자

 변환 연산자는 형식 간의 변환을 허용하는 단항 연산자입니다. 연산자는 피연산자 또는 반환 형식에서 정적 멤버로 정의해야 합니다. 변환 연산자에는 암시적과 명시적이라는 두 가지 형식이 있습니다.

 ❌ 최종 사용자가 이러한 변환을 명확하게 예상하지 못하는 경우 변환 연산자를 제공하지 마세요.

 ❌ 형식의 도메인 외부에서 변환 연산자를 정의하지 마세요.

 예를 들어 <xref:System.Int32>, <xref:System.Double>, <xref:System.Decimal>은 모두 숫자 형식이지만 <xref:System.DateTime>은 그렇지 않습니다. 따라서 `Double(long)`을 `DateTime`으로 변환하는 변환 연산자가 없어야 합니다. 이런 경우에는 생성자를 사용하는 것이 더 좋습니다.

 ❌ 변환이 잠재적으로 손실될 수 있는 경우 암시적 변환 연산자를 제공하지 마세요.

 예를 들어 `Double`은 `Int32`보다 범위가 더 넓기 때문에 `Double`에서 `Int32`로 암시적 변환이 없어야 합니다. 명시적 변환 연산자는 변환이 잠재적으로 손실될 수 있는 경우에도 제공할 수 있습니다.

 ❌ 암시적 캐스트에서 예외를 throw하지 마세요.

 최종 사용자는 변환이 수행되고 있다는 사실을 알 수 없기 때문에 발생하고 있는 상황을 이해하기가 매우 어렵습니다.

 ✔️ 캐스트 연산자 호출로 변환이 손실되고 연산자 계약에서는 손실된 변환을 허용하지 않는 경우 <xref:System.InvalidCastException?displayProperty=nameWithType>을 throw하세요.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](member.md)
- [프레임워크 디자인 지침](index.md)
