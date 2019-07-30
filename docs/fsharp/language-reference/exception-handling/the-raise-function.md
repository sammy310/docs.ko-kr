---
title: '예외: raise 함수'
description: F# ' Raise ' 함수를 사용 하 여 오류 또는 예외 조건이 발생 했음을 나타내는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630295"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="35ae7-103">예외: raise 함수</span><span class="sxs-lookup"><span data-stu-id="35ae7-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="35ae7-104">`raise` 함수는 오류 또는 예외 조건이 발생 했음을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="35ae7-105">오류에 대 한 정보는 예외 개체에서 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="35ae7-106">구문</span><span class="sxs-lookup"><span data-stu-id="35ae7-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="35ae7-107">설명</span><span class="sxs-lookup"><span data-stu-id="35ae7-107">Remarks</span></span>

<span data-ttu-id="35ae7-108">함수 `raise` 는 예외 개체를 생성 하 고 스택 해제 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="35ae7-109">스택 해제 프로세스는 CLR (공용 언어 런타임)에 의해 관리 되므로이 프로세스의 동작은 다른 .NET 언어와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="35ae7-110">스택 해제 프로세스는 생성 된 예외와 일치 하는 예외 처리기를 검색 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="35ae7-111">검색은 현재 `try...with` 식 (있는 경우)에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="35ae7-112">`with` 블록의 각 패턴은 순서 대로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="35ae7-113">일치 하는 예외 처리기가 있으면 예외가 처리 된 것으로 간주 됩니다. 그렇지 않으면 스택이 해제 되 고 `with` 일치 하는 처리기가 발견 될 때까지 호출 체인의 블록이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="35ae7-114">호출 `finally` 체인에서 발생 하는 모든 블록은 스택이 해제 될 때 순서 대로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="35ae7-115">함수 `raise` 는 C# 또는 C++의 `throw` 에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="35ae7-116">Catch `reraise` 처리기에서를 사용 하 여 호출 체인을 통해 동일한 예외를 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="35ae7-117">다음 코드 예제에서는 `raise` 함수를 사용 하 여 예외를 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="35ae7-118">다음 예제와 같이 함수를사용하여.net예외를발생시킬수도있습니다.`raise`</span><span class="sxs-lookup"><span data-stu-id="35ae7-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="35ae7-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="35ae7-119">See also</span></span>

- [<span data-ttu-id="35ae7-120">예외 처리</span><span class="sxs-lookup"><span data-stu-id="35ae7-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="35ae7-121">예외 형식</span><span class="sxs-lookup"><span data-stu-id="35ae7-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="35ae7-122">예외: `try...with` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="35ae7-123">예외: `try...finally` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="35ae7-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="35ae7-124">예외: `failwith` 함수</span><span class="sxs-lookup"><span data-stu-id="35ae7-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="35ae7-125">예외: `invalidArg` 함수</span><span class="sxs-lookup"><span data-stu-id="35ae7-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
