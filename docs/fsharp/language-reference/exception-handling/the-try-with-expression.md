---
title: '예외: try...with 식'
description: 사용 하는 방법을 알아봅니다는 F# 'try...with' 예외 처리에 대 한 식입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 3ba13227ac55eff770ceb7631d3406ad80b6ea45
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641932"
---
# <a name="exceptions-the-trywith-expression"></a>예외: try...with 식

에 대해 설명 합니다 `try...with` 식, 예외 처리에 사용 되는 식의 F# 언어.

## <a name="syntax"></a>구문

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>설명

합니다 `try...with` 식에서 예외를 처리 하는 F#합니다. 비슷합니다는 `try...catch` C# 문입니다. 위의 구문에서의 코드 *expression1* 예외가 발생할 수 있습니다. `try...with` 식 값을 반환 합니다. 예외가 throw 되 면 전체 식의 값을 반환 *expression1*합니다. 예외가 throw 되 면 각 *패턴* 는 비교할 첫 번째 일치 하는 패턴의 경우 해당 예외와 *식을*로 알려진는 *예외 처리기*에 해당 분기 실행 되 고 전체 식 예외 처리기에서 식의 값을 반환 합니다. 패턴 일치 하는 경우 일치 하는 처리기를 찾을 때까지 예외가 호출 스택으로 전파 합니다. 예외 처리기에서 각 식에서 반환 하는 값의 형식은 식에서 반환 되는 형식과 일치 해야 합니다는 `try` 블록입니다.

대부분의 경우는 또한 오류가 발생 하는 팩트 각 예외 처리기의 식에서 반환 될 수 있는 유효한 값 임을 의미 합니다. 빈번한 패턴은 옵션 형식 이어야 하는 식의 형식입니다. 다음 코드 예제에서는이 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

예외는.NET 예외 수 있거나 있을 수 있습니다 F# 예외입니다. 정의할 수 있습니다 F# 를 사용 하 여 예외를 `exception` 키워드입니다.

다양 한 패턴을 사용 하 여 예외 유형 및 기타 조건 필터링 옵션은 다음 표에 요약 되어 있습니다.

|무늬|설명|
|-------|-----------|
|:? *exception-type*|지정 된.NET 예외 형식과 일치합니다.|
|:? *예외 형식* 으로 *식별자*|지정된 된.NET 예외 형식에는 일치 하지만 예외를 명명 된 값을 제공 합니다.|
|*exception-name*(*arguments*)|일치 하는 F# 예외 형식 및 인수를 바인딩합니다.|
|*identifier*|모든 예외에 일치 하 고 예외 개체에 이름을 바인딩합니다. 같음 **:? 으로 System.Exception**_식별자_|
|*식별자* 때 *조건*|조건이 true 인 경우 모든 예외를 찾습니다.|

## <a name="examples"></a>예제

다음 코드 예제에서는 다양 한 예외 처리기 패턴의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> 합니다 `try...with` 구문은에서 별도 식의 `try...finally` 식입니다. 따라서 코드에 모두 필요한 경우는 `with` 블록 및 `finally` 블록 두 식을 중첩 해야 합니다.

> [!NOTE]
> 사용할 수 있습니다 `try...with` 비동기 워크플로 및 기타 계산 식에는 사용자 지정된 버전의 경우는 `try...with` 식이 사용 됩니다. 자세한 내용은 [비동기 워크플로](../asynchronous-workflows.md), 및 [계산 식](../computation-expressions.md)합니다.

## <a name="see-also"></a>참고자료

- [예외 처리](index.md)
- [예외 형식](exception-types.md)
- [예외: `try...finally` 식](the-try-finally-expression.md)
