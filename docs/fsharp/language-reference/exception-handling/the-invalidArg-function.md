---
title: '예외: invalidArg 함수'
description: 에 대해 알아봅니다 하는 방법을 F# 'invalidArg' 함수 인수 예외를 생성 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 7fd8d48b80970dbbafc0c23a478b4ccf3490f3ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996885"
---
# <a name="exceptions-the-invalidarg-function"></a>예외: invalidArg 함수

`invalidArg` 함수 인수 예외를 생성 합니다.

## <a name="syntax"></a>구문

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>설명

이전 구문에서 매개 변수 이름 인수가 잘못 되었습니다. 매개 변수 이름 문자열입니다. 합니다 *오류 메시지 문자열* 형식의 값 또는 리터럴 문자열은 `string`합니다. 되기는 `Message` 예외 개체의 속성입니다.

생성 된 예외 `invalidArg` 되는 `System.ArgumentException` 예외입니다. 다음 코드에서는 `invalidArg` 예외를 throw 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

출력은 다음을 뒤에 스택 추적 (표시 되지 않음).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>참고자료

- [예외 처리](index.md)
- [예외 형식](exception-types.md)
- [예외: `try...with` 식](the-try-with-expression.md)
- [예외: `try...finally` 식](the-try-finally-expression.md)
- [예외: `raise` 함수](the-raise-function.md)
- [예외: `failwith` 함수](the-failwith-function.md)