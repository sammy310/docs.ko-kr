---
title: 연산자 결과의 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: b80508c5619770da0c7dc78003ff9d4847dd94d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371429"
---
# <a name="data-types-of-operator-results-visual-basic"></a>연산자 결과의 데이터 형식(Visual Basic)
Visual Basic는 피연산자의 데이터 형식에 따라 작업의 결과 데이터 형식을 결정 합니다. 일부 경우에는 피연산자 중 하나 보다 큰 범위의 데이터 형식일 수 있습니다.  
  
## <a name="data-type-ranges"></a>데이터 형식 범위  
 가장 작은 숫자에서 가장 큰 데이터 형식의 범위는 다음과 같습니다.  
  
- [부울](../data-types/boolean-data-type.md) -두 가지 가능한 값  
  
- [SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md) -256 가능한 정수 값  
  
- [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md) -65536 (6.5 ... E + 4) 가능한 정수 값  
  
- [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md) -4294967296 (4.2 ... E + 9) 가능한 정수 값  
  
- [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md) -18446744073709551615 (1.8 ... E + 19) 가능한 정수 값  
  
- [Decimal](../data-types/decimal-data-type.md) -1.5 ... e + 29 가능한 정수 값, 최대 범위 7.9 ... e + 28 (절대값)  
  
- [단일](../data-types/single-data-type.md) -최대 범위 3.4 ... E + 38 (절대값)  
  
- [Double](../data-types/double-data-type.md) -최대 범위 1.7 ... E + 308 (절대값)  
  
 Visual Basic 데이터 형식에 대 한 자세한 내용은 [데이터 형식](../data-types/index.md)을 참조 하세요.  
  
 피연산자가 [Nothing](../nothing.md)으로 계산 되는 경우 Visual Basic 산술 연산자는이를 0으로 처리 합니다.  
  
## <a name="decimal-arithmetic"></a>소수 연산  
 [Decimal](../data-types/decimal-data-type.md) 데이터 형식은 부동 소수점 또는 정수가 아닙니다.  
  
 ,,, 또는 연산의 피연산자 중 하나가 `+` `–` `*` `/` `Mod` 이 `Decimal` 고 다른 피연산자가 또는가 아니면 `Single` `Double` 다른 피연산자를로 넓힙니다 Visual Basic `Decimal` . 에서 작업을 수행 하 `Decimal` 고, 결과 데이터 형식은 `Decimal` 입니다.  
  
## <a name="floating-point-arithmetic"></a>부동 소수점 산술  
 Visual Basic는 [Double](../data-types/double-data-type.md)에서 대부분의 부동 소수점 산술 연산을 수행 하며, 이러한 연산에 대해 가장 효율적인 데이터 형식입니다. 그러나 하나의 피연산자가 [단일](../data-types/single-data-type.md) 피연산자이 고 다른 피연산자가이 아닌 경우 `Double` Visual Basic에서 연산을 수행 `Single` 합니다. 필요에 따라 각 피연산자를 작업 이전에 적절 한 데이터 형식으로 확대 하 고 결과에 해당 데이터 형식이 있습니다.  
  
### <a name="-and--operators"></a>/및 ^ 연산자  
 `/`연산자는 [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)및 [Double](../data-types/double-data-type.md) 데이터 형식에 대해서만 정의 됩니다. 작업을 수행 하기 전에 필요에 따라 각 피연산자를 적절 한 데이터 형식으로 확장 하 고 결과에 해당 데이터 형식이 Visual Basic.  
  
 다음 표에서는 연산자의 결과 데이터 형식을 보여 줍니다 `/` . 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|모든 정수 형식|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|모든 정수 형식|Decimal|Single|Double|Double|  
  
 `^`연산자는 데이터 형식에 대해서만 정의 됩니다 `Double` . Visual Basic는 작업 이전에 필요에 따라 각 피연산자를 확대 하 `Double` 고 결과 데이터 형식은 항상 `Double` 입니다.  
  
## <a name="integer-arithmetic"></a>정수 산술 연산  
 정수 연산의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라 집니다. 일반적으로 Visual Basic는 결과 데이터 형식을 결정 하는 데 다음 정책을 사용 합니다.  
  
- 이항 연산자의 두 피연산자의 데이터 형식이 같으면 결과에 해당 데이터 형식이 포함 됩니다. 예외는로 강제 적용 되는입니다 `Boolean` `Short` .  
  
- 부호 없는 피연산자가 부호 있는 피연산자에 참여 하는 경우 결과에는 하나 이상의 피연산자로 된 범위 이상이 있는 부호 있는 형식이 있습니다.  
  
- 그렇지 않으면 결과에는 일반적으로 두 개의 피연산자 데이터 형식이 더 큽니다.  
  
 결과 데이터 형식이 피연산자 데이터 형식과 다를 수 있습니다.  
  
> [!NOTE]
> 결과 데이터 형식은 작업으로 인해 발생할 수 있는 모든 값을 저장할 수 있을 만큼 크지 않습니다. <xref:System.OverflowException>결과 데이터 형식에 대해 값이 너무 크면 예외가 발생할 수 있습니다.  
  
### <a name="unary--and--operators"></a>단항 + 및 – 연산자  
 다음 표에서는 두 개의 단항 연산자 및에 대 한 결과 데이터 형식을 보여 줍니다 `+` `–` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|플러스`+`|Short|SByte|Byte|Short|UShort|정수|UInteger|long|ULong|  
|플러스`–`|Short|SByte|Short|Short|정수|정수|long|long|Decimal|  
  
