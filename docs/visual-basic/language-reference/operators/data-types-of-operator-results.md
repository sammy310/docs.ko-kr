---
title: 연산자 결과의 데이터 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: 45dcc80ee791da1c2731ba32f0ebd34564faf806
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814985"
---
# <a name="data-types-of-operator-results-visual-basic"></a>연산자 결과의 데이터 형식(Visual Basic)
Visual Basic에는 피연산자의 데이터 형식을 기반으로 하는 작업의 결과 데이터 형식이 결정 합니다. 일부 경우에이 피연산자 중 하나가 보다 큰 범위의 데이터 형식일 수 있습니다.  
  
## <a name="data-type-ranges"></a>데이터 형식 범위  
 가장 크고 작은 순서로 관련 데이터 형식의 범위는 다음과 같습니다.  
  
-   [부울](../../../visual-basic/language-reference/data-types/boolean-data-type.md) -두 개의 가능한 값  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)하십시오 [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md) -256 개 정수 계열 값  
  
-   [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md)하십시오 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) -65,536 (6.5... E + 4) 가능한 정수 계열 값  
  
-   [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md)하십시오 [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) -4,294,967,296 (4.2... E + 9) 사용할 수 있는 정수 계열 값  
  
-   [긴](../../../visual-basic/language-reference/data-types/long-data-type.md)하십시오 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) -18446744073709551615 (1.8... E + 19) 가능한 정수 계열 값  
  
