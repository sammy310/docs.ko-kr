---
title: 예외 try...with 식
description: F# ' 시도 ... '를 사용 하는 방법을 알아봅니다. 예외 처리를 위한 식 사용.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630253"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="aeac4-103">예외 try...with 식</span><span class="sxs-lookup"><span data-stu-id="aeac4-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="aeac4-104">이 항목에서는 `try...with` F# 언어의 예외 처리에 사용 되는 식인 식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="aeac4-105">구문</span><span class="sxs-lookup"><span data-stu-id="aeac4-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="aeac4-106">설명</span><span class="sxs-lookup"><span data-stu-id="aeac4-106">Remarks</span></span>

<span data-ttu-id="aeac4-107">식은에서 F#예외를 처리 하는 데 사용 됩니다. `try...with`</span><span class="sxs-lookup"><span data-stu-id="aeac4-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="aeac4-108">의 `try...catch` C#문과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="aeac4-109">위의 구문에서 *expression1* 의 코드는 예외를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="aeac4-110">`try...with` 식은 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="aeac4-111">예외가 throw 되지 않으면 전체 식이 *expression1*의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="aeac4-112">예외가 throw 되 면 각 *패턴* 은 예외와 함께 차례로 비교 되 고 첫 번째 일치 하는 패턴의 경우 해당 분기에 대 한 *예외 처리기*라고 하는 해당 *식이*실행 되 고 전체 식이 실행 됩니다. 해당 예외 처리기에서 식의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="aeac4-113">일치 하는 패턴이 없는 경우 예외는 일치 하는 처리기가 발견 될 때까지 호출 스택을 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="aeac4-114">예외 처리기의 각 식에서 반환 되는 값의 형식은 `try` 블록의 식에서 반환 된 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="aeac4-115">오류가 발생 하는 경우에도 일반적으로 각 예외 처리기의 식에서 반환 될 수 있는 유효한 값이 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="aeac4-116">자주 패턴은 식의 형식을 옵션 형식으로 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="aeac4-117">다음 코드 예제에서는이 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="aeac4-118">예외는 .NET 예외 일 수도 있고 예외 일 F# 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="aeac4-119">키워드를 `exception` 사용 F# 하 여 예외를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="aeac4-120">다양 한 패턴을 사용 하 여 예외 형식 및 기타 조건에 대 한 필터링을 수행할 수 있습니다. 옵션은 다음 표에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="aeac4-121">무늬</span><span class="sxs-lookup"><span data-stu-id="aeac4-121">Pattern</span></span>|<span data-ttu-id="aeac4-122">설명</span><span class="sxs-lookup"><span data-stu-id="aeac4-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="aeac4-123">:?</span><span class="sxs-lookup"><span data-stu-id="aeac4-123">:?</span></span> <span data-ttu-id="aeac4-124">*exception-type*</span><span class="sxs-lookup"><span data-stu-id="aeac4-124">*exception-type*</span></span>|<span data-ttu-id="aeac4-125">지정 된 .NET 예외 형식과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="aeac4-126">:?</span><span class="sxs-lookup"><span data-stu-id="aeac4-126">:?</span></span> <span data-ttu-id="aeac4-127">*예외-* *식별자* 형식</span><span class="sxs-lookup"><span data-stu-id="aeac4-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="aeac4-128">지정 된 .NET 예외 형식과 일치 하지만 예외에 명명 된 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="aeac4-129">*예외-이름* (*인수*)</span><span class="sxs-lookup"><span data-stu-id="aeac4-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="aeac4-130">는 F# 예외 형식과 일치 하 고 인수를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="aeac4-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="aeac4-131">*identifier*</span></span>|<span data-ttu-id="aeac4-132">모든 예외를 일치 시키고 이름을 예외 개체에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="aeac4-133">와 동일 **합니다.** _식별자_ 로 서의 예외</span><span class="sxs-lookup"><span data-stu-id="aeac4-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="aeac4-134">*조건* 에 대 한 *식별자*</span><span class="sxs-lookup"><span data-stu-id="aeac4-134">*identifier* when *condition*</span></span>|<span data-ttu-id="aeac4-135">조건이 true 이면 모든 예외와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="aeac4-136">예</span><span class="sxs-lookup"><span data-stu-id="aeac4-136">Examples</span></span>

<span data-ttu-id="aeac4-137">다음 코드 예제에서는 다양 한 예외 처리기 패턴을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="aeac4-138">`try...with` 구문은 식`try...finally` 에서 분리 된 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="aeac4-139">따라서 코드에 `with` 블록과 `finally` 블록이 모두 필요한 경우에는 두 식을 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="aeac4-140">비동기 워크플로 및 `try...with` 기타 계산 식에서를 사용할 수 있으며,이 경우 사용자 지정 된 버전 `try...with` 의 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="aeac4-141">자세한 내용은 [비동기 워크플로](../asynchronous-workflows.md)및 [계산 식](../computation-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aeac4-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aeac4-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="aeac4-142">See also</span></span>

- [<span data-ttu-id="aeac4-143">예외 처리</span><span class="sxs-lookup"><span data-stu-id="aeac4-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="aeac4-144">예외 형식</span><span class="sxs-lookup"><span data-stu-id="aeac4-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="aeac4-145">예외: `try...finally` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aeac4-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
