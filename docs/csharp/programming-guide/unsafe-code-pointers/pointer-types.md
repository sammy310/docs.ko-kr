---
title: 포인터 형식 - C# 프로그래밍 가이드
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: ad6e6f17f9a8c30339a74b8ab41af3a99e716d3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745351"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="abbb4-102">포인터 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="abbb4-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="abbb4-103">안전하지 않은 컨텍스트에서는 형식이 포인터 형식, 값 형식 또는 참조 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="abbb4-104">포인터 형식 선언은 다음 형식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="abbb4-105">포인터 형식에서 `*` 앞에 지정된 형식을 **참조 형식**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="abbb4-106">[비관리형 형식](../../language-reference/builtin-types/unmanaged-types.md)만 참조 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-106">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="abbb4-107">포인터 형식은 [개체](../../language-reference/builtin-types/reference-types.md)에서 상속되지 않으며 포인터 형식과 `object`는 서로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-107">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="abbb4-108">또한 boxing과 unboxing은 포인터를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-108">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="abbb4-109">그러나 다른 포인터 형식 간의 변환 및 포인터 형식과 정수 형식 사이의 변환은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-109">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="abbb4-110">동일한 선언에서 여러 포인터를 선언하는 경우 별표(\*)는 기본 형식에만 함께 사용되고 각 포인터 이름의 접두사로는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-110">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="abbb4-111">예:</span><span class="sxs-lookup"><span data-stu-id="abbb4-111">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="abbb4-112">개체 참조는 포인터가 해당 개체 참조를 가리키는 경우에도 가비지 수집될 수 있으므로 포인터는 참조나 참조가 들어 있는 [구조체](../../language-reference/keywords/struct.md)를 가리킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-112">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="abbb4-113">가비지 수집기는 포인터 형식에서 개체를 가리키는지 여부를 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-113">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="abbb4-114">`myType*` 형식의 포인터 변수 값은 `myType` 형식의 변수 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-114">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="abbb4-115">다음은 포인터 형식 선언의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-115">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="abbb4-116">예제</span><span class="sxs-lookup"><span data-stu-id="abbb4-116">Example</span></span>|<span data-ttu-id="abbb4-117">설명</span><span class="sxs-lookup"><span data-stu-id="abbb4-117">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="abbb4-118">`p`는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-118">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="abbb4-119">`p`는 정수에 대한 포인터를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-119">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="abbb4-120">`p`는 정수에 대한 포인터의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-120">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="abbb4-121">`p`는 문자에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-121">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="abbb4-122">`p`는 알 수 없는 형식에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-122">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="abbb4-123">포인터 간접 참조 연산자 \*를 사용하면 포인터 변수가 가리키는 위치의 내용에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-123">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="abbb4-124">예를 들어, 다음 선언을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="abbb4-124">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="abbb4-125">여기서 `*myVariable` 식은 `int`에 포함된 주소에 있는 `myVariable` 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-125">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="abbb4-126">[fixed 문](../../language-reference/keywords/fixed-statement.md) 및 [포인터 변환](./pointer-conversions.md) 항목에 포인터에 대한 몇 가지 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-126">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="abbb4-127">다음 예제는 `unsafe` 키워드 및 `fixed` 문을 사용하고 정수 포인터를 증분하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-127">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="abbb4-128">이 코드를 실행하려면 콘솔 애플리케이션의 주 함수에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-128">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="abbb4-129">이러한 예제는 [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션 집합으로 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-129">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="abbb4-130">`void*` 형식의 포인터에는 간접 참조 연산자를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-130">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="abbb4-131">그러나 캐스트를 사용하여 void 포인터를 다른 포인터 형식으로 변환하거나 반대로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-131">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="abbb4-132">포인터는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-132">A pointer can be `null`.</span></span> <span data-ttu-id="abbb4-133">null 포인터에 간접 참조 연산자를 적용할 때 발생하는 동작은 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-133">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="abbb4-134">메서드 사이에 포인터를 전달하면 정의되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-134">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="abbb4-135">`in`, `out` 또는 `ref` 매개 변수를 통해, 또는 함수 결과로 지역 변수에 포인터를 반환하는 메서드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-135">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="abbb4-136">fixed 블록에서 포인터가 설정되면 이 포인터가 가리키는 변수의 고정 상태가 해제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-136">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="abbb4-137">다음 표에서는 안전하지 않은 컨텍스트에서 포인터에 대해 수행할 수 있는 연산자와 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-137">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="abbb4-138">연산자/문</span><span class="sxs-lookup"><span data-stu-id="abbb4-138">Operator/Statement</span></span>|<span data-ttu-id="abbb4-139">기능</span><span class="sxs-lookup"><span data-stu-id="abbb4-139">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="abbb4-140">포인터 간접 참조를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-140">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="abbb4-141">포인터를 통해 구조체 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-141">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="abbb4-142">포인터를 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-142">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="abbb4-143">변수 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-143">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="abbb4-144">`++` 및 `--`</span><span class="sxs-lookup"><span data-stu-id="abbb4-144">`++` and `--`</span></span>|<span data-ttu-id="abbb4-145">포인터를 증가 및 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-145">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="abbb4-146">`+` 및 `-`</span><span class="sxs-lookup"><span data-stu-id="abbb4-146">`+` and `-`</span></span>|<span data-ttu-id="abbb4-147">포인터 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-147">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="abbb4-148">`==`, `!=`, `<`, `>`, `<=` 및 `>=`</span><span class="sxs-lookup"><span data-stu-id="abbb4-148">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="abbb4-149">포인터를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-149">Compares pointers.</span></span>|
|[<span data-ttu-id="abbb4-150">`stackalloc` 연산자</span><span class="sxs-lookup"><span data-stu-id="abbb4-150">`stackalloc` operator</span></span>](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="abbb4-151">스택에 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-151">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="abbb4-152">`fixed` statement</span><span class="sxs-lookup"><span data-stu-id="abbb4-152">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="abbb4-153">해당 주소를 찾을 수 있도록 임시로 변수를 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="abbb4-153">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="abbb4-154">포인터에 관련 연산자에 대한 자세한 내용은 [포인터 관련 연산자](../../language-reference/operators/pointer-related-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abbb4-154">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="abbb4-155">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="abbb4-155">C# language specification</span></span>

<span data-ttu-id="abbb4-156">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [포인터 형식](~/_csharplang/spec/unsafe-code.md#pointer-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abbb4-156">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="abbb4-157">참조</span><span class="sxs-lookup"><span data-stu-id="abbb4-157">See also</span></span>

- [<span data-ttu-id="abbb4-158">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="abbb4-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="abbb4-159">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="abbb4-159">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="abbb4-160">포인터 변환</span><span class="sxs-lookup"><span data-stu-id="abbb4-160">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="abbb4-161">참조 형식</span><span class="sxs-lookup"><span data-stu-id="abbb4-161">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="abbb4-162">값 형식</span><span class="sxs-lookup"><span data-stu-id="abbb4-162">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="abbb4-163">unsafe</span><span class="sxs-lookup"><span data-stu-id="abbb4-163">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
