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
ms.openlocfilehash: dc8b630eebc48e5733344a00664b453360769c0b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346319"
---
# <a name="numeric-data-types-visual-basic"></a>숫자 데이터 형식(Visual Basic)
Visual Basic는 다양 한 표현에서 숫자를 처리 하기 위한 여러 *숫자 데이터 형식을* 제공 합니다. 정수 *계열* 형식은 정수 (양수, 음수 및 0)만 나타내고 정수 계열 형식은 정수 부분과 소수 부분을 모두 *포함 하는* 숫자를 나타냅니다.  
  
 Visual Basic 데이터 형식을 나란히 비교 하 여 보여 주는 표는 [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)을 참조 하세요.  
  
## <a name="integral-numeric-types"></a>정수 계열 숫자 형식  
 *정수 계열 데이터 형식은* 소수 부분이 없는 숫자만을 나타냅니다.  
  
 *부호 있는* 정수 계열 데이터 형식은 [SByte 데이터 형식](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 비트), [Short 데이터 형식](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 비트), [정수 데이터 형식](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 비트) 및 [Long 데이터 형식](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 비트)입니다. 변수가 항상 소수 자릿수가 아닌 정수를 저장 하는 경우 이러한 형식 중 하나로 선언 합니다.  
  
 *부호 없는* 정수 형식은 [Byte 데이터 형식](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 비트), [UShort 데이터 형식](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 비트), [UInteger 데이터 형식](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 비트) 및 [ULong 데이터 형식](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 비트)입니다. 변수가 이진 데이터를 포함 하거나 알 수 없는 형식의 데이터를 포함 하는 경우 이러한 형식 중 하나로 선언 합니다.  
  
### <a name="performance"></a>성능  
 산술 연산은 다른 데이터 형식 보다 정수 계열 형식으로 더 빠릅니다. Visual Basic에서 `Integer` 및 `UInteger` 유형을 사용 하는 것이 가장 빠릅니다.  
  
### <a name="large-integers"></a>매우 많은 정수  
 데이터 형식이 보유할 수 있는 `Integer` 보다 큰 정수를 유지 해야 하는 경우에는 `Long` 데이터 형식을 대신 사용할 수 있습니다. `Long` 변수는-9223372036854775808에서 9223372036854775807 까지의 숫자를 보유할 수 있습니다. `Long` 사용 하는 작업은 `Integer`보다 약간 느립니다.  
  
 훨씬 큰 값이 필요한 경우 [Decimal 데이터 형식을](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)사용할 수 있습니다. 소수 자릿수를 사용 하지 않는 경우 `Decimal` 변수에서 79228162514264337593543950335 까지의 숫자를 보유할 수 있습니다. 그러나 `Decimal` 숫자가 있는 연산은 다른 숫자 데이터 형식 보다 훨씬 느립니다.  
  
### <a name="small-integers"></a>작은 정수  
 `Integer` 데이터 형식의 전체 범위가 필요 하지 않은 경우에는-32768 ~ 32767의 정수를 보유할 수 있는 `Short` 데이터 형식을 사용할 수 있습니다. 가장 작은 정수 범위의 경우 `SByte` 데이터 형식에는-128에서 127 까지의 정수가 포함 됩니다. 작은 정수를 포함 하는 변수 수가 매우 많은 경우 공용 언어 런타임에서 `Short`를 저장 하 고 변수를 `SByte` 하 여 더 효율적으로 사용 하 고 메모리 사용을 줄일 수 있습니다. 그러나 `Short` 및 `SByte`를 사용 하는 작업은 `Integer`보다 약간 느립니다.  
  
