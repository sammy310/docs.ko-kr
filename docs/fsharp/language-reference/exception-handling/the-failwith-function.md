---
title: '예외: failwith 함수'
description: "'Failwith' 함수를 생성 하는 방법에 대해 알아봅니다는 F# 예외입니다."
ms.date: 05/16/2016
ms.openlocfilehash: 05d385ddfc98a910779a6f59949a7187c38f0812
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772686"
---
# <a name="exceptions-the-failwith-function"></a>예외: failwith 함수

합니다 `failwith` 함수 생성을 F# 예외입니다.

## <a name="syntax"></a>구문

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>설명

합니다 *오류 메시지 문자열* 리터럴 문자열이 나 형식의 값은 이전 구문에서 `string`합니다. 되기는 `Message` 예외의 속성입니다.

생성 되는 예외 `failwith` 은 `System.Exception` 이름이 참조 하는 예외 `Failure` 에서 F# 코드입니다. 다음 코드에서는 `failwith` 예외를 throw 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>참고자료

- [예외 처리](index.md)
- [예외 형식](exception-types.md)
- [예외: `try...with` 식](the-try-with-expression.md)
- [예외: `try...finally` 식](the-try-finally-expression.md)
- [예외: `raise` 함수](the-raise-function.md)