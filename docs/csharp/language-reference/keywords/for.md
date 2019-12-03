---
title: 문 - C# 참조
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: fc6a23cabd93323cacc33dfc4388116881c1fc84
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552262"
---
# <a name="for-c-reference"></a><span data-ttu-id="475a1-102">for(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="475a1-102">for (C# reference)</span></span>

<span data-ttu-id="475a1-103">`for` 문은 지정된 부울 식이 `true`로 계산되는 동안 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-103">The `for` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="475a1-104">`for` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="475a1-105">[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `for` 루프를 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-105">You also can exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="475a1-106">`for` 문의 구조</span><span class="sxs-lookup"><span data-stu-id="475a1-106">Structure of the `for` statement</span></span>

<span data-ttu-id="475a1-107">`for` 문은 *initializer*, *condition* 및 *iterator* 섹션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="475a1-108">세 개의 섹션은 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-108">All three sections are optional.</span></span> <span data-ttu-id="475a1-109">루프의 본문은 명령문 또는 명령문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="475a1-110">다음 예제에서는 모든 섹션이 정의된 `for` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="475a1-111">*initializer* 섹션</span><span class="sxs-lookup"><span data-stu-id="475a1-111">The *initializer* section</span></span>

<span data-ttu-id="475a1-112">*initializer* 섹션의 명령문은 루프로 유입되기 전에 한 번만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="475a1-113">*initializer* 섹션은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="475a1-114">루프 외부에서 액세스할 수 없는 로컬 루프 변수의 선언 및 초기화</span><span class="sxs-lookup"><span data-stu-id="475a1-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="475a1-115">쉼표로 구분된 다음 목록의 0개 이상의 명령문 식:</span><span class="sxs-lookup"><span data-stu-id="475a1-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="475a1-116">[assignment](../operators/assignment-operator.md) 문</span><span class="sxs-lookup"><span data-stu-id="475a1-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="475a1-117">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="475a1-117">invocation of a method</span></span>

  - <span data-ttu-id="475a1-118">접두사 또는 후위 [increment](../operators/arithmetic-operators.md#increment-operator-) 식(예: `++i` 또는`i++`)</span><span class="sxs-lookup"><span data-stu-id="475a1-118">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="475a1-119">접두사 또는 후위 [decrement](../operators/arithmetic-operators.md#decrement-operator---) 식(예: `--i` 또는`i--`)</span><span class="sxs-lookup"><span data-stu-id="475a1-119">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="475a1-120">[new](../operators/new-operator.md) 연산자를 사용하여 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="475a1-120">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

  - <span data-ttu-id="475a1-121">[await](../operators/await.md) 식</span><span class="sxs-lookup"><span data-stu-id="475a1-121">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="475a1-122">위의 예제에서 *initializer* 섹션은 로컬 루프 변수 `i`를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="475a1-123">*condition* 섹션</span><span class="sxs-lookup"><span data-stu-id="475a1-123">The *condition* section</span></span>

<span data-ttu-id="475a1-124">*condition* 섹션이 있으면 부울 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="475a1-125">이 식은 모든 루프 반복 전에 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="475a1-126">*condition* 섹션이 없거나 부울 식이 `true`로 평가되는 경우, 다음 루프 반복이 실행되고 그렇지 않으면 루프가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="475a1-127">위의 예제에서 *condition* 섹션은 로컬 루프 변수의 값에 따라 루프가 종료되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="475a1-128">*iterator* 섹션</span><span class="sxs-lookup"><span data-stu-id="475a1-128">The *iterator* section</span></span>

<span data-ttu-id="475a1-129">*iterator* 섹션은 루프의 본문을 반복할 때마다 수행되는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="475a1-130">*iterator* 섹션에는 쉼표로 구분된 다음 명령문 식이 0개 이상 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="475a1-131">[assignment](../operators/assignment-operator.md) 문</span><span class="sxs-lookup"><span data-stu-id="475a1-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="475a1-132">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="475a1-132">invocation of a method</span></span>

- <span data-ttu-id="475a1-133">접두사 또는 후위 [increment](../operators/arithmetic-operators.md#increment-operator-) 식(예: `++i` 또는`i++`)</span><span class="sxs-lookup"><span data-stu-id="475a1-133">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="475a1-134">접두사 또는 후위 [decrement](../operators/arithmetic-operators.md#decrement-operator---) 식(예: `--i` 또는`i--`)</span><span class="sxs-lookup"><span data-stu-id="475a1-134">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="475a1-135">[new](../operators/new-operator.md) 연산자를 사용하여 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="475a1-135">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

- <span data-ttu-id="475a1-136">[await](../operators/await.md) 식</span><span class="sxs-lookup"><span data-stu-id="475a1-136">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="475a1-137">위 예제의 *iterator* 섹션은 로컬 루프 변수를 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="475a1-138">예</span><span class="sxs-lookup"><span data-stu-id="475a1-138">Examples</span></span>

<span data-ttu-id="475a1-139">다음 예제에서는 *initializer* 섹션에서 외부 루프 변수에 값 할당, *initializer* 및 *iterator* 섹션에서 메서드 호출, *iterator* 섹션에서 두 변수의 값 변경과 같이 `for` 문 섹션의 여러 가지 덜 일반적인 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="475a1-140">**Run**을 선택하여 예제 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="475a1-141">그런 다음, 코드를 수정하고 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-141">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="475a1-142">다음 예제에서는 무한 `for` 루프를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="475a1-142">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="475a1-143">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="475a1-143">C# language specification</span></span>

<span data-ttu-id="475a1-144">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [for 문](~/_csharplang/spec/statements.md#the-for-statement) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="475a1-144">For more information, see [The for statement](~/_csharplang/spec/statements.md#the-for-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="475a1-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="475a1-145">See also</span></span>

- [<span data-ttu-id="475a1-146">C# 참조</span><span class="sxs-lookup"><span data-stu-id="475a1-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="475a1-147">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="475a1-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="475a1-148">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="475a1-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="475a1-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="475a1-149">foreach, in</span></span>](foreach-in.md)
