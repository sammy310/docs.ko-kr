---
title: '예외: raise 함수'
description: 설명 하는 방법을 F# 'raise' 함수는 오류 또는 예외 조건이 발생 했음을 알리는 데 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 87773ead7773c62a325c7e7ff105c729e10dd69c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772673"
---
# <a name="exceptions-the-raise-function"></a>예외: raise 함수

`raise` 함수는 오류 또는 예외 조건이 발생 했음을 나타내는 하는 데 사용 됩니다. 오류에 대 한 정보는 예외 개체에서 캡처됩니다.

## <a name="syntax"></a>구문

```fsharp
raise (expression)
```

## <a name="remarks"></a>설명

`raise` 함수는 예외 개체를 생성 하 고 스택 해제 프로세스를 시작 합니다. 이 프로세스의 동작 동일 하다는 다른.NET 언어 이므로 스택 해제 프로세스는 CLR (공용 언어 런타임)에 의해 관리 됩니다. 스택 해제 프로세스는 생성 된 예외와 일치 하는 예외 처리기를 검색 합니다. 검색은 현재에서 시작 `try...with` 식에 있는 경우. 각 패턴에는 `with` 순서 대로 블록 검사 합니다. 예외 처리; 비율은 일치 하는 예외 처리기가 발견 되 면 이 고, 그렇지 않으면 스택이 스택이 및 `with` 일치 하는 처리기를 찾을 때까지 호출 체인 블록을 검사 합니다. 모든 `finally` 스택이 해제 되므로 순서 대로 호출 체인에 발생 하는 블록도 실행 됩니다.

합니다 `raise` 함수는 해당 `throw` 에서 C# 또는 C++합니다. 사용 하 여 `reraise` catch 처리기 호출 체인 동일한 예외를 전파 합니다.

다음 코드 예제 사용법을 보여 줍니다.는 `raise` 예외를 생성 하는 함수입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

`raise` 다음 예와에서 같이 함수를.NET 예외를 발생 사용도 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>참고자료

- [예외 처리](index.md)
- [예외 형식](exception-types.md)
- [예외: `try...with` 식](the-try-with-expression.md)
- [예외: `try...finally` 식](the-try-finally-expression.md)
- [예외: `failwith` 함수](the-failwith-function.md)
- [예외: `invalidArg` 함수](the-invalidArg-function.md)