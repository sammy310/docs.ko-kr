---
title: => 연산자 - C# 참조
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 6e6ace55e7557e940970675c99ec4db87c124f1d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633893"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="18d90-102">=> 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="18d90-102">=> operator (C# Reference)</span></span>

<span data-ttu-id="18d90-103">`=>` 토큰은 람다 연산자와 식 본문 정의의 멤버 이름과 멤버 구현의 구분자라는 두 가지 형식으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="18d90-104">람다 연산자</span><span class="sxs-lookup"><span data-stu-id="18d90-104">Lambda operator</span></span>

<span data-ttu-id="18d90-105">[람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md)에서 람다 연산자 `=>`은 왼쪽의 입력 변수를 오른쪽의 람다 본문과 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="18d90-106">다음 예제에서는 메서드 구문이 포함된 [LINQ](../../programming-guide/concepts/linq/index.md) 기능을 사용하여 람다 식의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

<span data-ttu-id="18d90-107">람다 식의 입력 변수는 컴파일 시 강력한 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="18d90-108">위의 예제와 같이 컴파일러가 입력 변수의 형식을 추론하는 경우, 형식 선언을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="18d90-109">입력 변수의 형식을 지정해야 하는 경우 다음 예제와 같이 각 변수에 대해 입력 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

<span data-ttu-id="18d90-110">다음 예제에서는 입력 변수 없이 람다 식을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

<span data-ttu-id="18d90-111">자세한 내용은 [람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18d90-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="18d90-112">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="18d90-112">Expression body definition</span></span>

<span data-ttu-id="18d90-113">식 본문 정의의 일반 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="18d90-114">여기서 *expression*은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="18d90-115">*식*은 멤버의 반환 형식이 `void`이거나 멤버가 생성자, 종료자, 또는 속성 `set` 접근자인 경우에만 *명령문 식*일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="18d90-116">다음 예제에서는 `Person.ToString` 메서드에 대한 식 본문 정의를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="18d90-117">다음과 같은 메서드 정의의 약식 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="18d90-118">메서드 및 읽기 전용 속성에 대한 식 본문 정의는 C# 6부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="18d90-119">생성자, 종료자, 속성 접근자 및 인덱서에 대한 식 본문 정의는 C# 7.0부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="18d90-120">자세한 내용은 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18d90-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="18d90-121">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="18d90-121">Operator overloadability</span></span>

<span data-ttu-id="18d90-122">`=>` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18d90-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18d90-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="18d90-123">C# language specification</span></span>

<span data-ttu-id="18d90-124">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18d90-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18d90-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18d90-125">See also</span></span>

- [<span data-ttu-id="18d90-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="18d90-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="18d90-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="18d90-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="18d90-128">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="18d90-128">C# Operators</span></span>](index.md)
- [<span data-ttu-id="18d90-129">람다 식</span><span class="sxs-lookup"><span data-stu-id="18d90-129">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="18d90-130">식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="18d90-130">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)
