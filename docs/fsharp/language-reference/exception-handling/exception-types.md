---
title: 예외 형식
description: 정의 및 사용 하는 방법을 알아봅니다 F# 예외 형식입니다.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772725"
---
# <a name="exception-types"></a>예외 형식

두 종류의 예외 F#:.NET 예외 형식 및 F# 예외 형식입니다. 이 항목 정의 및 사용 하는 방법을 설명 F# 예외 형식입니다.

## <a name="syntax"></a>구문

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>설명

이전 구문에서 *예외 형식을* 의 새 이름입니다 F# 예외 형식 및 *인수 형식* 이 유형의 예외를 발생 시킬 때 제공할 수 있는 인수 형식을 나타냅니다. 튜플 형식을 사용 하 여 여러 인수를 지정할 수 있습니다 *인수 형식*합니다.

에 대 한 일반적인 정의 F# 예외는 다음 예제와 유사 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

사용 하 여이 형식의 예외를 생성할 수는 `raise` 함수를 다음과 같이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

사용할 수 있습니다는 F# 에 있는 필터에서 직접 예외 형식을 `try...with` 다음 예와에서 같이 식입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

사용 하 여 정의 하는 예외 형식 합니다 `exception` 키워드 F# 에서 상속 되는 새 유형이 `System.Exception`합니다.

## <a name="see-also"></a>참고자료

- [예외 처리](index.md)
- [예외: `raise` 함수](the-raise-function.md)
- [예외 계층](https://msdn.microsoft.com/library/z4c5tckx.aspx)