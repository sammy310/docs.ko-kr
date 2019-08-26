---
title: 연산자 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 4870c744383205c2b7e3832c01fb838a545f085f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588614"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="ce17d-102">연산자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ce17d-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="ce17d-103">C#에서 *연산자* 는 식 또는 문에서 하나 이상의 *피연산자* 에 적용되는 프로그램 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="ce17d-104">증가 연산자(`++`)나 `new`같이 피연산자 하나를 사용하는 연산자를 *단항* 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="ce17d-105">산술 연산자(`+`,`-`,`*`,`/`) 같이 피연산자 두 개를 사용하는 연산자를 *이항* 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="ce17d-106">조건 연산자(`?:`)는 피연산자 세 개를 사용하며 이는 C#에서 유일한 삼진 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="ce17d-107">다음 C# 문에는 단항 연산자 하나와 피연산자 하나가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="ce17d-108">증가 연산자 `++`는 피연산자 `y`의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="ce17d-109">다음 C# 문에는 이항 연산자가 두 개 있습니다. 각 연산자는 피연산자를 두 개씩 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="ce17d-110">할당 연산자 `=`에는 정수 변수 `y` 와 식 `2 + 3` 이 피연산자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="ce17d-111">식 `2 + 3` 자체는 더하기 연산자와 두 개의 피연산자, `2` 및 `3`으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="ce17d-112">피연산자는 모든 길이의 코드로 구성된 유효한 식이 될 수 있으며 모든 개수의 하위 식으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="ce17d-113">여러 연산자를 포함하는 식에서 연산자가 적용되는 순서는 *operator precedence*, *associativity*및 괄호로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="ce17d-114">연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="ce17d-114">Operator precedence</span></span>
  
<span data-ttu-id="ce17d-115">각 연산자에는 정의된 우선 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="ce17d-116">다른 우선 순위 수준을 가진 여러 연산자가 포함된 식에서 연산자의 우선 순위는 연산자가 평가되는 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="ce17d-117">예를 들어 다음 명령문은 `n1`에 3을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="ce17d-118">곱셈은 뺄셈보다 우선하기 때문에 곱하기가 가장 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="ce17d-119">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](../../language-reference/operators/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce17d-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="ce17d-120">associativity</span><span class="sxs-lookup"><span data-stu-id="ce17d-120">Associativity</span></span>

 <span data-ttu-id="ce17d-121">우선 순위가 동일한 연산자 두 개 이상이 식 하나에 있으면 두 연산자의 결합성에 따라 연산 순서가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="ce17d-122">왼쪽 결합성이 있는 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="ce17d-123">예를 들어, `x * y / z` 는 `(x * y) / z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="ce17d-124">오른쪽 결합성이 있는 연산자는 오른쪽에서 왼쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="ce17d-125">예를 들어, 할당 연산자는 오른쪽 결합성이 있는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="ce17d-126">아닌 경우 다음 코드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="ce17d-127">또 다른 예로, 3개로 구성된 연산자([?:](../../language-reference/operators/conditional-operator.md))는 오른쪽 결합형이고,</span><span class="sxs-lookup"><span data-stu-id="ce17d-127">As another example the ternary operator ([?:](../../language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="ce17d-128">대부분의 이항 연산자는 왼쪽 결합형입니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="ce17d-129">식에서 연산자가 왼쪽 결합성인지, 오른쪽 결합성인지에 따라 각 식의 피연산자가 먼저 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="ce17d-130">다음 예제는 연산자와 피연산자의 계산 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="ce17d-131">문</span><span class="sxs-lookup"><span data-stu-id="ce17d-131">Statement</span></span>|<span data-ttu-id="ce17d-132">계산 순서</span><span class="sxs-lookup"><span data-stu-id="ce17d-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="ce17d-133">a, b, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="ce17d-134">a, b, c, +, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="ce17d-135">a, b, c, d, \*, +, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="ce17d-136">a, b, c, \*, d, +, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="ce17d-137">a, b, c, -, d, +, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="ce17d-138">a, b, c, -=, +=</span><span class="sxs-lookup"><span data-stu-id="ce17d-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="ce17d-139">괄호 추가</span><span class="sxs-lookup"><span data-stu-id="ce17d-139">Adding parentheses</span></span>

 <span data-ttu-id="ce17d-140">괄호를 사용하여 연산자 우선 순위와 연결을 통해 부과된 실행 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="ce17d-141">예를 들어, `2 + 3 * 2` 는 일반적으로 승제 연산자가 가감 연산자보다 우선하기 때문에 8로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="ce17d-142">그러나 식을 `(2 + 3) * 2`처럼 작성하는 경우 곱셈 전에 덧셈이 계산되고 결과는 10입니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="ce17d-143">다음 예제는 괄호로 묶인 식의 계산 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="ce17d-144">이전 예제에서와 같이 피연산자는 연산자가 적용되기 전에 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="ce17d-145">문</span><span class="sxs-lookup"><span data-stu-id="ce17d-145">Statement</span></span>|<span data-ttu-id="ce17d-146">계산 순서</span><span class="sxs-lookup"><span data-stu-id="ce17d-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="ce17d-147">a, b, c, +, d, \*, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="ce17d-148">a, b, c, d, +, -, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="ce17d-149">a, b, c, +, d, e, -, \*, =</span><span class="sxs-lookup"><span data-stu-id="ce17d-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="ce17d-150">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="ce17d-150">Operator overloading</span></span>

<span data-ttu-id="ce17d-151">사용자 지정 클래스 및 구조체에 대한 특정 연산자의 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="ce17d-152">이러한 과정을 *연산자 오버로드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce17d-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="ce17d-153">자세한 내용은 [연산자 오버로드](../../language-reference/operators/operator-overloading.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce17d-153">For more information, see [Operator overloading](../../language-reference/operators/operator-overloading.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce17d-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce17d-154">See also</span></span>

- [<span data-ttu-id="ce17d-155">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ce17d-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ce17d-156">문, 식, 연산자</span><span class="sxs-lookup"><span data-stu-id="ce17d-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="ce17d-157">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="ce17d-157">C# Operators</span></span>](../../language-reference/operators/index.md)
