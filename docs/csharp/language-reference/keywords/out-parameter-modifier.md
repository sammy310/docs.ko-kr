---
title: out 매개 변수 한정자 - C# 참조
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 57308992268e1285cfeb82b28e2abf213e7a831b
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805864"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="32032-102">out 매개 변수 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="32032-102">out parameter modifier (C# Reference)</span></span>

<span data-ttu-id="32032-103">`out` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="32032-104">이 키워드는 정식 매개 변수를 위해 해당 인수의 별칭을 만드는데, 이는 반드시 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="32032-105">즉, 매개 변수에 대한 모든 작업이 인수에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="32032-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="32032-106">이러한 방식은 [ref](ref.md) 키워드와 비슷합니다. 단, `ref`의 경우에는 변수를 전달하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="32032-107">`in`이 호출된 메서드에서 인수 값 수정을 허용하지 않는 것을 제외하고 [in](in-parameter-modifier.md) 키워드와도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="32032-108">`out` 매개 변수를 사용하려면 메서드 정의와 호출 메서드가 모두 명시적으로 `out` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="32032-109">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="32032-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> <span data-ttu-id="32032-110">`out` 키워드를 제네릭 형식 매개 변수와 함께 사용하여 형식 매개 변수를 공변(covariant)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="32032-111">이 컨텍스트에서 `out` 키워드를 사용하는 방법에 대한 자세한 내용은 [out(제네릭 한정자)](out-generic-modifier.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32032-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="32032-112">`out` 인수로 전달되는 변수는 메서드 호출에서 전달되기 전에 초기화할 필요가 없지만</span><span class="sxs-lookup"><span data-stu-id="32032-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="32032-113">호출된 메서드는 메서드가 반환되기 전에 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="32032-114">`in`, `ref` 및 `out` 키워드는 오버로드 해결을 위한 메서드 시그니처의 일부로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="32032-115">따라서 메서드 하나는 `ref` 또는 `in` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="32032-116">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="32032-117">그러나 다음과 같이 메서드 하나는 `ref`, `in` 또는 `out` 인수를 사용하고 다른 하나는 해당 한정자를 갖지 않는 경우에는 오버로드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="32032-118">컴파일러는 메서드 호출에 사용되는 매개 변수 한정자에 호출 사이트에서 매개 변수 한정자를 일치하여 적합한 오버로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>

<span data-ttu-id="32032-119">속성은 변수가 아니므로 `out` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="32032-120">다음과 같은 종류의 메서드에는 `in`, `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="32032-121">[async](./async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="32032-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="32032-122">[yield return](./yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="32032-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="32032-123">또한 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-123">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="32032-124">확장 메서드의 첫 번째 인수에는 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-124">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="32032-125">인수가 구조체가 아니거나 구조체로 제한되지 않는 제네릭 형식일 경우에는 확장 메서드의 첫 번째 인수에 `ref` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-125">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="32032-126">첫 번째 인수가 구조체인 경우 이외에는 `in` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-126">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="32032-127">구조체로 제한되는 경우에도 `in` 키워드는 제네릭 형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-127">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="declaring-out-parameters"></a><span data-ttu-id="32032-128">`out` 매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="32032-128">Declaring `out` parameters</span></span>

<span data-ttu-id="32032-129">`out` 인수를 사용하여 메서드를 선언하는 것은 여러 값을 반환하기 위한 일반적인 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="32032-129">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="32032-130">C# 7.0부터 비슷한 시나리오에 대해 [튜플](../../tuples.md)을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="32032-130">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="32032-131">다음 예제에서는 `out`을 사용하여 단일 메서드 호출로 3개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-131">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="32032-132">세 번째 인수는 null에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="32032-132">The third argument is assigned to null.</span></span> <span data-ttu-id="32032-133">따라서 메서드가 값을 선택적으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-133">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="32032-134">`out` 인수를 사용하여 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="32032-134">Calling a method with an `out` argument</span></span>

<span data-ttu-id="32032-135">C# 6 및 이전 버전에서는 `out` 인수로 전달하기 전에 별도 문에서 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-135">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="32032-136">다음 예제에서는 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 메서드에 전달되기 전에 `number`라는 변수를 선언합니다. 이 메서드는 문자열을 숫자로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-136">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="32032-137">C# 7.0부터 별도 변수 선언이 아니라 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-137">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="32032-138">이렇게 하면 보다 간결하고 읽기 쉬운 코드가 생성되며 메서드 호출 전에 실수로 변수에 값이 할당되는 경우를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-138">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="32032-139">다음 예제는 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 메서드 호출에서 `number` 변수를 정의한다는 점을 제외하고 이전 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="32032-139">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

<span data-ttu-id="32032-140">앞의 예제에서 `number` 변수는 `int`로 강력하게 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="32032-140">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="32032-141">다음 예제와 같이 암시적 형식 지역 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32032-141">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="32032-142">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="32032-142">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32032-143">참조</span><span class="sxs-lookup"><span data-stu-id="32032-143">See also</span></span>

- [<span data-ttu-id="32032-144">C# 참조</span><span class="sxs-lookup"><span data-stu-id="32032-144">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="32032-145">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="32032-145">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="32032-146">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="32032-146">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="32032-147">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="32032-147">Method Parameters</span></span>](./method-parameters.md)
