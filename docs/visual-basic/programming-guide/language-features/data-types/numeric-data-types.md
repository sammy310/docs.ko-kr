---
title: 숫자 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
ms.openlocfilehash: 317c0862953e7bb866faa4712d42dfd5995ecf35
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086233"
---
# <a name="numeric-data-types-visual-basic"></a>숫자 데이터 형식(Visual Basic)

Visual Basic는 다양 한 표현에서 숫자를 처리 하기 위한 여러 *숫자 데이터 형식을* 제공 합니다. 정수 *계열* 형식은 정수 (양수, 음수 및 0)만 나타내고 정수 계열 형식은 정수 부분과 소수 부분을 모두 *포함 하는* 숫자를 나타냅니다.  
  
 Visual Basic 데이터 형식을 나란히 비교 하 여 보여 주는 표는 [데이터 형식](../../../language-reference/data-types/index.md)을 참조 하세요.  
  
## <a name="integral-numeric-types"></a>정수 계열 숫자 형식  

 *정수 계열 데이터 형식은* 소수 부분이 없는 숫자만을 나타냅니다.  
  
 *부호 있는* 정수 계열 데이터 형식은 [SByte 데이터 형식](../../../language-reference/data-types/sbyte-data-type.md) (8 비트), [Short 데이터 형식](../../../language-reference/data-types/short-data-type.md) (16 비트), [정수 데이터 형식](../../../language-reference/data-types/integer-data-type.md) (32 비트) 및 [Long 데이터 형식](../../../language-reference/data-types/long-data-type.md) (64 비트)입니다. 변수가 항상 소수 자릿수가 아닌 정수를 저장 하는 경우 이러한 형식 중 하나로 선언 합니다.  
  
 *부호 없는* 정수 형식은 [Byte 데이터 형식](../../../language-reference/data-types/byte-data-type.md) (8 비트), [UShort 데이터 형식](../../../language-reference/data-types/ushort-data-type.md) (16 비트), [UInteger 데이터 형식](../../../language-reference/data-types/uinteger-data-type.md) (32 비트) 및 [ULong 데이터 형식](../../../language-reference/data-types/ulong-data-type.md) (64 비트)입니다. 변수가 이진 데이터를 포함 하거나 알 수 없는 형식의 데이터를 포함 하는 경우 이러한 형식 중 하나로 선언 합니다.  
  
### <a name="performance"></a>성능  

 산술 연산은 다른 데이터 형식 보다 정수 계열 형식으로 더 빠릅니다. `Integer`Visual Basic의 및 형식이 가장 빠르게 사용 됩니다 `UInteger` .  
  
### <a name="large-integers"></a>매우 많은 정수  

 데이터 형식이 보유할 수 있는 것 보다 큰 정수를 보유 해야 하는 경우에 `Integer` 는 `Long` 데이터 형식을 대신 사용할 수 있습니다. `Long` 변수는-9223372036854775808에서 9223372036854775807 까지의 숫자를 보유할 수 있습니다. 를 사용 하 `Long` 는 작업은 보다 약간 느립니다 `Integer` .  
  
 훨씬 큰 값이 필요한 경우 [Decimal 데이터 형식을](../../../language-reference/data-types/decimal-data-type.md)사용할 수 있습니다. `Decimal`소수 자릿수를 사용 하지 않는 경우 변수에-79228162514264337593543950335 ~ 79228162514264337593543950335를 사용할 수 있습니다. 그러나 숫자가 있는 연산은 `Decimal` 다른 숫자 데이터 형식 보다 훨씬 느립니다.  
  
### <a name="small-integers"></a>작은 정수  

 데이터 형식의 전체 범위가 필요 하지 않은 경우에는 `Integer` `Short` -32768 ~ 32767의 정수를 포함할 수 있는 데이터 형식을 사용할 수 있습니다. 가장 작은 정수 범위의 경우 `SByte` 데이터 형식에는-128에서 127 까지의 정수가 포함 됩니다. 작은 정수를 포함 하는 변수가 매우 많은 경우 공용 언어 런타임에서는 `Short` 및 `SByte` 변수를 보다 효율적으로 저장 하 고 메모리 사용을 절약 하는 경우가 있습니다. 그러나 및을 사용 `Short` 하 `SByte` 는 작업은 보다 약간 느립니다 `Integer` .  
  
