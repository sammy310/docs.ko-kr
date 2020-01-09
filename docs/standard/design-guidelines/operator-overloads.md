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
ms.openlocfilehash: 4cea3c17de40a873d977223f36b6dcef4f2c2d78
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709142"
---
# <a name="operator-overloads"></a>연산자 오버로드
연산자 오버 로드를 사용 하면 프레임 워크 형식이 기본 제공 언어 기본 형식인 것 처럼 표시 됩니다.  
  
 일부 경우에는 허용 되 고 유용 하지만 연산자 오버 로드는 신중 하 게 사용 해야 합니다. 프레임 워크 디자이너에서 간단한 메서드로 사용 해야 하는 작업에 대해 연산자를 사용 하기 시작 하는 경우와 같이 연산자 오버 로드가 악용 되는 경우가 많습니다. 다음 지침은 연산자 오버 로드를 사용 하는 시기 및 방법을 결정 하는 데 도움이 됩니다.  
  
 **X AVOID** 기본 (기본 제공) 형식 느낌을 해야 하는 형식을 제외 하 고 연산자 오버 로드를 정의 합니다.  
  
 **✓ CONSIDER** 기본 형식 처럼 있어야 하는 형식에서 연산자 오버 로드를 정의 합니다.  
  
 예를 들어 <xref:System.String?displayProperty=nameWithType>에는 `operator==` 및 `operator!=` 정의 되어 있습니다.  
  
 **✓ DO** 번호를 나타내는 구조체에서 연산자 오버 로드를 정의 (예: <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X DO NOT** 연산자 오버 로드를 정의 하는 경우 간단한 수 있습니다.  
  
 연산자 오버 로드는 작업의 결과를 즉시 알 수 있는 경우에 유용 합니다. 예를 들어 다른 `DateTime`에서 한 <xref:System.DateTime>를 빼서 <xref:System.TimeSpan>를 가져올 수 있다는 것이 좋습니다. 그러나 논리 union 연산자를 사용 하 여 두 데이터베이스 쿼리를 통합 하거나 시프트 연산자를 사용 하 여 스트림에 쓰려면 적절 하지 않습니다.  
  
 **X DO NOT** 연산자는 오버 로드를 정의 하는 형식은 피연산자 중 하나 이상을 아닌 경우 오버 로드를 제공 합니다.  
  
 **✓ DO** 대칭 방식에서 연산자를 오버 로드 합니다.  
  
 예를 들어 `operator==`오버 로드 하는 경우 `operator!=`도 오버 로드 해야 합니다. 마찬가지로 `operator<`오버 로드 하는 경우 `operator>`도 오버 로드 해야 합니다.  
  
 **✓ CONSIDER** 각 오버 로드 된 연산자에 해당 하는 이름을 가진 메서드를 제공 합니다.  
  
 많은 언어에서 연산자 오버 로드를 지원 하지 않습니다. 따라서 연산자를 오버 로드 하는 형식에는 동등한 기능을 제공 하는 적절 한 도메인별 이름을 가진 보조 메서드가 포함 되는 것이 좋습니다.  
  
 다음 표에는 연산자 목록과 해당 하는 친숙 한 메서드 이름이 나와 있습니다.  
  
|C#연산자 기호|메타 데이터 이름|이름|  
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
  
### <a name="overloading-operator-"></a>오버 로드 연산자 = =  
 `operator ==` 오버 로드는 매우 복잡 합니다. 연산자의 의미 체계는 <xref:System.Object.Equals%2A?displayProperty=nameWithType>같은 다른 여러 멤버와 호환 되어야 합니다.  
  
### <a name="conversion-operators"></a>변환 연산자  
 변환 연산자는 한 형식에서 다른 형식으로의 변환을 허용 하는 단항 연산자입니다. 연산자는 피연산자 또는 반환 형식에서 정적 멤버로 정의 되어야 합니다. 변환 연산자에는 암시적 및 명시적 이라는 두 가지 유형이 있습니다.  
  
 **X DO NOT** 이러한 변환의 최종 사용자가 예상 되는 것은 명확 하 게 경우 변환 연산자를 제공 합니다.  
  
 **X DO NOT** 형식의 도메인 외부에서 변환 연산자를 정의 합니다.  
  
 예를 들어 <xref:System.Int32>, <xref:System.Double>및 <xref:System.Decimal>는 모두 숫자 형식이 며 <xref:System.DateTime>는 그렇지 않습니다. 따라서 `Double(long)` `DateTime`으로 변환 하는 변환 연산자는 없어야 합니다. 이 경우 생성자는 기본 설정입니다.  
  
 **X DO NOT** 변환이 손실 될 수 있는 경우에 암시적 변환 연산자를 제공 합니다.  
  
 예를 들어 `Double`의 범위가 `Int32`보다 넓기 때문에 `Double`에서 `Int32`로의 암시적 변환이 되어서는 안 됩니다. 변환이 잠재적으로 손실 될 수 있는 경우에도 명시적 변환 연산자를 제공할 수 있습니다.  
  
 **X DO NOT** 암시적 캐스트에서 예외를 throw 합니다.  
  
 최종 사용자는 변환이 발생 하는 것을 인식 하지 못할 수 있으므로 최종 사용자가 원인을 이해 하는 것은 매우 어렵습니다.  
  
 **✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> 하면 캐스트 연산자에 대 한 호출 손실 변환와 연산자의 계약 손실 변환을 허용 하지 않습니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
