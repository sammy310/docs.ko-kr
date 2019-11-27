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
ms.openlocfilehash: 3867d433ea5f9a6effe70db0ff4162390fb50b5c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331465"
---
# <a name="data-types-of-operator-results-visual-basic"></a>연산자 결과의 데이터 형식(Visual Basic)
Visual Basic는 피연산자의 데이터 형식에 따라 작업의 결과 데이터 형식을 결정 합니다. 일부 경우에는 피연산자 중 하나 보다 큰 범위의 데이터 형식일 수 있습니다.  
  
## <a name="data-type-ranges"></a>데이터 형식 범위  
 가장 작은 숫자에서 가장 큰 데이터 형식의 범위는 다음과 같습니다.  
  
- [부울](../../../visual-basic/language-reference/data-types/boolean-data-type.md) -두 가지 가능한 값  
  
- [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) -256 가능한 정수 값  
  
- [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) -65536 (6.5 ... E + 4) 가능한 정수 값  
  
- [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) -4294967296 (4.2 ... E + 9) 가능한 정수 값  
  
- [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) -18446744073709551615 (1.8 ... E + 19) 가능한 정수 값  
  
- [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -1.5 ... e + 29 가능한 정수 값, 최대 범위 7.9 ... e + 28 (절대값)  
  
- [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) -최대 범위 3.4 ... E + 38 (절대값)  
  
- [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -최대 범위 1.7 ... E + 308 (절대값)  
  
 Visual Basic 데이터 형식에 대 한 자세한 내용은 [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)을 참조 하세요.  
  
 피연산자가 [Nothing](../../../visual-basic/language-reference/nothing.md)으로 계산 되는 경우 Visual Basic 산술 연산자는이를 0으로 처리 합니다.  
  
## <a name="decimal-arithmetic"></a>소수 연산  
 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식은 부동 소수점 또는 정수가 아닙니다.  
  
 `+`, `–`, `*`, `/`또는 `Mod` 작업의 피연산자 중 하나가 `Decimal`이 고 다른 피연산자가 `Single` 또는 `Double`되지 않은 경우 다른 피연산자를 Visual Basic로 확대 `Decimal`합니다. `Decimal`에서 작업을 수행 하 고, 결과 데이터 형식이 `Decimal`됩니다.  
  
## <a name="floating-point-arithmetic"></a>부동 소수점 산술  
 Visual Basic는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)에서 대부분의 부동 소수점 산술 연산을 수행 하며, 이러한 연산에 대해 가장 효율적인 데이터 형식입니다. 그러나 하나의 피연산자가 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 피연산자이 고 다른 피연산자가 `Double`되지 않은 경우에는 `Single`에서 작업을 수행 Visual Basic. 필요에 따라 각 피연산자를 작업 이전에 적절 한 데이터 형식으로 확대 하 고 결과에 해당 데이터 형식이 있습니다.  
  
### <a name="-and--operators"></a>/및 ^ 연산자  
 `/` 연산자는 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)및 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식에 대해서만 정의 됩니다. 작업을 수행 하기 전에 필요에 따라 각 피연산자를 적절 한 데이터 형식으로 확장 하 고 결과에 해당 데이터 형식이 Visual Basic.  
  
 다음 표에서는 `/` 연산자에 대 한 결과 데이터 형식을 보여 줍니다. 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|모든 정수 형식|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|모든 정수 형식|Decimal|Single|Double|Double|  
  
 `^` 연산자는 `Double` 데이터 형식에 대해서만 정의 됩니다. 작업을 수행 하기 전에 `Double` 하는 데 필요한 만큼 각 피연산자를 확장 하 고 결과 데이터 형식이 항상 `Double`Visual Basic 합니다.  
  
## <a name="integer-arithmetic"></a>정수 산술 연산  
 정수 연산의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라 집니다. 일반적으로 Visual Basic는 결과 데이터 형식을 결정 하는 데 다음 정책을 사용 합니다.  
  
- 이항 연산자의 두 피연산자의 데이터 형식이 같으면 결과에 해당 데이터 형식이 포함 됩니다. 예외는 `Boolean`되며 `Short`강제로 적용 됩니다.  
  
- 부호 없는 피연산자가 부호 있는 피연산자에 참여 하는 경우 결과에는 하나 이상의 피연산자로 된 범위 이상이 있는 부호 있는 형식이 있습니다.  
  
- 그렇지 않으면 결과에는 일반적으로 두 개의 피연산자 데이터 형식이 더 큽니다.  
  
 결과 데이터 형식이 피연산자 데이터 형식과 다를 수 있습니다.  
  
> [!NOTE]
> 결과 데이터 형식은 작업으로 인해 발생할 수 있는 모든 값을 저장할 수 있을 만큼 크지 않습니다. 결과 데이터 형식에 대해 값이 너무 크면 <xref:System.OverflowException> 예외가 발생할 수 있습니다.  
  
### <a name="unary--and--operators"></a>단항 + 및 – 연산자  
 다음 표에서는 두 개의 단항 연산자, `+` 및 `–`에 대 한 결과 데이터 형식을 보여 줍니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|단항 `+`|Short|SByte|바이트|Short|UShort|정수|UInteger|Long|ULong|  