### <a name="unsigned-integers"></a>부호 없는 정수  

 변수에 음수를 포함할 필요가 없는 경우 *부호 없는 형식인*,, 및를 사용할 수 있습니다 `Byte` `UShort` `UInteger` `ULong` . 이러한 각 데이터 형식에는 해당 하는 부호 있는 형식 ( `SByte` ,, `Short` `Integer` 및) 만큼 양의 정수를 두 번 포함할 수 있습니다 `Long` . 성능 측면에서 부호 없는 각 형식은 해당 하는 부호 있는 형식과 정확히 일치 합니다. 특히 `UInteger` `Integer` 모든 기본 숫자 데이터 형식에 대 한 가장 효율적인 차이점을 공유 합니다.  
  
## <a name="nonintegral-numeric-types"></a>비정 때 숫자 형식  

 *비정 수 데이터 형식은* 정수 부분과 소수 부분을 모두 포함 하는 숫자를 나타냅니다.  
  
 비정 수 숫자 데이터 형식은 `Decimal` (128 비트 고정 소수점), [Single 데이터 형식](../../../language-reference/data-types/single-data-type.md) (32 비트 부동 소수점) 및 [Double 데이터 형식](../../../language-reference/data-types/double-data-type.md) (64 비트 부동 소수점)입니다. 모든 부호 있는 형식입니다. 변수가 분수를 포함할 수 있는 경우 이러한 형식 중 하나로 선언 합니다.  
  
 `Decimal` 이 부동 소수점 데이터 형식이 아닌 경우 `Decimal` 숫자에는 이진 정수 값과 소수 소수 부분을 지정 하는 정수 배율 인수가 있습니다.  
  
 `Decimal`Money 값에 변수를 사용할 수 있습니다. 장점은 값의 전체 자릿수입니다. `Double`데이터 형식은 더 빠르며 메모리가 더 필요 하지만 반올림 오류가 발생 합니다. `Decimal`데이터 형식은 전체 정확도를 28 자리로 유지 합니다.  
  
 부동 소수점 ( `Single` 및 `Double` ) 숫자의 범위는 숫자 보다 크지만 `Decimal` 반올림 오류의 영향을 받을 수 있습니다. 부동 소수점 형식은 보다 작은 유효 자릿수를 지원 `Decimal` 하지만 크기가 큰 값을 나타낼 수 있습니다.  
  
 비정 수 값은 mmmEeee로 표현할 수 있습니다. 여기서 mmm은가 *수 (유효* 숫자)이 고 eee는 *지* 수 (10의 거듭제곱)입니다. 비정 수 형식의 가장 높은 양수 값은 7.9228162514264337593543950335 E + 28 for, 3.4028235 E + 38,에 대 한 `Decimal` `Single` 1.79769313486231570 e + 308 `Double` 입니다.  
  
### <a name="performance"></a>성능  

 `Double` 현재 플랫폼의 프로세서에서 배정밀도의 부동 소수점 연산을 수행 하기 때문에는 소수 데이터 형식이 가장 효율적입니다. 그러나를 사용 하 `Double` 는 연산은와 같은 정수 계열 형식과는 속도가 빠르지 않습니다 `Integer` .  
  
### <a name="small-magnitudes"></a>Small 크고 많을  

 가장 작은 크기 (0에 가장 가깝습니다)가 있는 숫자의 경우 `Double` 변수는 음수 값에 대해-4.94065645841246544 e-324로 작은 숫자를, 양수 값의 경우 4.94065645841246544 e-324을 포함할 수 있습니다.  
  
### <a name="small-fractional-numbers"></a>작은 분수 숫자  

 데이터 형식의 전체 범위가 필요 하지 않은 경우 `Double` `Single` -3.4028235 e + 38에서 3.4028235 e + 38 까지의 부동 소수점 수를 포함할 수 있는 데이터 형식을 사용할 수 있습니다. 변수에 대 한 최소 크고 많을는 `Single` 음수 값의 경우-1.401298 e-45이 고 양수 값의 경우 1.401298 e-45입니다. 작은 부동 소수점 숫자를 포함 하는 변수를 매우 많이 사용 하는 경우 공용 언어 런타임에서는 때때로 `Single` 변수를 더 효율적으로 저장 하 고 메모리 사용을 줄일 수 있습니다.  
  
## <a name="see-also"></a>참조

- [기본 데이터 형식](elementary-data-types.md)
- [문자 데이터 형식](character-data-types.md)
- [기타 데이터 형식](miscellaneous-data-types.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
