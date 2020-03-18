---
title: if-else - C# 참조
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 98c1a8dceec3e5a47627841988e2d722c56fc36c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715257"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="561f3-102">if-else(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="561f3-102">if-else (C# Reference)</span></span>

<span data-ttu-id="561f3-103">`if` 문은 부울 식의 값에 따라 실행할 문을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-103">An `if` statement identifies which statement to run based on the value of a Boolean expression.</span></span> <span data-ttu-id="561f3-104">다음 예제에서는 `bool` 변수 `condition` 가 `true` 로 설정된 다음 `if` 문에서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-104">In the following example, the `bool` variable `condition` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="561f3-105">출력은 `The variable is set to true.`입니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-105">The output is `The variable is set to true.`.</span></span>

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

<span data-ttu-id="561f3-106">콘솔 앱의 `Main` 메서드에 배치하여 이 항목의 예제를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-106">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>

<span data-ttu-id="561f3-107">C#의 `if` 문은 다음 예제와 같이 두 가지 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-107">An `if` statement in C# can take two forms, as the following example shows.</span></span>

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

<span data-ttu-id="561f3-108">`if-else` 문에서 `condition` 이 true로 평가되는 경우 `then-statement` 가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-108">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="561f3-109">`condition` 이 false이면 `else-statement` 가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-109">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="561f3-110">`condition` 이 true인 동시에 false일 수는 없으므로 `then-statement` 문의 `else-statement` 및 `if-else` 를 둘 다 실행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-110">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="561f3-111">`then-statement` 또는 `else-statement` 가 실행된 후 제어가 `if` 문 뒤의 다음 문으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-111">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="561f3-112">`if` 문을 포함하지 않는 `else` 문에서 `condition` 이 true이면 `then-statement` 가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-112">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="561f3-113">`condition` 이 false이면 제어가 `if` 문 뒤의 다음 문으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-113">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="561f3-114">`then-statement` 및 `else-statement` 는 둘 다 단일 문이나 중괄호(`{}`)로 묶인 여러 문으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-114">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="561f3-115">단일 문의 경우 중괄호는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-115">For a single statement, the braces are optional but recommended.</span></span>

<span data-ttu-id="561f3-116">`then-statement` 및 `else-statement` 의 문은 원래 `if` 문 내부에 중첩된 다른 `if` 문을 포함하여 모든 종류일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-116">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="561f3-117">중첩된 `if` 문에서 각 `else` 절은 해당 `if` 가 없는 마지막 `else`에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-117">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="561f3-118">다음 예제에서 `Result1` 및 `m > 10` 이 둘 다 true이면 `n > 20` 이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-118">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="561f3-119">`m > 10` 이 true이지만 `n > 20` 이 false이면 `Result2` 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-119">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

<span data-ttu-id="561f3-120">`Result2` 이 false일 때 `(m > 10)` 를 대신 표시하려는 경우 다음 예제와 같이 중괄호로 중첩된 `if` 문의 시작 및 끝을 설정하여 해당 연결을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-120">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

<span data-ttu-id="561f3-121">조건`Result2` 이 false이면 `(m > 10)` 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-121">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>

## <a name="example"></a><span data-ttu-id="561f3-122">예제</span><span class="sxs-lookup"><span data-stu-id="561f3-122">Example</span></span>

<span data-ttu-id="561f3-123">다음 예제에서는 키보드에서 문자 하나를 입력하며, 프로그램이 중첩된 `if` 문을 사용하여 입력 문자가 영문자인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-123">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="561f3-124">입력 문자가 영문자이면 프로그램에서 입력 문자가 소문자인지 대문자인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-124">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="561f3-125">각 경우에 대한 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-125">A message appears for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a><span data-ttu-id="561f3-126">예제</span><span class="sxs-lookup"><span data-stu-id="561f3-126">Example</span></span>

<span data-ttu-id="561f3-127">다음 부분 코드와 같이 `if` 문을 else 블록 안에 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-127">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="561f3-128">예제에서는 `if` 문을 else 블록 2개와 then 블록 1개 안에 중첩합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-128">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="561f3-129">주석은 각 블록에서 true 또는 false인 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-129">The comments specify which conditions are true or false in each block.</span></span>

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a><span data-ttu-id="561f3-130">예제</span><span class="sxs-lookup"><span data-stu-id="561f3-130">Example</span></span>

<span data-ttu-id="561f3-131">다음 예제에서는 입력 문자가 소문자, 대문자 또는 숫자인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-131">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="561f3-132">세 가지 조건이 모두 false이면 문자는 영숫자 문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-132">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="561f3-133">예제에서는 각 경우에 대한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-133">The example displays a message for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

<span data-ttu-id="561f3-134">else 블록 또는 then 블록의 문이 유효한 모든 문일 수 있는 것과 마찬가지로 유효한 모든 부울 식을 조건에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-134">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="561f3-135">[, ](../operators/boolean-logical-operators.md), `!`, `&&`, `||` 및 `&`와 같은 `|`논리 연산자`^`를 사용하여 복합 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-135">You can use [logical operators](../operators/boolean-logical-operators.md) such as `!`, `&&`, `||`, `&`, `|`, and `^` to make compound conditions.</span></span> <span data-ttu-id="561f3-136">다음 코드는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="561f3-136">The following code shows examples.</span></span>

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a><span data-ttu-id="561f3-137">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="561f3-137">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="561f3-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="561f3-138">See also</span></span>

- [<span data-ttu-id="561f3-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="561f3-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="561f3-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="561f3-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="561f3-141">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="561f3-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="561f3-142">?: 연산자</span><span class="sxs-lookup"><span data-stu-id="561f3-142">?: Operator</span></span>](../operators/conditional-operator.md)
- [<span data-ttu-id="561f3-143">if-else 문(C++)</span><span class="sxs-lookup"><span data-stu-id="561f3-143">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)
- [<span data-ttu-id="561f3-144">switch</span><span class="sxs-lookup"><span data-stu-id="561f3-144">switch</span></span>](switch.md)
