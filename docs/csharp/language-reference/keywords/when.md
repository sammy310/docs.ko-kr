---
description: when 상황별 키워드 - C# 참조
title: when 상황별 키워드 - C# 참조
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: bd3a7beeb7d3c4b62d6b70e2b1c6f38ab4b6804f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138217"
---
# <a name="when-c-reference"></a><span data-ttu-id="04460-103">when(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="04460-103">when (C# Reference)</span></span>

<span data-ttu-id="04460-104">`when` 상황별 키워드를 사용하여 다음 컨텍스트에서 필터 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-104">You can use the `when` contextual keyword to specify a filter condition in the following contexts:</span></span>

- <span data-ttu-id="04460-105">[try/catch](try-catch.md) 또는 [try/catch/finally](try-catch-finally.md) 블록의 `catch` 문에서</span><span class="sxs-lookup"><span data-stu-id="04460-105">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="04460-106">[switch](switch.md) 문의 `case` 레이블에서</span><span class="sxs-lookup"><span data-stu-id="04460-106">In the `case` label of a [switch](switch.md) statement.</span></span>
- <span data-ttu-id="04460-107">[`switch` 식](../operators/switch-expression.md)에서</span><span class="sxs-lookup"><span data-stu-id="04460-107">In the [`switch` expression](../operators/switch-expression.md).</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="04460-108">`catch` 문의 `when`</span><span class="sxs-lookup"><span data-stu-id="04460-108">`when` in a `catch` statement</span></span>

<span data-ttu-id="04460-109">C# 6부터, 특정 예외에 대한 처리기를 실행하기 위해 참이 되어야 하는 조건을 지정하기 위해 `catch` 문에서 `when`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-109">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="04460-110">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-110">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="04460-111">여기서 *expr*은 부울 값으로 계산되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="04460-111">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="04460-112">`true`가 반환되면 예외 처리기가 실행되고, `false`가 반환되면 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-112">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="04460-113">다음 예제는 `when` 키워드를 사용하여 예외 메시지의 텍스트에 따라 <xref:System.Net.Http.HttpRequestException>에 대한 처리기를 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="04460-113">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="04460-114">`switch` 문의 `when`</span><span class="sxs-lookup"><span data-stu-id="04460-114">`when` in a `switch` statement</span></span>

<span data-ttu-id="04460-115">C# 7.0부터 `case` 레이블은 더 이상 상호 배타적일 필요가 없으며, `case` 레이블이 `switch` 문에 나타나는 순서에 따라 실행되는 스위치 블록을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-115">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="04460-116">필터 조건도 참인 경우에만 관련 사례 레이블을 참으로 만드는 필터 조건을 지정하려면 `when` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-116">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="04460-117">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04460-117">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="04460-118">여기서 *expr*은 일치 식과 비교되는 상수 패턴 또는 형식 패턴이며 *when-condition*은 부울 식입니다.</span><span class="sxs-lookup"><span data-stu-id="04460-118">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="04460-119">다음 예제에서는 `when` 키워드를 사용하여 영역이 0인 `Shape` 개체를 테스트하고 영역이 0보다 큰 다양한 `Shape` 개체를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="04460-119">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="04460-120">참조</span><span class="sxs-lookup"><span data-stu-id="04460-120">See also</span></span>

- [<span data-ttu-id="04460-121">switch 문</span><span class="sxs-lookup"><span data-stu-id="04460-121">switch statement</span></span>](switch.md)
- [<span data-ttu-id="04460-122">try/catch 문</span><span class="sxs-lookup"><span data-stu-id="04460-122">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="04460-123">try/catch/finally 문</span><span class="sxs-lookup"><span data-stu-id="04460-123">try/catch/finally statement</span></span>](try-catch-finally.md)