|단항 `–`|Short|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< 및 > > 연산자  
 다음 표에서는 두 비트 시프트 연산자, `<<` 및 `>>`에 대 한 결과 데이터 형식을 보여 줍니다. Visual Basic은 각 비트 시프트 연산자를 왼쪽 피연산자 (이동할 비트 패턴)에서 단항 연산자로 처리 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|바이트|Short|UShort|정수|UInteger|Long|ULong|  
  
 왼쪽 피연산자가 `Decimal`, `Single`, `Double`또는 `String`이면 작업 전에 Visual Basic로 변환 하려고 시도 하 고 결과 데이터 형식은 `Long` 됩니다.`Long` 오른쪽 피연산자 (이동할 비트 위치 수)는 `Integer` 또는 `Integer`로 확대 되는 형식 이어야 합니다.  
  
### <a name="binary----and-mod-operators"></a>Binary +, –, \*및 Mod 연산자  
 다음 표에서는 이진 `+` 및 `–` 연산자와 `*` 및 `Mod` 연산자에 대 한 결과 데이터 형식을 보여 줍니다. 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
|`Byte`|Short|Short|바이트|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Decimal|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\\ 연산자  
 다음 표에서는 `\` 연산자에 대 한 결과 데이터 형식을 보여 줍니다. 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`Byte`|Short|Short|바이트|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 `\` 연산자의 피연산자 중 하나가 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)인 경우 Visual Basic은 작업 전에 [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) 으로 변환 하려고 시도 하 고 결과 데이터 형식은 `Long`됩니다.  
  
## <a name="relational-and-bitwise-comparisons"></a>관계형 및 비트 비교  
 관계형 작업의 결과 데이터 형식 (`=`, `<>`, `<`, `>`, `<=`, `>=`)은 항상 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)`Boolean`입니다. `OrElse`피연산자에 대 한 논리 연산 (`And`, `AndAlso`, `Not`, `Or`, `Xor`, `Boolean`)의 경우에도 마찬가지입니다.  
  
 비트 논리 연산의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라 집니다. `AndAlso` 및 `OrElse`는 Visual Basic `Boolean`에 대해서만 정의 되며 작업을 수행 하기 전에 필요에 따라 각 피연산자를 `Boolean`로 변환 합니다.  
  
### <a name="-----and--operators"></a>=, < >, \<, >, \<= 및 > = 연산자  
 두 피연산자가 모두 `Boolean`되는 경우 Visual Basic `True` `False`보다 작은 것으로 간주 합니다. 숫자 형식이 `String`와 비교 되는 경우 Visual Basic은 작업 전에 `String`를 `Double`으로 변환 하려고 시도 합니다. `Char` 또는 `Date` 피연산자는 동일한 데이터 형식의 다른 피연산자와만 비교할 수 있습니다. 결과 데이터 형식은 항상 `Boolean`입니다.  
  
### <a name="bitwise-not-operator"></a>비트 Not 연산자  
 다음 표에서는 비트 `Not` 연산자에 대 한 결과 데이터 형식을 보여 줍니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|부울|SByte|바이트|Short|UShort|정수|UInteger|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`, `Double`또는 `String`이면 작업 전에 Visual Basic로 변환 하려고 시도 하 고 결과 데이터 형식은 `Long` 됩니다.`Long`  
  
### <a name="bitwise-and-or-and-xor-operators"></a>비트 and, Or 및 Xor 연산자  
 다음 표에서는 비트 `And`, `Or`및 `Xor` 연산자에 대 한 결과 데이터 형식을 보여 줍니다. 이 테이블은 대칭입니다. 피연산자 데이터 형식의 지정 된 조합에 대해 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|부울|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`Byte`|Short|Short|바이트|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`, `Double`또는 `String`이면 작업 전에 Visual Basic로 변환 하려고 시도 하 고, 결과 데이터 형식은 피연산자가 이미 `Long` 된 것과 동일 합니다.`Long`  
  
## <a name="miscellaneous-operators"></a>기타 연산자  
 `&` 연산자는 `String` 피연산자를 연결 하는 경우에만 정의 됩니다. Visual Basic는 필요에 따라 각 피연산자를 연산 전에 `String` 변환 하 고 결과 데이터 형식은 항상 `String`합니다. `&` 연산자의 목적을 위해 `String`에 대 한 모든 변환은 `Option Strict` `On`되더라도 확대 된 것으로 간주 됩니다.  
  
 `Is` 및 `IsNot` 연산자는 두 피연산자가 모두 참조 형식 이어야 합니다. `TypeOf`...`Is` 식에는 첫 번째 피연산자가 참조 형식 이어야 하 고 두 번째 피연산자는 데이터 형식의 이름 이어야 합니다. 이러한 모든 경우에는 결과 데이터 형식이 `Boolean`.  
  
 `Like` 연산자는 `String` 피연산자의 패턴 일치에 대해서만 정의 됩니다. Visual Basic는 필요에 따라 각 피연산자를 연산 전에 `String`으로 변환 하려고 합니다. 결과 데이터 형식은 항상 `Boolean`입니다.  
  
## <a name="see-also"></a>참고 항목

- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Visual Basic의 비교 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [연산자](../../../visual-basic/language-reference/operators/index.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
