---
title: stackalloc 연산자 - C# 참조
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: f211acaa8c47ab42a1f7f06cff6c35570cd22b75
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433837"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="dd7aa-102">stackalloc 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dd7aa-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="dd7aa-103">`stackalloc` 연산자는 스택의 메모리 블록을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="dd7aa-104">메서드 실행 중에 생성된 스택 할당 메모리 블록은 해당 메서드가 반환될 때 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="dd7aa-105">`stackalloc` 연산자를 사용하여 할당된 메모리는 명시적으로 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="dd7aa-106">스택 할당 메모리 블록에는 [가비지 수집](../../../standard/garbage-collection/index.md)이 적용되지 않으며, [`fixed` 문](../keywords/fixed-statement.md)을 사용해서 고정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="dd7aa-107">`stackalloc T[E]` 식에서 `T`는 [비관리형 형식](../builtin-types/unmanaged-types.md)이어야 하고 `E`는 `int` 형식의 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="dd7aa-108">`stackalloc` 연산자의 결과를 다음 형식 중 하나의 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="dd7aa-109">C# 7.2부터 <xref:System.Span%601?displayProperty=nameWithType> 또는 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>(다음 예제 참조)</span><span class="sxs-lookup"><span data-stu-id="dd7aa-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="dd7aa-110"><xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 변수에 스택 할당 메모리 블록을 할당할 때 [unsafe](../keywords/unsafe.md) 컨텍스트를 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="dd7aa-111">이러한 형식으로 작업하는 경우 다음 예제와 같이 [조건식](conditional-operator.md) 또는 대입식에 `stackalloc` 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="dd7aa-112">스택 할당 메모리로 작업할 때는 가능한 한, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="dd7aa-113">[포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)(다음 예제 참조)</span><span class="sxs-lookup"><span data-stu-id="dd7aa-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="dd7aa-114">포인터 형식으로 작업할 때는 위 예제와 같이 `unsafe` 컨텍스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="dd7aa-115">새로 할당된 메모리의 콘텐츠는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-115">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="dd7aa-116">C# 7.3부터, 배열 이니셜라이저 구문을 사용하여 새로 할당된 메모리의 콘텐츠를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-116">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="dd7aa-117">다음 예제에서는 이 작업을 수행하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-117">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="dd7aa-118">보안</span><span class="sxs-lookup"><span data-stu-id="dd7aa-118">Security</span></span>

<span data-ttu-id="dd7aa-119">`stackalloc`를 사용하면 CLR(공용 언어 런타임)에서 버퍼 오버런 검색 기능이 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-119">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="dd7aa-120">버퍼 오버런이 검색되면 악성 코드가 실행될 가능성을 최소화하기 위해 최대한 빨리 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-120">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dd7aa-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="dd7aa-121">C# language specification</span></span>

<span data-ttu-id="dd7aa-122">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [스택 할당](~/_csharplang/spec/unsafe-code.md#stack-allocation) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd7aa-122">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd7aa-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd7aa-123">See also</span></span>

- [<span data-ttu-id="dd7aa-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dd7aa-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="dd7aa-125">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="dd7aa-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="dd7aa-126">포인터 관련 연산자</span><span class="sxs-lookup"><span data-stu-id="dd7aa-126">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="dd7aa-127">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="dd7aa-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="dd7aa-128">메모리 및 범위 관련 형식</span><span class="sxs-lookup"><span data-stu-id="dd7aa-128">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
