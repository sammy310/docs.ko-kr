---
title: 문자열
description: F# '문자열' 형식이 유니코드 문자 시퀀스로 변경할 수 없는 텍스트를 나타내는 방법을 알아봅니다.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739562"
---
# <a name="strings"></a>문자열

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

형식은 `string` 유니코드 문자시퀀스로 변경할 수 없는 텍스트를 나타냅니다. `string`은 .NET Framework에서 `System.String`의 별칭입니다.

## <a name="remarks"></a>설명

문자열 리터럴은 따옴표(") 문자로 구분됩니다. 백슬래시 문자 \\ ()는 특정 특수 문자를 인코딩하는 데 사용됩니다. 백슬래시와 다음 문자를 함께 *이스케이프 시퀀스라고*합니다. F# 문자열 리터럴에서 지원되는 이스케이프 시퀀스는 다음 표에 나와 있습니다.

|문자|이스케이프 시퀀스|
|---------|---------------|
|경고|`\a`|
|백스페이스|`\b`|
|용지 공급|`\f`|
|줄 바꿈|`\n`|
|캐리지 리턴|`\r`|
|탭|`\t`|
|세로 탭|`\v`|
|백슬래시|`\\`|
|물음표|`\"`|
|아포스트로피|`\'`|
|유니코드 문자|`\DDD`(여기서 `D` 소수 자릿수, 범위는 000 - 255; 예를 `\231` 들어 = "ç")|
|유니코드 문자|`\xHH`(여기서 `H` 헥사데피상 자릿수; 00 - FF; 예를 `\xE7` 들어 = "ç")|
|유니코드 문자|`\uHHHH`(UTF-16) (여기서 `H` 헥사데피숫자; 0000의 범위 - FFFF;  예를 들어 `\u00E7` = "ç")|
|유니코드 문자|`\U00HHHHHH`(UTF-32) (여기서 `H` 헥사데피수 자릿수; 000000- 10FFFFFF의 범위;  예를 들어 `\U0001F47D` =👽" ")|

> [!IMPORTANT]
> 이스케이프 시퀀스는 `\DDD` 대부분의 다른 언어와 마찬가지로 십자수 표기형이 아닙니다. 따라서 `8` 숫자와 `9` 유효하며 공백(U+0020)을 `\032` 나타내는 시퀀스가 있는 반면, 팔각형 표기법의 동일한 코드 포인트는 . `\040`

> [!NOTE]
> 0 - 255(0xFF) 범위로 제한되는 `\DDD` `\x` 이스케이프 시퀀스는 처음 256개의 유니코드 코드 포인트와 일치하기 때문에 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 문자 집합이 효과적으로 설정됩니다.

## <a name="verbatim-strings"></a>축어 문자열

@ 기호 앞에 오는 경우 리터럴은 축어 문자열입니다. 즉, 두 개의 따옴표 문자가 하나의 따옴표 문자로 해석된다는 점을 제외하면 이스케이프 시퀀스는 무시됩니다.

## <a name="triple-quoted-strings"></a>트리플 인용 문자열

또한 문자열은 삼중 따옴표로 묶일 수 있습니다. 이 경우 이중 따옴표 문자를 포함하여 모든 이스케이프 시퀀스는 무시됩니다. 포함된 quoted 문자열이 포함된 문자열을 지정하려면 축어 문자열 또는 삼중 인용 문자열을 사용할 수 있습니다. 축어 문자열을 사용하는 경우 두 개의 따옴표 문자를 지정하여 단일 따옴표 문자를 지정해야 합니다. 삼중 따옴표 문자열을 사용하는 경우 문자열의 끝으로 구문 분석되지 않고 단일 따옴표 기호 문자를 사용할 수 있습니다. 이 기술은 XML 또는 포함된 따옴표를 포함하는 다른 구조로 작업할 때 유용할 수 있습니다.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

코드에서 줄 바꿈이 있는 문자열은 허용되고 줄 바꿈은 백슬래시 문자가 줄 바꿈 전마지막 문자가 아니면 말 그대로 줄 바꿈으로 해석됩니다. 백슬래시 문자를 사용할 때 다음 줄의 선도 공백은 무시됩니다. 다음 코드는 값이 `str1` 있는 문자열과 `"abc\ndef"` 값이 `str2` `"abcdef"`있는 문자열을 생성합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>문자열 인덱싱 및 슬라이싱

배열과 같은 구문을 사용하여 문자열의 개별 문자에 액세스할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

출력은 `b`입니다.

또는 다음 코드와 같이 배열 조각 구문을 사용하여 하위 문자열을 추출할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

출력은 다음과 같습니다.

```console
abc
def
```

부호없는 바이트의 배열로 ASCII 문자열을 나타낼 `byte[]`수 있습니다. 문자열 리터럴에 `B` 접미사를 추가하여 ASCII 문자열임을 나타냅니다. 바이트 배열에 사용되는 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외하고 유니코드 문자열과 동일한 이스케이프 시퀀스를 지원합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>문자열 연산자

연산자는 `+` .NET Framework 문자열 처리 기능과의 호환성을 유지하면서 문자열을 통합하는 데 사용할 수 있습니다. 다음 예제에서는 문자열 연결에 대해 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>문자열 클래스

F#의 문자열 형식은 실제로 .NET `System.String` Framework 형식이므로 모든 멤버를 `System.String` 사용할 수 있습니다. 여기에는 `+` 문자열, `Length` 속성 및 문자열을 유니코드 문자의 배열로 반환하는 `Chars` 속성을 통합하는 데 사용되는 연산자가 포함됩니다. 문자열에 대한 자세한 내용은 `System.String`을 참조하십시오.

`System.String`의 `Chars` 속성을 사용하여 다음 코드와 같이 인덱스를 지정하여 문자열의 개별 문자에 액세스할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>문자열 모듈

문자열 처리를 위한 추가 기능은 `String` `FSharp.Core` 네임스페이스의 모듈에 포함되어 있습니다. 자세한 내용은 [Core.String 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)을 참조하십시오.

## <a name="see-also"></a>참고 항목

- [F # 언어 참조](index.md)
