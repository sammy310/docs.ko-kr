---
title: ref 키워드 - C# 참조
ms.date: 03/26/2019
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 05f0bd8566851678203a3f064b96bfff7dee18b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398132"
---
# <a name="ref-c-reference"></a><span data-ttu-id="c54bb-102">ref(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c54bb-102">ref (C# Reference)</span></span>

<span data-ttu-id="c54bb-103">`ref` 키워드는 참조로 전달되는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="c54bb-104">다음 네 가지 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="c54bb-105">메서드 시그니처 및 메서드 호출에서 인수를 메서드에 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="c54bb-106">자세한 내용은 [참조로 인수 전달](#passing-an-argument-by-reference)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="c54bb-107">메서드 시그니처에서 값을 호출자에게 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="c54bb-108">자세한 내용은 [참조 반환 값](#reference-return-values)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="c54bb-109">멤버 본문에서 참조 반환 값이 호출자가 수정하려는 참조로 로컬에 저장되거나 일반적으로 지역 변수가 참조를 기준으로 다른 값에 액세스 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="c54bb-110">자세한 내용은 [ref 로컬](#ref-locals)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="c54bb-111">`ref struct` 또는 `readonly ref struct`을 선언하기 위한 `struct` 선언서.</span><span class="sxs-lookup"><span data-stu-id="c54bb-111">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="c54bb-112">자세한 내용은 [ref struct 형식](#ref-struct-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-112">For more information, see [ref struct types](#ref-struct-types).</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="c54bb-113">참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="c54bb-113">Passing an argument by reference</span></span>

<span data-ttu-id="c54bb-114">메서드의 매개 변수 목록에 사용되는 경우 `ref` 키워드는 인수가 값이 아니라 참조로 전달됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="c54bb-115">`ref` 키워드는 정식 매개 변수를 변수여야 하는 인수의 별칭으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-115">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="c54bb-116">즉, 매개 변수에 대한 모든 작업이 인수에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-116">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="c54bb-117">예를 들어 호출자가 지역 변수 식 또는 배열 요소 액세스 식을 전달하는 경우 호출된 메서드에서 ref 매개 변수가 참조하는 개체를 바꾸면 메서드 반환 시 호출자의 지역 변수 또는 배열 요소가 새 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-117">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="c54bb-118">참조로 전달의 개념과 참조 형식의 개념을 혼동해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-118">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="c54bb-119">이 두 개념은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-119">The two concepts are not the same.</span></span> <span data-ttu-id="c54bb-120">메서드 매개 변수는 값 형식이든 참조 형식이든 관계없이 `ref`를 통해 수정할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="c54bb-120">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="c54bb-121">참조로 전달되는 경우 값 형식은 boxing되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-121">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="c54bb-122">`ref` 매개 변수를 사용하려면 다음 예제에 나와 있는 것처럼 메서드 정의와 호출 메서드가 모두 `ref` 키워드를 명시적으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-122">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="c54bb-123">`ref` 또는 `in` 매개 변수로 전달하는 인수는 전달 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-123">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="c54bb-124">이러한 방식은 인수를 전달하기 전에 명시적으로 초기화할 필요가 없는 [out](out-parameter-modifier.md) 매개 변수와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-124">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="c54bb-125">클래스의 멤버는 `ref`, `in` 또는 `out`만 다른 서명을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-125">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="c54bb-126">특정 형식의 두 멤버가 하나는 `ref` 매개 변수를 포함하고 다른 하나는 `out` 또는 `in` 매개 변수를 포함한다는 것 외에는 차이가 없으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-126">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="c54bb-127">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-127">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="c54bb-128">그러나 다음 예제에 나와 있는 것처럼 메서드 하나에는 `ref`, `in` 또는 `out` 매개 변수가 포함되어 있고 다른 하나에는 값 매개 변수가 포함되어 있으면 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-128">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="c54bb-129">숨기기나 재정의와 같이 서명이 일치해야 하는 다른 상황에서는 `in`, `ref` 및 `out`이 서명의 일부가 되며 서로 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-129">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="c54bb-130">속성은 변수가 아니라</span><span class="sxs-lookup"><span data-stu-id="c54bb-130">Properties are not variables.</span></span> <span data-ttu-id="c54bb-131">메서드이며 `ref` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="c54bb-132">다음과 같은 종류의 메서드에는 `ref`, `in` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="c54bb-133">[async](async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="c54bb-133">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="c54bb-134">[yield return](yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="c54bb-134">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="c54bb-135">참조로 인수 전달: 예제</span><span class="sxs-lookup"><span data-stu-id="c54bb-135">Passing an argument by reference: An example</span></span>

<span data-ttu-id="c54bb-136">앞의 예제에서는 값 형식을 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-136">The previous examples pass value types by reference.</span></span> <span data-ttu-id="c54bb-137">`ref` 키워드를 사용하여 참조 형식을 참조로 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-137">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="c54bb-138">참조 형식을 참조로 전달하는 경우 호출된 메서드는 참조 매개 변수가 호출자에서 참조하는 개체를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-138">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="c54bb-139">개체의 스토리지 위치는 참조 매개 변수의 값으로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-139">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="c54bb-140">매개 변수의 스토리지 위치에서 값을 변경하여 새 개체를 가리키도록 하면 호출자가 참조하는 스토리지 위치도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-140">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="c54bb-141">다음 예제에서는 참조 형식 인스턴스를 `ref` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-141">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="c54bb-142">참조 형식을 참조 및 값으로 전달하는 방법에 대한 자세한 내용은 [참조-형식 매개 변수 전달](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-142">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="c54bb-143">참조 반환 값</span><span class="sxs-lookup"><span data-stu-id="c54bb-143">Reference return values</span></span>

<span data-ttu-id="c54bb-144">참조 반환 값(또는 ref return)은 메서드가 호출자에게 참조로 반환하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-144">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="c54bb-145">즉, 호출자가 메서드에서 반환된 값을 수정할 수 있으며 해당 변경 내용이 메서드를 포함하는 개체의 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-145">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="c54bb-146">참조 반환 값은 `ref` 키워드를 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-146">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="c54bb-147">메서드 시그니처에서.</span><span class="sxs-lookup"><span data-stu-id="c54bb-147">In the method signature.</span></span> <span data-ttu-id="c54bb-148">예를 들어 다음 메서드 시그니처는 `GetCurrentPrice` 메서드가 <xref:System.Decimal> 값을 참조로 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-148">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="c54bb-149">메서드의 `return` 문에서 반환된 `return` 토큰과 변수 간에.</span><span class="sxs-lookup"><span data-stu-id="c54bb-149">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="c54bb-150">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="c54bb-150">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="c54bb-151">호출자가 개체 상태를 수정하려면 참조 반환 값을 [참조 지역](#ref-locals)으로 명시적으로 정의된 변수에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-151">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="c54bb-152">호출된 메서드는 `ref readonly`로 반환 값을 선언하여 참조를 통해 값을 반환하고 호출 코드가 반환된 값을 수정할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-152">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="c54bb-153">호출 메서드는 지역 [ref readonly](#ref-readonly-locals) 변수에 값을 저장하여 반환된 값을 복사하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-153">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="c54bb-154">예를 들어 [ref 반환 및 ref 지역 예제](#a-ref-returns-and-ref-locals-example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-154">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="c54bb-155">참조 로컬</span><span class="sxs-lookup"><span data-stu-id="c54bb-155">Ref locals</span></span>

<span data-ttu-id="c54bb-156">참조 지역 변수는 `return ref`을 사용하여 반환된 값을 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-156">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="c54bb-157">참조 지역 변수는 비참조 반환 값으로 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-157">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="c54bb-158">즉, 초기화의 오른쪽은 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-158">In other words, the right hand side of the initialization must be a reference.</span></span> <span data-ttu-id="c54bb-159">참조 로컬 값의 수정 내용은 메서드가 값을 참조로 반환하는 개체 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-159">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="c54bb-160">변수 선언 앞, 값을 참조로 반환하는 메서드 호출 직전에 `ref` 키워드를 사용하여 참조 지역을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-160">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="c54bb-161">예를 들어 다음 문은 `GetEstimatedValue` 메서드에서 반환되는 참조 로컬 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-161">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="c54bb-162">동일한 방법으로 참조로 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-162">You can access a value by reference in the same way.</span></span> <span data-ttu-id="c54bb-163">경우에 따라 참조로 값에 액세스하면 비용이 많이 들 수 있는 복사 작업을 피함으로써 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-163">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="c54bb-164">예를 들어, 다음 명령문은 값을 참조하는 데 사용되는 참조 로컬 값을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-164">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="c54bb-165">두 예에서 `ref` 키워드는 두 위치에 모두 사용해야 합니다. 그렇지 않으면 컴파일러 오류 CS8172, "값을 사용하여 참조 형식 변수를 초기화할 수 없습니다."가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-165">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="c54bb-166">C# 7.3부터 `foreach` 문의 반복 변수는 ref 지역 또는 ref readonly 지역 변수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-166">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="c54bb-167">자세한 내용은 [foreach 문](foreach-in.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c54bb-167">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="c54bb-168">또한 C# 7.3부터 [ref 대입 연산자](../operators/assignment-operator.md#ref-assignment-operator)를 사용하여 ref 지역 또는 ref readonly 지역 변수를 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-168">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="c54bb-169">Ref readonly 로컬</span><span class="sxs-lookup"><span data-stu-id="c54bb-169">Ref readonly locals</span></span>

<span data-ttu-id="c54bb-170">Ref readonly 로컬은 해당 시그니처에 `ref readonly`가 있고 `return ref`를 사용하는 메서드 또는 속성을 통해 반환된 값을 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-170">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="c54bb-171">`ref readonly` 변수는 `ref` 지역 변수의 속성을 `readonly` 변수와 결합합니다. 이는 할당된 스토리지의 별칭이고 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-171">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="c54bb-172">참조 반환 및 참조 로컬 예제</span><span class="sxs-lookup"><span data-stu-id="c54bb-172">A ref returns and ref locals example</span></span>

<span data-ttu-id="c54bb-173">다음 예제에서는 두 개의 <xref:System.String> 필드 `Title` 및 `Author`가 있는 `Book` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-173">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="c54bb-174">또한 `Book` 개체의 private 배열을 포함하는 `BookCollection` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-174">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="c54bb-175">개별 책 개체는 해당 `GetBookByTitle` 메서드를 호출하여 참조로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-175">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="c54bb-176">호출자가 `GetBookByTitle` 메서드에서 참조 로컬로 반환된 값을 저장하는 경우 호출자가 반환 값을 변경하면 다음 예제와 같이 `BookCollection` 개체에 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-176">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a><span data-ttu-id="c54bb-177">Ref struct 형식</span><span class="sxs-lookup"><span data-stu-id="c54bb-177">Ref struct types</span></span>

<span data-ttu-id="c54bb-178">`struct` 선언에 `ref` 한정자를 추가하면 해당 형식의 인스턴스가 스택에 할당되도록 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-178">Adding the `ref` modifier to a `struct` declaration defines that instances of that type must be stack allocated.</span></span> <span data-ttu-id="c54bb-179">즉, 이러한 형식의 인스턴스는 다른 클래스의 멤버로 힙에 만들어질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-179">In other words, instances of these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="c54bb-180">이 기능의 기본 동기 부여는 <xref:System.Span%601> 및 관련 구조였습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-180">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span>

<span data-ttu-id="c54bb-181">`ref struct` 형식을 스택에 할당된 변수로 유지하는 목표로 인해 컴파일러가 모든 `ref struct` 형식에 대해 강제 적용하는 여러 규칙이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-181">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="c54bb-182">`ref struct`를 boxing할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-182">You can't box a `ref struct`.</span></span> <span data-ttu-id="c54bb-183">`ref struct` 형식을 `object`, `dynamic` 형식 또는 인터페이스 유형의 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-183">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="c54bb-184">`ref struct` 형식은 인터페이스를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-184">`ref struct` types cannot implement interfaces.</span></span>
- <span data-ttu-id="c54bb-185">`ref struct`를 클래스 또는 일반 구조체의 필드 멤버로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-185">You can't declare a `ref struct` as a field member of a class or a normal struct.</span></span> <span data-ttu-id="c54bb-186">여기에는 컴파일러에서 생성된 지원 필드를 만드는 자동 구현 속성의 선언이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-186">This includes declaring an auto-implemented property, which creates a compiler generated backing field.</span></span>
- <span data-ttu-id="c54bb-187">비동기 메서드에 `ref struct` 형식인 지역 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-187">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="c54bb-188"><xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> 또는 `Task`와 유사한 형식을 반환하는 동기 메서드에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-188">You can declare them in synchronous methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> or `Task`-like types.</span></span>
- <span data-ttu-id="c54bb-189">반복기에 `ref struct` 지역 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-189">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="c54bb-190">람다 식 또는 로컬 함수에서 `ref struct` 변수를 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-190">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="c54bb-191">이러한 제한 사항은 실수로 `ref struct`를 관리되는 힙으로 수준 올릴 수 있는 방식으로 이 구조체를 사용하지 않게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-191">These restrictions ensure you don't accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

<span data-ttu-id="c54bb-192">한정자를 결합하여 구조체를 `readonly ref`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-192">You can combine modifiers to declare a struct as `readonly ref`.</span></span> <span data-ttu-id="c54bb-193">`readonly ref struct`는 `ref struct` 및 `readonly struct` 선언의 이점과 제한 사항을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="c54bb-193">A `readonly ref struct` combines the benefits and restrictions of `ref struct` and `readonly struct` declarations.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c54bb-194">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c54bb-194">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c54bb-195">참조</span><span class="sxs-lookup"><span data-stu-id="c54bb-195">See also</span></span>

- [<span data-ttu-id="c54bb-196">안전하고 효율적인 코드 작성</span><span class="sxs-lookup"><span data-stu-id="c54bb-196">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="c54bb-197">Ref return 및 ref local</span><span class="sxs-lookup"><span data-stu-id="c54bb-197">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="c54bb-198">조건부 ref 식</span><span class="sxs-lookup"><span data-stu-id="c54bb-198">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="c54bb-199">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="c54bb-199">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="c54bb-200">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c54bb-200">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="c54bb-201">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c54bb-201">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c54bb-202">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c54bb-202">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c54bb-203">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="c54bb-203">C# Keywords</span></span>](index.md)
