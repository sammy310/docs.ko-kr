---
title: 형식 문자
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: a48260694c1dfcbbb8f804f220fe89b1663c7319
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393080"
---
# <a name="type-characters-visual-basic"></a>형식 문자 (Visual Basic)

선언문에서 데이터 형식을 지정 하는 것 외에도 *형식 문자*를 사용 하 여 일부 프로그래밍 요소의 데이터 형식을 강제할 수 있습니다. 형식 문자는 요소 바로 뒤에와 야 하며 모든 종류의 중간 문자는 없어야 합니다.

형식 문자는 요소 이름의 일부가 아닙니다. 형식 문자를 사용 하 여 정의 된 요소는 형식 문자 없이 참조할 수 있습니다.

## <a name="identifier-type-characters"></a>식별자 형식 문자

Visual Basic는 선언에서 변수나 상수의 데이터 형식을 지정 하는 데 사용할 수 있는 *식별자 형식 문자* 집합을 제공 합니다. 다음 표에서는 사용 가능한 식별자 형식 문자를 사용 예제와 함께 보여 줍니다.
  
|식별자 형식 문자|데이터 형식|예제|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 ,,,,,,,, 또는 데이터 형식에 대 한 식별자 형식 문자 `Boolean` `Byte` `Char` `Date` `Object` `SByte` `Short` `UInteger` `ULong` `UShort` 또는 배열이 나 구조체와 같은 복합 데이터 형식에 대 한 식별자 형식 문자는 없습니다.

경우에 따라 `$` `Left$` 형식의 반환 된 값을 얻기 위해 문자를 대신 Visual Basic 함수에 추가할 수 있습니다 `Left` `String` .

모든 경우에서 식별자 형식 문자는 식별자 이름 바로 뒤에와 야 합니다.

## <a name="literal-type-characters"></a>리터럴 형식 문자

*리터럴은* 데이터 형식의 특정 값에 대 한 텍스트 표현입니다.  

### <a name="default-literal-types"></a>기본 리터럴 형식

코드에 표시 되는 리터럴의 형식은 일반적으로 해당 데이터 형식을 결정 합니다. 다음 표에서는 이러한 기본 형식을 보여 줍니다.  
  
|리터럴의 텍스트 형식|기본 데이터 형식|예제|  
|-----------------------------|-----------------------|-------------|  
|숫자, 소수 부분 없음|`Integer`|`2147483647`|  
|숫자, 소수 부분 없음,에 대해 너무 큼`Integer`|`Long`|`2147483648`|  
|숫자, 소수 부분|`Double`|`1.2`|  
|큰따옴표로 묶어서|`String`|`"A"`|  
|숫자 기호로 묶여 있습니다.|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>강제 리터럴 형식

Visual Basic 리터럴 *형식 문자*집합을 제공 합니다 .이 문자를 사용 하 여 리터럴은 폼이 나타내는 데이터 형식이 아닌 다른 데이터 형식을 사용 하는 것을 강제할 수 있습니다. 리터럴 끝에 문자를 추가 하 여이 작업을 수행 합니다. 다음 표에서는 사용 가능한 리터럴 형식 문자를 사용 예제와 함께 보여 줍니다.
  
|리터럴 형식 문자|데이터 형식|예제|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

`Boolean`, `Byte` , `Date` ,, `Object` `SByte` 또는 `String` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식에 대 한 리터럴 형식 문자는 없습니다.

리터럴은 `%` `&` `@` `!` `#` `$` 변수, 상수 및 식으로 식별자 형식 문자 (,,,,,)를 사용할 수도 있습니다. 그러나 리터럴 형식 문자 ( `S` , `I` , `L` ,,, `D` `F` `R` ,)는 `C` 리터럴에만 사용할 수 있습니다.

모든 경우에서 리터럴 형식 문자는 리터럴 값 바로 뒤에와 야 합니다.

## <a name="hexadecimal-binary-and-octal-literals"></a>16 진수, 이진 및 8 진수 리터럴

컴파일러는 일반적으로 정수 리터럴을 10 진수 (밑수 10) 숫자 시스템에 있는 것으로 해석 합니다. 접두사를 사용 하 여 접두사를 포함 하는 16 진수 (기 수)로 정수 리터럴을 정의 하 고 접두사를 사용 하 여 `&H` `&B` 8 진수 (밑수 8)로 지정할 수도 있습니다 `&O` . 접두사 뒤의 숫자는 숫자 시스템에 적합 해야 합니다. 다음 표에서는이에 대해 설명 합니다.  
  
|숫자 기준|접두사|유효한 숫자 값|예제|
|-----------------|------------|------------------------|-------------|
|16진수|`&H`|0-9 및 A-f|`&HFFFF`|
|Binary (밑 2)|`&B`|0-1|`&B01111100`|
|8진수|`&O`|0-7|`&O77`|

Visual Basic 2017부터 밑줄 문자 ( `_` )를 그룹 구분 기호로 사용 하 여 정수 리터럴의 가독성을 향상 시킬 수 있습니다. 다음 예제에서는 문자를 사용 하 여 `_` 이진 리터럴을 8 비트 그룹으로 그룹화 합니다.

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

리터럴 형식 문자를 사용 하 여 접두 리터럴을 따라갈 수 있습니다. 다음 예에서는 이러한 방법을 보여 줍니다.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

앞의 예제에서의 `counter` 10 진수 값은-32768이 고 `flags` 10 진수 값은 + 32768입니다.

Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>참고 항목

- [데이터 형식](index.md)
- [기본 데이터 형식](elementary-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Visual Basic의 형식 변환](type-conversions.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [변수 선언](../variables/variable-declaration.md)
- [데이터 형식](../../../language-reference/data-types/index.md)
