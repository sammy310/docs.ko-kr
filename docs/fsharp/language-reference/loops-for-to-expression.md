---
title: '루프: for...to 식'
description: F# 자세한 내용은 다음을 참조 하세요. to expression은 루프 변수의 값 범위에 대해 루프를 반복 하는 데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283910"
---
# <a name="loops-forto-expression"></a>루프: for...to 식

`for...to` 식은 루프 변수의 값 범위에 대해 루프에서 반복 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>주의

식별자의 형식은 *start* 및 *finish* 식의 형식에서 유추 됩니다. 이러한 식의 형식은 32 비트 정수 여야 합니다.

기술적으로는 `for...to` 식이 명령형 프로그래밍 언어의 일반적인 문과 비슷합니다. *본문 식* 의 반환 형식은 `unit`이어야 합니다. 다음 예에서는 `for...to` 식의 다양 한 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

위 코드는 다음과 같이 출력됩니다.

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [루프: `for...in` 식](loops-for-in-expression.md)
- [루프: `while...do` 식](loops-while-do-expression.md)
