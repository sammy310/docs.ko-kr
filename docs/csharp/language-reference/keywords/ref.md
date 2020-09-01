---
description: ref 키워드 - C# 참조
title: ref 키워드 - C# 참조
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 58a4ce30e11ca023b50e5e53b1f1554a30d44390
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137086"
---
# <a name="ref-c-reference"></a><span data-ttu-id="421c5-103">ref(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="421c5-103">ref (C# Reference)</span></span>

<span data-ttu-id="421c5-104">`ref` 키워드는 참조로 전달되는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-104">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="421c5-105">다음 네 가지 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-105">It is used in four different contexts:</span></span>

- <span data-ttu-id="421c5-106">메서드 시그니처 및 메서드 호출에서 인수를 메서드에 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-106">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="421c5-107">자세한 내용은 [참조로 인수 전달](#passing-an-argument-by-reference)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-107">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="421c5-108">메서드 시그니처에서 값을 호출자에게 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-108">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="421c5-109">자세한 내용은 [참조 반환 값](#reference-return-values)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-109">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="421c5-110">멤버 본문에서 참조 반환 값이 호출자가 수정하려는 참조로 로컬에 저장되거나 일반적으로 로컬 변수가 참조를 기준으로 다른 값에 액세스 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-110">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="421c5-111">자세한 내용은 [ref 로컬](#ref-locals)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-111">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="421c5-112">`ref struct` 또는 `readonly ref struct`을 선언하기 위한 `struct` 선언서.</span><span class="sxs-lookup"><span data-stu-id="421c5-112">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="421c5-113">자세한 내용은 [구조체 형식](../builtin-types/struct.md) 문서의 [`ref` 구조체](../builtin-types/struct.md#ref-struct) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-113">For more information, see the [`ref` struct](../builtin-types/struct.md#ref-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="421c5-114">참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="421c5-114">Passing an argument by reference</span></span>

<span data-ttu-id="421c5-115">메서드의 매개 변수 목록에 사용되는 경우 `ref` 키워드는 인수가 값이 아니라 참조로 전달됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-115">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="421c5-116">`ref` 키워드는 정식 매개 변수를 변수여야 하는 인수의 별칭으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-116">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="421c5-117">즉, 매개 변수에 대한 모든 작업이 인수에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-117">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="421c5-118">예를 들어 호출자가 지역 변수 식 또는 배열 요소 액세스 식을 전달하는 경우 호출된 메서드에서 ref 매개 변수가 참조하는 개체를 바꾸면 메서드 반환 시 호출자의 지역 변수 또는 배열 요소가 새 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-118">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="421c5-119">참조로 전달의 개념과 참조 형식의 개념을 혼동해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-119">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="421c5-120">이 두 개념은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-120">The two concepts are not the same.</span></span> <span data-ttu-id="421c5-121">메서드 매개 변수는 값 형식이든 참조 형식이든 관계없이 `ref`를 통해 수정할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="421c5-121">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="421c5-122">참조로 전달되는 경우 값 형식은 boxing되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-122">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="421c5-123">`ref` 매개 변수를 사용하려면 다음 예제에 나와 있는 것처럼 메서드 정의와 호출 메서드가 모두 `ref` 키워드를 명시적으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-123">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="421c5-124">`ref` 또는 `in` 매개 변수로 전달하는 인수는 전달 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-124">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="421c5-125">이러한 방식은 인수를 전달하기 전에 명시적으로 초기화할 필요가 없는 [out](out-parameter-modifier.md) 매개 변수와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-125">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="421c5-126">클래스의 멤버는 `ref`, `in` 또는 `out`만 다른 서명을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-126">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="421c5-127">특정 형식의 두 멤버가 하나는 `ref` 매개 변수를 포함하고 다른 하나는 `out` 또는 `in` 매개 변수를 포함한다는 것 외에는 차이가 없으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-127">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="421c5-128">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-128">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="421c5-129">그러나 다음 예제에 나와 있는 것처럼 메서드 하나에는 `ref`, `in` 또는 `out` 매개 변수가 포함되어 있고 다른 하나에는 값 매개 변수가 포함되어 있으면 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-129">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="421c5-130">숨기기나 재정의와 같이 서명이 일치해야 하는 다른 상황에서는 `in`, `ref` 및 `out`이 서명의 일부가 되며 서로 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-130">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="421c5-131">속성은 변수가 아니라</span><span class="sxs-lookup"><span data-stu-id="421c5-131">Properties are not variables.</span></span> <span data-ttu-id="421c5-132">메서드이며 `ref` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-132">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="421c5-133">다음과 같은 종류의 메서드에는 `ref`, `in` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-133">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="421c5-134">[async](async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="421c5-134">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="421c5-135">[yield return](yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="421c5-135">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="421c5-136">또한 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-136">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="421c5-137">확장 메서드의 첫 번째 인수에는 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-137">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="421c5-138">인수가 구조체가 아니거나 구조체로 제한되지 않는 제네릭 형식일 경우에는 확장 메서드의 첫 번째 인수에 `ref` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-138">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="421c5-139">첫 번째 인수가 구조체인 경우 이외에는 `in` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-139">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="421c5-140">구조체로 제한되는 경우에도 `in` 키워드는 제네릭 형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-140">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="421c5-141">참조로 인수 전달: 예제</span><span class="sxs-lookup"><span data-stu-id="421c5-141">Passing an argument by reference: An example</span></span>

<span data-ttu-id="421c5-142">앞의 예제에서는 값 형식을 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-142">The previous examples pass value types by reference.</span></span> <span data-ttu-id="421c5-143">`ref` 키워드를 사용하여 참조 형식을 참조로 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-143">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="421c5-144">참조 형식을 참조로 전달하는 경우 호출된 메서드는 참조 매개 변수가 호출자에서 참조하는 개체를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-144">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="421c5-145">개체의 스토리지 위치는 참조 매개 변수의 값으로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-145">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="421c5-146">매개 변수의 스토리지 위치에서 값을 변경하여 새 개체를 가리키도록 하면 호출자가 참조하는 스토리지 위치도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-146">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="421c5-147">다음 예제에서는 참조 형식 인스턴스를 `ref` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-147">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="421c5-148">참조 형식을 참조 및 값으로 전달하는 방법에 대한 자세한 내용은 [참조-형식 매개 변수 전달](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-148">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="421c5-149">참조 반환 값</span><span class="sxs-lookup"><span data-stu-id="421c5-149">Reference return values</span></span>

<span data-ttu-id="421c5-150">참조 반환 값(또는 ref return)은 메서드가 호출자에게 참조로 반환하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-150">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="421c5-151">즉, 호출자는 메서드에서 반환된 값을 수정할 수 있으며 해당 변경 내용은 호출 메서드의 개체 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-151">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object in the calling method.</span></span>

<span data-ttu-id="421c5-152">참조 반환 값은 `ref` 키워드를 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-152">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="421c5-153">메서드 시그니처에서.</span><span class="sxs-lookup"><span data-stu-id="421c5-153">In the method signature.</span></span> <span data-ttu-id="421c5-154">예를 들어 다음 메서드 시그니처는 `GetCurrentPrice` 메서드가 <xref:System.Decimal> 값을 참조로 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-154">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="421c5-155">메서드의 `return` 문에서 반환된 `return` 토큰과 변수 간에.</span><span class="sxs-lookup"><span data-stu-id="421c5-155">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="421c5-156">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="421c5-156">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="421c5-157">호출자가 개체 상태를 수정하려면 참조 반환 값을 [참조 로컬](#ref-locals)로 명시적으로 정의된 변수에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-157">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="421c5-158">다음은 메서드 시그니처와 메서드 본문을 모두 보여주는 보다 완전한 참조 반환 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-158">Here is a more complete ref return example, showing both the method signature and method body.</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="421c5-159">호출된 메서드는 `ref readonly`로 반환 값을 선언하여 참조를 통해 값을 반환하고 호출 코드가 반환된 값을 수정할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-159">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="421c5-160">호출 메서드는 로컬 [ref readonly](#ref-readonly-locals) 변수에 값을 저장하여 반환된 값을 복사하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-160">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="421c5-161">예를 들어 [ref 반환 및 ref 지역 예제](#a-ref-returns-and-ref-locals-example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-161">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="421c5-162">참조 로컬</span><span class="sxs-lookup"><span data-stu-id="421c5-162">Ref locals</span></span>

<span data-ttu-id="421c5-163">참조 지역 변수는 `return ref`을 사용하여 반환된 값을 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-163">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="421c5-164">참조 지역 변수는 비참조 반환 값으로 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-164">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="421c5-165">즉, 초기화의 오른쪽은 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-165">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="421c5-166">참조 로컬 값의 수정 내용은 메서드가 값을 참조로 반환하는 개체 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-166">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="421c5-167">변수 선언 앞, 값을 참조로 반환하는 메서드 호출 직전에 `ref` 키워드를 사용하여 참조 로컬을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-167">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="421c5-168">예를 들어 다음 문은 `GetEstimatedValue` 메서드에서 반환되는 참조 로컬 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-168">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="421c5-169">동일한 방법으로 참조로 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-169">You can access a value by reference in the same way.</span></span> <span data-ttu-id="421c5-170">경우에 따라 참조로 값에 액세스하면 비용이 많이 들 수 있는 복사 작업을 피함으로써 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-170">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="421c5-171">예를 들어, 다음 명령문은 값을 참조하는 데 사용되는 참조 로컬 값을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-171">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="421c5-172">두 예에서 `ref` 키워드는 두 위치에 모두 사용해야 합니다. 그러지 않으면 컴파일러 오류 CS8172, "값을 사용하여 참조 형식 변수를 초기화할 수 없습니다."가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-172">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="421c5-173">C# 7.3부터 `foreach` 문의 반복 변수는 ref 지역 또는 ref readonly 지역 변수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-173">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="421c5-174">자세한 내용은 [foreach 문](foreach-in.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="421c5-174">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="421c5-175">또한 C# 7.3부터 [ref 대입 연산자](../operators/assignment-operator.md#ref-assignment-operator)를 사용하여 ref 지역 또는 ref readonly 지역 변수를 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-175">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="421c5-176">Ref readonly 로컬</span><span class="sxs-lookup"><span data-stu-id="421c5-176">Ref readonly locals</span></span>

<span data-ttu-id="421c5-177">Ref readonly 로컬은 해당 시그니처에 `ref readonly`가 있고 `return ref`를 사용하는 메서드 또는 속성을 통해 반환된 값을 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-177">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="421c5-178">`ref readonly` 변수는 `ref` 지역 변수의 속성을 `readonly` 변수와 결합합니다. 이는 할당된 스토리지의 별칭이고 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-178">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="421c5-179">참조 반환 및 참조 로컬 예제</span><span class="sxs-lookup"><span data-stu-id="421c5-179">A ref returns and ref locals example</span></span>

<span data-ttu-id="421c5-180">다음 예제에서는 두 개의 <xref:System.String> 필드 `Title` 및 `Author`가 있는 `Book` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-180">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="421c5-181">또한 `Book` 개체의 private 배열을 포함하는 `BookCollection` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-181">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="421c5-182">개별 책 개체는 해당 `GetBookByTitle` 메서드를 호출하여 참조로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-182">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="421c5-183">호출자가 `GetBookByTitle` 메서드에서 참조 로컬로 반환된 값을 저장하는 경우 호출자가 반환 값을 변경하면 다음 예제와 같이 `BookCollection` 개체에 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="421c5-183">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="421c5-184">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="421c5-184">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="421c5-185">참조</span><span class="sxs-lookup"><span data-stu-id="421c5-185">See also</span></span>

- [<span data-ttu-id="421c5-186">안전하고 효율적인 코드 작성</span><span class="sxs-lookup"><span data-stu-id="421c5-186">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="421c5-187">Ref return 및 ref local</span><span class="sxs-lookup"><span data-stu-id="421c5-187">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="421c5-188">조건부 ref 식</span><span class="sxs-lookup"><span data-stu-id="421c5-188">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="421c5-189">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="421c5-189">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="421c5-190">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="421c5-190">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="421c5-191">C# 참조</span><span class="sxs-lookup"><span data-stu-id="421c5-191">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="421c5-192">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="421c5-192">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="421c5-193">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="421c5-193">C# Keywords</span></span>](index.md)
