---
title: 문자열
description: "' String ' F# 형식에서 변경할 수 없는 텍스트를 유니코드 문자 시퀀스로 나타내는 방법에 대해 알아봅니다."
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452820"
---
# <a name="strings"></a>문자열

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

`string` 형식은 변경할 수 없는 텍스트를 유니코드 문자 시퀀스로 나타냅니다. `string`은 .NET Framework에서 `System.String`의 별칭입니다.

## <a name="remarks"></a>설명

문자열 리터럴은 따옴표 (") 문자로 구분 됩니다. 백슬래시 문자 (\\)는 특정 특수 문자를 인코딩하는 데 사용 됩니다. 백슬래시와 다음 문자를 함께 *이스케이프 시퀀스*라고 합니다. 다음 표에서는 F# 문자열 리터럴에서 지원 되는 이스케이프 시퀀스를 보여 줍니다.

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
|아포스트로피가|`\'`|
|유니코드 문자|`\DDD` (여기서 `D`는 10 진수를 나타냅니다. 범위는 000-255 (예: `\231` = "ç")입니다.|
|유니코드 문자|`\xHH` (여기서 `H`는 16 진수를 나타냅니다. 00-FF의 범위 (예: `\xE7` = "ç")|
|유니코드 문자|`\uHHHH` (UTF-16) (여기서 `H`는 16 진수를 나타냅니다. 0000-FFFF의 범위입니다.  예: `\u00E7` = "ç")|
|유니코드 문자|`\U00HHHHHH` (UTF-32) (여기서 `H`는 16 진수를 나타냅니다. 000000-10FFFF; 범위  예: `\U0001F47D` = "👽")|

> [!IMPORTANT]
> `\DDD` 이스케이프 시퀀스는 다른 언어와 같은 8 진수 표기법이 아닌 소수 표기법입니다. 따라서 숫자 `8` 및 `9`는 유효 하 고 `\032` 시퀀스는 공백 (U + 0020)을 나타내지만 8 진수 표기법의 동일한 코드 포인트는 `\040`됩니다.

> [!NOTE]
> 범위가 0-255 (0xFF)로 제한 되는 경우 `\DDD` 및 `\x` 이스케이프 시퀀스는 효과적으로 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 문자 집합입니다 .이는 첫 번째 256 유니코드 코드 지점과 일치 하기 때문입니다.

## <a name="verbatim-strings"></a>축 자 문자열

@ 기호가 앞에 오면 리터럴은 축 자 문자열입니다. 즉, 두 개의 따옴표 문자가 하나의 인용 부호 문자로 해석 된다는 점을 제외 하 고 모든 이스케이프 시퀀스는 무시 됩니다.

## <a name="triple-quoted-strings"></a>따옴표 붙은 문자열

또한 문자열을 삼중 따옴표로 묶을 수 있습니다. 이 경우 큰따옴표 문자를 포함 하 여 모든 이스케이프 시퀀스가 무시 됩니다. 포함 된 따옴표 붙은 문자열을 포함 하는 문자열을 지정 하려면 축 자 문자열 또는 세 개의 따옴표 붙은 문자열을 사용할 수 있습니다. 축 자 문자열을 사용 하는 경우 작은따옴표 문자를 나타내는 두 개의 따옴표 문자를 지정 해야 합니다. 세 번째 따옴표 붙은 문자열을 사용 하는 경우 문자열의 끝으로 구문 분석 되지 않고 작은따옴표 문자를 사용할 수 있습니다. 이 기법은 XML 또는 포함 된 따옴표를 포함 하는 다른 구조체로 작업 하는 경우에 유용할 수 있습니다.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

코드에서 줄 바꿈이 있는 문자열이 허용 되 고 줄 바꿈이 줄 바꿈 앞의 마지막 문자인 경우를 제외 하 고는 줄바꿈로 해석 됩니다. 백슬래시 문자를 사용 하는 경우 다음 줄의 선행 공백은 무시 됩니다. 다음 코드는 값이 `"abc\ndef"` 인 문자열 `str1`를 생성 하 고 값 `"abcdef"`를 포함 하는 문자열 `str2`를 생성 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>문자열 인덱싱 및 조각화

다음과 같이 배열 형식 구문을 사용 하 여 문자열의 개별 문자에 액세스할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

출력은 `b`입니다.

또는 다음 코드와 같이 배열 조각 구문을 사용 하 여 부분 문자열을 추출할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

출력은 다음과 같습니다.

```console
abc
def
```

부호 없는 바이트 배열, `byte[]`형식으로 ASCII 문자열을 나타낼 수 있습니다. 문자열 리터럴에 `B` 접미사를 추가 하 여 ASCII 문자열 임을 나타낼 수 있습니다. 바이트 배열과 함께 사용 되는 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외 하 고 유니코드 문자열과 동일한 이스케이프 시퀀스를 지원 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>문자열 연산자

문자열을 연결 하는 방법에는 두 가지가 있습니다. `+` 연산자를 사용 하거나 `^` 연산자를 사용 합니다. `+` 연산자는 .NET Framework 문자열 처리 기능과의 호환성을 유지 합니다.

다음 예제에서는 문자열 연결을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String 클래스

의 F# 문자열 형식은 실제로 .NET Framework `System.String` 형식 이므로 모든 `System.String` 멤버를 사용할 수 있습니다. 여기에는 문자열을 연결 하는 데 사용 되는 `+` 연산자, `Length` 속성 및 문자열을 유니코드 문자 배열로 반환 하는 `Chars` 속성이 포함 됩니다. 문자열에 대 한 자세한 내용은 `System.String`를 참조 하세요.

`System.String`의 `Chars` 속성을 사용 하 여 다음 코드와 같이 인덱스를 지정 하 여 문자열의 개별 문자에 액세스할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>문자열 모듈

문자열 처리를 위한 추가 기능은 `FSharp.Core` 네임 스페이스의 `String` 모듈에 포함 됩니다. 자세한 내용은 [Core. 문자열 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