### <a name="-and--operators"></a><\< and >> 연산자  
 다음 표에서는 두 비트 시프트 연산자 및에 대 한 결과 데이터 형식을 보여 줍니다 `<<` `>>` . Visual Basic은 각 비트 시프트 연산자를 왼쪽 피연산자 (이동할 비트 패턴)에서 단항 연산자로 처리 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|정수|UInteger|long|ULong|  
  
 왼쪽 피연산자가 `Decimal` , `Single` , `Double` Visual Basic 또는 이면 `String` 작업 이전으로 변환 하려고 시도 하 `Long` 고, 결과 데이터 형식은 `Long` 입니다. 오른쪽 피연산자 (이동할 비트 위치 수)는 `Integer` 이거나로 확대 되는 형식 이어야 합니다 `Integer` .  
  
### <a name="binary----and-mod-operators"></a>Binary +, –, \* 및 Mod 연산자  
 다음 표에서는 이진 `+` 및 `–` 연산자와 `*` 및 연산자에 대 한 결과 데이터 형식을 보여 줍니다 `Mod` . 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|long|long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|long|long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|long|long|Decimal|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|long|long|Decimal|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\\ 연산자  
 다음 표에서는 연산자의 결과 데이터 형식을 보여 줍니다 `\` . 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|long|long|long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|long|long|long|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|long|long|long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 연산자의 피연산자 중 하나가 `\` [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)또는 Visual Basic [Double](../data-types/double-data-type.md)인 경우 작업 이전에 [Long](../data-types/long-data-type.md) 으로 변환 하려고 시도 하 고 결과 데이터 형식은 `Long` 입니다.  
  
## <a name="relational-and-bitwise-comparisons"></a>관계형 및 비트 비교  
 관계형 작업의 결과 데이터 형식 ( `=` , `<>` ,,, `<` `>` `<=` ,)은 `>=` 항상 `Boolean` [Boolean 데이터 형식](../data-types/boolean-data-type.md)입니다. 연산자의 논리적 연산 ( `And` ,,,, `AndAlso` `Not` `Or` `OrElse` , `Xor` ) `Boolean` 에 대해서도 마찬가지입니다.  
  
 비트 논리 연산의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라 집니다. 및는 `AndAlso` `OrElse` 에 대해서만 정의 되며 `Boolean` , Visual Basic `Boolean` 작업을 수행 하기 전에 필요에 따라 각 피연산자를 변환 합니다.  
  
### <a name="-----and--operators"></a>=,  <>, \<, > , \<=, and > = 연산자  
 두 피연산자가 모두 이면 `Boolean` Visual Basic `True` 보다 작은 것으로 간주 `False` 합니다. 숫자 형식이 Visual Basic와 비교 되는 경우 `String` `String` 작업을 수행 하기 전에를로 변환 하려고 합니다 `Double` . `Char`또는 `Date` 피연산자는 동일한 데이터 형식의 다른 피연산자와만 비교할 수 있습니다. 결과 데이터 형식은 항상 `Boolean` 입니다.  
  
### <a name="bitwise-not-operator"></a>비트 Not 연산자  
 다음 표에서는 비트 연산자의 결과 데이터 형식을 보여 줍니다 `Not` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|부울|SByte|Byte|Short|UShort|정수|UInteger|long|ULong|  
  
 피연산자가,, `Decimal` `Single` Visual Basic 또는 인 경우 `Double` `String` 작업 이전으로 변환 하려고 시도 하 `Long` 고, 결과 데이터 형식은 `Long` 입니다.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>비트 and, Or 및 Xor 연산자  
 다음 표에서는 비트 `And` , 및 연산자에 대 한 결과 데이터 형식을 보여 줍니다 `Or` `Xor` . 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|부울|SByte|Short|Short|정수|정수|long|long|long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|long|long|long|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|long|long|long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 피연산자가 `Decimal` , `Single` , Visual Basic 또는 이면이를 `Double` `String` 작업 이전으로 변환 하려고 시도 하 `Long` 고, 결과 데이터 형식은 피연산자가 이미 있는 것과 동일 합니다 `Long` .  
  
## <a name="miscellaneous-operators"></a>기타 연산자  
 `&`연산자는 피연산자 연결에 대해서만 정의 됩니다 `String` . Visual Basic는 작업 이전에 필요에 따라 각 피연산자를 변환 `String` 하 고 결과 데이터 형식은 항상 `String` 입니다. 연산자의 목적에 맞게 `&` 를로 변환 하는 것은 `String` 가 인 경우에도 확대/축소 된 것으로 간주 됩니다 `Option Strict` `On` .  
  
 `Is`및 `IsNot` 연산자는 두 피연산자가 모두 참조 형식 이어야 합니다. `TypeOf`... 식에는 `Is` 첫 번째 피연산자가 참조 형식 이어야 하 고 두 번째 피연산자는 데이터 형식의 이름 이어야 합니다. 이러한 모든 경우에 결과 데이터 형식은 `Boolean` 입니다.  
  
 `Like`연산자는 피연산자의 패턴 일치에 대해서만 정의 됩니다 `String` . Visual Basic는 작업 이전에 필요에 따라 각 피연산자를 변환 하려고 시도 `String` 합니다. 결과 데이터 형식은 항상 `Boolean` 입니다.  
  
## <a name="see-also"></a>참고 항목

- [데이터 형식](../data-types/index.md)
- [연산자 및 식](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Visual Basic의 산술 연산자](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [연산자](index.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [산술 연산자](arithmetic-operators.md)
- [비교 연산자](comparison-operators.md)
- [Option Strict 문](../statements/option-strict-statement.md)
