---
title: out 매개 변수 한정자 - C# 참조
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: f963188d77685bb81f7dc9fb3794e343114fe3c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173564"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="fa5df-102">out 매개 변수 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fa5df-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="fa5df-103">`out` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="fa5df-104">이 키워드는 정식 매개 변수를 위해 해당 인수의 별칭을 만드는데, 이는 반드시 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="fa5df-105">즉, 매개 변수에 대한 모든 작업이 인수에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="fa5df-106">이러한 방식은 [ref](ref.md) 키워드와 비슷합니다. 단, `ref`의 경우에는 변수를 전달하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="fa5df-107">[이 호출된 메서드에서 인수 값 수정을 허용하지 않는 것을 제외하고 ](in-parameter-modifier.md)in`in` 키워드와도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="fa5df-108">`out` 매개 변수를 사용하려면 메서드 정의와 호출 메서드가 모두 명시적으로 `out` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="fa5df-109">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> <span data-ttu-id="fa5df-110">`out` 키워드를 제네릭 형식 매개 변수와 함께 사용하여 형식 매개 변수를 공변(covariant)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="fa5df-111">이 컨텍스트에서 `out` 키워드를 사용하는 방법에 대한 자세한 내용은 [out(제네릭 한정자)](out-generic-modifier.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa5df-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="fa5df-112">`out` 인수로 전달되는 변수는 메서드 호출에서 전달되기 전에 초기화할 필요가 없지만</span><span class="sxs-lookup"><span data-stu-id="fa5df-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="fa5df-113">호출된 메서드는 메서드가 반환되기 전에 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="fa5df-114">`in`, `ref` 및 `out` 키워드는 오버로드 해결을 위한 메서드 시그니처의 일부로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="fa5df-115">따라서 메서드 하나는 `ref` 또는 `in` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="fa5df-116">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="fa5df-117">그러나 다음과 같이 메서드 하나는 `ref`, `in` 또는 `out` 인수를 사용하고 다른 하나는 해당 한정자를 갖지 않는 경우에는 오버로드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="fa5df-118">컴파일러는 메서드 호출에 사용되는 매개 변수 한정자에 호출 사이트에서 매개 변수 한정자를 일치하여 적합한 오버로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>

<span data-ttu-id="fa5df-119">속성은 변수가 아니므로 `out` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="fa5df-120">다음과 같은 종류의 메서드에는 `in`, `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="fa5df-121">[async](./async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="fa5df-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="fa5df-122">[yield return](./yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="fa5df-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-parameters"></a><span data-ttu-id="fa5df-123">`out` 매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="fa5df-123">Declaring `out` parameters</span></span>

<span data-ttu-id="fa5df-124">`out` 인수를 사용하여 메서드를 선언하는 것은 여러 값을 반환하기 위한 일반적인 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-124">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="fa5df-125">C# 7.0부터 비슷한 시나리오에 대해 [튜플](../../tuples.md)을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="fa5df-125">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="fa5df-126">다음 예제에서는 `out`을 사용하여 단일 메서드 호출로 3개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-126">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="fa5df-127">세 번째 인수는 null에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-127">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="fa5df-128">따라서 메서드가 값을 선택적으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-128">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="fa5df-129">`out` 인수를 사용하여 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="fa5df-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="fa5df-130">C# 6 및 이전 버전에서는 `out` 인수로 전달하기 전에 별도 문에서 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="fa5df-131">다음 예제에서는 `number`Int32.TryParse[ 메서드에 전달되기 전에 ](xref:System.Int32.TryParse(System.String,System.Int32@))라는 변수를 선언합니다. 이 메서드는 문자열을 숫자로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="fa5df-132">C# 7.0부터 별도 변수 선언이 아니라 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="fa5df-133">이렇게 하면 보다 간결하고 읽기 쉬운 코드가 생성되며 메서드 호출 전에 실수로 변수에 값이 할당되는 경우를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="fa5df-134">다음 예제는 `number`Int32.TryParse[ 메서드 호출에서 ](xref:System.Int32.TryParse(System.String,System.Int32@)) 변수를 정의한다는 점을 제외하고 이전 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

<span data-ttu-id="fa5df-135">앞의 예제에서 `number` 변수는 `int`로 강력하게 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="fa5df-136">다음 예제와 같이 암시적 형식 지역 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5df-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="fa5df-137">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fa5df-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa5df-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa5df-138">See also</span></span>

- [<span data-ttu-id="fa5df-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fa5df-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fa5df-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fa5df-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fa5df-141">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fa5df-141">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="fa5df-142">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa5df-142">Method Parameters</span></span>](./method-parameters.md)