-   [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -1.5... E + 29 가능한 정수 값을 최대 범위 7.9... + 28 (절대 값)  
  
-   [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) -최대 범위 3.4... E + 38 (절대 값)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -최대 범위 1.7-E + 308 (절대 값)  
  
 Visual Basic 데이터 형식에 대 한 자세한 내용은 참조 하세요. [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)합니다.  
  
 피연산자가 [Nothing](../../../visual-basic/language-reference/nothing.md), Visual Basic 산술 연산자를 0으로 처리 합니다.  
  
## <a name="decimal-arithmetic"></a>10 진수 산술  
 합니다 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식이 아닌 부동 소수점 또는 정수입니다.  
  
 경우의 피연산자는 `+`, `–`를 `*`, `/`, 또는 `Mod` 작업이 `Decimal` 다른 이며 `Single` 또는 `Double`, Visual Basic 확대 다른피연산자`Decimal`. 작업 수행 `Decimal`, 결과 데이터 형식이 며 `Decimal`합니다.  
  
## <a name="floating-point-arithmetic"></a>부동 소수점 연산  
 Visual Basic에서 대부분의 부동 소수점 산술 연산 수행 [이중](../../../visual-basic/language-reference/data-types/double-data-type.md), 가장 효율적인 데이터는 이러한 작업에 대 한 입력 합니다. 그러나 경우 피연산자 하나 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 다른 이며 `Double`, Visual Basic에서 작업을 수행 `Single`합니다. 작업 전에 적절 한 데이터 형식으로 필요에 따라 각 피연산자를 확장 하 고 결과 데이터 형식이 해당.  
  
### <a name="-and--operators"></a>/ 및 ^ 연산자  
 `/` 연산자가 정의 합니다 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [단일](../../../visual-basic/language-reference/data-types/single-data-type.md), 및 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식입니다. Visual Basic 작업 전에 적절 한 데이터 형식으로 필요에 따라 각 피연산자를 확장 하 고 결과 데이터 형식이 해당 합니다.  
  
 다음 표에서 결과 데이터 형식에 대 한는 `/` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|임의의 정수 형식|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|임의의 정수 형식|Decimal|Single|Double|Double|  
  
 `^` 연산자에 대해서만 정의 되는 `Double` 데이터 형식입니다. Visual Basic에는 필요에 따라 각 피연산자 확장 `Double` 작업을 하 고 결과 데이터 형식은 항상 하기 전에 `Double`입니다.  
  
## <a name="integer-arithmetic"></a>정수 연산  
 정수 연산 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라 집니다. 일반적으로 Visual Basic 결과 데이터 형식을 결정 하기 위해 다음 정책을 사용 합니다.  
  
-   이항 연산자의 피연산자가 모두 동일한 경우 데이터 형식으로 결과 해당 데이터 형식입니다. 예외가 `Boolean`를 강제 적용할 `Short`합니다.  
  
-   서명 된 피연산자를 사용 하 여 참여 하는 부호 없는 피연산자, 경우 결과 범위가 부호 있는 형식을 사용 하 여 가능한 큰 이상 피연산자 중 하나가으로 합니다.  
  
-   이 고, 그렇지 결과 일반적으로 두 개의 피연산자 데이터 형식 중 더 큰 숫자를 있습니다.  
  
 결과 데이터 형식은 두 피연산자 데이터 형식으로 동일할 수 없습니다 있습니다 note 합니다.  
  
> [!NOTE]
>  결과 데이터 형식이 항상 작업에서 발생 가능한 모든 값을 보유 하기에 충분할 것은 아닙니다. <xref:System.OverflowException> 값 결과 데이터 형식에 대해 너무 크면 예외가 발생할 수 있습니다.  
  
### <a name="unary--and--operators"></a>단항 + 및-연산자  
 다음 표에서 결과 데이터 형식이 단항 연산자에 대 한 `+` 고 `–`입니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|단항 `+`|Short|SByte|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|단항 `–`|Short|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< 및 >> 연산자  
 다음 표에서 결과 데이터 형식은 두 비트 시프트 연산자에 대 한 `<<` 고 `>>`입니다. Visual Basic (이동할 비트 패턴)의 왼쪽된 피연산자에서 단항 연산자를 각 비트 시프트 연산자를 처리 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|정수|UInteger|Long|ULong|  
  
 왼쪽된 피연산자가 `Decimal`, `Single`를 `Double`, 또는 `String`, Visual Basic로 변환 하려고 `Long` 작업을 하 고 결과 데이터 형식은 하기 전에 `Long`입니다. 오른쪽 피연산자 (이동할 비트 위치 수) 이어야 합니다 `Integer` 로 확대 하는 형식 또는 `Integer`합니다.  
  
### <a name="binary----and-mod-operators"></a>이진 +,-, *, Mod 연산자  
 다음 표에서 결과 이진에 대 한 데이터 형식을 `+` 하 고 `–` 연산자와 `*` 및 `Mod` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Decimal|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ 연산자  
 다음 표에서 결과 데이터 형식에 대 한는 `\` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 경우의 피연산자는 `\` 연산자는 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [단일](../../../visual-basic/language-reference/data-types/single-data-type.md), 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic로 변환 하려고 [장기](../../../visual-basic/language-reference/data-types/long-data-type.md)작업을 하 고 결과 데이터 형식은 하기 전에 `Long`입니다.  
  
## <a name="relational-and-bitwise-comparisons"></a>관계형 및 비트 비교  
 관계형 작업의 결과 데이터 형식 (`=`, `<>`, `<`, `>`를 `<=`를 `>=`)는 항상 `Boolean` [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다. 논리 작업에 대 한 마찬가지입니다 (`And`, `AndAlso`, `Not`, `Or`를 `OrElse`를 `Xor`)에서 `Boolean` 피연산자.  
  
 비트 논리 작업의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라 집니다. 유의 `AndAlso` 및 `OrElse` 에 대해서만 정의 됩니다 `Boolean`, Visual Basic로 필요에 따라 각 피연산자를 변환 및 `Boolean` 작업을 수행 하기 전에 합니다.  
  
### <a name="-----and--operators"></a>=, <> \<, >, \<= 및 > = 연산자  
 두 피연산자가 모두 있으면 `Boolean`, Visual Basic은 간주 `True` 되도록 미만 `False`합니다. 숫자 형식을 비교할 경우는 `String`, Visual Basic로 변환 하려고 합니다 `String` 를 `Double` 작업 전에 합니다. A `Char` 또는 `Date` 피연산자는 동일한 데이터 형식의 다른 피연산자와만 비교할 수 있습니다. 결과 데이터 형식은 항상 `Boolean`합니다.  
  
### <a name="bitwise-not-operator"></a>비트 Not 연산자  
 다음 표에서 결과 데이터 형식에 대 한 비트 `Not` 연산자입니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|부울|SByte|Byte|Short|UShort|정수|UInteger|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`를 `Double`, 또는 `String`, Visual Basic로 변환 하려고 `Long` 작업을 하 고 결과 데이터 형식은 하기 전에 `Long`입니다.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>비트를, 및 Xor 연산자  
 다음 표에서 비트에 대 한 데이터 형식을 결과 보여 줍니다 `And`, `Or`, 및 `Xor` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 동일 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|부울|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`를 `Double`, 또는 `String`, Visual Basic로 변환 하려고 `Long` 하기 전에 작업을 하 고 결과 데이터 형식이 동일 해당 피연산자 이미 것 처럼 `Long`합니다.  
  
## <a name="miscellaneous-operators"></a>기타 연산자  
 합니다 `&` 연산자가 연결에 대해서만 정의 `String` 피연산자입니다. Visual Basic 변환 필요에 따라 각 피연산자 `String` 작업을 하 고 결과 데이터 형식은 항상 하기 전에 `String`입니다. 목적을 `&` 연산자, 모든 변환을 `String` 확대 될 것으로 간주 됩니다 하더라도 `Option Strict` 는 `On`합니다.  
  
 합니다 `Is` 및 `IsNot` 연산자에서는 두 피연산자가 참조 형식 이어야 합니다. `TypeOf`... `Is` 식에는 첫 번째 피연산자는 참조 형식 이어야 하 고 데이터 형식의 이름으로 두 번째 피연산자가 있어야 합니다. 이러한 모든 경우 결과 데이터 형식은 `Boolean`합니다.  
  
 합니다 `Like` 연산자가 패턴 일치에 대해서만 정의 `String` 피연산자입니다. Visual Basic에서 필요에 따라 각 피연산자를 변환 하려고 `String` 작업 전에 합니다. 결과 데이터 형식은 항상 `Boolean`합니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [연산자](../../../visual-basic/language-reference/operators/index.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
