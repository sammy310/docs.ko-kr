---
title: '! (null-forgiving) 연산자- C# 참조'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: cf941e5e3fa3fc6313ef8b2ff5c176aec68c1e6b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291682"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="1b78a-103">!</span><span class="sxs-lookup"><span data-stu-id="1b78a-103">!</span></span> <span data-ttu-id="1b78a-104">(null-forgiving) 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1b78a-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="1b78a-105">C# 8.0 이상에서 사용할 수 있는 단항 후위 `!` 연산자는 null-forgiving 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="1b78a-106">[null 허용 주석 컨텍스트](../../nullable-references.md#nullable-annotation-context)가 활성화된 경우에는 참조 형식의 `x` 식이 null이 아님을 선언하는 데 null-forgiving 연산자 `x!`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't null: `x!`.</span></span> <span data-ttu-id="1b78a-107">단항 접두사 `!` 연산자는 [논리 부정 연산자](boolean-logical-operators.md#logical-negation-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-107">The unary prefix `!` operator is a [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="1b78a-108">null-forgiving 연산자는 런타임에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="1b78a-109">식의 null 상태를 변경하여 컴파일러의 정적 흐름 분석에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="1b78a-110">런타임에서 `x!` 식은 기본 식 `x`의 결과로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="1b78a-111">nullable 참조 형식 기능에 대한 자세한 내용은 [nullable 참조 형식](../../nullable-references.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b78a-111">For more information about the nullable reference types feature, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="examples"></a><span data-ttu-id="1b78a-112">예</span><span class="sxs-lookup"><span data-stu-id="1b78a-112">Examples</span></span>

<span data-ttu-id="1b78a-113">null-forgiving 연산자의 사용 사례 중 하나는 인수 유효성 검사 논리를 테스트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="1b78a-114">예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="1b78a-115">[MSTest 테스트 프레임워크](../../../core/testing/unit-testing-with-mstest.md)를 사용하여 생성자에서 유효성 검사 논리에 대해 다음 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="1b78a-116">null-forgiving 연산자가 없으면 컴파일러가 이전 코드에 대해 다음 경고를 생성합니다. `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="1b78a-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="1b78a-117">null-forgiving 연산자를 사용하여 `null`이 전달될 것이고 경고를 표시하지 않아야 함을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-117">With the use of the null-forgiving operator, you let the compiler know that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="1b78a-118">식이 절대로 `null`이 될 수 없지만 컴파일러가 이를 인식할 수 없음이 확실할 경우에도 null-forgiving 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="1b78a-119">다음 예에서는 `IsValid` 메서드가 `true`를 반환하는 경우 해당 인수는 `null`이 아니므로 안전하게 역참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="1b78a-120">null-forgiving 연산자가 없으면 컴파일러가 `p.Name` 코드에 대해 다음 경고를 생성합니다. `Warning CS8602: Dereference of a possibly null reference.`.</span><span class="sxs-lookup"><span data-stu-id="1b78a-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference.`.</span></span>

<span data-ttu-id="1b78a-121">`IsValid` 메서드를 수정할 수 있는 경우 [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) 특성을 사용하여 메서드가 `true`를 반환할 때 `IsValid` 메서드의 인수는 `null`일 수 없다는 것을 컴파일러에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to let the compiler know that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="1b78a-122">앞의 예제에서는 컴파일러가 `if` 문 내에서 `p`가 `null`일 수 없다는 것을 확인할 수 있는 충분한 정보를 제공하기 때문에 null-forgiving 연산자를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b78a-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="1b78a-123">변수의 null 상태에 대한 추가 정보를 지정하는 데 사용할 수 있는 특성에 대한 자세한 내용은 [null 예상을 정의하는 특성을 포함한 API 업그레이드](../../nullable-attributes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b78a-123">For more information about the attributes that allow you to specify additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b78a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b78a-124">See also</span></span>

- [<span data-ttu-id="1b78a-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1b78a-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1b78a-126">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="1b78a-126">C# operators</span></span>](index.md)
- [<span data-ttu-id="1b78a-127">자습서: nullable 참조 형식을 사용하여 디자인</span><span class="sxs-lookup"><span data-stu-id="1b78a-127">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
