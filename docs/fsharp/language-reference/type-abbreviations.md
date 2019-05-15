---
title: 형식 약어
description: 에 대해 알아봅니다 F# 형식에 이름을 더 의미 있는 코드를 쉽게 읽을 수 있도록 하기 위해 약어를 입력 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 2930db1dcaa66741900bc91937aa1fd2f006c5f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641689"
---
# <a name="type-abbreviations"></a>형식 약어

A *형식 약어* 별칭 또는 형식의 이름을 대체 합니다.

## <a name="syntax"></a>구문

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>설명

형식에 이름을 더 의미 있는, 코드를 쉽게 읽을 수 있도록 하기 위해 형식 약어를 사용할 수 있습니다. 그렇지 않은 경우에 번거로운 작업 작성 하는 형식에 대 한 사용 하기 쉬운 이름을 만들 수 에서도 사용할 수 있습니다. 또한 쉽게 형식을 사용 하는 모든 코드를 변경 하지 않고 내부 형식을 변경할 수 있도록 형식 약어를 사용할 수 있습니다. 다음은 간단한 형식 약어입니다.

기본적으로 형식 약어의 접근성 `public`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

형식 약어에는 다음 코드와 같이 제네릭 매개 변수를 포함할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

이전 코드에서 `Transform` 형식의 단일 인수를 사용 하는 함수를 나타내는 형식 약어 이며 동일한 형식의 단일 값을 반환 합니다.

.NET Framework MSIL 코드에서 형식 약어 유지 되지 않습니다. 따라서 사용 하는 경우는 F# 어셈블리 다른.NET Framework 언어에서 형식 약어에 대 한 기본 형식 이름을 사용 해야 합니다.

측정 단위 형식 약어를 사용할 수도 있습니다. 자세한 내용은 [측정 단위를](units-of-measure.md)입니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
