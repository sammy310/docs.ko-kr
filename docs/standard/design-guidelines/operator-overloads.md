---
title: 연산자 오버로드
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401222"
---
# <a name="operator-overloads"></a>연산자 오버로드
연산자 오버로드를 사용하면 프레임워크 형식이 기본 제공 언어 기본 요소인 것처럼 표시될 수 있습니다.

 경우에 따라 허용되고 유용하지만 작업자 오버로드를 신중하게 사용해야 합니다. 프레임워크 디자이너가 간단한 메서드여야 하는 작업에 연산자를 사용하기 시작한 경우와 같이 연산자 오버로드가 악용되는 경우가 많습니다. 다음 지침은 연산자 오버로드를 사용할 시기와 방법을 결정하는 데 도움이 됩니다.

 ❌기본(기본 제공) 형식처럼 느껴야 하는 형식을 제외하고 연산자 오버로드를 정의하지 마십시오.

 ✔️ 기본 형식처럼 느껴야 하는 형식에서 연산자 오버로드를 정의하는 것을 고려합니다.

 예를 <xref:System.String?displayProperty=nameWithType> 들어, `operator==` `operator!=` 있고 정의한다.

 do ✔️ 숫자를 나타내는 구조체에서 연산자 오버로드를 정의합니다(예: <xref:System.Decimal?displayProperty=nameWithType>).

 ❌연산자 오버로드를 정의할 때 귀여워하지 마십시오.

 연산자 오버로드는 작업 결과가 무엇인지 즉시 알 수 있는 경우에 유용합니다. 예를 들어, 다른 <xref:System.DateTime> `DateTime` 에서 하나를 빼고 <xref:System.TimeSpan>를 얻을 수 있는 것이 합리적입니다. 그러나 논리 공용 구조자 연산자 두 개의 데이터베이스 쿼리를 통합하거나 shift 연산자에서 스트림에 쓰는 것은 적절하지 않습니다.

 ❌미연산자 중 하나 이상이 오버로드를 정의하는 형식이 아니면 작업자 오버로드를 제공하지 마십시오.

 ✔️ 대칭 방식으로 연산자 과부하를 수행합니다.

 예를 들어 , 에 `operator==`과부하가 가하면 `operator!=`을 오버로드해야 합니다. 마찬가지로 에 과부하가 `operator<`두는 경우 `operator>`및 이에 대해서도 오버로드해야 합니다.

 ✔️ 각 오버로드 연산자에 해당하는 친숙한 이름을 제공하는 방법을 고려하십시오.

 대부분의 언어는 연산자 오버로드를 지원하지 않습니다. 따라서 오버로드 연산자가 포함된 형식에는 동등한 기능을 제공하는 적절한 도메인 별 이름이 있는 보조 메서드가 포함되는 것이 좋습니다.

 다음 표에는 연산자 목록과 해당 친숙한 메서드 이름이 포함되어 있습니다.

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

### <a name="overloading-operator-"></a>과부하 연산자 ==
 오버로드는 `operator ==` 매우 복잡합니다. 연산자의 의미체계는 와 같은 <xref:System.Object.Equals%2A?displayProperty=nameWithType>여러 다른 멤버와 호환되어야 합니다.

### <a name="conversion-operators"></a>변환 연산자
 변환 연산자는 한 형식에서 다른 유형으로 변환할 수 있는 비형식 연산자입니다. 연산자는 진연또는 반환 형식의 정적 멤버로 정의되어야 합니다. 변환 연산자는 암시적 연산자와 명시적 연산자의 두 가지 유형이 있습니다.

 ❌최종 사용자가 이러한 변환을 명확하게 예상하지 못하는 경우 변환 연산자에게 제공하지 마십시오.

 ❌형식의 도메인 외부의 변환 연산자는 정의하지 마십시오.

 예를 들어 <xref:System.Int32> <xref:System.Double>, <xref:System.Decimal> 은 및 모든 숫자 <xref:System.DateTime> 형식이지만 그렇지 않습니다. 따라서 a를 `Double(long)` `DateTime`로 변환하는 변환 연산자가 없어야 합니다. 이러한 경우 생성자가 선호됩니다.

 ❌변환이 손실될 수 있는 경우 암시적 변환 연산자는 제공하지 마십시오.

 예를 `Double` 들어 `Int32` `Double` `Int32`보다 넓은 범위를 가지므로 에서 암시적 변환이 없어야 합니다. 변환이 손실될 수 있는 경우에도 명시적 변환 연산자가 제공될 수 있습니다.

 ❌암시적 캐스트에서 예외를 throw하지 마십시오.

 최종 사용자가 전환이 일어나고 있다는 것을 인식하지 못할 수 있으므로 어떤 일이 일어나고 있는지 이해하기가 매우 어렵습니다.

 ✔️ <xref:System.InvalidCastException?displayProperty=nameWithType> throw하면 캐스트 연산자에 대한 호출로 인해 손실 변환이 발생하며 운영자의 계약은 손실 변환을 허용하지 않습니다.

 *2005년, 2009년 마이크로소프트© 판권.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
