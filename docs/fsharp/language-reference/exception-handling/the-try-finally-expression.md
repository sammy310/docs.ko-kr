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
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="3ec3b-103">예외: try...finally 식</span><span class="sxs-lookup"><span data-stu-id="3ec3b-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="3ec3b-104">`try...finally` 표현식을 사용 하면 코드 블록에 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ec3b-105">구문</span><span class="sxs-lookup"><span data-stu-id="3ec3b-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="3ec3b-106">설명</span><span class="sxs-lookup"><span data-stu-id="3ec3b-106">Remarks</span></span>

<span data-ttu-id="3ec3b-107">합니다 `try...finally` 식에서 코드를 실행할 수 *expression2* 실행 하는 동안 예외가 생성 되는지 여부에 관계 없이 이전 구문에서 *expression1*합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="3ec3b-108">유형의 *expression2* , 전체 식의 값에 영향을 주지 않습니다 예외가 발생 하지 않는 경우 반환 되는 형식에서 마지막 값인 *expression1*합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="3ec3b-109">예외가 발생할 때 아무 값도 반환 하 고 제어 흐름이 호출 스택 위로 다음 일치 하는 예외 처리기로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="3ec3b-110">예외 처리기가 있으면 프로그램을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="3ec3b-111">전에 일치 하는 처리기의 코드를 실행 하거나 프로그램이 종료 코드는 `finally` 분기가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="3ec3b-112">다음 코드에서는 사용 된 `try...finally` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="3ec3b-113">콘솔에 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="3ec3b-114">외부 예외를 처리 하기 전에 스트림이 닫히고 출력에서 보듯이 파일과 `test.txt` 텍스트가 `test1`를 나타내는 버퍼 플러시 되었으며 예외 전송 하는 경우에 디스크에 기록 외부 예외 처리기로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="3ec3b-115">합니다 `try...with` 구문은 별도에서 `try...finally` 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="3ec3b-116">따라서 코드에 모두 필요한 경우는 `with` 블록 및 `finally` 블록에 다음 코드 예제와 같이 두 구문의 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="3ec3b-117">계산 식의 컨텍스트에서 시퀀스 식 및 비동기 워크플로 비롯 한 **try... 마지막** 식에는 사용자 지정 구현을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="3ec3b-118">자세한 내용은 [계산 식](../computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec3b-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec3b-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ec3b-119">See also</span></span>

- [<span data-ttu-id="3ec3b-120">예외 처리</span><span class="sxs-lookup"><span data-stu-id="3ec3b-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="3ec3b-121">예외: `try...with` 식</span><span class="sxs-lookup"><span data-stu-id="3ec3b-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
