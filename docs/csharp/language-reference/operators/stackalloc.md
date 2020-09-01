---
description: stackalloc 식 - C# 참조
title: stackalloc 식 - C# 참조
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 72d91cf9aa67957ed8e1cad5b2c4a1f3b6382c1f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136852"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="43e23-103">stackalloc 식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="43e23-103">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="43e23-104">`stackalloc` 식은 스택에 메모리 블록을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-104">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="43e23-105">메서드 실행 중에 생성된 스택 할당 메모리 블록은 해당 메서드가 반환될 때 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-105">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="43e23-106">`stackalloc`을 사용하여 할당된 메모리를 명시적으로 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-106">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="43e23-107">스택 할당 메모리 블록에는 [가비지 수집](../../../standard/garbage-collection/index.md)이 적용되지 않으며, [`fixed` 문](../keywords/fixed-statement.md)을 사용해서 고정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-107">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="43e23-108">`stackalloc` 식의 결과를 다음 형식 중 하나의 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-108">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="43e23-109">C# 7.2부터 <xref:System.Span%601?displayProperty=nameWithType> 또는 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>(다음 예제 참조):</span><span class="sxs-lookup"><span data-stu-id="43e23-109">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/shared/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="43e23-110"><xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 변수에 스택 할당 메모리 블록을 할당할 때 [unsafe](../keywords/unsafe.md) 컨텍스트를 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="43e23-111">이러한 형식으로 작업하는 경우 다음 예제와 같이 [조건식](conditional-operator.md) 또는 대입식에 `stackalloc` 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/shared/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="43e23-112">C# 8.0부터 다음 예제와 같이 <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 변수가 허용되는 경우 다른 식 내부에서 `stackalloc` 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-112">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/shared/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="43e23-113">스택 할당 메모리로 작업할 때는 가능한 한, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-113">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="43e23-114">[포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)(다음 예제 참조)</span><span class="sxs-lookup"><span data-stu-id="43e23-114">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/shared/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="43e23-115">포인터 형식으로 작업할 때는 위 예제와 같이 `unsafe` 컨텍스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-115">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="43e23-116">포인터 형식의 경우 지역 변수 선언에서만 `stackalloc` 식을 사용하여 변수를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-116">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="43e23-117">스택에서 사용 가능한 메모리 양이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-117">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="43e23-118">스택에 너무 많은 메모리를 할당하는 경우 <xref:System.StackOverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-118">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="43e23-119">이를 방지하려면 다음 규칙을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="43e23-119">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="43e23-120">`stackalloc`을 사용하여 할당하는 메모리의 양을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-120">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/shared/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="43e23-121">스택에서 사용 가능한 메모리 양은 코드를 실행하는 환경에 따라 달라지므로 실제 제한 값을 정의할 때는 신중해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-121">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="43e23-122">루프 내부에서 `stackalloc`을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="43e23-122">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="43e23-123">루프 외부에서 메모리 블록을 할당하고 루프 내부에서 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-123">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="43e23-124">새로 할당된 메모리의 콘텐츠는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-124">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="43e23-125">사용하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-125">You should initialize it before the use.</span></span> <span data-ttu-id="43e23-126">예를 들어 모든 항목을 `T`형식의 기본값으로 설정하는 <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-126">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="43e23-127">C# 7.3부터, 배열 이니셜라이저 구문을 사용하여 새로 할당된 메모리의 콘텐츠를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-127">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="43e23-128">다음 예제에서는 이 작업을 수행하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-128">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/shared/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="43e23-129">식 `stackalloc T[E]`에서 `T`는 [관리되지 않는 형식](../builtin-types/unmanaged-types.md)이어야 하며 `E`는 음수가 아닌 [int](../builtin-types/integral-numeric-types.md) 값으로 계산되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-129">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="43e23-130">보안</span><span class="sxs-lookup"><span data-stu-id="43e23-130">Security</span></span>

<span data-ttu-id="43e23-131">`stackalloc`를 사용하면 CLR(공용 언어 런타임)에서 버퍼 오버런 검색 기능이 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-131">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="43e23-132">버퍼 오버런이 검색되면 악성 코드가 실행될 가능성을 최소화하기 위해 최대한 빨리 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="43e23-132">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="43e23-133">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="43e23-133">C# language specification</span></span>

<span data-ttu-id="43e23-134">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [스택 할당](~/_csharplang/spec/unsafe-code.md#stack-allocation) 섹션과 중첩 컨텍스트[ 기능 제안 노트의 `stackalloc` 허용](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43e23-134">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="43e23-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43e23-135">See also</span></span>

- [<span data-ttu-id="43e23-136">C# 참조</span><span class="sxs-lookup"><span data-stu-id="43e23-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="43e23-137">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="43e23-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="43e23-138">포인터 관련 연산자</span><span class="sxs-lookup"><span data-stu-id="43e23-138">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="43e23-139">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="43e23-139">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="43e23-140">메모리 및 범위 관련 형식</span><span class="sxs-lookup"><span data-stu-id="43e23-140">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="43e23-141">stackalloc 관련 실행 사항 및 금지 사항</span><span class="sxs-lookup"><span data-stu-id="43e23-141">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
