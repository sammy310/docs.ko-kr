---
title: 예외 try...finally 식
description: F# ' 시도 ... finally ' 식을 사용 하면 코드 블록에서 예외를 throw 하는 경우에도 정리 코드를 실행할 수 있습니다.
ms.date: 05/16/2016
ms.openlocfilehash: 03fbda1ef5d55560232f0217f603fc04c0af0eb4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630279"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="e6763-103">예외 try...finally 식</span><span class="sxs-lookup"><span data-stu-id="e6763-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="e6763-104">식 `try...finally` 에서는 코드 블록에서 예외를 throw 하는 경우에도 정리 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6763-105">구문</span><span class="sxs-lookup"><span data-stu-id="e6763-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="e6763-106">설명</span><span class="sxs-lookup"><span data-stu-id="e6763-106">Remarks</span></span>

<span data-ttu-id="e6763-107">*Expression1를*실행 하는 동안 예외가 생성 되었는지 여부 에 관계 없이 앞의 구문을 사용 하 여 식에서코드를실행할수있습니다.`try...finally`</span><span class="sxs-lookup"><span data-stu-id="e6763-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="e6763-108">식 *2* 의 형식은 전체 식의 값에 영향을 주지 않습니다. 예외가 발생 하지 않는 경우 반환 되는 형식은 *expression1*의 마지막 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="e6763-109">예외가 발생 하면 값이 반환 되지 않고 제어 흐름이 호출 스택에 있는 다음 일치 하는 예외 처리기에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="e6763-110">예외 처리기를 찾을 수 없는 경우 프로그램이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="e6763-111">일치 하는 처리기의 코드가 실행 되거나 프로그램이 종료 되기 전에 `finally` 분기의 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="e6763-112">다음 코드에서는 `try...finally` 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="e6763-113">콘솔에 대 한 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="e6763-114">출력에서 볼 수 있듯이 외부 예외가 처리 되기 전에 스트림이 닫히고 파일 `test.txt` 에 텍스트가 `test1`포함 됩니다 .이는 예외가 전송 된 경우에도 버퍼가 플러시 되었고 디스크에 기록 되었음을 나타냅니다. 외부 예외 처리기에 대 한 제어입니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="e6763-115">`try...with` 구문은 구문`try...finally` 에서 별도의 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="e6763-116">따라서 코드에 `with` 블록과 `finally` 블록이 모두 필요한 경우 다음 코드 예제와 같이 두 구문을 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="e6763-117">시퀀스 식과 비동기 워크플로를 포함 하는 계산 식의 컨텍스트에서 ...를 시도 합니다.  **finally** 식에는 사용자 지정 구현이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="e6763-118">자세한 내용은 [계산 식](../computation-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6763-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6763-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="e6763-119">See also</span></span>

- [<span data-ttu-id="e6763-120">예외 처리</span><span class="sxs-lookup"><span data-stu-id="e6763-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="e6763-121">예외: `try...with` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6763-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
