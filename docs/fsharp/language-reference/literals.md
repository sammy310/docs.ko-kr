---
title: 리터럴
description: 'F # 프로그래밍 언어의 리터럴 형식에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559156"
---
# <a name="literals"></a>리터럴

이 문서에서는 F #에서 리터럴의 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.

## <a name="literal-types"></a>리터럴 형식

다음 표에서는 F #의 리터럴 형식을 보여 줍니다. 16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자를 구분 하지 않습니다. 형식을 식별 하는 문자는 대/소문자를 구분 합니다.

|Type|Description|접미사 또는 접두사|예제|
|----|-----------|----------------|--------|
|sbyte|부호 있는 8 비트 정수|y|`86y`<br /><br />`0b00000101y`|
|byte|부호 없는 8 비트 자연 수|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|부호 있는 16 비트 정수|s|`86s`|
|uint16|부호 없는 16 비트 자연 수|us|`86us`|
|int<br /><br />int32|부호 있는 32 비트 정수|l 또는 없음|`86`<br /><br />`86l`|
|uint<br /><br />uint32|부호 없는 32 비트 자연 수|u 또는 ul|`86u`<br /><br />`86ul`|
|nativeint|부호 있는 자연 숫자에 대 한 네이티브 포인터입니다.|n|`123n`|
|unativeint|부호 없는 자연 숫자로 된 네이티브 포인터|되지|`0x00002D3Fun`|
|int64|부호 있는 64 비트 정수|L|`86L`|
|uint64|부호 없는 64 비트 자연 수|UL|`86UL`|
|single, float32|32 비트 부동 소수점 숫자|F 또는 f|`4.14F` 또는 `4.14f`|
|||lf|`0x00000000lf`|
|f 차례로|64 비트 부동 소수점 숫자|없음|`4.14` 또는 `2.3E+32` 또는 `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|64 비트 표현으로 제한 되지 않는 정수|I|`9999999999999999999999999999I`|
|decimal|고정 소수점 또는 유리수로 표현 되는 소수 자릿수입니다.|M 또는 m|`0.7833M` 또는 `0.7833m`|
|Char|유니코드 문자|없음|`'a'` 또는 `'\u0061'`|
|String|유니코드 문자열|없음|`"text\n"`<br /><br />또는<br /><br />`@"c:\filename"`<br /><br />또는<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />또는<br /><br />`"string1" + "string2"`<br /><br />[문자열](Strings.md)도 참조 하세요.|
|byte|ASCII 문자|b|`'a'B`|
|byte[]|ASCII 문자열|b|`"text"B`|
|String 또는 byte []|축 자 문자열|@ 접두사|`@"\\server\share"` 유니코드<br /><br />`@"\\server\share"B` 부호|

## <a name="named-literals"></a>명명 된 리터럴

상수로 사용할 값은 [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) 특성으로 표시할 수 있습니다. 이 특성은 값이 상수로 컴파일되는 효과를 발생 시킵니다.

패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 리터럴이 아니라 바인딩할 변수로 취급 되므로 리터럴을 정의할 때 일반적으로 초기 대문자를 사용 해야 합니다.

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a>설명

유니코드 문자열에는를 사용 하 여 지정할 수 있는 명시적 인코딩 ( `\u` 0000-FFFF) 또는 `\U` 유니코드 코드 포인트 (0010FFFF)를 나타내는 32 비트 16 진수 코드를 사용 하 여 지정할 수 있는 u t f-32 인코딩이 포함 될 수 있습니다.

이외의 다른 비트 연산자를 사용할 `|||` 수 없습니다.

## <a name="integers-in-other-bases"></a>다른 기본의 정수

`0x`, 또는 접두사를 사용 하 여 부호 있는 32 비트 정수를 16 진수, 8 진수 또는 이진으로 지정할 수도 있습니다 `0o` `0b` .

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>숫자 리터럴의 밑줄

숫자를 밑줄 문자 ()로 구분할 수 있습니다 `_` .

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