### <a name="unsigned-integers"></a>부호 없는 정수  
 변수에 음수를 사용할 필요가 없는 경우에는 *서명 되지 않은 형식*`Byte`, `UShort`, `UInteger`및 `ULong`를 사용할 수 있습니다. 이러한 각 데이터 형식에는 해당 하는 부호 있는 형식 (`SByte`, `Short`, `Integer`및 `Long`) 만큼 양의 정수가 두 번 포함 될 수 있습니다. 성능 측면에서 부호 없는 각 형식은 해당 하는 부호 있는 형식과 정확히 일치 합니다. 특히 `UInteger` 공유를 사용 하 여 모든 기본 숫자 데이터 형식에 대 한 가장 효율적인 차이점을 `Integer` 합니다.  
  
## <a name="nonintegral-numeric-types"></a>비정 때 숫자 형식  
 *비정 수 데이터 형식은* 정수 부분과 소수 부분을 모두 포함 하는 숫자를 나타냅니다.  
  
 비정 수 숫자 데이터 형식은 `Decimal` (128 비트 고정 소수점), [Single 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32 비트 부동 소수점) 및 [Double 데이터 형식](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64 비트 부동 소수점)입니다. 모든 부호 있는 형식입니다. 변수가 분수를 포함할 수 있는 경우 이러한 형식 중 하나로 선언 합니다.  
  
 `Decimal`은 부동 소수점 데이터 형식이 아닙니다. `Decimal` 숫자에는 이진 정수 값과 소수 소수 부분을 지정 하는 정수 배율 인수가 있습니다.  
  
 Money 값에 `Decimal` 변수를 사용할 수 있습니다. 장점은 값의 전체 자릿수입니다. `Double` 데이터 형식은 더 빠르며 메모리가 더 필요 하지만 반올림 오류가 발생 합니다. `Decimal` 데이터 형식은 전체 정확도를 28 자리로 유지 합니다.  
  
 부동 소수점 (`Single` 및 `Double`) 숫자의 범위는 `Decimal` 수보다 크므로 반올림 오류의 영향을 받을 수 있습니다. 부동 소수점 형식은 `Decimal` 보다 덜 유효 자릿수를 지원 하지만 크기가 큰 값을 나타낼 수 있습니다.  
  
 비정 수 값은 mmmEeee로 표현할 수 있습니다. 여기서 mmm은가 *수 (유효* 숫자)이 고 eee는 *지* 수 (10의 거듭제곱)입니다. 비정 수 형식의 가장 높은 양수 값은 `Decimal`의 경우 7.9228162514264337593543950335 E + 28, `Single`의 경우 3.4028235 E + 38, `Double`의 경우 1.79769313486231570 E + 308입니다.  
  
### <a name="performance"></a>성능  
 현재 플랫폼의 프로세서는 배정밀도로 부동 소수점 연산을 수행 하기 때문에 `Double`는 소수 데이터 형식의 가장 효율적입니다. 그러나 `Double`를 사용 하는 연산은 `Integer`와 같은 정수 계열 유형과는 속도가 빠릅니다.  
  
### <a name="small-magnitudes"></a>Small 크고 많을  
 가장 작은 크기 (0에 가장 가깝습니다)가 있는 숫자의 경우 `Double` 변수는 음수 값에 대해-4.94065645841246544 E-324를 작은 값으로, 양수 값에는 4.94065645841246544 E-324를 포함할 수 있습니다.  
  
### <a name="small-fractional-numbers"></a>작은 분수 숫자  
 `Double` 데이터 형식의 전체 범위가 필요 하지 않은 경우에는 `Single` 데이터 형식을 사용 하 여-3.4028235 E + 38에서 3.4028235 E + 38 까지의 부동 소수점 숫자를 보유할 수 있습니다. `Single` 변수의 가장 작은 크고 많을는 음수 값의 경우-1.401298 E-45이 고 양수 값의 경우 1.401298 E-45입니다. 적은 수의 부동 소수점 숫자가 포함 된 변수가 매우 많은 경우 공용 언어 런타임에서 `Single` 변수를 보다 효율적으로 저장 하 고 메모리 사용을 절약할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [문자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [기타 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
