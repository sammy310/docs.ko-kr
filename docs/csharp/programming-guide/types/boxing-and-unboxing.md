---
title: Boxing 및 Unboxing - C# 프로그래밍 가이드
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 32156ad0fe4b3dce4371fe757d15f5b8040aaf19
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115858"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="2884e-102">Boxing 및 Unboxing(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2884e-102">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="2884e-103">Boxing은 [값 형식](../../language-reference/keywords/value-types.md)을 `object` 형식 또는 이 값 형식에서 구현된 임의의 인터페이스 형식으로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-103">Boxing is the process of converting a [value type](../../language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="2884e-104">CLR(공용 언어 런타임)은 값 형식을 boxing할 때 값을 <xref:System.Object?displayProperty=nameWithType> 인스턴스 내부에 래핑하고 관리되는 힙에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-104">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="2884e-105">unboxing하면 개체에서 값 형식이 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="2884e-106">Boxing은 암시적이며 unboxing은 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="2884e-107">Boxing 및 unboxing의 개념은 개체로 처리할 수 있는 모든 값 형식에서 형식 시스템의 C#에 통합된 뷰의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="2884e-108">다음 예제에서는 정수 변수 `i`를 *boxing*하고 개체 `o`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="2884e-109">그런 다음 `o` 개체를 unboxing하고 정수 변수 `i`에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-109">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="2884e-110">다음 예제에서는 C#에서 boxing이 사용되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-110">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="2884e-111">성능</span><span class="sxs-lookup"><span data-stu-id="2884e-111">Performance</span></span>

<span data-ttu-id="2884e-112">단순 할당에서는 boxing과 unboxing을 수행하는 데 많은 계산 과정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-112">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="2884e-113">값 형식을 boxing할 때는 새로운 개체를 할당하고 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-113">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="2884e-114">정도는 약간 덜하지만 unboxing에 필요한 캐스트에도 상당한 계산 과정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-114">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="2884e-115">자세한 내용은 [성능](../../../framework/performance/performance-tips.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2884e-115">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="2884e-116">boxing</span><span class="sxs-lookup"><span data-stu-id="2884e-116">Boxing</span></span>

<span data-ttu-id="2884e-117">boxing은 가비지 수집되는 힙에 값 형식을 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-117">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="2884e-118">Boxing은 [값 형식](../../language-reference/keywords/value-types.md)을 `object` 형식 또는 이 값 형식에서 구현된 임의의 인터페이스 형식으로 암시적으로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-118">Boxing is an implicit conversion of a [value type](../../language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="2884e-119">값 형식을 boxing하면 힙에 개체 인스턴스가 할당되고 값이 새 개체에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-119">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="2884e-120">다음과 같이 값 형식 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-120">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="2884e-121">다음 문에서는 변수 `i`에 암시적으로 boxing 연산을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-121">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="2884e-122">이 문의 결과로 힙에 있는 `o` 형식의 값을 참조하는 `int` 개체 참조가 스택에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-122">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="2884e-123">이 값은 변수`i`에 할당된 값 형식 값의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-123">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="2884e-124">두 변수 `i` 및 `o`의 차이점은 boxing 변환을 보여주는 다음 이미지에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-124">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![i 변수 o 변수의 차이를 보여주는 그래픽.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="2884e-126">다음 예제에서와 같이 명시적으로 boxing을 수행할 수도 있지만 명시적 boxing이 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-126">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="2884e-127">설명</span><span class="sxs-lookup"><span data-stu-id="2884e-127">Description</span></span>

<span data-ttu-id="2884e-128">이 예제에서는 boxing을 통해 정수 변수 `i`를 개체 `o`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-128">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="2884e-129">그런 다음 변수 `i`에 저장된 값을 `123`에서 `456`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-129">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="2884e-130">이 예제에서는 원래 값 형식과 boxing된 개체에 개별 메모리 위치를 사용하여 서로 다른 값을 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-130">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="2884e-131">예제</span><span class="sxs-lookup"><span data-stu-id="2884e-131">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="2884e-132">unboxing</span><span class="sxs-lookup"><span data-stu-id="2884e-132">Unboxing</span></span>

<span data-ttu-id="2884e-133">Unboxing은 `object` 형식에서 [값 형식](../../language-reference/keywords/value-types.md)으로, 또는 인터페이스 형식에서 해당 인터페이스를 구현하는 값 형식으로 명시적으로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-133">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/keywords/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="2884e-134">unboxing 연산 과정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-134">An unboxing operation consists of:</span></span>

- <span data-ttu-id="2884e-135">개체 인스턴스가 지정한 값 형식을 boxing한 값인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-135">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="2884e-136">인스턴스의 값을 값 형식 변수에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-136">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="2884e-137">다음 문은 boxing 및 unboxing 연산을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-137">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="2884e-138">다음 그림에서는 이전 문의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-138">The following figure demonstrates the result of the previous statements:</span></span>

![unboxing 변환을 보여주는 그래픽.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="2884e-140">런타임에 값 형식의 unboxing이 성공하려면 unboxing되는 항목은 이전에 해당 값 형식의 인스턴스를 boxing하여 생성된 개체에 대한 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-140">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="2884e-141">`null`을 unboxing하려고 하면 <xref:System.NullReferenceException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-141">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="2884e-142">호환되지 않는 값 형식에 대한 참조를 unboxing하려고 하면 <xref:System.InvalidCastException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-142">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="2884e-143">예제</span><span class="sxs-lookup"><span data-stu-id="2884e-143">Example</span></span>

<span data-ttu-id="2884e-144">다음 예제에서는 잘못된 unboxing의 경우와 그 결과로 발생하는 `InvalidCastException`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-144">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="2884e-145">이 예제에서는 `try` 및 `catch`를 사용하여 오류가 발생할 때 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-145">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="2884e-146">이 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-146">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="2884e-147">다음 문을</span><span class="sxs-lookup"><span data-stu-id="2884e-147">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="2884e-148">다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-148">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="2884e-149">변환이 수행되고 결과가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="2884e-149">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="2884e-150">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="2884e-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="related-sections"></a><span data-ttu-id="2884e-151">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2884e-151">Related sections</span></span>

<span data-ttu-id="2884e-152">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2884e-152">For more information:</span></span>

- [<span data-ttu-id="2884e-153">참조 형식</span><span class="sxs-lookup"><span data-stu-id="2884e-153">Reference Types</span></span>](../../language-reference/keywords/reference-types.md)

- [<span data-ttu-id="2884e-154">값 형식</span><span class="sxs-lookup"><span data-stu-id="2884e-154">Value Types</span></span>](../../language-reference/keywords/value-types.md)

## <a name="see-also"></a><span data-ttu-id="2884e-155">참조</span><span class="sxs-lookup"><span data-stu-id="2884e-155">See also</span></span>

- [<span data-ttu-id="2884e-156">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2884e-156">C# Programming Guide</span></span>](../index.md)
