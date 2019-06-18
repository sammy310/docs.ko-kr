---
title: 소스 줄, 파일 및 경로 식별자
description: 기본 제공을 사용 하는 방법을 알아봅니다 F# 식별자 값 원본에 액세스할 수 있도록 하는 줄 번호, 디렉터리 및 코드에서 파일 이름입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 3f2048aed9ef75037b43cd091a749e3d6bbaf9a3
ms.sourcegitcommit: 5e05f983e63d5bbd8c0b246d02c6e4f23d2fc1db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "67152058"
---
# <a name="source-line-file-and-path-identifiers"></a>소스 줄, 파일 및 경로 식별자

식별자 `__LINE__`, `__SOURCE_DIRECTORY__` 고 `__SOURCE_FILE__` 소스 줄 번호, 디렉터리 및 파일 이름을 코드에 액세스할 수 있는 기본 제공 값입니다.

## <a name="syntax"></a>구문

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>설명

이러한 각 값 형식이 `string`합니다.

다음 표에서 사용할 수 있는 소스 줄, 파일 및 경로 식별자 F#입니다. 이러한 식별자는 전처리기 매크로; 없습니다. 이러한 값은 컴파일러에서 인식 되는 기본 제공 값입니다.

|미리 정의 된 식별자|설명|
|---------------------|-----------|
|`__LINE__`|현재 줄 번호를로 고려 `#line` 지시문입니다.|
|`__SOURCE_DIRECTORY__`|원본 디렉터리의 전체 경로 평가 고려 `#line` 지시문입니다.|
|`__SOURCE_FILE__`|해당 경로가 없는 현재 소스 파일 이름에 평가 고려 `#line` 지시문입니다.|

에 대 한 자세한 내용은 합니다 `#line` 지시문을 참조 하십시오 [컴파일러 지시문](compiler-directives.md)합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 이러한 값을 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

출력:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>참고자료

- [컴파일러 지시문](compiler-directives.md)
- [F# 언어 참조](index.md)
