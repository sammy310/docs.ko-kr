---
title: 포인터 관련 연산자 - C# 참조
description: 포인터로 작업할 때 사용할 수 있는 C# 연산자에 대해 알아봅니다.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 2d522e9357fb6da7b8d66a663e99e8858c9dd521
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480385"
---
# <a name="pointer-related-operators-c-reference"></a><span data-ttu-id="4bdcc-103">포인터 관련 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4bdcc-103">Pointer related operators (C# reference)</span></span>

<span data-ttu-id="4bdcc-104">다음 연산자를 사용하여 포인터로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-104">You can use the following operators to work with pointers:</span></span>

- <span data-ttu-id="4bdcc-105">단항 [`&`(address-of)](#address-of-operator-) 연산자: 변수의 주소를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="4bdcc-105">Unary [`&` (address-of)](#address-of-operator-) operator: to get the address of a variable</span></span>
- <span data-ttu-id="4bdcc-106">단항 [`*`(포인터 간접 참조)](#pointer-indirection-operator-) 연산자: 포인터가 가리키는 변수를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="4bdcc-106">Unary [`*` (pointer indirection)](#pointer-indirection-operator-) operator: to obtain the variable pointed by a pointer</span></span>
- <span data-ttu-id="4bdcc-107">[`->`(멤버 액세스)](#pointer-member-access-operator--) 및 [`[]`(요소 액세스)](#pointer-element-access-operator-) 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-107">The [`->` (member access)](#pointer-member-access-operator--) and [`[]` (element access)](#pointer-element-access-operator-) operators</span></span>
- <span data-ttu-id="4bdcc-108">산술 연산자 [`+`, `-`, `++` 및 `--`](#pointer-arithmetic-operators)</span><span class="sxs-lookup"><span data-stu-id="4bdcc-108">Arithmetic operators [`+`, `-`, `++`, and `--`](#pointer-arithmetic-operators)</span></span>
- <span data-ttu-id="4bdcc-109">비교 연산자 [`==`, `!=`, `<`, `>`, `<=` 및 `>=`](#pointer-comparison-operators)</span><span class="sxs-lookup"><span data-stu-id="4bdcc-109">Comparison operators [`==`, `!=`, `<`, `>`, `<=`, and `>=`](#pointer-comparison-operators)</span></span>

<span data-ttu-id="4bdcc-110">포인터 형식에 대한 내용은 [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-110">For information about pointer types, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4bdcc-111">포인터를 사용한 작업에는 [안전하지 않은](../keywords/unsafe.md) 컨텍스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-111">Any operation with pointers requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="4bdcc-112">안전하지 않은 블록을 포함하는 코드는 [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks) 컴파일러 옵션을 사용하여 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-112">The code that contains unsafe blocks must be compiled with the [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks) compiler option.</span></span>

## <a name="address-of-operator-amp"></a><a name="address-of-operator-"></a> <span data-ttu-id="4bdcc-113">Address-of 연산자 &amp;</span><span class="sxs-lookup"><span data-stu-id="4bdcc-113">Address-of operator &amp;</span></span>

<span data-ttu-id="4bdcc-114">단항 `&` 연산자는 해당 피연산자의 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-114">The unary `&` operator returns the address of its operand:</span></span>

[!code-csharp[address of local](snippets/shared/PointerOperators.cs#AddressOf)]

<span data-ttu-id="4bdcc-115">`&` 연산자의 피연산자는 고정 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-115">The operand of the `&` operator must be a fixed variable.</span></span> <span data-ttu-id="4bdcc-116">*고정* 변수는 [가비지 수집기](../../../standard/garbage-collection/index.md)의 작동에 영향을 받지 않는 스토리지 위치에 있는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-116">*Fixed* variables are variables that reside in storage locations that are unaffected by operation of the [garbage collector](../../../standard/garbage-collection/index.md).</span></span> <span data-ttu-id="4bdcc-117">앞의 예제에서 로컬 변수 `number`는 스택에 있으므로 고정 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-117">In the preceding example, the local variable `number` is a fixed variable, because it resides on the stack.</span></span> <span data-ttu-id="4bdcc-118">가비지 수집기에 의해 영향을 받을 수 있는 스토리지 위치에 상주하는 변수(예: 재배치됨)를 *이동 가능한* 변수라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-118">Variables that reside in storage locations that can be affected by the garbage collector (for example, relocated) are called *movable* variables.</span></span> <span data-ttu-id="4bdcc-119">개체 필드 및 배열 요소는 이동 가능한 변수의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-119">Object fields and array elements are examples of movable variables.</span></span> <span data-ttu-id="4bdcc-120">[`fixed` 문](../keywords/fixed-statement.md)으로 "fix" 또는 "pin"으로 할 경우 이동 가능한 변수의 주소를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-120">You can get the address of a movable variable if you "fix", or "pin", it with a [`fixed` statement](../keywords/fixed-statement.md).</span></span> <span data-ttu-id="4bdcc-121">가져온 주소는 `fixed` 문 블록 내에서만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-121">The obtained address is valid only inside the block of a `fixed` statement.</span></span> <span data-ttu-id="4bdcc-122">다음 예제에서는 `fixed` 문과 `&` 연산자를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-122">The following example shows how to use a `fixed` statement and the `&` operator:</span></span>

[!code-csharp[address of fixed](snippets/shared/PointerOperators.cs#AddressOfFixed)]

<span data-ttu-id="4bdcc-123">상수 또는 값의 주소를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-123">You can't get the address of a constant or a value.</span></span>

<span data-ttu-id="4bdcc-124">고정 및 이동 가능한 변수에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [고정 및 이동 가능 변수](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-124">For more information about fixed and movable variables, see the [Fixed and moveable variables](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="4bdcc-125">이진 `&` 연산자는 해당 부울 피연산자의 [논리 AND](boolean-logical-operators.md#logical-and-operator-) 또는 해당 정수 피연산자의 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-)를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-125">The binary `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its Boolean operands or the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its integral operands.</span></span>

## <a name="pointer-indirection-operator-"></a><span data-ttu-id="4bdcc-126">포인터 간접 참조 연산자 \*</span><span class="sxs-lookup"><span data-stu-id="4bdcc-126">Pointer indirection operator \*</span></span>

<span data-ttu-id="4bdcc-127">단항 포인터 간접 참조 연산자 `*`는 피연산자가 가리키는 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-127">The unary pointer indirection operator `*` obtains the variable to which its operand points.</span></span> <span data-ttu-id="4bdcc-128">역참조 연산자라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-128">It's also known as the dereference operator.</span></span> <span data-ttu-id="4bdcc-129">`*` 연산자의 피연산자는 포인터 형식이여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-129">The operand of the `*` operator must be of a pointer type.</span></span>

[!code-csharp[pointer indirection](snippets/shared/PointerOperators.cs#PointerIndirection)]

<span data-ttu-id="4bdcc-130">`*` 연산자를 `void*` 유형의 식에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-130">You cannot apply the `*` operator to an expression of type `void*`.</span></span>

<span data-ttu-id="4bdcc-131">이진 `*` 연산자는 해당 숫자 피연산자의 [곱](arithmetic-operators.md#multiplication-operator-)을 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-131">The binary `*` operator computes the [product](arithmetic-operators.md#multiplication-operator-) of its numeric operands.</span></span>

## <a name="pointer-member-access-operator--"></a><span data-ttu-id="4bdcc-132">포인터 멤버 액세스 연산자 -></span><span class="sxs-lookup"><span data-stu-id="4bdcc-132">Pointer member access operator -></span></span>

<span data-ttu-id="4bdcc-133">`->` 연산자는 포인터 [간접 참조](#pointer-indirection-operator-)와 [멤버 액세스](member-access-operators.md#member-access-expression-)를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-133">The `->` operator combines [pointer indirection](#pointer-indirection-operator-) and [member access](member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="4bdcc-134">즉, `x`가 `T*` 형식의 포인터이고 `y`가 `T`의 액세스 가능한 멤버인 경우 양식의 식은</span><span class="sxs-lookup"><span data-stu-id="4bdcc-134">That is, if `x` is a pointer of type `T*` and `y` is an accessible member of type `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="4bdcc-135">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-135">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="4bdcc-136">다음 예제에서는 `->` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-136">The following example demonstrates the usage of the `->` operator:</span></span>

[!code-csharp[pointer member access](snippets/shared/PointerOperators.cs#MemberAccess)]

<span data-ttu-id="4bdcc-137">`->` 연산자를 `void*` 유형의 식에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-137">You cannot apply the `->` operator to an expression of type `void*`.</span></span>

## <a name="pointer-element-access-operator-"></a><span data-ttu-id="4bdcc-138">포인터 요소 액세스 연산자 []</span><span class="sxs-lookup"><span data-stu-id="4bdcc-138">Pointer element access operator []</span></span>

<span data-ttu-id="4bdcc-139">포인터 형식의 식 `p`의 경우 `p[n]` 양식의 포인터 요소 액세스는 `*(p + n)`으로 평가됩니다. 여기서 `n`은 암시적으로 `int`, `uint`, `long` 또는 `ulong`으로 전환할 수 있는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-139">For an expression `p` of a pointer type, a pointer element access of the form `p[n]` is evaluated as `*(p + n)`, where `n` must be of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="4bdcc-140">포인터가 있는 `+` 연산자의 동작에 대한 자세한 내용은 [포인터에 또는 포인터에서 정수 값 더하기 또는 빼기](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-140">For information about the behavior of the `+` operator with pointers, see the [Addition or subtraction of an integral value to or from a pointer](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) section.</span></span>

<span data-ttu-id="4bdcc-141">다음 예제에서는 포인터 및 `[]` 연산자를 사용하여 배열 요소에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-141">The following example demonstrates how to access array elements with a pointer and the `[]` operator:</span></span>

[!code-csharp[pointer element access](snippets/shared/PointerOperators.cs#ElementAccess)]

<span data-ttu-id="4bdcc-142">앞의 예제에서 [`stackalloc` 식](stackalloc.md)은 스택에 메모리 블록을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-142">In the preceding example, a [`stackalloc` expression](stackalloc.md) allocates a block of memory on the stack.</span></span>

> [!NOTE]
> <span data-ttu-id="4bdcc-143">포인터 요소 액세스 연산자는 범위 이탈 오류를 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-143">The pointer element access operator doesn't check for out-of-bounds errors.</span></span>

<span data-ttu-id="4bdcc-144">`void*` 형식의 식으로 포인터 요소 액세스에 `[]`(을)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-144">You cannot use `[]` for pointer element access with an expression of type `void*`.</span></span>

<span data-ttu-id="4bdcc-145">[배열 요소 또는 인덱서 액세스](member-access-operators.md#indexer-operator-)에 대해 `[]` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-145">You can also use the `[]` operator for [array element or indexer access](member-access-operators.md#indexer-operator-).</span></span>

## <a name="pointer-arithmetic-operators"></a><span data-ttu-id="4bdcc-146">포인터 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-146">Pointer arithmetic operators</span></span>

<span data-ttu-id="4bdcc-147">포인터를 사용하여 다음과 같은 산술 연산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-147">You can perform the following arithmetic operations with pointers:</span></span>

- <span data-ttu-id="4bdcc-148">포인터로 또는 포인터에서 정수 값 추가 또는 빼기</span><span class="sxs-lookup"><span data-stu-id="4bdcc-148">Add or subtract an integral value to or from a pointer</span></span>
- <span data-ttu-id="4bdcc-149">두 포인터 빼기</span><span class="sxs-lookup"><span data-stu-id="4bdcc-149">Subtract two pointers</span></span>
- <span data-ttu-id="4bdcc-150">포인터 증가 또는 감소</span><span class="sxs-lookup"><span data-stu-id="4bdcc-150">Increment or decrement a pointer</span></span>

<span data-ttu-id="4bdcc-151">`void*` 형식의 포인터를 사용하여 이러한 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-151">You cannot perform those operations with pointers of type `void*`.</span></span>

<span data-ttu-id="4bdcc-152">숫자 형식으로 지원되는 산술 연산에 대한 내용은 [산술 연산자](arithmetic-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-152">For information about supported arithmetic operations with numeric types, see [Arithmetic operators](arithmetic-operators.md).</span></span>

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a><span data-ttu-id="4bdcc-153">포인터로 또는 포인터에서 정수 값 더하기 또는 빼기</span><span class="sxs-lookup"><span data-stu-id="4bdcc-153">Addition or subtraction of an integral value to or from a pointer</span></span>

<span data-ttu-id="4bdcc-154">`T*` 형식의 포인터 `p` 및 `int`, `uint`, `long` 또는 `ulong`으로 암시적으로 변환할 수 있는 형식의 `n` 식에 대한 더하기와 빼기가 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-154">For a pointer `p` of type `T*` and an expression `n` of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`, addition and subtraction are defined as follows:</span></span>

- <span data-ttu-id="4bdcc-155">`p + n` 및 `n + p` 식 모두 `p`에서 지정한 주소에 `n * sizeof(T)`를 추가한 결과 `T*` 유형의 포인터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-155">Both `p + n` and `n + p` expressions produce a pointer of type `T*` that results from adding `n * sizeof(T)` to the address given by `p`.</span></span>
- <span data-ttu-id="4bdcc-156">`p - n` 식은 `p`에 의해 지정된 주소에서 `n * sizeof(T)`를 뺀 결과 `T*` 유형의 포인터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-156">The `p - n` expression produces a pointer of type `T*` that results from subtracting `n * sizeof(T)` from the address given by `p`.</span></span>

<span data-ttu-id="4bdcc-157">[`sizeof` 연산자](sizeof.md)는 바이트 단위의 형식 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-157">The [`sizeof` operator](sizeof.md) obtains the size of a type in bytes.</span></span>

<span data-ttu-id="4bdcc-158">다음 예제에서는 포인터로 `+` 연산자를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-158">The following example demonstrates the usage of the `+` operator with a pointer:</span></span>

[!code-csharp[pointer addition](snippets/shared/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a><span data-ttu-id="4bdcc-159">포인터 빼기</span><span class="sxs-lookup"><span data-stu-id="4bdcc-159">Pointer subtraction</span></span>

<span data-ttu-id="4bdcc-160">`T*` 형식의 두 가지 포인터 `p1` 및 `p2`에 대해 `p1 - p2` 식은 `p1`과 `p2`에 의해 지정된 주소 간의 차이를 `sizeof(T)`로 나누어 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-160">For two pointers `p1` and `p2` of type `T*`, the expression `p1 - p2` produces the difference between the addresses given by `p1` and `p2` divided by `sizeof(T)`.</span></span> <span data-ttu-id="4bdcc-161">결과의 형식은 `long`입니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-161">The type of the result is `long`.</span></span> <span data-ttu-id="4bdcc-162">즉, `p1 - p2`는 `((long)(p1) - (long)(p2)) / sizeof(T)`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-162">That is, `p1 - p2` is computed as `((long)(p1) - (long)(p2)) / sizeof(T)`.</span></span>

<span data-ttu-id="4bdcc-163">다음 예제에서는 포인터 빼기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-163">The following example demonstrates the pointer subtraction:</span></span>

[!code-csharp[pointer subtraction](snippets/shared/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a><span data-ttu-id="4bdcc-164">포인터 증가 및 감소</span><span class="sxs-lookup"><span data-stu-id="4bdcc-164">Pointer increment and decrement</span></span>

<span data-ttu-id="4bdcc-165">`++` 증가 연산자는 포인터 피연산자에 1을 [추가](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer)합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-165">The `++` increment operator [adds](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 to its pointer operand.</span></span> <span data-ttu-id="4bdcc-166">`--` 감소 연산자는 포인터 피연산자에서 1을 [뺍니다](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).</span><span class="sxs-lookup"><span data-stu-id="4bdcc-166">The `--` decrement operator [subtracts](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 from its pointer operand.</span></span>

<span data-ttu-id="4bdcc-167">두 연산자는 접미사(`p++` 및 `p--`)와 접두사(`++p` 및 `--p`)의 두 가지 형태로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-167">Both operators are supported in two forms: postfix (`p++` and `p--`) and prefix (`++p` and `--p`).</span></span> <span data-ttu-id="4bdcc-168">`p++` 및 `p--`의 결과는 작업 ‘전’의 `p`의 값입니다. </span><span class="sxs-lookup"><span data-stu-id="4bdcc-168">The result of `p++` and `p--` is the value of `p` *before* the operation.</span></span> <span data-ttu-id="4bdcc-169">`++p` 및 `--p`의 결과는 작업 ‘후’의 `p`의 값입니다. </span><span class="sxs-lookup"><span data-stu-id="4bdcc-169">The result of `++p` and `--p` is the value of `p` *after* the operation.</span></span>

<span data-ttu-id="4bdcc-170">다음 예제에서는 접미사 및 접두사 증가 연산자의 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-170">The following example demonstrates the behavior of both postfix and prefix increment operators:</span></span>

[!code-csharp[pointer increment](snippets/shared/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a><span data-ttu-id="4bdcc-171">포인터 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-171">Pointer comparison operators</span></span>

<span data-ttu-id="4bdcc-172">`==`, `!=`, `<`, `>`, `<=` 및 `>=` 연산자를 사용하여 `void*`를 포함한 모든 포인터 형식의 피연산자를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-172">You can use the `==`, `!=`, `<`, `>`, `<=`, and `>=` operators to compare operands of any pointer type, including `void*`.</span></span> <span data-ttu-id="4bdcc-173">이러한 연산자는 두 피연산자가 지정한 주소를 부호 없는 정수인 것처럼 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-173">Those operators compare the addresses given by the two operands as if they were unsigned integers.</span></span>

<span data-ttu-id="4bdcc-174">다른 형식의 피연산자에 대한 해당 연산자의 동작에 대한 정보는 [항등 연산자](equality-operators.md) 및 [비교 연산자](comparison-operators.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-174">For information about the behavior of those operators for operands of other types, see the [Equality operators](equality-operators.md) and [Comparison operators](comparison-operators.md) articles.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="4bdcc-175">연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="4bdcc-175">Operator precedence</span></span>

<span data-ttu-id="4bdcc-176">다음 목록에서는 포인터 관련 연산자를 가장 높은 우선순위부터 가장 낮은 것으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-176">The following list orders pointer related operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="4bdcc-177">접미사 증가 `x++` 및 감소 `x--` 연산자와 `->` 및 `[]` 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-177">Postfix increment `x++` and decrement `x--` operators and the `->` and `[]` operators</span></span>
- <span data-ttu-id="4bdcc-178">접두사 증가 `++x` 및 감소 `--x` 연산자와 `&` 및 `*` 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-178">Prefix increment `++x` and decrement `--x` operators and the `&` and `*` operators</span></span>
- <span data-ttu-id="4bdcc-179">가감 `+` 및 `-` 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-179">Additive `+` and `-` operators</span></span>
- <span data-ttu-id="4bdcc-180">비교 `<`, `>`, `<=` 및 `>=` 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-180">Comparison `<`, `>`, `<=`, and `>=` operators</span></span>
- <span data-ttu-id="4bdcc-181">같음 `==` 및 `!=` 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-181">Equality `==` and `!=` operators</span></span>

<span data-ttu-id="4bdcc-182">괄호(`()`)를 사용하여 연산자 우선순위에 따라 주어진 평가 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence.</span></span>

<span data-ttu-id="4bdcc-183">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](index.md#operator-precedence) 문서의 [연산자 우선 순위](index.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4bdcc-184">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="4bdcc-184">Operator overloadability</span></span>

<span data-ttu-id="4bdcc-185">사용자 정의 형식은 포인터 관련 연산자 `&`, `*`, `->` 및 `[]`(을)를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-185">A user-defined type cannot overload the pointer related operators `&`, `*`, `->`, and `[]`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4bdcc-186">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4bdcc-186">C# language specification</span></span>

<span data-ttu-id="4bdcc-187">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bdcc-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="4bdcc-188">고정 및 고정되지 않은 변수</span><span class="sxs-lookup"><span data-stu-id="4bdcc-188">Fixed and moveable variables</span></span>](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [<span data-ttu-id="4bdcc-189">address-of 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-189">The address-of operator</span></span>](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [<span data-ttu-id="4bdcc-190">포인터 간접 참조</span><span class="sxs-lookup"><span data-stu-id="4bdcc-190">Pointer indirection</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [<span data-ttu-id="4bdcc-191">포인터 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="4bdcc-191">Pointer member access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [<span data-ttu-id="4bdcc-192">포인터 요소 액세스</span><span class="sxs-lookup"><span data-stu-id="4bdcc-192">Pointer element access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [<span data-ttu-id="4bdcc-193">포인터 산술 연산</span><span class="sxs-lookup"><span data-stu-id="4bdcc-193">Pointer arithmetic</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [<span data-ttu-id="4bdcc-194">포인터 증가 및 감소</span><span class="sxs-lookup"><span data-stu-id="4bdcc-194">Pointer increment and decrement</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [<span data-ttu-id="4bdcc-195">포인터 비교</span><span class="sxs-lookup"><span data-stu-id="4bdcc-195">Pointer comparison</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a><span data-ttu-id="4bdcc-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4bdcc-196">See also</span></span>

- [<span data-ttu-id="4bdcc-197">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4bdcc-197">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4bdcc-198">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="4bdcc-198">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="4bdcc-199">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="4bdcc-199">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="4bdcc-200">unsafe 키워드</span><span class="sxs-lookup"><span data-stu-id="4bdcc-200">unsafe keyword</span></span>](../keywords/unsafe.md)
- [<span data-ttu-id="4bdcc-201">fixed 키워드</span><span class="sxs-lookup"><span data-stu-id="4bdcc-201">fixed keyword</span></span>](../keywords/fixed-statement.md)
- [<span data-ttu-id="4bdcc-202">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4bdcc-202">stackalloc</span></span>](stackalloc.md)
- [<span data-ttu-id="4bdcc-203">sizeof 연산자</span><span class="sxs-lookup"><span data-stu-id="4bdcc-203">sizeof operator</span></span>](sizeof.md)
