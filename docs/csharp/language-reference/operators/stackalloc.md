---
title: stackalloc 연산자 - C# 참조
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9c9767e0c9945a9589d049fa7abba192cb928ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846256"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="d9b40-102">stackalloc 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d9b40-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="d9b40-103">`stackalloc` 연산자는 스택의 메모리 블록을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="d9b40-104">메서드 실행 중에 생성된 스택 할당 메모리 블록은 해당 메서드가 반환될 때 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="d9b40-105">`stackalloc` 연산자를 사용하여 할당된 메모리는 명시적으로 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="d9b40-106">스택 할당 메모리 블록에는 [가비지 수집](../../../standard/garbage-collection/index.md)이 적용되지 않으며, [`fixed` 문](../keywords/fixed-statement.md)을 사용해서 고정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="d9b40-107">`stackalloc` 연산자의 결과를 다음 형식 중 하나의 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="d9b40-108">C# 7.2부터 <xref:System.Span%601?displayProperty=nameWithType> 또는 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>(다음 예제 참조):</span><span class="sxs-lookup"><span data-stu-id="d9b40-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="d9b40-109">[ 또는 ](../keywords/unsafe.md) 변수에 스택 할당 메모리 블록을 할당할 때 <xref:System.Span%601>unsafe<xref:System.ReadOnlySpan%601> 컨텍스트를 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="d9b40-110">이러한 형식으로 작업하는 경우 다음 예제와 같이 `stackalloc`조건식[ 또는 대입식에 ](conditional-operator.md) 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="d9b40-111">C# 8.0부터 다음 예제와 같이 `stackalloc` 또는 <xref:System.Span%601> 변수가 허용되는 경우 다른 식 내부에서 <xref:System.ReadOnlySpan%601> 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="d9b40-112">스택 할당 메모리로 작업할 때는 가능한 한, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="d9b40-113">[포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)(다음 예제 참조)</span><span class="sxs-lookup"><span data-stu-id="d9b40-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="d9b40-114">포인터 형식으로 작업할 때는 위 예제와 같이 `unsafe` 컨텍스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="d9b40-115">포인터 형식의 경우 지역 변수 선언에서만 `stackalloc` 식을 사용하여 변수를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="d9b40-116">새로 할당된 메모리의 콘텐츠는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-116">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="d9b40-117">C# 7.3부터, 배열 이니셜라이저 구문을 사용하여 새로 할당된 메모리의 콘텐츠를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-117">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="d9b40-118">다음 예제에서는 이 작업을 수행하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-118">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="d9b40-119">`stackalloc T[E]` 식에서 `T`는 [비관리형 형식](../builtin-types/unmanaged-types.md)이어야 하고 `E`는 [int](../builtin-types/integral-numeric-types.md) 형식의 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-119">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type [int](../builtin-types/integral-numeric-types.md).</span></span>

## <a name="security"></a><span data-ttu-id="d9b40-120">보안</span><span class="sxs-lookup"><span data-stu-id="d9b40-120">Security</span></span>

<span data-ttu-id="d9b40-121">`stackalloc`를 사용하면 CLR(공용 언어 런타임)에서 버퍼 오버런 검색 기능이 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="d9b40-122">버퍼 오버런이 검색되면 악성 코드가 실행될 가능성을 최소화하기 위해 최대한 빨리 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b40-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d9b40-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d9b40-123">C# language specification</span></span>

<span data-ttu-id="d9b40-124">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/unsafe-code.md#stack-allocation)의 [스택 할당](~/_csharplang/spec/introduction.md) 섹션과 중첩 컨텍스트[ 기능 제안 노트의 `stackalloc`허용](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b40-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b40-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9b40-125">See also</span></span>

- [<span data-ttu-id="d9b40-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d9b40-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d9b40-127">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="d9b40-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="d9b40-128">포인터 관련 연산자</span><span class="sxs-lookup"><span data-stu-id="d9b40-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="d9b40-129">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="d9b40-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="d9b40-130">메모리 및 범위 관련 형식</span><span class="sxs-lookup"><span data-stu-id="d9b40-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
