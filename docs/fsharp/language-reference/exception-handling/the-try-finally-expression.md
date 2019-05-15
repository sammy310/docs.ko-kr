---
title: '예외: try...finally 식'
description: 에 대해 알아봅니다 하는 방법을 F# ' try... 마지막 ' 식을 사용 하면 코드 블록에 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다.
ms.date: 05/16/2016
ms.openlocfilehash: d246bce52b5f30d5e8d7e3c36e9f7d7c48627913
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645458"
---
# <a name="exceptions-the-tryfinally-expression"></a>예외: try...finally 식

`try...finally` 표현식을 사용 하면 코드 블록에 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>설명

합니다 `try...finally` 식에서 코드를 실행할 수 *expression2* 실행 하는 동안 예외가 생성 되는지 여부에 관계 없이 이전 구문에서 *expression1*합니다.

유형의 *expression2* , 전체 식의 값에 영향을 주지 않습니다 예외가 발생 하지 않는 경우 반환 되는 형식에서 마지막 값인 *expression1*합니다. 예외가 발생할 때 아무 값도 반환 하 고 제어 흐름이 호출 스택 위로 다음 일치 하는 예외 처리기로 이동 합니다. 예외 처리기가 있으면 프로그램을 종료 합니다. 전에 일치 하는 처리기의 코드를 실행 하거나 프로그램이 종료 코드는 `finally` 분기가 실행 됩니다.

다음 코드에서는 사용 된 `try...finally` 식입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

콘솔에 출력은 다음과 같습니다.

```
Closing stream
Exception handled.
```

외부 예외를 처리 하기 전에 스트림이 닫히고 출력에서 보듯이 파일과 `test.txt` 텍스트가 `test1`를 나타내는 버퍼 플러시 되었으며 예외 전송 하는 경우에 디스크에 기록 외부 예외 처리기로 제어 합니다.

합니다 `try...with` 구문은 별도에서 `try...finally` 생성 합니다. 따라서 코드에 모두 필요한 경우는 `with` 블록 및 `finally` 블록에 다음 코드 예제와 같이 두 구문의 중첩 해야 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

계산 식의 컨텍스트에서 시퀀스 식 및 비동기 워크플로 비롯 한 **try... 마지막** 식에는 사용자 지정 구현을 가질 수 있습니다. 자세한 내용은 [계산 식](../computation-expressions.md)합니다.

## <a name="see-also"></a>참고자료

- [예외 처리](index.md)
- [예외: `try...with` 식](the-try-with-expression.md)
