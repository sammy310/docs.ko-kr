---
title: '루프: while...do 식'
description: 참조 하는 방법을... 하는 동안 수행 식은 지정된 된 테스트 조건이 참인 동안 반복 실행 (루프)를 수행 하는데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: d2a77e0bfefe3b6b026012e6b2938ba670326bcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904022"
---
# <a name="loops-whiledo-expression"></a>루프: while...do 식

`while...do` 식은 지정된 된 테스트 조건이 참인 동안 반복 실행 (루프)를 수행 하는데 사용 됩니다.

## <a name="syntax"></a>구문

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>설명

*테스트 식* 를 평가 합니다;이 경우 `true`, *식 본문* 실행 테스트 식을 다시 계산 됩니다. 합니다 *식 본문* 형식이 있어야 `unit`합니다. 테스트 식이 `false`, 반복 종료 합니다.

다음 예제를 사용 하 여 `while...do` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

이전 코드의 출력은 1에서 20 사이의 난수는 마지막은 10 스트림입니다.

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> 사용할 수 있습니다 `while...do` 시퀀스 식 및 기타 계산 식, 사용자 지정된 버전의 경우는 `while...do` 식이 사용 됩니다. 자세한 내용은 [시퀀스](sequences.md)를 [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [루프: `for...in` Expression](loops-for-in-expression.md)
- [루프: `for...to` Expression](loops-for-to-expression.md)